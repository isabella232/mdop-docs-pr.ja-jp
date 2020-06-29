---
title: テンプレートのコマンド
description: テンプレートのコマンド
author: dansimp
ms.assetid: 2ec11b3f-0c5c-4788-97bd-bd4bf64ba51a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7de90780caa1eb938f78597a760723f89e2e55ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820184"
---
# <span data-ttu-id="91fef-103">テンプレートのコマンド</span><span class="sxs-lookup"><span data-stu-id="91fef-103">Template Commands</span></span>


<span data-ttu-id="91fef-104">[**テンプレート**] タブ:</span><span class="sxs-lookup"><span data-stu-id="91fef-104">The **Templates** tab:</span></span>

-   <span data-ttu-id="91fef-105">新しいグループポリシーオブジェクト (Gpo) の作成に使用できる使用可能なテンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91fef-105">Displays a list of available templates that you can use to create new Group Policy Objects (GPOs).</span></span>

-   <span data-ttu-id="91fef-106">選択したテンプレートに基づいて GPO を作成したり、テンプレートを管理したり、テンプレートのレポートを表示したりするためのコマンドが含まれたショートカットメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="91fef-106">Provides a shortcut menu with commands for creating a GPO based on a selected template, managing templates, and displaying reports for templates.</span></span>

-   <span data-ttu-id="91fef-107">選択したテンプレートへのアクセス許可があるグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="91fef-107">Displays a list of the groups and users who have permission to access a selected template.</span></span>

<span data-ttu-id="91fef-108">テンプレートは変更できないため、テンプレートには履歴はありません。</span><span class="sxs-lookup"><span data-stu-id="91fef-108">Because a template cannot be altered, templates have no history.</span></span> <span data-ttu-id="91fef-109">ただし、任意の GPO バージョンと同様に、テンプレートの設定は、設定レポートとして表示したり、別の GPO と比較レポートを比較して表示したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="91fef-109">However, like any GPO version, the settings of a template can be displayed with a settings report or compared to another GPO with a difference report.</span></span>

<span data-ttu-id="91fef-110">**注** テンプレートは、新しい編集可能な Gpo を作成するための出発点として使用する、編集できない静的バージョンの GPO です。</span><span class="sxs-lookup"><span data-stu-id="91fef-110">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="91fef-111">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="91fef-111">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="91fef-112">コントロール</span><span class="sxs-lookup"><span data-stu-id="91fef-112">Control</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91fef-113">コマンド</span><span class="sxs-lookup"><span data-stu-id="91fef-113">Command</span></span></th>
<th align="left"><span data-ttu-id="91fef-114">効果</span><span class="sxs-lookup"><span data-stu-id="91fef-114">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="91fef-115">新しい制御された GPO</span><span class="sxs-lookup"><span data-stu-id="91fef-115">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-116">選択したテンプレートに基づいて新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="91fef-116">Create a new GPO based on the selected template.</span></span> <span data-ttu-id="91fef-117">新しい GPO を運用環境に展開するためのオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="91fef-117">The option to deploy the new GPO to the production environment is provided.</span></span> <span data-ttu-id="91fef-118">GPO を作成するアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="91fef-118">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="91fef-119">(このオプションは、の右クリックで GPO が選択されていない場合に表示されます <strong> 。グループポリシーオブジェクト </strong> リスト)</span><span class="sxs-lookup"><span data-stu-id="91fef-119">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="91fef-120">レポート</span><span class="sxs-lookup"><span data-stu-id="91fef-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91fef-121">コマンド</span><span class="sxs-lookup"><span data-stu-id="91fef-121">Command</span></span></th>
<th align="left"><span data-ttu-id="91fef-122">効果</span><span class="sxs-lookup"><span data-stu-id="91fef-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="91fef-123">設定</span><span class="sxs-lookup"><span data-stu-id="91fef-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-124">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="91fef-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="91fef-125">相違点</span><span class="sxs-lookup"><span data-stu-id="91fef-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-126">選択した2つの GPO テンプレート内の設定を比較する、HTML ベースまたは XML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="91fef-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPO templates.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="91fef-127">テンプレートの管理</span><span class="sxs-lookup"><span data-stu-id="91fef-127">Template management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91fef-128">コマンド</span><span class="sxs-lookup"><span data-stu-id="91fef-128">Command</span></span></th>
<th align="left"><span data-ttu-id="91fef-129">効果</span><span class="sxs-lookup"><span data-stu-id="91fef-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="91fef-130">既定に設定</span><span class="sxs-lookup"><span data-stu-id="91fef-130">Set as Default</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-131">新しい GPO の作成時に自動的に使用されるように、選択したテンプレートを既定として設定します。</span><span class="sxs-lookup"><span data-stu-id="91fef-131">Set the selected template as the default to be used automatically when creating a new GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="91fef-132">Delete</span><span class="sxs-lookup"><span data-stu-id="91fef-132">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-133">選択したテンプレートをごみ箱に移動し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="91fef-133">Move the selected template to the <strong>Recycle Bin</strong>.</span></span> <span data-ttu-id="91fef-134">GPO を削除するアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="91fef-134">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="91fef-135">Rename</span><span class="sxs-lookup"><span data-stu-id="91fef-135">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-136">選択したテンプレートの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="91fef-136">Change the name of the selected template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="91fef-137">その他</span><span class="sxs-lookup"><span data-stu-id="91fef-137">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="91fef-138">コマンド</span><span class="sxs-lookup"><span data-stu-id="91fef-138">Command</span></span></th>
<th align="left"><span data-ttu-id="91fef-139">効果</span><span class="sxs-lookup"><span data-stu-id="91fef-139">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="91fef-140">Refresh</span><span class="sxs-lookup"><span data-stu-id="91fef-140">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-141">グループポリシー管理コンソールの表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="91fef-141">Update the display of the Group Policy Management Console to incorporate any changes.</span></span> <span data-ttu-id="91fef-142">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="91fef-142">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="91fef-143">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="91fef-143">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="91fef-144">高度なグループポリシー管理 (AGPM) のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="91fef-144">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="91fef-145">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="91fef-145">Additional references</span></span>

-   [<span data-ttu-id="91fef-146">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="91fef-146">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="91fef-147">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="91fef-147">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="91fef-148">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="91fef-148">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





