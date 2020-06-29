---
title: MBAM 1.0 サーバーの展開計画
description: MBAM 1.0 サーバーの展開計画
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812427"
---
# <span data-ttu-id="50224-103">MBAM 1.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="50224-103">Planning for MBAM 1.0 Server Deployment</span></span>


<span data-ttu-id="50224-104">Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="50224-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of your enterprise.</span></span>

## <span data-ttu-id="50224-105">MBAM サーバー展開の計画</span><span class="sxs-lookup"><span data-stu-id="50224-105">Planning for MBAM Server deployment</span></span>


<span data-ttu-id="50224-106">次の MBAM 機能は、MBAM サーバー展開のサーバーインフラストラクチャを表しています。</span><span class="sxs-lookup"><span data-stu-id="50224-106">The following MBAM features represent the server infrastructure for an MBAM server deployment:</span></span>

-   <span data-ttu-id="50224-107">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="50224-107">Recovery and Hardware Database</span></span>

-   <span data-ttu-id="50224-108">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="50224-108">Compliance and Audit Database</span></span>

-   <span data-ttu-id="50224-109">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="50224-109">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="50224-110">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="50224-110">Administration and Monitoring Server</span></span>

<span data-ttu-id="50224-111">MBAM server データベースと機能は、スケーラビリティのニーズに応じて、さまざまな構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="50224-111">MBAM server databases and features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="50224-112">すべての MBAM Server 機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。</span><span class="sxs-lookup"><span data-stu-id="50224-112">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="50224-113">通常、運用環境では、3台のサーバーまたは5サーバーの構成を使用することをお勧めしますが、コンピューティングのニーズに応じて、2つまたは4つのサーバーの構成も使うことができます。</span><span class="sxs-lookup"><span data-stu-id="50224-113">Generally, we recommend that you use a three-server or five-server configuration for production environments, although configurations of two or four servers can also be used, depending on your computing needs.</span></span>

<span data-ttu-id="50224-114">**注** MBAM と推奨される展開トポロジのパフォーマンスのスケーラビリティの詳細については、「MBAM スケーラビリティと高可用性ガイド」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。</span><span class="sxs-lookup"><span data-stu-id="50224-114">**Note** For more information about performance scalability of MBAM and recommended deployment topologies, see the MBAM Scalability and High-Availability Guide white paper at <https://go.microsoft.com/fwlink/p/?LinkId=258314>.</span></span>

 

<span data-ttu-id="50224-115">各 MBAM 機能には、特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="50224-115">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="50224-116">サーバー機能の前提条件とハードウェアとソフトウェアの要件の一覧については、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50224-116">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="50224-117">サーバー関連の MBAM 機能に加えて、サーバーセットアップアプリケーションには MBAM グループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="50224-117">In addition to the server-related MBAM features, the server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="50224-118">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="50224-118">This template can be installed on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

## <span data-ttu-id="50224-119">MBAM Server 機能の展開の順序</span><span class="sxs-lookup"><span data-stu-id="50224-119">Order of deployment of MBAM Server Features</span></span>


<span data-ttu-id="50224-120">MBAM Server 機能を展開する場合は、次の順序で機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="50224-120">When you deploy the MBAM Server features, install the features in the following order:</span></span>

1.  <span data-ttu-id="50224-121">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="50224-121">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="50224-122">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="50224-122">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="50224-123">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="50224-123">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="50224-124">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="50224-124">Administration and Monitoring Server</span></span>

5.  <span data-ttu-id="50224-125">ポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="50224-125">Policy Template</span></span>

<span data-ttu-id="50224-126">**注** 各機能をインストールするコンピューターの名前を把握しておきます。</span><span class="sxs-lookup"><span data-stu-id="50224-126">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="50224-127">この情報は、インストールプロセス全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="50224-127">You will use this information throughout the installation process.</span></span> <span data-ttu-id="50224-128">インストールプロセスを支援するために、展開チェックリストを印刷して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="50224-128">You can print and use a deployment checklist to assist you in the installation process.</span></span> <span data-ttu-id="50224-129">MBAM 展開チェックリストの詳細については、「 [mbam 1.0 の展開チェックリスト](mbam-10-deployment-checklist.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50224-129">For more information about the MBAM deployment checklist, see [MBAM 1.0 Deployment Checklist](mbam-10-deployment-checklist.md).</span></span>

 

## <span data-ttu-id="50224-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="50224-130">Related topics</span></span>


[<span data-ttu-id="50224-131">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="50224-131">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="50224-132">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="50224-132">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





