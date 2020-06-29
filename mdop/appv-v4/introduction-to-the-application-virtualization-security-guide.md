---
title: Application Virtualization セキュリティガイドの概要
description: Application Virtualization セキュリティガイドの概要
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816267"
---
# <span data-ttu-id="a2049-103">Application Virtualization セキュリティガイドの概要</span><span class="sxs-lookup"><span data-stu-id="a2049-103">Introduction to the Application Virtualization Security Guide</span></span>


<span data-ttu-id="a2049-104">この Microsoft Application Virtualization (App-v) セキュリティガイドには、App-v の展開用に選択されたセキュリティ機能の構成を担当する管理者向けの手順が記載されています。</span><span class="sxs-lookup"><span data-stu-id="a2049-104">This Microsoft Application Virtualization (App-V) security guide provides instructions for administrators who are responsible for configuring the security features that were selected for the App-V deployment.</span></span>

<span data-ttu-id="a2049-105">**注** このドキュメントでは、特定のセキュリティオプションを選ぶためのガイダンスは提供していません。</span><span class="sxs-lookup"><span data-stu-id="a2049-105">**Note** This documentation does not provide guidance for choosing the specific security options.</span></span> <span data-ttu-id="a2049-106">この情報については、「App V セキュリティのベストプラクティス」をご覧 <https://go.microsoft.com/fwlink/?LinkId=127120> ください。</span><span class="sxs-lookup"><span data-stu-id="a2049-106">That information is provided in the App-V Security Best Practices white paper available at <https://go.microsoft.com/fwlink/?LinkId=127120>.</span></span>

 

<span data-ttu-id="a2049-107">このガイドを使用する App-v 管理者として、次のセキュリティ関連テクノロジに精通している必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2049-107">As an App-V administrator using this guide, you should be familiar with the following security-related technologies:</span></span>

-   <span data-ttu-id="a2049-108">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="a2049-108">Active Directory Domain Services</span></span>

-   <span data-ttu-id="a2049-109">公開キー基盤 (PKI)</span><span class="sxs-lookup"><span data-stu-id="a2049-109">Public key infrastructure (PKI)</span></span>

-   <span data-ttu-id="a2049-110">インターネットプロトコルセキュリティ (IPsec)</span><span class="sxs-lookup"><span data-stu-id="a2049-110">Internet Protocol Security (IPsec)</span></span>

-   <span data-ttu-id="a2049-111">グループポリシー</span><span class="sxs-lookup"><span data-stu-id="a2049-111">Group Policies</span></span>

-   <span data-ttu-id="a2049-112">インターネットインフォメーションサービス (IIS)</span><span class="sxs-lookup"><span data-stu-id="a2049-112">Internet Information Services (IIS)</span></span>

## <span data-ttu-id="a2049-113">APP-V インフラストラクチャコンポーネント</span><span class="sxs-lookup"><span data-stu-id="a2049-113">APP-V Infrastructure Components</span></span>


<span data-ttu-id="a2049-114">セキュリティで保護されたアプリを拡張する環境を計画するときは、いくつかの異なるインフラストラクチャモデルを検討することができます。</span><span class="sxs-lookup"><span data-stu-id="a2049-114">When planning an enhanced security App-V environment, you can consider several different infrastructure models.</span></span>

<span data-ttu-id="a2049-115">**注** App-v インフラストラクチャモデルの詳細については、次のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2049-115">**Note** For more information about App-V infrastructure models, see the following documentation:</span></span>

