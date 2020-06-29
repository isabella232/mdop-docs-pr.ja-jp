---
title: プロジェクト スコープを定義する
description: プロジェクト スコープを定義する
author: dansimp
ms.assetid: 84637d2a-2e30-417d-b150-dc81f414b3a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4f33562452327bba9036f56d9f6f96650f00c1f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823644"
---
# <span data-ttu-id="314ac-103">プロジェクト スコープを定義する</span><span class="sxs-lookup"><span data-stu-id="314ac-103">Define the Project Scope</span></span>


<span data-ttu-id="314ac-104">プロジェクトのスコープを定義するときは、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="314ac-104">When defining the project scope, determine the following:</span></span>

1.  <span data-ttu-id="314ac-105">MED-V エンドユーザー (エンドユーザーの場所と数) は、med-v クライアントインストールの場所と、med-v インスタンスの数と、MED-V イメージリポジトリの数と配置を決定する際に使用されます。</span><span class="sxs-lookup"><span data-stu-id="314ac-105">The MED-V end users—the location and number of end users are used in determining the location of MED-V client installations and the number of MED-V instances, as well as the number and placement of MED-V image repositories.</span></span>

2.  <span data-ttu-id="314ac-106">MED-V によって管理される仮想マシン (VM) の画像。イメージリポジトリの配置方法を決定します。</span><span class="sxs-lookup"><span data-stu-id="314ac-106">The virtual machine (VM) images to be managed by MED-V—to determine the method of distributing images and placement of image repositories.</span></span>

3.  <span data-ttu-id="314ac-107">組織のサービスレベルの期待値: MED-V サーバーとデータベース、およびイメージリポジトリのパフォーマンスとフォールトトレランスの要件を決定します。</span><span class="sxs-lookup"><span data-stu-id="314ac-107">The organization’s service level expectations—to determine the performance and fault-tolerance requirements for the MED-V server and database as well as the image repository.</span></span>

4.  <span data-ttu-id="314ac-108">ビジネスで検証する: 計画されたインフラストラクチャがビジネスにどのように影響するかを完全に理解していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="314ac-108">Validate with the business—ensure there is a complete understanding of how the planned infrastructure affects the business.</span></span>

## <span data-ttu-id="314ac-109">MED-V エンドユーザーを定義する</span><span class="sxs-lookup"><span data-stu-id="314ac-109">Define the MED-V End Users</span></span>


<span data-ttu-id="314ac-110">最初に、エンドユーザーが配置されている場所と、各場所のユーザー数を確認します。</span><span class="sxs-lookup"><span data-stu-id="314ac-110">First, determine where the end users are located, as well as the number of users in each location.</span></span> <span data-ttu-id="314ac-111">次に、ユーザーの場所とそれらの場所の利用可能な帯域幅を表示するネットワークインフラストラクチャ図を取得します。</span><span class="sxs-lookup"><span data-stu-id="314ac-111">Second, obtain a network infrastructure diagram that displays the user locations and the available bandwidth to those locations.</span></span> <span data-ttu-id="314ac-112">3番目に、ユーザーが場所の間を移動するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="314ac-112">Third, find out if users travel between locations.</span></span> <span data-ttu-id="314ac-113">ユーザーが移動した場合、サーバーインフラストラクチャとイメージリポジトリの設計では、追加の容量が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="314ac-113">If users travel, additional capacity may be required in the design of the server infrastructure and image repositories.</span></span>

## <span data-ttu-id="314ac-114">MED-V で管理する MED-V イメージを決定する</span><span class="sxs-lookup"><span data-stu-id="314ac-114">Determine the MED-V Images to Be Managed by MED-V</span></span>


<span data-ttu-id="314ac-115">MED-V のエンドユーザーを定義した後、各場所のユーザーに対して MED-V によって管理される Vm を決定します。</span><span class="sxs-lookup"><span data-stu-id="314ac-115">After the MED-V end users have been defined, determine which VMs will be managed by MED-V for the users in each location.</span></span>

<span data-ttu-id="314ac-116">Vm が1つの一元ライブラリに格納されている場合は、MED-V リポジトリとして使用するために評価されるように、ライブラリの場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="314ac-116">If any of the VMs are stored in a centralized library, determine the location of the library so that it may be evaluated for use as a MED-V repository.</span></span>

## <a href="" id="determine-the-organization-s-service-level-expectations"></a><span data-ttu-id="314ac-117">組織のサービスレベルの期待を決定する</span><span class="sxs-lookup"><span data-stu-id="314ac-117">Determine the Organization’s Service Level Expectations</span></span>


<span data-ttu-id="314ac-118">各 MED-V ワークスペースに対して、新しい画像が読み込まれるまでの許容時間と、重要な更新プログラムを展開する期間を記録します。</span><span class="sxs-lookup"><span data-stu-id="314ac-118">For each MED-V workspace, note the acceptable time for a new image to load and the timeframe for critical updates to be deployed.</span></span>

<span data-ttu-id="314ac-119">必要に応じて、サーバーインフラストラクチャの設計で使用するために、MED-V レポートのサービスレベルの期待値を記録します。</span><span class="sxs-lookup"><span data-stu-id="314ac-119">If applicable, record the service level expectations for MED-V reporting, to be used in the design of the server infrastructure.</span></span>

## <span data-ttu-id="314ac-120">ビジネスで検証する</span><span class="sxs-lookup"><span data-stu-id="314ac-120">Validate with the Business</span></span>


<span data-ttu-id="314ac-121">ビジネス関係者とアプリケーション所有者に次の質問をしてください。</span><span class="sxs-lookup"><span data-stu-id="314ac-121">Ask business stakeholders and application owners the following questions:</span></span>

-   <span data-ttu-id="314ac-122">組み合わせることができる既存の画像はありますか?</span><span class="sxs-lookup"><span data-stu-id="314ac-122">Are there any existing images that can be combined?</span></span> <span data-ttu-id="314ac-123">たとえば、WindowsXP 上のアプリケーション A が 1 VPC 画像であり、WindowsXP 上のアプリケーション B が VPC イメージを使用している場合、1つの画像に両方のアプリケーションを含めることができるため、イメージのダウンロードに必要なリポジトリスペースと帯域幅を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="314ac-123">For example, if application A on WindowsXP is one VPC image and application B on WindowsXP is another VPC image, perhaps a single image can contain both applications, thereby reducing repository space and bandwidth required for image download.</span></span>

-   <span data-ttu-id="314ac-124">MED-V によって VM に配信された場合、スコープ内のアプリケーションは則りと対応していますか?</span><span class="sxs-lookup"><span data-stu-id="314ac-124">Are the in-scope applications licensable and supportable if delivered in a VM by MED-V?</span></span> <span data-ttu-id="314ac-125">アプリケーションの提供元に連絡して、MED-V でアプリケーションを実行することによってライセンスとサポートの規約に違反しないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="314ac-125">Check with the application supplier to ensure that licensing and support terms will not be violated by delivering the application through MED-V.</span></span>

 

 





