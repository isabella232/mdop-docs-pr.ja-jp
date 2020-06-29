---
title: MBAM レポートの概要
description: MBAM レポートの概要
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822867"
---
# <span data-ttu-id="98a9f-103">MBAM レポートの概要</span><span class="sxs-lookup"><span data-stu-id="98a9f-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="98a9f-104">Microsoft BitLocker の管理と監視 (MBAM) では、BitLocker の使用状況とコンプライアンスを監視するさまざまなレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="98a9f-105">このトピックでは、企業のコンプライアンス、個々のコンピューター、ハードウェアの互換性、およびキーの回復アクティビティに関する MBAM レポートについて説明します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-105">This topic describes the MBAM reports for enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span>

## <span data-ttu-id="98a9f-106">レポートについて</span><span class="sxs-lookup"><span data-stu-id="98a9f-106">Understanding Reports</span></span>


<span data-ttu-id="98a9f-107">MBAM のレポート機能にアクセスするには、MBAM 管理 web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-107">To access the Reports feature of MBAM, open the MBAM administration website.</span></span> <span data-ttu-id="98a9f-108">ナビゲーションウィンドウで [**レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-108">Select **Reports** in the navigation pane.</span></span> <span data-ttu-id="98a9f-109">次に、[メインコンテンツ] ウィンドウで、レポートの種類のタブをクリックします。**エンタープライズコンプライアンスレポート**、**コンピューターのコンプライアンスレポート**、**ハードウェア監査レポート**、または**回復監査レポート**。</span><span class="sxs-lookup"><span data-stu-id="98a9f-109">Then, in the main content pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

### <span data-ttu-id="98a9f-110">エンタープライズコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="98a9f-110">Enterprise Compliance Report</span></span>

<span data-ttu-id="98a9f-111">エンタープライズコンプライアンスレポートは、組織内の全体的な BitLocker のコンプライアンスに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-111">An Enterprise Compliance Report provides information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="98a9f-112">このレポートで利用可能なフィルターを使用すると、コンプライアンスの状態やエラー状態に応じて、検索結果を絞り込むことができます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-112">The available filters for this report allow you to narrow your search results according to Compliance state and Error status.</span></span> <span data-ttu-id="98a9f-113">このレポートは6時間ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-113">This report runs every six hours.</span></span>

