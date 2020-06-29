---
title: ホストと MED-V ワークスペースの間でフォルダーを共有する方法
description: ホストと MED-V ワークスペースの間でフォルダーを共有する方法
author: dansimp
ms.assetid: 3cb295f2-c07e-4ee6-aa3c-ce4c8c45c191
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87f315c9894cd38834413d2549e652a36c5cc16d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825754"
---
# <span data-ttu-id="c0793-103">ホストと MED-V ワークスペースの間でフォルダーを共有する方法</span><span class="sxs-lookup"><span data-stu-id="c0793-103">How to Share Folders Between the Host and the MED-V Workspace</span></span>


<span data-ttu-id="c0793-104">ホストと MED-V ワークスペースの間でフォルダーを共有できます。</span><span class="sxs-lookup"><span data-stu-id="c0793-104">You can share folders between the host and the MED-V workspace.</span></span> <span data-ttu-id="c0793-105">共有フォルダーは、次の場所に保存できます。</span><span class="sxs-lookup"><span data-stu-id="c0793-105">The shared folders can be stored on the following:</span></span>

-   <span data-ttu-id="c0793-106">ネットワーク上の外部コンピューター</span><span class="sxs-lookup"><span data-stu-id="c0793-106">An external computer on the network</span></span>

-   <span data-ttu-id="c0793-107">ホストコンピューター</span><span class="sxs-lookup"><span data-stu-id="c0793-107">The host computer</span></span>

<span data-ttu-id="c0793-108">次の手順では、ホストと MED-V ワークスペースの間でフォルダーを共有する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c0793-108">The following procedures demonstrate how to share folders between the host and the MED-V workspace.</span></span>

**<span data-ttu-id="c0793-109">ネットワーク上にあるフォルダーを共有するには</span><span class="sxs-lookup"><span data-stu-id="c0793-109">To share folders located on the network</span></span>**

1.  <span data-ttu-id="c0793-110">フルデスクトップモードで MED-V を構成します。</span><span class="sxs-lookup"><span data-stu-id="c0793-110">Configure MED-V in full desktop mode.</span></span>

2.  <span data-ttu-id="c0793-111">MED 管理の [ネットワーク] タブで、[ **host (Bridge) と異なる IP アドレスを使用する**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0793-111">In MED-V management, on the Network tab, click **Use different IP address than host (Bridge)**.</span></span>

3.  <span data-ttu-id="c0793-112">ホストコンピューターで次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c0793-112">Do the following on the host computer:</span></span>

    1.  <span data-ttu-id="c0793-113">コントロールパネルで、[**ネットワークの状態とタスクの表示**] をクリックし、[**ネットワーク探索**] を [**オン**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="c0793-113">In Control Panel, click **View network status and tasks**, and set **Network discovery** to **On**.</span></span>

    2.  <span data-ttu-id="c0793-114">[スタート] メニューで [**コンピューター**] を右クリックし、[**ネットワークドライブの割り当て**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0793-114">On the Start menu, right-click **Computer**, and click **Map network drive**.</span></span>

    3.  <span data-ttu-id="c0793-115">[**ネットワークドライブのマップ**] ダイアログボックスの [**ドライブ**] フィールドで、ドライブを選びます。</span><span class="sxs-lookup"><span data-stu-id="c0793-115">In the **Map Network Drive** dialog box, in the **Drive** field, select a drive.</span></span>

        <span data-ttu-id="c0793-116">**注** 両方のコンピューターで同じドライブ文字が使用されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0793-116">**Note** Ensure that the same drive letter is not in use on both computers.</span></span>

         

    4.  <span data-ttu-id="c0793-117">**[Browse]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0793-117">Click **Browse**.</span></span>

    5.  <span data-ttu-id="c0793-118">[**フォルダーの参照**] ダイアログボックスで、共有ドライブを参照し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0793-118">In the **Browse For Folder** dialog box, browse to the shared drive, and click **OK**.</span></span>

    6.  <span data-ttu-id="c0793-119">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0793-119">Click **Finish**.</span></span>

4.  <span data-ttu-id="c0793-120">MED-V ワークスペースで手順3を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="c0793-120">Repeat step 3 in the MED-V workspace.</span></span> <span data-ttu-id="c0793-121">ホストコンピューターと同じドライブをポイントします。</span><span class="sxs-lookup"><span data-stu-id="c0793-121">Point to the same drive as on the host computer.</span></span>

**<span data-ttu-id="c0793-122">ホスト上にあるフォルダーを共有するには</span><span class="sxs-lookup"><span data-stu-id="c0793-122">To share folders located on the host</span></span>**

1.  <span data-ttu-id="c0793-123">適切な権限で共有されるようにフォルダーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c0793-123">Configure the folder to be shared with the appropriate permissions.</span></span>

2.  <span data-ttu-id="c0793-124">MED-V ワークスペースで、 **[マイネットワーク**] に移動し、共有フォルダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c0793-124">From the MED-V workspace, go to **My network places** and locate the shared folder.</span></span>

3.  <span data-ttu-id="c0793-125">MED-V ワークスペースで、共有フォルダーを見つけます。</span><span class="sxs-lookup"><span data-stu-id="c0793-125">From the MED-V workspace, locate the shared folder.</span></span>

<span data-ttu-id="c0793-126">**注** Host と MED-V の両方のワークスペースコンピューターが同じドメインまたはワークグループにあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c0793-126">**Note** Ensure that both the host and MED-V workspace computers are in the same domain or workgroup.</span></span>

 

 

 





