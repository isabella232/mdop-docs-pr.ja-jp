---
title: カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する
description: カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する
author: dansimp
ms.assetid: f0bb4920-0132-472c-a564-abf06a884275
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a8d863896e4ccfa92161f8a8f5e2b8955f139872
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819294"
---
# <span data-ttu-id="cb4af-103">カスタム ue-v (ue-v) テンプレートと UE-V Generator を使って作業する</span><span class="sxs-lookup"><span data-stu-id="cb4af-103">Working with Custom UE-V 2.x Templates and the UE-V 2.x Generator</span></span>


<span data-ttu-id="cb4af-104">ユーザーコンピューター間のアプリケーション設定を同期するには、Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 では、*設定場所テンプレート*を使用します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-104">To synchronize application settings between user computers, Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use *settings location templates*.</span></span> <span data-ttu-id="cb4af-105">ユーザーエクスペリエンスの仮想化には、一部の設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cb4af-105">Some settings location templates are included in User Experience Virtualization.</span></span> <span data-ttu-id="cb4af-106">また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成、編集、または検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-106">You can also create, edit, or validate custom settings location templates by using the UE-V Generator.</span></span>

<span data-ttu-id="cb4af-107">UE-V Generator は、Windows デスクトップアプリケーションを監視して、アプリケーションの設定が保存されている場所を検出し、キャプチャします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-107">The UE-V Generator monitors Windows desktop applications to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="cb4af-108">監視されるアプリケーションはデスクトップアプリケーションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-108">The application that is monitored must be a desktop application.</span></span> <span data-ttu-id="cb4af-109">UE-V Generator は、次の種類のアプリケーションの設定場所テンプレートを作成できません。</span><span class="sxs-lookup"><span data-stu-id="cb4af-109">The UE-V Generator cannot create a settings location template for the following application types:</span></span>

-   <span data-ttu-id="cb4af-110">仮想化されたアプリケーション</span><span class="sxs-lookup"><span data-stu-id="cb4af-110">Virtualized applications</span></span>

-   <span data-ttu-id="cb4af-111">ターミナルサービスを通じて提供されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="cb4af-111">Applications that are offered through Terminal Services</span></span>

-   <span data-ttu-id="cb4af-112">Java アプリケーション</span><span class="sxs-lookup"><span data-stu-id="cb4af-112">Java applications</span></span>

-   <span data-ttu-id="cb4af-113">Windows アプリ  </span><span class="sxs-lookup"><span data-stu-id="cb4af-113">Windows apps</span></span>

<span data-ttu-id="cb4af-114">このトピック</span><span class="sxs-lookup"><span data-stu-id="cb4af-114">This topic</span></span>

<span data-ttu-id="cb4af-115">**標準設定と非標準設定の場所:** UE-V Generator は、アプリケーションが設定情報を格納するために使用する設定ファイルとレジストリ設定を検索する場所を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-115">**Standard and Nonstandard settings locations:** The UE-V Generator helps you identify where applications search for settings files and registry settings that applications use to store settings information.</span></span> <span data-ttu-id="cb4af-116">ジェネレーターは、標準ユーザーがアクセスできる場所にある設定のみを検出します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-116">The generator only discovers settings in locations that are accessible to a standard user.</span></span> <span data-ttu-id="cb4af-117">他の場所に保存されている設定は除外されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-117">Settings that are stored in other locations are excluded.</span></span> <span data-ttu-id="cb4af-118">検出された設定は、**標準**と**非標準**の2つのカテゴリに分類されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-118">Discovered settings are grouped into two categories: **Standard** and **Non-standard**.</span></span> <span data-ttu-id="cb4af-119">同期には標準設定をお勧めし、UE-V では簡単にキャプチャして適用することができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-119">Standard settings are recommended for synchronization, and UE-V can readily capture and apply them.</span></span> <span data-ttu-id="cb4af-120">標準以外の設定では、設定を同期することはできますが、UE-V で使用されているルールのため、これらの設定が一貫していないか、確実同期設定になっている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-120">Non-standard settings can potentially synchronize settings but, because of the rules that UE-V uses, these settings might not consistently or dependably synchronize settings.</span></span> <span data-ttu-id="cb4af-121">これらの設定は、一時ファイルに依存する場合や、信頼性の低い同期の結果である場合や、役に立たない場合もあります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-121">These settings might depend on temporary files, result in unreliable synchronization, or might not be useful.</span></span> <span data-ttu-id="cb4af-122">これらの設定の場所は、UE-V ジェネレーターで示されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-122">These settings locations are presented in the UE-V Generator.</span></span> <span data-ttu-id="cb4af-123">ケースバイケースごとに、それらを含めるか除外するかを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-123">You can choose to include or exclude them on a case-by-case basis.</span></span>

