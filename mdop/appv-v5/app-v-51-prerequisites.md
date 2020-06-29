---
title: App-V 5.1 の前提条件
description: App-V 5.1 の前提条件
author: dansimp
ms.assetid: 1bfa03c1-a4ae-45ec-8a2b-b10c2b94bfb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a74d8f8d7148cdb6c32bcafa87f479d24305af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814739"
---
# App-V 5.1 の前提条件


Microsoft Application Virtualization (App-v) 5.1 をインストールする前に、次の必須の必須ソフトウェアがすべてインストールされていることを確認します。

App-v Server、Sequencer、および Client でサポートされているオペレーティングシステムとハードウェアの要件の一覧については、「 [app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

## 各オペレーティングシステムにプレインストールされているソフトウェアの概要


次の表は、さまざまなオペレーティングシステムに対して既にインストールされているソフトウェアを示しています。

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
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべての必須ソフトウェアがすでにインストールされています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>すべての必須ソフトウェアがすでにインストールされています。</p>
<div class="alert">
<strong>注</strong><br/><p>Windows 8 を実行している場合は、Windows 8.1 にアップグレードしてから app-v 5.1 を使用します。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>以下の必須ソフトウェアがすでにインストールされています。</p>
<ul>
<li><p>Microsoft .NET Framework 4.5</p></li>
<li><p>Windows PowerShell 3.0</p>
<div class="alert">
<strong>注</strong><br/><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>必須ソフトウェアはまだインストールされていません。 アプリをインストールするには、アプリをインストールする必要があります。</p></td>
</tr>
</tbody>
</table>



## App-v Server の必須ソフトウェア


App-v 5.1 サーバーコンポーネントに必要な必須ソフトウェアをインストールします。

### 始める前に知っておくべきこと

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>App-v Server をインストールするためのアカウント</p></td>
<td align="left"><p>App-v Server コンポーネントをインストールするために使用するアカウントには、次のものが必要です。</p>
<ul>
<li><p>コンポーネントをインストールするコンピューターの管理者権限。</p></li>
<li><p>Active Directory ドメインサービスに問い合わせることができます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ポートとファイアウォール</p></td>
<td align="left"><ul>
<li><p>各コンポーネントをホストするポートを指定します。</p></li>
<li><p>関連するファイアウォール規則を追加して、指定したポートへの受信要求を許可します。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 分散オーサリングとバージョン管理 (WebDAV)</p></td>
<td align="left"><p>WebDAV は、管理サービスに対して自動的に無効になります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされている展開シナリオ</p></td>
<td align="left"><ul>
<li><p>単体の展開。すべてのコンポーネントが同じサーバー上に展開されます。</p></li>
<li><p>分散展開。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>サポートされていない展開シナリオ</p></td>
<td align="left"><ul>
<li><p>複数の App-v Server バージョンの side-by-side インスタンスを同じサーバー上にインストールします。</p></li>
<li><p>Server core またはドメインコントローラーを実行しているコンピューターに、App-v サーバーコンポーネントをインストールします。</p></li>
</ul></td>
</tr>
</tbody>
</table>



### 管理サーバーの前提条件ソフトウェア

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件と必要な設定</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの SQL Server</p></td>
<td align="left"><p>サポートされているバージョンについては、「 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 でサポートされている構成」をご覧ください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p></td>
<td align="left"><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p></td>
</tr>
<tr class="even">
<td align="left"><p>KB2533623 をダウンロードしてインストールする <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"></a></p></td>
<td align="left"><p>Windows 7 にのみ適用されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64ビット ASP.NET 登録</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web サーバーの役割</p></td>
<td align="left"><p>この役割は、管理サーバーでサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web サーバー (IIS) 管理ツール</p></td>
<td align="left"><p>[ <strong> IIS 管理スクリプトとツール] をクリックし </strong> ます。</p></td>
</tr>
<tr class="odd">
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
</ul>
<p><strong>管理ツール:</strong></p>
<ul>
<li><p>IIS 管理コンソール</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>既定のインストール場所</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft Application Virtualization Server</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理データベースの場所</p></td>
<td align="left"><p>SQL Server データベース名、SQL Server データベースインスタンス名、データベース名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理コンソールと管理データベースの権限</p></td>
<td align="left"><p>展開の完了後に管理コンソールとデータベースにアクセスできるユーザーまたはグループ。 管理コンソールを使用して追加の管理者が追加されていない場合、これらのユーザーまたはグループは、管理コンソールとデータベースにのみアクセスできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理サービスの web サイト名</p></td>
<td align="left"><p>管理コンソール web サイトの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理サービスのポートバインディング</p></td>
<td align="left"><p>管理サービスの固有のポート番号。 このポートは、コンピューター上の別のプロセスで使用することはできません。</p></td>
</tr>
</tbody>
</table>



**重要**  
Web 管理コンソールを開くブラウザーで JavaScript を有効にする必要があります。



### 管理サーバーデータベースの前提条件となるソフトウェア

管理データベースは、App-v 5.1 Management server を使用している場合にのみ必要です。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件と必要な設定</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>既定のインストール場所</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft Application Virtualization Server</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー設定の SQL Server インスタンスの名前 (該当する場合)</p></td>
<td align="left"><p>使用する書式: <strong> INSTANCENAME</strong></p>
<p>この形式は、インストールがローカルコンピューターにあることを前提としています。</p>
<p>SVR\INSTANCE 形式で名前を指定した <strong> 場合 </strong> 、インストールは失敗します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>カスタムデータベース名 (該当する場合)</p></td>
<td align="left"><p>一意のデータベース名。</p>
<p>既定値: AppVManagement</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理サーバーの場所</p></td>
<td align="left"><p>管理サーバーが展開されているコンピューターアカウント。</p>
<p>使用する形式: \ machineaccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理サーバーのインストール管理者</p></td>
<td align="left"><p>管理サーバーをインストールするために使用されるアカウント。</p>
<p>使用する形式: \ アドミニストレーターログイン</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server Service Agent</p></td>
<td align="left"><p>管理データベースコンピューターを構成して、Microsoft SQL Server エージェントサービスが自動的に再起動されるようにします。 手順については、「 <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)"> サービスを自動的に再起動するように SQL Server エージェントを構成する」をご覧ください </a> 。</p></td>
</tr>
</tbody>
</table>



