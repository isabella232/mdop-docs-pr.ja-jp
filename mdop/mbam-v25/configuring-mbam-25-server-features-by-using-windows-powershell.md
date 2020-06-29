---
title: Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成
description: Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成
author: dansimp
ms.assetid: 826429fd-29bb-44be-b47e-5f5c7d20dd1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f350a9eb96a20f50644cfdc1965b7f72741a2c29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822837"
---
# Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成


MBAM 2.5 サーバーソフトウェアをインストールしたら、Windows PowerShell コマンドレットまたは MBAM サーバー構成ウィザードを使用して、MBAM 2.5 サーバー機能の構成を行うことができます。 このトピックでは、Windows PowerShell コマンドレットを使用して MBAM 2.5 を構成する方法について説明します。 代わりにウィザードを使用するには、「 [MBAM 2.5 サーバー機能を構成](configuring-the-mbam-25-server-features.md)する」を参照してください。

## このトピックの内容は以下のとおりです。


このトピックでは、Windows PowerShell を使用して MBAM を構成する方法について次の情報を示します。

-   [MBAM 2.5 の Windows PowerShell ヘルプを読み込む方法](#bkmk-load-posh-help)

-   [MBAM Windows PowerShell コマンドレットに関するヘルプを表示する方法](#bkmk-help-specific-cmdlet)

-   [MBAM サーバー構成ウィザードではなく、Windows PowerShell でのみ実行できる構成](#bkmk-config-only-posh)

-   [Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件と要件](#bkmk-prereqs-posh-mbamsvr)

-   [Windows PowerShell を使用してリモートコンピューターで MBAM を構成する](#bkmk-remote-config)

-   [必要なアカウントと対応する Windows PowerShell コマンドレットのパラメーター](#bkmk-reqd-posh-accts)

MBAM を管理するために使用される**Get Mbambitlockerrecoveryrecoverykey**と**MbamTPMOwnerPassword** Windows powershell コマンドレットについては、「 [Windows powershell を使用して mbam 2.5 を管理する](using-windows-powershell-to-administer-mbam-25.md)」を参照してください。

## <a href="" id="bkmk-load-posh-help"></a>MBAM 2.5 の Windows PowerShell ヘルプを読み込む方法


TechNet の Windows PowerShell コマンドレットの一覧については、「 [Windows powershell による Microsoft デスクトップ最適化パックオートメーション](https://go.microsoft.com/fwlink/?LinkId=392816)」を参照してください。

**MBAM サーバーソフトウェアをインストールした後に、Windows PowerShell コマンドレットの MBAM 2.5 ヘルプを読み込むには**

1.  Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。

2.  「**更新プログラム-ヘルプ-モジュール Microsoft MBAM」と**入力します。

## <a href="" id="bkmk-help-specific-cmdlet"></a>MBAM Windows PowerShell コマンドレットに関するヘルプを表示する方法


Windows PowerShell for MBAM のヘルプは、次の形式で使用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell ヘルプの形式</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows PowerShell コマンドプロンプトで、「 <strong> Get-ヘルプ </strong> &lt; <em> コマンドレット」と入力します。</em>&gt;</p></td>
<td align="left"><p>最新の Windows PowerShell コマンドレットをアップロードするには、前のセクションの手順に従って、MBAM の Windows PowerShell ヘルプを読み込む方法を参照してください。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web ページとしての TechNet の場合</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Word の .docx ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>.Pdf ファイルとしてダウンロードセンターで</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-config-only-posh"></a>MBAM サーバー構成ウィザードではなく、Windows PowerShell でのみ実行できる構成


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell を使用してのみ実行できる構成</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Web アプリケーションとは別のコンピューターに web サービスをインストールします。</p></td>
<td align="left"><p>このウィザードを使用するには、web サービスと web アプリケーションを同じコンピューターにインストールする必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>すべての Configuration Manager オブジェクトをインストールせずに、個別のレポートサービスポイントでレポートを有効にします。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager からすべてのオブジェクトを削除します。</p></td>
<td align="left"><p>でオブジェクトを削除すると、Configuration Manager からすべてのコンプライアンスデータが削除されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>データベースのカスタムの接続文字列を入力します。</p></td>
<td align="left"><p>例: ミラーリングと連携する web アプリケーションを構成するには、 <strong> MbamWebApplication コマンドレットを使用して、 </strong> 接続文字列に適切なフェールオーバーパートナーの構文を指定する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>前提条件の確認が失敗した場合でも、検証をスキップして機能を構成します。</p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 

**注** Windows PowerShell コマンドレットまたは MBAM サーバー構成ウィザードを使用して、MBAM データベースを無効にすることはできません。 コンプライアンスや監査データが誤って削除されるのを防ぐため、データベース管理者はデータベースを手動で削除する必要があります。

 

## <a href="" id="bkmk-prereqs-posh-mbamsvr"></a>Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件と要件


構成を開始する前に、次の前提条件を完了します。

**アカウントに関連する前提条件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細情報または追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>必要なアカウントを作成します。</p></td>
<td align="left"><p><strong>このトピックで後述する「必須アカウント」と「対応する Windows PowerShell コマンドレット」のパラメーターを参照してください </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows PowerShell コマンドレットにパラメーターとして渡すユーザーアカウントとグループは、ドメイン内の有効なアカウントである必要があります。</p></td>
<td align="left"><p>ローカルアカウントは使用できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>下位レベルの形式でアカウントを指定します。</p></td>
<td align="left"><p>例:</p>
<p>domainNetBiosName\userdomainNetBiosName\group</p></td>
</tr>
</tbody>
</table>

 

**権限に関連する前提条件**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細情報または追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM 機能を構成するローカルコンピューターの管理者である必要があります。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>昇格された Windows PowerShell コマンドプロンプトを使用して、すべての Windows PowerShell コマンドレットを実行します。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Mbamamdatabase </strong> コマンドレットの場合のみ、次の操作を行います。</p>
<p>&quot; &quot; ターゲットの Microsoft SQL Server データベースのインスタンスに対してデータベースの権限を作成する必要があります。</p>
<p>このユーザーアカウントは、MBAM ボリュームシャドウコピーサービス (VSS) ライターを登録するために、ローカル管理者グループまたは Backup Operators グループの一部である必要があります。</p></td>
<td align="left"><p>既定では、データベース管理者またはシステム管理者が、必要なデータベース権限を作成する必要があり &quot; &quot; ます。</p>
<p></p>
<p>VSS Writer の詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=392814" data-raw-source="[Volume Shadow Copy Service](https://go.microsoft.com/fwlink/?LinkId=392814)"> ボリュームシャドウコピーサービス」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>System Center Configuration Manager の統合 </strong> 機能のみ:</p>
<p>この機能を有効にするユーザーは、構成マネージャーで次の権限を持っている必要があります。</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">構成マネージャーでの権限の種類</th>
<th align="left">必要な権利</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サイトの権限:</p></td>
<td align="left"><p>- Read</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager のコレクションの権限:</p></td>
<td align="left"><p>- 作成-削除-読み取り-修正-構成アイテムの展開</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 構成アイテムの権限:</p></td>
<td align="left"><p>- 作成-削除-読み取り</p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-remote-config"></a>Windows PowerShell を使用してリモートコンピューターで MBAM を構成する


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>この機能を使用する状況</strong></p></td>
<td align="left"><p>リモートコンピューターで MBAM 2.5 サーバー機能を構成する場合。 Windows PowerShell コマンドレットが1台のコンピューターで実行されていて、別のリモートコンピューターで機能を構成している。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>必要な作業</strong></p></td>
<td align="left"><p>Windows PowerShell を使用して、リモートコンピューターで MBAM 2.5 サーバー機能を構成するには、次のことを行う必要があります。</p>
<ul>
<li><p>MBAM 2.5 サーバーソフトウェアがリモートコンピューターにインストールされていることを確認します。</p></li>
<li><p>資格情報セキュリティサポートプロバイダー (CredSSP) プロトコルを使用して、Windows PowerShell セッションを開きます。</p></li>
<li><p>Windows リモート管理 (WinRM) を有効にします。 WinRM を有効にして正しく構成できない場合は、 <strong> </strong> この表に記載されている新しい PSSession コマンドレットでエラーが表示され、問題を解決する方法が示されます。 WinRM の詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=393064" data-raw-source="[Using Windows Remote Management](https://go.microsoft.com/fwlink/?LinkId=393064)"> Windows リモート管理の使用」を参照してください </a> 。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>必要な理由</strong></p></td>
<td align="left"><p>このプロトコルでは、Windows PowerShell コマンドレットを使用して、ユーザーの管理資格情報を使用して Active Directory ドメインサービスに接続することができます。 このプロトコルを使わずに Windows PowerShell セッションを開始すると、検証エラーが表示されることがあります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>CredSSP プロトコルを使用して Windows PowerShell セッションを開始する方法</strong></p></td>
<td align="left"><p>Windows PowerShell のプロンプトで、次のコードを入力します。</p>
<p><code>$s = New-PSSession -ComputerName xxx -Authentication Credssp -Credential xxx</code></p>
<p>次のコードに例を示します </p>
<p><code>$session = New-PSSession -ComputerName &lt;MBAM_server_name&gt; -Authentication Credssp -Credential (Get-Credential)</code></p>
<p><code>Enter-PSSession $session</code></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqd-posh-accts"></a>必要なアカウントと対応する Windows PowerShell コマンドレットのパラメーター


次の表では、MBAM 2.5 サーバーの機能を構成するために必要なアカウントについて説明します。 また、構成時にアカウントを指定する必要がある、対応する Windows PowerShell コマンドレットとパラメーターも一覧表示されます。

コマンドレットパラメーターの種類 (ユーザーまたはグループ) 説明を有効にする-MBAMDatabase

AccessAccount

ユーザーまたはグループ

このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループを指定して、web アプリケーションがこのデータベース内のデータやレポートにアクセスできるようにします。 この値がドメインユーザーの場合は、 **MbamWebApplication**コマンドレットを実行するときに使用される**Webserviceapplicationpoolcredential**パラメーターは、同じユーザーアカウントを使用する必要があります。 値が domain Users グループの場合、 **Webserviceapplicationpoolcredential**パラメーターで使われるドメインアカウントは、このグループのメンバーである必要があります。

ReportAccount

ユーザーまたはグループ

このデータベースに読み取り専用のアクセス許可を持つドメインユーザーまたはユーザーグループを指定して、MBAM レポートでコンプライアンスデータと監査データへのアクセスを提供します。 値がドメインユーザーの場合**は、ComplianceAndAuditDBCredential パラメーターコマンドレット**の**ComplianceAndAuditDBCredential**パラメーターに同じユーザーアカウントを使用する必要があります。 値が domain Users グループの場合は、 **ComplianceAndAuditDBCredential**パラメーターで使われるドメインアカウントがこのグループのメンバーである必要があります。

-MbamReport を有効にする

ComplianceAndAuditDBCredential

ユーザー

MBAM コンプライアンスおよび監査データベースに接続するためにローカルの SSRS インスタンスで使用される管理資格情報を指定します。 管理資格情報のドメインユーザーは、 **reportaccount**パラメーターとして使用されるユーザーアカウントと同じである必要があります。これは、 **mbamdatabase**コマンドレットを実行しているときに使用されます。 **Reportaccount**パラメーターで domain Users グループを使用した場合は、このアカウントがそのグループのメンバーである必要があります。

**重要** 管理資格情報で指定されたアカウントは、セキュリティを強化するためのユーザー権限を制限している必要があります。 また、アカウントのパスワードを無期限に設定する必要があります。

 

ReportsReadOnlyAccessGroup

Group

レポートの読み取りアクセス許可を持つドメインユーザーグループを指定します。 指定したグループは、 **ReportsReadOnlyAccessGroup** **パラメーターに使用**されているグループと同じグループである必要があります。

Enable-MBAMWebApplication

Advanced Helpデスク Accessgroup

Group

[レポート] 領域以外の、管理および監視 Web サイトのすべての領域にアクセスできる domain Users グループを指定します。

Helpデスク Accessgroup

Group

管理と監視の Web サイトの TPM および**ドライブ回復**領域の**管理**にアクセスできる domain Users グループを指定します。

ReportsReadOnlyAccessGroup

Group

管理および監視 Web サイトの [**レポート**] 領域に対する読み取りアクセス許可を持つ domain Users グループを指定します。 指定したグループ**は、ReportsReadOnlyAccessGroup パラメーターコマンドレット**の**ReportsReadOnlyAccessGroup**パラメーターと同じグループである必要があります。

WebServiceApplicationPoolCredential

ユーザー

MBAM web アプリケーションのアプリケーションプールによって使用されるドメインユーザーを指定します。 これは、 **MbamDatabase**コマンドレットの**accessaccount**パラメーターで指定されているものと同じドメインユーザーアカウントである必要があります。 **Enable-MbamDatabase**コマンドレットを実行しているときに、 **accessaccount**パラメーターによって domain Users グループが使用されていた場合、ここで指定されたドメインユーザーはそのグループのメンバーである必要があります。 管理者の資格情報を指定しない場合は、以前に有効になっていた web アプリケーションで指定された管理資格情報が使用されます。 すべての web アプリケーションで同じアプリケーションプール id が使用されます。 複数回指定すると、最後に指定した値が使用されます。

**重要** セキュリティを向上させるには、管理者の資格情報で指定されているアカウントを制限付きのユーザー権限に設定します。 また、アカウントのパスワードを無期限に設定します。 組み込みの IIS \ _IUSRS アカウント、または**Webserviceapplicationpoolcredential**パラメーターとして使用されているアカウントが、[**認証後にクライアントを偽装**] のローカルセキュリティ設定に追加されていることを確認します。

ローカルセキュリティ設定を表示するには、**ローカルセキュリティポリシーエディター**を開き、[**ローカルポリシー** ] ノードを展開し、[**ユーザー権利の割り当て**] ノードを選びます。次に、[**認証後にクライアントを偽装**] グループポリシー設定をダブルクリック**して、** 詳細ウィンドウに表示します。

 

 




## 関連トピック


[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

[MBAM 2.5 サーバー機能の構成の確認](validating-the-mbam-25-server-feature-configuration.md)

[Windows PowerShell を使用した MBAM 2.5 の管理](using-windows-powershell-to-administer-mbam-25.md)

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。
 





