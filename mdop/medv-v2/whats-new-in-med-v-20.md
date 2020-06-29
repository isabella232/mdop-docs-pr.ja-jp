---
title: MED-V 2.0 の新機能
description: MED-V 2.0 の新機能
author: dansimp
ms.assetid: 53b10bff-2b6f-463b-bdc2-5edc56526792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 78dba25fec7ae2bb41da00902b59dcd15030f2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823704"
---
# <span data-ttu-id="65433-103">MED-V 2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="65433-103">What's New in MED-V 2.0</span></span>


<span data-ttu-id="65433-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 は、Windows 7 のアプリケーション互換性サポートを進化させ、このシナリオでは必要のない機能を削除しました。</span><span class="sxs-lookup"><span data-stu-id="65433-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 has evolved the application compatibility support for Windows 7 and removed functionality that is not required for this scenario.</span></span> <span data-ttu-id="65433-105">たとえば、MED-V ワークスペース、集中化された MED サーバー、および MED-V ワークスペースのトリム転送などの機能は削除されました。</span><span class="sxs-lookup"><span data-stu-id="65433-105">For example, features such as encryption of the MED-V workspace, the centralized MED-V server, and MED-V workspace trim transfer have been removed.</span></span>

## <span data-ttu-id="65433-106">標準機能の変更点</span><span class="sxs-lookup"><span data-stu-id="65433-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="65433-107">このセクションでは、MED-V 2.0 機能が変更されている主要な領域について説明します。</span><span class="sxs-lookup"><span data-stu-id="65433-107">This section discusses the key areas where MED-V 2.0 functionality has changed.</span></span>

### <span data-ttu-id="65433-108">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="65433-108">MED-V Workspace Creation</span></span>

<span data-ttu-id="65433-109">MED-V ワークスペースに使用されている仮想ハードディスクが、Windows 仮想 PC で作成されます。</span><span class="sxs-lookup"><span data-stu-id="65433-109">The virtual hard disk used for the MED-V workspace is now created in Windows Virtual PC.</span></span> <span data-ttu-id="65433-110">MED-V ワークスペースを作成するために使用されるメソッドには、Windows XP SP3 のインストール、オペレーティングシステムの更新、ソフトウェア管理インフラストラクチャを使用した管理の準備などがあります。</span><span class="sxs-lookup"><span data-stu-id="65433-110">The methods that are used to create the MED-V workspace include installing Windows XP SP3, updating the operating system, and preparing it to be managed through software management infrastructure.</span></span>

<span data-ttu-id="65433-111">専用の MED-V ワークスペースの暗号化と圧縮機能のほかに、オフライン管理とトリム転送機能も削除されました。</span><span class="sxs-lookup"><span data-stu-id="65433-111">The offline management and trim transfer functionality were removed, in addition to the proprietary MED-V workspace encryption and compression functionality.</span></span> <span data-ttu-id="65433-112">MED-V のワークスペースを作成する場合、管理者は、MED-V 1.0 で提供されている仮想マシンの準備ツールではなく、イメージに適切なアプリケーションと管理ツールを準備して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65433-112">When you create a MED-V workspace, an administrator should prepare and configure appropriate applications and management tools in the image instead of using the virtual machine preparation tool that is provided in MED-V 1.0.</span></span>

<span data-ttu-id="65433-113">Med-v イメージの Sysprep の実行は、MED-V ワークスペースのパッケージ化中に必要になり、検証されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="65433-113">Running Sysprep on the MED-V image is now required and validated during the packaging of the MED-V workspace.</span></span> <span data-ttu-id="65433-114">MED-V ワークスペースパッケージャーには、パッケージ化プロセスを通じて管理者に指示するグラフィカルユーザーインターフェイス (GUI) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="65433-114">The MED-V Workspace Packager provides a graphical user interface (GUI) that guides the administrator through the packaging process.</span></span> <span data-ttu-id="65433-115">MED-V 1.0 の本体は、画像の管理、MED-V workspace プロファイルの管理の機能、および MED-V ワークスペースのステージングと暗号化の要件と共に削除されました。</span><span class="sxs-lookup"><span data-stu-id="65433-115">The console from MED-V 1.0 was removed together with the functionality of managing images, managing MED-V workspace profiles, and the requirement to stage and encrypt MED-V workspaces.</span></span>

### <span data-ttu-id="65433-116">MED-V ワークスペースの展開</span><span class="sxs-lookup"><span data-stu-id="65433-116">MED-V Workspace Deployment</span></span>

