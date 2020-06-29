---
title: 電子ソフトウェア配布システムによって MED-V コンポーネントを展開する方法
description: 電子ソフトウェア配布システムによって MED-V コンポーネントを展開する方法
author: dansimp
ms.assetid: 8a800bdf-6fa4-47b4-b417-df053289d4e8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d772702c770340796fe770273146bd0308617a69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824854"
---
# <span data-ttu-id="2b793-103">電子ソフトウェア配布システムによって MED-V コンポーネントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="2b793-103">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>


<span data-ttu-id="2b793-104">電子的なソフトウェア配布システムを使用すると、低速または高速のネットワーク接続を介して多くのコンピューターにソフトウェアを効率的に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="2b793-104">An electronic software distribution system can help you efficiently move software to many computers over slow or fast network connections.</span></span> <span data-ttu-id="2b793-105">以下のセクションでは、ソフトウェア配布システムを使用して、企業全体で Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 コンポーネントを展開するのに役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b793-105">The following section provides information and instructions to help you deploy the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components throughout your enterprise by using a software distribution system.</span></span>

**<span data-ttu-id="2b793-106">注</span><span class="sxs-lookup"><span data-stu-id="2b793-106">Note</span></span>**  
<span data-ttu-id="2b793-107">どのソフトウェア配布ソリューションを使用する場合でも、特定の解決策の要件について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-107">Whichever software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="2b793-108">System Center Configuration Manager 2007 R2 またはそれ以降のバージョンを使用している場合は、Microsoft テクニカルライブラリの[Configuration Manager ドキュメントライブラリ](https://go.microsoft.com/fwlink/?LinkId=66999)を参照してください ( https://go.microsoft.com/fwlink/?LinkId=66999) .</span><span class="sxs-lookup"><span data-stu-id="2b793-108">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>



**<span data-ttu-id="2b793-109">重要</span><span class="sxs-lookup"><span data-stu-id="2b793-109">Important</span></span>**  
<span data-ttu-id="2b793-110">System Center Configuration Manager 2007 SP2 を使用していて、MED-V ワークスペースが**NAT**モードで動作するように構成されている場合、仮想マシンはインターネットベースのクライアントとして分類され、コンテンツをダウンロードする最も近い配布ポイントを検索することはできません。</span><span class="sxs-lookup"><span data-stu-id="2b793-110">If you are using System Center Configuration Manager 2007 SP2 and your MED-V workspaces are configured to operate in **NAT** mode, the virtual machines are classified as Internet-based clients and cannot find the closest distribution points from which to download content.</span></span>

