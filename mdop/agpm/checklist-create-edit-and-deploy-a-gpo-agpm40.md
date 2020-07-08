---
title: チェックリスト GPO の作成、編集、展開
description: チェックリスト GPO の作成、編集、展開
author: dansimp
ms.assetid: 44631bed-16d2-4b5a-af70-17a73fb5f6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d8bea9109040aa81a20df62356ef1d307d5eac0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819104"
---
# チェックリスト: GPO の作成、編集、展開


高度なグループポリシー管理 (AGPM) を使用して、複数のユーザーがグループポリシーオブジェクト (Gpo) を変更する環境では、AGPM 管理者 (フルコントロール) は、編集者、承認者、および校閲者に対して、グループまたは個人としてアクセス許可を委任します。 次に、エディターと承認者向けの一般的な GPO 開発プロセスを示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">タスク</th>
<th align="left">リファレンス</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>エディターによって、新しい GPO を作成するか、承認者が新しい GPO を作成するよう要求されます。</p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm40.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)">新しい制御された GPO の作成を要求する</a></p>
<p><a href="create-a-new-controlled-gpo-agpm40.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md)">新しい制御された GPO を作成する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>承認者は、エディターによって要求された場合に、GPO の作成を承認します。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)">保留中のアクションを承認または拒否する</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>エディターは、他のユーザーが GPO を変更できないように、アーカイブから GPO のコピーをチェックアウトします。 エディターによって GPO が変更され、変更された GPO がアーカイブにチェックされます。</p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm40.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm40.md)">オフラインで GPO を編集する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>テストフォレストで開発する場合、エディターは GPO をファイルにエクスポートし、そのファイルを運用フォレストに転送して、ファイルをインポートします。 さらに、エディターは、テストコンピューターとユーザーを含む組織単位に GPO をリンクできます。</p></td>
<td align="left"><p><a href="using-a-test-environment.md" data-raw-source="[Using a Test Environment](using-a-test-environment.md)">テスト環境の使用</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>エディターは、ドメインの運用環境への GPO の展開を要求します。</p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm40.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md)">GPO の展開を要求する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>承認者や編集者などのレビュー担当者が GPO を分析します。</p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm40.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md)">レビュー担当者タスクの実行</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>承認者が GPO を承認して、ドメインの運用環境に展開するか、GPO を拒否します。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)">保留中のアクションを承認または拒否する</a></p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

[Advanced Group Policy Management 4.0](advanced-group-policy-management-40.md)

 

 





