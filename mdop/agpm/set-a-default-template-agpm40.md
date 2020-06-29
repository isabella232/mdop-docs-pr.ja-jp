---
title: 既定のテンプレートを設定する
description: 既定のテンプレートを設定する
author: dansimp
ms.assetid: 07208b6b-cb3a-4f6c-9c84-36d4dc1486d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51a13c2c57e38adca883a6eb962d8c5eae4316db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820234"
---
# <span data-ttu-id="bb652-103">既定のテンプレートを設定する</span><span class="sxs-lookup"><span data-stu-id="bb652-103">Set a Default Template</span></span>


<span data-ttu-id="bb652-104">エディターとして、新しいグループポリシーオブジェクト (Gpo) を作成するすべてのグループポリシー管理者に対して提案される既定のテンプレートとして使用できるテンプレートを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="bb652-104">As an Editor, you can specify which of the available templates will be the default template suggested for all Group Policy administrators creating new Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="bb652-105">**注** テンプレートは、新しい編集可能な Gpo を作成するための出発点として使用する、編集できない静的バージョンの GPO です。</span><span class="sxs-lookup"><span data-stu-id="bb652-105">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="bb652-106">この手順を完了するには、Editor または AGPM 管理者 (フルコントロール) の役割を持つ、または高度なグループポリシー管理 (AGPM) に必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="bb652-106">A user account with the Editor or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="bb652-107">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bb652-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="bb652-108">新しい Gpo の作成時に使用する既定のテンプレートを設定するには</span><span class="sxs-lookup"><span data-stu-id="bb652-108">To set the default template for use when creating new GPOs</span></span>**

1.  <span data-ttu-id="bb652-109">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb652-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="bb652-110">[詳細] ウィンドウの [**コンテンツ**] タブで、[**テンプレート**] タブをクリックして、利用可能なテンプレートを表示します。</span><span class="sxs-lookup"><span data-stu-id="bb652-110">On the **Contents** tab in the details pane, click the **Templates** tab to display available templates.</span></span>

3.  <span data-ttu-id="bb652-111">既定として設定するテンプレートを右クリックし、[**既定に設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb652-111">Right-click the template that you want to set as the default, and then click **Set as Default**.</span></span>

4.  <span data-ttu-id="bb652-112">[**はい]** をクリックして確認します。</span><span class="sxs-lookup"><span data-stu-id="bb652-112">Click **Yes** to confirm.</span></span>

5.  <span data-ttu-id="bb652-113">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bb652-113">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="bb652-114">既定のテンプレートには青色のアイコンがあり、その状態は **[テンプレート] タブの**[**テンプレート] (既定)** として識別されます。</span><span class="sxs-lookup"><span data-stu-id="bb652-114">The default template has a blue icon and the state is identified as **Template (default)** on the **Templates** tab.</span></span>

### <span data-ttu-id="bb652-115">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="bb652-115">Additional considerations</span></span>

-   <span data-ttu-id="bb652-116">既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb652-116">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="bb652-117">具体的には、ドメインの [**リストコンテンツ]** と [テンプレートのアクセス許可の**作成**] のアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bb652-117">Specifically, you must have **List Contents** and **Create Template** permissions for the domain.</span></span>

-   <span data-ttu-id="bb652-118">テンプレートを既定として設定すると、グループポリシー管理者が新しい Gpo を作成するときに、そのテンプレートが [**新しいコントロール**された gpo] ダイアログボックスで最初に選択されます。</span><span class="sxs-lookup"><span data-stu-id="bb652-118">After you set a template as the default, that template will be the one initially selected in the **New Controlled GPO** dialog box when Group Policy administrators create new GPOs.</span></span> <span data-ttu-id="bb652-119">ただし、設定が含まれていない\*\* &lt; 空の gpo &gt; \*\*を含むその他の gpo テンプレートを選択するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="bb652-119">However, they will have the option to select any other GPO template, including **&lt;Empty GPO&gt;**, which does not include any settings.</span></span>

-   <span data-ttu-id="bb652-120">テンプレートの名前の変更や削除は、そのテンプレートを基にして作成された Gpo には影響しません。</span><span class="sxs-lookup"><span data-stu-id="bb652-120">Renaming or deleting a template does not impact GPOs created from that template.</span></span>

-   <span data-ttu-id="bb652-121">変更できないため、テンプレートには履歴がありません。</span><span class="sxs-lookup"><span data-stu-id="bb652-121">Because it cannot be altered, a template does not have a history.</span></span>

### <span data-ttu-id="bb652-122">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="bb652-122">Additional references</span></span>

-   [<span data-ttu-id="bb652-123">テンプレートの作成と既定のテンプレートの設定</span><span class="sxs-lookup"><span data-stu-id="bb652-123">Creating a Template and Setting a Default Template</span></span>](creating-a-template-and-setting-a-default-template-agpm40.md)

-   [<span data-ttu-id="bb652-124">新しい制御された GPO の作成を要求する</span><span class="sxs-lookup"><span data-stu-id="bb652-124">Request the Creation of a New Controlled GPO</span></span>](request-the-creation-of-a-new-controlled-gpo-agpm40.md)

 

 





