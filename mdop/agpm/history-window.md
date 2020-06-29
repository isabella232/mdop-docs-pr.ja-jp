---
title: '[履歴] ウィンドウ'
description: '[履歴] ウィンドウ'
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820787"
---
# [履歴] ウィンドウ


グループポリシーオブジェクト (GPO) の履歴を表示するには、GPO をダブルクリックするか、GPO を右クリックして [**履歴**] をクリックします。 各 GPO のタブとして、**グループポリシー管理コンソール**(GPMC) にも表示されます。

履歴には、アーカイブ内に保存された、選んだ GPO のすべてのバージョンの一覧が表示されます。 [**履歴**] ウィンドウから、gpo 内の設定のレポートを取得したり、gpo の複数のバージョンを比較したり、以前のバージョンの gpo にロールバックしたりすることができます。

## [履歴] ウィンドウのイベントをフィルター処理する


[**履歴**] ウィンドウ内のタブは、表示されたイベントをフィルター処理します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タブ</th>
<th align="left">フィルタリング</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>すべて表示</strong></p></td>
<td align="left"><p>GPO のすべてのバージョンを表示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>チェックイン済み</strong></p></td>
<td align="left"><p>チェックインされたバージョンの GPO のみを表示します。 展開されたバージョンは、この一覧には表示されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>ラベルのみ</strong></p></td>
<td align="left"><p>ラベルが関連付けられている Gpo のみを表示します。</p></td>
</tr>
</tbody>
</table>

 

## イベント情報


選択された GPO の履歴内の各イベントの情報が提供されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO の特性</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>コンピューター</strong></p></td>
<td align="left"><p>GPO のコンピューター構成部分の自動生成されたバージョン。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ユーザー</strong></p></td>
<td align="left"><p>自動的に生成される、GPO のユーザー構成部分のバージョン。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Time</strong></p></td>
<td align="left"><p>[状態] フィールドのアクションが実行されたときの GPO のバージョンのタイムスタンプ。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>状態</strong></p></td>
<td align="left"><p>選択された GPO の状態。</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong>展開済み </strong> : このバージョンの GPO は、現在の運用環境で有効です。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>チェックイン済み </strong> : このバージョンの GPO は、承認されたエディターが編集のためにチェックアウトするか、またはグループポリシー管理者が展開するために使用できます。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>チェックアウト済み </strong> : このバージョンの GPO は、現在、エディターによってチェックアウトされており、他のエディターでは使用できません。 (チェックアウト状態は、 <strong> に記録されません。履歴 </strong> 。 GPO が現在チェックアウトされているかどうかを示します。)</p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong>作成済み </strong> : GPO の最初の作成日と時刻を識別します。</p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong></strong>[ラベルあり: GPO のラベル付きバージョンを識別します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO の状態</strong></p></td>
<td align="left"><p>コンピューターの構成とユーザー構成は、個別に管理することができます。 この状態は、GPO のどの部分が有効になっているかを示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>所有者</strong></p></td>
<td align="left"><p>GPO をチェックインまたは展開したユーザー。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>コメント</strong></p></td>
<td align="left"><p>このバージョンが変更された時点での、GPO の所有者によって入力されたコメント。 以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</p></td>
</tr>
</tbody>
</table>

 

## レポート


1つの GPO バージョンと複数の GPO バージョンのどちらを選択するかによって、[**設定**] ボタンと [**相違点**] ボタンには、gpo 設定に関するレポートが表示されます。 [GPO バージョンの右クリック] では、XML ベースのレポートも表示できます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ボタン</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>設定</strong></p></td>
<td align="left"><p>選択したバージョンの GPO 内の設定を表示する HTML ベースのレポートを生成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>相違点</strong></p></td>
<td align="left"><p>複数の選択されたバージョンの GPO 内の設定を比較する HTML ベースのレポートを生成します。</p></td>
</tr>
</tbody>
</table>

 

### 差分レポートの重要な部分

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">シンボル</th>
<th align="left">意味</th>
<th align="left">色</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>なし</p></td>
<td align="left"><p>両方の Gpo で同じ設定のアイテムが存在する</p></td>
<td align="left"><p>レベルによって異なる</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[#]</strong></p></td>
<td align="left"><p>アイテムは両方の Gpo に存在しますが、設定が変更されています。</p></td>
<td align="left"><p>Rgb</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>[-]</strong></p></td>
<td align="left"><p>アイテムは最初の GPO にのみ存在します</p></td>
<td align="left"><p>赤</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[+]</strong></p></td>
<td align="left"><p>項目は2番目の GPO にのみ存在します</p></td>
<td align="left"><p>緑</p></td>
</tr>
</tbody>
</table>

 

-   設定が変更されたアイテムについては、アイテムが展開されると、変更された設定が識別されます。 各 GPO の属性の値は、レポートに Gpo が表示される順序で表示されます。

-   一部の設定を変更すると、変更された項目としてではなく、項目が2つの異なる項目 (1 つ目の GPO でのみ存在する) として報告される場合があります。

### その他の参照情報

-   [[内容] タブ](contents-tab.md)

 

 





