---
title: MED-V 2.0 のエンド ツー エンドの操作シナリオ
description: MED-V 2.0 のエンド ツー エンドの操作シナリオ
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826167"
---
# <span data-ttu-id="299ae-103">MED-V 2.0 のエンド ツー エンドの操作シナリオ</span><span class="sxs-lookup"><span data-stu-id="299ae-103">End-to-End Operations Scenario for MED-V 2.0</span></span>


<span data-ttu-id="299ae-104">このサンプルシナリオ Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 では、複数のシナリオをエンドツーエンドで使用して、MED-V の展開と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="299ae-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy and manage MED-V by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="299ae-105">このサンプルシナリオは、個々のシナリオと手順をコンテキストにまとめる際に役立つケーススタディと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="299ae-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="299ae-106">このセクションでは、企業内のエンドツーエンドのソリューションとして、MED-V ワークスペースを作成、展開、および管理するための基本的な情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-106">This section provides basic information and directions for creating, deploying, and managing MED-V workspaces as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="299ae-107">MED-V 操作のステップバイステップのシナリオ</span><span class="sxs-lookup"><span data-stu-id="299ae-107">MED-V Operations Step-by-step Scenario</span></span>


<span data-ttu-id="299ae-108">MED-V 操作シナリオで実行するステップバイステップの手順には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="299ae-108">The step-by-step procedures that you follow in a MED-V operations scenario include the following:</span></span>

-   <span data-ttu-id="299ae-109">[Med-v の Windows 仮想 Pc イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)Med-v の WINDOWS 仮想 pc イメージを作成して構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-109">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc) reviews how to create and configure a Windows Virtual PC image for MED-V.</span></span> <span data-ttu-id="299ae-110">MED-V ワークスペースをユーザーに提供する前に、med-v の MED-V workspace installer パッケージを作成するために使用する仮想ハードディスク (VHD) を準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="299ae-110">Before you can deliver a MED-V workspace to users, you must first prepare a virtual hard disk (VHD) that you use to build the MED-V workspace installer package for MED-V.</span></span>

-   <span data-ttu-id="299ae-111">[Med-v 用の Windows 仮想 Pc イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)WINDOWS 仮想 pc イメージに WINDOWS XP SP3 オペレーティングシステムをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-111">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc) reviews how to install the Windows XP SP3 operating system on your Windows Virtual PC image.</span></span> <span data-ttu-id="299ae-112">MED を使用するには、MED-V ワークスペースを構築する前に windows の仮想 PC のイメージに Windows XP SP3 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="299ae-112">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

-   <span data-ttu-id="299ae-113">[Med-v 用の Windows 仮想 Pc イメージを作成する-](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet) .net FRAMEWORK 3.5 SP1 と更新 KB959209 を手動でインストールして、med-v で使用するための準備をする WINDOWS 仮想 pc のイメージにする方法を確認します。</span><span class="sxs-lookup"><span data-stu-id="299ae-113">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet) reviews how to manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="299ae-114">MED には、.NET Framework 3.5 SP1 と update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) ( https://go.microsoft.com/fwlink/?LinkId=204950) いくつかの既知のアプリケーション互換性の問題に対処します) が必要です。</span><span class="sxs-lookup"><span data-stu-id="299ae-114">MED-V requires the .NET Framework 3.5 SP1, and the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

-   <span data-ttu-id="299ae-115">[Med-v 用の Windows 仮想 PC イメージの作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)windows XP イメージを更新して、最新のソフトウェア更新プログラムや、med-v の実行に必要な、または重要な修正プログラムを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-115">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc) reviews how to update your Windows XP image with the latest software updates and other hotfixes necessary or important for running MED-V.</span></span>

-   <span data-ttu-id="299ae-116">[Med-v の Windows 仮想 PC イメージを作成](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)すると、windows XP のイメージに統合コンポーネントパッケージをインストールする方法がレビューされます。</span><span class="sxs-lookup"><span data-stu-id="299ae-116">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration) reviews how to install the integration components package in your Windows XP image.</span></span> <span data-ttu-id="299ae-117">これらの機能を使うと、仮想環境と物理コンピューターの間の対話性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="299ae-117">These provide features that improve the interaction between the virtual environment and the physical computer.</span></span>

