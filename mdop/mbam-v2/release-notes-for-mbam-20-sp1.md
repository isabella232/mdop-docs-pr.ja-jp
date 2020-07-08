---
title: MBAM 2.0 SP1 のリリース ノート
description: MBAM 2.0 SP1 のリリース ノート
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825584"
---
# MBAM 2.0 SP1 のリリース ノート


これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。

Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) をインストールする前に、これらのリリースノートをよくお読みください。 これらのリリースノートには、BitLocker の管理と2.0 監視を行うために必要な情報が記載されています。また、これらの情報には、製品ドキュメントでは提供されていない情報が含まれています。 これらのリリースノートとその他の MBAM 2.0 SP1 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。 これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> MBAM 2.0 SP1 の既知の問題


このセクションでは、MBAM 2.0 SP1 の既知の問題について説明します。

### Configuration Manager の統合トポロジを使用した MBAM から MBAM 2.0 SP1 へのアップグレードは、Configuration Manager オブジェクトを手動で削除する必要がある

MBAM を Configuration Manager で使用していて、MBAM 2.0 SP1 にアップグレードする場合は、MBAM インストールの一部として構成マネージャーにインストールされたすべての Configuration Manager オブジェクトを手動で削除する必要があります。 手動で削除する必要があるオブジェクトは、MBAM レポート、MBAM サポートされているコンピューターのコレクション、および BitLocker 保護構成基準と関連する構成項目です。

**回避策**: 次の手順を実行して、Configuration Manager オブジェクトをアップグレードします。

1.  次の手順で説明するように、既存のコンプライアンスデータを外部ファイルにバックアップします。

    **注** 既存のすべての BitLocker コンプライアンスデータは、Configuration Manager で既存のベースラインを削除すると削除されます。 データは随時再生成されますが、コンプライアンスデータが再生成される前に、特定のコンピューターのコンプライアンスデータが必要になった場合に備えて、データのコピーを保存することをお勧めします。

     

    1.  BitLocker のコンプライアンスデータの履歴を保存するには、[ **Bitlocker Enterprise コンプライアンスの詳細**] レポートを開きます。

    2.  レポートの [**保存**] アイコンをクリックし、[ **Excel**] を選択します。

        保存されたレポートには、コンピューター名、ドメイン名、コンプライアンスの状態、除外、デバイスユーザー、コンプライアンスステータスの詳細、最終連絡先の日付/時刻などのデータが含まれます。 詳細なボリューム情報や暗号化の強度など、一部の情報は保存されません。

2.  **Mbam**インストーラーを使用して、サーバーから**mbam**をアンインストールします。

3.  次のオブジェクトを Configuration Manager から手動で削除します。

    -   MBAM サポートされているコンピューターコレクション

    -   BitLocker の保護のベースライン

    -   BitLocker オペレーティングシステムのドライブ保護構成項目

    -   BitLocker 固定データドライブ保護構成項目

4.  Configuration Manager SQL Server Reporting Services サイトで、[MBAM Reports] フォルダーを手動で削除します。 これには、次の手順を実行します。

    1.  Internet Explorer を使用して、http://(cmserver/レポート) などのレポートサービスポイントを参照し &lt; &gt; ます。

    2.  適切な Configuration Manager サイトコードのリンクをクリックします。

    3.  MBAM フォルダーを削除します。

5.  MBAM サーバーインストーラーを使って Configuration Manager の統合オブジェクトを再インストールします。 クライアントコンピューターは、時間を経て BitLocker コンプライアンスデータをもう一度アップロードし始めます。

### セルフサービスポータルの [送信] ボタンがインターネット Explorer10 で動作しない

インターネット Explorer10 を使用して管理と監視の Web サイトにアクセスしても、web サイトの [**送信**] ボタンが機能しません。

