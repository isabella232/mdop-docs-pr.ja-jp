---
title: 未制御の GPO の制御を要求する
description: 未制御の GPO の制御を要求する
author: dansimp
ms.assetid: a34e0aeb-33a1-4c9f-b187-1d08493a785c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bfccd7285f82990c2447319485738131cf559f48
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818447"
---
# <span data-ttu-id="45883-103">未制御の GPO の制御を要求する</span><span class="sxs-lookup"><span data-stu-id="45883-103">Request Control of an Uncontrolled GPO</span></span>


<span data-ttu-id="45883-104">既存のグループポリシーオブジェクト (GPO) の変更の制御を提供するには、GPO を制御する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45883-104">To provide change control for an existing Group Policy Object (GPO), the GPO must be controlled.</span></span> <span data-ttu-id="45883-105">承認者または AGPM 管理者 (フルコントロール) でない場合は、GPO の制御を要求する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45883-105">Unless you are an Approver or an AGPM Administrator (Full Control), you must request that the GPO be controlled.</span></span>

<span data-ttu-id="45883-106">この手順を完了するには、編集者の役割、または高度なグループポリシー管理 (AGPM) で必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="45883-106">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="45883-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="45883-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="45883-108">制御されない GPO を制御するには</span><span class="sxs-lookup"><span data-stu-id="45883-108">To control an uncontrolled GPO</span></span>**

1.  <span data-ttu-id="45883-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45883-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="45883-110">[詳細] ウィンドウの [**コンテンツ**] タブで、[**非コントロール**] タブをクリックして、制御されていない gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="45883-110">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="45883-111">AGPM で制御する GPO を右クリックし、[**コントロール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45883-111">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="45883-112">Gpo を制御するための特別なアクセス許可がない場合は、制御の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="45883-112">Unless you have special permission to control GPOs, you must submit a request for control.</span></span> <span data-ttu-id="45883-113">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="45883-113">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="45883-114">GPO の**履歴**に表示するコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45883-114">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="45883-115">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="45883-115">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="45883-116">[**非コントロール**] タブの一覧から GPO が削除され、[**保留中**] タブに追加されます。承認者がリクエストを承認すると、その GPO は [**コントロール**] タブに移動されます。</span><span class="sxs-lookup"><span data-stu-id="45883-116">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="45883-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="45883-117">Additional considerations</span></span>

-   <span data-ttu-id="45883-118">既定では、この手順を実行するには、編集者またはレビュー担当者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="45883-118">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="45883-119">具体的には、ドメインの [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="45883-119">Specifically, you must have **List Contents** and **Read Settings** permissions for the domain.</span></span>

-   <span data-ttu-id="45883-120">承認される前に要求を取り消すには、[**保留中**] タブをクリックします。 GPO を右クリックし、[**取り消し] をクリックし**ます。</span><span class="sxs-lookup"><span data-stu-id="45883-120">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="45883-121">GPO は [**非コントロール**] タブに戻ります。</span><span class="sxs-lookup"><span data-stu-id="45883-121">The GPO will be returned to the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="45883-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="45883-122">Additional references</span></span>

-   [<span data-ttu-id="45883-123">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="45883-123">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-ed.md)

 

 




