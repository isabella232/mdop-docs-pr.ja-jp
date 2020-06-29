---
title: App-V 5.0 SP3 について
description: App-V 5.0 SP3 について
author: dansimp
ms.assetid: 67b5268b-edc1-4027-98b0-b3937dd70a6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: bc72f3f72c2b06470287dfe4ba3ed22abcc6068b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814974"
---
# App-V 5.0 SP3 について


Microsoft Application Virtualization (App-v) 5.0 SP3 に適用される重大な変更に関する情報を確認するには、次のセクションを使用します。

-   [App-v 5.0 SP3 ソフトウェアの前提条件とサポートされる構成](#bkmk-sp3-prereq-configs)

-   [App-v 5.0 SP3 への移行](#bkmk-migrate-to-50sp3)

-   [手動で作成された接続グループの xml ファイルには、スキーマの更新が必要](#bkmk-update-schema-cg)

-   [接続グループの改善](#bkmk-cg-improvements)

-   [管理者は、特定のユーザーに対してパッケージの発行と発行の取り消しを行うことができます](#bkmk-usersid-pub-pkgs-specf-user)

-   [管理者のみがパッケージの発行と発行を解除できるようにする](#bkmk-admins-only-pub-unpub-pkgs)

-   [RunVirtual registry key は、ユーザーに公開されているパッケージをサポートします。](#bkmk-runvirtual-reg-key)

-   [新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプ](#bkmk-posh-cmdlets-help)

-   [プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンにすることもできます。](#bkmk-pvad-hidden)

-   [App-v の公開メタデータを表示するには、ClientVersion が必要です](#bkmk-pub-metadata-clientversion)

-   [App-v のイベントログが統合されている](#bkmk-event-logs-moved)

## <a href="" id="bkmk-sp3-prereq-configs"></a>App-v 5.0 SP3 ソフトウェアの前提条件とサポートされる構成


アプリ-V 5.0 SP3 ソフトウェアの前提条件とサポートされる構成については、次のリンクを参照してください。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件とサポートされる構成へのリンク</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-50-sp3-prerequisites.md" data-raw-source="[App-V 5.0 SP3 Prerequisites](app-v-50-sp3-prerequisites.md)">APP-V 5.0 SP3 の前提条件</a></p></td>
<td align="left"><p>App-v 5.0 SP3 のインストールを開始する前にインストールする必要がある必須ソフトウェア</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 でサポートされる構成</a></p></td>
<td align="left"><p>App-v Server、Sequencer、およびクライアントコンポーネントのサポートされているオペレーティングシステムとハードウェアの要件</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-migrate-to-50sp3"></a>App-v 5.0 SP3 への移行


以前のバージョンから App-v 5.0 SP3 にアップグレードするには、次の情報を使用します。

### アップグレードを開始する前に

アップグレードを開始する前に、次の情報を確認します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アップグレード前に確認する項目</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>アップグレードするコンポーネント</p></td>
<td align="left"><ol>
<li><p>App-v Server</p></li>
<li><p>Sequencer (シーケンサー)</p></li>
<li><p>App-v client または App-v リモートデスクトップサービス (RDS) クライアント</p></li>
<li><p>接続グループ</p></li>
</ol>
<div class="alert">
<strong>注</strong><br/><p>App-v クライアントユーザーインターフェイスを使用するには、 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Microsoft Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Microsoft Application Virtualization 5.0 クライアント UI アプリケーションから既存のバージョンをダウンロードし </a> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>アプリからのアップグレード-V 4. x</p></td>
<td align="left"><p>まず、App-V 5.0 にアップグレードする必要があります。 アプリ-V 5.0 SP3 からアプリに直接アップグレードすることはできません。</p>
<p>詳細については、以下を参照してください。</p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">App-V 5.0 について</a> </p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">APP-V の以前のバージョンからの移行計画</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.0 以降からのアップグレード</p></td>
<td align="left"><p>以下のいずれかのバージョンから直接 App-v 5.0 SP3 にアップグレードできます。</p>
<ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul>
<p>App-v 5.0 SP3 にアップグレードするには、この記事の残りのセクションの手順に従います。</p></td>
</tr>
<tr class="even">
<td align="left"><p>アップグレードした後でパッケージと接続グループに必要な変更を加える</p></td>
<td align="left"><p>なし。 パッケージと接続グループは、現時点でも引き続き機能します。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>App-v インフラストラクチャのアップグレード手順

次の手順を実行して、app-v インフラストラクチャの各コンポーネントを App-v 5.0 SP3 にアップグレードします。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>手順 1: App-v Server をアップグレードします。</p>
<p>App-v Server を使っていない場合は、この手順をスキップして次の手順に進みます。</p>
<div class="alert">
<strong>注</strong><br/><p>App-v 5.0 SP3 クライアントは、app-v 5.0 SP1 サーバーと互換性があります。</p>
</div>
<div>

</div></td>
<td align="left"><p>次の手順に従います。</p>
<ol>
<li><p>App-v <a href="release-notes-for-app-v-50-sp3.md" data-raw-source="[Release Notes for App-V 5.0 SP3](release-notes-for-app-v-50-sp3.md)"> </a> Server のインストールに影響する可能性のある問題については、「APP-V 5.0 SP3 のリリースノート」を参照してください。</p></li>
<li><p>管理データベースやレポートデータベースのアップグレードに使用する方法に応じて、次のいずれかの操作を行います。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">データベースのアップグレード方法</th>
<th align="left">ステップ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows インストーラー</p></td>
<td align="left"><p>この手順をスキップして、「App-v Server をアップグレードする場合」の手順3に進みます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL スクリプト</p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>管理データベース</strong></p></td>
<td align="left"><p>インストールまたはアップグレードするには、「 <a href="https://support.microsoft.com/kb/3031340" data-raw-source="[SQL scripts to install or upgrade the App-V 5.0 SP3 Management Server database fail](https://support.microsoft.com/kb/3031340)"> office スクリプトをインストールまたは5.0 アップグレードする」を参照してください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>レポートデータベース</strong></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">「SQL スクリプトを使用して App-v データベースを展開する方法」の手順に従い </a> ます。</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>
<p> </p></li>
<li><p>App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降でアップグレードする場合は、「 <a href="#bkmk-check-reg-key-svr" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](#bkmk-check-reg-key-svr)"> app-v 5.0 SP3 サーバーをインストールした後でレジストリキーを確認する」の手順を実行し </a> ます。</p></li>
<li><p>「 <a href="how-to-deploy-the-app-v-50-server-50sp3.md" data-raw-source="[How to Deploy the App-V 5.0 Server](how-to-deploy-the-app-v-50-server-50sp3.md)"> App-v 5.0 サーバーを展開する方法」の手順に従い </a> ます。</p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>手順 2: App-v Sequencer をアップグレードします。</p></td>
<td align="left"><p><a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)">Sequencer をインストールする方法について説明し </a> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>手順 3: App-v クライアントまたは App-v RDS クライアントをアップグレードします。</p></td>
<td align="left"><p>「 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> App-v クライアントを展開する方法」を参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-check-reg-key-svr"></a>App-v 5.0 SP3 サーバーをインストールする前にレジストリキーを確認する

これは、前の表の手順3です。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>この手順が必要な場合</strong></p></td>
<td align="left"><p>.Msp ファイルを使用してインストールした後続の修正プログラムパッケージを使用して、App-v SP1 からアップグレードしようとしています。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>この手順を実行する必要があるコンポーネント</strong></p></td>
<td align="left"><p>アップグレードしている App-v Server コンポーネントのみ</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>この手順を実行する必要がある場合</strong></p></td>
<td align="left"><p>App-v Server を app-v 5.0 SP3 にアップグレードする前に</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>必要な作業</strong></p></td>
<td align="left"><p>次の表の情報を使用して、[ <code>HKLM\Software\Microsoft\AppV\Server</code> 元のサーバーインストールで指定した値を使用して、各レジストリキーの値を更新します] を選びます。 この手順を完了すると、App-v SP1 の修正プログラムパッケージをインストールしたときに削除された可能性があるレジストリ値が復元されます。</p></td>
</tr>
</tbody>
</table>



**ManagementDatabase キー**

管理データベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>ローカル以外の管理データベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。 値が必要な場合は、"1" に設定されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_NAME</p></td>
<td align="left"><p>管理データベースの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>読み取り (パブリック) 管理データベースへのアクセスに使用するアカウント。</p>
<p>"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>管理データベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</p>
<p>"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理データベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p>管理データベースへの書き込み (管理者) アクセスのために使用されるアカウント。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>管理データベースへの書き込み (管理者) アクセスのために使用されるアカウントのセキュリティ識別子 (SID)。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>管理サーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>管理サーバー (ドメイン \ アカウント) のインストール管理者ログイン。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有効な値は次のとおりです。</p>
<ul>
<li><p><strong>1 </strong> –管理サービスはローカルコンピューターにあります。つまり、MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</p></li>
<li><p><strong>0 </strong> - 管理サービスは、ローカルコンピューターとは別のコンピューターにあります。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ManagementService キー**

管理サーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementService` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MANAGEMENT_ADMINACCOUNT</p></td>
<td align="left"><p>Active Directory ドメインサービス (AD DS) グループまたは、App-v (ドメイン \ アカウント) を管理する権限が与えられているアカウント。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MANAGEMENT_DB_SQL_INSTANCE</p></td>
<td align="left"><p>管理データベースを含む SQL server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MANAGEMENT_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>管理データベースのあるリモート SQL server の名前。</p>
<p>この値が空白の場合は、ローカルコンピューターが使用されます。</p></td>
</tr>
</tbody>
</table>



**ReportingDatabase キー**

レポートデータベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</p></td>
<td align="left"><p>ローカル以外のレポートデータベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。 値が必要な場合は、"1" に設定されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_NAME</p></td>
<td align="left"><p>レポートデータベースの名前。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</p></td>
<td align="left"><p>レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウント。</p>
<p>"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p>レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</p>
<p>"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>レポートデータベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</p></td>
<td align="left"><p>レポートサーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</p></td>
<td align="left"><p>[Reporting server (ドメイン \ アカウント)] のインストール管理者としてログインします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_SERVER_MACHINE_USE_LOCAL</p></td>
<td align="left"><p>有効な値は次のとおりです。</p>
<ul>
<li><p><strong>1 </strong> –レポートサービスはローカルコンピューターにあります。つまり、REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</p></li>
<li><p><strong>0 </strong> - レポートサービスは、ローカルコンピューターの別のコンピューターにあります。</p></li>
</ul></td>
</tr>
</tbody>
</table>



**ReportingService キー**

レポートサーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingService` します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">キー名</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>REPORTING_DB_SQL_INSTANCE</p></td>
<td align="left"><p>レポートデータベースの SQL Server インスタンス。</p>
<p>この値が空白の場合、既定のデータベースインスタンスが使用されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REPORTING_DB_SQL_SERVER_NAME</p></td>
<td align="left"><p>レポートデータベースのあるリモート SQL server の名前。</p>
<p>この値が空白の場合は、ローカルコンピューターが使用されます。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-update-schema-cg"></a>手動で作成された接続グループの xml ファイルには、スキーマの更新が必要


接続グループの XML ファイルを手動で作成していて、新しい "オプションパッケージ" を使い、強化された[接続グループ](#bkmk-cg-improvements)の機能を使用したい場合は、XML ファイルで次のスキーマを指定する必要があります。

`xmlns="http://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup"`

詳細については、「[接続グループファイルについ](about-the-connection-group-file.md)て」を参照してください。

## <a href="" id="bkmk-cg-improvements"></a>接続グループの改善


アプリ-V 5.0 SP3 で追加されたオプションのパッケージやその他の改善によって、接続グループをより簡単に管理できます。 次の表は、新しい接続グループ機能を使用して実行できるタスクと、各タスクに関する詳細情報へのリンクをまとめたものです。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク/機能</th>
<th align="left">説明</th>
<th align="left">詳細情報へのリンク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>接続グループにオプションのパッケージを含めることを有効にする</p></td>
<td align="left"><p>接続グループにオプションのパッケージを含めることで、ユーザーが資格を持つアプリケーションに基づいて、接続グループの仮想環境に含めるアプリケーションを動的に決定することができます。</p>
<p>複数の接続グループを管理する必要はありません。同じ接続グループでオプションとオプション以外のパッケージを混在させることができます。 パッケージを混在させることで、ユーザーは共通のパッケージを1つしか持っていない場合でも、異なるグループのユーザーが同じ接続グループを使用できるようになります。</p>
<p><strong>例 </strong> : すべてのユーザーに対して Microsoft Office でパッケージを有効にすることはできますが、異なる Office プラグインを含むさまざまなオプションパッケージをユーザーの異なるサブセットに対して有効にすることができます。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">接続グループでオプション パッケージを使用する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>接続グループを変更せずに、省略可能なパッケージを非公開にする、または削除する</p></td>
<td align="left"><p>接続グループに含まれているオプションのパッケージを公開または削除するか、非公開にして再公開します。これは、App-v クライアントで接続グループを無効にするか、再び有効にする必要はありません。</p></td>
<td align="left"><p><a href="how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional" data-raw-source="[How to Use Optional Packages in Connection Groups](how-to-use-optional-packages-in-connection-groups.md#bkmk-apps-plugs-optional)">接続グループでオプション パッケージを使用する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ユーザーに公開されたパッケージとグローバルに公開されたパッケージを含む接続グループを公開する</p></td>
<td align="left"><p>ユーザーが公開した、またはグローバルに公開されたパッケージを含む、ユーザーに公開された接続グループを作成します。</p></td>
<td align="left"><p><a href="how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md" data-raw-source="[How to Create a Connection Group with User-Published and Globally Published Packages](how-to-create-a-connection-group-with-user-published-and-globally-published-packages.md)">ユーザー単位で公開されるパッケージとグローバルに公開されるパッケージを含む接続グループを作成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージバージョンを無視するように接続グループを設定する</p></td>
<td align="left"><p>接続グループを構成して、任意のバージョンのパッケージを受け入れるようにします。これにより、接続グループを無効にすることなくパッケージをアップグレードできます。 また、接続グループに正しくないバージョンのオプションのパッケージが含まれている場合は、パッケージは無視され、接続グループの仮想環境の作成がブロックされることはありません。</p></td>
<td align="left"><p><a href="how-to-make-a-connection-group-ignore-the-package-version.md" data-raw-source="[How to Make a Connection Group Ignore the Package Version](how-to-make-a-connection-group-ignore-the-package-version.md)">パッケージのバージョンを無視するように接続グループを構成する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>エンドユーザーの発行機能を制限する</p></td>
<td align="left"><p>(エンドユーザーではなく) 管理者のみがパッケージを公開し、接続グループを有効にすることを許可します。</p></td>
<td align="left"><p>接続グループの詳細については、「 <a href="how-to-allow-only-administrators-to-enable-connection-groups.md" data-raw-source="[How to Allow Only Administrators to Enable Connection Groups](how-to-allow-only-administrators-to-enable-connection-groups.md)"> 管理者のみが接続グループを有効にできるようにする方法」を参照してください。</a></p>
<p>パッケージの詳細については、次の記事を参照してください。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">詳細情報へのリンク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理コンソール</p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-50.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md)">管理コンソールを使用してパッケージを公開する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admin-only-posh-topic-cg)">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>サードパーティの電子ソフトウェア配信システム</p></td>
<td align="left"><p><a href="how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md" data-raw-source="[How to Enable Only Administrators to Publish Packages by Using an ESD](how-to-enable-only-administrators-to-publish-packages-by-using-an-esd.md)">ESD を使用して管理者のみが公開パッケージを有効にできるようにする方法</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>特定のユーザーの接続グループを有効または無効にする</p></td>
<td align="left"><p>管理者は、 <strong> </strong> 次のコマンドレットを使用してオプション– UserSID パラメーターを使用して、特定のユーザーの接続グループを有効または無効にすることができます。</p>
<ul>
<li><p>Enable-AppVClientConnectionGroup</p></li>
<li><p>Disable-AppVClientConnectionGroup</p></li>
</ul></td>
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md#bkmk-enable-cg-for-user-poshtopic)">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>同一のパッケージパスを接続グループ内の1つの仮想ディレクトリにマージする</p></td>
<td align="left"><p>接続グループ内の2つ以上のパッケージに同一のディレクトリパスが含まれている場合、そのパスは接続グループの仮想環境内の1つの仮想ディレクトリにマージされます。</p>
<p>このパスの結合によって、1つのパッケージに含まれるアプリケーションが、別のパッケージに含まれているファイルにアクセスすることができます。</p></td>
<td align="left"><p><a href="about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp" data-raw-source="[About the Connection Group Virtual Environment](about-the-connection-group-virtual-environment.md#bkmk-merged-root-ve-exp)">接続グループの仮想環境について</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-usersid-pub-pkgs-specf-user"></a>管理者は、特定のユーザーに対してパッケージの発行と発行の取り消しを行うことができます


管理者は、次のコマンドレットを使用して、特定のユーザーに対してパッケージを公開または非公開にすることができます。 コマンドレットを使うには、 **– UserSID**パラメーターに続けてユーザーのセキュリティ識別子 (SID) を入力します。 詳細については、以下を参照してください。

-   [PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-pub-pkg-a-user-standalone-posh)

-   [PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-unpub-pkg-specfc-use)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンドレット</th>
<th align="left">例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>公開-AppvClientPackage</p></td>
<td align="left"><p>Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
<tr class="even">
<td align="left"><p>未発行-AppvClientPackage</p></td>
<td align="left"><p>未発行-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-admins-only-pub-unpub-pkgs"></a>管理者のみがパッケージの発行と発行を解除できるようにする


次のいずれかの方法を使用して、管理者 (エンドユーザーではなく) だけがパッケージの発行と公開解除を行うことができるようにすることができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>グループ ポリシー設定</p></td>
<td align="left"><p>次のグループポリシーオブジェクトノードに移動します。</p>
<p><strong>コンピューター構成 &gt; ポリシー &gt; 管理用テンプレート &gt; System &gt; App-V の &gt; 公開 </strong> 。</p>
<p>[ <strong> 管理者として発行する] グループポリシーの設定を有効にし </strong> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell</p></td>
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</a></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-runvirtual-reg-key"></a>RunVirtual registry key は、ユーザーに公開されているパッケージをサポートします。


App-v 5.0 SP3 は、ユーザーによって公開されたパッケージ内の仮想化されたアプリケーションとの**Runvirtual** registry キーの使用をサポートします。 **Runvirtual** registry キーを使うと、ローカルにインストールされたアプリケーションを仮想環境に、または app-v を使って仮想化されたアプリケーションと共に実行できます。

以前は、App-v パッケージで仮想化されたアプリケーションをグローバルに公開する必要がありました。 **Runvirtual**について詳しくは、仮想化されたアプリケーションの仮想環境でローカルにインストールされたアプリケーションを実行するその他の方法については、「[仮想環境内でローカルにインストールされたアプリケーションを仮想化](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)されたアプリケーションで実行する」をご覧ください

## <a href="" id="bkmk-posh-cmdlets-help"></a>新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプ


新しい PowerShell コマンドレットと更新可能なコマンドレットのヘルプは、App-v 5.0 SP3 に含まれています。 コマンドレットモジュールをダウンロードするには、「 [PowerShell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md#bkmk-load-cmdlets)」を参照してください。

### 新しいアプリ-V 5.0 SP3 サーバー PowerShell コマンドレット

接続グループを管理できるように、App-v Server 用の新しい Windows PowerShell コマンドレットが追加されました。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンドレット</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Add-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>接続グループ&#39;s パッケージリストの末尾にパッケージを追加して、パッケージをオプションとして、または接続グループ内のバージョンなしで構成できるようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>オプションであるかどうかなど、接続グループパッケージの詳細を編集できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Remove-AppvServerConnectionGroupPackage</p></td>
<td align="left"><p>接続グループからパッケージを削除します。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-get-cmdlet-help"></a>PowerShell コマンドレットのヘルプの表示

コマンドレットのヘルプは、次の形式で利用できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">形式</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ダウンロード可能なモジュールとして</p></td>
<td align="left"><p>コマンドレットモジュールをダウンロードした後に最新のヘルプを表示するには、次の操作を行います。</p>
<ol>
<li><p>Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</p></li>
<li><p>次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。</p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v コンポーネント</th>
<th align="left">入力するコマンド</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvServer</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v Sequencer</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvSequencer</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v クライアント</p></td>
<td align="left"><p>更新-ヘルプ-モジュール AppvClient</p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p>Web ページとしての TechNet の場合</p></td>
<td align="left"><p>「 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell での Microsoft デスクトップ最適化パックオートメーション」の下の [App-V] ノードを参照してください </a> 。</p></td>
</tr>
</tbody>
</table>



詳細については、「 [PowerShell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)」を参照してください。

## <a href="" id="bkmk-pvad-hidden"></a>プライマリ仮想アプリケーションディレクトリ (PVAD) は非表示になっていますが、オンにすることもできます。


プライマリ仮想アプリケーションディレクトリ (PVAD) は、App-v 5.0 SP3 では非表示になっていますが、次のいずれかの方法を使用して再びオンにし、表示することができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">メソッド</th>
<th align="left">手順</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コマンドラインパラメーターを使用する</p></td>
<td align="left"><p><strong>– Enablepvadcontrol </strong> パラメーターをSequencer.exeに渡し <strong> </strong> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>レジストリサブキーを作成する</p></td>
<td align="left"><ol>
<li><p>レジストリエディターで、次の操作を行います。 <code>HKLM\SOFTWARE\Microsoft\AppV\Sequencer\Compatibility</code></p>
<div class="alert">
<strong>注</strong><br/><p>サブキーが存在しない場合は <code>Compatibility</code> 、作成する必要があります。</p>
</div>
<div>

</div></li>
<li><p>Enablepvadcontrol という名前の DWORD 値を作成 <strong> </strong> し、値を1に設定し <strong> </strong> ます。</p>
<p>値が0の場合は、 <strong> </strong> pvad が非表示になることを意味します。</p></li>
</ol></td>
</tr>
</tbody>
</table>



**PVAD の詳細:** Sequencer を使ってパッケージを作成する場合は、パッケージの任意のインストールパスを入力できます。 以前のバージョンの App-v では、アプリケーションのプライマリ仮想アプリケーションディレクトリ (PVAD) をパスとして指定する必要がありました。 PVAD は、通常は、App-v を使っていない場合に、ローカルコンピューターにアプリケーションをインストールするディレクトリです。 たとえば、コンピューターに Office をインストールする場合は、通常、PVAD は c/1/1 (Microsoft office¥) となります。

## <a href="" id="bkmk-pub-metadata-clientversion"></a>App-v の公開メタデータを表示するには、ClientVersion が必要です


App-v 5.0 SP3 では、メタデータのために App-v パブリッシングサーバーにクエリを実行するときに、アドレスに次の値を指定する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">値</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>ClientVersion</strong></p></td>
<td align="left"><p>クエリから clientversion パラメーターを省略した場合、 <strong> </strong> メタデータには新しいアプリ-V 5.0 SP3 機能は含まれません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ClientOS</strong></p></td>
<td align="left"><p>この値を指定する必要があるのは、パッケージの順序を指定するときに特定のクライアントオペレーティングシステムを選択する場合のみです。 既定の (すべてのオペレーティングシステム) を選択した場合は、この値をクエリで指定しないでください。</p>
<p><strong>クエリから clientos パラメーターを省略した場合 </strong> 、任意のオペレーティングシステムをサポートするように指定されたパッケージのみがメタデータに表示されます。</p></td>
</tr>
</tbody>
</table>



このクエリの構文と例については、「 [App-v Server 発行メタデータを表示](viewing-app-v-server-publishing-metadata.md)する」をご覧ください。

## <a href="" id="bkmk-event-logs-moved"></a>App-v のイベントログが統合されている


次のイベントログは、以前は**アプリケーションとサービスログ、microsoft/appv/app-v &lt; コンポーネント &gt; **に置かれていましたが、**アプリケーションとサービスログ、Microsoft/appv/servicelog**に移動されました。

ログを表示するには**View** 、 &gt; イベントビューアーアプリケーションで、[**分析ログとデバッグログ**の表示] を選択します。

クライアント-カタログクライアント統合クライアント-オーケストレーションクライアント-VFSC FilesystemMetadataLibrary ManifestLibrary-スクリプトクライアント-サービスクライアント-Vemgr Client-ManifestLibrary Policy Library サブシステム-AppPath サブシステム-Com サブシステム– fta

## MDOP 技術の入手方法


App-v は、Microsoft デスクトップ最適化パック (MDOP) の一部です。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスと MDOP の入手の詳細については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください。






## 関連トピック


[App-V 5.0 SP3 リリース ノート](release-notes-for-app-v-50-sp3.md)









