---
title: 未制御の GPO を制御する
description: 未制御の GPO を制御する
author: dansimp
ms.assetid: dc81545c-8da5-4b6f-b266-f01a82e27c6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 418e2a4100e1d824198b7d05034443948ec8a44c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818904"
---
# <span data-ttu-id="04af4-103">未制御の GPO を制御する</span><span class="sxs-lookup"><span data-stu-id="04af4-103">Control an Uncontrolled GPO</span></span>


<span data-ttu-id="04af4-104">グループポリシーオブジェクト (GPO) の変更制御を指定するには、まず GPO を制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04af4-104">To provide change control for a Group Policy Object (GPO), you must first control the GPO.</span></span>

<span data-ttu-id="04af4-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="04af4-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="04af4-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="04af4-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="04af4-107">制御されない GPO を制御するには</span><span class="sxs-lookup"><span data-stu-id="04af4-107">To control an uncontrolled GPO</span></span>**

1.  <span data-ttu-id="04af4-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04af4-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="04af4-109">[詳細] ウィンドウの [**コンテンツ**] タブで、[**非コントロール**] タブをクリックして、制御されていない gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="04af4-109">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="04af4-110">AGPM で制御する GPO を右クリックし、[**コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04af4-110">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="04af4-111">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04af4-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="04af4-112">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="04af4-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="04af4-113">[**非コントロール**] タブの一覧から GPO が削除され、[**コントロール**] タブに追加されます。</span><span class="sxs-lookup"><span data-stu-id="04af4-113">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Controlled** tab.</span></span>

### <span data-ttu-id="04af4-114">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="04af4-114">Additional considerations</span></span>

-   <span data-ttu-id="04af4-115">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="04af4-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="04af4-116">具体的には、ドメインの [**コンテンツの一覧表示**] と [GPO のアクセス許可の**作成**] を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="04af4-116">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="04af4-117">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="04af4-117">Additional references</span></span>

-   [<span data-ttu-id="04af4-118">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="04af4-118">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





