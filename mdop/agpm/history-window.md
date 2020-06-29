---
title: '[履歴] ウィンドウ'
description: '[履歴] ウィンドウ'
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820787"
---
# <span data-ttu-id="5a2a1-103">[履歴] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="5a2a1-103">History Window</span></span>


<span data-ttu-id="5a2a1-104">グループポリシーオブジェクト (GPO) の履歴を表示するには、GPO をダブルクリックするか、GPO を右クリックして [**履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-104">The history of a Group Policy object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="5a2a1-105">各 GPO のタブとして、**グループポリシー管理コンソール**(GPMC) にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="5a2a1-106">履歴には、アーカイブ内に保存された、選んだ GPO のすべてのバージョンの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-106">The history provides a list of all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="5a2a1-107">[**履歴**] ウィンドウから、gpo 内の設定のレポートを取得したり、gpo の複数のバージョンを比較したり、以前のバージョンの gpo にロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-107">From the **History** window, you can obtain a report of the settings within a GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="5a2a1-108">[履歴] ウィンドウのイベントをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="5a2a1-108">Filtering events in the History window</span></span>


<span data-ttu-id="5a2a1-109">[**履歴**] ウィンドウ内のタブは、表示されたイベントをフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-109">The tabs within the **History** window filter the events displayed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a2a1-110">タブ</span><span class="sxs-lookup"><span data-stu-id="5a2a1-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="5a2a1-111">フィルタリング</span><span class="sxs-lookup"><span data-stu-id="5a2a1-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-112">すべて表示</span><span class="sxs-lookup"><span data-stu-id="5a2a1-112">Show All</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-113">GPO のすべてのバージョンを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-113">Display all versions of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-114">チェックイン済み</span><span class="sxs-lookup"><span data-stu-id="5a2a1-114">Checked In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-115">チェックインされたバージョンの GPO のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-115">Display only checked-in versions of the GPO.</span></span> <span data-ttu-id="5a2a1-116">展開されたバージョンは、この一覧には表示されません。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-116">The deployed version is omitted from this list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-117">ラベルのみ</span><span class="sxs-lookup"><span data-stu-id="5a2a1-117">Labels Only</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-118">ラベルが関連付けられている Gpo のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-118">Display only GPOs that have labels associated with them.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5a2a1-119">イベント情報</span><span class="sxs-lookup"><span data-stu-id="5a2a1-119">Event information</span></span>


<span data-ttu-id="5a2a1-120">選択された GPO の履歴内の各イベントの情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-120">Information is provided for each event in the history of the selected GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a2a1-121">GPO の特性</span><span class="sxs-lookup"><span data-stu-id="5a2a1-121">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="5a2a1-122">説明</span><span class="sxs-lookup"><span data-stu-id="5a2a1-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-123">コンピューター</span><span class="sxs-lookup"><span data-stu-id="5a2a1-123">Computer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-124">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-124">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-125">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5a2a1-125">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-126">自動的に生成される、GPO のユーザー構成部分のバージョン。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-126">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-127">Time</span><span class="sxs-lookup"><span data-stu-id="5a2a1-127">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-128">[状態] フィールドのアクションが実行されたときの GPO のバージョンのタイムスタンプ。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-128">Timestamp of the version of the GPO when the action in the status field was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-129">状態</span><span class="sxs-lookup"><span data-stu-id="5a2a1-129">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-130">選択された GPO の状態。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-130">The state of the selected version of the GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="5a2a1-131">展開済み </strong> : このバージョンの GPO は、現在の運用環境で有効です。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-131">Deployed</strong>: This version of the GPO is currently live in the production environment.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="5a2a1-132">チェックイン済み </strong> : このバージョンの GPO は、承認されたエディターが編集のためにチェックアウトするか、またはグループポリシー管理者が展開するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-132">Checked In</strong>: This version of the GPO is available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="5a2a1-133">チェックアウト済み </strong> : このバージョンの GPO は、現在、エディターによってチェックアウトされており、他のエディターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-133">Checked Out</strong>: This version of the GPO is currently checked out by an Editor and is unavailable for other Editors.</span></span> <span data-ttu-id="5a2a1-134">(チェックアウト状態は、 <strong> に記録されません。履歴 </strong> 。 GPO が現在チェックアウトされているかどうかを示します。)</span><span class="sxs-lookup"><span data-stu-id="5a2a1-134">(The checked out state is not recorded in the <strong>History</strong> except to indicate if a GPO is currently checked out.)</span></span></p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong><span data-ttu-id="5a2a1-135">作成済み </strong> : GPO の最初の作成日と時刻を識別します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-135">Created</strong>: Identifies the date and time of the initial creation of the GPO.</span></span></p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong><span data-ttu-id="5a2a1-136"></strong>[ラベルあり: GPO のラベル付きバージョンを識別します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-136">Labeled</strong>: Identifies a labeled version of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-137">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="5a2a1-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-138">コンピューターの構成とユーザー構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="5a2a1-139">この状態は、GPO のどの部分が有効になっているかを示します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-140">所有者</span><span class="sxs-lookup"><span data-stu-id="5a2a1-140">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-141">GPO をチェックインまたは展開したユーザー。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-141">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-142">コメント</span><span class="sxs-lookup"><span data-stu-id="5a2a1-142">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-143">このバージョンが変更された時点での、GPO の所有者によって入力されたコメント。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-143">A comment entered by the owner of a GPO at the time that this version was modified.</span></span> <span data-ttu-id="5a2a1-144">以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-144">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5a2a1-145">レポート</span><span class="sxs-lookup"><span data-stu-id="5a2a1-145">Reports</span></span>


<span data-ttu-id="5a2a1-146">1つの GPO バージョンと複数の GPO バージョンのどちらを選択するかによって、[**設定**] ボタンと [**相違点**] ボタンには、gpo 設定に関するレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-146">Depending on whether a single GPO version or multiple GPO versions are selected, the **Settings** and **Differences** buttons display reports on GPO settings.</span></span> <span data-ttu-id="5a2a1-147">[GPO バージョンの右クリック] では、XML ベースのレポートも表示できます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-147">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a2a1-148">ボタン</span><span class="sxs-lookup"><span data-stu-id="5a2a1-148">Button</span></span></th>
<th align="left"><span data-ttu-id="5a2a1-149">効果</span><span class="sxs-lookup"><span data-stu-id="5a2a1-149">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-150">設定</span><span class="sxs-lookup"><span data-stu-id="5a2a1-150">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-151">選択したバージョンの GPO 内の設定を表示する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-151">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-152">相違点</span><span class="sxs-lookup"><span data-stu-id="5a2a1-152">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-153">複数の選択されたバージョンの GPO 内の設定を比較する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-153">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5a2a1-154">差分レポートの重要な部分</span><span class="sxs-lookup"><span data-stu-id="5a2a1-154">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a2a1-155">シンボル</span><span class="sxs-lookup"><span data-stu-id="5a2a1-155">Symbol</span></span></th>
<th align="left"><span data-ttu-id="5a2a1-156">意味</span><span class="sxs-lookup"><span data-stu-id="5a2a1-156">Meaning</span></span></th>
<th align="left"><span data-ttu-id="5a2a1-157">色</span><span class="sxs-lookup"><span data-stu-id="5a2a1-157">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5a2a1-158">なし</span><span class="sxs-lookup"><span data-stu-id="5a2a1-158">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-159">両方の Gpo で同じ設定のアイテムが存在する</span><span class="sxs-lookup"><span data-stu-id="5a2a1-159">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-160">レベルによって異なる</span><span class="sxs-lookup"><span data-stu-id="5a2a1-160">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-161">[#]</span><span class="sxs-lookup"><span data-stu-id="5a2a1-161">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-162">アイテムは両方の Gpo に存在しますが、設定が変更されています。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-162">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-163">Rgb</span><span class="sxs-lookup"><span data-stu-id="5a2a1-163">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a2a1-164">[-]</span><span class="sxs-lookup"><span data-stu-id="5a2a1-164">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-165">アイテムは最初の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="5a2a1-165">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-166">赤</span><span class="sxs-lookup"><span data-stu-id="5a2a1-166">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a2a1-167">[+]</span><span class="sxs-lookup"><span data-stu-id="5a2a1-167">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-168">項目は2番目の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="5a2a1-168">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="5a2a1-169">緑</span><span class="sxs-lookup"><span data-stu-id="5a2a1-169">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="5a2a1-170">設定が変更されたアイテムについては、アイテムが展開されると、変更された設定が識別されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-170">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="5a2a1-171">各 GPO の属性の値は、レポートに Gpo が表示される順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-171">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="5a2a1-172">一部の設定を変更すると、変更された項目としてではなく、項目が2つの異なる項目 (1 つ目の GPO でのみ存在する) として報告される場合があります。</span><span class="sxs-lookup"><span data-stu-id="5a2a1-172">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="5a2a1-173">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="5a2a1-173">Additional references</span></span>

-   [<span data-ttu-id="5a2a1-174">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="5a2a1-174">Contents Tab</span></span>](contents-tab.md)

 

 





