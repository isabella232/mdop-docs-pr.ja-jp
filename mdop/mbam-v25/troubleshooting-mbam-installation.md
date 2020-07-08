---
title: MBAM 2.5 のインストールに関する問題のトラブルシューティング
description: MBAM 2.5 のインストールに関する問題のトラブルシューティングを行う方法について説明します。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812866"
---
# MBAM 2.5 のインストールに関する問題のトラブルシューティング

この記事では、スタンドアロン構成での Microsoft BitLocker 管理および監視 (MBAM) 2.5 インストールの問題のトラブルシューティング方法について説明します。

## トラブルシューティング用の MBAM ログファイルの参照

MBAM サーバーのインストール、クライアントのインストール、イベントのログが含まれます。 このログは、トラブルシューティングのために参照する必要があります。 
 
### MBAM サーバーインストールログファイル

MBAMServerSetup.exe は、MBAM のインストール中に、ユーザーの% temp% フォルダーに次のログファイルを生成します。<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14 番号> .log**

MBAMServerSetup.exe は、MBAM セットアップおよび MBAM サーバー機能のインストール時に実行された操作をログに記録します。<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi**

MBAMServerSetup.exe、インストール中に実行されたその他の操作を記録します。

### MBAM クライアントインストールログファイル

クライアントのインストールは、% temp% フォルダーの次のログファイル (またはクライアントのインストール方法に応じて、カスタムの場所) に記録されます。 <br />**MSI.DLL \<five random characters\>**

このログには、MBAM クライアントのインストール中に実行されるアクションが含まれています。
 
### MBAM クライアントイベント-ログチャネル

MBAM には、個別のイベントログチャネルがあります。 管理、分析、オペレーションの各ログファイルは、イベントビューアーの [**アプリケーションとサービスログ**] にあり  >  **Microsoft**  >  ます。 Microsoft**Windows**  >  **mbam**。

次の表では、各イベントログについて簡単に説明します。
 
|イベント ログ| 説明|
|----------|-------|
|Microsoft-Windows-MBAM/Admin|  エラーメッセージが表示される|
|Microsoft-Windows-MBAM/分析|   詳細なログ情報が含まれています|
|Microsoft-Windows-MBAM/Operational|    成功メッセージを含む|

### MBAM サーバーイベント-ログチャネル

ログファイルは、イベントビューアーの [**アプリケーションとサービス**] の下にある [  >  **Microsoft**  >  **Windows**  >  **mbam**] をログに記録します。 次の表は、MBAM 2.5 で導入されたサーバーイベントログを示しています。

|イベント ログ| 説明|
|--------|-------------|
|Microsoft-Windows-MBAM/Admin|  エラーメッセージが表示される|
|Microsoft-Windows-MBAM/分析|   詳細なログ情報が含まれています|
|Microsoft-Windows-MBAM/Operational|    成功メッセージを含む|

### MBAM web サービスログ

各 MBAM web サービスログは、ログ情報を SVCLOG ファイルに書き込みます。 既定では、各 web サービスは、C:\inetpub\Microsoft BitLocker 管理 Solution\Logs フォルダーでその名前を使用するフォルダーの下にトレースファイルを書き込みます。

サービストレースビューアーツール (Microsoft Visual Studio の一部) を使うと、svclog トレースを確認できます。

## 暗号化と報告に関する問題のトラブルシューティング

このセクションには、サーバー機能、クライアント機能、構成設定、既知の問題に関するトラブルシューティング情報が含まれています。
 
### MBAM クライアントのインストール、グループポリシーの設定

クライアントコンピューターに MBAM エージェントがインストールされているかどうかを確認します。 MBAM をインストールすると、[BitLocker 管理クライアントサービス] という名前のサービスが作成されます。 このサービスは、自動的に開始するように構成されています。 サービスが実行されているかどうかを確認します。

クライアントコンピューターに MBAM グループポリシー設定が適用されていることを確認します。 クライアントコンピューターにグループポリシー設定が適用されている場合は、次のレジストリサブキーが作成されます。 **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**

このキーが存在し、グループポリシー設定ごとの値を使用して設定されていることを確認します。

### 最初の遅延期間の MBAM エージェント

MBAM クライアントでは、インストール後すぐに操作を開始することはできません。 MBAM エージェントが操作を開始する前の初回ランダム遅延は 1 ~ 18 分です。 最初の遅延に加えて、少なくとも90分の遅延が発生します。 (遅延時間は、クライアントの状態を確認する頻度に対して構成されているグループポリシー設定によって異なります)。したがって、クライアントが操作を開始するまでの合計遅延時間は、*ランダムな起動遅延*  +  *クライアントチェック頻度の遅延*です。

