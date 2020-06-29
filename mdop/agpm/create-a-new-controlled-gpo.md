---
title: 新しい制御された GPO を作成する
description: 新しい制御された GPO を作成する
author: dansimp
ms.assetid: b43ce0f4-4519-4278-83c4-c7d5163ddd11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a64e22036bfe99e1d5012d732e3f2e081acdcca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821094"
---
# <span data-ttu-id="983ca-103">新しい制御された GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="983ca-103">Create a New Controlled GPO</span></span>


<span data-ttu-id="983ca-104">**変更コントロール**ノードを使用して作成された新しいグループポリシーオブジェクト (gpo) は、自動的に制御され、高度なグループポリシー管理 (AGPM) を使ってそれらを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="983ca-104">New Group Policy objects (GPOs) created through the **Change Control** node will automatically be controlled, enabling you to manage them with Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="983ca-105">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="983ca-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="983ca-106">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="983ca-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="983ca-107">AGPM によって管理される変更コントロールで新しい GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="983ca-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="983ca-108">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="983ca-109">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-109">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="983ca-110">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="983ca-110">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="983ca-111">新しい GPO の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="983ca-111">Type a name for the new GPO.</span></span>

    2.  <span data-ttu-id="983ca-112">オプション: GPO の**履歴**に表示される新しい gpo のコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="983ca-112">Optional: Type a comment for the new GPO to be displayed in the **History** for the GPO.</span></span>

    3.  <span data-ttu-id="983ca-113">新しい GPO を直ちに運用環境に展開するには、[**ライブの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-113">To immediately deploy the new GPO to the production environment, click **Create live**.</span></span> <span data-ttu-id="983ca-114">新しい GPO をすぐに展開せずにオフラインで作成するには、[**オフラインで作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-114">To create the new GPO offline without immediately deploying it, click **Create offline**.</span></span>

    4.  <span data-ttu-id="983ca-115">新しい GPO の開始点として使用する GPO テンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="983ca-115">Select the GPO template to use as a starting point for the new GPO.</span></span>

    5.  <span data-ttu-id="983ca-116">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-116">Click **OK**.</span></span>

4.  <span data-ttu-id="983ca-117">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="983ca-117">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="983ca-118">新しい GPO が [**コントロール**] タブの gpo の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="983ca-118">The new GPO is displayed in the list of GPOs on the **Controlled** tab.</span></span>

### <span data-ttu-id="983ca-119">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="983ca-119">Additional considerations</span></span>

-   <span data-ttu-id="983ca-120">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="983ca-120">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="983ca-121">具体的には、ドメインの [**コンテンツの一覧表示**] と [GPO のアクセス許可の**作成**] を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="983ca-121">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="983ca-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="983ca-122">Additional references</span></span>

-   [<span data-ttu-id="983ca-123">GPO の作成、制御、インポート</span><span class="sxs-lookup"><span data-stu-id="983ca-123">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





