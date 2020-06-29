---
title: MBAM 2.5 に対応する環境の準備
description: MBAM 2.5 に対応する環境の準備
author: dansimp
ms.assetid: 7552ba08-9dbf-40cd-8920-203d733fd242
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b18c9853035018c2e36dd447fbf0effbf49c45cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825494"
---
# <span data-ttu-id="25e6a-103">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="25e6a-103">Preparing your Environment for MBAM 2.5</span></span>


<span data-ttu-id="25e6a-104">Microsoft BitLocker の管理と監視 (MBAM) のセットアップを開始する前に、製品をインストールするための前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-104">Before beginning Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should make sure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="25e6a-105">前提条件が事前に判明していることがわかっている場合は、組織のビジネス目標を効率的にサポートするために、製品を効率的に展開し、その機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="25e6a-105">When you know what the prerequisites are ahead of time, you can efficiently deploy the product and enable its features so that it most effectively supports your organization’s business objectives.</span></span>

<span data-ttu-id="25e6a-106">Configuration Manager を使用して Microsoft BitLocker の管理と監視を展開している場合は、このトピックで後述する構成マネージャーの追加要件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-106">If you are deploying Microsoft BitLocker Administration and Monitoring with Configuration Manager, ensure that you meet the additional requirements for Configuration Manager, which are listed later in this topic.</span></span>

## <span data-ttu-id="25e6a-107">MBAM 2.5 の展開の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="25e6a-107">Review MBAM 2.5 deployment prerequisites</span></span>


<span data-ttu-id="25e6a-108">MBAM の展開を成功させるためには、MBAM クライアントをインストールして MBAM サーバー機能を構成する前に、必要なソフトウェアの前提条件を確認して完了していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-108">To ensure that your MBAM deployment is successful, make sure that you review and complete the required software prerequisites before you install the MBAM Client and configure the MBAM Server features.</span></span>

[<span data-ttu-id="25e6a-109">MBAM 2.5 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="25e6a-109">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)

## <span data-ttu-id="25e6a-110">MBAM 2.5 グループポリシー要件を計画する</span><span class="sxs-lookup"><span data-stu-id="25e6a-110">Plan for MBAM 2.5 Group Policy requirements</span></span>


<span data-ttu-id="25e6a-111">MBAM で企業のクライアントを管理するには、MBAM に固有のグループポリシーテンプレートをダウンロードして構成し、環境に合わせてグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e6a-111">Before MBAM can manage clients in the enterprise, you must download and configure Group Policy templates that are specific to MBAM, and then configure the Group Policy settings that you want for your environment.</span></span>

[<span data-ttu-id="25e6a-112">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="25e6a-112">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)

## <span data-ttu-id="25e6a-113">MBAM 2.5 ロールとアカウントの計画</span><span class="sxs-lookup"><span data-stu-id="25e6a-113">Plan for MBAM 2.5 roles and accounts</span></span>


<span data-ttu-id="25e6a-114">前提条件の一部として、MBAM で使用される特定の役割とアカウントを定義し、SQL Server 上で実行されているデータベース、管理/監視サーバー上で実行されている web アプリケーションなどの特定のサーバーや機能に対するセキュリティとアクセス権を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="25e6a-114">As part of the prerequisites, you must define certain roles and accounts, which are used in MBAM to provide security and access rights to specific servers and features, such as the databases running on SQL Server and the web applications running on the Administration and Monitoring Server.</span></span>

[<span data-ttu-id="25e6a-115">MBAM 2.5 グループとアカウントの計画</span><span class="sxs-lookup"><span data-stu-id="25e6a-115">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)

## <span data-ttu-id="25e6a-116">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="25e6a-116">Other resources for MBAM planning</span></span>


[<span data-ttu-id="25e6a-117">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="25e6a-117">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="25e6a-118">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="25e6a-118">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="25e6a-119">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="25e6a-120">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="25e6a-121">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="25e6a-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





