---
title: '[履歴] ウィンドウ'
description: '[履歴] ウィンドウ'
author: dansimp
ms.assetid: 114f50a4-508d-4589-b006-6cd05cffe6b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81911b5103c76e267d806fb7cd8acf55811440c9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820797"
---
# <span data-ttu-id="b45ce-103">[履歴] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="b45ce-103">History Window</span></span>


<span data-ttu-id="b45ce-104">グループポリシーオブジェクト (GPO) の履歴を表示するには、GPO をダブルクリックするか、GPO を右クリックして [**履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b45ce-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="b45ce-105">各 GPO のタブとして、**グループポリシー管理コンソール**(GPMC) にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="b45ce-106">履歴には、選択した GPO の有効期間内のイベントのレコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="b45ce-107">[**履歴**] ウィンドウから、gpo の1つのバージョン内の設定のレポートを取得したり、gpo の複数のバージョンを比較したり、以前のバージョンの gpo にロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-107">From the **History** window, you can obtain a report of the settings within a version of the GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="b45ce-108">[履歴] ウィンドウのイベントをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="b45ce-108">Filtering events in the History window</span></span>


<span data-ttu-id="b45ce-109">[**履歴**] ウィンドウ内のタブは、GPO の履歴の状態をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b45ce-110">タブ</span><span class="sxs-lookup"><span data-stu-id="b45ce-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="b45ce-111">フィルタリング</span><span class="sxs-lookup"><span data-stu-id="b45ce-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-112">すべての状態</span><span class="sxs-lookup"><span data-stu-id="b45ce-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-113">GPO の履歴にすべての状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-114">固有バージョン</span><span class="sxs-lookup"><span data-stu-id="b45ce-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-115">アーカイブにチェックインされた固有のバージョンの GPO のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="b45ce-116">運用環境に展開されているバージョン、固有のバージョンのショートカット、および情報の状態は、この一覧から省略されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b45ce-117">イベント情報</span><span class="sxs-lookup"><span data-stu-id="b45ce-117">Event information</span></span>


<span data-ttu-id="b45ce-118">各状態についての情報は、GPO の履歴に記載されています。</span><span class="sxs-lookup"><span data-stu-id="b45ce-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b45ce-119">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="b45ce-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="b45ce-120">説明</span><span class="sxs-lookup"><span data-stu-id="b45ce-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-121">日付を変更する</span><span class="sxs-lookup"><span data-stu-id="b45ce-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-122"><strong>状態列で操作 </strong> が実行された時刻のタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="b45ce-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-123">状態</span><span class="sxs-lookup"><span data-stu-id="b45ce-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-124">GPO の履歴の状態。</span><span class="sxs-lookup"><span data-stu-id="b45ce-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-125">変更者</span><span class="sxs-lookup"><span data-stu-id="b45ce-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-126">GPO をチェックインまたは展開したユーザー。</span><span class="sxs-lookup"><span data-stu-id="b45ce-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-127">コメント</span><span class="sxs-lookup"><span data-stu-id="b45ce-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-128">このバージョンの変更時に、GPO をチェックインまたは展開したユーザーによって入力されたコメント。</span><span class="sxs-lookup"><span data-stu-id="b45ce-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was modified.</span></span> <span data-ttu-id="b45ce-129">以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-129">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-130">不可</span><span class="sxs-lookup"><span data-stu-id="b45ce-130">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-131">アーカイブに保持されている各 GPO の一意のバージョンの数が制限されている場合に、このバージョンの GPO を削除できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="b45ce-131">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b45ce-132">注</span><span class="sxs-lookup"><span data-stu-id="b45ce-132">Note</span></span></strong><br/><p><span data-ttu-id="b45ce-133">GPO のバージョンが削除されるかどうかを変更するには、それを右クリックして、[削除を許可しない] または [削除を許可する] をクリックし <strong> </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-133">You can modify whether a version of a GPO is deletable by right-clicking it and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-134">コンピューターのバージョン</span><span class="sxs-lookup"><span data-stu-id="b45ce-134">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-135">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="b45ce-135">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-136">ユーザーバージョン</span><span class="sxs-lookup"><span data-stu-id="b45ce-136">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-137">自動的に生成される、GPO のユーザー構成部分のバージョン。</span><span class="sxs-lookup"><span data-stu-id="b45ce-137">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-138">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="b45ce-138">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-139">コンピューターの構成とユーザー構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-139">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="b45ce-140">この状態は、GPO のどの部分が有効になっているかを示します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-140">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-141">WMI フィルター</span><span class="sxs-lookup"><span data-stu-id="b45ce-141">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-142">この GPO に適用されているすべての WMI フィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-142">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="b45ce-143">WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] フォルダーで管理されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-143">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b45ce-144">レポート</span><span class="sxs-lookup"><span data-stu-id="b45ce-144">Reports</span></span>


