---
title: 制御された GPO のコマンド
description: 制御された GPO のコマンド
author: dansimp
ms.assetid: 82db4772-154a-4a8d-99cd-2c69e1738698
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e537751107a2796727e5ed71511649b6bce953a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818877"
---
# <span data-ttu-id="e0146-103">制御された GPO のコマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-103">Controlled GPO Commands</span></span>


<span data-ttu-id="e0146-104">[**コントロール**] タブ:</span><span class="sxs-lookup"><span data-stu-id="e0146-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="e0146-105">高度なグループポリシー管理 (AGPM) によって管理されているグループポリシーオブジェクト (Gpo) の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0146-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="e0146-106">Gpo を管理するためのコマンドと、Gpo の履歴とレポートを表示するためのショートカットメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e0146-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="e0146-107">選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0146-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="e0146-108">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="e0146-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="e0146-109">コントロールと履歴</span><span class="sxs-lookup"><span data-stu-id="e0146-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0146-110">コマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-110">Command</span></span></th>
<th align="left"><span data-ttu-id="e0146-111">効果</span><span class="sxs-lookup"><span data-stu-id="e0146-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-112">新しい制御された GPO</span><span class="sxs-lookup"><span data-stu-id="e0146-112">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-113">AGPM で変更コントロールが管理される新しい GPO を作成し、それを運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="e0146-113">Create a new GPO with change control managed through AGPM and deploy it to the production environment.</span></span> <span data-ttu-id="e0146-114">GPO を作成するアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e0146-114">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="e0146-115">(このオプションは、の右クリックで GPO が選択されていない場合に表示されます <strong> 。グループポリシーオブジェクト </strong> リスト)</span><span class="sxs-lookup"><span data-stu-id="e0146-115">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-116">履歴</span><span class="sxs-lookup"><span data-stu-id="e0146-116">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-117">アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="e0146-117">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="e0146-118">履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0146-118">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to a previous version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e0146-119">レポート</span><span class="sxs-lookup"><span data-stu-id="e0146-119">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0146-120">コマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-120">Command</span></span></th>
<th align="left"><span data-ttu-id="e0146-121">効果</span><span class="sxs-lookup"><span data-stu-id="e0146-121">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-122">設定</span><span class="sxs-lookup"><span data-stu-id="e0146-122">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-123">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、GPO が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ GPO へのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="e0146-123">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-124">相違点</span><span class="sxs-lookup"><span data-stu-id="e0146-124">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-125">選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0146-125">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e0146-126">編集</span><span class="sxs-lookup"><span data-stu-id="e0146-126">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0146-127">コマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-127">Command</span></span></th>
<th align="left"><span data-ttu-id="e0146-128">効果</span><span class="sxs-lookup"><span data-stu-id="e0146-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-129">Edit</span><span class="sxs-lookup"><span data-stu-id="e0146-129">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-130">[ <strong> グループポリシー管理エディター] ウィンドウを開いて、 </strong> 選んだ GPO に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="e0146-130">Open the <strong>Group Policy Management Editor</strong> window to make changes to the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-131">チェックアウト</span><span class="sxs-lookup"><span data-stu-id="e0146-131">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-132">オフライン編集のために、選択した GPO のコピーをアーカイブから取得し、それがアーカイブに戻ってくるまで他のユーザーが編集できないようにします。</span><span class="sxs-lookup"><span data-stu-id="e0146-132">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing it until it is checked back into the archive.</span></span> <span data-ttu-id="e0146-133">(チェックアウトは、AGPM 管理者 (フルコントロール) で無効にすることができます。)</span><span class="sxs-lookup"><span data-stu-id="e0146-133">(Check Out can be overridden by an AGPM Administrator (Full Control).)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-134">チェックイン</span><span class="sxs-lookup"><span data-stu-id="e0146-134">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-135">選んだ GPO の編集されたバージョンをアーカイブにチェックインすると、他の承認された編集者が変更を加えたり、承認したりすることができるようになります。</span><span class="sxs-lookup"><span data-stu-id="e0146-135">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy it to the production environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-136">チェックアウトを取り消す</span><span class="sxs-lookup"><span data-stu-id="e0146-136">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-137">チェックアウトされた GPO をアーカイブに戻します。変更はありません。</span><span class="sxs-lookup"><span data-stu-id="e0146-137">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e0146-138">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="e0146-138">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0146-139">コマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-139">Command</span></span></th>
<th align="left"><span data-ttu-id="e0146-140">効果</span><span class="sxs-lookup"><span data-stu-id="e0146-140">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-141">生産からのインポート</span><span class="sxs-lookup"><span data-stu-id="e0146-141">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-142">選択した GPO の場合、運用環境のバージョンをアーカイブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e0146-142">For the selected GPO, copy the version in the production environment to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-143">Delete</span><span class="sxs-lookup"><span data-stu-id="e0146-143">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-144">選択した GPO を [ごみ箱] に移動し、展開されたバージョン (存在する場合) を運用環境に残しておくか、アーカイブ内のバージョンと一緒に削除するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="e0146-144">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete it as well as the version in the archive.</span></span> <span data-ttu-id="e0146-145">GPO を削除するアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e0146-145">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-146">展開</span><span class="sxs-lookup"><span data-stu-id="e0146-146">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-147">アーカイブにチェックインされている、選択された GPO を運用環境に移動します。</span><span class="sxs-lookup"><span data-stu-id="e0146-147">Move the selected GPO that is checked into the archive to the production environment.</span></span> <span data-ttu-id="e0146-148">このアクションにより、ネットワーク上でアクティブになり、以前にアクティブだったバージョンの GPO が存在する場合は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="e0146-148">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="e0146-149">GPO を展開する権限がない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="e0146-149">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-150">Label</span><span class="sxs-lookup"><span data-stu-id="e0146-150">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-151">選択した GPO をわかりやすいラベル ( &quot; [既知の問題] など &quot; ) と [記録の記録] のコメントにマークします。</span><span class="sxs-lookup"><span data-stu-id="e0146-151">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="e0146-152">ラベルは、[ <strong> </strong> <strong> </strong> 履歴] ウィンドウの [コメント] 列に表示され <strong> </strong> ます。これにより、特定のラベルで識別された GPO の以前のバージョンを簡単に識別できるようになり、問題が発生した場合にロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="e0146-152">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window, enabling you to easily identify previous versions of a GPO identified with a particular label, so you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-153">Rename</span><span class="sxs-lookup"><span data-stu-id="e0146-153">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-154">選択した GPO の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="e0146-154">Change the name of the selected GPO.</span></span> <span data-ttu-id="e0146-155">GPO が既に展開されている場合、GPO を再展開すると、その名前が運用環境で更新されます。</span><span class="sxs-lookup"><span data-stu-id="e0146-155">If the GPO has already been deployed, the name will be updated in the production environment when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-156">テンプレートとして保存</span><span class="sxs-lookup"><span data-stu-id="e0146-156">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-157">選んだ GPO の設定に基づいて新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="e0146-157">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e0146-158">その他</span><span class="sxs-lookup"><span data-stu-id="e0146-158">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0146-159">コマンド</span><span class="sxs-lookup"><span data-stu-id="e0146-159">Command</span></span></th>
<th align="left"><span data-ttu-id="e0146-160">効果</span><span class="sxs-lookup"><span data-stu-id="e0146-160">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e0146-161">Refresh</span><span class="sxs-lookup"><span data-stu-id="e0146-161">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-162">グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="e0146-162">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="e0146-163">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="e0146-163">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e0146-164">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="e0146-164">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e0146-165">AGPM のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="e0146-165">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e0146-166">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="e0146-166">Additional references</span></span>

-   [<span data-ttu-id="e0146-167">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="e0146-167">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="e0146-168">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e0146-168">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="e0146-169">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e0146-169">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="e0146-170">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e0146-170">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





