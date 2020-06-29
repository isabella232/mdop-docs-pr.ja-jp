---
title: User Experience Virtualization 1.0 の概要
description: User Experience Virtualization 1.0 の概要
author: dansimp
ms.assetid: 74a068dc-4f87-4cb4-b114-8ca2a37149f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 010cefc42c8f2d65ac7f815eff51ec2df42df4d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827117"
---
# <span data-ttu-id="6e2e4-103">User Experience Virtualization 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="6e2e4-103">Getting Started With User Experience Virtualization 1.0</span></span>


<span data-ttu-id="6e2e4-104">Microsoft User Experience Virtualization (UE-V) では、ユーザーのアプリケーション設定と Windows オペレーティングシステムの設定がキャプチャされ、集中化されます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-104">Microsoft User Experience Virtualization (UE-V) captures and centralizes application settings and Windows operating system settings for the user.</span></span> <span data-ttu-id="6e2e4-105">これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-105">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="6e2e4-106">UE-V は、Microsoft アプリケーションと Windows の一般的な設定に対する設定の同期を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-106">UE-V offers settings synchronization for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="6e2e4-107">また、企業全体でユーザーが作業するときに、いつでもユーザー設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-107">It also delivers user settings at any time to wherever users work throughout the enterprise.</span></span> <span data-ttu-id="6e2e4-108">UE-V では、管理者が、どのアプリケーション設定と Windows 設定をローミングするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-108">UE-V allows administrators to specify which application settings and Windows settings roam.</span></span> <span data-ttu-id="6e2e4-109">UE-V は、エンタープライズで使用されるサードパーティまたは基幹業務アプリケーションのカスタム設定の場所テンプレートを管理者が作成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-109">UE-V helps administrators to create custom settings location templates for third-party or line-of-business applications that are used in the enterprise.</span></span>

<span data-ttu-id="6e2e4-110">ユーザーエクスペリエンスの仮想化によって、強化されたユーザーの状態仮想化エクスペリエンスが提供されます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-110">User Experience Virtualization delivers an enhanced user state virtualization experience.</span></span> <span data-ttu-id="6e2e4-111">次のシナリオでは、ユーザー設定の一貫性のあるカスタマイズを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-111">It provides consistent personalization of the user’s settings in the following scenarios:</span></span>

-   <span data-ttu-id="6e2e4-112">コンピューター間でのローミングユーザーアプリケーションと Windows の設定。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-112">Roaming user application and Windows settings between computers.</span></span>

-   <span data-ttu-id="6e2e4-113">さまざまなメソッドを使用して展開されているアプリケーションのインスタンス間のローミングユーザー設定。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-113">Roaming user settings between the instances of an application that are deployed by using different methods:</span></span>

    -   <span data-ttu-id="6e2e4-114">インストールされているアプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e2e4-114">Installed applications</span></span>

    -   <span data-ttu-id="6e2e4-115">Application Virtualization (App-v) シーケンスアプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e2e4-115">Application Virtualization (App-V) sequenced applications</span></span>

    -   <span data-ttu-id="6e2e4-116">RemoteApp (リモートデスクトップ仮想化) アプリケーション</span><span class="sxs-lookup"><span data-stu-id="6e2e4-116">RemoteApp (Remote Desktop Virtualization) applications</span></span>

-   <span data-ttu-id="6e2e4-117">置き換え、ハードウェアのアップグレード、または再イメージを行った後で、コンピューターの設定を回復します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-117">Recovering settings for a computer after replacement, hardware upgrade, or reimage.</span></span>

<span data-ttu-id="6e2e4-118">この製品を展開するか、その機能を使用する前に、完全な計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-118">This product requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="6e2e4-119">この製品は組織内のすべてのコンピューターに影響を与える可能性があるため、展開を慎重に計画しないと、ネットワーク全体が壊れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-119">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="6e2e4-120">ただし、展開を慎重に計画し、業務上のニーズを満たすように管理している場合は、この製品を使用すると、管理のオーバーヘッドと総所有コストの削減に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-120">However, if you plan your deployment carefully and manage it so that it meets your business needs, this product can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="6e2e4-121">この製品を初めてお持ちの場合は、ドキュメントを慎重に読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-121">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="6e2e4-122">製品を運用環境に展開する前に、テストネットワーク環境で展開計画を検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-122">Before you deploy the product to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="6e2e4-123">関連するテクノロジのトレーニングの受講もご検討ください。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-123">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="6e2e4-124">Microsoft のトレーニングの機会の詳細については、「Microsoft トレーニングの概要」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-124">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="6e2e4-125">**注** この管理者ガイドのダウンロード可能なバージョンは利用できません。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-125">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="6e2e4-126">ただし、TechNet ライブラリの特別モードでは、記事の選択、コレクションへのグループ化、またはのファイルへのエクスポートを行うことができ <https://go.microsoft.com/fwlink/?LinkId=272497> https://go.microsoft.com/fwlink/?LinkId=272497) ます。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-126">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272497> (https://go.microsoft.com/fwlink/?LinkId=272497).</span></span>

 

## <span data-ttu-id="6e2e4-127">Microsoft User Experience Virtualization の概要</span><span class="sxs-lookup"><span data-stu-id="6e2e4-127">Getting started with Microsoft User Experience Virtualization topics</span></span>


-   [<span data-ttu-id="6e2e4-128">User Experience Virtualization 1.0 について</span><span class="sxs-lookup"><span data-stu-id="6e2e4-128">About User Experience Virtualization 1.0</span></span>](about-user-experience-virtualization-10.md)

    <span data-ttu-id="6e2e4-129">ユーザーエクスペリエンスの仮想化の機能と機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-129">Describes the functionality and features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="6e2e4-130">UE-V 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="6e2e4-130">High-Level Architecture for UE-V 1.0</span></span>](high-level-architecture-for-ue-v-10.md)

    <span data-ttu-id="6e2e4-131">ユーザーエクスペリエンスの仮想化機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-131">Explains the features of User Experience Virtualization.</span></span>

-   [<span data-ttu-id="6e2e4-132">Microsoft User Experience Virtualization (UE-V) 1.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6e2e4-132">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)

    <span data-ttu-id="6e2e4-133">UE-V の既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-133">Describes the known issues for UE-V.</span></span>

-   [<span data-ttu-id="6e2e4-134">UE-V のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="6e2e4-134">Accessibility for UE-V</span></span>](accessibility-for-ue-v.md)

    <span data-ttu-id="6e2e4-135">UE-V のキーボードショートカットとユーザー補助情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="6e2e4-135">Describes the keyboard shortcuts and accessibility information for UE-V.</span></span>

## <span data-ttu-id="6e2e4-136">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="6e2e4-136">Other resources for this product</span></span>


-   [<span data-ttu-id="6e2e4-137">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="6e2e4-137">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

-   [<span data-ttu-id="6e2e4-138">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="6e2e4-138">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

-   [<span data-ttu-id="6e2e4-139">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="6e2e4-139">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

-   [<span data-ttu-id="6e2e4-140">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="6e2e4-140">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

-   [<span data-ttu-id="6e2e4-141">UE-V 1.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="6e2e4-141">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





