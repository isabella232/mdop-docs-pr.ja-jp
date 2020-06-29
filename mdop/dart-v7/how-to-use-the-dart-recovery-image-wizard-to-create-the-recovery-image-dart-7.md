---
title: DaRT の回復イメージ ウィザードを使用して回復イメージを作成する方法
description: DaRT の回復イメージ ウィザードを使用して回復イメージを作成する方法
author: dansimp
ms.assetid: 1b8ef983-fff9-4d75-a2f6-53120c5c00c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49253a8c0bf9c9073b57712acc773e4a57e31d72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822924"
---
# <span data-ttu-id="af45b-103">DaRT の回復イメージ ウィザードを使用して回復イメージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="af45b-103">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="af45b-104">Microsoft 診断/回復ツールセット (DaRT) 7 には、Windows で使用される**Dart Recovery イメージウィザード**が含まれており、これを使って、起動可能な国際標準化機関 (ISO) 画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="af45b-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="af45b-105">ISO 画像は、CD の生のコンテンツを表すファイルです。</span><span class="sxs-lookup"><span data-stu-id="af45b-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

<span data-ttu-id="af45b-106">**DaRT の回復イメージウィザード**には、次の情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="af45b-106">The **DaRT Recovery Image Wizard** requires the following information:</span></span>

-   <span data-ttu-id="af45b-107">[**ブートイメージ**の度] DaRT 回復イメージを作成するために必要な WINDOWS 7 DVD または windows 7 のソースファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-107">**Boot Image**˚˚You must provide the path of a Windows 7 DVD or Windows 7 source files that are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="af45b-108">**ツール選択**度度 DaRT リカバリ画像に含めるツールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="af45b-108">**Tool Selection**˚˚You can select the tools to include on the DaRT recovery image.</span></span>

-   <span data-ttu-id="af45b-109">[**リモート接続**]: DaRT 回復イメージに、ヘルプデスクとエンドユーザーコンピューター間のリモート接続を確立する機能を含めるかどうかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-109">**Remote Connections**˚˚You can select whether you want the DaRT recovery image to include the ability to establish a remote connection between the helpdesk and the end-user computer.</span></span>

-   <span data-ttu-id="af45b-110">**Windows 用デバッグツール**の場合は、windows 用のデバッグツールの場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="af45b-110">**Debugging Tools for Windows**˚˚You are asked to provide the location of the Debugging Tools for Windows.</span></span>

-   <span data-ttu-id="af45b-111">**単体システム Sweeper 度の定義**。回復イメージを作成するときに最新の定義をダウンロードするか、後で定義をダウンロードするかを決めることができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-111">**Definitions for Standalone System Sweeper**˚˚You can decide whether to download the latest definitions at the time that you create the recovery image or download the definitions later.</span></span>

-   <span data-ttu-id="af45b-112">**ドライバ**度 \* また、ISO 画像にドライバを追加するかどうかを尋ねるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-112">**Drivers**˚˚You are asked whether you want to add drivers to the ISO image.</span></span>

-   <span data-ttu-id="af45b-113">**追加ファイル**の角度問題の診断に役立つファイルを、ISO イメージに追加することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-113">**Additional Files**˚˚You can add files to the ISO image that might help diagnose problems.</span></span>

-   <span data-ttu-id="af45b-114">**Iso イメージの場所**を確認する必要がある場合は、iso 画像を配置する場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="af45b-114">**ISO Image Location**˚˚You are asked to specify where the ISO image should be located.</span></span>

-   <span data-ttu-id="af45b-115">**Cd または Dvd ドライブ**の \* \* cd または dvd ドライブを使って cd または dvd を焼き付けるかどうかを指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="af45b-115">**CD/DVD Drive**˚˚You are asked to specify whether the CD or DVD drive should be used to burn the CD or DVD.</span></span>

<span data-ttu-id="af45b-116">**注** ISO イメージのサイズは、 **DaRT リカバリ画像ウィザード**で選択されたツールによって異なる場合があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-116">**Note** The ISO image size can vary, depending on the tools that were selected in the **DaRT Recovery Image Wizard**.</span></span>

 

## <span data-ttu-id="af45b-117">DaRT 回復イメージウィザードを使用して回復イメージを作成するには</span><span class="sxs-lookup"><span data-stu-id="af45b-117">To create the recovery image using the DaRT Recovery Image Wizard</span></span>


