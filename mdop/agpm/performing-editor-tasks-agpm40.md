---
title: 編集者タスクの実行
description: 編集者タスクの実行
author: dansimp
ms.assetid: 81976a01-2a95-4256-b703-9fb3c884ef34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8e23bb91d8762d19eed9ae817967ba5a57505a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820407"
---
# <span data-ttu-id="408d6-103">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="408d6-103">Performing Editor Tasks</span></span>


<span data-ttu-id="408d6-104">[高度なグループポリシー管理 (AGPM)] のエディターは、AGPM 管理者 (フルコントロール) によって承認されたユーザーで、グループポリシーオブジェクト (Gpo) を変更したり、GPO テンプレートを作成したりします。</span><span class="sxs-lookup"><span data-stu-id="408d6-104">In Advanced Group Policy Management (AGPM), an Editor is a person authorized by an AGPM Administrator (Full Control) to change Group Policy Objects (GPOs) and create GPO templates.</span></span> <span data-ttu-id="408d6-105">さらに、編集者は、GPO の作成、削除、復元を要求することができます。</span><span class="sxs-lookup"><span data-stu-id="408d6-105">Additionally, an Editor can request that a GPO be created, deleted, or restored.</span></span> <span data-ttu-id="408d6-106">承認者は、実装の要求を承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="408d6-106">An Approver must approve the request for it to be implemented.</span></span> <span data-ttu-id="408d6-107">エディターでは、GPO をファイルにエクスポートして、別のフォレストのドメインにコピーできるようにしたり、別のドメインからコピーした GPO をインポートしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="408d6-107">An Editor can export a GPO to a file so that it can be copied to a domain in another forest, and import a GPO that was copied from another domain.</span></span>

<span data-ttu-id="408d6-108">**重要** Gpo の中央アーカイブに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="408d6-108">**Important** Make sure that you are connecting to the central archive for GPOs.</span></span> <span data-ttu-id="408d6-109">詳細については、「 [AGPM サーバー接続を構成](configure-an-agpm-server-connection-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="408d6-109">For more information, see [Configure an AGPM Server Connection](configure-an-agpm-server-connection-agpm40.md).</span></span>

 

-   [<span data-ttu-id="408d6-110">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="408d6-110">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-ed.md)

-   [<span data-ttu-id="408d6-111">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="408d6-111">Editing a GPO</span></span>](editing-a-gpo-agpm40.md)

-   [<span data-ttu-id="408d6-112">テスト環境の使用</span><span class="sxs-lookup"><span data-stu-id="408d6-112">Using a Test Environment</span></span>](using-a-test-environment.md)

-   [<span data-ttu-id="408d6-113">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="408d6-113">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm40.md)

-   [<span data-ttu-id="408d6-114">テンプレートの作成と既定のテンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="408d6-114">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [<span data-ttu-id="408d6-115">GPO の削除または復元</span><span class="sxs-lookup"><span data-stu-id="408d6-115">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

<span data-ttu-id="408d6-116">**注** 編集者ロールにはレビュー担当者ロールの権限が含まれているため、編集者は設定を確認して Gpo を比較することもできます。</span><span class="sxs-lookup"><span data-stu-id="408d6-116">**Note** Because the Editor role includes the permissions for the Reviewer role, an Editor can also review settings and compare GPOs.</span></span> <span data-ttu-id="408d6-117">詳細については、「[校閲者タスクを実行](performing-reviewer-tasks-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="408d6-117">See [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md) for more information.</span></span>

 

### <span data-ttu-id="408d6-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="408d6-118">Additional considerations</span></span>

<span data-ttu-id="408d6-119">既定では、編集者の役割に対して次の権限が提供されます。</span><span class="sxs-lookup"><span data-stu-id="408d6-119">By default, the following permissions are provided for the Editor role:</span></span>

-   <span data-ttu-id="408d6-120">リストの内容</span><span class="sxs-lookup"><span data-stu-id="408d6-120">List Contents</span></span>

-   <span data-ttu-id="408d6-121">設定の読み取り</span><span class="sxs-lookup"><span data-stu-id="408d6-121">Read Settings</span></span>

-   <span data-ttu-id="408d6-122">設定を編集する</span><span class="sxs-lookup"><span data-stu-id="408d6-122">Edit Settings</span></span>

-   <span data-ttu-id="408d6-123">GPO をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="408d6-123">Export GPO</span></span>

-   <span data-ttu-id="408d6-124">GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="408d6-124">Import GPO</span></span>

-   <span data-ttu-id="408d6-125">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="408d6-125">Create Template</span></span>

 

 





