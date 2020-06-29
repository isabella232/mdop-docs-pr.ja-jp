---
title: MED-V 2.0 展開の概要
description: MED-V 2.0 展開の概要
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826107"
---
# <span data-ttu-id="3a0be-103">MED-V 2.0 展開の概要</span><span class="sxs-lookup"><span data-stu-id="3a0be-103">MED-V 2.0 Deployment Overview</span></span>


<span data-ttu-id="3a0be-104">このセクションでは、Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 をインストールして展開する方法に関する一般的な情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-104">This section provides general information and instructions about how to install and deploy Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="3a0be-105">概要</span><span class="sxs-lookup"><span data-stu-id="3a0be-105">Overview</span></span>


<span data-ttu-id="3a0be-106">MED-V 2.0 はアプリケーションモデルに基づくものであり、アプリケーションを展開するために使うメソッドを使用して、MED-V の展開と管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-106">MED-V 2.0 is based on an application model, where the same methods that you use to deploy applications can be used to deploy and manage MED-V.</span></span> <span data-ttu-id="3a0be-107">展開された MED-V ソリューションには、MED-V ホストエージェントとゲストエージェントの2つのコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-107">A deployed MED-V solution includes two components: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="3a0be-108">MED-V Host Agent は Windows 7 デスクトップ上にインストールされ、med-v ゲストエージェントは MED-V ワークスペース内の Windows XP にインストールされています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-108">The MED-V Host Agent is installed on the Windows 7 desktop and the MED-V Guest Agent is installed on Windows XP inside the MED-V workspace.</span></span> <span data-ttu-id="3a0be-109">Med-v には、med-v ワークスペースの作成と構成に必要な情報とツールを提供する MED-V Workspace パッケージャーも含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-109">MED-V also includes a MED-V Workspace Packager that provides the information and tools necessary for creating and configuring MED-V workspaces.</span></span>

**<span data-ttu-id="3a0be-110">重要</span><span class="sxs-lookup"><span data-stu-id="3a0be-110">Important</span></span>**  
<span data-ttu-id="3a0be-111">MED-V では、MED-V Workspace パッケージャー、MED-V ホストエージェント、およびすべてのユーザーの MED-V ワークスペースのインストールのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-111">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="3a0be-112">現在のユーザーの MED-V をインストールするには、 **ALLUSERS = ""** を選択します。コンポーネントのインストールと med-v ワークスペースのセットアップでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-112">Installing MED-V for the current user only by selecting **ALLUSERS=””** causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>



### <span data-ttu-id="3a0be-113">MED-V インストールファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-113">The MED-V Installation Files</span></span>

<span data-ttu-id="3a0be-114">MED には、MED-V の実行に必要な次のインストールファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-114">MED-V includes the following installation files, required for running MED-V:</span></span>

**<span data-ttu-id="3a0be-115">MED-V ホストエージェントインストールファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-115">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="3a0be-116">ホストエージェントのインストールファイルには、MED-V\_HostAgent\_Setup.exe という名前が付けられます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-116">The Host Agent installation file is named MED-V\_HostAgent\_Setup.exe.</span></span> <span data-ttu-id="3a0be-117">このファイルは、企業全体の MED-V の展開の一部として、関連する各エンドユーザーのコンピューターに配布され、インストールされます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-117">This file is distributed and installed on each relevant end-user computer as part of your enterprise-wide deployment of MED-V.</span></span>

**<span data-ttu-id="3a0be-118">MED-V ワークスペースパッケージャーインストールファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-118">The MED-V Workspace Packager Installation File</span></span>**

<span data-ttu-id="3a0be-119">MED-V Workspace パッケージャーのインストールファイルには、MED-V\_WorkspacePackager\_Setup.exe という名前が付いています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-119">The MED-V Workspace Packager installation file is named MED-V\_WorkspacePackager\_Setup.exe.</span></span> <span data-ttu-id="3a0be-120">このファイルを使用して、管理者の権限とアクセス許可を持っているコンピューターに、MED-V Workspace パッケージャーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-120">Use this file to install the MED-V Workspace Packager on a computer where you have administrator rights and permissions.</span></span> <span data-ttu-id="3a0be-121">デスクトップ管理者は、med-v ワークスペースパッケージャーを使って、MED-V ワークスペースの作成と管理を行います。</span><span class="sxs-lookup"><span data-stu-id="3a0be-121">The desktop administrator uses the MED-V Workspace Packager to create and manage MED-V workspaces.</span></span>

