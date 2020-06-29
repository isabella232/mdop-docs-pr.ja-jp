---
title: '[内容] タブの機能'
description: '[内容] タブの機能'
author: dansimp
ms.assetid: f1f4849d-bf94-47d5-ad81-0eee33abcaca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 081cffb7c2871d0e49abd229ec06773726483f2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818894"
---
# <span data-ttu-id="49a8a-103">[内容] タブの機能</span><span class="sxs-lookup"><span data-stu-id="49a8a-103">Contents Tab Features</span></span>


<span data-ttu-id="49a8a-104">[**コンテンツ**] タブ内の各 [セカンダリ] タブには、**グループポリシーオブジェクト**と**グループとユーザー**の2つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="49a8a-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="49a8a-105">グループポリシーオブジェクトセクション</span><span class="sxs-lookup"><span data-stu-id="49a8a-105">Group Policy objects section</span></span>


<span data-ttu-id="49a8a-106">[**グループポリシーオブジェクト**] セクションには、グループポリシーオブジェクト (gpo) の一覧が表示され、各 gpo の次の属性が示されます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO.</span></span> <span data-ttu-id="49a8a-107">**検索**ボックスを使用して、特定の属性を持つ gpo を検索することができます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-107">You can use the **Search** box to search for GPOs with specific attributes.</span></span> <span data-ttu-id="49a8a-108">詳細については、「 [gpo の一覧を検索してフィルター処理する](search-and-filter-the-list-of-gpos.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a8a-108">For more information, see [Search and Filter the List of GPOs](search-and-filter-the-list-of-gpos.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49a8a-109">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="49a8a-109">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="49a8a-110">説明</span><span class="sxs-lookup"><span data-stu-id="49a8a-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-111">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="49a8a-111">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-112">GPO の名前。</span><span class="sxs-lookup"><span data-stu-id="49a8a-112">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-113">状態</span><span class="sxs-lookup"><span data-stu-id="49a8a-113">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-114">選択された GPO の状態</span><span class="sxs-lookup"><span data-stu-id="49a8a-114">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-115">変更者</span><span class="sxs-lookup"><span data-stu-id="49a8a-115">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-116">選択された GPO を展開した、チェックインまたは承認者がいるエディター。</span><span class="sxs-lookup"><span data-stu-id="49a8a-116">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-117">日付を変更する</span><span class="sxs-lookup"><span data-stu-id="49a8a-117">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-118">制御されている GPO の場合、変更されたか、チェックアウトされた後にチェックインされた最新の日付。</span><span class="sxs-lookup"><span data-stu-id="49a8a-118">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="49a8a-119">制御されていない GPO の場合、最終変更日。</span><span class="sxs-lookup"><span data-stu-id="49a8a-119">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-120">コメント</span><span class="sxs-lookup"><span data-stu-id="49a8a-120">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-121">GPO を変更したときにチェックインまたは展開したユーザーが入力したコメント。</span><span class="sxs-lookup"><span data-stu-id="49a8a-121">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="49a8a-122">以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-122">Useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-123">コンピューターのバージョン</span><span class="sxs-lookup"><span data-stu-id="49a8a-123">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-124">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="49a8a-124">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-125">ユーザーバージョン</span><span class="sxs-lookup"><span data-stu-id="49a8a-125">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-126">自動的に生成される、GPO のユーザー構成部分。</span><span class="sxs-lookup"><span data-stu-id="49a8a-126">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-127">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="49a8a-127">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-128">コンピューターの構成とユーザーの構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-128">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="49a8a-129">Gpo の状態は、有効になっている GPO の部分を示します。</span><span class="sxs-lookup"><span data-stu-id="49a8a-129">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-130">WMI フィルター</span><span class="sxs-lookup"><span data-stu-id="49a8a-130">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-131">この GPO に適用されているすべての WMI フィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="49a8a-131">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="49a8a-132">WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] フォルダーで管理されます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-132">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49a8a-133">[グループとユーザー] セクション</span><span class="sxs-lookup"><span data-stu-id="49a8a-133">Groups and Users section</span></span>


<span data-ttu-id="49a8a-134">GPO が選択されている場合、[**グループとユーザー** ] セクションには、その gpo へのアクセス権を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-134">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="49a8a-135">グループまたはユーザーごとに、許可されているアクセス許可と継承が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-135">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="49a8a-136">AGPM 管理者は、標準の AGPM ロール (エディター、承認者、レビューアー、AGPM 管理者) またはカスタマイズされたアクセス許可の組み合わせを使って、アクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-136">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49a8a-137">ボタン</span><span class="sxs-lookup"><span data-stu-id="49a8a-137">Button</span></span></th>
<th align="left"><span data-ttu-id="49a8a-138">効果</span><span class="sxs-lookup"><span data-stu-id="49a8a-138">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-139">Add</span><span class="sxs-lookup"><span data-stu-id="49a8a-139">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-140">セキュリティ記述子に新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="49a8a-140">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="49a8a-141">Active Directory の任意のユーザーまたはグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-141">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-142">[削除]</span><span class="sxs-lookup"><span data-stu-id="49a8a-142">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-143">選択したエントリをアクセス制御リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="49a8a-143">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49a8a-144">プロパティ</span><span class="sxs-lookup"><span data-stu-id="49a8a-144">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-145">選択したオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="49a8a-145">Display the properties for the selected object.</span></span> <span data-ttu-id="49a8a-146">[プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</span><span class="sxs-lookup"><span data-stu-id="49a8a-146">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49a8a-147">詳細設定</span><span class="sxs-lookup"><span data-stu-id="49a8a-147">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49a8a-148"><strong>Access コントロールリストエディターを開き </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="49a8a-148">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="49a8a-149">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="49a8a-149">Additional considerations</span></span>

-   <span data-ttu-id="49a8a-150">特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks-agpm40.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks-agpm40.md)する」、「[承認者タスク](performing-approver-tasks-agpm40.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks-agpm40.md)を実行する」のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="49a8a-150">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm40.md), [Performing Editor Tasks](performing-editor-tasks-agpm40.md), [Performing Approver Tasks](performing-approver-tasks-agpm40.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md).</span></span>

### <span data-ttu-id="49a8a-151">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="49a8a-151">Additional references</span></span>

-   [<span data-ttu-id="49a8a-152">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="49a8a-152">Contents Tab</span></span>](contents-tab-agpm40.md)

 

 





