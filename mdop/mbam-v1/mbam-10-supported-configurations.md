---
title: MBAM 1.0 がサポートされる構成
description: MBAM 1.0 がサポートされる構成
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825937"
---
# <span data-ttu-id="5e127-103">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="5e127-103">MBAM 1.0 Supported Configurations</span></span>


<span data-ttu-id="5e127-104">このトピックでは、お使いの環境に Microsoft BitLocker 管理と監視 (MBAM) をインストールして実行するために必要な要件を示します。</span><span class="sxs-lookup"><span data-stu-id="5e127-104">This topic specifies the necessary requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) in your environment.</span></span>

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="5e127-105">MBAM サーバーシステム要件</span><span class="sxs-lookup"><span data-stu-id="5e127-105">MBAM server system Requirements</span></span>


### <span data-ttu-id="5e127-106">サーバーオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="5e127-106">Server operating system requirements</span></span>

<span data-ttu-id="5e127-107">次の表は、Microsoft BitLocker の管理と監視のサーバーインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="5e127-107">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

**<span data-ttu-id="5e127-108">注</span><span class="sxs-lookup"><span data-stu-id="5e127-108">Note</span></span>**  
<span data-ttu-id="5e127-109">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e127-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="5e127-110">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e127-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="5e127-111">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e127-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5e127-112">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="5e127-112">Operating System</span></span></th>
<th align="left"><span data-ttu-id="5e127-113">エディション</span><span class="sxs-lookup"><span data-stu-id="5e127-113">Edition</span></span></th>
<th align="left"><span data-ttu-id="5e127-114">Service Pack</span><span class="sxs-lookup"><span data-stu-id="5e127-114">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="5e127-115">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5e127-115">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e127-116">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="5e127-116">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-117">標準、エンタープライズ、データセンター、または Web サーバー</span><span class="sxs-lookup"><span data-stu-id="5e127-117">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-118">SP2 のみ</span><span class="sxs-lookup"><span data-stu-id="5e127-118">SP2 only</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-119">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-119">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5e127-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5e127-120">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-121">標準、エンタープライズ、データセンター、または Web サーバー</span><span class="sxs-lookup"><span data-stu-id="5e127-121">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="5e127-122">64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-122">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="5e127-123">Warning</span><span class="sxs-lookup"><span data-stu-id="5e127-123">Warning</span></span>**  
<span data-ttu-id="5e127-124">MBAM サービス、レポート、データベースのドメインコントローラーコンピューターへのインストールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5e127-124">There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>



### <a href="" id="server-random-access-memory--ram--requirements-"></a><span data-ttu-id="5e127-125">サーバーランダムアクセスメモリ (RAM) 要件</span><span class="sxs-lookup"><span data-stu-id="5e127-125">Server random access memory (RAM) requirements</span></span>

<span data-ttu-id="5e127-126">MBAM サーバーのインストールに固有の RAM 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="5e127-126">There are no RAM requirements that are specific to MBAM Server installation.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="5e127-127">SQL Server データベースの要件</span><span class="sxs-lookup"><span data-stu-id="5e127-127">SQL Server Database requirements</span></span>

<span data-ttu-id="5e127-128">次の表は、MBAM サーバー機能のインストールでサポートされている SQL Server のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="5e127-128">The following table lists the SQL Server versions that are supported for the MBAM Server feature installation.</span></span>

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
<th align="left"><span data-ttu-id="5e127-129">MBAM サーバー機能</span><span class="sxs-lookup"><span data-stu-id="5e127-129">MBAM Server Feature</span></span></th>
<th align="left"><span data-ttu-id="5e127-130">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="5e127-130">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="5e127-131">エディション</span><span class="sxs-lookup"><span data-stu-id="5e127-131">Edition</span></span></th>
<th align="left"><span data-ttu-id="5e127-132">Service Pack</span><span class="sxs-lookup"><span data-stu-id="5e127-132">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="5e127-133">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5e127-133">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e127-134">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="5e127-134">Compliance and Audit Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-135">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="5e127-135">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="5e127-136">R2、Standard、Enterprise、Datacenter、または Developer Edition</span><span class="sxs-lookup"><span data-stu-id="5e127-136">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-137">SP2</span><span class="sxs-lookup"><span data-stu-id="5e127-137">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-138">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-138">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5e127-139">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="5e127-139">Recovery and Hardware Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-140">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="5e127-140">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="5e127-141">R2、Enterprise、Datacenter、または Developer Edition</span><span class="sxs-lookup"><span data-stu-id="5e127-141">R2, Enterprise, Datacenter, or Developer Edition</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5e127-142">重要</span><span class="sxs-lookup"><span data-stu-id="5e127-142">Important</span></span></strong><br/><p><span data-ttu-id="5e127-143">SQL Server Standard エディションは、MBAM 回復とハードウェアデータベースサーバー機能のインストールではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5e127-143">SQL Server Standard Editions are not supported for MBAM Recovery and Hardware Database Server feature installation.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="5e127-144">SP2</span><span class="sxs-lookup"><span data-stu-id="5e127-144">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-145">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e127-146">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="5e127-146">Compliance and Audit Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-147">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="5e127-147">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="5e127-148">R2、Standard、Enterprise、Datacenter、または Developer Edition</span><span class="sxs-lookup"><span data-stu-id="5e127-148">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-149">SP2</span><span class="sxs-lookup"><span data-stu-id="5e127-149">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-150">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-150">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="5e127-151">MBAM クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="5e127-151">MBAM Client system requirements</span></span>


### <span data-ttu-id="5e127-152">クライアントのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="5e127-152">Client operating system requirements</span></span>

<span data-ttu-id="5e127-153">次の表は、MBAM クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="5e127-153">The following table lists the operating systems that are supported for MBAM Client installation.</span></span>

**<span data-ttu-id="5e127-154">注</span><span class="sxs-lookup"><span data-stu-id="5e127-154">Note</span></span>**  
<span data-ttu-id="5e127-155">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="5e127-155">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="5e127-156">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="5e127-156">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="5e127-157">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5e127-157">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5e127-158">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="5e127-158">Operating System</span></span></th>
<th align="left"><span data-ttu-id="5e127-159">エディション</span><span class="sxs-lookup"><span data-stu-id="5e127-159">Edition</span></span></th>
<th align="left"><span data-ttu-id="5e127-160">Service Pack</span><span class="sxs-lookup"><span data-stu-id="5e127-160">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="5e127-161">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="5e127-161">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5e127-162">Windows 7</span><span class="sxs-lookup"><span data-stu-id="5e127-162">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-163">Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="5e127-163">Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-164">なし、SP1</span><span class="sxs-lookup"><span data-stu-id="5e127-164">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-165">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-165">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5e127-166">Windows 7</span><span class="sxs-lookup"><span data-stu-id="5e127-166">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-167">究極のエディション</span><span class="sxs-lookup"><span data-stu-id="5e127-167">Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-168">なし、SP1</span><span class="sxs-lookup"><span data-stu-id="5e127-168">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="5e127-169">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="5e127-169">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="5e127-170">クライアント RAM の要件</span><span class="sxs-lookup"><span data-stu-id="5e127-170">Client RAM requirements</span></span>

<span data-ttu-id="5e127-171">MBAM クライアントのインストールに固有の RAM 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="5e127-171">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <span data-ttu-id="5e127-172">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e127-172">Related topics</span></span>


[<span data-ttu-id="5e127-173">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="5e127-173">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="5e127-174">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="5e127-174">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)









