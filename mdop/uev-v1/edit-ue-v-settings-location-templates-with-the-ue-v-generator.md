---
title: UE-V Generator を使用して UE-V 設定場所テンプレートを編集する
description: UE-V Generator を使用して UE-V 設定場所テンプレートを編集する
author: dansimp
ms.assetid: da78f9c8-1624-4111-8c96-79db7224bd0b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b90cd58761e6ac40c089f3afeade3c445a52ea6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827114"
---
# <span data-ttu-id="320da-103">UE-V Generator を使用して UE-V 設定場所テンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="320da-103">Edit UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="320da-104">Microsoft User Experience Virtualization (UE-V) Generator を使用して、設定場所テンプレートを編集します。</span><span class="sxs-lookup"><span data-stu-id="320da-104">Use the Microsoft User Experience Virtualization (UE-V) Generator to edit settings location templates.</span></span> <span data-ttu-id="320da-105">UE-V Generator を使用して、変更された設定がテンプレートに追加されると、そのテンプレート内のバージョン情報が自動的に更新され、企業に展開されている既存のテンプレートが正しく更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="320da-105">When the revised settings are added to the templates using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates deployed in the enterprise are updated correctly.</span></span>

**<span data-ttu-id="320da-106">Ue-v Generator を使用して UE-V 設定の場所テンプレートを編集する方法</span><span class="sxs-lookup"><span data-stu-id="320da-106">How to edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="320da-107">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="320da-107">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="320da-108">[**設定の場所テンプレートの編集] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="320da-108">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="320da-109">最近使用したテンプレートの一覧で、編集するテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="320da-109">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="320da-110">または、設定テンプレートファイルを**参照**します。</span><span class="sxs-lookup"><span data-stu-id="320da-110">Alternatively, **Browse** to the settings template file.</span></span> <span data-ttu-id="320da-111">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="320da-111">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="320da-112">設定テンプレートの**プロパティ**、**レジストリ**の場所、**ファイル**の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="320da-112">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="320da-113">必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="320da-113">Edit as needed.</span></span>

    -   <span data-ttu-id="320da-114">[**プロパティ**] タブでは、次のプロパティを表示して編集できます。</span><span class="sxs-lookup"><span data-stu-id="320da-114">The **Properties** tab allows you to view and edit the following properties:</span></span>

        -   <span data-ttu-id="320da-115">[ **Application name**]: プログラムファイルプロパティの説明で書かれたアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="320da-115">**Application name**: The application name written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="320da-116">[ **Program name**]: プログラムファイルのプロパティから取得したプログラムの名前です。</span><span class="sxs-lookup"><span data-stu-id="320da-116">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="320da-117">通常、この名前には .exe 拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="320da-117">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="320da-118">[**製品バージョン**: アプリケーションの .exe ファイルの製品バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="320da-118">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="320da-119">このプロパティは、**ファイルバージョン**と共に、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="320da-119">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="320da-120">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="320da-120">This property accepts a major version number.</span></span> <span data-ttu-id="320da-121">このプロパティが空の場合、設定場所テンプレートは製品のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="320da-121">If this property is empty, then the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="320da-122">[ **File version**: application の the.exe ファイルのファイルバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="320da-122">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="320da-123">このプロパティは**製品バージョン**と共に、設定場所テンプレートによって対象となるアプリケーションを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="320da-123">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="320da-124">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="320da-124">This property accepts a major version number.</span></span> <span data-ttu-id="320da-125">このプロパティが空の場合は、設定の場所テンプレートがプログラムのすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="320da-125">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="320da-126">**テンプレート作成者の名前**(省略可能): 設定テンプレートの作成者の名前。</span><span class="sxs-lookup"><span data-stu-id="320da-126">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="320da-127">**テンプレート作成者のメール**(オプション): 設定場所テンプレートの作成者のメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="320da-127">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="320da-128">[**レジストリ**] タブには、設定場所テンプレートに含まれているレジストリの場所の**キー**と**範囲**が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="320da-128">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="320da-129">[**タスク**] ドロップダウンメニューを使用して、レジストリの場所を編集できます。</span><span class="sxs-lookup"><span data-stu-id="320da-129">You can edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="320da-130">タスクには、新しいキーの追加、既存のキーの名前または範囲の編集、キーの削除、キーが存在するレジストリの参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="320da-130">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry in which the keys are located.</span></span> <span data-ttu-id="320da-131">レジストリのスコープを定義するときは、**すべての設定**のスコープを使用して、指定したキーの下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="320da-131">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="320da-132">**すべての設定**と**サブ**キーを使用して、指定したキー、サブキー、サブキーの設定の下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="320da-132">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="320da-133">[**ファイル**] タブには、設定場所テンプレートに含まれているファイルの場所のファイルパスとファイルマスクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="320da-133">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="320da-134">[**タスク**] ドロップダウンメニューを使用して、ファイルの場所を編集できます。</span><span class="sxs-lookup"><span data-stu-id="320da-134">You can edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="320da-135">ファイルの場所のタスクには、新しいファイルまたはフォルダーの場所の追加、既存のファイルまたはフォルダーの範囲の編集、ファイルまたはフォルダーの削除、選択した場所を Windows エクスプローラーで開くなどがあります。</span><span class="sxs-lookup"><span data-stu-id="320da-135">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="320da-136">指定したフォルダーにあるすべてのファイルを含めるには、ファイルのマスクを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="320da-136">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="320da-137">[**保存**] をクリックして、設定場所テンプレートの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="320da-137">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="320da-138">[**閉じる**] をクリックして、設定テンプレートウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="320da-138">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="320da-139">UE-V Generator アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="320da-139">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="320da-140">アプリケーションの設定場所テンプレートを編集した後で、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="320da-140">After editing the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="320da-141">組織内の運用環境に展開する前に、ラボ環境に改訂された設定場所のテンプレートを展開します。</span><span class="sxs-lookup"><span data-stu-id="320da-141">Deploy the revised settings location template in a lab environment before putting it into production in the enterprise.</span></span>

**<span data-ttu-id="320da-142">設定場所テンプレートを手動で編集する方法</span><span class="sxs-lookup"><span data-stu-id="320da-142">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="320da-143">設定場所テンプレート (.xml ファイル) のローカルコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="320da-143">Create a local copy of the settings location template (.xml file).</span></span> <span data-ttu-id="320da-144">UE-V settings location テンプレートは、アプリケーションストアの設定値が格納されている場所を識別する .xml ファイルです。</span><span class="sxs-lookup"><span data-stu-id="320da-144">UE-V settings location templates are .xml files identifying the locations where application store settings values.</span></span>

2.  <span data-ttu-id="320da-145">XML エディターを使用して設定場所テンプレートファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="320da-145">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="320da-146">設定場所テンプレートファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="320da-146">Edit the settings location template file.</span></span> <span data-ttu-id="320da-147">すべての変更は、SettingsLocationTempate で定義されている UE-V スキーマファイルに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="320da-147">All changes must conform to the UE-V schema file defined in SettingsLocationTempate.xsd.</span></span> <span data-ttu-id="320da-148">.Xsd ファイルのコピーは、既定で配置されています `\ProgramData\Microsoft\UEV\Templates` 。</span><span class="sxs-lookup"><span data-stu-id="320da-148">A copy of the .xsd file is located in `\ProgramData\Microsoft\UEV\Templates` by default.</span></span>

4.  <span data-ttu-id="320da-149">設定場所テンプレートファイルを保存して、XML エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="320da-149">Save the settings location template file and close the XML editor.</span></span>

5.  <span data-ttu-id="320da-150">変更された設定場所テンプレートファイルについて、UE-V Generator を使って検証します。</span><span class="sxs-lookup"><span data-stu-id="320da-150">Validate the modified settings location template file with the UE-V Generator.</span></span> <span data-ttu-id="320da-151">UE-V Generator による検証の詳細については、「ue-v [generator を使用して Ue-v 設定の場所テンプレートを検証](validate-ue-v-settings-location-templates-with-ue-v-generator.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="320da-151">For more information about validating with the UE-V Generator, see [Validate UE-V Settings Location Templates with UE-V Generator](validate-ue-v-settings-location-templates-with-ue-v-generator.md).</span></span>

## <span data-ttu-id="320da-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="320da-152">Related topics</span></span>


[<span data-ttu-id="320da-153">カスタム UE-V テンプレートと UE-V Generator の操作</span><span class="sxs-lookup"><span data-stu-id="320da-153">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="320da-154">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="320da-154">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





