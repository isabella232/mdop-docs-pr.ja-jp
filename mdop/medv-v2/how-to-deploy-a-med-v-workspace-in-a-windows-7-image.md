---
title: Windows 7 イメージで MED-V ワークスペースを展開する方法
description: Windows 7 イメージで MED-V ワークスペースを展開する方法
author: dansimp
ms.assetid: a83aba4e-8681-4906-9872-f431c0bb15f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49dd796d6f6af425b9000b595a0d828c3cb0035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827284"
---
# <span data-ttu-id="cf0a6-103">Windows 7 イメージで MED-V ワークスペースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="cf0a6-103">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>


<span data-ttu-id="cf0a6-104">Windows 7 の新規インストールと同じように、企業全体に配布する Windows 7 イメージに、すべての MED-V コンポーネントをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-104">You can install all the MED-V components into a Windows 7 image that you distribute throughout your enterprise just as you would any new installation of Windows 7.</span></span> <span data-ttu-id="cf0a6-105">エンドユーザーは、MED-V を開始するように構成した [**スタート**] メニューのショートカットをクリックして、med-v ワークスペースのインストールを終了します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-105">The end user then finishes the installation of the MED-V workspace by clicking a **Start** menu shortcut that you configure to start MED-V.</span></span> <span data-ttu-id="cf0a6-106">セットアップが初めて開始され、エンドユーザーが指示に従って構成を完了します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-106">First time setup starts and the end user follows the instructions to complete the configuration.</span></span>

<span data-ttu-id="cf0a6-107">以下のセクションでは、Windows 7 のイメージを使用して、企業全体で MED-V ワークスペースを展開するのに役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-107">The following section provides information and instructions to help you deploy the MED-V workspace throughout your enterprise by using a Windows 7 image.</span></span>

**<span data-ttu-id="cf0a6-108">Windows 7 イメージで MED-V ワークスペースを展開するには</span><span class="sxs-lookup"><span data-stu-id="cf0a6-108">To deploy a MED-V workspace in a Windows 7 image</span></span>**

1.  <span data-ttu-id="cf0a6-109">Windows 7 の標準イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-109">Create a standard image of Windows 7.</span></span> <span data-ttu-id="cf0a6-110">詳細については、「 [Windows 7 の標準イメージの構築: ステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=204843)()」を参照してください https://go.microsoft.com/fwlink/?LinkId=204843) 。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-110">For more information, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=204843) (https://go.microsoft.com/fwlink/?LinkId=204843).</span></span>

2.  <span data-ttu-id="cf0a6-111">Windows 7 の画像で、windows Virtual PC と Windows 仮想 PC の更新プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-111">In the Windows 7 image, install Windows Virtual PC and the Windows Virtual PC updates.</span></span> <span data-ttu-id="cf0a6-112">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

3.  <span data-ttu-id="cf0a6-113">MED-V \ _HostAgent \ _Setup インストールファイルを使用して、MED-V ホストエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-113">Install the MED-V Host Agent by using the MED-V\_HostAgent\_Setup installation file.</span></span> <span data-ttu-id="cf0a6-114">詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    <span data-ttu-id="cf0a6-115">**警告** MED-V ホストエージェントをインストールする前に、Internet Explorer を閉じておく必要があります。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-115">**Warning** Internet Explorer must be closed before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="cf0a6-116">また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-116">You can also do this by specifying a computer restart during a distribution.</span></span>

     

4.  <span data-ttu-id="cf0a6-117">MED-V ワークスペースパッケージファイルを Windows 7 イメージにコピーします。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-117">Copy the MED-V workspace package files to the Windows 7 image.</span></span> <span data-ttu-id="cf0a6-118">MED-V ワークスペースパッケージファイルは、med-v workspace installer、medv ファイル、および**Med-v Workspace パッケージャー**を使って作成したファイルを setup.exe ます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-118">The MED-V workspace package files are the MED-V workspace installer, .medv file, and setup.exe file that you created by using the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="cf0a6-119">**重要** Medv ファイルと setup.exe ファイルは、MED-V workspace installer と同じフォルダーにある必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-119">**Important** The .medv and setup.exe file must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="cf0a6-120">次に、setup.exe を実行して、MED-V ワークスペースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-120">Then, install the MED-V workspace by running setup.exe.</span></span>

     

5.  <span data-ttu-id="cf0a6-121">[**スタート**] メニューのショートカットを構成して、med-v ワークスペースパッケージのインストールを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-121">Configure a shortcut on the **Start** menu to open the MED-V workspace package installation.</span></span>

    <span data-ttu-id="cf0a6-122">エンドユーザーが必要に応じて MED-V インストールを開始できるようにする、setup.exe ファイルへの [**スタート**] メニューのショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-122">Create a **Start** menu shortcut to the setup.exe file that lets the end user start a MED-V installation as required.</span></span>

6.  <span data-ttu-id="cf0a6-123">会社の標準的な画像展開プロセスを使用して、MED-V を必要とする企業内のコンピューターに Windows 7 イメージを配布します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-123">By using your company’s standard image deployment process, distribute the Windows 7 image to computers in your enterprise that require MED-V.</span></span>

<span data-ttu-id="cf0a6-124">エンドユーザーが、MED-V ワークスペースで公開されているアプリケーションにアクセスする必要がある場合、[**スタート**] メニューのショートカットをクリックして、med-v ワークスペースをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-124">When the end user has to access an application published in the MED-V workspace, they can click the **Start** menu shortcut to install the MED-V workspace.</span></span> <span data-ttu-id="cf0a6-125">これにより、初回のセットアップが自動的に開始され、MED-V の構成が完了します。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-125">This automatically starts first time setup and completes the configuration of MED-V.</span></span> <span data-ttu-id="cf0a6-126">セットアップの初回完了後、エンドユーザーは [**スタート**] メニューの med-v アプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf0a6-126">After first time setup is complete, the end user can access the MED-V applications on the **Start** menu.</span></span>

## <span data-ttu-id="cf0a6-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cf0a6-127">Related topics</span></span>


[<span data-ttu-id="cf0a6-128">MED-V 2.0 展開の概要</span><span class="sxs-lookup"><span data-stu-id="cf0a6-128">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="cf0a6-129">電子ソフトウェア配布システムによって MED-V ワークスペースを展開する方法</span><span class="sxs-lookup"><span data-stu-id="cf0a6-129">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)

 

 





