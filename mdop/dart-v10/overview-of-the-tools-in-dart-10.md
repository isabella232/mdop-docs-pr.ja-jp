---
title: DaRT 10 のツールの概要
description: DaRT 10 のツールの概要
author: dansimp
ms.assetid: 752467dd-b646-4335-82ce-9090d4651f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8bef2b92e998bebffae526d4288c76be081fe0a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822994"
---
# <span data-ttu-id="277ad-103">DaRT 10 のツールの概要</span><span class="sxs-lookup"><span data-stu-id="277ad-103">Overview of the Tools in DaRT 10</span></span>


<span data-ttu-id="277ad-104">Microsoft 診断/回復ツールセット (DaRT) 10 の [**診断/回復ツールセット**] ウィンドウから、dart 10 の回復イメージを作成するときに含める個々のツールを開始できます。</span><span class="sxs-lookup"><span data-stu-id="277ad-104">From the **Diagnostics and Recovery Toolset** window in Microsoft Diagnostics and Recovery Toolset (DaRT) 10, you can start any of the individual tools that you include when you create the DaRT 10 recovery image.</span></span> <span data-ttu-id="277ad-105">**診断/回復ツールセット**ウィンドウにアクセスする方法については、「 [DaRT 回復イメージを使用してローカルコンピューターを回復する方法](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="277ad-105">For information about how to access the **Diagnostics and Recovery Toolset** window, see [How to Recover Local Computers by Using the DaRT Recovery Image](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-10.md).</span></span>

<span data-ttu-id="277ad-106">利用可能な場合は、[**診断と回復] のツールセット**ウィンドウで**ソリューションウィザード**を使って、特定の問題に最も適したツールを選択できます。このツールは、ウィザードで提供される簡単なインタビューに基づきます。</span><span class="sxs-lookup"><span data-stu-id="277ad-106">If it is available, you can use the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to select the tool that best addresses your particular issue, based on a brief interview that the wizard provides.</span></span>

## <span data-ttu-id="277ad-107">DaRT ツールのご紹介</span><span class="sxs-lookup"><span data-stu-id="277ad-107">Exploring the DaRT tools</span></span>


<span data-ttu-id="277ad-108">DaRT 10 のツールについて、以下に説明します。</span><span class="sxs-lookup"><span data-stu-id="277ad-108">A description of the DaRT 10 tools follows.</span></span>

### <span data-ttu-id="277ad-109">コンピューターの管理</span><span class="sxs-lookup"><span data-stu-id="277ad-109">Computer Management</span></span>

<span data-ttu-id="277ad-110">**コンピューターの管理**は、問題のあるコンピューターのトラブルシューティングに役立つ Windows 管理ツールのコレクションです。</span><span class="sxs-lookup"><span data-stu-id="277ad-110">**Computer Management** is a collection of Windows administrative tools that help you troubleshoot a problem computer.</span></span> <span data-ttu-id="277ad-111">DaRT の**コンピューター管理**ツールを使用して、システム情報とイベントログの表示、ディスクの管理、autoruns の一覧表示、サービスとドライバーの管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-111">You can use the **Computer Management** tools in DaRT to view system information and event logs, manage disks, list autoruns, and manage services and drivers.</span></span> <span data-ttu-id="277ad-112">**コンピューターの管理**コンソールは、Windows オペレーティングシステムの起動を妨げている可能性がある問題の診断と修復を行うためにカスタマイズされています。</span><span class="sxs-lookup"><span data-stu-id="277ad-112">The **Computer Management** console is customized to help you diagnose and repair problems that might be preventing the Windows operating system from starting.</span></span>

<span data-ttu-id="277ad-113">**注** DaRT によるダイナミックディスクの回復はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="277ad-113">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="277ad-114">クラッシュアナライザー</span><span class="sxs-lookup"><span data-stu-id="277ad-114">Crash Analyzer</span></span>

<span data-ttu-id="277ad-115">**クラッシュ解析ツールウィザード**を使って、修復している Windows オペレーティングシステムのメモリダンプファイルを分析することで、コンピューターの障害の原因をすばやく特定します。</span><span class="sxs-lookup"><span data-stu-id="277ad-115">Use the **Crash Analyzer Wizard** to quickly determine the cause of a computer failure by analyzing the memory dump file on the Windows operating system that you are repairing.</span></span> <span data-ttu-id="277ad-116">**クラッシュアナライザー**は、コンピューターに障害が発生した可能性のあるドライバーのメモリダンプファイルを検査します。</span><span class="sxs-lookup"><span data-stu-id="277ad-116">**Crash Analyzer** examines the memory dump file for the driver that caused a computer to fail.</span></span> <span data-ttu-id="277ad-117">次に、**コンピューターの管理**ツールの [**サービスとドライバー** ] ノードを使用して、問題のあるデバイスドライバーを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-117">You can then disable the problem device driver by using the **Services and Drivers** node in the **Computer Management** tool.</span></span>

<span data-ttu-id="277ad-118">**クラッシュ解析ウィザード**を使用するには、修復するオペレーティングシステム用の Windows 用デバッグツールとシンボルファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="277ad-118">The **Crash Analyzer Wizard** requires the Debugging Tools for Windows and symbol files for the operating system that you are repairing.</span></span> <span data-ttu-id="277ad-119">DaRT リカバリ画像を作成する際には、両方の要件を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-119">You can include both requirements when you create the DaRT recovery image.</span></span> <span data-ttu-id="277ad-120">回復イメージに含まれておらず、修復しているコンピューターでそれらのファイルにアクセスできない場合は、メモリダンプファイルを別のコンピューターにコピーし、スタンドアロンバージョンの**Crash Analyzer**を使って問題を診断することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-120">If they are not included on the recovery image and you do not have access to them on the computer that you are repairing, you can copy the memory dump file to another computer and use the stand-alone version of **Crash Analyzer** to diagnose the problem.</span></span>

<span data-ttu-id="277ad-121">コンピュータのイメージを再作成することを計画している場合でも、**クラッシュ解析ツール**を実行することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="277ad-121">Running **Crash Analyzer** is a good idea even if you plan to reimage the computer.</span></span> <span data-ttu-id="277ad-122">イメージに問題のあるドライバーが含まれている可能性があります。これにより、環境内で問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="277ad-122">The image could have a defective driver that is causing problems in your environment.</span></span> <span data-ttu-id="277ad-123">**Crash Analyzer**を実行すると、問題のドライバーを特定し、イメージの安定性を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-123">By running **Crash Analyzer**, you can identify problem drivers and improve the image stability.</span></span>

<span data-ttu-id="277ad-124">**クラッシュアナライザー**の詳細については、「[クラッシュアナライザーによるシステム障害の診断](diagnosing-system-failures-with-crash-analyzer-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="277ad-124">For more information about **Crash Analyzer**, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md).</span></span>

### <span data-ttu-id="277ad-125">ディスクコマンダー</span><span class="sxs-lookup"><span data-stu-id="277ad-125">Disk Commander</span></span>

<span data-ttu-id="277ad-126">**Disk コマンダー**では、次のいずれかの回復プロセスを使用して、ディスクパーティションまたはボリュームの回復と修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-126">**Disk Commander** lets you recover and repair disk partitions or volumes by using one of the following recovery processes:</span></span>

-   <span data-ttu-id="277ad-127">マスターブートレコード (MBR) を復元する</span><span class="sxs-lookup"><span data-stu-id="277ad-127">Restore the master boot record (MBR)</span></span>

-   <span data-ttu-id="277ad-128">消失した1つ以上のボリュームを回復する</span><span class="sxs-lookup"><span data-stu-id="277ad-128">Recover one or more lost volumes</span></span>

-   <span data-ttu-id="277ad-129">**Disk コマンダー** backup からパーティションテーブルを復元します。</span><span class="sxs-lookup"><span data-stu-id="277ad-129">Restore partition tables from **Disk Commander** backup</span></span>

-   <span data-ttu-id="277ad-130">**ディスクコマンダー**バックアップにパーティションテーブルを保存する</span><span class="sxs-lookup"><span data-stu-id="277ad-130">Save partition tables to **Disk Commander** backup</span></span>

<span data-ttu-id="277ad-131">**警告** ディスク**コマンダー**を使用して修復する前に、ディスクのバックアップを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="277ad-131">**Warning** We recommend that you back up a disk before you use **Disk Commander** to repair it.</span></span> <span data-ttu-id="277ad-132">**ディスクコマンダー**を使用すると、ボリュームが破損し、アクセスできなくなる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="277ad-132">By using **Disk Commander**, you can potentially damage volumes and make them inaccessible.</span></span> <span data-ttu-id="277ad-133">さらに、1つのボリュームに対する変更は、ディスク上のボリュームがパーティションテーブルを共有するため、他のボリュームに影響を与える可能性があります。</span><span class="sxs-lookup"><span data-stu-id="277ad-133">Additionally, changes to one volume can affect other volumes because volumes on a disk share a partition table.</span></span>

 

<span data-ttu-id="277ad-134">**注** DaRT によるダイナミックディスクの回復はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="277ad-134">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="277ad-135">ディスクワイプ</span><span class="sxs-lookup"><span data-stu-id="277ad-135">Disk Wipe</span></span>

<span data-ttu-id="277ad-136">ディスク**ワイプ**を使用すると、ハードディスクドライブの書式を変更した後で、ディスクまたはボリュームからすべてのデータを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-136">You can use **Disk Wipe** to delete all data from a disk or volume, even the data that is left behind after you reformat a hard disk drive.</span></span> <span data-ttu-id="277ad-137">**ディスクワイプ**では、単一パス上書きと、現在の米国国防総省によって満たされた4パス上書きのいずれかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-137">**Disk Wipe** lets you select from either a single-pass overwrite or a four-pass overwrite, which meets current U.S. Department of Defense standards.</span></span>

<span data-ttu-id="277ad-138">**警告** ディスクまたはボリュームを消去した後は、データを回復することはできません。</span><span class="sxs-lookup"><span data-stu-id="277ad-138">**Warning** After wiping a disk or volume, you cannot recover the data.</span></span> <span data-ttu-id="277ad-139">消去する前に、ボリュームのサイズとラベルを確認します。</span><span class="sxs-lookup"><span data-stu-id="277ad-139">Verify the size and label of a volume before erasing it.</span></span>

 

### <span data-ttu-id="277ad-140">エクス</span><span class="sxs-lookup"><span data-stu-id="277ad-140">Explorer</span></span>

<span data-ttu-id="277ad-141">**エクスプローラー**ツールを使用すると、コンピューターのファイルシステムとネットワーク共有を参照して、ユーザーがローカルドライブに保存した重要なデータを削除してから、コンピューターを修復または再イメージすることができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-141">The **Explorer** tool lets you browse the computer’s file system and network shares so that you can remove important data that the user stored on the local drive before you try to repair or reimage the computer.</span></span> <span data-ttu-id="277ad-142">また、ドライブ文字をネットワーク共有に対応付けることができるため、コンピューターからネットワークにファイルをコピーして、安全に保存したり、ネットワークからコンピューターに移動して復元したりすることが簡単にできます。</span><span class="sxs-lookup"><span data-stu-id="277ad-142">And because you can map drive letters to network shares, you can easily copy and move files from the computer to the network for safekeeping or from the network to the computer to restore them.</span></span>

### <span data-ttu-id="277ad-143">ファイルの復元</span><span class="sxs-lookup"><span data-stu-id="277ad-143">File Restore</span></span>

<span data-ttu-id="277ad-144">**ファイルの復元**で、誤って削除された、または大きすぎてごみ箱に収まらないファイルを復元することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-144">**File Restore** lets you try to restore files that were accidentally deleted or that were too big to fit in the Recycle Bin.</span></span> <span data-ttu-id="277ad-145">**ファイルの復元**は、通常のディスクボリュームに限定されるわけではありませんが、紛失したボリュームまたは BitLocker で暗号化されたボリュームでファイルを検索して復元することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-145">**File Restore** is not limited to regular disk volumes, but can find and restore files on lost volumes or on volumes that are encrypted by BitLocker.</span></span>

<span data-ttu-id="277ad-146">**注** DaRT によるダイナミックディスクの回復はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="277ad-146">**Note** The recovery of dynamic disks with DaRT is not supported.</span></span>

 

### <span data-ttu-id="277ad-147">ファイル検索</span><span class="sxs-lookup"><span data-stu-id="277ad-147">File Search</span></span>

<span data-ttu-id="277ad-148">コンピューターを再作成する前に、ローカルのハードディスクからファイルを回復することが重要です。特に、ユーザーがファイルをバックアップしていないか、他の場所に保存していない場合です。</span><span class="sxs-lookup"><span data-stu-id="277ad-148">Before reimaging a computer, recovering files from the local hard disk is important, especially when the user might not have backed up or stored the files elsewhere.</span></span>

<span data-ttu-id="277ad-149">[**検索**] ツールを使うと、ファイル**検索**ウィンドウが開き、ファイルのパスがわからない場合や、すべてのローカルハードディスクで一般的な種類のファイルを検索する場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="277ad-149">The **Search** tool opens a **File Search** window that you can use to find documents when you do not know the file path or to search for general kinds of files across all local hard disks.</span></span> <span data-ttu-id="277ad-150">特定のパスで特定のファイル名パターンを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-150">You can search for specific file-name patterns in specific paths.</span></span> <span data-ttu-id="277ad-151">また、結果を日付の範囲またはサイズの範囲に制限することもできます。</span><span class="sxs-lookup"><span data-stu-id="277ad-151">You can also limit results to a date range or size range.</span></span>

### <span data-ttu-id="277ad-152">修正プログラムのアンインストール</span><span class="sxs-lookup"><span data-stu-id="277ad-152">Hotfix Uninstall</span></span>

<span data-ttu-id="277ad-153">**ホットフィックスアンインストールウィザード**を使用すると、修復しているコンピューターの Windows オペレーティングシステムから修正プログラムまたはサービスパックを削除できます。</span><span class="sxs-lookup"><span data-stu-id="277ad-153">The **Hotfix Uninstall Wizard** lets you remove hotfixes or service packs from the Windows operating system on the computer that you are repairing.</span></span> <span data-ttu-id="277ad-154">このツールは、修正プログラムまたはサービスパックがオペレーティングシステムの起動を妨げている可能性がある場合に使用します。</span><span class="sxs-lookup"><span data-stu-id="277ad-154">Use this tool when a hotfix or service pack is suspected in preventing the operating system from starting.</span></span>

<span data-ttu-id="277ad-155">ツールによって複数のホットフィックスをアンインストールすることはできますが、アンインストールは一度に1つだけ行うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="277ad-155">We recommend that you uninstall only one hotfix at a time, even though the tool lets you uninstall more than one.</span></span>

<span data-ttu-id="277ad-156">**重要** 修正プログラムをインストールした後にインストールまたは更新したプログラムは、修正プログラムをアンインストールした後に正常に動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="277ad-156">**Important** Programs that were installed or updated after a hotfix was installed might not work correctly after you uninstall a hotfix.</span></span>

 

### <span data-ttu-id="277ad-157">Locksmith</span><span class="sxs-lookup"><span data-stu-id="277ad-157">Locksmith</span></span>

<span data-ttu-id="277ad-158">**Locksmith ウィザード**を使用すると、分析または修復する Windows オペレーティングシステムのローカルアカウントのパスワードを設定または変更することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-158">The **Locksmith Wizard** lets you set or change the password for any local account on the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="277ad-159">現在のパスワードを確認する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="277ad-159">You do not have to know the current password.</span></span> <span data-ttu-id="277ad-160">ただし、設定したパスワードは、ローカルグループポリシーオブジェクトで定義されている要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="277ad-160">However, the password that you set must comply with any requirements that are defined by a local Group Policy Object.</span></span> <span data-ttu-id="277ad-161">これには、パスワードの長さと複雑さが含まれます。</span><span class="sxs-lookup"><span data-stu-id="277ad-161">This includes password length and complexity.</span></span>

<span data-ttu-id="277ad-162">**Locksmith**は、ローカル管理者アカウントなどのローカルアカウントのパスワードが不明な場合に使用できます。</span><span class="sxs-lookup"><span data-stu-id="277ad-162">You can use **Locksmith** when the password for a local account, such as the local Administrator account, is unknown.</span></span> <span data-ttu-id="277ad-163">**Locksmith**を使用して、ドメインアカウントのパスワードを設定することはできません。</span><span class="sxs-lookup"><span data-stu-id="277ad-163">You cannot use **Locksmith** to set passwords for domain accounts.</span></span>

### <span data-ttu-id="277ad-164">レジストリ エディター</span><span class="sxs-lookup"><span data-stu-id="277ad-164">Registry Editor</span></span>

<span data-ttu-id="277ad-165">**レジストリエディター**を使って、分析または修復している Windows オペレーティングシステムのレジストリにアクセスして変更することができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-165">You can use **Registry Editor** to access and change the registry of the Windows operating system that you are analyzing or repairing.</span></span> <span data-ttu-id="277ad-166">これには、キーと値の追加、削除、編集、レジストリ (.reg) ファイルのインポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="277ad-166">This includes adding, removing, and editing keys and values, and importing registry (.reg) files.</span></span>

<span data-ttu-id="277ad-167">**警告** **レジストリエディター**を使用してレジストリを誤って変更した場合、重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="277ad-167">**Warning** Serious problems can occur if you change the registry incorrectly by using **Registry Editor**.</span></span> <span data-ttu-id="277ad-168">このような問題では、オペレーティング システムの再インストールが必要になることもあります。</span><span class="sxs-lookup"><span data-stu-id="277ad-168">These problems might require you to reinstall the operating system.</span></span> <span data-ttu-id="277ad-169">レジストリに変更を加える前に、コンピューター上の重要なデータをバックアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="277ad-169">Before you make changes to the registry, you should back up any valued data on the computer.</span></span> <span data-ttu-id="277ad-170">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="277ad-170">Change the registry at your own risk.</span></span>

 

### <span data-ttu-id="277ad-171">SFC スキャン</span><span class="sxs-lookup"><span data-stu-id="277ad-171">SFC Scan</span></span>

<span data-ttu-id="277ad-172">**SFC スキャン**ツールは、**システムファイルの修復ウィザード**を開始し、インストールされている Windows オペレーティングシステムの起動を妨げているシステムファイルを修復できるようにします。</span><span class="sxs-lookup"><span data-stu-id="277ad-172">The **SFC Scan** tool starts the **System File Repair Wizard** and lets you repair system files that are preventing the installed Windows operating system from starting.</span></span> <span data-ttu-id="277ad-173">**システムファイルの修復ウィザード**を使用すると、破損または紛失しているシステムファイルを自動的に修復したり、修復を実行する前に確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="277ad-173">The **System File Repair Wizard** can automatically repair system files that are corrupted or missing, or it can prompt you before it performs any repairs.</span></span>

### <span data-ttu-id="277ad-174">ソリューションウィザード</span><span class="sxs-lookup"><span data-stu-id="277ad-174">Solution Wizard</span></span>

<span data-ttu-id="277ad-175">**ソリューションウィザード**では一連の質問が表示され、お客様の回答に基づいて、状況に最適なツールが提案されます。</span><span class="sxs-lookup"><span data-stu-id="277ad-175">The **Solution Wizard** presents a series of questions and then recommends the best tool for the situation, based on your answers.</span></span> <span data-ttu-id="277ad-176">このウィザードは、DaRT のツールに慣れていないときに使用するツールを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="277ad-176">This wizard helps you determine which tool to use when you are not familiar with the tools in DaRT.</span></span>

### <span data-ttu-id="277ad-177">TCP/IP 構成</span><span class="sxs-lookup"><span data-stu-id="277ad-177">TCP/IP Config</span></span>

<span data-ttu-id="277ad-178">問題のあるコンピューターを DaRT に起動すると、動的ホスト構成プロトコル (DHCP) から TCP/IP 構成 (IP アドレスと DNS サーバー) が自動的に取得されるように設定されます。</span><span class="sxs-lookup"><span data-stu-id="277ad-178">When you boot a problem computer into DaRT, it is set to automatically obtain its TCP/IP configuration (IP address and DNS server) from Dynamic Host Configuration Protocol (DHCP).</span></span> <span data-ttu-id="277ad-179">DHCP を使用できない場合は、 **tcp/ip**構成ツールを使って手動で tcp/ip を構成できます。</span><span class="sxs-lookup"><span data-stu-id="277ad-179">If DHCP is unavailable, you can manually configure TCP/IP by using the **TCP/IP Config** tool.</span></span> <span data-ttu-id="277ad-180">まずネットワークアダプターを選んでから、そのアダプターの IP アドレスと DNS サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="277ad-180">You first select a network adapter, and then configure the IP address and DNS server for that adapter.</span></span>

## <span data-ttu-id="277ad-181">関連トピック</span><span class="sxs-lookup"><span data-stu-id="277ad-181">Related topics</span></span>


[<span data-ttu-id="277ad-182">DaRT 10 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="277ad-182">Getting Started with DaRT 10</span></span>](getting-started-with-dart-10.md)

 

 





