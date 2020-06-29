---
title: DaRT 7.0 のツールの概要
description: DaRT 7.0 のツールの概要
author: dansimp
ms.assetid: 67c5991e-cbe6-4ce9-9fe5-f1761369d1fe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d327e14fd1851f0e0d82e1c3ad692bcf7842a835
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823444"
---
# <span data-ttu-id="3b85b-103">DaRT 7.0 のツールの概要</span><span class="sxs-lookup"><span data-stu-id="3b85b-103">Overview of the Tools in DaRT 7.0</span></span>


<span data-ttu-id="3b85b-104">Microsoft 診断/回復ツールセット (DaRT) 7 の [**診断/回復ツールセット**] ウィンドウから、dart 回復イメージの作成時に含まれていた個々のツールを開始できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT)7, you can start any of the individual tools that were included when the DaRT recovery image was created.</span></span> <span data-ttu-id="3b85b-105">**診断/回復ツールセット**ウィンドウにアクセスする方法については、「 [DaRT 回復イメージを使用してローカルコンピューターを回復する方法](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b85b-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers Using the DaRT Recovery Image](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="3b85b-106">利用できる場合は、[**診断/回復ツールセット**] ウィンドウで**ソリューションウィザード**を使用して、簡単なインタビューに基づいて、特定の問題に最も適したツールを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview.</span></span>

## <span data-ttu-id="3b85b-107">DaRT ツールのご紹介</span><span class="sxs-lookup"><span data-stu-id="3b85b-107">Exploring the DaRT Tools</span></span>


<span data-ttu-id="3b85b-108">このセクションでは、DaRT の一部であるさまざまなツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-108">This section describes the various tools that are part of DaRT.</span></span>

### <span data-ttu-id="3b85b-109">レジストリ エディター</span><span class="sxs-lookup"><span data-stu-id="3b85b-109">Registry Editor</span></span>

<span data-ttu-id="3b85b-110">**レジストリエディター**を使って、分析または修復している Windows オペレーティングシステムのレジストリにアクセスして変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-110">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="3b85b-111">これには、キーと値の追加、削除、編集、レジストリ (.reg) ファイルのインポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-111">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="3b85b-112">**注意** このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-112">**Caution** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="3b85b-113">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-113">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="3b85b-114">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-114">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="3b85b-115">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="3b85b-115">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="3b85b-116">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="3b85b-116">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="3b85b-117">Locksmith</span><span class="sxs-lookup"><span data-stu-id="3b85b-117">Locksmith</span></span>

<span data-ttu-id="3b85b-118">**Locksmith ウィザード**を使用すると、分析または修復する Windows オペレーティングシステムのローカルアカウントのパスワードを設定または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-118">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="3b85b-119">現在のパスワードを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3b85b-119">You do not have to know the current password.</span></span> <span data-ttu-id="3b85b-120">ただし、設定したパスワードは、ローカルグループポリシーオブジェクトで定義されている要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-120">However, the password that you set must comply with any requirements that are defined by a local Group Policy object.</span></span> <span data-ttu-id="3b85b-121">これには、パスワードの長さと複雑さが含まれます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-121">This includes password length and complexity.</span></span>

<span data-ttu-id="3b85b-122">**Locksmith**は、ローカル管理者アカウントなどのローカルアカウントのパスワードが不明な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-122">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="3b85b-123">**Locksmith**を使用して、ドメインアカウントのパスワードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b85b-123">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="3b85b-124">クラッシュアナライザー</span><span class="sxs-lookup"><span data-stu-id="3b85b-124">Crash Analyzer</span></span>

<span data-ttu-id="3b85b-125">**Crash Analyzer ウィザード**を使用すると、修復している Windows オペレーティングシステムのメモリダンプファイルを分析して、コンピューターのクラッシュの原因をすばやく判断できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-125">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer crash by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="3b85b-126">**クラッシュ**ダンプは、コンピューターに障害が発生した可能性のあるドライバーのクラッシュダンプファイルを調査します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-126">**Crash Analyzer** examines the crash dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="3b85b-127">次に、**コンピューターの管理**ツールの [**サービスとドライバー** ] ノードを使用して、問題のあるデバイスドライバーを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-127">Then, you can disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="3b85b-128">**クラッシュ解析ウィザード**を使用するには、修復するオペレーティングシステム用の Windows 用デバッグツールとシンボルファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="3b85b-128">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="3b85b-129">DaRT リカバリ画像を作成する際には、両方の要件を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-129">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="3b85b-130">回復イメージに含まれておらず、修復しているコンピューターでそれらのファイルにアクセスできない場合は、メモリダンプファイルを別のコンピューターにコピーし、スタンドアロンバージョンの**Crash Analyzer**を使って問題を診断することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-130">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="3b85b-131">コンピュータのイメージを再作成することを計画している場合でも、**クラッシュ解析ツール**を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b85b-131">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="3b85b-132">イメージに問題のあるドライバーが含まれている可能性があります。これにより、環境内で問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-132">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="3b85b-133">**Crash Analyzer**を実行すると、問題のドライバーを特定し、イメージの安定性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-133">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="3b85b-134">**クラッシュアナライザー**の詳細については、「[クラッシュアナライザーによるシステム障害の診断](diagnosing-system-failures-with-crash-analyzer--dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3b85b-134">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md).</span></span>

### <span data-ttu-id="3b85b-135">ファイルの復元</span><span class="sxs-lookup"><span data-stu-id="3b85b-135">File Restore</span></span>

<span data-ttu-id="3b85b-136">**ファイルの復元**で、誤って削除された、または大きすぎてごみ箱に収まらないファイルを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-136">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="3b85b-137">**ファイルの復元**は、通常のディスクボリュームに限定されるわけではありませんが、紛失したボリュームまたは BitLocker で暗号化されたボリュームでファイルを検索して復元することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-137">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

### <span data-ttu-id="3b85b-138">ディスクコマンダー</span><span class="sxs-lookup"><span data-stu-id="3b85b-138">Disk Commander</span></span>

<span data-ttu-id="3b85b-139">**Disk コマンダー**では、次のいずれかの回復プロセスを使用して、ディスクパーティションまたはボリュームの回復と修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-139">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="3b85b-140">マスターブートレコード (MBR) を復元する</span><span class="sxs-lookup"><span data-stu-id="3b85b-140">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="3b85b-141">消失した1つ以上のボリュームを回復する</span><span class="sxs-lookup"><span data-stu-id="3b85b-141">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="3b85b-142">**Disk コマンダー** backup からパーティションテーブルを復元します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-142">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="3b85b-143">**ディスクコマンダー**バックアップにパーティションテーブルを保存する</span><span class="sxs-lookup"><span data-stu-id="3b85b-143">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="3b85b-144">**警告** ディスク**コマンダー**を使用して修復する前に、ディスクのバックアップを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b85b-144">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="3b85b-145">**ディスクコマンダー**を使用すると、ボリュームが破損し、アクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-145">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="3b85b-146">さらに、1つのボリュームに対する変更は、ディスク上のボリュームがパーティションテーブルを共有するため、他のボリュームに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-146">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

### <span data-ttu-id="3b85b-147">ディスクワイプ</span><span class="sxs-lookup"><span data-stu-id="3b85b-147">Disk Wipe</span></span>

<span data-ttu-id="3b85b-148">ディスク**ワイプ**を使用すると、ハードディスクドライブの書式を変更した後で、ディスクまたはボリュームからすべてのデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-148">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="3b85b-149">**ディスクワイプ**では、単一パス上書きと、現在の米国国防総省によって満たされた4パス上書きのいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-149">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="3b85b-150">**警告** ディスクまたはボリュームを消去した後は、データを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b85b-150">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="3b85b-151">消去する前に、ボリュームのサイズとラベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-151">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="3b85b-152">コンピューターの管理</span><span class="sxs-lookup"><span data-stu-id="3b85b-152">Computer Management</span></span>

<span data-ttu-id="3b85b-153">**コンピューターの管理**は、問題のあるコンピューターのトラブルシューティングに役立つ Windows 管理ツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="3b85b-153">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="3b85b-154">DaRT の**コンピューター管理**ツールを使用して、システム情報とイベントログの表示、ディスクの管理、autoruns の一覧表示、サービスとドライバーの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-154">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="3b85b-155">**コンピューターの管理**コンソールは、Windows オペレーティングシステムの起動を妨げている可能性がある問題の診断と修復を行うためにカスタマイズされています。</span><span class="sxs-lookup"><span data-stu-id="3b85b-155">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

### <span data-ttu-id="3b85b-156">エクス</span><span class="sxs-lookup"><span data-stu-id="3b85b-156">Explorer</span></span>

<span data-ttu-id="3b85b-157">**エクスプローラー**ツールを使用すると、コンピューターのファイルシステムとネットワーク共有を参照して、ユーザーがローカルドライブに保存した重要なデータを削除してから、コンピューターを修復または再イメージすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-157">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="3b85b-158">また、ドライブ文字をネットワーク共有に対応付けることができるため、コンピューターからネットワークにファイルをコピーして、安全に保存したり、ネットワークからコンピューターに移動して復元したりすることが簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-158">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="3b85b-159">ソリューションウィザード</span><span class="sxs-lookup"><span data-stu-id="3b85b-159">Solution Wizard</span></span>

<span data-ttu-id="3b85b-160">**ソリューションウィザード**では一連の質問が表示され、お客様の回答に基づいて、状況に最適なツールが提案されます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-160">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="3b85b-161">このウィザードは、DaRT のツールに慣れていないときに使用するツールを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-161">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="3b85b-162">TCP/IP 構成</span><span class="sxs-lookup"><span data-stu-id="3b85b-162">TCP/IP Config</span></span>

<span data-ttu-id="3b85b-163">問題のあるコンピューターを DaRT に起動すると、動的ホスト構成プロトコル (DHCP) から TCP/IP 構成 (IP アドレスと DNS サーバー) が自動的に取得されるように設定されます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-163">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="3b85b-164">DHCP を使用できない場合は、 **tcp/ip**構成ツールを使って手動で tcp/ip を構成できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-164">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="3b85b-165">まずネットワークアダプターを選んでから、そのアダプターの IP アドレスと DNS サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-165">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

### <span data-ttu-id="3b85b-166">修正プログラムのアンインストール</span><span class="sxs-lookup"><span data-stu-id="3b85b-166">Hotfix Uninstall</span></span>

<span data-ttu-id="3b85b-167">**ホットフィックスアンインストールウィザード**を使用すると、修復しているコンピューターの Windows オペレーティングシステムから修正プログラムまたはサービスパックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-167">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="3b85b-168">このツールは、修正プログラムまたはサービスパックがオペレーティングシステムの起動を妨げている可能性がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="3b85b-168">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="3b85b-169">ツールによって複数のホットフィックスをアンインストールすることはできますが、アンインストールは一度に1つだけ行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3b85b-169">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="3b85b-170">**重要** 修正プログラムをインストールした後にインストールまたは更新したプログラムは、修正プログラムをアンインストールした後に正常に動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-170">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="3b85b-171">SFC スキャン</span><span class="sxs-lookup"><span data-stu-id="3b85b-171">SFC Scan</span></span>

<span data-ttu-id="3b85b-172">**SFC スキャン**ツールは、**システムファイルの修復ウィザード**を開始し、インストールされている Windows オペレーティングシステムの起動を妨げているシステムファイルを修復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3b85b-172">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="3b85b-173">**システムファイルの修復ウィザード**を使用すると、破損または紛失しているシステムファイルを自動的に修復したり、修復を実行する前に確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-173">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="3b85b-174">検索</span><span class="sxs-lookup"><span data-stu-id="3b85b-174">Search</span></span>

<span data-ttu-id="3b85b-175">コンピューターを再作成する前に、ローカルのハードディスクからファイルを回復することが重要です。特に、ユーザーがファイルをバックアップしていないか、他の場所に保存していない場合です。</span><span class="sxs-lookup"><span data-stu-id="3b85b-175">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="3b85b-176">[**検索**] ツールを使うと、ファイル**検索**ウィンドウが開き、ファイルのパスがわからない場合や、すべてのローカルハードディスクで一般的な種類のファイルを検索する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-176">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="3b85b-177">特定のパスで特定のファイル名パターンを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-177">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="3b85b-178">また、結果を日付の範囲またはサイズの範囲に制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-178">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="3b85b-179">スタンドアロンシステム Sweeper</span><span class="sxs-lookup"><span data-stu-id="3b85b-179">Standalone System Sweeper</span></span>

<span data-ttu-id="3b85b-180">**重要** スタンドアロンのシステム Sweeper が展開されている環境では、代わりにマルウェア検出用に Microsoft Defender オフライン (WDO) 保護イメージを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-180">**Important** Environments with the Standalone System Sweeper deployed should instead use the Microsoft Defender Offline (WDO) protection image for malware detection.</span></span> <span data-ttu-id="3b85b-181">スタンドアロンシステム Sweeper ツールは DaRT に統合されているため、サポートされているすべての DaRT バージョンの展開では、これらのマルウェア対策の更新を DaRT 画像に適用することはできません。</span><span class="sxs-lookup"><span data-stu-id="3b85b-181">Because of how the Standalone System Sweeper tool integrates into DaRT, all supported DaRT version deployments cannot apply these anti-malware updates to their DaRT images.</span></span>

 

<span data-ttu-id="3b85b-182">**スタンドアロンのシステム Sweeper**は、マルウェアや不要なソフトウェアを検出し、セキュリティのリスクについて警告するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-182">The **Standalone System Sweeper** can help detect malware and unwanted software and warn you of security risks.</span></span> <span data-ttu-id="3b85b-183">このツールを使用すると、インストールされている Windows オペレーティングシステムが実行されていない場合でも、コンピューターをスキャンし、マルウェアを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-183">You can use this tool to scan a computer for and remove malware even when the installed Windows operating system is not running.</span></span> <span data-ttu-id="3b85b-184">**スタンドアロンシステム Sweeper**が悪意のあるソフトウェアまたは望ましくないソフトウェアを検出すると、各アイテムの削除、検疫、または許可を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-184">When the **Standalone System Sweeper** detects malicious or unwanted software, it prompts you to remove, quarantine, or allow for each item.</span></span>

<span data-ttu-id="3b85b-185">ルートキットを使うマルウェアは、実行中のオペレーティングシステムから直接マスクすることができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-185">Malware that uses rootkits can mask itself from the running operating system.</span></span> <span data-ttu-id="3b85b-186">Rootkit 対応のウイルスまたはスパイウェアがコンピューターに含まれている場合、ほとんどのリアルタイムのスキャンおよび削除ツールでは、それを表示したり、削除したりすることはできなくなります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-186">If a rootkit-enabled virus or spyware is in a computer, most real-time scanning and removal tools can no longer see it or remove it.</span></span> <span data-ttu-id="3b85b-187">問題のあるコンピューターを DaRT に起動し、インストールされているオペレーティングシステムがオフラインになっているため、rootkit を検出することなく、rootkit を検出することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-187">Because you boot the problem computer into DaRT and the installed operating system is offline, you can detect the rootkit without it being able to mask itself.</span></span>

### <span data-ttu-id="3b85b-188">リモート接続</span><span class="sxs-lookup"><span data-stu-id="3b85b-188">Remote Connection</span></span>

<span data-ttu-id="3b85b-189">DaRT の**リモート接続**ツールを使用すると、エンドユーザのコンピュータで DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-189">The **Remote Connection** tool in DaRT lets you remotely run the DaRT tools on an end-user computer.</span></span> <span data-ttu-id="3b85b-190">エンドユーザー (またはエンドユーザーのコンピューターで作業中のヘルプデスクプロフェッショナル) によって特定の情報が提供されると、IT 管理者は、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3b85b-190">After certain specific information is provided by the end user (or by a helpdesk professional working on the end-user computer), the IT administrator can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="3b85b-191">**重要** リモート接続を確立する2台のコンピューターは、同じネットワークの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3b85b-191">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

## <span data-ttu-id="3b85b-192">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3b85b-192">Related topics</span></span>


[<span data-ttu-id="3b85b-193">DaRT 7.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="3b85b-193">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)

 

 





