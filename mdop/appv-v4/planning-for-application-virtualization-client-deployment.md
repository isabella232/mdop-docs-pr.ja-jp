---
title: Application Virtualization Client の展開計画
description: Application Virtualization Client の展開計画
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815954"
---
# <span data-ttu-id="9bcff-103">Application Virtualization Client の展開計画</span><span class="sxs-lookup"><span data-stu-id="9bcff-103">Planning for Application Virtualization Client Deployment</span></span>


<span data-ttu-id="9bcff-104">仮想アプリケーションパッケージを公開してエンドユーザーのコンピューターに展開する方法を決定したら、Application Virtualization クライアントソフトウェアの展開を計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-104">After you have decided how you will publish and deploy virtual application packages to your end user computers, you should plan the deployment of the Application Virtualization Client software.</span></span>

<span data-ttu-id="9bcff-105">アプリケーションの仮想化クライアントは、実際に仮想アプリケーションを実行するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="9bcff-105">The Application Virtualization Client is the component that actually runs the virtual applications.</span></span> <span data-ttu-id="9bcff-106">Application Virtualization クライアントを使うと、ユーザーはアイコンを操作したり、ファイルの種類をダブルクリックして仮想アプリケーションを開始したりできます。</span><span class="sxs-lookup"><span data-stu-id="9bcff-106">The Application Virtualization Client enables users to interact with icons and to double-click file types to start a virtual application.</span></span> <span data-ttu-id="9bcff-107">また、ストリーミングサーバーからのアプリケーションコンテンツのストリーミングを処理し、アプリケーションを起動する前にキャッシュします。</span><span class="sxs-lookup"><span data-stu-id="9bcff-107">It also handles streaming of the application content from a streaming server and caches it before starting the application.</span></span> <span data-ttu-id="9bcff-108">アプリケーションのコンテンツは、アプリケーションを起動するために必要なすべてのコンテンツと、最初のユーザーの操作を処理するために、エンドユーザーのコンピューターにストリーミングされるように構成されています。</span><span class="sxs-lookup"><span data-stu-id="9bcff-108">The application content is structured such that all the content needed to start the application and handle initial user interaction is streamed to the end user computer first.</span></span> <span data-ttu-id="9bcff-109">Application Virtualization クライアントソフトウェアには、リモートデスクトップサービス (RDSession Host) サーバーシステムで使用される application Virtualization クライアントと、その他のすべてのコンピューターで使用される Application Virtualization Desktop Client という2種類の種類のアプリケーションがあります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-109">There are two different types of Application Virtualization Client software: the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services), which is used on Remote Desktop Session Host (RDSession Host) server systems, and the Application Virtualization Desktop Client, which is used for all other computers.</span></span>

<span data-ttu-id="9bcff-110">アプリケーションの仮想化クライアントは、アプリケーションの仮想化管理コンソールまたはインストーラーのコマンドラインで、次のようないくつかの重要な設定を含む、インストール時に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-110">The Application Virtualization Client should be configured at installation time, either in the Application Virtualization Management Console or via the installer command line, with a number of important settings, including the following:</span></span>

-   <span data-ttu-id="9bcff-111">すべてのアプリケーションのアイコンの場所。</span><span class="sxs-lookup"><span data-stu-id="9bcff-111">Locations of the icons for all the applications.</span></span>

-   <span data-ttu-id="9bcff-112">パッケージ定義情報を含む OSD ファイルの場所。</span><span class="sxs-lookup"><span data-stu-id="9bcff-112">The location of the OSD file that contains the package definition information.</span></span>

-   <span data-ttu-id="9bcff-113">アプリケーションのコンテンツソース。</span><span class="sxs-lookup"><span data-stu-id="9bcff-113">The application content source.</span></span>

-   <span data-ttu-id="9bcff-114">上記の項目を取得するときに使用する通信プロトコル。</span><span class="sxs-lookup"><span data-stu-id="9bcff-114">The communications protocol to be used when retrieving the preceding items.</span></span>

-   <span data-ttu-id="9bcff-115">使用するキャッシュサイズとキャッシュサイズの管理方法。</span><span class="sxs-lookup"><span data-stu-id="9bcff-115">The cache size and cache size management method to be used.</span></span>

<span data-ttu-id="9bcff-116">電子ソフトウェア配布 (ESD) ソリューションを使用するときに、Application Virtualization クライアントソフトウェアの展開を迅速化するには、前の設定を慎重に定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-116">To expedite the deployment of the Application Virtualization Client software when using an electronic software distribution (ESD) solution, the preceding settings must be defined carefully in advance.</span></span> <span data-ttu-id="9bcff-117">これは、さまざまな場所にあるコンピューターを使用している場合に、クライアントが異なるソースの場所を使用するように構成する必要がある場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="9bcff-117">This is especially important when you have computers in different offices, where their clients would need to be configured to use different source locations.</span></span>

