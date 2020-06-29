---
title: MED-V 2.0 のベスト プラクティス
description: MED-V 2.0 のベスト プラクティス
author: dansimp
ms.assetid: 47ba2dd1-6c6e-4d6e-8e18-b42291f8e02a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7b664d33b403b821ce6bc9c045d937380ab4f91b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826114"
---
# <span data-ttu-id="557d0-103">MED-V 2.0 のベスト プラクティス</span><span class="sxs-lookup"><span data-stu-id="557d0-103">MED-V 2.0 Best Practices</span></span>


<span data-ttu-id="557d0-104">企業の MED-V の計画、展開、管理を行う際には、ベストプラクティスの推奨事項が役に立つ場合があります。</span><span class="sxs-lookup"><span data-stu-id="557d0-104">When you are planning, deploying, and managing MED-V in your enterprise, you may find the best practice recommendations to be useful.</span></span>

### <span data-ttu-id="557d0-105">初めて実行するときの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-105">Configure first time setup to run unattended</span></span>

<span data-ttu-id="557d0-106">任意の設定を指定することもできますが、MED-V のベストプラクティスは、初回のセットアップを**無人**モードで実行できるように sysprep.inf ファイルを作成することです。</span><span class="sxs-lookup"><span data-stu-id="557d0-106">Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode.</span></span> <span data-ttu-id="557d0-107">そのためには、**セットアップマネージャー**ウィザードを続行するときに必要なすべての設定情報を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="557d0-107">This requires you to provide all the required settings information as you continue through the **Setup Manager** wizard.</span></span> <span data-ttu-id="557d0-108">MED-V イメージの構成方法の詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成](configuring-a-windows-virtual-pc-image-for-med-v.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557d0-108">For more information about how to configure the MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="557d0-109">仮想マシンで復元ポイントを無効にする</span><span class="sxs-lookup"><span data-stu-id="557d0-109">Disable restore points on the virtual machine</span></span>

<span data-ttu-id="557d0-110">MED-V ワークスペースパッケージを作成する前に、仮想マシン上の復元ポイントを無効にして差分ディスクの拡張を禁止することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-110">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="557d0-111">詳細については、「 [WINDOWS XP でシステムの復元を有効または無効にする方法](https://go.microsoft.com/fwlink/?LinkId=195927)」を参照してください ( https://go.microsoft.com/fwlink/?LinkId=195927) .</span><span class="sxs-lookup"><span data-stu-id="557d0-111">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

### <span data-ttu-id="557d0-112">ローカルプロファイルを使用するように MED-V イメージを構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-112">Configure MED-V image to use local profiles</span></span>

<span data-ttu-id="557d0-113">Windows XP のアプリケーション互換性環境で適切なポリシーのみを適用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-113">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="557d0-114">たとえば、デスクトップのカスタマイズポリシーは通常、適用する必要がないため、無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="557d0-114">For example, desktop customization policies do not typically have to be applied and should be disabled.</span></span> <span data-ttu-id="557d0-115">ローカルプロファイルのみを許可する方法について詳しくは、「[ローミングユーザープロファイルのグループポリシー設定](https://go.microsoft.com/fwlink/?LinkId=205072)」をご覧ください https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="557d0-115">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

### <span data-ttu-id="557d0-116">グループポリシーのパフォーマンス更新プログラムを構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-116">Configure a Group Policy performance update</span></span>

<span data-ttu-id="557d0-117">既定では、グループポリシーは一度に1バイトのコンピューターにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="557d0-117">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="557d0-118">これにより、MED-V がドメインに参加しているときに遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="557d0-118">This causes delays when MED-V is being joined to the domain.</span></span> <span data-ttu-id="557d0-119">グループポリシーのパフォーマンスを向上させるには、次のレジストリキー値をレジストリに設定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-119">To increase the performance of Group Policy, we recommend that you set the following registry key value to the registry:</span></span>

<span data-ttu-id="557d0-120">レジストリサブキー: HKEY \ _LOCAL \ _MACHINE ¥ (Windows nt¥)</span><span class="sxs-lookup"><span data-stu-id="557d0-120">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="557d0-121">エントリ: バッファーポリシーの読み取り</span><span class="sxs-lookup"><span data-stu-id="557d0-121">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="557d0-122">型: DWORD</span><span class="sxs-lookup"><span data-stu-id="557d0-122">Type: DWORD</span></span>

<span data-ttu-id="557d0-123">値: 1</span><span class="sxs-lookup"><span data-stu-id="557d0-123">Value: 1</span></span>

### <span data-ttu-id="557d0-124">MED-V イメージではなく、グループポリシーを使用して法的な通知を配布する</span><span class="sxs-lookup"><span data-stu-id="557d0-124">Distribute legal notice through Group Policy instead of in the MED-V image</span></span>

<span data-ttu-id="557d0-125">エンドユーザーが MED-V にアクセスする前にサービスレベルアグリーメント (SLA) を表示する必要がある場合は、後でグループポリシーを使用して SLA を適用することをお勧めします。これにより、セットアップが完了した後でエンドユーザーに SLA が表示されるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-125">If you want end users to see a service level agreement (SLA) before they access MED-V, we recommend that you enforce the SLA through Group Policy later so that the SLA is displayed to the end user after the first time setup is finished.</span></span>

<span data-ttu-id="557d0-126">**注意** **無人**モードで初めてセットアップを実行することをお勧めしますが、ローカルポリシーまたはレジストリエントリに、イメージ (仮想ハードディスク) の SLA を含めるように設定する場合は、最初にセットアップを**有人**モードで実行することを指定する必要があります。または、最初にセットアップを失敗させることもできます。</span><span class="sxs-lookup"><span data-stu-id="557d0-126">**Caution** Even though a best practice is to run first time setup in **Unattended** mode, if you decide to set the local policy or registry entry to include an SLA in your image (virtual hard disk), you must also specify that first time setup is run in **Attended** mode, or first time setup can fail.</span></span>

 

### <span data-ttu-id="557d0-127">仮想ハードディスクを圧縮する</span><span class="sxs-lookup"><span data-stu-id="557d0-127">Compact the virtual hard disk</span></span>

<span data-ttu-id="557d0-128">仮想ハードディスクを最適化して空のディスク領域を再利用し、仮想ハードディスクのサイズを小さくすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-128">We recommend that you compact your virtual hard disk to reclaim empty disk space and reduce the size of the virtual hard disk.</span></span> <span data-ttu-id="557d0-129">仮想ハードディスクのコンパクト化の詳細については、「 [Med-v 仮想ハードディスクの最適化](compacting-the-med-v-virtual-hard-disk.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557d0-129">For more information about how to compact your virtual hard disk, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

### <span data-ttu-id="557d0-130">ブルースクリーンがクラッシュしたときに再起動するように仮想マシンを構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-130">Configure virtual machine to restart on blue screen crash</span></span>

<span data-ttu-id="557d0-131">ブルースクリーンワークスペース仮想マシンを構成して、ブルースクリーンのクラッシュが発生したときに自動的に再起動されるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-131">We recommend that you configure the MED-V workspace virtual machine to automatically restart when it encounters a blue screen crash.</span></span> <span data-ttu-id="557d0-132">ゲストでこの設定を構成するには、HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\CrashControl キーの AutoReboot 値を "1" に設定します。</span><span class="sxs-lookup"><span data-stu-id="557d0-132">To configure this setting in the guest, set the AutoReboot value in the HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\CrashControl key to “1”.</span></span>

<span data-ttu-id="557d0-133">[**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**システム**] をクリックして、この設定を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="557d0-133">You can also configure this setting by clicking **Start**, clicking **Control Panel**, and then clicking **System**.</span></span> <span data-ttu-id="557d0-134">次に、[**詳細**設定] タブの [**起動と回復**] 領域で、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="557d0-134">Then, in the **Startup and Recovery** area of the **Advanced** tab, click **Settings**.</span></span> <span data-ttu-id="557d0-135">[**自動的に再起動**する] チェックボックスをオンにし、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="557d0-135">Select the **Automatically restart** check box and click **OK**.</span></span>

### <span data-ttu-id="557d0-136">封印する前に、MED-V イメージをバックアップする</span><span class="sxs-lookup"><span data-stu-id="557d0-136">Back up MED-V image before sealing it</span></span>

<span data-ttu-id="557d0-137">封印する前に、MED-V イメージのバックアップコピーを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-137">We recommend that you create a backup copy of the MED-V image before you seal it.</span></span> <span data-ttu-id="557d0-138">MED-V イメージの封印の詳細については、「 [med-v 用に Windows 仮想 PC イメージを構成する](configuring-a-windows-virtual-pc-image-for-med-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557d0-138">For more information about sealing your MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="557d0-139">バッチファイルからインストールする場合は、Windows Virtual PC を最後にインストールする</span><span class="sxs-lookup"><span data-stu-id="557d0-139">Install Windows Virtual PC last when installing from a batch file</span></span>

<span data-ttu-id="557d0-140">バッチファイルを使用して MED-V コンポーネントをインストールする場合は、MED-V ホストエージェントと MED-V ワークスペースパッケージファイルの後に、Windows 仮想 PC と Windows 仮想 PC ホットフィックスをインストールすることを指定します。</span><span class="sxs-lookup"><span data-stu-id="557d0-140">When you install the MED-V components by using a batch file, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="557d0-141">これにより、Windows の更新プログラムでは、再起動を要求することによってインストールプロセスに干渉することがなくなります。</span><span class="sxs-lookup"><span data-stu-id="557d0-141">This ensures that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

### <span data-ttu-id="557d0-142">ローカルフォルダーから MED-V ワークスペースをインストールする</span><span class="sxs-lookup"><span data-stu-id="557d0-142">Install MED-V workspace from local folder</span></span>

<span data-ttu-id="557d0-143">ネットワーク上の場所から MED-V をインストールするときに発生する問題のため、MED-V ワークスペースのセットアップファイルをローカルにコピーして、setup.exe を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-143">Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>

### <a href="" id="manage-printer-redirection-in-one-manner-only-"></a><span data-ttu-id="557d0-144">1つの方法でのみプリンターのリダイレクションを管理する</span><span class="sxs-lookup"><span data-stu-id="557d0-144">Manage printer redirection in one manner only</span></span>

<span data-ttu-id="557d0-145">プリンターが手動で MED-V ゲスト仮想マシンにインストールされている場合に、同じプリンターがホストコンピューターにインストールされていると、その結果、ゲストに2回インストールされます。</span><span class="sxs-lookup"><span data-stu-id="557d0-145">If a printer is manually installed on the MED-V guest virtual machine, and the same printer is later installed on the host computer, the result is that it is installed two times in the guest.</span></span> <span data-ttu-id="557d0-146">このような状況を回避するために、プリンターのリダイレクションは1つの方法で管理することをお勧めします。リダイレクトを無効にして、ゲスト上のプリンターを手動でインストールするか、またはリダイレクトを有効にして、ゲストにプリンターを手動でインストールしないようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-146">To avoid this situation, we recommend as MED-V best practice that you manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

### <a href="" id="configure-settings-for-med-v-guest-patching-"></a><span data-ttu-id="557d0-147">MED ゲストパッチの設定を構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-147">Configure settings for MED-V guest patching</span></span>

<span data-ttu-id="557d0-148">が起動仮想マシンで自動更新を受信するタイミングと時間を制御するには、レジストリで関連する構成値を定義します。</span><span class="sxs-lookup"><span data-stu-id="557d0-148">You can control when and for how long the MED-V virtual machine awakens to receive automatic updates by defining the relevant configuration values in the registry.</span></span> <span data-ttu-id="557d0-149">MED-V のベストプラクティスは、MED-V 仮想マシンの定期的な更新プログラムがスケジュールされている時刻と一致するように、ウェイクアップ間隔を設定することです。</span><span class="sxs-lookup"><span data-stu-id="557d0-149">A MED-V best practice is to set your wake-up interval to match the time when you have scheduled regular updates for MED-V virtual machines.</span></span> <span data-ttu-id="557d0-150">また、これらの設定は、ホストコンピューターの動作に似た構成にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-150">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

<span data-ttu-id="557d0-151">MED-V のゲストパッチの設定を構成する方法の詳細については、「 [Med-v ワークスペースの自動更新を管理](managing-automatic-updates-for-med-v-workspaces.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="557d0-151">For more information about how to configure settings for MED-V guest patching, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

### <span data-ttu-id="557d0-152">ウイルス対策/バックアップソフトウェアを構成する</span><span class="sxs-lookup"><span data-stu-id="557d0-152">Configure antivirus/backup software</span></span>

<span data-ttu-id="557d0-153">ウイルス対策によって仮想デスクトップのパフォーマンスが影響を受けないようにするには、次のような仮想マシンのファイルの種類を、MED-V ホストコンピューターで実行されているすべてのウイルス対策またはバックアッププロセスから除外することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="557d0-153">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend that when you can, you exclude the following virtual machine file types from any antivirus or backup process that is running on the MED-V host computer:</span></span>

-   <span data-ttu-id="557d0-154">\*..VMC</span><span class="sxs-lookup"><span data-stu-id="557d0-154">\*.VMC</span></span>

-   <span data-ttu-id="557d0-155">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="557d0-155">\*.VUD</span></span>

-   <span data-ttu-id="557d0-156">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="557d0-156">\*.VSV</span></span>

-   <span data-ttu-id="557d0-157">\*.VHD</span><span class="sxs-lookup"><span data-stu-id="557d0-157">\*.VHD</span></span>

## <span data-ttu-id="557d0-158">関連トピック</span><span class="sxs-lookup"><span data-stu-id="557d0-158">Related topics</span></span>


[<span data-ttu-id="557d0-159">MED-V のセキュリティと保護</span><span class="sxs-lookup"><span data-stu-id="557d0-159">Security and Protection for MED-V</span></span>](security-and-protection-for-med-v.md)

 

 





