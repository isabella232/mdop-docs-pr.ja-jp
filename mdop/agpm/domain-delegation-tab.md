---
title: '[ドメインの委任] タブ'
description: '[ドメインの委任] タブ'
author: dansimp
ms.assetid: 15a9bfff-e25b-4b62-9ebc-521a5f4eae96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d49083bcefe6c7edcb3a95dc63d2249826d50327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818627"
---
# <span data-ttu-id="372b7-103">[ドメインの委任] タブ</span><span class="sxs-lookup"><span data-stu-id="372b7-103">Domain Delegation Tab</span></span>


<span data-ttu-id="372b7-104">[**変更] コントロール**ウィンドウの [**ドメインの委任**] タブには、アーカイブへのドメインレベルのアクセス権を持つグループポリシー管理者の一覧が表示され、それぞれの役割が示されます。</span><span class="sxs-lookup"><span data-stu-id="372b7-104">The **Domain Delegation** tab on the **Change Control** pane provides a list of Group Policy administrators who have domain-level access to the archive and indicates the roles of each.</span></span> <span data-ttu-id="372b7-105">さらに、このタブでは、AGPM 管理者 (フルコントロール) を使用して、エディター、承認者、校閲者、その他の AGPM 管理者に対してドメインレベルの権限を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="372b7-105">Additionally, this tab enables AGPM Administrators (Full Control) to configure domain-level permissions for Editors, Approvers, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="372b7-106">[**ドメインの委任**] タブには、ドメインレベルでの高度なグループポリシー管理 (AGPM) の電子メール通知とロールベースの委任の構成という2つのセクションがあります。</span><span class="sxs-lookup"><span data-stu-id="372b7-106">There are two sections on the **Domain Delegation** tab—configuration of e-mail notification and role-based delegation for Advanced Group Policy Management (AGPM) at the domain level.</span></span>

## <span data-ttu-id="372b7-107">メール通知の設定</span><span class="sxs-lookup"><span data-stu-id="372b7-107">Configuration of e-mail notification</span></span>


<span data-ttu-id="372b7-108">このタブの [電子メール通知] セクションには、AGPM で操作が保留中の場合に通知を受け取る承認者が示されます。</span><span class="sxs-lookup"><span data-stu-id="372b7-108">The e-mail notification section of this tab identifies the Approvers that will receive notification when operations are pending in AGPM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="372b7-109">設定</span><span class="sxs-lookup"><span data-stu-id="372b7-109">Setting</span></span></th>
<th align="left"><span data-ttu-id="372b7-110">説明</span><span class="sxs-lookup"><span data-stu-id="372b7-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="372b7-111">アップグレード前</span><span class="sxs-lookup"><span data-stu-id="372b7-111">From</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-112">承認者に通知が送信される AGPM エイリアス。</span><span class="sxs-lookup"><span data-stu-id="372b7-112">The AGPM alias from which notification is sent to Approvers.</span></span> <span data-ttu-id="372b7-113">複数のドメインがある環境では、環境全体で同じエイリアスを使用するか、ドメインごとに異なるエイリアスを使用することができます。</span><span class="sxs-lookup"><span data-stu-id="372b7-113">In an environment with multiple domains, this can be the same alias throughout the environment or a different alias for each domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="372b7-114">アップグレード後</span><span class="sxs-lookup"><span data-stu-id="372b7-114">To</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-115">通知が送信される承認者の電子メールアドレスのコンマ区切りリスト</span><span class="sxs-lookup"><span data-stu-id="372b7-115">A comma-delimited list of e-mail addresses of Approvers to whom notification is to be sent</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="372b7-116">SMTP サーバー</span><span class="sxs-lookup"><span data-stu-id="372b7-116">SMTP server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-117">メールサーバーの名前 (mail.contoso.com など)</span><span class="sxs-lookup"><span data-stu-id="372b7-117">The name of the e-mail server, such as mail.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="372b7-118">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="372b7-118">User name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-119">SMTP サーバーへのアクセス権を持つユーザー</span><span class="sxs-lookup"><span data-stu-id="372b7-119">A user with access to the SMTP server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="372b7-120">パスワード</span><span class="sxs-lookup"><span data-stu-id="372b7-120">Password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-121">SMTP サーバーに対する認証のためのユーザーパスワード</span><span class="sxs-lookup"><span data-stu-id="372b7-121">User's password for authentication to the SMTP server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="372b7-122">パスワードの確認</span><span class="sxs-lookup"><span data-stu-id="372b7-122">Confirm password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-123">ユーザーのパスワードを確認する</span><span class="sxs-lookup"><span data-stu-id="372b7-123">Confirm user's password</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="372b7-124">ドメインレベルの役割ベースの委任</span><span class="sxs-lookup"><span data-stu-id="372b7-124">Domain-level role-based delegation</span></span>


