---
title: ごみ箱のコマンド
description: ごみ箱のコマンド
author: dansimp
ms.assetid: 347a101f-0ba0-4afc-bd59-752cc06bb904
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b05a5c25a59be751a062086f77daa009d7cb32f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818544"
---
# ごみ箱のコマンド


[**ごみ箱**] タブ:

-   アーカイブから削除されたグループポリシーオブジェクト (Gpo) の一覧が表示されます。

-   Gpo を管理するためのコマンドと、Gpo のレポートを表示するためのショートカットメニューが用意されています。

-   選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。

このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。

## レポート


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>設定</strong></p></td>
<td align="left"><p>選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、Gpo が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ Gpo へのリンクを表示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>相違点</strong></p></td>
<td align="left"><p>選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</p></td>
</tr>
</tbody>
</table>

 

## バージョン管理


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Destroy</strong></p></td>
<td align="left"><p>選択した GPO をごみ箱から削除し <strong> </strong> て、復元できないようにします。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>復元</strong></p></td>
<td align="left"><p>選択した GPO を <strong> ごみ箱から [ </strong> <strong> コントロール] タブに移動し </strong> ます。この方法では、GPO は運用環境に復元されません。</p></td>
</tr>
</tbody>
</table>

 

## その他


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コマンド</th>
<th align="left">効果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Refresh</strong></p></td>
<td align="left"><p>グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。 表示が更新されるまで、一部の変更は表示されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ヘルプ</strong></p></td>
<td align="left"><p>高度なグループポリシー管理 (AGPM) のヘルプを表示します。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[内容] タブ](contents-tab-agpm40.md)

-   [承認者タスクの実行](performing-approver-tasks-agpm40.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks-agpm40.md)

 

 





