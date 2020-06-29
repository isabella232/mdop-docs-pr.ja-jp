---
title: 承認者タスクの実行
description: 承認者タスクの実行
author: dansimp
ms.assetid: e0a4b7fe-ce69-4755-9104-c7f523ea6b62
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a0815bdd6c34a7a23b27075b3b5367757c1f84e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820467"
---
# <span data-ttu-id="ba66d-103">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ba66d-103">Performing Approver Tasks</span></span>


<span data-ttu-id="ba66d-104">承認者は、AGPM 管理者 (フルコントロール) によって承認されたユーザーであり、グループポリシーオブジェクト (Gpo) を作成、展開、削除したり、要求を承認または拒否 (通常は編集者) して、Gpo の作成、展開、削除を行います。</span><span class="sxs-lookup"><span data-stu-id="ba66d-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy Objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="ba66d-105">**重要** Gpo の中央アーカイブに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba66d-105">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="ba66d-106">詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba66d-106">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

 

-   [<span data-ttu-id="ba66d-107">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="ba66d-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action-agpm40.md)

-   [<span data-ttu-id="ba66d-108">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="ba66d-108">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

-   [<span data-ttu-id="ba66d-109">GPO をチェックインする</span><span class="sxs-lookup"><span data-stu-id="ba66d-109">Check In a GPO</span></span>](check-in-a-gpo-agpm40.md)

-   [<span data-ttu-id="ba66d-110">GPO を展開する</span><span class="sxs-lookup"><span data-stu-id="ba66d-110">Deploy a GPO</span></span>](deploy-a-gpo-agpm40.md)

-   [<span data-ttu-id="ba66d-111">GPO の以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="ba66d-111">Roll Back to an Earlier Version of a GPO</span></span>](roll-back-to-an-earlier-version-of-a-gpo-agpm40.md)

-   [<span data-ttu-id="ba66d-112">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="ba66d-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm40.md)

<span data-ttu-id="ba66d-113">**注** 承認前に、GPO に含まれているポリシー設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba66d-113">**Note** Before approving a GPO, an Approver should review the policy settings that it contains.</span></span> <span data-ttu-id="ba66d-114">承認者ロールには、レビュー担当者ロールの権限が含まれているので、承認者はポリシー設定を確認して Gpo を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="ba66d-114">The Approver role includes the permissions for the Reviewer role, so that an Approver can review policy settings and compare GPOs.</span></span> <span data-ttu-id="ba66d-115">詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba66d-115">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md) for more information.</span></span>

 

### <span data-ttu-id="ba66d-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ba66d-116">Additional considerations</span></span>

<span data-ttu-id="ba66d-117">既定では、承認者の役割に対して次の権限が提供されます。</span><span class="sxs-lookup"><span data-stu-id="ba66d-117">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="ba66d-118">リストの内容</span><span class="sxs-lookup"><span data-stu-id="ba66d-118">List Contents</span></span>

-   <span data-ttu-id="ba66d-119">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="ba66d-119">Read Settings</span></span>

-   <span data-ttu-id="ba66d-120">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ba66d-120">Create GPO</span></span>

-   <span data-ttu-id="ba66d-121">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="ba66d-121">Deploy GPO</span></span>

-   <span data-ttu-id="ba66d-122">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="ba66d-122">Delete GPO</span></span>

<span data-ttu-id="ba66d-123">また、承認者は、作成または管理された Gpo を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="ba66d-123">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





