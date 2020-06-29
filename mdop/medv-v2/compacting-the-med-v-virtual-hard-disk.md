---
title: MED-V 仮想ハード ディスクの最適化
description: MED-V 仮想ハード ディスクの最適化
author: dansimp
ms.assetid: 5e6122d1-9847-4b33-adab-594919eec3c5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f71aefb1e4e901078b4d0a421065b7bd5acdf0ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823277"
---
# <span data-ttu-id="01686-103">MED-V 仮想ハード ディスクの最適化</span><span class="sxs-lookup"><span data-stu-id="01686-103">Compacting the MED-V Virtual Hard Disk</span></span>


<span data-ttu-id="01686-104">必須ではありませんが、仮想ハードディスク (VHD) を圧縮して、Windows 仮想 PC イメージを構成する前に、空のディスク領域を再利用し、VHD のサイズを小さくすることができます。</span><span class="sxs-lookup"><span data-stu-id="01686-104">Although it is optional, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you configure the Windows Virtual PC image.</span></span>

<span data-ttu-id="01686-105">**重要** 続行する前に、Windows XP イメージのバックアップコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="01686-105">**Important** Before you proceed, create a backup copy of your Windows XP image.</span></span>

 

**<span data-ttu-id="01686-106">仮想ハードディスクの準備</span><span class="sxs-lookup"><span data-stu-id="01686-106">Preparing the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="01686-107">Windows XP のイメージを開きます。</span><span class="sxs-lookup"><span data-stu-id="01686-107">Open your Windows XP image.</span></span>

    <span data-ttu-id="01686-108">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc**]、[ **windows 仮想**pc] の順にクリックして、windows XP のイメージをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-108">Click **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, then double-click your Windows XP image.</span></span>

2.  <span data-ttu-id="01686-109">DLL キャッシュをクリアします。</span><span class="sxs-lookup"><span data-stu-id="01686-109">Clear the DLL cache.</span></span>

    1.  <span data-ttu-id="01686-110">仮想マシンのコマンドプロンプトで、「 **sfc/cachesize = 1**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="01686-110">At a command prompt in the virtual machine, type **sfc /cachesize=1**.</span></span>

    2.  <span data-ttu-id="01686-111">仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="01686-111">Restart the virtual machine.</span></span>

    3.  <span data-ttu-id="01686-112">仮想マシンのコマンドプロンプトで、「 **sfc/purgecache**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="01686-112">At a command prompt in the virtual machine, type **sfc /purgecache**.</span></span>

3.  <span data-ttu-id="01686-113">アンインストーラー、一時ファイル、ログファイル、ページファイル、共有フォルダーなどの不要なファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="01686-113">Delete unnecessary files, such as uninstallers, temp files, log files, page files, shared folders, and so on.</span></span>

