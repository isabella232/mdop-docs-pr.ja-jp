---
title: Configuration Manager による MBAM の展開計画
description: Configuration Manager による MBAM の展開計画
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825627"
---
# <span data-ttu-id="181d6-103">Configuration Manager による MBAM の展開計画</span><span class="sxs-lookup"><span data-stu-id="181d6-103">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="181d6-104">Configuration Manager トポロジで MBAM を展開するには、20万クライアントをサポートする3つのサーバーアーキテクチャが推奨されます。</span><span class="sxs-lookup"><span data-stu-id="181d6-104">To deploy MBAM with the Configuration Manager topology, a three-server architecture, which supports 200,000 clients, is recommended.</span></span> <span data-ttu-id="181d6-105">Configuration Manager を実行するには、別のサーバーを使用し、[[はじめ](getting-started---using-mbam-with-configuration-manager.md)に] のアーキテクチャイメージに示されているように、2つのサーバーに基本的な管理機能と監視機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="181d6-105">Use a separate server to run Configuration Manager, and install the basic Administration and Monitoring features on two servers, as shown in the architecture image in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span>

**<span data-ttu-id="181d6-106">重要</span><span class="sxs-lookup"><span data-stu-id="181d6-106">Important</span></span>**  
<span data-ttu-id="181d6-107">Configuration Manager 2007 で MBAM の統合トポロジをインストールする場合、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="181d6-107">Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>



## <span data-ttu-id="181d6-108">MBAM を Configuration Manager にインストールするための展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="181d6-108">Deployment Prerequisites for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="181d6-109">MBAM を Configuration Manager にインストールする前に、次の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="181d6-109">Ensure that you have met the following prerequisites before you install MBAM with Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-110">受講</span><span class="sxs-lookup"><span data-stu-id="181d6-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="181d6-111">追加情報</span><span class="sxs-lookup"><span data-stu-id="181d6-111">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-112">Configuration Manager サーバーが Configuration Manager システムのプライマリサイトであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="181d6-112">Ensure that the Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-113">なし</span><span class="sxs-lookup"><span data-stu-id="181d6-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-114">Configuration Manager サーバーでハードウェアインベントリクライアントエージェントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="181d6-114">Enable the Hardware Inventory Client Agent on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-115">Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> サイトのハードウェアインベントリを構成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="181d6-115">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p>
<p><span data-ttu-id="181d6-116">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 構成マネージャーでハードウェアインベントリを構成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="181d6-116">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-117">使用している Configuration Manager のバージョンに応じて、目的の構成管理 (DCM) エージェントまたはコンプライアンス設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="181d6-117">Enable the Desired Configuration Management (DCM) agent or the compliance settings, depending on the version of Configuration Manager that you are using.</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-118">Configuration Manager 2007 の場合は、[ <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 必要な構成管理クライアントエージェントのプロパティを確認する] を有効にし </a> ます。</span><span class="sxs-lookup"><span data-stu-id="181d6-118">For Configuration Manager 2007, enable the see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p>
<p><span data-ttu-id="181d6-119">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 構成マネージャーでコンプライアンス設定を構成する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="181d6-119">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-120">構成マネージャーでレポートサービスポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="181d6-120">Define a reporting services point in Configuration Manager.</span></span> <span data-ttu-id="181d6-121">SQL Reporting Services の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="181d6-121">Required for SQL Reporting Services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-122">Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> SQL Reporting services 用のレポートサービスポイントを作成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="181d6-122">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p>
<p><span data-ttu-id="181d6-123">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 構成マネージャーでレポートを作成するための前提条件」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="181d6-123">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> <span data-ttu-id="181d6-124">Configuration Manager でサポートされているバージョン</span><span class="sxs-lookup"><span data-stu-id="181d6-124">Configuration Manager Supported Versions</span></span>


