---
title: 保留中の GPO のコマンド
description: 保留中の GPO のコマンド
author: dansimp
ms.assetid: b62f49e1-43ab-4c93-8102-96cd97a4adad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa5afed2335d75132c0fd99c69e0b5e09985d98f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822464"
---
# <span data-ttu-id="1f1b7-103">保留中の GPO のコマンド</span><span class="sxs-lookup"><span data-stu-id="1f1b7-103">Pending GPO Commands</span></span>


<span data-ttu-id="1f1b7-104">[**保留中**] タブ:</span><span class="sxs-lookup"><span data-stu-id="1f1b7-104">The **Pending** tab:</span></span>

-   <span data-ttu-id="1f1b7-105">グループポリシーオブジェクト (Gpo) の一覧が表示され、GPO 管理アクション (作成、コントロール、展開、削除など) の保留中の要求が含まれます。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-105">Displays a list of Group Policy Objects (GPOs) with pending requests for GPO management actions (such as creation, control, deployment, or deletion).</span></span>

-   <span data-ttu-id="1f1b7-106">保留中の要求に応答したり、Gpo の履歴とレポートを表示したりするためのコマンドを含むショートカットメニューを提供します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-106">Provides a shortcut menu with commands for responding to pending requests and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="1f1b7-107">選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="1f1b7-108">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="1f1b7-109">コントロールと履歴</span><span class="sxs-lookup"><span data-stu-id="1f1b7-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1f1b7-110">コマンド</span><span class="sxs-lookup"><span data-stu-id="1f1b7-110">Command</span></span></th>
<th align="left"><span data-ttu-id="1f1b7-111">効果</span><span class="sxs-lookup"><span data-stu-id="1f1b7-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1f1b7-112">履歴</span><span class="sxs-lookup"><span data-stu-id="1f1b7-112">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-113">アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-113">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="1f1b7-114">履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-114">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to an earlier version of a GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1f1b7-115">撤退</span><span class="sxs-lookup"><span data-stu-id="1f1b7-115">Withdraw</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-116">要求が承認される前に、選択した GPO を作成、制御、または削除するために、保留中の要求を取り消す。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-116">Withdraw your pending request to create, control, or delete the selected GPO before the request has been approved.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1f1b7-117">承認</span><span class="sxs-lookup"><span data-stu-id="1f1b7-117">Approve</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-118">選択した GPO を作成、制御、または削除するために、編集者からの保留中の要求を完了します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-118">Complete a pending request from an Editor to create, control, or delete the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1f1b7-119">拒否</span><span class="sxs-lookup"><span data-stu-id="1f1b7-119">Reject</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-120">選択された GPO を作成、制御、または削除するには、編集者からの保留中の要求を拒否します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-120">Deny a pending request from an Editor to create, control, or delete the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1f1b7-121">レポート</span><span class="sxs-lookup"><span data-stu-id="1f1b7-121">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1f1b7-122">コマンド</span><span class="sxs-lookup"><span data-stu-id="1f1b7-122">Command</span></span></th>
<th align="left"><span data-ttu-id="1f1b7-123">効果</span><span class="sxs-lookup"><span data-stu-id="1f1b7-123">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1f1b7-124">設定</span><span class="sxs-lookup"><span data-stu-id="1f1b7-124">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-125">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、Gpo が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ Gpo へのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-125">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs are most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1f1b7-126">相違点</span><span class="sxs-lookup"><span data-stu-id="1f1b7-126">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-127">選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-127">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1f1b7-128">その他</span><span class="sxs-lookup"><span data-stu-id="1f1b7-128">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1f1b7-129">コマンド</span><span class="sxs-lookup"><span data-stu-id="1f1b7-129">Command</span></span></th>
<th align="left"><span data-ttu-id="1f1b7-130">効果</span><span class="sxs-lookup"><span data-stu-id="1f1b7-130">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1f1b7-131">Refresh</span><span class="sxs-lookup"><span data-stu-id="1f1b7-131">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-132">グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-132">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="1f1b7-133">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-133">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1f1b7-134">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="1f1b7-134">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1f1b7-135">AGPM のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="1f1b7-135">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="1f1b7-136">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="1f1b7-136">Additional references</span></span>

-   [<span data-ttu-id="1f1b7-137">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="1f1b7-137">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="1f1b7-138">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="1f1b7-138">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="1f1b7-139">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="1f1b7-139">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





