---
title: App-V 5.0 の前提条件
description: App-V 5.0 の前提条件
author: dansimp
ms.assetid: 9756b571-c785-4ce6-a95c-d4e134e89429
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 176c9729d8c909325c6d6694e024938d9ce9df53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814811"
---
# App-V 5.0 の前提条件

Microsoft Application Virtualization (App-v) 5.0 のセットアップを始める前に、製品をインストールするための前提条件を満たしていることを確認する必要があります。 このトピックでは、App-v 5.0 機能を展開する前に、コンピューティング環境の準備を計画する際に役立つ情報について説明します。

> [!Important]
> **この記事の前提条件は、app-v 5.0 にのみ適用**されます。 App-v 5.0 Service Pack に適用されるその他の要件については、次の web ページを参照してください。

-   [App-V 5.0 SP1 の新機能](whats-new-in-app-v-50-sp1.md)

-   [App-V 5.0 SP2 について](about-app-v-50-sp2.md)

-   [APP-V 5.0 SP3 の前提条件](app-v-50-sp3-prerequisites.md)

次の表は、特定のオペレーティングシステムに関連する必須情報を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">前提条件の説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>実行されているコンピューター:</p>
<ul>
<li><p>Windows 8</p></li>
<li><p>Windows Server 2012</p></li>
</ul></td>
<td align="left"><p>次の前提条件は既にインストールされています。</p>
<ul>
<li><p>Microsoft .NET Framework 4.5 – Microsoft .NET Framework 4 は必要ありません。</p></li>
<li><p>Windows PowerShell 3.0</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>実行されているコンピューター:</p>
<ul>
<li><p>Windows7</p></li>
<li><p>Windows Server 2008</p></li>
</ul></td>
<td align="left"><p>次の KB をダウンロードしてください。</p>
<p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[Microsoft Security Advisory: Insecure library loading could allow remote code execution](https://support.microsoft.com/kb/2533623)">Microsoft Security 勧告: 安全でないライブラリの読み込みにより、リモートでコードが実行できる場合がある</a></p>
<p>このものが優先されるようになった以降の KBs を確認してください。一部の kbs では、以前の更新プログラムをアンインストールする必要があります。</p></td>
</tr>
</tbody>
</table>

## App-v 5.0 のインストールの前提条件

> [!Note]  
> Windows 8 を実行しているコンピューターには、次の前提条件が既にインストールされています。

App-v 5.0 の機能が正常にインストールされる前に満たす必要がある特定の前提条件は、各 App-v 5.0 の各機能に含まれています。

### App-v 5.0 クライアントの前提条件

次の表は、App-v 5.0 クライアントのインストールの前提条件を示しています。

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
<td align="left"><p><strong>ソフトウェア要件</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p>
<div class="alert">
<strong>注</strong><br/><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p>
</div>
<div>

</div></li>
<li><p>KB2533623 をダウンロードしてインストールする <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"></a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>以前のサポート技術情報の記事をダウンロードしてインストールすることができます。 ただし、最新バージョンに置き換えられている可能性があります。</p>
</div>
<div>

</div></li>
<li><p>クライアントインストーラー (.exe) では、次の前提条件をインストールする必要があるかどうかが検出され、それに従って実行されます。</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p>
<p>この前提条件は、Application Virtualization 5.0 SP2 以降の修正プログラムパッケージ4をインストールしている場合にのみ必要です。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual C++ 2010 再頒布可能</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x86)</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 リモートデスクトップサービスクライアントの前提条件

> [!Note]  
> Windows Server 2012 を実行しているコンピューターには、次の前提条件が既にインストールされています。

次の表は、アプリ-V 5.0 リモートデスクトップサービスクライアントのインストールの前提条件を示しています。

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
<td align="left"><p><strong>ソフトウェア要件</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft.NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft.NET フレームワーク 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p>
<div class="alert">
<strong>注</strong><br/><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p>
</div>
<div>

</div></li>
<li><p>KB2533623 をダウンロードしてインストールする <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"></a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>以前のサポート技術情報の記事をダウンロードしてインストールすることができます。 ただし、最新バージョンに置き換えられている可能性があります。</p>
</div>
<div>

