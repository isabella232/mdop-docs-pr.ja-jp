---
title: MBAM 1.0 の展開計画
description: MBAM 1.0 の展開計画
author: dansimp
ms.assetid: 30ad4304-45c6-427d-8e33-ebe8053c7871
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2ff25e705717db5086150ed08a5640335bbacb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823187"
---
# <span data-ttu-id="53dc5-103">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="53dc5-103">Planning to Deploy MBAM 1.0</span></span>


<span data-ttu-id="53dc5-104">Microsoft BitLocker の管理と監視 (MBAM) 1.0 展開計画を作成する前に、さまざまな展開構成と前提条件について検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53dc5-104">You should consider a number of different deployment configurations and prerequisites before you create your Microsoft BitLocker Administration and Monitoring (MBAM) 1.0 deployment plan.</span></span> <span data-ttu-id="53dc5-105">このセクションには、お客様のビジネス要件を満たす展開計画を策定するために必要な情報を収集するために役立つ情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="53dc5-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="53dc5-106">MBAM 1.0 でサポートされている構成を確認する</span><span class="sxs-lookup"><span data-stu-id="53dc5-106">Review the MBAM 1.0 supported configurations</span></span>


<span data-ttu-id="53dc5-107">MBAM クライアントとサーバー機能のインストールのためにコンピューティング環境を準備したら、mbam のサポートされている構成情報を確認して、MBAM をインストールするコンピューターがハードウェアとオペレーティングシステムの最小要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="53dc5-107">After you prepare your computing environment for the MBAM Client and Server feature installation, make sure that you review the Supported Configurations information for MBAM to confirm that the computers on which you install MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="53dc5-108">MBAM の展開の前提条件の詳細については、「 [mbam 1.0 の展開の前提条件](mbam-10-deployment-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53dc5-108">For more information about MBAM deployment prerequisites, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="53dc5-109">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="53dc5-109">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

## <span data-ttu-id="53dc5-110">MBAM 1.0 サーバーとクライアントの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="53dc5-110">Plan for MBAM 1.0 Server and Client deployment</span></span>


<span data-ttu-id="53dc5-111">MBAM サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="53dc5-111">The MBAM server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="53dc5-112">これらの機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。</span><span class="sxs-lookup"><span data-stu-id="53dc5-112">These features can be installed on a single server or distributed across multiple servers.</span></span>

<span data-ttu-id="53dc5-113">MBAM クライアントでは、管理者が企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="53dc5-113">The MBAM Client enables administrators to enforce and monitor the BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="53dc5-114">BitLocker クライアントを組織に統合するには、Active Directory ドメインサービスなどのツールを使用してクライアントを展開するか、または最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化します。</span><span class="sxs-lookup"><span data-stu-id="53dc5-114">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="53dc5-115">MBAM では、エンドユーザーがコンピューターを受け取る前または後にグループポリシーを使って、組織内のコンピューターを暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="53dc5-115">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer or afterwards, by using Group Policy.</span></span> <span data-ttu-id="53dc5-116">組織内の一方または両方の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="53dc5-116">You can use one or both methods in your organization.</span></span> <span data-ttu-id="53dc5-117">両方の方法を選択すると、コンプライアンス、レポート、キー回復のサポートが改善されます。</span><span class="sxs-lookup"><span data-stu-id="53dc5-117">If you choose to use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

[<span data-ttu-id="53dc5-118">MBAM 1.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="53dc5-118">Planning for MBAM 1.0 Server Deployment</span></span>](planning-for-mbam-10-server-deployment.md)

[<span data-ttu-id="53dc5-119">MBAM 1.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="53dc5-119">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="53dc5-120">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="53dc5-120">Other resources for MBAM planning</span></span>


-   [<span data-ttu-id="53dc5-121">MBAM 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="53dc5-121">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





