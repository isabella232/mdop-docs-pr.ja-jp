---
title: '[履歴] ウィンドウ'
description: '[履歴] ウィンドウ'
author: dansimp
ms.assetid: 5bea62e7-d267-40b2-a66d-fb1be7373a1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81f19e3834e945a45238856e23f6ee4a86407c4a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820794"
---
# <span data-ttu-id="a39ff-103">[履歴] ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a39ff-103">History Window</span></span>


<span data-ttu-id="a39ff-104">グループポリシーオブジェクト (GPO) の履歴を表示するには、GPO をダブルクリックするか、GPO を右クリックして [**履歴**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a39ff-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="a39ff-105">各 GPO のタブとして、グループポリシー管理コンソール (GPMC) にも表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-105">It is also displayed in the Group Policy Management Console (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="a39ff-106">履歴には、選択した GPO の有効期間内のイベントのレコードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="a39ff-107">[**履歴**] ウィンドウでは、gpo の1つのバージョンの設定のレポートを取得したり、gpo の複数のバージョンを比較したり、以前のバージョンの gpo にロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-107">From the **History** window, you can obtain a report of the settings in a version of the GPO, compare multiple versions of a GPO, or roll back to an earlier version of a GPO.</span></span>

## <span data-ttu-id="a39ff-108">[履歴] ウィンドウのイベントをフィルター処理する</span><span class="sxs-lookup"><span data-stu-id="a39ff-108">Filtering events in the History window</span></span>


<span data-ttu-id="a39ff-109">[**履歴**] ウィンドウ内のタブは、GPO の履歴の状態をフィルター処理します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a39ff-110">タブ</span><span class="sxs-lookup"><span data-stu-id="a39ff-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="a39ff-111">フィルタリング</span><span class="sxs-lookup"><span data-stu-id="a39ff-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-112">すべての状態</span><span class="sxs-lookup"><span data-stu-id="a39ff-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-113">GPO の履歴にすべての状態を表示します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-114">固有バージョン</span><span class="sxs-lookup"><span data-stu-id="a39ff-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-115">アーカイブにチェックインされた固有のバージョンの GPO のみを表示します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="a39ff-116">運用環境に展開されているバージョン、固有のバージョンのショートカット、および情報の状態は、この一覧から省略されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="a39ff-117">イベント情報</span><span class="sxs-lookup"><span data-stu-id="a39ff-117">Event information</span></span>


<span data-ttu-id="a39ff-118">各状態についての情報は、GPO の履歴に記載されています。</span><span class="sxs-lookup"><span data-stu-id="a39ff-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a39ff-119">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="a39ff-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="a39ff-120">説明</span><span class="sxs-lookup"><span data-stu-id="a39ff-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-121">日付を変更する</span><span class="sxs-lookup"><span data-stu-id="a39ff-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-122"><strong>状態列で操作 </strong> が実行された時刻のタイムスタンプです。</span><span class="sxs-lookup"><span data-stu-id="a39ff-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-123">状態</span><span class="sxs-lookup"><span data-stu-id="a39ff-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-124">GPO の履歴の状態。</span><span class="sxs-lookup"><span data-stu-id="a39ff-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-125">変更者</span><span class="sxs-lookup"><span data-stu-id="a39ff-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-126">GPO をチェックインまたは展開したユーザー。</span><span class="sxs-lookup"><span data-stu-id="a39ff-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-127">コメント</span><span class="sxs-lookup"><span data-stu-id="a39ff-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-128">以前のバージョンにロールバックする必要がある場合に、このバージョンが変更されたときに、GPO をチェックインまたは展開したユーザーが入力したコメント。バージョンの詳細を識別するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was changed, useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-129">不可</span><span class="sxs-lookup"><span data-stu-id="a39ff-129">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-130">アーカイブに保持されている各 GPO の一意のバージョンの数が制限されている場合に、このバージョンの GPO を削除できるかどうか。</span><span class="sxs-lookup"><span data-stu-id="a39ff-130">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a39ff-131">注</span><span class="sxs-lookup"><span data-stu-id="a39ff-131">Note</span></span></strong><br/><p><span data-ttu-id="a39ff-132">Gpo を右クリックして [削除を許可しない] または [削除を許可する] をクリックすることで、GPO のバージョンを削除するかどうかを変更でき <strong> </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-132">You can change whether a version of a GPO can be deleted by right-clicking the GPO and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-133">コンピューターのバージョン</span><span class="sxs-lookup"><span data-stu-id="a39ff-133">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-134">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="a39ff-134">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-135">ユーザーバージョン</span><span class="sxs-lookup"><span data-stu-id="a39ff-135">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-136">自動的に生成される、GPO のユーザー構成部分。</span><span class="sxs-lookup"><span data-stu-id="a39ff-136">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-137">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="a39ff-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-138">コンピューターの構成とユーザー構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="a39ff-139">この状態は、GPO のどの部分が有効になっているかを示します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-140">ソース GPO 情報</span><span class="sxs-lookup"><span data-stu-id="a39ff-140">Source GPO Information</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-141">別のフォレストからインポートされた GPO の場合、元の GPO 名、ドメイン、および最終変更に関連するユーザーと日付。</span><span class="sxs-lookup"><span data-stu-id="a39ff-141">For a GPO that has been imported from another forest, the original GPO name, domain, and user and date associated with the last change.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="a39ff-142">レポート</span><span class="sxs-lookup"><span data-stu-id="a39ff-142">Reports</span></span>


<span data-ttu-id="a39ff-143">[**設定**と**相違点**] ボタンでは、選択した gpo のバージョンまたはバージョンの gpo 設定に関するレポートが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-143">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="a39ff-144">また、GPO のバージョンまたはバージョンを右クリックすると、XML ベースのレポートを表示するオプションが提供されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-144">Also, right-clicking a GPO version or versions provides the option to display XML-based reports.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a39ff-145">ボタン</span><span class="sxs-lookup"><span data-stu-id="a39ff-145">Button</span></span></th>
<th align="left"><span data-ttu-id="a39ff-146">効果</span><span class="sxs-lookup"><span data-stu-id="a39ff-146">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-147">設定</span><span class="sxs-lookup"><span data-stu-id="a39ff-147">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-148">選択したバージョンの GPO 内の設定を表示する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-148">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-149">相違点</span><span class="sxs-lookup"><span data-stu-id="a39ff-149">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-150">複数の選択されたバージョンの GPO 内の設定を比較する HTML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="a39ff-150">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="a39ff-151">差分レポートの重要な部分</span><span class="sxs-lookup"><span data-stu-id="a39ff-151">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a39ff-152">シンボル</span><span class="sxs-lookup"><span data-stu-id="a39ff-152">Symbol</span></span></th>
<th align="left"><span data-ttu-id="a39ff-153">意味</span><span class="sxs-lookup"><span data-stu-id="a39ff-153">Meaning</span></span></th>
<th align="left"><span data-ttu-id="a39ff-154">色</span><span class="sxs-lookup"><span data-stu-id="a39ff-154">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a39ff-155">なし</span><span class="sxs-lookup"><span data-stu-id="a39ff-155">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="a39ff-156">両方の Gpo で同じ設定のアイテムが存在する</span><span class="sxs-lookup"><span data-stu-id="a39ff-156">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="a39ff-157">レベルによって異なる</span><span class="sxs-lookup"><span data-stu-id="a39ff-157">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-158">[#]</span><span class="sxs-lookup"><span data-stu-id="a39ff-158">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-159">アイテムは両方の Gpo に存在しますが、設定が変更されています。</span><span class="sxs-lookup"><span data-stu-id="a39ff-159">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="a39ff-160">Rgb</span><span class="sxs-lookup"><span data-stu-id="a39ff-160">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a39ff-161">[-]</span><span class="sxs-lookup"><span data-stu-id="a39ff-161">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-162">アイテムは最初の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="a39ff-162">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="a39ff-163">赤</span><span class="sxs-lookup"><span data-stu-id="a39ff-163">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a39ff-164">[+]</span><span class="sxs-lookup"><span data-stu-id="a39ff-164">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a39ff-165">項目は2番目の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="a39ff-165">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="a39ff-166">緑</span><span class="sxs-lookup"><span data-stu-id="a39ff-166">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="a39ff-167">設定が変更されたアイテムについては、アイテムが展開されると、変更された設定が識別されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-167">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="a39ff-168">各 GPO の属性の値は、レポートに Gpo が表示される順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="a39ff-168">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="a39ff-169">設定を変更すると、変更された1つの項目ではなく、項目が2つの項目として報告される場合があります (1 つ目の GPO のみに存在する項目もあります)。</span><span class="sxs-lookup"><span data-stu-id="a39ff-169">Some changes to settings may cause an item to be reported as two items (one present only in the first GPO, one present only in the second), instead of one item that has changed.</span></span>

### <span data-ttu-id="a39ff-170">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="a39ff-170">Additional references</span></span>

-   [<span data-ttu-id="a39ff-171">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="a39ff-171">Contents Tab</span></span>](contents-tab-agpm40.md)









