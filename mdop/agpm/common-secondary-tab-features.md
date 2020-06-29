---
title: 一般的なセカンダリ タブの機能
description: 一般的なセカンダリ タブの機能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819087"
---
# <span data-ttu-id="5a9b6-103">一般的なセカンダリ タブの機能</span><span class="sxs-lookup"><span data-stu-id="5a9b6-103">Common Secondary Tab Features</span></span>


<span data-ttu-id="5a9b6-104">各 [セカンダリ] タブには、**グループポリシーオブジェクト**と**グループとユーザー**の2つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-104">Each secondary tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="5a9b6-105">グループポリシーオブジェクトセクション</span><span class="sxs-lookup"><span data-stu-id="5a9b6-105">Group Policy objects section</span></span>


<span data-ttu-id="5a9b6-106">[**グループポリシーオブジェクト**] セクションには、グループポリシーオブジェクト (gpo) の一覧が表示され、各 GPO の次の特性が示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-106">The **Group Policy objects** section displays a filtered list of Group Policy objects (GPOs) and identifies the following characteristics for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a9b6-107">GPO の特性</span><span class="sxs-lookup"><span data-stu-id="5a9b6-107">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="5a9b6-108">説明</span><span class="sxs-lookup"><span data-stu-id="5a9b6-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-109">Name (名前)</span><span class="sxs-lookup"><span data-stu-id="5a9b6-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-110">グループポリシーオブジェクトの名前。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-110">Name of the Group Policy object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-111">コンピュータ (カンプ)</span><span class="sxs-lookup"><span data-stu-id="5a9b6-111">Computer (Comp.)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-112">GPO のコンピューター構成部分の自動生成されたバージョン。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-112">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-113">ユーザー</span><span class="sxs-lookup"><span data-stu-id="5a9b6-113">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-114">自動的に生成される、GPO のユーザー構成部分のバージョン。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-114">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-115">状態</span><span class="sxs-lookup"><span data-stu-id="5a9b6-115">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-116">選択された GPO の状態:</span><span class="sxs-lookup"><span data-stu-id="5a9b6-116">The state of the selected GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="5a9b6-117">非制御: </strong> AGPM で管理されません。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-117">Uncontrolled:</strong> Not managed by AGPM.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="5a9b6-118">チェックイン: </strong> 承認された編集者またはグループポリシー管理者が展開するために、承認された編集者に対して使用できます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-118">Checked In:</strong> Available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="5a9b6-119">チェックアウト済み: </strong> 現在編集中です。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-119">Checked Out:</strong> Currently being edited.</span></span> <span data-ttu-id="5a9b6-120">他のエディターは、チェックアウトしたエディターまたは AGPM 管理者がチェックインするまで、他のエディターでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-120">Unavailable for other Editors to check out until the Editor who checked it out or an AGPM Administrator checks it in.</span></span></p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong><span data-ttu-id="5a9b6-121">[保留中 </strong> ]: グループポリシー管理者による承認待ちのため、作成、管理、展開、または削除されます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-121">Pending:</strong> Awaiting approval from a Group Policy administrator before being created, controlled, deployed, or deleted.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="5a9b6-122">[削除済み </strong> ]: アーカイブから削除されますが、復元することはできます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-122">Deleted:</strong> Deleted from the archive, but still able to be restored.</span></span></p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong><span data-ttu-id="5a9b6-123">テンプレート: </strong> 新しい gpo の作成時の出発点として使用する gpo の静的なバージョン。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-123">Template:</strong> A static version of a GPO for use as a starting point when creating new GPOs.</span></span></p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong><span data-ttu-id="5a9b6-124">テンプレート (既定): </strong> 既定では、新しい GPO の作成時に使用される開始点はこのテンプレートです。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-124">Template (default):</strong> By default, this template is the starting point used when creating a new GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-125">GPO の状態</span><span class="sxs-lookup"><span data-stu-id="5a9b6-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-126">コンピューターの構成とユーザーの構成は、個別に管理することができます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="5a9b6-127">Gpo の状態は、有効になっている GPO の部分を示します。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-128">WMI フィルター</span><span class="sxs-lookup"><span data-stu-id="5a9b6-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-129">この GPO に適用されているすべての WMI フィルターを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="5a9b6-130">WMI フィルターは、 <strong> </strong> GPMC のコンソールツリーで、ドメインの [wmi フィルター] ノードで管理されます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-130">WMI filters are managed under the <strong>WMI Filters</strong> node for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-131">変更</span><span class="sxs-lookup"><span data-stu-id="5a9b6-131">Modified</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-132">コントロールされた GPO の場合、変更されたか、チェックアウトされた後にチェックインされた最新の日付。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-132">For a controlled GPO, the most recent date when it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="5a9b6-133">制御されていない GPO の場合、最終変更日。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-133">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-134">所有者</span><span class="sxs-lookup"><span data-stu-id="5a9b6-134">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-135">選択された GPO を展開した、チェックインまたは承認者がいるエディター。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-135">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5a9b6-136">[グループとユーザー] セクション</span><span class="sxs-lookup"><span data-stu-id="5a9b6-136">Groups and Users section</span></span>


<span data-ttu-id="5a9b6-137">GPO が選択されている場合、[**グループとユーザー** ] セクションには、その gpo へのアクセス権を持つグループとユーザーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-137">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="5a9b6-138">グループまたはユーザーごとに、許可されているアクセス許可と継承が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-138">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="5a9b6-139">AGPM 管理者は、標準の AGPM ロール (エディター、承認者、および校閲者) またはカスタマイズされたアクセス許可の組み合わせを使って、アクセス許可を構成できます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-139">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, and Reviewer) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5a9b6-140">ボタン</span><span class="sxs-lookup"><span data-stu-id="5a9b6-140">Button</span></span></th>
<th align="left"><span data-ttu-id="5a9b6-141">効果</span><span class="sxs-lookup"><span data-stu-id="5a9b6-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-142">Add</span><span class="sxs-lookup"><span data-stu-id="5a9b6-142">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-143">セキュリティ記述子に新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-143">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="5a9b6-144">Active Directory の任意のユーザーまたはグループを追加できます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-144">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-145">[削除]</span><span class="sxs-lookup"><span data-stu-id="5a9b6-145">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-146">選択したエントリをアクセス制御リストから削除します。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-146">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="5a9b6-147">プロパティ</span><span class="sxs-lookup"><span data-stu-id="5a9b6-147">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-148">選択したオブジェクトのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-148">Display the properties for the selected object.</span></span> <span data-ttu-id="5a9b6-149">[プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-149">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="5a9b6-150">詳細設定</span><span class="sxs-lookup"><span data-stu-id="5a9b6-150">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="5a9b6-151"><strong>Access コントロールリストエディターを開き </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-151">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="5a9b6-152">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="5a9b6-152">Additional considerations</span></span>

-   <span data-ttu-id="5a9b6-153">特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks.md)する」、「[承認者タスク](performing-approver-tasks.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks.md)を実行する」のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a9b6-153">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks.md), [Performing Editor Tasks](performing-editor-tasks.md), [Performing Approver Tasks](performing-approver-tasks.md), and [Performing Reviewer Tasks](performing-reviewer-tasks.md).</span></span>

### <span data-ttu-id="5a9b6-154">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="5a9b6-154">Additional references</span></span>

-   [<span data-ttu-id="5a9b6-155">[内容] タブ</span><span class="sxs-lookup"><span data-stu-id="5a9b6-155">Contents Tab</span></span>](contents-tab.md)

 

 