**<span data-ttu-id="98a9f-114">エンタープライズコンプライアンスレポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="98a9f-114">Enterprise Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-115">列名</span><span class="sxs-lookup"><span data-stu-id="98a9f-115">Column Name</span></span></th>
<th align="left"><span data-ttu-id="98a9f-116">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-117">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="98a9f-117">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-118">MBAM で管理されているユーザー指定の DNS 名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-118">The user-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-119">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="98a9f-119">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-120">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-120">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-121">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-121">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-122">コンピューターに指定されているポリシーに従って、コンピューターのコンプライアンスの状態。</span><span class="sxs-lookup"><span data-stu-id="98a9f-122">The state of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="98a9f-123">可能な状態は、準拠していません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-123">The possible states are Noncompliant and Compliant.</span></span> <span data-ttu-id="98a9f-124">詳細については、このトピックの「エンタープライズコンプライアンスレポートのコンプライアンスの状態」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a9f-124">For more information, see Enterprise Compliance Report Compliance States in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-125">除外</span><span class="sxs-lookup"><span data-stu-id="98a9f-125">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-126">ハードウェアの種類の識別を決定するコンピューターハードウェアの状態と、コンピューターがポリシーの適用除外を行っているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-126">The state of the computer hardware for determining the identification of the hardware type and whether the computer is exempt from policy.</span></span> <span data-ttu-id="98a9f-127">次の3つの状態があります。ハードウェア不明 (ハードウェアの種類は MBAM によって識別されていません)、ハードウェアの除外 (ハードウェアの種類は、MBAM policy から除外されたものとマークされていましたが、ハードウェアはポリシーに適用されていませんでした)。</span><span class="sxs-lookup"><span data-stu-id="98a9f-127">There are three possible states: Hardware Unknown (the hardware type has not been identified by MBAM), Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy), and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-128">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="98a9f-128">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-129">MBAM で管理されているコンピューター上の既知のユーザー。</span><span class="sxs-lookup"><span data-stu-id="98a9f-129">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-130">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="98a9f-130">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-131">指定したポリシーに従った、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="98a9f-131">Error and status messages about the compliance state of the computer in accordance to the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-132">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="98a9f-132">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-133">コンピューターが最後にサーバーに接続してコンプライアンス状態を報告した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="98a9f-133">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="98a9f-134">この時刻は構成可能です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-134">This time is configurable.</span></span> <span data-ttu-id="98a9f-135">「MBAM ポリシーの設定」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="98a9f-135">See MBAM policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="98a9f-136">企業のコンプライアンスレポートのコンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-136">Enterprise Compliance Report Compliance states</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-137">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-137">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="98a9f-138">除外</span><span class="sxs-lookup"><span data-stu-id="98a9f-138">Exemption</span></span></th>
<th align="left"><span data-ttu-id="98a9f-139">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-139">Description</span></span></th>
<th align="left"><span data-ttu-id="98a9f-140">ユーザーの操作</span><span class="sxs-lookup"><span data-stu-id="98a9f-140">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-141">互換性</span><span class="sxs-lookup"><span data-stu-id="98a9f-141">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-142">非課税</span><span class="sxs-lookup"><span data-stu-id="98a9f-142">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-143">指定したポリシーに準拠していないコンピューターで、ハードウェアの種類がポリシーの適用除外として指定されていない。</span><span class="sxs-lookup"><span data-stu-id="98a9f-143">The computer is noncompliant according to the specified policy, and the hardware type has not been indicated as exempt from policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-144">[ <strong> コンピューター名] をクリックして </strong> 、コンピューターのコンプライアンスレポートを展開し、各ドライブの状態が指定したポリシーに準拠しているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-144">Click <strong>Computer Name</strong> to expand the Computer Compliance Report and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="98a9f-145">暗号化の状態にコンピューターが暗号化されていないことが示されている場合、暗号化が処理中であるか、またはコンピューターにエラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98a9f-145">If the encryption state indicates that the computer is not encrypted, encryption might still be in process, or there might be an error on the computer.</span></span> <span data-ttu-id="98a9f-146">エラーがない場合、原因としては、コンピューターがまだ暗号化状態の接続または確立のプロセスを行っていることが考えられます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-146">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="98a9f-147">後でもう一度確認して、状態が変わっていないかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-147">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-148">仕様</span><span class="sxs-lookup"><span data-stu-id="98a9f-148">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-149">非課税</span><span class="sxs-lookup"><span data-stu-id="98a9f-149">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-150">コンピューターは、指定されたポリシーに準拠しています。</span><span class="sxs-lookup"><span data-stu-id="98a9f-150">The computer is compliant in accordance with the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-151">操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-151">No Action needed.</span></span> <span data-ttu-id="98a9f-152">必要に応じて、コンピューターのコンプライアンスレポートを表示して、コンピューターの状態を確認することができます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-152">Optionally, you can view the Computer Compliance Report to confirm the state of the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-153">仕様</span><span class="sxs-lookup"><span data-stu-id="98a9f-153">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-154">ハードウェア適用除外</span><span class="sxs-lookup"><span data-stu-id="98a9f-154">Hardware Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-155">ハードウェアの種類が免税の場合。</span><span class="sxs-lookup"><span data-stu-id="98a9f-155">If the Hardware type is exempt.</span></span> <span data-ttu-id="98a9f-156">ポリシーがどのように設定されているか、または各ハードドライブの個々の状態に関係なく、全体的な状態は準拠するものと見なされます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-156">Regardless of how the policy is set or the individual status of each hard-drive, the overall state is considered to be compliant.</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-157">操作は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-157">No action needed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-158">仕様</span><span class="sxs-lookup"><span data-stu-id="98a9f-158">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-159">ハードウェア不明</span><span class="sxs-lookup"><span data-stu-id="98a9f-159">Hardware Unknown</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-160">MBAM はハードウェアの種類を認識していますが、MBAM は、除外されているかどうかを確認しません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-160">MBAM recognizes the hardware type, but MBAM does not know whether it is exempt or not exempt.</span></span> <span data-ttu-id="98a9f-161">これは、管理者がハードウェアの互換性の状態を設定していない場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-161">This occurs if the administrator has not set the Compatible status for the hardware.</span></span> <span data-ttu-id="98a9f-162">そのため、既定では、MBAM は準拠状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="98a9f-162">Therefore, MBAM reverts to Compliant status by default.</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-163">これは、新しく展開された MBAM クライアントの初期状態です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-163">This is the initial state of a newly deployed MBAM client.</span></span> <span data-ttu-id="98a9f-164">通常は一時的な状態でしかありません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-164">It is typically only a transient state.</span></span> <span data-ttu-id="98a9f-165">管理者がハードウェアを互換性のあるものとしてマークしている場合でも、クライアントコンピューターが再び報告される前に、大幅な遅延、または構成可能な待ち時間が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98a9f-165">Even if the administrator has marked the Hardware as Compatible, there can be a significant delay or configurable wait time before the client computer reports back in.</span></span> <span data-ttu-id="98a9f-166">最後の連絡先の時刻をメモし、指定した間隔の後にもう一度チェックインして、状態が変わったかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-166">Make note of the time of Last Contact, and check in again after the specified interval to see if the state has changed.</span></span> <span data-ttu-id="98a9f-167">状態が変更されていない場合は、このコンピューターまたはハードウェアの種類にエラーが発生している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="98a9f-167">If the state has not changed, there may be an error for this computer or hardware type.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="98a9f-168">コンピューターのコンプライアンスレポート</span><span class="sxs-lookup"><span data-stu-id="98a9f-168">Computer Compliance Report</span></span>

