---
title: オフラインで GPO を編集する
description: オフラインで GPO を編集する
author: dansimp
ms.assetid: 51677d8a-6209-41b5-82ed-4f3be817abc0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 74b6ae9fdf11456a9a45cb5504ed97a9bc6aecb4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818624"
---
# <span data-ttu-id="bad13-103">オフラインで GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="bad13-103">Edit a GPO Offline</span></span>


<span data-ttu-id="bad13-104">グループポリシーオブジェクト (GPO) に変更を加えるには、まず、その GPO のコピーをアーカイブからチェックアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-104">To make changes to a controlled Group Policy Object (GPO), you must first check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="bad13-105">他のユーザーは、もう一度チェックインするまで GPO を変更することはできません。これにより、複数のグループポリシー管理者による競合している変更の導入を防ぐことができます。</span><span class="sxs-lookup"><span data-stu-id="bad13-105">No one else will be able to modify the GPO until it is checked in again, preventing the introduction of conflicting changes by multiple Group Policy administrators.</span></span> <span data-ttu-id="bad13-106">GPO の変更が完了したら、それをアーカイブにチェックインして、運用環境に確認して展開できるようにします。</span><span class="sxs-lookup"><span data-stu-id="bad13-106">When you have finished modifying the GPO, you check it into the archive so that it can be reviewed and deployed to the production environment.</span></span>

<span data-ttu-id="bad13-107">この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-107">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="bad13-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad13-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="bad13-109">GPO をオフラインで編集する</span><span class="sxs-lookup"><span data-stu-id="bad13-109">Editing a GPO offline</span></span>


<span data-ttu-id="bad13-110">GPO を編集するには、アーカイブから GPO をチェックアウトして、オフラインでその gpo を編集してから、その GPO が確認され、展開される (または他のエディターによって変更される) ことができるように、その GPO をアーカイブにチェックインします。</span><span class="sxs-lookup"><span data-stu-id="bad13-110">To edit a GPO, you check out the GPO from the archive, edit the GPO offline, and then check the GPO into the archive so that it can be reviewed and deployed (or modified by other Editors).</span></span>

