---
title: DaRT 10 の回復イメージの作成
description: DaRT 10 の回復イメージの作成
author: dansimp
ms.assetid: 173556de-2f20-4ea6-9e29-fc5ccc71ebd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebb48ee140a6e3f70e05acd3f6affc6e3b71ff37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813210"
---
# <span data-ttu-id="4f26e-103">DaRT 10 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="4f26e-103">Creating the DaRT 10 Recovery Image</span></span>


<span data-ttu-id="4f26e-104">Microsoft 診断/回復ツールセット (DaRT) 10 をインストールした後、DaRT 10 の回復イメージを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-104">After installing Microsoft Diagnostics and Recovery Toolset (DaRT) 10, you create a DaRT 10 recovery image.</span></span> <span data-ttu-id="4f26e-105">回復イメージは Windows RE を起動します。これにより、DaRT ツールを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-105">The recovery image starts Windows RE, from which you can then start the DaRT tools.</span></span> <span data-ttu-id="4f26e-106">国際標準化機構 (ISO) ファイル、および Windows イメージング形式 (WIM) 画像を生成できます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-106">You can generate International Organization for Standardization (ISO) files and Windows Imaging Format (WIM) images.</span></span> <span data-ttu-id="4f26e-107">さらに、PowerShell を使用して、DaRT Recovery イメージウィザードで選択した設定を使用するスクリプトを生成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-107">In addition, you can use PowerShell to generate scripts that use the settings you select in the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="4f26e-108">後でスクリプトを使用して、同じ設定を使用して回復イメージを再構築することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-108">You can use the script later to rebuild recovery images by using the same settings.</span></span> <span data-ttu-id="4f26e-109">回復イメージには、さまざまな回復ツールが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4f26e-109">The recovery image provides a variety of recovery tools.</span></span> <span data-ttu-id="4f26e-110">ツールの説明については、「 [DaRT 10 のツールの概要](overview-of-the-tools-in-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-110">For a description of the tools, see [Overview of the Tools in DaRT 10](overview-of-the-tools-in-dart-10.md).</span></span>

<span data-ttu-id="4f26e-111">DaRT にコンピューターを起動した後、さまざまな DaRT ツールを実行して、コンピュータの診断と修復を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-111">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span> <span data-ttu-id="4f26e-112">このセクションでは、DaRT リカバリ画像の作成プロセスについて説明し、イメージの一部として含めるツールと機能を選択できるようにします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-112">This section walks you through the process of creating the DaRT recovery image and lets you select the tools and features that you want to include as part of the image.</span></span>

<span data-ttu-id="4f26e-113">DaRT リカバリ画像を作成するには、次の2つの方法のいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-113">You can create the DaRT recovery image by using either of two methods:</span></span>

-   <span data-ttu-id="4f26e-114">Windows 環境で実行される DaRT 回復イメージウィザードを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-114">Use the DaRT Recovery Image wizard, which runs in a Windows environment.</span></span>

-   <span data-ttu-id="4f26e-115">必要な値を使用して、PowerShell スクリプトの例を変更します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-115">Modify an example PowerShell script with the values you want.</span></span> <span data-ttu-id="4f26e-116">詳細については、「 [PowerShell スクリプトを使用して回復イメージを作成する方法](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-116">For more information, see [How to Use a PowerShell Script to Create the Recovery Image](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-10.md).</span></span>

<span data-ttu-id="4f26e-117">書き込み可能な CD または DVD に ISO を書き込んだり、USB フラッシュドライブに保存したり、リモートパーティションまたは回復パーティションから DaRT を起動するために使用できる形式で保存したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-117">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span>

<span data-ttu-id="4f26e-118">作成した ISO イメージは、空の CD または DVD に書き込むことができます (コンピューターに CD または DVD ドライブがある場合)。</span><span class="sxs-lookup"><span data-stu-id="4f26e-118">Once you have created the ISO image, you can burn it onto a blank CD or DVD (if your computer has a CD or DVD drive).</span></span> <span data-ttu-id="4f26e-119">この目的でコンピューターにドライブがない場合は、Cd または Dvd の書き込みに使用する一般的なプログラムを使用できます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-119">If your computer does not have a drive for this purpose, you can use most generic programs that are used to burn CDs or DVDs.</span></span>

## <span data-ttu-id="4f26e-120">イメージのアーキテクチャを選んでパスを指定する</span><span class="sxs-lookup"><span data-stu-id="4f26e-120">Select the image architecture and specify the path</span></span>


<span data-ttu-id="4f26e-121">[Windows 10 メディア] ページで、32ビットまたは64ビットの DaRT 回復イメージを作成するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-121">On the Windows 10 Media page, you select whether to create a 32-bit or 64-bit DaRT recovery image.</span></span> <span data-ttu-id="4f26e-122">32 32 ビットの DaRT 回復イメージと64ビットの Windows を使って、64ビットの DaRT 回復イメージを構築します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-122">Use the 32-bit Windows to build 32-bit DaRT recovery images, and 64-bit Windows to build 64-bit DaRT recovery images.</span></span> <span data-ttu-id="4f26e-123">単一のコンピューターを使用して、両方のアーキテクチャの種類の回復イメージを作成することはできますが、32ビットと64ビットの両方のアーキテクチャで動作する1つのイメージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f26e-123">You can use a single computer to create recovery images for both architecture types, but you cannot create one image that works on both 32-bit and 64-bit architectures.</span></span> <span data-ttu-id="4f26e-124">また、Windows 10 のインストールメディアのパスも指定します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-124">You also indicate the path of the Windows 10 installation media.</span></span> <span data-ttu-id="4f26e-125">作成する回復イメージのいずれかと一致するアーキテクチャを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-125">Choose the architecture that matches the one of the recovery image that you are creating.</span></span>

**<span data-ttu-id="4f26e-126">イメージのアーキテクチャを選んでパスを指定するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-126">To select the image architecture and specify the path</span></span>**

1.  <span data-ttu-id="4f26e-127">[ **Windows 10 メディア**] ページで、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-127">On the **Windows 10 Media** page, select one of the following:</span></span>

    -   <span data-ttu-id="4f26e-128">64ビットコンピューターの回復イメージを作成する場合は、[ **x64 (64 ビット) DaRT イメージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-128">If you are creating a recovery image for 64-bit computers, select **Create x64 (64-bit) DaRT image**.</span></span>

    -   <span data-ttu-id="4f26e-129">32ビットコンピューターの回復イメージを作成する場合は、[ **x86 (32 ビット) DaRT イメージの作成**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-129">If you are creating a recovery image for 32-bit computers, select **Create x86 (32-bit) DaRT image**.</span></span>

2.  <span data-ttu-id="4f26e-130">[ **Windows 10 &lt; 64 ビットまたは32ビット &gt; インストールメディアのルートパスを指定**してください] ボックスに、Windows 10 のインストールファイルのパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-130">In the **Specify the root path of the Windows 10 &lt;64-bit or 32-bit&gt; install media** box, type the path of the Windows 10 installation files.</span></span> <span data-ttu-id="4f26e-131">作成している回復イメージのアーキテクチャと一致するパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-131">Use a path that matches the architecture of the recovery image that you are creating.</span></span>

3.  <span data-ttu-id="4f26e-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-132">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-133">回復イメージに含めるツールを選択する</span><span class="sxs-lookup"><span data-stu-id="4f26e-133">Select the tools to include on the recovery image</span></span>


<span data-ttu-id="4f26e-134">[ツール] ページで、さまざまなツールを選択して回復イメージに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-134">On the Tools page, you can select numerous tools to include on the recovery image.</span></span> <span data-ttu-id="4f26e-135">これらのツールは、エンドユーザーが DaRT イメージを起動したときに利用できます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-135">These tools will be available to end users when they boot into the DaRT image.</span></span> <span data-ttu-id="4f26e-136">ただし、DaRT イメージの作成時にリモート接続を有効にした場合は、どのツールを使用するかに関係なく、ヘルプデスクの作業者がエンドユーザーのコンピューターに接続すると、すべてのツールが利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-136">However, if you enable remote connectivity when creating the DaRT image, all of the tools will be available when a help desk worker connects to the end user’s computer, regardless of which tools you chose to include on the image.</span></span>

<span data-ttu-id="4f26e-137">エンドユーザーによるこれらのツールへのアクセスを制限しながら、リモート接続ビューアーを使用してツールへのフルアクセスを保持するには、[ツール] ページでこれらのツールを選択しないでください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-137">To restrict end-user access to these tools, but still retain full access to the tools through the Remote Connection Viewer, do not select those tools on the Tools page.</span></span> <span data-ttu-id="4f26e-138">エンドユーザーはリモート接続のみを使用できるようになり、回復イメージから除外したツールは表示されますが、アクセスはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-138">End users will be able to use only Remote Connection and will be able to see, but not access, any tools that you exclude from the recovery image.</span></span>

**<span data-ttu-id="4f26e-139">回復イメージに含めるツールを選ぶには</span><span class="sxs-lookup"><span data-stu-id="4f26e-139">To select the tools to include on the recovery image</span></span>**

1.  <span data-ttu-id="4f26e-140">[**ツール**] ページで、画像に含める各ツールの横にあるチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-140">On the **Tools** page, select the check box beside each tool that you want to include on the image.</span></span>

2.  <span data-ttu-id="4f26e-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-141">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-142">ヘルプデスクによるリモート接続を許可するかどうかを選ぶ</span><span class="sxs-lookup"><span data-stu-id="4f26e-142">Choose whether to allow remote connectivity by a help desk</span></span>


<span data-ttu-id="4f26e-143">[リモート接続] ページでは、ヘルプデスクワーカーがエンドユーザーのコンピューターで DaRT ツールにリモート接続して実行できるようにするかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-143">On the Remote Connection page, you can choose to enable a help desk worker to remotely connect to and run the DaRT tools on an end user’s computer.</span></span> <span data-ttu-id="4f26e-144">[診断/回復ツールセット] ウィンドウで、[リモート接続] オプションが利用可能なオプションとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-144">The remote connectivity option is then shown as an available option in the Diagnostics and Recovery Toolset window.</span></span> <span data-ttu-id="4f26e-145">ヘルプデスクのワーカーがリモート接続を確立した後、エンドユーザーのコンピューター上の DaRT ツールをリモートの場所から実行することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-145">After help desk workers establish a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

**<span data-ttu-id="4f26e-146">ヘルプデスクの担当者によるリモート接続を許可するかどうかを選ぶには</span><span class="sxs-lookup"><span data-stu-id="4f26e-146">To choose whether to allow remote connectivity by help desk workers</span></span>**

1.  <span data-ttu-id="4f26e-147">[**リモート接続**] ページで、[**リモート**接続を許可する] チェックボックスをオンにしてリモート接続を許可するか、チェックボックスをオフにしてリモート接続を禁止します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-147">On the **Remote Connection** page, select the **Allow remote connections** check box to allow remote connections, or clear the check box to prevent remote connections.</span></span>

2.  <span data-ttu-id="4f26e-148">[**リモート接続を許可**する] チェックボックスをオフにした場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-148">If you cleared the **Allow remote connections** check box, click **Next**.</span></span> <span data-ttu-id="4f26e-149">それ以外の場合は、次の手順に進み、リモート接続の構成を続行します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-149">Otherwise, go to the next step to continue configuring remote connectivity.</span></span>

3.  <span data-ttu-id="4f26e-150">次のいずれかのオプションを選択してください:</span><span class="sxs-lookup"><span data-stu-id="4f26e-150">Select one of the following:</span></span>

    -   <span data-ttu-id="4f26e-151">Windows で開いているポート番号を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-151">Let Windows choose an open port number.</span></span>

    -   <span data-ttu-id="4f26e-152">ポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-152">Specify the port number.</span></span> <span data-ttu-id="4f26e-153">このオプションを選択した場合は、オプションの下のフィールドに 1 ~ 65535 のポート番号を入力します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-153">If you select this option, enter a port number between 1 and 65535 in the field beneath the option.</span></span> <span data-ttu-id="4f26e-154">このポート番号は、リモート接続を確立するときに使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-154">This port number will be used when establishing a remote connection.</span></span> <span data-ttu-id="4f26e-155">競合の可能性を最小限に抑えるため、ポート番号を1024以上にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-155">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

4.  <span data-ttu-id="4f26e-156">(オプション)**リモート接続のウェルカム**メッセージボックスに、リモート接続を確立するときにエンドユーザーが受信するカスタマイズされたメッセージを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-156">(Optional) in the **Remote connection welcome** message box, create a customized message that end users receive when they establish a remote connection.</span></span> <span data-ttu-id="4f26e-157">メッセージの最大文字数は2048です。</span><span class="sxs-lookup"><span data-stu-id="4f26e-157">The message can be a maximum of 2048 characters.</span></span>

5.  <span data-ttu-id="4f26e-158">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-158">Click **Next**.</span></span>

    <span data-ttu-id="4f26e-159">DaRT ツールをリモートで実行する方法について詳しくは、「 [Dart リカバリ画像を使ってリモートコンピューターを回復する方法](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-10.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-159">For more information about running the DaRT tools remotely, see [How to Recover Remote Computers by Using the DaRT Recovery Image](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-10.md).</span></span>

## <span data-ttu-id="4f26e-160">回復イメージにドライバーを追加する</span><span class="sxs-lookup"><span data-stu-id="4f26e-160">Add drivers to the recovery image</span></span>


<span data-ttu-id="4f26e-161">[詳細オプション] ページの [ドライバー] タブでは、コンピューターの修復時に必要になる可能性のあるその他のデバイスドライバーを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-161">On the Drivers tab of the Advanced Options page, you can add additional device drivers that you may need when repairing a computer.</span></span> <span data-ttu-id="4f26e-162">通常、Windows 10 によって提供される記憶域またはネットワークコントローラーが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-162">These may typically include storage or network controllers that Windows 10 does not provide.</span></span> <span data-ttu-id="4f26e-163">ドライバーは、画像の作成時にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-163">Drivers are installed when the image is created.</span></span>

<span data-ttu-id="4f26e-164">**重要** 含めるドライバーを選択するときは、ワイヤレス接続 (Bluetooth や 802.11 a/b/g/g など) が DaRT でサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-164">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="4f26e-165">回復イメージにドライバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-165">To add drivers to the recovery image</span></span>**

1.  <span data-ttu-id="4f26e-166">[**詳細設定] オプション**ページで、[**ドライバー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-166">On the **Advanced Options** page, click the **Drivers** tab.</span></span>

2.  <span data-ttu-id="4f26e-167">**[追加]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-167">Click **Add**.</span></span>

3.  <span data-ttu-id="4f26e-168">ドライバーに追加するファイルを参照し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-168">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="4f26e-169">**注** ドライバーファイルは、記憶域またはネットワークコントローラーの製造元によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-169">**Note** The driver file is provided by the manufacturer of the storage or network controller.</span></span>

     

4.  <span data-ttu-id="4f26e-170">追加するすべてのドライバーについて、手順2と3を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-170">Repeat Steps 2 and 3 for every driver that you want to include.</span></span>

5.  <span data-ttu-id="4f26e-171">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-171">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-172">回復イメージに WinPE オプションパッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="4f26e-172">Add WinPE optional packages to the recovery image</span></span>


<span data-ttu-id="4f26e-173">[詳細オプション] ページの [WinPE] タブで、DaRT イメージに WinPE オプションパッケージを追加できます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-173">On the WinPE tab of the Advanced Options page, you can add WinPE optional packages to the DaRT image.</span></span> <span data-ttu-id="4f26e-174">これらのパッケージは Windows ADK に含まれています。これは、DaRT 回復イメージウィザードのインストール必須条件です。</span><span class="sxs-lookup"><span data-stu-id="4f26e-174">These packages are part of the Windows ADK, which is an installation prerequisite for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="4f26e-175">選択できるツールはすべてオプションです。</span><span class="sxs-lookup"><span data-stu-id="4f26e-175">The tools that you can select are all optional.</span></span> <span data-ttu-id="4f26e-176">[ツール] ページで選択したツールに基づいて、必要なパッケージが自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-176">Any required packages are added automatically, based on the tools you selected on the Tools page.</span></span>

<span data-ttu-id="4f26e-177">スクラッチ領域のサイズを指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-177">You can also specify the size of the scratch space.</span></span> <span data-ttu-id="4f26e-178">スクラッチ領域とは、DaRT を実行するために確保された RAM ディスクスペースの量です。</span><span class="sxs-lookup"><span data-stu-id="4f26e-178">Scratch space is the amount of RAM disk space that is set aside for DaRT to run.</span></span> <span data-ttu-id="4f26e-179">スクラッチ領域は、エンドユーザーのハードディスクが利用できない場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="4f26e-179">The scratch space is useful in case the end user’s hard disk is not available.</span></span> <span data-ttu-id="4f26e-180">追加のツールとドライバーを実行している場合は、スクラッチ領域を増やすことができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-180">If you are running additional tools and drivers, you may want to increase the scratch space.</span></span>

**<span data-ttu-id="4f26e-181">回復イメージに WinPE オプションパッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-181">To add WinPE optional packages to the recovery image</span></span>**

1.  <span data-ttu-id="4f26e-182">[**詳細オプション**] ページで、[ **WinPE** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-182">On the **Advanced Options** page, click the **WinPE** tab.</span></span>

2.  <span data-ttu-id="4f26e-183">イメージに含める各パッケージの横にあるチェックボックスをオンにするか、[**名前**] チェックボックスをオンにしてすべてのパッケージを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-183">Select the check box beside each package that you want to include on the image, or click the **Name** check box to select all of the packages.</span></span>

3.  <span data-ttu-id="4f26e-184">[**スクラッチ領域**] フィールドで、エンドユーザーのハードディスクが利用できない場合の DaRT の実行に割り当てる RAM ディスクスペースの量を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-184">In the **Scratch Space** field, select the amount of RAM disk space to allocate for running DaRT in case the end user’s hard disk is not available.</span></span>

4.  <span data-ttu-id="4f26e-185">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-185">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-186">クラッシュアナライザーのデバッグツールを追加する</span><span class="sxs-lookup"><span data-stu-id="4f26e-186">Add the debugging tools for Crash Analyzer</span></span>


<span data-ttu-id="4f26e-187">ISO イメージに Crash Analyzer ツールを含める場合は、Windows 用のデバッグツールも含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-187">If you include the Crash Analyzer tool in the ISO image, you must also include the Debugging Tools for Windows.</span></span> <span data-ttu-id="4f26e-188">[詳細オプション] ページの [Crash Analyzer] タブで、Windows 10 デバッグツールのパスを入力します。これは、Crash Analyzer でメモリダンプファイルを分析するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-188">On the Crash Analyzer tab of the Advanced Options page, you enter the path of the Windows 10 Debugging Tools, which Crash Analyzer uses to analyze memory dump files.</span></span> <span data-ttu-id="4f26e-189">DaRT 回復イメージウィザードを実行しているコンピューター上のツールを使用することも、エンドユーザーのコンピューター上のツールを使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-189">You can use the tools that are on the computer where you are running the DaRT Recovery Image wizard, or you can use the tools that are on the end-user computer.</span></span> <span data-ttu-id="4f26e-190">エンドユーザーコンピューターでツールを使用することにした場合、診断するすべてのコンピューターに、デバッグツールがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-190">If you decide to use the tools on the end-user computer, remember that every computer that you diagnose must have the Debugging Tools installed.</span></span>

<span data-ttu-id="4f26e-191">Microsoft Windows ソフトウェア開発キット (SDK) または Microsoft Windows 開発キット (WDK) をインストールした場合は、Windows 10 デバッグツールが既定で回復イメージに追加され、デバッグツールへのパスが自動的に入力されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-191">If you installed the Microsoft Windows Software Development Kit (SDK) or the Microsoft Windows Development Kit (WDK), the Windows 10 Debugging Tools are added to the recovery image by default, and the path to the Debugging Tools is automatically filled in.</span></span> <span data-ttu-id="4f26e-192">既定のファイルパスで示されている場所以外の場所にファイルがある場合は、Windows 10 デバッグツールのパスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-192">You can change the path of the Windows 10 Debugging Tools if the files are located somewhere other than the location indicated by the default file path.</span></span> <span data-ttu-id="4f26e-193">ウィザードのリンクにより、Windows 用のデバッグツールがまだインストールされていない場合は、ダウンロードしてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-193">A link in the wizard lets you download and install debugging tools for Windows if they are not already installed.</span></span>

<span data-ttu-id="4f26e-194">Windows デバッグツールをダウンロードするには、「 [windows 用デバッグツール](https://go.microsoft.com/fwlink/?LinkId=266248)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f26e-194">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span> <span data-ttu-id="4f26e-195">既定の場所にデバッグツールをインストールします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-195">Install the Debugging Tools to the default location.</span></span>

<span data-ttu-id="4f26e-196">**注** DaRT ウィザードは、レジストリキーのツールをチェックし `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` ます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-196">**Note** The DaRT wizard checks for the tools in the `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` registry key.</span></span> <span data-ttu-id="4f26e-197">レジストリ値が存在しない場合、ウィザードはシステムアーキテクチャに応じて次のいずれかの場所を検索します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-197">If the registry value is not there, the wizard looks in one of the following locations, depending on your system architecture:</span></span>

`%ProgramFilesX86%\Windows Kits\10.0\Debuggers\x64`

`%ProgramFilesX86%\Windows Kits\10.0\Debuggers\x86`

 

**<span data-ttu-id="4f26e-198">クラッシュアナライザーのデバッグツールを追加するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-198">To add the debugging tools for Crash Analyzer</span></span>**

1.  <span data-ttu-id="4f26e-199">[**詳細オプション**] ページで、[**クラッシュアナライザー** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-199">On the **Advanced Options** page, click the **Crash Analyzer** tab.</span></span>

2.  <span data-ttu-id="4f26e-200">省略[**デバッグツールのダウンロード**] をクリックして、Windows 用のデバッグツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-200">(Optional) Click **Download the Debugging Tools** to download the Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="4f26e-201">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-201">Select one of the following options:</span></span>

    -   <span data-ttu-id="4f26e-202">**Windows 10 の &lt; 64 ビットまたは32ビットの &gt; デバッグツールを含め**ます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-202">**Include the Windows 10 &lt;64-bit or 32-bit&gt; Debugging Tools**.</span></span> <span data-ttu-id="4f26e-203">このオプションを選択した場合は、パスがまだ表示されていない場合は、ツールの場所を参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-203">If you select this option, browse to and select the location of the tools if the path is not already displaying.</span></span>

    -   <span data-ttu-id="4f26e-204">デバッグ**するシステムのデバッグツールを使い**ます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-204">**Use the Debugging Tools from the system that is being debugged**.</span></span> <span data-ttu-id="4f26e-205">このオプションを選択すると、Windows 用デバッグツールが問題のコンピューターで見つからない場合に、クラッシュアナライザーが機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-205">If you select this option, the Crash Analyzer will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

4.  <span data-ttu-id="4f26e-206">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-206">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-207">作成する回復イメージファイルの種類を選択する</span><span class="sxs-lookup"><span data-stu-id="4f26e-207">Select the types of recovery image files to create</span></span>


<span data-ttu-id="4f26e-208">[イメージの作成] ページで、回復イメージの出力フォルダーを選び、画像名を入力して、作成する DaRT 回復イメージファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-208">On the Create Image page, you choose an output folder for the recovery image, enter an image name, and select the types of DaRT recovery image files to create.</span></span> <span data-ttu-id="4f26e-209">回復イメージの作成プロセス中に、Windows ソースファイルが展開され、DaRT ファイルがそのファイルにコピーされ、このページで選択したファイル形式でイメージが再パックされます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-209">During the recovery image creation process, Windows source files are unpacked, DaRT files are copied to it, and the image is then “re-packed” into the file formats that you select on this page.</span></span>

<span data-ttu-id="4f26e-210">使用できる画像ファイルの種類は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="4f26e-210">The available image file types are:</span></span>

-   <span data-ttu-id="4f26e-211">**Windows Imaging File (WIM)** -DaRT をプレブート実行環境 (PXE) またはローカルパーティションに展開するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-211">**Windows Imaging File (WIM)** - used to deploy DaRT to a preboot execution environment (PXE) or local partition).</span></span>

-   <span data-ttu-id="4f26e-212">**国際標準化機構 (ISO)** – CD または DVD に展開したり、仮想マシン (VM) で使用したりするために使用されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-212">**International Standards Organization (ISO)** – used to deploy to CD or DVD, or for use in virtual machines (VM)s).</span></span> <span data-ttu-id="4f26e-213">この機能を使うには、CD または DVD に書き込むほとんどのプログラムにこの拡張子が必要であるため、ISO の画像に .iso ファイル名の拡張子が付いている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-213">The wizard requires that the ISO image have an .iso file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="4f26e-214">別の場所を指定しない場合は、DaRT10 名前の付いた ISO 画像がデスクトップに作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-214">If you do not specify a different location, the ISO image is created on your desktop with the name DaRT10.ISO.</span></span>

-   <span data-ttu-id="4f26e-215">**PowerShell スクリプト**– Dart リカバリ画像ウィザードを使用して選択できるのと同じオプションを提供する dart リカバリ画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-215">**PowerShell script** – creates a DaRT recovery image with commands that provide essentially the same options that you can select by using the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="4f26e-216">このスクリプトでは、DaRT リカバリ画像のファイルを追加または変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-216">The script also enables you to add or changes files in the DaRT recovery image.</span></span>

<span data-ttu-id="4f26e-217">このページで [イメージの編集] チェックボックスをオンにした場合、イメージの作成プロセス中に回復イメージをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-217">If you select the Edit Image check box on this page, you can customize the recovery image during the image creation process.</span></span> <span data-ttu-id="4f26e-218">たとえば、"winpeshl.ini" ファイルを変更して、カスタムの起動順序を作成したり、サードパーティ製のツールを追加したりできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-218">For example, you can change the “winpeshl.ini” file to create a custom startup order or to add third-party tools.</span></span>

**<span data-ttu-id="4f26e-219">作成する回復イメージファイルの種類を選ぶには</span><span class="sxs-lookup"><span data-stu-id="4f26e-219">To select the types of recovery image files to create</span></span>**

1.  <span data-ttu-id="4f26e-220">[**イメージの作成**] ページで [**参照**] をクリックして、画像ファイルの出力フォルダーを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-220">On the **Create Image** page, click **Browse** to choose the output folder for the image file.</span></span>

    <span data-ttu-id="4f26e-221">**注** 画像のサイズは、選んだツールとウィザードで追加したファイルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="4f26e-221">**Note** The size of the image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

     

2.  <span data-ttu-id="4f26e-222">[**イメージ名**] ボックスに DaRT リカバリ画像の名前を入力するか、既定の名前 (DaRT10) をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-222">In the **Image name** box, enter a name for the DaRT recovery image, or accept the default name, which is DaRT10.</span></span>

    <span data-ttu-id="4f26e-223">ウィザードによって、この名前の出力パス内にサブフォルダーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-223">The wizard creates a subfolder in the output path by this name.</span></span>

3.  <span data-ttu-id="4f26e-224">作成する画像ファイルの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-224">Select the types of image files that you want to create.</span></span>

4.  <span data-ttu-id="4f26e-225">次のいずれかのオプションを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-225">Choose one of the following:</span></span>

    -   <span data-ttu-id="4f26e-226">イメージファイルを作成する前に回復イメージのファイルを変更するには、[**イメージの編集**] チェックボックスをオンにし、[**準備**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-226">To change the files in the recovery image before you create the image files, select the **Edit Image** check box, and then click **Prepare**.</span></span>

    -   <span data-ttu-id="4f26e-227">ファイルを変更せずに回復イメージを作成するには、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-227">To create the recovery image without changing the files, click **Create**.</span></span>

5.  

    <span data-ttu-id="4f26e-228">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-228">Click **Next**.</span></span>

## <span data-ttu-id="4f26e-229">回復イメージファイルを編集する</span><span class="sxs-lookup"><span data-stu-id="4f26e-229">Edit the recovery image files</span></span>


<span data-ttu-id="4f26e-230">回復イメージを編集できるのは、[イメージの作成] ページの [イメージの編集] チェックボックスをオンにした場合のみです。</span><span class="sxs-lookup"><span data-stu-id="4f26e-230">You can edit the recovery image only if you selected the Edit Image check box on the Create Image page.</span></span> <span data-ttu-id="4f26e-231">回復イメージを編集する準備ができたら、起動可能なメディアを作成する前に、回復イメージファイルを追加して変更することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-231">After the recovery image has been prepared for editing, you can add and modify the recovery image files before creating the bootable media.</span></span> <span data-ttu-id="4f26e-232">たとえば、スタートアップのカスタム注文を作成したり、さまざまなサードパーティ製のツールを追加したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-232">For example, you can create a custom order for startup, add various third-party tools, and so on.</span></span>

**<span data-ttu-id="4f26e-233">回復イメージファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-233">To edit the recovery image files</span></span>**

1.  <span data-ttu-id="4f26e-234">[**イメージの編集**] ページで、[Windows エクスプローラーで**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-234">On the **Edit Image** page, click **Open** in Windows Explorer.</span></span>

2.  <span data-ttu-id="4f26e-235">このダイアログボックスに表示されているフォルダー内にサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-235">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="4f26e-236">目的のファイルを新しいサブフォルダーにコピーするか、不要なファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-236">Copy the files that you want to the new subfolder, or remove files that you don’t want.</span></span>

4.  <span data-ttu-id="4f26e-237">[**作成**] をクリックして、回復イメージの作成を開始します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-237">Click **Create** to start creating the recovery image.</span></span>

## <span data-ttu-id="4f26e-238">回復イメージファイルを生成する</span><span class="sxs-lookup"><span data-stu-id="4f26e-238">Generate the recovery image files</span></span>


<span data-ttu-id="4f26e-239">[ファイルの生成] ページで、[イメージの作成] ページで選択したファイルの種類に対応する DaRT 回復イメージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-239">On the Generate Files page, the DaRT recovery image is generated for the file types that you selected on the Create Image page.</span></span>

**<span data-ttu-id="4f26e-240">回復イメージファイルを生成するには</span><span class="sxs-lookup"><span data-stu-id="4f26e-240">To generate the recovery image files</span></span>**

-   <span data-ttu-id="4f26e-241">[**ファイルの生成**] ページで、[**次**へ] をクリックして、回復イメージファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="4f26e-241">On the **Generate Files** page, click **Next** to generate the recovery image files.</span></span>

## <span data-ttu-id="4f26e-242">回復イメージを CD、DVD、または USB にコピーする</span><span class="sxs-lookup"><span data-stu-id="4f26e-242">Copy the recovery image to a CD, DVD, or USB</span></span>


<span data-ttu-id="4f26e-243">[起動可能なメディアの作成] ページでは、必要に応じて、画像ファイルを CD、DVD、または USB フラッシュドライブ (UFD) にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-243">On the Create Bootable Media page, you can optionally copy the image file to a CD, DVD, or USB flash drive (UFD).</span></span> <span data-ttu-id="4f26e-244">ウィザードを再起動して、このページから追加の起動可能なメディアを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-244">You can also create additional bootable media from this page by restarting the wizard.</span></span>

<span data-ttu-id="4f26e-245">**注** プレブート実行環境 (PXE) とローカルイメージ展開は、このツールでネイティブにサポートされていません。そのため、System Center Configuration Manager サーバーや Microsoft 開発ツールキットなどの追加のエンタープライズツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f26e-245">**Note** The Preboot execution environment (PXE) and local image deployment are not supported natively by this tool since they require additional enterprise tools, such as System Center Configuration Manager server and Microsoft Development Toolkit.</span></span>

 

**<span data-ttu-id="4f26e-246">回復イメージを CD、DVD、または USB にコピーするには</span><span class="sxs-lookup"><span data-stu-id="4f26e-246">To copy the recovery image to a CD, DVD, or USB</span></span>**

1.  <span data-ttu-id="4f26e-247">[**ブータブルメディアの作成**] ページで、コピーする iso ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-247">On the **Create Bootable Media** page, select the iso file that you want to copy.</span></span>

2.  <span data-ttu-id="4f26e-248">CD、DVD、または USB を挿入して、ドライブを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-248">Insert a CD, DVD, or USB, and then select the drive.</span></span>

    <span data-ttu-id="4f26e-249">**注** ドライブが認識されず、新しいドライブをインストールする場合は、[**更新**] をクリックして、利用可能なドライブの一覧を自動的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="4f26e-249">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="4f26e-250">[**ブート可能なメディアを作成する**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-250">Click the **Create Bootable Media** button.</span></span>

4.  <span data-ttu-id="4f26e-251">別の回復イメージを作成するには、[再起動] をクリックするか、必要なすべてのメディアの作成が完了したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f26e-251">To create another recovery image, click Restart, or click **Close** if you have finished creating all of the media that you want.</span></span>

## <span data-ttu-id="4f26e-252">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4f26e-252">Related topics</span></span>


[<span data-ttu-id="4f26e-253">DaRT 10 のツールの概要</span><span class="sxs-lookup"><span data-stu-id="4f26e-253">Overview of the Tools in DaRT 10</span></span>](overview-of-the-tools-in-dart-10.md)

[<span data-ttu-id="4f26e-254">DaRT 10 の展開</span><span class="sxs-lookup"><span data-stu-id="4f26e-254">Deploying DaRT 10</span></span>](deploying-dart-10.md)

 

 





