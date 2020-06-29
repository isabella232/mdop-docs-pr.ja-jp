---
title: GPO のリンクを確認する
description: GPO のリンクを確認する
author: dansimp
ms.assetid: 3c472448-f16a-493c-a229-5ca60a470965
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe8b40b4401f08a36217237487bf2b2c0c6c0689
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818344"
---
# <span data-ttu-id="d7690-103">GPO のリンクを確認する</span><span class="sxs-lookup"><span data-stu-id="d7690-103">Review GPO Links</span></span>


<span data-ttu-id="d7690-104">選択したグループポリシーオブジェクト (GPO) または Gpo が組織単位にリンクされている場所を示す図を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="d7690-104">You can display a diagram showing where a Group Policy object (GPO) or GPOs that you select are linked to organizational units.</span></span> <span data-ttu-id="d7690-105">GPO リンク図は、GPO が制御、インポート、またはチェックインされるたびに更新されます。</span><span class="sxs-lookup"><span data-stu-id="d7690-105">GPO link diagrams are updated each time the GPO is controlled, imported, or checked in.</span></span>

<span data-ttu-id="d7690-106">この手順を完了するには、レビュー担当者、編集者、承認者、または AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシー管理の必要なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7690-106">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="d7690-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d7690-107">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="d7690-108">GPO リンクを確認する</span><span class="sxs-lookup"><span data-stu-id="d7690-108">Reviewing GPO links</span></span>


-   [<span data-ttu-id="d7690-109">1つ以上の Gpo の場合</span><span class="sxs-lookup"><span data-stu-id="d7690-109">For one or more GPOs</span></span>](#bkmk-gpos)

-   [<span data-ttu-id="d7690-110">1つ以上のバージョンの GPO の場合</span><span class="sxs-lookup"><span data-stu-id="d7690-110">For one or more versions of a GPO</span></span>](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**<span data-ttu-id="d7690-111">1つ以上の Gpo の GPO リンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="d7690-111">To display GPO links for one or more GPOs</span></span>**

1.  <span data-ttu-id="d7690-112">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7690-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d7690-113">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**]、[**保留中**]、または [**ごみ箱**] タブをクリックして、gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7690-113">On the **Contents** tab in the details pane, click the **Controlled**, **Pending**, or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="d7690-114">リンクを表示する1つ以上の Gpo を選択し、選択した GPO を右クリックして [**設定**] をクリックし、[ **gpo リンク**] をクリックして、選んだ gpo へのリンクを含むドメインと組織単位の図を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7690-114">Select one or more GPOs for which to display links, right-click a selected GPO, click **Settings**, and then click **GPO Links** to display a diagram of domains and organizational units with links to the selected GPO(s).</span></span>

### <a href="" id="bkmk-gpo-versions"></a>

**<span data-ttu-id="d7690-115">1つ以上のバージョンの GPO の GPO リンクを表示するには</span><span class="sxs-lookup"><span data-stu-id="d7690-115">To display GPO links for one or more versions of a GPO</span></span>**

1.  <span data-ttu-id="d7690-116">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d7690-116">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d7690-117">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] または [**ごみ箱**] タブをクリックして、gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7690-117">On the **Contents** tab in the details pane, click the **Controlled** or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="d7690-118">GPO をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7690-118">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="d7690-119">設定を確認する GPO のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] または [ **XML レポート**] をクリックして、gpo の設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="d7690-119">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="d7690-120">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="d7690-120">Additional considerations</span></span>

-   <span data-ttu-id="d7690-121">既定では、この手順を実行するには、レビュー担当者、編集者、承認者、AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7690-121">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d7690-122">具体的には、GPO の [**リストコンテンツ]** と [**読み取り設定**] のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7690-122">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="d7690-123">また、Gpo の一覧を表示するには、ドメインの**リストコンテンツ**のアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7690-123">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="d7690-124">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="d7690-124">Additional references</span></span>

-   [<span data-ttu-id="d7690-125">レビュー担当者タスクの実行</span><span class="sxs-lookup"><span data-stu-id="d7690-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

 

 





