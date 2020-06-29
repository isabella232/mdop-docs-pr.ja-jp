---
title: MBAM 2.0 をお使いになる前に
description: MBAM 2.0 をお使いになる前に
author: dansimp
ms.assetid: 29f5c9af-5bbf-4d37-aa0f-0716046904af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7c683e3d8718da24ebd2164328bda0dab0123037
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825647"
---
# <span data-ttu-id="d6d90-103">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="d6d90-103">Getting Started with MBAM 2.0</span></span>


<span data-ttu-id="d6d90-104">Microsoft BitLockerAdministration と Monitoring (MBAM) 2.0 は、展開またはその機能を使用する前に、十分な計画を立てる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d6d90-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="d6d90-105">この製品は組織内のすべてのコンピューターに影響を与える可能性があるため、展開を慎重に計画しないと、ネットワーク全体が壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="d6d90-105">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="d6d90-106">ただし、展開を慎重に計画して、ビジネス要件を満たすように管理したい場合は、BitLockerAdministration と Monitoring 2.0 を使用すると、管理者のオーバーヘッドと総所有コストの削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d6d90-106">However, if you plan your deployment carefully and manage it so that it meets your business requirements, BitLockerAdministration and Monitoring2.0 can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="d6d90-107">この製品を初めてお持ちの場合は、ドキュメントを慎重に読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6d90-107">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="d6d90-108">MBAM ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/p/?LinkId=322049)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d6d90-108">To get the MBAM software, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span> <span data-ttu-id="d6d90-109">MBAM を運用環境に展開する前に、テスト環境で展開計画を検証することもお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d6d90-109">Before you deploy MBAM to a production environment, we also recommend that you validate your deployment plan in a test environment.</span></span> <span data-ttu-id="d6d90-110">関連するテクノロジのトレーニングの受講もご検討ください。</span><span class="sxs-lookup"><span data-stu-id="d6d90-110">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="d6d90-111">Microsoft のトレーニングの機会の詳細については、「Microsoft トレーニングの概要」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="d6d90-111">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="d6d90-112">MBAM 2.0 管理者ガイドのこのセクションには、展開を計画する前に、MBAM 2.0 についての詳細な情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d6d90-112">This section of the MBAM2.0 Administrator’s Guide includes high-level information about MBAM2.0 to provide a basic understanding of the product before you begin to plan deployment.</span></span> <span data-ttu-id="d6d90-113">Configuration Manager の統合トポロジでの MBAM の展開について詳しくは、「 [mbam と構成マネージャーを使用する](using-mbam-with-configuration-manager.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d6d90-113">For specific information about deploying MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="d6d90-114">Microsoft BitLocker の管理と監視 (MBAM) ドキュメントリソースのダウンロードページで、追加の MBAM ドキュメントを見つけることができ <https://go.microsoft.com/fwlink/p/?LinkId=258391> ます。</span><span class="sxs-lookup"><span data-stu-id="d6d90-114">You can find additional MBAM documentation on the Microsoft BitLocker Administration and Monitoring (MBAM) Documentation Resources Download Page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="d6d90-115">MBAM 2.0 の概要</span><span class="sxs-lookup"><span data-stu-id="d6d90-115">Getting Started with MBAM2.0</span></span>


-   [<span data-ttu-id="d6d90-116">MBAM 2.0 の概要</span><span class="sxs-lookup"><span data-stu-id="d6d90-116">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

    <span data-ttu-id="d6d90-117">MBAM 2.0 の概要と組織での使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6d90-117">Provides a high-level overview of MBAM2.0 and describes how it can be used in your organization.</span></span>

-   [<span data-ttu-id="d6d90-118">MBAM 2.0 の評価</span><span class="sxs-lookup"><span data-stu-id="d6d90-118">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)

    <span data-ttu-id="d6d90-119">組織で使用するために MBAM 2.0 を最適に評価する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d6d90-119">Provides information about how you can best evaluate MBAM2.0 for use in your organization.</span></span>

-   [<span data-ttu-id="d6d90-120">MBAM 2.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="d6d90-120">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)

    <span data-ttu-id="d6d90-121">MBAM 2.0 の機能と実稼働環境の推奨アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6d90-121">Describes the MBAM2.0 features and the recommended architecture for a production environment.</span></span>

-   [<span data-ttu-id="d6d90-122">MBAM 2.0 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="d6d90-122">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)

    <span data-ttu-id="d6d90-123">MBAM 2.0 で利用できるキーボードショートカットについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d6d90-123">Describes the keyboard shortcuts that are available for MBAM2.0.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="d6d90-124">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="d6d90-124">Other Resources for this Product</span></span>


[<span data-ttu-id="d6d90-125">Microsoft BitLocker の管理と監視2管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="d6d90-125">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="d6d90-126">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="d6d90-126">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="d6d90-127">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="d6d90-127">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

[<span data-ttu-id="d6d90-128">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="d6d90-128">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="d6d90-129">MBAM 2.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d6d90-129">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