<span data-ttu-id="af45b-118">**Dart リカバリ画像ウィザード**を使用して dart リカバリ画像を作成するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af45b-118">Follow these instructions to use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span>

### <span data-ttu-id="af45b-119">DaRT リカバリ画像に含めるツールを選択するには</span><span class="sxs-lookup"><span data-stu-id="af45b-119">To select the tools to include on the DaRT recovery image</span></span>

<span data-ttu-id="af45b-120">**DaRT の回復イメージウィザード**には、**ツールの選択**ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-120">The **DaRT Recovery Image Wizard** presents a **Tool Selection** dialog box.</span></span> <span data-ttu-id="af45b-121">ツールを強調表示し、[**有効**] または [**無効**] ボタンをクリックして、DaRT リカバリ画像に含めるツールのリストからツールを選択または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-121">You can select or remove tools from the list of tools to be included on the DaRT recovery image by highlighting a tool and then clicking the **Enable** or **Disable** buttons.</span></span>

<span data-ttu-id="af45b-122">回復イメージに含めるすべてのツールを選んだら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-122">After you have selected all the tools that you want to include on the recovery image, click **Next**.</span></span>

### <span data-ttu-id="af45b-123">リモート接続を許可するオプションを追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-123">To add the option to allow remote connectivity</span></span>

<span data-ttu-id="af45b-124">[**リモート接続を許可**する] チェックボックスをオンにすると、**診断/回復ツールセット**ウィンドウに、ヘルプデスクエージェントとエンドユーザーコンピューター間のリモート接続を確立するオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-124">You can select the **Allow remote connections** check box to provide the option in the **Diagnostics and Recovery Toolset** window to establish a remote connection between the helpdesk agent and an end-user computer.</span></span> <span data-ttu-id="af45b-125">ヘルプデスクエージェントは、リモート接続を確立した後、エンドユーザーのコンピューター上の DaRT ツールをリモートの場所から実行することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-125">After a helpdesk agent establishes a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

<span data-ttu-id="af45b-126">[**ポート番号の指定**] チェックボックスをオンにして、リモート接続を確立するときに使用される特定のポート番号を入力できます。</span><span class="sxs-lookup"><span data-stu-id="af45b-126">You can select the **Specify the port number** check box to enter a specific port number that will be used when establishing a remote connection.</span></span> <span data-ttu-id="af45b-127">1 ~ 65535 の範囲のポート番号を指定できます。</span><span class="sxs-lookup"><span data-stu-id="af45b-127">You can specify a port number between 1 and 65535.</span></span> <span data-ttu-id="af45b-128">競合の可能性を最小限に抑えるため、ポート番号を1024以上にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af45b-128">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

<span data-ttu-id="af45b-129">エンドユーザーがリモート接続を確立するときに受け取るカスタマイズされたメッセージを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="af45b-129">You can also create a customized message that an end user will receive when they establish a remote connection.</span></span> <span data-ttu-id="af45b-130">メッセージの最大文字数は2048です。</span><span class="sxs-lookup"><span data-stu-id="af45b-130">The message can be a maximum of 2048 characters.</span></span>

