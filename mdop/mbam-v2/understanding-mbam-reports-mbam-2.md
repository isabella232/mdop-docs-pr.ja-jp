---
title: MBAM レポートの概要
description: MBAM レポートの概要
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823814"
---
# <span data-ttu-id="b476d-103">MBAM レポートの概要</span><span class="sxs-lookup"><span data-stu-id="b476d-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="b476d-104">Microsoft BitLocker の管理と監視 (MBAM) をインストールしたときに単体のトポロジを選んだ場合は、MBAM でさまざまなレポートを実行して、BitLocker の使用状況とコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="b476d-104">If you chose the Stand-alone topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), you can run different reports in MBAM to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="b476d-105">MBAM は、管理するすべてのコンピューターとデバイスに関するコンプライアンスおよびその他の情報を報告します。</span><span class="sxs-lookup"><span data-stu-id="b476d-105">MBAM reports compliance and other information about all of the computers and devices it manages.</span></span> <span data-ttu-id="b476d-106">このトピックの情報は、企業および個々のコンピューターのコンプライアンスおよび主要な回復アクティビティのための Microsoft BitLocker の管理および監視レポートの理解に役立つために使用できます。</span><span class="sxs-lookup"><span data-stu-id="b476d-106">The information in this topic can be used to help you understand the Microsoft BitLocker Administration and Monitoring reports for enterprise and individual computer compliance and for key recovery activity.</span></span>

<span data-ttu-id="b476d-107">**注** Microsoft BitLocker の管理と監視 (MBAM) をインストールしたときに Configuration Manager トポロジを選択した場合、レポートは MBAM からではなく構成マネージャーから生成されます。</span><span class="sxs-lookup"><span data-stu-id="b476d-107">**Note** If you chose the Configuration Manager topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), reports are generated from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="b476d-108">構成マネージャーから実行されるレポートの詳細については、「 [Configuration manager での MBAM レポートに](understanding-mbam-reports-in-configuration-manager.md)ついて」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b476d-108">For more information about reports that are run from Configuration Manager, see [Understanding MBAM Reports in Configuration Manager](understanding-mbam-reports-in-configuration-manager.md).</span></span>

 

## <span data-ttu-id="b476d-109">レポートについて</span><span class="sxs-lookup"><span data-stu-id="b476d-109">Understanding Reports</span></span>


<span data-ttu-id="b476d-110">Microsoft BitLocker の管理と監視のレポート機能にアクセスするには、web ブラウザーを開き、管理と監視の web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="b476d-110">To access the Reports feature of Microsoft BitLocker Administration and Monitoring, open a web browser and open the Administration and Monitoring website.</span></span> <span data-ttu-id="b476d-111">左側のメニューバーで [**レポート**] を選択し、トップメニューバーで、生成するレポートの種類を選択します。</span><span class="sxs-lookup"><span data-stu-id="b476d-111">Select **Reports** in the left menu bar and then select from the top menu bar the kind of report that you want to generate.</span></span>

### <span data-ttu-id="b476d-112">エンタープライズコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="b476d-112">Enterprise Compliance Report</span></span>

<span data-ttu-id="b476d-113">このレポートの種類を使用して、組織内の全体的な BitLocker のコンプライアンスに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="b476d-113">Use this report type to collect information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="b476d-114">さまざまなフィルターを使って、検索結果をコンプライアンスの状態やエラー状態に絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="b476d-114">You can use different filters to narrow your search results to Compliance state and Error status.</span></span> <span data-ttu-id="b476d-115">レポート情報は6時間ごとに更新されます。</span><span class="sxs-lookup"><span data-stu-id="b476d-115">The report information is updated every six hours.</span></span>

