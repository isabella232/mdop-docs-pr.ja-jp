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
# <span data-ttu-id="6bdc5-103">チェックリスト: GPO の作成、編集、展開</span><span class="sxs-lookup"><span data-stu-id="6bdc5-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="6bdc5-104">高度なグループポリシー管理 (AGPM) を使用して、複数のユーザーがグループポリシーオブジェクト (Gpo) を変更する環境では、AGPM 管理者 (フルコントロール) は、編集者、承認者、および校閲者に対して、グループまたは個人としてアクセス許可を委任します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-104">In an environment where multiple people change Group Policy Objects (GPOs) by using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers either as groups or as individuals.</span></span> <span data-ttu-id="6bdc5-105">次に、エディターと承認者向けの一般的な GPO 開発プロセスを示します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6bdc5-106">タスク</span><span class="sxs-lookup"><span data-stu-id="6bdc5-106">Task</span></span></th>
<th align="left"><span data-ttu-id="6bdc5-107">リファレンス</span><span class="sxs-lookup"><span data-stu-id="6bdc5-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6bdc5-108">エディターによって、新しい GPO を作成するか、承認者が新しい GPO を作成するよう要求されます。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-108">Editor requests that a new GPO be created or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm40.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="6bdc5-109">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm40.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="6bdc5-110">新しい制御された GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6bdc5-111">承認者は、エディターによって要求された場合に、GPO の作成を承認します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="6bdc5-112">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6bdc5-113">エディターは、他のユーザーが GPO を変更できないように、アーカイブから GPO のコピーをチェックアウトします。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-113">Editor checks out a copy of the GPO from the archive so that no one else can modify the GPO.</span></span> <span data-ttu-id="6bdc5-114">エディターによって GPO が変更され、変更された GPO がアーカイブにチェックされます。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm40.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm40.md)"><span data-ttu-id="6bdc5-115">オフラインで GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6bdc5-116">テストフォレストで開発する場合、エディターは GPO をファイルにエクスポートし、そのファイルを運用フォレストに転送して、ファイルをインポートします。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-116">If developing in a test forest, Editor exports the GPO to a file, transfers the file to the production forest, and imports the file.</span></span> <span data-ttu-id="6bdc5-117">さらに、エディターは、テストコンピューターとユーザーを含む組織単位に GPO をリンクできます。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-117">Additionally, an Editor can link the GPO to an organizational unit that contains test computers and users.</span></span></p></td>
<td align="left"><p><a href="using-a-test-environment.md" data-raw-source="[Using a Test Environment](using-a-test-environment.md)"><span data-ttu-id="6bdc5-118">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="6bdc5-118">Using a Test Environment</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6bdc5-119">エディターは、ドメインの運用環境への GPO の展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-119">Editor requests deployment of the GPO to the production environment of the domain.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm40.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md)"><span data-ttu-id="6bdc5-120">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-120">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6bdc5-121">承認者や編集者などのレビュー担当者が GPO を分析します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-121">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm40.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md)"><span data-ttu-id="6bdc5-122">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="6bdc5-122">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6bdc5-123">承認者が GPO を承認して、ドメインの運用環境に展開するか、GPO を拒否します。</span><span class="sxs-lookup"><span data-stu-id="6bdc5-123">Approver approves and deploys the GPO to the production environment of the domain or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="6bdc5-124">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="6bdc5-124">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6bdc5-125">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="6bdc5-125">Additional references</span></span>

[<span data-ttu-id="6bdc5-126">Advanced Group Policy Management 4.0</span><span class="sxs-lookup"><span data-stu-id="6bdc5-126">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





