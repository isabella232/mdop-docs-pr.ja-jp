---
title: ドメイン レベルのアクセスを委任する
description: ドメイン レベルのアクセスを委任する
author: dansimp
ms.assetid: 64c8e773-38cc-4991-9ed2-5a801094d06e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7eb4c33e60b0d995e45fca6c9e91a26c30dd4a7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820997"
---
# <span data-ttu-id="43df2-103">ドメイン レベルのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="43df2-103">Delegate Domain-Level Access</span></span>


<span data-ttu-id="43df2-104">グループポリシー管理者が適切なアクセス権を持ち、グループポリシーオブジェクト (Gpo) を制御できるように、環境の委任を設定します。</span><span class="sxs-lookup"><span data-stu-id="43df2-104">Set up delegation for your environment so Group Policy administrators have the appropriate access to and control over Group Policy objects (GPOs).</span></span> <span data-ttu-id="43df2-105">高度なグループポリシー管理 (AGPM) の操作をより効率的にするために、適用できるベースラインのアクセス許可があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-105">There are baseline permissions you can apply to make the operation of Advanced Group Policy Management (AGPM) more efficient.</span></span> <span data-ttu-id="43df2-106">組織のニーズに合った任意の方法でアクセス許可を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="43df2-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="43df2-107">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割または高度なグループポリシー管理の必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="43df2-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="43df2-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="43df2-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="43df2-109">ユーザーやグループがドメイン全体のすべての Gpo に対する適切な権限を持つように、アクセスを委任するには</span><span class="sxs-lookup"><span data-stu-id="43df2-109">To delegate access so users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="43df2-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="43df2-111">[ **Domain Delegation** ] タブをクリックし、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-111">Click the **Domain Delegation** tab, then click the **Advanced** button.</span></span>

3.  <span data-ttu-id="43df2-112">[**アクセス許可**] ダイアログボックスで、個別に割り当てる役割のチェックボックスをオンにして、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-112">In the **Permissions** dialog box, click the check box for each role to be assigned to an individual, and then click the **Advanced** button.</span></span>

    <span data-ttu-id="43df2-113">**注** 編集者には、レビュー担当者の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="43df2-113">**Note** Editor and Approver include Reviewer permissions.</span></span>

     

4.  <span data-ttu-id="43df2-114">[**詳細なセキュリティ設定**] ダイアログボックスで、グループポリシーの管理者を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-114">In the **Advanced Security Settings** dialog box, select a Group Policy administrator, and then click **Edit**.</span></span>

5.  <span data-ttu-id="43df2-115">[**適用先**] で、**このオブジェクトと入れ子になったオブジェクト**を選び、標準の AGPM ロールを超える特殊なアクセス許可を構成し、[**アクセス許可\*\*\*\*エントリ**] ダイアログボックスで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-115">For **Apply onto**, select **This object and nested objects**, configure any special permissions beyond the standard AGPM roles, then click **OK** in the **Permission** **Entry** dialog box.</span></span>

6.  <span data-ttu-id="43df2-116">[**詳細なセキュリティ設定**] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-116">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="43df2-117">[**アクセス許可**] ダイアログボックスで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="43df2-117">In the **Permissions** dialog box, click **OK**.</span></span>

### <span data-ttu-id="43df2-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="43df2-118">Additional considerations</span></span>

-   <span data-ttu-id="43df2-119">既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="43df2-120">具体的には、ドメインの [**セキュリティの変更**] アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="43df2-121">AGPM を使用するグループポリシー管理者に読み取りアクセスを委任するには、**リストの内容**と**読み取り設定**のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="43df2-122">こうすることで、ユーザーは AGPM の [**コンテンツ**] タブで gpo を表示できます。</span><span class="sxs-lookup"><span data-stu-id="43df2-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="43df2-123">**このオブジェクトと入れ子になったオブジェクト**に適用するアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="43df2-123">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="43df2-124">その他の権限は、明示的に委任する必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-124">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="43df2-125">グループポリシーソフトウェアインストールを最大限に活用するために、編集者には、展開された GPO のコピーに対する**読み取り**アクセス許可が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-125">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="43df2-126">グループポリシー Creator Owners グループのメンバーシップは、Gpo へのアクセスの AGPM 管理を回避するために使用されないように制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="43df2-126">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="43df2-127">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="43df2-127">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="43df2-128">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="43df2-128">Additional references</span></span>

-   [<span data-ttu-id="43df2-129">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="43df2-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





