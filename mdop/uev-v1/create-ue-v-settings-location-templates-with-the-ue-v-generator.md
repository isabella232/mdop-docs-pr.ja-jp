---
title: UE-V Generator を使用して UE-V 設定場所テンプレートを作成する
description: UE-V Generator を使用して UE-V 設定場所テンプレートを作成する
author: dansimp
ms.assetid: b8e50e2f-0cc6-4f74-bb48-c471fefdc7d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ef7e3e5d00a95b9fcfc426207ce04f928cc0ebbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826644"
---
# <span data-ttu-id="d740e-103">UE-V Generator を使用して UE-V 設定場所テンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="d740e-103">Create UE-V Settings Location Templates with the UE-V Generator</span></span>


<span data-ttu-id="d740e-104">Microsoft User Experience Virtualization (UE-V) は、*設定場所テンプレート*を使って、ユーザーのコンピューター間でアプリケーションの設定をローミングします。</span><span class="sxs-lookup"><span data-stu-id="d740e-104">Microsoft User Experience Virtualization (UE-V) uses *settings location templates* to roam application settings between user computers.</span></span> <span data-ttu-id="d740e-105">一部の標準的な設定場所テンプレートは、ユーザーエクスペリエンスの仮想化に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d740e-105">Some standard settings location templates are included with User Experience Virtualization.</span></span> <span data-ttu-id="d740e-106">また、UE-V Generator を使用して、カスタム設定の場所テンプレートを作成、編集、または検証することもできます。</span><span class="sxs-lookup"><span data-stu-id="d740e-106">You can also create, edit, or validate custom settings location templates with the UE-V Generator.</span></span>

<span data-ttu-id="d740e-107">UE-V Generator は、アプリケーションがその設定を保存する場所を検出し、キャプチャするために、アプリケーションを監視します。</span><span class="sxs-lookup"><span data-stu-id="d740e-107">The UE-V Generator monitors an application to discover and capture the locations where the application stores its settings.</span></span> <span data-ttu-id="d740e-108">監視されるアプリケーションは、従来のアプリケーションである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d740e-108">The application that is being monitored must be a traditional application.</span></span> <span data-ttu-id="d740e-109">UE-V Generator は、次のアプリケーションの種類から設定場所テンプレートを作成できません。</span><span class="sxs-lookup"><span data-stu-id="d740e-109">The UE-V Generator cannot create a settings location template from the following application types:</span></span>

-   <span data-ttu-id="d740e-110">仮想化されたアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d740e-110">Virtualized applications</span></span>

-   <span data-ttu-id="d740e-111">ターミナルサービスを通じて提供されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="d740e-111">Application offered through terminal services</span></span>

-   <span data-ttu-id="d740e-112">Java アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d740e-112">Java applications</span></span>

-   <span data-ttu-id="d740e-113">Windows 8 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="d740e-113">Windows 8 applications</span></span>

<span data-ttu-id="d740e-114">**注** UE-V テンプレートは、仮想化されたアプリケーションまたはターミナルサービスアプリケーションから作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="d740e-114">**Note** UE-V templates cannot be created from virtualized applications or terminal services applications.</span></span> <span data-ttu-id="d740e-115">ただし、テンプレートを使用して同期した設定は、それらのアプリケーションに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="d740e-115">However, settings synchronized using the templates can be applied to those applications.</span></span> <span data-ttu-id="d740e-116">仮想デスクトップインフラストラクチャ (VDI) とターミナルサービスアプリケーションをサポートするテンプレートを作成するには、UE-V Generator を使用して、Windows Installer ファイル (.msi) バージョンのアプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="d740e-116">To create templates that support Virtual Desktop Infrastructure (VDI) and terminal services applications, open a Windows Installer File (.msi) version of the application with UE-V Generator.</span></span>

 

**<span data-ttu-id="d740e-117">除外された場所</span><span class="sxs-lookup"><span data-stu-id="d740e-117">Excluded Locations</span></span>**

