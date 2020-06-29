---
title: Configuration Manager 統合機能の前提条件
description: Configuration Manager 統合機能の前提条件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825014"
---
# <span data-ttu-id="ef52c-103">Configuration Manager 統合機能の前提条件</span><span class="sxs-lookup"><span data-stu-id="ef52c-103">Prerequisites for the Configuration Manager Integration Feature</span></span>


<span data-ttu-id="ef52c-104">System Center Configuration Manager の統合トポロジで MBAM を展開する場合は、「 [mbam 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」で説明されているように、3サーバーアーキテクチャをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ef52c-104">If you deploy MBAM with the System Center Configuration Manager Integration topology, we recommend a three-server architecture, as described in [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span> <span data-ttu-id="ef52c-105">このアーキテクチャでは、50万クライアントコンピューターをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="ef52c-105">This architecture can support 500,000 client computers.</span></span>

**<span data-ttu-id="ef52c-106">重要</span><span class="sxs-lookup"><span data-stu-id="ef52c-106">Important</span></span>**  
<span data-ttu-id="ef52c-107">Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ef52c-107">Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>



## <span data-ttu-id="ef52c-108">Configuration Manager の統合機能の一般的な前提条件</span><span class="sxs-lookup"><span data-stu-id="ef52c-108">General prerequisites for the Configuration Manager Integration feature</span></span>


<span data-ttu-id="ef52c-109">Configuration Manager を使用して MBAM をインストールする場合、スタンドアロントポロジの前提条件に加えて、次の追加の前提条件が必要になります。</span><span class="sxs-lookup"><span data-stu-id="ef52c-109">When you install MBAM with Configuration Manager, the following additional prerequisites are required in addition to the prerequisites for the Stand-alone topology.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef52c-110">受講</span><span class="sxs-lookup"><span data-stu-id="ef52c-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="ef52c-111">追加情報</span><span class="sxs-lookup"><span data-stu-id="ef52c-111">Additional information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-112">Configuration Manager サーバーは、Configuration Manager システムのプライマリサイトです。</span><span class="sxs-lookup"><span data-stu-id="ef52c-112">The Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-113">なし</span><span class="sxs-lookup"><span data-stu-id="ef52c-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef52c-114">ハードウェアインベントリクライアントエージェントは、Configuration Manager サーバー上にあります。</span><span class="sxs-lookup"><span data-stu-id="ef52c-114">The Hardware Inventory Client Agent is on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-115">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 構成マネージャーでハードウェアインベントリを構成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-115">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ef52c-116">Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> サイトのハードウェアインベントリを構成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-116">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-117">使用している Configuration Manager のバージョンに応じて、次のいずれかが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ef52c-117">One of the following is enabled, depending on the version of Configuration Manager that you are using:</span></span></p>
<ul>
<li><p><span data-ttu-id="ef52c-118">コンプライアンス設定-(System Center 2012 構成マネージャー)</span><span class="sxs-lookup"><span data-stu-id="ef52c-118">Compliance Settings - (System Center 2012 Configuration Manager)</span></span></p></li>
<li><p><span data-ttu-id="ef52c-119">必要な構成管理 (DCM) クライアントエージェント– (構成マネージャー 2007)</span><span class="sxs-lookup"><span data-stu-id="ef52c-119">Desired Configuration Management (DCM) Client Agent – (Configuration Manager 2007)</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="ef52c-120">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 構成マネージャーでコンプライアンス設定を構成する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-120">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ef52c-121">Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> Desired Configuration Management Client Agent プロパティ」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-121">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef52c-122">Reporting services ポイントは、構成マネージャーで定義されます。</span><span class="sxs-lookup"><span data-stu-id="ef52c-122">A reporting services point is defined in Configuration Manager.</span></span> <span data-ttu-id="ef52c-123">SQL Server Reporting Services (SSRS) の場合は必須です。</span><span class="sxs-lookup"><span data-stu-id="ef52c-123">Required for SQL Server Reporting Services (SSRS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-124">System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 構成マネージャーでレポートを作成するための前提条件」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-124">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p>
<p><span data-ttu-id="ef52c-125">Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> SQL Reporting services 用のレポートサービスポイントを作成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef52c-125">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-126">Configuration Manager 2007 には Microsoft .NET Framework 2.0 が必要です</span><span class="sxs-lookup"><span data-stu-id="ef52c-126">Configuration Manager 2007 requires Microsoft .NET Framework 2.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-127">Configuration Manager 2007 の必要な構成管理 (DCM) クライアントエージェントは、コンプライアンスを報告するために .NET Framework 2.0 を必要とします。</span><span class="sxs-lookup"><span data-stu-id="ef52c-127">The Desired Configuration Management (DCM) Client Agent in Configuration Manager 2007 requires .NET Framework 2.0 to report compliance.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ef52c-128">注</span><span class="sxs-lookup"><span data-stu-id="ef52c-128">Note</span></span></strong><br/><p><span data-ttu-id="ef52c-129">.NET Framework 3.5 をインストールすると、.NET Framework 2.0 が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ef52c-129">Installing .NET Framework 3.5 automatically installs .NET Framework 2.0.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ef52c-130">Configuration Manager で MBAM をインストールするのに必要な権限</span><span class="sxs-lookup"><span data-stu-id="ef52c-130">Required permissions to install MBAM with Configuration Manager</span></span>


<span data-ttu-id="ef52c-131">Configuration Manager を使用して MBAM をインストールするには、次の表に示されている最低限の権限を持つセキュリティロールを持つ、構成マネージャーの管理者ユーザーがいる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef52c-131">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="ef52c-132">また、この表には、MBAM サーバーをインストールするために、基本的なコンピューターの管理者権限以外に必要な権限が表示されています。</span><span class="sxs-lookup"><span data-stu-id="ef52c-132">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

**<span data-ttu-id="ef52c-133">次の表のアクセス許可は、両方の Configuration Manager のバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="ef52c-133">The permissions in the following table apply to both versions of Configuration Manager.</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef52c-134">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ef52c-134">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ef52c-135">MBAM サーバー機能</span><span class="sxs-lookup"><span data-stu-id="ef52c-135">MBAM Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-136">SQL Server インスタンスのログインサーバーの役割:-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="ef52c-136">SQL Server instance login server roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="ef52c-137">回復データベース-監査データベース</span><span class="sxs-lookup"><span data-stu-id="ef52c-137">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef52c-138">SSRS インスタンスの権限:-フォルダーの作成-レポートの発行</span><span class="sxs-lookup"><span data-stu-id="ef52c-138">SSRS instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="ef52c-139">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-139">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ef52c-140">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="ef52c-140">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef52c-141">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ef52c-141">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ef52c-142">Configuration Manager サーバー機能</span><span class="sxs-lookup"><span data-stu-id="ef52c-142">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-143">Configuration Manager サイトの権限:-読み取り</span><span class="sxs-lookup"><span data-stu-id="ef52c-143">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-144">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-144">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef52c-145">Configuration Manager コレクションの権限:-作成-削除-読み取り-修正-構成アイテムの展開</span><span class="sxs-lookup"><span data-stu-id="ef52c-145">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-146">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-146">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-147">Configuration Manager 構成項目の権限:-作成-削除-読み取り</span><span class="sxs-lookup"><span data-stu-id="ef52c-147">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-148">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-148">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="ef52c-149">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="ef52c-149">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef52c-150">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="ef52c-150">Permissions</span></span></th>
<th align="left"><span data-ttu-id="ef52c-151">Configuration Manager サーバー機能</span><span class="sxs-lookup"><span data-stu-id="ef52c-151">Configuration Manager Server feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-152">Configuration Manager サイトの権限:-読み取り</span><span class="sxs-lookup"><span data-stu-id="ef52c-152">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-153">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-153">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef52c-154">Configuration Manager コレクションの権限:-作成-削除-読み取り専用リソース</span><span class="sxs-lookup"><span data-stu-id="ef52c-154">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-155">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-155">System Center Configuration Manager Integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef52c-156">Configuration Manager 構成項目の権限:-作成-削除-読み取り-配布</span><span class="sxs-lookup"><span data-stu-id="ef52c-156">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef52c-157">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="ef52c-157">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="ef52c-158">.Mof ファイルに必要な変更</span><span class="sxs-lookup"><span data-stu-id="ef52c-158">Required changes for the .mof files</span></span>


<span data-ttu-id="ef52c-159">MBAM Configuration manager のレポートを通じて、クライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするためには、System Center 2012 構成マネージャーおよび Microsoft System Center Configuration Manager 2007 用の構成の .mof ファイルと Sms \ _def ファイルを編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ef52c-159">To enable the client computers to report BitLocker compliance details through the MBAM Configuration Manager reports, you have to edit the Configuration.mof file and Sms\_def.mof file for System Center 2012 Configuration Manager and Microsoft System Center Configuration Manager 2007.</span></span> <span data-ttu-id="ef52c-160">手順については、「Mbam 2.5 Server の前提条件」を参照してください。これ[は、Configuration Manager の統合トポロジにのみ適用](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)されます。</span><span class="sxs-lookup"><span data-stu-id="ef52c-160">For instructions, see [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="ef52c-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ef52c-161">Related topics</span></span>


[<span data-ttu-id="ef52c-162">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="ef52c-162">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[<span data-ttu-id="ef52c-163">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="ef52c-163">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span>](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## <span data-ttu-id="ef52c-164">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="ef52c-164">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ef52c-165">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="ef52c-165">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ef52c-166">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="ef52c-166">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





