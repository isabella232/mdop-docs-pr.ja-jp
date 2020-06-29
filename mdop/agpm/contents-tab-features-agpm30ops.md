---
title: '[内容] タブの機能'
description: '[内容] タブの機能'
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818907"
---
# [内容] タブの機能


[**コンテンツ**] タブ内の各 [セカンダリ] タブには、**グループポリシーオブジェクト**と**グループとユーザー**の2つのセクションがあります。

## グループポリシーオブジェクトセクション


[**グループポリシーオブジェクト**] セクションには、グループポリシーオブジェクト (gpo) の一覧が表示され、各 gpo の次の属性が示されます。

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
<td align="left"><p><strong>Name (名前)</strong></p></td>
<td align="left"><p>GPO の名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>状態</strong></p></td>
<td align="left"><p>選択された GPO の状態</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>変更者</strong></p></td>
<td align="left"><p>選択された GPO を展開した、チェックインまたは承認者がいるエディター。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>日付を変更する</strong></p></td>
<td align="left"><p>制御されている GPO の場合、変更されたか、チェックアウトされた後にチェックインされた最新の日付。 制御されていない GPO の場合、最終変更日。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>コメント</strong></p></td>
<td align="left"><p>GPO を変更したときにチェックインまたは展開したユーザーが入力したコメント。 以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</p></td>
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
<td align="left"><p>コンピューターの構成とユーザーの構成は、個別に管理することができます。 Gpo の状態は、有効になっている GPO の部分を示します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>WMI フィルター</strong></p></td>
<td align="left"><p>この GPO に適用されているすべての WMI フィルターを表示します。 WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] フォルダーで管理されます。</p></td>
</tr>
</tbody>
</table>

 

## [グループとユーザー] セクション


GPO が選択されている場合、[**グループとユーザー** ] セクションには、その gpo へのアクセス権を持つグループとユーザーの一覧が表示されます。 グループまたはユーザーごとに、許可されているアクセス許可と継承が表示されます。 AGPM 管理者は、標準の AGPM ロール (エディター、承認者、レビューアー、AGPM 管理者) またはカスタマイズされたアクセス許可の組み合わせを使って、アクセス許可を構成できます。

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
<td align="left"><p><strong>Add</strong></p></td>
<td align="left"><p>セキュリティ記述子に新しいエントリを追加します。 Active Directory の任意のユーザーまたはグループを追加できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[削除]</strong></p></td>
<td align="left"><p>選択したエントリをアクセス制御リストから削除します。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>プロパティ</strong></p></td>
<td align="left"><p>選択したオブジェクトのプロパティを表示します。 [プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>詳細設定</strong></p></td>
<td align="left"><p><strong>Access コントロールリストエディターを開き </strong> ます。</p></td>
</tr>
</tbody>
</table>

 

### その他の考慮事項

-   特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks-agpm30ops.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks-agpm30ops.md)する」、「[承認者タスク](performing-approver-tasks-agpm30ops.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks-agpm30ops.md)を実行する」のタスクを参照してください。

### その他の参照情報

-   [[内容] タブ](contents-tab-agpm30ops.md)

 

 