**<span data-ttu-id="b476d-116">エンタープライズコンプライアンスレポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="b476d-116">Enterprise Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b476d-117">列名</span><span class="sxs-lookup"><span data-stu-id="b476d-117">Column Name</span></span></th>
<th align="left"><span data-ttu-id="b476d-118">説明</span><span class="sxs-lookup"><span data-stu-id="b476d-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-119">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="b476d-119">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-120">MBAM で管理されているユーザー指定の DNS 名。</span><span class="sxs-lookup"><span data-stu-id="b476d-120">User-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-121">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="b476d-121">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-122">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="b476d-122">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-123">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-123">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-124">コンピューターに対して指定されたポリシーに従って、コンピューターのコンプライアンスの状態を指定します。</span><span class="sxs-lookup"><span data-stu-id="b476d-124">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="b476d-125">状態は準拠していないため、準拠しています。</span><span class="sxs-lookup"><span data-stu-id="b476d-125">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="b476d-126">コンプライアンスの状態を解釈する方法について詳しくは、「エンタープライズコンプライアンスレポートのコンプライアンス状態」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b476d-126">See the Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-127">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="b476d-127">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-128">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b476d-128">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-129">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="b476d-129">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-130">コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="b476d-130">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="b476d-131">連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="b476d-131">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="b476d-132">企業のコンプライアンスレポートのコンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-132">Enterprise Compliance Report Compliance States</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b476d-133">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-133">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="b476d-134">除外</span><span class="sxs-lookup"><span data-stu-id="b476d-134">Exemption</span></span></th>
<th align="left"><span data-ttu-id="b476d-135">説明</span><span class="sxs-lookup"><span data-stu-id="b476d-135">Description</span></span></th>
<th align="left"><span data-ttu-id="b476d-136">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="b476d-136">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-137">互換性</span><span class="sxs-lookup"><span data-stu-id="b476d-137">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-138">非課税</span><span class="sxs-lookup"><span data-stu-id="b476d-138">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-139">指定したポリシーに従って、コンピューターが準拠していません。</span><span class="sxs-lookup"><span data-stu-id="b476d-139">The computer is noncompliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-140">[ <strong> コンピューター名 </strong> ] をクリックして、各ドライブの状態が指定したポリシーに準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b476d-140">Expand the Computer Compliance Report details by clicking <strong>Computer Name</strong>, and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="b476d-141">暗号化の状態にコンピューターが暗号化されていないことが示されている場合は、暗号化が処理中であるか、またはコンピューターにエラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="b476d-141">If the encryption state indicates that the computer is not encrypted, encryption may be in process, or there is an error on the computer.</span></span> <span data-ttu-id="b476d-142">エラーがない場合、原因としては、コンピューターがまだ暗号化状態の接続または確立のプロセスを行っていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="b476d-142">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="b476d-143">後でもう一度確認して、状態が変わっていないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="b476d-143">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-144">仕様</span><span class="sxs-lookup"><span data-stu-id="b476d-144">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-145">非課税</span><span class="sxs-lookup"><span data-stu-id="b476d-145">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-146">指定したポリシーに従って、コンピューターは準拠しています。</span><span class="sxs-lookup"><span data-stu-id="b476d-146">The computer is compliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-147">操作は必要ありません。コンピューターのコンプライアンスレポートを表示することで、コンピューターの状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="b476d-147">No action needed; the state of the computer can be confirmed by viewing the Computer Compliance Report.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b476d-148">コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="b476d-148">Computer Compliance Report</span></span>