<span data-ttu-id="372b7-125">このタブの [ロールベースの委任] セクションに表示される、AGPM 管理者は、アーカイブへのアクセス権を持つドメインの各グループとユーザーに対して、許可、拒否、継承された権限を委任することができます。</span><span class="sxs-lookup"><span data-stu-id="372b7-125">The role-based delegation section of this tab displays and enables an AGPM Administrator to delegate allowed, denied, and inherited permissions for each group and user on the domain with access to the archive.</span></span> <span data-ttu-id="372b7-126">AGPM 管理者は、標準の AGPM ロール (エディター、承認者、レビュー担当者、AGPM 管理者) を使用するか、グループポリシー管理者ごとに権限のカスタマイズされた組み合わせを使って、ドメイン全体の権限を構成できます。</span><span class="sxs-lookup"><span data-stu-id="372b7-126">An AGPM Administrator can configure domain-wide permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions for each Group Policy administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="372b7-127">ボタン</span><span class="sxs-lookup"><span data-stu-id="372b7-127">Button</span></span></th>
<th align="left"><span data-ttu-id="372b7-128">効果</span><span class="sxs-lookup"><span data-stu-id="372b7-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="372b7-129">Add</span><span class="sxs-lookup"><span data-stu-id="372b7-129">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-130">セキュリティ記述子に新しいエントリを追加します。</span><span class="sxs-lookup"><span data-stu-id="372b7-130">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="372b7-131">Active Directory 内のすべてのユーザーまたはグループをグループポリシーの管理者として追加できます。</span><span class="sxs-lookup"><span data-stu-id="372b7-131">Any users or groups in Active Directory can be added as Group Policy administrators.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="372b7-132">[削除]</span><span class="sxs-lookup"><span data-stu-id="372b7-132">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-133">選択したグループポリシーの管理者を [アクセス制御] の一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="372b7-133">Remove the selected Group Policy administrators from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="372b7-134">プロパティ</span><span class="sxs-lookup"><span data-stu-id="372b7-134">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-135">選択したグループポリシー管理者のプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="372b7-135">Display the properties for the selected Group Policy administrators.</span></span> <span data-ttu-id="372b7-136">[プロパティ] ページは、[ <strong> Active Directory ユーザーとコンピューター] のオブジェクトに対して表示されるものと同じです </strong> 。</span><span class="sxs-lookup"><span data-stu-id="372b7-136">The properties page is the same one displayed for an object in <strong>Active Directory User and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="372b7-137">詳細設定</span><span class="sxs-lookup"><span data-stu-id="372b7-137">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="372b7-138"><strong>Access コントロールリストエディターを開き </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="372b7-138">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="372b7-139">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="372b7-139">Additional considerations</span></span>

-   <span data-ttu-id="372b7-140">特定のタスクに関連するロールと権限の詳細については、「 [AGPM 管理者タスク](performing-agpm-administrator-tasks.md)を実行する」、「[エディタータスクを実行](performing-editor-tasks.md)する」、「[承認者タスク](performing-approver-tasks.md)を実行する」、「[校閲者タスク](performing-reviewer-tasks.md)を実行する」のタスクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="372b7-140">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks.md), [Performing Editor Tasks](performing-editor-tasks.md), [Performing Approver Tasks](performing-approver-tasks.md), and [Performing Reviewer Tasks](performing-reviewer-tasks.md).</span></span>

### <span data-ttu-id="372b7-141">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="372b7-141">Additional references</span></span>

-   [<span data-ttu-id="372b7-142">ユーザー インターフェイス: 高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="372b7-142">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

-   [<span data-ttu-id="372b7-143">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="372b7-143">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





