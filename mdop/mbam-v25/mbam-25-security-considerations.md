---
title: MBAM 2.5 のセキュリティに関する考慮事項
description: MBAM 2.5 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826837"
---
# MBAM 2.5 のセキュリティに関する考慮事項


このトピックには、Microsoft BitLocker の管理と監視 (MBAM) をセキュリティで保護する方法に関する次の情報が含まれています。

-   [MBAM を構成して TPM をエスクローし、所有者の認証パスワードを保存する](#bkmk-tpm)

-   [ロックアウト後に TPM を自動的にロック解除するように MBAM を設定する](#bkmk-autounlock)

-   [SQL Server への接続をセキュリティで保護する](#bkmk-secure-databases)

-   [アカウントとグループを作成する](#bkmk-accts-groups)

-   [MBAM ログファイルを使用する](#bkmk-logfiles)

-   [MBAM データベースの確認に関する考慮事項](#bkmk-tde)

-   [一般的なセキュリティの考慮事項を理解する](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a>MBAM を構成して TPM をエスクローし、所有者の認証パスワードを保存する

**注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。 さらに、TPM をプロビジョニングするときに、Windows によって TPM 所有者のパスワードは保持されません。 詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)を参照してください。

構成によっては、信頼されたプラットフォームモジュール (TPM) は特定の状況でロックされます。たとえば、パスワードが多すぎる場合や、一定の期間ロックされている場合などがあります。 TPM のロックアウト中は、BitLocker で暗号化キーにアクセスしてロック解除または暗号化解除の操作を実行することはできません。ユーザーは、オペレーティングシステムドライブにアクセスするために BitLocker 回復キーを入力する必要があります。 TPM ロックアウトをリセットするには、TPM OwnerAuth パスワードを指定する必要があります。

MBAM は、tpm を所有している場合、またはパスワードを escrows 場合は、MBAM データベースに TPM OwnerAuth パスワードを保存できます。 所有者認証パスワードは、TPM ロックアウトから回復する必要がある場合に、管理と監視の Web サイトで簡単にアクセスできます。ロックアウトが自動的に解決されるのを待つ必要はありません。

### Windows 8 以上の Escrowing TPM OwnerAuth

**注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。 Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。 詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)を参照してください。

Windows 8 以上の場合、MBAM は、ownerauth がローカルコンピューターで利用可能であれば、OwnerAuth パスワードを保存するために TPM を所有している必要がなくなりました。

MBAM からエスクローを有効にし、TPM OwnerAuth パスワードを保存するには、これらのグループポリシー設定を構成する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">グループポリシーの設定</th>
<th align="left">構成</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Active Directory ドメインサービスへの TPM バックアップを有効にする</p></td>
<td align="left"><p>Disabled または未構成</p></td>
</tr>
<tr class="even">
<td align="left"><p>オペレーティングシステムで利用できる TPM 所有者認証情報のレベルを構成する</p></td>
<td align="left"><p>委任/なしまたは未構成</p></td>
</tr>
</tbody>
</table>

 

これらのグループポリシー設定の場所は、**コンピューター構成**の &gt; **管理用テンプレート** &gt; **システム**の &gt; **信頼できるプラットフォームモジュールサービス**です。

**注** MBAM がこれらの設定で正常に escrows した場合、Windows はローカルで OwnerAuth を削除します。

 

### Windows 7 の Escrowing TPM OwnerAuth

Windows 7 では、mbam データベースの TPM OwnerAuth 情報を自動的に設定するために、MBAM は TPM を所有している必要があります。 MBAM が TPM を所有していない場合は、MBAM Active Directory (AD) データインポートコマンドレットを使用して、Active Directory から MBAM データベースに TPM OwnerAuth をコピーする必要があります。

### MBAM Active Directory データのインポートコマンドレット

MBAM Active Directory データのインポートコマンドレットを使用して、Active Directory に保存されている回復キーパッケージと OwnerAuth パスワードを取得できます。

MBAM 2.5 SP1 サーバーには、既定で MBAM データベースを作成するための4つの PowerShell コマンドレットが付属しており、ボリューム回復と、TPM 所有者の情報は Active Directory に保存されています。

ボリューム回復キーとパッケージの場合:

-   読み取り-ADRecoveryInformation

-   書き込み用の MbamRecoveryInformation

TPM 所有者情報:

-   読み取り-ADTpmInformation

-   書き込み-MbamTpmInformation

ユーザーをコンピューターに関連付けるには、次の操作を行います。

-   書き込み用の MbamComputerUser

Read-AD \ * コマンドレットは Active Directory から情報を読み取ります。 書き込み用の Mbam \ * コマンドレットは、MBAM データベースにデータをプッシュします。 構文、パラメーター、例など、これらのコマンドレットの詳細については、「 [Microsoft Bitlocker 管理と監視の2.5 のコマンドレットリファレンス](https://technet.microsoft.com/library/dn459018.aspx)」を参照してください。

**ユーザー間の関連付けを作成する:** MBAM Active Directory データインポートコマンドレットは、Active Directory から情報を収集し、MBAM データベースにデータを挿入します。 ただし、ユーザーはユーザーをボリュームに関連付けることはできません。 Add-ComputerUser.ps1 PowerShell スクリプトをダウンロードしてユーザー間の関連付けを作成することができます。これにより、ユーザーは管理と監視の Web サイトを通じて、またはセルフサービスポータルを使用して、コンピューターにアクセスできるようになります。 Add-ComputerUser.ps1 スクリプトは、Active Directory (AD) の [**管理者**] 属性、ad のオブジェクト所有者、またはカスタム CSV ファイルからデータを収集します。 次に、スクリプトは検出されたユーザーを回復情報パイプラインオブジェクトに追加します。これは、データを回復用データベースに挿入するために、MbamRecoveryInformation に渡す必要があります。

[Microsoft ダウンロードセンター](https://go.microsoft.com/fwlink/?LinkId=613122)から Add-ComputerUser.ps1 PowerShell スクリプトをダウンロードします。

スクリプトのヘルプを表示するには、コマンドレットとスクリプトの使い方の例など、**ヘルプ Add-ComputerUser.ps1**を指定します。

MBAM サーバーをインストールした後に、ユーザーとコンピューターの関連付けを作成するには、MbamComputerUser PowerShell コマンドレットを使用します。 このコマンドレットでは、Add-ComputerUser.ps1 PowerShell スクリプトと同様に、セルフサービスポータルを使用して、指定されたコンピューターの TPM OwnerAuth information またはボリューム回復パスワードを取得できるユーザーを指定できます。

**注** MBAM エージェントは、コンピューターがサーバーへのレポートを開始するときに、ユーザーとコンピューターの関連付けを上書きします。

 

**前提条件:** 読み取り専用 \ * コマンドレットは、ドメイン管理者などの高い権限を持つユーザーアカウントとして実行されるか、または情報への読み取りアクセス権が付与されたカスタムセキュリティグループのアカウントとして実行される場合にのみ、広告から情報を取得できます (推奨)。

[BitLocker ドライブ暗号化操作ガイド: AD DS を使用して暗号化さ](https://technet.microsoft.com/library/cc771778(WS.10).aspx)れたボリュームを回復すると、広告情報に対する読み取りアクセス権を持つカスタムセキュリティグループ (または複数のグループ) の作成に関する詳細が提供されます。

**Mbam Recovery と Hardware Web サービスの書き込みアクセス許可:** 書き込み用の Mbam \ * コマンドレットは、MBAM 回復とハードウェアサービスの URL を受け取り、回復または TPM 情報の公開に使用します。 通常、MBAM Recovery およびハードウェアサービスと通信できるのは、ドメインコンピューターサービスアカウントだけです。 MBAM 2.5 SP1 では、DataMigrationAccessGroup というセキュリティグループを使用して、MBAM 回復とハードウェアサービスを構成することができます。これにより、メンバーは、ドメインコンピューターサービスアカウントのチェックを省略できます。 書き込み用の Mbam \ * コマンドレットは、この構成されたグループに属しているユーザーとして実行する必要があります。 (または、構成されたグループ内の個別のユーザーの資格情報を、Mbam \ * コマンドレットの-Credential パラメーターを使って指定できます)。

以下のいずれかの方法で、このセキュリティグループの名前を使用して、MBAM Recovery とハードウェアサービスを構成できます。

-   DataMigrationAccessGroup パラメーターを使用して、セキュリティグループ (個別) の名前を Enable-MbamWebApplication – AgentService Powershell コマンドレットに指定します。

-   MBAM 回復とハードウェアサービスがインストールされた後にグループを構成するには、 &lt; inetpub &gt; ¥ Microsoft Bitlocker Management solution¥ Recovery and hardware Service\ \ フォルダーの web.config ファイルを編集します。

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    ここ &lt; &gt; で、GroupName は Active Directory からのデータ移行を許可するために使用されるドメインとグループ名 (または個々のユーザー) に置き換えられます。

-   この appSetting を編集するには、IIS Manager の構成エディターを使用します。

次の例では、ADRecoveryInformation グループとデータ移行ユーザーグループの両方のメンバーとして実行すると、mbam.contoso.com サーバー上で実行されている MBAM 回復とハードウェアサービスを使って、contoso.com ドメインのワークステーション組織単位 (OU) のコンピューターからボリューム回復情報を取得して、MBAM に書き込みます。

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

**読み取り-AD \ * コマンドレット**は、回復または TPM 情報を照会する Active Directory ホスティングサーバーコンピューターの名前または IP アドレスを受け入れます。 コンピューターオブジェクトが SearchBase パラメーターの値として存在する広告コンテナーの識別名を指定することをお勧めします。 複数の Ou にわたってコンピューターが保存されている場合、コマンドレットでパイプライン入力を受け入れて、各コンテナーについて1回実行することができます。 広告コンテナーの識別名は、OU = マシン、DC = contoso、DC = com と同様に表示されます。 特定のコンテナーを対象とした検索を実行すると、次の利点が得られます。

-   コンピューターオブジェクトの大規模な広告データセットを照会するときのタイムアウトのリスクを軽減します。

-   データセンターサーバーまたはバックアップが必要とされていない可能性があるその他のクラスを含む Ou は省略できます。

別の方法として、指定した検索ベースまたはドメイン全体の下にあるすべてのコンテナーでコンピューターオブジェクトを検索するために、オプションの検索ベースを指定するか、または省略することもできます。 -再帰フラグを使う場合は、-MaxPageSize パラメーターを使って、クエリを処理するために必要なローカルメモリとリモートメモリの量を制御することもできます。

これらのコマンドレットは、型 PsObject のパイプラインオブジェクトに書き込みます。 各 PsObject インスタンスには、関連付けられたコンピューター名、タイムスタンプ、およびその他の情報を MBAM データストアに公開するために必要なその他の情報を含む、1つのボリューム回復キーまたは TPM 所有者の文字列が含まれています。

**書き込み用の Mbam \ * コマンドレット**は、プロパティ名によってパイプラインから回復情報パラメーターの値を受け取ります。 これにより、書き込み用の Mbam \ * コマンドレットは、Read-AD \ * コマンドレットのパイプライン出力を受け入れることができます (たとえば、contoso.com-Server の–再帰 |書き込み-MbamRecoveryInformation – RecoveryServiceEndpoint mbam.contoso.com)。

書き込み用の**Mbam \ * コマンドレット**には、フォールトトレランス、詳細なログ、および WhatIf と Confirm の環境設定のオプションを提供するオプションのパラメーターが含まれています。

**書き込み用の Mbam \ * コマンドレット**には、 **DateTime**オブジェクトの値を含むオプションの*Time*パラメーターも含まれています。 このオブジェクトには*Kind* `Local` 、、、またはに設定できる Kind 属性が含まれてい `UTC` `Unspecified` ます。 Active Directory から取得したデータから*time*パラメーターを設定すると、時刻は UTC に変換され、この*Kind*属性は自動的にに設定され `UTC` ます。 ただし、別のソース (テキストファイルなど) を使用して*Time*パラメーターを設定する場合は、 *Kind*属性を適切な値に明示的に設定する必要があります。

**注** 読み取り-AD \ * コマンドレットには、コンピューターユーザーを表すユーザーアカウントを検出する機能はありません。 ユーザーアカウントの関連付けは、次の場合に必要です。

-   セルフサービスポータルを使用してボリュームパスワード/パッケージを復元するユーザー

-   インストール時に定義された MBAM Advanced ヘルプデスクのユーザーセキュリティグループに含まれていないユーザー、他のユーザーの代理として回復する

 

## <a href="" id="bkmk-autounlock"></a>ロックアウト後に TPM を自動的にロック解除するように MBAM を設定する


MBAM 2.5 SP1 を構成すると、ロックアウトの場合に TPM が自動的にロックされます。 TPM のロックアウト自動リセットが有効になっている場合、MBAM は、ユーザーがロックされていることを検出し、MBAM データベースから OwnerAuth パスワードを取得して、ユーザーの TPM を自動的にロック解除します。 TPM のロックアウト自動リセットは、そのコンピューターの OS の回復キーがセルフサービスポータルまたは管理/監視 Web サイトを使用して取得された場合にのみ使用できます。

**重要** TPM ロックアウトの自動リセットを有効にするには、この機能をサーバー側とクライアント側のグループポリシーの両方で構成する必要があります。

 

-   クライアント側で tpm ロックアウトの自動リセットを有効にするには、グループポリシー設定を構成します。**コンピューターの構成** &gt; **管理用テンプレート** &gt; **Windows コンポーネント** &gt; **MDOP mbam** &gt; **クライアント管理**

-   サーバー側で TPM ロックアウトの自動リセットを有効にするには、セットアップ時に MBAM サーバー構成ウィザードで [TPM ロックアウトの自動リセットを有効にする] をオンにします。

    また、「-TPM ロックアウト自動リセット」スイッチを指定して、エージェントサービス web コンポーネントを有効にすることで、PowerShell で TPM ロックアウトの自動リセットを有効にすることもできます。

ユーザーがセルフサービスポータルまたは管理と監視の Web サイトから取得した BitLocker 回復キーを入力した後、MBAM エージェントは、TPM がロックされているかどうかを確認します。ロックアウトされている場合は、MBAM データベースからコンピューターの TPM OwnerAuth を取得しようとします。 TPM OwnerAuth が正常に取得された場合は、TPM のロックを解除するために使われます。 Tpm のロックを解除すると、tpm が完全に機能し、ユーザーは TPM ロックアウト後の再起動中に回復パスワードの入力を強制されません。

TPM のロックアウトの自動リセットは、既定では無効になっています。

**注** TPM のロックアウト自動リセットは、TPM バージョン1.2 を実行しているコンピューターでのみサポートされます。 TPM 2.0 には、組み込みのロックアウト自動リセット機能が用意されています。

 

**回復監査レポート**には、TPM ロックアウト自動リセットに関連するイベントが含まれています。 MBAM クライアントから要求された場合、TPM OwnerAuth パスワードを取得するために、イベントがログに記録され、回復を示します。 監査エントリには、次のイベントが含まれます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">記録</th>
<th align="left">値</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>監査要求ソース</p></td>
<td align="left"><p>エージェント TPM のロック解除</p></td>
</tr>
<tr class="even">
<td align="left"><p>キーの種類</p></td>
<td align="left"><p>TPM パスワードハッシュ</p></td>
</tr>
<tr class="odd">
<td align="left"><p>理由の説明</p></td>
<td align="left"><p>TPM リセット</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a>SQL Server への接続をセキュリティで保護する


MBAM では、sql Server は、SQL Server Reporting Services と、管理および監視 web サイトとセルフサービスポータル用の web サービスと通信します。 SQL Server との通信をセキュリティで保護することをお勧めします。 詳細については、「 [SQL Server への接続の暗号化](https://technet.microsoft.com/library/ms189067.aspx)」を参照してください。

MBAM web サイトのセキュリティ保護の詳細については、「 [Mbam Web サイトをセキュリティで保護する方法を計画する](planning-how-to-secure-the-mbam-websites.md)」を参照してください。

## <a href="" id="bkmk-accts-groups"></a>アカウントとグループを作成する


ユーザーアカウントを管理するためのベストプラクティスは、ドメイングローバルグループを作成し、ユーザーアカウントを追加することです。 推奨されるアカウントとグループの説明については、「 [MBAM 2.5 グループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md)」を参照してください。

## <a href="" id="bkmk-logfiles"></a>MBAM ログファイルを使用する


このセクションでは、MBAM Server および MBAM クライアントログファイルについて説明します。

**MBAM サーバーセットアップログファイル**

MBAM のインストール中に、 **MBAMServerSetup.exe**ファイルによって、ユーザーの **% temp%** フォルダーに次のログファイルが生成されます。

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; # &gt; .log**

    MBAM セットアップおよび MBAM サーバー機能の構成中に実行されたアクションをログに記録します。

-   **Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi**

    インストール中に実行される追加のアクションを記録します。

**MBAM サーバー構成ログファイル**

-   **アプリケーションとサービスログ/Microsoft Windows/MBAM-セットアップ**

    Windows Powershell コマンドレットまたは MBAM サーバー構成ウィザードを使っているときに、MBAM サーバー機能を構成するときに発生するエラーをログに記録します。

**MBAM クライアントのセットアップログファイル**

-   **MSI &lt; 5 ランダム文字 &gt; ログ**

    MBAM クライアントのインストール中に実行されたアクションをログに記録します。

**MBAM-Web ログファイル**

-   Web ポータルとサービスからのアクティビティを表示します。

## <a href="" id="bkmk-tde"></a>MBAM データベースの確認に関する考慮事項


SQL Server で使用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスのオプションのインストールです。

TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。 TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化に最適な選択肢です。 TDE はファイルレベルで動作します。これは、暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化の2つの Windows 機能に似ています。 どちらの機能も、ハードドライブ上のデータを暗号化します。 TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。

データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。 そのため、データベース暗号化キーを保護するために使用された証明書がバックアップされ、データベースのバックアップと維持されるように、特別な注意を払う必要があります。 この証明書 (または証明書) が失われると、データを読み取ることができなくなります。

データベースを使用して証明書をバックアップします。 各証明書のバックアップには、2つのファイルが必要です。 これらのファイルはどちらもアーカイブする必要があります。 セキュリティのために、データベースバックアップファイルとは別にバックアップすることをお勧めします。 または、拡張キー管理 (EKM) 機能の使用を検討してください (「拡張キー管理」を参照してください)。

MBAM データベースインスタンスの TDE を有効にする方法の例については、「[透過データ暗号化 (tde) の概要](https://technet.microsoft.com/library/bb934049.aspx)」をご覧ください。

## <a href="" id="bkmk-general-security"></a>一般的なセキュリティの考慮事項を理解する


**セキュリティのリスクについて説明します。** Microsoft BitLocker の管理と監視を使用するときに最も重大なリスクは、BitLocker ドライブの暗号化を再構成し、MBAM クライアントで BitLocker 暗号化キーデータを取得できる承認されていないユーザーによって、その機能が侵害される可能性があるということです。 ただし、サービス拒否攻撃のために MBAM 機能が短期間で失われても、メールやネットワーク通信の損失、または電源の損失など、通常、重大な影響はありません。

**コンピューターを物理的に保護**します。 物理的なセキュリティがない場合は、セキュリティは必要ありません。 MBAM サーバーに物理的にアクセスできる攻撃者は、クライアントベース全体を攻撃するためにそれを使用する可能性があります。 すべての潜在的な物理的な攻撃は、高リスクと見なされ、適切に軽減する必要があります。 MBAM サーバは、アクセスを制御できる安全なサーバールームに保存する必要があります。 オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。

**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。 セキュリティの更新プログラムについて最新情報を入手するには、[セキュリティ TechCenter](https://go.microsoft.com/fwlink/?LinkId=28819)のセキュリティ通知サービスをサブスクライブします。

**強力なパスワードを使用するか、語句を渡し**ます。 すべての MBAM 管理者アカウントには、常に15文字以上の強力なパスワードを使用してください。 空のパスワードは使用しないでください。 パスワードの概念の詳細については、「[パスワードポリシー](https://technet.microsoft.com/library/hh994572.aspx)」を参照してください。



## 関連トピック


[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





