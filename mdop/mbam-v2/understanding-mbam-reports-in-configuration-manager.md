---
title: Configuration Manager の MBAM レポートの概要
description: Configuration Manager の MBAM レポートの概要
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823824"
---
# <span data-ttu-id="ffab3-103">Configuration Manager の MBAM レポートの概要</span><span class="sxs-lookup"><span data-stu-id="ffab3-103">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="ffab3-104">Configuration Manager の統合トポロジを使用して Microsoft BitLocker の管理と監視 (MBAM) をインストールすると、ハードウェアのコンプライアンスとレポート機能は構成マネージャーインフラストラクチャに移動され、MBAM から除外されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-104">When Microsoft BitLocker Administration and Monitoring (MBAM) is installed with the Configuration Manager Integrated topology, the hardware compliance and reporting features are moved into the Configuration Manager infrastructure and out of MBAM.</span></span> <span data-ttu-id="ffab3-105">Configuration Manager トポロジを使用している場合は、MBAM からではなく構成マネージャーからレポートを実行します。ただし、引き続き管理と監視の Web サイトを使用してアクセスする回復監査レポートは除きます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-105">When you use the Configuration Manager topology, you run reports from Configuration Manager rather than from MBAM, except for the Recovery Audit Report, which you continue to access by using the Administration and Monitoring Website.</span></span>

<span data-ttu-id="ffab3-106">Configuration Manager の統合されたトポロジのレポートには、企業の BitLocker のコンプライアンス、および MBAM 管理されている個々のコンピューターとデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-106">The reports for the Configuration Manager Integrated topology show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="ffab3-107">レポートには、表形式の情報とグラフの両方が用意されており、レポートをフィルター処理してさまざまな視点からのデータを表示することができます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-107">The reports provide both tabular information and charts, and enable you to filter reports to view data from different perspectives.</span></span>

<span data-ttu-id="ffab3-108">このトピックでは、Configuration Manager から実行する MBAM レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-108">The information in this topic describes the MBAM reports that you run from Configuration Manager.</span></span> <span data-ttu-id="ffab3-109">スタンドアロントポロジ用の MBAM レポートの詳細については、「 [MBAM レポートについ](understanding-mbam-reports-mbam-2.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ffab3-109">For information about MBAM reports for the Stand-alone topology, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

## <span data-ttu-id="ffab3-110">Configuration Manager でレポートにアクセスする</span><span class="sxs-lookup"><span data-stu-id="ffab3-110">Accessing Reports in Configuration Manager</span></span>


<span data-ttu-id="ffab3-111">Configuration Manager のレポート機能にアクセスするには、 **Configuration manager コンソール**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-111">To access the Reports feature in Configuration Manager, open the **Configuration Manager console**.</span></span> <span data-ttu-id="ffab3-112">利用可能なレポートの一覧を表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ffab3-112">To display the list of available reports:</span></span>

