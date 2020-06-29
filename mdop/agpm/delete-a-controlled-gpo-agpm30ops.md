---
title: 制御された GPO を削除する
description: 制御された GPO を削除する
author: dansimp
ms.assetid: f51c1737-c116-4faf-a6f6-c72303f60a3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 365554d90ac13d749508edbc84dacd432ac4ceec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818714"
---
# <span data-ttu-id="d722a-103">制御された GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="d722a-103">Delete a Controlled GPO</span></span>


<span data-ttu-id="d722a-104">承認者は、管理されたグループポリシーオブジェクト (GPO) を削除して、ごみ箱に移動することができます。</span><span class="sxs-lookup"><span data-stu-id="d722a-104">Approvers can delete a controlled Group Policy Object (GPO), moving it to the Recycle Bin.</span></span>

<span data-ttu-id="d722a-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="d722a-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="d722a-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d722a-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d722a-107">コントロールされた GPO を削除するには</span><span class="sxs-lookup"><span data-stu-id="d722a-107">To delete a controlled GPO</span></span>**

1.  <span data-ttu-id="d722a-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d722a-109">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d722a-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="d722a-110">削除する GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="d722a-111">展開されているバージョンの GPO を運用環境でそのまま残して、アーカイブから GPO を削除するには、[ **gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="d722a-112">アーカイブと運用環境の両方から GPO を削除するには、[**アーカイブと運用] から [gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="d722a-113">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-113">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="d722a-114">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="d722a-115">GPO は [**コントロール**] タブから削除され、[**ごみ箱**] タブに表示され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="d722a-115">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span> <span data-ttu-id="d722a-116">GPO がアーカイブからのみ削除された場合は、[**非コントロール**] タブにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="d722a-116">If the GPO was deleted only from the archive, it is also displayed on the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="d722a-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d722a-117">Additional considerations</span></span>

-   <span data-ttu-id="d722a-118">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d722a-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d722a-119">具体的には、GPO の [**コンテンツの一覧表示**] および [ **gpo の削除**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d722a-119">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="d722a-120">制御されていない GPO を運用環境から削除するには、まず**グループポリシー管理コンソール**で、[**フォレスト**] をクリックし、[**ドメイン**] をクリックして、[ \*\* &lt; MyDomain &gt; **] をクリックし、[**グループポリシーオブジェクト\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-120">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="d722a-121">非制御 GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d722a-121">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="d722a-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="d722a-122">Additional references</span></span>

-   [<span data-ttu-id="d722a-123">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="d722a-123">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





