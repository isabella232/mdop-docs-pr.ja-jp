---
title: MBAM 2.0 のリリース ノート
description: MBAM 2.0 のリリース ノート
author: dansimp
ms.assetid: c3f16cf3-94f2-47ac-b3a4-3dc505c6a8dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d5d3c7d539cf2828d28c1844321bc34ab7736ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825587"
---
# MBAM 2.0 のリリース ノート


これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

Microsoft BitLockerAdministration および Monitoring (MBAM) 2.0 をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、BitLockerAdministration と Monitoring 2.0 を正常にインストールするために必要な情報が含まれています。また、製品ドキュメントでは提供されていない情報が含まれています。 リリースノートとその他の MBAM 2.0 のドキュメントの違いが異なる場合は、最新の変更を、権限のあるものとして扱う必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## <a href="" id="---------mbam-2-0-known-issues"></a> MBAM 2.0 の既知の問題


このセクションには、MBAM 2.0 のリリースノートが含まれています。

### Microsoft System Center Configuration Manager 2007 で MBAM を実行すると、[コンピューター名] フィールドが BitLocker コンピューターのコンプライアンスおよび BitLocker Enterprise コンプライアンスの詳細レポートに表示されない場合がある

Configuration Manager 2007 で MBAM を使用している場合、[コンピューター名] フィールドは、BitLocker コンピューターのコンプライアンスと BitLocker Enterprise コンプライアンスの詳細レポートで空白になることがあります。

回避策: なし。

### スタンドアロンの MBAM サーバーインフラストラクチャをアップグレードした後、エンタープライズコンプライアンスレポートの更新に失敗する

MBAM スタンドアロントポロジを使用していて、サーバーインフラストラクチャをバージョン1.0 から2.0 にアップグレードした場合、エンタープライズコンプライアンスレポートの更新に失敗します。

対応策: アップグレード後に、コンプライアンスと監査データベースに対して次のスクリプトを実行します。

```sql
-- =============================================
-- Script Template
-- =============================================

DECLARE @DatabaseName nvarchar(255);
SET @DatabaseName = DB_NAME()

USE msdb;

DECLARE @JobID BINARY(16)
SELECT @JobID = job_id
FROM msdb.dbo.sysjobs
WHERE (name = N'CreateCache')

if (@JobID IS NOT NULL)
BEGIN
    EXEC dbo.sp_delete_job
         @job_name = N'CreateCache';
END

EXEC dbo.sp_add_job
    @job_name = N'CreateCache',
    @enabled = 1;

EXEC dbo.sp_add_jobstep
     @job_name = N'CreateCache',
     @step_name = N'Copy Data',
     @subsystem = N'TSQL',
     @command = N'EXEC [ComplianceCore].UpdateCache',
     @database_name = @DatabaseName,
     @retry_attempts = 5,
     @retry_interval = 5;


EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 010000,
     @active_end_time = 020000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 070000,
     @active_end_time = 080000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 130000,
     @active_end_time = 140000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1pm';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 190000,
     @active_end_time = 200000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7pm';

EXEC dbo.sp_add_jobserver
     @job_name = N'CreateCache';
```

### ヘルプデスクポータルのレポートでは、SSL が SSRS で構成されていない場合は警告が表示される

SQL Server Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーをインストールするときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。 次に、ヘルプデスクポータルを参照してレポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。

回避策: レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。 この問題に対処するには、SQL Server Reporting Services がインストールされている MBAM コンピューターにアクセスし、 **Reporting Services 構成マネージャー**を実行してから、[ **WEB サービスの URL**] をクリックします。 サーバーに適切な SSL 証明書を選択し、適切な SSL ポート (既定のポートは 443) を入力して、[**適用**] をクリックします。

### Configuration Manager データベースの既定以外のインスタンスはサポートされていません

MBAM は、Configuration Manager 2007 と SystemCenter2012 ConfigurationManager の Configuration Manager データベースの既定のインスタンスのみを検索します。 既定以外のインスタンスを使用している場合、MBAM をインストールすることはできません。

回避策: なし。

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a>コンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生することがある

コンプライアンスの概要レポートにドリルダウンして、SSRS レポートの [**戻る**] リンクをクリックすると、エラーがスローされることがあります。

回避策: なし。

### 使用領域のみの暗号化が正常に動作しない

MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシーオブジェクトを設定していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。 MBAM クライアントをインストールするときにコンピューターが既に暗号化されていて、同じグループポリシーオブジェクトを設定している場合、暗号化は正常に動作し、コンピューター上で使用されているディスク領域だけが暗号化されます。

回避策: なし。

### コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない

**[ドライブの暗号化方法の選択] および [暗号強度**] グループポリシーオブジェクトで特定の暗号強度を設定しなかった場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジ内のコンピューターのコンプライアンスレポートでは、暗号強度に対して "unknown" が常に表示されます。 グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。

回避策: **[ドライブの暗号化方法を選択してください] および [暗号強度**] グループポリシーオブジェクトで、常に特定の暗号強度を設定します。

### ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される

SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。

回避策: なし。 MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。

### セキュリティの構成を強化すると、レポートが正しく表示されない場合がある

Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"アクセス拒否" というメッセージが表示されることがあります。 既定では、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対してサーバーの脅威が減ることで、サーバーを保護するために ESC が有効になっています。

回避策: MBAM サーバーでレポートを表示しようとしたときに "アクセス拒否" メッセージが表示される場合は、グループポリシーオブジェクトを設定するか、イメージ内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。 また、ESC が有効になっていない別のコンピューターからレポートを表示することもできます。

