---
title: 電子ソフトウェア配布ベースのシナリオ
description: 電子ソフトウェア配布ベースのシナリオ
author: dansimp
ms.assetid: 18be0f8d-60ee-449b-aa83-93c86d1a908e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 52b9a30f2b1d403ec41090252f331a984225fd19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821594"
---
# <span data-ttu-id="39e58-103">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="39e58-103">Electronic Software Distribution-Based Scenario</span></span>


<span data-ttu-id="39e58-104">Microsoft Application Virtualization 環境で電子ソフトウェア配布 (ESD) 展開シナリオを使用することを計画している場合は、その決定によって影響を受ける要因について理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="39e58-104">If you plan to use an electronic software distribution (ESD) deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="39e58-105">このセクションのトピックでは、ESD シナリオについて説明し、展開戦略で考慮する必要があるパッケージ配信方法、伝送プロトコル、外部コンポーネントについての情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="39e58-105">The topics in this section describe the ESD scenario and provide information about package delivery methods, transmission protocols, and external components that you will need to consider in your deployment strategy.</span></span> <span data-ttu-id="39e58-106">このセクションの手順を使用して展開を完了することもできます。これは、サーバー構成フェーズから展開確認フェーズを通じて行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="39e58-106">You can also use the procedures in this section to complete your deployment, from the server configuration phase through the deployment verification phase.</span></span>

## <span data-ttu-id="39e58-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="39e58-107">In This Section</span></span>


<a href="" id="electronic-software-distribution-based-scenario-overview"></a>[<span data-ttu-id="39e58-108">電子ソフトウェア配布ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="39e58-108">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)  
<span data-ttu-id="39e58-109">ESD ベースの展開に使用できる発行とストリーミングの方法についての重要な情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="39e58-109">Provides important information about the publishing and streaming methods you can use for an ESD-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-esd-based-deployment"></a>[<span data-ttu-id="39e58-110">ESD ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="39e58-110">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)  
<span data-ttu-id="39e58-111">このセクションでは、アプリケーションの仮想化ストリーミングサーバー、IIS サーバー、および電子ソフトウェア配布ベースの展開戦略用のファイルサーバーを構成するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="39e58-111">This section provides procedures you can use to configure the Application Virtualization Streaming Servers, the IIS server, and the file server for your electronic software distribution–based deployment strategy.</span></span>

<a href="" id="how-to-install-the-client-by-using-the-command-line"></a>[<span data-ttu-id="39e58-112">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="39e58-112">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)  
<span data-ttu-id="39e58-113">setup.exe または setup.msi ファイルのいずれかを使用して、Application Virtualization クライアントをインストールするためのコマンドラインの手順を示します。</span><span class="sxs-lookup"><span data-stu-id="39e58-113">Provides command-line procedures for installing the Application Virtualization Client, using either the setup.exe or the setup.msi file.</span></span>

<a href="" id="how-to-uninstall-the-app-v-client"></a>[<span data-ttu-id="39e58-114">App-V Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="39e58-114">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)  
<span data-ttu-id="39e58-115">アプリケーションの仮想化クライアントがインストールされていて、正常に機能していることを確認するためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="39e58-115">Provides a step-by-step procedure you can use to confirm that the Application Virtualization Client has been installed and is functioning correctly.</span></span>

<a href="" id="how-to-publish-a-virtual-application-on-the-client"></a>[<span data-ttu-id="39e58-116">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="39e58-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)  
<span data-ttu-id="39e58-117">Windows Installer または SFTMIME を使用して、アプリケーションパッケージを公開するためのコマンドライン手順を示します。</span><span class="sxs-lookup"><span data-stu-id="39e58-117">Provides command-line procedures for publishing an application package, using either Windows Installer or SFTMIME.</span></span>

## <span data-ttu-id="39e58-118">リファレンス</span><span class="sxs-lookup"><span data-stu-id="39e58-118">Reference</span></span>


[<span data-ttu-id="39e58-119">Application Virtualization Client インストーラーのコマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="39e58-119">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="39e58-120">関連セクション</span><span class="sxs-lookup"><span data-stu-id="39e58-120">Related Sections</span></span>


[<span data-ttu-id="39e58-121">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="39e58-121">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

## <span data-ttu-id="39e58-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39e58-122">Related topics</span></span>


[<span data-ttu-id="39e58-123">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="39e58-123">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="39e58-124">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="39e58-124">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