Operational イベントログと管理イベントログが空白の場合、クライアントはまだ操作を開始せず、前に説明した遅延期間中です。 遅延を回避するには、次の手順を実行します。
 
1. BitLocker 管理クライアントサービスサービスを停止します。

2. **HKEY_LOCAL_MACHINE \software\microsoft\mbam** registry サブキーの下で、 **nostartupdelay**レジストリ値を作成し、その型を [ **REG_DWORD**] に設定して、その値を**1**に設定します。

3. [ **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**で、 **ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に設定します。 グループポリシーの更新がコンピューターにあると、これらの値は元の設定に戻ります。

4. BitLocker 管理クライアントサービスサービスを開始します。

サービスが開始された後、コンピューターにローカルにログインし、エラーがない場合は、1分以内にコンピューターを暗号化するように求めるメッセージが表示されます。 要求を受信しない場合は、すべてのエラーエントリについて MBAM 管理ログを確認する必要があります。

### コンピューターに TPM デバイスがないか、BIOS で TPM デバイスが有効になっていません

MBAM 管理イベントログを確認します。 MBAM 管理イベントログには、次のようなイベントエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

TPM 管理 (tpm) を開いて、コンピューターに TPM デバイスがあるかどうかを確認します。 Tpm にデバイスが表示されない場合は、デバイスマネージャー (devmgmt) を開いて、[セキュリティデバイス] の下にトラステッドプラットフォームモジュールがあるかどうかを確認します。 トラステッドプラットフォームモジュールデバイスが表示されない場合は、次のいずれかの理由で該当する可能性があります。

* お使いのシステムには、トラステッドプラットフォームモジュール (TPM/セキュリティ) デバイスがありません。

* TPM デバイスが BIOS で無効にされています。

* BIOS で TPM デバイスが有効になっていますが、BIOS でオペレーティングシステム設定からの TPM デバイスの管理が無効になっています。

* TPM デバイス用の Microsoft ドライバーを使用していない。 デバイスマネージャーに表示されているデバイスを確認して、Microsoft TPM デバイスドライバーを確認します。

TPM デバイスで C:\Windows\System32\tpm.sys ドライバーを使用していない場合は、C:\Windows\Inf\tpm.inf ファイルを選択してドライバーを更新する必要があります。

### コンピューターに有効なシステムパーティションがありません

MBAM 管理イベントログを確認します。 MBAM 管理イベントログには、次のようなイベントエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

BitLocker で暗号化を有効にするには、システムパーティションが必要です ([Windows 7 では、Bitlocker ドライブ暗号化](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)を有効にする方法についてよく寄せられる質問)。

MBAM システムパーティションは自動的には作成されません。 BitLocker ドライブ準備ユーティリティ (bdehdcfg.exe) を使用して、システムパーティションを作成し、必要なスタートアップファイルを移動することができます。

たとえば、コマンド **% windir% \system32\bdeHdCfg.exe (ターゲットの既定サイズの300– quiet** ) を使うと、mbam を展開してドライブを暗号化する前に、ドライブをサイレントモードで準備することができます。 これには再起動が必要です。 必要に応じて、アクションのスクリプトを作成することもできます。 次のドキュメントでは、BitLocker ドライブ準備ツールについて説明します。

[BitLocker ドライブ準備ツールの説明](https://support.microsoft.com/help/933246)

### ドライブは互換性のあるファイルシステムを持つように書式設定されていない

[BitLocker のファイルシステム要件につい](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)ては、TechNet の記事を参照してください。

### グループポリシーの競合

MBAM 管理イベントログには、次のようなイベントエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

グループポリシー設定を確認して、MBAM グループポリシー設定の間に競合している設定がないことを確認します。

グループポリシーは、MDOP MBAM テンプレートではなく、MDOP MBAM テンプレートを使って構成する必要があります。

以下に例を示します。

[オペレーティングシステムドライブの暗号化設定] で、プロテクターとして TPM を選択し、[**スタートアップの拡張 pin を許可**する] も選択しました。 TPM のみの保護で PIN が必要にならないため、これらは設定が競合しています。 そのため、拡張ピンの設定を無効にする必要があります。

### ユーザーが除外を要求した可能性があります

コンピューターの構成機能 \ Components\MDOP MBAM (BitLocker 管理) \ Client Management \ ユーザーの免税ポリシーのグループポリシー設定を有効にした場合、除外を要求するオプションがユーザーに提供されます。

既定では、ユーザーが除外を要求した場合、除外は7日間有効になり、その間、ユーザーは暗号化の確認メッセージを受信しません。 (ポリシー構成中は既定値を増減できます)。除外期間が終了すると、ユーザーに暗号化の確認を求めるメッセージが表示されます。

コンピューターがユーザーの例外の対象になっている場合、MBAM 管理イベントログに次のエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

コンピューターのユーザーの除外を手動で無効にする場合は、次の手順を実行します。
 
1. 次のレジストリサブキーで AllowUserExemption 値を**0**に設定します。 <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. **Agentversion**、**エンコード Computername**、**インストールされている**ものを除き、次のレジストリサブキーの下にあるすべてのレジストリ値を削除します。<br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM**

    **注**変更を有効にするには、MBAM agent を再起動する必要があります。

コンピューターにグループポリシーを適用すると、これらの値が元の設定に戻る場合があることに注意してください。

### WMI の問題

MBAM は、win32_encryptablevolume クラスのメソッドを使用して BitLocker を管理します。 このモジュールが登録されていないか破損している場合、MBAM クライアントは正しく動作しません。また、MBAM 管理イベントログに次のイベントエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

また、エラーコード0x8007007e で、回復とハードウェアのポリシーが適用されないことがあります。 これは、"指定されたモジュールが見つかりませんでした。" という意味です。

この問題を解決するには、次のコマンドを使用して**win32_encryptablevolume**クラスを登録する必要があります。

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## MBAM エージェントの通信に関する問題のトラブルシューティング

このセクションには、MBAM エージェントの通信に関連する次の問題に関するトラブルシューティング情報が含まれています。

### MBAM サービスの URL が正しくありません

MBAM コンプライアンス状態のサービスまたは回復とハードウェアサービスの値が正しくない場合は、クライアントコンピューターの MBAM 管理イベントログに次のようなイベントエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

クライアントコンピューターの次のレジストリサブキーの下にある**Keyrecoveryserviceendpoint**と**statusreportingserviceendpoint**の値を確認します。 <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

既定では、KeyRecoveryServiceEndPoint (MBAM Recovery および Hardware service endpoint) の URL は、次の形式になっています。 <br />
**http:// \<servername\> : \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

既定では、StatusReportingServiceEndpoint (MBAM Status reporting service エンドポイント) の URL は、次の形式になっています。<br />
**http:// \<servername\> : \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL にスペースを含めないでください。

サービスの URL が正しくない場合は、次のグループポリシー設定でサービス URL を修正する必要があります。

**コンピューターの構成**  > **ポリシー**  > **管理用テンプレート**  > **Windows コンポーネント**  > **MDOP MBAM (BitLocker 管理)**  > **クライアント管理**  > **MBAM サービスを設定する**

### MBAM 管理サーバーに影響を与える接続の問題

クライアントエージェントと MBAM 管理サーバーの間に接続の問題がある場合、MBAM agent はデータベースへの更新を投稿できません。 この場合、クライアントコンピューターの MBAM 管理イベントログに接続エラーのエントリが表示されます。

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

基本的なチェック:

* 名前と IP で MBAM 管理サーバーに ping を行って、基本的な接続を確認します。 Telnet または portqry を使って、MBAM 管理 web サイトまたはサービスポートに接続できるかどうかを確認します。

* MBAM 管理および監視サーバーで IIS サービスが実行されていること、および MBAM web サービスが MBAM クライアントコンピューター () で構成されている同じポートでリッスンしていることを確認し `netstat –ano | find "portnumber"` ます。

* MBAM web サイト用に構成されているポート番号が IIS Manager (inetmgr) を使用していることを確認します。 ポート番号がクライアントがリッスンしているポート番号と同じであることを確認します。 ポート番号が別のアプリケーションによって共有されていないことを確認します。 たとえば、サーバー上の別のアプリケーションでは、同じポートを使用しないようにします。

* ファイアウォールがある場合は、ファイアウォールまたはプロキシサーバーでポートが開かれていることを確認します。

* クライアントとサーバーの間の通信がセキュリティで保護されている場合は、有効な SSL 証明書を使用していることを確認してください。

* Web サーバーと、データを挿入するために送信するデータベースサーバーとの間のネットワーク接続を確認します。 ODBC データソース管理を使用して、web サーバーからデータベースサーバーへのデータベース接続を確認できます。 Sql server の接続のトラブルシューティング情報につい[ては、「Sql Server データベースエンジンへの接続に関するトラブルシューティング」を](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)参照してください。

#### 接続の問題のトラブルシューティング

クライアントで構成されているサービスの URL が正しいことを確認します。 レジストリから KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**) の URL の値をコピーして、Internet Explorer で開きます。

同様に、StatusReportingServiceEndpoint の URL の値 (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**) をコピーして、Internet Explorer で開きます。

> [!Note]
> クライアントコンピューターから URL を参照できない場合は、クライアントから IIS を実行しているサーバーへの基本的なネットワーク接続をテストする必要があります。 前のセクションの「1、2、3、4」を参照してください。

さらに、管理および監視サーバーのアプリケーションログでエラーを確認します。

クライアントとサーバー間のネットワークトレースを同時に行うことができます。トレースを確認して、クライアントエージェントと MBAM 管理サーバー間の接続エラーの原因を特定します。

> [!Note]
> クライアントコンピューターからサービス Url を参照できるが、MBAM 管理イベントログに接続エラーエントリがある場合は、管理サーバーとデータベースサーバーの間の接続エラーが原因である可能性があります。

両方のサービス Url に正常にアクセスでき、クライアントと実行されているサーバーの間に接続がある場合は、IIS が動作しています。 ただし、IIS を実行しているサーバーとデータベースサーバーの間の通信に問題がある可能性があります。

ネットワークの問題またはデータベース接続文字列の設定が正しくないため、MBAM サービスがデータベースサーバーに接続できない場合があります。 管理/監視サーバーでアプリケーションログを確認します。 ソース ASP.NET 2.0.50727.0 からのエラーエントリまたは警告が表示されることがあります。これは、次のようなログエントリに似ています。

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### 考えられる原因

##### 原因1

管理および監視サーバーコンポーネントのインストール中に、管理者が無効なデータベースインスタンス名またはデータベース名を指定している可能性があります。

IIS 管理コンソールを使用して、データベース接続文字列を確認して修正することができます。 これを行うには、IIS Manager を開き、Microsoft BitLocker の管理と監視に移動します。 左側に表示される各サービスについて、次の手順に従ってデータベース接続文字列を変更します。

1. [**機能] ビュー**で、[**接続文字列**] をダブルクリックします。

2. [**接続文字列**] ページで、変更する接続文字列を選びます。

3. [**操作**] ウィンドウで、[**編集**] を選びます。

4. [**接続文字列の編集**] ダイアログボックスで、変更するプロパティを変更して、[ **OK]** を選択します。

##### 原因2

ファイアウォールでブロックされている SQL Server ポート。 SQL Server がリッスンするように構成されているポート番号を確認し、管理サーバーとデータベースサーバー間のファイアウォールでポートが開かれていることを確認します。

##### 原因3

SQL server の TCP/IP バインドが正しくありません。 データベースサーバーの SQL Server 構成マネージャーで SQL TCP/IP バインドを確認します。 MBAM では、データベースへの接続に TCP/IP および名前付きパイププロトコルが有効になっている必要があります。

##### 原因4

NT Authority\Network Service アカウントまたは MBAM 管理サーバーのコンピューターアカウントには、SQL データベースに接続するために必要な権限がありません。

データベースサーバーにデータベースコンポーネントをインストールするときに、インストーラーは次の2つのローカルグループを作成します。 MBAM コンプライアンス監査データベースアクセスと MBAM 回復とハードウェアデータベースアクセス。

NT Authority\Network サービスアカウント、MBAM 管理サーバーのコンピューターアカウント、およびデータベースコンポーネントをインストールしたユーザーは、これらのグループに自動的に追加されます。

これらのグループには、インストール中にデータベースに必要なアクセス許可が付与されます。 このグループに参加しているすべてのユーザーは、データベースに対して必要なアクセス許可を自動的に受け取ります。

次の条件の1つ以上が該当する場合、アクセス許可の問題が原因で、web サービスがデータベースサーバーに接続されないことがあります。

* 前に説明したグループは、データベースサーバーのローカルグループから削除されます。

* NT Authority\Network サービスアカウントと MBAM 管理サーバーのコンピューターアカウントは、これらのグループのメンバーではありません。

* これらのグループには、データベースに対する必要なアクセス許可がありません。

以前の条件のいずれかが満たされている場合、MBAM 管理および監視サーバーのアプリケーションログでアクセス許可に関連するエラーが発生します。 その場合は、NT Authority\Network Service アカウントと MBAM 管理サーバーのコンピューターアカウントを手動で追加し、SQL Server Management Studio () を使用している SQL データベースサーバーでサーバー全体のパブリックロールを付与する必要があり https://msdn.microsoft.com/library/aa337562.aspx) ます。

#### Web サービスのログを確認する

MBAM 管理サーバーのアプリケーションログにイベントが記録されていない場合は、MBAM 管理と監視サーバーでホストされている MBAM web サービスの web サービスログ (svclog) を確認します。 ログファイルを表示するには、サービストレースビューアーツール (SvcTraceViewer.exe) を使用する必要があり https://msdn.microsoft.com/library/ms732023.aspx ます。

主に、Recoveryandハードウェアサービスと ComplianceStatusService のサービストレースログを調査する必要があります。 既定では、web サービスログは C:\inetpub\Microsoft BitLocker 管理 Solution\Logs フォルダーにあります。 各サービスは、それぞれのフォルダーの下に svclog ファイルを書き込みます。

サービスのトレースログで、エラーまたは警告エントリのアクティビティを確認します。 既定では、エラーエントリは赤で強調表示されています。 エラーエントリの詳細情報を表示するには、トレースビューアーの右側のウィンドウでエラーの説明を選択します。 トレースログからのエラーエントリの例を次に示します。

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## MBAM インフラストラクチャの再インストールまたは再構成

MBAM インフラストラクチャを再インストールまたは再構成するには、次の点を把握しておく必要があります。

* アプリケーションプールアカウント

* MBAM Groups (ヘルプデスク、詳細、レポートユーザーグループ)

* MBAM レポート URL

* SQL Server 名とデータベース名

* MBAM ReadWrite および ReadOnly アカウント

### アプリケーションプールアカウント

アプリケーションプールアカウントを見つけるには、MBAM Web サーバーにログオンし、**インターネットインフォメーションサービス (IIS) マネージャー**を開いて、[**アプリケーションプール**] を選びます。

![アプリケーションプール](images/troubleshooting-MBAM-installation-1.png)

このアカウントでサービスプリンシパル名 (SPN) を設定する必要があります。 この設定は、MBAM の機能に非常に重要です。

### MBAM グループ (ヘルプデスク、詳細、レポートユーザーグループ、レポート URL)

![MBAM グループ](images/troubleshooting-MBAM-installation-2.png)

これには、ヘルプデスクグループ、上級のヘルプデスクグループ、レポートユーザーグループ、MBAM レポート URL などの情報が記載されています。 MBAM レポート URL は、MBAM セットアップで指定する必要があります。「http (s)://servername/ReportServer.」と入力する必要があります。

### SQL Server 名とデータベース (DB) 名

MBAM Db をホストしている SQL Server 名とインスタンスを検索するには、MBAM Web (IIS) サーバーにログオンし、次のレジストリサブキーを参照します。

**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM \ Web**

![Regedit.exe](images/troubleshooting-MBAM-installation-3.png)

強調表示されている部分は接続文字列です。 SQL Server 名、データベース名、およびインスタンス (名前付きの場合) を指定する必要があります。

### MBAM ReadWrite および ReadOnly アカウント

この情報は、web サーバーの名前が既に存在する SQL Server データベースに表示されます。

#### ReadWrite アカウント

1. SQL Management Studio にログインします。

2. [ **Mbam 回復とハードウェア**] を右クリックし、[**プロパティ**] を選択して、[**アクセス許可**] を選択します。

たとえば、ラボアカウント名は**Mbamwrite**です。 アプリケーションプールと ReadWrite のアカウントが同じになるように設定されています。

![SQL DB](images/troubleshooting-MBAM-installation-4.png)

![DB プロパティ](images/troubleshooting-MBAM-installation-5.png)

SQL Management Studio で [**セキュリティ**]、[**ログイン**] の順に移動します。 前のスクリーンショットに示されているアカウントに移動します。

![SQL セキュリティ](images/troubleshooting-MBAM-installation-6.png)

アカウントを右クリックし、[**プロパティマッピング**] に移動して、Mbam Recovery とハードウェアデータベースを探します。

![ユーザーマッピング](images/troubleshooting-MBAM-installation-7.png)

#### 読み取り専用アカウント

SSRS サーバーで SQL Server Reporting Services 構成マネージャーを開きます。 [**レポートマネージャーの url**] を選択し、次に**url**を参照します。

![レポートマネージャー](images/troubleshooting-MBAM-installation-8.png)

**Microsoft Bitlocker の管理と監視**を選択します。

![Bitlocker の管理と監視](images/troubleshooting-MBAM-installation-9.png)

[ **MaltaDatasource**] を選択します。

![Db](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource には ReadOnly アカウント名が必要であり、MBAM セットアップで使用する必要があります。

## リファレンス

詳細については、次の記事を参照してください。

[スタンドアロン構成で MBAM 2.5 を展開する](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker Administration and Monitoring 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