### SQL Server 2008 から SQL Server 2012 にアップグレードした場合、MBAM サーバーのインストールが失敗する

SQL Server 2008 から SQL Server 2012 にアップグレードして、コンプライアンスおよび監査データベースまたは回復データベースをインストールしようとすると、インストールが失敗してロールバックされます。 このエラーは、必要な SQLCMD.exe ファイルが SQL アップグレード中に削除され、MBAM インストーラーで見つからないために発生します。 MSI ログファイルの行は、次のようになります。

RunDbInstallScript 回復データベース CA: BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery データベース ca: dbInstance-xxxxxx\\I01RunDbInstallScript Recovery データベース CA: sqlScript-_Recovery at ¥ \ _and \ _HardwareRunDbInstallScript 回復用データベース CA: defaultFileName-MBAM \ _Recovery \ _and \ _HardwareRunDbInstallScript 回復データベース CA: defaultDataPath-F:\\MSSQL\\MSSQL10. をしてください。I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath-K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01 "" という管理および Monitoring\\ Setup\\ key_and _Recovery recoveryDefaultDataPath \ _Hardware "DefaultFileName =" MBAM \ _Recovery \ _and \ _Hardware "F:\\MSSQL\\MSSQL10. =" (\ \ \ \ "="I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript Recovery Db CA: 回復データベースの実行を開始します。回復用データベースのインストール scriptRunDbInstallScript 回復用データベース ca 例外: 回復用データベースのインストールカスタムアクションコマンドライン出力例外: 指定したファイルが見つからない

MBAM Server Windows Installer では、HKLM\\Software\\Microsoft\\Microsoft SQL Server ¥¥¥¥¥¥¥¥の [Path 文字列] の値を確認することで、SQLCMD.exe パスをハードコーディングすることができます。 Sql Server 2008 から SQL Server 2012 への移行中にキーは引き続き存在しますが、SQL アップグレードのプロセスによってファイルが削除されたため、データ値によって参照されるパスに SQLCMD.exe ファイルが含まれていません。

回避策: HKLM\\Software\\Microsoft\\Microsoft SQL server \\ 100\\ ¥¥の名前を**Path \ _old**に一時的に変更してから、Mbam Server Windows インストーラーを再実行します。 インストールが正常に完了し、SQL Server 2012 でデータベースが作成されたら、 **_Old path**の値を**path**に変更します。

## MBAM 2.0 の修正プログラムとサポート技術情報の記事


このセクションには、MBAM 2.0 の修正プログラムとサポート技術情報の記事が含まれています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>サポート技術情報の記事</strong></th>
<th align="left">タイトル</th>
<th align="left"><strong>リンク</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2831166</p></td>
<td align="left"><p>Microsoft BitLocker の管理と監視 (MBAM) 2.0 のインストールで、 &quot; 既にインストールされている System CENTER CM オブジェクトがエラーになる&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)">support.microsoft.com/kb/2831166/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870849</p></td>
<td align="left"><p>MBAM 2.0 セルフサービスポータルを使用して、ユーザーが BitLocker 回復キーを取得できない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)">support.microsoft.com/kb/2870849/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2756402</p></td>
<td align="left"><p>MBAM クライアントでイベント ID 4 およびエラーコード0x8004100E が表示されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620287</p></td>
<td align="left"><p>MBAM で [レポート] タブをクリックしたときに表示される "/レポート" というエラーメッセージ "サーバーエラー"</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)">support.microsoft.com/kb/2620287/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>MBAM で Enterprise またはコンピューターのコンプライアンスレポートを開くときにエラーが発生する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM Enterprise レポートが更新されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2712461</p></td>
<td align="left"><p>ドメインコントローラーでの MBAM のインストールはサポートされていません</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)">support.microsoft.com/kb/2712461/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2876732</p></td>
<td align="left"><p>MBAM 2.0 の単体または Configuration Manager の統合セットアップ中にエラーコード0x80071a90 が表示される</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)">support.microsoft.com/kb/2876732/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2754259</p></td>
<td align="left"><p>MBAM とセキュリティで保護されたネットワーク通信</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)">support.microsoft.com/kb/2754259/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>SQL Server 2008 での Configuration Manager の統合シナリオ中に MBAM 2.0 セットアップが失敗する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2668533</p></td>
<td align="left"><p>SQL SSRS が適切に構成されていない場合、MBAM セットアップが失敗する</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)">support.microsoft.com/kb/2668533/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870847</p></td>
<td align="left"><p>MBAM 2.0 のセットアップで &quot; &#39;Reporting Services ポイント&#39; ロールの Configuration Manager サーバーの役割設定を取得するときにエラーが発生する&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)">support.microsoft.com/kb/2870847/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2870839</p></td>
<td align="left"><p>Mbam 2.0 Enterprise レポートが、SQL ジョブ CreateCache エラーのために MBAM 2.0 スタンドアロントポロジで更新されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)">support.microsoft.com/kb/2870839/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM Enterprise レポートが更新されない</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2935997</p></td>
<td align="left"><p>MBAM サポートされているコンピューターのコンプライアンスレポートにサポートされない製品が含まれている</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)">support.microsoft.com/kb/2935997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2612822</p></td>
<td align="left"><p>MBAM でコンピューターレコードが拒否される</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)">support.microsoft.com/kb/2612822/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 2.0 の概要](about-mbam-20-mbam-2.md)

 

 





