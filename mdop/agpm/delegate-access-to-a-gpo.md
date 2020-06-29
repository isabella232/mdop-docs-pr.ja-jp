---
title: GPO へのアクセスを委任する
description: GPO へのアクセスを委任する
author: dansimp
ms.assetid: f1d6bb6c-d5bf-4080-a6cb-32774689f804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57a71528120b65676d25d952d9f9392dc0250ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818784"
---
# <span data-ttu-id="71ad8-103">GPO へのアクセスを委任する</span><span class="sxs-lookup"><span data-stu-id="71ad8-103">Delegate Access to a GPO</span></span>


<span data-ttu-id="71ad8-104">承認者は、**その承認者によって作成さ**れたグループポリシーオブジェクト (GPO) の管理を委任できます。</span><span class="sxs-lookup"><span data-stu-id="71ad8-104">An Approver can delegate the management of a controlled Group Policy object (GPO) that was **created by that Approver**.</span></span> <span data-ttu-id="71ad8-105">AGPM 管理者 (フルコントロール) と同様に、承認者はこのような GPO へのアクセスを委任することができます。これにより、選択した編集者はその GPO を編集してレビューでき、他の承認者は承認することができます。</span><span class="sxs-lookup"><span data-stu-id="71ad8-105">Like an AGPM Administrator (Full Control), the Approver can delegate access to such a GPO, so selected Editors can edit it, Reviewers can review it, and other Approvers can approve it.</span></span> <span data-ttu-id="71ad8-106">既定では、承認者は、別のグループポリシー管理者によって作成された Gpo へのアクセスを委任することはできません。</span><span class="sxs-lookup"><span data-stu-id="71ad8-106">By default, an Approver cannot delegate access to GPOs created by another Group Policy administrator.</span></span>

<span data-ttu-id="71ad8-107">この手順を完了するには、AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、GPO を作成した承認者のユーザーアカウント、または高度なグループポリシー管理で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71ad8-107">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="71ad8-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="71ad8-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="71ad8-109">制御された GPO の管理を委任するには</span><span class="sxs-lookup"><span data-stu-id="71ad8-109">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="71ad8-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71ad8-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="71ad8-111">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、制御された gpo を表示し、委任する gpo をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71ad8-111">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate.</span></span>

3.  <span data-ttu-id="71ad8-112">[**追加**] ボタンをクリックし、アクセスを許可するユーザーまたはグループを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71ad8-112">Click the **Add** button, select the users or groups to be permitted access, and then click **OK**.</span></span>

4.  <span data-ttu-id="71ad8-113">それぞれの権限をカスタマイズするには、[**コンテンツ**] タブの [**詳細設定**] ボタンをクリックして、役割の権限をチェックして許可または拒否します。</span><span class="sxs-lookup"><span data-stu-id="71ad8-113">To customize the permissions for each, click the **Advanced** button on the **Contents** tab and check role permissions to allow or deny.</span></span> <span data-ttu-id="71ad8-114">(詳細なコントロールの場合は、[**アクセス許可**] ダイアログボックスで [**詳細設定**] をクリックします)。</span><span class="sxs-lookup"><span data-stu-id="71ad8-114">(For more detailed control, click **Advanced** in the **Permissions** dialog box.)</span></span>

5.  <span data-ttu-id="71ad8-115">[**適用**] をクリックし、[**アクセス許可**] ダイアログボックスで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="71ad8-115">Click **Apply**, and then click **OK** in the **Permissions** dialog box.</span></span>

### <span data-ttu-id="71ad8-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="71ad8-116">Additional considerations</span></span>

-   <span data-ttu-id="71ad8-117">既定では、この手順を実行するには、GPO を作成または管理した承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="71ad8-117">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="71ad8-118">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持ち、GPO のセキュリティのアクセス許可を**変更**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71ad8-118">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

### <span data-ttu-id="71ad8-119">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="71ad8-119">Additional references</span></span>

-   [<span data-ttu-id="71ad8-120">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="71ad8-120">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





