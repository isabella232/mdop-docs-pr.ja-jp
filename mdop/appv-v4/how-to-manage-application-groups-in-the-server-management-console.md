---
title: サーバー管理コンソールでアプリケーション グループを管理する方法
description: サーバー管理コンソールでアプリケーション グループを管理する方法
author: dansimp
ms.assetid: 46997971-bdc8-4565-aefd-f47e90d6d7a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 59a357d93ea63cc728f59a0633b7a5b9953aad14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817204"
---
# <span data-ttu-id="484f6-103">サーバー管理コンソールでアプリケーション グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-103">How to Manage Application Groups in the Server Management Console</span></span>


<span data-ttu-id="484f6-104">Application Virtualization Server 管理コンソールで、アプリケーショングループ内の1つ以上のアプリケーションを表示して管理することができます。</span><span class="sxs-lookup"><span data-stu-id="484f6-104">You can display and manage one or more applications in application groups in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="484f6-105">これは、次の操作を実行する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="484f6-105">This can be useful when you want to do the following:</span></span>

-   <span data-ttu-id="484f6-106">多くのアプリケーションを、より管理しやすいサブグループにまとめる。</span><span class="sxs-lookup"><span data-stu-id="484f6-106">Organize many applications into more manageable subgroups.</span></span>

-   <span data-ttu-id="484f6-107">部門またはその他の会社部門に固有のアプリケーションのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="484f6-107">Create groups of applications specific to a department or other company division.</span></span>

-   <span data-ttu-id="484f6-108">財務ソフトウェアなど、同様の種類のアプリケーションをグループ化します。</span><span class="sxs-lookup"><span data-stu-id="484f6-108">Group similar types of applications, such as financial software.</span></span>

-   <span data-ttu-id="484f6-109">グループ別のアクセス権限またはライセンス管理を簡素化します。</span><span class="sxs-lookup"><span data-stu-id="484f6-109">Simplify access permissions or license management by group.</span></span>

-   <span data-ttu-id="484f6-110">グループ内のアプリケーションとアプリケーショングループのプロパティを同時に変更します。</span><span class="sxs-lookup"><span data-stu-id="484f6-110">Change the properties of applications and application groups within a group simultaneously.</span></span>

<span data-ttu-id="484f6-111">グループを作成し、コンソールの [**アプリケーション**] ツリーで希望の場所に配置して、アプリケーションをグループにインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="484f6-111">You can create a group, place it where you would like in the console's **Applications** tree, and import applications to the group.</span></span> <span data-ttu-id="484f6-112">次に、グループのプロパティを構成および管理して、すべてのアプリケーションに影響を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="484f6-112">Then you can configure and manage the group's properties to affect all of its applications.</span></span> <span data-ttu-id="484f6-113">グループ間でアプリケーションを移動することもできます。</span><span class="sxs-lookup"><span data-stu-id="484f6-113">You can also move applications among groups.</span></span>

<span data-ttu-id="484f6-114">**注** アプリケーションをグループに移動しても、サーバーのファイルシステムでのファイル (SFT、OSD、または SPRJ) の場所には影響しません。</span><span class="sxs-lookup"><span data-stu-id="484f6-114">**Note** Moving applications into groups does not affect the locations of their files (SFT, OSD, or SPRJ) on the server's file system.</span></span>

 

## <span data-ttu-id="484f6-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="484f6-115">In This Section</span></span>


<a href="" id="how-to-create-an-application-group"></a>[<span data-ttu-id="484f6-116">アプリケーション グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-116">How to Create an Application Group</span></span>](how-to-create-an-application-group.md)  
<span data-ttu-id="484f6-117">アプリケーショングループを作成するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="484f6-117">Provides step-by-step instructions for creating an application group.</span></span>

<a href="" id="how-to-move-an-application-group"></a>[<span data-ttu-id="484f6-118">アプリケーション グループを移動する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-118">How to Move an Application Group</span></span>](how-to-move-an-application-group.md)  
<span data-ttu-id="484f6-119">アプリケーショングループを移動するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="484f6-119">Provides step-by-step instructions for moving an application group.</span></span>

<a href="" id="how-to-rename-an-application-group"></a>[<span data-ttu-id="484f6-120">アプリケーション グループの名前を変更する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-120">How to Rename an Application Group</span></span>](how-to-rename-an-application-group.md)  
<span data-ttu-id="484f6-121">アプリケーショングループの名前を変更するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="484f6-121">Provides step-by-step instructions for renaming an application group.</span></span>

<a href="" id="how-to-remove-an-application-group"></a>[<span data-ttu-id="484f6-122">アプリケーション グループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-122">How to Remove an Application Group</span></span>](how-to-remove-an-application-group.md)  
<span data-ttu-id="484f6-123">アプリケーショングループを削除または削除するための詳しい手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="484f6-123">Provides step-by-step instructions for removing or deleting an application group.</span></span>

## <span data-ttu-id="484f6-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="484f6-124">Related topics</span></span>


[<span data-ttu-id="484f6-125">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="484f6-126">Application Virtualization サーバー管理コンソールで管理タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="484f6-126">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





