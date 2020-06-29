---
title: '[テンプレート] タブ'
description: '[テンプレート] タブ'
author: dansimp
ms.assetid: 5676e9f9-eb52-49e1-a55d-15c1059af368
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7469ee72eb23903ddec66152f8cc5d59861dfc9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820174"
---
# [テンプレート] タブ


[**テンプレート**] タブ:

-   新しいグループポリシーオブジェクト (Gpo) の作成に使用できる使用可能なテンプレートの一覧が表示されます。

-   選択したテンプレートに基づいて GPO を作成したり、テンプレートを管理したり、テンプレートのレポートを表示したりするためのコマンドが含まれたショートカットメニューが用意されています。

-   選択したテンプレートへのアクセス許可があるグループとユーザーの一覧が表示されます。

テンプレートは変更できないため、テンプレートには履歴はありません。 ただし、任意の GPO バージョンと同様に、テンプレートの設定は、設定レポートとして表示したり、別の GPO と比較レポートを比較して表示したりすることができます。

**注** テンプレートは、新しい編集可能な Gpo を作成するための出発点として使用する、編集できない静的バージョンの GPO です。

 

このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。

## コントロール


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
<td align="left"><p><strong>新しい制御された GPO</strong></p></td>
<td align="left"><p>選択したテンプレートに基づいて新しい GPO を作成します。 新しい GPO を運用環境に展開するためのオプションが用意されています。 GPO を作成するアクセス許可が与えられていない場合は、要求を送信するように求められます。 (このオプションは、の右クリックで GPO が選択されていない場合に表示されます <strong> 。グループポリシーオブジェクト </strong> リスト)</p></td>
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
<td align="left"><p>選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>相違点</strong></p></td>
<td align="left"><p>選択した2つの GPO テンプレート内の設定を比較する、HTML ベースまたは XML ベースのレポートを生成します。</p></td>
</tr>
</tbody>
</table>

 

## テンプレートの管理


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
<td align="left"><p><strong>既定に設定</strong></p></td>
<td align="left"><p>新しい GPO の作成時に自動的に使用されるように、選択したテンプレートを既定として設定します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Delete</strong></p></td>
<td align="left"><p>選択したテンプレートをごみ箱に移動し <strong> </strong> ます。 GPO を削除するアクセス許可が与えられていない場合は、要求を送信するように求められます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Rename</strong></p></td>
<td align="left"><p>選択したテンプレートの名前を変更します。</p></td>
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
<td align="left"><p>グループポリシー管理コンソールの表示を更新して、変更を反映します。 表示が更新されるまで、一部の変更は表示されません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>ヘルプ</strong></p></td>
<td align="left"><p>高度なグループポリシー管理 (AGPM) のヘルプを表示します。</p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

-   [[内容] タブ](contents-tab.md)

-   [編集者タスクの実行](performing-editor-tasks.md)

-   [レビュー担当者タスクの実行](performing-reviewer-tasks.md)

 

 





