---
title: MED-V ワークスペース パッケージ ツールをインストールする方法
description: MED-V ワークスペース パッケージ ツールをインストールする方法
author: dansimp
ms.assetid: 627478e9-6798-4b32-9a50-7a1b72bea295
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e23492852813752f028ae2201e656162d6189642
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824847"
---
# <span data-ttu-id="df54b-103">MED-V ワークスペース パッケージ ツールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="df54b-103">How to Install the MED-V Workspace Packager</span></span>


<span data-ttu-id="df54b-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 には、 **Med-v ワークスペースのパッケージャー**が含まれています。これは、エンドユーザーに配布される med-v ワークスペース展開パッケージの作成に、デスクトップ管理者が使用します。</span><span class="sxs-lookup"><span data-stu-id="df54b-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 includes a **MED-V Workspace Packager**, which the desktop administrator uses to create the MED-V workspace deployment packages that are distributed to the end users.</span></span> <span data-ttu-id="df54b-105">このパッケージャーでは、MED-V ワークスペースの作成方法と、プロセスに役立つウィザードが含まれています。</span><span class="sxs-lookup"><span data-stu-id="df54b-105">The packager provides step-by-step guidance on how to create MED-V workspaces and contains wizards that help in the process.</span></span>

<span data-ttu-id="df54b-106">**重要** ウィザードの実行を開始する前に、インストールするための準備ができている VHD を確認してください。</span><span class="sxs-lookup"><span data-stu-id="df54b-106">**Important** Before you start to run the wizards, make sure that you have a prepared VHD ready to install.</span></span> <span data-ttu-id="df54b-107">詳細については、「 [Med-v イメージを準備する](prepare-a-med-v-image.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="df54b-107">For more information, see [Prepare a MED-V Image](prepare-a-med-v-image.md).</span></span>

 

<span data-ttu-id="df54b-108">このセクションでは、 **Med-v ワークスペースパッケージャー**をインストールまたは修復するためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="df54b-108">This section provides step-by-step instructions for installing or repairing the **MED-V Workspace Packager**.</span></span>

**<span data-ttu-id="df54b-109">MED-V ワークスペースのパッケージャーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="df54b-109">To install the MED-V Workspace Packager</span></span>**

1.  <span data-ttu-id="df54b-110">ソフトウェアダウンロードの一部として受信した MED-V インストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="df54b-110">Locate the MED-V installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="df54b-111">MED-V \ _WorkspacePackager \ _Setup インストールファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-111">Double-click the MED-V\_WorkspacePackager\_Setup installation file.</span></span>

    <span data-ttu-id="df54b-112">**Microsoft Enterprise デスクトップ仮想化 (med-v) ワークスペースのパッケージャーのセットアップ**ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="df54b-112">The **Microsoft Enterprise Desktop Virtualization (MED-V) Workspace Packager Setup** wizard opens.</span></span> <span data-ttu-id="df54b-113">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="df54b-113">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="df54b-114">Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-114">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="df54b-115">MED-V Workspace パッケージャーをインストールするための移動先フォルダーを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-115">Select the destination folder for installing the MED-V Workspace Packager, and then click **Next**.</span></span>

5.  <span data-ttu-id="df54b-116">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-116">To begin the installation, click **Install**.</span></span>

6.  <span data-ttu-id="df54b-117">インストールが正常に完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="df54b-117">After the installation is completed successfully, click **Finish** to close the wizard.</span></span>

    <span data-ttu-id="df54b-118">パッケージャーが正常にインストールされたことを確認するには、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**] の順にクリックして、[ **med-v Workspace パッケージャー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-118">To verify that the installation of the packager was successful, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager.**</span></span>

    <span data-ttu-id="df54b-119">**Med-v Workspace パッケージャー**の使い方について詳しくは、「 [Med-v ワークスペースパッケージを作成](create-a-med-v-workspace-package.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="df54b-119">For information about how to use the **MED-V Workspace Packager**, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

<span data-ttu-id="df54b-120">パッケージャーが予期したとおりに開かない場合は、インストールの修復を試みることができます。</span><span class="sxs-lookup"><span data-stu-id="df54b-120">If the packager does not open as expected, you can try to repair the installation.</span></span>

**<span data-ttu-id="df54b-121">MED-V Workspace のパッケージャーインストールを修復するには</span><span class="sxs-lookup"><span data-stu-id="df54b-121">To repair the MED-V Workspace Packager installation</span></span>**

1.  <span data-ttu-id="df54b-122">MED-V \ _WorkspacePackager \ _Setup インストールファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-122">Double-click the MED-V\_WorkspacePackager\_Setup installation file.</span></span>

    <span data-ttu-id="df54b-123">**Microsoft Enterprise デスクトップ仮想化 (med-v) ワークスペースのパッケージャーのセットアップ**ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="df54b-123">The **Microsoft Enterprise Desktop Virtualization (MED-V) Workspace Packager Setup** wizard opens.</span></span> <span data-ttu-id="df54b-124">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="df54b-124">Click **Next** to continue.</span></span>

2.  <span data-ttu-id="df54b-125">インストールで発生した可能性のあるエラーを修復するには、[**修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-125">To repair errors that might have occurred in the installation, click **Repair**.</span></span>

3.  <span data-ttu-id="df54b-126">修復処理を開始するには、もう一度 [**修復**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-126">To begin the repair process, click **Repair** again.</span></span>

4.  <span data-ttu-id="df54b-127">修復が正常に完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="df54b-127">After the repair is completed successfully, click **Finish** to close the wizard.</span></span>

    <span data-ttu-id="df54b-128">パッケージャーの修復が成功したことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Workspace パッケージャー** ] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="df54b-128">To verify that the repair of the packager was successful, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Workspace Packager.**</span></span>

## <span data-ttu-id="df54b-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="df54b-129">Related topics</span></span>


[<span data-ttu-id="df54b-130">MED-V ホスト エージェントを手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="df54b-130">How to Manually Install the MED-V Host Agent</span></span>](how-to-manually-install-the-med-v-host-agent.md)

[<span data-ttu-id="df54b-131">MED-V コンポーネントをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="df54b-131">How to Uninstall the MED-V Components</span></span>](how-to-uninstall-the-med-v-components.md)

 

 





