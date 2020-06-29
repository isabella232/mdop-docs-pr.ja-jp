---
title: MBAM 1.0 のアーキテクチャの概要
description: MBAM 1.0 のアーキテクチャの概要
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825237"
---
# <span data-ttu-id="b058c-103">MBAM 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="b058c-103">High Level Architecture for MBAM 1.0</span></span>


<span data-ttu-id="b058c-104">Microsoft BitLocker の管理と監視 (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker のコンプライアンスとレポートを向上させ、サポートのコストを削減するために役立つクライアント/サーバーデータ暗号化ソリューションです。</span><span class="sxs-lookup"><span data-stu-id="b058c-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server data encryption solution that can help you simplify BitLocker provisioning and deployment, improve BitLocker compliance and reporting, and reduce support costs.</span></span> <span data-ttu-id="b058c-105">MBAM には、このトピックで説明されている機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="b058c-105">MBAM includes the features that are described in this topic.</span></span>

<span data-ttu-id="b058c-106">また、MBAM アーキテクチャと MBAM セットアップの概要を示すビデオも用意されています。</span><span class="sxs-lookup"><span data-stu-id="b058c-106">Additionally, there is a video that provides an overview of the MBAM architecture and MBAM Setup.</span></span> <span data-ttu-id="b058c-107">詳細については、「 [Mbam 展開とアーキテクチャの概要](https://go.microsoft.com/fwlink/p/?LinkId=258392)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b058c-107">For more information, see [MBAM Deployment and Architecture Overview](https://go.microsoft.com/fwlink/p/?LinkId=258392).</span></span>

## <span data-ttu-id="b058c-108">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="b058c-108">Architecture Overview</span></span>


<span data-ttu-id="b058c-109">次の図は、MBAM アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="b058c-109">The following diagram displays the MBAM architecture.</span></span> <span data-ttu-id="b058c-110">MBAM 機能の紹介については、シングルサーバーの MBAM 展開トポロジを示します。</span><span class="sxs-lookup"><span data-stu-id="b058c-110">The single-server MBAM deployment topology is shown to introduce the MBAM features.</span></span> <span data-ttu-id="b058c-111">ただし、この MBAM 展開トポロジは、ラボ環境でのみ推奨されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-111">However, this MBAM deployment topology is recommended only for lab environments.</span></span>

<span data-ttu-id="b058c-112">**注** 運用展開では、少なくとも3台のコンピューターからインストールされた MBAM 展開トポロジをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b058c-112">**Note** At least a three-computer MBAM deployment topology is recommended for a production deployment.</span></span> <span data-ttu-id="b058c-113">MBAM 展開トポロジの詳細については、「 [mbam 1.0 サーバーインフラストラクチャの展開](deploying-the-mbam-10-server-infrastructure.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b058c-113">For more information about MBAM deployment topologies, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

![mbam single server deployment トポロジ](images/mbam-1-server.jpg)

1.  <span data-ttu-id="b058c-115">**管理と監視サーバー**。</span><span class="sxs-lookup"><span data-stu-id="b058c-115">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="b058c-116">MBAM 管理と監視サーバーは Windows サーバーにインストールされ、MBAM 管理および管理 web サイトと監視 web サービスをホストします。</span><span class="sxs-lookup"><span data-stu-id="b058c-116">The MBAM Administration and Monitoring Server is installed on a Windows server and hosts the MBAM Administration and Management website and the monitoring web services.</span></span> <span data-ttu-id="b058c-117">MBAM 管理および管理 web サイトは、エンタープライズのコンプライアンス状態の決定、アクティビティの監査、ハードウェア機能の管理、回復データ (BitLocker 回復キーなど) へのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-117">The MBAM Administration and Management website is used to determine enterprise compliance status, to audit activity, to manage hardware capability, and to access recovery data, such as the BitLocker recovery keys.</span></span> <span data-ttu-id="b058c-118">管理および監視サーバーは、次のデータベースとサービスに接続します。</span><span class="sxs-lookup"><span data-stu-id="b058c-118">The Administration and Monitoring Server connects to the following databases and services:</span></span>

    -   <span data-ttu-id="b058c-119">回復とハードウェアデータベース。</span><span class="sxs-lookup"><span data-stu-id="b058c-119">Recovery and Hardware Database.</span></span> <span data-ttu-id="b058c-120">回復とハードウェアのデータベースは、Windows ベースのサーバーとサポートされている SQLServer インスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b058c-120">The Recovery and Hardware database is installed on a Windows-based server and supported SQLServer instance.</span></span> <span data-ttu-id="b058c-121">このデータベースには、MBAM クライアントコンピューターから収集された回復データとハードウェア情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-121">This database stores recovery data and hardware information that is collected from MBAM client computers.</span></span>

    -   <span data-ttu-id="b058c-122">コンプライアンスと監査データベース。</span><span class="sxs-lookup"><span data-stu-id="b058c-122">Compliance and Audit Database.</span></span> <span data-ttu-id="b058c-123">コンプライアンスと監査データベースは、Windows server とサポートされている SQLServer インスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b058c-123">The Compliance and Audit Database is installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="b058c-124">このデータベースには、MBAM クライアントコンピューターのコンプライアンスデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-124">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="b058c-125">このデータは、主に SQL Server Reporting Services (SSRS) でホストされているレポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-125">This data is used primarily for reports that are hosted by SQL Server Reporting Services (SSRS).</span></span>

    -   <span data-ttu-id="b058c-126">コンプライアンスおよび監査レポート。</span><span class="sxs-lookup"><span data-stu-id="b058c-126">Compliance and Audit Reports.</span></span> <span data-ttu-id="b058c-127">コンプライアンスと監査レポートは、Windows ベースのサーバーにインストールされ、SSRS 機能がインストールされている SQLServer インスタンスでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b058c-127">The Compliance and Audit Reports are installed on a Windows-based server and supported SQLServer instance that has the SSRS feature installed.</span></span> <span data-ttu-id="b058c-128">これらのレポートでは、Microsoft BitLocker の管理と監視のレポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-128">These reports provide Microsoft BitLocker Administration and Monitoring reports.</span></span> <span data-ttu-id="b058c-129">これらのレポートには、MBAM 管理および管理 web サイトから、または SSRS サーバーから直接アクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b058c-129">These reports can be accessed from the MBAM Administration and Management website or directly from the SSRS Server.</span></span>

2.  <span data-ttu-id="b058c-130">**Mbam クライアント**。</span><span class="sxs-lookup"><span data-stu-id="b058c-130">**MBAM Client**.</span></span> <span data-ttu-id="b058c-131">Microsoft BitLocker 管理および監視クライアントは、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="b058c-131">The Microsoft BitLocker Administration and Monitoring Client performs the following tasks:</span></span>

    -   <span data-ttu-id="b058c-132">グループポリシーを使用して、企業内のクライアントコンピューターの BitLocker 暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="b058c-132">Uses Group Policy to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

    -   <span data-ttu-id="b058c-133">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="b058c-133">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

    -   <span data-ttu-id="b058c-134">クライアントコンピューターに関する回復情報とハードウェア情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="b058c-134">Collects recovery information and hardware information about the client computers.</span></span>

    -   <span data-ttu-id="b058c-135">コンピューターのコンプライアンスデータを収集し、データをレポートシステムに渡します。</span><span class="sxs-lookup"><span data-stu-id="b058c-135">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

3.  <span data-ttu-id="b058c-136">**ポリシーテンプレート**。</span><span class="sxs-lookup"><span data-stu-id="b058c-136">**Policy Template**.</span></span> <span data-ttu-id="b058c-137">MBAM グループポリシーテンプレートは、サポートされている Windows ベースのサーバーまたはクライアントコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="b058c-137">The MBAM Group Policy template is installed on a supported Windows-based server or client computer.</span></span> <span data-ttu-id="b058c-138">このテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を指定するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b058c-138">This template is used to specify the MBAM implementation settings for BitLocker drive encryption.</span></span>

## <span data-ttu-id="b058c-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b058c-139">Related topics</span></span>


[<span data-ttu-id="b058c-140">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="b058c-140">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)

 

 





