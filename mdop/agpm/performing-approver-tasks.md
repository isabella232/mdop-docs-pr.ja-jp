---
title: 承認者タスクの実行
description: 承認者タスクの実行
author: dansimp
ms.assetid: 6f6310b3-19c1-47c9-8615-964ddd10ce14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fc77a1dd9a3d54e637ae4baeb452d327672ed250
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820427"
---
# <span data-ttu-id="b3782-103">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="b3782-103">Performing Approver Tasks</span></span>


<span data-ttu-id="b3782-104">承認者は、AGPM 管理者 (フルコントロール) によって承認されたユーザーであり、グループポリシーオブジェクト (Gpo) を作成、展開、削除したり、要求を承認または拒否 (通常は編集者) して、Gpo の作成、展開、削除を行います。</span><span class="sxs-lookup"><span data-stu-id="b3782-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="b3782-105">**重要** Gpo の中央アーカイブに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b3782-105">**Important** Ensure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="b3782-106">詳細については、「 [AGPM サーバー接続を構成する](configure-the-agpm-server-connection-reviewer.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3782-106">For more information, see [Configure the AGPM Server Connection](configure-the-agpm-server-connection-reviewer.md).</span></span>

 

-   [<span data-ttu-id="b3782-107">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="b3782-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action.md)

-   [<span data-ttu-id="b3782-108">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="b3782-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

-   [<span data-ttu-id="b3782-109">GPO をチェックインする</span><span class="sxs-lookup"><span data-stu-id="b3782-109">Check In a GPO</span></span>](check-in-a-gpo-approver.md)

-   [<span data-ttu-id="b3782-110">GPO を展開する</span><span class="sxs-lookup"><span data-stu-id="b3782-110">Deploy a GPO</span></span>](deploy-a-gpo.md)

-   [<span data-ttu-id="b3782-111">GPO の以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="b3782-111">Roll Back to a Previous Version of a GPO</span></span>](roll-back-to-a-previous-version-of-a-gpo.md)

-   [<span data-ttu-id="b3782-112">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="b3782-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

<span data-ttu-id="b3782-113">**注** 承認者ロールにはレビュー担当者ロールの権限が含まれているため、承認者は設定を確認して Gpo を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="b3782-113">**Note** Because the Approver role includes the permissions for the Reviewer role, an Approver can also review settings and compare GPOs.</span></span> <span data-ttu-id="b3782-114">詳細については、「[校閲者タスクを実行](performing-reviewer-tasks.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b3782-114">See [Performing Reviewer Tasks](performing-reviewer-tasks.md) for more information.</span></span>

 

### <span data-ttu-id="b3782-115">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b3782-115">Additional considerations</span></span>

<span data-ttu-id="b3782-116">既定では、承認者の役割に対して次の権限が提供されます。</span><span class="sxs-lookup"><span data-stu-id="b3782-116">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="b3782-117">リストの内容</span><span class="sxs-lookup"><span data-stu-id="b3782-117">List Contents</span></span>

-   <span data-ttu-id="b3782-118">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="b3782-118">Read Settings</span></span>

-   <span data-ttu-id="b3782-119">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="b3782-119">Create GPO</span></span>

-   <span data-ttu-id="b3782-120">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="b3782-120">Deploy GPO</span></span>

-   <span data-ttu-id="b3782-121">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="b3782-121">Delete GPO</span></span>

<span data-ttu-id="b3782-122">また、承認者は、作成または管理された Gpo を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="b3782-122">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





