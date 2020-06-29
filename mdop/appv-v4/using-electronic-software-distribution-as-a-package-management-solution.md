---
title: パッケージ管理ソリューションとしての電子ソフトウェア配布の使用
description: パッケージ管理ソリューションとしての電子ソフトウェア配布の使用
author: dansimp
ms.assetid: 7d96ea70-3e7e-49fa-89cc-586804a10657
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 12ec56d0fd52825a91a772e418ddd48b76294792
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815097"
---
# <span data-ttu-id="c93e7-103">パッケージ管理ソリューションとしての電子ソフトウェア配布の使用</span><span class="sxs-lookup"><span data-stu-id="c93e7-103">Using Electronic Software Distribution as a Package Management Solution</span></span>


<span data-ttu-id="c93e7-104">アプリケーションの仮想化では、パッケージを順序付けしてテストした後、仮想アプリケーションパッケージをターゲットコンピューターに展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c93e7-104">In Application Virtualization, after you have sequenced and tested a package, you need to deploy the virtual application package to the target computers.</span></span> <span data-ttu-id="c93e7-105">これを実現するには、パッケージコンテンツを配置する場所を決定し、それをエンドユーザーのコンピューターに配布する方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c93e7-105">To accomplish this, you will need to determine where to put the package content and how to deliver it to the end user computers.</span></span> <span data-ttu-id="c93e7-106">効率的で効果的な電子ソフトウェア配布ベースの展開計画を使用すると、多数のエンドユーザーのコンピューターで、低速のネットワーク接続経由でパッケージコンテンツを取得する必要がある状況を回避することができます。</span><span class="sxs-lookup"><span data-stu-id="c93e7-106">An efficient, effective electronic software distribution–based deployment plan will help you avoid the situation where large numbers of end users computers need to retrieve the package content over slow network connections.</span></span>

<span data-ttu-id="c93e7-107">現在、日常的な操作で電子ソフトウェア配布 (ESD) システムがある場合は、それを使って、アプリケーションの仮想化に必要なすべての管理タスクを処理することができます。</span><span class="sxs-lookup"><span data-stu-id="c93e7-107">If you currently have an electronic software distribution (ESD) system in daily operation, you can use it to handle all necessary management tasks in Application Virtualization.</span></span> <span data-ttu-id="c93e7-108">つまり、新しいサーバーやアプリケーションソフトウェアを追加する必要がなく、または必要な追加の管理オーバーヘッドが発生しないように、既存のインフラストラクチャを効果的に使うことができます。</span><span class="sxs-lookup"><span data-stu-id="c93e7-108">This means that you can effectively use your existing infrastructure to the best advantage, without the need to add new servers and application software or incur the additional administrative overhead that these would require.</span></span> <span data-ttu-id="c93e7-109">Microsoft Endpoint Configuration Manager が展開されて運用可能であることが理想的な場合は、Application Virtualization 管理タスクを実行するための組み込み機能が構成マネージャーに用意されていることがわかります。</span><span class="sxs-lookup"><span data-stu-id="c93e7-109">Ideally, if you have Microsoft Endpoint Configuration Manager deployed and operational, you will find that Configuration Manager has built-in capability for performing the Application Virtualization management tasks.</span></span>

<span data-ttu-id="c93e7-110">ESD ベースの展開を実行する方法について詳しくは、[電子的なソフトウェアの配布に基づくシナリオ](electronic-software-distribution-based-scenario.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c93e7-110">For in-depth information about performing an ESD-based deployment, [Electronic Software Distribution-Based Scenario](electronic-software-distribution-based-scenario.md).</span></span>

## <span data-ttu-id="c93e7-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c93e7-111">In This Section</span></span>


<a href="" id="publishing-virtual-applications-using-electronic-software-distribution"></a>[<span data-ttu-id="c93e7-112">電子ソフトウェア配布を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="c93e7-112">Publishing Virtual Applications Using Electronic Software Distribution</span></span>](publishing-virtual-applications-using-electronic-software-distribution.md)  
<span data-ttu-id="c93e7-113">順序付けされたアプリケーションをクライアントに配布するために使用できる ESD ベースのメソッドについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c93e7-113">Describes the available ESD-based methods for distributing your sequenced applications to clients.</span></span>

<a href="" id="planning-your-streaming-solution-in-an-electronic-software-distribution-implementation"></a>[<span data-ttu-id="c93e7-114">電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="c93e7-114">Planning Your Streaming Solution in an Electronic Software Distribution Implementation</span></span>](planning-your-streaming-solution-in-an-electronic-software-distribution-implementation.md)  
<span data-ttu-id="c93e7-115">ストリーミングサーバーを使用して、順序付けしたアプリケーションをクライアントに展開するために使用できるオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c93e7-115">Describes available options for using a streaming server to deploy your sequenced applications to clients.</span></span>

## <span data-ttu-id="c93e7-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c93e7-116">Related topics</span></span>


[<span data-ttu-id="c93e7-117">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c93e7-117">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="c93e7-118">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="c93e7-118">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





