---
title: MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)
description: MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824044"
---
# <span data-ttu-id="9c86b-103">MBAM 2.5 レポートの表示 (Configuration Manager 統合トポロジ)</span><span class="sxs-lookup"><span data-stu-id="9c86b-103">Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="9c86b-104">このトピックでは、Configuration Manager の統合トポロジを使用して Microsoft BitLocker 管理と監視 (MBAM) を構成するときに使用できるレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-104">This topic describes the reports that are available when you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="9c86b-105">このレポートには、エンタープライズの BitLocker コンプライアンスと、MBAM 管理されている個々のコンピューターとデバイスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-105">The reports show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="9c86b-106">レポートには表形式の情報とグラフが用意されており、さまざまな視点からのデータを表示できるフィルターがあります。</span><span class="sxs-lookup"><span data-stu-id="9c86b-106">The reports provide tabular information and charts, and they have filters that let you view data from different perspectives.</span></span>

<span data-ttu-id="9c86b-107">Configuration Manager の統合トポロジでは、管理と監視の Web サイトからではなく、構成マネージャーからレポートを表示します。**回復監査レポート**は除き、管理と監視の web サイトから引き続き表示できます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-107">In the Configuration Manager Integration topology, you view reports from Configuration Manager rather than from the Administration and Monitoring Website, with the exception of the **Recovery Audit Report**, which you continue to view from the Administration and Monitoring Website.</span></span>