<span data-ttu-id="b45ce-145">[**設定**と**相違点**] ボタンでは、選択した gpo のバージョンまたはバージョンの gpo 設定に関するレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-145">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="b45ce-146">[GPO バージョンの右クリック] では、XML ベースのレポートも表示できます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-146">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b45ce-147">ボタン</span><span class="sxs-lookup"><span data-stu-id="b45ce-147">Button</span></span></th>
<th align="left"><span data-ttu-id="b45ce-148">効果</span><span class="sxs-lookup"><span data-stu-id="b45ce-148">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-149">設定</span><span class="sxs-lookup"><span data-stu-id="b45ce-149">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-150">選択したバージョンの GPO 内の設定を表示する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-150">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-151">相違点</span><span class="sxs-lookup"><span data-stu-id="b45ce-151">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-152">複数の選択されたバージョンの GPO 内の設定を比較する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="b45ce-152">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="b45ce-153">差分レポートの重要な部分</span><span class="sxs-lookup"><span data-stu-id="b45ce-153">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b45ce-154">シンボル</span><span class="sxs-lookup"><span data-stu-id="b45ce-154">Symbol</span></span></th>
<th align="left"><span data-ttu-id="b45ce-155">意味</span><span class="sxs-lookup"><span data-stu-id="b45ce-155">Meaning</span></span></th>
<th align="left"><span data-ttu-id="b45ce-156">色</span><span class="sxs-lookup"><span data-stu-id="b45ce-156">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b45ce-157">なし</span><span class="sxs-lookup"><span data-stu-id="b45ce-157">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="b45ce-158">両方の Gpo で同じ設定のアイテムが存在する</span><span class="sxs-lookup"><span data-stu-id="b45ce-158">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="b45ce-159">レベルによって異なる</span><span class="sxs-lookup"><span data-stu-id="b45ce-159">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-160">[#]</span><span class="sxs-lookup"><span data-stu-id="b45ce-160">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-161">アイテムは両方の Gpo に存在しますが、設定が変更されています。</span><span class="sxs-lookup"><span data-stu-id="b45ce-161">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="b45ce-162">Rgb</span><span class="sxs-lookup"><span data-stu-id="b45ce-162">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b45ce-163">[-]</span><span class="sxs-lookup"><span data-stu-id="b45ce-163">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-164">アイテムは最初の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="b45ce-164">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="b45ce-165">赤</span><span class="sxs-lookup"><span data-stu-id="b45ce-165">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="b45ce-166">[+]</span><span class="sxs-lookup"><span data-stu-id="b45ce-166">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="b45ce-167">項目は2番目の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="b45ce-167">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="b45ce-168">緑</span><span class="sxs-lookup"><span data-stu-id="b45ce-168">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="b45ce-169">設定が変更されたアイテムについては、アイテムが展開されると、変更された設定が識別されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-169">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="b45ce-170">各 GPO の属性の値は、レポートに Gpo が表示される順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="b45ce-170">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="b45ce-171">一部の設定を変更すると、変更された項目としてではなく、項目が2つの異なる項目 (1 つ目の GPO でのみ存在する) として報告される場合があります。</span><span class="sxs-lookup"><span data-stu-id="b45ce-171">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="b45ce-172">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="b45ce-172">Additional references</span></span>

-   [<span data-ttu-id="b45ce-173">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="b45ce-173">Contents Tab</span></span>](contents-tab-agpm30ops.md)









