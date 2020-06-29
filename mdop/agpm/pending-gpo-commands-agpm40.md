---
title: 保留中の GPO のコマンド
description: 保留中の GPO のコマンド
author: dansimp
ms.assetid: b62f49e1-43ab-4c93-8102-96cd97a4adad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa5afed2335d75132c0fd99c69e0b5e09985d98f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822464"
---
# 保留中の GPO のコマンド


[**保留中**] タブ:

-   グループポリシーオブジェクト (Gpo) の一覧が表示され、GPO 管理アクション (作成、コントロール、展開、削除など) の保留中の要求が含まれます。

-   保留中の要求に応答したり、Gpo の履歴とレポートを表示したりするためのコマンドを含むショートカットメニューを提供します。

-   選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。

このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。

## コントロールと履歴


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
<td align="left"><p><strong>履歴</strong></p></td>
<td align="left"><p>アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。 履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>撤退</strong></p></td>
<td align="left"><p>要求が承認される前に、選択した GPO を作成、制御、または削除するために、保留中の要求を取り消す。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>承認</strong></p></td>
<td align="left"><p>選択した GPO を作成、制御、または削除するために、編集者からの保留中の要求を完了します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>拒否</strong></p></td>
<td align="left"><p>選択された GPO を作成、制御、または削除するには、編集者からの保留中の要求を拒否します。</p></td>
</tr>
</tbody>
</table>

 

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
<td align="left"><p>AGPM のヘルプを表示します。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[内容] タブ](contents-tab-agpm40.md)

-   [承認者タスクの実行](performing-approver-tasks-agpm40.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks-agpm40.md)

 

 





