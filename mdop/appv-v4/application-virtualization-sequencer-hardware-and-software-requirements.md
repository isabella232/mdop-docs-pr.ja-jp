---
title: Application Virtualization Sequencer のハードウェア要件とソフトウェア要件
description: Application Virtualization Sequencer のハードウェア要件とソフトウェア要件
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819624"
---
# <span data-ttu-id="b9072-103">Application Virtualization Sequencer のハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-103">Application Virtualization Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="b9072-104">このトピックでは、Microsoft Application Virtualization (App-v) Sequencer を実行しているコンピューターの最低限の推奨されるハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9072-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="b9072-105">**重要** Sequencer がローカルシステムに行った変更のため、管理者特権を持つアカウントを使用して、App-v sequencer (**SFTSequencer.exe**) を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9072-105">**Important** You must run the App-V sequencer (**SFTSequencer.exe**) using an account that has administrator privileges because of the changes the sequencer makes to the local system.</span></span> <span data-ttu-id="b9072-106">これらの変更には、C:\ の**ファイル**ディレクトリへのファイルの書き込み、レジストリの変更、サービスの開始と停止、ファイルのセキュリティ記述子の更新、アクセス許可の変更などがあります。</span><span class="sxs-lookup"><span data-stu-id="b9072-106">These changes can include writing files to the **C:\\Program Files** directory, making registry changes, starting and stopping services, updating security descriptors for files, and changing permissions.</span></span>

 

<span data-ttu-id="b9072-107">Sequencer をインストールする前に、各アプリケーションの順序を指定した後、クリーンなオペレーティングシステムイメージをシーケンスコンピューターに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9072-107">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="b9072-108">Sequencer を実行しているコンピューターを復元するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="b9072-108">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="b9072-109">ハードドライブを再フォーマットして、オペレーティングシステムを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="b9072-109">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="b9072-110">別のディスクイメージングソフトウェアを使用して、Sequencer イメージを実行しているコンピューターのハードドライブを復元します。</span><span class="sxs-lookup"><span data-stu-id="b9072-110">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

-   <span data-ttu-id="b9072-111">Microsoft Virtual PC イメージなどの仮想オペレーティングシステムイメージを元に戻します。</span><span class="sxs-lookup"><span data-stu-id="b9072-111">Revert a virtual operating system image such as a Microsoft Virtual PC image.</span></span> <span data-ttu-id="b9072-112">仮想マシンを使用すると、最小限の管理で簡単に再利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="b9072-112">Using a virtual machine allows for clean sequencing environments to be easily reused with minimal administration.</span></span>

<span data-ttu-id="b9072-113">次のリストは、App-v Sequencer を実行するために推奨されるハードウェア要件の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9072-113">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

<span data-ttu-id="b9072-114">要件は、Microsoft Application Virtualization (App-v) 4.6 SP2 の後に記載されています。その後に、App-v 4.6 SP2 より前のバージョンの要件が示されています。</span><span class="sxs-lookup"><span data-stu-id="b9072-114">The requirements are listed first for Microsoft Application Virtualization (App-V)4.6 SP2, followed by the requirements for versions that preceded App-V4.6SP2.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="b9072-115">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-115">Hardware Requirements</span></span>

-   <span data-ttu-id="b9072-116">プロセッサ: Intel Pentium III、1 GHz (32 ビットまたは64ビット)。</span><span class="sxs-lookup"><span data-stu-id="b9072-116">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="b9072-117">シーケンス処理はシングルスレッドプロセスであり、デュアルプロセッサは利用できません。</span><span class="sxs-lookup"><span data-stu-id="b9072-117">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="b9072-118">メモリ: 1 GB 以上、2 GB 推奨。</span><span class="sxs-lookup"><span data-stu-id="b9072-118">Memory—1GB or above, 2GB recommended.</span></span>

