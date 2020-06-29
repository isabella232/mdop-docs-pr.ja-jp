---
title: サーバーおよびシステム コンポーネントをインストールする方法
description: サーバーおよびシステム コンポーネントをインストールする方法
author: dansimp
ms.assetid: c6f5fef0-522a-4ef1-8585-05b292d0289b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ceb5b8376189aee7631229dca912140e454536b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817244"
---
# <span data-ttu-id="2685a-103">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-103">How to Install the Servers and System Components</span></span>


<span data-ttu-id="2685a-104">ユーザーにアプリケーションを配布するには、Microsoft Application Virtualization Platform コンポーネントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2685a-104">Before you can deliver applications to users, you must install the Microsoft Application Virtualization Platform components.</span></span> <span data-ttu-id="2685a-105">このセクションのトピックでは、Application Virtualization サーバーとその他の Application Virtualization システムコンポーネントをインストールするために必要な情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-105">The topics in this section provide the information required to install the Application Virtualization Servers and the other Application Virtualization System components.</span></span>

<span data-ttu-id="2685a-106">**注** このセクションの手順では、カスタムインストールを実行します。ここでは、運用環境で推奨されるように、別のコンピューターにインストールするコンポーネントを選択して選択します。</span><span class="sxs-lookup"><span data-stu-id="2685a-106">**Note** The procedures in this section take you through a customized installation, where you pick and choose components to install on separate computers, as recommended in a production environment.</span></span> <span data-ttu-id="2685a-107">ただし、お客様の運用手順では別の方法が考えられる場合があり、インストールプロセス中にコンポーネントをグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="2685a-107">However, your operating procedures might dictate a different approach, and during the installation process you might want to group components together.</span></span> <span data-ttu-id="2685a-108">コンポーネントをインストールする場所に関係なく、任意の順序でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2685a-108">Regardless of where you install the components, you can install them in any order.</span></span>

 

## <span data-ttu-id="2685a-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="2685a-109">In This Section</span></span>


<a href="" id="how-to-install-application-virtualization-management-server"></a>[<span data-ttu-id="2685a-110">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-110">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)  
<span data-ttu-id="2685a-111">Application Virtualization Management Server をインストールして、適切なサーバーグループに割り当てる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-111">Provides a step-by-step procedure for installing the Application Virtualization Management Server and assigning it to the appropriate server group.</span></span>

<a href="" id="how-to-install-the-application-virtualization-streaming-server"></a>[<span data-ttu-id="2685a-112">Application Virtualization Streaming Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-112">How to Install the Application Virtualization Streaming Server</span></span>](how-to-install-the-application-virtualization-streaming-server.md)  
<span data-ttu-id="2685a-113">Application Virtualization ストリーミングサーバーをインストールして、適切なサーバーグループに割り当てる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-113">Provides a step-by-step procedure for installing the Application Virtualization Streaming Server and assigning it to the appropriate server group.</span></span>

<a href="" id="how-to-install-the-management-web-service"></a>[<span data-ttu-id="2685a-114">Management Web Service をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-114">How to Install the Management Web Service</span></span>](how-to-install-the-management-web-service.md)  
<span data-ttu-id="2685a-115">ネットワーク上のターゲットコンピューターに Application Virtualization Management Web サービスをインストールするためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-115">Provides a step-by-step procedure for installing the Application Virtualization Management Web Service on a target computer on your network.</span></span>

<a href="" id="how-to-install-the-management-console"></a>[<span data-ttu-id="2685a-116">Management Console をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-116">How to Install the Management Console</span></span>](how-to-install-the-management-console.md)  
<span data-ttu-id="2685a-117">ネットワーク上のターゲットコンピューターに Application Virtualization 管理コンソールをインストールするためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-117">Provides a step-by-step procedure for installing the Application Virtualization Management Console on a target computer on your network.</span></span>

<a href="" id="how-to-install-a-database"></a>[<span data-ttu-id="2685a-118">データベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-118">How to Install a Database</span></span>](how-to-install-a-database.md)  
<span data-ttu-id="2685a-119">データベースがまだ利用できない場合に、サーバーベースのアプリケーションの仮想化の展開用にデータベースをインストールするための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-119">Provides a step-by-step procedure for installing a database for your server-based deployment of Application Virtualization, if a database is not already available.</span></span>

<a href="" id="how-to-remove-the-application-virtualization-system-components"></a>[<span data-ttu-id="2685a-120">Application Virtualization システム コンポーネントを削除する方法</span><span class="sxs-lookup"><span data-stu-id="2685a-120">How to Remove the Application Virtualization System Components</span></span>](how-to-remove-the-application-virtualization-system-components.md)  
<span data-ttu-id="2685a-121">ターゲットコンピューターからすべてまたは選択したアプリケーション仮想化ソフトウェアのコンポーネントを削除するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2685a-121">Provides step-by-step procedures to remove all or selected Application Virtualization software components from a target computer.</span></span>

## <span data-ttu-id="2685a-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2685a-122">Related topics</span></span>


[<span data-ttu-id="2685a-123">Application Virtualization サーバー ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="2685a-123">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)

[<span data-ttu-id="2685a-124">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2685a-124">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="2685a-125">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="2685a-125">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)

 

 





