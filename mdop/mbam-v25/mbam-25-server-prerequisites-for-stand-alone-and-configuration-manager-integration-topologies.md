---
title: スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件
description: スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825997"
---
# スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件


Microsoft BitLocker の管理と監視 (MBAM) のインストールを開始する前に、このトピックで説明されている前提条件を完了する必要があります。 これらの前提条件は、MBAM スタンドアロントポロジと System Center Configuration Manager の統合トポロジに適用されます。

System Center Configuration Manager を使用して MBAM を展開する場合は、「Mbam 2.5 Server の前提条件」で示されている、[構成マネージャーの統合トポロジにのみ適用](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)される追加の前提条件を完了する必要があります。

MBAM でサポートされているハードウェアとオペレーティングシステムの一覧については、「 [mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。

**重要**  
MBAM なしで BitLocker を使用していた場合は、ドライブの暗号化を解除し、tpm を使って TPM をクリアする必要があります。 クライアント PC が既に暗号化されていて、TPM 所有者パスワードが作成されている場合、MBAM は TPM の所有権を取得できません。



## 必須の MBAM ロールとアカウント


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Active Directory ドメインサービス (AD DS) で作成されたグループ</p></td>
<td align="left"><p><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> </a> これらのグループとアカウントの説明については、「mbam 2.5 のグループとアカウントの計画」を参照してください。</p></td>
</tr>
</tbody>
</table>



## 回復データベースの前提条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの SQL Server</p></td>
<td align="left"><p>SQL_Latin1_General_CP1_CI_AS の照合を使用して Microsoft SQL Server をインストールします。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</p></td>
</tr>
<tr class="even">
<td align="left"><p>必須の SQL Server 権限</p></td>
<td align="left"><p>必要な権限:</p>
<ul>
<li><p>SQL Server インスタンスのログインサーバーの役割:</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services インスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>オプション-SQL Server で使用できる透過データ暗号化 (TDE) 機能をインストールする</p></td>
<td align="left"><p>TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業に適用される法律、規制、ガイドラインを遵守するのに役立ちます。</p>
<div class="alert">
<strong>注</strong><br/><p>TDE は、データベース情報のリアルタイムの暗号化解除を実行します。 つまり、SQL Server データベースの回復キー情報を表示していて、データベースに対するアクセス許可を持つアカウントでログオンしている場合は、回復キーの情報が表示されます。 TDE の詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティの考慮事項」を参照してください </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server データベースエンジンサービス</p></td>
<td align="left"><p>MBAM Server のインストール中に SQL Server データベースエンジンサービスをインストールして実行する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell を回復データベースサーバーにインストールする必要はありません。</p></td>
</tr>
</tbody>
</table>



## コンプライアンスおよび監査データベースの前提条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの SQL Server</p></td>
<td align="left"><p>SQL_Latin1_General_CP1_CI_AS の照合順序で SQL Server をインストールします。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</p></td>
</tr>
<tr class="even">
<td align="left"><p>必須の SQL Server 権限</p></td>
<td align="left"><p>必要な権限:</p>
<ul>
<li><p>SQL Server インスタンスのログインサーバーの役割:</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services インスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>オプション-透過データ暗号化 (TDE) 機能を SQL Server にインストールする</p></td>
<td align="left"><p>TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業に適用される法律、規制、ガイドラインを遵守するのに役立ちます。</p>
<p>TDE は、データベース情報のリアルタイムの暗号化解除を実行します。 つまり、SQL Server データベースの回復キー情報を表示していて、データベースに対するアクセス許可を持つアカウントでログオンしている場合は、回復キーの情報が表示されます。 TDE の詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティの考慮事項」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server データベースエンジンサービス</p></td>
<td align="left"><p>MBAM Server のインストール中に SQL Server データベースエンジンサービスをインストールして実行する必要があります。 ただし、SQL Server はリモートで実行できます。MBAM サーバソフトウェアをインストールしているのと同じサーバ上にある必要はありません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell をコンプライアンスおよび監査データベースサーバーにインストールする必要はありません。</p></td>
</tr>
</tbody>
</table>



## レポートの前提条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの SQL Server</p></td>
<td align="left"><p>SQL_Latin1_General_CP1_CI_AS の照合順序で SQL Server をインストールします。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services (SSRS)</p></td>
<td align="left"><p>SSRS は、MBAM サーバのインストール中にインストールして実行する必要があります。</p>
<p>&quot; &quot; 未構成または SharePoint モードではなく、ネイティブモードで SSRS を構成 &quot; &quot; します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS インスタンスの権限–レポートが構成されているサーバーとは別のサーバーにデータベースをインストールする場合のみ、レポートを構成するために必要です。</p></td>
<td align="left"><p>必要なインスタンスの権限:</p>
<ul>
<li><p>フォルダーを作成する</p></li>
<li><p>レポートを発行する</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows PowerShell 3.0 以降</p></td>
<td align="left"><p>Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell をこのデータベースサーバーにインストールする必要はありません。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a>管理および監視サーバーの前提条件


次の表は、MBAM 管理および監視サーバーのインストールの前提条件を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server Web サーバーの役割</p></td>
<td align="left"><p>この役割は、管理と監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web サーバー (IIS) 管理ツール</p></td>
<td align="left"><p>[ <strong> IIS 管理スクリプトとツール] をクリックし </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 証明書</strong></p></td>
<td align="left"><p>省略可能。 クライアントコンピューターと web サービスの間の通信をセキュリティで保護するために、信頼されたセキュリティ機関が署名した証明書を取得してインストールする必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web サーバーの役割サービス</p></td>
<td align="left"><p><strong>一般的な HTTP 機能:</strong></p>
<ul>
<li><p>静的なコンテンツ</p></li>
<li><p>既定のドキュメント</p></li>
</ul>
<p><strong>アプリケーション開発:</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET の拡張性</p></li>
<li><p>ISAPI 拡張機能</p></li>
<li><p>ISAPI フィルター</p></li>
</ul>
<p><strong>証券</strong></p>
<ul>
<li><p>Windows 認証</p></li>
<li><p>フィルターを要求する</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server の機能</p></td>
<td align="left"><p><strong>.NET Framework 4.5 の機能:</strong></p>
<ul>
<li><p><strong>.NET Framework 4.5 または4.6</strong></p>
<ul>
<li><p><strong>Windows Server 2016 </strong> - .net Framework 4.6 は、これらのバージョンの windows server 用に既にインストールされていますが、有効にする必要があります。</p></li>  
<li><p><strong>Windows server 2012 または Windows Server 2012 R2 </strong> - .net Framework 4.5 は、これらのバージョンの windows server 用に既にインストールされていますが、有効にする必要があります。</p></li>
<li><p><strong>Windows Server 2008 R2 </strong> - .net framework 4.5 は windows Server 2008 r2 には含まれていないため、 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> Microsoft .net framework 4.5 をダウンロードして別途インストールする必要があり </a> ます。</p>
<div class="alert">
<strong>注</strong><br/><p>MBAM 2.0 または MBAM 2.0 SP1 からアップグレードしていて、.NET Framework 4.5 をインストールする必要がある場合は、「 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> mbam 2.5 のリリースノート」を参照して </a> 、web サイトを作成するための追加の必要な手順を参照してください。</p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong>WCF のアクティブ化</strong></p>
<ul>
<li><p>HTTP アクティベーション</p></li>
<li><p>非 HTTP ライセンス認証 (Windows Server 2008、2012、2012 R2 の場合のみ)</p>
<p></p></li>
</ul></li>
<li><p><strong>TCP ライセンス認証</strong></p></li>
</ul>
<p><strong>Windows プロセスアクティブ化サービス:</strong></p>
<ul>
<li><p>プロセスモデル</p></li>
<li><p>.NET Framework 環境</p></li>
<li><p>構成 Api</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4.0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 ダウンロード</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>サービスプリンシパル名 (SPN)</p></td>
<td align="left"><p>Web アプリケーションでは、web アプリケーションプールに使用するドメインアカウントの下に、仮想ホスト名の SPN を指定する必要があります。</p>
<p>管理者権限で Active Directory ドメインサービスの Spn の作成が許可されている場合は、MBAM によって SPN が作成されます。 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Spn の </a> 作成に必要な権利については、「Setspn」を参照してください。</p>
<p>Spn を作成するための管理者権限がない場合は、次のコマンドを使用して、組織内の Active Directory 管理者に、SPN の作成を依頼する必要があります。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>このコード例では、仮想ホスト名は mbamvirtual.contoso.com であり、web アプリケーションプールに使用されているドメインアカウントは contoso\mbamapppooluser.</p>
<div class="alert">
<strong>注</strong><br/><p>負荷分散を設定する場合は、すべてのサーバーで同じアプリケーションプールアカウントを使用します。</p>
</div>
<div>

</div>
<p>完全修飾、NetBIOS、カスタムのホスト名の Spn の登録について詳しくは、「 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> MBAM Web サイトをセキュリティで保護する方法を計画する」をご覧ください </a> 。</p></td>
</tr>
</tbody>
</table>



## セルフサービスポータルの前提条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの Windows Server</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4.0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 ダウンロード</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web サービス IIS 管理ツール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>サービスプリンシパル名 (SPN)</p></td>
<td align="left"><p>Web アプリケーションでは、web アプリケーションプールに使用するドメインアカウントの下に、仮想ホスト名の SPN を指定する必要があります。</p>
<p>管理者権限で Active Directory ドメインサービスの Spn の作成が許可されている場合は、MBAM によって SPN が作成されます。 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Spn の </a> 作成に必要な権利については、「Setspn」を参照してください。</p>
<p>Spn を作成するための管理者権限がない場合は、次のコマンドを使用して、組織内の組織の管理者に、SPN の作成を依頼する必要があります。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>このコード例では、仮想ホスト名は mbamvirtual.contoso.com であり、web アプリケーションプールに使用されているドメインアカウントは contoso\mbamapppooluser.</p>
<div class="alert">
<strong>注</strong><br/><p>負荷分散を設定する場合は、すべてのサーバーで同じアプリケーションプールアカウントを使用します。</p>
</div>
<div>

</div>
<p>完全修飾、NetBIOS、カスタムのホスト名の Spn の登録について詳しくは、「 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> MBAM Web サイトをセキュリティで保護する方法を計画する」をご覧ください </a> 。</p></td>
</tr>
</tbody>
</table>



## 管理ワークステーションの前提条件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM クライアントをインストールする前に、MBAM グループポリシーテンプレートをダウンロードして、そのために、組織 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> </a> 内で BitLocker ドライブ暗号化用に実装する設定を構成します。</p></td>
<td align="left"><p>MBAM クライアントをインストールする前に、次の操作を行います。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">操作</th>
<th align="left">手順を表示する場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM グループポリシーテンプレートをコピーする</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">MBAM 2.5 グループ ポリシー テンプレートのコピー</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>グループポリシー設定を編集する</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">MBAM 2.5 グループ ポリシー設定の編集</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## 関連トピック


[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)

[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

[MBAM 2.5 がサポートされる構成](mbam-25-supported-configurations.md)




## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




