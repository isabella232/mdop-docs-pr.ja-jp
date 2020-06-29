---
title: App-V 5.0 SP3 でサポートされる構成
description: App-V 5.0 SP3 でサポートされる構成
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814794"
---
# <span data-ttu-id="40c4f-103">App-V 5.0 SP3 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="40c4f-103">App-V 5.0 SP3 Supported Configurations</span></span>


<span data-ttu-id="40c4f-104">このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.0 SP3 をインストールして実行するための要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="40c4f-104">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.0 SP3 in your environment.</span></span>

## <span data-ttu-id="40c4f-105">App-v Server のシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-105">App-V Server system requirements</span></span>


<span data-ttu-id="40c4f-106">このセクションでは、すべての App-v Server コンポーネントのオペレーティングシステムとハードウェアの要件を示します。</span><span class="sxs-lookup"><span data-stu-id="40c4f-106">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="40c4f-107">サポートされていないアプリ-V 5.0 SP3 サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="40c4f-107">Unsupported App-V 5.0 SP3 Server scenarios</span></span>

<span data-ttu-id="40c4f-108">App-v 5.0 SP3 サーバーでは、次のシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-108">The App-V 5.0 SP3 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="40c4f-109">Microsoft Windows Server Core を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="40c4f-109">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="40c4f-110">以前のバージョンの App-v 5.0 SP3 サーバーコンポーネントを実行するコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="40c4f-110">Deployment to a computer that runs a previous version of App-V 5.0 SP3 Server components.</span></span> <span data-ttu-id="40c4f-111">App-v 5.0 SP3 は、アプリ-V 4.5 軽量ストリーミングサーバー (LWS) サーバーでのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="40c4f-111">You can install App-V 5.0 SP3 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="40c4f-112">App-v 4.5 Application Virtualization Management Service (HWS) サーバーを使ったアプリの展開は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-112">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="40c4f-113">Microsoft SQL Server Express edition を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="40c4f-113">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="40c4f-114">管理サーバーデータベースまたはレポートデータベースのリモート展開。</span><span class="sxs-lookup"><span data-stu-id="40c4f-114">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="40c4f-115">インストーラーは、Microsoft SQL Server を実行しているコンピューターで直接実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c4f-115">You must run the installer directly on the computer that is running Microsoft SQL Server.</span></span>

-   <span data-ttu-id="40c4f-116">ドメインコントローラーへの展開。</span><span class="sxs-lookup"><span data-stu-id="40c4f-116">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="40c4f-117">短いパス。</span><span class="sxs-lookup"><span data-stu-id="40c4f-117">Short paths.</span></span> <span data-ttu-id="40c4f-118">短いパスを使用する予定の場合は、新しいボリュームを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="40c4f-118">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="40c4f-119">管理サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-119">Management server operating system requirements</span></span>

<span data-ttu-id="40c4f-120">次の表は、app-v 5.0 SP3 Management server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-120">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Management server installation.</span></span>

<span data-ttu-id="40c4f-121">**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="40c4f-121">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="40c4f-122">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="40c4f-122">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="40c4f-123">詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c4f-123">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-124">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-124">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-125">Service Pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-125">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-126">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-126">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-127">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-127">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-128">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-128">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-129">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-129">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-130">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-130">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-131">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-131">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-132">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-132">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-133">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-133">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="40c4f-134">**重要** リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-134">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="40c4f-135">管理サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-135">Management server hardware requirements</span></span>

-   <span data-ttu-id="40c4f-136">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="40c4f-136">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="40c4f-137">RAM: 1 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="40c4f-137">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="40c4f-138">ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-138">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="40c4f-139">管理サーバーのデータベース要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-139">Management server database requirements</span></span>

<span data-ttu-id="40c4f-140">次の表は、App-v 5.0 SP3 Management データベースのインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-140">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-141">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="40c4f-141">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="40c4f-142">Service pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-142">Service pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-143">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-143">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-144">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="40c4f-144">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-145">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-146">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-146">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-147">SP2</span><span class="sxs-lookup"><span data-stu-id="40c4f-147">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-148">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-148">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-149">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-149">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-150">読み</span><span class="sxs-lookup"><span data-stu-id="40c4f-150">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-151">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-151">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="40c4f-152">発行サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-152">Publishing server operating system requirements</span></span>

<span data-ttu-id="40c4f-153">次の表は、app-v 5.0 SP3 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-153">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Publishing server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-154">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-154">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-155">Service Pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-155">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-156">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-156">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-157">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-157">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-158">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-158">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-159">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-159">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-160">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-160">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-161">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-161">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-162">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-162">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-163">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-163">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="40c4f-164">発行サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-164">Publishing server hardware requirements</span></span>

<span data-ttu-id="40c4f-165">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-165">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="40c4f-166">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="40c4f-166">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="40c4f-167">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="40c4f-167">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="40c4f-168">ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-168">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="40c4f-169">レポートサーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-169">Reporting server operating system requirements</span></span>

<span data-ttu-id="40c4f-170">次の表は、app-v 5.0 SP3 Reporting server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-170">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Reporting server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-171">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-171">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-173">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-173">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-174">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-174">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-175">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-175">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-176">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-176">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-177">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-177">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-178">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-178">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-179">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-180">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-180">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="40c4f-181">レポートサーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-181">Reporting server hardware requirements</span></span>

