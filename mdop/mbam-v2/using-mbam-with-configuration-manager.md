---
title: MBAM と Configuration Manager の使用
description: MBAM と Configuration Manager の使用
author: dansimp
ms.assetid: 03868717-4aa7-4897-8166-9a3df5e9519e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e3c5dd199010ac758ab701b0753d913ea323efd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823787"
---
# <span data-ttu-id="50548-103">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="50548-103">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="50548-104">Microsoft BitLocker の管理と監視 (MBAM) をインストールすると、Microsoft BitLocker の管理と監視を System Center Configuration Manager で統合したインストールを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="50548-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose an installation that integrates Microsoft BitLocker Administration and Monitoring with System Center Configuration Manager.</span></span> <span data-ttu-id="50548-105">構成マネージャーのサポートされているバージョンの一覧については、「 [Configuration manager を使用して MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="50548-105">For a list of the supported versions of Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="50548-106">この統合により、Microsoft System Center Configuration Manager のネイティブ環境に Microsoft BitLocker 管理と監視インフラストラクチャが移行されます。</span><span class="sxs-lookup"><span data-stu-id="50548-106">This integration moves the Microsoft BitLocker Administration and Monitoring compliance and reporting infrastructure into the native environment of Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="50548-107">Configuration Manager のトポロジを使用すると、IT 管理者は、Configuration Manager 管理コンソールから、エンタープライズのレポートとコンプライアンスの状態を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="50548-107">With the Configuration Manager topology, IT administrators can view reports and the compliance status of their enterprise from the Configuration Manager Management Console.</span></span>

<span data-ttu-id="50548-108">**重要** Configuration Manager 2007 で MBAM の統合トポロジをインストールする場合、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="50548-108">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <a href="" id="getting-started---using-mbam-with-configuration-manager"></a><span data-ttu-id="50548-109">はじめに-Configuration Manager での MBAM の使用</span><span class="sxs-lookup"><span data-stu-id="50548-109">Getting Started – Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="50548-110">このセクションでは、Configuration Manager を使用した MBAM の動作について説明し、構成マネージャーの統合トポロジで MBAM を展開するための推奨アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="50548-110">This section describes how MBAM works with Configuration Manager and explains the recommended architecture for deploying MBAM with the Configuration Manager Integration topology.</span></span>

[<span data-ttu-id="50548-111">はじめに - MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="50548-111">Getting Started - Using MBAM with Configuration Manager</span></span>](getting-started---using-mbam-with-configuration-manager.md)

## <span data-ttu-id="50548-112">Configuration Manager による MBAM の展開計画</span><span class="sxs-lookup"><span data-stu-id="50548-112">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="50548-113">このセクションでは、Configuration Manager のトポロジで MBAM をインストールする前に考慮する必要がある、インストールの前提条件、サポートされる構成、およびハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="50548-113">This section describes the installation prerequisites, supported configurations, and hardware and software requirements that you need to consider before you install MBAM with the Configuration Manager topology.</span></span>

[<span data-ttu-id="50548-114">Configuration Manager による MBAM の展開計画</span><span class="sxs-lookup"><span data-stu-id="50548-114">Planning to Deploy MBAM with Configuration Manager</span></span>](planning-to-deploy-mbam-with-configuration-manager-2.md)

## <span data-ttu-id="50548-115">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="50548-115">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="50548-116">このセクションでは、Configuration Manager を使用して MBAM を展開する方法と、管理および監視サーバーおよび Configuration Manager サーバーに MBAM をインストールして構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="50548-116">This section describes how to deploy MBAM with Configuration Manager, and includes instructions for installing and configuring the MBAM on the Administration and Monitoring Server and Configuration Manager Server.</span></span>

[<span data-ttu-id="50548-117">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="50548-117">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

## <span data-ttu-id="50548-118">Configuration Manager の MBAM レポートの概要</span><span class="sxs-lookup"><span data-stu-id="50548-118">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="50548-119">このセクションでは、Configuration Manager から実行できる MBAM レポートについて説明します。このセクションでは、エンタープライズの各コンピューターの企業とコンプライアンスのコンプライアンスを示すことができます。</span><span class="sxs-lookup"><span data-stu-id="50548-119">This section describes the MBAM reports that you can run from Configuration Manager to show the compliance of your enterprise and compliance of individual computers in your enterprise.</span></span>

[<span data-ttu-id="50548-120">Configuration Manager の MBAM レポートの概要</span><span class="sxs-lookup"><span data-stu-id="50548-120">Understanding MBAM Reports in Configuration Manager</span></span>](understanding-mbam-reports-in-configuration-manager.md)

## <span data-ttu-id="50548-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="50548-121">Related topics</span></span>


[<span data-ttu-id="50548-122">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="50548-122">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