<span data-ttu-id="2b793-111">[Med-v によって管理される vm の機能を改善するための修正プログラム](https://go.microsoft.com/fwlink/?LinkId=201088)( https://go.microsoft.com/fwlink/?LinkId=201088) med-v によって管理され、 **NAT**モードで動作するように構成されている仮想マシンに新機能が追加されています)。</span><span class="sxs-lookup"><span data-stu-id="2b793-111">The [hotfix to improve the functionality for VMs that are managed by MED-V](https://go.microsoft.com/fwlink/?LinkId=201088) (https://go.microsoft.com/fwlink/?LinkId=201088) adds new functionality to virtual machines that are managed by MED-V and that are configured to operate in **NAT** mode.</span></span> <span data-ttu-id="2b793-112">新しい機能により、仮想マシンは最も近い配布ポイントにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2b793-112">The new functionality lets virtual machines access the closest distribution points.</span></span> <span data-ttu-id="2b793-113">そのため、管理者は仮想マシンとホストコンピューターを同じ方法で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2b793-113">Therefore, the administrator can manage the virtual machine and the host computer in the same manner.</span></span> <span data-ttu-id="2b793-114">この修正プログラムは、最初にサイトサーバーにインストールしてから、クライアントでインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-114">This hotfix must be installed first on the site server and then on the client.</span></span>

<span data-ttu-id="2b793-115">更新プログラムは公開されています。</span><span class="sxs-lookup"><span data-stu-id="2b793-115">The update is publicly available.</span></span> <span data-ttu-id="2b793-116">ただし、Microsoft サービスのライセンス契約に同意するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-116">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="2b793-117">この修正プログラムを取得するには、連続する web ページの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="2b793-117">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>



**<span data-ttu-id="2b793-118">注</span><span class="sxs-lookup"><span data-stu-id="2b793-118">Note</span></span>**  
<span data-ttu-id="2b793-119">ソフトウェア配布システムを使用して MED-V コンポーネントを展開するには、MED-V workspace パッケージャーをインストールし、MED-V ワークスペースを構築する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-119">You must install the MED-V workspace packager and build your MED-V workspaces before you can deploy the MED-V components through your software distribution system.</span></span> <span data-ttu-id="2b793-120">イメージを準備して、MED-V ワークスペースを構築する方法について詳しくは、「 [med-v の操作](operations-for-med-v.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2b793-120">For more information about how to prepare an image and to build your MED-V workspaces, see [Operations for MED-V](operations-for-med-v.md).</span></span>



**<span data-ttu-id="2b793-121">ソフトウェア配布システムを使用して MED-V コンポーネントを展開するには</span><span class="sxs-lookup"><span data-stu-id="2b793-121">To deploy the MED-V components by using a software distribution system</span></span>**

1.  <span data-ttu-id="2b793-122">電子ソフトウェア配布システムでコンピューターとユーザーのグループを、コンピューター/ユーザーのターゲットセットとして定義します。</span><span class="sxs-lookup"><span data-stu-id="2b793-122">Define a group of computers and users in the electronic software distribution system as the target set of computers/users.</span></span>

2.  <span data-ttu-id="2b793-123">配布する必要がある Microsoft インストールファイルごとにパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="2b793-123">Create packages for each Microsoft installation file that needs to be distributed.</span></span> <span data-ttu-id="2b793-124">必要なファイルと、それらをインストールする順序を次に示します。</span><span class="sxs-lookup"><span data-stu-id="2b793-124">The following are the required files and the order in which they must be installed:</span></span>

    1.  <span data-ttu-id="2b793-125">**Windows VIRTUAL PC** –まだインストールされていない場合は (コンピューターの再起動が必要)。</span><span class="sxs-lookup"><span data-stu-id="2b793-125">**Windows Virtual PC** – if not already installed (a computer restart is required).</span></span> <span data-ttu-id="2b793-126">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-126">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    2.  <span data-ttu-id="2b793-127">**Windows VIRTUAL PC の追加と更新プログラム**(まだインストールされていない場合)。</span><span class="sxs-lookup"><span data-stu-id="2b793-127">**Windows Virtual PC Additions and Updates** – if not already installed.</span></span> <span data-ttu-id="2b793-128">詳細については、「[インストールの前提条件を構成する](configure-installation-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-128">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    3.  <span data-ttu-id="2b793-129">**Med-v Host Agent インストールファイル**–ホストエージェント (med-v \ _HostAgent \ _Setup インストールファイル) をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-129">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="2b793-130">詳細については、「 [Med-v Host Agent を手動でインストールする方法](how-to-manually-install-the-med-v-host-agent.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-130">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

        **<span data-ttu-id="2b793-131">Warning</span><span class="sxs-lookup"><span data-stu-id="2b793-131">Warning</span></span>**  
        <span data-ttu-id="2b793-132">MED-V Host Agent をインストールする前に Internet Explorer を閉じます。そうでないと、後で URL リダイレクションを使用して競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-132">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="2b793-133">また、配布中にコンピューターを再起動することを指定して、この操作を行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2b793-133">You can also do this by specifying a computer restart during a distribution.</span></span>   

    4.  <span data-ttu-id="2b793-134">Med-v ワークスペースの**インストーラー、VHD、セットアップの実行可能ファイル**( **med-v workspace パッケージャー**で作成)</span><span class="sxs-lookup"><span data-stu-id="2b793-134">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="2b793-135">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-135">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        **<span data-ttu-id="2b793-136">重要</span><span class="sxs-lookup"><span data-stu-id="2b793-136">Important</span></span>**  
        <span data-ttu-id="2b793-137">圧縮仮想ハードディスクファイル (medv) とセットアップ実行可能プログラム (setup.exe) は、MED-V workspace installer と同じフォルダーに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-137">The compressed virtual hard disk file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="2b793-138">次に、setup.exe を実行して、MED-V ワークスペースインストーラーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-138">Then, install the MED-V workspace installer by running setup.exe.</span></span>

        **<span data-ttu-id="2b793-139">ヒント</span><span class="sxs-lookup"><span data-stu-id="2b793-139">Tip</span></span>**  
        <span data-ttu-id="2b793-140">ネットワーク上の場所から MED-V をインストールするときに問題が発生する可能性があるため、MED-V ワークスペースのセットアップファイルをローカルにコピーして、setup.exe を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b793-140">Because problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>       

3.  <span data-ttu-id="2b793-141">サイレントモードで実行するようにパッケージを構成します (ユーザーの操作は必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="2b793-141">Configure the packages to run in silent mode (no user interaction is required).</span></span>

    <span data-ttu-id="2b793-142">サイレントモードで実行している場合、Internet Explorer が実行されている場合はそれを閉じるか、MED-V ホストエージェントを起動するように求めるメッセージが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="2b793-142">Running in silent mode eliminates the prompt to close Internet Explorer if it is running and the prompt to start the MED-V Host Agent.</span></span> <span data-ttu-id="2b793-143">どちらの操作も、コンピューターを再起動したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="2b793-143">Both actions are performed when the computer is restarted.</span></span>

    **<span data-ttu-id="2b793-144">注</span><span class="sxs-lookup"><span data-stu-id="2b793-144">Note</span></span>**  
    <span data-ttu-id="2b793-145">Windows Virtual PC をインストールするには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-145">Installation of Windows Virtual PC requires you to restart the computer.</span></span> <span data-ttu-id="2b793-146">再起動を抑制して、MED-V をインストールするために必要な前提条件を無視した場合は、1つのインストールプロセスを作成し、すべてのコンポーネントを同時にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b793-146">You can create a single installation process and install all the components at the same time if you suppress the restart and ignore the prerequisites necessary for MED-V to install.</span></span> <span data-ttu-id="2b793-147">これは、コマンドライン引数を使って行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="2b793-147">You can also do this by using command-line arguments.</span></span> <span data-ttu-id="2b793-148">これらの引数の例については、「[バッチファイルを使用して med-v コンポーネントをインストールする」を](#bkmk-batch)参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-148">For an example of these arguments, see [To install the MED-V components by using a batch file](#bkmk-batch).</span></span> <span data-ttu-id="2b793-149">MED-V は、コンピューターを再起動したときに自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b793-149">MED-V automatically starts when the computer is restarted.</span></span>

4.  <span data-ttu-id="2b793-150">Windows Virtual PC をインストールする前に、MED-V とそのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-150">Install MED-V and its components before installing Windows Virtual PC.</span></span> <span data-ttu-id="2b793-151">このトピックで後述するバッチファイルの例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-151">See the example batch file later in this topic.</span></span>

    **<span data-ttu-id="2b793-152">重要</span><span class="sxs-lookup"><span data-stu-id="2b793-152">Important</span></span>**  
    <span data-ttu-id="2b793-153">必要な VPC コンポーネントの前に MED-V コンポーネントをインストールできるように、例として、[ **\ _PREREQUISITES 無視**] オプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="2b793-153">Select the **IGNORE\_PREREQUISITES** option as shown in the example batch file so that the MED-V components can be installed prior to the required VPC components.</span></span> <span data-ttu-id="2b793-154">1回の再起動を許可するには、MED-V コンポーネントをこの順序でインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-154">Install the MED-V components in this order to allow for the single restart.</span></span>

5.  <span data-ttu-id="2b793-155">インストールおよびソフトウェア配布システム (ターゲットプラットフォーム、空きディスク領域など) に必要なその他の要件を特定します。</span><span class="sxs-lookup"><span data-stu-id="2b793-155">Identify any other requirements necessary for the installation and for your software distribution system, such as target platforms and the free disk space.</span></span>

6.  <span data-ttu-id="2b793-156">パッケージをコンピューター/ユーザーのターゲットセットに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="2b793-156">Assign the packages to the target set of computers/users.</span></span>

    <span data-ttu-id="2b793-157">コンピューターが実行されている間、ソフトウェア配布システムクライアントは、新しいパッケージが利用可能であることを認識し、定義と要件に従ってパッケージのインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="2b793-157">As computers are running, the software distribution system client recognizes that new packages are available and begins to install the packages per the definition and requirements.</span></span> <span data-ttu-id="2b793-158">インストールはサイレントモードで連続して実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b793-158">The installations should run sequentially in silent mode.</span></span> <span data-ttu-id="2b793-159">これは、すべてのパッケージがインストールされるまで、再起動を必要としない単一のプロセスとして実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b793-159">We recommend that this is performed as a single process that does not require a restart until all the packages are installed.</span></span>

7.  <span data-ttu-id="2b793-160">インストールが完了したら、更新されたコンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2b793-160">After the installations are complete, restart the updated computers.</span></span>

    <span data-ttu-id="2b793-161">ソフトウェア配布システムによっては、コンピューターの再起動をスケジュールしたり、通常の作業中にエンドユーザーが手動でコンピューターを再起動したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b793-161">Depending on the software distribution system, you can schedule a restart of the computer or the end users can restart the computers manually during their regular work.</span></span> <span data-ttu-id="2b793-162">コンピューターの再起動後、MED-V はエンドユーザーがログオンした後に自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="2b793-162">After the computer is restarted, MED-V automatically starts after an end user logs on.</span></span> <span data-ttu-id="2b793-163">MED-V が初めて開始されるときには、初回のセットアップが実行されます。</span><span class="sxs-lookup"><span data-stu-id="2b793-163">When MED-V starts for the first time, it runs first time setup.</span></span>

<span data-ttu-id="2b793-164">初めてセットアップを開始したときに、指定した仮想ハードディスクのサイズと、起動時に MED-V ワークスペースに適用されたポリシーの数に応じて、セットアップが完了するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="2b793-164">First time setup starts and might take several minutes to finish, depending on the size of the virtual hard disk that you specified and the number of policies applied to the MED-V workspace on startup.</span></span> <span data-ttu-id="2b793-165">エンドユーザーは、通知領域の MED-V アイコンを見て、進捗状況を追跡できます。</span><span class="sxs-lookup"><span data-stu-id="2b793-165">The end user can track the progress by watching the MED-V icon in the notification area.</span></span> <span data-ttu-id="2b793-166">初めてセットアップする場合の詳細については、「 [med-v 2.0 の展開の概要](med-v-20-deployment-overview.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b793-166">For more information about first time setup, see [MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md).</span></span>

<a href="" id="bkmk-batch"></a>**<span data-ttu-id="2b793-167">バッチファイルを使用して MED-V コンポーネントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="2b793-167">To install the MED-V components by using a batch file</span></span>**

1.  <span data-ttu-id="2b793-168">管理者の資格情報を使用して、コマンドプロンプトでインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b793-168">Run the installation at a command prompt with administrative credentials.</span></span>

2.  <span data-ttu-id="2b793-169">各コンポーネントを1つのディレクトリに配置します。</span><span class="sxs-lookup"><span data-stu-id="2b793-169">Deploy each component to a single directory.</span></span> <span data-ttu-id="2b793-170">ネットワーク共有から実行する場合は、medv ファイルを展開するために長い時間が必要です。</span><span class="sxs-lookup"><span data-stu-id="2b793-170">If run from a network share, a longer time is required to decompress the .medv file.</span></span>

3.  <span data-ttu-id="2b793-171">ベストプラクティスとして、Windows 仮想 PC と Windows 仮想 PC ホットフィックスは、MED-V Host Agent ファイルと MED-V ワークスペースパッケージファイルの後にインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b793-171">As a best practice, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="2b793-172">このため、Windows Update では、再起動を要求することによって、インストールプロセスに干渉することはありません。</span><span class="sxs-lookup"><span data-stu-id="2b793-172">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

4.  <span data-ttu-id="2b793-173">バッチファイルが完了したら、コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="2b793-173">Restart the computer after the batch file is finished.</span></span>

<span data-ttu-id="2b793-174">再起動すると、ユーザーに対して、初回のセットアップを実行して、MED-V の構成を完了するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2b793-174">After the restart, the user is prompted to run first time setup and complete the configuration of MED-V.</span></span>

<span data-ttu-id="2b793-175">次の例では、指定された引数を使って、1つのプロセスで64ビット MED-V コンポーネントをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="2b793-175">The following example, with the specified arguments, shows how to install 64-bit MED-V components in a single process:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2b793-176">引数</span><span class="sxs-lookup"><span data-stu-id="2b793-176">Argument</span></span></th>
<th align="left"><span data-ttu-id="2b793-177">説明</span><span class="sxs-lookup"><span data-stu-id="2b793-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b793-178">/norestart</span><span class="sxs-lookup"><span data-stu-id="2b793-178">/norestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b793-179">Windows 仮想 PC と Windows 仮想 PC の更新プログラムをインストールして、ホストコンピューターを再起動しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2b793-179">Prevents the installation of Windows Virtual PC and the Windows Virtual PC update from restarting the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b793-180">/quiet</span><span class="sxs-lookup"><span data-stu-id="2b793-180">/quiet</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b793-181">ユーザーの操作なしで、MED-V コンポーネントを quiet モードでインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-181">Installs the MED-V components in quiet mode without user interaction.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b793-182">/qn</span><span class="sxs-lookup"><span data-stu-id="2b793-182">/qn</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b793-183">ユーザーインターフェイスを使わずに、MED-V コンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-183">Installs the MED-V components without a user interface.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b793-184">IGNORE_PREREQUISITES</span><span class="sxs-lookup"><span data-stu-id="2b793-184">IGNORE_PREREQUISITES</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b793-185">Windows 仮想 PC をチェックせずにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b793-185">Installs without checking for Windows Virtual PC.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="2b793-186">注</span><span class="sxs-lookup"><span data-stu-id="2b793-186">Note</span></span></strong><br/><p><span data-ttu-id="2b793-187">この引数を指定するのは、このインストールの一部として Windows Virtual PC をインストールする場合のみです。</span><span class="sxs-lookup"><span data-stu-id="2b793-187">Only specify this argument if you are installing Windows Virtual PC as part of this installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b793-188">オーバー・ WRITEVHD</span><span class="sxs-lookup"><span data-stu-id="2b793-188">OVERWRITEVHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b793-189">MED-V ワークスペースのインストールを強制し、生成される可能性のあるプロンプトを表示しないようにします。</span><span class="sxs-lookup"><span data-stu-id="2b793-189">Forces the installation of the MED-V workspace and prevents any prompts that it might generate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="2b793-190">例</span><span class="sxs-lookup"><span data-stu-id="2b793-190">Example</span></span>


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## <span data-ttu-id="2b793-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2b793-191">Related topics</span></span>


[<span data-ttu-id="2b793-192">MED-V 2.0 展開の概要</span><span class="sxs-lookup"><span data-stu-id="2b793-192">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="2b793-193">MED-V コンポーネントを展開する</span><span class="sxs-lookup"><span data-stu-id="2b793-193">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)









