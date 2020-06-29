---
title: MBAM 2.0 の展開計画
description: MBAM 2.0 の展開計画
author: dansimp
ms.assetid: 2dc05fcd-aed9-4315-aeaf-92aaa9e0e955
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c7f065e52655212261dfe8b6b3f081f697142473
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825634"
---
# <span data-ttu-id="f1c18-103">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="f1c18-103">Planning to Deploy MBAM 2.0</span></span>


<span data-ttu-id="f1c18-104">Microsoft BitLocker の管理と監視 (MBAM) の展開計画を作成する前に、さまざまな展開構成と前提条件について検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f1c18-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="f1c18-105">このセクションには、お客様のビジネス要件に最適な展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f1c18-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span> <span data-ttu-id="f1c18-106">Configuration Manager トポロジを使用して MBAM をインストールする場合は、「 [Configuration manager で MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)場合の計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1c18-106">If you are installing MBAM with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional planning information.</span></span>

## <span data-ttu-id="f1c18-107">MBAM 2.0 でサポートされている構成を確認する</span><span class="sxs-lookup"><span data-stu-id="f1c18-107">Review the MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="f1c18-108">MBAM サーバーとクライアントの機能をインストールするためのコンピューティング環境を準備したら、MBAM をインストールするコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="f1c18-108">After preparing your computing environment for the MBAM Server and Client feature installation, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="f1c18-109">MBAM の展開の前提条件の詳細については、「 [mbam 2.0 の展開の前提条件](mbam-20-deployment-prerequisites-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f1c18-109">For more information about MBAM deployment prerequisites, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md).</span></span>

[<span data-ttu-id="f1c18-110">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="f1c18-110">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)

## <span data-ttu-id="f1c18-111">MBAM 2.0 サーバーとクライアントの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="f1c18-111">Plan for MBAM 2.0 Server and Client Deployment</span></span>


<span data-ttu-id="f1c18-112">MBAM サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="f1c18-112">The MBAM Server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="f1c18-113">これらの機能は、複数のサーバー間で分散された構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="f1c18-113">These features can be installed in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="f1c18-114">**注** 1つのサーバーに MBAM をインストールするのは、ラボ環境の場合のみにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f1c18-114">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="f1c18-115">MBAM クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="f1c18-115">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="f1c18-116">エンタープライズソフトウェア配信システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターにクライアントエージェントをインストールすることによって、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="f1c18-116">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the client agent on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="f1c18-117">MBAM では、エンドユーザーがコンピューターを受け取る前、またはグループポリシーを使用する前に、組織内のコンピューターを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="f1c18-117">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="f1c18-118">MBAM 2.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="f1c18-118">Planning for MBAM 2.0 Server Deployment</span></span>](planning-for-mbam-20-server-deployment-mbam-2.md)

[<span data-ttu-id="f1c18-119">MBAM 2.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="f1c18-119">Planning for MBAM 2.0 Client Deployment</span></span>](planning-for-mbam-20-client-deployment-mbam-2.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="f1c18-120">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="f1c18-120">Other Resources for MBAM Planning</span></span>


[<span data-ttu-id="f1c18-121">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="f1c18-121">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

 

 





