---
title: MBAM 1.0 サーバー インフラストラクチャの展開
description: MBAM 1.0 サーバー インフラストラクチャの展開
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de136db557233a097d95f47ef0a1bba5996798c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825177"
---
# <span data-ttu-id="542c0-103">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="542c0-103">Deploying the MBAM 1.0 Server Infrastructure</span></span>


<span data-ttu-id="542c0-104">Microsoft BitLocker 管理と監視 (MBAM) サーバー機能は、1 ~ 5 台のサーバーを使用して、さまざまな構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="542c0-104">You can install Microsoft BitLocker Administration and Monitoring (MBAM) Server features in different configurations by using one to five servers.</span></span> <span data-ttu-id="542c0-105">通常、運用環境では、スケーラビリティのニーズに応じて、3 ~ 5 台のサーバーの構成を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="542c0-105">Generally, you should use a configuration of three to five servers for production environments, depending on your scalability needs.</span></span> <span data-ttu-id="542c0-106">MBAM と推奨される展開トポロジのパフォーマンスのスケーラビリティの詳細については、「 [Mbam スケーラビリティと高可用性ガイドホワイトペーパー](https://go.microsoft.com/fwlink/p/?LinkId=258314)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="542c0-106">For more information about performance scalability of MBAM and recommended deployment topologies, see the [MBAM Scalability and High-Availability Guide White Paper](https://go.microsoft.com/fwlink/p/?LinkId=258314).</span></span>

## <span data-ttu-id="542c0-107">すべての MBAM 1.0 を1台のサーバーに展開する</span><span class="sxs-lookup"><span data-stu-id="542c0-107">Deploy all MBAM 1.0 on a single server</span></span>


<span data-ttu-id="542c0-108">この構成では、すべての MBAM 機能が1台のサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-108">In this configuration, all MBAM features are installed on a single server.</span></span> <span data-ttu-id="542c0-109">MBAM サーバーインフラストラクチャ向けのこの展開トポロジは、最大 21000 MBAM クライアントコンピューターをサポートします。</span><span class="sxs-lookup"><span data-stu-id="542c0-109">This deployment topology for MBAM server infrastructure will support up to 21,000 MBAM client computers.</span></span>

<span data-ttu-id="542c0-110">**重要** この構成はサポートされていますが、テストのみに使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="542c0-110">**Important** This configuration is supported, but we recommend it for testing only.</span></span>

 

<span data-ttu-id="542c0-111">このセクションの手順では、1つのサーバーに MBAM 機能を完全にインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="542c0-111">The procedures in this section describe the full installation of the MBAM features on a single server.</span></span>

[<span data-ttu-id="542c0-112">単一サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="542c0-112">How to Install and Configure MBAM on a Single Server</span></span>](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <span data-ttu-id="542c0-113">分散サーバーに MBAM 1.0 を展開する</span><span class="sxs-lookup"><span data-stu-id="542c0-113">Deploy MBAM 1.0 on distributed servers</span></span>


<span data-ttu-id="542c0-114">MBAM 機能は、スケーラビリティのニーズに応じて、さまざまな構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="542c0-114">MBAM features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="542c0-115">MBAM サーバー機能の展開を計画する方法の詳細については、「 [mbam 1.0 サーバー展開の計画](planning-for-mbam-10-server-deployment.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="542c0-115">For more information about how to plan for MBAM server feature deployment, see [Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md).</span></span>

<span data-ttu-id="542c0-116">このセクションの手順では、分散サーバー上の MBAM 機能の完全なインストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="542c0-116">The procedures in this section describe the full installation of the MBAM features on distributed servers.</span></span>

### <span data-ttu-id="542c0-117">3台のコンピューター構成</span><span class="sxs-lookup"><span data-stu-id="542c0-117">Three-computer configuration</span></span>

<span data-ttu-id="542c0-118">次の図は、MBAM 向けの3台のコンピューターの展開トポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="542c0-118">The following diagram displays the three-computer deployment topology for MBAM.</span></span> <span data-ttu-id="542c0-119">最大 55000 MBAM クライアントをサポートする運用環境では、このトポロジをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="542c0-119">We recommend this topology for production environments that support up to 55,000 MBAM Clients.</span></span>

![mbam 3 台のコンピューターの展開トポロジ](images/mbam-3-server.jpg)

<span data-ttu-id="542c0-121">この構成では、MBAM 機能は次の構成でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-121">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="542c0-122">回復とハードウェアデータベース、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートはサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-122">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="542c0-123">サーバーには、管理と監視のサーバー機能がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="542c0-123">Administration and Monitoring Server feature is installed on a server.</span></span>

3.  <span data-ttu-id="542c0-124">MBAM グループポリシーテンプレートは、グループポリシーオブジェクト (GPO) を変更できるコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="542c0-124">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects (GPO).</span></span>

### <span data-ttu-id="542c0-125">4台のコンピューターによる構成</span><span class="sxs-lookup"><span data-stu-id="542c0-125">Four-computer configuration</span></span>

<span data-ttu-id="542c0-126">次の図は、MBAM 向けの4台のコンピューターの展開トポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="542c0-126">The following diagram displays the four-computer deployment topology for MBAM.</span></span> <span data-ttu-id="542c0-127">最大 11万 MBAM クライアントをサポートしている運用環境では、このトポロジをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="542c0-127">We recommended this topology for production environments that support up to 110,000 MBAM Clients.</span></span>

![mbam 4 台のコンピューターの展開トポロジ。](images/mbam-4-computer.jpg)

<span data-ttu-id="542c0-129">この構成では、MBAM 機能は次の構成でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-129">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="542c0-130">回復とハードウェアデータベース、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートはサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-130">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="542c0-131">管理と監視サーバー機能は、ネットワーク負荷分散 (NLB) サーバークラスターで構成されているサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-131">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

3.  <span data-ttu-id="542c0-132">MBAM グループポリシーテンプレートは、グループポリシーオブジェクトを変更できるコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="542c0-132">MBAM Group Policy template is installed on a computer that is capable of modifying the Group Policy Objects.</span></span>

### <span data-ttu-id="542c0-133">5台のコンピューター構成</span><span class="sxs-lookup"><span data-stu-id="542c0-133">Five-computer configuration</span></span>

<span data-ttu-id="542c0-134">次の図は、MBAM の5台のコンピューターの展開トポロジを示しています。</span><span class="sxs-lookup"><span data-stu-id="542c0-134">The following diagram displays the five-computer deployment topology for MBAM.</span></span> <span data-ttu-id="542c0-135">最大 135000 MBAM クライアントをサポートする運用環境では、このトポロジをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="542c0-135">We recommend this topology for production environments that support up to 135,000 MBAM Clients.</span></span>

![mbam 5 台のコンピューターの展開トポロジ。](images/mbam-5-computer.jpg)

<span data-ttu-id="542c0-137">この構成では、MBAM 機能は次の構成でインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-137">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="542c0-138">回復とハードウェアデータベースはサーバーにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="542c0-138">Recovery and Hardware Database is installed on a server.</span></span>

2.  <span data-ttu-id="542c0-139">コンプライアンスと監査データベース、コンプライアンスおよび監査レポートは、サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-139">The Compliance and Audit Database and Compliance and Audit Reports are installed on a server.</span></span>

3.  <span data-ttu-id="542c0-140">管理と監視サーバー機能は、ネットワーク負荷分散 (NLB) サーバークラスターで構成されているサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="542c0-140">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

4.  <span data-ttu-id="542c0-141">MBAM グループポリシーテンプレートは、グループポリシーオブジェクトを変更できるコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="542c0-141">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects.</span></span>

[<span data-ttu-id="542c0-142">分散サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="542c0-142">How to Install and Configure MBAM on Distributed Servers</span></span>](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[<span data-ttu-id="542c0-143">MBAM のネットワーク負荷分散を構成する方法</span><span class="sxs-lookup"><span data-stu-id="542c0-143">How to Configure Network Load Balancing for MBAM</span></span>](how-to-configure-network-load-balancing-for-mbam.md)

## <span data-ttu-id="542c0-144">MBAM 1.0 Server 機能の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="542c0-144">Other resources for MBAM 1.0 Server features deployment</span></span>


[<span data-ttu-id="542c0-145">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="542c0-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





