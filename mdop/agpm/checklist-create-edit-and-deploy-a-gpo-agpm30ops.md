---
title: チェックリスト GPO の作成、編集、展開
description: チェックリスト GPO の作成、編集、展開
author: dansimp
ms.assetid: a7a17706-304a-4455-9ada-52508ec620f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35255926ba2384e2942900fc30eae06a30049a15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819107"
---
# チェックリスト: GPO の作成、編集、展開


高度なグループポリシー管理 (AGPM) を使って、複数のユーザーがグループポリシーオブジェクト (Gpo) に変更を加えた環境では、AGPM 管理者 (フルコントロール) により、編集者 (グループまたは個人として) の権限が与えられます。 次に、エディターと承認者向けの一般的な GPO 開発プロセスを示します。

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
<td align="left"><p>エディターは新しい GPO または承認者の作成を要求します。新しい gpo を作成します。</p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)">新しい制御された GPO の作成を要求する</a></p>
<p><a href="create-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm30ops.md)">新しい制御された GPO を作成する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>承認者は、エディターによって要求された場合に、GPO の作成を承認します。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)">保留中のアクションを承認または拒否する</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>エディターは、アーカイブから GPO のコピーをチェックアウトします。そのため、他のユーザーはその GPO を変更することはできません。 エディターによって GPO が変更され、変更された GPO がアーカイブにチェックされます。</p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm30ops.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm30ops.md)">オフラインで GPO を編集する</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>編集者が、GPO を運用環境に展開することを要求します。</p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm30ops.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm30ops.md)">GPO の展開を要求する</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>承認者や編集者などのレビュー担当者が GPO を分析します。</p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm30ops.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md)">レビュー担当者タスクの実行</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>承認者が GPO を承認して運用環境に展開するか、GPO を拒否します。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)">保留中のアクションを承認または拒否する</a></p></td>
</tr>
</tbody>
</table>

 

### その他の参照情報

[Microsoft Advanced Group Policy Management 3.0 運用ガイド](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





