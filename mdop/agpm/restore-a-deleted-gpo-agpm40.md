---
title: 削除された GPO を復元する
description: 削除された GPO を復元する
author: dansimp
ms.assetid: 0a131d26-a741-4a51-b612-c0bc7dbba06b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14fdf2f74f2d3db4be0db1aab7c185f5c1ab2cd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818424"
---
# <span data-ttu-id="0c6bc-103">削除された GPO を復元する</span><span class="sxs-lookup"><span data-stu-id="0c6bc-103">Restore a Deleted GPO</span></span>


<span data-ttu-id="0c6bc-104">承認者は、削除されたグループポリシーオブジェクト (GPO) をごみ箱から復元し、アーカイブに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-104">Approvers can restore a deleted Group Policy Object (GPO) from the Recycle Bin, returning it to the archive.</span></span>

<span data-ttu-id="0c6bc-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="0c6bc-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="0c6bc-107">削除された GPO を復元するには</span><span class="sxs-lookup"><span data-stu-id="0c6bc-107">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="0c6bc-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="0c6bc-109">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="0c6bc-110">復元する GPO を右クリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-110">Right-click the GPO to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="0c6bc-111">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="0c6bc-112">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="0c6bc-113">GPO は [**ごみ箱**] タブから削除され、[**コントロール**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-113">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="0c6bc-114">**注** GPO が運用環境から削除された場合、アーカイブに復元しても、自動的に運用環境に再配置されることはありません。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-114">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="0c6bc-115">GPO を運用環境に戻すには、GPO を展開します。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-115">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="0c6bc-116">詳細については、「 [GPO の展開](deploy-a-gpo-agpm40.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-116">For information, see [Deploy a GPO](deploy-a-gpo-agpm40.md).</span></span>

 

### <span data-ttu-id="0c6bc-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="0c6bc-117">Additional considerations</span></span>

-   <span data-ttu-id="0c6bc-118">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="0c6bc-119">具体的には、**リストコンテンツ**が必要です。また、gpo の [Gpo の**展開**] または [Gpo の権限の**削除**] のいずれかを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c6bc-119">Specifically, you must have **List Contents** and either **Deploy GPO** or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="0c6bc-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="0c6bc-120">Additional references</span></span>

-   [<span data-ttu-id="0c6bc-121">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="0c6bc-121">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm40.md)

 

 





