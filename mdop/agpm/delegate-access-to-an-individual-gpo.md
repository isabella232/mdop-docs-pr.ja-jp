---
title: 個々 の GPO へのアクセスを委任する
description: 個々 の GPO へのアクセスを委任する
author: dansimp
ms.assetid: b2a7d550-14bf-4b41-b6e4-2cc091eedd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5d2ae8c6ef52eae39feb67b9df42e84f523300
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818734"
---
# <span data-ttu-id="7f34d-103">個々 の GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="7f34d-103">Delegate Access to an Individual GPO</span></span>


<span data-ttu-id="7f34d-104">AGPM 管理者 (フルコントロール) として、制御されたグループポリシーオブジェクト (GPO) の管理を委任することができます。これにより、選択したグループと編集者が編集できるようになり、レビュー担当者は承認できます。</span><span class="sxs-lookup"><span data-stu-id="7f34d-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy object (GPO), so selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="7f34d-105">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、GPO を作成した承認者のユーザーアカウント、または高度なグループポリシー管理で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="7f34d-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7f34d-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="7f34d-107">制御された GPO の管理を委任するには</span><span class="sxs-lookup"><span data-stu-id="7f34d-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="7f34d-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f34d-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="7f34d-109">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、制御された gpo を表示し、委任する gpo をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f34d-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate.</span></span>

3.  <span data-ttu-id="7f34d-110">[**追加**] ボタンをクリックし、アクセスを許可するユーザーまたはグループを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f34d-110">Click the **Add** button, select the users or groups to be permitted access, and then click **OK**.</span></span>

4.  <span data-ttu-id="7f34d-111">ユーザーまたはグループごとにアクセス許可をカスタマイズするには、[**コンテンツ**] タブの [**詳細設定**] ボタンをクリックし、許可または拒否する役割の権限を確認します。</span><span class="sxs-lookup"><span data-stu-id="7f34d-111">To customize the permissions for each user or group, click the **Advanced** button on the **Contents** tab and check role permissions to allow or deny.</span></span> <span data-ttu-id="7f34d-112">(詳細なコントロールの場合は、[**アクセス許可**] ダイアログボックスで [**詳細設定**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="7f34d-112">(For more detailed control, click **Advanced** in the **Permissions** dialog box.)</span></span>

5.  <span data-ttu-id="7f34d-113">[**適用**] をクリックし、[**アクセス許可**] ダイアログボックスで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="7f34d-113">Click **Apply**, and then click **OK** in the **Permissions** dialog box.</span></span>

### <span data-ttu-id="7f34d-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="7f34d-114">Additional considerations</span></span>

-   <span data-ttu-id="7f34d-115">既定では、この手順を実行するには、GPO を作成または管理した承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-115">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="7f34d-116">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持ち、GPO のセキュリティのアクセス許可を**変更**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-116">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="7f34d-117">AGPM を使用するグループポリシー管理者に読み取りアクセスを委任するには、**リストの内容**と**読み取り設定**のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-117">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="7f34d-118">こうすることで、ユーザーは AGPM の [**コンテンツ**] タブで gpo を表示できます。</span><span class="sxs-lookup"><span data-stu-id="7f34d-118">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="7f34d-119">**このオブジェクトと入れ子になったオブジェクト**に適用するアクセス許可を設定します。</span><span class="sxs-lookup"><span data-stu-id="7f34d-119">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="7f34d-120">その他の権限は、明示的に委任する必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-120">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="7f34d-121">編集者は、グループポリシーソフトウェアインストールを最大限に活用するために、展開された GPO のコピーに対する**読み取り**アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-121">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="7f34d-122">グループポリシー Creator Owners グループのメンバーシップは、Gpo へのアクセスの AGPM 管理を回避するために使用されないように制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="7f34d-122">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="7f34d-123">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="7f34d-123">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="7f34d-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="7f34d-124">Additional references</span></span>

-   [<span data-ttu-id="7f34d-125">AGPM 管理者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="7f34d-125">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





