---
title: 既存の仮想アプリケーション パッケージを変更する方法 (App-V 4.6 SP1)
description: 既存の仮想アプリケーション パッケージを変更する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: f43a9927-4325-4b2d-829f-3068e4e84349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0e9d45a32afa240ce7f6fb2ee5dfbc51889c1fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817037"
---
# <span data-ttu-id="786af-103">既存の仮想アプリケーション パッケージを変更する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="786af-103">How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="786af-104">既存の仮想アプリケーションパッケージを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="786af-104">Use the following procedures to modify an existing virtual application package.</span></span> <span data-ttu-id="786af-105">以下の手順を使用して、次の操作を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="786af-105">You can use these procedures to:</span></span>

-   <span data-ttu-id="786af-106">既存の仮想アプリケーションパッケージの一部であるアプリケーションを更新します。</span><span class="sxs-lookup"><span data-stu-id="786af-106">Update an application that is part of an existing virtual application package.</span></span> <span data-ttu-id="786af-107">この処理を実行するには、このドキュメントの **「既存のアプリケーションパッケージのアプリケーションを更新するに**は」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="786af-107">To perform this task, use the procedure **"To update an application in an existing application package"** in this document.</span></span>

-   <span data-ttu-id="786af-108">既存の仮想アプリケーションパッケージに関連付けられているプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="786af-108">Modify the properties associated with an existing virtual application package.</span></span> <span data-ttu-id="786af-109">この処理を実行するには、このドキュメントの **「既存の仮想アプリケーションパッケージに関連するプロパティを変更するに**は」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="786af-109">To perform this task, use the procedure **"To modify the properties associated with an existing virtual application package"** in this document.</span></span>

-   <span data-ttu-id="786af-110">既存の仮想アプリケーションパッケージに新しいアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="786af-110">Add a new application to an existing virtual application package.</span></span> <span data-ttu-id="786af-111">この処理を実行するには、このドキュメントの **「既存の仮想アプリケーションパッケージに新しいアプリケーションを追加するに**は」の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="786af-111">To perform this task, use the procedure **"To add a new application to an existing virtual application package"** in this document.</span></span>

