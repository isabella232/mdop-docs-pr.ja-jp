---
title: MBAM 2.5 サーバーの展開計画
description: MBAM 2.5 サーバーの展開計画
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826214"
---
# <span data-ttu-id="2539a-103">MBAM 2.5 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="2539a-103">Planning for MBAM 2.5 Server Deployment</span></span>


<span data-ttu-id="2539a-104">このトピックでは、MBAM スタンドアロンおよび Configuration Manager のトポロジ用に展開する機能の一覧を示し、展開する必要がある順序を示します。</span><span class="sxs-lookup"><span data-stu-id="2539a-104">This topic lists the features that you deploy for the MBAM Stand-alone and Configuration Manager topologies and lists the order in which you need to deploy them.</span></span> <span data-ttu-id="2539a-105">各トポロジに推奨される構成があります。</span><span class="sxs-lookup"><span data-stu-id="2539a-105">There is a recommended configuration for each topology.</span></span> <span data-ttu-id="2539a-106">ただし、拡張性の要件に応じて、MBAM server データベースと機能をさまざまな構成と複数のサーバー間で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="2539a-106">However, you can configure MBAM server databases and features in different configurations and across multiple servers, depending on your scalability requirements.</span></span>

## <span data-ttu-id="2539a-107">両方のトポロジの計画に関する重要な考慮事項</span><span class="sxs-lookup"><span data-stu-id="2539a-107">Important planning considerations for both topologies</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2539a-108">考慮事項</span><span class="sxs-lookup"><span data-stu-id="2539a-108">Considerations</span></span></th>
<th align="left"><span data-ttu-id="2539a-109">詳細または目的</span><span class="sxs-lookup"><span data-stu-id="2539a-109">Details or purpose</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2539a-110">展開を開始する前に、次の内容を確認します。</span><span class="sxs-lookup"><span data-stu-id="2539a-110">Review the following before you start the deployment:</span></span></p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="2539a-111">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="2539a-111">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="2539a-112">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="2539a-112">MBAM 2.5 Supported Configurations</span></span></a></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="2539a-113">MBAM の各機能には、MBAM インストールを開始する前に満たす必要がある特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="2539a-113">Each MBAM feature has specific prerequisites that must be met before you start the MBAM installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2539a-114">MBAM の BitLocker 回復キーは、1回使用した後に有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="2539a-114">BitLocker recovery keys in MBAM expire after a single use.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2539a-115">1つの用途としては、管理と監視の Web サイト (ヘルプデスクとも呼ばれます)、セルフサービスポータル、または <strong> Windows PowerShell コマンドレットを使用して回復キーを取得したことを意味し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="2539a-115">A single use means that the recovery key has been retrieved through the Administration and Monitoring Website (also known as Help Desk), Self-Service Portal, or by using the Get-<strong>MbamBitLockerRecoveryKey</strong> Windows PowerShell cmdlet.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2539a-116">各機能を構成するコンピューターの名前を追跡します。</span><span class="sxs-lookup"><span data-stu-id="2539a-116">Keep track of the names of the computers on which you configure each feature.</span></span> <span data-ttu-id="2539a-117">この情報は、構成プロセス全体で使用します。</span><span class="sxs-lookup"><span data-stu-id="2539a-117">You will use this information throughout the configuration process.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2539a-118"><a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)">この目的には、mbam 2.5 展開チェックリストを使用することができ </a> ます。</span><span class="sxs-lookup"><span data-stu-id="2539a-118">You may want to use the <a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)">MBAM 2.5 Deployment Checklist</a> for this purpose.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2539a-119">[MDOP MBAM (BitLocker 管理)] ノードのグループポリシー設定のみを構成します。</span><span class="sxs-lookup"><span data-stu-id="2539a-119">Configure only the Group Policy settings in the MDOP MBAM (BitLocker Management) node.</span></span> <span data-ttu-id="2539a-120">BitLocker ドライブ暗号化ノードのグループポリシー設定は変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="2539a-120">Do not change the Group Policy settings in the BitLocker Drive Encryption node.</span></span></p></td>
<td align="left"><p><span data-ttu-id="2539a-121">BitLocker ドライブ暗号化ノードでグループポリシーの設定を変更すると、MBAM が機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="2539a-121">If you change the Group Policy settings in the BitLocker Drive Encryption node, MBAM will not work.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a><span data-ttu-id="2539a-122">MBAM サーバー展開の計画–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="2539a-122">Planning for MBAM Server deployment – Stand-alone topology</span></span>


