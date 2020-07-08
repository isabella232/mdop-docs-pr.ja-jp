---
title: '[履歴] ウィンドウ'
description: '[履歴] ウィンドウ'
author: dansimp
ms.assetid: 114f50a4-508d-4589-b006-6cd05cffe6b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81911b5103c76e267d806fb7cd8acf55811440c9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820797"
---
# [履歴] ウィンドウ


グループポリシーオブジェクト (GPO) の履歴を表示するには、GPO をダブルクリックするか、GPO を右クリックして [**履歴**] をクリックします。 各 GPO のタブとして、**グループポリシー管理コンソール**(GPMC) にも表示されます。

履歴には、選択した GPO の有効期間内のイベントのレコードが表示されます。 [**履歴**] ウィンドウから、gpo の1つのバージョン内の設定のレポートを取得したり、gpo の複数のバージョンを比較したり、以前のバージョンの gpo にロールバックしたりすることができます。

## [履歴] ウィンドウのイベントをフィルター処理する


[**履歴**] ウィンドウ内のタブは、GPO の履歴の状態をフィルター処理します。

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
<td align="left"><p><strong>すべての状態</strong></p></td>
<td align="left"><p>GPO の履歴にすべての状態を表示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>固有バージョン</strong></p></td>
<td align="left"><p>アーカイブにチェックインされた固有のバージョンの GPO のみを表示します。 運用環境に展開されているバージョン、固有のバージョンのショートカット、および情報の状態は、この一覧から省略されます。</p></td>
</tr>
</tbody>
</table>



## イベント情報


各状態についての情報は、GPO の履歴に記載されています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 属性</th>
<th align="left">説明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>日付を変更する</strong></p></td>
<td align="left"><p><strong>状態列で操作 </strong> が実行された時刻のタイムスタンプです。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>状態</strong></p></td>
<td align="left"><p>GPO の履歴の状態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>変更者</strong></p></td>
<td align="left"><p>GPO をチェックインまたは展開したユーザー。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>コメント</strong></p></td>
<td align="left"><p>このバージョンの変更時に、GPO をチェックインまたは展開したユーザーによって入力されたコメント。 以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>不可</strong></p></td>
<td align="left"><p>アーカイブに保持されている各 GPO の一意のバージョンの数が制限されている場合に、このバージョンの GPO を削除できるかどうか。</p>
<div class="alert">
<strong>注</strong><br/><p>GPO のバージョンが削除されるかどうかを変更するには、それを右クリックして、[削除を許可しない] または [削除を許可する] をクリックし <strong> </strong> <strong> </strong> ます。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>コンピューターのバージョン</strong></p></td>
<td align="left"><p>GPO のコンピューター構成部分の自動生成されたバージョン。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>ユーザーバージョン</strong></p></td>
<td align="left"><p>自動的に生成される、GPO のユーザー構成部分のバージョン。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO の状態</strong></p></td>
<td align="left"><p>コンピューターの構成とユーザー構成は、個別に管理することができます。 この状態は、GPO のどの部分が有効になっているかを示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>WMI フィルター</strong></p></td>
<td align="left"><p>この GPO に適用されているすべての WMI フィルターを表示します。 WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] フォルダーで管理されます。</p></td>
</tr>
</tbody>
</table>



## レポート


[**設定**と**相違点**] ボタンでは、選択した gpo のバージョンまたはバージョンの gpo 設定に関するレポートが表示されます。 [GPO バージョンの右クリック] では、XML ベースのレポートも表示できます。

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

-   [[内容] タブ](contents-tab-agpm30ops.md)