<span data-ttu-id="cb4af-124">UE-V Generator は、アプリを検出プロセスの一部として開きます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-124">The UE-V Generator opens the application as part of the discovery process.</span></span> <span data-ttu-id="cb4af-125">ジェネレーターは、次の場所で設定をキャプチャできます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-125">The generator can capture settings in the following locations:</span></span>

-   <span data-ttu-id="cb4af-126">**レジストリ設定**– HKEY の下にあるレジストリの場所 \ **_CURRENT \ _USER**</span><span class="sxs-lookup"><span data-stu-id="cb4af-126">**Registry Settings** – Registry locations under **HKEY\_CURRENT\_USER**</span></span>

-   <span data-ttu-id="cb4af-127">**アプリケーション設定ファイル**– \ \ **Users** \ \ [ユーザー名 \] に保存されているファイル (\ \ の場合) \ \ **AppData**  \\  **ローミング**</span><span class="sxs-lookup"><span data-stu-id="cb4af-127">**Application Settings Files** – Files that are stored under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**</span></span>

<span data-ttu-id="cb4af-128">UE-V Generator では、場所を除外します。これは、一般的にはアプリケーションソフトウェアファイルを保存しますが、ユーザーのコンピューターまたは環境間で適切に同期されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cb4af-128">The UE-V Generator excludes locations, which commonly store application software files, but do not synchronize well between user computers or environments.</span></span> <span data-ttu-id="cb4af-129">UE-V Generator では、これらの場所は除外されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-129">The UE-V Generator excludes these locations.</span></span> <span data-ttu-id="cb4af-130">除外する場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cb4af-130">Excluded locations are as follows:</span></span>

-   <span data-ttu-id="cb4af-131">HKEY \ _CURRENT \ _USER のレジストリキーと、ログオンしたユーザーが値を書き込むことができないファイル</span><span class="sxs-lookup"><span data-stu-id="cb4af-131">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="cb4af-132">HKEY \ _CURRENT \ _USER のレジストリキーと、Windows オペレーティングシステムのコア機能に関連付けられているファイル</span><span class="sxs-lookup"><span data-stu-id="cb4af-132">HKEY\_CURRENT\_USER registry keys and files that are associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="cb4af-133">HKEY \ _LOCAL \ _MACHINE hive に含まれているすべてのレジストリキーで、管理者権限が必要であり、ユーザーアカウント制御 (UAC) 契約の設定が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-133">All registry keys that are located in the HKEY\_LOCAL\_MACHINE hive, which requires administrator rights and might require to set a User Account Control (UAC) agreement</span></span>

-   <span data-ttu-id="cb4af-134">Program Files ディレクトリにあるファイル。管理者権限が必要であり、UAC 契約の設定が必要になる可能性があるファイル</span><span class="sxs-lookup"><span data-stu-id="cb4af-134">Files that are located in Program Files directories, which requires administrator rights and might require to set a UAC agreement</span></span>

-   <span data-ttu-id="cb4af-135">ユーザー名 \ \ \ [ユーザー名 \] の下にあるファイル。</span><span class="sxs-lookup"><span data-stu-id="cb4af-135">Files that are located under Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="cb4af-136">% Systemroot% にある Windows オペレーティングシステムファイル。管理者権限が必要であり、UAC 契約の設定が必要な可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-136">Windows operating system files that are located in %Systemroot%, which requires administrator rights and might require to set a UAC agreement</span></span>

<span data-ttu-id="cb4af-137">これらの場所に格納されているレジストリキーとファイルがアプリケーション設定を同期するために必要な場合は、除外された場所をテンプレートの作成プロセス中に手動で追加できます (ただし、HKEY \ _LOCAL \ _MACHINE ハイブのレジストリエントリは除きます)。</span><span class="sxs-lookup"><span data-stu-id="cb4af-137">If registry keys and files that are stored in these locations are required to synchronize application settings, you can manually add the excluded locations to the settings location template during the template creation process (except for registry entries in the HKEY\_LOCAL\_MACHINE hive).</span></span>

