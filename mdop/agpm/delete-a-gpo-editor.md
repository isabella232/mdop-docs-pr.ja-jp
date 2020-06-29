---
title: GPO を削除する
description: GPO を削除する
author: dansimp
ms.assetid: 66be3dde-653e-4c25-8cb7-00e7090c8d31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c27ddf87a12ed6010c481d93bfc85bb531f3d4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820974"
---
# <span data-ttu-id="e0679-103">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="e0679-103">Delete a GPO</span></span>


<span data-ttu-id="e0679-104">編集者は、グループポリシーオブジェクト (GPO) の削除を完了するアクセス許可が与えられていない可能性がありますが、プロセスを開始して要求を承認者に送信するために必要なアクセス許可を持っている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e0679-104">As an Editor, you may not have permission to complete the deletion of a Group Policy object (GPO), but you do have the permission necessary to begin the process and submit your request to an Approver.</span></span>

<span data-ttu-id="e0679-105">この手順を完了するには、編集者の役割を持つユーザーアカウント、または高度なグループポリシーの管理に必要なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0679-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="e0679-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e0679-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="e0679-107">コントロールされた GPO の削除を要求するには</span><span class="sxs-lookup"><span data-stu-id="e0679-107">To request the deletion of a controlled GPO</span></span>**

1.  <span data-ttu-id="e0679-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="e0679-109">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="e0679-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="e0679-110">削除する GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-110">Right-click the GPO to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="e0679-111">展開されたバージョンの GPO を運用環境でそのまま残して、アーカイブから GPO を削除するには、[ **gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only (uncontrol)**.</span></span>

    -   <span data-ttu-id="e0679-112">アーカイブと運用環境の両方から GPO を削除するには、[**アーカイブと運用] から [gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

        <span data-ttu-id="e0679-113">Gpo を削除するための特別なアクセス許可を持っていない場合は、展開された GPO の削除の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0679-113">Unless you have special permission to delete GPOs, you must submit a request for deletion of the deployed GPO.</span></span> <span data-ttu-id="e0679-114">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e0679-114">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="e0679-115">GPO の監査トレールに表示されるコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-115">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

4.  <span data-ttu-id="e0679-116">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="e0679-117">GPO は、[**保留中**] タブの gpo の一覧に表示されます。承認者が要求を承認した場合、GPO は [**保留中**] タブから [**ごみ箱**] タブに移動され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="e0679-117">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

### <span data-ttu-id="e0679-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e0679-118">Additional considerations</span></span>

-   <span data-ttu-id="e0679-119">既定では、展開された GPO の削除を要求するエディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="e0679-119">By default, you must be an Editor to request the deletion of a deployed GPO.</span></span> <span data-ttu-id="e0679-120">具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="e0679-120">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="e0679-121">既定では、アーカイブから GPO を削除するには、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0679-121">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to delete a GPO from the archive.</span></span> <span data-ttu-id="e0679-122">具体的には、GPO の [**コンテンツの一覧]** と [**設定の編集**] または [ **gpo の削除**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e0679-122">Specifically, you must have **List Contents** and either **Edit Settings** or **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="e0679-123">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="e0679-123">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="e0679-124">GPO は [**コントロール**] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="e0679-124">The GPO will be returned to the **Controlled** tab.</span></span>

-   <span data-ttu-id="e0679-125">制御されていない GPO を運用環境から削除するには、まず**グループポリシー管理コンソール**で、[**フォレスト**] をクリックし、[**ドメイン**] をクリックして、[ \*\* &lt; MyDomain &gt; **] をクリックし、[**グループポリシーオブジェクト\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-125">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="e0679-126">非制御 GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e0679-126">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="e0679-127">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="e0679-127">Additional references</span></span>

-   [<span data-ttu-id="e0679-128">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="e0679-128">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

 

 