-   <span data-ttu-id="299ae-118">[Windows 仮想 PC のイメージにアプリケーションをインストール](installing-applications-on-a-windows-virtual-pc-image.md)すると、電子ソフトウェアの配布システムやウイルス対策ソフトウェアなど、med-v の実行時に役立つ windows XP イメージに特定の種類のソフトウェアをインストールする方法が確認されます。</span><span class="sxs-lookup"><span data-stu-id="299ae-118">[Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md) reviews how you can install certain kinds of software on your Windows XP image that are helpful when you are running MED-V, such as an electronic software distribution system and antivirus software.</span></span>

-   <span data-ttu-id="299ae-119">[Windows 仮想 PC イメージを med-v で構成](configuring-a-windows-virtual-pc-image-for-med-v.md)すると、Sysprep を使用してイメージを構成し、med-v で使用できる状態になっていることを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-119">[Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md) discusses how to configure the image by using Sysprep to make sure that it is ready for use with MED-V.</span></span> <span data-ttu-id="299ae-120">次に、既成の MED-V イメージを使用して、MED-V ワークスペースパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="299ae-120">The prepared MED-V image is then used to create your MED-V workspace package.</span></span>

-   <span data-ttu-id="299ae-121">[Med-v ワークスペースパッケージを作成](create-a-med-v-workspace-package.md)する企業全体で展開する med-v ワークスペースパッケージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-121">[Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) reviews how to build the MED-V workspace package that you deploy throughout your enterprise.</span></span> <span data-ttu-id="299ae-122">MED-V ワークスペースパッケージを展開して、エンドユーザーのコンピューターに MED-V ワークスペースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="299ae-122">You deploy the MED-V workspace package to install the MED-V workspace on end-user computers.</span></span> <span data-ttu-id="299ae-123">MED-V ワークスペースとは、エンドユーザーが MED-V によって提供される仮想マシンとやり取りする Windows XP デスクトップ環境です。</span><span class="sxs-lookup"><span data-stu-id="299ae-123">A MED-V workspace is the Windows XP desktop environment from which end users interact with the virtual machine provided by MED-V.</span></span>

-   <span data-ttu-id="299ae-124">[Med-v Workspace パッケージをテスト](testing-the-med-v-workspace-package.md)することで、初回のセットアップ設定やアプリケーションの公開など、med-v ワークスペースパッケージの機能をテストできるテスト環境を作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-124">[Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md) discusses how to create a test environment in which you can test the functionality of the MED-V workspace package, such as first time setup settings and application publishing.</span></span> <span data-ttu-id="299ae-125">MED-V ワークスペースパッケージのテストが完了し、意図したとおりに機能していることを確認したら、エンタープライズ全体で展開できます。</span><span class="sxs-lookup"><span data-stu-id="299ae-125">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy it throughout your enterprise.</span></span>

-   <span data-ttu-id="299ae-126">[Med-v ワークスペースパッケージを展開](deploying-the-med-v-workspace-package.md)すると、電子ソフトウェアの配布システムまたは Windows 7 のイメージを使用して、med-v ワークスペースを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-126">[Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md) discusses how to deploy the MED-V workspace either by using an electronic software distribution system or in a Windows 7 image.</span></span> <span data-ttu-id="299ae-127">また、必要に応じて、MED-V ワークスペースを手動で展開する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-127">Or if you prefer, this section also shows you how you can deploy the MED-V workspace manually.</span></span>

-   <span data-ttu-id="299ae-128">[Med-v ワークスペースを監視](monitor-med-v-workspaces.md)する med-v ワークスペースの展開を監視して、初回のセットアップが正常に完了したかどうかを確認する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-128">[Monitor MED-V Workspaces](monitor-med-v-workspaces.md) reviews how to monitor the deployment of MED-V workspaces to determine whether first time setup completed successfully.</span></span> <span data-ttu-id="299ae-129">初回のセットアップが正常に完了するまでは、MED-V が使用可能な状態になっていないため、初回のセットアップの成功を監視することが重要です。</span><span class="sxs-lookup"><span data-stu-id="299ae-129">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has completed successfully.</span></span> <span data-ttu-id="299ae-130">このセクションでは、MED-V に影響を与える可能性があるネットワークの変更を検出するように環境をセットアップする方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-130">This section also shows you can set up your environment to detect those network changes that can affect MED-V.</span></span>