<span data-ttu-id="2539a-123">スタンドアロンのトポロジでは、3 ~ 4 台のサーバーの構成を使うことができますが、運用環境には2サーバー構成をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2539a-123">For the Stand-alone topology, a two-server configuration is recommended for production environments, although configurations of three to four servers can be used.</span></span>

<span data-ttu-id="2539a-124">MBAM スタンドアロントポロジのサーバーインフラストラクチャには、次の機能が含まれています。これらの機能は、記載されている順序で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2539a-124">The Server infrastructure for the MBAM Stand-alone topology contains the following features, which must be configured in the order listed:</span></span>

1.  <span data-ttu-id="2539a-125">データベース (コンプライアンスおよび監査データベースと復元データベース)</span><span class="sxs-lookup"><span data-stu-id="2539a-125">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="2539a-126">レポート</span><span class="sxs-lookup"><span data-stu-id="2539a-126">Reports</span></span>

3.  <span data-ttu-id="2539a-127">Web アプリケーション (および対応する web サービス)</span><span class="sxs-lookup"><span data-stu-id="2539a-127">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="2539a-128">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="2539a-128">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="2539a-129">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="2539a-129">Self-Service Portal</span></span>

<span data-ttu-id="2539a-130">これらの機能について詳しくは、「 [MBAM 2.5 の高レベルアーキテクチャとスタンドアロントポロジ](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2539a-130">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a><span data-ttu-id="2539a-131">MBAM サーバー展開の計画– Configuration Manager トポロジ</span><span class="sxs-lookup"><span data-stu-id="2539a-131">Planning for MBAM Server deployment – Configuration Manager topology</span></span>


<span data-ttu-id="2539a-132">構成マネージャーの統合トポロジについては、運用環境には3サーバー構成をお勧めしますが、その他のサーバーの構成を使用することもできます。</span><span class="sxs-lookup"><span data-stu-id="2539a-132">For the Configuration Manager Integration topology, a three-server configuration is recommended for production environments, although configurations of additional servers can be used.</span></span>

<span data-ttu-id="2539a-133">MBAM Configuration Manager トポロジのサーバーインフラストラクチャには、次の機能が含まれています。これらの機能は、記載されている順序で構成または実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2539a-133">The Server infrastructure for the MBAM Configuration Manager topology contains the following features, which must be configured or performed in the order listed:</span></span>

1.  <span data-ttu-id="2539a-134">データベース (コンプライアンスおよび監査データベースと復元データベース)</span><span class="sxs-lookup"><span data-stu-id="2539a-134">Databases (Compliance and Audit Database and Recovery Database)</span></span>

2.  <span data-ttu-id="2539a-135">レポート</span><span class="sxs-lookup"><span data-stu-id="2539a-135">Reports</span></span>

3.  <span data-ttu-id="2539a-136">Web アプリケーション (および対応する web サービス)</span><span class="sxs-lookup"><span data-stu-id="2539a-136">Web applications (and their corresponding web services)</span></span>

    -   <span data-ttu-id="2539a-137">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="2539a-137">Administration and Monitoring Website</span></span>

    -   <span data-ttu-id="2539a-138">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="2539a-138">Self-Service Portal</span></span>

4.  <span data-ttu-id="2539a-139">System Center Configuration Manager の統合</span><span class="sxs-lookup"><span data-stu-id="2539a-139">System Center Configuration Manager Integration</span></span>

<span data-ttu-id="2539a-140">これらの機能について詳しくは、「 [MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2539a-140">For a description of these features, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>



## <span data-ttu-id="2539a-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2539a-141">Related topics</span></span>


[<span data-ttu-id="2539a-142">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="2539a-142">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="2539a-143">MBAM 2.5 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="2539a-143">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)

 

## <span data-ttu-id="2539a-144">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="2539a-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2539a-145">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2539a-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2539a-146">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="2539a-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