**対応策**: 管理と監視の web サイトをインストールしたサーバーで、 [ASP.NET browser 定義ファイルの修正プログラム](https://go.microsoft.com/fwlink/?LinkId=317798)をインストールします。

### 国際ドメイン名はサポートされていません

MBAM 2.0 SP1 は、国際ドメイン名をサポートしていません。

**回避策**: なし。

### 管理と監視の web サイトにあるレポートで、SSL が SSRS で構成されていない場合は警告が表示される

SQLServer Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーをインストールするときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。 次に、管理と監視の web サイトを参照してレポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。

**対応策**: この問題を修正するには、SQLServer Reporting services がインストールされている mbam サーバー上の**Reporting Services 構成マネージャー**で SSL を構成します。 管理と監視サーバーの web サイトをアンインストールしてから再インストールします。

### コンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生する場合がある

コンプライアンスの概要レポートにドリルダウンしている場合、SSRS レポートの [**戻る**] リンクをクリックすると、エラーが発生する可能性があります。

**回避策**: なし。

### 使用領域のみの暗号化が正常に動作しない

MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシーオブジェクトを設定していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。 MBAM クライアントをインストールする前に、使われているスペースのみの暗号化でコンピューターが暗号化されていて、同じ使用スペース専用の暗号化グループポリシーオブジェクトを設定している場合、MBAM は設定を認識し、コンプライアンスレポートで暗号化を正しく報告します。

**回避策**: なし。

### コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない

**[ドライブの暗号化方法の選択] と [暗号強度**] のグループポリシーオブジェクトで特定の暗号強度を設定しない場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジ内のコンピューターのコンプライアンスレポートは常に、暗号強度の**不明な**状態で表示されます。 グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。

**回避策**: **[ドライブの暗号化方法を選択してください] および [暗号強度**] グループポリシーオブジェクトで、常に特定の暗号強度を設定します。

### ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される

SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。

**回避策**: なし。 MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。

### セキュリティの構成を強化すると、レポートが正しく表示されない場合がある

Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"**アクセス拒否**" というメッセージが表示されることがあります。 既定では、強化されたセキュリティ構成は、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対するサーバーの脅威を減らすことによって、サーバーを保護するために有効になっています。

**対応策**: Mbam サーバーでレポートを表示しようとしたときに、**アクセス拒否**メッセージが表示される場合は、グループポリシーオブジェクトを設定するか、または画像内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。 または、強化されたセキュリティ構成が有効になっていない別のコンピューターからレポートを表示することもできます。

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> SQLServer2008 から SQLServer2012 にアップグレードすると、MBAM サーバーのインストールが失敗する

SQLServer2008 から SQLServer2012 にアップグレードして、コンプライアンスおよび監査データベースまたは回復データベースをインストールしようとすると、インストールが失敗してロールバックされます。 このエラーは、必須の SQLCMD.exe ファイルが SQLServer のアップグレード中に削除され、MBAM インストーラーで見つからないために発生します。 MSI ログファイルの行は、次のようになります。

RunDbInstallScript 回復データベース CA: BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery データベース ca: dbInstance-xxxxxx\\I01RunDbInstallScript Recovery データベース CA: sqlScript-_Recovery at ¥ \ _and \ _HardwareRunDbInstallScript 回復用データベース CA: defaultFileName-MBAM \ _Recovery \ _and \ _HardwareRunDbInstallScript 回復データベース CA: defaultDataPath-F:\\MSSQL\\MSSQL10. をしてください。I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath-K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01 "" という管理および Monitoring\\ Setup\\ key_and _Recovery recoveryDefaultDataPath \ _Hardware "DefaultFileName =" MBAM \ _Recovery \ _and \ _Hardware "F:\\MSSQL\\MSSQL10. =" (\ \ \ \ "="I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript Recovery Db CA: 回復データベースの実行を開始します。回復用データベースのインストール scriptRunDbInstallScript 回復用データベース ca 例外: 回復用データベースのインストールカスタムアクションコマンドライン出力例外: 指定したファイルが見つからない

MBAM Server Windows Installer は、HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup. の下にあるレジストリの Path 文字列の値を確認することにより、SQLCMD.exe パスをハードコーディングしています。 このキーは、SQLServer2008 から SQLServer2012 への移行時にも表示されますが、データ値によって参照されるパスには、ファイルが削除されているため、SQLCMD.exe ファイルは含まれません。

**回避策**: HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 文字列値の名前を**path \ _old**に一時的に変更してから、Mbam サーバーで Windows インストーラーを実行します。 インストールが正常に完了し、SQLServer2012 でデータベースが作成されたら、 **_Old path**の名前を**path**に変更します。

## MBAM 2.0 SP1 のホットフィックスとサポート技術情報の記事


このセクションには、MBAM 2.0 SP1 の修正プログラムとサポート技術情報の記事が含まれています。

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


[MBAM 2.0 SP1 の概要](about-mbam-20-sp1.md)

 

 