</div></li>
<li><p>クライアント (.exe) インストーラーは、次の前提条件をインストールする必要があるかどうかを検出し、それに従って実行します。</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p>
<p>この前提条件は、Application Virtualization 5.0 SP2 以降の修正プログラムパッケージ4をインストールしている場合にのみ必要です。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual C++ 2010 再頒布可能</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual C++ 2005 SP1 再頒布可能パッケージ (x86)</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 Sequencer の前提条件

> [!Note]
> Windows 8 と Windows Server 2012 を実行しているコンピューターには、次の前提条件が既にインストールされています。

次の表は、アプリ-V 5.0 Sequencer のインストールの前提条件を示しています。 可能であれば、Sequencer を実行するコンピューターのハードウェアとソフトウェアの構成は、仮想アプリケーションを実行するコンピューターと同じにする必要があります。

> [!Note]  
> ローカルにインストールされたアプリケーションのシステム要件が Sequencer の要件を超えている場合は、そのアプリケーションの要件を満たしている必要があります。 また、シーケンス処理はシステムリソースを消費するため、Sequencer を実行するコンピューターには十分なメモリ、高速プロセッサ、高速のハードドライブを搭載することをお勧めします。 詳細については[、「app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。

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
<td align="left"><p><strong>ソフトウェア要件</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p>
<p>この前提条件は、Application Virtualization 5.0 SP2 用の修正プログラムパッケージ4をインストールしている場合にのみ必要です。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p></li>
<li><p>KB2533623 をダウンロードしてインストールする <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"></a></p>
<p></p></li>
<li><p>Microsoft Windows Server 2008 R2 SP1 を実行しているコンピューターの場合は、KB2533623 をダウンロードしてインストールします。 <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"></a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>上記の KB 記事のいずれかをダウンロードしてインストールすることができます。 ただし、最新バージョンに置き換えられている可能性があります。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 サーバーの前提条件

> [!Note]
> Windows Server 2012 を実行しているコンピューターには、次の前提条件が既にインストールされています。

-   Microsoft .NET Framework 4.5 これにより、Microsoft .NET Framework 4 の要件がなくなります。

-   Windows PowerShell 3.0

-   [KB2533623](https://support.microsoft.com/kb/2533623)をダウンロードしてインストールします (https://support.microsoft.com/kb/2533623)

    > [!Important]
    > 以前の KB をダウンロードすることもできます。 ただし、最新バージョンに置き換えられている可能性があります。

次の表は、App-v 5.0 サーバーのインストールの前提条件を示しています。 サーバーコンポーネントをインストールするために使用するアカウントは、インストール先のコンピューターの管理者権限を持っている必要があります。 このアカウントには、Active Directory ディレクトリサービスを照会する機能も用意されている必要があります。 App-v 5.0 サーバーをインストールして構成する前に、各コンポーネントをホストするポートを指定する必要があります。 また、関連するファイアウォール規則を追加して、指定したポートへの受信要求を許可する必要もあります。

> [!Note]
> Web 分散オーサリングとバージョン管理 (WebDAV) は、管理サービスに対して自動的に無効になります。

App-v 5.0 サーバーは、スタンドアロン展開でサポートされます。ここでは、すべてのコンポーネントが同じサーバー上に配置され、分散配置されています。 App-v 5.0 サーバーの展開に使用するトポロジに応じて、各コンポーネントに必要なデータが少し変更されます。

> [!Important]
> 以前のバージョンまたは App-v のコンポーネントを実行しているコンピューターに、app-v 5.0 サーバーをインストールすることはできません。 さらに、Server Core またはドメインコントローラーを実行するコンピューターにもサーバーコンポーネントをインストールすることはサポートされません。

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
<td align="left"><p><strong>管理サーバー</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<div class="alert">
<strong>注</strong><br/><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p>
</div>
<div>

</div></li>
<li><p>IIS の役割が有効になっている Windows Web サーバーと、 <strong> 一般的な HTTP 機能 </strong> (静的コンテンツと既定のドキュメント)、 <strong> アプリケーション開発 </strong> (ASP.NET、.NET 拡張機能、ISAPI 拡張機能と ISAPI フィルター)、 <strong> セキュリティ </strong> (Windows 認証、要求フィルター)、 <strong> 管理ツール </strong> (IIS 管理コンソール)。</p></li>
<li><p>KB2533623 をダウンロードしてインストールする <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"></a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>以前の KB をダウンロードすることもできます。 ただし、最新バージョンに置き換えられている可能性があります。</p>
</div>
<div>

</div></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=13523" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x64)](https://www.microsoft.com/download/details.aspx?id=13523)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x64)</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x86)</a></p></li>
<li><p>64ビット ASP.NET 登録</p></li>
</ul>
<p>App-v 5.0 サーバーコンポーネントは依存していますが、展開する必要がある要件とインストールオプションはさまざまです。 次の情報を使用して、App-v 5.0 management server を実行するための環境を準備します。</p>
<ul>
<li><p>インストール場所: 既定では、このコンポーネントは、 <strong> %PROGRAMFILES%\Microsoft Application Virtualization サーバーにインストールされ </strong> ます。</p></li>
<li><p>アプリ-V 5.0 管理データベースの場所。 SQL Server 名、SQL インスタンス名、データベース名。</p></li>
<li><p>App-v 5.0 管理コンソールのアクセス権-これは、展開の最後に管理コンソールへのアクセス許可を付与するユーザーまたはグループです。 展開後は、管理コンソールに追加の管理者が追加されるまで、これらのユーザーのみが管理コンソールにアクセスできます。</p>
<div class="alert">
<strong>注</strong><br/><p>セキュリティグループと単一ユーザーはサポートされていません。 AD DS グループを指定する必要があります。</p>
</div>
<div>

</div></li>
<li><p>App-v 5.0 management service web サイト名– web サイトの名前を指定するか、既定の名前を使用します。</p></li>
<li><p>App-v 5.0 management service ポートバインド-これは、コンピューター上の別の web サイトで使用されない一意のポート番号である必要があります。</p></li>
<li><p>Microsoft Silverlight のサポート-管理コンソールを使用するには、Microsoft Silverlight がインストールされている必要があります。 これは展開の要件ではありませんが、サーバーは Microsoft Silverlight をサポートできる必要があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>管理データベース</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注</strong><br/><p>このデータベースは、App-v 5.0 management server を使用する場合にのみ必要です。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x86)</a></p></li>
</ul>
<p>App-v 5.0 サーバーコンポーネントは依存していますが、展開する必要がある要件とインストールオプションはさまざまです。 次の情報を使用して、App-v 5.0 管理データベースを実行するための環境を準備します。</p>
<ul>
<li><p>インストール場所-既定では、このコンポーネントは <strong> %PROGRAMFILES%\Microsoft Application Virtualization サーバーにインストールされ </strong> ます。</p></li>
<li><p>ユーザー設定の SQL Server インスタンス名 (該当する場合): <strong> インストールは </strong> ローカルコンピューター上にあることを前提としているため、形式は INSTANCENAME である必要があります。 次の形式の名前を指定した場合、 <strong> SVR\INSTANCE </strong> は失敗します。</p></li>
<li><p>Custom App-v 5.0 データベース名 (該当する場合) –一意のデータベース名を指定する必要があります。 管理データベースの既定値は AppVManagement です <strong> </strong> 。</p></li>
<li><p>App-v 5.0 management server location –管理サーバーが展開されているコンピューターアカウントを指定します。 これは、次の形式で指定する必要があり <strong> </strong> ます。</p></li>
<li><p>App-v 5.0 management server インストール管理者-app-v 5.0 management server をインストールするために使用されるアカウントを指定します。 次の形式を使用する必要があり <strong> ます。 </strong></p></li>
<li><p>Microsoft SQL Server Service Agent-Microsoft SQL Server エージェントサービスが自動的に再起動されるように、App-v 5.0 管理データベースを実行しているコンピューターを構成します。 詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=273725" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://go.microsoft.com/fwlink/?LinkId=273725)"> サービスを自動的に再起動するように SQL Server エージェントを構成する」をご覧ください。</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>レポートサーバー</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x86)</a></p></li>
<li><div class="alert">
<strong>注</strong><br/><p>迷惑メールや悪意のあるデータがレポートサーバーに送信されるリスクを軽減するために、企業のセキュリティポリシーに従ってレポート Web サービスへのアクセスを制限する必要があります。</p>
</div>
<div>

