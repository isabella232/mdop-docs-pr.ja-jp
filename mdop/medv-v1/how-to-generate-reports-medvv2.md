---
title: レポートを生成する方法
description: レポートを生成する方法
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826994"
---
# <span data-ttu-id="783eb-103">レポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="783eb-103">How to Generate Reports</span></span>


<span data-ttu-id="783eb-104">次のレポートの種類は、MED-V で管理者が作成できます。</span><span class="sxs-lookup"><span data-stu-id="783eb-104">The following report types can be created by administrators in MED-V:</span></span>

-   <span data-ttu-id="783eb-105">[[状態](#bkmk-generatingastatusreport)] — [状態] レポートを使用して、定義された期間に基づいて、すべてのアクティブユーザーとすべての med-v ワークスペースの現在の状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="783eb-105">[Status](#bkmk-generatingastatusreport)—Use the status report to review the current status of all active users and all MED-V workspaces of each user based on a defined period of time.</span></span> <span data-ttu-id="783eb-106">これには、サーバーに現在接続されているコンピューター、または現在接続されていない場合は、サーバーに最後に接続した日付と時刻、各コンピューターの状態、その他の関連情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-106">This includes viewing computers that are currently connected to the server or, if they are not currently connected, the date and time they were last connected to the server, the status of each computer, and other relevant information.</span></span>

-   <span data-ttu-id="783eb-107">[アクティビティログ](#bkmk-generatinganactivitylogreport)—このレポートを使用して、定義された日付範囲内の特定のホストまたはユーザーからのイベントを確認します。</span><span class="sxs-lookup"><span data-stu-id="783eb-107">[Activity Log](#bkmk-generatinganactivitylogreport)—Use this report to review events that originated from a specific host or user in a defined date range.</span></span>

-   <span data-ttu-id="783eb-108">[エラーログ](#bkmk-generatinganerrorlogreport): このレポートを使用して、定義された日付範囲内の特定のホストまたはユーザーから発生したエラーを表示します。</span><span class="sxs-lookup"><span data-stu-id="783eb-108">[Error Log](#bkmk-generatinganerrorlogreport)—Use this report to view errors that originated from a specific host or user in a defined date range.</span></span>

<span data-ttu-id="783eb-109">レポートの結果は、適切な列名をクリックして、任意の列によって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="783eb-109">The report results can be sorted by any column by clicking the appropriate column name.</span></span>

<span data-ttu-id="783eb-110">レポートの結果をグループ化するには、列見出しをレポートの一番上にドラッグします。</span><span class="sxs-lookup"><span data-stu-id="783eb-110">The report results can be grouped by dragging a column header to the top of the report.</span></span> <span data-ttu-id="783eb-111">複数の列見出しをドラッグして、他の列の後に1つの列をグループ化します。</span><span class="sxs-lookup"><span data-stu-id="783eb-111">Drag multiple column headers to group one column after another.</span></span>

## <a href="" id="bkmk-generatingastatusreport"></a><span data-ttu-id="783eb-112">進捗レポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="783eb-112">How to Generate a Status Report</span></span>


**<span data-ttu-id="783eb-113">進捗レポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="783eb-113">To generate a status report</span></span>**

1.  <span data-ttu-id="783eb-114">[**レポート**の管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-114">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="783eb-115">**レポート**モジュールの [**レポートの種類**] メニューで、[**状態**] を選択し、[**生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-115">In the **Reports** module, on the **Report Types** menu, select **Status**, and click **Generate**.</span></span>

    <span data-ttu-id="783eb-116">[レポートパラメーター] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-116">The Report Parameters dialog box appears.</span></span>

3.  <span data-ttu-id="783eb-117">[**レポートパラメーター** ] ダイアログボックスの [**日数**] フィールドに数値を入力するか、または矢印を使用して進捗レポートに含める日数を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-117">In the **Report Parameters** dialog box, in the **Number of days** field, enter a number or use the arrows to select the number of days to include in the status report, and click **OK**.</span></span>

    <span data-ttu-id="783eb-118">進捗レポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-118">A status report is generated.</span></span> <span data-ttu-id="783eb-119">レポートパラメーターは、次の表で定義されています。</span><span class="sxs-lookup"><span data-stu-id="783eb-119">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="783eb-120">クライアントの MED-V ワークスペースのプロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-120">Client MED-V Workspace Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="783eb-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-121">Property</span></span></th>
<th align="left"><span data-ttu-id="783eb-122">説明</span><span class="sxs-lookup"><span data-stu-id="783eb-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-123">時間</span><span class="sxs-lookup"><span data-stu-id="783eb-123">Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-124">イベントが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="783eb-124">The date and time the event occurred.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="783eb-125">注</span><span class="sxs-lookup"><span data-stu-id="783eb-125">Note</span></span></strong><br/><p><span data-ttu-id="783eb-126">既定では、イベントは降順の日付で表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-126">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="783eb-127">ただし、[受信時刻] 列をクリックして変更することができます。</span><span class="sxs-lookup"><span data-stu-id="783eb-127">However, it can be changed by clicking the Time Received column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-128">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="783eb-128">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-129">イベントを開始したユーザー。</span><span class="sxs-lookup"><span data-stu-id="783eb-129">The user who initiated the event.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="783eb-130">注</span><span class="sxs-lookup"><span data-stu-id="783eb-130">Note</span></span></strong><br/><p><span data-ttu-id="783eb-131">ユーザーがログオンする前にイベントが発生した場合、ユーザー名はシステムです。</span><span class="sxs-lookup"><span data-stu-id="783eb-131">If the event occurred before a user logged on, the user name is SYSTEM.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-132">ホスト名</span><span class="sxs-lookup"><span data-stu-id="783eb-132">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-133">ホストコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-133">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-134">ワークスペース名</span><span class="sxs-lookup"><span data-stu-id="783eb-134">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-135">MED-V ワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-135">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-136">ワークスペースコンピューター名</span><span class="sxs-lookup"><span data-stu-id="783eb-136">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-137">MED-V ワークスペースが実行されているコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-137">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-138">オンライン</span><span class="sxs-lookup"><span data-stu-id="783eb-138">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-139">クライアントコンピューターの現在の状態:</span><span class="sxs-lookup"><span data-stu-id="783eb-139">The current state of the client computer:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="783eb-140">中断</span><span class="sxs-lookup"><span data-stu-id="783eb-140">Stopped</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="783eb-141">&lt;ワークスペースが開始されたときの開始日&gt;</span><span class="sxs-lookup"><span data-stu-id="783eb-141">Started at &lt;date and time the workspace was started&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-142">クライアントのバージョン</span><span class="sxs-lookup"><span data-stu-id="783eb-142">Client Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-143">クライアントのバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="783eb-143">The version number of the client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-144">ポリシーのバージョン</span><span class="sxs-lookup"><span data-stu-id="783eb-144">Policy Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-145">MED-V ワークスペースで現在使用されているポリシーバージョン。</span><span class="sxs-lookup"><span data-stu-id="783eb-145">The policy version that the MED-V workspace is currently using.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-146">画像名</span><span class="sxs-lookup"><span data-stu-id="783eb-146">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-147">画像の名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-147">The name of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-148">画像のバージョン</span><span class="sxs-lookup"><span data-stu-id="783eb-148">Image Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-149">MED-V ワークスペースで現在使用されている画像のバージョン。</span><span class="sxs-lookup"><span data-stu-id="783eb-149">The image version that the MED-V workspace is currently using.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="783eb-150">注</span><span class="sxs-lookup"><span data-stu-id="783eb-150">Note</span></span></strong><br/><p><span data-ttu-id="783eb-151">MED-V ワークスペースバージョンがまだコンピューターにダウンロードされていない場合は、不明の場合があります。</span><span class="sxs-lookup"><span data-stu-id="783eb-151">MED-V workspace version can be Unknown if it has not yet been downloaded onto a computer.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a><span data-ttu-id="783eb-152">アクティビティログレポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="783eb-152">How to Generate an Activity Log Report</span></span>


**<span data-ttu-id="783eb-153">アクティビティログレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="783eb-153">To generate an activity log report</span></span>**

1.  <span data-ttu-id="783eb-154">[**レポート**の管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-154">Click the **Reports** management button.</span></span>

    <span data-ttu-id="783eb-155">レポートモジュールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-155">The Reports module appears.</span></span>

2.  <span data-ttu-id="783eb-156">**レポート**モジュールの [**レポートの種類**] メニューで [**アクティビティログ**] を選択し、[**生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-156">In the **Reports** module, on the **Report Types** menu, select **Activity Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="783eb-157">[**レポートパラメーター** ] ダイアログボックスで、次のパラメーターを1つ以上構成します。</span><span class="sxs-lookup"><span data-stu-id="783eb-157">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="783eb-158">**日数**(日数): レポートに表示する日数。</span><span class="sxs-lookup"><span data-stu-id="783eb-158">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="783eb-159">**ユーザー名**には、入力されたテキストがユーザー名に含まれているすべてのイベントがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="783eb-159">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="783eb-160">[ **Host name contains**] —入力したテキストがホスト名に含まれているすべてのイベントがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="783eb-160">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="783eb-161">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-161">Click **OK**.</span></span>

    <span data-ttu-id="783eb-162">選択されたイベントと日付でレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-162">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="783eb-163">レポートパラメーターは、次の表で定義されています。</span><span class="sxs-lookup"><span data-stu-id="783eb-163">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="783eb-164">アクティビティログレポートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-164">Activity Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="783eb-165">プロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-165">Property</span></span></th>
<th align="left"><span data-ttu-id="783eb-166">説明</span><span class="sxs-lookup"><span data-stu-id="783eb-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-167">イベント ID</span><span class="sxs-lookup"><span data-stu-id="783eb-167">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-168">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="783eb-168">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-169">重大度</span><span class="sxs-lookup"><span data-stu-id="783eb-169">Severity</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="783eb-170">情報、エラー、警告</span><span class="sxs-lookup"><span data-stu-id="783eb-170">Information, Error, Warning</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-171">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="783eb-171">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-172">レポートで参照されているモジュール。</span><span class="sxs-lookup"><span data-stu-id="783eb-172">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-173">説明</span><span class="sxs-lookup"><span data-stu-id="783eb-173">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-174">イベントの説明。</span><span class="sxs-lookup"><span data-stu-id="783eb-174">A description of the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-175">受信時刻</span><span class="sxs-lookup"><span data-stu-id="783eb-175">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-176">サーバーでイベントが受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="783eb-176">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="783eb-177">注</span><span class="sxs-lookup"><span data-stu-id="783eb-177">Note</span></span></strong><br/><p><span data-ttu-id="783eb-178">クライアントがオフラインで作業している場合、クライアントがオンラインであるときにサーバーはレポートを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="783eb-178">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="783eb-179">注</span><span class="sxs-lookup"><span data-stu-id="783eb-179">Note</span></span></strong><br/><p><span data-ttu-id="783eb-180">既定では、イベントは降順の日付で表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-180">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="783eb-181">ただし、[受信時刻] 列をクリックして変更することができ <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="783eb-181">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-182">クライアント時間</span><span class="sxs-lookup"><span data-stu-id="783eb-182">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-183">クライアントのクロックに従ってイベントが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="783eb-183">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-184">ホスト名</span><span class="sxs-lookup"><span data-stu-id="783eb-184">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-185">ホストコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-185">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-186">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="783eb-186">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-187">イベントを開始したユーザー。</span><span class="sxs-lookup"><span data-stu-id="783eb-187">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-188">ワークスペース名</span><span class="sxs-lookup"><span data-stu-id="783eb-188">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-189">MED-V ワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-189">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-190">ワークスペースコンピューター名</span><span class="sxs-lookup"><span data-stu-id="783eb-190">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-191">MED-V ワークスペースが実行されているコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-191">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a><span data-ttu-id="783eb-192">エラーログレポートを生成する方法</span><span class="sxs-lookup"><span data-stu-id="783eb-192">How to Generate an Error Log Report</span></span>


**<span data-ttu-id="783eb-193">エラーログレポートを生成するには</span><span class="sxs-lookup"><span data-stu-id="783eb-193">To generate an error log report</span></span>**

1.  <span data-ttu-id="783eb-194">[**レポート**の管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-194">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="783eb-195">**レポート**モジュールの [**レポートの種類**] メニューで、[**エラーログ**] を選択し、[**生成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-195">In the **Reports** module, on the **Report Types** menu, select **Error Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="783eb-196">[**レポートパラメーター** ] ダイアログボックスで、次のパラメーターを1つ以上構成します。</span><span class="sxs-lookup"><span data-stu-id="783eb-196">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="783eb-197">**日数**(日数): レポートに表示する日数。</span><span class="sxs-lookup"><span data-stu-id="783eb-197">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="783eb-198">**ユーザー名**には、入力されたテキストがユーザー名に含まれているすべてのイベントがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="783eb-198">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="783eb-199">[ **Host name contains**] —入力したテキストがホスト名に含まれているすべてのイベントがレポートに含まれます。</span><span class="sxs-lookup"><span data-stu-id="783eb-199">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="783eb-200">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="783eb-200">Click **OK**.</span></span>

    <span data-ttu-id="783eb-201">選択されたイベントと日付でレポートが生成されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-201">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="783eb-202">レポートパラメーターは、次の表で定義されています。</span><span class="sxs-lookup"><span data-stu-id="783eb-202">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="783eb-203">エラーログレポートのプロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-203">Error Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="783eb-204">プロパティ</span><span class="sxs-lookup"><span data-stu-id="783eb-204">Property</span></span></th>
<th align="left"><span data-ttu-id="783eb-205">説明</span><span class="sxs-lookup"><span data-stu-id="783eb-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-206">イベント ID</span><span class="sxs-lookup"><span data-stu-id="783eb-206">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-207">イベント ID。</span><span class="sxs-lookup"><span data-stu-id="783eb-207">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-208">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="783eb-208">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-209">レポートで参照されているモジュール。</span><span class="sxs-lookup"><span data-stu-id="783eb-209">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-210">説明</span><span class="sxs-lookup"><span data-stu-id="783eb-210">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-211">イベントの説明。</span><span class="sxs-lookup"><span data-stu-id="783eb-211">A description of the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-212">受信時刻</span><span class="sxs-lookup"><span data-stu-id="783eb-212">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-213">サーバーでイベントが受信された日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="783eb-213">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="783eb-214">注</span><span class="sxs-lookup"><span data-stu-id="783eb-214">Note</span></span></strong><br/><p><span data-ttu-id="783eb-215">クライアントがオフラインで作業している場合、クライアントがオンラインであるときにサーバーはレポートを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="783eb-215">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="783eb-216">注</span><span class="sxs-lookup"><span data-stu-id="783eb-216">Note</span></span></strong><br/><p><span data-ttu-id="783eb-217">既定では、イベントは降順の日付で表示されます。</span><span class="sxs-lookup"><span data-stu-id="783eb-217">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="783eb-218">ただし、[受信時刻] 列をクリックして変更することができ <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="783eb-218">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-219">クライアント時間</span><span class="sxs-lookup"><span data-stu-id="783eb-219">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-220">クライアントのクロックに従ってイベントが発生した日付と時刻。</span><span class="sxs-lookup"><span data-stu-id="783eb-220">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-221">ホスト名</span><span class="sxs-lookup"><span data-stu-id="783eb-221">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-222">ホストコンピューターの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-222">The name of the host computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="783eb-223">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="783eb-223">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-224">イベントを開始したユーザー。</span><span class="sxs-lookup"><span data-stu-id="783eb-224">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="783eb-225">ワークスペース名</span><span class="sxs-lookup"><span data-stu-id="783eb-225">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="783eb-226">MED-V ワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="783eb-226">The name of the MED-V workspace.</span></span></p></td>
</tr>
</tbody>
</table>











