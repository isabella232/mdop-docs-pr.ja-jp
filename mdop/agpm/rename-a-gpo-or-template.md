---
title: GPO またはテンプレートの名前を変更する
description: GPO またはテンプレートの名前を変更する
author: dansimp
ms.assetid: 64a1aaf4-f672-48b5-94c6-473bf1076cf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 495fc090487ff324bc19c89dcd36ecf0efbcb151
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818494"
---
# <span data-ttu-id="aaad9-103">GPO またはテンプレートの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="aaad9-103">Rename a GPO or Template</span></span>


<span data-ttu-id="aaad9-104">コントロールされたグループポリシーオブジェクト (GPO) またはテンプレートの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="aaad9-104">You can rename a controlled Group Policy object (GPO) or a template.</span></span>

<span data-ttu-id="aaad9-105">この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理で必要なアクセス許可を持つユーザーアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaad9-105">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="aaad9-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="aaad9-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="aaad9-107">GPO またはテンプレートの名前を変更するには</span><span class="sxs-lookup"><span data-stu-id="aaad9-107">To rename a GPO or template</span></span>**

1.  <span data-ttu-id="aaad9-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaad9-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="aaad9-109">[**コンテンツ**] タブで、[**コントロール**] または [**テンプレート**] タブをクリックして、名前を変更するアイテムを表示します。</span><span class="sxs-lookup"><span data-stu-id="aaad9-109">On the **Contents** tab, click the **Controlled** or **Templates** tab to display the item to rename.</span></span>

3.  <span data-ttu-id="aaad9-110">名前を変更する GPO またはテンプレートを右クリックし、[**名前の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaad9-110">Right-click the GPO or template to rename and click **Rename**.</span></span>

4.  <span data-ttu-id="aaad9-111">GPO またはテンプレートの新しい名前とコメントを入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaad9-111">Type the new name for the GPO or template and a comment, then click **OK**.</span></span>

5.  <span data-ttu-id="aaad9-112">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="aaad9-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="aaad9-113">GPO またはテンプレートが [**コンテンツ**] タブの新しい名前の下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="aaad9-113">The GPO or template appears under the new name on the **Contents** tab.</span></span>

### <span data-ttu-id="aaad9-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="aaad9-114">Additional considerations</span></span>

-   <span data-ttu-id="aaad9-115">既定では、この手順を実行するには、GPO、エディター、または AGPM 管理者 (フルコントロール) を作成または管理している承認者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="aaad9-115">By default, you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="aaad9-116">具体的には、GPO の [**コンテンツの一覧]** と [**設定の編集**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="aaad9-116">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="aaad9-117">展開されている GPO の名前を変更すると、アーカイブ内でその名前がすぐに変更されます。</span><span class="sxs-lookup"><span data-stu-id="aaad9-117">When you rename a GPO that has been deployed, the name is immediately changed in the archive.</span></span> <span data-ttu-id="aaad9-118">この名前は、GPO が再展開された場合にのみ、実稼働環境で変更されます。</span><span class="sxs-lookup"><span data-stu-id="aaad9-118">The name is changed in the production environment only when the GPO is redeployed.</span></span>

    <span data-ttu-id="aaad9-119">GPO が再展開されるか (または、プロダクションコピーが削除されるまで)、古い名前はまだ実稼働環境で使用されているため、別の GPO に使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="aaad9-119">Until the GPO is redeployed (or the production copy is deleted), the old name is still in use in the production environment and therefore cannot be used for another GPO.</span></span> <span data-ttu-id="aaad9-120">同様に、アーカイブ内の GPO は、GPO が配置される (運用コピーの名前を変更する) か、プロダクションコピーが削除されるまで、元の名前に戻すことはできません。</span><span class="sxs-lookup"><span data-stu-id="aaad9-120">Likewise, the GPO in the archive cannot be renamed back to its original name until the GPO has been deployed (changing the name of the production copy) or the production copy has been deleted.</span></span>

### <span data-ttu-id="aaad9-121">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="aaad9-121">Additional references</span></span>

-   [<span data-ttu-id="aaad9-122">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="aaad9-122">Editing a GPO</span></span>](editing-a-gpo.md)

 

 





