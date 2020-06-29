---
title: チェックリスト GPO の作成、編集、展開
description: チェックリスト GPO の作成、編集、展開
author: dansimp
ms.assetid: 614e2d9a-c18b-4f62-99fd-e17a2ac8559d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c79fefaa65c138372ebee00b769ccc5243142e22
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819114"
---
# <span data-ttu-id="a445f-103">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="a445f-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="a445f-104">複数のユーザーがグループポリシーオブジェクト (Gpo) に変更を加えている環境では、AGPM 管理者 (フルコントロール) は、グループまたは個人として、編集者、承認者、および校閲者へのアクセス許可を委任します。</span><span class="sxs-lookup"><span data-stu-id="a445f-104">In an environment where multiple people make changes to Group Policy objects (GPOs), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="a445f-105">次に、エディターと承認者向けの一般的な GPO 開発プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="a445f-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a445f-106">タスク</span><span class="sxs-lookup"><span data-stu-id="a445f-106">Task</span></span></th>
<th align="left"><span data-ttu-id="a445f-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="a445f-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a445f-108">エディターは新しい GPO または承認者の作成を要求します。新しい gpo を作成します。</span><span class="sxs-lookup"><span data-stu-id="a445f-108">Editor requests the creation of a new GPO or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo.md)"><span data-ttu-id="a445f-109">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="a445f-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo.md)"><span data-ttu-id="a445f-110">新しい制御された GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="a445f-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a445f-111">承認者は、エディターによって要求された場合に、GPO の作成を承認します。</span><span class="sxs-lookup"><span data-stu-id="a445f-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action.md)"><span data-ttu-id="a445f-112">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="a445f-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a445f-113">エディターは、アーカイブから GPO のコピーをチェックアウトします。そのため、他のユーザーはその GPO を変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="a445f-113">Editor checks out a copy of the GPO from the archive, so no one else can modify the GPO.</span></span> <span data-ttu-id="a445f-114">エディターによって GPO が変更され、変更された GPO がアーカイブにチェックされます。</span><span class="sxs-lookup"><span data-stu-id="a445f-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline.md)"><span data-ttu-id="a445f-115">オフラインで GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="a445f-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a445f-116">編集者が、GPO を運用環境に展開することを要求します。</span><span class="sxs-lookup"><span data-stu-id="a445f-116">Editor requests deployment of the GPO to the production environment.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo.md)"><span data-ttu-id="a445f-117">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="a445f-117">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a445f-118">承認者や編集者などのレビュー担当者が GPO を分析します。</span><span class="sxs-lookup"><span data-stu-id="a445f-118">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks.md)"><span data-ttu-id="a445f-119">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="a445f-119">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a445f-120">承認者が GPO を承認して運用環境に展開するか、GPO を拒否します。</span><span class="sxs-lookup"><span data-stu-id="a445f-120">Approver approves and deploys the GPO to the production environment or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action.md)"><span data-ttu-id="a445f-121">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="a445f-121">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





