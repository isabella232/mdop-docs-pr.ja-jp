---
title: MBAM 1.0 をお使いになる前に
description: MBAM 1.0 をお使いになる前に
author: dansimp
ms.assetid: 4fab4e4a-d25e-4661-b235-2b45bf5ac3e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0bbbcabfb25cfc8b24cbb4cbc3d344d4e7f209b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825274"
---
# <span data-ttu-id="5b883-103">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="5b883-103">Getting Started with MBAM 1.0</span></span>

> <span data-ttu-id="5b883-104">**重要**MBAM 1.0 は、2021年9月14日にサポートを終了します。</span><span class="sxs-lookup"><span data-stu-id="5b883-104">**IMPORTANT** MBAM 1.0 will reach end of support on September 14, 2021.</span></span> 
> <span data-ttu-id="5b883-105">詳細については、[ライフサイクルのページ](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5b883-105">See our [lifecycle page](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0) for more information.</span></span> <span data-ttu-id="5b883-106">[Mbam 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions)またはサポートされている別のバージョンの mbam に移行するか、BitLocker 管理を[Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)に移行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b883-106">We recommend [migrating to MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions) or another supported version of MBAM, or migrating your BitLocker management to [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span>


<span data-ttu-id="5b883-107">Microsoft BitLocker の管理と監視 (MBAM) には、展開または機能を使用する前に、十分な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="5b883-107">Microsoft BitLocker Administration and Monitoring (MBAM) requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="5b883-108">この製品は組織内のすべてのコンピューターに影響を与える可能性があるため、展開を慎重に計画しないと、ネットワーク全体が壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5b883-108">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="5b883-109">ただし、展開を慎重に計画し、業務上のニーズを満たすように管理したい場合は、MBAM を使用すると、管理のオーバーヘッドと総所有コストの削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5b883-109">However, if you plan your deployment carefully and manage it so that it meets your business needs, MBAM can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="5b883-110">この製品を初めて使用する場合は、このドキュメントをよく読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b883-110">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="5b883-111">運用環境に展開する前に、テストネットワーク環境で展開計画を検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5b883-111">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="5b883-112">関連するテクノロジのトレーニングの受講もご検討ください。</span><span class="sxs-lookup"><span data-stu-id="5b883-112">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="5b883-113">Microsoft のトレーニングの機会の詳細については、「Microsoft トレーニングの概要」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="5b883-113">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="5b883-114">**注** このドキュメントのダウンロード可能なバージョンと MBAM の評価ガイドを参照でき <https://go.microsoft.com/fwlink/p/?LinkId=225356> ます。</span><span class="sxs-lookup"><span data-stu-id="5b883-114">**Note** You can find a downloadable version of this documentation and the MBAM Evaluation Guide at <https://go.microsoft.com/fwlink/p/?LinkId=225356>.</span></span>

 

<span data-ttu-id="5b883-115">MBAM 管理者ガイドのこのセクションには、展開計画を開始する前に、お客様に製品についての基本的な理解を提供するために、MBAM に関する高度な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5b883-115">This section of the MBAM Administrator’s Guide includes high-level information about MBAM to provide you with a basic understanding of the product before you begin the deployment planning.</span></span> <span data-ttu-id="5b883-116">追加の MBAM ドキュメントについては、MBAM のドキュメントリソースのダウンロードページを参照 <https://go.microsoft.com/fwlink/p/?LinkId=258391> してください。</span><span class="sxs-lookup"><span data-stu-id="5b883-116">Additional MBAM documentation can be found on the MBAM Documentation Resources Download page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="5b883-117">MBAM 1.0 の使用を開始する</span><span class="sxs-lookup"><span data-stu-id="5b883-117">Getting started with MBAM 1.0</span></span>


-   [<span data-ttu-id="5b883-118">MBAM 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="5b883-118">About MBAM 1.0</span></span>](about-mbam-10.md)

    <span data-ttu-id="5b883-119">MBAM の概要と組織での使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b883-119">Provides a high-level overview of MBAM and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="5b883-120">MBAM 1.0 の評価</span><span class="sxs-lookup"><span data-stu-id="5b883-120">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)

    <span data-ttu-id="5b883-121">組織で使用するために MBAM を最適に評価する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="5b883-121">Provides information about how you can best evaluate MBAM for use in your organization.</span></span>

-   [<span data-ttu-id="5b883-122">MBAM 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="5b883-122">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)

    <span data-ttu-id="5b883-123">MBAM 機能とその連携のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5b883-123">Provides a description of the MBAM features and how they work together.</span></span>

-   [<span data-ttu-id="5b883-124">MBAM 1.0 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="5b883-124">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)

    <span data-ttu-id="5b883-125">障碍のある方がこの製品とそれに対応するドキュメントのアクセシビリティを高めるための機能とサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5b883-125">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="5b883-126">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="5b883-126">Other resources for this product</span></span>


-   [<span data-ttu-id="5b883-127">Microsoft BitLocker の管理と監視1管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="5b883-127">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>](index.md)

-   [<span data-ttu-id="5b883-128">MBAM 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="5b883-128">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

-   [<span data-ttu-id="5b883-129">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="5b883-129">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

-   [<span data-ttu-id="5b883-130">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="5b883-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

-   [<span data-ttu-id="5b883-131">MBAM 1.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="5b883-131">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)

 

 





