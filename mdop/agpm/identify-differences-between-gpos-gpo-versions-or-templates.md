---
title: GPO、GPO のバージョン、またはテンプレート間の相違点を識別する
description: GPO、GPO のバージョン、またはテンプレート間の相違点を識別する
author: dansimp
ms.assetid: 6320afc4-af81-47e8-9f4c-463ff99d5a53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fd7966c9c72b2f0d30595af55520940c779a409f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820757"
---
# GPO、GPO のバージョン、またはテンプレート間の相違点を識別する


HTML ベースまたは XML ベースの差分レポートを生成して、グループポリシーオブジェクト (Gpo)、テンプレート、または異なるバージョンの GPO の違いを分析できます。

この手順を完了するには、レビュー担当者、編集者、承認者、または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理の必要なアクセス許可が必要です。 詳細については、このトピックの「その他の考慮事項」を参照してください。

## Gpo、GPO のバージョン、またはテンプレートの違いを特定する


-   [2つの Gpo またはテンプレートの間](#bkmk-two-gpos)

-   [GPO とテンプレートの間](#bkmk-gpo-and-template)

-   [1つの GPO の2つのバージョン間](#bkmk-two-versions)

-   [GPO のバージョンとテンプレートの間](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**2つの Gpo またはテンプレートの違いを確認するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。

3.  2つの Gpo またはテンプレートを選択します。

4.  いずれかの Gpo またはテンプレートを右クリックし、[**相違点**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo またはテンプレートの設定をまとめた差異レポートを表示します。

### <a href="" id="bkmk-gpo-and-template"></a>

**GPO とテンプレートの違いを確認するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。

3.  GPO を右クリックし、[**相違点**] をクリックして、[**テンプレート**] をクリックします。

4.  レポートのテンプレートと種類を選び、[ **OK** ] をクリックして、GPO とテンプレートの設定を要約した差異レポートを表示します。

### <a href="" id="bkmk-two-versions"></a>

**1つの GPO の2つのバージョンの違いを確認するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。

3.  GPO をダブルクリックしてその履歴を表示し、比較するバージョンを強調表示します。

4.  いずれかのバージョンを右クリックし、[**相違点**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo の設定をまとめた差異レポートを表示します。

### <a href="" id="bkmk-gpo-version-and-template"></a>

**GPO のバージョンとテンプレートの違いを確認するには**

1.  [**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。

2.  [詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。

3.  GPO をダブルクリックして、その履歴を表示します。

4.  目的の GPO バージョンを右クリックし、[**相違点**] をクリックして、[**テンプレート**] をクリックします。

5.  レポートのテンプレートと種類を選び、[ **OK** ] をクリックして、GPO のバージョンとテンプレートの設定を要約した差異レポートを表示します。

## 差分レポートの重要な部分


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

-   一部の設定を変更すると、変更された項目としてではなく、項目が2つの異なる項目 (1 つ目の GPO のみに存在する) として報告される場合があります。

### その他の考慮事項

-   既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。 具体的には、GPO の [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可が必要です。 また、Gpo の一覧を表示するには、ドメインの**リストコンテンツ**のアクセス許可が必要です。

### その他の参照情報

-   [レビュー担当者タスクの実行](performing-reviewer-tasks.md)

 

 