-   [<span data-ttu-id="bad13-111">編集するためにアーカイブから GPO をチェックアウトする</span><span class="sxs-lookup"><span data-stu-id="bad13-111">Check out a GPO from the archive for editing</span></span>](#bkmk-checkout)

-   [<span data-ttu-id="bad13-112">GPO をオフラインで編集する</span><span class="sxs-lookup"><span data-stu-id="bad13-112">Edit a GPO offline</span></span>](#bkmk-edit)

-   [<span data-ttu-id="bad13-113">GPO をアーカイブにチェックインする</span><span class="sxs-lookup"><span data-stu-id="bad13-113">Check a GPO into the archive</span></span>](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**<span data-ttu-id="bad13-114">アーカイブから GPO をチェックアウトして編集するには</span><span class="sxs-lookup"><span data-stu-id="bad13-114">To check out a GPO from the archive for editing</span></span>**

1.  <span data-ttu-id="bad13-115">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-115">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="bad13-116">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="bad13-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="bad13-117">編集する GPO を右クリックし、[チェックアウト] をクリック**します。**</span><span class="sxs-lookup"><span data-stu-id="bad13-117">Right-click the GPO to be edited, and then click **Check Out**.</span></span>

4.  <span data-ttu-id="bad13-118">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-118">Type a comment to be displayed in the History of the GPO while it is checked out, and then click **OK**.</span></span>

5.  <span data-ttu-id="bad13-119">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="bad13-120">[**コントロール**] タブで、GPO の状態が**チェックアウト済み**として識別されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bad13-120">On the **Controlled** tab, the state of the GPO is now identified as **Checked Out**.</span></span>

### <a href="" id="bkmk-edit"></a>

**<span data-ttu-id="bad13-121">GPO をオフラインで編集するには</span><span class="sxs-lookup"><span data-stu-id="bad13-121">To edit a GPO offline</span></span>**

1.  <span data-ttu-id="bad13-122">[**コントロール**] タブで、編集する GPO を右クリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-122">On the **Controlled** tab, right-click the GPO to be edited, and then click **Edit**.</span></span>

2.  <span data-ttu-id="bad13-123">[**グループポリシー管理エディター** ] ウィンドウで、GPO のオフラインコピーに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="bad13-123">In the **Group Policy Management Editor** window, make changes to an offline copy of the GPO.</span></span>

    <span data-ttu-id="bad13-124">**注** すべてのコンピューターの構成設定またはすべてのユーザー構成設定を無効にするには、[**グループポリシー管理エディター** ] ウィンドウで GPO を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-124">**Note** To disable all Computer Configuration settings or all User Configuration settings, right-click the GPO in the **Group Policy Management Editor** window and click **Properties**.</span></span> <span data-ttu-id="bad13-125">[**コンピューターの設定を無効にする**] を選択するか、必要に応じて**ユーザー構成の設定を無効に**します。</span><span class="sxs-lookup"><span data-stu-id="bad13-125">Select **Disable Computer Configuration settings** or **Disable User Configuration settings** as appropriate.</span></span>

     

3.  <span data-ttu-id="bad13-126">GPO の変更が完了したら、[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="bad13-126">When you have finished modifying the GPO, close the **Group Policy Management Editor** window.</span></span>

### <a href="" id="bkmk-checkin"></a>

**<span data-ttu-id="bad13-127">GPO をアーカイブにチェックインするには</span><span class="sxs-lookup"><span data-stu-id="bad13-127">To check a GPO into the archive</span></span>**

1.  <span data-ttu-id="bad13-128">[**コントロール**] タブで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="bad13-128">On the **Controlled** tab:</span></span>

    -   <span data-ttu-id="bad13-129">GPO を変更していない場合は、GPO を右クリックし、[**元に戻す**] をクリックし、[**はい**] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="bad13-129">If you have made no changes to the GPO, right-click the GPO and click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="bad13-130">GPO に変更を加えた場合は、その GPO を右クリックして [**チェックイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-130">If you have made changes to the GPO, right-click the GPO and click **Check In**.</span></span>

2.  <span data-ttu-id="bad13-131">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-131">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

3.  <span data-ttu-id="bad13-132">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bad13-132">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="bad13-133">[**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="bad13-133">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="bad13-134">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bad13-134">Additional considerations</span></span>

-   <span data-ttu-id="bad13-135">GPO をチェックアウトして編集するには、既定で、GPO、エディター、または AGPM 管理者 (フルコントロール) を作成または管理する承認者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-135">To check out and edit a GPO, by default you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="bad13-136">具体的には、GPO の [**リストコンテンツ]** と [**編集設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="bad13-136">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span> <span data-ttu-id="bad13-137">さらに、GPO を編集するには、GPO をチェックアウトした個人である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-137">Additionally, to edit the GPO you must be the individual who has checked out the GPO.</span></span>

-   <span data-ttu-id="bad13-138">GPO をチェックインするには、既定で、編集者、承認者、または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-138">To check in a GPO, by default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="bad13-139">具体的には、その GPO の [**コンテンツの一覧]** と [**設定の編集**] または [gpo のアクセス許可の**展開**] を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-139">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="bad13-140">承認者または AGPM 管理者 (または**gpo の展開**に関するその他のグループポリシー管理者) ではない場合は、gpo をチェックアウトしたエディターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-140">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

-   <span data-ttu-id="bad13-141">GPO を編集している場合、別の GPO にあるパッケージのグループポリシーソフトウェアのインストールアップグレードは、チェックアウトしたコピーではなく、展開された GPO を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad13-141">When editing a GPO, any Group Policy Software Installation upgrade of a package in another GPO should reference the deployed GPO, and not the checked-out copy.</span></span>

### <span data-ttu-id="bad13-142">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="bad13-142">Additional references</span></span>

-   [<span data-ttu-id="bad13-143">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="bad13-143">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

-   <span data-ttu-id="bad13-144">GPO を確認する</span><span class="sxs-lookup"><span data-stu-id="bad13-144">Reviewing a GPO</span></span>

    -   [<span data-ttu-id="bad13-145">GPO の設定を確認する</span><span class="sxs-lookup"><span data-stu-id="bad13-145">Review GPO Settings</span></span>](review-gpo-settings-agpm30ops.md)

    -   [<span data-ttu-id="bad13-146">GPO のリンクを確認する</span><span class="sxs-lookup"><span data-stu-id="bad13-146">Review GPO Links</span></span>](review-gpo-links-agpm30ops.md)

    -   [<span data-ttu-id="bad13-147">GPO、GPO のバージョン、またはテンプレート間の相違点を識別する</span><span class="sxs-lookup"><span data-stu-id="bad13-147">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>](identify-differences-between-gpos-gpo-versions-or-templates-agpm30ops.md)

-   <span data-ttu-id="bad13-148">GPO の展開</span><span class="sxs-lookup"><span data-stu-id="bad13-148">Deploying a GPO</span></span>

    -   [<span data-ttu-id="bad13-149">GPO の展開を要求する</span><span class="sxs-lookup"><span data-stu-id="bad13-149">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm30ops.md)

    -   [<span data-ttu-id="bad13-150">GPO を展開する</span><span class="sxs-lookup"><span data-stu-id="bad13-150">Deploy a GPO</span></span>](deploy-a-gpo-agpm30ops.md)

 

 





