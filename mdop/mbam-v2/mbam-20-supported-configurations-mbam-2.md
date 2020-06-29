---
title: MBAM 2.0 がサポートされる構成
description: MBAM 2.0 がサポートされる構成
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823907"
---
# <span data-ttu-id="f6ee1-103">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="f6ee1-103">MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="f6ee1-104">このトピックでは、スタンドアロントポロジを使用して、お客様の環境で Microsoft BitLocker 管理と監視 (MBAM) 2.0 をインストールして実行するための要件を示します。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-104">This topic specifies the requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in your environment by using the Stand-alone topology.</span></span> <span data-ttu-id="f6ee1-105">以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-105">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="f6ee1-106">Configuration Manager トポロジを使用して MBAM 2.0 をインストールし、システム要件の一覧を確認したい場合は、「 [Configuration manager で MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-106">If you plan to install MBAM 2.0 by using the Configuration Manager topology and want to review a list of the system requirements, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="f6ee1-107">運用環境で MBAM を実行するために推奨される構成は、スケーラビリティの要件に応じて、2つのサーバーを使用することです。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-107">The recommended configuration for running MBAM in a production environment is with two servers, depending on your scalability requirements.</span></span> <span data-ttu-id="f6ee1-108">この構成では、最大 20万 MBAM クライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-108">This configuration supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="f6ee1-109">スタンドアロンの MBAM サーバーインフラストラクチャの画像と説明については、「 [mbam 2.0 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-20-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-109">For an image and descriptions of the Stand-alone MBAM server infrastructure, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="f6ee1-110">**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-110">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="f6ee1-111">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-111">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="f6ee1-112">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-112">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="f6ee1-113">MBAM サーバーシステム要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-113">MBAM Server System Requirements</span></span>


### <span data-ttu-id="f6ee1-114">サーバーオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-114">Server Operating System Requirements</span></span>

<span data-ttu-id="f6ee1-115">次の表は、Microsoft BitLocker の管理と監視のサーバーインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-115">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-116">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="f6ee1-116">Operating system</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-117">エディション</span><span class="sxs-lookup"><span data-stu-id="f6ee1-117">Edition</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-118">Service pack</span><span class="sxs-lookup"><span data-stu-id="f6ee1-118">Service pack</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-119">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6ee1-119">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-120">WindowsServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="f6ee1-120">WindowsServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-121">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-121">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-122">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-122">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-123">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-123">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-124">WindowsServer2012</span><span class="sxs-lookup"><span data-stu-id="f6ee1-124">WindowsServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-125">Standard Edition または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-125">Standard or Datacenter Edition</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="f6ee1-126">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-126">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f6ee1-127">**注** MBAM サービス、レポート、データベースのドメインコントローラーコンピューターへのインストールはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-127">**Note** There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a><span data-ttu-id="f6ee1-128">サーバープロセッサ、RAM、ディスク容量の要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-128">Server Processor, RAM, and Disk Space Requirements</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-129">ハードウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6ee1-129">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-130">最小要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-130">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-131">推奨要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-131">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-132">処理者</span><span class="sxs-lookup"><span data-stu-id="f6ee1-132">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-133">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="f6ee1-133">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-134">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="f6ee1-134">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-135">RAM</span><span class="sxs-lookup"><span data-stu-id="f6ee1-135">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-136">8 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-136">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-137">12 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-137">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-138">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="f6ee1-138">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-139">1 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-139">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-140">2 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-140">2 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="f6ee1-141">SQLServer データベースの要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-141">SQLServer Database Requirements</span></span>

<span data-ttu-id="f6ee1-142">次の表に、管理および監視サーバー機能のインストールでサポートされている SQLServer バージョンの一覧を示します。これには、回復データベース、コンプライアンスと監査データベース、コンプライアンスおよび監査レポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-142">The following table lists the SQLServer versions that are supported for the Administration and Monitoring Server feature installation, which includes the Recovery Database, Compliance and Audit Database, and Compliance and Audit Reports.</span></span> <span data-ttu-id="f6ee1-143">また、データベースには、SQL Server 管理ツールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-143">The databases additionally require the installation of SQL Server Management Tools.</span></span>

