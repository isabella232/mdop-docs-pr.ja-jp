---
title: 新しい制御された GPO の作成を要求する
description: 新しい制御された GPO の作成を要求する
author: dansimp
ms.assetid: cb265238-386f-4780-a59a-0c9a4a87d736
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 85a435f84e055013c5100a720377f4bffaef4319
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820317"
---
# <span data-ttu-id="e8fb6-103">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="e8fb6-103">Request the Creation of a New Controlled GPO</span></span>


<span data-ttu-id="e8fb6-104">承認者または AGPM 管理者 (フルコントロール) でない場合は、新しいグループポリシーオブジェクト (GPO) の作成を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the creation of a new Group Policy Object (GPO).</span></span>

<span data-ttu-id="e8fb6-105">この手順を完了するには、編集者の役割、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-105">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="e8fb6-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="e8fb6-107">AGPM によって管理される変更コントロールで新しい GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="e8fb6-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="e8fb6-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="e8fb6-109">[コントロールの**変更**] を右クリックし、[**新しい制御**された GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-109">Right-click **Change Control**, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="e8fb6-110">Gpo を作成するための特別なアクセス許可がない場合は、作成の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-110">Unless you have special permission to create GPOs, you must submit a request for creation.</span></span> <span data-ttu-id="e8fb6-111">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-111">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="e8fb6-112">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-112">To receive a copy of the request, enter your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="e8fb6-113">新しい GPO の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-113">Type a name for the new GPO.</span></span>

    3.  <span data-ttu-id="e8fb6-114">オプション: 新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-114">Optional: Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="e8fb6-115">承認を受けた後で、新しい GPO をドメインの運用環境に展開するには、[**ライブの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-115">To deploy the new GPO to the production environment of the domain immediately upon approval, click **Create live**.</span></span> <span data-ttu-id="e8fb6-116">承認されたときにすぐに新しい GPO をオフラインで作成するには、[**オフラインで作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-116">To create the new GPO offline without immediately deploying it upon approval, click **Create offline**.</span></span>

    5.  <span data-ttu-id="e8fb6-117">新しい GPO の開始点として使用する GPO テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-117">Select the GPO template to use as a starting point for the new GPO.</span></span>

    6.  <span data-ttu-id="e8fb6-118">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-118">Click **Submit**.</span></span>

4.  <span data-ttu-id="e8fb6-119">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="e8fb6-120">新しい GPO が、[**保留中**] タブの gpo の一覧に表示されます。承認者がリクエストを承認すると、その GPO は [**コントロール**] タブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-120">The new GPO is displayed in the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="e8fb6-121">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="e8fb6-121">Additional considerations</span></span>

-   <span data-ttu-id="e8fb6-122">既定では、この手順を実行するには、編集者またはレビュー担当者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-122">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="e8fb6-123">具体的には、ドメインの**リストコンテンツ**のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-123">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="e8fb6-124">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-124">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, then click **Withdraw**.</span></span> <span data-ttu-id="e8fb6-125">GPO は破棄されます。</span><span class="sxs-lookup"><span data-stu-id="e8fb6-125">The GPO will be destroyed.</span></span>

### <span data-ttu-id="e8fb6-126">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="e8fb6-126">Additional references</span></span>

-   [<span data-ttu-id="e8fb6-127">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="e8fb6-127">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-ed.md)

 

 