## <a href="" id="edit"></a><span data-ttu-id="cb4af-138">UE-V Generator を使用して設定場所テンプレートを編集する</span><span class="sxs-lookup"><span data-stu-id="cb4af-138">Edit Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="cb4af-139">UE-V Generator を使って、設定場所テンプレートを編集します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-139">Use the UE-V Generator to edit settings location templates.</span></span> <span data-ttu-id="cb4af-140">UE-V Generator を使用して、変更された設定がテンプレートに追加されると、そのテンプレート内のバージョン情報が自動的に更新され、企業に展開されている既存のテンプレートが正しく更新されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-140">When the revised settings are added to the templates by using the UE-V Generator, the version information within the template is automatically updated to ensure that any existing templates that are deployed in the enterprise are updated correctly.</span></span>

<span data-ttu-id="cb4af-141">**注** Ue-v 2 のジェネレーターを使って UE-V 1.0 テンプレートを編集する場合、テンプレートは自動的に UE-V 2 テンプレートに変換されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-141">**Note** If you edit a UE-V 1.0 template by using the UE-V 2 Generator, the template is automatically converted to a UE-V 2 template.</span></span> <span data-ttu-id="cb4af-142">UE-V 1.0 エージェントは、編集済みのテンプレートを使用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="cb4af-142">UE-V 1.0 Agents can no longer use the edited template.</span></span>

 

**<span data-ttu-id="cb4af-143">Ue-v のジェネレーターを使用して UE-V 設定の場所テンプレートを編集するには</span><span class="sxs-lookup"><span data-stu-id="cb4af-143">To edit a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="cb4af-144">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-144">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="cb4af-145">[**設定の場所テンプレートの編集] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-145">Click **Edit a settings location template**.</span></span>

