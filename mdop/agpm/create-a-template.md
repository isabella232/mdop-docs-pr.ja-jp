---
title: テンプレートを作成する
description: テンプレートを作成する
author: dansimp
ms.assetid: 6992bd55-4a4f-401f-9815-c468bac598ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9ad57204170fc3f49b01b571d82b00e1faf62de0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821067"
---
# <span data-ttu-id="b46db-103">テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="b46db-103">Create a Template</span></span>


<span data-ttu-id="b46db-104">テンプレートを作成すると、特定のバージョンのグループポリシーオブジェクト (GPO) のすべての設定を保存して、新しい Gpo の作成の開始点として使用することができます。</span><span class="sxs-lookup"><span data-stu-id="b46db-104">Creating a template enables you to save all of the settings of a particular version of a Group Policy object (GPO) to use as a starting point for creating new GPOs.</span></span>

<span data-ttu-id="b46db-105">**注** テンプレートは、新しい編集可能な Gpo を作成するための出発点として使用する、編集できない静的バージョンの GPO です。</span><span class="sxs-lookup"><span data-stu-id="b46db-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="b46db-106">この手順を完了するには、エディターまたは AGPM 管理者 (フルコントロール) の役割を持つユーザーアカウント、または高度なグループポリシーの管理に必要なアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="b46db-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="b46db-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b46db-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="b46db-108">既存の GPO に基づいてテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="b46db-108">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="b46db-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b46db-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="b46db-110">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] または [**非コントロール**] タブをクリックして、使用できる gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="b46db-110">On the **Contents** tab in the details pane, click the **Controlled** or **Uncontrolled** tab to display available GPOs.</span></span>

3.  <span data-ttu-id="b46db-111">テンプレートを作成する GPO を右クリックし、[**テンプレートとして保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b46db-111">Right-click the GPO from which you want to create a template, then click **Save as Template**.</span></span>

4.  <span data-ttu-id="b46db-112">テンプレートの名前とコメントを入力して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b46db-112">Type a name for the template and a comment, then click **OK**.</span></span>

5.  <span data-ttu-id="b46db-113">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b46db-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="b46db-114">新しいテンプレートが [**テンプレート**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="b46db-114">The new template appears on the **Templates** tab.</span></span>

### <span data-ttu-id="b46db-115">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="b46db-115">Additional considerations</span></span>

-   <span data-ttu-id="b46db-116">既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="b46db-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="b46db-117">具体的には、ドメインの [**リストコンテンツ]** と [テンプレートのアクセス許可の**作成**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b46db-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="b46db-118">テンプレートの名前の変更や削除は、そのテンプレートを基にして作成された Gpo には影響しません。</span><span class="sxs-lookup"><span data-stu-id="b46db-118">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="b46db-119">変更できないため、テンプレートには履歴がありません。</span><span class="sxs-lookup"><span data-stu-id="b46db-119">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="b46db-120">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="b46db-120">Additional references</span></span>

-   [<span data-ttu-id="b46db-121">テンプレートの作成と既定のテンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="b46db-121">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template.md)

-   [<span data-ttu-id="b46db-122">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="b46db-122">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo.md)

 

 





