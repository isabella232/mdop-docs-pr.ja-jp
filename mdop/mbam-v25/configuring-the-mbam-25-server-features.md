---
title: MBAM 2.5 サーバー機能の構成
description: MBAM 2.5 サーバー機能の構成
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823057"
---
# <span data-ttu-id="91662-103">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="91662-103">Configuring the MBAM 2.5 Server Features</span></span>


<span data-ttu-id="91662-104">[Mbam 2.5 サーバーソフトウェアをインストール](installing-the-mbam-25-server-software.md)した後、Microsoft BitLocker 管理および監視 (mbam) 2.5 サーバー機能を構成するための出発点として、この情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="91662-104">Use this information as a starting place for configuring Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server features after [Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md).</span></span> <span data-ttu-id="91662-105">MBAM を構成するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="91662-105">There are two methods you can use to configure MBAM:</span></span>

-   <span data-ttu-id="91662-106">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="91662-106">MBAM Server Configuration wizard</span></span>

-   <span data-ttu-id="91662-107">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="91662-107">Windows PowerShell cmdlets</span></span>

## <span data-ttu-id="91662-108">MBAM サーバー機能の構成を開始する前に</span><span class="sxs-lookup"><span data-stu-id="91662-108">Before you start configuring MBAM Server features</span></span>


<span data-ttu-id="91662-109">MBAM サーバー機能の構成を開始する前に、次の手順を確認して完了します。</span><span class="sxs-lookup"><span data-stu-id="91662-109">Review and complete the following steps before you start configuring the MBAM Server features:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91662-110">ステップ</span><span class="sxs-lookup"><span data-stu-id="91662-110">Step</span></span></th>
<th align="left"><span data-ttu-id="91662-111">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="91662-111">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91662-112">MBAM の推奨アーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="91662-112">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="91662-113">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="91662-113">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91662-114">MBAM のサポートされている構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="91662-114">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="91662-115">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="91662-115">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91662-116">各サーバーに必要な前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="91662-116">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="91662-117">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="91662-117">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="91662-118">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="91662-118">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91662-119">Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="91662-119">Install the MBAM Server software on each server where you will configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="91662-120">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="91662-120">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91662-121">Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件を確認します (この方法を使用して MBAM サーバー機能を構成する場合)。</span><span class="sxs-lookup"><span data-stu-id="91662-121">Review the prerequisites for using Windows PowerShell to configure MBAM Server features (if you are using this method to configure MBAM Server features).</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="91662-122">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="91662-122">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="91662-123">MBAM サーバー機能を構成する手順</span><span class="sxs-lookup"><span data-stu-id="91662-123">Steps for configuring MBAM Server features</span></span>


<span data-ttu-id="91662-124">次の表の各行では、 [MBAM 2.5 の推奨される高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)に従って、個別のサーバーで構成する機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="91662-124">Each row in the following table describes the features that you will configure on a separate server, according to the recommended [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91662-125">インストールする機能</span><span class="sxs-lookup"><span data-stu-id="91662-125">Features to install</span></span></th>
<th align="left"><span data-ttu-id="91662-126">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="91662-126">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91662-127">データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="91662-127">Configure the databases.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)"><span data-ttu-id="91662-128">MBAM 2.5 データベースを構成する方法</span><span class="sxs-lookup"><span data-stu-id="91662-128">How to Configure the MBAM 2.5 Databases</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91662-129">レポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="91662-129">Configure the reports.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)"><span data-ttu-id="91662-130">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="91662-130">How to Configure the MBAM 2.5 Reports</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="91662-131">Web アプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="91662-131">Configure the web applications.</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)"><span data-ttu-id="91662-132">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="91662-132">How to Configure the MBAM 2.5 Web Applications</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="91662-133">System Center Configuration Manager の統合を構成します (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="91662-133">Configure the System Center Configuration Manager Integration (if applicable).</span></span></p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)"><span data-ttu-id="91662-134">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</span><span class="sxs-lookup"><span data-stu-id="91662-134">How to Configure the MBAM 2.5 System Center Configuration Manager Integration</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="91662-135">MBAM サーバー機能の構成について詳しくは、「[サーバーイベントログ](server-event-logs.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="91662-135">For a list of events about MBAM Server feature configuration, see [Server Event Logs](server-event-logs.md).</span></span>



## <span data-ttu-id="91662-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="91662-136">Related topics</span></span>


<span data-ttu-id="91662-137">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="91662-137">Configuring the MBAM 2.5 Server Features</span></span>
 

 
## <span data-ttu-id="91662-138">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="91662-138">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="91662-139">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="91662-139">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="91662-140">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="91662-140">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