<span data-ttu-id="40c4f-182">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-182">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="40c4f-183">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="40c4f-183">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="40c4f-184">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="40c4f-184">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="40c4f-185">ディスク領域: 200 MB のハードディスク空き容量</span><span class="sxs-lookup"><span data-stu-id="40c4f-185">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="40c4f-186">レポートサーバーデータベースの要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-186">Reporting server database requirements</span></span>

<span data-ttu-id="40c4f-187">次の表は、App-v 5.0 SP3 レポートデータベースのインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-187">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-188">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="40c4f-188">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="40c4f-189">Service pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-189">Service pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-190">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-190">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-191">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="40c4f-191">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-192">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-192">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-193">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-193">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-194">SP2</span><span class="sxs-lookup"><span data-stu-id="40c4f-194">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-195">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-195">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-196">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-196">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-197">読み</span><span class="sxs-lookup"><span data-stu-id="40c4f-197">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-198">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-198">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="40c4f-199">App-v クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-199">App-V client system requirements</span></span>


<span data-ttu-id="40c4f-200">次の表は、App-v 5.0 SP3 クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-200">The following table lists the operating systems that are supported for the App-V 5.0 SP3 client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-201">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-201">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-203">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-204">Microsoft Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="40c4f-204">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-205">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-205">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-206">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="40c4f-206">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-207">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-208">Windows7</span><span class="sxs-lookup"><span data-stu-id="40c4f-208">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-209">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-209">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-210">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-210">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="40c4f-211">次のような App-v クライアントインストールシナリオはサポートされていません。記載されている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="40c4f-211">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="40c4f-212">Windows Server を実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="40c4f-212">Computers that run Windows Server</span></span>

-   <span data-ttu-id="40c4f-213">App-v 4.6 SP1 またはそれ以前のバージョンを実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="40c4f-213">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="40c4f-214">App-v 5.0 SP3 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="40c4f-214">The App-V 5.0 SP3 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="40c4f-215">App-v クライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-215">App-V client hardware requirements</span></span>

<span data-ttu-id="40c4f-216">次の一覧は、App-v 5.0 SP3 クライアントのインストールでサポートされているハードウェア構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-216">The following list displays the supported hardware configuration for the App-V 5.0 SP3 client installation.</span></span>

-   <span data-ttu-id="40c4f-217">プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="40c4f-217">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="40c4f-218">RAM: 1 GB (32 ビット) または 2 GB (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="40c4f-218">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="40c4f-219">ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-219">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="40c4f-220">リモートデスクトップサービスクライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-220">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="40c4f-221">次の表は、App-v 5.0 SP3 リモートデスクトップサービス (RDS) クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-221">The following table lists the operating systems that are supported for App-V 5.0 SP3 Remote Desktop Services (RDS) client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-222">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-222">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-223">Service Pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-223">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-224">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-224">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-225">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-225">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-226">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-226">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-227">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-227">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-228">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-228">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-229">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-229">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-230">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-230">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-231">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-231">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="40c4f-232">リモートデスクトップサービスクライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-232">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="40c4f-233">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-233">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="40c4f-234">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="40c4f-234">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="40c4f-235">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="40c4f-235">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="40c4f-236">ディスク領域: 200 MB のハードディスク空き容量</span><span class="sxs-lookup"><span data-stu-id="40c4f-236">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="40c4f-237">Sequencer システム要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-237">Sequencer system requirements</span></span>


<span data-ttu-id="40c4f-238">次の表は、App-v 5.0 SP3 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-238">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Sequencer installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="40c4f-239">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="40c4f-239">Operating system</span></span></th>
<th align="left"><span data-ttu-id="40c4f-240">Service pack</span><span class="sxs-lookup"><span data-stu-id="40c4f-240">Service pack</span></span></th>
<th align="left"><span data-ttu-id="40c4f-241">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="40c4f-241">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-242">Microsoft Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-242">Microsoft Windows Server2012 R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="40c4f-243">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-243">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-244">Microsoft Windows Server2012</span><span class="sxs-lookup"><span data-stu-id="40c4f-244">Microsoft Windows Server2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-245">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-245">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-246">Microsoft Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="40c4f-246">Microsoft Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-247">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-247">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-248">64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-248">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-249">Microsoft Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="40c4f-249">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-250">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-250">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="40c4f-251">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="40c4f-251">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="40c4f-252">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-252">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="40c4f-253">Microsoft Windows7</span><span class="sxs-lookup"><span data-stu-id="40c4f-253">Microsoft Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-254">SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-254">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="40c4f-255">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="40c4f-255">32-bit and 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="40c4f-256">Sequencer ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="40c4f-256">Sequencer hardware requirements</span></span>

<span data-ttu-id="40c4f-257">ハードウェア要件については、Windows または Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c4f-257">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="40c4f-258">App-v は、追加のハードウェア要件を追加しません。</span><span class="sxs-lookup"><span data-stu-id="40c4f-258">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="40c4f-259">サポートされている System Center Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="40c4f-259">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="40c4f-260">App-v クライアントでは、次のバージョンの System Center Configuration Manager がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="40c4f-260">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="40c4f-261">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="40c4f-261">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="40c4f-262">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="40c4f-262">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="40c4f-263">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="40c4f-263">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="40c4f-264">Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="40c4f-264">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="40c4f-265">関連トピック</span><span class="sxs-lookup"><span data-stu-id="40c4f-265">Related topics</span></span>


[<span data-ttu-id="40c4f-266">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="40c4f-266">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="40c4f-267">APP-V 5.0 SP3 の前提条件</span><span class="sxs-lookup"><span data-stu-id="40c4f-267">App-V 5.0 SP3 Prerequisites</span></span>](app-v-50-sp3-prerequisites.md)

 

 