<span data-ttu-id="f6ee1-144">**注** MBAM は、SQL クラスタリング、ミラーリング、または可用性グループをネイティブでサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-144">**Note** MBAM does not natively support SQL clustering, mirroring, or Availability Groups.</span></span> <span data-ttu-id="f6ee1-145">データベースをインストールするには、スタンドアロンの SQL Server で MBAM サーバーインストールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-145">To install the databases, you must run the MBAM Server installation on a stand-alone SQL server.</span></span>

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-146">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="f6ee1-146">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-147">エディション</span><span class="sxs-lookup"><span data-stu-id="f6ee1-147">Edition</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-148">Service pack</span><span class="sxs-lookup"><span data-stu-id="f6ee1-148">Service pack</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-149">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6ee1-149">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-150">MicrosoftSQLServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="f6ee1-150">MicrosoftSQLServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-151">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-151">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-152">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-152">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-153">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-153">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-154">MicrosoftSQLServer2012</span><span class="sxs-lookup"><span data-stu-id="f6ee1-154">MicrosoftSQLServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-155">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-155">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-156">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-156">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-157">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-157">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-158">ハードウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="f6ee1-158">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-159">最小要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-159">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-160">推奨要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-160">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-161">処理者</span><span class="sxs-lookup"><span data-stu-id="f6ee1-161">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-162">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="f6ee1-162">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-163">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="f6ee1-163">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-164">RAM</span><span class="sxs-lookup"><span data-stu-id="f6ee1-164">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-165">8 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-165">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-166">12 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-166">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-167">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="f6ee1-167">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-168">5 GB</span><span class="sxs-lookup"><span data-stu-id="f6ee1-168">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-169">5 GB 以上</span><span class="sxs-lookup"><span data-stu-id="f6ee1-169">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="f6ee1-170">MBAM クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-170">MBAM Client System Requirements</span></span>


### <span data-ttu-id="f6ee1-171">クライアントのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-171">Client Operating System Requirements</span></span>

<span data-ttu-id="f6ee1-172">次の表は、Microsoft BitLocker の管理とクライアントのインストールの監視がサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-172">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-173">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="f6ee1-173">Operating system</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-174">エディション</span><span class="sxs-lookup"><span data-stu-id="f6ee1-174">Edition</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-175">Service pack</span><span class="sxs-lookup"><span data-stu-id="f6ee1-175">Service pack</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-176">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6ee1-176">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-177">Windows7</span><span class="sxs-lookup"><span data-stu-id="f6ee1-177">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-178">Enterprise または Ultimate Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-178">Enterprise or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-179">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-180">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-180">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-181">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f6ee1-181">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-182">Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-182">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-183">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-183">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-184">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="f6ee1-184">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-185">Windows 8 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-185">Windows 8 Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-186">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-186">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="f6ee1-187">クライアント RAM の要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-187">Client RAM Requirements</span></span>

<span data-ttu-id="f6ee1-188">Microsoft BitLocker の管理と監視クライアントインストールに固有の RAM 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-188">There are no RAM requirements that are specific to the Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="f6ee1-189">MBAM グループポリシーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-189">MBAM Group Policy System Requirements</span></span>


<span data-ttu-id="f6ee1-190">次の表は、Microsoft BitLocker 管理およびグループポリシーテンプレートのインストールがサポートされているオペレーティングシステムの一覧です。</span><span class="sxs-lookup"><span data-stu-id="f6ee1-190">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Group Policy template installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f6ee1-191">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="f6ee1-191">Operating system</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-192">エディション</span><span class="sxs-lookup"><span data-stu-id="f6ee1-192">Edition</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-193">Service pack</span><span class="sxs-lookup"><span data-stu-id="f6ee1-193">Service pack</span></span></th>
<th align="left"><span data-ttu-id="f6ee1-194">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="f6ee1-194">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-195">Windows7</span><span class="sxs-lookup"><span data-stu-id="f6ee1-195">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-196">Enterprise、または Ultimate Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-196">Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-197">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-197">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-198">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-198">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-199">Windows 8</span><span class="sxs-lookup"><span data-stu-id="f6ee1-199">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-200">Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-200">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-201">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-201">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f6ee1-202">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="f6ee1-202">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-203">標準、エンタープライズ、または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-203">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-204">SP1</span><span class="sxs-lookup"><span data-stu-id="f6ee1-204">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-205">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-205">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f6ee1-206">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f6ee1-206">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-207">Standard Edition または Datacenter Edition</span><span class="sxs-lookup"><span data-stu-id="f6ee1-207">Standard or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="f6ee1-208">64 ビット</span><span class="sxs-lookup"><span data-stu-id="f6ee1-208">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f6ee1-209">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f6ee1-209">Related topics</span></span>


[<span data-ttu-id="f6ee1-210">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="f6ee1-210">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="f6ee1-211">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="f6ee1-211">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





