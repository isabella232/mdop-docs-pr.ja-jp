---
title: Sequencer のハードウェア要件とソフトウェア要件
description: Sequencer のハードウェア要件とソフトウェア要件
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815534"
---
# <span data-ttu-id="ee5a0-103">Sequencer のハードウェア要件とソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ee5a0-103">Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="ee5a0-104">このトピックでは、Microsoft Application Virtualization (App-v) Sequencer を実行しているコンピューターの最低限の推奨されるハードウェアとソフトウェアの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="ee5a0-105">Sequencer をインストールする前に、各アプリケーションの順序を指定した後、クリーンなオペレーティングシステムイメージをシーケンスコンピューターに復元する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-105">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="ee5a0-106">Sequencer を実行しているコンピューターを復元するには、次のいずれかの方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-106">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="ee5a0-107">ハードドライブを再フォーマットして、オペレーティングシステムを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-107">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="ee5a0-108">別のディスクイメージングソフトウェアを使用して、Sequencer イメージを実行しているコンピューターのハードドライブを復元します。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-108">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

<span data-ttu-id="ee5a0-109">次のリストは、App-v Sequencer を実行するために推奨されるハードウェア要件の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-109">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="ee5a0-110">ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="ee5a0-110">Hardware Requirements</span></span>

-   <span data-ttu-id="ee5a0-111">プロセッサ: Intel Pentium III、1 GHz (32 ビットまたは64ビット)。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-111">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="ee5a0-112">シーケンス処理はシングルスレッドプロセスであり、デュアルプロセッサは利用できません。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-112">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="ee5a0-113">メモリ: 1 gb 以上、推奨される 2 GB。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-113">Memory—1GB or above, 2 GB recommended.</span></span>

-   <span data-ttu-id="ee5a0-114">ハードディスク:40 gb のハードディスク容量 (使用可能なハードディスク容量は最低 15 GB)。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-114">Hard Disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="ee5a0-115">順序を設定するアプリケーションで必要なハードディスク容量が少なくとも3回あることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-115">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="ee5a0-116">**注** シーケンス処理には、負荷の高いディスク使用が必要です。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-116">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="ee5a0-117">高速なディスク速度では、優先順位付けの時間を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-117">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="ee5a0-118">ソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ee5a0-118">Software Requirements</span></span>

<span data-ttu-id="ee5a0-119">次のリストは、Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-119">The following list outlines the supported operating systems for running the Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee5a0-120">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ee5a0-120">Operating System</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-121">エディション</span><span class="sxs-lookup"><span data-stu-id="ee5a0-121">Edition</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-122">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ee5a0-122">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-123">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ee5a0-123">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee5a0-124">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="ee5a0-124">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-125">Professional</span><span class="sxs-lookup"><span data-stu-id="ee5a0-125">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-126">SP2 または SP3</span><span class="sxs-lookup"><span data-stu-id="ee5a0-126">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-127">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-127">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee5a0-128">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="ee5a0-128">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-129">ビジネス、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="ee5a0-129">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-130">Service pack、SP1、または SP2 がない</span><span class="sxs-lookup"><span data-stu-id="ee5a0-130">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-131">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-131">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee5a0-132">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="ee5a0-132">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-133">プロフェッショナル、エンタープライズ、または究極</span><span class="sxs-lookup"><span data-stu-id="ee5a0-133">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-134">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-134">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ee5a0-135">¹ SP1 または SP2 を搭載した App-v 4.5 でサポートされているアプリ-V 4.6</span><span class="sxs-lookup"><span data-stu-id="ee5a0-135">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="ee5a0-136">**注** Application Virtualization (App-v) 4.6 Sequencer では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-136">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="ee5a0-137">ターゲットコンピューターにインストールされているアプリケーションと同じアプリケーションを使って、Sequencer を実行しているコンピューターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-137">You should configure computers running the Sequencer with the same applications that are installed on target computers.</span></span>

### <span data-ttu-id="ee5a0-138">リモートデスクトップサービスのソフトウェア要件</span><span class="sxs-lookup"><span data-stu-id="ee5a0-138">Software Requirements for Remote Desktop Services</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ee5a0-139">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ee5a0-139">Operating System</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-140">エディション</span><span class="sxs-lookup"><span data-stu-id="ee5a0-140">Edition</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-141">Service Pack</span><span class="sxs-lookup"><span data-stu-id="ee5a0-141">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="ee5a0-142">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="ee5a0-142">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee5a0-143">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="ee5a0-143">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-144">Standard Edition、Enterprise Edition、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="ee5a0-144">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-145">SP1 または SP2</span><span class="sxs-lookup"><span data-stu-id="ee5a0-145">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-146">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-146">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee5a0-147">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="ee5a0-147">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-148">Standard Edition、Enterprise Edition、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="ee5a0-148">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-149">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-149">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee5a0-150">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="ee5a0-150">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-151">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="ee5a0-151">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-152">SP1 または SP2</span><span class="sxs-lookup"><span data-stu-id="ee5a0-152">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee5a0-153">x86</span><span class="sxs-lookup"><span data-stu-id="ee5a0-153">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ee5a0-154">**注** Application Virtualization (App-v) 4.6 for Remote Desktop Services では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="ee5a0-154">**Note** Application Virtualization (App-V) 4.6 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="ee5a0-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ee5a0-155">Related topics</span></span>


[<span data-ttu-id="ee5a0-156">Application Virtualization Sequencer の概要</span><span class="sxs-lookup"><span data-stu-id="ee5a0-156">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





