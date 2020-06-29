---
title: '[内容] タブの機能'
description: '[内容] タブの機能'
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818907"
---
# <span data-ttu-id="38e72-103">[内容] タブの機能</span><span class="sxs-lookup"><span data-stu-id="38e72-103">Contents Tab Features</span></span>


<span data-ttu-id="38e72-104">[**コンテンツ**] タブ内の各 [セカンダリ] タブには、**グループポリシーオブジェクト**と**グループとユーザー**の2つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="38e72-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="38e72-105">グループポリシーオブジェクトセクション</span><span class="sxs-lookup"><span data-stu-id="38e72-105">Group Policy objects section</span></span>


<span data-ttu-id="38e72-106">[**グループポリシーオブジェクト**] セクションには、グループポリシーオブジェクト (gpo) の一覧が表示され、各 gpo の次の属性が示されます。</span><span class="sxs-lookup"><span data-stu-id="38e72-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="38e72-107">GPO 属性</span><span class="sxs-lookup"><span data-stu-id="38e72-107">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="38e72-108">説明</span><span class="sxs-lookup"><span data-stu-id="38e72-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-109">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="38e72-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-110">GPO の名前。</span><span class="sxs-lookup"><span data-stu-id="38e72-110">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-111">状態</span><span class="sxs-lookup"><span data-stu-id="38e72-111">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-112">選択された GPO の状態</span><span class="sxs-lookup"><span data-stu-id="38e72-112">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-113">変更者</span><span class="sxs-lookup"><span data-stu-id="38e72-113">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-114">選択された GPO を展開した、チェックインまたは承認者がいるエディター。</span><span class="sxs-lookup"><span data-stu-id="38e72-114">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-115">日付を変更する</span><span class="sxs-lookup"><span data-stu-id="38e72-115">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-116">制御されている GPO の場合、変更されたか、チェックアウトされた後にチェックインされた最新の日付。</span><span class="sxs-lookup"><span data-stu-id="38e72-116">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="38e72-117">制御されていない GPO の場合、最終変更日。</span><span class="sxs-lookup"><span data-stu-id="38e72-117">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-118">コメント</span><span class="sxs-lookup"><span data-stu-id="38e72-118">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-119">GPO を変更したときにチェックインまたは展開したユーザーが入力したコメント。</span><span class="sxs-lookup"><span data-stu-id="38e72-119">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="38e72-120">以前のバージョンにロールバックする必要がある場合に、バージョンの詳細を識別するために役立ちます。</span><span class="sxs-lookup"><span data-stu-id="38e72-120">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-121">コンピューターのバージョン</span><span class="sxs-lookup"><span data-stu-id="38e72-121">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-122">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="38e72-122">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-123">ユーザーバージョン</span><span class="sxs-lookup"><span data-stu-id="38e72-123">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-124">自動的に生成される、GPO のユーザー構成部分のバージョン。</span><span class="sxs-lookup"><span data-stu-id="38e72-124">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-125">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="38e72-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-126">コンピューターの構成とユーザーの構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="38e72-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="38e72-127">Gpo の状態は、有効になっている GPO の部分を示します。</span><span class="sxs-lookup"><span data-stu-id="38e72-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-128">WMI フィルター</span><span class="sxs-lookup"><span data-stu-id="38e72-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-129">この GPO に適用されているすべての WMI フィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="38e72-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="38e72-130">WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] フォルダーで管理されます。</span><span class="sxs-lookup"><span data-stu-id="38e72-130">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="38e72-131">[グループとユーザー] セクション</span><span class="sxs-lookup"><span data-stu-id="38e72-131">Groups and Users section</span></span>


<span data-ttu-id="38e72-132">GPO が選択されている場合、[**グループとユーザー** ] セクションには、その gpo へのアクセス権を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38e72-132">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="38e72-133">グループまたはユーザーごとに、許可されているアクセス許可と継承が表示されます。</span><span class="sxs-lookup"><span data-stu-id="38e72-133">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="38e72-134">AGPM 管理者は、標準の AGPM ロール (エディター、承認者、レビューアー、AGPM 管理者) またはカスタマイズされたアクセス許可の組み合わせを使って、アクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="38e72-134">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="38e72-135">ボタン</span><span class="sxs-lookup"><span data-stu-id="38e72-135">Button</span></span></th>
<th align="left"><span data-ttu-id="38e72-136">効果</span><span class="sxs-lookup"><span data-stu-id="38e72-136">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-137">Add</span><span class="sxs-lookup"><span data-stu-id="38e72-137">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-138">セキュリティ記述子に新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="38e72-138">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="38e72-139">Active Directory の任意のユーザーまたはグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="38e72-139">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-140">[削除]</span><span class="sxs-lookup"><span data-stu-id="38e72-140">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-141">選択したエントリをアクセス制御リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="38e72-141">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="38e72-142">プロパティ</span><span class="sxs-lookup"><span data-stu-id="38e72-142">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-143">選択したオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="38e72-143">Display the properties for the selected object.</span></span> <span data-ttu-id="38e72-144">[プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</span><span class="sxs-lookup"><span data-stu-id="38e72-144">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="38e72-145">詳細設定</span><span class="sxs-lookup"><span data-stu-id="38e72-145">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="38e72-146"><strong>Access コントロールリストエディターを開き </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="38e72-146">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="38e72-147">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="38e72-147">Additional considerations</span></span>

-   <span data-ttu-id="38e72-148">特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks-agpm30ops.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks-agpm30ops.md)する」、「[承認者タスク](performing-approver-tasks-agpm30ops.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks-agpm30ops.md)を実行する」のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="38e72-148">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm30ops.md), [Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), [Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md).</span></span>

### <span data-ttu-id="38e72-149">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="38e72-149">Additional references</span></span>

-   [<span data-ttu-id="38e72-150">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="38e72-150">Contents Tab</span></span>](contents-tab-agpm30ops.md)

 

 