<span data-ttu-id="98a9f-169">コンピューターのコンプライアンスレポートには、コンピューターまたはユーザーに固有の情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-169">The Computer Compliance Report displays information that is specific to a computer or user.</span></span>

<span data-ttu-id="98a9f-170">コンピューターのコンプライアンスレポートは、オペレーティングシステムドライブや固定データドライブなど、コンピューター上の各ドライブについて、詳細な暗号化情報と適用されるポリシーを提供します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-170">The Computer Compliance Report provides detailed encryption information and applicable policies for each drive on a computer, including operating system drives and fixed data drives.</span></span> <span data-ttu-id="98a9f-171">このレポートの種類を表示するには、[エンタープライズコンプライアンス] レポートでコンピューター名をクリックするか、コンピューターのコンプライアンスレポートでコンピューター名を入力します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-171">To view this report type, click the computer name in the Enterprise Compliance Report or type the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="98a9f-172">各ドライブの詳細を表示するには、[コンピューター名] エントリを展開します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-172">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="98a9f-173">**注** このレポートでは、リムーバブルデータボリュームの暗号化の状態は提供されません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-173">**Note** This report does not provide encryption status for Removable Data Volumes.</span></span>

 

**<span data-ttu-id="98a9f-174">コンピューターのコンプライアンスレポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="98a9f-174">Computer Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-175">列名</span><span class="sxs-lookup"><span data-stu-id="98a9f-175">Column Name</span></span></th>
<th align="left"><span data-ttu-id="98a9f-176">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-177">コンピューター名</span><span class="sxs-lookup"><span data-stu-id="98a9f-177">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-178">MBAM で管理されているユーザー指定の DNS コンピューター名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-178">The user-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-179">ドメイン名</span><span class="sxs-lookup"><span data-stu-id="98a9f-179">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-180">クライアントコンピューターが存在し、MBAM で管理されている完全修飾ドメイン名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-180">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-181">コンピュータの種類</span><span class="sxs-lookup"><span data-stu-id="98a9f-181">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-182">コンピュータの移植性の種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-182">The portability type of computer.</span></span> <span data-ttu-id="98a9f-183">有効な型は、ポータブルでもポータブルでもありません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-183">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-184">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="98a9f-184">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-185">MBAM 管理クライアントコンピューターにインストールされているオペレーティングシステムの種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-185">Operating System type installed on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-186">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-186">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-187">MBAM で管理されているコンピューターの全体的なコンプライアンスの状態。</span><span class="sxs-lookup"><span data-stu-id="98a9f-187">The overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="98a9f-188">有効な状態は、準拠して準拠していません。</span><span class="sxs-lookup"><span data-stu-id="98a9f-188">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="98a9f-189">同じコンピューターに準拠しているドライブと準拠していないドライブを含めることはできますが、このフィールドには、指定したポリシーごとの全体的なコンピューターのコンプライアンスが示されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-189">While it is possible to have Compliant and Noncompliant drives in the same computer, this field indicates the overall computer compliance per specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-190">ポリシー Cypher 強度</span><span class="sxs-lookup"><span data-stu-id="98a9f-190">Policy Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-191">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="98a9f-191">The Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="98a9f-192">たとえば、ディフューザー付きの128ビット</span><span class="sxs-lookup"><span data-stu-id="98a9f-192">For example, 128-bit with Diffuser</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-193">ポリシーのオペレーティングシステムドライブ</span><span class="sxs-lookup"><span data-stu-id="98a9f-193">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-194">O/S とプロテクターの種類に対して暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-194">Indicates whether encryption is required for the O/S and the protector type as applicable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-195">ポリシー固定データドライブ</span><span class="sxs-lookup"><span data-stu-id="98a9f-195">Policy Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-196">固定ドライブで暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-196">Indicates whether encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-197">ポリシーのリムーバブルデータドライブ</span><span class="sxs-lookup"><span data-stu-id="98a9f-197">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-198">リムーバブルドライブに暗号化が必要かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-198">Indicates whether encryption is required for the Removable Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-199">デバイスユーザー</span><span class="sxs-lookup"><span data-stu-id="98a9f-199">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-200">コンピューター上の既知のユーザーの id を提供します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-200">Provides the identity of known users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-201">除外</span><span class="sxs-lookup"><span data-stu-id="98a9f-201">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-202">コンピューターのハードウェアの種類が MBAM で認識されているかどうかを示します。また、既知の場合は、コンピューターがポリシーの適用除外として示されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-202">Indicates whether the computer hardware type is recognized by MBAM and, if known, whether the computer has been indicated as exempt from policy.</span></span> <span data-ttu-id="98a9f-203">[ハードウェア不明] という3つの状態があります (ハードウェアの種類は MBAM で識別されていません)。ハードウェア除外 (ハードウェアの種類は、MBAM ポリシーの適用除外として指定されました)除外されていない (ハードウェアは認識されており、ポリシーの対象外である)。</span><span class="sxs-lookup"><span data-stu-id="98a9f-203">There are three states: Hardware Unknown (the hardware type has not been identified by MBAM); Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy); and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-204">製造元</span><span class="sxs-lookup"><span data-stu-id="98a9f-204">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-205">コンピューターの BIOS に表示されるコンピューターの製造元名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-205">The computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-206">モデル</span><span class="sxs-lookup"><span data-stu-id="98a9f-206">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-207">コンピューターの BIOS に表示されるコンピューターの製造元のモデル名。</span><span class="sxs-lookup"><span data-stu-id="98a9f-207">The computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-208">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="98a9f-208">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-209">指定したポリシーに従って、コンピューターのコンプライアンスの状態に関するエラーメッセージと状態メッセージ。</span><span class="sxs-lookup"><span data-stu-id="98a9f-209">Error and status messages of the compliance state of the computer in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-210">最終連絡先</span><span class="sxs-lookup"><span data-stu-id="98a9f-210">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-211">コンピューターがコンプライアンス状態を報告するためにサーバーに最後に接続した日時です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-211">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="98a9f-212">T</span><span class="sxs-lookup"><span data-stu-id="98a9f-212">T</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="98a9f-213">コンピューターのコンプライアンスレポートのドライブフィールド</span><span class="sxs-lookup"><span data-stu-id="98a9f-213">Computer Compliance Report Drive fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-214">列名</span><span class="sxs-lookup"><span data-stu-id="98a9f-214">Column Name</span></span></th>
<th align="left"><span data-ttu-id="98a9f-215">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-216">ドライブ文字</span><span class="sxs-lookup"><span data-stu-id="98a9f-216">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-217">ユーザーがこの特定のドライブに割り当てたコンピューターのドライブ文字です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-217">Computer drive letter that was assigned to this particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-218">ドライブの種類</span><span class="sxs-lookup"><span data-stu-id="98a9f-218">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-219">ドライブの種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-219">Type of drive.</span></span> <span data-ttu-id="98a9f-220">有効な値は、オペレーティングシステムドライブと固定データドライブです。</span><span class="sxs-lookup"><span data-stu-id="98a9f-220">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="98a9f-221">これらは論理ボリュームではなく物理ドライブです。</span><span class="sxs-lookup"><span data-stu-id="98a9f-221">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-222">Cypher 強度</span><span class="sxs-lookup"><span data-stu-id="98a9f-222">Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-223">MBAM ポリシー仕様に基づいて管理者によって選択された暗号強度。</span><span class="sxs-lookup"><span data-stu-id="98a9f-223">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-224">プロテクターの種類</span><span class="sxs-lookup"><span data-stu-id="98a9f-224">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-225">オペレーティングシステムまたは固定ボリュームの暗号化に使用するポリシーによって選択されたプロテクターの種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-225">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="98a9f-226">オペレーティングシステムドライブ上の有効なプロテクターの種類は、TPM または TPM + PIN です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-226">The valid protector types on an operating system drive are TPM or TPM+PIN.</span></span> <span data-ttu-id="98a9f-227">固定データボリュームの有効な保護機能の種類は、パスワードのみです。</span><span class="sxs-lookup"><span data-stu-id="98a9f-227">The only valid protector type for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-228">プロテクターの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-228">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-229">このフィールドは、コンピューターでポリシーに指定されているプロテクターの種類が有効になっているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-229">This field indicates whether the computer has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="98a9f-230">有効な状態は、オンまたはオフです。</span><span class="sxs-lookup"><span data-stu-id="98a9f-230">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-231">暗号化の状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-231">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-232">これは、ドライブの現在の暗号化の状態です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-232">This is the current encryption state of the drive.</span></span> <span data-ttu-id="98a9f-233">有効な状態は、暗号化され、暗号化されず、暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-233">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-234">コンプライアンスの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-234">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-235">ドライブがポリシーに準拠しているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-235">Indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="98a9f-236">状態は準拠していないため、準拠しています。</span><span class="sxs-lookup"><span data-stu-id="98a9f-236">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-237">コンプライアンスステータスの詳細</span><span class="sxs-lookup"><span data-stu-id="98a9f-237">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-238">コンピューターのコンプライアンスの状態に関するエラーと状態のメッセージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="98a9f-238">Contains error and status messages regarding the compliance state of the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="98a9f-239">ハードウェア監査レポート</span><span class="sxs-lookup"><span data-stu-id="98a9f-239">Hardware Audit Report</span></span>

