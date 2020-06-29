---
title: DaRT 8.0 の展開
description: DaRT 8.0 の展開
author: dansimp
ms.assetid: 5a976d4e-3372-4ef6-9095-1b48e99af21b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7cc847836587abb0eaa22c009c8fd18d0ba0899b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824164"
---
# <span data-ttu-id="b0bd0-103">DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="b0bd0-103">Deploying DaRT 8.0</span></span>


<span data-ttu-id="b0bd0-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 では、さまざまな展開構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 supports a number of different deployment configurations.</span></span> <span data-ttu-id="b0bd0-105">このセクションでは、展開の各ステージで完了する必要があるタスクを正常に実行するために役立つ DaRT 8.0 と段階的な手順の展開について考慮する必要がある情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-105">This section includes information you should consider about the deployment of DaRT 8.0 and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="b0bd0-106">展開情報</span><span class="sxs-lookup"><span data-stu-id="b0bd0-106">Deployment Information</span></span>


-   [<span data-ttu-id="b0bd0-107">管理者用コンピューターへの DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="b0bd0-107">Deploying DaRT 8.0 to Administrator Computers</span></span>](deploying-dart-80-to-administrator-computers-dart-8.md)

    <span data-ttu-id="b0bd0-108">このセクションでは、要件に応じたさまざまな DaRT 導入オプションと、それらの導入方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-108">This section describes the different DaRT deployment options for your requirements and explains how to deploy them.</span></span>

-   [<span data-ttu-id="b0bd0-109">DaRT 8.0 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="b0bd0-109">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

    <span data-ttu-id="b0bd0-110">このセクションでは、dart リカバリ画像を作成するために使用できる方法について説明し、DaRT リカバリ画像ウィザードを使用して回復イメージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-110">This section describes the methods you can use to create the DaRT recovery image and provides instructions to create the recovery image by using the DaRT Recovery Image wizard.</span></span>

-   [<span data-ttu-id="b0bd0-111">DaRT の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="b0bd0-111">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

    <span data-ttu-id="b0bd0-112">このセクションでは、要件に合わせて最高の DaRT 回復イメージ展開オプションを決定する際に役立つ情報を提供し、回復イメージの展開方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-112">This section provides information to help you decide on the best DaRT recovery image deployment option for your requirements and provides instructions on how to deploy the recovery image.</span></span>

-   [<span data-ttu-id="b0bd0-113">DaRT 8.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="b0bd0-113">DaRT 8.0 Deployment Checklist</span></span>](dart-80-deployment-checklist-dart-8.md)

    <span data-ttu-id="b0bd0-114">このセクションには、DaRT の展開に役立つ展開チェックリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-114">This section contains a deployment checklist that can help you to deploy DaRT.</span></span>

### <span data-ttu-id="b0bd0-115">DaRT の入手方法</span><span class="sxs-lookup"><span data-stu-id="b0bd0-115">How to get DaRT</span></span>

<span data-ttu-id="b0bd0-116">この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-116">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="b0bd0-117">企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-117">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="b0bd0-118">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/p/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="b0bd0-118">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/p/?LinkId=322049) (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

## <span data-ttu-id="b0bd0-119">DaRT の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="b0bd0-119">Other Resources for deploying DaRT</span></span>


[<span data-ttu-id="b0bd0-120">診断/回復ツールセット8管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="b0bd0-120">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="b0bd0-121">DaRT 8.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="b0bd0-121">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="b0bd0-122">DaRT 8.0 の計画</span><span class="sxs-lookup"><span data-stu-id="b0bd0-122">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

[<span data-ttu-id="b0bd0-123">DaRT 8.0 の操作</span><span class="sxs-lookup"><span data-stu-id="b0bd0-123">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="b0bd0-124">DaRT 8.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b0bd0-124">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)

 

 