<span data-ttu-id="af45b-131">DaRT ツールのリモート実行の詳細については、「 [Dart リカバリ画像を使ってリモートコンピューターを回復する方法](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af45b-131">For more information about remotely running the DaRT tools, see [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="af45b-132">Windows 用デバッグツールを DaRT 回復イメージに追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-132">To add the Debugging Tools for Windows to the DaRT recovery image</span></span>

<span data-ttu-id="af45b-133">**DaRT 回復イメージウィザード**の [ **Crash Analyzer** ] ダイアログボックスで、Windows 用のデバッグツールの場所を指定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="af45b-133">In the **Crash Analyzer** dialog box of the **DaRT Recovery Image Wizard**, you are asked to specify the location of the Debugging Tools for Windows.</span></span> <span data-ttu-id="af45b-134">ツールのコピーを持っていない場合は、Microsoft からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="af45b-134">If you do not have a copy of the tools, you can download them from Microsoft.</span></span> <span data-ttu-id="af45b-135">ダウンロードページへの次のリンクは、ウィザードに用意されています。 [Windows 用のデバッグツールをダウンロードしてインストール](https://go.microsoft.com/fwlink/?LinkId=99934)します。</span><span class="sxs-lookup"><span data-stu-id="af45b-135">The following link to the download page is provided in the wizard: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

<span data-ttu-id="af45b-136">**DaRT Recovery イメージウィザード**を実行しているコンピューター上のデバッグツールの場所を指定するか、または移動先のコンピューターにあるツールを使用するかどうかを決定することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-136">You can either specify the location of the debugging tools on the computer where you are running the **DaRT Recovery Image Wizard**, or you can decide to use the tools that are located on the destination computer.</span></span> <span data-ttu-id="af45b-137">別のコンピューターでコピーを使用する場合は、クラッシュを診断する各コンピューターにツールがインストールされていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-137">If you decide to use a copy on another computer, you must make sure that the tools are installed on each computer on which you are diagnosing a crash.</span></span>

<span data-ttu-id="af45b-138">**注** ISO イメージに**Crash Analyzer**を含める場合は、Windows 用のデバッグツールも含めることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="af45b-138">**Note** If you include the **Crash Analyzer** in the ISO image, we recommend that you also include the Debugging Tools for Windows.</span></span>

 

<span data-ttu-id="af45b-139">Windows 用のデバッグツールを追加するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="af45b-139">Follow these steps to add the Debugging Tools for Windows:</span></span>

1.  <span data-ttu-id="af45b-140">省略ハイパーリンクをクリックして、Windows 用デバッグツールをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="af45b-140">(Optional) Click the hyperlink to download the Debugging Tools for Windows.</span></span>

2.  <span data-ttu-id="af45b-141">次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="af45b-141">Select one of the following options:</span></span>

    -   <span data-ttu-id="af45b-142">**次の場所で、Windows 用デバッグツールを使用**します。</span><span class="sxs-lookup"><span data-stu-id="af45b-142">**Use the Debugging Tools for Windows in the following location**.</span></span> <span data-ttu-id="af45b-143">このオプションを選択すると、ツールの場所を参照できます。</span><span class="sxs-lookup"><span data-stu-id="af45b-143">If you select this option, you can browse to the location of the tools.</span></span>

    -   <span data-ttu-id="af45b-144">**修復するシステム上の Windows 用デバッグツールを見つけ**ます。</span><span class="sxs-lookup"><span data-stu-id="af45b-144">**Locate the Debugging Tools for Windows on the system that you are repairing**.</span></span> <span data-ttu-id="af45b-145">このオプションを選択すると、Windows 用デバッグツールが問題のコンピューターで見つからない場合に、**クラッシュアナライザー**が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="af45b-145">If you select this option, the **Crash Analyzer** will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

3.  <span data-ttu-id="af45b-146">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-146">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="af45b-147">単体システム Sweeper の定義を DaRT リカバリ画像に追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-147">To add definitions for Standalone System Sweeper to the DaRT recovery image</span></span>

<span data-ttu-id="af45b-148">定義は、既知のマルウェアやその他の望ましくない可能性のあるソフトウェアのリポジトリです。</span><span class="sxs-lookup"><span data-stu-id="af45b-148">Definitions are a repository of known malware and other potentially unwanted software.</span></span> <span data-ttu-id="af45b-149">マルウェアは絶えず開発されているため、**スタンドアロンのシステム Sweeper**は現在の定義に依存して、コンピューターの設定をインストール、実行、または変更しようとしているソフトウェアが望ましくない可能性のあるソフトウェアであるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="af45b-149">Because malware is being continually developed, **Standalone System Sweeper** relies on current definitions to determine whether software that is trying to install, run, or change settings on a computer is potentially unwanted or malicious software.</span></span>

<span data-ttu-id="af45b-150">DaRT リカバリ画像に最新の定義を含めるには (推奨)、[**はい、最新の定義をダウンロードしてください**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-150">To include the latest definitions in the DaRT recovery image (recommended), click **Yes, download the latest definitions.**</span></span> <span data-ttu-id="af45b-151">定義の更新プログラムが自動的に開始されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-151">The definition update starts automatically.</span></span> <span data-ttu-id="af45b-152">この処理を完了するには、インターネットに接続している必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-152">You must be connected to the Internet to complete this process.</span></span>

<span data-ttu-id="af45b-153">定義の更新をスキップするには、[**いいえ、後で定義を手動でダウンロード**します] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-153">To skip the definition update, click **No, manually download definitions later**.</span></span> <span data-ttu-id="af45b-154">定義は DaRT リカバリ画像には含まれません。</span><span class="sxs-lookup"><span data-stu-id="af45b-154">Definitions will not be included in the DaRT recovery image.</span></span>

<span data-ttu-id="af45b-155">回復イメージに最新の定義を含めない場合、または**スタンドアロンシステム Sweeper**を使用する準備ができた時点で回復イメージに含まれている定義が最新ではない場合は、**スタンドアロンシステム Sweeper**で提供されている手順に従って、スキャンを開始する前に最新の定義を取得してください。</span><span class="sxs-lookup"><span data-stu-id="af45b-155">If you decide not to include the latest definitions on the recovery image, or if the definitions included on the recovery image are no longer current by the time that you are ready to use **Standalone System Sweeper**, obtain the latest definitions before you begin a scan by following the instructions that are provided in the **Standalone System Sweeper**.</span></span>

<span data-ttu-id="af45b-156">**重要** 定義が存在しない場合はスキャンできません。</span><span class="sxs-lookup"><span data-stu-id="af45b-156">**Important** You cannot scan if there are no definitions.</span></span>

 

<span data-ttu-id="af45b-157">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-157">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="af45b-158">DaRT リカバリ画像にドライバを追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-158">To add drivers to the DaRT recovery image</span></span>

<span data-ttu-id="af45b-159">**注意** 既定では、ドライバーを DaRT 回復イメージに追加すると、そのフォルダーにあるすべての追加ファイルとサブフォルダーが回復イメージに追加されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-159">**Caution** By default, when you add a driver to the DaRT recovery image, all additional files and subfolders that are located in that folder are added into the recovery image.</span></span> <span data-ttu-id="af45b-160">詳細については、「 [DaRT 7.0 のトラブルシューティング](troubleshooting-dart-70-new-ia.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="af45b-160">For more information, see [Troubleshooting DaRT 7.0](troubleshooting-dart-70-new-ia.md).</span></span>

 

<span data-ttu-id="af45b-161">コンピューターを修復するときに必要になる可能性のある、DaRT7 の回復イメージに追加のドライバーを含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-161">You should include additional drivers on the recovery image for DaRT7 that you may need when repairing a computer.</span></span> <span data-ttu-id="af45b-162">通常、Windows DVD に含まれていないストレージまたはネットワークコントローラーが含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="af45b-162">These may typically include storage or network controllers that are not included on the Windows DVD.</span></span>

<span data-ttu-id="af45b-163">**重要** 含めるドライバーを選択するときは、ワイヤレス接続 (Bluetooth や 802.11 a/b/g/g など) が DaRT でサポートされていないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="af45b-163">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="af45b-164">回復イメージに記憶域ドライバーまたはネットワークコントローラードライバーを追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-164">To add a storage or network controller driver to the recovery image</span></span>**

1.  <span data-ttu-id="af45b-165">**DaRT 回復イメージウィザード**の [**追加ドライバー** ] ダイアログボックスで、[**デバイスの追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-165">In the **Additional Drivers** dialog box of the **DaRT Recovery Image Wizard**, click **Add Device**.</span></span>

2.  <span data-ttu-id="af45b-166">ドライバーに追加するファイルを参照し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-166">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="af45b-167">**注** **ドライバー**ファイルは、記憶域またはネットワークコントローラーの製造元によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-167">**Note** The **driver** file is provided by the manufacturer of the storage or network controller.</span></span>

     

3.  <span data-ttu-id="af45b-168">追加するすべてのドライバーについて、手順1と2を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="af45b-168">Repeat Steps 1 and 2 for every driver that you want to include.</span></span>

4.  <span data-ttu-id="af45b-169">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-169">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="af45b-170">DaRT リカバリ画像にファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="af45b-170">To add files to the DaRT recovery image</span></span>

<span data-ttu-id="af45b-171">次の手順に従って、回復イメージにファイルを追加して、コンピューターの問題の診断に使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="af45b-171">Follow these steps to add files to the recovery image so that you can use them to diagnose computer problems.</span></span>

1.  <span data-ttu-id="af45b-172">**DaRT 回復イメージウィザード**の [**追加ファイル**] ダイアログボックスで、[**ファイルの表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-172">In the **Additional Files** dialog box of the **DaRT Recovery Image Wizard**, click **Show Files**.</span></span> <span data-ttu-id="af45b-173">これにより、共有ファイルを含むフォルダーが表示されたエクスプローラーウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="af45b-173">This opens an Explorer window that displays the folder that holds the shared files.</span></span>

2.  <span data-ttu-id="af45b-174">このダイアログボックスに表示されているフォルダー内にサブフォルダーを作成します。</span><span class="sxs-lookup"><span data-stu-id="af45b-174">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="af45b-175">目的のファイルを新しいサブフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="af45b-175">Copy the files that you want to the new subfolder.</span></span>

4.  <span data-ttu-id="af45b-176">完了したら、[次へ] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="af45b-176">After you have finished, click **Next.**</span></span>

### <span data-ttu-id="af45b-177">DaRT リカバリ画像が含まれる ISO の場所を選択するには</span><span class="sxs-lookup"><span data-stu-id="af45b-177">To select a location for the ISO that contains the DaRT recovery image</span></span>

<span data-ttu-id="af45b-178">次の手順に従って、ISO イメージを作成する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="af45b-178">Follow these steps to specify the location where the ISO image is created:</span></span>

1.  <span data-ttu-id="af45b-179">**DaRT 回復イメージウィザード**の [**起動イメージの作成**] ダイアログボックスで、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-179">In the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**, click **Browse**.</span></span>

2.  <span data-ttu-id="af45b-180">[**名前を付けて保存**] ウィンドウで目的の場所を参照し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-180">Browse to the preferred location in the **Save As** window, and then click **Save**.</span></span>

3.  <span data-ttu-id="af45b-181">完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-181">After you have finished, click **Next**.</span></span>

<span data-ttu-id="af45b-182">ISO イメージのサイズは、選んだツールとウィザードで追加したファイルによって異なります。</span><span class="sxs-lookup"><span data-stu-id="af45b-182">The size of the ISO image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

<span data-ttu-id="af45b-183">この機能を使うには、CD または DVD に書き込むほとんどのプログラムにこの拡張子が必要であるため、ISO イメージのファイル名拡張子は **.iso**である必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-183">The wizard requires the ISO image to have an **.iso** file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="af45b-184">別の場所を指定しない場合は、 **DaRT70**名前の付いた iso 画像がデスクトップに作成されます。</span><span class="sxs-lookup"><span data-stu-id="af45b-184">If you do not specify a different location, the ISO image is created on your desktop with the name **DaRT70.ISO**.</span></span>

### <span data-ttu-id="af45b-185">回復イメージを CD または DVD に書き込むには</span><span class="sxs-lookup"><span data-stu-id="af45b-185">To burn the recovery image to a CD or DVD</span></span>

<span data-ttu-id="af45b-186">**DaRT Recovery イメージウィザード**で、コンピューター上に対応する cd-rw ドライブが検出された場合は、ISO イメージをディスクに書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-186">If the **DaRT Recovery Image Wizard** detects a compatible CD-RW drive on your computer, it offers to burn the ISO image to a disc for you.</span></span> <span data-ttu-id="af45b-187">CD または DVD に書き込みを行うときに、ウィザードでドライブが認識されない場合は、ドライブに付属していたプログラムなどの別のプログラムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="af45b-187">If you want to burn a CD or DVD and the wizard does not recognize your drive, you must use another program, such as the program that was included with your drive.</span></span> <span data-ttu-id="af45b-188">Duplicator、複製サービス、または CD または DVD 書き込みソフトウェアを使用して、追加のコピーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-188">You can use a duplicator, a duplicating service, or CD or DVD-burning software to make any additional copies.</span></span>

1.  <span data-ttu-id="af45b-189">**DaRT 回復イメージウィザード**の [**書き込み可能な CD/dvd に書き込み**] ダイアログボックスで、[**次の書き込み可能な cd/Dvd ドライブにイメージを書き込む**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="af45b-189">In the **Burn to a recordable CD/DVD** dialog box of the **DaRT Recovery Image Wizard**, select **Burn the image to the following recordable CD/DVD drive**.</span></span>

2.  <span data-ttu-id="af45b-190">CD または DVD ドライブを選択します。</span><span class="sxs-lookup"><span data-stu-id="af45b-190">Select the CD or DVD drive.</span></span>

    <span data-ttu-id="af45b-191">**注** ドライブが認識されず、新しいドライブをインストールする場合は、[**ドライブの一覧の更新**] をクリックして、利用可能なドライブの一覧を自動的に更新することができます。</span><span class="sxs-lookup"><span data-stu-id="af45b-191">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh Drive List** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="af45b-192">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="af45b-192">Click **Next**.</span></span>

## <span data-ttu-id="af45b-193">関連トピック</span><span class="sxs-lookup"><span data-stu-id="af45b-193">Related topics</span></span>


[<span data-ttu-id="af45b-194">DaRT 7.0 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="af45b-194">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