**<span data-ttu-id="3a0be-122">注</span><span class="sxs-lookup"><span data-stu-id="3a0be-122">Note</span></span>**  
<span data-ttu-id="3a0be-123">MED-V ゲストエージェントは、初回セットアップ時に自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-123">The MED-V Guest Agent is installed automatically during first time setup.</span></span>



### <span data-ttu-id="3a0be-124">MED-V 展開プロセス</span><span class="sxs-lookup"><span data-stu-id="3a0be-124">The MED-V Deployment Process</span></span>

<span data-ttu-id="3a0be-125">次に、MED-V のインストールと展開プロセスの概要を示します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-125">The following is a high-level overview of the MED-V installation and deployment process:</span></span>

1.  <span data-ttu-id="3a0be-126">管理者の資格情報を持ち、MED-V ワークスペースパッケージの構築に使用するコンピューターに、MED-V ワークスペースパッケージャーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-126">Install the MED-V Workspace Packager on the computer where you have administrative credentials and that you will be using to build the MED-V workspace packages.</span></span> <span data-ttu-id="3a0be-127">詳細については、「 [Med-v ワークスペースパッケージャーをインストールする方法](how-to-install-the-med-v-workspace-packager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-127">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

2.  <span data-ttu-id="3a0be-128">Med-v イメージを準備し、med-v ワークスペースパッケージャーを使って、MED-V ワークスペースパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-128">Prepare your MED-V image and create your MED-V workspace packages by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="3a0be-129">詳細については、「 [med-v の操作](operations-for-med-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-129">For more information, see [Operations for MED-V](operations-for-med-v.md).</span></span>

3.  <span data-ttu-id="3a0be-130">企業全体で必要な MED-V コンポーネントを展開します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-130">Deploy the required MED-V components throughout your enterprise.</span></span> <span data-ttu-id="3a0be-131">MED-V の必要なコンポーネントは、Windows 仮想 PC、MED-V ホストエージェント、および MED-V ワークスペースです。</span><span class="sxs-lookup"><span data-stu-id="3a0be-131">The required components of MED-V are Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span>

**<span data-ttu-id="3a0be-132">重要</span><span class="sxs-lookup"><span data-stu-id="3a0be-132">Important</span></span>**  
<span data-ttu-id="3a0be-133">MED-V コンポーネントをインストールするには、管理者の資格情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0be-133">Installation of the MED-V components requires administrative credentials.</span></span> <span data-ttu-id="3a0be-134">エンドユーザーが MED-V をインストールしている場合は、管理者資格情報を入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-134">If an end user is installing MED-V, they are prompted to enter administrative credentials.</span></span> <span data-ttu-id="3a0be-135">または、電子ソフトウェア配布 (ESD) システムを使用してインストールする場合は、コンテキストで管理者資格情報を提供できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-135">Alternately, administrative credentials can be provided in context if you are installing by using an electronic software distribution (ESD) system.</span></span>



### <span data-ttu-id="3a0be-136">MED-V コンポーネント</span><span class="sxs-lookup"><span data-stu-id="3a0be-136">The MED-V Components</span></span>

<span data-ttu-id="3a0be-137">エンタープライズ全体で展開する MED-V コンポーネントは、次のように構成されています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-137">The MED-V components that you deploy throughout your enterprise consist of the following:</span></span>

**<span data-ttu-id="3a0be-138">Windows 仮想 PC</span><span class="sxs-lookup"><span data-stu-id="3a0be-138">Windows Virtual PC</span></span>**

