---
title: MED-V の Windows 仮想 PC イメージの作成
description: MED-V の Windows 仮想 PC イメージの作成
author: dansimp
ms.assetid: fd7c0b1a-0769-4e7b-ad1a-dad19cca081f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f947479776e84a4c54edb10d583dd21d7ccf6f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812683"
---
# <span data-ttu-id="76557-103">MED-V の Windows 仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="76557-103">Creating a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="76557-104">MED-V ワークスペースをユーザーに提供するには、まず Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 用の MED-V workspace installer パッケージを作成するために使用する仮想ハードディスクを準備する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-104">Before you can deliver a MED-V workspace to users, you have to first prepare a virtual hard disk that you use to build the MED-V workspace installer package for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="76557-105">必要な仮想ハードディスクを準備するには、後でアプリケーションと URL リダイレクション情報をユーザーに展開できるように、必要なオペレーティングシステム、更新プログラム、ソフトウェアが含まれた Windows 仮想 PC イメージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-105">To prepare the necessary virtual hard disk, you must create a Windows Virtual PC image that contains the required operating system, updates, and software to let you later deploy applications and URL redirection information to users.</span></span> <span data-ttu-id="76557-106">このセクションでは、仮想ハードディスクを作成する方法に関するガイダンスを示します。</span><span class="sxs-lookup"><span data-stu-id="76557-106">This section provides guidance about how to create the virtual hard disk.</span></span>

<span data-ttu-id="76557-107">MED-V の仮想イメージを作成するには、次の手順に従う必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-107">To create a virtual image for MED-V, you must follow these steps.</span></span>

1.  [<span data-ttu-id="76557-108">Windows 仮想 PC イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="76557-108">Create a Windows Virtual PC image</span></span>](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)