3.  <span data-ttu-id="cb4af-146">最近使用したテンプレートの一覧で、編集するテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-146">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="cb4af-147">または、[**参照**] をクリックして設定テンプレートファイルを検索します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-147">Alternatively, click **Browse** to search for the settings template file.</span></span> <span data-ttu-id="cb4af-148">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-148">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="cb4af-149">設定テンプレートの**プロパティ**、**レジストリ**の場所、**ファイル**の場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-149">Review the **Properties**, **Registry** locations, and **Files** locations for the settings template.</span></span> <span data-ttu-id="cb4af-150">必要に応じて編集します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-150">Edit as required.</span></span>

    -   <span data-ttu-id="cb4af-151">[**プロパティ**] タブでは、次のプロパティを表示して編集できます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-151">On the **Properties** tab, you can view and edit the following properties:</span></span>

        -   <span data-ttu-id="cb4af-152">[ **Application name**]: プログラムファイルプロパティの説明に記載されているアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="cb4af-152">**Application name**: The application name that is written in the description of the program file properties.</span></span>

        -   <span data-ttu-id="cb4af-153">[ **Program name**]: プログラムファイルのプロパティから取得したプログラムの名前。</span><span class="sxs-lookup"><span data-stu-id="cb4af-153">**Program name**: The name of the program that is taken from the program file properties.</span></span> <span data-ttu-id="cb4af-154">通常、この名前には .exe ファイル名拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-154">This name usually has the .exe file name extension.</span></span>

        -   <span data-ttu-id="cb4af-155">[**製品バージョン**: アプリケーションの .exe ファイルの製品バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="cb4af-155">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="cb4af-156">このプロパティは、**ファイルバージョン**と共に、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-156">This property, together with the **File version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="cb4af-157">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-157">This property accepts a major version number.</span></span> <span data-ttu-id="cb4af-158">このプロパティが空の場合、[設定の場所] テンプレートは製品のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-158">If this property is empty, then the settings location template applies to all versions of the product.</span></span>

        -   <span data-ttu-id="cb4af-159">**ファイルのバージョン**: アプリケーションの .exe ファイルのファイルバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="cb4af-159">**File version**: The file version number of the .exe file of the application.</span></span> <span data-ttu-id="cb4af-160">このプロパティは**製品バージョン**と共に、設定場所テンプレートによって対象となるアプリケーションを特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-160">This property, along with the **Product version**, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="cb4af-161">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-161">This property accepts a major version number.</span></span> <span data-ttu-id="cb4af-162">このプロパティが空の場合は、設定の場所テンプレートがプログラムのすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-162">If this property is empty, the settings location template applies to all versions of the program.</span></span>

        -   <span data-ttu-id="cb4af-163">**テンプレート作成者の名前**(省略可能): 設定テンプレートの作成者の名前。</span><span class="sxs-lookup"><span data-stu-id="cb4af-163">**Template author name** (optional): The name of the settings template author.</span></span>

        -   <span data-ttu-id="cb4af-164">**テンプレート作成者のメール**(オプション): 設定場所テンプレートの作成者のメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="cb4af-164">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="cb4af-165">[**レジストリ**] タブには、設定場所テンプレートに含まれているレジストリの場所の**キー**と**範囲**が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-165">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="cb4af-166">[**タスク**] ドロップダウンメニューを使用して、レジストリの場所を編集できます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-166">You can edit the registry locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="cb4af-167">[タスク] メニューで、新しいキーの追加、既存のキーの名前または範囲の編集、キーの削除、キーが存在するレジストリの参照を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-167">In the Tasks menu, you can add new keys, edit the name or scope of existing keys, delete keys, and browse the registry in which the keys are located.</span></span> <span data-ttu-id="cb4af-168">レジストリのスコープを定義するときは、**すべての設定**のスコープを使用して、指定したキーの下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-168">When you define the scope for the registry, you can use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="cb4af-169">**すべての設定**と**サブ**キーを使用して、指定したキー、サブキー、サブキーの設定の下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-169">Use **All Settings** and **Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="cb4af-170">[**ファイル**] タブには、設定場所テンプレートに含まれているファイルの場所のファイルパスとファイルマスクが一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-170">The **Files** tab lists the file path and file mask of the file locations that are included in the settings location template.</span></span> <span data-ttu-id="cb4af-171">[**タスク**] ドロップダウンメニューを使用して、ファイルの場所を編集できます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-171">You can edit the file locations by using the **Tasks** drop-down menu.</span></span> <span data-ttu-id="cb4af-172">[ファイルの場所] の [**タスク**] メニューでは、新しいファイルまたはフォルダーの場所を追加したり、既存のファイルまたはフォルダーの範囲を編集したり、ファイルまたはフォルダーを削除したり、エクスプローラーで選択した場所を開くことができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-172">In the **Tasks** menu for file locations, you can add new files or folder locations, edit the scope of existing files or folders, delete files or folders, and open the selected location in Windows Explorer.</span></span> <span data-ttu-id="cb4af-173">指定したフォルダーにあるすべてのファイルを含めるには、ファイルのマスクを空のままにします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-173">To include all files in the specified folder, leave the file mask empty.</span></span>

5.  <span data-ttu-id="cb4af-174">[**保存**] をクリックして、設定場所テンプレートの変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-174">Click **Save** to save the changes to the settings location template.</span></span>

6.  <span data-ttu-id="cb4af-175">[**閉じる**] をクリックして、設定テンプレートウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-175">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="cb4af-176">UE-V Generator アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-176">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="cb4af-177">アプリケーションの設定場所テンプレートを編集したら、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-177">After you edit the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="cb4af-178">組織内の運用環境に配置する前に、ラボ環境で変更された設定場所のテンプレートを展開します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-178">Deploy the revised settings location template in a lab environment before you put it into production in the enterprise.</span></span>

**<span data-ttu-id="cb4af-179">設定場所テンプレートを手動で編集する方法</span><span class="sxs-lookup"><span data-stu-id="cb4af-179">How to manually edit a settings location template</span></span>**

1.  <span data-ttu-id="cb4af-180">設定場所テンプレート .xml ファイルのローカルコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-180">Create a local copy of the settings location template .xml file.</span></span> <span data-ttu-id="cb4af-181">UE-V settings location テンプレートは、アプリケーションストアの設定値が格納されている場所を識別する .xml ファイルです。</span><span class="sxs-lookup"><span data-stu-id="cb4af-181">UE-V settings location templates are .xml files that identify the locations where application store settings values.</span></span>

    <span data-ttu-id="cb4af-182">**注** 設定場所テンプレートは、テンプレート**ID**のために一意です。</span><span class="sxs-lookup"><span data-stu-id="cb4af-182">**Note** A settings location template is unique because of the template **ID**.</span></span> <span data-ttu-id="cb4af-183">テンプレートをコピーして .xml ファイルの名前を変更した場合、UE-V は、.xml ファイルのファイル名ではなく名前を確認するために、.xml ファイル内のテンプレート**ID**タグを読み取るために失敗します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-183">If you copy the template and rename the .xml file, template registration fails because UE-V reads the template **ID** tag in the .xml file to determine the name, not the file name of the .xml file.</span></span> <span data-ttu-id="cb4af-184">また、UE-V は、変更されたものがあるかどうかを確認する**バージョン**番号も読み取ります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-184">UE-V also reads the **Version** number to know if anything has changed.</span></span> <span data-ttu-id="cb4af-185">バージョン番号が大きい場合は、UE-V によってテンプレートが更新されます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-185">If the version number is higher, UE-V updates the template.</span></span>

     

2.  <span data-ttu-id="cb4af-186">XML エディターを使用して設定場所テンプレートファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-186">Open the settings location template file with an XML editor.</span></span>

3.  <span data-ttu-id="cb4af-187">設定場所テンプレートファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-187">Edit the settings location template file.</span></span> <span data-ttu-id="cb4af-188">すべての変更は、 [Settingslocationtempate](https://technet.microsoft.com/library/dn763947.aspx)で定義されている ue-v スキーマファイルに準拠している必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-188">All changes must conform to the UE-V schema file that is defined in [SettingsLocationTempate.xsd](https://technet.microsoft.com/library/dn763947.aspx).</span></span> <span data-ttu-id="cb4af-189">既定では、.xsd ファイルのコピーは、¥¥ programdata¥ microsoft templates にあります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-189">By default, a copy of the .xsd file is located in \\ProgramData\\Microsoft\\UEV\\Templates.</span></span>

4.  <span data-ttu-id="cb4af-190">設定場所テンプレートの**バージョン**番号をインクリメントします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-190">Increment the **Version** number for the settings location template.</span></span>

5.  <span data-ttu-id="cb4af-191">設定場所テンプレートファイルを保存してから、XML エディターを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-191">Save the settings location template file, and then close the XML editor.</span></span>

6.  <span data-ttu-id="cb4af-192">UE-V Generator を使用して、変更された設定場所テンプレートファイルを検証します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-192">Validate the modified settings location template file by using the UE-V Generator.</span></span>

7.  <span data-ttu-id="cb4af-193">クライアントコンピューター間で設定を同期できるようにするには、編集した UE-V 設定の場所テンプレートを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-193">You must register the edited UE-V settings location template before it can synchronize settings between client computers.</span></span> <span data-ttu-id="cb4af-194">テンプレートを登録するには、Windows PowerShell を開き、次のコマンドレットを実行し `update-uevtemplate [templatefilename]` ます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-194">To register a template, open Windows PowerShell, and then run the following cmdlet: `update-uevtemplate [templatefilename]`.</span></span> <span data-ttu-id="cb4af-195">次に、ファイルを設定のストレージカタログにコピーできます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-195">You can then copy the file to the settings storage catalog.</span></span> <span data-ttu-id="cb4af-196">ユーザーのコンピューター上の UE-V エージェントは、スケジュールされたタスクでスケジュールどおりに更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-196">The UE-V Agent on users’ computers should then update as scheduled in the scheduled task.</span></span>

## <a href="" id="validate"></a><span data-ttu-id="cb4af-197">UE-V Generator を使用して設定場所テンプレートを検証する</span><span class="sxs-lookup"><span data-stu-id="cb4af-197">Validate Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="cb4af-198">UE-V Generator を使わずに、XML エディターで設定場所テンプレートを作成または編集することができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-198">It is possible to create or edit settings location templates in an XML editor without using the UE-V Generator.</span></span> <span data-ttu-id="cb4af-199">その場合は、UE-V Generator を使って、新しい XML または変更された XML が、テンプレートに対して定義されているスキーマと一致するかどうかを検証できます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-199">If you do, you can use the UE-V Generator to validate that the new or revised XML matches the schema that has been defined for the template.</span></span>

**<span data-ttu-id="cb4af-200">Ue-v Generator を使用して UE-V 設定の場所テンプレートを検証するには</span><span class="sxs-lookup"><span data-stu-id="cb4af-200">To validate a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="cb4af-201">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-201">Click **Start**, point to **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="cb4af-202">[**設定の場所テンプレートの検証] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-202">Click **Validate a settings location template**.</span></span>

3.  <span data-ttu-id="cb4af-203">最近使用したテンプレートの一覧で、編集するテンプレートを選択します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-203">In the list of recently used templates, select the template to be edited.</span></span> <span data-ttu-id="cb4af-204">または、設定テンプレートファイルを**参照**することもできます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-204">Alternatively, you can **Browse** to the settings template file.</span></span> <span data-ttu-id="cb4af-205">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-205">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="cb4af-206">続行するには、[**検証**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cb4af-206">Click **Validate** to continue.</span></span>

5.  <span data-ttu-id="cb4af-207">[**閉じる**] をクリックして、設定テンプレートウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-207">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="cb4af-208">UE-V Generator アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-208">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="cb4af-209">アプリケーションの設定場所テンプレートを検証したら、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-209">After you validate the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="cb4af-210">ラボ環境にテンプレートを展開してから、エンタープライズの運用環境に配置します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-210">Deploy the template in a lab environment before you put it into a production environment in enterprise.</span></span>

## <a href="" id="share"></a><span data-ttu-id="cb4af-211">テンプレートギャラリーを使用して設定場所テンプレートを共有する</span><span class="sxs-lookup"><span data-stu-id="cb4af-211">Share Settings Location Templates with the Template Gallery</span></span>


<span data-ttu-id="cb4af-212">Microsoft User Experience Virtualization (UE-V) 2.0 テンプレートギャラリーでは、管理者が UE-V 設定の場所テンプレートを共有できます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-212">The Microsoft User Experience Virtualization (UE-V) 2.0 template gallery enables administrators to share their UE-V settings location templates.</span></span> <span data-ttu-id="cb4af-213">ギャラリーでは、他のユーザーが使用できるように設定場所テンプレートをアップロードすることができます。また、他のユーザーが作成したテンプレートをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-213">In the gallery, you can upload your settings location templates for other users to use, and you can download templates that other users have created.</span></span> <span data-ttu-id="cb4af-214">UE-V テンプレートギャラリーは、[ここ](https://go.microsoft.com/fwlink/p/?LinkId=246589)に記載されています。</span><span class="sxs-lookup"><span data-stu-id="cb4af-214">The UE-V template gallery is located on Microsoft TechNet [here](https://go.microsoft.com/fwlink/p/?LinkId=246589).</span></span>

<span data-ttu-id="cb4af-215">UE-V テンプレートギャラリーで設定場所テンプレートを共有する前に、個人情報や会社情報が含まれていないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="cb4af-215">Before you share a settings location template on the UE-V template gallery, ensure it does not contain any personal or company information.</span></span> <span data-ttu-id="cb4af-216">任意の XML ビューアーを使って、設定場所テンプレートファイルの内容を開いて表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cb4af-216">You can use any XML viewer to open and view the contents of a settings location template file.</span></span> <span data-ttu-id="cb4af-217">組織外のユーザーとテンプレートを共有するには、次のテンプレート値を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-217">The following template values should be reviewed before you share a template with anyone outside your company.</span></span>

-   <span data-ttu-id="cb4af-218">テンプレート作成者名–テンプレートの作成者名の一般的な非識別名を指定するか、テンプレートからこのデータを除外します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-218">Template Author Name – Specify a general, non-identifying name for the template author name or exclude this data from the template.</span></span>

-   <span data-ttu-id="cb4af-219">テンプレート作成者のメール–一般的な非識別テンプレート作成者のメールを指定するか、テンプレートからこのデータを除外します。</span><span class="sxs-lookup"><span data-stu-id="cb4af-219">Template Author Email – Specify a general, non-identifying template author email or exclude this data from the template.</span></span>

<span data-ttu-id="cb4af-220">UE-V ギャラリーからダウンロードした設定場所テンプレートを展開する前に、まず、テスト環境でアプリケーション設定が正しく同期されていることを確認するために、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cb4af-220">Before you deploy any settings location template that you have downloaded from the UE-V gallery, you should first test the template to ensure that the application settings synchronize settings correctly in a test environment.</span></span>






## <span data-ttu-id="cb4af-221">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cb4af-221">Related topics</span></span>


[<span data-ttu-id="cb4af-222">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="cb4af-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="cb4af-223">カスタムアプリケーションの UE-V 2. x の展開</span><span class="sxs-lookup"><span data-stu-id="cb4af-223">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





