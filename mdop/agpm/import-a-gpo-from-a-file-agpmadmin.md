---
title: ファイルから GPO をインポートする
description: ファイルから GPO をインポートする
author: dansimp
ms.assetid: 2cbcda72-4de3-47ad-aaf8-4fc7341d5a00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04819dacac8df73f0a61cace0dab8b9fa79b7307
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820754"
---
# <span data-ttu-id="1487c-103">ファイルから GPO をインポートする</span><span class="sxs-lookup"><span data-stu-id="1487c-103">Import a GPO from a File</span></span>


<span data-ttu-id="1487c-104">詳細なグループポリシー管理 (AGPM) では、AGPM 管理者 (フルコントロール) で、グループポリシーオブジェクト (GPO) を CAB ファイルにエクスポートした場合、その GPO から別のフォレストのドメインの新しい GPO または既存の GPO にポリシー設定をインポートできます。</span><span class="sxs-lookup"><span data-stu-id="1487c-104">In Advanced Group Policy Management (AGPM), if you are an AGPM Administrator (Full Control) and you have exported a Group Policy Object (GPO) to a CAB file, you can import the policy settings from that GPO into a new GPO or an existing GPO in a domain in another forest.</span></span> <span data-ttu-id="1487c-105">CAB ファイルに GPO 設定をエクスポートする方法について詳しくは、「 [gpo をファイルにエクスポート](export-a-gpo-to-a-file.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="1487c-105">For information about exporting GPO settings to a CAB file, see [Export a GPO to a File](export-a-gpo-to-a-file.md).</span></span>

<span data-ttu-id="1487c-106">新しい制御された GPO にポリシー設定をインポートするには、AGPM 管理者の役割または AGPM の必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1487c-106">A user account with the AGPM Administrator role or the necessary permissions in AGPM is required to import policy settings into a new controlled GPO.</span></span> <span data-ttu-id="1487c-107">既存の GPO にポリシー設定をインポートするには、エディターまたは AGPM 管理者の役割または AGPM の必要なアクセス許可を持つユーザーアカウントが必要です。</span><span class="sxs-lookup"><span data-stu-id="1487c-107">A user account with the Editor or AGPM Administrator role or necessary permissions in AGPM is required to import policy settings into an existing GPO.</span></span> <span data-ttu-id="1487c-108">詳細については、このトピックの「その他の考慮事項」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1487c-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="1487c-109">ファイルからポリシー設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="1487c-109">Importing policy settings from a file</span></span>


<span data-ttu-id="1487c-110">ファイルからポリシー設定をインポートする場合は、新しい GPO または既存の GPO にインポートすることができます。</span><span class="sxs-lookup"><span data-stu-id="1487c-110">When you import policy settings from a file, you can import them into a new GPO or an existing GPO.</span></span> <span data-ttu-id="1487c-111">ただし、既存の GPO にポリシー設定をインポートする場合は、その中のすべてのポリシー設定が置換されます。</span><span class="sxs-lookup"><span data-stu-id="1487c-111">However, if you import policy settings into an existing GPO, all policy settings within it are replaced.</span></span>

-   [<span data-ttu-id="1487c-112">ポリシー設定を新しい制御された GPO にインポートする</span><span class="sxs-lookup"><span data-stu-id="1487c-112">Import policy settings into a new controlled GPO</span></span>](#bkmk-new)

-   [<span data-ttu-id="1487c-113">既存の GPO にポリシー設定をインポートする</span><span class="sxs-lookup"><span data-stu-id="1487c-113">Import policy settings into an existing GPO</span></span>](#bkmk-existing)

### <a href="" id="bkmk-new"></a>

**<span data-ttu-id="1487c-114">ポリシー設定を新しい制御された GPO にインポートするには</span><span class="sxs-lookup"><span data-stu-id="1487c-114">To import policy settings into a new controlled GPO</span></span>**

1.  <span data-ttu-id="1487c-115">[**グループポリシー管理コンソール**] ツリーで、ポリシー設定をインポートするドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1487c-115">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="1487c-116">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="1487c-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="1487c-117">新しい制御された GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="1487c-117">Create a new controlled GPO.</span></span> <span data-ttu-id="1487c-118">[**新しいコントロール**された GPO] ダイアログボックスで、[**インポート**] をクリックし、[**ウィザードの起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1487c-118">In the **New Controlled GPO** dialog box, click **Import** and then click **Launch Wizard**.</span></span> <span data-ttu-id="1487c-119">GPO の作成方法の詳細については、「[新しい制御された gpo を作成](create-a-new-controlled-gpo-agpm40.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1487c-119">For more information about how to create a GPO, see [Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md).</span></span>

4.  <span data-ttu-id="1487c-120">**設定のインポートウィザード**の指示に従って、gpo のバックアップを選択し、新しい gpo 用のポリシー設定をインポートして、新しい gpo の監査トレールのコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1487c-120">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import policy settings from it for the new GPO, and enter a comment for the audit trail of the new GPO.</span></span>

### <a href="" id="bkmk-existing"></a>

**<span data-ttu-id="1487c-121">既存の GPO にポリシー設定をインポートするには</span><span class="sxs-lookup"><span data-stu-id="1487c-121">To import policy settings into an existing GPO</span></span>**

1.  <span data-ttu-id="1487c-122">[**グループポリシー管理コンソール**] ツリーで、ポリシー設定をインポートするドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1487c-122">In the **Group Policy Management Console** tree, click **Change Control** in the domain to which you want to import policy settings.</span></span>

2.  <span data-ttu-id="1487c-123">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="1487c-123">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="1487c-124">ポリシー設定をインポートする宛先 GPO を確認します。</span><span class="sxs-lookup"><span data-stu-id="1487c-124">Check out the destination GPO to which you want to import policy settings.</span></span>

4.  <span data-ttu-id="1487c-125">送信先 GPO を右クリックし、[**インポート元**] をポイントして、[**ファイル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1487c-125">Right-click the destination GPO, point to **Import from**, and then click **File**.</span></span>

5.  <span data-ttu-id="1487c-126">**設定のインポートウィザード**の指示に従って、GPO のバックアップを選び、宛先 gpo のポリシー設定をインポートして、移行先 gpo の監査証跡に関するコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="1487c-126">Follow the instructions in the **Import Settings Wizard** to select a GPO backup, import its policy settings to replace those in the destination GPO, and enter a comment for the audit trail of the destination GPO.</span></span> <span data-ttu-id="1487c-127">既定では、ウィザードが終了すると、送信先 GPO がチェックインされます。</span><span class="sxs-lookup"><span data-stu-id="1487c-127">By default, the destination GPO is checked in when the wizard is finished.</span></span>

### <span data-ttu-id="1487c-128">その他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="1487c-128">Additional considerations</span></span>

-   <span data-ttu-id="1487c-129">ポリシー設定を新しい制御された GPO にインポートするには、[**コンテンツの一覧**]、[ **gpo のインポート**]、ドメインの gpo のアクセス許可を**作成**する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1487c-129">To import policy settings to a new controlled GPO, you must have **List Contents**, **Import GPO**, and **Create GPO** permissions for the domain.</span></span> <span data-ttu-id="1487c-130">既定では、この手順を実行するには AGPM 管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1487c-130">By default, you must be an AGPM Administrator to perform this procedure.</span></span>

-   <span data-ttu-id="1487c-131">既存の GPO にポリシー設定をインポートするには、ドメインの [**コンテンツの一覧表示**]、[**設定の編集**]、[ **gpo のインポート**] のアクセス許可が必要です。また、gpo をチェックアウトする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1487c-131">To import policy settings to an existing GPO, you must have **List Contents**, **Edit Settings**, and **Import GPO** permissions for the domain, and the GPO must be checked out by you.</span></span> <span data-ttu-id="1487c-132">既定では、この手順を実行するには、Editor または AGPM 管理者 (フルコントロール) である必要があります。</span><span class="sxs-lookup"><span data-stu-id="1487c-132">By default, you must be an Editor or an AGPM Administrator (Full Control) to perform this procedure.</span></span>

### <span data-ttu-id="1487c-133">その他の参照情報</span><span class="sxs-lookup"><span data-stu-id="1487c-133">Additional references</span></span>

-   [<span data-ttu-id="1487c-134">アーカイブの管理</span><span class="sxs-lookup"><span data-stu-id="1487c-134">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





