---
title: GPO を展開する
description: GPO を展開する
author: dansimp
ms.assetid: a0a3f292-e3ab-46ae-a0fd-d7b2b4ad8883
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a98bdd758937d86cf8c30c5abf0b49302d377360
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818697"
---
# <span data-ttu-id="a3c62-103">GPO を展開する</span><span class="sxs-lookup"><span data-stu-id="a3c62-103">Deploy a GPO</span></span>


<span data-ttu-id="a3c62-104">高度なグループポリシー管理 (AGPM) により、承認者は新しいグループポリシーオブジェクト (GPO) を運用環境に展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a3c62-104">Advanced Group Policy Management (AGPM) enables an Approver to deploy a new or edited Group Policy object (GPO) to the production environment.</span></span> <span data-ttu-id="a3c62-105">以前のバージョンの GPO を再展開する方法については、「[以前のバージョンの gpo にロールバックする](roll-back-to-a-previous-version-of-a-gpo.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3c62-105">For information about redeploying a previous version of a GPO, see [Roll Back to a Previous Version of a GPO](roll-back-to-a-previous-version-of-a-gpo.md).</span></span>

<span data-ttu-id="a3c62-106">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3c62-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="a3c62-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3c62-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="a3c62-108">GPO を運用環境に展開するには</span><span class="sxs-lookup"><span data-stu-id="a3c62-108">To deploy a GPO to the production environment</span></span>**

1.  <span data-ttu-id="a3c62-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="a3c62-110">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3c62-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="a3c62-111">展開する GPO を右クリックし、[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-111">Right-click the GPO to be deployed and then click **Deploy**.</span></span>

4.  <span data-ttu-id="a3c62-112">GPO へのリンクを確認するには、[**詳細設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-112">To review links to the GPO, click **Advanced**.</span></span> <span data-ttu-id="a3c62-113">ツリー内のノードにマウスポインターを置くと、詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3c62-113">Pause the mouse pointer on a node in the tree to display details.</span></span>

    -   <span data-ttu-id="a3c62-114">既定では、GPO へのすべてのリンクが復元されます。</span><span class="sxs-lookup"><span data-stu-id="a3c62-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="a3c62-115">リンクが復元されないようにするには、そのリンクのチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="a3c62-116">すべてのリンクが復元されないようにするには、[ **GPO の展開**] ダイアログボックスの [**リンクの復元**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="a3c62-117">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-117">Click **Yes**.</span></span> <span data-ttu-id="a3c62-118">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3c62-118">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

<span data-ttu-id="a3c62-119">**注** 最新バージョンの GPO が展開されているかどうかを確認するには、[**コントロール**] タブで gpo をダブルクリックして、その**履歴**を表示します。</span><span class="sxs-lookup"><span data-stu-id="a3c62-119">**Note** To verify whether the most recent version of a GPO has been deployed, on the **Controlled** tab, double-click the GPO to display its **History**.</span></span> <span data-ttu-id="a3c62-120">GPO の**履歴**では、[**状態**] 列に gpo が展開されているかどうかが示されます。</span><span class="sxs-lookup"><span data-stu-id="a3c62-120">In the **History** for the GPO, the **State** column indicates whether a GPO has been deployed.</span></span>

 

### <span data-ttu-id="a3c62-121">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="a3c62-121">Additional considerations</span></span>

-   <span data-ttu-id="a3c62-122">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c62-122">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="a3c62-123">具体的には、GPO の [**コンテンツの一覧表示**] と [ **gpo の展開**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3c62-123">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="a3c62-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="a3c62-124">Additional references</span></span>

-   [<span data-ttu-id="a3c62-125">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="a3c62-125">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

 

 





