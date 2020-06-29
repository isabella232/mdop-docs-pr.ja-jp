---
title: GPO をチェックインする
description: GPO をチェックインする
author: dansimp
ms.assetid: e428cfff-651f-4903-bf01-d742714d2fa9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6adbcfa1c2b0d79389bc16dd1dde5afc0a4ec4a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819147"
---
# <span data-ttu-id="d9d5c-103">GPO をチェックインする</span><span class="sxs-lookup"><span data-stu-id="d9d5c-103">Check In a GPO</span></span>


<span data-ttu-id="d9d5c-104">通常、編集が完了したときに編集したグループポリシーオブジェクト (Gpo) は、編集者がチェックインする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-104">Ordinarily, Editors should check in Group Policy objects (GPOs) that they have edited when their modifications are complete.</span></span> <span data-ttu-id="d9d5c-105">詳細については、「 [GPO をオフラインで編集する](edit-a-gpo-offline.md)」を参照してください。ただし、エディターを使用できない場合は、承認者が GPO をチェックインすることもできます。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-105">(For details, see [Edit a GPO Offline](edit-a-gpo-offline.md).) However, if the Editor is unavailable, an Approver can also check in a GPO.</span></span>

<span data-ttu-id="d9d5c-106">この手順を完了するには、エディター、承認者、または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理の必要なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-106">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="d9d5c-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d9d5c-108">編集者によってチェックアウトされた GPO をチェックインするには</span><span class="sxs-lookup"><span data-stu-id="d9d5c-108">To check in a GPO that has been checked out by an Editor</span></span>**

1.  <span data-ttu-id="d9d5c-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d9d5c-110">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理されている gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-110">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

    -   <span data-ttu-id="d9d5c-111">エディターによって行われた変更を破棄するには、GPO を右クリックし、[**元に戻す**] をクリックし、[**はい**] をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-111">To discard any changes made by the Editor, right-click the GPO, click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="d9d5c-112">エディターで加えた変更を保持するには、GPO を右クリックし、[**チェックイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-112">To retain changes made by the Editor, right-click the GPO and then click **Check In**.</span></span>

3.  <span data-ttu-id="d9d5c-113">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-113">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="d9d5c-114">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="d9d5c-115">[**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-115">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="d9d5c-116">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d9d5c-116">Additional considerations</span></span>

-   <span data-ttu-id="d9d5c-117">既定では、この手順を実行するには、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-117">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d9d5c-118">具体的には、その GPO の [**コンテンツの一覧]** と [**設定の編集**] または [gpo のアクセス許可の**展開**] を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-118">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="d9d5c-119">承認者または AGPM 管理者 (または**gpo の展開**に関するその他のグループポリシー管理者) ではない場合は、gpo をチェックアウトしたエディターである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d9d5c-119">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

### <span data-ttu-id="d9d5c-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="d9d5c-120">Additional references</span></span>

-   [<span data-ttu-id="d9d5c-121">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d9d5c-121">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="d9d5c-122">オフラインで GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="d9d5c-122">Edit a GPO Offline</span></span>](edit-a-gpo-offline.md)

 

 





