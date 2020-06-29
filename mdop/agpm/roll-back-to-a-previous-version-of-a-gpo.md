---
title: GPO の以前のバージョンにロールバックする
description: GPO の以前のバージョンにロールバックする
author: dansimp
ms.assetid: 028631c0-4cb9-4642-90ad-04cd813051b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a71740eaa60a4b1292e47ca8aa57d4657231ab57
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820284"
---
# <span data-ttu-id="dadc7-103">GPO の以前のバージョンにロールバックする</span><span class="sxs-lookup"><span data-stu-id="dadc7-103">Roll Back to a Previous Version of a GPO</span></span>


<span data-ttu-id="dadc7-104">高度なグループポリシー管理 (AGPM) により、承認者は、以前のバージョンの GPO を履歴から再展開することで、グループポリシーオブジェクト (GPO) への変更をロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="dadc7-104">Advanced Group Policy Management (AGPM) enables an Approver to roll back changes to a Group Policy object (GPO) by redeploying an earlier version of the GPO from its history.</span></span> <span data-ttu-id="dadc7-105">以前のバージョンの GPO を展開すると、現在運用されている GPO のバージョンが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="dadc7-105">Deploying an earlier version of a GPO overwrites the version of the GPO currently in production.</span></span>

<span data-ttu-id="dadc7-106">この手順を完了するには、承認者または AGPM 管理者 (フルコントロール) の役割、または高度なグループポリシーの管理に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="dadc7-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="dadc7-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dadc7-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="dadc7-108">以前のバージョンの GPO を運用環境に展開するには</span><span class="sxs-lookup"><span data-stu-id="dadc7-108">To deploy a previous version of a GPO to the production environment</span></span>**

1.  <span data-ttu-id="dadc7-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dadc7-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="dadc7-110">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="dadc7-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="dadc7-111">展開する GPO をダブルクリックして、その**履歴**を表示します。</span><span class="sxs-lookup"><span data-stu-id="dadc7-111">Double-click the GPO to be deployed to display its **History**.</span></span>

4.  <span data-ttu-id="dadc7-112">展開するバージョンを右クリックし、[**展開**] をクリックして、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dadc7-112">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

5.  <span data-ttu-id="dadc7-113">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dadc7-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="dadc7-114">[**履歴**] ウィンドウで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dadc7-114">In the **History** window, click **Close**.</span></span>

<span data-ttu-id="dadc7-115">**注** 再配置されたバージョンが目的のバージョンと一致することを確認するには、2つのバージョンの差レポートを調べます。</span><span class="sxs-lookup"><span data-stu-id="dadc7-115">**Note** To verify that the version that has been redeployed matches the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="dadc7-116">GPO の [**履歴**] ウィンドウで、2つのバージョンを強調表示し、右クリックして、[**相違点**] と [ **HTML レポート**] または [ **XML レポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="dadc7-116">In the **History** window for the GPO, highlight the two versions, and then right-click and select **Difference** and either **HTML Report** or **XML Report**.</span></span>

 

### <span data-ttu-id="dadc7-117">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="dadc7-117">Additional considerations</span></span>

-   <span data-ttu-id="dadc7-118">既定では、この手順を実行するには、承認者または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadc7-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="dadc7-119">具体的には、GPO の [**コンテンツの一覧表示**] と [ **gpo の展開**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="dadc7-119">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="dadc7-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="dadc7-120">Additional references</span></span>

-   [<span data-ttu-id="dadc7-121">承認者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="dadc7-121">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

 

 