<span data-ttu-id="d740e-118">検出プロセスでは、ユーザーのコンピューターまたは環境間で適切にローミングされないアプリケーションソフトウェアファイルが保存されている場所を除外します。</span><span class="sxs-lookup"><span data-stu-id="d740e-118">The discovery process excludes locations which commonly store application software files that do not roam well between user computers or environments.</span></span> <span data-ttu-id="d740e-119">以下は除外されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-119">The following are excluded:</span></span>

-   <span data-ttu-id="d740e-120">HKEY \ _CURRENT \ _USER のレジストリキーと、ログオンしたユーザーが値を書き込むことができないファイル</span><span class="sxs-lookup"><span data-stu-id="d740e-120">HKEY\_CURRENT\_USER registry keys and files to which the logged-on user cannot write values</span></span>

-   <span data-ttu-id="d740e-121">HKEY \ _CURRENT \ _USER のレジストリキーと、Windows オペレーティングシステムのコア機能に関連付けられているファイル</span><span class="sxs-lookup"><span data-stu-id="d740e-121">HKEY\_CURRENT\_USER registry keys and files associated with the core functionality of the Windows operating system</span></span>

-   <span data-ttu-id="d740e-122">HKEY \ _LOCAL \ _MACHINE ハイブにあるすべてのレジストリキー</span><span class="sxs-lookup"><span data-stu-id="d740e-122">All registry keys located in the HKEY\_LOCAL\_MACHINE hive</span></span>

-   <span data-ttu-id="d740e-123">Program Files ディレクトリにあるファイル</span><span class="sxs-lookup"><span data-stu-id="d740e-123">Files located in Program Files directories</span></span>

-   <span data-ttu-id="d740e-124">ユーザー (\ \ \ [ユーザー名 \]) にあるファイル (ユーザー名 \ \)</span><span class="sxs-lookup"><span data-stu-id="d740e-124">Files located in Users \\ \[User name\] \\ AppData \\ LocalLow</span></span>

-   <span data-ttu-id="d740e-125">% Systemroot% にある Windows オペレーティングシステムファイル</span><span class="sxs-lookup"><span data-stu-id="d740e-125">Windows operating system files located in %systemroot%</span></span>

<span data-ttu-id="d740e-126">これらの除外した場所に保存されているレジストリキーとファイルがアプリケーション設定をローミングするために必要な場合は、管理者はテンプレートの作成プロセス中に場所を設定場所テンプレートに手動で追加することができます。</span><span class="sxs-lookup"><span data-stu-id="d740e-126">If registry keys and files stored in these excluded locations are required in order to roam application settings, administrators can manually add the locations to the settings location template during the template creation process.</span></span>

## <span data-ttu-id="d740e-127">UE-V のテンプレートを作成する</span><span class="sxs-lookup"><span data-stu-id="d740e-127">Create UE-V templates</span></span>


<span data-ttu-id="d740e-128">UE-V Generator を使って、基幹業務アプリケーションまたはその他のアプリケーションの設定場所テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="d740e-128">Use the UE-V Generator to create settings location templates for line-of-business applications or other applications.</span></span> <span data-ttu-id="d740e-129">アプリケーションのテンプレートが作成されたら、そのテンプレートをコンピューターに展開して、ユーザーがそのアプリケーションの設定を移動できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="d740e-129">After the template for an application is created, you can deploy the template to computers so users can roam the settings for that application.</span></span>

**<span data-ttu-id="d740e-130">Ue-v Generator を使用して UE-V 設定の場所テンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="d740e-130">To create a UE-V settings location template with the UE-V Generator</span></span>**

