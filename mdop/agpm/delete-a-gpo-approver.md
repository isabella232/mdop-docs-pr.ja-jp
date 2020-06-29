---
title: GPO を削除する
description: GPO を削除する
author: dansimp
ms.assetid: 85fca371-5707-49c1-aa51-813fc3a58dfc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a6419943604ee5a76d305228bb7418a8525bf33
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820984"
---
# <span data-ttu-id="8d6b6-103">GPO を削除する</span><span class="sxs-lookup"><span data-stu-id="8d6b6-103">Delete a GPO</span></span>


<span data-ttu-id="8d6b6-104">高度なグループポリシー管理 (AGPM) では、管理者がグループポリシーオブジェクト (GPO) を削除し、ごみ箱に移動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-104">Advanced Group Policy Management (AGPM) enables Approvers to delete a controlled Group Policy object (GPO), moving it to the Recycle Bin.</span></span>

<span data-ttu-id="8d6b6-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="8d6b6-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="8d6b6-107">コントロールされた GPO を削除するには</span><span class="sxs-lookup"><span data-stu-id="8d6b6-107">To delete a controlled GPO</span></span>**

1.  <span data-ttu-id="8d6b6-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="8d6b6-109">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="8d6b6-110">削除する GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-110">Right-click the GPO to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="8d6b6-111">展開されたバージョンの GPO を運用環境でそのまま残して、アーカイブから GPO を削除するには、[ **gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only (uncontrol)**.</span></span>

    -   <span data-ttu-id="8d6b6-112">アーカイブと運用環境の両方から GPO を削除するには、[**アーカイブと運用] から [gpo の削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="8d6b6-113">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-113">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="8d6b6-114">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="8d6b6-115">GPO は [**コントロール**] タブから削除され、[**ごみ箱**] タブに表示され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-115">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span> <span data-ttu-id="8d6b6-116">GPO がアーカイブからのみ削除された場合は、[**非コントロール**] タブにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-116">If the GPO was deleted only from the archive, it is also displayed on the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="8d6b6-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="8d6b6-117">Additional considerations</span></span>

-   <span data-ttu-id="8d6b6-118">既定では、展開された GPO を削除するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to delete a deployed GPO.</span></span> <span data-ttu-id="8d6b6-119">具体的には、GPO の [**コンテンツの一覧表示**] および [ **gpo の削除**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-119">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="8d6b6-120">既定では、アーカイブから GPO を削除するには、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-120">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to delete a GPO from the archive.</span></span> <span data-ttu-id="8d6b6-121">具体的には、GPO の [**コンテンツの一覧]** と [**設定の編集**] または [ **gpo の削除**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-121">Specifically, you must have **List Contents** and either **Edit Settings** or **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="8d6b6-122">制御されていない GPO を運用環境から削除するには、まず**グループポリシー管理コンソール**で、[**フォレスト**] をクリックし、[**ドメイン**] をクリックして、[ \*\* &lt; MyDomain &gt; **] をクリックし、[**グループポリシーオブジェクト\*\*] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-122">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="8d6b6-123">非制御 GPO を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d6b6-123">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="8d6b6-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="8d6b6-124">Additional references</span></span>

-   [<span data-ttu-id="8d6b6-125">GPO の削除、復元、破棄</span><span class="sxs-lookup"><span data-stu-id="8d6b6-125">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

 

 