### 発行サーバーの前提条件となるソフトウェア

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件と必要な設定</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>64ビット ASP.NET 登録</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server Web サーバーの役割</p></td>
<td align="left"><p>この役割は、管理サーバーでサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web サーバー (IIS) 管理ツール</p></td>
<td align="left"><p>[ <strong> IIS 管理スクリプトとツール] をクリックし </strong> ます。</p></td>
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
</ul>
<p><strong>管理ツール:</strong></p>
<ul>
<li><p>IIS 管理コンソール</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>既定のインストール場所</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft Application Virtualization Server</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理サービスの URL</p></td>
<td align="left"><p>App-v 管理サービスの URL。 これは、発行サーバーが通信するポートです。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">インストールのアーキテクチャ</th>
<th align="left">URL に使用する形式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理サーバーと発行サーバーが同じサーバーにインストールされている</p></td>
<td align="left"><p><a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>管理サーバーと発行サーバーがさまざまなサーバーにインストールされている</p></td>
<td align="left"><p><a href="http://MyAppvServer.MyDomain.com" data-raw-source="http://MyAppvServer.MyDomain.com">http://MyAppvServer.MyDomain.com</a></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>公開サービスの web サイト名</p></td>
<td align="left"><p>発行 web サイトの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>公開サービスのポートバインディング</p></td>
<td align="left"><p>発行サービスの固有のポート番号。 このポートは、コンピューター上の別のプロセスで使用することはできません。</p></td>
</tr>
</tbody>
</table>



