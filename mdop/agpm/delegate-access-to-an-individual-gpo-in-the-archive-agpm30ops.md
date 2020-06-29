---
title: アーカイブ内の個々の GPO へのアクセスを委任する
description: アーカイブ内の個々の GPO へのアクセスを委任する
author: dansimp
ms.assetid: 7b37b188-2b6b-4e52-be97-8ef899e9893b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 592937a28b0e2556991b0c338b88b2cfa88ba83d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818767"
---
# <span data-ttu-id="a6467-103">アーカイブ内の個々の GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="a6467-103">Delegate Access to an Individual GPO in the Archive</span></span>


<span data-ttu-id="a6467-104">AGPM 管理者 (フルコントロール) として、管理されたグループポリシーオブジェクト (GPO) の管理を、選択したグループと編集者が編集できるように、また承認者が承認できるように、アーカイブに委任することができます。</span><span class="sxs-lookup"><span data-stu-id="a6467-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy Object (GPO) in the archive so that selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="a6467-105">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、GPO を作成した承認者のユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="a6467-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a6467-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="a6467-107">制御された GPO の管理を委任するには</span><span class="sxs-lookup"><span data-stu-id="a6467-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="a6467-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="a6467-109">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、制御された gpo を表示し、委任する gpo をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="a6467-110">ユーザーまたはグループにアクセス権を追加するには、[**追加**] ボタンをクリックし、ユーザーまたはグループを選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-110">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="a6467-111">[**グループまたはユーザーの追加**] ダイアログボックスで、役割を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-111">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="a6467-112">ユーザーまたはグループのアクセス許可を削除するには、ユーザーまたはグループを選択し、[**削除**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-112">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

        <span data-ttu-id="a6467-113">**注** ユーザーまたはグループがドメイン全体のアクセスを継承している場合、[**削除**] ボタンは使用できません。</span><span class="sxs-lookup"><span data-stu-id="a6467-113">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="a6467-114">[**ドメイン委任**] タブで、ドメイン全体のアクセスを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="a6467-114">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="a6467-115">ユーザーまたはグループに委任されるロールと権限を変更するには、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-115">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="a6467-116">[**アクセス許可**] ダイアログボックスで、ユーザーまたはグループを選択し、そのユーザーまたはグループに割り当てる各役割のチェックボックスをオンにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a6467-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and click **OK**.</span></span>

        <span data-ttu-id="a6467-117">**注** 編集者には、レビュー担当者の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a6467-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="a6467-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a6467-118">Additional considerations</span></span>

-   <span data-ttu-id="a6467-119">既定では、この手順を実行するには、GPO を作成または管理した承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-119">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="a6467-120">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持ち、GPO のセキュリティのアクセス許可を**変更**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-120">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="a6467-121">AGPM を使用するグループポリシー管理者に読み取りアクセスを委任するには、**リストの内容**と**読み取り設定**のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="a6467-122">こうすることで、ユーザーは AGPM の [**コンテンツ**] タブで gpo を表示できます。</span><span class="sxs-lookup"><span data-stu-id="a6467-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="a6467-123">その他の権限は、明示的に委任する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="a6467-124">編集者は、グループポリシーソフトウェアインストールを最大限に活用するために、展開された GPO のコピーに対する**読み取り**アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a6467-124">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="a6467-125">グループポリシー Creator Owners グループのメンバーシップは制限されている必要があります。 soit は、Gpo へのアクセスの AGPM 管理を回避するために使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="a6467-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="a6467-126">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="a6467-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="a6467-127">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="a6467-127">Additional references</span></span>

-   [<span data-ttu-id="a6467-128">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="a6467-128">Managing the Archive</span></span>](managing-the-archive.md)

 

 