<span data-ttu-id="98a9f-240">このレポートは、特定のコンピューターの作成およびモデルのハードウェア互換性状態の変更を監査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-240">This report can help you audit changes to the Hardware Compatibility status of specific computer makes and models.</span></span> <span data-ttu-id="98a9f-241">検索結果を絞り込むために、このレポートには、変更の種類や発生時間などの条件に対するフィルターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="98a9f-241">To help you narrow your search results, this report includes filtering on criteria such as type of change and time of occurrence.</span></span> <span data-ttu-id="98a9f-242">各状態の変更は、ユーザーと日付と時刻によって追跡されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-242">Each state change is tracked by user and date and time.</span></span> <span data-ttu-id="98a9f-243">ハードウェアの種類は、クライアントコンピューターで実行される MBAM エージェントによって自動的に設定されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-243">The Hardware Type is automatically populated by the MBAM agent that runs on the client computer.</span></span> <span data-ttu-id="98a9f-244">このレポートは、MBAM 管理コンピューターから直接収集された情報に対するユーザーによる変更を追跡します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-244">This report tracks user changes to the information collected directly from the MBAM managed computer.</span></span> <span data-ttu-id="98a9f-245">一般的な管理上の変更は、互換性のあるものから互換性がないものに変更されます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-245">A typical administrative change is changing from Compatible to incompatible.</span></span> <span data-ttu-id="98a9f-246">ただし、管理者はフィールドを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-246">However, the administrator can also revise any field.</span></span>