<span data-ttu-id="b476d-149">このレポートの種類を使用して、コンピューターまたはユーザーに固有の情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="b476d-149">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="b476d-150">このレポートを表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="b476d-150">This report can be viewed by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="b476d-151">コンピューターのコンプライアンスレポートは、コンピューター上の各ドライブ (オペレーティングシステムと固定データドライブ) に関する詳細な暗号化情報を提供します。また、コンピューター上の各ドライブの種類に適用されるポリシーを示しています。</span><span class="sxs-lookup"><span data-stu-id="b476d-151">The Computer Compliance Report provides detailed encryption information about each drive (operating system and fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="b476d-152">各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。</span><span class="sxs-lookup"><span data-stu-id="b476d-152">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="b476d-153">**注** リムーバブルデータボリュームの暗号化の状態は、レポートには表示されません。</span><span class="sxs-lookup"><span data-stu-id="b476d-153">**Note** Removable Data Volume encryption status will not be shown in the report.</span></span>

 

**<span data-ttu-id="b476d-154">コンピューターのコンプライアンスレポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="b476d-154">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b476d-155">列名</span><span class="sxs-lookup"><span data-stu-id="b476d-155">Column Name</span></span></th>
<th align="left"><span data-ttu-id="b476d-156">説明</span><span class="sxs-lookup"><span data-stu-id="b476d-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-157">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="b476d-157">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-158">MBAM で管理されている、ユーザーが指定した DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="b476d-158">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-159">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="b476d-159">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-160">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="b476d-160">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-161">コンピュータの種類</span><span class="sxs-lookup"><span data-stu-id="b476d-161">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-162">コンピューターの種類。</span><span class="sxs-lookup"><span data-stu-id="b476d-162">Type of computer.</span></span> <span data-ttu-id="b476d-163">有効な型は、ポータブルでもポータブルでもありません。</span><span class="sxs-lookup"><span data-stu-id="b476d-163">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-164">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b476d-164">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-165">MBAM 管理クライアントコンピューターで検出されたオペレーティングシステムの種類。</span><span class="sxs-lookup"><span data-stu-id="b476d-165">Operating system type found on the MBAM-managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-166">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-166">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-167">MBAM で管理されているコンピューターの全体のコンプライアンス状態。</span><span class="sxs-lookup"><span data-stu-id="b476d-167">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="b476d-168">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="b476d-168">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="b476d-169">ドライブあたりのコンプライアンスの状態 (次の表を参照) は、異なるコンプライアンスの状態を示している可能性があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="b476d-169">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="b476d-170">ただし、このフィールドは、指定したポリシーに従って、コンプライアンスの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="b476d-170">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-171">ポリシー暗号強度</span><span class="sxs-lookup"><span data-stu-id="b476d-171">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-172">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度 (例: ディフューザー付きの128ビット)。</span><span class="sxs-lookup"><span data-stu-id="b476d-172">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-173">ポリシーのオペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="b476d-173">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-174">オペレーティングシステムに暗号化が必要かどうかを示します。適切なプロテクターの種類が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b476d-174">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-175">ポリシー-固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="b476d-175">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-176">固定データドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b476d-176">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-177">ポリシーのリムーバブルデータドライブ</span><span class="sxs-lookup"><span data-stu-id="b476d-177">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-178">リムーバブルドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="b476d-178">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-179">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="b476d-179">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-180">MBAM で管理されているコンピューター上の既知のユーザー。</span><span class="sxs-lookup"><span data-stu-id="b476d-180">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-181">製造元</span><span class="sxs-lookup"><span data-stu-id="b476d-181">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-182">コンピューターの BIOS に表示されるコンピューターの製造元名。</span><span class="sxs-lookup"><span data-stu-id="b476d-182">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-183">モデル</span><span class="sxs-lookup"><span data-stu-id="b476d-183">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-184">コンピューターの BIOS に表示されたコンピューターの製造元のモデル名。</span><span class="sxs-lookup"><span data-stu-id="b476d-184">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-185">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="b476d-185">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-186">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b476d-186">Error and status messages of the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-187">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="b476d-187">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-188">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="b476d-188">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="b476d-189">連絡先の頻度は構成可能です (「MBAM ポリシー設定」をご覧ください)。</span><span class="sxs-lookup"><span data-stu-id="b476d-189">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="b476d-190">コンピューターのコンプライアンスレポートのドライブフィールド</span><span class="sxs-lookup"><span data-stu-id="b476d-190">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b476d-191">列名</span><span class="sxs-lookup"><span data-stu-id="b476d-191">Column Name</span></span></th>
<th align="left"><span data-ttu-id="b476d-192">説明</span><span class="sxs-lookup"><span data-stu-id="b476d-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-193">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="b476d-193">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-194">ユーザーが特定のドライブに割り当てたコンピューターのドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="b476d-194">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-195">ドライブの種類</span><span class="sxs-lookup"><span data-stu-id="b476d-195">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-196">ドライブの種類。</span><span class="sxs-lookup"><span data-stu-id="b476d-196">Type of drive.</span></span> <span data-ttu-id="b476d-197">有効な値は、オペレーティングシステムドライブと固定データドライブです。</span><span class="sxs-lookup"><span data-stu-id="b476d-197">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="b476d-198">これらは論理ボリュームではなく物理ドライブです。</span><span class="sxs-lookup"><span data-stu-id="b476d-198">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-199">暗号強度</span><span class="sxs-lookup"><span data-stu-id="b476d-199">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-200">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="b476d-200">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-201">プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="b476d-201">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-202">オペレーティングシステムまたは固定データボリュームの暗号化に使用されるポリシーによって選択されたプロテクターの種類。</span><span class="sxs-lookup"><span data-stu-id="b476d-202">Type of protector selected via the policy used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-203">プロテクターの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-203">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-204">MBAM で管理されているコンピューターが、ポリシーで指定されているプロテクターの種類を有効にしていることを示します。</span><span class="sxs-lookup"><span data-stu-id="b476d-204">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="b476d-205">有効な状態は、オンまたはオフです。</span><span class="sxs-lookup"><span data-stu-id="b476d-205">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-206">暗号化の状態</span><span class="sxs-lookup"><span data-stu-id="b476d-206">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-207">ドライブの暗号化の状態。</span><span class="sxs-lookup"><span data-stu-id="b476d-207">Encryption state of the drive.</span></span> <span data-ttu-id="b476d-208">有効な状態は、暗号化され、暗号化されず、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="b476d-208">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-209">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-209">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-210">ドライブがポリシーに準拠しているかどうかを示す状態。</span><span class="sxs-lookup"><span data-stu-id="b476d-210">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="b476d-211">状態は準拠していないため、準拠しています。</span><span class="sxs-lookup"><span data-stu-id="b476d-211">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-212">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="b476d-212">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-213">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="b476d-213">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b476d-214">回復監査レポート</span><span class="sxs-lookup"><span data-stu-id="b476d-214">Recovery Audit Report</span></span>

<span data-ttu-id="b476d-215">このレポートの種類を使用して、回復キーへのアクセスを要求したユーザーを監査します。</span><span class="sxs-lookup"><span data-stu-id="b476d-215">Use this report type to audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="b476d-216">レポートには、目的のフィルター条件に基づいて、いくつかのフィルターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="b476d-216">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="b476d-217">ユーザーは、ヘルプデスクユーザーまたはエンドユーザー、要求が失敗したか、成功したか、要求された特定の種類のキー、取得した日付の範囲など、特定の種類のユーザーに対してフィルター処理できます。</span><span class="sxs-lookup"><span data-stu-id="b476d-217">Users can filter on a specific type of user, either a Help Desk user or an end user, whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span> <span data-ttu-id="b476d-218">管理者は、必要に応じてコンテキストレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="b476d-218">The administrator can produce contextual reports based on need.</span></span>

**<span data-ttu-id="b476d-219">回復監査レポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="b476d-219">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b476d-220">列名</span><span class="sxs-lookup"><span data-stu-id="b476d-220">Column Name</span></span></th>
<th align="left"><span data-ttu-id="b476d-221">説明</span><span class="sxs-lookup"><span data-stu-id="b476d-221">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-222">日付と時刻を要求する</span><span class="sxs-lookup"><span data-stu-id="b476d-222">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-223">エンドユーザーまたはヘルプデスクのユーザーによってキーの取得要求が行われた日時。</span><span class="sxs-lookup"><span data-stu-id="b476d-223">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-224">リクエストの状態</span><span class="sxs-lookup"><span data-stu-id="b476d-224">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-225">リクエストのステータス。</span><span class="sxs-lookup"><span data-stu-id="b476d-225">Status of the request.</span></span> <span data-ttu-id="b476d-226">有効な状態は、成功したか (キーが取得された)、失敗した (キーが取得されなかった) かどうか。</span><span class="sxs-lookup"><span data-stu-id="b476d-226">Valid statuses are either Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-227">ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="b476d-227">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-228">キーの取得要求を開始したヘルプデスクユーザー。</span><span class="sxs-lookup"><span data-stu-id="b476d-228">Help Desk user that initiated the request for key retrieval.</span></span> <span data-ttu-id="b476d-229">注: ヘルプデスクのユーザーがエンドユーザーの代わりにキーを取得した場合、[エンドユーザー] フィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="b476d-229">Note: If the Help Desk user retrieves the key on behalf on an end-user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-230">ユーザー</span><span class="sxs-lookup"><span data-stu-id="b476d-230">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-231">キーの取得要求を開始したエンドユーザー。</span><span class="sxs-lookup"><span data-stu-id="b476d-231">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b476d-232">キーの種類</span><span class="sxs-lookup"><span data-stu-id="b476d-232">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-233">ヘルプデスクユーザーまたはエンドユーザーによって要求されたキーの種類。</span><span class="sxs-lookup"><span data-stu-id="b476d-233">Type of key that was requested by either the Help Desk user or the end user.</span></span> <span data-ttu-id="b476d-234">MBAM で収集される3種類のキーには、回復キーパスワード (回復モードでコンピューターを回復するために使用されます)、回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復する場合に使用)、TPM パスワードハッシュ (ロックされた TPM を使用してコンピューターを回復するために使用) があります。</span><span class="sxs-lookup"><span data-stu-id="b476d-234">The three types of keys that MBAM collects are: Recovery Key Password (used to recovery a computer in recovery mode), Recovery Key ID (used to recover a computer in recovery mode on behalf of another user), and TPM Password Hash (used to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b476d-235">理由の説明</span><span class="sxs-lookup"><span data-stu-id="b476d-235">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="b476d-236">理由指定されたキーの種類が、ヘルプデスクユーザーまたはエンドユーザーによって要求された理由です。</span><span class="sxs-lookup"><span data-stu-id="b476d-236">Reason the specified Key Type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="b476d-237">この理由は、ドライブの回復で指定され、管理と監視の web サイトの TPM 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="b476d-237">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring website.</span></span> <span data-ttu-id="b476d-238">有効なエントリは、ユーザーが入力したテキスト、または次の理由コードのいずれかです。</span><span class="sxs-lookup"><span data-stu-id="b476d-238">The valid entries are either user-entered text, or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="b476d-239">オペレーティングシステムのブート順序が変更されました</span><span class="sxs-lookup"><span data-stu-id="b476d-239">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="b476d-240">BIOS が変更されました</span><span class="sxs-lookup"><span data-stu-id="b476d-240">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="b476d-241">オペレーティングシステムファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="b476d-241">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="b476d-242">失われたスタートアップキー</span><span class="sxs-lookup"><span data-stu-id="b476d-242">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="b476d-243">PIN を紛失</span><span class="sxs-lookup"><span data-stu-id="b476d-243">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="b476d-244">TPM リセット</span><span class="sxs-lookup"><span data-stu-id="b476d-244">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="b476d-245">パスフレーズの紛失</span><span class="sxs-lookup"><span data-stu-id="b476d-245">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="b476d-246">紛失したスマートカード</span><span class="sxs-lookup"><span data-stu-id="b476d-246">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="b476d-247">PIN のロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="b476d-247">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="b476d-248">TPM を有効にする</span><span class="sxs-lookup"><span data-stu-id="b476d-248">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="b476d-249">TPM をオフにする</span><span class="sxs-lookup"><span data-stu-id="b476d-249">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="b476d-250">TPM パスワードを変更する</span><span class="sxs-lookup"><span data-stu-id="b476d-250">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="b476d-251">TPM をクリアする</span><span class="sxs-lookup"><span data-stu-id="b476d-251">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b476d-252">**注** レポートの結果をファイルに保存するには、[レポート] メニューバーの [**エクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b476d-252">**Note** Report results can be saved to a file by clicking the **Export** button on the reports menu bar.</span></span> <span data-ttu-id="b476d-253">MBAM レポートの実行方法の詳細については、「 [Mbam レポートを生成する方法](how-to-generate-mbam-reports-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b476d-253">For more information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

 

## <span data-ttu-id="b476d-254">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b476d-254">Related topics</span></span>


[<span data-ttu-id="b476d-255">MBAM 2.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="b476d-255">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