-   <span data-ttu-id="b9072-119">ハードディスク:40 gb のハードディスク容量 (使用可能なハードディスク容量は最低 15 GB)。</span><span class="sxs-lookup"><span data-stu-id="b9072-119">Hard disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="b9072-120">順序を設定するアプリケーションで必要なハードディスク容量が少なくとも3回あることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9072-120">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="b9072-121">**注** シーケンス処理には、負荷の高いディスク使用が必要です。</span><span class="sxs-lookup"><span data-stu-id="b9072-121">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="b9072-122">高速なディスク速度では、優先順位付けの時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="b9072-122">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="b9072-123">App-v 4.6 SP2 のソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-123">Software Requirements for App-V 4.6 SP2</span></span>

<span data-ttu-id="b9072-124">次のリストは、App-v 4.6 SP2 Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9072-124">The following list outlines the supported operating systems for running the App-V 4.6 SP2 Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b9072-125">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b9072-125">Operating System</span></span></th>
<th align="left"><span data-ttu-id="b9072-126">エディション</span><span class="sxs-lookup"><span data-stu-id="b9072-126">Edition</span></span></th>
<th align="left"><span data-ttu-id="b9072-127">Service Pack</span><span class="sxs-lookup"><span data-stu-id="b9072-127">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="b9072-128">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b9072-128">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-129">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="b9072-129">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-130">Professional</span><span class="sxs-lookup"><span data-stu-id="b9072-130">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-131">読み</span><span class="sxs-lookup"><span data-stu-id="b9072-131">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-132">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-132">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-133">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="b9072-133">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-134">ビジネス、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="b9072-134">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-135">SP2</span><span class="sxs-lookup"><span data-stu-id="b9072-135">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-136">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-136">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-137">Windows7</span><span class="sxs-lookup"><span data-stu-id="b9072-137">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-138">プロフェッショナル、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="b9072-138">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-139">Service pack または SP1 がない</span><span class="sxs-lookup"><span data-stu-id="b9072-139">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-140">x86 and x64 (x86 と x64)</span><span class="sxs-lookup"><span data-stu-id="b9072-140">x86 and x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-141">Windows 8</span><span class="sxs-lookup"><span data-stu-id="b9072-141">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-142">Pro または Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-142">Pro or Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b9072-143">x86 and x64 (x86 と x64)</span><span class="sxs-lookup"><span data-stu-id="b9072-143">x86 and x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b9072-144">**注** Application Virtualization (App-v) 4.6 SP2 Sequencer では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9072-144">**Note** The Application Virtualization (App-V) 4.6 SP2 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="b9072-145">ターゲットコンピューターにインストールされているアプリケーションと同じアプリケーションを使って、Sequencer を実行しているコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9072-145">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="b9072-146">App-v 4.6 SP2 より前のバージョンのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-146">Software Requirements for Versions that Precede App-V 4.6 SP2</span></span>

