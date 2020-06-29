---
title: アーカイブへのドメイン レベルのアクセスを委任する
description: アーカイブへのドメイン レベルのアクセスを委任する
author: dansimp
ms.assetid: d232069e-71d5-4b4d-b22e-bef11de1cfd4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01fbc4964493da6ba40382ac40671922eeffa30e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821007"
---
# <span data-ttu-id="ed681-103">アーカイブへのドメイン レベルのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="ed681-103">Delegate Domain-Level Access to the Archive</span></span>


<span data-ttu-id="ed681-104">グループポリシー管理者が適切なアクセス権を持ち、アーカイブ内のグループポリシーオブジェクト (Gpo) を制御できるように、環境の委任を設定します。</span><span class="sxs-lookup"><span data-stu-id="ed681-104">Set up delegation for your environment so that Group Policy administrators have the appropriate access to and control over Group Policy Objects (GPOs) in the archive.</span></span> <span data-ttu-id="ed681-105">操作を効率化するために適用できるベースラインの権限があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-105">There are baseline permissions you can apply to make operation more efficient.</span></span> <span data-ttu-id="ed681-106">組織のニーズに合った任意の方法でアクセス許可を付与することができます。</span><span class="sxs-lookup"><span data-stu-id="ed681-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="ed681-107">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="ed681-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="ed681-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ed681-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="ed681-109">ユーザーやグループがドメイン全体のすべての Gpo に対して適切な権限を持つように、アクセスを委任するには</span><span class="sxs-lookup"><span data-stu-id="ed681-109">To delegate access so that users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="ed681-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ed681-111">[ **Domain Delegation** ] タブをクリックし、ドメイン内のすべての gpo へのアクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ed681-111">Click the **Domain Delegation** tab, and configure access to all GPOs in the domain:</span></span>

    1.  <span data-ttu-id="ed681-112">ユーザーまたはグループにアクセス権を追加するには、[**追加**] ボタンをクリックし、ユーザーまたはグループを選択して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="ed681-113">[**グループまたはユーザーの追加**] ダイアログボックスで、役割を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="ed681-114">ユーザーまたはグループのアクセス許可を削除するには、ユーザーまたはグループを選択し、[**削除**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-114">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

    3.  <span data-ttu-id="ed681-115">ユーザーまたはグループに委任されたロールと権限を変更するには、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-115">To modify the roles and permissions delegated to a user or group, select click the **Advanced** button.</span></span> <span data-ttu-id="ed681-116">[**アクセス許可**] ダイアログボックスで、ユーザーまたはグループを選択し、そのユーザーまたはグループに割り当てる各役割のチェックボックスをオンにして、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ed681-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="ed681-117">**注** 編集者には、レビュー担当者の権限が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ed681-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="ed681-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="ed681-118">Additional considerations</span></span>

-   <span data-ttu-id="ed681-119">既定では、この手順を実行するには AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="ed681-120">具体的には、ドメインの [**セキュリティの変更**] アクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="ed681-121">AGPM を使用するグループポリシー管理者に読み取りアクセスを委任するには、**リストの内容**と**読み取り設定**のアクセス許可を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="ed681-122">こうすることで、ユーザーは AGPM の [**コンテンツ**] タブで gpo を表示できます。</span><span class="sxs-lookup"><span data-stu-id="ed681-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="ed681-123">その他の権限は、明示的に委任する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="ed681-124">グループポリシーソフトウェアインストールを最大限に活用するために、編集者には、展開された GPO のコピーに対する**読み取り**アクセス許可が付与されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ed681-124">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="ed681-125">グループポリシー Creator Owners グループのメンバーシップは制限されている必要があります。 soit は、Gpo へのアクセスの AGPM 管理を回避するために使用されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ed681-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="ed681-126">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="ed681-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="ed681-127">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="ed681-127">Additional references</span></span>

-   [<span data-ttu-id="ed681-128">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="ed681-128">Managing the Archive</span></span>](managing-the-archive.md)

 

 