**<span data-ttu-id="98a9f-247">ハードウェア監査レポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="98a9f-247">Hardware Audit Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-248">列名</span><span class="sxs-lookup"><span data-stu-id="98a9f-248">Column Name</span></span></th>
<th align="left"><span data-ttu-id="98a9f-249">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-249">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-250">日付と時刻</span><span class="sxs-lookup"><span data-stu-id="98a9f-250">Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-251">ハードウェアの種類に変更が加えられた日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="98a9f-251">Date and time that a change was made to the Hardware Type.</span></span> <span data-ttu-id="98a9f-252">すべての固有のハードウェアの種類が、少なくとも1つのエントリに割り当てられていることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="98a9f-252">Note that every unique hardware type is assigned to at least one entry.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-253">ユーザー</span><span class="sxs-lookup"><span data-stu-id="98a9f-253">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-254">特定のエントリに変更を加えた管理ユーザー。</span><span class="sxs-lookup"><span data-stu-id="98a9f-254">Administrative user that has made the change for the particular entry.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-255">種類を変更する</span><span class="sxs-lookup"><span data-stu-id="98a9f-255">Change Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-256">ハードウェアの種類情報に加えられた変更の種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-256">Type of change that was made to the hardware type information.</span></span> <span data-ttu-id="98a9f-257">有効な値は、追加 (新しいエントリ)、更新 (既存のエントリの変更)、または削除 (既存のエントリの削除) です。</span><span class="sxs-lookup"><span data-stu-id="98a9f-257">Valid values are Addition (new entry), Update (change existing entry), or Deletion (remove existing entry).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-258">元の値</span><span class="sxs-lookup"><span data-stu-id="98a9f-258">Original Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-259">変更が加えられる前のハードウェアの種類仕様の値。</span><span class="sxs-lookup"><span data-stu-id="98a9f-259">Value of the hardware type specification before the change was made.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-260">現在価値</span><span class="sxs-lookup"><span data-stu-id="98a9f-260">Current Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-261">変更が加えられた後のハードウェアの種類仕様の値。</span><span class="sxs-lookup"><span data-stu-id="98a9f-261">Value of the hardware type specification after the change was made.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="98a9f-262">回復監査レポート</span><span class="sxs-lookup"><span data-stu-id="98a9f-262">Recovery Audit Report</span></span>

