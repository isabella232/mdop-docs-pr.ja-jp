---
title: 制御された GPO の管理を委任する
description: 制御された GPO の管理を委任する
author: dansimp
ms.assetid: 96b4bfb3-5657-4267-8326-85d7a0db87ce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0833e6b002d15c64e3b60fa0570640f8ea7fb2ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821004"
---
# <span data-ttu-id="c3f08-103">制御された GPO の管理を委任する</span><span class="sxs-lookup"><span data-stu-id="c3f08-103">Delegate Management of a Controlled GPO</span></span>


<span data-ttu-id="c3f08-104">承認者は、その承認者によって作成されたグループポリシーオブジェクト (GPO) の管理を委任できます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-104">An Approver can delegate the management of a controlled Group Policy Object (GPO) that was created by that Approver.</span></span> <span data-ttu-id="c3f08-105">AGPM 管理者 (フルコントロール) と同様に、承認者は、このような GPO へのアクセスを委任して、選択した編集者が編集できるようにしたり、校閲者が確認したり、他の承認者が承認できるようにしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-105">Like an AGPM Administrator (Full Control), the Approver can delegate access to such a GPO so that selected Editors can edit it, Reviewers can review it, and other Approvers can approve it.</span></span> <span data-ttu-id="c3f08-106">既定では、承認者は、別のグループポリシー管理者によって作成された Gpo へのアクセスを委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="c3f08-106">By default, an Approver cannot delegate access to GPOs created by another Group Policy administrator.</span></span>

<span data-ttu-id="c3f08-107">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、GPO を作成した承認者のユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-107">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="c3f08-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3f08-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c3f08-109">制御された GPO の管理を委任するには</span><span class="sxs-lookup"><span data-stu-id="c3f08-109">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="c3f08-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c3f08-111">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、制御された gpo を表示し、委任する gpo をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-111">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="c3f08-112">ユーザーまたはグループにアクセス権を追加するには、[**追加**] ボタンをクリックし、ユーザーまたはグループを選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="c3f08-113">[**グループまたはユーザーの追加**] ダイアログボックスで、役割を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="c3f08-114">ユーザーまたはグループのアクセス許可を削除するには、ユーザーまたはグループを選択し、[**削除**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-114">To remove access for a user or group, select the user or group, and then click the **Remove** button.</span></span>

        <span data-ttu-id="c3f08-115">**注** ユーザーまたはグループがドメイン全体のアクセスを継承している場合、[**削除**] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="c3f08-115">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="c3f08-116">[**ドメイン委任**] タブで、ドメイン全体のアクセスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-116">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="c3f08-117">ユーザーまたはグループに委任されるロールと権限を変更するには、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-117">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="c3f08-118">[**アクセス許可**] ダイアログボックスで、ユーザーまたはグループを選択し、そのユーザーまたはグループに割り当てる各役割のチェックボックスをオンにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3f08-118">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="c3f08-119">**注** 編集者には、レビュー担当者の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c3f08-119">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="c3f08-120">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c3f08-120">Additional considerations</span></span>

-   <span data-ttu-id="c3f08-121">既定では、この手順を実行するには、GPO を作成または管理した承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-121">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="c3f08-122">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持ち、GPO のセキュリティのアクセス許可を**変更**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-122">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="c3f08-123">AGPM を使用するグループポリシー管理者に読み取りアクセスを委任するには、**リストの内容**と**読み取り設定**のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-123">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="c3f08-124">こうすることで、ユーザーは AGPM の [**コンテンツ**] タブで gpo を表示できます。</span><span class="sxs-lookup"><span data-stu-id="c3f08-124">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="c3f08-125">その他の権限は、明示的に委任する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-125">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="c3f08-126">編集者は、グループポリシーソフトウェアインストールを最大限に活用するために、展開された GPO のコピーに対する**読み取り**アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3f08-126">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

### <span data-ttu-id="c3f08-127">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="c3f08-127">Additional references</span></span>

-   [<span data-ttu-id="c3f08-128">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="c3f08-128">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





