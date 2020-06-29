---
title: DaRT 7.0 の展開計画
description: DaRT 7.0 の展開計画
author: dansimp
ms.assetid: 05e97cdb-a8c2-46e4-9c75-a7d12fe26fe8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09725e994a95f4f93ae655402e7577e137e33f18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821317"
---
# <span data-ttu-id="d783a-103">DaRT 7.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="d783a-103">Planning to Deploy DaRT 7.0</span></span>


<span data-ttu-id="d783a-104">展開計画を作成する前に考慮する必要がある、さまざまな展開構成と前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="d783a-104">There are a number of different deployment configurations and prerequisites that you must consider before you create your deployment plan.</span></span> <span data-ttu-id="d783a-105">このセクションには、お客様のビジネス要件を満たす展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="d783a-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

<span data-ttu-id="d783a-106">Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 のインストールを計画する場合は、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d783a-106">Consider the following when you plan your Microsoft Diagnostics and Recovery Toolset (DaRT)7 installation:</span></span>

-   <span data-ttu-id="d783a-107">DaRT をインストールする場合は、DaRT の実行に関連するすべてのタスクを実行する IT 管理者コンピュータにすべての機能をインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="d783a-107">When you install DaRT, you can either install all functionality on an IT administrator computer where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="d783a-108">または、IT 管理者のコンピューターに回復イメージを作成する DaRT 機能のみをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d783a-108">Or you can install only the DaRT functionality that creates the recovery image on the IT administrator computer.</span></span> <span data-ttu-id="d783a-109">次に、サポート担当者のコンピューターで**Dart リモート接続ビューアー**や**クラッシュアナライザー**などの dart を実行するために使用される機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d783a-109">Then, install the functionality used to run DaRT, such as the **DaRT Remote Connection Viewer** and **Crash Analyzer**, on a helpdesk agent computer.</span></span>

-   <span data-ttu-id="d783a-110">DaRT をリモートで実行できるようにするには、ヘルプデスクのエージェントコンピュータと、リモートでトラブルシューティングしているすべてのコンピュータが同じネットワーク上にあることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d783a-110">To be able to run DaRT remotely, make sure that the helpdesk agent computer and all computers that you might be troubleshooting remotely are on the same network.</span></span>

-   <span data-ttu-id="d783a-111">DaRT を運用環境に展開する前に、テスト用のラボ環境を構築することができます。</span><span class="sxs-lookup"><span data-stu-id="d783a-111">Before you roll out DaRT into production, you can first build a lab environment for testing.</span></span> <span data-ttu-id="d783a-112">テストラボには、少なくとも2台のコンピューターを含める必要があります。1つは IT 管理者またはヘルプデスクエージェントコンピューターとして機能し、もう1つはエンドユーザーコンピューターとして機能します。</span><span class="sxs-lookup"><span data-stu-id="d783a-112">A test lab should include a minimum of two computers, one to act as the IT administrator/helpdesk agent computer and one to act as an end-user computer.</span></span> <span data-ttu-id="d783a-113">また、IT 管理者の責任を、ヘルプデスクエージェントの担当者と分離する場合は、ラボで3台のコンピューターを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d783a-113">Or, you can use three computers in your lab if you want to separate the IT administrator responsibilities from those of the helpdesk agent.</span></span>

## <span data-ttu-id="d783a-114">サポートされている構成を確認する</span><span class="sxs-lookup"><span data-stu-id="d783a-114">Review the supported configurations</span></span>


<span data-ttu-id="d783a-115">クライアントまたは機能のインストール用に選択したコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認するには、Microsoft 診断/回復ツールセット (DaRT) 7 でサポートされている構成の情報を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d783a-115">You should review the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Supported Configurations information to confirm that the computers you have selected for client or feature installation meet the minimum hardware and operating system requirements.</span></span>

[<span data-ttu-id="d783a-116">DaRT 7.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="d783a-116">DaRT 7.0 Supported Configurations</span></span>](dart-70-supported-configurations-dart-7.md)

## <span data-ttu-id="d783a-117">DaRT リカバリ画像の作成計画</span><span class="sxs-lookup"><span data-stu-id="d783a-117">Plan for creating the DaRT recovery image</span></span>


<span data-ttu-id="d783a-118">DaRT リカバリ画像を作成する場合は、イメージに含めるツールを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d783a-118">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="d783a-119">この決定を行うときは、さまざまな DaRT ツールへのアクセス権がエンドユーザーによって異なる可能性があることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="d783a-119">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="d783a-120">回復イメージを作成するときに、追加のドライバーまたはファイルを含めるかどうかも指定します。</span><span class="sxs-lookup"><span data-stu-id="d783a-120">When you create the recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="d783a-121">DaRT リカバリ画像に含める追加のドライバーまたはファイルの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="d783a-121">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="d783a-122">DaRT リカバリ画像の作成に関する前提条件とその他の計画に関する推奨事項について注意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d783a-122">You should be aware of the prerequisites and other additional planning recommendations for creating the DaRT recovery image.</span></span>

[<span data-ttu-id="d783a-123">DaRT 7.0 の回復イメージの作成計画</span><span class="sxs-lookup"><span data-stu-id="d783a-123">Planning to Create the DaRT 7.0 Recovery Image</span></span>](planning-to-create-the-dart-70-recovery-image.md)

## <span data-ttu-id="d783a-124">DaRT リカバリイメージの保存と展開を計画する</span><span class="sxs-lookup"><span data-stu-id="d783a-124">Plan for saving and deploying the DaRT recovery image</span></span>


<span data-ttu-id="d783a-125">DaRT リカバリ画像を保存して展開するには、いくつかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="d783a-125">Several methods can be used to save and deploy the DaRT recovery image.</span></span> <span data-ttu-id="d783a-126">使用する方法を決定する際には、それぞれの長所と短所を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="d783a-126">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="d783a-127">また、企業での DaRT の使用方法についても検討してください。</span><span class="sxs-lookup"><span data-stu-id="d783a-127">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="d783a-128">**注** 組織では、複数の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="d783a-128">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="d783a-129">たとえば、ほとんどの状況についてはリモートのパーティションから DaRT を起動し、エンドユーザーのコンピューターがネットワークに接続できない場合は USB フラッシュドライブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="d783a-129">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

[<span data-ttu-id="d783a-130">DaRT 7.0 の回復イメージの保存および展開方法の計画</span><span class="sxs-lookup"><span data-stu-id="d783a-130">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)

## <span data-ttu-id="d783a-131">DaRT の展開を計画するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="d783a-131">Other resources for Planning to Deploy DaRT</span></span>


[<span data-ttu-id="d783a-132">DaRT 7.0 の計画</span><span class="sxs-lookup"><span data-stu-id="d783a-132">Planning for DaRT 7.0</span></span>](planning-for-dart-70-new-ia.md)

 

 