<span data-ttu-id="9c86b-108">スタンドアロントポロジ用の MBAM レポートについては、「 [mbam 2.5 レポートでスタンドアロントポロジを表示](viewing-mbam-25-reports-for-the-stand-alone-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-108">For information about MBAM reports for the Stand-alone topology, see [Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md).</span></span>

## <span data-ttu-id="9c86b-109">Configuration Manager でレポートにアクセスする</span><span class="sxs-lookup"><span data-stu-id="9c86b-109">Accessing reports in Configuration Manager</span></span>


<span data-ttu-id="9c86b-110">構成マネージャーでレポート機能にアクセスするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="9c86b-110">To access the Reports feature in Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-111">Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="9c86b-111">Version of Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="9c86b-112">レポートを表示する方法</span><span class="sxs-lookup"><span data-stu-id="9c86b-112">How to view the reports</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-113">SystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="9c86b-113">SystemCenter2012 ConfigurationManager</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="9c86b-114">左側のウィンドウで、[監視] ワークスペースを選択し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-114">In the left pane, select the <strong>Monitoring</strong> workspace.</span></span></p></li>
<li><p><span data-ttu-id="9c86b-115">ツリーで、[ <strong> 概要 </strong> &gt; <strong> レポート </strong> &gt; <strong> レポート </strong> &gt; <strong> mbam </strong> ] を展開します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-115">In the tree, expand <strong>Overview</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reports</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="9c86b-116">レポートを表示する言語を表すフォルダーを選択し、右側のウィンドウからレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-116">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-117">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="9c86b-117">Configuration Manager 2007</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="9c86b-118">左側のウィンドウで、[ <strong> コンピューター管理] レポート </strong> &gt; <strong> </strong> &gt; <strong> サービス </strong> &gt; <strong> &lt; サーバー名 &gt; </strong> &gt; <strong> レポートフォルダー </strong> &gt; <strong> mbam </strong> を展開します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-118">In the left pane, expand <strong>Computer Management</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reporting Services</strong> &gt; <strong>&lt;server name&gt;</strong> &gt; <strong>Report folders</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="9c86b-119">レポートを表示する言語を表すフォルダーを選択し、右側のウィンドウからレポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-119">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9c86b-120">Configuration Manager のレポートの説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-120">Description of reports in Configuration Manager</span></span>


<span data-ttu-id="9c86b-121">構成マネージャーの統合トポロジおよびスタンドアロントポロジのレポートには、いくつかのわずかな違いがあります。</span><span class="sxs-lookup"><span data-stu-id="9c86b-121">There are a few minor differences in the reports for the Configuration Manager Integration topology and the Stand-alone topology.</span></span> <span data-ttu-id="9c86b-122">以下のセクションでは、Configuration Manager 統合トポロジの MBAM レポートのデータについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-122">The following sections describe the data in the MBAM reports for the Configuration Manager Integration topology:</span></span>

-   [<span data-ttu-id="9c86b-123">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9c86b-123">BitLocker Enterprise Compliance Dashboard</span></span>](#bkmk-dashboard)

-   [<span data-ttu-id="9c86b-124">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="9c86b-124">BitLocker Enterprise Compliance Details</span></span>](#bkmk-compliancedetails)

-   [<span data-ttu-id="9c86b-125">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="9c86b-125">BitLocker Enterprise Compliance Summary</span></span>](#bkmk-compliancesummary)

-   [<span data-ttu-id="9c86b-126">BitLocker コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="9c86b-126">BitLocker Computer Compliance Report</span></span>](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a><span data-ttu-id="9c86b-127">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="9c86b-127">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="9c86b-128">BitLocker Enterprise コンプライアンスダッシュボードには、次のグラフが用意されています。これは、企業全体での BitLocker のコンプライアンスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-128">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="9c86b-129">コンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="9c86b-129">Compliance Status Distribution</span></span>

-   <span data-ttu-id="9c86b-130">不適合エラー分布</span><span class="sxs-lookup"><span data-stu-id="9c86b-130">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="9c86b-131">ドライブの種類によるコンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="9c86b-131">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="9c86b-132">コンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="9c86b-132">Compliance Status Distribution</span></span>**

<span data-ttu-id="9c86b-133">この円グラフは、企業内のコンピューターのコンプライアンスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-133">This pie chart shows compliance status for computers within the enterprise.</span></span> <span data-ttu-id="9c86b-134">また、選択したコレクション内のコンピューターの合計数と比較して、そのコンプライアンスの状態を示すコンピューターの割合も表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-134">It also shows the percentage of computers, compared to the total number of computers in the selected collection, that has that compliance status.</span></span> <span data-ttu-id="9c86b-135">各状態の実際のコンピューターの数も表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-135">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="9c86b-136">円グラフには、次のコンプライアンスの状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-136">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="9c86b-137">仕様</span><span class="sxs-lookup"><span data-stu-id="9c86b-137">Compliant</span></span>

-   <span data-ttu-id="9c86b-138">非準拠</span><span class="sxs-lookup"><span data-stu-id="9c86b-138">Non Compliant</span></span>

-   <span data-ttu-id="9c86b-139">ユーザの除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-139">User Exempt</span></span>

-   <span data-ttu-id="9c86b-140">テンポラリユーザの除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-140">Temporary User Exempt</span></span>

-   <span data-ttu-id="9c86b-141">ポリシーが適用されない</span><span class="sxs-lookup"><span data-stu-id="9c86b-141">Policy Not Enforced</span></span>

-   <span data-ttu-id="9c86b-142">未.</span><span class="sxs-lookup"><span data-stu-id="9c86b-142">Unknown.</span></span> <span data-ttu-id="9c86b-143">これらのコンピューターでは、状態エラーが報告されたか、またはコレクションの一部であるが、コンプライアンスの状態は報告していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-143">These computers reported a status error, or they are part of the collection, but have never reported their compliance status.</span></span> <span data-ttu-id="9c86b-144">コンピューターが組織から切断されていると、コンプライアンスの状態がない場合があります。</span><span class="sxs-lookup"><span data-stu-id="9c86b-144">The lack of a compliance status could occur if the computer is disconnected from the organization.</span></span>

**<span data-ttu-id="9c86b-145">不適合エラー分布</span><span class="sxs-lookup"><span data-stu-id="9c86b-145">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="9c86b-146">この円グラフには、BitLocker ドライブ暗号化ポリシーに準拠していない企業内のコンピューターのカテゴリが表示され、各カテゴリのコンピューターの数が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-146">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker Drive Encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="9c86b-147">各カテゴリのパーセンテージは、コレクション内の非準拠コンピューターの合計数から計算されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-147">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="9c86b-148">ユーザーによる暗号化の延期</span><span class="sxs-lookup"><span data-stu-id="9c86b-148">User postponed encryption</span></span>

-   <span data-ttu-id="9c86b-149">互換性のある TPM が見つかりません</span><span class="sxs-lookup"><span data-stu-id="9c86b-149">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="9c86b-150">システムパーティションが利用できない、または大きすぎる</span><span class="sxs-lookup"><span data-stu-id="9c86b-150">System partition not available or large enough</span></span>

-   <span data-ttu-id="9c86b-151">ポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="9c86b-151">Policy conflict</span></span>

-   <span data-ttu-id="9c86b-152">TPM 自動プロビジョニングを待機しています</span><span class="sxs-lookup"><span data-stu-id="9c86b-152">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="9c86b-153">不明なエラーが発生しました</span><span class="sxs-lookup"><span data-stu-id="9c86b-153">An unknown error has occurred</span></span>

-   <span data-ttu-id="9c86b-154">情報がありません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-154">No information.</span></span> <span data-ttu-id="9c86b-155">これらのコンピューターに MBAM クライアントがインストールされていない場合、または MBAM クライアントがインストールされていても、ライセンス認証されていない場合 (サービスが動作していない場合など)。</span><span class="sxs-lookup"><span data-stu-id="9c86b-155">These computers do not have the MBAM Client installed, or they have the MBAM Client installed but not activated (for example, the service is not working).</span></span>

**<span data-ttu-id="9c86b-156">ドライブの種類によるコンプライアンスの状態の配布</span><span class="sxs-lookup"><span data-stu-id="9c86b-156">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="9c86b-157">この棒グラフは、ドライブの種類別の現在の BitLocker コンプライアンスの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-157">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="9c86b-158">状態は、**準拠**していないものであり、**準拠**していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-158">The statuses are **Compliant** and **Non Compliant**.</span></span> <span data-ttu-id="9c86b-159">固定データドライブとオペレーティングシステムドライブの場合は、バーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-159">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="9c86b-160">固定データドライブを持っていないコンピューターは、**オペレーティングシステムのドライブ**バーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-160">Computers that do not have a fixed data drive are included and show a value only in the **Operating System Drive** bar.</span></span> <span data-ttu-id="9c86b-161">このグラフには、BitLocker ドライブ暗号化ポリシーまたはポリシーなしカテゴリの除外を許可されているユーザーは含まれません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-161">The chart does not include users who have been granted an exemption from the BitLocker Drive Encryption policy or the No Policy category.</span></span>

### <a href="" id="bkmk-compliancedetails"></a><span data-ttu-id="9c86b-162">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="9c86b-162">BitLocker Enterprise Compliance Details</span></span>

<span data-ttu-id="9c86b-163">このレポートには、BitLocker の使用を目的としたコンピューターのコレクションに対する、エンタープライズ全体での BitLocker のコンプライアンス全体に関する情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-163">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="9c86b-164">BitLocker エンタープライズコンプライアンスの詳細フィールド</span><span class="sxs-lookup"><span data-stu-id="9c86b-164">BitLocker Enterprise Compliance Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-165">列名</span><span class="sxs-lookup"><span data-stu-id="9c86b-165">Column Name</span></span></th>
<th align="left"><span data-ttu-id="9c86b-166">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-167">管理されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="9c86b-167">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-168">MBAM で管理されているコンピューターの数です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-168">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-169">% 準拠</span><span class="sxs-lookup"><span data-stu-id="9c86b-169">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-170">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-170">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-171">% 非準拠率</span><span class="sxs-lookup"><span data-stu-id="9c86b-171">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-172">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-172">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-173">% 不明のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-173">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-174">コンプライアンスの状態が不明であるコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-174">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-175">% 免税</span><span class="sxs-lookup"><span data-stu-id="9c86b-175">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-176">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-176">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-177">% 免税以外</span><span class="sxs-lookup"><span data-stu-id="9c86b-177">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-178">BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-178">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-179">仕様</span><span class="sxs-lookup"><span data-stu-id="9c86b-179">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-180">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-180">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-181">準拠していない</span><span class="sxs-lookup"><span data-stu-id="9c86b-181">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-182">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-182">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-183">不明なコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-183">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-184">コンプライアンスの状態が不明であるコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-184">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-185">適用除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-185">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-186">BitLocker 暗号化要件から除外されたコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="9c86b-186">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-187">非免税</span><span class="sxs-lookup"><span data-stu-id="9c86b-187">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-188">BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="9c86b-188">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9c86b-189">BitLocker エンタープライズコンプライアンスの詳細の状態</span><span class="sxs-lookup"><span data-stu-id="9c86b-189">BitLocker Enterprise Compliance Details States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-190">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="9c86b-190">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="9c86b-191">除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-191">Exemption</span></span></th>
<th align="left"><span data-ttu-id="9c86b-192">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-193">互換性</span><span class="sxs-lookup"><span data-stu-id="9c86b-193">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-194">非課税</span><span class="sxs-lookup"><span data-stu-id="9c86b-194">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-195">指定したポリシーに従って、コンピューターが準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-195">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-196">仕様</span><span class="sxs-lookup"><span data-stu-id="9c86b-196">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-197">非課税</span><span class="sxs-lookup"><span data-stu-id="9c86b-197">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-198">コンピューターは、指定されたポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="9c86b-198">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancesummary"></a><span data-ttu-id="9c86b-199">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="9c86b-199">BitLocker Enterprise Compliance Summary</span></span>

<span data-ttu-id="9c86b-200">このレポートの種類を使用して、組織全体の BitLocker のコンプライアンス全体に関する情報を表示したり、BitLocker の使用を目的としているコンピューターのコレクション内にある個々のコンピューターのコンプライアンスを表示したりします。</span><span class="sxs-lookup"><span data-stu-id="9c86b-200">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="9c86b-201">BitLocker エンタープライズコンプライアンスの概要フィールド</span><span class="sxs-lookup"><span data-stu-id="9c86b-201">BitLocker Enterprise Compliance Summary Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-202">列名</span><span class="sxs-lookup"><span data-stu-id="9c86b-202">Column Name</span></span></th>
<th align="left"><span data-ttu-id="9c86b-203">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-203">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-204">管理されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="9c86b-204">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-205">MBAM で管理されているコンピューターの数です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-205">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-206">% 準拠</span><span class="sxs-lookup"><span data-stu-id="9c86b-206">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-207">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-207">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-208">% 非準拠率</span><span class="sxs-lookup"><span data-stu-id="9c86b-208">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-209">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-209">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-210">% 不明のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-210">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-211">コンプライアンスの状態が不明であるコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-211">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-212">% 免税</span><span class="sxs-lookup"><span data-stu-id="9c86b-212">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-213">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-213">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-214">% 免税以外</span><span class="sxs-lookup"><span data-stu-id="9c86b-214">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-215">BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-215">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-216">仕様</span><span class="sxs-lookup"><span data-stu-id="9c86b-216">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-217">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-217">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-218">準拠していない</span><span class="sxs-lookup"><span data-stu-id="9c86b-218">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-219">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-219">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-220">不明なコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-220">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-221">コンプライアンスの状態が不明であるコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="9c86b-221">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-222">適用除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-222">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-223">BitLocker 暗号化要件から除外されたコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="9c86b-223">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-224">非免税</span><span class="sxs-lookup"><span data-stu-id="9c86b-224">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-225">BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="9c86b-225">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9c86b-226">BitLocker Enterprise コンプライアンスサマリーコンピューターの詳細</span><span class="sxs-lookup"><span data-stu-id="9c86b-226">BitLocker Enterprise Compliance Summary Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-227">列名</span><span class="sxs-lookup"><span data-stu-id="9c86b-227">Column Name</span></span></th>
<th align="left"><span data-ttu-id="9c86b-228">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-228">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-229">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="9c86b-229">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-230">MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-230">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-231">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="9c86b-231">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-232">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-232">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-233">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="9c86b-233">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-234">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-234">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="9c86b-235">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-235">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="9c86b-236">ドライブあたりのコンプライアンスの状態 (後の表を参照) が、異なるコンプライアンスの状態を示している可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-236">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="9c86b-237">ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-237">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-238">除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-238">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-239">ユーザーが除外されているか、非表示になっているかを BitLocker ポリシーから除外するかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-239">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-240">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="9c86b-240">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-241">デバイスのユーザー。</span><span class="sxs-lookup"><span data-stu-id="9c86b-241">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-242">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="9c86b-242">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-243">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9c86b-243">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-244">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="9c86b-244">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-245">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-245">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="9c86b-246">連絡先の頻度は、グループポリシー設定を通じて構成できます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-246">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a><span data-ttu-id="9c86b-247">BitLocker コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="9c86b-247">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="9c86b-248">このレポートの種類を使用して、コンピューターに固有の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-248">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="9c86b-249">BitLocker コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-249">The BitLocker Computer Compliance Report provides detailed encryption information about each drive on a computer (operating system and fixed data drives).</span></span> <span data-ttu-id="9c86b-250">また、コンピューター上の各ドライブの種類に適用されるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-250">It also provides an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="9c86b-251">各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-251">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="9c86b-252">**注** リムーバブルデータボリュームの暗号化の状態は、このレポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-252">**Note** The Removable Data Volume encryption status is not shown in this report.</span></span>

 

**<span data-ttu-id="9c86b-253">BitLocker コンピューターのコンプライアンスレポート: コンピューターの詳細フィールド</span><span class="sxs-lookup"><span data-stu-id="9c86b-253">BitLocker Computer Compliance Report: Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-254">列名</span><span class="sxs-lookup"><span data-stu-id="9c86b-254">Column Name</span></span></th>
<th align="left"><span data-ttu-id="9c86b-255">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-255">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-256">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="9c86b-256">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-257">MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-257">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-258">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="9c86b-258">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-259">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-259">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-260">コンピュータの種類</span><span class="sxs-lookup"><span data-stu-id="9c86b-260">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-261">コンピューターの種類。</span><span class="sxs-lookup"><span data-stu-id="9c86b-261">Type of computer.</span></span> <span data-ttu-id="9c86b-262">有効な型は、ポータブルでもポータブルでもありません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-262">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-263">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="9c86b-263">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-264">MBAM 管理クライアントコンピューターで検出されたオペレーティングシステムの種類。</span><span class="sxs-lookup"><span data-stu-id="9c86b-264">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-265">全体のコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-265">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-266">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-266">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="9c86b-267">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-267">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="9c86b-268">ドライブあたりのコンプライアンスの状態 (後の表を参照) が、異なるコンプライアンスの状態を示している可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-268">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="9c86b-269">ただし、このフィールドは、指定したポリシーに準拠したコンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-269">However, this field represents that compliance state in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-270">オペレーティングシステムのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-270">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-271">MBAM で管理されているオペレーティングシステムのコンプライアンスの状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-271">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="9c86b-272">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-272">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-273">固定データドライブのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="9c86b-273">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-274">MBAM で管理されている固定データドライブのコンプライアンスステータス。</span><span class="sxs-lookup"><span data-stu-id="9c86b-274">Compliance status of the fixed data drive that is managed by MBAM.</span></span> <span data-ttu-id="9c86b-275">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="9c86b-275">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-276">最終更新日</span><span class="sxs-lookup"><span data-stu-id="9c86b-276">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-277">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-277">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="9c86b-278">連絡先の頻度は、グループポリシー設定を通じて構成できます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-278">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-279">除外</span><span class="sxs-lookup"><span data-stu-id="9c86b-279">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-280">ユーザーが除外されているか、非表示になっているかを BitLocker ポリシーから除外するかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-280">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-281">除外対象ユーザー</span><span class="sxs-lookup"><span data-stu-id="9c86b-281">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-282">BitLocker ポリシーから除外されているユーザー。</span><span class="sxs-lookup"><span data-stu-id="9c86b-282">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-283">免税日</span><span class="sxs-lookup"><span data-stu-id="9c86b-283">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-284">免税が付与された日付。</span><span class="sxs-lookup"><span data-stu-id="9c86b-284">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-285">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="9c86b-285">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-286">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="9c86b-286">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-287">ポリシー暗号強度</span><span class="sxs-lookup"><span data-stu-id="9c86b-287">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-288">MBAM ポリシー仕様の間に管理者によって選択された暗号強度 (例: ディフューザー付きの128ビット)。</span><span class="sxs-lookup"><span data-stu-id="9c86b-288">Cipher strength selected by the Administrator during the MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-289">ポリシー: オペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="9c86b-289">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-290">オペレーティングシステムと適切なプロテクターの種類に対して暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-290">Indicates if encryption is required for the operating system and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-291">ポリシー: 固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="9c86b-291">Policy: Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-292">固定データドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-292">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-293">製造元</span><span class="sxs-lookup"><span data-stu-id="9c86b-293">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-294">コンピューターの BIOS に表示されるコンピューターの製造元名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-294">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-295">モデル</span><span class="sxs-lookup"><span data-stu-id="9c86b-295">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-296">コンピューターの BIOS に表示されるコンピューターの製造元のモデル名。</span><span class="sxs-lookup"><span data-stu-id="9c86b-296">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-297">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="9c86b-297">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-298">MBAM で管理されているコンピューター上の既知のユーザー。</span><span class="sxs-lookup"><span data-stu-id="9c86b-298">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="9c86b-299">BitLocker コンピューターのコンプライアンスレポート: コンピューターのボリュームフィールド</span><span class="sxs-lookup"><span data-stu-id="9c86b-299">BitLocker Computer Compliance Report: Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c86b-300">列名</span><span class="sxs-lookup"><span data-stu-id="9c86b-300">Column Name</span></span></th>
<th align="left"><span data-ttu-id="9c86b-301">説明</span><span class="sxs-lookup"><span data-stu-id="9c86b-301">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-302">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="9c86b-302">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-303">ユーザーが特定のドライブに割り当てたコンピューターのドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-303">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-304">ドライブの種類</span><span class="sxs-lookup"><span data-stu-id="9c86b-304">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-305">ドライブの種類。</span><span class="sxs-lookup"><span data-stu-id="9c86b-305">Type of drive.</span></span> <span data-ttu-id="9c86b-306">有効な値は、オペレーティングシステムドライブと固定データドライブです。</span><span class="sxs-lookup"><span data-stu-id="9c86b-306">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="9c86b-307">これらは論理ボリュームではなく物理ドライブです。</span><span class="sxs-lookup"><span data-stu-id="9c86b-307">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-308">暗号強度</span><span class="sxs-lookup"><span data-stu-id="9c86b-308">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-309">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="9c86b-309">Cipher strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-310">プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="9c86b-310">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-311">オペレーティングシステムまたは固定データドライブの暗号化に使用するポリシーを通じて選択されたプロテクターの種類。</span><span class="sxs-lookup"><span data-stu-id="9c86b-311">Type of protector selected through the policy used to encrypt an operating system or fixed data drive.</span></span> <span data-ttu-id="9c86b-312">オペレーティングシステムの有効なプロテクターの種類は、TPM または TPM + PIN です。</span><span class="sxs-lookup"><span data-stu-id="9c86b-312">The valid protector types for an operating system are TPM or TPM+PIN.</span></span> <span data-ttu-id="9c86b-313">固定データドライブの有効なプロテクター型はパスワードです。</span><span class="sxs-lookup"><span data-stu-id="9c86b-313">The valid protector type for a fixed data drive is a password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c86b-314">プロテクターの状態</span><span class="sxs-lookup"><span data-stu-id="9c86b-314">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-315">MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="9c86b-315">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="9c86b-316">有効な状態は、オンまたはオフです。</span><span class="sxs-lookup"><span data-stu-id="9c86b-316">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c86b-317">暗号化の状態</span><span class="sxs-lookup"><span data-stu-id="9c86b-317">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c86b-318">ドライブの暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="9c86b-318">Encryption state of the drive.</span></span> <span data-ttu-id="9c86b-319">有効な状態は、暗号化され、暗号化されず、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="9c86b-319">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9c86b-320">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c86b-320">Related topics</span></span>


[<span data-ttu-id="9c86b-321">MBAM 2.5 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="9c86b-321">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## <span data-ttu-id="9c86b-322">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-322">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9c86b-323">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-323">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9c86b-324">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="9c86b-324">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





