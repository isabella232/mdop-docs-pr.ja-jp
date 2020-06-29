---
title: ごみ箱のコマンド
description: ごみ箱のコマンド
author: dansimp
ms.assetid: ffe8f020-7aa9-40ad-8019-cc99901a7840
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6abf063c3255538142a2ca2728a034cbaa4a1c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818547"
---
# <span data-ttu-id="2a349-103">ごみ箱のコマンド</span><span class="sxs-lookup"><span data-stu-id="2a349-103">Recycle Bin Commands</span></span>


<span data-ttu-id="2a349-104">[**ごみ箱**] タブ:</span><span class="sxs-lookup"><span data-stu-id="2a349-104">The **Recycle Bin** tab:</span></span>

-   <span data-ttu-id="2a349-105">アーカイブから削除されたグループポリシーオブジェクト (Gpo) の一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a349-105">Displays a list of Group Policy Objects (GPOs) that have been deleted from the archive.</span></span>

-   <span data-ttu-id="2a349-106">Gpo を管理するためのコマンドと、Gpo のレポートを表示するためのショートカットメニューが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2a349-106">Provides a shortcut menu with commands for managing GPOs and for displaying reports for GPOs.</span></span>

-   <span data-ttu-id="2a349-107">選択された GPO へのアクセス許可を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a349-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="2a349-108">このタブの [**グループポリシーオブジェクト**] リストを右クリックすると、次のいずれかのオプションを含むショートカットメニューが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2a349-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable:</span></span>

## <span data-ttu-id="2a349-109">レポート</span><span class="sxs-lookup"><span data-stu-id="2a349-109">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2a349-110">コマンド</span><span class="sxs-lookup"><span data-stu-id="2a349-110">Command</span></span></th>
<th align="left"><span data-ttu-id="2a349-111">効果</span><span class="sxs-lookup"><span data-stu-id="2a349-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="2a349-112">設定</span><span class="sxs-lookup"><span data-stu-id="2a349-112">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-113">選択された GPO 内の設定を表示する HTML ベースまたは XML ベースのレポートを生成するか、Gpo が最後に制御、インポート、またはチェックインされた時点から、組織単位から選んだ Gpo へのリンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a349-113">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs were most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="2a349-114">相違点</span><span class="sxs-lookup"><span data-stu-id="2a349-114">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-115">選択した2つの Gpo、または選んだ GPO とテンプレート内の設定を比較して、HTML ベースまたは XML ベースのレポートを作成します。</span><span class="sxs-lookup"><span data-stu-id="2a349-115">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2a349-116">バージョン管理</span><span class="sxs-lookup"><span data-stu-id="2a349-116">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2a349-117">コマンド</span><span class="sxs-lookup"><span data-stu-id="2a349-117">Command</span></span></th>
<th align="left"><span data-ttu-id="2a349-118">効果</span><span class="sxs-lookup"><span data-stu-id="2a349-118">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="2a349-119">Destroy</span><span class="sxs-lookup"><span data-stu-id="2a349-119">Destroy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-120">選択した GPO をごみ箱から削除し <strong> </strong> て、復元できないようにします。</span><span class="sxs-lookup"><span data-stu-id="2a349-120">Remove the selected GPO from the <strong>Recycle Bin</strong>, so it can no longer be restored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="2a349-121">復元</span><span class="sxs-lookup"><span data-stu-id="2a349-121">Restore</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-122">選択した GPO を <strong> ごみ箱から [ </strong> <strong> コントロール] タブに移動し </strong> ます。この方法では、GPO は運用環境に復元されません。</span><span class="sxs-lookup"><span data-stu-id="2a349-122">Move the selected GPO from the <strong>Recycle Bin</strong> to the <strong>Controlled</strong> tab. This does not restore the GPO to the production environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2a349-123">その他</span><span class="sxs-lookup"><span data-stu-id="2a349-123">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2a349-124">コマンド</span><span class="sxs-lookup"><span data-stu-id="2a349-124">Command</span></span></th>
<th align="left"><span data-ttu-id="2a349-125">効果</span><span class="sxs-lookup"><span data-stu-id="2a349-125">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="2a349-126">Refresh</span><span class="sxs-lookup"><span data-stu-id="2a349-126">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-127">グループポリシー管理コンソール (GPMC) の表示を更新して、変更を反映します。</span><span class="sxs-lookup"><span data-stu-id="2a349-127">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="2a349-128">表示が更新されるまで、一部の変更は表示されません。</span><span class="sxs-lookup"><span data-stu-id="2a349-128">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="2a349-129">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="2a349-129">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="2a349-130">高度なグループポリシー管理 (AGPM) のヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="2a349-130">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="2a349-131">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="2a349-131">Additional references</span></span>

-   [<span data-ttu-id="2a349-132">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="2a349-132">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="2a349-133">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="2a349-133">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="2a349-134">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="2a349-134">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





