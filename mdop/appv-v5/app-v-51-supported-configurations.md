---
title: App-V 5.1 でサポートされる構成
description: App-V 5.1 でサポートされる構成
author: dansimp
ms.assetid: 8b8db63b-f71c-4ae9-80e7-a6752334e1f6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/02/2020
ms.openlocfilehash: fbda364de66b1f7b8730dca38f864a84f7848e58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814723"
---
# <span data-ttu-id="151c5-103">App-V 5.1 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="151c5-103">App-V 5.1 Supported Configurations</span></span>

><span data-ttu-id="151c5-104">適用対象: Windows 10 バージョン 1607;Window Server 2019;Windows Server 2016Windows Server 2012 R2Windows Server 2012Windows Server 2008 R2 (拡張セキュリティ更新プログラム)</span><span class="sxs-lookup"><span data-stu-id="151c5-104">Applies to: Windows 10, version 1607; Window Server 2019; Windows Server 2016; Windows Server 2012 R2; Windows Server 2012; Windows Server 2008 R2 (Extended Security Update)</span></span>

<span data-ttu-id="151c5-105">このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.1 をインストールして実行するための要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="151c5-105">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.1 in your environment.</span></span>

## <span data-ttu-id="151c5-106">App-v Server のシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-106">App-V Server system requirements</span></span>

<span data-ttu-id="151c5-107">このセクションでは、すべての App-v Server コンポーネントのオペレーティングシステムとハードウェアの要件を示します。</span><span class="sxs-lookup"><span data-stu-id="151c5-107">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="151c5-108">サポートされていない App-v 5.1 サーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="151c5-108">Unsupported App-V 5.1 Server scenarios</span></span>

<span data-ttu-id="151c5-109">App-v 5.1 サーバーでは、次のシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="151c5-109">The App-V 5.1 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="151c5-110">Microsoft Windows Server Core を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="151c5-110">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="151c5-111">以前のバージョンの App-v 5.1 サーバーコンポーネントを実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="151c5-111">Deployment to a computer that runs a previous version of App-V 5.1 Server components.</span></span> <span data-ttu-id="151c5-112">App-v 5.1 は、アプリ-V 4.5 軽量ストリーミングサーバー (LWS) サーバーでのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="151c5-112">You can install App-V 5.1 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="151c5-113">App-v 4.5 Application Virtualization Management Service (HWS) サーバーを使ったアプリの展開は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="151c5-113">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="151c5-114">Microsoft SQL Server Express edition を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="151c5-114">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="151c5-115">ドメインコントローラーへの展開。</span><span class="sxs-lookup"><span data-stu-id="151c5-115">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="151c5-116">短いパス。</span><span class="sxs-lookup"><span data-stu-id="151c5-116">Short paths.</span></span> <span data-ttu-id="151c5-117">短いパスを使用する予定の場合は、新しいボリュームを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="151c5-117">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="151c5-118">管理サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-118">Management server operating system requirements</span></span>

<span data-ttu-id="151c5-119">次の表は、App-v 5.1 Management server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-119">The following table lists the operating systems that are supported for the App-V 5.1 Management server installation.</span></span>

> [!NOTE]
> <span data-ttu-id="151c5-120">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="151c5-120">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="151c5-121">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="151c5-121">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="151c5-122">詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151c5-122">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 | <span data-ttu-id="151c5-123">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-123">Operating System</span></span>                 | <span data-ttu-id="151c5-124">Service Pack</span><span class="sxs-lookup"><span data-stu-id="151c5-124">Service Pack</span></span> | <span data-ttu-id="151c5-125">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-125">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="151c5-126">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-126">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="151c5-127">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-127">64-bit</span></span>       |
| <span data-ttu-id="151c5-128">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-128">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="151c5-129">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-129">64-bit</span></span>       |
| <span data-ttu-id="151c5-130">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-130">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="151c5-131">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-131">64-bit</span></span>       |
| <span data-ttu-id="151c5-132">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-132">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="151c5-133">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-133">64-bit</span></span>       |
| <span data-ttu-id="151c5-134">Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="151c5-134">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span>|      <span data-ttu-id="151c5-135">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-135">SP1</span></span>     |        <span data-ttu-id="151c5-136">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-136">64-bit</span></span>       |
 

<span data-ttu-id="151c5-137">**重要** リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="151c5-137">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="151c5-138">管理サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-138">Management server hardware requirements</span></span>

-   <span data-ttu-id="151c5-139">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="151c5-139">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="151c5-140">RAM: 1 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="151c5-140">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="151c5-141">ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="151c5-141">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="151c5-142">管理サーバーのデータベース要件</span><span class="sxs-lookup"><span data-stu-id="151c5-142">Management server database requirements</span></span>

