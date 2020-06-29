---
title: Application Virtualization アプリケーションについて
description: Application Virtualization アプリケーションについて
author: dansimp
ms.assetid: 3bf833b7-d172-4eef-a9e8-4b4f0c7eb15b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4eeea7a0ec4454aefcdde5196ae15ed029da45b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820087"
---
# <span data-ttu-id="bf899-103">Application Virtualization アプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="bf899-103">About Application Virtualization Applications</span></span>


<span data-ttu-id="bf899-104">アプリケーションの仮想化では、アプリケーションは、Microsoft Visio などの実行可能なプログラム*であり、* アプリケーション仮想化のデスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) のクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="bf899-104">In Application Virtualization, an *application* is an executable program, such as Microsoft Visio, that is streamed to the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) from an Application Virtualization Management Server.</span></span> <span data-ttu-id="bf899-105">アプリケーションをクライアントにストリーミングするには、その前にアプリケーションの仮想化 Sequencer でそのアプリケーションを処理することによって、ストリーミングの準備ができている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf899-105">Before an application can be streamed to a client, the application must be prepared for streaming by processing it with the Application Virtualization Sequencer.</span></span>

## <span data-ttu-id="bf899-106">アプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="bf899-106">Managing Applications</span></span>


<span data-ttu-id="bf899-107">アプリケーションをユーザーが利用できるようにするには、その前にシステムにアプリケーションを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf899-107">You must add applications to the system before you can make the applications available to users.</span></span> <span data-ttu-id="bf899-108">システムにアプリケーションを追加する最も一般的な方法は、アプリケーションをインポートすることです。</span><span class="sxs-lookup"><span data-stu-id="bf899-108">The most common method for adding applications to the system is to import them.</span></span> <span data-ttu-id="bf899-109">この機能にアクセスするには、Application Virtualization Server 管理コンソールで [**アプリケーション**] ノードを右クリックして、[**アプリケーションのインポート**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="bf899-109">To access this feature, right-click the **Applications** node in the Application Virtualization Server Management Console and choose **Import Applications**.</span></span>

<span data-ttu-id="bf899-110">同時に複数のオープンソフトウェア記述子 (OSD) ファイルをインポートすることも、複数の OSD ファイルを含む Sequencer プロジェクトファイル (SPRJ) をインポートすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bf899-110">You can import more than one Open Software Descriptor (OSD) file at the same time, or you can import a Sequencer Project file (SPRJ) that can contain multiple OSD files.</span></span> <span data-ttu-id="bf899-111">この機能により、関連するアプリケーションも同様に構成できます。</span><span class="sxs-lookup"><span data-stu-id="bf899-111">This functionality enables you to configure related applications similarly.</span></span>

<span data-ttu-id="bf899-112">次の機能を使用して、アプリケーションを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf899-112">You can also use the following features to help you manage your applications:</span></span>

-   <span data-ttu-id="bf899-113">**アプリケーショングループ**—アプリケーションの論理グループを作成して、管理を簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf899-113">**Application Groups**—Enables you to create logical groups of applications for simplified management.</span></span> <span data-ttu-id="bf899-114">グループ (アクセス許可など) に変更が加えられると、その変更はグループ内のすべてのアプリケーションに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bf899-114">When changes are made to a group (for example, access permissions), the changes are applied to all applications in the group.</span></span> <span data-ttu-id="bf899-115">グループ内のアプリケーションは、異なるパッケージから取得できます。</span><span class="sxs-lookup"><span data-stu-id="bf899-115">Applications in a group can come from different packages.</span></span>

-   <span data-ttu-id="bf899-116">複数**選択**: CTRL キーを押しながらアプリケーションをクリックしてアプリケーションのプロパティを変更することで、複数のアプリケーションを一度に選択できます。</span><span class="sxs-lookup"><span data-stu-id="bf899-116">**Multi Select**—Enables you to select multiple applications at once by holding the CTRL key when you click an application to modify the application properties.</span></span> <span data-ttu-id="bf899-117">ただし、アプリケーション間の関係を維持する場合は、アプリケーションを保持するアプリケーショングループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf899-117">However, if you want to maintain a relationship between the applications, you should create an application group to hold the applications.</span></span>

-   <span data-ttu-id="bf899-118">**クロスシステムコピー**: 1 つの手順で同じバージョンの app-v を実行している別の環境にアプリケーションをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="bf899-118">**Cross System Copy**—Enables you to copy applications from one environment to another environment that is running the same version of App-V in one step.</span></span> <span data-ttu-id="bf899-119">たとえば、アプリケーションの最初の展開と構成を行うユーザー受け入れテスト環境がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bf899-119">For example, you might have a user acceptance test environment where you initially deploy and configure applications.</span></span> <span data-ttu-id="bf899-120">テストフェーズが終了したら、同じセットのアプリケーション (権限を含む) を運用環境にレプリケートすることができます。</span><span class="sxs-lookup"><span data-stu-id="bf899-120">After you finish your testing phase, you might want to replicate the same set of applications (including permissions) to the production environment.</span></span>

## <span data-ttu-id="bf899-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bf899-121">Related topics</span></span>


[<span data-ttu-id="bf899-122">Application Virtualization パッケージについて</span><span class="sxs-lookup"><span data-stu-id="bf899-122">About Application Virtualization Packages</span></span>](about-application-virtualization-packages.md)

[<span data-ttu-id="bf899-123">Application Virtualization サーバー管理コンソールについて</span><span class="sxs-lookup"><span data-stu-id="bf899-123">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="bf899-124">サーバー管理コンソールでアプリケーション グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="bf899-124">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="bf899-125">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="bf899-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





