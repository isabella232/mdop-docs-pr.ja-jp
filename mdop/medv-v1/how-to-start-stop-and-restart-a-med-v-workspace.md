---
title: MED-V ワークスペースを開始、停止、再開する方法
description: MED-V ワークスペースを開始、停止、再開する方法
author: dansimp
ms.assetid: 54ce139c-8f32-499e-944b-72f123ebfd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2739ace085a4d57d333daf7872e01a7712a7fbd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825724"
---
# <span data-ttu-id="e5848-103">MED-V ワークスペースを開始、停止、再開する方法</span><span class="sxs-lookup"><span data-stu-id="e5848-103">How to Start, Stop, and Restart a MED-V Workspace</span></span>


**<span data-ttu-id="e5848-104">MED-V ワークスペースを開始するには</span><span class="sxs-lookup"><span data-stu-id="e5848-104">To start a MED-V workspace</span></span>**

1.  <span data-ttu-id="e5848-105">通知領域で、MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-105">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="e5848-106">サブメニューで、[**ワークスペースの開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-106">On the submenu, click **Start Workspace**.</span></span>

    -   <span data-ttu-id="e5848-107">コンピューター上で実行されている複数の MED-V ワークスペースがある場合は、**ワークスペースの選択**ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-107">If there are multiple MED-V workspaces running on the computer, the **Workspace Selection** window appears.</span></span>

        1.  <span data-ttu-id="e5848-108">MED-V ワークスペースを選択します。</span><span class="sxs-lookup"><span data-stu-id="e5848-108">Select a MED-V workspace.</span></span>

        2.  <span data-ttu-id="e5848-109">次回クライアントを起動し、選択した MED-V ワークスペースを自動的に開くには、[確認メッセージを表示**せずに、選択したワークスペース**をスキップする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="e5848-109">Select the **Start the selected Workspace without asking me** check box to skip this window the next time the client is started and to automatically open the selected MED-V workspace.</span></span>

        3.  <span data-ttu-id="e5848-110">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-110">Click **OK**.</span></span>

    <span data-ttu-id="e5848-111">[**ワークスペースの認証の開始**] ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-111">The **Start Workspace Authentication** window appears.</span></span>

    -   <span data-ttu-id="e5848-112">コンピューター上に複数の MED-V ワークスペースがあり、指定した MED-V ワークスペースを使うことを選んだ場合、次の図のようなウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-112">If there are several MED-V workspaces on the computer and you have opted to use a specified MED-V workspace, the window shown in the following figure appears.</span></span>

        ![](images/medv-logon.gif)

    -   <span data-ttu-id="e5848-113">コンピューター上に MED-V ワークスペースが1つしかない場合、[最後に使用した作業を開始する] オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="e5848-113">If there is only one MED-V workspace on the computer, the “Start last used Workspace” option is unavailable.</span></span>

3.  <span data-ttu-id="e5848-114">ドメインユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="e5848-114">Type in your domain user credentials.</span></span>

    <span data-ttu-id="e5848-115">**注** Med-v ワークスペースを初めて起動するときに、ユーザー名は次の形式になっている必要があります。 &lt; ドメイン名の &gt; \\ &lt; ユーザー名 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="e5848-115">**Note** The first time a MED-V workspace is started, the user name should be in the following format: &lt;domain name&gt;\\&lt;user name&gt;.</span></span>

     

4.  <span data-ttu-id="e5848-116">[**パスワードを保存**してセッション間のパスワードを保存する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e5848-116">Select **Save my password** to save your password between sessions.</span></span>

    <span data-ttu-id="e5848-117">**注** パスワードの保存機能を有効にするには、ClientSettings.xml ファイルで EnableSavePassword 属性が True に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e5848-117">**Note** To enable the save password feature, the EnableSavePassword attribute must be set to True in the ClientSettings.xml file.</span></span> <span data-ttu-id="e5848-118">ファイルは\*Servers\\Configuration \*フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="e5848-118">The file can be found in the *Servers\\Configuration Server\\* folder.</span></span>

     

5.  <span data-ttu-id="e5848-119">[最後に使用した**作業を開始**する] チェックボックスをオフにして、別の med-v ワークスペースを選びます。</span><span class="sxs-lookup"><span data-stu-id="e5848-119">Clear the **Start last used workspace** check box to choose a different MED-V workspace.</span></span>

6.  <span data-ttu-id="e5848-120">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-120">Click **OK**.</span></span>

    <span data-ttu-id="e5848-121">MED-V ワークスペースの構成に応じて、いくつかの状態画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-121">Several status screens appear depending on the MED-V workspace configuration.</span></span>

    <span data-ttu-id="e5848-122">[**ワークスペースの開始**] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-122">The **Starting Workspace** screen appears.</span></span>

**<span data-ttu-id="e5848-123">MED-V ワークスペースを再起動するには</span><span class="sxs-lookup"><span data-stu-id="e5848-123">To restart a MED-V workspace</span></span>**

1.  <span data-ttu-id="e5848-124">クライアントが実行されているときに、通知領域で MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-124">When the client is running, in the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="e5848-125">サブメニューで、[**ワークスペースの再起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-125">On the submenu, click **Restart Workspace**.</span></span>

    <span data-ttu-id="e5848-126">MED-V ワークスペースが再起動されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-126">The MED-V workspace is restarted.</span></span>

    -   <span data-ttu-id="e5848-127">永続的な MED-V ワークスペースでは、仮想マシンはシャットダウンされ、再起動されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-127">In a persistent MED-V workspace, the virtual machine is shut down and then restarted.</span></span>

    -   <span data-ttu-id="e5848-128">Revertible MED ワークスペースでは、仮想マシンは実際にはシャットダウンされません。代わりに、元の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="e5848-128">In a revertible MED-V workspace, the virtual machine does not actually shut down; instead, it returns to its original state.</span></span>

**<span data-ttu-id="e5848-129">MED-V ワークスペースを停止するには</span><span class="sxs-lookup"><span data-stu-id="e5848-129">To stop a MED-V workspace</span></span>**

1.  <span data-ttu-id="e5848-130">通知領域で、MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-130">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="e5848-131">サブメニューで、[**ワークスペースの停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e5848-131">On the submenu, click **Stop Workspace**.</span></span>

    <span data-ttu-id="e5848-132">MED-V ワークスペースは停止されます。</span><span class="sxs-lookup"><span data-stu-id="e5848-132">The MED-V workspace is stopped.</span></span>

## <span data-ttu-id="e5848-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e5848-133">Related topics</span></span>


[<span data-ttu-id="e5848-134">MED-V クライアントを開始および終了する方法</span><span class="sxs-lookup"><span data-stu-id="e5848-134">How to Start and Exit the MED-V Client</span></span>](how-to-start-and-exit-the-med-v-client.md)

 

 





