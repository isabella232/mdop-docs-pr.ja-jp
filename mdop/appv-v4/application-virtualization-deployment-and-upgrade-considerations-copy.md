---
title: Application Virtualization の展開およびアップグレードに関する考慮事項
description: Application Virtualization の展開およびアップグレードに関する考慮事項
author: dansimp
ms.assetid: c3c38930-0da3-43e6-b240-945edfd00a01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09e6943c74c7f17b6a61bc7be4bcde925a54be56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822274"
---
# <span data-ttu-id="319dc-103">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="319dc-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="319dc-104">Microsoft Application Virtualization (App-v) の展開を開始する前に、さまざまなアプリケーションの仮想化コンポーネントをインストールするためのハードウェアとソフトウェアの要件を含む環境要件を確認することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="319dc-104">Before you begin the deployment of Microsoft Application Virtualization (App-V), you might have to review your environment requirements that includes the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="319dc-105">また、以前のバージョンからアップグレードする場合、このセクションのトピックでは、現在の Sequencer、サーバー、およびクライアントのバージョンをアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-105">Also, if you are upgrading from an earlier version, the topics in this section provide information about how to upgrade your current Sequencer, Server, and Client versions.</span></span>

## <span data-ttu-id="319dc-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="319dc-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="319dc-107">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="319dc-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="319dc-108">アプリケーションの仮想化の展開に関するシステム要件とアップグレードの考慮事項に関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="319dc-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-checklists"></a>[<span data-ttu-id="319dc-109">Application Virtualization の展開およびアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="319dc-109">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)  
<span data-ttu-id="319dc-110">特定の手順へのリンクを含む、インストールとアップグレードのタスクの詳細な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="319dc-110">Provides detailed lists of installation and upgrade tasks with links to the specific procedures.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="319dc-111">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-111">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="319dc-112">サーバーベースの展開に必要な Application Virtualization (App-v) プラットフォームコンポーネントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-112">Describes how to install the Application Virtualization (App-V) platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-manually-install-the-application-virtualization-client"></a>[<span data-ttu-id="319dc-113">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-113">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)  
<span data-ttu-id="319dc-114">Application Virtualization クライアントソフトウェアをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-114">Describes how to install the Application Virtualization Client software.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="319dc-115">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="319dc-116">Application Virtualization Sequencer をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-116">Describes how to install the Application Virtualization Sequencer.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="319dc-117">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-117">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="319dc-118">Application Virtualization デスクトップクライアント、またはリモートデスクトップサービス (旧ターミナルサービス) 用の Application Virtualization クライアントをアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-118">Describes how to upgrade the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="319dc-119">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-119">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="319dc-120">すべての Application Virtualization 管理システムコンピューターにインストールされているソフトウェアコンポーネントをアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-120">Describes how to upgrade the software components installed on all Application Virtualization Management System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="319dc-121">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="319dc-121">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="319dc-122">Windows Vista または WindowsXP を実行しているコンピューターで Sequencer をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="319dc-122">Describes how to upgrade the Sequencer on computers that are running WindowsVista or WindowsXP.</span></span>

## <span data-ttu-id="319dc-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="319dc-123">Related topics</span></span>


[<span data-ttu-id="319dc-124">Application Virtualization リファレンス</span><span class="sxs-lookup"><span data-stu-id="319dc-124">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="319dc-125">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="319dc-125">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="319dc-126">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="319dc-126">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="319dc-127">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="319dc-127">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





