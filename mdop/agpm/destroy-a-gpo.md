---
title: GPO を破棄する
description: GPO を破棄する
author: dansimp
ms.assetid: d74941a3-beef-46cd-a4ca-80a324dcfadf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5545918c417fce16bfc2369ebc6fc2199390adc6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818647"
---
# <span data-ttu-id="3cf9e-103">GPO を破棄する</span><span class="sxs-lookup"><span data-stu-id="3cf9e-103">Destroy a GPO</span></span>


<span data-ttu-id="3cf9e-104">高度なグループポリシー管理 (AGPM) では、承認者がグループポリシーオブジェクト (GPO) を破棄し、ごみ箱から削除し、復元できないように完全に削除することができます。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-104">Advanced Group Policy Management (AGPM) enables Approvers to destroy a Group Policy object (GPO), removing it from the Recycle Bin and permanently deleting it so that it can no longer be restored.</span></span>

<span data-ttu-id="3cf9e-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="3cf9e-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="3cf9e-107">GPO を復元できなくなるように完全に削除するには</span><span class="sxs-lookup"><span data-stu-id="3cf9e-107">To permanently delete a GPO so it can no longer be restored</span></span>**

1.  <span data-ttu-id="3cf9e-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="3cf9e-109">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="3cf9e-110">破棄する GPO を右クリックし、[**破棄**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-110">Right-click the GPO to destroy, and then click **Destroy**.</span></span>

4.  <span data-ttu-id="3cf9e-111">[**はい**] をクリックして、選んだ GPO とアーカイブからすべてのバックアップを完全に削除することを確認します。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-111">Click **Yes** to confirm that you want to permanently delete the selected GPO and all backups from the archive.</span></span>

5.  <span data-ttu-id="3cf9e-112">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="3cf9e-113">GPO は [**ごみ箱**] タブから削除され、完全に削除されます。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-113">The GPO is removed from the **Recycle Bin** tab and is permanently deleted.</span></span>

### <span data-ttu-id="3cf9e-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="3cf9e-114">Additional considerations</span></span>

-   <span data-ttu-id="3cf9e-115">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="3cf9e-116">具体的には、GPO の [**コンテンツの一覧表示**] および [ **gpo の削除**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3cf9e-116">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="3cf9e-117">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="3cf9e-117">Additional references</span></span>

-   [<span data-ttu-id="3cf9e-118">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="3cf9e-118">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

 

 





