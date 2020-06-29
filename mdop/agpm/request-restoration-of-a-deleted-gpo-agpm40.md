---
title: 削除された GPO の復元を要求する
description: 削除された GPO の復元を要求する
author: dansimp
ms.assetid: bac5ca3b-be47-49b5-bf1b-96280625fda8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 606690554ca1f813e1c20787bca59cfe2de6432d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820374"
---
# <span data-ttu-id="53951-103">削除された GPO の復元を要求する</span><span class="sxs-lookup"><span data-stu-id="53951-103">Request Restoration of a Deleted GPO</span></span>


<span data-ttu-id="53951-104">承認者または AGPM 管理者 (フルコントロール) でない場合は、削除されたグループポリシーオブジェクト (GPO) をごみ箱から復元してアーカイブに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="53951-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the restoration of a deleted Group Policy Object (GPO) from the Recycle Bin to return it to the archive.</span></span>

<span data-ttu-id="53951-105">この手順を完了するには、編集者の役割を持つユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要な権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="53951-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="53951-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53951-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="53951-107">削除された GPO の復元を要求するには</span><span class="sxs-lookup"><span data-stu-id="53951-107">To request the restoration of a deleted GPO</span></span>**

1.  <span data-ttu-id="53951-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53951-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="53951-109">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="53951-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="53951-110">復元する GPO を右クリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53951-110">Right-click the GPO you want to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="53951-111">Gpo を復元するための特別なアクセス許可を持っていない場合は、削除された GPO の復元の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="53951-111">Unless you have special permission to restore GPOs, you must submit a request for restoration of the deleted GPO.</span></span> <span data-ttu-id="53951-112">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="53951-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="53951-113">GPO の監査トレールに表示されるコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53951-113">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="53951-114">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="53951-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="53951-115">GPO は [**ごみ箱**] タブから削除され、[**コントロール**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="53951-115">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="53951-116">**注** GPO が運用環境から削除された場合、アーカイブに復元しても、自動的に運用環境に再配置されることはありません。</span><span class="sxs-lookup"><span data-stu-id="53951-116">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="53951-117">GPO を運用環境に戻すには、GPO を展開します。</span><span class="sxs-lookup"><span data-stu-id="53951-117">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="53951-118">詳細については、「 [GPO の展開を要求する](request-deployment-of-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="53951-118">For information, see [Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md).</span></span>

 

### <span data-ttu-id="53951-119">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="53951-119">Additional considerations</span></span>

-   <span data-ttu-id="53951-120">既定では、この手順を実行するには、エディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="53951-120">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="53951-121">具体的には、GPO の [**コンテンツの一覧]** と [**設定の編集**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="53951-121">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="53951-122">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="53951-122">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="53951-123">GPO は [**ごみ箱**] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="53951-123">The GPO will be returned to the **Recycle Bin** tab.</span></span>

### <span data-ttu-id="53951-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="53951-124">Additional references</span></span>

-   [<span data-ttu-id="53951-125">GPO の削除または復元</span><span class="sxs-lookup"><span data-stu-id="53951-125">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

 

 





