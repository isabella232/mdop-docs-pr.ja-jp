---
title: アプリケーション グループを削除する方法
description: アプリケーション グループを削除する方法
author: dansimp
ms.assetid: 3016b373-f5a0-4c82-96e8-e5e7960f0cc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b392fe84f4318cf7f355de0c07e4d6f1f5108ed7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816784"
---
# <span data-ttu-id="639c6-103">アプリケーション グループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="639c6-103">How to Remove an Application Group</span></span>


<span data-ttu-id="639c6-104">次の手順を使用して、Application Virtualization Server 管理コンソールでアプリケーショングループを削除すると、次の2つの方法のいずれかで行うことができます。</span><span class="sxs-lookup"><span data-stu-id="639c6-104">You can use the following procedures to remove an application group in the Application Virtualization Server Management Console in one of two ways:</span></span>

<span data-ttu-id="639c6-105">**注意** アプリケーションを使用してグループを削除すると、アプリケーションの仮想化管理サーバーからこれらのアプリケーションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="639c6-105">**Caution** Deleting a group with its applications deletes those applications from the Application Virtualization Management Server.</span></span> <span data-ttu-id="639c6-106">この操作を行おうとすると、ポップアップウィンドウで削除を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="639c6-106">When you try to do this, you must confirm the deletion in a pop-up window.</span></span>

 

**<span data-ttu-id="639c6-107">アプリケーショングループを空にしてから削除するには</span><span class="sxs-lookup"><span data-stu-id="639c6-107">To empty and then delete an application group</span></span>**

1.  <span data-ttu-id="639c6-108">Application Virtualization Server 管理コンソールで、左側のウィンドウで [**アプリケーション**] を展開し、削除する**アプリケーション**グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="639c6-108">In the Application Virtualization Server Management Console, expand **Applications** in the left pane and select the **Application** group you want to remove.</span></span>

2.  <span data-ttu-id="639c6-109">右側のウィンドウで、保持するアプリケーションとアプリケーショングループを選びます。</span><span class="sxs-lookup"><span data-stu-id="639c6-109">In the right pane, select the applications and application groups you want to keep.</span></span> <span data-ttu-id="639c6-110">**CTRL**キーと**Shift**キーを使用して、複数のアプリケーションとアプリケーショングループを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="639c6-110">You can use the **CTRL** and **Shift** keys to select multiple applications and application groups.</span></span>

3.  <span data-ttu-id="639c6-111">選択したアプリケーションを右クリックし、[**移動**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="639c6-111">Right-click the selected applications, and choose **Move**.</span></span>

4.  <span data-ttu-id="639c6-112">**[ターゲットの選択**] ウィンドウで、新しい場所に移動し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="639c6-112">In the **Select Target** window, navigate to the new location and click **OK**.</span></span> <span data-ttu-id="639c6-113">複数のアプリケーションを複数のグループに移動する場合は、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="639c6-113">Repeat this step if you want to move different applications to more than one group.</span></span>

5.  <span data-ttu-id="639c6-114">残しておきたいアプリケーションの移動が完了したら、アプリケーショングループを右クリックして、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="639c6-114">When you finish moving the applications you want to keep, right-click the application group and choose **Delete**.</span></span>

6.  <span data-ttu-id="639c6-115">[**はい]** をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="639c6-115">Click **Yes** to confirm.</span></span>

**<span data-ttu-id="639c6-116">すべての子グループとそのアプリケーションのグループを削除するには</span><span class="sxs-lookup"><span data-stu-id="639c6-116">To delete the group, with all its child groups and its applications</span></span>**

1.  <span data-ttu-id="639c6-117">Application Virtualization Server 管理コンソールで、左側のウィンドウで [**アプリケーション**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="639c6-117">In the Application Virtualization Server Management Console, expand **Applications** in the left pane.</span></span>

2.  <span data-ttu-id="639c6-118">削除するアプリケーショングループを右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="639c6-118">Right-click the application group you want to remove, and choose **Delete**.</span></span>

3.  <span data-ttu-id="639c6-119">[**はい]** をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="639c6-119">Click **Yes** to confirm.</span></span>

    <span data-ttu-id="639c6-120">**注** 複数のアプリケーショングループを同時に選択して削除することができます。</span><span class="sxs-lookup"><span data-stu-id="639c6-120">**Note** You can select and remove multiple application groups simultaneously.</span></span> <span data-ttu-id="639c6-121">右側のウィンドウで、CTRL キーを**押しながら**クリックするか、 **Shift**キーを押しながらクリックして、複数のグループを選択します。</span><span class="sxs-lookup"><span data-stu-id="639c6-121">In the right pane, use the **CTRL**-click or **Shift**-click key combinations to select more than one group.</span></span>

     

## <span data-ttu-id="639c6-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="639c6-122">Related topics</span></span>


[<span data-ttu-id="639c6-123">サーバー管理コンソールでアプリケーション グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="639c6-123">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="639c6-124">サーバー管理コンソールでアプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="639c6-124">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





