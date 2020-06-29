---
title: MBAM 2.5 の展開計画
description: MBAM 2.5 の展開計画
author: dansimp
ms.assetid: 1343b80c-d87a-42e7-b912-e84ba997d7e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2e955b426b00539aa2a4ef0b7c3a6650b05633a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826694"
---
# <span data-ttu-id="073db-103">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="073db-103">Planning to Deploy MBAM 2.5</span></span>


<span data-ttu-id="073db-104">Microsoft BitLocker の管理と監視 (MBAM) の展開計画を作成する前に、さまざまな展開構成と前提条件について検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="073db-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="073db-105">このセクションには、お客様のビジネス要件に最適な展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="073db-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="073db-106">MBAM 2.5 でサポートされている構成を確認する</span><span class="sxs-lookup"><span data-stu-id="073db-106">Review the MBAM 2.5 supported configurations</span></span>


<span data-ttu-id="073db-107">MBAM Server およびクライアント機能の展開のためにコンピューティング環境を準備した後、MBAM をインストールするコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="073db-107">After preparing your computing environment for the MBAM Server and Client feature deployment, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="073db-108">MBAM の展開の前提条件の詳細については、「 [mbam 2.5 の展開の前提条件](mbam-25-deployment-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="073db-108">For more information about MBAM deployment prerequisites, see [MBAM 2.5 Deployment Prerequisites](mbam-25-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="073db-109">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="073db-109">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="073db-110">MBAM 2.5 サーバーとクライアントの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="073db-110">Plan for MBAM 2.5 Server and Client deployment</span></span>


<span data-ttu-id="073db-111">MBAM サーバーインフラストラクチャは、企業の要件に基づいて、1つまたは複数のサーバーコンピューターで構成できるサーバー機能のセットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="073db-111">The MBAM Server infrastructure depends on a set of server features that can be configured on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="073db-112">これらの機能は、複数のサーバー間の分散構成で構成できます。</span><span class="sxs-lookup"><span data-stu-id="073db-112">These features can be configured in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="073db-113">**注** 1つのサーバーに MBAM をインストールするのは、ラボ環境の場合のみにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="073db-113">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="073db-114">MBAM クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="073db-114">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="073db-115">エンタープライズソフトウェア配信システムを通じてクライアントを展開するか、または最初のイメージングプロセスの一部としてクライアントコンピューターにクライアントをインストールすることによって、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="073db-115">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the Client on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="073db-116">MBAM では、エンドユーザーがコンピューターを受け取る前、またはグループポリシーを使用する前に、組織内のコンピューターを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="073db-116">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="073db-117">MBAM 2.5 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="073db-117">Planning for MBAM 2.5 Server Deployment</span></span>](planning-for-mbam-25-server-deployment.md)

[<span data-ttu-id="073db-118">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="073db-118">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="073db-119">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="073db-119">Other resources for MBAM planning</span></span>


[<span data-ttu-id="073db-120">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="073db-120">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

## <span data-ttu-id="073db-121">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="073db-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="073db-122">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="073db-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="073db-123">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="073db-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





