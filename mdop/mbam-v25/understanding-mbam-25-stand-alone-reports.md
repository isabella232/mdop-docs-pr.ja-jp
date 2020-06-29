---
title: MBAM 2.5 スタンドアロン レポートについて
description: MBAM 2.5 スタンドアロン レポートについて
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812778"
---
# <span data-ttu-id="23e04-103">MBAM 2.5 スタンドアロン レポートについて</span><span class="sxs-lookup"><span data-stu-id="23e04-103">Understanding MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="23e04-104">このトピックでは、スタンドアロントポロジで Microsoft BitLocker の管理と監視 (MBAM) を実行しているときに使用できるレポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="23e04-104">This topic describes the reports that are available when you are running Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology.</span></span>

**<span data-ttu-id="23e04-105">注</span><span class="sxs-lookup"><span data-stu-id="23e04-105">Note</span></span>**  
<span data-ttu-id="23e04-106">Configuration Manager の統合トポロジで MBAM を実行している場合は、MBAM からではなく、Configuration Manager からレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="23e04-106">If you are running MBAM with the Configuration Manager Integration topology, you generate reports from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="23e04-107">これらのレポートの詳細については[、「Configuration Manager の統合トポロジの MBAM 2.5 レポートを表示](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-107">See [Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md) for more information about these reports.</span></span>



## <span data-ttu-id="23e04-108">MBAM 単体のトポロジレポートについて</span><span class="sxs-lookup"><span data-stu-id="23e04-108">Understanding the MBAM Stand-alone topology reports</span></span>


<span data-ttu-id="23e04-109">MBAM には、組織で BitLocker のコンプライアンスを監視するために使用できる、次の3種類のレポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="23e04-109">MBAM provides three report types that you can use to monitor your organization for BitLocker compliance:</span></span>

-   [<span data-ttu-id="23e04-110">エンタープライズコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="23e04-110">Enterprise Compliance Report</span></span>](#bkmk-enterprisecompliance)

-   [<span data-ttu-id="23e04-111">コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="23e04-111">Computer Compliance Report</span></span>](#bkmk-compliance)

-   [<span data-ttu-id="23e04-112">回復監査レポート</span><span class="sxs-lookup"><span data-stu-id="23e04-112">Recovery Audit Report</span></span>](#bkmk-recovery)

<span data-ttu-id="23e04-113">単体のトポロジで MBAM を実行しているときに MBAM レポートにアクセスするには、web ブラウザーを開いて、[管理と監視] Web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="23e04-113">To access MBAM reports when you are running MBAM in the Stand-alone topology, open a web browser, and then open the Administration and Monitoring Website.</span></span> <span data-ttu-id="23e04-114">左側のメニューバーで [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="23e04-114">Select **Reports** in the left menu bar.</span></span> <span data-ttu-id="23e04-115">上部のメニューバーで、生成するレポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="23e04-115">From the top menu bar, select the kind of report that you want to generate.</span></span> <span data-ttu-id="23e04-116">これらのレポートを生成する方法について詳しくは、「 [MBAM 2.5 単体レポートの生成](generating-mbam-25-stand-alone-reports.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="23e04-116">For more information about generating these reports, see [Generating MBAM 2.5 Stand-alone Reports](generating-mbam-25-stand-alone-reports.md).</span></span>

### <a href="" id="bkmk-enterprisecompliance"></a><span data-ttu-id="23e04-117">エンタープライズコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="23e04-117">Enterprise Compliance Report</span></span>

<span data-ttu-id="23e04-118">このレポートの種類を使用して、組織内の全体的な BitLocker のコンプライアンスに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="23e04-118">Use this report type to collect information about overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="23e04-119">組織内のコンピューターのコンプライアンスの状態とエラー状態について詳しく知るには、フィルターを使用して検索結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="23e04-119">You can use filters to narrow your search results to learn more about the compliance state and error status of computers in your organization.</span></span>

**<span data-ttu-id="23e04-120">エンタープライズコンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="23e04-120">Enterprise Compliance Overview</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23e04-121">列名</span><span class="sxs-lookup"><span data-stu-id="23e04-121">Column Name</span></span></th>
<th align="left"><span data-ttu-id="23e04-122">説明</span><span class="sxs-lookup"><span data-stu-id="23e04-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-123">管理されたコンピューター</span><span class="sxs-lookup"><span data-stu-id="23e04-123">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-124">MBAM で管理されているコンピューターの数です。</span><span class="sxs-lookup"><span data-stu-id="23e04-124">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-125">% 準拠</span><span class="sxs-lookup"><span data-stu-id="23e04-125">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-126">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-126">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-127">% 非準拠率</span><span class="sxs-lookup"><span data-stu-id="23e04-127">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-128">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-128">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-129">% 免税</span><span class="sxs-lookup"><span data-stu-id="23e04-129">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-130">BitLocker 暗号化要件から除外されたコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-130">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-131">% 免税以外</span><span class="sxs-lookup"><span data-stu-id="23e04-131">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-132">BitLocker 暗号化要件の対象から除外されていないコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-132">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-133">仕様</span><span class="sxs-lookup"><span data-stu-id="23e04-133">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-134">企業内の準拠しているコンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-134">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-135">準拠していない</span><span class="sxs-lookup"><span data-stu-id="23e04-135">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-136">企業内の非準拠コンピューターの割合。</span><span class="sxs-lookup"><span data-stu-id="23e04-136">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-137">適用除外</span><span class="sxs-lookup"><span data-stu-id="23e04-137">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-138">BitLocker 暗号化要件から除外されたコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="23e04-138">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-139">非免税</span><span class="sxs-lookup"><span data-stu-id="23e04-139">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-140">BitLocker 暗号化要件の対象から除外されていないコンピューターの合計数。</span><span class="sxs-lookup"><span data-stu-id="23e04-140">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="23e04-141">エンタープライズコンプライアンスコンピューターの詳細</span><span class="sxs-lookup"><span data-stu-id="23e04-141">Enterprise Compliance Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23e04-142">列名</span><span class="sxs-lookup"><span data-stu-id="23e04-142">Column Name</span></span></th>
<th align="left"><span data-ttu-id="23e04-143">説明</span><span class="sxs-lookup"><span data-stu-id="23e04-143">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-144">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="23e04-144">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-145">MBAM で管理されるユーザー指定の DNS 名。</span><span class="sxs-lookup"><span data-stu-id="23e04-145">User-specified DNS name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-146">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="23e04-146">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-147">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="23e04-147">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-148">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="23e04-148">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-149">コンピューターに対して指定されたポリシーに従って、コンピューターのコンプライアンスの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="23e04-149">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="23e04-150">状態は準拠していないため、準拠しています。</span><span class="sxs-lookup"><span data-stu-id="23e04-150">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="23e04-151">コンプライアンスの状態を解釈する方法の詳細については、次の「企業コンプライアンスレポートのコンプライアンス状態」の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-151">See the following Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-152">除外</span><span class="sxs-lookup"><span data-stu-id="23e04-152">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-153">このコンピューターが BitLocker ポリシーから除外されているかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="23e04-153">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-154">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="23e04-154">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-155">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="23e04-155">Error and status messages about the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-156">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="23e04-156">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-157">コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="23e04-157">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="23e04-158">コンタクトの周波数は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="23e04-158">The contact frequency is configurable.</span></span> <span data-ttu-id="23e04-159">詳細については、「MBAM グループポリシーの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-159">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a><span data-ttu-id="23e04-160">コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="23e04-160">Computer Compliance Report</span></span>

<span data-ttu-id="23e04-161">このレポートの種類を使用して、コンピューターまたはユーザーに固有の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="23e04-161">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="23e04-162">このレポートを表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="23e04-162">View this report by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="23e04-163">このレポートには、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23e04-163">This report shows detailed encryption information about each drive (operating system and fixed data drives) on a computer.</span></span> <span data-ttu-id="23e04-164">また、コンピューター上の各ドライブの種類に適用されるポリシーを示します。</span><span class="sxs-lookup"><span data-stu-id="23e04-164">It also indicates the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="23e04-165">各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。</span><span class="sxs-lookup"><span data-stu-id="23e04-165">To view the details of each drive, expand the Computer Name entry.</span></span>

**<span data-ttu-id="23e04-166">注</span><span class="sxs-lookup"><span data-stu-id="23e04-166">Note</span></span>**  
<span data-ttu-id="23e04-167">リムーバブルデータボリュームの暗号化の状態は、このレポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="23e04-167">Removable Data Volume encryption status is not shown in this report.</span></span>



**<span data-ttu-id="23e04-168">コンピューターのコンプライアンスレポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="23e04-168">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23e04-169">列名</span><span class="sxs-lookup"><span data-stu-id="23e04-169">Column Name</span></span></th>
<th align="left"><span data-ttu-id="23e04-170">説明</span><span class="sxs-lookup"><span data-stu-id="23e04-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-171">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="23e04-171">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-172">MBAM で管理されるユーザー指定の DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="23e04-172">User-specified DNS computer name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-173">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="23e04-173">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-174">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="23e04-174">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-175">コンピュータの種類</span><span class="sxs-lookup"><span data-stu-id="23e04-175">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-176">コンピューターの種類。</span><span class="sxs-lookup"><span data-stu-id="23e04-176">Type of computer.</span></span> <span data-ttu-id="23e04-177">有効な型は、ポータブルでもポータブルでもありません。</span><span class="sxs-lookup"><span data-stu-id="23e04-177">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-178">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="23e04-178">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-179">MBAM で管理されているクライアントコンピューターで検出されたオペレーティングシステムの種類。</span><span class="sxs-lookup"><span data-stu-id="23e04-179">Operating system type found on the client computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-180">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="23e04-180">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-181">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="23e04-181">Overall compliance status of the computer that is managed by MBAM.</span></span> <span data-ttu-id="23e04-182">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="23e04-182">Valid states are Compliant and Noncompliant.</span></span></p>
<p><span data-ttu-id="23e04-183">ドライブあたりのコンプライアンスの状態 (次の表を参照) は、異なるコンプライアンスの状態を示している可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-183">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="23e04-184">ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="23e04-184">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-185">ポリシー暗号強度</span><span class="sxs-lookup"><span data-stu-id="23e04-185">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-186">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度 (例: ディフューザー付きの128ビット)。</span><span class="sxs-lookup"><span data-stu-id="23e04-186">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-187">ポリシーのオペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="23e04-187">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-188">オペレーティングシステムに暗号化が必要かどうかを示します。適切なプロテクターの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="23e04-188">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-189">ポリシー-固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="23e04-189">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-190">固定データドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23e04-190">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-191">ポリシーのリムーバブルデータドライブ</span><span class="sxs-lookup"><span data-stu-id="23e04-191">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-192">リムーバブルドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="23e04-192">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-193">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="23e04-193">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-194">MBAM で管理されているコンピューター上の既知のユーザー。</span><span class="sxs-lookup"><span data-stu-id="23e04-194">Known users on the computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-195">除外</span><span class="sxs-lookup"><span data-stu-id="23e04-195">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-196">このコンピューターが BitLocker ポリシーから除外されているかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="23e04-196">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-197">製造元</span><span class="sxs-lookup"><span data-stu-id="23e04-197">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-198">コンピューターの BIOS に表示されるコンピューターの製造元名。</span><span class="sxs-lookup"><span data-stu-id="23e04-198">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-199">モデル</span><span class="sxs-lookup"><span data-stu-id="23e04-199">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-200">コンピューターの BIOS に表示されたコンピューターの製造元のモデル名。</span><span class="sxs-lookup"><span data-stu-id="23e04-200">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-201">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="23e04-201">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-202">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="23e04-202">Error and status messages about the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-203">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="23e04-203">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-204">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="23e04-204">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="23e04-205">コンタクトの周波数は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="23e04-205">The contact frequency is configurable.</span></span> <span data-ttu-id="23e04-206">詳細については、「MBAM グループポリシーの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-206">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="23e04-207">コンピューターのコンプライアンスレポートのドライブフィールド</span><span class="sxs-lookup"><span data-stu-id="23e04-207">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23e04-208">列名</span><span class="sxs-lookup"><span data-stu-id="23e04-208">Column Name</span></span></th>
<th align="left"><span data-ttu-id="23e04-209">説明</span><span class="sxs-lookup"><span data-stu-id="23e04-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-210">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="23e04-210">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-211">ユーザーが特定のドライブに割り当てたコンピューターのドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="23e04-211">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-212">ドライブの種類</span><span class="sxs-lookup"><span data-stu-id="23e04-212">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-213">ドライブの種類。</span><span class="sxs-lookup"><span data-stu-id="23e04-213">Type of drive.</span></span> <span data-ttu-id="23e04-214">有効な値は、オペレーティングシステムドライブと固定データドライブです。</span><span class="sxs-lookup"><span data-stu-id="23e04-214">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="23e04-215">これらは論理ボリュームではなく物理ドライブです。</span><span class="sxs-lookup"><span data-stu-id="23e04-215">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-216">暗号強度</span><span class="sxs-lookup"><span data-stu-id="23e04-216">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-217">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="23e04-217">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-218">プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="23e04-218">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-219">オペレーティングシステムまたは固定データボリュームの暗号化に使用するグループポリシー設定によって選択されたプロテクターの種類。</span><span class="sxs-lookup"><span data-stu-id="23e04-219">Type of protector selected through the Group Policy setting used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-220">プロテクターの状態</span><span class="sxs-lookup"><span data-stu-id="23e04-220">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-221">MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="23e04-221">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="23e04-222">有効な状態は、オンまたはオフです。</span><span class="sxs-lookup"><span data-stu-id="23e04-222">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-223">暗号化の状態</span><span class="sxs-lookup"><span data-stu-id="23e04-223">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-224">ドライブの暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="23e04-224">Encryption state of the drive.</span></span> <span data-ttu-id="23e04-225">有効な状態は、暗号化され、暗号化されず、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="23e04-225">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-226">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="23e04-226">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-227">ドライブがポリシーに準拠しているかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="23e04-227">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="23e04-228">状態は準拠していないため、準拠しています。</span><span class="sxs-lookup"><span data-stu-id="23e04-228">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-229">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="23e04-229">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-230">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="23e04-230">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-recovery"></a><span data-ttu-id="23e04-231">回復監査レポート</span><span class="sxs-lookup"><span data-stu-id="23e04-231">Recovery Audit Report</span></span>

<span data-ttu-id="23e04-232">このレポートの種類を使用して、BitLocker 回復キーへのアクセスを要求したユーザーを監査します。</span><span class="sxs-lookup"><span data-stu-id="23e04-232">Use this report type to audit users who have requested access to BitLocker recovery keys.</span></span> <span data-ttu-id="23e04-233">レポートには、目的のフィルター条件に基づいて、いくつかのフィルターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="23e04-233">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="23e04-234">特定の種類のユーザー (ヘルプデスクユーザーまたはエンドユーザー) に対して、要求が失敗したか、成功したか、要求された特定の種類のキー、取得した日付範囲に基づいてフィルターを適用できます。</span><span class="sxs-lookup"><span data-stu-id="23e04-234">You can filter on a specific type of user (a Help Desk user or an end user), whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span>

**<span data-ttu-id="23e04-235">回復監査レポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="23e04-235">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23e04-236">列名</span><span class="sxs-lookup"><span data-stu-id="23e04-236">Column Name</span></span></th>
<th align="left"><span data-ttu-id="23e04-237">説明</span><span class="sxs-lookup"><span data-stu-id="23e04-237">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-238">日付と時刻を要求する</span><span class="sxs-lookup"><span data-stu-id="23e04-238">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-239">エンドユーザーまたはヘルプデスクのユーザーによってキーの取得要求が行われた日時。</span><span class="sxs-lookup"><span data-stu-id="23e04-239">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-240">監査要求ソース</span><span class="sxs-lookup"><span data-stu-id="23e04-240">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-241">要求が開始されたサイト。</span><span class="sxs-lookup"><span data-stu-id="23e04-241">The site from which the request was initiated.</span></span> <span data-ttu-id="23e04-242">このエントリには、 <strong> セルフサービスポータル </strong> または <strong> ヘルプデスクの2つの値のいずれかが表示され </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="23e04-242">This entry will have one of two values: <strong>Self-Service Portal</strong> or <strong>Helpdesk</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-243">リクエストの状態</span><span class="sxs-lookup"><span data-stu-id="23e04-243">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-244">リクエストのステータス。</span><span class="sxs-lookup"><span data-stu-id="23e04-244">Status of the request.</span></span> <span data-ttu-id="23e04-245">有効な状態 (キーが取得された)、または失敗 (キーは取得されませんでした)。</span><span class="sxs-lookup"><span data-stu-id="23e04-245">Valid statuses are Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-246">ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="23e04-246">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-247">キーの取得要求を開始したヘルプデスクのユーザー。</span><span class="sxs-lookup"><span data-stu-id="23e04-247">Help Desk user who initiated the request for key retrieval.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="23e04-248">注</span><span class="sxs-lookup"><span data-stu-id="23e04-248">Note</span></span></strong><br/><p><span data-ttu-id="23e04-249">上級のヘルプデスクユーザーがエンドユーザーを指定せずにキーを回復した場合、[ <strong> 終了ユーザー </strong> ] フィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="23e04-249">If an Advanced Helpdesk User recovers the key without specifying the end user, the <strong>End User</strong> field will be blank.</span></span> <span data-ttu-id="23e04-250">標準のヘルプデスクユーザーは、エンドユーザーを指定する必要があります。そのユーザーはこのフィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="23e04-250">A standard Helpdesk User must specify the end user, and that user will appear in this field.</span></span></p>
<p><span data-ttu-id="23e04-251">セルフサービスポータルによる回復では、このフィールドと [エンドユーザー] フィールドの両方に、要求側のエンドユーザーの一覧が表示され <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="23e04-251">A recovery via the Self-Service Portal will list the requesting end user both in this field and in the <strong>End User</strong> field.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-252">エンドユーザー</span><span class="sxs-lookup"><span data-stu-id="23e04-252">End User</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-253">キーの取得要求を開始したエンドユーザー。</span><span class="sxs-lookup"><span data-stu-id="23e04-253">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-254">コンピューター</span><span class="sxs-lookup"><span data-stu-id="23e04-254">Computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-255">回復されたコンピューターのコンピューター名。</span><span class="sxs-lookup"><span data-stu-id="23e04-255">Computer name of the computer that was recovered.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23e04-256">キーの種類</span><span class="sxs-lookup"><span data-stu-id="23e04-256">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-257">ヘルプデスクユーザーまたはエンドユーザーによって要求されたキーの種類。</span><span class="sxs-lookup"><span data-stu-id="23e04-257">Type of key that was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="23e04-258">MBAM で収集されるキーには、次の3種類があります。</span><span class="sxs-lookup"><span data-stu-id="23e04-258">The three types of keys that MBAM collects are:</span></span></p>
<ul>
<li><p><span data-ttu-id="23e04-259">回復キーパスワード (回復モードでコンピューターを回復するために使用)</span><span class="sxs-lookup"><span data-stu-id="23e04-259">Recovery Key Password (used to recover a computer in recovery mode)</span></span></p></li>
<li><p><span data-ttu-id="23e04-260">回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復するために使用されます)</span><span class="sxs-lookup"><span data-stu-id="23e04-260">Recovery Key ID (used to recover a computer in recovery mode on behalf of another user)</span></span></p></li>
<li><p><span data-ttu-id="23e04-261">TPM パスワードハッシュ (ロックされている TPM を使用してコンピューターを回復するために使用)</span><span class="sxs-lookup"><span data-stu-id="23e04-261">TPM Password Hash (used to recover a computer with a locked TPM)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23e04-262">理由の説明</span><span class="sxs-lookup"><span data-stu-id="23e04-262">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="23e04-263">理由指定されたキーの種類が、ヘルプデスクユーザーまたはエンドユーザーによって要求された理由です。</span><span class="sxs-lookup"><span data-stu-id="23e04-263">Reason the specified key type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="23e04-264">この理由は、ドライブの回復で指定され、管理と監視の Web サイトの TPM 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="23e04-264">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring Website.</span></span> <span data-ttu-id="23e04-265">有効なエントリは、ユーザーが入力したテキスト、または次の理由コードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="23e04-265">The valid entries are user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="23e04-266">オペレーティングシステムのブート順序が変更されました</span><span class="sxs-lookup"><span data-stu-id="23e04-266">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="23e04-267">BIOS が変更されました</span><span class="sxs-lookup"><span data-stu-id="23e04-267">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="23e04-268">オペレーティングシステムファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="23e04-268">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="23e04-269">失われたスタートアップキー</span><span class="sxs-lookup"><span data-stu-id="23e04-269">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="23e04-270">PIN を紛失</span><span class="sxs-lookup"><span data-stu-id="23e04-270">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="23e04-271">TPM リセット</span><span class="sxs-lookup"><span data-stu-id="23e04-271">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="23e04-272">パスフレーズの紛失</span><span class="sxs-lookup"><span data-stu-id="23e04-272">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="23e04-273">紛失したスマートカード</span><span class="sxs-lookup"><span data-stu-id="23e04-273">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="23e04-274">PIN のロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="23e04-274">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="23e04-275">TPM を有効にする</span><span class="sxs-lookup"><span data-stu-id="23e04-275">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="23e04-276">TPM をオフにする</span><span class="sxs-lookup"><span data-stu-id="23e04-276">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="23e04-277">TPM パスワードを変更する</span><span class="sxs-lookup"><span data-stu-id="23e04-277">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="23e04-278">TPM をクリアする</span><span class="sxs-lookup"><span data-stu-id="23e04-278">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="23e04-279">注</span><span class="sxs-lookup"><span data-stu-id="23e04-279">Note</span></span>**  
<span data-ttu-id="23e04-280">レポートの結果をファイルに保存するには、[**レポート**] メニューバーの [**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="23e04-280">Report results can be saved to a file by clicking the **Export** button on the **Reports** menu bar.</span></span>




## <span data-ttu-id="23e04-281">関連トピック</span><span class="sxs-lookup"><span data-stu-id="23e04-281">Related topics</span></span>


[<span data-ttu-id="23e04-282">MBAM 2.5 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="23e04-282">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="23e04-283">MBAM 2.5 スタンドアロン レポートの生成</span><span class="sxs-lookup"><span data-stu-id="23e04-283">Generating MBAM 2.5 Stand-alone Reports</span></span>](generating-mbam-25-stand-alone-reports.md)



## <span data-ttu-id="23e04-284">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="23e04-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="23e04-285">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="23e04-285">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="23e04-286">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="23e04-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





