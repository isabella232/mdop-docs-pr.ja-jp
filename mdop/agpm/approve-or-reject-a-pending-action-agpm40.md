---
title: 保留中のアクションを承認または拒否する
description: 保留中のアクションを承認または拒否する
author: dansimp
ms.assetid: 078ea8b5-9ac5-45fc-9ac1-a1aa629c10b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 61014ec46db2beb9a525abe8d9b2b0902b3aa78d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819224"
---
# <span data-ttu-id="e3b2c-103">保留中のアクションを承認または拒否する</span><span class="sxs-lookup"><span data-stu-id="e3b2c-103">Approve or Reject a Pending Action</span></span>


<span data-ttu-id="e3b2c-104">承認者の主な責務は、グループポリシーオブジェクト (GPO) の作成、展開、削除の要求を、それらの操作を実行する権限を持っていないエディターまたは校閲者に対して評価し、承認または拒否することです。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-104">The core responsibility of an Approver is to evaluate and then approve or reject requests for Group Policy Object (GPO) creation, deployment, and deletion from Editors or Reviewers who do not have permission to complete those actions.</span></span> <span data-ttu-id="e3b2c-105">レポートは、承認者に対して新しいバージョンの GPO の評価に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-105">Reports can assist an Approver with evaluating a new version of a GPO.</span></span>

<span data-ttu-id="e3b2c-106">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="e3b2c-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="e3b2c-108">保留中のリクエストを承認または却下するには</span><span class="sxs-lookup"><span data-stu-id="e3b2c-108">To approve or reject a pending request</span></span>**

1.  <span data-ttu-id="e3b2c-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="e3b2c-110">[**コンテンツ**] タブで、[**保留中**] タブをクリックして、保留中の gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-110">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

3.  <span data-ttu-id="e3b2c-111">保留中の GPO を右クリックし、[**承認**] または [**拒否**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-111">Right-click a pending GPO, and then click either **Approve** or **Reject**.</span></span>

4.  <span data-ttu-id="e3b2c-112">展開を承認する場合は、[**保留中の操作を承認**します] ダイアログボックスの [**詳細**] をクリックして、GPO へのリンクを確認します。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-112">If approving deployment, click **Advanced** in the **Approve Pending Operation** dialog box to review links to the GPO.</span></span> <span data-ttu-id="e3b2c-113">ツリー内の項目の上にマウスポインターを置くと、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-113">Pause the mouse pointer on an item in the tree to display details.</span></span>

    -   <span data-ttu-id="e3b2c-114">既定では、GPO へのすべてのリンクが復元されます。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="e3b2c-115">リンクが復元されないようにするには、そのリンクのチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="e3b2c-116">すべてのリンクが復元されないようにするには、[ **GPO の展開**] ダイアログボックスの [**リンクの復元**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="e3b2c-117">[**はい**] または [ **OK** ] をクリックして、保留中のアクションの承認または拒否を確認します。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-117">Click **Yes** or **OK** to confirm approval or rejection of the pending action.</span></span> <span data-ttu-id="e3b2c-118">要求を承認した場合、GPO は実行されたアクションの適切なタブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-118">If you have approved the request, the GPO is moved to the appropriate tab for the action performed.</span></span>

    <span data-ttu-id="e3b2c-119">**注** 承認者の電子メールアドレスが [**ドメイン\*\*\*\*委任**] タブの [**宛先の電子メールアドレス**] フィールドに含まれている場合、編集者は、エディターまたは校閲者が要求を送信したときに、AGPM エイリアスからメールを受信します。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-119">**Note** If an Approver's e-mail address is included in the **To e-mail address** field on the **Domain** **Delegation** tab, the Approver will receive e-mail from the AGPM alias when an Editor or Reviewer submits a request.</span></span>

     

### <span data-ttu-id="e3b2c-120">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e3b2c-120">Additional considerations</span></span>

-   <span data-ttu-id="e3b2c-121">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-121">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="e3b2c-122">具体的には、承認する要求を実行するために必要なアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3b2c-122">Specifically, you must have the permissions required to perform the request that you are approving.</span></span>

### <span data-ttu-id="e3b2c-123">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="e3b2c-123">Additional references</span></span>

-   [<span data-ttu-id="e3b2c-124">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e3b2c-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

 

 