1.  <span data-ttu-id="d740e-131">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **microsoft user Experience Virtualization**]、[ **microsoft user experience virtualization Generator**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="d740e-131">Click **Start**, click **All Programs**, click **Microsoft User Experience Virtualization**, and then click **Microsoft User Experience Virtualization Generator**.</span></span>

2.  <span data-ttu-id="d740e-132">[**設定場所テンプレートの作成] を**クリックします。</span><span class="sxs-lookup"><span data-stu-id="d740e-132">Click **Create a settings location template**.</span></span>

3.  <span data-ttu-id="d740e-133">アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="d740e-133">Specify the application.</span></span> <span data-ttu-id="d740e-134">設定場所テンプレートを作成するアプリケーション (.exe) またはアプリケーションショートカット (.lnk) のファイルパスを参照します。</span><span class="sxs-lookup"><span data-stu-id="d740e-134">Browse to the file path of the application (.exe) or the application shortcut (.lnk) for which you want to create a settings location template.</span></span> <span data-ttu-id="d740e-135">必要に応じて、コマンドライン引数 (存在する場合) と作業ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="d740e-135">Specify the command line arguments, if any, and working directory, if any.</span></span> <span data-ttu-id="d740e-136">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d740e-136">Click **Next** to continue.</span></span>

    <span data-ttu-id="d740e-137">**注** アプリケーションが起動する前に、システムによって**ユーザーアカウント制御**のプロンプトが表示されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-137">**Note** Before the application is started, the system displays a prompt for **User Account Control**.</span></span> <span data-ttu-id="d740e-138">レジストリと、アプリケーションが設定を保存するために使用するファイルの場所を監視するには、アクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="d740e-138">Permission is required to monitor the registry and file locations that the application uses to store settings.</span></span>

     

4.  <span data-ttu-id="d740e-139">アプリケーションが起動したら、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d740e-139">After the application starts, close the application.</span></span> <span data-ttu-id="d740e-140">UE-V Generator は、アプリケーションの設定が保存されている場所を記録します。</span><span class="sxs-lookup"><span data-stu-id="d740e-140">The UE-V Generator records the locations where the application stores its settings.</span></span>

5.  <span data-ttu-id="d740e-141">処理が完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d740e-141">After the process is complete, click **Next** to continue.</span></span>

6.  <span data-ttu-id="d740e-142">このアプリケーションでローミングする適切なレジストリ設定の場所と設定ファイルの場所の横にあるチェックボックスを確認して選択します。</span><span class="sxs-lookup"><span data-stu-id="d740e-142">Review and select the check boxes next to the appropriate registry settings locations and settings file locations to roam for this application.</span></span> <span data-ttu-id="d740e-143">この一覧には、設定場所に関する次の2つのカテゴリが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d740e-143">The list includes the following two categories for settings locations:</span></span>

    -   <span data-ttu-id="d740e-144">**標準**: HKEY \ _CURRENT \ _USER キーの下にあるレジストリに保存されているアプリケーション設定、または \\**ユーザー** \ \ \ [ユーザー名 \] **\ \ の**ファイルフォルダーの下にあり  \\  **Roaming**ます。</span><span class="sxs-lookup"><span data-stu-id="d740e-144">**Standard**: Application settings that are stored in the registry under the HKEY\_CURRENT\_USER keys or in the file folders under \\ **Users** \\ \[User name\] \\ **AppData** \\ **Roaming**.</span></span> <span data-ttu-id="d740e-145">UE-V Generator では、これらの設定が既定で含まれています。</span><span class="sxs-lookup"><span data-stu-id="d740e-145">The UE-V Generator includes these settings by default.</span></span>

    -   <span data-ttu-id="d740e-146">**非標準**: 設定データストレージのベストプラクティスで指定された場所の外側に保存されているアプリケーション設定 (オプション)。</span><span class="sxs-lookup"><span data-stu-id="d740e-146">**Nonstandard**: Application settings that are stored outside the locations specified in the best practices for settings data storage (optional).</span></span> <span data-ttu-id="d740e-147">これには、**ユーザー** \ \ \ [ユーザー名 \] \ \ **AppData**ローカルのファイルとフォルダーが含ま  \\  **Local**れます。</span><span class="sxs-lookup"><span data-stu-id="d740e-147">These include files and folders under **Users** \\ \[User name\] \\ **AppData** \\ **Local**.</span></span> <span data-ttu-id="d740e-148">これらの場所を確認して、設定場所テンプレートに含めるかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="d740e-148">Review these locations to determine whether to include them in the settings location template.</span></span> <span data-ttu-id="d740e-149">[場所] チェックボックスをオンにして追加します。</span><span class="sxs-lookup"><span data-stu-id="d740e-149">Select the locations check boxes to include them.</span></span>

    <span data-ttu-id="d740e-150">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d740e-150">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="d740e-151">設定場所テンプレートの**プロパティ**、**レジストリ**の場所、**ファイル**の場所を確認して編集します。</span><span class="sxs-lookup"><span data-stu-id="d740e-151">Review and edit any **Properties**, **Registry** locations, and **Files** locations for the settings location template.</span></span>

    -   <span data-ttu-id="d740e-152">[**プロパティ**] タブで、次のプロパティを編集します。</span><span class="sxs-lookup"><span data-stu-id="d740e-152">Edit the following properties on the **Properties** tab:</span></span>

        -   <span data-ttu-id="d740e-153">[ **Application name**]: program files プロパティの説明で書かれたアプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="d740e-153">**Application Name**: The application name written in the description of the program files properties.</span></span>

        -   <span data-ttu-id="d740e-154">[ **Program name**]: プログラムファイルのプロパティから取得したプログラムの名前です。</span><span class="sxs-lookup"><span data-stu-id="d740e-154">**Program name**: The name of the program taken from the program file properties.</span></span> <span data-ttu-id="d740e-155">通常、この名前には .exe 拡張子が付きます。</span><span class="sxs-lookup"><span data-stu-id="d740e-155">This name usually has the .exe extension.</span></span>

        -   <span data-ttu-id="d740e-156">[**製品バージョン**: アプリケーションの .exe ファイルの製品バージョン番号。</span><span class="sxs-lookup"><span data-stu-id="d740e-156">**Product version**: The product version number of the .exe file of the application.</span></span> <span data-ttu-id="d740e-157">このプロパティは、ファイルバージョンと組み合わせて、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d740e-157">This property, in conjunction with the File version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="d740e-158">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d740e-158">This property accepts a major version number.</span></span> <span data-ttu-id="d740e-159">このプロパティが空の場合、設定の場所テンプレートは製品のすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-159">If this property is empty, the settings location template will apply to all versions of the product.</span></span>

        -   <span data-ttu-id="d740e-160">[ **File version**: application の the.exe ファイルのファイルバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="d740e-160">**File version**: The file version number of the.exe file of the application.</span></span> <span data-ttu-id="d740e-161">このプロパティは製品バージョンと組み合わせて、設定場所テンプレートのターゲットとなるアプリケーションを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d740e-161">This property, in conjunction with the Product version, helps determine which applications are targeted by the settings location template.</span></span> <span data-ttu-id="d740e-162">このプロパティは、メジャーバージョン番号を受け取ります。</span><span class="sxs-lookup"><span data-stu-id="d740e-162">This property accepts a major version number.</span></span> <span data-ttu-id="d740e-163">このプロパティが空の場合は、設定の場所テンプレートがプログラムのすべてのバージョンに適用されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-163">If this property is empty, the settings location template will apply to all versions of the program.</span></span>

        -   <span data-ttu-id="d740e-164">**テンプレート作成者の名前**(省略可能): 設定場所テンプレートの作成者の名前。</span><span class="sxs-lookup"><span data-stu-id="d740e-164">**Template author name** (optional): The name of the settings location template author.</span></span>

        -   <span data-ttu-id="d740e-165">**テンプレート作成者のメール**(オプション): 設定場所テンプレートの作成者のメールアドレス。</span><span class="sxs-lookup"><span data-stu-id="d740e-165">**Template author email** (optional): The email address of the settings location template author.</span></span>

    -   <span data-ttu-id="d740e-166">[**レジストリ**] タブには、設定場所テンプレートに含まれているレジストリの場所の**キー**と**範囲**が一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-166">The **Registry** tab lists the **Key** and **Scope** of the registry locations that are included in the settings location template.</span></span> <span data-ttu-id="d740e-167">[**タスク**] ドロップダウンメニューを使用して、レジストリの場所を編集します。</span><span class="sxs-lookup"><span data-stu-id="d740e-167">Edit the registry locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="d740e-168">タスクには、新しいキーの追加、既存のキーの名前または範囲の編集、キーの削除、キーが配置されているレジストリの参照が含まれます。</span><span class="sxs-lookup"><span data-stu-id="d740e-168">Tasks include adding new keys, editing the name or scope of existing keys, deleting keys, and browsing the registry where the keys are located.</span></span> <span data-ttu-id="d740e-169">すべての**設定**のスコープを使用して、指定したキーの下にすべてのレジストリ設定を追加します。</span><span class="sxs-lookup"><span data-stu-id="d740e-169">Use the **All Settings** scope to include all the registry settings under the specified key.</span></span> <span data-ttu-id="d740e-170">すべての**設定とサブ**キーを使用して、指定したキー、サブキー、サブキーの設定の下にすべてのレジストリ設定を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="d740e-170">Use the **All Settings and Subkeys** to include all the registry settings under the specified key, subkeys, and subkey settings.</span></span>

    -   <span data-ttu-id="d740e-171">[**ファイル**] タブには、設定場所テンプレートに含まれているファイルの場所のファイルパスとファイルマスクの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d740e-171">The **Files** tab lists the file path and file mask of the file locations included in the settings location template.</span></span> <span data-ttu-id="d740e-172">[**タスク**] ドロップダウンメニューを使用して、ファイルの場所を編集します。</span><span class="sxs-lookup"><span data-stu-id="d740e-172">Edit the file locations by use of the **Tasks** drop-down menu.</span></span> <span data-ttu-id="d740e-173">ファイルの場所のタスクには、新しいファイルまたはフォルダーの場所の追加、既存のファイルまたはフォルダーの範囲の編集、ファイルまたはフォルダーの削除、選択した場所を Windows エクスプローラーで開くなどがあります。</span><span class="sxs-lookup"><span data-stu-id="d740e-173">Tasks for file locations include adding new files or folder locations, editing the scope of existing files or folders, deleting files or folders, and opening the selected location in Windows Explorer.</span></span> <span data-ttu-id="d740e-174">指定したフォルダー内のすべてのファイルを含めるには、[ファイルマスク] を空のままにします。</span><span class="sxs-lookup"><span data-stu-id="d740e-174">Leave the file mask empty to include all files in the specified folder.</span></span>

8.  <span data-ttu-id="d740e-175">[**作成**] をクリックして、設定場所テンプレートをコンピューターに保存します。</span><span class="sxs-lookup"><span data-stu-id="d740e-175">Click **Create** and save the settings location template on the computer.</span></span>

9.  <span data-ttu-id="d740e-176">[**閉じる**] をクリックして、設定テンプレートウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="d740e-176">Click **Close** to close the Settings Template Wizard.</span></span> <span data-ttu-id="d740e-177">UE-V Generator アプリケーションを終了します。</span><span class="sxs-lookup"><span data-stu-id="d740e-177">Exit the UE-V Generator application.</span></span>

    <span data-ttu-id="d740e-178">アプリケーションの設定場所テンプレートを作成したら、テンプレートをテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d740e-178">After you have created the settings location template for an application, you should test the template.</span></span> <span data-ttu-id="d740e-179">ラボ環境にテンプレートを展開してから、エンタープライズで実働環境に配置します。</span><span class="sxs-lookup"><span data-stu-id="d740e-179">Deploy the template in a lab environment before putting it into production in the enterprise.</span></span>

## <span data-ttu-id="d740e-180">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d740e-180">Related topics</span></span>


[<span data-ttu-id="d740e-181">カスタム UE-V テンプレートと UE-V Generator の操作</span><span class="sxs-lookup"><span data-stu-id="d740e-181">Working with Custom UE-V Templates and the UE-V Generator</span></span>](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)

[<span data-ttu-id="d740e-182">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="d740e-182">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