<span data-ttu-id="3a0be-139">互換性解決のために、Windows 仮想 PC イメージ内の MED-V 関数を使用します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-139">MED-V functions inside Windows Virtual PC images for its compatibility solution.</span></span> <span data-ttu-id="3a0be-140">Windows Virtual PC と Windows 7 用更新プログラム (KB977206) が必要です。</span><span class="sxs-lookup"><span data-stu-id="3a0be-140">Windows Virtual PC and the update for Windows 7 (KB977206) are required.</span></span> <span data-ttu-id="3a0be-141">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-141">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

**<span data-ttu-id="3a0be-142">MED-V ホストエージェントインストールファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-142">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="3a0be-143">MED-V\_HostAgent\_Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="3a0be-143">MED-V\_HostAgent\_Setup.exe.</span></span>

**<span data-ttu-id="3a0be-144">MED-V ワークスペースインストールファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-144">The MED-V Workspace Installation Files</span></span>**

<span data-ttu-id="3a0be-145">MED ワークスペースのインストールファイルは、次のように構成される MED-V workspace パッケージをビルドすると作成されます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-145">The MED-V workspace installation files are created when you build your MED-V workspace package that consists of the following:</span></span>

<span data-ttu-id="3a0be-146">MED-V ワークスペースインストールを実行する setup.exe 実行可能プログラム</span><span class="sxs-lookup"><span data-stu-id="3a0be-146">A setup.exe executable program that executes the MED-V workspace installation</span></span>

<span data-ttu-id="3a0be-147">&lt;Med-v (MED) _workspace \ _name &gt;</span><span class="sxs-lookup"><span data-stu-id="3a0be-147">A &lt;MED-V\_workspace\_name&gt;.msi installer</span></span>

<span data-ttu-id="3a0be-148">&lt; &gt; 圧縮された仮想ハードディスクである VHD \ _filename ファイル</span><span class="sxs-lookup"><span data-stu-id="3a0be-148">A &lt;VHD\_filename&gt;.medv file, which is the compressed virtual hard disk</span></span>

<span data-ttu-id="3a0be-149">構成設定用のファイル ( &lt; ワークスペース \ _name &gt; .reg と &lt; ワークスペース \ _name &gt; . ps1)</span><span class="sxs-lookup"><span data-stu-id="3a0be-149">The files for configuration settings (&lt;workspace\_name&gt;.reg and &lt;workspace\_name&gt;.ps1)</span></span>

<span data-ttu-id="3a0be-150">MED-V を展開するには、ホストコンピューターまたはホストコンピューターからアクセスできる共有に、必要なすべてのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-150">To deploy MED-V, copy all the required installation files to the host computer or to a share that can be accessed by the host computer.</span></span> <span data-ttu-id="3a0be-151">Windows Virtual PC、MED-V Host Agent、および MED-V ワークスペースのコンポーネントインストールファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-151">Run the component installation files for Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span> <span data-ttu-id="3a0be-152">次に、med-v ホストエージェントを起動して、MED-V の初回セットアップを完了します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-152">Then start the MED-V Host Agent to complete the first time setup of MED-V.</span></span>