<span data-ttu-id="b9072-147">次の一覧は、App-v 4.6 SP2 より前のバージョンで Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="b9072-147">The following list outlines the supported operating systems for running the Sequencer for versions that precede App-V 4.6 SP2.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b9072-148">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b9072-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="b9072-149">エディション</span><span class="sxs-lookup"><span data-stu-id="b9072-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="b9072-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="b9072-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="b9072-151">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b9072-151">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-152">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="b9072-152">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-153">Professional</span><span class="sxs-lookup"><span data-stu-id="b9072-153">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-154">SP2 または SP3</span><span class="sxs-lookup"><span data-stu-id="b9072-154">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-155">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-155">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-156">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="b9072-156">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-157">ビジネス、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="b9072-157">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-158">Service pack、SP1、または SP2 がない</span><span class="sxs-lookup"><span data-stu-id="b9072-158">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-159">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-159">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-160">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="b9072-160">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-161">プロフェッショナル、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="b9072-161">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b9072-162">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-162">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b9072-163">¹ SP1 または SP2 を搭載した App-v 4.5 でサポートされているアプリ-V 4.6</span><span class="sxs-lookup"><span data-stu-id="b9072-163">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="b9072-164">**注** Application Virtualization (App-v) 4.6 Sequencer では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9072-164">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="b9072-165">ターゲットコンピューターにインストールされているアプリケーションと同じアプリケーションを使って、Sequencer を実行しているコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9072-165">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="b9072-166">App-v 4.6 SP2 用のリモートデスクトップサービスのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-166">Software Requirements for Remote Desktop Services for App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b9072-167">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b9072-167">Operating System</span></span></th>
<th align="left"><span data-ttu-id="b9072-168">エディション</span><span class="sxs-lookup"><span data-stu-id="b9072-168">Edition</span></span></th>
<th align="left"><span data-ttu-id="b9072-169">Service Pack</span><span class="sxs-lookup"><span data-stu-id="b9072-169">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="b9072-170">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b9072-170">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-171">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="b9072-171">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-172">Standard Edition、Enterprise Edition、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-172">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-173">SP2</span><span class="sxs-lookup"><span data-stu-id="b9072-173">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-174">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-174">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-175">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="b9072-175">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-176">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-176">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-177">SP2</span><span class="sxs-lookup"><span data-stu-id="b9072-177">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-178">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-178">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-179">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="b9072-179">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-180">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-180">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-181">Service pack または SP1 がない</span><span class="sxs-lookup"><span data-stu-id="b9072-181">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-182">x64</span><span class="sxs-lookup"><span data-stu-id="b9072-182">x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-183">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b9072-183">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-184">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-184">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="b9072-185">x86 または x64</span><span class="sxs-lookup"><span data-stu-id="b9072-185">x86 or x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b9072-186">**注** Application Virtualization (App-v) 4.6 SP2 リモートデスクトップサービスでは、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9072-186">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

### <span data-ttu-id="b9072-187">App-V 4.6 SP2 より前のバージョンのリモートデスクトップサービスのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-187">Software Requirements for Remote Desktop Services for Versions that Precede App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b9072-188">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b9072-188">Operating System</span></span></th>
<th align="left"><span data-ttu-id="b9072-189">エディション</span><span class="sxs-lookup"><span data-stu-id="b9072-189">Edition</span></span></th>
<th align="left"><span data-ttu-id="b9072-190">Service Pack</span><span class="sxs-lookup"><span data-stu-id="b9072-190">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="b9072-191">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="b9072-191">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-192">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="b9072-192">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-193">Standard Edition、Enterprise Edition、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-193">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-194">SP1 または SP2</span><span class="sxs-lookup"><span data-stu-id="b9072-194">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-195">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-195">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-196">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="b9072-196">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-197">Standard Edition、Enterprise Edition、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-197">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-198">Service pack または SP2 がない</span><span class="sxs-lookup"><span data-stu-id="b9072-198">No service pack or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-199">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-199">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9072-200">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="b9072-200">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-201">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-201">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-202">SP1 または SP2</span><span class="sxs-lookup"><span data-stu-id="b9072-202">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-203">x86</span><span class="sxs-lookup"><span data-stu-id="b9072-203">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9072-204">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="b9072-204">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-205">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="b9072-205">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-206">Service pack または SP1 がない</span><span class="sxs-lookup"><span data-stu-id="b9072-206">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9072-207">x64</span><span class="sxs-lookup"><span data-stu-id="b9072-207">x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b9072-208">**注** Application Virtualization (App-v) 4.6 SP2 リモートデスクトップサービスでは、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9072-208">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="b9072-209">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b9072-209">Related topics</span></span>


[<span data-ttu-id="b9072-210">Application Virtualization Client のハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="b9072-210">Application Virtualization Client Hardware and Software Requirements</span></span>](application-virtualization-client-hardware-and-software-requirements.md)

[<span data-ttu-id="b9072-211">Application Virtualization のシステム要件</span><span class="sxs-lookup"><span data-stu-id="b9072-211">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="b9072-212">Application Virtualization Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="b9072-212">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)

[<span data-ttu-id="b9072-213">Application Virtualization Sequencer をアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="b9072-213">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





