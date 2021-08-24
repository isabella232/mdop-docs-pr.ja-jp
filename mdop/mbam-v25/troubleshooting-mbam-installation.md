---
title: MBAM 2.5 のインストールに関する問題のトラブルシューティング
description: MBAM 2.5 インストールの問題をトラブルシューティングする方法について説明します。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 6ea152792801c630fa365f37d1668d1a4d84b3a5
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910632"
---
# <a name="troubleshooting-mbam-25-installation-problems"></a>MBAM 2.5 のインストールに関する問題のトラブルシューティング

この記事では、スタンドアロン構成での Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 インストールの問題をトラブルシューティングする方法について説明します。

## <a name="referring-mbam-log-files-for-troubleshooting"></a>トラブルシューティングのための MBAM ログ ファイルの参照

MBAM には、サーバーインストール、クライアント インストール、およびイベントのログが含まれます。 このログは、トラブルシューティングのために参照する必要があります。 
 
### <a name="mbam-server-installation-log-files"></a>MBAM サーバーのインストール ログ ファイル

MBAMServerSetup.exe MBAM のインストール中に、ユーザーの %temp% フォルダーに次のログ ファイルが生成されます。<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<.log の 14>番号**

MBAMServerSetup.exe MBAM セットアップおよび MBAM サーバー機能のインストール中に実行されたアクションをログに記録します。<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log**

MBAMServerSetup.exe中に実行された追加のアクションをログに記録します。

### <a name="mbam-client-installation-log-file"></a>MBAM クライアント インストール ログ ファイル

クライアント のインストールは、%temp% フォルダー (またはクライアントのインストール方法に応じて、カスタムの場所) の次のログ ファイルに記録されます。 <br />**MSI \<five random characters\> .log**

このログには、MBAM クライアントのインストール中に実行されるアクションが含まれます。
 
### <a name="mbam-client-event-logging-channel"></a>MBAM クライアント イベント ログ チャネル

