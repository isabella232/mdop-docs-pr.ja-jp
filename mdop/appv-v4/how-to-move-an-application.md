---
title: アプリケーションを移動する方法
description: アプリケーションを移動する方法
author: dansimp
ms.assetid: 3ebbf30c-b435-4a69-a0ba-2313aaf0017c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01879cf5c1451d49475b1c1984f6881a3969eef2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816914"
---
# <span data-ttu-id="11d98-103">アプリケーションを移動する方法</span><span class="sxs-lookup"><span data-stu-id="11d98-103">How to Move an Application</span></span>


<span data-ttu-id="11d98-104">Application Virtualization Server 管理コンソールの [**アプリケーション**] ノードの下にアプリケーショングループがある場合は、アプリケーションをグループに移動するか、メインノードからグループに移動することができます。</span><span class="sxs-lookup"><span data-stu-id="11d98-104">If you have application groups under the **Applications** node in the Application Virtualization Server Management Console, you can move an application between groups or from the main node to a group.</span></span> <span data-ttu-id="11d98-105">操作に合わせてアプリケーションを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="11d98-105">You can move the applications to suit your operations.</span></span> <span data-ttu-id="11d98-106">また、入れ子になったグループのプロパティを同時に変更できるようにグループ化することもできます。</span><span class="sxs-lookup"><span data-stu-id="11d98-106">You also can group them so that you can change the properties of nested groups simultaneously.</span></span>

<span data-ttu-id="11d98-107">**重要** アプリケーションを移動するには、[**アプリケーション**] ノードの下に1つ以上のアプリケーショングループが必要です。</span><span class="sxs-lookup"><span data-stu-id="11d98-107">**Important** You must have one or more application groups under the **Applications** node to move applications.</span></span>

 

**<span data-ttu-id="11d98-108">アプリケーションを移動するには</span><span class="sxs-lookup"><span data-stu-id="11d98-108">To move an application</span></span>**

1.  <span data-ttu-id="11d98-109">Application Virtualization Server 管理コンソールの左側のウィンドウで、[**アプリケーション**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="11d98-109">In the left pane of the Application Virtualization Server Management Console, expand **Applications**.</span></span>

2.  <span data-ttu-id="11d98-110">移動するアプリケーションを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="11d98-110">Highlight the application you want to move.</span></span>

3.  <span data-ttu-id="11d98-111">アプリケーションを右クリックして、[**移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="11d98-111">Right-click the application and choose **Move**.</span></span>

4.  <span data-ttu-id="11d98-112">**[ターゲットの選択**] ウィンドウで、このグループを配置するグループに移動します。</span><span class="sxs-lookup"><span data-stu-id="11d98-112">In the **Select Target** window, navigate to the group in which you want to place this group.</span></span>

5.  <span data-ttu-id="11d98-113">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11d98-113">Click **OK**.</span></span>

    <span data-ttu-id="11d98-114">アプリケーションがターゲットグループの下に表示されるようになります。</span><span class="sxs-lookup"><span data-stu-id="11d98-114">The applications now appear under the target group.</span></span> <span data-ttu-id="11d98-115">この移動では、グループまたはそのアプリケーションのプロパティは変更されません。サーバー上のアプリケーションのファイルは移動されません。</span><span class="sxs-lookup"><span data-stu-id="11d98-115">This move does not change the properties of the group or its applications, and it does not move any of the application's files on the server.</span></span>

    <span data-ttu-id="11d98-116">**注** 複数のアプリケーショングループを同時に選択して移動することができます。</span><span class="sxs-lookup"><span data-stu-id="11d98-116">**Note** You can select and move multiple application groups simultaneously.</span></span> <span data-ttu-id="11d98-117">右側のウィンドウで、CTRL キーを**押しながら**クリックするか、 **Shift**キーを押しながらクリックして、複数のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="11d98-117">In the right pane, use the **CTRL**-click or **Shift**-click key combinations to select more than one group.</span></span>

     

## <span data-ttu-id="11d98-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="11d98-118">Related topics</span></span>


[<span data-ttu-id="11d98-119">アプリケーション グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="11d98-119">How to Create an Application Group</span></span>](how-to-create-an-application-group.md)

[<span data-ttu-id="11d98-120">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="11d98-120">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





