---
title: APP-V で Office を使用するための計画
description: APP-V で Office を使用するための計画
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813426"
---
# APP-V で Office を使用するための計画


以下の情報を使用して、App-v を使って Office を展開する方法を計画します。 この記事の内容は次のとおりです。

-   [言語パック用の app-v サポート](#bkmk-lang-pack)

-   [サポートされている Microsoft Office のバージョン](#bkmk-office-vers-supp-appv)

-   [共存バージョンの Office での App-v の使用を計画する](#bkmk-plan-coexisting)

-   [Office を展開するときに Office を展開するときに Windows と統合する方法](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a>言語パック用の app-v サポート


アプリ-V 5.0 Sequencer を使って、言語パック、言語インターフェイスパック、校正ツール、ポップヒント言語用のプラグインパッケージを作成できます。 その後、Office 展開ツールキットを使って作成した Office 2013 パッケージと共に、接続グループにプラグインパッケージを含めることができます。 Office アプリケーションとプラグイン言語パックは、接続グループで一緒にグループ化されている他のパッケージと同じように、同じ接続グループでシームレスにやり取りされます。

**注** Microsoft Visio および Microsoft Project は、タイ語言語パックのサポートを提供していません。

 

## <a href="" id="bkmk-office-vers-supp-appv"></a>サポートされている Microsoft Office のバージョン


次の表に、App-v でサポートされている Microsoft Office のバージョン、Office パッケージの作成方法、サポートされているライセンス、サポートされている展開の一覧を示します。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされている Office のバージョン</th>
<th align="left">サポートされている App-v のバージョン</th>
<th align="left">パッケージの作成</th>
<th align="left">サポートされているライセンス</th>
<th align="left">サポートされている展開</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>エンタープライズ向けの Microsoft 365 アプリ</p>
<p>以下もサポートされています。</p>
<ul>
<li><p>Visio Pro for Office 365</p></li>
<li><p>Project Pro for Office 365</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 展開ツール</p></td>
<td align="left"><p>サブスクリプション</p></td>
<td align="left"><ul>
<li><p>Desktop</p></li>
<li><p>パーソナル VDI</p></li>
<li><p>プールされた VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Office Professional Plus 2013</p>
<p>以下もサポートされています。</p>
<ul>
<li><p>Visio Professional 2013</p></li>
<li><p>Project Professional 2013</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-v 5.0</p></li>
<li><p>App-v 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 展開ツール</p></td>
<td align="left"><p>ボリューム ライセンス</p></td>
<td align="left"><ul>
<li><p>Desktop</p></li>
<li><p>パーソナル VDI</p></li>
<li><p>プールされた VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a>共存バージョンの Office での App-v の使用を計画する


"Microsoft Office の共存" を使用すると、同じコンピューターに複数のバージョンの Microsoft Office を同時にインストールできます。 Windows Installer ベース (MSi) バージョンの Office、クイック実行、および App-v 5.0 SP2 を使用して、office のすべての主要バージョンとインストール方法を組み合わせて、office を共存させることができます。 ただし、Microsoft では Office の共存を使用することはお勧めしません。

Microsoft の推奨されるベストプラクティスは、互換性の問題を回避するために、Office を完全に共存させないようにすることです。 ただし、新しいバージョンの Office に移行する場合は、すぐに解決できない問題が発生する可能性があるため、一時的に共存を実装して、最新の製品バージョンへの移行を容易にすることができます。 長期ベースで Office の共存を使用することはお勧めしません。また、組織では、すぐに完全に移行するための計画が必要です。

### Office の共存を実装する前に

Office の共存を実装する前に、次の Office ドキュメントを確認してください。 共存を実装する予定の最新バージョンの Office に対応する記事を選択します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Office のバージョン</th>
<th align="left">ガイダンスへのリンク</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)">他のバージョンの Office を実行しているコンピューターで Office 2013 スイートとプログラム (MSI 展開) を使用する方法についての情報</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)">他のバージョンの Office を実行しているコンピューターで Office 2010 スイートとプログラムを使用する方法についての情報</a></p></td>
</tr>
</tbody>
</table>

 

Office ドキュメントでは、Windows Installer ベース (MSi) およびクイック実行インストールの Office の共存に関する広範なガイダンスを提供しています。 このアプリの共存に関するこのトピックでは、App-v の展開に固有の情報を使用して Office ガイダンスを補足します。

### サポートされている Office の共存シナリオ

次の表は、サポートされている共存シナリオをまとめたものです。 これらは、最初に使用しているバージョンと展開方法と、移行するバージョンおよび展開方法に従って構成されます。 実働の対象ユーザーに展開する前に、すべての共存ソリューションを完全にテストしてください。

**注** Microsoft は、リモートデスクトップセッションホストの役割サービスが有効になっている Windows Server 環境での複数バージョンの Office の使用をサポートしていません。 Office の共存シナリオを実行するには、この役割サービスを無効にする必要があります。

 

### Windows 統合 & Office の共存

Windows Installer ベースおよびクイック実行の Office インストール方法は、基になる Windows オペレーティングシステムの特定のポイントと統合されます。 共存を使用すると、2つの Office バージョン間での一般的なオペレーティングシステムの統合が競合し、互換性とユーザーエクスペリエンスの問題が発生する可能性があります。 App-v では、特定のバージョンの Office をシーケンスして、統合を除外し、オペレーティングシステムから "分離" することができます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">このバージョンの Office を順序指定できるモード (App-v)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2007</p></td>
<td align="left"><p>常に統合されていない。 App-v は、仮想化されたバージョンの Office 2007 とのオペレーティングシステム統合を提供しません。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p>統合モードと非統合モード。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p>常に統合されます。 Windows オペレーティングシステムの統合を無効にすることはできません。</p></td>
</tr>
</tbody>
</table>

 

Microsoft では、統合された Office インスタンスを1つだけ使用して Office を共存させることをお勧めします。 たとえば、Office 2010 と Office 2013 を展開するために App-v を使っている場合は、非統合モードで Office 2010 をシーケンスする必要があります。 統合されていない (分離) モードでの Office の優先順位については、「microsoft [Application Virtualization 5.0 で Microsoft office 2010 の順序を付ける方法](https://support.microsoft.com/kb/2830069)」を参照してください。

### Office の共存シナリオの既知の制限事項

以下のセクションでは、App-v を使用して Office との共存を実装するときに発生する可能性のあるいくつかの問題について説明します。

### Windows Installer ベースまたはクイック実行および App-v Office の共存シナリオに関する制限事項

同じコンピューターに次のバージョンの Office をインストールすると、次のような制限が発生する可能性があります。

-   Windows インストーラーベースのバージョンを使用した Office 2010 の場合

-   Office 2013 (app-v を使用)

以前のバージョンの Windows Installer ベースの Office 2010 を使用して、Office 2013 を side-by-side 使用して公開した後、Windows インストーラーが起動されることがあります。 これは、Windows Installer ベースまたはクイック実行バージョンの Office 2010 が、自動的にそのコンピューターに登録しようとしているためです。

ネイティブ Word 2010 の自動登録操作をバイパスするには、次の手順を実行します。

1.  Word 2010 を終了します。

2.  次の操作を行って、レジストリエディターを起動します。

    -   Windows 7 の場合: [**スタート**] ボタンをクリックし、[検索の開始] ボックスに「 **regedit** 」と入力して、enter キーを押します。

    -   Windows 8 では、スタートページで enter キー**を押し、enter キーを**押します。

    管理者パスワードまたは確認のメッセージが表示された場合は、パスワードを入力するか、[**続行**] をクリックします。

3.  次のレジストリサブキーを見つけて選択します。

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  [**編集**] メニューの [**新規作成**] をクリックし、[ **DWORD 値**] をクリックします。

5.  「 **NoReReg**」と入力して、enter キーを押します。

6.  [ **NoReReg** ] を右クリックし、[**変更**] をクリックします。

7.  [ **Valuedata** ] ボックスに「 **1**」と入力し、[ **OK**] をクリックします。

8.  [ファイル] メニューの [**終了**] をクリックして、レジストリエディターを終了します。

## <a href="" id="bkmk-office-integration-win"></a>App-v を使用して Office を展開するときの、Office と Windows との統合方法


App-v を使用して Office 2013 を展開すると、Office はオペレーティングシステムと完全に統合されます。これにより、office は、アプリを展開した場合と同じ機能と機能をエンドユーザーに提供します。

Office 2013 App-v パッケージでは、次の統合ポイントが Windows オペレーティングシステムと共にサポートされています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">拡張点</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Firefox および Chrome 用の Lync 会議参加プラグイン</p></td>
<td align="left"><p>ユーザーは Firefox と Chrome から Lync 会議に参加できます</p></td>
</tr>
<tr class="even">
<td align="left"><p>OneNote プリンタードライバーに送信されました</p></td>
<td align="left"><p>ユーザーは OneNote に印刷できます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote のリンクノート</p></td>
<td align="left"><p>OneNote のリンクノート</p></td>
</tr>
<tr class="even">
<td align="left"><p>OneNote Internet Explorer アドインに送る</p></td>
<td align="left"><p>ユーザーは IE から OneNote に送信できます</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync と Outlook のファイアウォール例外</p></td>
<td align="left"><p>Lync と Outlook のファイアウォール例外</p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI クライアント</p></td>
<td align="left"><p>ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Firefox 用 SharePoint プラグイン</p></td>
<td align="left"><p>ユーザーは Firefox の SharePoint 機能を使用できる</p></td>
</tr>
<tr class="even">
<td align="left"><p>メールコントロールパネルアプレット</p></td>
<td align="left"><p>ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プライマリ相互運用機能アセンブリ</p></td>
<td align="left"><p>マネージアドインのサポート</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office ドキュメントキャッシュハンドラー</p></td>
<td align="left"><p>Office アプリケーションのドキュメントキャッシュを許可します</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook プロトコルの検索ハンドラー</p></td>
<td align="left"><p>ユーザーが outlook で検索できる</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X コントロール:</p></td>
<td align="left"><p>ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove の各モバイルの場合</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect サイト</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   SharePoint のエクスポートデータベース</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SharePoint. DragUploadCtl</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   SharePoint. DragDownloadCtl</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Sharepoint の OpenXMLDocuments</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   Sharepoint のクリップボード Ctl</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx マネージャー</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNETListnet</p></td>
<td align="left"><p>Active X コントロール</p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive Pro ブラウザーヘルパー</p></td>
<td align="left"><p>アクティブエックスコントロール]</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro アイコンのオーバーレイ</p></td>
<td align="left"><p>ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</p></td>
</tr>
<tr class="even">
<td align="left"><p>シェル拡張</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ショートカット</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Search</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