</div>
<p>次の機能を備えた IIS の役割を持つ Windows Web Server: <strong> 一般的な HTTP 機能 </strong> (静的コンテンツと既定のドキュメント)、 <strong> アプリケーション開発 </strong> (ASP.NET、.Net Extensions、ISAPI 拡張機能と isapi フィルター)、セキュリティ (windows 認証、要求フィルター)、セキュリティ (Windows 認証、要求フィルター)、 <strong> </strong> <strong> </strong> <strong> 管理ツール </strong> (IIS 管理コンソール)</p></li>
<li><p>64ビット ASP.NET 登録</p></li>
<li><p>インストール場所-既定では、このコンポーネントは <strong> %PROGRAMFILES%\Microsoft Application Virtualization サーバーにインストールされ </strong> ます。</p></li>
<li><p>App-v 5.0 reporting service web サイト名– web サイト名または使用される既定の名前を指定します。</p></li>
<li><p>App-v 5.0 reporting service ポートバインド-コンピューター上で実行されている別の web サイトで既に使用されていない一意のポート番号を指定する必要があります。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>レポートデータベース</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注</strong><br/><p>データベースは、App-v 5.0 レポートサーバーを使用する場合にのみ必要です。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x86)</a></p></li>
</ul>
<p>App-v 5.0 サーバーコンポーネントは依存していますが、展開する必要がある要件とインストールオプションはさまざまです。 次の情報を使用して、App-v 5.0 レポートデータベースを実行するための環境を準備します。</p>
<ul>
<li><p>インストール場所-既定では、このコンポーネントは <strong> %PROGRAMFILES%\Microsoft Application Virtualization サーバーにインストールされ </strong> ます。</p></li>
<li><p>ユーザー設定の SQL Server インスタンス名 (該当する場合): <strong> インストールは </strong> ローカルコンピューター上にあることを前提としているため、形式は INSTANCENAME である必要があります。 次の形式の名前を指定した場合、 <strong> SVR\INSTANCE </strong> は失敗します。</p></li>
<li><p>Custom App-v 5.0 データベース名 (該当する場合) –一意のデータベース名を指定する必要があります。 レポートデータベースの既定値は <strong> AppVReporting </strong> です。</p></li>
<li><p>App-v 5.0 レポートサーバーの場所–レポートサーバーが展開されているコンピューターアカウントを指定します。 これは、次の形式で指定する必要があり <strong> </strong> ます。</p></li>
<li><p>App-v 5.0 reporting server インストール管理者-app-v 5.0 レポートサーバーをインストールするために使用されるアカウントを指定します。 次の形式を使用する必要があり <strong> ます。 </strong></p></li>
<li><p>Microsoft SQL Server Service と Microsoft SQL Server エージェントサービス–これらのサービスは、クエリ広告へのアクセス権を持つユーザーアカウントに関連付けられている必要があります。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>発行サーバー</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 (パッケージ全体)</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual C++ 2010 SP1 再頒布可能パッケージ (x86)</a></p></li>
<li><p>次の機能を備えた IIS の役割を持つ Windows Web Server: <strong> 一般的な HTTP 機能 </strong> (静的コンテンツと既定のドキュメント)、 <strong> アプリケーション開発 </strong> (ASP.NET、.Net Extensions、ISAPI 拡張機能と isapi フィルター)、セキュリティ (windows 認証、要求フィルター)、セキュリティ (Windows 認証、要求フィルター)、 <strong> </strong> <strong> </strong> <strong> 管理ツール </strong> (IIS 管理コンソール)</p></li>
<li><p>64ビット ASP.NET 登録</p></li>
</ul>
<p>App-v 5.0 サーバーコンポーネントは依存していますが、展開する必要がある要件とインストールオプションはさまざまです。 次の情報を使用して、App-v 5.0 公開サーバーを実行するための環境を準備します。</p>
<ul>
<li><p>インストール場所-既定では、このコンポーネントは <strong> %PROGRAMFILES%\Microsoft Application Virtualization サーバーにインストールされ </strong> ます。</p></li>
<li><p>App-v 5.0 management service URL – App-v 5.0 management service の URL を指定します。 これは、公開サーバーが通信するポートであり、次の形式を使用して指定する必要があり <strong><a href="http://localhost:12345" data-raw-source="http://localhost:12345"> ます。 http://localhost:12345 </a></strong></p></li>
<li><p>App-v 5.0 publishing service web サイト名– web サイト名または使用される既定の名前を指定します。</p></li>
<li><p>App-v 5.0 公開サービスのポートバインド-これは、コンピューターで実行されている別の web サイトで既に使用されていない一意のポート番号である必要があります。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 関連トピック

[App-V の展開計画](planning-to-deploy-app-v.md)

[App-V 5.0 でサポートされる構成](app-v-50-supported-configurations.md)