<span data-ttu-id="181d6-125">MBAM は次のバージョンの Configuration Manager をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="181d6-125">MBAM supports the following versions of Configuration Manager:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-126">サポートされているバージョン</span><span class="sxs-lookup"><span data-stu-id="181d6-126">Supported version</span></span></th>
<th align="left"><span data-ttu-id="181d6-127">Service pack</span><span class="sxs-lookup"><span data-stu-id="181d6-127">Service pack</span></span></th>
<th align="left"><span data-ttu-id="181d6-128">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="181d6-128">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-129">Microsoft System Center Configuration Manager 2007 R2</span><span class="sxs-lookup"><span data-stu-id="181d6-129">Microsoft System Center Configuration Manager 2007 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-130">SP1 以降</span><span class="sxs-lookup"><span data-stu-id="181d6-130">SP1 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-131">64 ビット</span><span class="sxs-lookup"><span data-stu-id="181d6-131">64-bit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="181d6-132">注</span><span class="sxs-lookup"><span data-stu-id="181d6-132">Note</span></span></strong><br/><p><span data-ttu-id="181d6-133">Configuration Manager 2007 は32ビットですが、64ビット MBAM ソフトウェアと一致させるためには、64ビットのオペレーティングシステムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="181d6-133">Although Configuration Manager 2007 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-134">Microsoft System Center 2012 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="181d6-134">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-135">SP1</span><span class="sxs-lookup"><span data-stu-id="181d6-135">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-136">64 ビット</span><span class="sxs-lookup"><span data-stu-id="181d6-136">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="181d6-137">Configuration Manager サーバーでサポートされている構成の一覧については、使用している Configuration Manager のバージョンに対応した web ページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="181d6-137">For a list of supported configurations for the Configuration Manager Server, see the appropriate webpage for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="181d6-138">MBAM には、Configuration Manager サーバーに関する追加のシステム要件はありません。</span><span class="sxs-lookup"><span data-stu-id="181d6-138">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> <span data-ttu-id="181d6-139">MBAM と SQL Server のシステム要件</span><span class="sxs-lookup"><span data-stu-id="181d6-139">MBAM and SQL Server System Requirements</span></span>


<span data-ttu-id="181d6-140">MBAM サーバーおよび Configuration Manager トポロジの SQL Server でサポートされる構成とシステム要件は、スタンドアロントポロジの場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="181d6-140">The supported configurations and system requirements for the MBAM servers and SQL Server for the Configuration Manager topology are the same as those for the Stand-alone topology.</span></span> <span data-ttu-id="181d6-141">単体システム要件については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="181d6-141">For the Stand-alone system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="181d6-142">MBAM サーバーと SQL Server プロセッサ、RAM、および Configuration Manager のトポロジに必要なディスク容量の要件については、次のセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="181d6-142">For the MBAM Server and SQL Server processor, RAM, and disk space requirements for the Configuration Manager topology, see the following sections.</span></span>

## <span data-ttu-id="181d6-143">MBAM サーバプロセッサ、RAM、および MBAM のディスク容量要件</span><span class="sxs-lookup"><span data-stu-id="181d6-143">MBAM Server Processor, RAM, and Disk Space Requirements for MBAM</span></span>


<span data-ttu-id="181d6-144">次の表は、Configuration Manager の統合トポロジを使用している場合に、MBAM サーバーのサーバープロセッサ、RAM、およびディスク領域の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="181d6-144">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-145">ハードウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="181d6-145">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="181d6-146">最小要件</span><span class="sxs-lookup"><span data-stu-id="181d6-146">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="181d6-147">推奨要件</span><span class="sxs-lookup"><span data-stu-id="181d6-147">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-148">処理者</span><span class="sxs-lookup"><span data-stu-id="181d6-148">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-149">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="181d6-149">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-150">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="181d6-150">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-151">RAM</span><span class="sxs-lookup"><span data-stu-id="181d6-151">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-152">4 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-152">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-153">8 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-153">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-154">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="181d6-154">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-155">1 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-155">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-156">2 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-156">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="181d6-157">SQL Server プロセッサ、RAM、ディスク容量の要件</span><span class="sxs-lookup"><span data-stu-id="181d6-157">SQL Server Processor, RAM, and Disk Space Requirements</span></span>


