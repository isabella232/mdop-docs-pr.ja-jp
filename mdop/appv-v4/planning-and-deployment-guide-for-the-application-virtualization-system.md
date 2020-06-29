---
title: Application Virtualization システムの計画と展開ガイド
description: Application Virtualization システムの計画と展開ガイド
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815957"
---
# <span data-ttu-id="e9524-103">Application Virtualization システムの計画と展開ガイド</span><span class="sxs-lookup"><span data-stu-id="e9524-103">Planning and Deployment Guide for the Application Virtualization System</span></span>


<span data-ttu-id="e9524-104">Microsoft Application Virtualization Management は、アプリケーションをコンピューターに直接インストールしなくても、エンドユーザーのコンピューターでアプリケーションを利用できるようにする機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="e9524-104">Microsoft Application Virtualization Management provides the capability to make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="e9524-105">これは、*アプリケーションの順序*付けと呼ばれるプロセスによって可能になります。これにより、各アプリケーションは、クライアントコンピューター上の独立した仮想環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="e9524-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="e9524-106">シーケンス処理されたアプリケーションは、アプリケーションの競合を排除し、クライアントコンピューターを操作することができます。</span><span class="sxs-lookup"><span data-stu-id="e9524-106">The sequenced applications are isolated from one another, eliminating application conflicts, yet can still interact with the client computer.</span></span>

<span data-ttu-id="e9524-107">Application Virtualization クライアントは、エンドユーザーがコンピューターに公開された後にアプリケーションを操作できるようにする Application Virtualization システムコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="e9524-107">The Application Virtualization Client is the Application Virtualization system component that enables the end user to interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="e9524-108">クライアントは、仮想化されたアプリケーションが各コンピューターで実行される仮想環境を管理します。</span><span class="sxs-lookup"><span data-stu-id="e9524-108">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="e9524-109">クライアントがコンピューターにインストールされた後、アプリケーションは*発行*と呼ばれるプロセスによってコンピューターから利用できるようにする必要があります。これにより、エンドユーザーは仮想アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9524-109">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="e9524-110">公開プロセスでは、仮想アプリケーションのアイコンとショートカットがコンピューター (通常は Windows デスクトップまたは [**スタート**] メニュー) に配置され、パッケージ定義とファイルの種類の関連付け情報がコンピューターに配置されます。</span><span class="sxs-lookup"><span data-stu-id="e9524-110">The publishing process places the virtual application icons and shortcuts on the computer—typically on the Windows desktop or on the **Start** menu—and also places the package definition and file type association information on the computer.</span></span> <span data-ttu-id="e9524-111">公開すると、エンドユーザーのコンピューターでもアプリケーションパッケージのコンテンツを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e9524-111">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="e9524-112">仮想アプリケーションパッケージのコンテンツは、1つまたは複数の Application Virtualization サーバーに配置できます。これにより、オンデマンドでクライアントにストリーミングしてローカルにキャッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="e9524-112">The virtual application package content can be placed on one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="e9524-113">ファイルサーバーと Web サーバーをストリーミングサーバーとして使用することも、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布システムを使用している場合など、エンドユーザーのコンピューターに直接配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="e9524-113">File servers and Web servers can also be used as streaming servers, or the content can be placed directly on the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="e9524-114">複数サーバーの実装では、すべてのストリーミングサーバーでパッケージコンテンツを保持し、最新の状態に維持するには、包括的なパッケージ管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="e9524-114">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="e9524-115">組織の規模によっては、世界中のエンドユーザーが使用できる仮想アプリケーションが数多く必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e9524-115">Depending on the size of your organization, you might need to have many virtual applications accessible to end users located all over the world.</span></span> <span data-ttu-id="e9524-116">パッケージを管理して、すべてのユーザーが適切なアプリケーションを使用できるようにするには、そのような要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="e9524-116">Managing the packages to ensure that the right applications are available to all users where and when they need access to them is therefore an essential requirement.</span></span>

<span data-ttu-id="e9524-117">「アプリケーション仮想化計画と展開ガイド」では、Microsoft Application Virtualization アプリケーションとそのコンポーネントの理解と展開を強化するために役立つ情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="e9524-117">The Application Virtualization Planning and Deployment Guide provides information to help you better understand and deploy the Microsoft Application Virtualization application and its components.</span></span> <span data-ttu-id="e9524-118">また、主要な展開シナリオを実装するためのステップバイステップの手順も示します。</span><span class="sxs-lookup"><span data-stu-id="e9524-118">It also provides step-by-step procedures for implementing the key deployment scenarios.</span></span>

## <span data-ttu-id="e9524-119">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="e9524-119">In This Section</span></span>


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[<span data-ttu-id="e9524-120">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="e9524-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)  
<span data-ttu-id="e9524-121">アプリケーションの仮想化システムの実装と展開を計画するために必要なガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="e9524-121">Provides the guidance necessary to plan the implementation and deployment of your Application Virtualization system.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[<span data-ttu-id="e9524-122">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e9524-122">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)  
<span data-ttu-id="e9524-123">さまざまなアプリケーションの仮想化コンポーネントとアップグレード情報をインストールするためのハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9524-123">Provides information about hardware and software requirements for installing the various Application Virtualization components, as well as upgrade information.</span></span>

<a href="" id="electronic-software-distribution-based-scenario"></a>[<span data-ttu-id="e9524-124">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="e9524-124">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)  
<span data-ttu-id="e9524-125">電子ソフトウェア配布 (ESD) システムを使用したアプリケーションの仮想化の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9524-125">Provides information about deploying Application Virtualization using an electronic software distribution (ESD) system.</span></span>

<a href="" id="application-virtualization-server-based-scenario"></a>[<span data-ttu-id="e9524-126">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="e9524-126">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)  
<span data-ttu-id="e9524-127">Application Virtualization Management Server を使用したアプリケーションの仮想化の展開について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9524-127">Provides information about deploying Application Virtualization using the Application Virtualization Management Server.</span></span>

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[<span data-ttu-id="e9524-128">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="e9524-128">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
<span data-ttu-id="e9524-129">ESD またはサーバーベースのリソースを使わずに、スタンドアロンモードでアプリケーションの仮想化を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e9524-129">Describes how to deploy Application Virtualization in a stand-alone mode, without the use of ESD or server-based resources.</span></span>

<a href="" id="application-virtualization-reference"></a>[<span data-ttu-id="e9524-130">Application Virtualization リファレンス</span><span class="sxs-lookup"><span data-stu-id="e9524-130">Application Virtualization Reference</span></span>](application-virtualization-reference.md)  
<span data-ttu-id="e9524-131">システムコンポーネントのインストールと管理に関連する詳細な技術参考資料が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e9524-131">Contains detailed technical reference material related to installing and managing system components.</span></span>

 

 





