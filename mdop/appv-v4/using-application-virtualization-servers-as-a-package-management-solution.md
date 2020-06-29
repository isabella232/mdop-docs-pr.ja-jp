---
title: パッケージ管理ソリューションとしての Application Virtualization サーバーの使用
description: パッケージ管理ソリューションとしての Application Virtualization サーバーの使用
author: dansimp
ms.assetid: 41597355-e7bb-45e2-b300-7b1724419975
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2b81ed3ab6fa3a70fe4780904059091f22579d9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815124"
---
# <span data-ttu-id="7feca-103">パッケージ管理ソリューションとしての Application Virtualization サーバーの使用</span><span class="sxs-lookup"><span data-stu-id="7feca-103">Using Application Virtualization Servers as a Package Management Solution</span></span>


<span data-ttu-id="7feca-104">既存の ESD システムで Application Virtualization ソリューションを展開する場合や、使用しない場合は、システムアーキテクチャの中核として、1つ以上の Application Virtualization 管理サーバーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="7feca-104">If you do not have an existing ESD system to deploy your Application Virtualization solution or do not wish to use one, you will need to install one or more Application Virtualization Management Servers as the core of your system architecture.</span></span> <span data-ttu-id="7feca-105">Application Virtualization Management Server には、専用のサーバーコンピューターが必要です。 Microsoft SQL Server データベースが必要です。</span><span class="sxs-lookup"><span data-stu-id="7feca-105">The Application Virtualization Management Server requires a dedicated server computer and needs a Microsoft SQL Server database.</span></span> <span data-ttu-id="7feca-106">データベースは、同じサーバー上に置くことも、高速 LAN 接続を介してアプリケーションの仮想化管理サーバーからアクセスできる企業のデータベースサーバー上で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="7feca-106">The database can be on the same server, or it can be configured on a corporate database server that is accessible to the Application Virtualization Management Server over a high-speed LAN connection.</span></span> <span data-ttu-id="7feca-107">さらに、Application Virtualization management Server または指定した管理ワークステーションに Microsoft Application Virtualization 管理コンソールをインストールする必要があります。また、Microsoft Application Virtualization management Web Service をインストールする必要があります。このサービスは、Application Virtualization Management Server または別の IIS サーバーにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="7feca-107">In addition, you will need to install the Microsoft Application Virtualization Management Console, on either the Application Virtualization Management Server or on a designated management workstation, and you will need to install the Microsoft Application Virtualization Management Web Service, which can also be installed on the Application Virtualization Management Server or on a separate IIS server.</span></span> <span data-ttu-id="7feca-108">Application virtualization 管理コンソールは、application virtualization management Web サービスに接続するために使用されます。これにより、システム管理者が Application Virtualization Management Server を操作できるようになります。</span><span class="sxs-lookup"><span data-stu-id="7feca-108">The Application Virtualization Management Console is used to connect to the Application Virtualization Management Web Service, enabling the system administrator to interact with the Application Virtualization Management Server.</span></span>

<span data-ttu-id="7feca-109">**注** アプリケーションへのアクセスは Active Directory ドメインサービスのセキュリティグループによって制御されるため、仮想化されたアプリケーションごとにセキュリティグループをセットアップし、各グループに追加されるユーザーを管理するためのプロセスを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7feca-109">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process to set up a security group for each virtualized application and for managing which users are added to each group.</span></span> <span data-ttu-id="7feca-110">これらの Active Directory グループを使用するようにサーバーが構成され、サーバーは Active Directory グループメンバーシップに基づいてパッケージへのアクセスを自動的に制御します。</span><span class="sxs-lookup"><span data-stu-id="7feca-110">The Application Virtualization Management Server administrator configures the server to use these Active Directory groups, and the server then automatically controls access to the packages based on Active Directory group membership.</span></span>

 

## <span data-ttu-id="7feca-111">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="7feca-111">In This Section</span></span>


<a href="" id="overview-of-the-application-virtualization-system-components"></a>[<span data-ttu-id="7feca-112">Application Virtualization システム コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="7feca-112">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)  
<span data-ttu-id="7feca-113">Microsoft Application Virtualization Management System の主要コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7feca-113">Lists and describes the primary components of the Microsoft Application Virtualization Management System.</span></span>

<a href="" id="publishing-virtual-applications-using-application-virtualization-management-servers"></a>[<span data-ttu-id="7feca-114">Application Virtualization Management Server を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="7feca-114">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)  
<span data-ttu-id="7feca-115">Application Virtualization Server ベースの展開シナリオで仮想アプリケーションを公開する方法の概要を簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="7feca-115">Provides a brief overview of how virtual applications are published in an Application Virtualization Server-based deployment scenario.</span></span>

<a href="" id="planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation"></a>[<span data-ttu-id="7feca-116">Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="7feca-116">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)  
<span data-ttu-id="7feca-117">Application virtualization Management Server ベースの実装と組み合わせて、アプリケーションの仮想化ストリーミングサーバーを使用するために使用できるオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7feca-117">Describes available options for using Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation.</span></span>

## <span data-ttu-id="7feca-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7feca-118">Related topics</span></span>


[<span data-ttu-id="7feca-119">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="7feca-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="7feca-120">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="7feca-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





