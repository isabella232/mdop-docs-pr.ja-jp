---
title: MED-V ワークスペースを手動で展開する方法
description: MED-V ワークスペースを手動で展開する方法
author: dansimp
ms.assetid: 94bfb209-2230-49b6-bb40-9c6ab088dbf4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f13d06e2232681f87df7a71b9a3ef3269b4f9ce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827277"
---
# <span data-ttu-id="6a259-103">MED-V ワークスペースを手動で展開する方法</span><span class="sxs-lookup"><span data-stu-id="6a259-103">How to Deploy a MED-V Workspace Manually</span></span>


<span data-ttu-id="6a259-104">場合によっては、会社が電子ソフトウェア配布システムを使用してアプリケーションを展開していない場合などに、手動で MED-V のワークスペースを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="6a259-104">In some instances, you might want to deploy your MED-V workspace manually, for example, if your company does not use an electronic software distribution system to deploy applications.</span></span>

<span data-ttu-id="6a259-105">このセクションでは、MED-V ワークスペースを手動で展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6a259-105">This section provides instruction about how to manually deploy a MED-V workspace.</span></span>

**<span data-ttu-id="6a259-106">MED-V ワークスペースを手動で展開するには</span><span class="sxs-lookup"><span data-stu-id="6a259-106">To deploy a MED-V workspace manually</span></span>**

1.  <span data-ttu-id="6a259-107">すべての必須アプリケーションと MED-V ワークスペースパッケージファイルを共有ドライブまたは DVD にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6a259-107">Copy all prerequisite applications and the MED-V workspace package files to a shared drive or to a DVD.</span></span> <span data-ttu-id="6a259-108">必要なアプリケーションとファイルの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6a259-108">The following is a list of the required applications and files.</span></span>

    -   <span data-ttu-id="6a259-109">**Windows 仮想 PC**。</span><span class="sxs-lookup"><span data-stu-id="6a259-109">**Windows Virtual PC**.</span></span> <span data-ttu-id="6a259-110">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a259-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="6a259-111">**Windows VIRTUAL PC の追加と更新**。</span><span class="sxs-lookup"><span data-stu-id="6a259-111">**Windows Virtual PC Additions and Updates**.</span></span> <span data-ttu-id="6a259-112">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6a259-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="6a259-113">**Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a259-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span>

        **<span data-ttu-id="6a259-114">Warning</span><span class="sxs-lookup"><span data-stu-id="6a259-114">Warning</span></span>**  
        <span data-ttu-id="6a259-115">MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6a259-115">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="6a259-116">また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="6a259-116">You can also do this by specifying a computer restart during a distribution.</span></span>



~~~
-   **MED-V Workspace Installer, VHD, and Setup Executable** – created with the **MED-V Workspace Packager**. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    **Important**  
    The compressed VHD file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.
~~~



2. <span data-ttu-id="6a259-117">記載されている順序に従って、以下をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6a259-117">Install the following in the order listed.</span></span> <span data-ttu-id="6a259-118">エンドユーザーは、この作業を手動で実行するか、または次のようなスクリプトを作成してインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="6a259-118">The end user can perform this task manually or you can create a script to install the following:</span></span>

   -   <span data-ttu-id="6a259-119">Windows 仮想 pc と Windows 仮想 PC の追加と更新。</span><span class="sxs-lookup"><span data-stu-id="6a259-119">Windows Virtual PC and the Windows Virtual PC additions and updates.</span></span> <span data-ttu-id="6a259-120">コンピューターの再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="6a259-120">A computer restart is required.</span></span>

   -   <span data-ttu-id="6a259-121">MED-V ホストエージェント。</span><span class="sxs-lookup"><span data-stu-id="6a259-121">The MED-V Host Agent.</span></span>

       **<span data-ttu-id="6a259-122">注</span><span class="sxs-lookup"><span data-stu-id="6a259-122">Note</span></span>**  
       <span data-ttu-id="6a259-123">実行されている場合は、MED-V Host Agent のインストールが終了する前に、Internet Explorer を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6a259-123">If it is running, Internet Explorer must be restarted before the installation of the MED-V Host Agent can finish.</span></span>



~~~
-   The MED-V workspace package.

    Install the MED-V workspace by running the setup.exe program that is included in the MED-V workspace package files.
~~~

3. <span data-ttu-id="6a259-124">初回のセットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="6a259-124">Complete first time setup.</span></span>

   <span data-ttu-id="6a259-125">MED-V ワークスペースをインストールした後、MED-V を開始するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="6a259-125">After the MED-V workspace is installed, you have the option of starting MED-V.</span></span> <span data-ttu-id="6a259-126">これにより、MED-V ホストエージェントが開始されます。</span><span class="sxs-lookup"><span data-stu-id="6a259-126">This starts the MED-V Host Agent.</span></span> <span data-ttu-id="6a259-127">この時点で MED-V を開始するか、または後で MED-V Host Agent を起動して初めてセットアップを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="6a259-127">You can either start MED-V at that time, or start the MED-V Host Agent later to complete first time setup.</span></span>

   <span data-ttu-id="6a259-128">MED-V Host Agent を起動するには、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v host agent**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="6a259-128">To start the MED-V Host Agent, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

## <span data-ttu-id="6a259-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6a259-129">Related topics</span></span>


[<span data-ttu-id="6a259-130">電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6a259-130">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="6a259-131">Windows 7 イメージで MED-V ワークスペースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6a259-131">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)

[<span data-ttu-id="6a259-132">MED-V ワークスペース パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="6a259-132">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)









