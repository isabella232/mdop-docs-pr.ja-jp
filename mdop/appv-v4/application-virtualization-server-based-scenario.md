---
title: Application Virtualization サーバー ベースのシナリオ
description: Application Virtualization サーバー ベースのシナリオ
author: dansimp
ms.assetid: 10ed0b18-087d-470f-951b-5083f4cb076f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6699bdc734258f67e4938e33266a2f061531939
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819527"
---
# <span data-ttu-id="86f79-103">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="86f79-103">Application Virtualization Server-Based Scenario</span></span>


<span data-ttu-id="86f79-104">Microsoft Application Virtualization (App-v) 環境でサーバーベースの展開シナリオを使用する予定がある場合は、Application Virtualization Management Server と Application Virtualization ストリーミングサーバーの違いについて理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="86f79-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization (App-V) environment, you should understand the differences between the Application Virtualization Management Server and the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="86f79-105">このセクションのトピックでは、これらの相違点について説明し、展開を続行するときに考慮する必要があるパッケージ配信方法、転送プロトコル、外部コンポーネントについても説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-105">The topics in this section describe those differences and also provide information about package delivery methods, transmission protocols, and external components that you have to consider as you continue with your deployment.</span></span> <span data-ttu-id="86f79-106">このセクションでは、App-v 管理サーバーと Application Virtualization ストリーミングサーバーをインストールして構成するためのステップバイステップの手順についても説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-106">This section also provides step-by-step procedures for installing and configuring the App-V Management Server and the Application Virtualization Streaming Servers.</span></span>

## <span data-ttu-id="86f79-107">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="86f79-107">In This Section</span></span>


<a href="" id="application-virtualization-server-based-scenario-overview"></a>[<span data-ttu-id="86f79-108">Application Virtualization サーバー ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="86f79-108">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)  
<span data-ttu-id="86f79-109">Application Virtualization Management Server、Application Virtualization Streaming Server、およびサーバーベースの展開計画に関連するパッケージ配信方法、プロトコル、外部コンポーネントに関する重要な展開情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="86f79-109">Provides important deployment information about the Application Virtualization Management Server, the Application Virtualization Streaming Server, and the package delivery methods, protocols, and external components relevant to your server-based deployment plan.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="86f79-110">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="86f79-110">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="86f79-111">サーバーベースの展開に必要な Microsoft Application Virtualization platform コンポーネントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-111">Describes how to install the Microsoft Application Virtualization platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-server-based-deployment"></a>[<span data-ttu-id="86f79-112">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="86f79-112">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)  
<span data-ttu-id="86f79-113">Application Virtualization Management Server、Application Virtualization Streaming Server、インターネット情報統合 (IIS) サーバー、およびファイルサーバーを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-113">Describes how to configure the Application Virtualization Management Server, the Application Virtualization Streaming Server, the Internet Information Integration (IIS) server, and the file server.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-"></a>[<span data-ttu-id="86f79-114">App-V Client の読み取り専用キャッシュを構成する方法 (VDI)</span><span class="sxs-lookup"><span data-stu-id="86f79-114">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-.md)  
<span data-ttu-id="86f79-115">読み取り専用キャッシュを使用するように App-v クライアントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-115">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--rds-"></a>[<span data-ttu-id="86f79-116">App-V Client の読み取り専用キャッシュを構成する方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="86f79-116">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--rds--sp1.md)  
<span data-ttu-id="86f79-117">読み取り専用キャッシュを使用するように App-v クライアントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-117">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v"></a>[<span data-ttu-id="86f79-118">App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="86f79-118">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)  
<span data-ttu-id="86f79-119">アプリ-V システムで Microsoft SQL Server を使用してデータベースミラーリングを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="86f79-119">Describes how to configure database mirroring by using Microsoft SQL Server for your App-V system.</span></span>

## <span data-ttu-id="86f79-120">リファレンス</span><span class="sxs-lookup"><span data-stu-id="86f79-120">Reference</span></span>


[<span data-ttu-id="86f79-121">Application Virtualization Client インストーラーのコマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="86f79-121">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="86f79-122">関連セクション</span><span class="sxs-lookup"><span data-stu-id="86f79-122">Related Sections</span></span>


[<span data-ttu-id="86f79-123">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="86f79-123">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

## <span data-ttu-id="86f79-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="86f79-124">Related topics</span></span>


[<span data-ttu-id="86f79-125">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="86f79-125">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="86f79-126">Application Virtualization Client のスタンドアロン配信シナリオ</span><span class="sxs-lookup"><span data-stu-id="86f79-126">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





