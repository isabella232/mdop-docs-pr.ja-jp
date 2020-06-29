---
title: 承認者タスクの実行
description: 承認者タスクの実行
author: dansimp
ms.assetid: 9f711824-191b-4b4b-a1c6-a3b2116006a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e4a848608a3be1dbb0632f0145b4fc1d1bc631
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820474"
---
# <span data-ttu-id="85734-103">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="85734-103">Performing Approver Tasks</span></span>


<span data-ttu-id="85734-104">承認者は、AGPM 管理者 (フルコントロール) によって承認されたユーザーであり、グループポリシーオブジェクト (Gpo) を作成、展開、削除したり、要求を承認または拒否 (通常は編集者) して、Gpo の作成、展開、削除を行います。</span><span class="sxs-lookup"><span data-stu-id="85734-104">An Approver is a person authorized by an AGPM Administrator (Full Control) to create, deploy, and delete Group Policy Objects (GPOs) and to approve or reject requests (typically from Editors) to create, deploy, or delete GPOs.</span></span>

<span data-ttu-id="85734-105">**重要** Gpo の中央アーカイブに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="85734-105">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="85734-106">詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-reviewer-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85734-106">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-reviewer-agpm30ops.md).</span></span>

 

-   [<span data-ttu-id="85734-107">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="85734-107">Approve or Reject a Pending Action</span></span>](approve-or-reject-a-pending-action-agpm30ops.md)

-   [<span data-ttu-id="85734-108">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="85734-108">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

-   [<span data-ttu-id="85734-109">GPO をチェックインする</span><span class="sxs-lookup"><span data-stu-id="85734-109">Check In a GPO</span></span>](check-in-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="85734-110">GPO を展開する</span><span class="sxs-lookup"><span data-stu-id="85734-110">Deploy a GPO</span></span>](deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="85734-111">GPO の以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="85734-111">Roll Back to a Previous Version of a GPO</span></span>](roll-back-to-a-previous-version-of-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="85734-112">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="85734-112">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

<span data-ttu-id="85734-113">**注** 承認前に、GPO に含まれているポリシー設定を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="85734-113">**Note** Before approving a GPO, an Approver should review the policy settings that it contains.</span></span> <span data-ttu-id="85734-114">承認者ロールには、レビュー担当者ロールの権限が含まれているので、承認者はポリシー設定を確認して Gpo を比較することができます。</span><span class="sxs-lookup"><span data-stu-id="85734-114">The Approver role includes the permissions for the Reviewer role, so that an Approver can review policy settings and compare GPOs.</span></span> <span data-ttu-id="85734-115">詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm30ops.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="85734-115">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md) for more information.</span></span>

 

### <span data-ttu-id="85734-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="85734-116">Additional considerations</span></span>

<span data-ttu-id="85734-117">既定では、承認者の役割に対して次の権限が提供されます。</span><span class="sxs-lookup"><span data-stu-id="85734-117">By default, the following permissions are provided for the Approver role:</span></span>

-   <span data-ttu-id="85734-118">リストの内容</span><span class="sxs-lookup"><span data-stu-id="85734-118">List Contents</span></span>

-   <span data-ttu-id="85734-119">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="85734-119">Read Settings</span></span>

-   <span data-ttu-id="85734-120">GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="85734-120">Create GPO</span></span>

-   <span data-ttu-id="85734-121">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="85734-121">Deploy GPO</span></span>

-   <span data-ttu-id="85734-122">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="85734-122">Delete GPO</span></span>

<span data-ttu-id="85734-123">また、承認者は、作成または管理された Gpo を完全に制御できます。</span><span class="sxs-lookup"><span data-stu-id="85734-123">Also, an Approver has full control over GPOs that he created or controlled.</span></span>

 

 





