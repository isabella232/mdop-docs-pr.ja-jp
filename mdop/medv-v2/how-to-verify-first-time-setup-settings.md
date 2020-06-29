---
title: 初回使用時のセットアップの設定を確認する方法
description: 初回使用時のセットアップの設定を確認する方法
author: dansimp
ms.assetid: e8a07d4c-5786-4455-ac43-2deac4042efd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859d627ec90fbc26d18019062d5e316f907cec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813026"
---
# <span data-ttu-id="2d648-103">初回使用時のセットアップの設定を確認する方法</span><span class="sxs-lookup"><span data-stu-id="2d648-103">How to Verify First Time Setup Settings</span></span>


<span data-ttu-id="2d648-104">初回のセットアップが実行されているか、または完了した後、次のタスクを実行して、MED-V ワークスペースで構成した設定を確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d648-104">While your test of first time setup is running or after it finishes, you can verify the settings that you configured in your MED-V workspace by performing the following tasks.</span></span>

<span data-ttu-id="2d648-105">**注** 展開後のエンタープライズ全体での初回のセットアップが正常に完了したことを監視する方法については、「 [Med-v ワークスペース展開を監視](monitoring-med-v-workspace-deployments.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d648-105">**Note** For information about how to monitor the successful completion of first time setup throughout your enterprise after deployment, see [Monitoring MED-V Workspace Deployments](monitoring-med-v-workspace-deployments.md).</span></span>

 

**<span data-ttu-id="2d648-106">初めてセットアップを行うときに設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="2d648-106">To verify settings during first time setup</span></span>**

1.  <span data-ttu-id="2d648-107">セットアップの初回実行時に、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-107">While first time setup is running, verify the following:</span></span>

    <span data-ttu-id="2d648-108">**無人**モードを指定した場合は、セットアップを初めて実行したときに仮想マシンが表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-108">If you specified **Unattended** mode, verify that the virtual machine does not appear when first time setup is running.</span></span>

    <span data-ttu-id="2d648-109">有人モードを指定した場合は、仮想マシンが表示されていること、およびユーザー入力が必要なすべてのフィールドが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-109">If you specified attended mode, verify that the virtual machine appears and that all fields that require user input are displayed.</span></span>

2.  <span data-ttu-id="2d648-110">最初のセットアップが実行されているときに仮想マシンを表示することで、初回のセットアッププロセスを監視することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d648-110">You can also monitor the complete first time setup process by viewing the virtual machine when first time setup is running.</span></span> <span data-ttu-id="2d648-111">これを行うには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="2d648-111">To do this, follow these steps:</span></span>

    1.  <span data-ttu-id="2d648-112">Windows Virtual PC コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d648-112">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="2d648-113">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc**]、[ **windows 仮想 pc**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d648-113">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="2d648-114">まだ実行されていない場合は、MED-V を開始します。</span><span class="sxs-lookup"><span data-stu-id="2d648-114">Start MED-V if it is not already running.</span></span>

        <span data-ttu-id="2d648-115">まだ存在しない場合は、短時間で展開された MED-V ワークスペースの名前の仮想マシンが仮想マシンの一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2d648-115">If not already present, in a short time, a virtual machine with the name of the deployed MED-V workspace appears in the list of virtual machines.</span></span>

    3.  <span data-ttu-id="2d648-116">MED-V 仮想マシンをダブルクリックして開きます。</span><span class="sxs-lookup"><span data-stu-id="2d648-116">Double-click the MED-V virtual machine to open it.</span></span>

        <span data-ttu-id="2d648-117">設定されている場合は、MED-V 仮想マシンを観察し、ミニセットアップ手順のトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="2d648-117">You can observe the MED-V virtual machine when it is being set up, and you can troubleshoot the Mini-Setup procedure.</span></span> <span data-ttu-id="2d648-118">ネットワーク設定の構成、コンピュータードメインの参加情報、ゲストエージェントの構成、個人設定のセットアップ、シャットダウンなど、さまざまな画面で情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-118">Verify the information in the different screens as they go by, such as configuring networking settings, computer domain join information, configuring of the Guest Agent, set up of personal settings, and shutdown.</span></span>

    4.  <span data-ttu-id="2d648-119">仮想マシンは、セットアップが初めて終了したときに自動的に閉じられます。</span><span class="sxs-lookup"><span data-stu-id="2d648-119">The virtual machine closes automatically when first time setup finishes.</span></span>

        <span data-ttu-id="2d648-120">**注** 仮想マシンのウィンドウはいつでも閉じ、セットアップを続けることができます。</span><span class="sxs-lookup"><span data-stu-id="2d648-120">**Note** You can close the virtual machine window at any time and first time setup continues.</span></span>

         

**<span data-ttu-id="2d648-121">セットアップの完了後に設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="2d648-121">To verify settings after first time setup finishes</span></span>**

1.  <span data-ttu-id="2d648-122">初回のセットアップが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-122">Ensure that first time setup finished successfully.</span></span>

2.  <span data-ttu-id="2d648-123">MED-V ワークスペースが正しく設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-123">Verify that the MED-V workspace is set up correctly.</span></span>

    1.  <span data-ttu-id="2d648-124">Windows Virtual PC コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="2d648-124">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="2d648-125">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc**]、[ **windows 仮想 pc**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d648-125">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="2d648-126">インストールされている MED-V ワークスペースをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d648-126">Double-click your installed MED-V workspace.</span></span>

        <span data-ttu-id="2d648-127">MED-V ワークスペースで既に仮想アプリケーションが実行されている場合は、仮想マシンを開く前にアプリケーションを閉じるように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2d648-127">If the MED-V workspace is already running a virtual application, you might be prompted to close the application before you can open the virtual machine.</span></span>

    3.  <span data-ttu-id="2d648-128">MED-V ワークスペースで、[**マイコンピューター**] を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d648-128">In the MED-V workspace, right-click **My Computer**, and then click **Properties**.</span></span>

    4.  <span data-ttu-id="2d648-129">MED-V ワークスペースが正しいドメインに参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-129">Verify that the MED-V workspace joined the correct domain.</span></span> <span data-ttu-id="2d648-130">組織に該当する場合は、2つの異なるドメインを指定してドメイン参加をテストし、ゲストドメインがホストドメインによって上書きされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-130">If applicable to your organization, test domain joining by specifying two different domains to verify that the guest domain is overridden by the host domain.</span></span>

    5.  <span data-ttu-id="2d648-131">指定したドメイン組織単位に、MED-V ワークスペースが参加していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-131">Verify that the MED-V workspace joined the domain organizational unit that you specified.</span></span>

    6.  <span data-ttu-id="2d648-132">コンピューター名のマスクを指定した場合は、新しいコンピューター名が指定したものと一致することを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-132">If you specified the computer name mask, verify that the new computer name matches what was specified.</span></span>

3.  <span data-ttu-id="2d648-133">指定したロケール設定が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-133">Verify that the locale settings that you specified are correct.</span></span>

    1.  <span data-ttu-id="2d648-134">MED-V ワークスペースで、[**スタート**] をクリックし、[**コントロールパネル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d648-134">In the MED-V workspace, click **Start** and then click **Control Panel**.</span></span>

    2.  <span data-ttu-id="2d648-135">**日付、時刻**、**地域と言語**など、指定した構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="2d648-135">Verify your specified configuration settings, for example, **Date and Time** and **Regional and Language**.</span></span>

<span data-ttu-id="2d648-136">**注** セットアップ設定の初回確認で問題が発生した場合は、「[操作のトラブルシューティング](operations-troubleshooting-medv2.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2d648-136">**Note** If you encounter any problems when verifying your first time setup settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

 

<span data-ttu-id="2d648-137">初めてセットアップしたときの設定が正しいことを確認したら、他の MED-V ワークスペースの構成をテストして、アプリケーションの発行や URL のリダイレクションなど、意図したとおりに機能するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="2d648-137">After you have verified that your first time setup settings are correct, you can test other MED-V workspace configurations to verify that they function as intended, such as application publishing and URL redirection.</span></span>

<span data-ttu-id="2d648-138">MED-V ワークスペースパッケージのテストがすべて完了し、意図したとおりに機能していることを確認したら、MED-V ワークスペースを企業に展開できます。</span><span class="sxs-lookup"><span data-stu-id="2d648-138">After you have completed all testing of your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="2d648-139">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2d648-139">Related topics</span></span>


[<span data-ttu-id="2d648-140">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="2d648-140">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="2d648-141">URL のリダイレクトをテストする方法</span><span class="sxs-lookup"><span data-stu-id="2d648-141">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="2d648-142">MED-V ワークスペース パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="2d648-142">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

[<span data-ttu-id="2d648-143">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="2d648-143">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





