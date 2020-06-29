---
title: GPO の削除を要求する
description: GPO の削除を要求する
author: dansimp
ms.assetid: 2410f7a1-ccca-44cf-ab26-76ad474409e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfdb50fba872b76c82152b469f787f2e1a6fb539
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818427"
---
# <span data-ttu-id="c0fd9-103">GPO の削除を要求する</span><span class="sxs-lookup"><span data-stu-id="c0fd9-103">Request Deletion of a GPO</span></span>


<span data-ttu-id="c0fd9-104">承認者または AGPM 管理者 (フルコントロール) でない場合は、グループポリシーオブジェクト (GPO) の削除を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the deletion of a Group Policy Object (GPO).</span></span>

<span data-ttu-id="c0fd9-105">この手順を完了するには、編集者の役割を持つユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要な権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="c0fd9-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c0fd9-107">コントロールされた GPO の削除を要求するには</span><span class="sxs-lookup"><span data-stu-id="c0fd9-107">To request the deletion of a controlled GPO</span></span>**

1.  <span data-ttu-id="c0fd9-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c0fd9-109">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="c0fd9-110">削除する GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="c0fd9-111">展開されているバージョンの GPO を運用環境でそのまま残して、アーカイブから GPO を削除するには、[ **gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="c0fd9-112">ドメインのアーカイブ環境と運用環境の両方から GPO を削除するには、[**アーカイブと運用] から [gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-112">To delete the GPO from both the archive and production environment of the domain, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="c0fd9-113">Gpo を削除するための特別なアクセス許可を持っていない場合は、展開された GPO の削除の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-113">Unless you have special permission to delete GPOs, you must submit a request for deletion of the deployed GPO.</span></span> <span data-ttu-id="c0fd9-114">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-114">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="c0fd9-115">GPO の監査トレールに表示されるコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-115">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="c0fd9-116">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="c0fd9-117">GPO は、[**保留中**] タブの gpo の一覧に表示されます。承認者が要求を承認した場合、GPO は [**保留中**] タブから [**ごみ箱**] タブに移動され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-117">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

### <span data-ttu-id="c0fd9-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c0fd9-118">Additional considerations</span></span>

-   <span data-ttu-id="c0fd9-119">既定では、この手順を実行するには、エディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-119">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="c0fd9-120">具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-120">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="c0fd9-121">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-121">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="c0fd9-122">GPO は [**コントロール**] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-122">The GPO will be returned to the **Controlled** tab.</span></span>

-   <span data-ttu-id="c0fd9-123">制御されていない GPO を運用環境から削除するには、まず**グループポリシー管理コンソール**で、[**フォレスト**] をクリックし、[**ドメイン**] をクリックして、[ \*\* &lt; MyDomain &gt; **] をクリックし、[**グループポリシーオブジェクト\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-123">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="c0fd9-124">非制御 GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c0fd9-124">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="c0fd9-125">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="c0fd9-125">Additional references</span></span>

-   [<span data-ttu-id="c0fd9-126">GPO の削除または復元</span><span class="sxs-lookup"><span data-stu-id="c0fd9-126">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

 

 





