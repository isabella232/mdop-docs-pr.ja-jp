---
title: APP-V を使用した Microsoft Office 2010 の展開
description: APP-V を使用した Microsoft Office 2010 の展開
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814626"
---
# APP-V を使用した Microsoft Office 2010 の展開


Microsoft Application Virtualization (App-v) 5.1 用の Office 2010 パッケージを作成するには、次のいずれかの方法を使用します。

-   Application Virtualization (App-v) Sequencer

-   Application Virtualization (App-v) パッケージアクセラレータ

## Office 2010 用の app-v サポート


次の表は、App-v のバージョン、Office パッケージの作成方法、サポートされているライセンス、Office 2010 のサポートされている展開方法を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされるアイテム</th>
<th align="left">サポートのレベル</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>サポートされている App-v のバージョン</p></td>
<td align="left"><ul>
<li><p>4.6</p></li>
<li><p>5.0</p></li>
<li><p>5.1</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>パッケージ作成</p></td>
<td align="left"><ul>
<li><p>付け</p></li>
<li><p>パッケージアクセラレータ</p></li>
<li><p>Office 展開キット</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>サポートされているライセンス</p></td>
<td align="left"><p>ボリューム ライセンス</p></td>
</tr>
<tr class="even">
<td align="left"><p>サポートされる展開</p></td>
<td align="left"><ul>
<li><p>Desktop</p></li>
<li><p>パーソナル VDI</p></li>
<li><p>RDS</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## Sequencer を使用した Office 2010 App-V 5.1 の作成


シーケンス Office 2010 は、App-v 5.1 で Office 2010 パッケージを作成するための主な方法の1つです。 Microsoft は、サポート技術情報の記事を通じて詳細なレシピを提供しています。 App-v 5.1 で Office 2010 パッケージを作成するには、詳細な手順については、次のリンクを参照してください。

[Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## パッケージアクセラレータを使用した Office 2010 App-V 5.1 パッケージの作成


Office 2010 アプリ-V 5.1 パッケージは、パッケージアクセラレータを使用して作成できます。 Microsoft は、windows 10、Windows 8、Windows 7 で Office 2010 を作成するためのパッケージアクセラレータを提供しています。 パッケージアクセラレータを使用して App-v で Office 2010 パッケージを作成するには、次のページを参照して適切なパッケージアクセラレータにアクセスしてください。

-   [Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 8)](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 7)](https://go.microsoft.com/fwlink/p/?LinkId=330678)

App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法の詳細については、「 [App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)」を参照してください。

## App-v 5.1 用 Microsoft Office パッケージの展開


Office 2010 パッケージを展開するには、次のいずれかの App-v 展開方法を使用します。

-   System Center Configuration Manager

-   App-v server

-   PowerShell コマンドを使用したスタンドアロン

## Office App-v パッケージの管理とカスタマイズ


Office 2010 パッケージは、既知のパッケージ管理メカニズムを通じて、他の App-v 5.1 パッケージと同じように管理できます。 Office パッケージの追加、公開、発行取り消し、削除など、特別な手順は必要ありません。

## Microsoft Office と Windows の統合


次の表では、Office 2010 でサポートされている統合ポイントの完全な一覧を示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">拡張点</th>
<th align="left">説明</th>
<th align="left">Office 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Firefox および Chrome 用の Lync 会議参加プラグイン</p></td>
<td align="left"><p>ユーザーは Firefox と Chrome から Lync 会議に参加できます</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>OneNote プリンタードライバーに送信されました</p></td>
<td align="left"><p>ユーザーは OneNote に印刷できます</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote のリンクノート</p></td>
<td align="left"><p>OneNote のリンクノート</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>OneNote Internet Explorer アドインに送る</p></td>
<td align="left"><p>ユーザーは IE から OneNote に送信できます</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync と Outlook のファイアウォール例外</p></td>
<td align="left"><p>Lync と Outlook のファイアウォール例外</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI クライアント</p></td>
<td align="left"><p>ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Firefox 用 SharePoint プラグイン</p></td>
<td align="left"><p>ユーザーは Firefox の SharePoint 機能を使用できる</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>メールコントロールパネルアプレット</p></td>
<td align="left"><p>ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="odd">
<td align="left"><p>プライマリ相互運用機能アセンブリ</p></td>
<td align="left"><p>マネージアドインのサポート</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office ドキュメントキャッシュハンドラー</p></td>
<td align="left"><p>Office アプリケーションのドキュメントキャッシュを許可します</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook プロトコルの検索ハンドラー</p></td>
<td align="left"><p>ユーザーが outlook で検索できる</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X コントロール:</p></td>
<td align="left"><p>ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove の各モバイルの場合</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect サイト</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   SharePoint のエクスポートデータベース</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SharePoint. DragUploadCtl</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   SharePoint. DragDownloadCtl</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Sharepoint Xmldocuments</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   Sharepoint のクリップボード Ctl</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx マネージャー</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNETListnet</p></td>
<td align="left"><p>Active X コントロール</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive Pro ブラウザーヘルパー</p></td>
<td align="left"><p>アクティブエックスコントロール]</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro アイコンのオーバーレイ</p></td>
<td align="left"><p>ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## その他の情報


**Office 2013 App-v パッケージのその他のリソース**

[シーケンス付きの App-v パッケージとして Microsoft Office を展開する場合のサポートされるシナリオ](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**Office 2010 App-v パッケージ**

[Microsoft Application Virtualization 5.0 用 microsoft Office 2010 シーケンスキット](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[App-v 5.0 Office 2010 パッケージを作成または使用するときの既知の問題](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**接続グループ**

[Microsoft App での接続グループの展開-V v5](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[接続グループの管理](managing-connection-groups51.md)

**動的構成**

[App-V 5.1 の動的構成について](about-app-v-51-dynamic-configuration.md)






 

 





