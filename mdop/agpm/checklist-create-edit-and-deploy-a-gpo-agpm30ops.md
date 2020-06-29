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
# <span data-ttu-id="c504c-103">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="c504c-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="c504c-104">高度なグループポリシー管理 (AGPM) を使って、複数のユーザーがグループポリシーオブジェクト (Gpo) に変更を加えた環境では、AGPM 管理者 (フルコントロール) により、編集者 (グループまたは個人として) の権限が与えられます。</span><span class="sxs-lookup"><span data-stu-id="c504c-104">In an environment where multiple people make changes to Group Policy Objects (GPOs) using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="c504c-105">次に、エディターと承認者向けの一般的な GPO 開発プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="c504c-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c504c-106">タスク</span><span class="sxs-lookup"><span data-stu-id="c504c-106">Task</span></span></th>
<th align="left"><span data-ttu-id="c504c-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="c504c-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c504c-108">エディターは新しい GPO または承認者の作成を要求します。新しい gpo を作成します。</span><span class="sxs-lookup"><span data-stu-id="c504c-108">Editor requests the creation of a new GPO or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="c504c-109">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="c504c-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="c504c-110">新しい制御された GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="c504c-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c504c-111">承認者は、エディターによって要求された場合に、GPO の作成を承認します。</span><span class="sxs-lookup"><span data-stu-id="c504c-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="c504c-112">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="c504c-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c504c-113">エディターは、アーカイブから GPO のコピーをチェックアウトします。そのため、他のユーザーはその GPO を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="c504c-113">Editor checks out a copy of the GPO from the archive, so no one else can modify the GPO.</span></span> <span data-ttu-id="c504c-114">エディターによって GPO が変更され、変更された GPO がアーカイブにチェックされます。</span><span class="sxs-lookup"><span data-stu-id="c504c-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm30ops.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm30ops.md)"><span data-ttu-id="c504c-115">オフラインで GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="c504c-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c504c-116">編集者が、GPO を運用環境に展開することを要求します。</span><span class="sxs-lookup"><span data-stu-id="c504c-116">Editor requests deployment of the GPO to the production environment.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm30ops.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm30ops.md)"><span data-ttu-id="c504c-117">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="c504c-117">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c504c-118">承認者や編集者などのレビュー担当者が GPO を分析します。</span><span class="sxs-lookup"><span data-stu-id="c504c-118">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm30ops.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md)"><span data-ttu-id="c504c-119">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="c504c-119">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c504c-120">承認者が GPO を承認して運用環境に展開するか、GPO を拒否します。</span><span class="sxs-lookup"><span data-stu-id="c504c-120">Approver approves and deploys the GPO to the production environment or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="c504c-121">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="c504c-121">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c504c-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="c504c-122">Additional references</span></span>

[<span data-ttu-id="c504c-123">Microsoft Advanced Group Policy Management 3.0 運用ガイド</span><span class="sxs-lookup"><span data-stu-id="c504c-123">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