<span data-ttu-id="786af-112">仮想アプリケーションパッケージを変更するには、App-v Sequencer をインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="786af-112">You must have the App-V Sequencer installed to modify a virtual application package.</span></span> <span data-ttu-id="786af-113">App-v Sequencer のインストールの詳細については、「 [Sequencer のインストール方法 (app-v 4.6 SP1)](how-to-install-the-sequencer---app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="786af-113">For more information about installing the App-V Sequencer, see [How to Install the Sequencer (App-V 4.6 SP1)](how-to-install-the-sequencer---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="786af-114">既存の仮想アプリケーションパッケージのアプリケーションを更新するには</span><span class="sxs-lookup"><span data-stu-id="786af-114">To update an application in an existing virtual application package</span></span>**

1.  <span data-ttu-id="786af-115">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="786af-115">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="786af-116">App-v Sequencer で、[**既存の仮想アプリケーションパッケージの変更**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-116">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="786af-117">[**タスクの選択**] ページで、[**既存のパッケージのアプリケーションの更新**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-117">On the **Select Task** page, click **Update Application in Existing Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="786af-118">[**パッケージの選択**] ページで [**参照**] をクリックして、更新するアプリケーションが含まれている仮想アプリケーションパッケージを見つけ、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-118">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application that you want to update, and then click **Next**.</span></span>

5.  <span data-ttu-id="786af-119">[**コンピューターの準備**] ページで、アプリケーションの更新に失敗する原因となる可能性のある問題を確認します。または、アプリケーションの更新に不要なデータが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="786af-119">On the **Prepare Computer** page, review the issues that could cause the application update to fail, or for the application update to contain unnecessary data.</span></span> <span data-ttu-id="786af-120">続行する前に、発生する可能性があるすべての問題を解決することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="786af-120">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="786af-121">競合を修正した後、表示される情報を更新するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-121">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="786af-122">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-122">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="786af-123">**重要** ウイルススキャンソフトウェアを無効にする必要がある場合は、sequencer を実行しているコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-123">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files are added to the package.</span></span>

     

6.  <span data-ttu-id="786af-124">[**インストーラーの選択**] ページで [**参照**] をクリックし、アプリケーションの更新インストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="786af-124">On the **Select Installer** page, click **Browse** and specify the update installation file for the application.</span></span> <span data-ttu-id="786af-125">更新プログラムに関連するインストーラーファイルがなく、すべてのインストール手順を手動で実行する予定の場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-125">If the update does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="786af-126">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、アプリの更新プログラムをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-126">On the **Installation** page, when the sequencer and application installer are ready, install the application update so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="786af-127">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="786af-127">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="786af-128">インストールが完了したら、[インストールを**完了**しました] を選択します。</span><span class="sxs-lookup"><span data-stu-id="786af-128">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="786af-129">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-129">Click **Next**.</span></span>

    <span data-ttu-id="786af-130">**注** Sequencer は、sequencer を実行しているコンピューターに対するすべての変更とインストールを監視します。これには、シーケンスウィザードの外部で実行される変更とインストールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="786af-130">**Note** The sequencer monitors all changes and installations to the computer running the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="786af-131">[**インストールレポート**] ページで、更新した仮想アプリケーションに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="786af-131">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="786af-132">[**追加情報**] に表示される情報について詳しくは、イベントをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="786af-132">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="786af-133">情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-133">After you have reviewed the information, click **Next**.</span></span>

9.  <span data-ttu-id="786af-134">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-134">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="786af-135">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="786af-135">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="786af-136">すべてのアプリケーションが実行されたら、各アプリケーションを閉じて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-136">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="786af-137">**注** この手順の実行中にアプリケーションの読み込みを中止する場合は、 **[アプリケーションの起動**] ダイアログボックスで [**停止**] をクリックし、次のいずれかのオプションをクリックします。 [すべての**アプリケーションを停止**] または [**このアプリケーションを停止**する] は、必要に応じて設定します。</span><span class="sxs-lookup"><span data-stu-id="786af-137">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop**, and then click one of the following options, **Stop all applications** or **Stop this application only**, depending on what you want.</span></span>

     

10. <span data-ttu-id="786af-138">[**パッケージの作成**] ページでパッケージを保存せずに変更するには、[**パッケージエディターを使用してパッケージを保存せずにパッケージを変更**します] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="786af-138">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="786af-139">このオプションを選択すると、Sequencer コンソールのパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="786af-139">When you select this option, the package in the Sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="786af-140">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-140">Click **Next**.</span></span>

    <span data-ttu-id="786af-141">パッケージを直ちに保存するには、[既定で**パッケージを保存**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="786af-141">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="786af-142">パッケージに関連付けられる**コメント**(省略可能) を追加します。</span><span class="sxs-lookup"><span data-stu-id="786af-142">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="786af-143">コメントは、パッケージについてのバージョンとその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="786af-143">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="786af-144">既定の**保存場所**も表示されます。</span><span class="sxs-lookup"><span data-stu-id="786af-144">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="786af-145">既定の場所を変更するには、[**参照**] をクリックし、新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="786af-145">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="786af-146">圧縮されていないパッケージサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="786af-146">The uncompressed package size is displayed.</span></span> <span data-ttu-id="786af-147">パッケージサイズが 4 GB (非圧縮) を超えていて、パッケージをターゲットコンピューターにストリーミングする予定の場合は、[**パッケージの圧縮**] を選択し、[**作成**] をクリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="786af-147">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**, and then click **Create**.</span></span>

11. <span data-ttu-id="786af-148">[**完了**] ページで、[**閉じる**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="786af-148">On the **Completion** page, click **Close** to close the wizard.</span></span> <span data-ttu-id="786af-149">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="786af-149">The package is now available in the sequencer.</span></span>

**<span data-ttu-id="786af-150">既存の仮想アプリケーションパッケージに関連付けられているプロパティを変更するには</span><span class="sxs-lookup"><span data-stu-id="786af-150">To modify the properties associated with an existing virtual application package</span></span>**

1.  <span data-ttu-id="786af-151">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="786af-151">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="786af-152">App-v Sequencer で、[**既存の仮想アプリケーションパッケージの変更**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-152">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="786af-153">[**タスクの選択**] ページで [**パッケージの編集**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-153">On the **Select Task** page, click **Edit Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="786af-154">[**パッケージの選択**] ページで [**参照**] をクリックして、変更するアプリケーションのプロパティが含まれている仮想アプリケーションパッケージを見つけ、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-154">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application properties that you want to modify, and then click **Edit**.</span></span>

5.  <span data-ttu-id="786af-155">Sequencer コンソールでは、次のいずれかのタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="786af-155">In the Sequencer console, you can perform any of the following tasks:</span></span>

    -   <span data-ttu-id="786af-156">パッケージのプロパティを表示します。</span><span class="sxs-lookup"><span data-stu-id="786af-156">View package properties.</span></span>

    -   <span data-ttu-id="786af-157">パッケージの変更履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="786af-157">View package change history.</span></span>

    -   <span data-ttu-id="786af-158">関連付けられたパッケージファイルを表示します。</span><span class="sxs-lookup"><span data-stu-id="786af-158">View associated package files.</span></span>

    -   <span data-ttu-id="786af-159">レジストリ設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="786af-159">Edit registry settings.</span></span>

    -   <span data-ttu-id="786af-160">追加のパッケージ設定を確認します (オペレーティングシステムのファイルプロパティを除く)。</span><span class="sxs-lookup"><span data-stu-id="786af-160">Review additional package settings (except operating system file properties).</span></span>

    -   <span data-ttu-id="786af-161">関連付けられた Windows インストーラー (MSI) を作成します。</span><span class="sxs-lookup"><span data-stu-id="786af-161">Create an associated Windows Installer (MSI).</span></span>

    -   <span data-ttu-id="786af-162">OSD ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="786af-162">Modify OSD file.</span></span>

    -   <span data-ttu-id="786af-163">パッケージの圧縮と圧縮解除を行います。</span><span class="sxs-lookup"><span data-stu-id="786af-163">Compress and uncompress package.</span></span>

    -   <span data-ttu-id="786af-164">ファイルの種類の関連付けを追加します。</span><span class="sxs-lookup"><span data-stu-id="786af-164">Add file type associations.</span></span>

    -   <span data-ttu-id="786af-165">仮想化されたレジストリキーの状態 (上書きまたはマージ) を設定します。</span><span class="sxs-lookup"><span data-stu-id="786af-165">Set virtualized registry key state (override or merge).</span></span>

    -   <span data-ttu-id="786af-166">仮想化されたフォルダーの状態を設定します。</span><span class="sxs-lookup"><span data-stu-id="786af-166">Set virtualized folder state.</span></span>

    -   <span data-ttu-id="786af-167">仮想ファイルシステムのマッピングを編集します。</span><span class="sxs-lookup"><span data-stu-id="786af-167">Edit virtual file system mappings.</span></span>

6.  <span data-ttu-id="786af-168">パッケージプロパティの変更が完了したら、[**ファイル**の  /  **保存**] をクリックしてパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="786af-168">When you have finished modifying the package properties, click **File** / **Save** to save the package,.</span></span>

**<span data-ttu-id="786af-169">既存の仮想アプリケーションパッケージに新しいアプリケーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="786af-169">To add a new application to an existing virtual application package</span></span>**

1.  <span data-ttu-id="786af-170">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="786af-170">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="786af-171">App-v Sequencer で、[**既存の仮想アプリケーションパッケージの変更**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-171">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="786af-172">[**タスクの選択**] ページで、[**新しいアプリケーションの追加**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-172">On the **Select Task** page, click **Add New Application**, and then click **Next**.</span></span>

4.  <span data-ttu-id="786af-173">[**パッケージの選択**] ページで [**参照**] をクリックして、アプリケーションを追加する仮想アプリケーションパッケージを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-173">On the **Select Package** page, click **Browse** to locate the virtual application package that you want to add the application to, and then click **Next**.</span></span>

5.  <span data-ttu-id="786af-174">[**コンピューターの準備**] ページで、パッケージの作成に失敗する可能性のある問題を確認します。または、更新に不要なデータが含まれている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="786af-174">On the **Prepare Computer** page, review the issues that could cause the package creation to fail, or for the update to contain unnecessary data.</span></span> <span data-ttu-id="786af-175">続行する前に、発生する可能性があるすべての問題を解決することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="786af-175">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="786af-176">競合を修正した後、表示される情報を更新するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-176">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="786af-177">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-177">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="786af-178">**重要** ウイルススキャンソフトウェアを無効にする必要がある場合は、sequencer を実行しているコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-178">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>

     

6.  <span data-ttu-id="786af-179">[**インストーラーの選択**] ページで [**参照**] をクリックして、アプリケーションのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="786af-179">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="786af-180">アプリケーションに関連付けられたインストーラーファイルがなく、インストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-180">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="786af-181">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、アプリをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-181">On the **Installation** page, when the sequencer and application installer are ready, install the application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="786af-182">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="786af-182">If additional installation files must be run as part of the installation, click **Run**, and locate and run the additional installation files.</span></span> <span data-ttu-id="786af-183">インストールが完了したら、[インストールを**完了**しました] を選択します。</span><span class="sxs-lookup"><span data-stu-id="786af-183">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="786af-184">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-184">Click **Next**.</span></span> <span data-ttu-id="786af-185">[**フォルダーの参照**] ダイアログボックスで、アプリケーションをインストールするプライマリディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="786af-185">In the **Browse for Folder** dialog box, specify the primary directory where the application will be installed.</span></span> <span data-ttu-id="786af-186">これは新しい場所であり、仮想アプリケーションパッケージの既存のバージョンを上書きしないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="786af-186">This should be a new location so that you do not overwrite the existing version of the virtual application package.</span></span>

    <span data-ttu-id="786af-187">**注** Sequencer を実行しているコンピューターへのすべての変更とインストールは、sequencer によって監視されます。これには、シーケンスウィザードの外部で実行される変更とインストールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="786af-187">**Note** All changes and installations to the computer running the sequencer are monitored by the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="786af-188">[**ソフトウェアの構成**] ページで、必要に応じてパッケージに含まれるプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="786af-188">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="786af-189">この手順では、ターゲットコンピューターにパッケージを展開して実行する前に、アプリの実行に必要な関連付けられたすべてのライセンスまたは構成タスクを完了することができます。</span><span class="sxs-lookup"><span data-stu-id="786af-189">This step helps complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="786af-190">すべてのプログラムを同時に実行するには、1つ以上のプログラムを選択し、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-190">To run all the programs at the same time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="786af-191">特定のプログラムを実行するには、実行するプログラムを選択し、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-191">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="786af-192">必要な構成タスクを完了して、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="786af-192">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="786af-193">すべてのプログラムが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="786af-193">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="786af-194">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-194">Click **Next**.</span></span>

9.  <span data-ttu-id="786af-195">[**インストールレポート**] ページで、更新した仮想アプリケーションに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="786af-195">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="786af-196">[**追加情報**] に表示される情報について詳しくは、イベントをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="786af-196">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="786af-197">情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-197">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="786af-198">仮想アプリケーションのインストールと構成が完了したら、[**カスタマイズ**] ページで [**今すぐ停止**] を選択し、この手順の手順14に進みます。</span><span class="sxs-lookup"><span data-stu-id="786af-198">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="786af-199">次の一覧の項目をカスタマイズする場合は、[**ユーザー設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-199">If you want to customize any of the items in the following list, click **Customize**.</span></span>

    -   <span data-ttu-id="786af-200">アプリケーションに関連付けられているファイルの種類の関連付けを編集します。</span><span class="sxs-lookup"><span data-stu-id="786af-200">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="786af-201">ストリーミング用の仮想パッケージを準備します。</span><span class="sxs-lookup"><span data-stu-id="786af-201">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="786af-202">ストリーミングにより、仮想アプリケーションパッケージがターゲットコンピューターで実行されるときのエクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="786af-202">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    <span data-ttu-id="786af-203">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-203">Click **Next**.</span></span>

11. <span data-ttu-id="786af-204">[**ショートカットの編集**] ページでは、パッケージ内のさまざまなアプリケーションに関連付けられるファイルの種類の関連付け (FTA) をオプションで構成できます。</span><span class="sxs-lookup"><span data-stu-id="786af-204">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="786af-205">新しい FTA を作成するには、左側のウィンドウでカスタマイズするアプリケーションを選択して展開し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-205">To create a new FTA, select and expand the application that you want to customize in the left pane, and then click **Add**.</span></span> <span data-ttu-id="786af-206">[**ファイルの種類の関連付けの追加**] ダイアログボックスで、新しい FTA に必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="786af-206">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="786af-207">アプリケーションに関連付けられているショートカット情報を確認するには、アプリケーションの下にある [**ショートカット**] チェックボックスをオンにし、[**場所**] ウィンドウでアイコンファイル情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="786af-207">To review the shortcut information associated with an application, under the application, select the **Shortcuts** check box, and in the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="786af-208">既存の FTA を編集するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-208">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="786af-209">FTA を削除するには、FTA を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-209">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="786af-210">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-210">Click **Next**.</span></span>

12. <span data-ttu-id="786af-211">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="786af-211">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="786af-212">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="786af-212">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="786af-213">すべてのアプリケーションが実行されたら、各アプリケーションを閉じて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-213">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="786af-214">**注** この手順の実行中にアプリケーションの読み込みを中止する場合は、 **[アプリケーションの起動**] ダイアログボックスで [**停止**] をクリックし、必要に応じて、[すべての**アプリケーションを停止**する] または [**このアプリケーションのみ**を停止する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="786af-214">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select either the **Stop all applications** or the **Stop this application only** check box, depending on what you want.</span></span>

     

13. <span data-ttu-id="786af-215">[**パッケージの作成**] ページで、[パッケージ**エディターを使ってパッケージを保存せずにパッケージを変更**します] チェックボックスをオンにして、パッケージを保存せずに変更します。</span><span class="sxs-lookup"><span data-stu-id="786af-215">On the **Create Package** page, select the **Continue to modify package without saving using the package editor** check box, to modify the package without saving it.</span></span> <span data-ttu-id="786af-216">このオプションを選択すると、sequencer コンソールのパッケージが開き、保存する前にパッケージを変更することができます。</span><span class="sxs-lookup"><span data-stu-id="786af-216">When you select this option, the package in the sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="786af-217">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-217">Click **Next**.</span></span>

    <span data-ttu-id="786af-218">[**今すぐパッケージを保存**する] を選択して、パッケージを直ちに保存します。</span><span class="sxs-lookup"><span data-stu-id="786af-218">Select the default **Save the package now**, to save the package immediately.</span></span> <span data-ttu-id="786af-219">パッケージに関連付けられる**コメント**(省略可能) を追加します。</span><span class="sxs-lookup"><span data-stu-id="786af-219">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="786af-220">コメントは、パッケージについてのバージョンとその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="786af-220">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="786af-221">既定の**保存場所**も表示されます。</span><span class="sxs-lookup"><span data-stu-id="786af-221">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="786af-222">既定の場所を変更するには、[**参照**] をクリックし、新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="786af-222">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="786af-223">圧縮されていないパッケージサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="786af-223">The uncompressed package size is displayed.</span></span> <span data-ttu-id="786af-224">パッケージサイズが 4 GB (非圧縮) を超えていて、パッケージをターゲットコンピューターにストリーミングする予定の場合は、[**パッケージの圧縮**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="786af-224">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="786af-225">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-225">Click **Create**.</span></span>

14. <span data-ttu-id="786af-226">**[完了]** ページで、**[閉じる]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="786af-226">On the **Completion** page, click **Close**.</span></span> <span data-ttu-id="786af-227">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="786af-227">The package is now available in the sequencer.</span></span>

## <span data-ttu-id="786af-228">関連トピック</span><span class="sxs-lookup"><span data-stu-id="786af-228">Related topics</span></span>


[<span data-ttu-id="786af-229">Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="786af-229">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