-   <span data-ttu-id="ffab3-113">Configuration Manager 2007 で、[**コンピューターの管理**] ノードを展開し、[**レポート**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-113">In Configuration Manager 2007, expand the **Computer Management** node, and then expand the **Reporting** node.</span></span>

-   <span data-ttu-id="ffab3-114">SystemCenter2012 ConfigurationManager の [**概要**] の下にある [監視] ワークスペースで、[**レポート**] ノードを展開し、[**レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ffab3-114">In SystemCenter2012 ConfigurationManager, in the Monitoring workspace under **Overview**, expand the **Reporting** node and then click **Reports**.</span></span>

### <span data-ttu-id="ffab3-115">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="ffab3-115">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="ffab3-116">BitLocker Enterprise コンプライアンスダッシュボードには、次のグラフが用意されています。これは、企業全体での BitLocker のコンプライアンスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-116">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="ffab3-117">コンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="ffab3-117">Compliance Status Distribution</span></span>

-   <span data-ttu-id="ffab3-118">不適合エラー分布</span><span class="sxs-lookup"><span data-stu-id="ffab3-118">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="ffab3-119">ドライブの種類によるコンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="ffab3-119">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="ffab3-120">コンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="ffab3-120">Compliance Status Distribution</span></span>**

<span data-ttu-id="ffab3-121">この円グラフは、企業内のコンピューターのコンプライアンスの状態を示し、選択されたコレクション内のコンピューターの合計数と比較して、そのコンプライアンスの状態を表示しているコンピューターの割合を示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-121">This pie chart shows computer compliance statuses within the enterprise, and shows the percentage of computers, compared to the total number of computers in the selected collection, that have that compliance status.</span></span> <span data-ttu-id="ffab3-122">各状態の実際のコンピューターの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-122">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="ffab3-123">円グラフには、次のコンプライアンスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-123">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="ffab3-124">仕様</span><span class="sxs-lookup"><span data-stu-id="ffab3-124">Compliant</span></span>

-   <span data-ttu-id="ffab3-125">非準拠</span><span class="sxs-lookup"><span data-stu-id="ffab3-125">Non Compliant</span></span>

-   <span data-ttu-id="ffab3-126">ユーザの除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-126">User Exempt</span></span>

-   <span data-ttu-id="ffab3-127">テンポラリユーザの除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-127">Temporary User Exempt</span></span>

-   <span data-ttu-id="ffab3-128">ポリシーが適用されない</span><span class="sxs-lookup"><span data-stu-id="ffab3-128">Policy Not Enforced</span></span>

-   <span data-ttu-id="ffab3-129">不明-状態がエラーとして報告された、またはコレクションの一部であるが、組織から切断されているなど、コンプライアンスの状態を報告していないコンピューター</span><span class="sxs-lookup"><span data-stu-id="ffab3-129">Unknown -computers whose status was reported as an error, or devices that are part of the collection but have never reported their compliance status, for example, if they are disconnected from the organization</span></span>

**<span data-ttu-id="ffab3-130">不適合エラー分布</span><span class="sxs-lookup"><span data-stu-id="ffab3-130">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="ffab3-131">この円グラフには、BitLocker ドライブ暗号化ポリシーに準拠していない企業内のコンピューターのカテゴリが表示され、各カテゴリのコンピューターの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-131">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker drive encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="ffab3-132">各カテゴリのパーセンテージは、コレクション内の非準拠コンピューターの合計数から計算されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-132">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="ffab3-133">ユーザーによる暗号化の延期</span><span class="sxs-lookup"><span data-stu-id="ffab3-133">User postponed encryption</span></span>

-   <span data-ttu-id="ffab3-134">互換性のある TPM が見つかりません</span><span class="sxs-lookup"><span data-stu-id="ffab3-134">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="ffab3-135">システムパーティションが利用できない、または大きすぎる</span><span class="sxs-lookup"><span data-stu-id="ffab3-135">System Partition not available or large enough</span></span>

-   <span data-ttu-id="ffab3-136">ポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="ffab3-136">Policy conflict</span></span>

-   <span data-ttu-id="ffab3-137">TPM 自動プロビジョニングを待機しています</span><span class="sxs-lookup"><span data-stu-id="ffab3-137">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="ffab3-138">不明なエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="ffab3-138">An unknown error has occurred</span></span>

-   <span data-ttu-id="ffab3-139">情報なし: MBAM クライアントがインストールされていない場合、または MBAM クライアントがインストールされていても、ライセンス認証されていない場合は、サービスが機能していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-139">No information – computers that do not have the MBAM Client installed, or that have the MBAM Client installed but not activated, for example, the service is not working</span></span>

**<span data-ttu-id="ffab3-140">ドライブの種類によるコンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="ffab3-140">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="ffab3-141">この棒グラフは、ドライブの種類別の現在の BitLocker コンプライアンスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-141">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="ffab3-142">状態は、"準拠" および "非準拠" です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-142">The statuses are “Compliant” and “Non Compliant.”</span></span> <span data-ttu-id="ffab3-143">固定データドライブとオペレーティングシステムドライブの場合は、バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-143">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="ffab3-144">固定データドライブを持っていないコンピューターは、オペレーティングシステムのドライブバーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-144">Computers that do not have a fixed data drive are included and show a value only in the Operating System Drive bar.</span></span> <span data-ttu-id="ffab3-145">このグラフには、BitLocker ドライブ暗号化ポリシーまたは "ポリシーなし" カテゴリの除外を許可されているユーザーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-145">The chart does not include users who have been granted an exemption from the BitLocker drive encryption policy or the “No Policy” category.</span></span>

### <span data-ttu-id="ffab3-146">BitLocker Enterprise コンプライアンスの詳細レポート</span><span class="sxs-lookup"><span data-stu-id="ffab3-146">BitLocker Enterprise Compliance Details Report</span></span>

<span data-ttu-id="ffab3-147">このレポートには、BitLocker の使用を目的としたコンピューターのコレクションに対する、エンタープライズ全体での BitLocker のコンプライアンス全体に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-147">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="ffab3-148">BitLocker エンタープライズコンプライアンスの詳細レポートフィールド</span><span class="sxs-lookup"><span data-stu-id="ffab3-148">BitLocker Enterprise Compliance Details Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-149">列名</span><span class="sxs-lookup"><span data-stu-id="ffab3-149">Column Name</span></span></th>
<th align="left"><span data-ttu-id="ffab3-150">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-151">管理されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="ffab3-151">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-152">MBAM で管理されているコンピューターの数です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-152">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-153">% 準拠</span><span class="sxs-lookup"><span data-stu-id="ffab3-153">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-154">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-154">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-155">% 非準拠率</span><span class="sxs-lookup"><span data-stu-id="ffab3-155">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-156">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-156">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-157">% 不明のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-157">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-158">コンプライアンスの状態が不明なコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-158">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-159">% 免税</span><span class="sxs-lookup"><span data-stu-id="ffab3-159">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-160">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-160">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-161">% 免税以外</span><span class="sxs-lookup"><span data-stu-id="ffab3-161">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-162">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-162">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-163">仕様</span><span class="sxs-lookup"><span data-stu-id="ffab3-163">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-164">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-164">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-165">準拠していない</span><span class="sxs-lookup"><span data-stu-id="ffab3-165">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-166">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-166">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-167">不明なコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-167">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-168">コンプライアンスの状態が不明なコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-168">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-169">適用除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-169">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-170">BitLocker 暗号化要件から除外されたコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="ffab3-170">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-171">非免税</span><span class="sxs-lookup"><span data-stu-id="ffab3-171">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-172">BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="ffab3-172">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="ffab3-173">BitLocker エンタープライズコンプライアンスの詳細レポート-コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="ffab3-173">BitLocker Enterprise Compliance Details Report - Compliance States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-174">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="ffab3-174">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="ffab3-175">除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-175">Exemption</span></span></th>
<th align="left"><span data-ttu-id="ffab3-176">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-177">互換性</span><span class="sxs-lookup"><span data-stu-id="ffab3-177">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-178">非課税</span><span class="sxs-lookup"><span data-stu-id="ffab3-178">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-179">指定したポリシーに従って、コンピューターが準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-179">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-180">仕様</span><span class="sxs-lookup"><span data-stu-id="ffab3-180">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-181">非課税</span><span class="sxs-lookup"><span data-stu-id="ffab3-181">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-182">コンピューターは、指定されたポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="ffab3-182">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ffab3-183">BitLocker Enterprise コンプライアンスサマリーレポート</span><span class="sxs-lookup"><span data-stu-id="ffab3-183">BitLocker Enterprise Compliance Summary Report</span></span>

<span data-ttu-id="ffab3-184">このレポートの種類を使用して、組織全体の BitLocker のコンプライアンス全体に関する情報を表示したり、BitLocker の使用を目的としているコンピューターのコレクション内にある個々のコンピューターのコンプライアンスを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="ffab3-184">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="ffab3-185">BitLocker エンタープライズコンプライアンスの概要レポートフィールド</span><span class="sxs-lookup"><span data-stu-id="ffab3-185">BitLocker Enterprise Compliance Summary Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-186">列名</span><span class="sxs-lookup"><span data-stu-id="ffab3-186">Column Name</span></span></th>
<th align="left"><span data-ttu-id="ffab3-187">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-188">管理されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="ffab3-188">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-189">MBAM で管理されているコンピューターの数です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-189">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-190">% 準拠</span><span class="sxs-lookup"><span data-stu-id="ffab3-190">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-191">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-191">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-192">% 非準拠率</span><span class="sxs-lookup"><span data-stu-id="ffab3-192">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-193">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-193">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-194">% 不明のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-194">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-195">コンプライアンスの状態が不明なコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-195">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-196">% 免税</span><span class="sxs-lookup"><span data-stu-id="ffab3-196">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-197">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-197">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-198">% 免税以外</span><span class="sxs-lookup"><span data-stu-id="ffab3-198">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-199">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-199">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-200">仕様</span><span class="sxs-lookup"><span data-stu-id="ffab3-200">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-201">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-201">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-202">準拠していない</span><span class="sxs-lookup"><span data-stu-id="ffab3-202">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-203">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-203">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-204">不明なコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-204">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-205">コンプライアンスの状態が不明なコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="ffab3-205">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-206">適用除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-206">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-207">BitLocker 暗号化要件から除外されたコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="ffab3-207">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-208">非免税</span><span class="sxs-lookup"><span data-stu-id="ffab3-208">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-209">BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="ffab3-209">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="ffab3-210">BitLocker エンタープライズコンプライアンスの概要レポート-コンピューターの詳細</span><span class="sxs-lookup"><span data-stu-id="ffab3-210">BitLocker Enterprise Compliance Summary Report - Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-211">列名</span><span class="sxs-lookup"><span data-stu-id="ffab3-211">Column Name</span></span></th>
<th align="left"><span data-ttu-id="ffab3-212">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-213">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="ffab3-213">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-214">MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-214">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-215">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="ffab3-215">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-216">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-216">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-217">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="ffab3-217">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-218">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-218">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="ffab3-219">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-219">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="ffab3-220">ドライブあたりのコンプライアンスの状態 (その後の表を参照) が、さまざまなコンプライアンスの状態を示している可能性があることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="ffab3-220">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="ffab3-221">ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-221">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-222">除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-222">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-223">ユーザーが除外されているか、BitLocker ポリシーから除外されているかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-223">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-224">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="ffab3-224">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-225">デバイスのユーザー。</span><span class="sxs-lookup"><span data-stu-id="ffab3-225">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-226">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="ffab3-226">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-227">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ffab3-227">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-228">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="ffab3-228">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-229">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-229">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="ffab3-230">連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="ffab3-230">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ffab3-231">BitLocker コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="ffab3-231">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="ffab3-232">このレポートの種類を使用して、コンピューターに固有の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-232">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="ffab3-233">コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。また、コンピューター上の各ドライブの種類に適用されるポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="ffab3-233">The Computer Compliance Report provides detailed encryption information about each drive (Operating System and Fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="ffab3-234">各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-234">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="ffab3-235">**注** リムーバブルデータボリュームの暗号化の状態は、レポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-235">**Note** Removable Data Volume encryption status is not shown in the report.</span></span>

 

**<span data-ttu-id="ffab3-236">BitLocker コンピューターのコンプライアンスレポート–コンピューターの詳細のフィールド</span><span class="sxs-lookup"><span data-stu-id="ffab3-236">BitLocker Computer Compliance Report – Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-237">列名</span><span class="sxs-lookup"><span data-stu-id="ffab3-237">Column Name</span></span></th>
<th align="left"><span data-ttu-id="ffab3-238">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-239">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="ffab3-239">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-240">MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-240">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-241">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="ffab3-241">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-242">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-242">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-243">コンピュータの種類</span><span class="sxs-lookup"><span data-stu-id="ffab3-243">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-244">コンピューターの種類。</span><span class="sxs-lookup"><span data-stu-id="ffab3-244">Type of computer.</span></span> <span data-ttu-id="ffab3-245">有効な型は、ポータブルでもポータブルでもありません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-245">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-246">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="ffab3-246">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-247">MBAM 管理クライアントコンピューターで検出されたオペレーティングシステムの種類。</span><span class="sxs-lookup"><span data-stu-id="ffab3-247">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-248">全体のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-248">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-249">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-249">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="ffab3-250">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-250">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="ffab3-251">ドライブあたりのコンプライアンスの状態 (その後の表を参照) が、さまざまなコンプライアンスの状態を示している可能性があることに注目してください。</span><span class="sxs-lookup"><span data-stu-id="ffab3-251">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="ffab3-252">ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-252">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-253">オペレーティングシステムのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-253">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-254">MBAM で管理されているオペレーティングシステムのコンプライアンスの状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-254">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="ffab3-255">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-255">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-256">固定データドライブのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="ffab3-256">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-257">MBAM で管理されている固定データドライブのコンプライアンスステータス。</span><span class="sxs-lookup"><span data-stu-id="ffab3-257">Compliance status of the Fixed Data Drive that is managed by MBAM.</span></span> <span data-ttu-id="ffab3-258">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="ffab3-258">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-259">最終更新日</span><span class="sxs-lookup"><span data-stu-id="ffab3-259">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-260">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-260">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="ffab3-261">連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="ffab3-261">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-262">除外</span><span class="sxs-lookup"><span data-stu-id="ffab3-262">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-263">ユーザーが除外されているか、BitLocker ポリシーから除外されているかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-263">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-264">除外対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="ffab3-264">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-265">BitLocker ポリシーから除外されているユーザー。</span><span class="sxs-lookup"><span data-stu-id="ffab3-265">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-266">免税日</span><span class="sxs-lookup"><span data-stu-id="ffab3-266">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-267">免税が付与された日付。</span><span class="sxs-lookup"><span data-stu-id="ffab3-267">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-268">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="ffab3-268">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-269">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="ffab3-269">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-270">ポリシー暗号強度</span><span class="sxs-lookup"><span data-stu-id="ffab3-270">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-271">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="ffab3-271">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="ffab3-272">(例: ディフューザー付きの128ビット)。</span><span class="sxs-lookup"><span data-stu-id="ffab3-272">(for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-273">ポリシー: オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="ffab3-273">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-274">O/S と適切なプロテクターの種類に対して暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-274">Indicates if encryption is required for the O/S and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-275">ポリシー: 固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="ffab3-275">Policy:Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-276">固定ドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-276">Indicates if encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-277">製造元</span><span class="sxs-lookup"><span data-stu-id="ffab3-277">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-278">コンピューターの BIOS に表示されるコンピューターの製造元名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-278">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-279">モデル</span><span class="sxs-lookup"><span data-stu-id="ffab3-279">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-280">コンピューターの BIOS に表示されるコンピューターの製造元のモデル名。</span><span class="sxs-lookup"><span data-stu-id="ffab3-280">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-281">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="ffab3-281">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-282">MBAM で管理されているコンピューター上の既知のユーザー。</span><span class="sxs-lookup"><span data-stu-id="ffab3-282">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="ffab3-283">BitLocker コンピューターのコンプライアンスレポート–コンピューターのボリュームフィールド</span><span class="sxs-lookup"><span data-stu-id="ffab3-283">BitLocker Computer Compliance Report – Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ffab3-284">列名</span><span class="sxs-lookup"><span data-stu-id="ffab3-284">Column Name</span></span></th>
<th align="left"><span data-ttu-id="ffab3-285">説明</span><span class="sxs-lookup"><span data-stu-id="ffab3-285">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-286">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="ffab3-286">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-287">ユーザーが特定のドライブに割り当てたコンピューターのドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="ffab3-287">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-288">ドライブの種類</span><span class="sxs-lookup"><span data-stu-id="ffab3-288">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-289">ドライブの種類。</span><span class="sxs-lookup"><span data-stu-id="ffab3-289">Type of drive.</span></span> <span data-ttu-id="ffab3-290">有効な値は、オペレーティングシステムドライブと固定データドライブです。</span><span class="sxs-lookup"><span data-stu-id="ffab3-290">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="ffab3-291">これらは論理ボリュームではなく物理ドライブです。</span><span class="sxs-lookup"><span data-stu-id="ffab3-291">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-292">暗号強度</span><span class="sxs-lookup"><span data-stu-id="ffab3-292">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-293">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="ffab3-293">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-294">プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="ffab3-294">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-295">オペレーティングシステムまたは固定ボリュームの暗号化に使用するポリシーによって選択されたプロテクターの種類。</span><span class="sxs-lookup"><span data-stu-id="ffab3-295">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="ffab3-296">オペレーティングシステムで有効なプロテクター型は、TPM または TPM + PIN であり、固定データボリュームにはパスワードです。</span><span class="sxs-lookup"><span data-stu-id="ffab3-296">The valid protector types on an operating system are TPM or TPM+PIN and for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ffab3-297">プロテクターの状態</span><span class="sxs-lookup"><span data-stu-id="ffab3-297">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-298">MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="ffab3-298">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="ffab3-299">有効な状態は、オンまたはオフです。</span><span class="sxs-lookup"><span data-stu-id="ffab3-299">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ffab3-300">暗号化の状態</span><span class="sxs-lookup"><span data-stu-id="ffab3-300">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="ffab3-301">ドライブの暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="ffab3-301">Encryption state of the drive.</span></span> <span data-ttu-id="ffab3-302">有効な状態は、暗号化され、暗号化されず、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ffab3-302">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ffab3-303">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ffab3-303">Related topics</span></span>


[<span data-ttu-id="ffab3-304">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="ffab3-304">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