-   [<span data-ttu-id="a2049-116">App-v の計画と展開ガイド</span><span class="sxs-lookup"><span data-stu-id="a2049-116">App-V Planning and Deployment Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [<span data-ttu-id="a2049-117">インフラストラクチャ計画と設計ガイドシリーズ</span><span class="sxs-lookup"><span data-stu-id="a2049-117">Infrastructure Planning and Design Guide Series</span></span>](https://go.microsoft.com/fwlink/?LinkId=151986)

 

<span data-ttu-id="a2049-118">これらのモデルでは、次の図に示すように、一部の App-v コンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2049-118">These models utilize some but possibly not all of the App-V components depicted in the following illustration.</span></span>

![app-v ブランチオフィスダイアグラム](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a><span data-ttu-id="a2049-120">Application Virtualization (App V) Management Server</span><span class="sxs-lookup"><span data-stu-id="a2049-120">Application Virtualization (App-V) Management Server</span></span>  
<span data-ttu-id="a2049-121">App-v 管理サーバーは、パッケージコンテンツをストリームし、ショートカットとファイルの種類の関連付けを App-v クライアントに公開します。</span><span class="sxs-lookup"><span data-stu-id="a2049-121">The App-V Management Server streams the package content and publishes the shortcuts and file-type associations to the App-V Client.</span></span> <span data-ttu-id="a2049-122">App-v 管理サーバーでは、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースもサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a2049-122">The App-V Management Server also supports active upgrade, license management, and a database that can be used for reporting.</span></span>

<a href="" id="application-virtualization--app-v--streaming-server"></a><span data-ttu-id="a2049-123">Application Virtualization (App-v) Streaming Server</span><span class="sxs-lookup"><span data-stu-id="a2049-123">Application Virtualization (App-V) Streaming Server</span></span>  
<span data-ttu-id="a2049-124">App-v ストリーミングサーバーは、ブランチオフィスなどの環境で、app-v クライアントにストリーミングするためのパッケージをホストします。これは、パッケージコンテンツをクライアントにストリーミング配信するための帯域幅が十分でない場合です。</span><span class="sxs-lookup"><span data-stu-id="a2049-124">The App-V Streaming Server hosts the packages for streaming to App-V Clients in environments such as branch offices, where the bandwidth of the connection to the App-V Management Server is insufficient for streaming package content to clients.</span></span> <span data-ttu-id="a2049-125">ストリーミングサーバーにはストリーミング機能のみが含まれており、App-v の管理コンソールまたは App-v の管理 Web サービスを利用することはできません。</span><span class="sxs-lookup"><span data-stu-id="a2049-125">The Streaming Server contains only streaming functionality and does not provide you with the App-V Management Console or the App-V Management Web Service.</span></span>

<a href="" id="application-virtualization--app-v--data-store"></a><span data-ttu-id="a2049-126">Application Virtualization (App-v) データストア</span><span class="sxs-lookup"><span data-stu-id="a2049-126">Application Virtualization (App-V) Data Store</span></span>  
<span data-ttu-id="a2049-127">SQL データベースの App-v データストアは、App-v インフラストラクチャに関連する情報を保持します。</span><span class="sxs-lookup"><span data-stu-id="a2049-127">The App-V data store, in the SQL database, retains information related to the App-V infrastructure.</span></span> <span data-ttu-id="a2049-128">App-v データストアの情報には、すべてのアプリケーションレコード、アプリケーションの割り当て、およびアプリケーションの仮想化環境を管理するグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a2049-128">The information in the App-V data store includes all application records, application assignments, and which groups manage the Application Virtualization environment.</span></span>

<a href="" id="application-virtualization--app-v--management-service"></a><span data-ttu-id="a2049-129">Application Virtualization (App-v) 管理サービス</span><span class="sxs-lookup"><span data-stu-id="a2049-129">Application Virtualization (App-V) Management Service</span></span>  
<span data-ttu-id="a2049-130">App-v 管理サービスは、読み取り/書き込み要求をアプリケーションの仮想化データストアに伝達します。</span><span class="sxs-lookup"><span data-stu-id="a2049-130">The App-V Management Service communicates read/write requests to the Application Virtualization data store.</span></span> <span data-ttu-id="a2049-131">このコンポーネントは、App-v Management Server と同じコンピューター、または IIS がインストールされている別のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a2049-131">This component can be installed on the same computer as the App-V Management Server or on a separate computer with IIS installed.</span></span>

<a href="" id="application-virtualization--app-v--management-console"></a><span data-ttu-id="a2049-132">Application Virtualization (App V) 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="a2049-132">Application Virtualization (App-V) Management Console</span></span>  
<span data-ttu-id="a2049-133">App-v 管理コンソールは、app-v Server 管理のスナップイン管理ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="a2049-133">The App-V Management Console is a snap-in management utility for App-V Server administration.</span></span> <span data-ttu-id="a2049-134">このコンポーネントは、App-v Server と同じコンピューター上にインストールすることも、MMC 3.0 との別のワークステーションにインストールすることもできます。NET 2.0 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="a2049-134">This component can be installed on the same computer as the App-V Server or on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span>

<a href="" id="application-virtualization--app-v--sequencer"></a><span data-ttu-id="a2049-135">Application Virtualization (App-v) Sequencer</span><span class="sxs-lookup"><span data-stu-id="a2049-135">Application Virtualization (App-V) Sequencer</span></span>  
<span data-ttu-id="a2049-136">App-v Sequencer は、アプリケーションのインストールを監視してキャプチャし、仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a2049-136">The App-V Sequencer monitors and captures the installation of applications and creates virtual application packages.</span></span> <span data-ttu-id="a2049-137">Sequencer の出力は、アプリケーションアイコン、アプリケーション定義情報を含む OSD ファイル、パッケージマニフェストファイル、およびアプリケーションのコンテンツファイルを含む SFT ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a2049-137">The output of the Sequencer consists of the application icon, the OSD file containing application definition information, a package manifest file, and an SFT file containing the application’s content files.</span></span> <span data-ttu-id="a2049-138">必要に応じて、App-v インフラストラクチャを使わずに、パッケージをインストールするための Windows Installer ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="a2049-138">Optionally, a Windows Installer file can be created for installing the package without using the App-V infrastructure.</span></span>

<a href="" id="application-virtualization--app-v--client"></a><span data-ttu-id="a2049-139">Application Virtualization (App-v) クライアント</span><span class="sxs-lookup"><span data-stu-id="a2049-139">Application Virtualization (App-V) Client</span></span>  
<span data-ttu-id="a2049-140">App-v クライアントは、app-v デスクトップクライアントコンピューターまたは App-v ターミナルサービスクライアントコンピューターにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="a2049-140">The App-V Client is installed on the App-V Desktop Client computer or on the App-V Terminal Services Client computer.</span></span> <span data-ttu-id="a2049-141">仮想アプリケーションパッケージの仮想環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="a2049-141">It provides the virtual environment for the virtual application packages.</span></span> <span data-ttu-id="a2049-142">App-v クライアントは、アプリへのパッケージストリーミング、仮想アプリケーション発行の更新、アプリケーション仮想化サーバーとの操作を管理します。</span><span class="sxs-lookup"><span data-stu-id="a2049-142">The App-V Client manages the package streaming to the cache, virtual application publishing refresh, and interaction with the Application Virtualization Servers.</span></span>

 

 