**<span data-ttu-id="9bcff-118">注</span><span class="sxs-lookup"><span data-stu-id="9bcff-118">Note</span></span>**  
-   <span data-ttu-id="9bcff-119">[Icon location] と [OSD file] の値は、Windows Installer または SFTMIME のどちらを使用するかにかかわらず、発行方法を選ぶ際に考慮すべき重要な要素です。</span><span class="sxs-lookup"><span data-stu-id="9bcff-119">The icon location and OSD file values are an important factor to consider when choosing your publishing method, whether using Windows Installer or SFTMIME.</span></span> <span data-ttu-id="9bcff-120">アプリケーションコンテンツソースの設定は、ストリーミングメソッドの選択によって定義されます。</span><span class="sxs-lookup"><span data-stu-id="9bcff-120">The setting for the application content source is defined by your choice of streaming method.</span></span>

-   <span data-ttu-id="9bcff-121">展開される可能性のあるすべてのパッケージに対して十分な領域がキャッシュに割り当てられるようにするには、必要に応じてキャッシュを拡大できるように、クライアントを構成するときに、[**空きディスク領域のしきい値を使用**する] 設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bcff-121">To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="9bcff-122">または、アプリの V キャッシュに必要なディスク容量を事前に確認して、インストール時にキャッシュサイズを適切に設定します。</span><span class="sxs-lookup"><span data-stu-id="9bcff-122">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span> <span data-ttu-id="9bcff-123">キャッシュスペース管理機能の詳細については、「Microsoft Application Virtualization (App-v) Operations Guide の**キャッシュスペース管理機能を使用する方法**」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bcff-123">For more information about the cache space management feature, see **How to Use the Cache Space Management Feature** in the Microsoft Application Virtualization (App-V) Operations Guide.</span></span>

-   <span data-ttu-id="9bcff-124">Publishing および HTTP (S) ストリーミング操作の両方で、App-v 4.5 SP1 クライアントは、ユーザーのコンピューターの Internet Explorer で構成されているプロキシサーバー設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="9bcff-124">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>

<span data-ttu-id="9bcff-125">クライアントのインストールパラメーターの構成の詳細については、「 [Application Virtualization クライアントインストーラーのコマンドラインパラメーター](application-virtualization-client-installer-command-line-parameters.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9bcff-125">For more information about configuring the client installation parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

 

<span data-ttu-id="9bcff-126">最後に、デスクトップクライアント用の Application Virtualization デスクトップクライアントソフトウェアの展開方法を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-126">Finally, you need to determine how to deploy the Application Virtualization Desktop Client software for the desktop clients.</span></span> <span data-ttu-id="9bcff-127">各コンピューターにアプリケーションの仮想化デスクトップクライアントを手動で展開することもできますが、ほとんどの組織では、いくつかの自動化されたプロセスを通じてこれを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-127">Although it is possible to deploy the Application Virtualization Desktop Client manually on each computer, most organizations would need to do this through some automated process.</span></span> <span data-ttu-id="9bcff-128">中規模または大規模の組織では、実行中の ESD システムがある場合があります。これは、クライアントを展開するのに最適な方法です。</span><span class="sxs-lookup"><span data-stu-id="9bcff-128">A medium or large organization might have an ESD system in operation, and that would be an ideal way to deploy the client.</span></span> <span data-ttu-id="9bcff-129">ESD システムが存在しない場合は、組織にソフトウェアをインストールするための標準的な方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="9bcff-129">If no ESD system exists, you can use your standard method of installing software in your organization.</span></span> <span data-ttu-id="9bcff-130">選択肢には、グループポリシーやさまざまなスクリプト手法があります。</span><span class="sxs-lookup"><span data-stu-id="9bcff-130">Choices include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="9bcff-131">使用しているオフィスの数とサイズによっては、この展開プロセスが複雑な場合があり、すべてのコンピューターが適切な構成でクライアントをインストールできるように、構造化されたアプローチを取ることが重要です。</span><span class="sxs-lookup"><span data-stu-id="9bcff-131">Depending on the number and size of the offices you have, this deployment process can be complex, and it is essential that you take a structured approach to ensure all computers get a client installed with the correct configuration.</span></span>

## <span data-ttu-id="9bcff-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9bcff-132">Related topics</span></span>


[<span data-ttu-id="9bcff-133">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="9bcff-133">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

[<span data-ttu-id="9bcff-134">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9bcff-134">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="9bcff-135">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="9bcff-135">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="9bcff-136">Application Virtualization Client をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="9bcff-136">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="9bcff-137">App-V Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="9bcff-137">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





