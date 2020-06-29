---
title: 未制御の GPO を制御する
description: 未制御の GPO を制御する
author: dansimp
ms.assetid: 452689a9-4e32-4e3b-8208-56353a82bf36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d7349b16b326a49b701efae5379c313bde0964f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818887"
---
# <span data-ttu-id="67fe4-103">未制御の GPO を制御する</span><span class="sxs-lookup"><span data-stu-id="67fe4-103">Control a Previously Uncontrolled GPO</span></span>


<span data-ttu-id="67fe4-104">高度なグループポリシー管理 (AGPM) を使ってグループポリシーオブジェクト (GPO) の変更制御を提供するには、まず、AGPM で GPO を制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67fe4-104">To use Advanced Group Policy Management (AGPM) to provide change control for a Group Policy object (GPO), you must first control the GPO with AGPM.</span></span>

<span data-ttu-id="67fe4-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="67fe4-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="67fe4-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67fe4-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="67fe4-107">以前に制御していない GPO を制御するには</span><span class="sxs-lookup"><span data-stu-id="67fe4-107">To control a previously uncontrolled GPO</span></span>**

1.  <span data-ttu-id="67fe4-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fe4-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="67fe4-109">[詳細] ウィンドウの [**コンテンツ**] タブで、[**非コントロール**] タブをクリックして、制御されていない gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="67fe4-109">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="67fe4-110">AGPM で制御する GPO を右クリックし、[**コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fe4-110">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="67fe4-111">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fe4-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="67fe4-112">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67fe4-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="67fe4-113">[**非コントロール**] タブの一覧から GPO が削除され、[**コントロール**] タブに追加されます。</span><span class="sxs-lookup"><span data-stu-id="67fe4-113">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Controlled** tab.</span></span>

### <span data-ttu-id="67fe4-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="67fe4-114">Additional considerations</span></span>

-   <span data-ttu-id="67fe4-115">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="67fe4-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="67fe4-116">具体的には、ドメインの [**コンテンツの一覧表示**] と [GPO のアクセス許可の**作成**] を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67fe4-116">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="67fe4-117">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="67fe4-117">Additional references</span></span>

-   [<span data-ttu-id="67fe4-118">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="67fe4-118">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