2.  [<span data-ttu-id="76557-109">Windows XP をイメージにインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-109">Install Windows XP on the image</span></span>](#bkmk-installingwindowsxpontovpc)

3.  [<span data-ttu-id="76557-110">.NET Framework をイメージにインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-110">Install the .NET Framework on the image</span></span>](#bkmk-installingnet)

4.  [<span data-ttu-id="76557-111">イメージに更新プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="76557-111">Apply updates to the image</span></span>](#bkmk-applypatchestovpc)

5.  [<span data-ttu-id="76557-112">統合コンポーネントをインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-112">Install Integration Components</span></span>](#bkmk-installintegration)

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="76557-113">Windows 仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="76557-113">Creating a Windows Virtual PC Image</span></span>


<span data-ttu-id="76557-114">Windows 仮想 PC のイメージを作成するには、Windows Virtual PC のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="76557-114">To create a Windows Virtual PC image, see the Windows Virtual PC documentation:</span></span>

-   <span data-ttu-id="76557-115">[Windows 仮想 PC のホームページ](https://go.microsoft.com/fwlink/?LinkId=148103)( https://go.microsoft.com/fwlink/?LinkId=148103) .</span><span class="sxs-lookup"><span data-stu-id="76557-115">[Windows Virtual PC Home Page](https://go.microsoft.com/fwlink/?LinkId=148103) (https://go.microsoft.com/fwlink/?LinkId=148103).</span></span>

-   <span data-ttu-id="76557-116">[Windows VIRTUAL PC ヘルプ](https://go.microsoft.com/fwlink/?LinkId=182378)( https://go.microsoft.com/fwlink/?LinkId=182378) .</span><span class="sxs-lookup"><span data-stu-id="76557-116">[Windows Virtual PC Help](https://go.microsoft.com/fwlink/?LinkId=182378) (https://go.microsoft.com/fwlink/?LinkId=182378).</span></span>

<span data-ttu-id="76557-117">または、仮想イメージの基礎として使用する Windows Imaging (WIM) ファイルが既にある場合は、そのファイルを、MED-V ワークスペースの構築に使用する VHD に変換できます。</span><span class="sxs-lookup"><span data-stu-id="76557-117">Alternately, if you already have a Windows Imaging (WIM) file that you want to use as the basis for your virtual image, you can convert it to a VHD that you use to build the MED-V workspace.</span></span> <span data-ttu-id="76557-118">WIM を仮想ハードディスクに変換する方法の詳細については、「 [Windows 7 のネイティブ VHD サポート](https://go.microsoft.com/fwlink/?LinkId=195922)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=195922) 。</span><span class="sxs-lookup"><span data-stu-id="76557-118">For more information about how to convert a WIM to a virtual hard disk, see [Native VHD Support in Windows 7](https://go.microsoft.com/fwlink/?LinkId=195922) (https://go.microsoft.com/fwlink/?LinkId=195922).</span></span>

<span data-ttu-id="76557-119">**重要** MED-V は仮想マシンあたり1つの仮想ハードディスクのみをサポートし、各仮想ディスクには1つのパーティションのみをサポートします。</span><span class="sxs-lookup"><span data-stu-id="76557-119">**Important** MED-V only supports one virtual hard disk per virtual machine and only one partition on each virtual disk.</span></span>

 

<span data-ttu-id="76557-120">仮想ハードディスクを作成したら、Windows XP をそのイメージにインストールします。</span><span class="sxs-lookup"><span data-stu-id="76557-120">After you have created your virtual hard disk, install Windows XP on the image.</span></span>

## <a href="" id="bkmk-installingwindowsxpontovpc"></a><span data-ttu-id="76557-121">Windows 仮想 PC イメージに Windows XP をインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-121">Installing Windows XP on a Windows Virtual PC Image</span></span>


<span data-ttu-id="76557-122">MED を使用するには、MED-V ワークスペースを構築する前に windows の仮想 PC のイメージに Windows XP SP3 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-122">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

<span data-ttu-id="76557-123">Windows XP のインストール方法の詳細については、「[仮想マシンを作成する」および「ゲストオペレーティングシステムをインストール](https://go.microsoft.com/fwlink/?LinkId=182379)する (」を参照してください https://go.microsoft.com/fwlink/?LinkId=182379) 。</span><span class="sxs-lookup"><span data-stu-id="76557-123">For more information about how to install Windows XP, see [Create a virtual machine and install a guest operating system](https://go.microsoft.com/fwlink/?LinkId=182379) (https://go.microsoft.com/fwlink/?LinkId=182379).</span></span>

## <a href="" id="bkmk-installingnet"></a><span data-ttu-id="76557-124">.NET Framework 3.5 SP1 の Windows Virtual PC イメージへのインストール</span><span class="sxs-lookup"><span data-stu-id="76557-124">Installing the .NET Framework 3.5 SP1 on a Windows Virtual PC Image</span></span>


<span data-ttu-id="76557-125">.NET Framework 3.5 SP1 と更新 KB959209 を手動でインストールして、MED-V で使用するために準備する Windows 仮想 PC イメージにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-125">You must manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="76557-126">更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) ( https://go.microsoft.com/fwlink/?LinkId=204950) いくつかの既知のアプリケーション互換性の問題に対処してください。</span><span class="sxs-lookup"><span data-stu-id="76557-126">The update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

## <a href="" id="bkmk-applypatchestovpc"></a><span data-ttu-id="76557-127">Windows 仮想 PC のイメージに更新プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="76557-127">Applying Updates to the Windows Virtual PC Image</span></span>


<span data-ttu-id="76557-128">仮想マシンに Windows XP をインストールした後、必要な Windows XP の更新プログラムを、SP3 などのイメージにインストールします。</span><span class="sxs-lookup"><span data-stu-id="76557-128">After you have installed Windows XP on your virtual machine, install any required Windows XP updates on the image, such as SP3.</span></span> <span data-ttu-id="76557-129">パフォーマンスを向上させるために、特定のオプションの更新プログラムをインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="76557-129">You can also install certain optional updates for better performance.</span></span>

<span data-ttu-id="76557-130">**重要** MED では、Windows XP SP3 がゲストオペレーティングシステムで実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-130">**Important** MED-V requires that Windows XP SP3 be running on the guest operating system.</span></span>

 

<span data-ttu-id="76557-131">**警告** Windows XP の更新プログラムをインストールする場合は、MED-V ワークスペースで使用する予定のゲストの Internet Explorer のバージョンがそのままであることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76557-131">**Warning** When you install updates to Windows XP, make sure that you remain on the version of Internet Explorer in the guest that you intend to use in the MED-V workspace.</span></span> <span data-ttu-id="76557-132">たとえば、MED-V ワークスペースで Internet Explorer 6 を実行する場合は、今すぐインストールする更新プログラムに Internet Explorer 7 または Internet Explorer 8 が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76557-132">For example, if you intend to run Internet Explorer 6 in the MED-V workspace, make sure that any updates that you install now do not include Internet Explorer 7 or Internet Explorer 8.</span></span> <span data-ttu-id="76557-133">また、自動更新によって Internet Explorer がアップグレードされないようにレジストリを構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76557-133">In addition, we recommend that you configure the registry to prevent automatic updates from upgrading Internet Explorer.</span></span>

 

### <span data-ttu-id="76557-134">オプションのパフォーマンス更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-134">Installing an Optional Performance Update</span></span>

<span data-ttu-id="76557-135">必須ではありませんが、 [HOTFIX KB972435](https://go.microsoft.com/fwlink/?LinkId=201077) () 用の次の更新プログラムをインストールすることをお勧めし https://go.microsoft.com/fwlink/?LinkId=201077) ます。</span><span class="sxs-lookup"><span data-stu-id="76557-135">Although it is optional, we recommend that you install the following update for [hotfix KB972435](https://go.microsoft.com/fwlink/?LinkId=201077) (https://go.microsoft.com/fwlink/?LinkId=201077).</span></span> <span data-ttu-id="76557-136">この更新プログラムは、ターミナルサービスセッションでの共有フォルダーのパフォーマンスを向上させます。</span><span class="sxs-lookup"><span data-stu-id="76557-136">This update increases the performance of shared folders in a Terminal Services session:</span></span>

<span data-ttu-id="76557-137">**注** 更新プログラムは公開されています。</span><span class="sxs-lookup"><span data-stu-id="76557-137">**Note** The update is publicly available.</span></span> <span data-ttu-id="76557-138">ただし、Microsoft サービスのライセンス契約に同意するように求められる場合があります。</span><span class="sxs-lookup"><span data-stu-id="76557-138">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="76557-139">この修正プログラムを取得するには、連続する web ページの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="76557-139">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>

 

### <span data-ttu-id="76557-140">グループポリシーのパフォーマンス更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="76557-140">Configuring a Group Policy Performance Update</span></span>

<span data-ttu-id="76557-141">既定では、グループポリシーは一度に1バイトのコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="76557-141">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="76557-142">これにより、MED-V がドメインに参加しているときに遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="76557-142">This causes delays while MED-V is being joined to the domain.</span></span> <span data-ttu-id="76557-143">グループポリシーのパフォーマンスを向上させるには、次のレジストリキー値をレジストリに設定します。</span><span class="sxs-lookup"><span data-stu-id="76557-143">To increase the performance of Group Policy, set the following registry key value to the registry:</span></span>

<span data-ttu-id="76557-144">レジストリサブキー: HKEY \ _LOCAL \ _MACHINE ¥ (Windows nt¥)</span><span class="sxs-lookup"><span data-stu-id="76557-144">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="76557-145">エントリ: バッファーポリシーの読み取り</span><span class="sxs-lookup"><span data-stu-id="76557-145">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="76557-146">型: DWORD</span><span class="sxs-lookup"><span data-stu-id="76557-146">Type: DWORD</span></span>

<span data-ttu-id="76557-147">値: 1</span><span class="sxs-lookup"><span data-stu-id="76557-147">Value: 1</span></span>

## <a href="" id="bkmk-installintegration"></a><span data-ttu-id="76557-148">統合コンポーネントのインストール</span><span class="sxs-lookup"><span data-stu-id="76557-148">Installing Integration Components</span></span>


<span data-ttu-id="76557-149">Windows Virtual PC には、統合コンポーネントパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="76557-149">Windows Virtual PC includes the Integration Components package.</span></span> <span data-ttu-id="76557-150">これには、仮想環境と物理コンピューターの間の対話性を向上させるための機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="76557-150">This provides features that improve the interaction between the virtual environment and the physical computer.</span></span> <span data-ttu-id="76557-151">たとえば、統合コンポーネントパッケージでは、ホストとゲストコンピューターの間でマウスを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="76557-151">For example, the Integration Components package lets your mouse move between the host and the guest computers.</span></span>

<span data-ttu-id="76557-152">**重要** MED では、統合コンポーネントパッケージをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-152">**Important** MED-V requires the installation of the Integration Components package.</span></span>

 

<span data-ttu-id="76557-153">MED-V で動作するように仮想イメージを構成する場合は、統合コンポーネントパッケージをゲストオペレーティングシステムに手動でインストールして、統合機能を使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-153">When you configure the virtual image to work with MED-V, you must manually install the Integration Components package on the guest operating system to make the integration features that are available.</span></span>

<span data-ttu-id="76557-154">統合コンポーネントパッケージをインストールして使用する方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76557-154">For more information about how to install and use the Integration Components package, see the following:</span></span>

-   <span data-ttu-id="76557-155">[統合コンポーネントパッケージ () をインストールまたはアップグレードし](https://go.microsoft.com/fwlink/?LinkId=195923) https://go.microsoft.com/fwlink/?LinkId=195923) ます。</span><span class="sxs-lookup"><span data-stu-id="76557-155">[Install or Upgrade the Integration Components Package](https://go.microsoft.com/fwlink/?LinkId=195923) (https://go.microsoft.com/fwlink/?LinkId=195923).</span></span>

-   <span data-ttu-id="76557-156">[統合機能](https://go.microsoft.com/fwlink/?LinkId=195924)( https://go.microsoft.com/fwlink/?LinkId=195924) .</span><span class="sxs-lookup"><span data-stu-id="76557-156">[About Integration Features](https://go.microsoft.com/fwlink/?LinkId=195924) (https://go.microsoft.com/fwlink/?LinkId=195924).</span></span>

### <span data-ttu-id="76557-157">RemoteApp の更新プログラムをインストールする</span><span class="sxs-lookup"><span data-stu-id="76557-157">Installing RemoteApp Update</span></span>

<span data-ttu-id="76557-158">統合コンポーネントパッケージをインストールすると、「RemoteApp を有効にするために Windows XP SP3 用の更新プログラム」という更新プログラムをインストールするように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="76557-158">After you install the Integration Components package, you are prompted to install the following update: "Update for Windows XP SP3 to enable RemoteApp."</span></span> <span data-ttu-id="76557-159">これは、MED-V に必要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="76557-159">This is a required component for MED-V.</span></span>

<span data-ttu-id="76557-160">**重要** RemoteApp の更新プログラムをインストールするように求めるメッセージが表示されない場合は、手動でダウンロードしてインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-160">**Important** If you are not prompted to install the RemoteApp update, you must download and install it manually.</span></span> <span data-ttu-id="76557-161">この更新プログラムのダウンロード方法の詳細と手順については、「 [WINDOWS XP SP3 で RemoteApp を有効にするための更新プログラム](https://go.microsoft.com/fwlink/?LinkId=195925)」を参照してください https://go.microsoft.com/fwlink/?LinkId=195925) 。</span><span class="sxs-lookup"><span data-stu-id="76557-161">For more information and instructions about how to download this update, see [Update for Windows XP SP3 to enable RemoteApp](https://go.microsoft.com/fwlink/?LinkId=195925) (https://go.microsoft.com/fwlink/?LinkId=195925).</span></span>

 

### <span data-ttu-id="76557-162">リモートデスクトップを有効にする</span><span class="sxs-lookup"><span data-stu-id="76557-162">Enabling Remote Desktop</span></span>

<span data-ttu-id="76557-163">既定では、統合コンポーネントパッケージをインストールすると、リモートデスクトップは有効になります。</span><span class="sxs-lookup"><span data-stu-id="76557-163">By default, Remote Desktop is enabled after you install the Integration Components package.</span></span> <span data-ttu-id="76557-164">MED-V が動作するためには、リモートデスクトップが有効になっていることを確認し、それを無効にするグループポリシーは配布しないようにします。</span><span class="sxs-lookup"><span data-stu-id="76557-164">For MED-V to be operational, ensure that Remote Desktop is enabled, and do not distribute any Group Policy that disables it.</span></span>

<span data-ttu-id="76557-165">リモートデスクトップを有効にする方法について[は、「リモートデスクトップを有効または無効](https://go.microsoft.com/fwlink/?LinkId=201162)にする (」を参照してください https://go.microsoft.com/fwlink/?LinkId=201162) 。</span><span class="sxs-lookup"><span data-stu-id="76557-165">For information about how to enable Remote Desktop, see [Enable or disable Remote Desktop](https://go.microsoft.com/fwlink/?LinkId=201162) (https://go.microsoft.com/fwlink/?LinkId=201162).</span></span>

## <span data-ttu-id="76557-166">Internet Explorer 管理キットを使用して Internet Explorer をカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="76557-166">Customizing Internet Explorer by Using the Internet Explorer Administration Kit</span></span>


<span data-ttu-id="76557-167">必要に応じて、Internet Explorer 管理キットを使用して、ゲストオペレーティングシステムで Internet Explorer をカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="76557-167">If you want, you can use the Internet Explorer Administration Kit to customize Internet Explorer on the guest operating system.</span></span> <span data-ttu-id="76557-168">詳細については、「 [Internet Explorer 6 管理キットと展開ガイド](https://go.microsoft.com/fwlink/?LinkId=200007)(http://go.microsoft.com/fwlink/?LinkId=200007)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76557-168">For more information, see the [Internet Explorer 6 Administration Kit and Deployment Guide](https://go.microsoft.com/fwlink/?LinkId=200007) (http:// go.microsoft.com/fwlink/?LinkId=200007).</span></span>

<span data-ttu-id="76557-169">**警告** MED-V ワークスペースの Internet Explorer のカスタマイズに関連するセキュリティの問題を考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76557-169">**Warning** You should consider security concerns associated with customizing Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="76557-170">詳細については、「 [Med-v 操作のセキュリティのベストプラクティス](security-best-practices-for-med-v-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76557-170">For more information, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).</span></span>

 

<span data-ttu-id="76557-171">仮想ハードディスクが最新のゲストオペレーティングシステムと共にインストールされた後、イメージにアプリケーションをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="76557-171">After your virtual hard disk is installed with an up-to-date guest operating system, you can install applications on the image.</span></span>

## <span data-ttu-id="76557-172">関連トピック</span><span class="sxs-lookup"><span data-stu-id="76557-172">Related topics</span></span>


[<span data-ttu-id="76557-173">Windows 仮想 PC イメージ上でのアプリケーションのインストール</span><span class="sxs-lookup"><span data-stu-id="76557-173">Installing Applications on a Windows Virtual PC Image</span></span>](installing-applications-on-a-windows-virtual-pc-image.md)

[<span data-ttu-id="76557-174">MED-V の Windows 仮想 PC イメージの構成</span><span class="sxs-lookup"><span data-stu-id="76557-174">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

 

 





