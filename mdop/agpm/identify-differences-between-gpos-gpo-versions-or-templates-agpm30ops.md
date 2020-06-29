---
title: GPO、GPO のバージョン、またはテンプレート間の相違点を識別する
description: GPO、GPO のバージョン、またはテンプレート間の相違点を識別する
author: dansimp
ms.assetid: e391fa91-3956-4150-9d43-900cfc88d543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 88c37a3723c31fb110e731084237a8d89350a4ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820774"
---
# <span data-ttu-id="857cb-103">GPO、GPO のバージョン、またはテンプレート間の相違点を識別する</span><span class="sxs-lookup"><span data-stu-id="857cb-103">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>


<span data-ttu-id="857cb-104">HTML ベースまたは XML ベースの差分レポートを生成して、グループポリシーオブジェクト (Gpo)、テンプレート、または異なるバージョンの GPO の違いを分析できます。</span><span class="sxs-lookup"><span data-stu-id="857cb-104">You can generate HTML-based or XML-based difference reports to analyze the differences between Group Policy Objects (GPOs), templates, or different versions of a GPO.</span></span>

<span data-ttu-id="857cb-105">この手順を完了するには、レビュー担当者、編集者、承認者、または AGPM 管理者 (フルコントロール) の役割、または詳細なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="857cb-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="857cb-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="857cb-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="857cb-107">Gpo、GPO のバージョン、またはテンプレートの違いを特定する</span><span class="sxs-lookup"><span data-stu-id="857cb-107">Identifying differences between GPOs, GPO versions, or templates</span></span>


