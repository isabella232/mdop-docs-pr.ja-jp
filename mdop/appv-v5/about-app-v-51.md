---
title: App-V 5.1 について
description: App-V 5.1 について
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4f2404dcd431b32f5d9a4ae7c49f1e376979e04e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814947"
---
# App-V 5.1 について


Application Virtualization (App-v) 5.1 に適用される重大な変更に関する情報を確認するには、次のセクションを使用します。

[App-v 5.1 ソフトウェアの前提条件とサポートされる構成](#bkmk-51-prereq-configs)

[App への移行-V 5.1](#bkmk-migrate-to-51)

[App-v 5.1 の新機能](#bkmk-whatsnew)

[Windows 10 での app-v のサポート](#bkmk-win10support)

[App-v 管理コンソールの変更](#bkmk-mgmtconsole)

[Sequencer の機能強化](#bkmk-seqimprove)

[パッケージコンバーターの改善](#bkmk-pkgconvimprove)

[1つのイベントトリガーでの複数のスクリプトのサポート](#bkmk-supmultscripts)

[インストールフォルダーへのハードコーディングされたパスは、仮想ファイルシステムのルートにリダイレクトされます](#bkmk-hardcodepath)

## <a href="" id="bkmk-51-prereq-configs"></a>App-v 5.1 ソフトウェアの前提条件とサポートされる構成


App-V 5.1 ソフトウェアの前提条件とサポートされる構成については、次のリンクを参照してください。

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
<td align="left"><p><a href="app-v-51-prerequisites.md" data-raw-source="[App-V 5.1 Prerequisites](app-v-51-prerequisites.md)">App-V 5.1 の前提条件</a></p></td>
<td align="left"><p>App-v 5.1 のインストールを開始する前にインストールする必要がある必須ソフトウェア</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 でサポートされる構成</a></p></td>
<td align="left"><p>App-v Server、Sequencer、およびクライアントコンポーネントのサポートされているオペレーティングシステムとハードウェアの要件</p></td>
</tr>
</tbody>
</table>



**Configuration Manager を app-v と共に使用する場合のサポート:** App-v 5.1 は System Center 2012 R2 Configuration Manager SP1 をサポートしています。 構成マネージャーと構成マネージャーとのアプリの統合については、「 [Configuration manager とのアプリの統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」をご覧ください。

## <a href="" id="bkmk-migrate-to-51"></a>App への移行-V 5.1


以前のバージョンから App-v 5.1 にアップグレードするには、次の情報を使用します。 詳細について[は、「以前のバージョンから app-v 5.1 に移行する](migrating-to-app-v-51-from-a-previous-version.md)」を参照してください。

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
<td align="left"><p>アップグレードするコンポーネント (任意の順序)</p></td>
<td align="left"><ol>
<li><p>App-v Server</p></li>
<li><p>Sequencer (シーケンサー)</p></li>
<li><p>App-v Client または App-v リモートデスクトップサービス (RDS) クライアント</p></li>
</ol>
<div class="alert">
<strong>注</strong><br/><p>App-v 5.0 SP2 より前に、クライアント管理ユーザーインターフェイス (UI) は、App-v クライアントのインストールで提供されていました。 App-v 5.0 SP2 インストール (以降) の場合は、 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> Application Virtualization 5.0 クライアント UI アプリケーションからダウンロードして、クライアント管理 UI を使用でき </a> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>アプリからのアップグレード-V 4. x</p></td>
<td align="left"><p>まず、App-V 5.0 にアップグレードする必要があります。 App-v から app-v 5.1 に直接アップグレードすることはできません。 詳細については、以下を参照してください。</p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">アプリ-v 5.0 についての「app-v 4.6 と app-v 5.0 の違い」</a></p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">APP-V の以前のバージョンからの移行計画</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.0 以降からのアップグレード</p></td>
<td align="left"><p>以下のいずれかのバージョンから直接 App-v 5.1 にアップグレードできます。</p>
<ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
<li><p>App-v 5.0 SP3</p></li>
</ul>
<p>App-v 5.1 にアップグレードするには、このトピックの残りのセクションの手順に従います。</p>
<p>パッケージと接続グループは、現在の場合と同様に、引き続き App-v 5.1 で動作します。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>App-v インフラストラクチャのアップグレード手順

次の手順を実行して、app-v インフラストラクチャの各コンポーネントを App-v 5.1 にアップグレードします。 次の順序は提案にすぎません。コンポーネントのアップグレードは任意の順序で行うことができます。

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
<div class="alert">
<strong>注</strong><br/><p>App-v Server を使っていない場合は、この手順をスキップして次の手順に進みます。</p>
</div>
<div>

</div></td>
<td align="left"><p>次の手順に従います。</p>
<ol>
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
<td align="left"><p>この手順をスキップして、「App-v Server をアップグレードする場合」の手順2に進みます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL スクリプト</p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)">「SQL スクリプトを使用して App-v データベースを展開する方法」の手順に従い </a> ます。</p></td>
</tr>
</tbody>
</table>
<li><p>App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降でアップグレードする場合は、「 <a href="check-reg-key-svr.md" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](check-reg-key-svr.md)"> app-v 5.0 SP3 サーバーをインストールした後でレジストリキーを確認する」の手順を実行し </a> ます。</p></li>
<li><p>「 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> App-v 5.1 サーバーを展開する方法」の手順に従ってください。</a></p></li>
<p> </p></li>
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



### 以前のバージョンの App-v を使用して作成されたパッケージの変換

Package converter ユーティリティーを使って、app-v 5.0 のバージョンを使って作成された仮想アプリケーションパッケージをアップグレードしてください。 パッケージコンバーターは、PowerShell を使用してパッケージを変換し、変換が必要なパッケージが多い場合は、プロセスの自動化に役立ちます。

**注**  
App-v 5.1 パッケージは、app-v 5.0 パッケージとまったく同じです。 バージョン間のパッケージ形式は変更されていないため、App-v 5.0 パッケージを App-v 5.1 パッケージに変換する必要はありません。



## <a href="" id="bkmk-whatsnew"></a>App-v 5.1 の新機能


これらのセクションは、既に App-v に精通していて、App-v 5.1 で何が変更されているかを確認したいユーザーを対象としています。 まだ App-v に精通していない場合は、まず「 [app-v 5.1 の計画](planning-for-app-v-51.md)」を参照してください。

### <a href="" id="bkmk-win10support"></a>Windows 10 での app-v のサポート

次の表は、Windows 10 の App-v のサポートを示しています。 Windows 10 は、アプリ-v 5.1 より前のバージョンではサポートされていません。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンポーネント</th>
<th align="left">App-V 5.1</th>
<th align="left">App-v 5.0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v クライアント</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v RDS クライアント</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v Sequencer</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>なし</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-mgmtconsole"></a>App-v 管理コンソールの変更

このセクションでは、App-v 管理コンソールの現在の機能と以前の機能を比較します。

### Silverlight は必要なくなりました

管理コンソールの UI には Silverlight は不要です。 5.1 管理コンソールは、HTML5 と Javascript で構築されています。

### 通知とメッセージが個別にダイアログボックスに表示される

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリの新バージョン-V 5.1</th>
<th align="left">App-v 5.1 より前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>メッセージ数:</strong></p>
<p>App-v 管理コンソールのタイトルバーで、表示待ちのメッセージの数を示すフラグアイコンの横に数字が表示されるようになりました。</p></td>
<td align="left"><p>一度に1つのメッセージまたはエラーしか表示されず、表示されたメッセージの数を確認できませんでした。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>メッセージの外観:</strong></p>
<ul>
<li><p>ユーザー入力が必要なメッセージは、表示されている現在のページの上部に表示される別のダイアログボックスに表示されます。このダイアログボックスを閉じる前に返信する必要があります。</p></li>
<li><p>メッセージとエラーがリストに表示され、その下に1つが表示されます。</p></li>
</ul></td>
<td align="left"><p>一度に1つのメッセージまたはエラーしか表示できません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>メッセージを消す:</strong></p>
<p>すべての <strong> メッセージとエラーを一度に無視するには、[すべて消去 </strong> ] リンクを使います。または、一度に1つずつ閉じます。</p></td>
<td align="left"><p>一度に1つのメッセージとエラーを消すことができます。</p></td>
</tr>
</tbody>
</table>



### 本体のページが別の Url になりました

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリの新バージョン-V 5.1</th>
<th align="left">App-v 5.1 より前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>本体の各ページには異なる URL があります。これにより、特定のページをブックマークして、後ですばやくアクセスできるようになります。</p>
<p>一部の Url に表示される番号は、特定のパッケージを示します。 これらの番号は一意です。</p></td>
<td align="left"><p>すべてのコンソールページは、同じ URL 経由でアクセスされます。</p></td>
</tr>
</tbody>
</table>



### [新規]、[別の接続グループ] ページ、および [メニュー] オプション

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリの新バージョン-V 5.1</th>
<th align="left">App-v 5.1 より前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>[接続グループ] ページは、[パッケージ] ページと同じレベルで、メインメニューの一部になります。</p></td>
<td align="left"><p>[接続グループ] ページを開くには、[パッケージ] ページ内を移動します。</p></td>
</tr>
</tbody>
</table>



### パッケージのメニューオプションが変更されました

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アプリの新バージョン-V 5.1</th>
<th align="left">App-v 5.1 より前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>[パッケージ] ページの下部に表示される [現在のオプション] ボタンは次のとおりです。</p>
<ul>
<li><p>追加またはアップグレード</p></li>
<li><p>公開</p></li>
<li><p>発行</p></li>
<li><p>Delete</p></li>
</ul>
<p>次のオプションは、パッケージを右クリックしてドロップダウンコンテキストメニューを開くときにも表示されます。</p>
<ul>
<li><p>公開</p></li>
<li><p>発行</p></li>
<li><p>広告アクセスの編集</p></li>
<li><p>展開構成を編集する</p></li>
<li><p>展開構成を転送...</p></li>
<li><p>アクセスと構成を転送する...</p></li>
<li><p>Delete</p></li>
</ul>
<p>[削除] をクリックして <strong> </strong> パッケージを削除すると、ダイアログボックスが開き、パッケージを削除するかどうかを確認するメッセージが表示されます。</p></td>
<td align="left"><p>[ <strong> 追加] または [アップグレード] オプションは、[ </strong> パッケージ] ページの右上のボタンです。</p>
<p>[ <strong> 発行 </strong> ]、[非公開]、および [削除] オプションは、[ <strong> </strong> <strong> </strong> パッケージ] 一覧でパッケージ名を右クリックした場合にのみ使用できました。</p></td>
</tr>
<tr class="even">
<td align="left"><p>次のパッケージ操作は、各パッケージの [パッケージの詳細] ページのボタンになります。</p>
<ul>
<li><p>転送 (ドロップダウンメニューには、次のオプションがあります)。</p>
<ul>
<li><p>展開構成を転送...</p></li>
<li><p>アクセスと構成を転送する...</p></li>
</ul></li>
<li><p>編集 (接続グループと広告アクセス)</p></li>
<li><p>発行</p></li>
<li><p>Delete</p></li>
<li><p>既定の構成を編集する</p></li>
</ul></td>
<td align="left"><p>これらのパッケージオプションは、[パッケージ] 一覧でパッケージ名を右クリックした場合にのみ使用できました。</p></td>
</tr>
</tbody>
</table>



### 左側のウィンドウのアイコンに新しい色とテキストが設定されている

左側のウィンドウのアイコンの色が変更され、テキストが追加され、アイコンが他の Microsoft 製品と一貫性が保たれます。

### 概要ページが削除されました

管理コンソールの左側のウィンドウで、[概要] メニューオプションとそれに関連する概要ページが削除されました。

### <a href="" id="bkmk-seqimprove"></a>Sequencer の機能強化

App-v 5.1 Sequencer のパッケージエディターには、次のような改善が加えられました。

### マニフェストファイルをインポートおよびエクスポートする

AppxManifest.xml ファイルをインポートしてエクスポートすることができます。 マニフェストファイルをエクスポートするには、[**詳細設定**] タブを選択し、[マニフェストファイル] ボックスで [**エクスポート**] をクリックします。マニフェストファイルに変更を加えることができます。たとえば、シェルの拡張機能の削除やファイルの種類の関連付けの編集などです。

変更を加えたら、[**インポート**] をクリックし、編集したファイルを選択します。 再びインポートした後、マニフェストファイルはパッケージエディター内ですぐに更新されます。

**注意**  
ファイルをインポートすると、その変更は XML スキーマに対して検証されます。 ファイルが有効でない場合は、エラーが表示されます。 XML スキーマに対して検証されたファイルをインポートすることはできますが、その他の理由でまだ実行できない場合があることに注意してください。



### Windows 10 からオペレーティングシステムの一覧への追加

[展開] タブで、Windows 10 32 ビットと Windows 10-64 ビットがパッケージのシーケンスを行うことができるオペレーティングシステムの一覧に追加されています。 **任意のオペレーティングシステム**を選択した場合は、シーケンス処理されたパッケージでサポートされるオペレーティングシステムの間に Windows 10 が自動的に含まれます。

### 仮想レジストリエディターの下部に現在のパスが表示される

[仮想レジストリ] タブでは、現在選択されているキーを確認できるように、仮想レジストリエディターの下部にパスが表示されます。 以前は、現在選択されているキーを見つけるためにレジストリツリーをスクロールする必要がありました。

### <a href="" id="combined--find-and-replace--dialog-box-and-shortcut-keys-added-in-virtual-registry-editor"></a>[検索と置換] ダイアログボックスと、仮想レジストリエディターに追加されたショートカットキーの組み合わせ

仮想レジストリエディターでは、検索オプション (Ctrl + F) のショートカットキーが追加され、[検索] と [置換] のタスクを結合したダイアログボックスが追加され、値とデータの検索と置換を行うことができます。 この結合ダイアログボックスにアクセスするには、キーを選択し、次のいずれかの操作を行います。

-   Ctrl キーを押し**ながら H**キーを押します。

-   キーを右クリックし、[**置換**] を選択します。

-   [ **View** &gt; **Virtual Registry** &gt; **Replace**の表示] を選択します。

以前は、[置換] ダイアログボックスは存在しませんでした。手動で変更を行う必要がありました。

### レジストリキーとパッケージファイルの名前を正常に変更する

Sequencer の問題が発生しなくても、仮想レジストリキーとファイルの名前を変更することができます。 以前は、キーの名前を変更しようとした場合、Sequencer は動作を停止しました。

### 仮想レジストリキーのインポートとエクスポート

仮想レジストリキーのインポートとエクスポートを行うことができます。 キーをインポートするには、キーをインポートするノードを右クリックし、インポートするキーに移動して、[**インポート**] をクリックします。 キーをエクスポートするには、キーを右クリックし、[**エクスポート**] を選択します。

### 仮想ファイルシステムにディレクトリをインポートする

ディレクトリを VFS にインポートすることができます。 ディレクトリをインポートするには、[**パッケージファイル**] タブをクリック**View**し、[ &gt; **仮想ファイルシステム** &gt; の**インポートディレクトリ**の表示] をクリックします。 既に VFS に登録されているファイルを含むディレクトリをインポートしようとすると、インポートが失敗し、説明メッセージが表示されます。 App-v 5.1 より前のバージョンでは、ディレクトリをインポートできませんでした。

### VFS ファイルを削除してパッケージに追加し直すことなくインポートまたはエクスポートする

ファイルを削除することなく、VFS からファイルをインポートまたはエクスポートして、ファイルをパッケージに戻すことはできません。 たとえば、この機能を使って、変更ログをローカルドライブにエクスポートし、外部エディターを使用してファイルを編集してから、ファイルを VFS に再インポートすることができます。

ファイルをエクスポートするには、[**パッケージファイル**] タブを選択し、VFS 内のファイルを右クリックして [**エクスポート**] をクリックし、編集を行うことができるエクスポート場所を選びます。

ファイルをインポートするには、[**パッケージファイル**] タブを選択し、エクスポートしたファイルを右クリックします。 編集したファイルを参照し、[**インポート**] をクリックします。 インポートされたファイルによって、既存のファイルが上書きされます。

ファイルをインポートした後、[**ファイル**の保存] をクリックしてパッケージを保存する必要があり &gt; **Save**ます。

### パッケージファイルの追加のメニューが移動されました

パッケージファイルを追加するためのメニューオプションが移動されました。 [追加] オプションを見つけるには、[**パッケージファイル**] タブを選択し、[ **View** &gt; **仮想ファイルシステム**の表示] をクリックし &gt; **Add File**ます。 以前は、[VFS] ノードの下にあるフォルダーを右クリックし、[**ファイルの追加**] を選択しました。

### 仮想レジストリノードによって、既定でマシンとユーザーのハイブが拡張される

仮想レジストリを開くと、コンピューターとユーザーのハイブがトップレベルのレジストリノードの下に表示されます。 以前は、[REGISTRY] ノードを展開して、その下にあるハイブを表示する必要がありました。

### Browser Helper オブジェクトを有効または無効にする

ブラウザーヘルパーオブジェクトを有効または無効にするには、Sequencer のユーザーインターフェイスの [詳細設定] タブで、[ブラウザーヘルパーオブジェクトを有効にする] チェックボックスをオンまたはオフにします。 Browser Helper オブジェクトの場合:

-   パッケージ内に存在し、有効になっている場合は、既定でチェックボックスがオンになっています。

-   パッケージ内に存在し、無効になっている場合、このチェックボックスは既定でオフになっています。

-   パッケージ内に存在し、1つ以上の有効な状態と1つ以上の無効な場合は、チェックボックスは既定で [不確定] に設定されます。

-   パッケージには存在しません。このチェックボックスは無効です。

### <a href="" id="bkmk-pkgconvimprove"></a>パッケージコンバーターの改善

これで、パッケージコンバーターを使用して、スクリプトを含む App-v 4.6 パッケージ、ソースからのレジストリ情報とスクリプトをパッケージコンバーター出力に含めることができるようになりました。

例を含む詳細については、「[以前のバージョンからの app-v 5.1 への移行](migrating-to-app-v-51-from-a-previous-version.md)」を参照してください。

### <a href="" id="bkmk-supmultscripts"></a>1つのイベントトリガーでの複数のスクリプトのサポート

App-v 5.1 は、app-v パッケージの1つのイベントトリガーで複数のスクリプトを使うことをサポートしています。これには、アプリ-V 4.6 から App-v 5.0 以降に変換するパッケージが含まれます。 複数のスクリプトを使用できるようにするために、App-v 5.1 は、ScriptRunner.exe という名前のスクリプト起動アプリケーションを使用します。このアプリケーションは、App-v クライアントのインストールの一部としてインストールされます。

イベントトリガーの一覧やスクリプトを実行できるコンテキストなどの詳細については、「 [app-v 5.1 の動的構成について](about-app-v-51-dynamic-configuration.md)」のスクリプトセクションを参照してください。

### <a href="" id="bkmk-hardcodepath"></a>インストールフォルダーへのハードコーディングされたパスは、仮想ファイルシステムのルートにリダイレクトされます

パッケージを App-v 4.6 から5.1 に変換する場合、App-v 5.1 パッケージは、4.6 パッケージを作成するときに必要だったハードコードされたドライブにアクセスできます。 ドライブ文字は、4.6 の優先順位のコンピューターでインストールドライブとして選択したドライブになります。 (既定のドライブ文字は Q:\\.)

以前は、4.6 ルートフォルダーは認識されず、App-v 5.0 パッケージによってアクセスできませんでした。 App-v 5.1 パッケージでは、完全なパスを使用してハードコーディングされたファイルにアクセスしたり、プログラムによってアプリ-V 4.6 のインストールルートでファイルを列挙したりすることができます。

**技術的な詳細:** App-v 5.1 パッケージコンバーターによって、Filesystem 要素の FilesystemMetadata.xml ファイルに、App-v 4.6 インストールルートフォルダーと短いフォルダー名が保存されます。 App-v 5.1 クライアントで仮想プロセスが作成されると、アプリ-V 4.6 インストールルートから仮想ファイルシステムのルートへの要求がマップされます。

## MDOP 技術の入手方法


App-v は、Microsoft デスクトップ最適化パック (MDOP) の一部です。 MDOP は、Microsoft ソフトウェアアシュアランスの一部です。 Microsoft ソフトウェアアシュアランスと MDOP の入手の詳細については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください。






## 関連トピック


[App-V 5.1 のリリース ノート](release-notes-for-app-v-51.md)









