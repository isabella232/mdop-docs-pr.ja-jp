---
title: 制御された GPO のコマンド
description: 制御された GPO のコマンド
author: dansimp
ms.assetid: 370d3db9-4efc-4799-983d-e29ba5f32b07
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 65e9d06beb4c36762e845e452bab497a8d3da747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821117"
---
# <span data-ttu-id="ac3ec-103">制御された GPO のコマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-103">Controlled GPO Commands</span></span>


<span data-ttu-id="ac3ec-104">[**コントロール**] タブ:</span><span class="sxs-lookup"><span data-stu-id="ac3ec-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="ac3ec-105">高度なグループポリシー管理 (AGPM) によって管理されているグループポリシーオブジェクト (Gpo) の一覧を表示します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="ac3ec-106">Gpo を管理するためのコマンドと、Gpo の履歴とレポートを表示するためのショートカットメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="ac3ec-107">選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="ac3ec-108">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、ショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu.</span></span> <span data-ttu-id="ac3ec-109">このメニューには、次のいずれかのオプションが適用されます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-109">This menu includes whichever of the following options are applicable.</span></span>

## <span data-ttu-id="ac3ec-110">コントロールと履歴</span><span class="sxs-lookup"><span data-stu-id="ac3ec-110">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac3ec-111">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-111">Command</span></span></th>
<th align="left"><span data-ttu-id="ac3ec-112">効果</span><span class="sxs-lookup"><span data-stu-id="ac3ec-112">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-113">新しい制御された GPO</span><span class="sxs-lookup"><span data-stu-id="ac3ec-113">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-114">AGPM で変更コントロールが管理される新しい GPO を作成し、ドメインの運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-114">Create a new GPO with change control managed through AGPM and deploy it to the production environment of the domain.</span></span> <span data-ttu-id="ac3ec-115">GPO を作成するアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-115">If you do not have permission to create a GPO, you are prompted to submit a request.</span></span> <span data-ttu-id="ac3ec-116">(このオプションは、の右クリックで GPO が選択されていない場合に表示されます <strong> 。グループポリシーオブジェクト </strong> リスト)</span><span class="sxs-lookup"><span data-stu-id="ac3ec-116">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-117">履歴</span><span class="sxs-lookup"><span data-stu-id="ac3ec-117">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-118">アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-118">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="ac3ec-119">履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-119">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to an earlier version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ac3ec-120">レポート</span><span class="sxs-lookup"><span data-stu-id="ac3ec-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac3ec-121">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-121">Command</span></span></th>
<th align="left"><span data-ttu-id="ac3ec-122">効果</span><span class="sxs-lookup"><span data-stu-id="ac3ec-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-123">設定</span><span class="sxs-lookup"><span data-stu-id="ac3ec-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-124">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、GPO が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ GPO へのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-125">相違点</span><span class="sxs-lookup"><span data-stu-id="ac3ec-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-126">選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ac3ec-127">編集</span><span class="sxs-lookup"><span data-stu-id="ac3ec-127">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac3ec-128">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-128">Command</span></span></th>
<th align="left"><span data-ttu-id="ac3ec-129">効果</span><span class="sxs-lookup"><span data-stu-id="ac3ec-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-130">Edit</span><span class="sxs-lookup"><span data-stu-id="ac3ec-130">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-131">[ <strong> グループポリシー管理エディター </strong> ] ウィンドウを開いて、選択されている GPO を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-131">Open the <strong>Group Policy Management Editor</strong> window to change the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-132">チェックアウト</span><span class="sxs-lookup"><span data-stu-id="ac3ec-132">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-133">オフライン編集のために、選択した GPO のコピーをアーカイブから取得して、他のユーザーがその GPO をアーカイブにチェックインするまで他のユーザーが編集できないようにします。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-133">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing the GPO until it is checked back into the archive.</span></span> <span data-ttu-id="ac3ec-134">チェックアウトは、AGPM 管理者 (フルコントロール) によって無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-134">Check Out can be overridden by an AGPM Administrator (Full Control).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-135">チェックイン</span><span class="sxs-lookup"><span data-stu-id="ac3ec-135">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-136">選択した GPO の編集されたバージョンをアーカイブにチェックインすると、他の承認された編集者が変更を加えたり、承認者がそのドメインの運用環境に GPO を展開したりできるようになります。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-136">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy the GPO to the production environment of the domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-137">チェックアウトを取り消す</span><span class="sxs-lookup"><span data-stu-id="ac3ec-137">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-138">チェックアウトされた GPO をアーカイブに戻します。変更はありません。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-138">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ac3ec-139">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="ac3ec-139">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac3ec-140">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-140">Command</span></span></th>
<th align="left"><span data-ttu-id="ac3ec-141">効果</span><span class="sxs-lookup"><span data-stu-id="ac3ec-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-142">生産からのインポート</span><span class="sxs-lookup"><span data-stu-id="ac3ec-142">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-143">選択した GPO について、ドメインの運用環境のバージョンをアーカイブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-143">For the selected GPO, copy the version in the production environment of the domain to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-144">ファイルからインポートする</span><span class="sxs-lookup"><span data-stu-id="ac3ec-144">Import from File</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-145">選択されているチェックアウト済み GPO のポリシー設定を、GPO バックアップファイルのポリシー設定と置き換えます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-145">Replace the policy settings of the selected, checked-out GPO with those from a GPO backup file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-146">Delete</span><span class="sxs-lookup"><span data-stu-id="ac3ec-146">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-147">選択した GPO をごみ箱に移動し、展開されたバージョン (存在する場合) を運用環境に残しておくか、アーカイブ内のバージョンに加えて展開されたバージョンを削除するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-147">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete the deployed version in addition to the version in the archive.</span></span> <span data-ttu-id="ac3ec-148">GPO を削除するアクセス許可が付与されていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-148">If you do not have permission to delete a GPO, you are prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-149">展開</span><span class="sxs-lookup"><span data-stu-id="ac3ec-149">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-150">アーカイブにチェックインされている選んだ GPO を、ドメインの運用環境に移動します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-150">Move the selected GPO that is checked into the archive to the production environment of the domain.</span></span> <span data-ttu-id="ac3ec-151">このアクションにより、ネットワーク上でアクティブになり、以前にアクティブだったバージョンの GPO が存在する場合は上書きされます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-151">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="ac3ec-152">GPO を展開する権限がない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-152">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-153">エクスポート先</span><span class="sxs-lookup"><span data-stu-id="ac3ec-153">Export to</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-154">選択した GPO を別のドメインにコピーできるようにバックアップファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-154">Save the selected GPO to a backup file so that you can copy it to another domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-155">Label</span><span class="sxs-lookup"><span data-stu-id="ac3ec-155">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-156">選択した GPO をわかりやすいラベル ( &quot; [既知の問題] など &quot; ) と [記録の記録] のコメントにマークします。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-156">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="ac3ec-157">[状態] 列にラベルが、[ <strong> </strong> <strong> </strong> 履歴] ウィンドウの [コメント] 列にコメントが表示され <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-157">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window.</span></span> <span data-ttu-id="ac3ec-158">以前のバージョンの GPO を特定することで、問題が発生した場合にロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-158">They help you identify earlier versions of a GPO so that you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-159">Rename</span><span class="sxs-lookup"><span data-stu-id="ac3ec-159">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-160">選択した GPO の名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-160">Change the name of the selected GPO.</span></span> <span data-ttu-id="ac3ec-161">GPO が既に展開されている場合、その名前は、GPO が再展開されたときに、ドメインの運用環境で更新されます。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-161">If the GPO has already been deployed, the name will be updated in the production environment of the domain when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-162">テンプレートとして保存</span><span class="sxs-lookup"><span data-stu-id="ac3ec-162">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-163">選んだ GPO の設定に基づいて新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-163">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ac3ec-164">その他</span><span class="sxs-lookup"><span data-stu-id="ac3ec-164">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ac3ec-165">コマンド</span><span class="sxs-lookup"><span data-stu-id="ac3ec-165">Command</span></span></th>
<th align="left"><span data-ttu-id="ac3ec-166">効果</span><span class="sxs-lookup"><span data-stu-id="ac3ec-166">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ac3ec-167">Refresh</span><span class="sxs-lookup"><span data-stu-id="ac3ec-167">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-168">グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-168">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="ac3ec-169">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-169">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ac3ec-170">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="ac3ec-170">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ac3ec-171">AGPM のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="ac3ec-171">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ac3ec-172">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="ac3ec-172">Additional references</span></span>

-   [<span data-ttu-id="ac3ec-173">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="ac3ec-173">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="ac3ec-174">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ac3ec-174">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="ac3ec-175">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ac3ec-175">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="ac3ec-176">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="ac3ec-176">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