<span data-ttu-id="3a0be-153">インストールは手動で実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-153">You can perform the installation manually.</span></span> <span data-ttu-id="3a0be-154">ただし、コンポーネントの展開を自動化するには、電子的なソフトウェアの配布方法を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-154">However, we recommend that you use an electronic software distribution method to automate the deployment of the components.</span></span> <span data-ttu-id="3a0be-155">詳細については、「[電子ソフトウェア配布システムを通じて med-v のワークスペースを展開する方法](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-155">For more information, see [How to Deploy a MED-V Workspace Through an Electronic Software Distribution System](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md).</span></span>

**<span data-ttu-id="3a0be-156">注</span><span class="sxs-lookup"><span data-stu-id="3a0be-156">Note</span></span>**  
<span data-ttu-id="3a0be-157">インストールオプションを制御するために使用できるコマンドライン引数の詳細については、「 [Med-v インストールファイルのコマンドラインオプション](command-line-options-for-med-v-installation-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-157">For information about available command-line arguments to control install options, see [Command-Line Options for MED-V Installation Files](command-line-options-for-med-v-installation-files.md).</span></span>



## <span data-ttu-id="3a0be-158">展開の手順</span><span class="sxs-lookup"><span data-stu-id="3a0be-158">Deployment Steps</span></span>


<span data-ttu-id="3a0be-159">企業全体で MED-V を展開する場合は、インストールと初回のセットアップの2つの主要な考慮事項があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-159">When you deploy MED-V throughout your enterprise, there are two main considerations: installation and first time setup.</span></span>

### <span data-ttu-id="3a0be-160">インストール</span><span class="sxs-lookup"><span data-stu-id="3a0be-160">Installation</span></span>

1.  <span data-ttu-id="3a0be-161">**Windows 仮想 pc** -インストール中、WINDOWS 仮想 pc を使用する med-v と、windows 7 の必須更新プログラム (KB977206)。</span><span class="sxs-lookup"><span data-stu-id="3a0be-161">**Windows Virtual PC** - During installation, MED-V checks for Windows Virtual PC and its required update for Windows 7 (KB977206).</span></span> <span data-ttu-id="3a0be-162">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-162">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    <span data-ttu-id="3a0be-163">MED-V をインストールする前に、Windows 7 インストールの一部としてインストールするか、または MED-V の一部としてインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-163">You can install these as part of the Windows 7 installations before you install MED-V, or you can install them as part of the MED-V distribution.</span></span> <span data-ttu-id="3a0be-164">ただし、MED-V には展開のメカニズムは含まれていません。これらは、電子ソフトウェア配布 (ESD) システムまたは Windows 7 イメージの一部として展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-164">However, MED-V does not include a mechanism for their deployment; they must be deployed by using an electronic software distribution (ESD) system or as part of the Windows 7 image.</span></span>

    **<span data-ttu-id="3a0be-165">重要</span><span class="sxs-lookup"><span data-stu-id="3a0be-165">Important</span></span>**  
    <span data-ttu-id="3a0be-166">バッチファイルを使用して MED-V コンポーネントをインストールする場合は、MED-V ホストエージェントと MED-V ワークスペースパッケージファイルの後に Windows 仮想 PC と Windows 仮想 PC ホットフィックスをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-166">When you install the MED-V components by using a batch file, a best practice is to specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="3a0be-167">このため、Windows Update では、再起動を要求することによって、インストールプロセスに干渉することはありません。</span><span class="sxs-lookup"><span data-stu-id="3a0be-167">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. <span data-ttu-id="3a0be-168">**Med-v Host agent** – med-v が実行される Windows 7 コンピューターに Med-v host agent をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-168">**MED-V Host Agent** – Install the MED-V Host Agent on the Windows 7 computer where MED-V will be run.</span></span> <span data-ttu-id="3a0be-169">MED-V ワークスペースをインストールする前に、これをインストールして、Windows 仮想 PC がインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-169">This must be installed before installing the MED-V workspace and checks to make sure that Windows Virtual PC is installed.</span></span>

3. <span data-ttu-id="3a0be-170">**Med-v ワークスペース**– Med-v ワークスペースパッケージャー: setup.exe、. medv、.msi ファイルを使用して、このインストールで必要なファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-170">**MED-V workspace** – You create the files that are required in this installation by using the MED-V Workspace Packager: the setup.exe, .medv, and .msi files.</span></span> <span data-ttu-id="3a0be-171">MED-V ワークスペースをインストールするには、setup.exe を実行します。これにより、必要に応じて他のファイルがトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-171">To install the MED-V workspace, run setup.exe; this triggers the other files as required.</span></span> <span data-ttu-id="3a0be-172">インストールでは、ローカルコンピューターの実行キーの下のレジストリにエントリが格納され、Windows が起動すると常に MED-V が実行される MED-V ホストエージェントが起動します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-172">The installation places an entry in the registry under the local machine run key to start the MED-V Host Agent, which always runs MED-V when Windows is started.</span></span>

   **<span data-ttu-id="3a0be-173">重要</span><span class="sxs-lookup"><span data-stu-id="3a0be-173">Important</span></span>**  
   <span data-ttu-id="3a0be-174">MED-V ワークスペースのインストールは、エンドユーザーによって対話式で実行するか、または電子ソフトウェア配布システムを使ってサイレントに実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-174">The installation of the MED-V workspace can be run interactively by the end user or silently through an electronic software distribution system.</span></span> <span data-ttu-id="3a0be-175">MED-V workspace をインストールするには管理者の資格情報が必要であるため、エンドユーザーは MED-V ワークスペースをインストールするには、コンピューターの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-175">Installation of the MED-V workspace requires administrative credentials, so end users must be administrators of their computers to install the MED-V workspace.</span></span> <span data-ttu-id="3a0be-176">または、通常、電子ソフトウェア配布システムはシステムコンテキストで実行され、十分な権限があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-176">Alternately, an electronic software distribution system typically runs in the system context and has sufficient permissions.</span></span>



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### <span data-ttu-id="3a0be-177">初回のセットアップ</span><span class="sxs-lookup"><span data-stu-id="3a0be-177">First Time Setup</span></span>

<span data-ttu-id="3a0be-178">MED-V とその必須コンポーネントをインストールした後、MED-V を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-178">After MED-V and its required components are installed, MED-V must be configured.</span></span> <span data-ttu-id="3a0be-179">MED-V の構成は、初回のセットアップと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-179">The configuration of MED-V is known as first time setup.</span></span> <span data-ttu-id="3a0be-180">**Med-v ワークスペースパッケージャー**を使って、サイレントまたは対話形式で実行するための初回のセットアップを構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-180">By using the **MED-V Workspace Packager**, you can configure first time setup to run silently or interactively.</span></span> <span data-ttu-id="3a0be-181">MED-V の初回のセットアップでは、エンドユーザーは、MED-V ワークスペースに対して認証するためにパスワードを入力する必要がありますが、それ以外の場合は、ユーザーに対してほとんど非表示にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-181">First time setup of MED-V requires end users to enter their password to authenticate to the MED-V workspace, but otherwise can be almost invisible to the user.</span></span> <span data-ttu-id="3a0be-182">通知は通知領域に表示されます。たとえば、初回のセットアップが完了し、アプリケーションが準備できている場合です。</span><span class="sxs-lookup"><span data-stu-id="3a0be-182">Notifications are shown in the notification area, such as when first time setup is complete and applications are ready.</span></span> <span data-ttu-id="3a0be-183">MED-V の初回セットアップ時に発生するアクションを次に示します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-183">The following are the actions that occur during first time setup of MED-V:</span></span>

1.  <span data-ttu-id="3a0be-184">仮想ハードディスクを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-184">The virtual hard disk must be configured.</span></span> <span data-ttu-id="3a0be-185">ミニセットアップでは、Windows XP のイメージが実行され、展開されます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-185">Mini-Setup runs and expands the Windows XP image.</span></span> <span data-ttu-id="3a0be-186">通常、これは非表示のウィンドウで発生しますが、MED-V はこの構成時に表示されるように構成できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-186">Typically, this occurs in a hidden window, but MED-V can be configured to display during this configuration.</span></span>

2.  <span data-ttu-id="3a0be-187">ミニセットアップが完了すると、ESD ソフトウェアやその他のアプリケーションのインストール、イメージの構成などの追加構成を行うために必要なコマンドを実行できます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-187">After Mini-Setup finishes, you can run commands that you must have for additional configuration, such as installing ESD software or other applications, or configuring the image.</span></span> <span data-ttu-id="3a0be-188">これらは、Sysprep.inf ファイルで呼び出すことができますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="3a0be-188">These can be called in the Sysprep.inf file, but are not required there.</span></span> <span data-ttu-id="3a0be-189">詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成する](configuring-a-windows-virtual-pc-image-for-med-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-189">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

3.  <span data-ttu-id="3a0be-190">Ftscompletion.exe は、構成の最後の手順として実行されます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-190">Ftscompletion.exe is run as the last step in configuration.</span></span> <span data-ttu-id="3a0be-191">このプロセスは、MED-V 構成を完了し、ユーザーを RDP グループに追加して、MED-V ワークスペースへのアクセス、ログのコピー、med-v ワークスペースの準備ができている MED-V の通知を行い、MED-V ワークスペースを再起動します。</span><span class="sxs-lookup"><span data-stu-id="3a0be-191">This process completes the MED-V configuration, adds the user to the RDP group to let them access the MED-V workspace, copies logs, signals MED-V that the MED-V workspace is ready, and then restarts the MED-V workspace.</span></span> <span data-ttu-id="3a0be-192">このプロセスでは、MED-V ワークスペースが作成されたときに、そのユーザーを MED-V ワークスペースの管理者として追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-192">This process can also add the user as an administrator of the MED-V workspace if this was configured when the MED-V workspace was created.</span></span> <span data-ttu-id="3a0be-193">通常、Ftscompletion.exe は、Sysprep と inf ファイルを通じて呼び出されますが、スクリプトなどの別の方法で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-193">Ftscompletion.exe is typically called through the Sysprep,inf file but can also be run through another method, such as a script.</span></span> <span data-ttu-id="3a0be-194">ただし、Ftscompletion.exe は、ワークステーションが構成されたときに実行される最後の操作である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-194">However, Ftscompletion.exe must be the last action that is performed when the workstation is configured.</span></span> <span data-ttu-id="3a0be-195">詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成する](configuring-a-windows-virtual-pc-image-for-med-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3a0be-195">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

4.  <span data-ttu-id="3a0be-196">Ftscompletion.exe で MED-V ワークスペースを再起動した後、エンドユーザーはログオンしています。</span><span class="sxs-lookup"><span data-stu-id="3a0be-196">After the MED-V workspace is restarted by Ftscompletion.exe, the end user is logged on.</span></span> <span data-ttu-id="3a0be-197">初めてセットアップしたときにパスワードを保存していない場合は、もう一度入力を求められます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-197">If they did not save their password during first time setup, they are prompted for it again.</span></span> <span data-ttu-id="3a0be-198">次に、MED-V ワークスペースが開始され、ユーザーに対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-198">The MED-V workspace is then started and configured for the user.</span></span> <span data-ttu-id="3a0be-199">構成には、グループポリシーの適用が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-199">Configuration includes applying Group Policy.</span></span>

    <span data-ttu-id="3a0be-200">Windows XP のアプリケーション互換性環境で適切なポリシーのみを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3a0be-200">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="3a0be-201">たとえば、通常、デスクトップパーソナル化ポリシーを適用する必要がないため、無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3a0be-201">For example, desktop personalization policies do not typically need to be applied and should be disabled.</span></span> <span data-ttu-id="3a0be-202">ローカルプロファイルのみを許可する方法について詳しくは、「[ローミングユーザープロファイルのグループポリシー設定](https://go.microsoft.com/fwlink/?LinkId=205072)」をご覧ください https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="3a0be-202">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

<span data-ttu-id="3a0be-203">初回のセットアップが完了した後、公開されたアプリケーションの準備ができたことがエンドユーザーに通知されます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-203">After first time setup is complete, the end user is notified that the published applications are ready.</span></span> <span data-ttu-id="3a0be-204">これらのユーザーは、[**スタート**] メニューから med-v ワークスペースにインストールされているアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3a0be-204">They are then able to access the applications installed in the MED-V workspace from their **Start** menu.</span></span>

## <span data-ttu-id="3a0be-205">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3a0be-205">Related topics</span></span>


[<span data-ttu-id="3a0be-206">MED-V の展開環境を準備する</span><span class="sxs-lookup"><span data-stu-id="3a0be-206">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

[<span data-ttu-id="3a0be-207">MED-V の展開</span><span class="sxs-lookup"><span data-stu-id="3a0be-207">Deployment of MED-V</span></span>](deployment-of-med-v.md)