-   <span data-ttu-id="299ae-131">[Med-v ワークスペースアプリケーションを管理](manage-med-v-workspace-applications.md)する展開された med-v ワークスペースでアプリケーションをインストールして削除または公開し、発行を取り消す方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-131">[Manage MED-V Workspace Applications](manage-med-v-workspace-applications.md) reviews how to install and remove or publish and unpublish applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="299ae-132">このセクションでは、MED-V ワークスペースのソフトウェアを手動で更新する方法と自動更新を管理する方法についても説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-132">This section also shows how to manually update software in a MED-V workspace and how to manage automatic updates.</span></span> <span data-ttu-id="299ae-133">MED-V ワークスペースは、組織内の物理コンピューターとまったく同じように、自動ソフトウェア更新プロセスを管理する必要がある個別のオペレーティングシステムが含まれている仮想マシンです。</span><span class="sxs-lookup"><span data-stu-id="299ae-133">The MED-V workspace is a virtual machine that contains a separate operating system whose automatic software update process must be managed exactly like the physical computers in your enterprise.</span></span>

-   <span data-ttu-id="299ae-134">[MED-V URL リダイレクションを管理](manage-med-v-url-redirection.md)する展開された med-v ワークスペースで web アドレスリダイレクション設定を追加および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-134">[Manage MED-V URL Redirection](manage-med-v-url-redirection.md) reviews how to add and remove web address redirection settings on the deployed MED-V workspace.</span></span> <span data-ttu-id="299ae-135">レジストリから、または MED-V ワークスペースを再構築することで、URL リダイレクション情報を追加または削除できます。</span><span class="sxs-lookup"><span data-stu-id="299ae-135">You can add or remove URL redirection information through the registry or by rebuilding the MED-V workspace.</span></span> <span data-ttu-id="299ae-136">MED-V ワークスペースパッケージャーのウィザードを使用して、web アドレスリダイレクションを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="299ae-136">You can also use the wizard on the MED-V Workspace Packager to manage web address redirection.</span></span>

-   <span data-ttu-id="299ae-137">[Med-v のワークスペース設定を管理](manage-med-v-workspace-settings.md)する Med-v ワークスペースパッケージャーを使って、med-v 構成の設定を表示および編集する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="299ae-137">[Manage MED-V Workspace Settings](manage-med-v-workspace-settings.md) reviews how to view and edit MED-V configuration settings by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="299ae-138">このセクションには、すべての構成可能な MED-V レジストリキーの一覧と、それぞれの種類、既定値、説明が含まれています。</span><span class="sxs-lookup"><span data-stu-id="299ae-138">This section lists all the configurable MED-V registry keys and includes the type, default, and description of each.</span></span> <span data-ttu-id="299ae-139">このセクションには、MED-V ワークスペースでプリンターを管理する方法に関する情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="299ae-139">This section also includes information about how to manage printers in MED-V workspaces.</span></span> <span data-ttu-id="299ae-140">MED-V 2.0 では、プリンターリダイレクションによって、MED-V 仮想マシンとホストコンピューターの間で一貫した印刷操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="299ae-140">In MED-V 2.0, printer redirection gives users a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

## <span data-ttu-id="299ae-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="299ae-141">Related topics</span></span>


[<span data-ttu-id="299ae-142">MED-V の操作</span><span class="sxs-lookup"><span data-stu-id="299ae-142">Operations for MED-V</span></span>](operations-for-med-v.md)

[<span data-ttu-id="299ae-143">MED-V 2.0 のエンド ツー エンドのプランニング シナリオ</span><span class="sxs-lookup"><span data-stu-id="299ae-143">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="299ae-144">MED-V 2.0 のエンド ツー エンドの展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="299ae-144">End-to-End Deployment Scenario for MED-V 2.0</span></span>](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