<span data-ttu-id="65433-117">MED-V ワークスペースを展開すると、管理者は、電子ソフトウェアの配布ツールを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="65433-117">To deploy a MED-V workspace, an administrator is now able to take advantage of their electronic software distribution tools.</span></span> <span data-ttu-id="65433-118">MED-V 1.0 で使用できるクライアントプルメソッドが削除され、MED-V ワークスペースが、MED-V 以外のメソッドを使用して提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="65433-118">The client-pull method available in MED-V 1.0 was removed and the MED-V workspace is now delivered by using methods outside MED-V.</span></span> <span data-ttu-id="65433-119">管理者は、他のアプリケーションパッケージと同じように MED-V ワークスペースを扱うことができます。また、既存のツールとプロセスを使用して、MED-V の展開とインストールをスケジュール設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="65433-119">Administrators can treat MED-V workspaces as they would any other application package and can schedule deployments and installations of MED-V by using their existing tools and processes.</span></span> <span data-ttu-id="65433-120">MED-V をサイレントインストールして、既存のソフトウェア配布インフラストラクチャ内で簡単に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="65433-120">MED-V installations can be deployed silently and can easily be managed inside an existing software distribution infrastructure.</span></span>

### <span data-ttu-id="65433-121">MED-V ワークスペースの管理</span><span class="sxs-lookup"><span data-stu-id="65433-121">MED-V Workspace Management</span></span>

<span data-ttu-id="65433-122">MED-V 2.0 の MED-V ワークスペースは、Windows 仮想 PC 仮想ハードディスクに基づいています。</span><span class="sxs-lookup"><span data-stu-id="65433-122">The MED-V workspace in MED-V 2.0 is based on a Windows Virtual PC virtual hard disk.</span></span> <span data-ttu-id="65433-123">MED-V では、Windows 仮想 PC で提供される機能が拡張され、暗号化や特殊なツールを使って MED-V ワークスペースにアクセスする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="65433-123">MED-V has extended the capabilities that Windows Virtual PC provides by improving the seamless experience without requiring encryption or special tools to access the MED-V workspace.</span></span>

<span data-ttu-id="65433-124">MED-V がワークステーションに展開されると、Windows Virtual PC を使用して、MED-V ワークスペースを全画面モードで開くことができます。</span><span class="sxs-lookup"><span data-stu-id="65433-124">After MED-V is deployed to a workstation, the MED-V workspace can be opened in full-screen mode by using Windows Virtual PC.</span></span> <span data-ttu-id="65433-125">この新機能により、シームレスまたは全画面モードの環境設定を設定し、診断とトラブルシューティングのための全画面表示を強制する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="65433-125">This new functionality removed the requirement for policies that set a preference for seamless or full-screen modes and also removed the need to force full-screen for diagnostics and troubleshooting.</span></span>

<span data-ttu-id="65433-126">MED-V ワークスペースへのアプリケーションの公開は、プロファイルでは実行されません。また、手動でアプリケーションへのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="65433-126">Publishing applications to the MED-V workspace is no longer performed with profiles and by manually entering the path to applications.</span></span> <span data-ttu-id="65433-127">代わりに、アプリケーションがゲストにインストールされると自動的に発生します。</span><span class="sxs-lookup"><span data-stu-id="65433-127">Instead, it occurs automatically as applications are installed on the guest.</span></span> <span data-ttu-id="65433-128">トリム転送によって配信された画像のバージョンが含まれている中央のイメージリポジトリが削除されます。</span><span class="sxs-lookup"><span data-stu-id="65433-128">The central image repository that included versions of the images that were delivered through trim transfer is removed.</span></span> <span data-ttu-id="65433-129">代わりに、MED-V を使用すると、管理者は、専用の MED-V インフラストラクチャを複雑にせずにアプリケーションと更新プログラムを配布できるため、物理コンピューターと同じように MED-V ワークスペースを管理できます。</span><span class="sxs-lookup"><span data-stu-id="65433-129">Instead, MED-V enables administrators to manage the MED-V workspace as they would a physical computer, by letting applications and updates be distributed without the complexity of a dedicated MED-V infrastructure.</span></span>

## <span data-ttu-id="65433-130">MED-V 機能の変更点</span><span class="sxs-lookup"><span data-stu-id="65433-130">Changes in MED-V Features</span></span>


<span data-ttu-id="65433-131">MED-V 2.0 のいくつかの主要領域には、次の機能の改善と追加が反映されています。</span><span class="sxs-lookup"><span data-stu-id="65433-131">Several key areas of MED-V 2.0 reflect improvements or additions to the following features.</span></span>

### <span data-ttu-id="65433-132">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="65433-132">MED-V Workspace Creation</span></span>

