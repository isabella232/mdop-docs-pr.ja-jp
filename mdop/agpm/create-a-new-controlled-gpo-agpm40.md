---
title: 新しい制御された GPO を作成する
description: 新しい制御された GPO を作成する
author: dansimp
ms.assetid: 5ce760f6-9f05-42b4-b787-7835ab8e324e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67c6af686b9ba7254cdaf93bd2d294b2d5bbb681
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821097"
---
# <span data-ttu-id="4e2dc-103">新しい制御された GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="4e2dc-103">Create a New Controlled GPO</span></span>


<span data-ttu-id="4e2dc-104">**変更コントロール**フォルダーを使用して作成された新しいグループポリシーオブジェクト (gpo) は、自動的に制御され、管理できるようになります。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-104">New Group Policy Objects (GPOs) created through the **Change Control** folder will automatically be controlled, enabling you to manage them.</span></span>

<span data-ttu-id="4e2dc-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="4e2dc-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4e2dc-107">AGPM によって管理される変更コントロールで新しい GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="4e2dc-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="4e2dc-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4e2dc-109">[コントロールの**変更**] を右クリックし、[**新しい制御**された GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-109">Right-click **Change Control**, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="4e2dc-110">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-110">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="4e2dc-111">新しい GPO の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-111">Type a name for the new GPO.</span></span>

    2.  <span data-ttu-id="4e2dc-112">オプション: GPO の**履歴**に表示される新しい gpo のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-112">Optional: Type a comment for the new GPO to be displayed in the **History** for the GPO.</span></span>

    3.  <span data-ttu-id="4e2dc-113">新しい GPO をドメインの運用環境に直ちに展開するには、[**ライブの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-113">To immediately deploy the new GPO to the production environment of the domain, click **Create live**.</span></span> <span data-ttu-id="4e2dc-114">新しい GPO をすぐに展開せずにオフラインで作成するには、[**オフラインで作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-114">To create the new GPO offline without immediately deploying it, click **Create offline**.</span></span>

    4.  <span data-ttu-id="4e2dc-115">新しい GPO の開始点として使用する GPO テンプレートを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-115">Select the GPO template to use as a starting point for the new GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="4e2dc-116">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="4e2dc-117">新しい GPO が [**コントロール**] タブの gpo の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-117">The new GPO is displayed in the list of GPOs on the **Controlled** tab.</span></span>

### <span data-ttu-id="4e2dc-118">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="4e2dc-118">Additional considerations</span></span>

-   <span data-ttu-id="4e2dc-119">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-119">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="4e2dc-120">具体的には、ドメインの [**コンテンツの一覧表示**] と [GPO のアクセス許可の**作成**] を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4e2dc-120">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="4e2dc-121">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="4e2dc-121">Additional references</span></span>

-   [<span data-ttu-id="4e2dc-122">GPO の作成または制御</span><span class="sxs-lookup"><span data-stu-id="4e2dc-122">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