<span data-ttu-id="181d6-158">次の表は、構成マネージャーの統合トポロジを使用している場合の SQL Server コンピューターのサーバープロセッサ、RAM、ディスク容量の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="181d6-158">The following table lists the server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-159">ハードウェアコンポーネント</span><span class="sxs-lookup"><span data-stu-id="181d6-159">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="181d6-160">最小要件</span><span class="sxs-lookup"><span data-stu-id="181d6-160">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="181d6-161">推奨要件</span><span class="sxs-lookup"><span data-stu-id="181d6-161">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-162">処理者</span><span class="sxs-lookup"><span data-stu-id="181d6-162">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-163">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="181d6-163">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-164">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="181d6-164">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-165">RAM</span><span class="sxs-lookup"><span data-stu-id="181d6-165">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-166">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-167">8 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-167">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-168">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="181d6-168">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-169">5 GB</span><span class="sxs-lookup"><span data-stu-id="181d6-169">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-170">5 GB 以上</span><span class="sxs-lookup"><span data-stu-id="181d6-170">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="181d6-171">MBAM サーバーをインストールするのに必要な権限</span><span class="sxs-lookup"><span data-stu-id="181d6-171">Required permissions to install the MBAM Server</span></span>


<span data-ttu-id="181d6-172">Configuration Manager を使用して MBAM をインストールするには、次の表に示されている最低限の権限を持つセキュリティロールを持つ、構成マネージャーの管理者ユーザーがいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="181d6-172">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="181d6-173">また、この表には、MBAM サーバーをインストールするために、基本的なコンピューターの管理者権限以外に必要な権限が表示されています。</span><span class="sxs-lookup"><span data-stu-id="181d6-173">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-174">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="181d6-174">Permissions</span></span></th>
<th align="left"><span data-ttu-id="181d6-175">MBAM サーバー機能</span><span class="sxs-lookup"><span data-stu-id="181d6-175">MBAM Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-176">SQL インスタンスログインサーバーロール:-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="181d6-176">SQL instance Login Server Roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="181d6-177">回復データベース-監査データベース</span><span class="sxs-lookup"><span data-stu-id="181d6-177">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-178">SQL Server Reporting Services インスタンスの権限:-フォルダーの作成-レポートの発行</span><span class="sxs-lookup"><span data-stu-id="181d6-178">SQL Server Reporting Services instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="181d6-179">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-179">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="181d6-180">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="181d6-180">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-181">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="181d6-181">Permissions</span></span></th>
<th align="left"><span data-ttu-id="181d6-182">Configuration Manager サーバー機能</span><span class="sxs-lookup"><span data-stu-id="181d6-182">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-183">Configuration Manager サイトの権限:-読み取り</span><span class="sxs-lookup"><span data-stu-id="181d6-183">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-184">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-184">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-185">Configuration Manager コレクションの権限:-作成-削除-読み取り-修正-構成アイテムの展開</span><span class="sxs-lookup"><span data-stu-id="181d6-185">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-186">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-186">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-187">Configuration Manager 構成項目の権限:-作成-削除-読み取り</span><span class="sxs-lookup"><span data-stu-id="181d6-187">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-188">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-188">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="181d6-189">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="181d6-189">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="181d6-190">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="181d6-190">Permissions</span></span></th>
<th align="left"><span data-ttu-id="181d6-191">Configuration Manager サーバー機能</span><span class="sxs-lookup"><span data-stu-id="181d6-191">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-192">Configuration Manager サイトの権限:-読み取り</span><span class="sxs-lookup"><span data-stu-id="181d6-192">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-193">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-193">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="181d6-194">Configuration Manager コレクションの権限:-作成-削除-読み取り専用リソース</span><span class="sxs-lookup"><span data-stu-id="181d6-194">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-195">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-195">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="181d6-196">Configuration Manager 構成項目の権限:-作成-削除-読み取り-配布</span><span class="sxs-lookup"><span data-stu-id="181d6-196">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-197">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="181d6-197">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="181d6-198">Configuration Manager トポロジ用の MBAM 機能の展開順序</span><span class="sxs-lookup"><span data-stu-id="181d6-198">Order of Deployment of MBAM Features for the Configuration Manager Topology</span></span>