-   [<span data-ttu-id="857cb-108">2つの Gpo またはテンプレートの間</span><span class="sxs-lookup"><span data-stu-id="857cb-108">Between two GPOs or templates</span></span>](#bkmk-two-gpos)

-   [<span data-ttu-id="857cb-109">GPO とテンプレートの間</span><span class="sxs-lookup"><span data-stu-id="857cb-109">Between a GPO and a template</span></span>](#bkmk-gpo-and-template)

-   [<span data-ttu-id="857cb-110">1つの GPO の2つのバージョン間</span><span class="sxs-lookup"><span data-stu-id="857cb-110">Between two versions of one GPO</span></span>](#bkmk-two-versions)

-   [<span data-ttu-id="857cb-111">GPO のバージョンとテンプレートの間</span><span class="sxs-lookup"><span data-stu-id="857cb-111">Between a GPO version and a template</span></span>](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**<span data-ttu-id="857cb-112">2つの Gpo またはテンプレートの違いを確認するには</span><span class="sxs-lookup"><span data-stu-id="857cb-112">To identify differences between two GPOs or templates</span></span>**

1.  <span data-ttu-id="857cb-113">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-113">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="857cb-114">[詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-114">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="857cb-115">2つの Gpo またはテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="857cb-115">Select the two GPOs or templates.</span></span>

4.  <span data-ttu-id="857cb-116">いずれかの Gpo またはテンプレートを右クリックし、[**相違点**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo またはテンプレートの設定をまとめた差異レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-116">Right-click one of the GPOs or templates, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs or templates.</span></span>

### <a href="" id="bkmk-gpo-and-template"></a>

**<span data-ttu-id="857cb-117">GPO とテンプレートの違いを確認するには</span><span class="sxs-lookup"><span data-stu-id="857cb-117">To identify differences between a GPO and a template</span></span>**

1.  <span data-ttu-id="857cb-118">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-118">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="857cb-119">[詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-119">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="857cb-120">GPO を右クリックし、[**相違点**] をクリックして、[**テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-120">Right-click the GPO, click **Differences**, and then click **Template**.</span></span>

4.  <span data-ttu-id="857cb-121">レポートのテンプレートと種類を選び、[ **OK** ] をクリックして、GPO とテンプレートの設定を要約した差異レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-121">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO and template.</span></span>

### <a href="" id="bkmk-two-versions"></a>

**<span data-ttu-id="857cb-122">1つの GPO の2つのバージョンの違いを確認するには</span><span class="sxs-lookup"><span data-stu-id="857cb-122">To identify differences between two versions of one GPO</span></span>**

1.  <span data-ttu-id="857cb-123">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-123">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="857cb-124">[詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-124">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="857cb-125">GPO をダブルクリックしてその履歴を表示し、比較するバージョンを強調表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-125">Double-click the GPO to display its history, and then highlight the versions to be compared.</span></span>

4.  <span data-ttu-id="857cb-126">いずれかのバージョンを右クリックし、[**相違点**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo の設定をまとめた差異レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-126">Right-click one of the versions, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs.</span></span>

### <a href="" id="bkmk-gpo-version-and-template"></a>

**<span data-ttu-id="857cb-127">GPO のバージョンとテンプレートの違いを確認するには</span><span class="sxs-lookup"><span data-stu-id="857cb-127">To identify differences between a GPO version and a template</span></span>**

1.  <span data-ttu-id="857cb-128">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-128">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="857cb-129">[詳細] ウィンドウの [**コンテンツ**] タブで、タブをクリックして、gpo (または2つのテンプレートを比較する場合は [テンプレート]) を表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-129">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="857cb-130">GPO をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-130">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="857cb-131">目的の GPO バージョンを右クリックし、[**相違点**] をクリックして、[**テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="857cb-131">Right-click the GPO version of interest, click **Differences**, and then click **Template**.</span></span>

5.  <span data-ttu-id="857cb-132">レポートのテンプレートと種類を選び、[ **OK** ] をクリックして、GPO のバージョンとテンプレートの設定を要約した差異レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="857cb-132">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO version and template.</span></span>

## <span data-ttu-id="857cb-133">差分レポートの重要な部分</span><span class="sxs-lookup"><span data-stu-id="857cb-133">Key to difference reports</span></span>


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="857cb-134">シンボル</span><span class="sxs-lookup"><span data-stu-id="857cb-134">Symbol</span></span></th>
<th align="left"><span data-ttu-id="857cb-135">意味</span><span class="sxs-lookup"><span data-stu-id="857cb-135">Meaning</span></span></th>
<th align="left"><span data-ttu-id="857cb-136">色</span><span class="sxs-lookup"><span data-stu-id="857cb-136">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="857cb-137">なし</span><span class="sxs-lookup"><span data-stu-id="857cb-137">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="857cb-138">両方の Gpo で同じ設定のアイテムが存在する</span><span class="sxs-lookup"><span data-stu-id="857cb-138">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="857cb-139">レベルによって異なる</span><span class="sxs-lookup"><span data-stu-id="857cb-139">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="857cb-140">[#]</span><span class="sxs-lookup"><span data-stu-id="857cb-140">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="857cb-141">アイテムは両方の Gpo に存在しますが、設定が変更されています。</span><span class="sxs-lookup"><span data-stu-id="857cb-141">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="857cb-142">Rgb</span><span class="sxs-lookup"><span data-stu-id="857cb-142">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="857cb-143">[-]</span><span class="sxs-lookup"><span data-stu-id="857cb-143">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="857cb-144">アイテムは最初の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="857cb-144">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="857cb-145">赤</span><span class="sxs-lookup"><span data-stu-id="857cb-145">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="857cb-146">[+]</span><span class="sxs-lookup"><span data-stu-id="857cb-146">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="857cb-147">項目は2番目の GPO にのみ存在します</span><span class="sxs-lookup"><span data-stu-id="857cb-147">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="857cb-148">緑</span><span class="sxs-lookup"><span data-stu-id="857cb-148">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="857cb-149">設定が変更されたアイテムについては、アイテムが展開されると、変更された設定が識別されます。</span><span class="sxs-lookup"><span data-stu-id="857cb-149">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="857cb-150">各 GPO の属性の値は、レポートに Gpo が表示される順序で表示されます。</span><span class="sxs-lookup"><span data-stu-id="857cb-150">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="857cb-151">一部の設定を変更すると、変更された項目としてではなく、項目が2つの異なる項目 (1 つ目の GPO のみに存在する) として報告される場合があります。</span><span class="sxs-lookup"><span data-stu-id="857cb-151">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second) rather than as one item that has changed.</span></span>

### <span data-ttu-id="857cb-152">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="857cb-152">Additional considerations</span></span>

-   <span data-ttu-id="857cb-153">既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="857cb-153">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="857cb-154">具体的には、GPO の [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="857cb-154">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="857cb-155">また、Gpo の一覧を表示するには、ドメインの**リストコンテンツ**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="857cb-155">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="857cb-156">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="857cb-156">Additional references</span></span>

-   [<span data-ttu-id="857cb-157">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="857cb-157">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