<span data-ttu-id="151c5-143">次の表は、App-v 5.1 Management データベースのインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-143">The following table lists the SQL Server versions that are supported for the App-V 5.1 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="151c5-144">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="151c5-144">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="151c5-145">Service pack</span><span class="sxs-lookup"><span data-stu-id="151c5-145">Service pack</span></span></th>
<th align="left"><span data-ttu-id="151c5-146">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-146">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-147">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-147">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="151c5-148">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-148">32-bit or 64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-149">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="151c5-149">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="151c5-150">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-150">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-151">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-151">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-152">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-152">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-153">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-153">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-154">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="151c5-154">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-155">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-155">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-156">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-156">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-157">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-157">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-158">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-158">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-159">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-159">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-160">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-160">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-161">読み</span><span class="sxs-lookup"><span data-stu-id="151c5-161">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-162">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-162">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="151c5-163">SQL server 2016 以降のユーザー構成ファイルの詳細については、[サポートの記事](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151c5-163">For more information on user configuration files with SQL server 2016 or later, see the [support article](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f).</span></span>

### <span data-ttu-id="151c5-164">発行サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-164">Publishing server operating system requirements</span></span>

<span data-ttu-id="151c5-165">次の表は、App-v 5.1 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-165">The following table lists the operating systems that are supported for the App-V 5.1 Publishing server installation.</span></span>

| <span data-ttu-id="151c5-166">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-166">Operating System</span></span>                 | <span data-ttu-id="151c5-167">Service Pack</span><span class="sxs-lookup"><span data-stu-id="151c5-167">Service Pack</span></span> | <span data-ttu-id="151c5-168">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-168">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="151c5-169">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-169">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="151c5-170">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-170">64-bit</span></span>       |
| <span data-ttu-id="151c5-171">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-171">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="151c5-172">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-172">64-bit</span></span>       |
| <span data-ttu-id="151c5-173">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-173">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="151c5-174">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-174">64-bit</span></span>       |
| <span data-ttu-id="151c5-175">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-175">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="151c5-176">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-176">64-bit</span></span>       |
| <span data-ttu-id="151c5-177">Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="151c5-177">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="151c5-178">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-178">SP1</span></span>     |        <span data-ttu-id="151c5-179">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-179">64-bit</span></span>       |

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="151c5-180">発行サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-180">Publishing server hardware requirements</span></span>

<span data-ttu-id="151c5-181">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="151c5-181">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="151c5-182">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="151c5-182">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="151c5-183">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="151c5-183">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="151c5-184">ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="151c5-184">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="151c5-185">レポートサーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-185">Reporting server operating system requirements</span></span>

<span data-ttu-id="151c5-186">次の表は、App-v 5.1 Reporting server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-186">The following table lists the operating systems that are supported for the App-V 5.1 Reporting server installation.</span></span>

| <span data-ttu-id="151c5-187">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-187">Operating System</span></span>                 | <span data-ttu-id="151c5-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="151c5-188">Service Pack</span></span> | <span data-ttu-id="151c5-189">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-189">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="151c5-190">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-190">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="151c5-191">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-191">64-bit</span></span>       |
| <span data-ttu-id="151c5-192">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-192">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="151c5-193">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-193">64-bit</span></span>       |
| <span data-ttu-id="151c5-194">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-194">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="151c5-195">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-195">64-bit</span></span>       |
| <span data-ttu-id="151c5-196">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-196">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="151c5-197">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-197">64-bit</span></span>       |
| <span data-ttu-id="151c5-198">Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="151c5-198">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="151c5-199">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-199">SP1</span></span>     |        <span data-ttu-id="151c5-200">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-200">64-bit</span></span>       |

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="151c5-201">レポートサーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-201">Reporting server hardware requirements</span></span>

<span data-ttu-id="151c5-202">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="151c5-202">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="151c5-203">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="151c5-203">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="151c5-204">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="151c5-204">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="151c5-205">ディスク領域: 200 MB のハードディスク空き容量</span><span class="sxs-lookup"><span data-stu-id="151c5-205">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="151c5-206">レポートサーバーデータベースの要件</span><span class="sxs-lookup"><span data-stu-id="151c5-206">Reporting server database requirements</span></span>

<span data-ttu-id="151c5-207">次の表は、App-v 5.1 Reporting database のインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-207">The following table lists the SQL Server versions that are supported for the App-V 5.1 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="151c5-208">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="151c5-208">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="151c5-209">Service pack</span><span class="sxs-lookup"><span data-stu-id="151c5-209">Service pack</span></span></th>
<th align="left"><span data-ttu-id="151c5-210">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-210">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-211">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="151c5-211">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="151c5-212">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-212">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-213">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-213">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-214">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-214">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-215">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-215">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-216">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="151c5-216">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-217">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-217">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-218">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-218">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-219">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-219">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-220">SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-220">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-221">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-221">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-222">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-222">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-223">読み</span><span class="sxs-lookup"><span data-stu-id="151c5-223">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-224">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-224">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="151c5-225">App-v クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-225">App-V client system requirements</span></span>

<span data-ttu-id="151c5-226">次の表は、App-v 5.1 クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-226">The following table lists the operating systems that are supported for the App-V 5.1 client installation.</span></span>

> [!NOTE]
> <span data-ttu-id="151c5-227">Windows 10 記念日リリース (1607 バージョン) では、app-v クライアントはボックス内にあり、以前のバージョンの App-v クライアントのインストールはブロックされます。</span><span class="sxs-lookup"><span data-stu-id="151c5-227">With the Windows 10 Anniversary release (aka 1607 version), the App-V client is in-box and will block installation of any previous version of the App-V client</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="151c5-228">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-228">Operating system</span></span></th>
<th align="left"><span data-ttu-id="151c5-229">Service pack</span><span class="sxs-lookup"><span data-stu-id="151c5-229">Service pack</span></span></th>
<th align="left"><span data-ttu-id="151c5-230">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-230">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-231">Microsoft Windows 10 (1607 以前のバージョン)</span><span class="sxs-lookup"><span data-stu-id="151c5-231">Microsoft Windows10 (pre-1607 version)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="151c5-232">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-232">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-233">Microsoft Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="151c5-233">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="151c5-234">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-234">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-235">Windows7</span><span class="sxs-lookup"><span data-stu-id="151c5-235">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-236">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-236">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-237">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-237">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="151c5-238">次のような App-v クライアントインストールシナリオはサポートされていません。記載されている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="151c5-238">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="151c5-239">Windows Server を実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="151c5-239">Computers that run Windows Server</span></span>

-   <span data-ttu-id="151c5-240">App-v 4.6 SP1 またはそれ以前のバージョンを実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="151c5-240">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="151c5-241">App-v 5.1 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="151c5-241">The App-V 5.1 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="151c5-242">App-v クライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-242">App-V client hardware requirements</span></span>

<span data-ttu-id="151c5-243">次の一覧は、App-v 5.1 クライアントのインストールでサポートされているハードウェア構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-243">The following list displays the supported hardware configuration for the App-V 5.1 client installation.</span></span>

-   <span data-ttu-id="151c5-244">プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="151c5-244">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="151c5-245">RAM: 1 GB (32 ビット) または 2 GB (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="151c5-245">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="151c5-246">ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。</span><span class="sxs-lookup"><span data-stu-id="151c5-246">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="151c5-247">リモートデスクトップサービスクライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-247">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="151c5-248">次の表は、App-v 5.1 リモートデスクトップサービス (RDS) クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-248">The following table lists the operating systems that are supported for App-V 5.1 Remote Desktop Services (RDS) client installation.</span></span>

| <span data-ttu-id="151c5-249">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-249">Operating System</span></span>                 | <span data-ttu-id="151c5-250">Service Pack</span><span class="sxs-lookup"><span data-stu-id="151c5-250">Service Pack</span></span> | <span data-ttu-id="151c5-251">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-251">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="151c5-252">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-252">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="151c5-253">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-253">64-bit</span></span>       |
| <span data-ttu-id="151c5-254">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-254">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="151c5-255">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-255">64-bit</span></span>       |
| <span data-ttu-id="151c5-256">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-256">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="151c5-257">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-257">64-bit</span></span>       |
| <span data-ttu-id="151c5-258">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-258">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="151c5-259">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-259">64-bit</span></span>       |
| <span data-ttu-id="151c5-260">Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="151c5-260">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="151c5-261">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-261">SP1</span></span>     |        <span data-ttu-id="151c5-262">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-262">64-bit</span></span>       |

### <span data-ttu-id="151c5-263">リモートデスクトップサービスクライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-263">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="151c5-264">App-v では、Windows Server の場合以外に追加要件はありません。</span><span class="sxs-lookup"><span data-stu-id="151c5-264">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="151c5-265">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="151c5-265">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="151c5-266">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="151c5-266">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="151c5-267">ディスク領域: 200 MB のハードディスク空き容量</span><span class="sxs-lookup"><span data-stu-id="151c5-267">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="151c5-268">Sequencer システム要件</span><span class="sxs-lookup"><span data-stu-id="151c5-268">Sequencer system requirements</span></span>

<span data-ttu-id="151c5-269">次の表は、App-v 5.1 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="151c5-269">The following table lists the operating systems that are supported for the App-V 5.1 Sequencer installation.</span></span>

| <span data-ttu-id="151c5-270">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="151c5-270">Operating System</span></span>                 | <span data-ttu-id="151c5-271">Service Pack</span><span class="sxs-lookup"><span data-stu-id="151c5-271">Service Pack</span></span> | <span data-ttu-id="151c5-272">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="151c5-272">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="151c5-273">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="151c5-273">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="151c5-274">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-274">64-bit</span></span>       |
| <span data-ttu-id="151c5-275">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="151c5-275">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="151c5-276">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-276">64-bit</span></span>       |
| <span data-ttu-id="151c5-277">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="151c5-277">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="151c5-278">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-278">64-bit</span></span>       |
| <span data-ttu-id="151c5-279">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="151c5-279">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="151c5-280">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-280">64-bit</span></span>       |
| <span data-ttu-id="151c5-281">Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="151c5-281">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="151c5-282">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-282">SP1</span></span>     |        <span data-ttu-id="151c5-283">64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-283">64-bit</span></span>       |
| <span data-ttu-id="151c5-284">Microsoft Windows 10</span><span class="sxs-lookup"><span data-stu-id="151c5-284">Microsoft Windows 10</span></span>             |              | <span data-ttu-id="151c5-285">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-285">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="151c5-286">Microsoft Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="151c5-286">Microsoft Windows 8.1</span></span>            |              | <span data-ttu-id="151c5-287">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-287">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="151c5-288">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="151c5-288">Microsoft Windows 7</span></span>              |      <span data-ttu-id="151c5-289">SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-289">SP1</span></span>     | <span data-ttu-id="151c5-290">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="151c5-290">32-bit and 64-bit</span></span>   |

### <span data-ttu-id="151c5-291">Sequencer ハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="151c5-291">Sequencer hardware requirements</span></span>

<span data-ttu-id="151c5-292">ハードウェア要件については、Windows または Windows Server のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="151c5-292">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="151c5-293">App-v は、追加のハードウェア要件を追加しません。</span><span class="sxs-lookup"><span data-stu-id="151c5-293">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="151c5-294">サポートされている System Center Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="151c5-294">Supported versions of System Center Configuration Manager</span></span>

<span data-ttu-id="151c5-295">App-v クライアントでは、次のバージョンの System Center Configuration Manager がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="151c5-295">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="151c5-296">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="151c5-296">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="151c5-297">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="151c5-297">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="151c5-298">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-298">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="151c5-299">次の App-v および System Center Configuration Manager のバージョンマトリックスには、すべての正式にサポートされている App-v と構成マネージャーの組み合わせが表示されます。</span><span class="sxs-lookup"><span data-stu-id="151c5-299">The following App-V and System Center Configuration Manager version matrix shows all officially supported combinations of App-V and Configuration Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="151c5-300">App-v 4.5 と4.6 の両方が、メインストリームサポートを終了しました。</span><span class="sxs-lookup"><span data-stu-id="151c5-300">Both App-V 4.5 and 4.6 have exited Mainstream support.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="151c5-301">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="151c5-301">App-V Version</span></span></th>
<th align="left"><span data-ttu-id="151c5-302">System Center Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="151c5-302">System Center Configuration Manager 2007</span></span></th>
<th align="left"><span data-ttu-id="151c5-303">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="151c5-303">System Center 2012 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="151c5-304">System Center 2012 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-304">System Center 2012 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="151c5-305">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="151c5-305">System Center 2012 R2 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="151c5-306">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="151c5-306">System Center 2012 R2 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="151c5-307">System Center 2012 Configuration Manager SP2</span><span class="sxs-lookup"><span data-stu-id="151c5-307">System Center 2012 Configuration Manager SP2</span></span></th>
<th align="left"><span data-ttu-id="151c5-308">System Center Configuration Manager バージョン1511</span><span class="sxs-lookup"><span data-stu-id="151c5-308">System Center Configuration Manager Version 1511</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="151c5-309">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="151c5-309">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-310">MSI ラッパーのみ</span><span class="sxs-lookup"><span data-stu-id="151c5-310">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-311">なし</span><span class="sxs-lookup"><span data-stu-id="151c5-311">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-312">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="151c5-312">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-313">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="151c5-313">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-314">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-314">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-315">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-315">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-316">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-316">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="151c5-317">App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="151c5-317">App-V 5.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-318">MSI ラッパーのみ</span><span class="sxs-lookup"><span data-stu-id="151c5-318">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-319">なし</span><span class="sxs-lookup"><span data-stu-id="151c5-319">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-320">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="151c5-320">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-321">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="151c5-321">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-322">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-322">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-323">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-323">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="151c5-324">あり</span><span class="sxs-lookup"><span data-stu-id="151c5-324">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="151c5-325">Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="151c5-325">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>

## <span data-ttu-id="151c5-326">関連トピック</span><span class="sxs-lookup"><span data-stu-id="151c5-326">Related topics</span></span>

[<span data-ttu-id="151c5-327">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="151c5-327">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

[<span data-ttu-id="151c5-328">App-V 5.1 の前提条件</span><span class="sxs-lookup"><span data-stu-id="151c5-328">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)
