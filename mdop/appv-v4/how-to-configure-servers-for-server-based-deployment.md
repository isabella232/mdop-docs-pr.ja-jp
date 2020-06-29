---
title: サーバー ベースの展開用にサーバーを構成する方法
description: サーバー ベースの展開用にサーバーを構成する方法
author: dansimp
ms.assetid: 6371c37a-46eb-44e8-ad6b-4430c866c8b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c60ae89bc42fddad8aeb6a4f6df0f2c0b4ee4f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817917"
---
# <span data-ttu-id="a58d9-103">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-103">How to Configure Servers for Server-Based Deployment</span></span>


<span data-ttu-id="a58d9-104">このセクションでは、Application Virtualization Server ベースの展開戦略に応じて、Microsoft System Center Application Virtualization (App-v) 管理サーバーと Microsoft System Center Application Virtualization ストリーミングサーバー、およびインターネットインフォメーションサービス (IIS) とファイルサーバーを構成するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-104">This section provides procedures you can use to configure the Microsoft System Center Application Virtualization (App-V) Management Servers and Microsoft System Center Application Virtualization Streaming Servers, and the Internet Information Services (IIS) and file servers, as appropriate for your Application Virtualization Server-based deployment strategy.</span></span>

## <span data-ttu-id="a58d9-105">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="a58d9-105">In This Section</span></span>


<a href="" id="how-to-configure-the-application-virtualization-management-servers"></a>[<span data-ttu-id="a58d9-106">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-106">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)  
<span data-ttu-id="a58d9-107">Application Virtualization Management Server を構成するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-107">Provides a step-by-step procedure for configuring the Application Virtualization Management Servers.</span></span>

<a href="" id="how-to-configure-the-application-virtualization-streaming-servers"></a>[<span data-ttu-id="a58d9-108">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-108">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)  
<span data-ttu-id="a58d9-109">Application Virtualization ストリーミングサーバーを構成するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-109">Provides a step-by-step procedure for configuring the Application Virtualization Streaming Servers.</span></span>

<a href="" id="how-to-configure-the-server-for-iis"></a>[<span data-ttu-id="a58d9-110">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-110">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)  
<span data-ttu-id="a58d9-111">サーバーベースの展開用に IIS サーバーを構成するためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-111">Provides a step-by-step procedure for configuring the IIS server for your server-based deployment.</span></span>

<a href="" id="how-to-configure-the-server-to-be-trusted-for-delegation"></a>[<span data-ttu-id="a58d9-112">サーバーを委任に対して信頼されるように構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-112">How to Configure the Server to be Trusted for Delegation</span></span>](how-to-configure-the-server-to-be-trusted-for-delegation.md)  
<span data-ttu-id="a58d9-113">委任に対して信頼されるようにサーバーを構成する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-113">Provides detailed instructions about how to configure the server to be trusted for delegation.</span></span>

<a href="" id="configuring-the-firewall-for-the-app-v-servers"></a>[<span data-ttu-id="a58d9-114">App-V サーバー用にファイアウォールを構成する</span><span class="sxs-lookup"><span data-stu-id="a58d9-114">Configuring the Firewall for the App-V Servers</span></span>](configuring-the-firewall-for-the-app-v-servers.md)  
<span data-ttu-id="a58d9-115">App-v サーバーに必要なファイアウォール設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-115">Describes the firewall settings required for the App-V servers.</span></span>

<a href="" id="how-to-install-and-configure-the-default-application"></a>[<span data-ttu-id="a58d9-116">既定のアプリケーションをインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-116">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)  
<span data-ttu-id="a58d9-117">App-v システムをテストするための既定のアプリケーションをインストールして構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a58d9-117">Describes how to install and configure the default application for testing the App-V system.</span></span>

## <span data-ttu-id="a58d9-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a58d9-118">Related topics</span></span>


[<span data-ttu-id="a58d9-119">Application Virtualization サーバー ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="a58d9-119">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)

[<span data-ttu-id="a58d9-120">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="a58d9-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="a58d9-121">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="a58d9-121">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