MBAM には、個別のイベント ログ チャネルがあります。 管理者、分析ログ、および運用ログ ファイルは、イベント ビューアーの****[アプリケーションとサービス ログ Microsoft Windows  >  ****  >  ****  >  **MBAM です**。

次の表に、各イベント ログの簡単な説明を示します。
 
|イベント ログ| 説明|
|----------|-------|
|Microsoft-Windows-MBAM/Admin|  エラー メッセージが含まれます|
|Microsoft-Windows-MBAM/Analytic|   高度なログ情報が含まれる|
|Microsoft-Windows-MBAM/運用|    成功メッセージが含まれます|

### <a name="mbam-server-event-logging-channel"></a>MBAM サーバーのイベント ログ チャネル

ログ ファイルは、イベント ビューアーの [**** アプリケーションとサービス ログ] の下にある Microsoft Windows  >  ****  >  ****  >  **MBAM です**。 次の表に、MBAM 2.5 で導入されたサーバー イベント ログを示します。

|イベント ログ| 説明|
|--------|-------------|
|Microsoft-Windows-MBAM/Admin|  エラー メッセージが含まれます|
|Microsoft-Windows-MBAM/Analytic|   高度なログ情報が含まれる|
|Microsoft-Windows-MBAM/運用|    成功メッセージが含まれます|

### <a name="mbam-web-service-logs"></a>MBAM Web サービス ログ

各 MBAM Web サービス ログは、ログ情報を SVCLOG ファイルに書き込みます。 既定では、各 Web サービスは、C:\inetpub\Microsoft BitLocker 管理ソリューション\Logs フォルダー内の名前を使用するフォルダーの下にトレース ファイルを書き込みます。

サービス トレース ビューアー ツール (Microsoft Visual Studio) を使用して、svclog トレースを確認できます。

## <a name="troubleshooting-encryption-and-reporting-issues"></a>暗号化とレポートの問題のトラブルシューティング

このセクションには、サーバー機能、クライアント機能、構成設定、および既知の問題に関するトラブルシューティング情報が含まれる。
 
### <a name="mbam-client-installation-group-policy-settings"></a>MBAM クライアントのインストール、グループ ポリシーの設定

MBAM エージェントがクライアント コンピューターにインストールされているかどうかを確認します。 MBAM がインストールされている場合、BitLocker Management Client Service という名前のサービスが作成されます。 このサービスは、自動的に開始するように構成されています。 サービスが実行されているかどうかを確認します。

MBAM グループ ポリシーの設定がクライアント コンピューターに適用されている必要があります。 グループ ポリシーの設定がクライアント コンピューターに適用されている場合は、次のレジストリ サブキーが**作成**されます。HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement

このキーが存在し、グループ ポリシー設定ごとに値を使用して設定することを確認します。

### <a name="mbam-agent-in-the-initial-delay-period"></a>初期遅延期間の MBAM エージェント

MBAM クライアントは、インストール後すぐに操作を開始しない。 MBAM エージェントが操作を開始する 1 ~ 18 分前の初期ランダム遅延があります。 初期遅延に加えて、少なくとも 90 分の遅延があります。 (遅延は、クライアントの状態を確認する頻度に構成されているグループ ポリシー設定によって異なります)。したがって、クライアントが操作を開始する前の合計遅延は、ランダム*な*起動遅延  +  *クライアントのチェック頻度遅延です*。

[操作] イベント ログと [管理] イベント ログが空白の場合、クライアントはまだ操作を開始していないので、前述の遅延期間です。 遅延をバイパスする場合は、次の手順を実行します。
 
1. BitLocker 管理クライアント サービス サービスを停止します。

2. [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM**** レジストリ サブキーで **、NoStartupDelay**レジストリ値を作成し、その種類を REG_DWORD に設定し、その**値**を 1 に**設定します**。

3. **[HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement、 ** **ClientWakeupFrequency**と**StatusReportingFrequency**の値を**1 に設定します**。 これらの値は、グループ ポリシーの更新プログラムがコンピューターに適用された後、元の設定に戻されます。

4. BitLocker 管理クライアント サービス サービスを開始します。

サービスの開始後、コンピューターでローカルにログインし、エラーがない場合は、1 分以内にコンピューターを暗号化する要求を受け取る必要があります。 要求を受信しない場合は、エラー エントリについて MBAM 管理者ログを確認する必要があります。

### <a name="computer-does-not-have-a-tpm-device-or-the-tpm-device-is-not-enabled-in-the-bios"></a>コンピューターに TPM デバイスが存在しないか、BIOS で TPM デバイスが有効になっていない

MBAM Admin イベント ログを確認します。 MBAM Admin イベント ログには、次のようなイベント エントリが表示されます。

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

TPM 管理 (tpm.msc) を開き、コンピューターに TPM デバイスがあるかどうか確認します。 tpm.msc にデバイスが表示されない場合は、[デバイス マネージャー] (devmgmt.msc) を開き、[セキュリティ デバイス] の [信頼できるプラットフォーム モジュール] を確認します。 信頼できるプラットフォーム モジュール デバイスが表示されない場合は、次のいずれかの理由でこれが当てはまる可能性があります。

* システムに信頼できるプラットフォーム モジュール (TPM/セキュリティ) デバイスが存在しない。

* BIOS で TPM デバイスが無効になっています。

* TPM デバイスは BIOS で有効になっていますが、BIOS ではオペレーティング システム設定からの TPM デバイスの管理が無効になっています。

* TPM デバイスに Microsoft ドライバーを使用していない。 デバイス マネージャーに一覧表示されているデバイスを確認して、Microsoft TPM デバイス ドライバーを識別します。

TPM デバイスがコンピューター ドライバーを使用していないC:\Windows\System32\tpm.sys、C:\Windows\Inf\tpm.inf ファイルを選択してドライバーを更新する必要があります。

### <a name="computer-does-not-have-a-valid-system-partition"></a>コンピューターに有効な SYSTEM パーティションが存在しない

MBAM Admin イベント ログを確認します。 MBAM Admin イベント ログには、次のようなイベント エントリが表示されます。

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

BitLocker では、暗号化を有効にするには SYSTEM パーティションが必要です (BitLocker ドライブの暗号化は、Windows[7: よく寄せられる](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)質問)。

MBAM はシステム パーティションを自動的に作成しない。 BitLocker ドライブ準備ユーティリティ (bdehdcfg.exe) を使用して、システム パーティションを作成し、必要なスタートアップ ファイルを移動できます。

たとえば、コマンド **%windir%\system32\bdeHdCfg.exe -target default -size 300 –quiet** を使用して、MBAM を展開してドライブを暗号化する前に、ドライブをサイレントモードで準備できます。 これには再起動が必要です。 必要に応じて、アクションをスクリプト化することもできます。 次のドキュメントでは、BitLocker ドライブ準備ツールについて説明します。

[BitLocker ドライブ準備ツールの説明](https://support.microsoft.com/help/933246)

### <a name="drives-are-not-formatted-to-have-a-compatible-file-system"></a>互換性のあるファイル システムを持つドライブの形式が設定されていない

[BitLocker のファイル システム要件については、TechNet の記事を参照してください](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)。

### <a name="group-policy-conflict"></a>グループ ポリシーの競合

MBAM Admin イベント ログには、次のようなイベント エントリが表示されます。

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

グループ ポリシー設定を確認して、MBAM グループ ポリシー設定の間で競合する設定が設定されていないことを確認します。

BitLocker ドライブ暗号化テンプレートではなく、MDOP MBAM テンプレートを使用してグループ ポリシーを構成する必要があります。

以下に例を示します。

[オペレーティング システム ドライブの暗号化設定] で、保護機能として [TPM] を選択し、[スタートアップに拡張 PIN を許可する **] も選択しました**。 TPM のみの保護では PIN が必要ないので、これらは競合する設定です。 したがって、拡張 PIN の設定を無効にする必要があります。

### <a name="user-may-have-requested-an-exemption"></a>ユーザーが除外を要求した可能性がある

コンピューター構成\管理用テンプレート\Windows Components\MDOP MBAM (BitLocker Management)\Client Management\Configure user exemption policy Group Policy setting を有効にした場合、ユーザーには除外を要求するオプションが提供されます。

既定では、ユーザーが除外を要求した場合、除外は 7 日間有効であり、この期間中は暗号化を求めるメッセージはユーザーに表示されません。 (既定値は、ポリシーの構成中に増減できます)。除外期間が終了すると、ユーザーは暗号化を求めるメッセージが表示されます。

コンピューターがユーザーの除外対象である場合、MBAM Admin イベント ログに次のエントリが表示されます。

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

コンピューターのユーザーの除外を手動で上書きする場合は、次の手順を実行します。
 
1. 次のレジストリ サブキーで AllowUserExemption 値を **0** に設定します。 <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. **AgentVersion、EncodedComputerName、** および Installed を**** 除く、次のレジストリ サブキーのすべてのレジストリ値を削除**します**。<br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM**

    **メモ** 変更を有効にするには、MBAM エージェントを再起動する必要があります。

コンピューターにグループ ポリシーを適用すると、これらの値が元の設定に戻る場合があります。

### <a name="wmi-issue"></a>WMI の問題

MBAM は、BitLocker を管理win32_encryptablevolumeクラスのメソッドを使用します。 このモジュールが未登録または破損している場合、MBAM クライアントは正しく動作しなくなります。MBAM Admin イベント ログに次のイベント エントリが表示されます。

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

さらに、回復ポリシーとハードウェア ポリシーがエラー コード と一緒に適用されない場合0x8007007e。 これは"指定されたモジュールが見つかりませんでした" に変換されます。

この問題を解決するには、次のコマンドを使用して **win32_encryptablevolumeクラスを** 再登録する必要があります。

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <a name="troubleshooting-mbam-agent-communication-issues"></a>MBAM エージェントの通信に関する問題のトラブルシューティング

このセクションには、MBAM エージェント通信に関連する次の問題のトラブルシューティング情報が含まれます。

### <a name="incorrect-mbam-service-url"></a>不適切な MBAM サービス URL

MBAM コンプライアンス 状態サービスまたは回復およびハードウェア サービスの値が正しくない場合は、クライアント コンピューターの MBAM Admin イベント ログに次のようなイベント エントリが表示されます。

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

クライアント コンピューター上の次のレジストリ サブキーで **、KeyRecoveryServiceEndPoint** と **StatusReportingServiceEndpoint** の値を確認します。 <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

既定では、KeyRecoveryServiceEndPoint (MBAM Recovery and Hardware Service Endpoint) の URL は次の形式です。 <br />
**http:// \<servername\> : \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

既定では、StatusReportingServiceEndpoint (MBAM Status Reporting Service エンドポイント) の URL は次の形式です。<br />
**http:// : \<servername\> \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL にスペースが含まれている必要はありません。

サービス URL が正しくない場合は、次のグループ ポリシー設定でサービス URL を修正する必要があります。

**コンピューターの構成**  > **ポリシー**  > **管理用テンプレート**  > **Windowsコンポーネント**  > **MDOP MBAM (BitLocker 管理)**  > **クライアント管理**  > **MBAM サービスの構成**

### <a name="connectivity-issue-that-affects-the-mbam-administration-server"></a>MBAM 管理サーバーに影響する接続の問題

クライアント エージェントと MBAM 管理サーバーの間に接続の問題が存在する場合、MBAM エージェントはデータベースに更新プログラムを投稿できません。 この場合、クライアント コンピューター上の MBAM Admin イベント ログに接続エラー エントリが表示されます。

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

* 名前と IP で MBAM 管理サーバーに ping を実行して、基本的な接続を確認します。 Telnet または portqry を使用して MBAM 管理 Web サイトまたはサービス ポートに接続できるかどうかを確認します。

* IIS サービスが MBAM 管理および監視サーバーで実行され、MBAM Web サービスが MBAM クライアント コンピューター () で構成されているのと同じポートでリッスンされていることを確認します `netstat –ano | find "portnumber"` 。

* MBAM Web サイト用に構成されているポート番号が IIS マネージャー (inetmgr) を使用されていることを確認します。 ポート番号がクライアントがリッスンしているポート番号と同じことを確認します。 ポート番号が別のアプリケーションで共有されていないか確認します。 たとえば、サーバー上の別のアプリケーションで同じポートを使用しない必要があります。

* ファイアウォールがある場合は、ファイアウォールまたはプロキシ サーバーでポートが開いているか確認します。

* クライアントとサーバー間の通信が安全である場合は、有効な SSL 証明書を使用してください。

* 挿入のためにデータが送信される Web サーバーとデータベース サーバー間のネットワーク接続を確認します。 ODBC データ ソース管理者を使用して、Web サーバーからデータベース サーバーへのデータベース接続を確認できます。 接続のSQL Serverの詳細については、「How to Troubleshoot Connection to the SQL Server データベース エンジン」 を[参照してください](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)。

#### <a name="troubleshooting-the-connectivity-issue"></a>接続の問題のトラブルシューティング

クライアントで構成されているサービス URL が正しいか確認します。 レジストリから KeyRecoveryServiceEndPoint** ( **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) の URL の値をコピーし、レジストリで開Internet Explorer。

同様に、StatusReportingServiceEndpoint** ( **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) の URL の値をコピーし、その URL をInternet Explorer。

> [!Note]
> クライアント コンピューターから URL を参照できない場合は、クライアントから IIS を実行しているサーバーへの基本的なネットワーク接続をテストする必要があります。 前のセクションのポイント 1、2、3、および 4 を参照してください。

さらに、管理サーバーと監視サーバーのアプリケーション ログでエラーが発生した場合は確認します。

クライアントとサーバーの間で同時にネットワーク トレースを行い、トレースを確認して、クライアント エージェントと MBAM 管理サーバー間の接続エラーの原因を特定できます。

> [!Note]
> クライアント コンピューターからサービス URL を参照し、MBAM 管理イベント ログに接続エラー エントリがある場合は、管理サーバーとデータベース サーバー間の接続エラーが原因である可能性があります。

両方のサービス URL を正常に参照し、クライアントと実行中のサーバーとの間に接続がある場合、IIS は動作しています。 ただし、IIS を実行しているサーバーとデータベース サーバー間の通信に問題がある可能性があります。

ネットワークの問題やデータベース接続文字列の設定が正しくないため、MBAM サービスがデータベース サーバーに接続できない場合があります。 管理サーバーと監視サーバーのアプリケーション ログを確認します。 2.0.50727.0 のソース ASP.NET のエラー エントリまたは警告が表示される場合があります。これは次のログ エントリのようになります。

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

#### <a name="possible-causes"></a>考えられる原因

##### <a name="cause-1"></a>原因 1

管理者は、管理および監視サーバー コンポーネントのインストール中に無効なデータベース インスタンス名/データベース名を指定している可能性があります。

IIS 管理コンソールを使用して、データベース接続文字列を確認および修正できます。 これを行うには、IIS マネージャーを開き、Microsoft BitLocker の管理と監視を参照します。 左側に表示されるサービスごとに、次の手順に従ってデータベース接続文字列を変更します。

1. [ **機能] ビューで**、[接続文字列] **をダブルクリックします**。

2. [接続文字列 **] ページ** で、変更する接続文字列を選択します。

3. [操作] **ウィンドウで** 、[編集] を **選択します**。

4. [接続文字列 **の編集] ダイアログ** ボックスで、変更するプロパティを変更し **、[OK] を選択します**。

##### <a name="cause-2"></a>原因 2

SQL Serverでブロックされているポートを指定します。 リッスンするように構成SQL Serverポート番号を確認し、管理サーバーとデータベース サーバーの間のファイアウォールでポートが開いているか確認します。

##### <a name="cause-3"></a>原因 3

サーバー TCP/IP SQLが正しくありません。 データベース SQLの TCP/IP SQL Server 構成マネージャーを確認します。 MBAM では、データベースへの接続に TCP/IP プロトコルと名前付きパイプ プロトコルが有効になっている必要があります。

##### <a name="cause-4"></a>原因 4

NT Authority\Network Service アカウントまたは MBAM 管理サーバーのコンピューター アカウントには、データベースへの接続に必要なアクセス許可SQLありません。

データベース サーバーへのデータベース コンポーネントのインストール中に、インストーラーは 2 つのローカル グループ (MBAM コンプライアンス監査 DB Access と MBAM Recovery and Hardware DB Access) を作成します。

NT Authority\Network Service アカウント、MBAM 管理サーバーのコンピューター アカウント、およびデータベース コンポーネントをインストールするユーザーは、これらのグループに自動的に追加されます。

これらのグループには、インストール時にデータベースに対して必要なアクセス許可が付与されます。 このグループに参加しているすべてのユーザーは、データベースに対して必要なアクセス許可を自動的に受け取る。

次の 1 つ以上の条件に当てはまる場合、アクセス許可の問題により、Web サービスがデータベース サーバーに接続できない場合があります。

* 前述したグループは、データベース サーバー上のローカル グループから削除されます。

* NT Authority\Network Service アカウントと MBAM 管理サーバーのコンピューター アカウントは、これらのグループのメンバーではありません。

* これらのグループには、データベースに対する必要なアクセス許可はありません。

以前の条件に当てはまる場合は、MBAM 管理サーバーと監視サーバーのアプリケーション ログにアクセス許可関連のエラーが表示されます。 その場合は、NT Authority\Network Service アカウントと MBAM 管理サーバーのコンピューター アカウントを手動で追加し、SQL Server Management Studio ( ) を使用している SQL データベース サーバー上でサーバー全体のパブリック 役割を付与する必要があります。 https://msdn.microsoft.com/library/aa337562.aspx)

#### <a name="review-the-web-service-logs"></a>Web サービス ログの確認

MBAM 管理サーバーのアプリケーション ログにイベントが記録されない場合は、MBAM 管理および監視サーバーでホストされている MBAM Web サービスの Web サービス ログ (.svclog) を確認します。 ログ ファイルを表示するには、サービス トレース ビューアー ツール (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx を使用する必要があります。

主に RecoveryandHardwareService および ComplianceStatusService のサービス トレース ログを調査する必要があります。 既定では、Web サービス ログは C:\inetpub\Microsoft BitLocker 管理ソリューション\Logs フォルダーにあります。 各サービスは、その .svclog ファイルを独自のフォルダーの下に書き込みます。

サービス トレース ログのアクティビティで、エラーまたは警告エントリを確認します。 既定では、エラー エントリは赤で強調表示されます。 トレース ビューアーの右側のウィンドウでエラーの説明を選択して、エラー エントリに関する詳細情報を表示します。 トレース ログのエラー エントリの例を次に示します。

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

## <a name="re-installation-or-reconfiguration-of-mbam-infrastructure"></a>MBAM インフラストラクチャの再インストールまたは再構成

MBAM インフラストラクチャを再インストールまたは再構成するには、次のことを知っている必要があります。

* アプリケーション プール アカウント

* MBAM グループ (ヘルプデスク、Advanced、Report Users グループ)

* MBAM レポート URL

* SQL Server名とデータベース名

* MBAM ReadWrite アカウントと ReadOnly アカウント

### <a name="application-pool-account"></a>アプリケーション プール アカウント

アプリケーション プール アカウントを見つけるには、MBAM Web Server にログオンし、次インターネット インフォメーション サービス **(IIS) マネージャー**を開き、[アプリケーション プール]**を選択します**。

![アプリケーション プール。](images/troubleshooting-MBAM-installation-1.png)

サービス プリンシパル名 (SPN) は、このアカウントで設定する必要があります。 この設定は、MBAM の機能にとって非常に重要です。

### <a name="mbam-groups-helpdesk-advanced-report-users-group-and-reports-url"></a>MBAM グループ (ヘルプデスク、Advanced、Report Users Group and Reports URL)

![MBAM グループ。](images/troubleshooting-MBAM-installation-2.png)

ヘルプデスク グループ、Advanced Helpdesk Group、Report Users Group、MBAM Reports URL などの情報を提供します。 MBAM レポート URL は MBAM セットアップで指定する必要があります。http://servername/ReportServer と読み取る必要があります。

### <a name="sql-server-name-and-database-db-names"></a>SQL Serverおよびデータベース (DB) 名

MBAM DB をホストSQL Serverの名前とインスタンスを検索するには、MBAM Web (IIS) サーバーにログオンし、削除するレジストリ サブキーを参照します。

**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web**

![Regedit。](images/troubleshooting-MBAM-installation-3.png)

強調表示されている部分は接続文字列です。 これらは、名前、データベースSQL Serverインスタンス (名前が付いた場合) の名前を持つ必要があります。

### <a name="mbam-readwrite-and-readonly-accounts"></a>MBAM ReadWrite アカウントと ReadOnly アカウント

この情報は、web サーバー SQL Serverが見つかったデータベース内に存在します。

#### <a name="readwrite-account"></a>ReadWrite アカウント

1. サーバーにログインSQL Management Studio。

2. **[MBAM 回復とハードウェア] を右クリックし、[****プロパティ]** を選択し、[アクセス許可]**を選択します**。

たとえば、ラボ アカウント名は **MBAMWrite です**。 アプリケーション プールアカウントと ReadWrite アカウントは同じに設定されます。

![SQLDB。](images/troubleshooting-MBAM-installation-4.png)

![DB プロパティ。](images/troubleshooting-MBAM-installation-5.png)

[セキュリティ **] を参照**し、[**ログイン]** SQL Management Studio。 前のスクリーンショットに示したアカウントを参照します。

![SQLセキュリティ。](images/troubleshooting-MBAM-installation-6.png)

アカウントを右クリックし、[プロパティ] [ユーザー マッピング] **に移動**し、MBAM 回復データベースとハードウェア データベースを探します。

![ユーザー マッピング。](images/troubleshooting-MBAM-installation-7.png)

#### <a name="readonly-account"></a>ReadOnly アカウント

SSRS サーバー SQL Server Reporting Services構成マネージャーを開きます。 [ **レポート マネージャーの URL] を**選択し **、URL を参照します**。

![レポート マネージャー。](images/troubleshooting-MBAM-installation-8.png)

[Microsoft **Bitlocker の管理と監視] を選択します**。

![Bitlocker の管理と監視。](images/troubleshooting-MBAM-installation-9.png)

Select **MaltaDatasource**:

![DB。](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource。](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource には ReadOnly アカウント名が必要で、MBAM セットアップで使用する必要があります。

## <a name="reference"></a>リファレンス

詳細については、次の記事を参照してください。

[スタンドアロン構成での MBAM 2.5 の展開](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker Administration and Monitoring 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
