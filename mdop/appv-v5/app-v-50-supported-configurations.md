---
title: App-V 5.0 でサポートされる構成
description: App-V 5.0 でサポートされる構成
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814787"
---
# <span data-ttu-id="9f8ca-103">App-V 5.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="9f8ca-103">App-V 5.0 Supported Configurations</span></span>


<span data-ttu-id="9f8ca-104">このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.0 をインストールして実行するために必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-104">This topic specifies the requirements that are necessary to install and run Microsoft Application Virtualization (App-V) 5.0 in your environment.</span></span>

**<span data-ttu-id="9f8ca-105">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-105">Important</span></span>**  
<span data-ttu-id="9f8ca-106">**この記事でサポートされている構成は、app-v 5.0 にのみ適用さ**れます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-106">**The supported configurations in this article apply only to App-V 5.0**.</span></span> <span data-ttu-id="9f8ca-107">App-v 5.0 Service Pack に適用される構成については、次の web ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-107">For supported configurations that apply to App-V 5.0 Service Packs, see the following web pages:</span></span>

-   [<span data-ttu-id="9f8ca-108">App-V 5.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="9f8ca-108">What's new in App-V 5.0 SP1</span></span>](whats-new-in-app-v-50-sp1.md)

-   [<span data-ttu-id="9f8ca-109">App-V 5.0 SP2 について</span><span class="sxs-lookup"><span data-stu-id="9f8ca-109">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

-   [<span data-ttu-id="9f8ca-110">App-V 5.0 SP3 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="9f8ca-110">App-V 5.0 SP3 Supported Configurations</span></span>](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> <span data-ttu-id="9f8ca-111">App-v 5.0 server のシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-111">App-V 5.0 server system requirements</span></span>


**<span data-ttu-id="9f8ca-112">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-112">Important</span></span>**  
<span data-ttu-id="9f8ca-113">App-v 5.0 サーバーでは、次のシナリオはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-113">The App-V 5.0 server does not support the following scenarios:</span></span>



-   <span data-ttu-id="9f8ca-114">Microsoft Windows Server Core を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-114">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="9f8ca-115">以前のバージョンの App-v 5.0 サーバーコンポーネントを実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-115">Deployment to a computer that runs a previous version of App-V 5.0 server components.</span></span>

    **<span data-ttu-id="9f8ca-116">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-116">Note</span></span>**  
    <span data-ttu-id="9f8ca-117">App-v 5.0 をインストールするには、アプリ-V 4.5 ライトストリーミングサーバー (LWS) サーバーのみを使用します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-117">You can install App-V 5.0 side-by-side with the App-V 4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="9f8ca-118">App-v 5.0 アプリケーションの仮想化管理サービス (HWS) サーバー4.5 とのアプリの展開は、サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-118">Deployment of App-V 5.0 side-by-side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>



-   <span data-ttu-id="9f8ca-119">Microsoft SQL Server Express edition を実行しているコンピューターへの展開。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-119">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="9f8ca-120">管理サーバーデータベースまたはレポートデータベースのリモート展開。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-120">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="9f8ca-121">データベースのインストールを成功させるには、インストーラーを Microsoft SQL を実行しているコンピューター上で直接実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-121">The installer must be run directly on the computer running Microsoft SQL for the database installation to succeed.</span></span>

-   <span data-ttu-id="9f8ca-122">ドメインコントローラーへの展開。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-122">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="9f8ca-123">短いパスはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-123">Short paths are not supported.</span></span> <span data-ttu-id="9f8ca-124">短いパスの使用を計画している場合は、新しいボリュームを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-124">If you plan to use a short path you must create a new volume.</span></span>

### <span data-ttu-id="9f8ca-125">管理サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-125">Management Server operating system requirements</span></span>

<span data-ttu-id="9f8ca-126">次の表は、App-v 5.0 management server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-126">The following table lists the operating systems that are supported for the App-V 5.0 management server installation.</span></span>

**<span data-ttu-id="9f8ca-127">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-127">Note</span></span>**  
<span data-ttu-id="9f8ca-128">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-128">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-129">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-129">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-130">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-130">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-131">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f8ca-131">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-132">エディション</span><span class="sxs-lookup"><span data-stu-id="9f8ca-132">Edition</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-133">Service pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-133">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-134">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-134">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-135">Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-135">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-136">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-136">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-137">SP1 以降</span><span class="sxs-lookup"><span data-stu-id="9f8ca-137">SP1 and higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-138">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-138">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-139">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-139">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-140">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-140">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-141">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-141">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-142">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-142">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-143">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-143">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="9f8ca-144">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-144">Important</span></span>**  
<span data-ttu-id="9f8ca-145">リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-145">Deployment of the management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>



### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="9f8ca-146">管理サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-146">Management Server hardware requirements</span></span>

-   <span data-ttu-id="9f8ca-147">プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-147">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="9f8ca-148">RAM: 1 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-148">RAM— 1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="9f8ca-149">ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-149">Disk space—200 MB available hard disk space, not including the content directory.</span></span>

### <span data-ttu-id="9f8ca-150">発行サーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-150">Publishing Server operating system requirements</span></span>

<span data-ttu-id="9f8ca-151">次の表は、App-v 5.0 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-151">The following table lists the operating systems that are supported for the App-V 5.0 publishing server installation.</span></span>

**<span data-ttu-id="9f8ca-152">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-152">Note</span></span>**  
<span data-ttu-id="9f8ca-153">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-153">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-154">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-154">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-155">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-155">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-156">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f8ca-156">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-157">エディション</span><span class="sxs-lookup"><span data-stu-id="9f8ca-157">Edition</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-158">Service pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-158">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-159">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-159">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-160">Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-160">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-161">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-161">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-162">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-162">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-163">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-163">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-164">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-164">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-165">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-165">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-166">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-166">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-167">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-167">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="9f8ca-168">発行サーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-168">Publishing Server hardware requirements</span></span>

-   <span data-ttu-id="9f8ca-169">プロセッサー (1.4 GHz 以上)。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-169">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="9f8ca-170">64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-170">64-bit (x64) processor</span></span>

-   <span data-ttu-id="9f8ca-171">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-171">RAM— 2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="9f8ca-172">ディスク領域: 200 MB のハードディスク領域。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-172">Disk space—200 MB available hard disk space.</span></span> <span data-ttu-id="9f8ca-173">コンテンツディレクトリを含まない</span><span class="sxs-lookup"><span data-stu-id="9f8ca-173">not including content directory</span></span>

### <span data-ttu-id="9f8ca-174">レポートサーバーのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-174">Reporting Server operating system requirements</span></span>

<span data-ttu-id="9f8ca-175">次の表は、App-v 5.0 reporting server のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-175">The following table lists the operating systems that are supported for the App-V 5.0 reporting server installation.</span></span>

**<span data-ttu-id="9f8ca-176">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-176">Note</span></span>**  
<span data-ttu-id="9f8ca-177">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-177">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-178">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-178">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-179">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-179">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-180">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f8ca-180">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-181">エディション</span><span class="sxs-lookup"><span data-stu-id="9f8ca-181">Edition</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-182">Service Pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-182">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-183">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-183">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-184">Microsoft Windows Server 2008 (標準、エンタープライズ、データセンター、または Web サーバー)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-184">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-185">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-185">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-186">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-186">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-187">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-187">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-188">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-189">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-189">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-190">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-190">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-191">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-191">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="9f8ca-192">レポートサーバーのハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-192">Reporting Server hardware requirements</span></span>

-   <span data-ttu-id="9f8ca-193">プロセッサー (1.4 GHz 以上)。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-193">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="9f8ca-194">64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-194">64-bit (x64) processor</span></span>

-   <span data-ttu-id="9f8ca-195">RAM: 2 GB RAM (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-195">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="9f8ca-196">ディスク領域: 200 MB のハードディスク空き容量</span><span class="sxs-lookup"><span data-stu-id="9f8ca-196">Disk space—200 MB available hard disk space</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="9f8ca-197">SQL Server データベースの要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-197">SQL Server database requirements</span></span>

<span data-ttu-id="9f8ca-198">次の表は、App-v 5.0 データベースとサーバーのインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-198">The following table lists the SQL Server versions that are supported for the App-V 5.0 database and server installation.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-199">App-v 5.0 サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="9f8ca-199">App-V 5.0 server type</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-200">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="9f8ca-200">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-201">エディション</span><span class="sxs-lookup"><span data-stu-id="9f8ca-201">Edition</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-203">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-204">管理/レポート作成</span><span class="sxs-lookup"><span data-stu-id="9f8ca-204">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-205">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9f8ca-205">Microsoft SQL Server 2008</span></span></p>
<p><span data-ttu-id="9f8ca-206">(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</span><span class="sxs-lookup"><span data-stu-id="9f8ca-206">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-207">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-208">管理/レポート作成</span><span class="sxs-lookup"><span data-stu-id="9f8ca-208">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-209">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="9f8ca-209">Microsoft SQL Server 2008</span></span> </p>
<p><span data-ttu-id="9f8ca-210">(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</span><span class="sxs-lookup"><span data-stu-id="9f8ca-210">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-211">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-211">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-212">SP2</span><span class="sxs-lookup"><span data-stu-id="9f8ca-212">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-213">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-213">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-214">管理/レポート作成</span><span class="sxs-lookup"><span data-stu-id="9f8ca-214">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-215">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="9f8ca-215">Microsoft SQL Server 2012</span></span></p>
<p><span data-ttu-id="9f8ca-216">(標準、Enterprise、Datacenter、または Developer エディション: <strong>データベースエンジンサービス </strong> )</span><span class="sxs-lookup"><span data-stu-id="9f8ca-216">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-217">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-217">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> <span data-ttu-id="9f8ca-218">App-v 5.0 クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-218">App-V 5.0 client system requirements</span></span>


<span data-ttu-id="9f8ca-219">次の表は、App-v 5.0 クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-219">The following table lists the operating systems that are supported for the App-V 5.0 client installation.</span></span>

**<span data-ttu-id="9f8ca-220">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-220">Note</span></span>**  
<span data-ttu-id="9f8ca-221">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-221">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-222">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-222">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-223">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-223">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-224">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f8ca-224">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-225">Service pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-225">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-226">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-226">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-227">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="9f8ca-227">Microsoft Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-228">SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-228">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-229">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-229">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-230">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="9f8ca-230">Microsoft Windows 8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-231">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-231">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="9f8ca-232">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-232">Important</span></span></strong><br/><p><span data-ttu-id="9f8ca-233">Windows 8.1 は、app-v 5.0 SP2 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-233">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="9f8ca-234">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-234">Windows 8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-235">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-235">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="9f8ca-236">次のような App-v クライアントインストールシナリオはサポートされていません。記載されている場合を除きます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-236">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="9f8ca-237">Windows Server を実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="9f8ca-237">Computers that run Windows Server</span></span>

-   <span data-ttu-id="9f8ca-238">App-v 4.6 SP1 またはそれ以前のバージョンを実行しているコンピューター</span><span class="sxs-lookup"><span data-stu-id="9f8ca-238">Computers that run App-V 4.6 SP1 or earlier versions</span></span>

-   <span data-ttu-id="9f8ca-239">App-v 5.0 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-239">The App-V 5.0 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="client-hardware-requirements-"></a><span data-ttu-id="9f8ca-240">クライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-240">Client hardware requirements</span></span>

<span data-ttu-id="9f8ca-241">次の一覧は、App-v 5.0 クライアントのインストールでサポートされているハードウェア構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-241">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="9f8ca-242">プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-242">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="9f8ca-243">RAM: 1 GB (32 ビット) または 2 GB (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-243">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="9f8ca-244">ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-244">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> <span data-ttu-id="9f8ca-245">App-v 5.0 リモートデスクトップクライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-245">App-V 5.0 Remote Desktop client system requirements</span></span>


<span data-ttu-id="9f8ca-246">次の表は、App-v 5.0 リモートデスクトップクライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-246">The following table lists the operating systems that are supported for App-V 5.0 Remote Desktop client installation.</span></span>

**<span data-ttu-id="9f8ca-247">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-247">Note</span></span>**  
<span data-ttu-id="9f8ca-248">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-248">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-249">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-249">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-250">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-250">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<span data-ttu-id="9f8ca-251">オペレーティングシステムエディションの Service pack Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9f8ca-251">Operating system Edition Service pack Microsoft Windows Server 2008</span></span>

<span data-ttu-id="9f8ca-252">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-252">R2</span></span>

<span data-ttu-id="9f8ca-253">SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-253">SP1</span></span>

<span data-ttu-id="9f8ca-254">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9f8ca-254">Microsoft Windows Server 2012</span></span>

**<span data-ttu-id="9f8ca-255">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-255">Important</span></span>**  
<span data-ttu-id="9f8ca-256">Windows Server 2012 R2 は、App-v 5.0 SP2 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-256">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span>



<span data-ttu-id="9f8ca-257">Microsoft Windows Server 2012 (標準、データセンター)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-257">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span>

<span data-ttu-id="9f8ca-258">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-258">R2</span></span>

<span data-ttu-id="9f8ca-259">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-259">64-bit</span></span>



### <a href="" id="remote-desktop-client-hardware-requirements-"></a><span data-ttu-id="9f8ca-260">リモートデスクトップクライアントハードウェア要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-260">Remote Desktop client hardware requirements</span></span>

<span data-ttu-id="9f8ca-261">次の一覧は、App-v 5.0 クライアントのインストールでサポートされているハードウェア構成を示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-261">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="9f8ca-262">プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-262">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="9f8ca-263">RAM: 1 GB (32 ビット) または 2 GB (64 ビット)</span><span class="sxs-lookup"><span data-stu-id="9f8ca-263">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="9f8ca-264">ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-264">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> <span data-ttu-id="9f8ca-265">App-v 5.0 Sequencer システム要件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-265">App-V 5.0 Sequencer system requirements</span></span>


<span data-ttu-id="9f8ca-266">次の表は、App-v 5.0 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-266">The following table lists the operating systems that are supported for App-V 5.0 Sequencer installation.</span></span>

**<span data-ttu-id="9f8ca-267">注</span><span class="sxs-lookup"><span data-stu-id="9f8ca-267">Note</span></span>**  
<span data-ttu-id="9f8ca-268">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-268">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="9f8ca-269">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-269">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="9f8ca-270">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-270">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-271">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9f8ca-271">Operating system</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-272">エディション</span><span class="sxs-lookup"><span data-stu-id="9f8ca-272">Edition</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-273">Service pack</span><span class="sxs-lookup"><span data-stu-id="9f8ca-273">Service pack</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-274">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="9f8ca-274">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-275">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="9f8ca-275">Microsoft Windows 7</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-276">SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-276">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-277">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-277">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-278">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="9f8ca-278">Microsoft Windows 8</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-279">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-279">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="9f8ca-280">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-280">Important</span></span></strong><br/><p><span data-ttu-id="9f8ca-281">Windows 8.1 は、app-v 5.0 SP2 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-281">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="9f8ca-282">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-282">Windows 8.1</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-283">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-283">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-284">Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="9f8ca-284">Microsoft Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-285">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-285">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-286">SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-286">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-287">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-287">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-288">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9f8ca-288">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-289">32 ビットと 64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-289">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong><span data-ttu-id="9f8ca-290">重要</span><span class="sxs-lookup"><span data-stu-id="9f8ca-290">Important</span></span></strong><br/><p><span data-ttu-id="9f8ca-291">Windows Server 2012 R2 は、App-v 5.0 SP2 でのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-291">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="9f8ca-292">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="9f8ca-292">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="9f8ca-293">もたらし</span><span class="sxs-lookup"><span data-stu-id="9f8ca-293">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="9f8ca-294">64 ビット</span><span class="sxs-lookup"><span data-stu-id="9f8ca-294">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="9f8ca-295">サポートされている System Center Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="9f8ca-295">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="9f8ca-296">Microsoft System Center 2012 Configuration Manager または System Center 2012 R2 構成マネージャーを使用して、App-v 仮想アプリケーション、レポート、その他の機能を管理できます。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-296">You can use Microsoft System Center 2012 Configuration Manager or System Center 2012 R2 Configuration Manager to manage App-V virtual applications, reporting, and other functions.</span></span> <span data-ttu-id="9f8ca-297">次の表は、各バージョンの App-v でサポートされている Configuration Manager のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-297">The following table lists the supported versions of Configuration Manager for each applicable version of App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9f8ca-298">サポートされている Configuration Manager バージョン</span><span class="sxs-lookup"><span data-stu-id="9f8ca-298">Supported Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="9f8ca-299">App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="9f8ca-299">App-V version</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9f8ca-300">Microsoft System Center 2012 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="9f8ca-300">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9f8ca-301">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="9f8ca-301">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="9f8ca-302">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-302">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="9f8ca-303">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="9f8ca-303">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9f8ca-304">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9f8ca-304">System Center 2012 R2 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9f8ca-305">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="9f8ca-305">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="9f8ca-306">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="9f8ca-306">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="9f8ca-307">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="9f8ca-307">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="9f8ca-308">Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9f8ca-308">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="9f8ca-309">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9f8ca-309">Related topics</span></span>


[<span data-ttu-id="9f8ca-310">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="9f8ca-310">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="9f8ca-311">App-V 5.0 の前提条件</span><span class="sxs-lookup"><span data-stu-id="9f8ca-311">App-V 5.0 Prerequisites</span></span>](app-v-50-prerequisites.md)









