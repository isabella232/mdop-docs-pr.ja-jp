---
title: GPO の現在のバージョンにラベルを付ける
description: GPO の現在のバージョンにラベルを付ける
author: dansimp
ms.assetid: 3845211a-0bc9-4875-9906-cb758c443825
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f9e656258591a56397c5a8053b2e98772f57949a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820667"
---
# <span data-ttu-id="6213b-103">GPO の現在のバージョンにラベルを付ける</span><span class="sxs-lookup"><span data-stu-id="6213b-103">Label the Current Version of a GPO</span></span>


<span data-ttu-id="6213b-104">グループポリシーオブジェクト (GPO) の現在のバージョンにラベルを付けて、履歴を簡単に識別することができます。</span><span class="sxs-lookup"><span data-stu-id="6213b-104">You can label the current version of a Group Policy Object (GPO) for easy identification in its history.</span></span> <span data-ttu-id="6213b-105">問題が発生した場合は、ラベルを使用して、ロールバックできる既知の適切なバージョンを特定できます。</span><span class="sxs-lookup"><span data-stu-id="6213b-105">You can use a label to identify a known good version to which you could roll back if a problem occurs.</span></span> <span data-ttu-id="6213b-106">また、同じラベルの複数の Gpo に一度にラベルを付けることで、ロールバックする必要がある場合は、同じポイントにロールバックする必要がある関連する Gpo にマークを付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6213b-106">Also, by labeling multiple GPOs with the same label at one time, you can mark related GPOs that should be rolled back to the same point if rollback should later be necessary.</span></span>

<span data-ttu-id="6213b-107">この手順を完了するには、エディター、承認者、または AGPM 管理者 (フルコントロール) の役割を持つ、または高度なグループポリシー管理 (AGPM) の必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="6213b-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="6213b-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6213b-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="6213b-109">履歴で現在のバージョンの Gpo にラベルを付けるには</span><span class="sxs-lookup"><span data-stu-id="6213b-109">To label the current version of GPOs in their histories</span></span>**

1.  <span data-ttu-id="6213b-110">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="6213b-111">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="6213b-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="6213b-112">現在のバージョンのラベルを付ける GPO をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-112">Click a GPO for which to label the current version.</span></span> <span data-ttu-id="6213b-113">複数の Gpo を選択するには、SHIFT キーを押しながら、Gpo の隣接するグループ内の最後の GPO をクリックするか、CTRL キーを押しながら個別の Gpo をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-113">To select multiple GPOs, press SHIFT and click the last GPO in a contiguous group of GPOs, or press CTRL and click individual GPOs.</span></span> <span data-ttu-id="6213b-114">選択した GPO を右クリックし、[**ラベル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-114">Right-click a selected GPO, and then click **Label**.</span></span>

4.  <span data-ttu-id="6213b-115">選択されている各 GPO の履歴に表示するラベルとコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-115">Type a label and a comment to be displayed in the history of each GPO selected, and then click **OK**.</span></span>

5.  <span data-ttu-id="6213b-116">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6213b-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

### <span data-ttu-id="6213b-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6213b-117">Additional considerations</span></span>

-   <span data-ttu-id="6213b-118">既定では、この手順を実行するには、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6213b-118">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="6213b-119">具体的には、その GPO の [**コンテンツの一覧]** と [**設定の編集**] または [gpo のアクセス許可の**展開**] を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6213b-119">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="6213b-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="6213b-120">Additional references</span></span>

-   [<span data-ttu-id="6213b-121">GPO の編集</span><span class="sxs-lookup"><span data-stu-id="6213b-121">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

 

 