4.  <span data-ttu-id="01686-114">システムの復元をオフにします。</span><span class="sxs-lookup"><span data-stu-id="01686-114">Turn off System Restore.</span></span> <span data-ttu-id="01686-115">この手順は、Sysprep.inf ファイルで指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="01686-115">You can also specify this step in your Sysprep.inf file.</span></span>

    1.  <span data-ttu-id="01686-116">**コントロールパネル**で、[**システム**] をダブルクリックし、[**システムの復元**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="01686-116">In **Control Panel**, double-click **System**, and then select the **System Restore** tab.</span></span>

    2.  <span data-ttu-id="01686-117">[**システムの復元をオフにする**] を選び、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-117">Select **Turn off System Restore**, and then click **OK**.</span></span>

5.  <span data-ttu-id="01686-118">イベントログの最大サイズを設定し、すべてのイベントを消去します。</span><span class="sxs-lookup"><span data-stu-id="01686-118">Set maximum event log sizes and clear all events.</span></span>

    1.  <span data-ttu-id="01686-119">イベントビューアーを開きます。</span><span class="sxs-lookup"><span data-stu-id="01686-119">Open the event viewer.</span></span>

        <span data-ttu-id="01686-120">[**スタート**] をクリックし、[**コントロールパネル**] をクリックし、[**管理ツール**] をダブルクリックして、[**イベントビューアー**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-120">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, then double-click **Event Viewer**.</span></span>

    2.  <span data-ttu-id="01686-121">[**アプリケーション**] を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-121">Right-click **Application**, and click **Properties**.</span></span>

    3.  <span data-ttu-id="01686-122">[ **Log size** ] 領域で、[ **Maximum Log size** ] を [512kb] に設定し、[**必要に応じてイベントを上書き**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01686-122">In the **Log Size** area, set **Maximum Log Size** to 512KB and then select **Overwrite events as needed**.</span></span>

    4.  <span data-ttu-id="01686-123">[**ログの消去**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-123">Click **Clear Log**.</span></span> <span data-ttu-id="01686-124">[**イベントビューアー** ] ダイアログボックスが表示されたら、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-124">In the **Event Viewer** dialog box that appears, click **No**.</span></span>

    5.  <span data-ttu-id="01686-125">[**プロパティ**] ウィンドウで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-125">In the **Properties** window, click **OK**.</span></span>

    6.  <span data-ttu-id="01686-126">**セキュリティ**と**システム**ログについて、手順 a ~ e を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="01686-126">Repeat steps a through e for the **Security** and **System** logs.</span></span>

6.  <span data-ttu-id="01686-127">ディスククリーンアップツールを実行します。</span><span class="sxs-lookup"><span data-stu-id="01686-127">Run the Disk Cleanup Tool.</span></span>

    <span data-ttu-id="01686-128">[**スタート**] をクリックし、[**すべてのプログラム**]、[**アクセサリ**]、[**システムツール**]、[**ディスククリーンアップ**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-128">Click **Start**, click **All Programs**, click **Accessories**, click **System Tools**, and then click **Disk Cleanup**.</span></span>

7.  <span data-ttu-id="01686-129">必要に応じて、アプリケーションでページファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="01686-129">Configure your page file as needed for your applications.</span></span>

    1.  <span data-ttu-id="01686-130">**コントロールパネル**で、[**システム**] をダブルクリックし、[**詳細設定**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="01686-130">In **Control Panel**, double-click **System**, and then select the **Advanced** tab.</span></span>

    2.  <span data-ttu-id="01686-131">[**パフォーマンス**] 領域で、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-131">In the **Performance** area, click **Settings**.</span></span>

    3.  <span data-ttu-id="01686-132">[**仮想メモリ**] 領域で、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-132">In the **Virtual Memory** area, click **Change**.</span></span>

    4.  <span data-ttu-id="01686-133">ページファイルの設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="01686-133">Configure your page file settings.</span></span>

8.  <span data-ttu-id="01686-134">Windows XP のイメージをシャットダウンします。</span><span class="sxs-lookup"><span data-stu-id="01686-134">Shut down the Windows XP image.</span></span>

**<span data-ttu-id="01686-135">仮想ハードディスクの最適化と最適化前の方法</span><span class="sxs-lookup"><span data-stu-id="01686-135">Defragmenting and Pre-compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="01686-136">Windows 7 を実行しているホストコンピューターの**コントロールパネル**で、[**管理ツール**] をクリックし、[**コンピューターの管理**] をダブルクリックして、[ディスクの**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-136">In **Control Panel** on the host computer that is running Windows 7, click **Administrative Tools**, double-click **Computer Management**, then click **Disk Management**.</span></span>

2.  <span data-ttu-id="01686-137">ディスク管理コンソールを使用して、仮想ハードディスクを接続 (マウント) し、ディスクを最適化します。</span><span class="sxs-lookup"><span data-stu-id="01686-137">By using the Disk Management Console, attach (mount) the virtual hard disk and then defragment the disk.</span></span>

3.  <span data-ttu-id="01686-138">ISO 抽出ツールを使用して、\\ プログラムファイル \\ Windows 仮想デバイス \\ 統合コンポーネントフォルダーにある precompact .iso を抽出します。</span><span class="sxs-lookup"><span data-stu-id="01686-138">By using an ISO extraction tool, extract the precompact.iso located in the \\Program Files\\Windows Virtual PC\\Integration Components folder.</span></span>

4.  <span data-ttu-id="01686-139">precompact.exe プログラムを使用して、Windows XP の仮想ハードディスクを圧縮します。</span><span class="sxs-lookup"><span data-stu-id="01686-139">Use the precompact.exe program to compress the Windows XP virtual hard disk.</span></span>

5.  <span data-ttu-id="01686-140">ディスク管理コンソールを使用して、仮想ハードディスクをデタッチします。</span><span class="sxs-lookup"><span data-stu-id="01686-140">By using the Disk Management Console, detach the virtual hard disk.</span></span>

**<span data-ttu-id="01686-141">仮想ハードディスクの最適化</span><span class="sxs-lookup"><span data-stu-id="01686-141">Compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="01686-142">Windows 仮想 PC を開きます。</span><span class="sxs-lookup"><span data-stu-id="01686-142">Open Windows Virtual PC.</span></span>

    <span data-ttu-id="01686-143">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 Pc**]、[ **windows 仮想 pc**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-143">Click **Start**, click **All Programs**, click **Windows Virtual PC**, then click **Windows Virtual PC**.</span></span>

2.  <span data-ttu-id="01686-144">Windows XP の画像を右クリックして、[**設定**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="01686-144">Right-click your Windows XP image and select **Settings**.</span></span>

3.  <span data-ttu-id="01686-145">Windows XP のイメージに対応する [**ハードディスク**] をクリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-145">Click **Hard Disk** for the one that corresponds to your Windows XP image, and then click **Modify**.</span></span>

4.  <span data-ttu-id="01686-146">[**コンパクト仮想ハードディスク**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-146">Click **Compact virtual hard disk**.</span></span>

5.  <span data-ttu-id="01686-147">[**圧縮**] をクリックし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="01686-147">Click **Compact** and then click **OK**.</span></span>

<span data-ttu-id="01686-148">最適化した仮想ハードディスクのバックアップコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="01686-148">Create a backup copy of your compacted virtual hard disk.</span></span>

## <span data-ttu-id="01686-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="01686-149">Related topics</span></span>


[<span data-ttu-id="01686-150">MED-V の Windows 仮想 PC イメージの構成</span><span class="sxs-lookup"><span data-stu-id="01686-150">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="01686-151">MED-V テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="01686-151">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