<span data-ttu-id="98a9f-263">回復監査レポートは、回復キーへのアクセスを要求したユーザーを監査するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-263">The Recovery Audit Report can help you audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="98a9f-264">このレポートのフィルター条件には、要求を行っているユーザーの種類、要求されたキーの種類、発生の時間、発生時間、ユーザー要求の種類 (ヘルプデスク、エンドユーザー) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-264">The filter criteria for this report includes type of user making the request, type of key requested, time of occurrence, success or fail, time of occurrence, and type of user requesting (help desk, end user).</span></span> <span data-ttu-id="98a9f-265">このレポートを使用すると、管理者は必要に応じてコンテキストレポートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-265">This report enables administrators to produce contextual reports based on need.</span></span>

**<span data-ttu-id="98a9f-266">回復監査レポートのフィールド</span><span class="sxs-lookup"><span data-stu-id="98a9f-266">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="98a9f-267">列名</span><span class="sxs-lookup"><span data-stu-id="98a9f-267">Column Name</span></span></th>
<th align="left"><span data-ttu-id="98a9f-268">説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-269">日付と時刻を要求する</span><span class="sxs-lookup"><span data-stu-id="98a9f-269">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-270">エンドユーザーまたはヘルプデスクユーザーによってキーの取得要求が行われた日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="98a9f-270">The date and time that a key retrieval request was made by an end user or help desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-271">リクエストの状態</span><span class="sxs-lookup"><span data-stu-id="98a9f-271">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-272">リクエストのステータス。</span><span class="sxs-lookup"><span data-stu-id="98a9f-272">Status of the request.</span></span> <span data-ttu-id="98a9f-273">有効な状態は、成功したか (キーが取得された)、失敗した (キーが取得されなかった) かどうか。</span><span class="sxs-lookup"><span data-stu-id="98a9f-273">Valid statuses are either Successful (the key was retrieved) or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-274">ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="98a9f-274">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-275">キーの取得要求を開始したヘルプデスクのユーザー。</span><span class="sxs-lookup"><span data-stu-id="98a9f-275">The help desk user who initiated the request for key retrieval.</span></span> <span data-ttu-id="98a9f-276">ヘルプデスクのユーザーがエンドユーザーの代わりにキーを取得した場合、[終了ユーザー] フィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="98a9f-276">If the help desk user retrieves the key on behalf of an end user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-277">ユーザー</span><span class="sxs-lookup"><span data-stu-id="98a9f-277">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-278">キーの取得要求を開始したエンドユーザー。</span><span class="sxs-lookup"><span data-stu-id="98a9f-278">The end user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="98a9f-279">キーの種類</span><span class="sxs-lookup"><span data-stu-id="98a9f-279">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-280">要求されたキーの種類。</span><span class="sxs-lookup"><span data-stu-id="98a9f-280">The type of key that was requested.</span></span> <span data-ttu-id="98a9f-281">MBAM は、回復キーパスワード (回復モードでコンピューターを回復する) という3種類のキーを収集します。回復キー ID (別のユーザーの代わりに回復モードでコンピューターを回復する場合)。トラステッドプラットフォームモジュール (TPM) パスワードハッシュ (ロックされている TPM を使用してコンピューターを回復します)。</span><span class="sxs-lookup"><span data-stu-id="98a9f-281">MBAM collects three key types: Recovery Key Password (to recovery a computer in recovery mode); Recovery Key ID (to recover a computer in recovery mode on behalf of another user); and Trusted Platform Module (TPM) Password Hash (to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="98a9f-282">理由の説明</span><span class="sxs-lookup"><span data-stu-id="98a9f-282">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="98a9f-283">指定したキーの種類が要求された理由。</span><span class="sxs-lookup"><span data-stu-id="98a9f-283">The reason that the specified Key Type was requested.</span></span> <span data-ttu-id="98a9f-284">この理由は、ドライブの回復で指定され、管理 web サイトの TPM 機能を管理します。</span><span class="sxs-lookup"><span data-stu-id="98a9f-284">The reasons are specified in the Drive Recovery and Manage TPM features of the Administrative web site.</span></span> <span data-ttu-id="98a9f-285">有効なエントリには、ユーザーが入力したテキスト、または次の理由コードのいずれかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="98a9f-285">Valid entries include user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="98a9f-286">オペレーティングシステムのブート順序が変更されました</span><span class="sxs-lookup"><span data-stu-id="98a9f-286">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="98a9f-287">BIOS が変更されました</span><span class="sxs-lookup"><span data-stu-id="98a9f-287">BIOS changed</span></span></p></li>
<li><p><span data-ttu-id="98a9f-288">オペレーティングシステムファイルが変更されました</span><span class="sxs-lookup"><span data-stu-id="98a9f-288">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="98a9f-289">失われたスタートアップキー</span><span class="sxs-lookup"><span data-stu-id="98a9f-289">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="98a9f-290">PIN を紛失</span><span class="sxs-lookup"><span data-stu-id="98a9f-290">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="98a9f-291">TPM リセット</span><span class="sxs-lookup"><span data-stu-id="98a9f-291">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="98a9f-292">パスフレーズの紛失</span><span class="sxs-lookup"><span data-stu-id="98a9f-292">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="98a9f-293">紛失したスマートカード</span><span class="sxs-lookup"><span data-stu-id="98a9f-293">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="98a9f-294">PIN のロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="98a9f-294">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="98a9f-295">TPM を有効にする</span><span class="sxs-lookup"><span data-stu-id="98a9f-295">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="98a9f-296">TPM をオフにする</span><span class="sxs-lookup"><span data-stu-id="98a9f-296">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="98a9f-297">TPM パスワードを変更する</span><span class="sxs-lookup"><span data-stu-id="98a9f-297">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="98a9f-298">TPM をクリアする</span><span class="sxs-lookup"><span data-stu-id="98a9f-298">Clear TPM</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="98a9f-299">**注** レポートの結果をファイルに保存するには、[レポート] メニューバーの [**エクスポート**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="98a9f-299">**Note** To save report results to a file, click the **Export** button on the reports menu bar.</span></span>

 

## <span data-ttu-id="98a9f-300">関連トピック</span><span class="sxs-lookup"><span data-stu-id="98a9f-300">Related topics</span></span>


[<span data-ttu-id="98a9f-301">MBAM 1.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="98a9f-301">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





