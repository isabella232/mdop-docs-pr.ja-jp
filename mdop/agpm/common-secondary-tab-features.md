---
title: 一般的なセカンダリ タブの機能
description: 一般的なセカンダリ タブの機能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819087"
---
# 一般的なセカンダリ タブの機能


各 [セカンダリ] タブには、**グループポリシーオブジェクト**と**グループとユーザー**の2つのセクションがあります。

## グループポリシーオブジェクトセクション


[**グループポリシーオブジェクト**] セクションには、グループポリシーオブジェクト (gpo) の一覧が表示され、各 GPO の次の特性が示されます。

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
<td align="left"><p><strong>Name (名前)</strong></p></td>
<td align="left"><p>グループポリシーオブジェクトの名前。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>コンピュータ (カンプ)</strong></p></td>
<td align="left"><p>GPO のコンピューター構成部分の自動生成されたバージョン。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>ユーザー</strong></p></td>
<td align="left"><p>自動的に生成される、GPO のユーザー構成部分のバージョン。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>状態</strong></p></td>
<td align="left"><p>選択された GPO の状態:</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong>非制御: </strong> AGPM で管理されません。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>チェックイン: </strong> 承認された編集者またはグループポリシー管理者が展開するために、承認された編集者に対して使用できます。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>チェックアウト済み: </strong> 現在編集中です。 他のエディターは、チェックアウトしたエディターまたは AGPM 管理者がチェックインするまで、他のエディターでは使用できません。</p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong>[保留中 </strong> ]: グループポリシー管理者による承認待ちのため、作成、管理、展開、または削除されます。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>[削除済み </strong> ]: アーカイブから削除されますが、復元することはできます。</p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong>テンプレート: </strong> 新しい gpo の作成時の出発点として使用する gpo の静的なバージョン。</p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong>テンプレート (既定): </strong> 既定では、新しい GPO の作成時に使用される開始点はこのテンプレートです。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO の状態</strong></p></td>
<td align="left"><p>コンピューターの構成とユーザーの構成は、個別に管理することができます。 Gpo の状態は、有効になっている GPO の部分を示します。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>WMI フィルター</strong></p></td>
<td align="left"><p>この GPO に適用されているすべての WMI フィルターを表示します。 WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] ノードで管理されます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>変更</strong></p></td>
<td align="left"><p>コントロールされた GPO の場合、変更されたか、チェックアウトされた後にチェックインされた最新の日付。 制御されていない GPO の場合、最終変更日。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>所有者</strong></p></td>
<td align="left"><p>選択された GPO を展開した、チェックインまたは承認者がいるエディター。</p></td>
</tr>
</tbody>
</table>

 

## [グループとユーザー] セクション


GPO が選択されている場合、[**グループとユーザー** ] セクションには、その gpo へのアクセス権を持つグループとユーザーの一覧が表示されます。 グループまたはユーザーごとに、許可されているアクセス許可と継承が表示されます。 AGPM 管理者は、標準の AGPM ロール (エディター、承認者、および校閲者) またはカスタマイズされたアクセス許可の組み合わせを使って、アクセス許可を構成できます。

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

-   特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks.md)する」、「[承認者タスク](performing-approver-tasks.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks.md)を実行する」のタスクを参照してください。

### その他の参照情報

-   [[内容] タブ](contents-tab.md)

 

 





