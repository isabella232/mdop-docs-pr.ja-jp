---
title: 運用環境へのアクセスを委任する
description: 運用環境へのアクセスを委任する
author: dansimp
ms.assetid: 4c670581-8c47-41ea-80eb-02846ff1ec1f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a3920a8ba5835cbbcb8a74f0af4e3ca1e1c5f43f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818727"
---
# <span data-ttu-id="4f645-103">運用環境へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="4f645-103">Delegate Access to the Production Environment</span></span>


<span data-ttu-id="4f645-104">高度なグループポリシー管理 (AGPM) では、ドメインの運用環境のグループポリシーオブジェクト (Gpo) へのアクセスを変更し、それらの Gpo に対する既存のアクセス許可を置き換えます。</span><span class="sxs-lookup"><span data-stu-id="4f645-104">In Advanced Group Policy Management (AGPM), you can change access to Group Policy Objects (GPOs) in the production environment of the domain, replacing any existing permissions on those GPOs.</span></span> <span data-ttu-id="4f645-105">ドメインレベルでアクセス許可を構成して、ユーザーがグループポリシー管理コンソール (GPMC) で**Change Control**フォルダーを使用していない場合に、運用環境で gpo のセキュリティを編集、削除、または変更できないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4f645-105">You can configure permissions at the domain level to either allow or prevent users from editing, deleting, or modifying the security of GPOs in the production environment when they are not using the **Change Control** folder in the Group Policy Management Console (GPMC).</span></span>

**<span data-ttu-id="4f645-106">注</span><span class="sxs-lookup"><span data-stu-id="4f645-106">Note</span></span>**  
-   <span data-ttu-id="4f645-107">運用環境へのアクセスを委任する方法を変更しても、ユーザーが Gpo をリンクする機能には影響しません。</span><span class="sxs-lookup"><span data-stu-id="4f645-107">Changing how access to the production environment is delegated does not affect users' ability to link GPOs.</span></span>

-   <span data-ttu-id="4f645-108">Gpo が制御または展開されている場合は、他のアカウント ([**読み取り**] および [**適用**] のアクセス許可を持つアカウントを除く) へのアクセスは削除されます。</span><span class="sxs-lookup"><span data-stu-id="4f645-108">When GPOs are controlled or deployed, access for any other accounts except those with **Read** and **Apply** permissions is removed.</span></span>

 

<span data-ttu-id="4f645-109">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割か、高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="4f645-109">A user account that has either the role of AGPM Administrator (Full Control) or the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="4f645-110">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4f645-110">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4f645-111">ドメインの運用環境で Gpo へのアクセスを変更するには</span><span class="sxs-lookup"><span data-stu-id="4f645-111">To change access to GPOs in the production environment of the domain</span></span>**

1.  <span data-ttu-id="4f645-112">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f645-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4f645-113">[**運用の委任**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f645-113">Click the **Production Delegation** tab.</span></span>

3.  <span data-ttu-id="4f645-114">運用環境にアクセスできないユーザーまたはグループにアクセス許可を追加するか、またはアクセス権があるユーザーまたはグループのアクセス許可を置き換えるには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4f645-114">To add permissions for a user or group that does not have access to the production environment, or to replace the permissions for a user or group that does have access:</span></span>

    1.  <span data-ttu-id="4f645-115">[**追加**] をクリックし、ユーザーまたはグループを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f645-115">Click **Add**, select a user or group, and then click **OK**.</span></span>

    2.  <span data-ttu-id="4f645-116">[権限] を選択して、実稼働環境のユーザーまたはグループに委任し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f645-116">Select permissions to delegate to that user or group for the production environment, and then click **OK**.</span></span>

4.  <span data-ttu-id="4f645-117">ユーザーまたはグループの運用環境に対するすべての権限を削除するには、ユーザーまたはグループを選択し、[**削除**] をクリックして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f645-117">To remove all permissions to the production environment for a user or group, select the user or group, click **Remove**, and then click **OK**.</span></span>

### <span data-ttu-id="4f645-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="4f645-118">Additional considerations</span></span>

-   <span data-ttu-id="4f645-119">既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f645-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="4f645-120">具体的には、ドメインの [**セキュリティの変更**] アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f645-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="4f645-121">AGPM サービスアカウントのアクセス許可は、[運用の**委任**] タブで変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f645-121">Permissions for the AGPM Service Account cannot be changed on the **Production Delegation** tab.</span></span>

-   <span data-ttu-id="4f645-122">既定では、次のアカウントには、実稼働環境の Gpo に対する権限があります。</span><span class="sxs-lookup"><span data-stu-id="4f645-122">By default, the following accounts have permissions for GPOs in the production environment:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="4f645-123">Account</span><span class="sxs-lookup"><span data-stu-id="4f645-123">Account</span></span></th>
    <th align="left"><span data-ttu-id="4f645-124">Gpo の既定のアクセス許可</span><span class="sxs-lookup"><span data-stu-id="4f645-124">Default Permissions for GPOs</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4f645-125">&lt;AGPM サービスアカウント&gt;</span><span class="sxs-lookup"><span data-stu-id="4f645-125">&lt;AGPM Service Account&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-126">設定の編集、削除、セキュリティの変更</span><span class="sxs-lookup"><span data-stu-id="4f645-126">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4f645-127">認証済みユーザー</span><span class="sxs-lookup"><span data-stu-id="4f645-127">Authenticated Users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-128">読み取り、適用</span><span class="sxs-lookup"><span data-stu-id="4f645-128">Read, Apply</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4f645-129">ドメイン管理者</span><span class="sxs-lookup"><span data-stu-id="4f645-129">Domain Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-130">設定の編集、削除、セキュリティの変更</span><span class="sxs-lookup"><span data-stu-id="4f645-130">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4f645-131">エンタープライズ管理者</span><span class="sxs-lookup"><span data-stu-id="4f645-131">Enterprise Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-132">設定の編集、削除、セキュリティの変更</span><span class="sxs-lookup"><span data-stu-id="4f645-132">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4f645-133">エンタープライズドメインコントローラー</span><span class="sxs-lookup"><span data-stu-id="4f645-133">Enterprise Domain Controllers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-134">Read</span><span class="sxs-lookup"><span data-stu-id="4f645-134">Read</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4f645-135">システム</span><span class="sxs-lookup"><span data-stu-id="4f645-135">System</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4f645-136">設定の編集、削除、セキュリティの変更</span><span class="sxs-lookup"><span data-stu-id="4f645-136">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="4f645-137">グループポリシー Creator Owners グループのメンバーシップは制限されている必要があります。 soit は、Gpo へのアクセスの AGPM 管理を回避するために使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="4f645-137">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="4f645-138">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="4f645-138">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="4f645-139">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="4f645-139">Additional references</span></span>

-   [<span data-ttu-id="4f645-140">高度なグループ ポリシーの管理の構成</span><span class="sxs-lookup"><span data-stu-id="4f645-140">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