### レポートサーバーの前提条件となるソフトウェア

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件と必要な設定</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされているバージョンの SQL Server</p></td>
<td align="left"><p>サポートされているバージョンについては、「 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 でサポートされている構成」をご覧ください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64ビット ASP.NET 登録</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web サーバーの役割</p></td>
<td align="left"><p>この役割は、管理サーバーでサポートされているサーバーオペレーティングシステムに追加する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web サーバー (IIS) 管理ツール</p></td>
<td align="left"><p>[ <strong> IIS 管理スクリプトとツール] をクリックし </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web サーバーの役割サービス</p></td>
<td align="left"><p>迷惑メールや悪意のあるデータがレポートサーバーに送信されるリスクを軽減するには、企業のセキュリティポリシーに従って、レポート Web サービスへのアクセスを制限する必要があります。</p>
<p><strong>一般的な HTTP 機能:</strong></p>
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
</ul>
<p><strong>管理ツール:</strong></p>
<ul>
<li><p>IIS 管理コンソール</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>既定のインストール場所</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft Application Virtualization Server</p></td>
</tr>
<tr class="odd">
<td align="left"><p>レポートサービスの web サイト名</p></td>
<td align="left"><p>レポート web サイトの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p>レポートサービスのポートバインディング</p></td>
<td align="left"><p>レポートサービスの固有のポート番号。 このポートは、コンピューター上の別のプロセスで使用することはできません。</p></td>
</tr>
</tbody>
</table>



### レポートデータベースの前提条件となるソフトウェア

レポートデータベースは、App-v 5.1 レポートサーバーを使用している場合にのみ必要です。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">前提条件と必要な設定</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>既定のインストール場所</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft Application Virtualization Server</p></td>
</tr>
<tr class="even">
<td align="left"><p>ユーザー設定の SQL Server インスタンスの名前 (該当する場合)</p></td>
<td align="left"><p>使用する書式: <strong> INSTANCENAME</strong></p>
<p>この形式は、インストールがローカルコンピューターにあることを前提としています。</p>
<p>SVR\INSTANCE 形式で名前を指定した <strong> 場合 </strong> 、インストールは失敗します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>カスタムデータベース名 (該当する場合)</p></td>
<td align="left"><p>一意のデータベース名。</p>
<p>既定値: AppVReporting</p></td>
</tr>
<tr class="even">
<td align="left"><p>レポートサーバーの場所</p></td>
<td align="left"><p>レポートサーバーが展開されているコンピューターアカウント。</p>
<p>使用する形式: \ machineaccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Reporting server インストール管理者</p></td>
<td align="left"><p>レポートサーバーをインストールするために使用されるアカウント。</p>
<p>使用する形式: \ アドミニストレーターログイン</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server サービスと Microsoft SQL Server Service Agent</p></td>
<td align="left"><p>これらのサービスを、query AD DS へのアクセス権を持つユーザーアカウントに関連付けられるように構成します。</p></td>
</tr>
</tbody>
</table>



## App-v client の必須ソフトウェア


以下の必須ソフトウェアを App-v クライアントにインストールします。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p></td>
<td align="left"><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>Windows 7 にのみ適用されます。 KB をダウンロードしてインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## リモートデスクトップサービスクライアントの前提条件となるソフトウェア


App-v リモートデスクトップサービスクライアントに対して、次の必須ソフトウェアをインストールします。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p></td>
<td align="left"><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>Windows 7 にのみ適用されます。 KB をダウンロードしてインストールします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 用の visual C++ 再頒布可能パッケージ</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## Sequencer の前提条件ソフトウェア


**前提条件をインストールする前に知っておくべきこと:**

-   ベストプラクティス: Sequencer を実行するコンピューターのハードウェアとソフトウェアの構成は、仮想アプリケーションを実行するコンピューターと同じにする必要があります。

-   シーケンス処理はリソースを大量に消費するため、Sequencer を実行するコンピューターに十分なメモリ、高速プロセッサ、高速のハードドライブを搭載していることを確認してください。 ローカルにインストールされたアプリケーションのシステム要件は、Sequencer のシステム要件を超えることはできません。 詳細については、「 [app-v 5.1 でサポートされている構成](app-v-51-supported-configurations.md)」を参照してください。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 (Web Installer)</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3.0</a></p>
<p></p></td>
<td align="left"><p>PowerShell 3.0 をインストールするには、再起動が必要です。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>Windows 7 にのみ適用されます。 KB をダウンロードしてインストールします。</p></td>
</tr>
</tbody>
</table>








## 関連トピック


[App-V 5.1 の計画](planning-for-app-v-51.md)

[App-V 5.1 でサポートされる構成](app-v-51-supported-configurations.md)