<span data-ttu-id="181d6-199">Configuration Manager サーバーに MBAM を展開する場合は、次の順序で展開タスクを完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="181d6-199">When deploying MBAM on the Configuration Manager Server, you must complete the deployment tasks in the following order:</span></span>

1.  <span data-ttu-id="181d6-200">Configuration Manager サーバーで構成の .mof ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="181d6-200">Edit the configuration.mof file on the Configuration Manager Server.</span></span>

2.  <span data-ttu-id="181d6-201">Sms \ _def のファイル構成マネージャーサーバーを作成または編集します。</span><span class="sxs-lookup"><span data-stu-id="181d6-201">Create or edit the sms\_def.mof file Configuration Manager Server.</span></span>

3.  <span data-ttu-id="181d6-202">Configuration Manager サーバーに MBAM をインストールします。</span><span class="sxs-lookup"><span data-stu-id="181d6-202">Install MBAM on the Configuration Manager Server.</span></span>

4.  <span data-ttu-id="181d6-203">データベースサーバーに回復データベースと監査データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="181d6-203">Install the Recovery Database and the Audit Database on the Database server.</span></span>

5.  <span data-ttu-id="181d6-204">管理/監視サーバーに MBAM 機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="181d6-204">Install the MBAM features on the Administration and Monitoring Server.</span></span>

## <span data-ttu-id="181d6-205">MBAM を Configuration Manager と共にインストールするための計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="181d6-205">Planning Checklist for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="181d6-206">このチェックリストは、推奨される手順と、構成マネージャーを使用して展開を監視するために Microsoft BitLocker の管理と監視を計画する際に考慮する項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="181d6-206">This checklist outlines the recommended steps and a high-level list of items to consider when planning for an Microsoft BitLocker Administration and Monitoring deployment with Configuration Manager.</span></span> <span data-ttu-id="181d6-207">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="181d6-207">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="181d6-208">タスク</span><span class="sxs-lookup"><span data-stu-id="181d6-208">Task</span></span></th>
<th align="left"><span data-ttu-id="181d6-209">参照先</span><span class="sxs-lookup"><span data-stu-id="181d6-209">References</span></span></th>
<th align="left"><span data-ttu-id="181d6-210">備考</span><span class="sxs-lookup"><span data-stu-id="181d6-210">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="181d6-211">「はじめに」の情報を確認します。これは、Configuration Manager と MBAM の連携方法と、推奨される高レベルのアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="181d6-211">Review the getting started information, which describes how Configuration Manager works with MBAM and shows the recommended high-level architecture.</span></span></p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)"><span data-ttu-id="181d6-212">はじめに - MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="181d6-212">Getting Started - Using MBAM with Configuration Manager</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="181d6-213">展開の前提条件、サポートされている構成、必要なアクセス許可、および各機能の展開順序について説明する計画情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="181d6-213">Review the planning information, which describes the deployment prerequisites, supported configurations, required permissions, and deployment order for each feature.</span></span></p></td>
<td align="left"><p><span data-ttu-id="181d6-214">Configuration Manager による MBAM の展開計画</span><span class="sxs-lookup"><span data-stu-id="181d6-214">Planning to Deploy MBAM with Configuration Manager</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="181d6-215">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="181d6-215">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="181d6-216">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="181d6-216">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="181d6-217">必要な Active Directory ドメインサービスセキュリティグループを計画して作成し、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="181d6-217">Plan for and create necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="181d6-218">MBAM 2.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="181d6-218">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="181d6-219">MBAM クライアント展開の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="181d6-219">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="181d6-220">MBAM 2.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="181d6-220">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="181d6-221">関連トピック</span><span class="sxs-lookup"><span data-stu-id="181d6-221">Related topics</span></span>


[<span data-ttu-id="181d6-222">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="181d6-222">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)









