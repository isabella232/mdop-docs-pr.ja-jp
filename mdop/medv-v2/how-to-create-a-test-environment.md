---
title: テスト環境を作成する方法
description: テスト環境を作成する方法
author: dansimp
ms.assetid: a0db2299-16f3-4516-8769-7d55ca4a1e98
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ee2ab131f6003b56cce7a60ffea1cd00b067fae3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827287"
---
# <span data-ttu-id="33277-103">テスト環境を作成する方法</span><span class="sxs-lookup"><span data-stu-id="33277-103">How to Create a Test Environment</span></span>


<span data-ttu-id="33277-104">エンタープライズ全体で展開する前に、MED-V ワークスペースパッケージをローカルでテストするために使用できるテスト環境を作成するための手順と手順を以下に示します。</span><span class="sxs-lookup"><span data-stu-id="33277-104">The following are some steps and instructions to help you create a test environment that you can use to test your MED-V workspace package locally before deploying it throughout your enterprise.</span></span> <span data-ttu-id="33277-105">このセクションでは、手動で、または電子ソフトウェア配布システムを使用して、テスト環境を作成する方法に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="33277-105">This section provides guidance about how to create a test environment, either manually or by using an electronic software distribution system.</span></span>

**<span data-ttu-id="33277-106">ESD を使ってテスト環境を作成するには</span><span class="sxs-lookup"><span data-stu-id="33277-106">To create a test environment by using an ESD</span></span>**

1.  <span data-ttu-id="33277-107">組織全体でソフトウェアを展開する方法を使用して、次の必要なコンポーネントをテストコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="33277-107">Use your company’s method of deploying software throughout the enterprise to deploy the following necessary components to a test computer.</span></span> <span data-ttu-id="33277-108">次の順序でインストールします。</span><span class="sxs-lookup"><span data-stu-id="33277-108">Install them in the following order:</span></span>

    -   <span data-ttu-id="33277-109">**Windows VIRTUAL PC** –まだインストールされていない場合。</span><span class="sxs-lookup"><span data-stu-id="33277-109">**Windows Virtual PC** – if not already installed.</span></span> <span data-ttu-id="33277-110">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="33277-111">**Windows VIRTUAL PC の追加と更新プログラム**(まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="33277-111">**Windows Virtual PC Additions and Updates**– if not already installed.</span></span> <span data-ttu-id="33277-112">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="33277-113">**Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="33277-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="33277-114">詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    -   <span data-ttu-id="33277-115">Med-v ワークスペースの**インストーラー、VHD、セットアップの実行可能ファイル**( **med-v workspace パッケージャー**で作成)</span><span class="sxs-lookup"><span data-stu-id="33277-115">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="33277-116">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-116">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        <span data-ttu-id="33277-117">**重要** VHD とセットアップの実行可能プログラムは、MED-V ワークスペースインストーラーと同じフォルダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33277-117">**Important** The VHD and Setup executable program must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="33277-118">次に、setup.exe を実行して、MED-V ワークスペースインストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="33277-118">Then, install the MED-V workspace installer by running setup.exe.</span></span>

         

2.  <span data-ttu-id="33277-119">すべてのコンポーネントをテストコンピューターにインストールしたら、MED-V Host Agent を実行して、初回のセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="33277-119">After all of the components are installed on the test computer, run the MED-V Host Agent to start first time setup.</span></span>

    <span data-ttu-id="33277-120">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="33277-120">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

    <span data-ttu-id="33277-121">**注** テストコンピューターで MED-V ホストエージェントを物理的に実行できない場合、次にコンピューターを再起動したときに、最初にセットアップが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="33277-121">**Note** If you cannot physically run the MED-V Host Agent on the test computer, first time setup starts automatically the next time that the computer restarts.</span></span>

     

<span data-ttu-id="33277-122">セットアップが初めて開始され、10分以上かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="33277-122">First time setup starts and can take ten minutes or more to finish.</span></span>

<span data-ttu-id="33277-123">セットアップの初回実行時に構成設定をテストする方法については、「[初回のセットアップ設定を確認する方法](how-to-verify-first-time-setup-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-123">For information about testing your configuration settings when first time setup is running, see [How to Verify First Time Setup Settings](how-to-verify-first-time-setup-settings.md).</span></span>

**<span data-ttu-id="33277-124">テスト環境を手動で作成するには</span><span class="sxs-lookup"><span data-stu-id="33277-124">To create a test environment manually</span></span>**

1.  <span data-ttu-id="33277-125">Windows 仮想 PC (追加と更新プログラム付き) などの MED-V の前提条件を含む、med-v ホストエージェントをローカルテスト環境にインストールします。</span><span class="sxs-lookup"><span data-stu-id="33277-125">Install the MED-V Host Agent in a local test environment that includes MED-V prerequisites, such as Windows Virtual PC with additions and updates.</span></span> <span data-ttu-id="33277-126">詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="33277-126">For information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

2.  <span data-ttu-id="33277-127">MED-V ワークスペースファイルをテスト環境にコピーします。</span><span class="sxs-lookup"><span data-stu-id="33277-127">Copy the MED-V workspace files to your test environment.</span></span> <span data-ttu-id="33277-128">MED-V ワークスペースファイルは、 **Med-v ワークスペースパッケージャー**で指定した移動先フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="33277-128">The MED-V workspace files are located in the destination folder that you specified in the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="33277-129">**重要** VHD とセットアップの実行可能プログラムは、MED-V ワークスペースインストーラーとしてテスト環境の同じフォルダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="33277-129">**Important** The VHD and Setup executable program must be in the same folder on your test environment as the MED-V workspace installer.</span></span>

     

3.  <span data-ttu-id="33277-130">setup.exe を実行して、MED-V ワークスペースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="33277-130">Install the MED-V workspace by running setup.exe.</span></span>

4.  <span data-ttu-id="33277-131">MED-V ホストエージェントを実行して、初めてセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="33277-131">Start first time setup by running the MED-V Host Agent.</span></span>

    <span data-ttu-id="33277-132">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="33277-132">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="33277-133">初めてセットアップを開始したときに、指定した VHD のサイズによっては、完了まで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="33277-133">First time setup starts and might take several minutes to complete, depending on the size of the VHD specified.</span></span>

<span data-ttu-id="33277-134">これで、MED-V ワークスペースで指定した構成、アプリケーション発行、URL リダイレクションのさまざまな設定をテストする準備が整いました。</span><span class="sxs-lookup"><span data-stu-id="33277-134">You are now ready to test the different settings for configuration, application publishing, and URL redirection that you specified for your MED-V workspace.</span></span>

<span data-ttu-id="33277-135">**注** 既定では、MED-V はゲストの画面ロックポリシーを上書きします。</span><span class="sxs-lookup"><span data-stu-id="33277-135">**Note** By default, MED-V overrides the screen lock policy in the guest.</span></span> <span data-ttu-id="33277-136">ただし、ホストコンピューターは画面ロックポリシーを引き続き受け入れているため、これによってセキュリティの問題が発生することはありません。</span><span class="sxs-lookup"><span data-stu-id="33277-136">However, this does not pose a security problem because the host computer still honors the screen lock policy.</span></span>

 

## <span data-ttu-id="33277-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="33277-137">Related topics</span></span>


[<span data-ttu-id="33277-138">初回使用時のセットアップの設定を確認する方法</span><span class="sxs-lookup"><span data-stu-id="33277-138">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="33277-139">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="33277-139">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="33277-140">URL のリダイレクトをテストする方法</span><span class="sxs-lookup"><span data-stu-id="33277-140">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

 

 