<span data-ttu-id="65433-133">MED-V ワークスペースを作成するには、Windows Virtual PC を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65433-133">MED-V workspaces must be created by using Windows Virtual PC.</span></span> <span data-ttu-id="65433-134">既存の仮想 PC 2007 の画像を移行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65433-134">Existing Virtual PC 2007 images must be migrated.</span></span> <span data-ttu-id="65433-135">Virtual machine Prep ツールは、MED-V 2.0 には含まれていません。管理者は、MED-V 2.0 ヘルプファイルに従って、画像を構成、更新、最適化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65433-135">The virtual machine Prep tool is not included in MED-V 2.0 and administrators should configure, update, and optimize their images according to the MED-V 2.0 Help file.</span></span> <span data-ttu-id="65433-136">MED-V イメージでの Sysprep の実行は必須の手順であり、パッケージ化の前に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65433-136">Running Sysprep on the MED-V image is a required step and must be performed before packaging.</span></span>

### <span data-ttu-id="65433-137">MED-V ワークスペースパッケージ</span><span class="sxs-lookup"><span data-stu-id="65433-137">MED-V Workspace Packaging</span></span>

<span data-ttu-id="65433-138">Windows PowerShell は、MED-V ワークスペースパッケージャーの基盤です。</span><span class="sxs-lookup"><span data-stu-id="65433-138">Windows PowerShell is the foundation of the MED-V Workspace Packager.</span></span> <span data-ttu-id="65433-139">この機能は、MED-V の集中化された機能を管理する、以前の一部の本体の機能や機能に代わるものです。</span><span class="sxs-lookup"><span data-stu-id="65433-139">This functionality replaces some former console abilities and functionality that managed centralized functions of MED-V.</span></span> <span data-ttu-id="65433-140">MED-V ワークスペースパッケージャーでは、管理者が簡単に展開できるように、適切な設定とイメージを使って仮想ハードディスクをパッケージ化します。</span><span class="sxs-lookup"><span data-stu-id="65433-140">The MED-V Workspace Packager merely packages the virtual hard disk with the appropriate settings and image so that it can be easily deployed by administrators.</span></span> <span data-ttu-id="65433-141">高度な機能は、Windows PowerShell を使用して提供されます。</span><span class="sxs-lookup"><span data-stu-id="65433-141">Advanced features are provided by using Windows PowerShell.</span></span>

### <span data-ttu-id="65433-142">MED-V ワークスペースの配布</span><span class="sxs-lookup"><span data-stu-id="65433-142">MED-V Workspace Distribution</span></span>

<span data-ttu-id="65433-143">専用サーバーインフラストラクチャは、MED-V 2.0 には不要であり、MED-V ワークスペースを展開するためのクライアントプルメソッドが削除されました。</span><span class="sxs-lookup"><span data-stu-id="65433-143">Dedicated server infrastructure is no longer required for MED-V 2.0 and the client pull method to deploy MED-V workspaces was removed.</span></span> <span data-ttu-id="65433-144">MED-V ワークスペースは、電子ソフトウェア配布インフラストラクチャを使用して展開されるようになり、他のインストールパッケージで使用される共通の共有に保存できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="65433-144">MED-V workspaces are now deployed using your electronic software distribution infrastructure and can be stored on common shares that are used for other installation packages.</span></span>

### <span data-ttu-id="65433-145">初回のセットアップ</span><span class="sxs-lookup"><span data-stu-id="65433-145">First Time Setup</span></span>

<span data-ttu-id="65433-146">初回のセットアッププロセスが、Sysprep の標準のイメージング規則と統合されました。</span><span class="sxs-lookup"><span data-stu-id="65433-146">The first time setup process is now integrated with the standard imaging convention of Sysprep.</span></span> <span data-ttu-id="65433-147">MED-V ワークスペースの初回セットアッププロセスでは、ミニセットアップが開始されるときに、MED-V ワークスペースパッケージャーで指定した設定を動的に画像に適用することができます。</span><span class="sxs-lookup"><span data-stu-id="65433-147">The MED-V workspace first time setup process can dynamically apply settings specified in the MED-V Workspace Packager to the image as it begins Mini-Setup.</span></span> <span data-ttu-id="65433-148">コンソールのスクリプトツールが削除され、管理者が、MED-V ワークスペースパッケージャーで構成されているオプションに基づいて初めてセットアッププロセスを開始しました。</span><span class="sxs-lookup"><span data-stu-id="65433-148">The scripting tool in the console was removed and the first time setup process is now based on options that are configured in the MED-V Workspace Packager by the administrator.</span></span>

### <span data-ttu-id="65433-149">アプリケーションの発行</span><span class="sxs-lookup"><span data-stu-id="65433-149">Application Publishing</span></span>

<span data-ttu-id="65433-150">管理者は、パッケージ前、または MED-V ワークスペースの展開後、または両方の組み合わせを使って、アプリを MED-V イメージにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="65433-150">Administrators can install applications on the MED-V image either before packaging, after the MED-V workspace is deployed, or by using a combination of both.</span></span> <span data-ttu-id="65433-151">MED-V では、アプリケーションを公開するために MED-V ワークスペースポリシーを検証するのではなく、ゲストに実際にインストールされているものを参照します。</span><span class="sxs-lookup"><span data-stu-id="65433-151">MED-V no longer examines MED-V workspace policy to publish applications, but instead refers to what is actually installed on the guest.</span></span> <span data-ttu-id="65433-152">アプリケーションはゲストにインストールされると、自動的に検出され、ホストの [**スタート**] メニューに公開され、エンドユーザーが開始する準備ができます。</span><span class="sxs-lookup"><span data-stu-id="65433-152">As applications are installed on the guest, they are automatically detected and published to the host **Start** menu and are ready to be started by the end user.</span></span>

