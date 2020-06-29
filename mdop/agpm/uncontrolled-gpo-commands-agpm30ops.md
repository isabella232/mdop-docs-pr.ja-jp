---
title: 未制御の GPO のコマンド
description: 未制御の GPO のコマンド
author: dansimp
ms.assetid: 94c07b09-cb96-4ff2-b963-b25f103e73e9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 58177ef902a2f010e43fb5f33ae85f147eea11dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820114"
---
# <span data-ttu-id="854e5-103">未制御の GPO のコマンド</span><span class="sxs-lookup"><span data-stu-id="854e5-103">Uncontrolled GPO Commands</span></span>


<span data-ttu-id="854e5-104">[**非コントロール**] タブ:</span><span class="sxs-lookup"><span data-stu-id="854e5-104">The **Uncontrolled** tab:</span></span>

-   <span data-ttu-id="854e5-105">高度なグループポリシー管理 (AGPM) で管理されていないグループポリシーオブジェクト (Gpo) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="854e5-105">Displays a list of Group Policy Objects (GPOs) not managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="854e5-106">コントロールの Gpo を AGPM の管理下に表示したり、Gpo の履歴とレポートを表示したりするためのコマンドを含むショートカットメニューを提供します。</span><span class="sxs-lookup"><span data-stu-id="854e5-106">Provides a shortcut menu with commands for bringing uncontrolled GPOs under the management of AGPM and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="854e5-107">選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="854e5-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="854e5-108">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="854e5-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="854e5-109">コントロールと履歴</span><span class="sxs-lookup"><span data-stu-id="854e5-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="854e5-110">コマンド</span><span class="sxs-lookup"><span data-stu-id="854e5-110">Command</span></span></th>
<th align="left"><span data-ttu-id="854e5-111">効果</span><span class="sxs-lookup"><span data-stu-id="854e5-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="854e5-112">履歴</span><span class="sxs-lookup"><span data-stu-id="854e5-112">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-113">アーカイブに保存されている選択した GPO のすべてのバージョンを一覧表示するウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="854e5-113">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="854e5-114">履歴から、GPO 内の設定のレポートを取得したり、2つのバージョンの GPO を比較したり、GPO をテンプレートと比較したり、GPO の以前のバージョンにロールバックしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="854e5-114">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to a previous version of a GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="854e5-115">コントロール</span><span class="sxs-lookup"><span data-stu-id="854e5-115">Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-116">選択された非制御 GPO を、AGPM の変更コントロールの管理の下に移動します。</span><span class="sxs-lookup"><span data-stu-id="854e5-116">Bring the selected uncontrolled GPO under the change control management of AGPM.</span></span> <span data-ttu-id="854e5-117">GPO を制御するためのアクセス許可が与えられていない場合は、要求を送信するように求められます。</span><span class="sxs-lookup"><span data-stu-id="854e5-117">If you do not have permission to control a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="854e5-118">テンプレートとして保存</span><span class="sxs-lookup"><span data-stu-id="854e5-118">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-119">選んだ GPO の設定に基づいて新しいテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="854e5-119">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="854e5-120">レポート</span><span class="sxs-lookup"><span data-stu-id="854e5-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="854e5-121">コマンド</span><span class="sxs-lookup"><span data-stu-id="854e5-121">Command</span></span></th>
<th align="left"><span data-ttu-id="854e5-122">効果</span><span class="sxs-lookup"><span data-stu-id="854e5-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="854e5-123">設定</span><span class="sxs-lookup"><span data-stu-id="854e5-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-124">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="854e5-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="854e5-125">相違点</span><span class="sxs-lookup"><span data-stu-id="854e5-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-126">選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="854e5-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="854e5-127">その他</span><span class="sxs-lookup"><span data-stu-id="854e5-127">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="854e5-128">コマンド</span><span class="sxs-lookup"><span data-stu-id="854e5-128">Command</span></span></th>
<th align="left"><span data-ttu-id="854e5-129">効果</span><span class="sxs-lookup"><span data-stu-id="854e5-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="854e5-130">Refresh</span><span class="sxs-lookup"><span data-stu-id="854e5-130">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-131">グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="854e5-131">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="854e5-132">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="854e5-132">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="854e5-133">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="854e5-133">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="854e5-134">AGPM のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="854e5-134">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="854e5-135">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="854e5-135">Additional references</span></span>

-   [<span data-ttu-id="854e5-136">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="854e5-136">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="854e5-137">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="854e5-137">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="854e5-138">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="854e5-138">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="854e5-139">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="854e5-139">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





