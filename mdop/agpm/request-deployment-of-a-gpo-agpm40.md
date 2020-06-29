---
title: GPO の展開を要求する
description: GPO の展開を要求する
author: dansimp
ms.assetid: 5783cfd0-bd93-46b4-8fa0-684bd39aa8fc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 46e9cc0fc12962dbdd7758c429a20fdd7c55b3cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820384"
---
# <span data-ttu-id="d9c72-103">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="d9c72-103">Request Deployment of a GPO</span></span>


<span data-ttu-id="d9c72-104">グループポリシーオブジェクト (GPO) を変更してチェックインした後、GPO を展開して、実稼働環境で有効にします。</span><span class="sxs-lookup"><span data-stu-id="d9c72-104">After you have modified and checked in a Group Policy Object (GPO), deploy the GPO, so it will take effect in the production environment.</span></span>

<span data-ttu-id="d9c72-105">この手順を完了するには、編集者の役割を持つユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要な権限を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9c72-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="d9c72-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9c72-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d9c72-107">ドメインの運用環境に GPO の展開を要求するには</span><span class="sxs-lookup"><span data-stu-id="d9c72-107">To request the deployment of a GPO to the production environment of the domain</span></span>**

1.  <span data-ttu-id="d9c72-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9c72-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d9c72-109">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d9c72-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="d9c72-110">展開する GPO を右クリックし、[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9c72-110">Right-click the GPO to be deployed, and then click **Deploy**.</span></span>

4.  <span data-ttu-id="d9c72-111">承認者または AGPM 管理者であるか、Gpo を展開するための特別なアクセス許可を持っていない場合は、展開の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9c72-111">Unless you are an Approver or AGPM Administrator or have special permission to deploy GPOs, you must submit a request for deployment.</span></span> <span data-ttu-id="d9c72-112">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="d9c72-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="d9c72-113">GPO の**履歴**に表示するコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9c72-113">Type a comment to be displayed in the **History** for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="d9c72-114">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9c72-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="d9c72-115">GPO は、[**保留中**] タブの gpo の一覧に表示されます。承認者が要求を承認した場合、GPO は [**保留中**] タブから [**コントロール**] タブに移動され、展開されます。</span><span class="sxs-lookup"><span data-stu-id="d9c72-115">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Controlled** tab and be deployed.</span></span>

### <span data-ttu-id="d9c72-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d9c72-116">Additional considerations</span></span>

-   <span data-ttu-id="d9c72-117">既定では、この手順を実行するには、エディターが必要です。</span><span class="sxs-lookup"><span data-stu-id="d9c72-117">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="d9c72-118">具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9c72-118">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="d9c72-119">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="d9c72-119">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="d9c72-120">GPO は [**コントロール**] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="d9c72-120">The GPO will be returned to the **Controlled** tab.</span></span>

### <span data-ttu-id="d9c72-121">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="d9c72-121">Additional references</span></span>

-   [<span data-ttu-id="d9c72-122">編集者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d9c72-122">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

 

 