### <span data-ttu-id="65433-153">URL リダイレクション</span><span class="sxs-lookup"><span data-stu-id="65433-153">URL Redirection</span></span>

<span data-ttu-id="65433-154">MED-V 2.0 では、管理者によって構成および管理されているポリシーに基づいて、シームレスなホスト間の web アドレスリダイレクションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="65433-154">MED-V 2.0 provides seamless host-to-guest web address redirection based on the policies configured and managed by the administrator.</span></span> <span data-ttu-id="65433-155">ゲストブラウザーに URL がリダイレクトされたら、既定の操作では、リダイレクトされたサイトにユーザーを制限しようとします。</span><span class="sxs-lookup"><span data-stu-id="65433-155">After a URL is redirected to the guest browser, the default experience is to attempt to limit the user to that redirected site.</span></span> <span data-ttu-id="65433-156">これにより、管理者によって意図されていないユーザーが実行できる参照アクティビティが最小限に抑えられます。</span><span class="sxs-lookup"><span data-stu-id="65433-156">This minimizes the browsing activities that a user can perform that are not intended by the administrator.</span></span> <span data-ttu-id="65433-157">ゲスト間のブラウザーのリダイレクトが削除されました。</span><span class="sxs-lookup"><span data-stu-id="65433-157">Guest-to-host browser redirection was removed.</span></span>

### <span data-ttu-id="65433-158">トラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="65433-158">Troubleshooting</span></span>

<span data-ttu-id="65433-159">MED-V は、トラブルシューティングのための標準的なホストベースのプロセスを利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="65433-159">MED-V now takes advantage of standard host-based processes for troubleshooting.</span></span> <span data-ttu-id="65433-160">MED-V ワークスペースは暗号化されなくなったため、Windows Virtual PC 本体の全画面表示で開くことができます。このモードでは、標準のワークステーションとして表示および操作できます。</span><span class="sxs-lookup"><span data-stu-id="65433-160">Because the MED-V workspace is no longer encrypted, it can be opened in full-screen mode within the Windows Virtual PC console, where it can be viewed and worked with as a standard workstation.</span></span> <span data-ttu-id="65433-161">さらに、ログはローカルで暗号化されなくなり、一元管理されます。</span><span class="sxs-lookup"><span data-stu-id="65433-161">In addition, the logs are no longer encrypted locally and logged centrally.</span></span> <span data-ttu-id="65433-162">MED-V では、ローカルイベントログを広範に使用できるようになりました。出力のログレベルは、情報をデバッグレベルによって簡単に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="65433-162">MED-V now makes extensive use of the local event logs, and the logging level of the output, from informational to debug levels, can be easily configured.</span></span> <span data-ttu-id="65433-163">最後に、トラブルシューティングツールキットが提供されるようになり、管理者やヘルプデスクの担当者は、すべてのトラブルシューティングオプションを視覚的に集約して表示できるようになりました。また、それぞれのニーズに最も適合するアクティビティを簡単に選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="65433-163">Finally, a troubleshooting toolkit is now provided so administrators and helpdesk personnel can have a graphical, aggregated view of all the troubleshooting options, and they can effortlessly select the activities that most suit their needs.</span></span>

<span data-ttu-id="65433-164">MED-V は、システムサービスとして実行されなくなりました。</span><span class="sxs-lookup"><span data-stu-id="65433-164">MED-V is no longer run as a system service.</span></span> <span data-ttu-id="65433-165">代わりに、ユーザーが所有するプロセスとして実行され、ユーザーがログオンしている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="65433-165">Instead, it is run as user-owned processes, and it only runs when a user is logged on.</span></span><span data-ttu-id="65433-166">システム所有のサービスによって以前提供されていた機能は、ユーザー側のプロセスで提供されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="65433-166">Functionality that was formerly provided by the system-owned service is now provided in the user-side processes.</span></span>

## <span data-ttu-id="65433-167">関連トピック</span><span class="sxs-lookup"><span data-stu-id="65433-167">Related topics</span></span>


[<span data-ttu-id="65433-168">MED-V の展開</span><span class="sxs-lookup"><span data-stu-id="65433-168">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="65433-169">MED-V の操作</span><span class="sxs-lookup"><span data-stu-id="65433-169">Operations for MED-V</span></span>](operations-for-med-v.md)

 

 





