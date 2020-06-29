---
title: Application Virtualization の展開およびアップグレードに関する考慮事項
description: Application Virtualization の展開およびアップグレードに関する考慮事項
author: dansimp
ms.assetid: adc562ee-7276-4b14-b10a-da17f05e1682
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9e6c1a624b9da18bba75c5f3816a8e9c5391a8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822244"
---
# <span data-ttu-id="2506e-103">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="2506e-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="2506e-104">Microsoft Application Virtualization の展開を開始する前に、さまざまなアプリケーションの仮想化コンポーネントをインストールするためのハードウェアとソフトウェアの要件を含む、環境要件を確認することが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="2506e-104">Before you begin the deployment of Microsoft Application Virtualization, you might need to review your environment requirements, including the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="2506e-105">また、以前のバージョンからアップグレードする場合、このセクションのトピックでは、現在の Sequencer、サーバー、クライアントバージョンのアップグレードに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2506e-105">Also, if you are upgrading from a previous version, the topics in this section provide information about upgrading your current Sequencer, server, and client versions.</span></span>

## <span data-ttu-id="2506e-106">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2506e-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="2506e-107">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="2506e-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="2506e-108">アプリケーションの仮想化の展開に関するシステム要件とアップグレードの考慮事項に関する一般的な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="2506e-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="2506e-109">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="2506e-109">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="2506e-110">Application Virtualization デスクトップクライアント、またはリモートデスクトップサービス (旧ターミナルサービス) 用の Application Virtualization クライアントをアップグレードするための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2506e-110">Provides step-by-step procedures for upgrading the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="2506e-111">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="2506e-111">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="2506e-112">すべての Application Virtualization システムコンピューターにインストールされているソフトウェアコンポーネントをアップグレードするために使用できるステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2506e-112">Provides a step-by-step procedure you can use to upgrade the software components installed on all Application Virtualization System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="2506e-113">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="2506e-113">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="2506e-114">Windows Vista または WindowsXP を実行しているコンピューターで Sequencer をアップグレードするためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2506e-114">Provides step-by-step procedures for upgrading the Sequencer on computers running Windows Vista or WindowsXP.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="2506e-115">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2506e-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="2506e-116">Sequencer をインストールするためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2506e-116">Provides a step-by-step procedure for installing the Sequencer.</span></span>

## <span data-ttu-id="2506e-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2506e-117">Related topics</span></span>


[<span data-ttu-id="2506e-118">Application Virtualization リファレンス</span><span class="sxs-lookup"><span data-stu-id="2506e-118">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="2506e-119">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2506e-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="2506e-120">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="2506e-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="2506e-121">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="2506e-121">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





