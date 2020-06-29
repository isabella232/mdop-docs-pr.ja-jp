---
title: MED-V ホスト エージェントを手動でインストールする方法
description: MED-V ホスト エージェントを手動でインストールする方法
author: dansimp
ms.assetid: 4becc90b-6481-4e1f-a4d3-aec74c8821ec
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a7fb44b23a390cf394af2331152955afc2d8eba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812898"
---
# <span data-ttu-id="53c09-103">MED-V ホスト エージェントを手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="53c09-103">How to Manually Install the MED-V Host Agent</span></span>


<span data-ttu-id="53c09-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 ソリューションに関連するコンポーネントは2つありますが、MED-V Host Agent とゲストエージェントの2つは関連しています。</span><span class="sxs-lookup"><span data-stu-id="53c09-104">There are two separate but related components to the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="53c09-105">ホストエージェントはホストコンピューター (Windows 7 を実行しているユーザーのコンピューター) にあり、チャネルを提供して、ホストコンピューターで実行されている MED-V ゲスト (MED-V 仮想マシン) と通信します。</span><span class="sxs-lookup"><span data-stu-id="53c09-105">The Host Agent resides on the host computer (a user’s computer that is running Windows 7) and provides a channel to communicate with the MED-V guest (the MED-V virtual machine running in the host computer).</span></span> <span data-ttu-id="53c09-106">また、アプリケーションの発行などの一部の MED-V 関連機能も提供します。</span><span class="sxs-lookup"><span data-stu-id="53c09-106">It also provides certain MED-V related functionality, such as application publishing.</span></span>

<span data-ttu-id="53c09-107">通常は、会社の推奨されるプロビジョニング方法を使用して、MED-V Host Agent を展開してインストールします。</span><span class="sxs-lookup"><span data-stu-id="53c09-107">Typically, you deploy and install the MED-V Host Agent by using your company’s preferred method of provisioning software.</span></span> <span data-ttu-id="53c09-108">ただし、企業全体で MED-V を展開する前に、テストのためにホストエージェントをローカルにインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="53c09-108">However, before deploying MED-V across your enterprise, you might prefer to install the Host Agent locally for testing.</span></span> <span data-ttu-id="53c09-109">このセクションでは、MED-V Host Agent を手動でインストールするためのステップバイステップの手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="53c09-109">This section provides step-by-step instructions for manually installing the MED-V Host Agent.</span></span>

<span data-ttu-id="53c09-110">**注** MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="53c09-110">**Note** The MED-V Guest Agent is installed automatically during first time setup.</span></span>

 

<span data-ttu-id="53c09-111">**重要** MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="53c09-111">**Important** Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="53c09-112">また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="53c09-112">You can also do this by specifying a computer restart during a distribution.</span></span>

 

**<span data-ttu-id="53c09-113">MED-V ホストエージェントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="53c09-113">To install the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="53c09-114">ソフトウェアダウンロードの一部として受信した MED-V インストールファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="53c09-114">Locate the MED-V installation files that you received as part of your software download.</span></span>

2.  <span data-ttu-id="53c09-115">MED-V \ _HostAgent \ _Setup インストールファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="53c09-115">Double-click the MED-V\_HostAgent\_Setup installation file.</span></span>

    <span data-ttu-id="53c09-116">**Microsoft Enterprise デスクトップ仮想化 (med-v) Host Agent セットアップ**ウィザードが開きます。</span><span class="sxs-lookup"><span data-stu-id="53c09-116">The **Microsoft Enterprise Desktop Virtualization (MED-V) Host Agent Setup** wizard opens.</span></span> <span data-ttu-id="53c09-117">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="53c09-117">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="53c09-118">Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53c09-118">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

4.  <span data-ttu-id="53c09-119">MED-V ホストエージェントをインストールするための移動先フォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="53c09-119">Select the destination folder for installing the MED-V Host Agent.</span></span> <span data-ttu-id="53c09-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53c09-120">Click **Next**.</span></span>

5.  <span data-ttu-id="53c09-121">ホストエージェントのインストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53c09-121">To begin the Host Agent installation, click **Install**.</span></span>

6.  <span data-ttu-id="53c09-122">インストールが正常に完了したら、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="53c09-122">After the installation is completed successfully, click **Finish** to close the wizard.</span></span>

    <span data-ttu-id="53c09-123">ホストエージェントが正常にインストールされたことを確認するには、[**スタート**]、[**すべてのプログラム**]、[ **Microsoft Enterprise デスクトップ仮想化**]、[ **med-v Host Agent**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="53c09-123">To verify that the installation of the Host Agent was successful, click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="53c09-124">**注** MED-V ワークスペースをインストールするまでは、MED-V ホストエージェントを起動して実行できますが、機能は提供されません。</span><span class="sxs-lookup"><span data-stu-id="53c09-124">**Note** Until a MED-V workspace is installed, the MED-V Host Agent can be started and runs, but provides no functionality.</span></span>

 

## <span data-ttu-id="53c09-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="53c09-125">Related topics</span></span>


[<span data-ttu-id="53c09-126">電子ソフトウェア配布システムによって MED-V コンポーネントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="53c09-126">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md)

[<span data-ttu-id="53c09-127">MED-V ワークスペース パッケージ ツールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="53c09-127">How to Install the MED-V Workspace Packager</span></span>](how-to-install-the-med-v-workspace-packager.md)

[<span data-ttu-id="53c09-128">MED-V コンポーネントをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="53c09-128">How to Uninstall the MED-V Components</span></span>](how-to-uninstall-the-med-v-components.md)

 

 





