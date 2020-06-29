---
title: 新しいアドオンまたはプラグイン アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)
description: 新しいアドオンまたはプラグイン アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 2c018215-66e5-4301-8481-159891a6b35b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5c5bc1e96ead819459cda3879127ebdaf94f0ee7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816707"
---
# <span data-ttu-id="5fd0d-103">新しいアドオンまたはプラグイン アプリケーションをシーケンス処理する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="5fd0d-103">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="5fd0d-104">次の手順を使用して、Application Virtualization (App-v) Sequencer を使用して、新しいアドオンまたはプラグインの仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-104">Use the following procedure to create a new add-on or plug-in virtual application package by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="5fd0d-105">アドオンまたはプラグインアプリケーションとは、アプリケーションの機能を拡張するアプリケーションのことです。たとえば、Microsoft Excel のプラグインなどです。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-105">An add-on or plug-in application is an application that extends the functionality of an application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="5fd0d-106">順序を指定できるアプリケーションの種類の詳細については、「どの[種類のアプリケーションをシーケンス処理するか (app-v 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-106">For more information about the types of applications you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="5fd0d-107">重要</span><span class="sxs-lookup"><span data-stu-id="5fd0d-107">Important</span></span>**  
<span data-ttu-id="5fd0d-108">次の手順を実行する前に、sequencer を実行しているコンピューターに親アプリケーションをローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-108">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="5fd0d-109">たとえば、Microsoft Excel のプラグインの順序を付ける場合は、sequencer を実行しているコンピューターに Microsoft Excel をローカルにインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-109">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="5fd0d-110">また、アプリケーションがターゲットコンピューターにインストールされているディレクトリに、親アプリケーションもインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-110">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="5fd0d-111">プラグインまたはアドオンを既存の仮想アプリケーションパッケージと共に使用する場合は、親仮想アプリケーションパッケージを作成したときに使用したのと同じ仮想アプリケーションドライブにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-111">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



<span data-ttu-id="5fd0d-112">既存の仮想アプリケーションパッケージを親アプリケーションとして使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-112">You can also use an existing virtual application package as the parent application.</span></span> <span data-ttu-id="5fd0d-113">既存の仮想アプリケーションパッケージを使用するには、新しいアドオンまたはプラグインを順序付けする前に、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-113">To use an existing virtual application package, use the following procedure before sequencing the new add-on or plug-in.</span></span>

1.  <span data-ttu-id="5fd0d-114">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-114">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="5fd0d-115">Sequencer を実行しているコンピューターに既存のパッケージを展開するには、[**ツール**] をクリックして [  /  **パッケージをローカルシステムに展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-115">To expand an existing package to the computer running the sequencer, click **Tools** / **Expand Package to Local System**.</span></span>

3.  <span data-ttu-id="5fd0d-116">展開するパッケージ (**sprj**ファイル) を参照して選び、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-116">Browse to and select the package (**.sprj** file) that you want to expand, and then click **Open**.</span></span> <span data-ttu-id="5fd0d-117">次の手順に進みます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-117">Continue with the following procedure.</span></span>

**<span data-ttu-id="5fd0d-118">新しいアドオンまたはプラグインアプリケーションを順序付けるには</span><span class="sxs-lookup"><span data-stu-id="5fd0d-118">To sequence a new add-on or plug-in application</span></span>**

1.  <span data-ttu-id="5fd0d-119">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-119">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="5fd0d-120">**新しいパッケージの作成ウィザード**を開始するには、[**新しい仮想アプリケーションパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-120">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="5fd0d-121">パッケージを作成するには、[**パッケージの作成 (既定)**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-121">To create the package, select **Create Package (default)**, and click then **Next**.</span></span>

3.  <span data-ttu-id="5fd0d-122">[**コンピューターの準備**] ページで、パッケージの作成に失敗する原因となる可能性のある問題、またはパッケージに不要なデータを含めることができる問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-122">On the **Prepare Computer** page, review the issues that might cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="5fd0d-123">続行する前に、発生する可能性があるすべての問題を解決することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-123">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="5fd0d-124">競合を修正した後、表示される情報を更新するには、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-124">After you have fixed the conflicts, to update the information displayed, click **Refresh**.</span></span> <span data-ttu-id="5fd0d-125">すべての潜在的な問題を解決したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-125">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="5fd0d-126">重要</span><span class="sxs-lookup"><span data-stu-id="5fd0d-126">Important</span></span>**  
    <span data-ttu-id="5fd0d-127">ウイルススキャンソフトウェアを無効にする必要がある場合は、sequencer を実行しているコンピューターをスキャンして、不要なファイルや悪意のあるファイルがパッケージに追加されないようにします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-127">If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="5fd0d-128">[**アプリケーションの種類**] ページで、[**アドオンまたはプラグイン**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-128">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

    <span data-ttu-id="5fd0d-129">順序を指定できるアプリケーションの種類の詳細については、「どの[種類のアプリケーションをシーケンス処理するか (app-v 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-129">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="5fd0d-130">[**インストーラーの選択**] ページで [**参照**] をクリックし、アドオンまたはプラグインのインストールファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-130">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="5fd0d-131">アプリケーションに関連付けられたインストーラーファイルがなく、インストール手順を手動で実行する場合は、[**このオプションを選択してカスタムインストールを実行**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-131">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6.  <span data-ttu-id="5fd0d-132">[**プライマリの選択**] ページで [**参照**] をクリックし、親アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-132">On the **Select Primary** page, click **Browse** and specify the parent application.</span></span>

    **<span data-ttu-id="5fd0d-133">重要</span><span class="sxs-lookup"><span data-stu-id="5fd0d-133">Important</span></span>**  
    <span data-ttu-id="5fd0d-134">インストールするアドオンまたはプラグインがサポートしている親アプリケーションがローカルにインストールされていない場合は、ここを停止して、sequencer を実行しているコンピューターにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-134">If the parent application that the add-on or plug-in you are installing is going to support has not been installed locally, stop here and install the application on the computer running the sequencer.</span></span> <span data-ttu-id="5fd0d-135">たとえば、 **Excel.exe**プログラムファイルは、Microsoft Excel プラグインのローカルにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-135">For example, the **Excel.exe** program file must be installed locally for a Microsoft Excel plug-in.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="5fd0d-136">[**パッケージ名**] ページで、パッケージに関連付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-136">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="5fd0d-137">パッケージに追加されるアプリケーションの目的とバージョンを識別するのに役立つ名前を使用します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-137">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="5fd0d-138">パッケージ名は、App-v 管理コンソールにも表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-138">The package name will also be displayed in the App-V management console.</span></span> <span data-ttu-id="5fd0d-139">**インストール場所**には、アプリケーションをインストールするアプリケーションの仮想化パスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-139">The **Installation Location** displays the Application Virtualization path where the application will be installed.</span></span> <span data-ttu-id="5fd0d-140">この場所を編集するには、[**編集 (詳細)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-140">To edit this location, select **Edit (Advanced)**.</span></span>

   **<span data-ttu-id="5fd0d-141">重要</span><span class="sxs-lookup"><span data-stu-id="5fd0d-141">Important</span></span>**  
   <span data-ttu-id="5fd0d-142">Application Virtualization パスの編集は、高度な構成タスクです。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-142">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="5fd0d-143">パスを変更することによる影響について十分に理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-143">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="5fd0d-144">ほとんどのアプリケーションでは、既定のパスを使うことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-144">For most applications, we recommend the default path.</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="5fd0d-145">**インストール**ページで、sequencer とアプリケーションインストーラーの準備ができたら、プラグインまたはアドインアプリケーションをインストールして、sequencer がインストールプロセスを監視できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-145">On the **Installation** page, when the sequencer and application installer are ready, install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="5fd0d-146">アプリケーションのインストールプロセスを使用して、インストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-146">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="5fd0d-147">インストールの一部として追加のインストールファイルを実行する必要がある場合は、[**実行**] をクリックして、追加のインストールファイルを見つけて実行します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-147">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="5fd0d-148">インストールが完了したら、[インストールを**完了**しました] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-148">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="5fd0d-149">[**インストールレポート**] ページで、順序付けした仮想アプリケーションパッケージに関する情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-149">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="5fd0d-150">[**追加情報**] に表示される情報について詳しくは、イベントをダブルクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-150">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="5fd0d-151">情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-151">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="5fd0d-152">仮想アプリケーションのインストールと構成が完了したら、[**カスタマイズ**] ページで [**今すぐ停止**] を選択し、この手順の手順14に進みます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-152">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="5fd0d-153">次の一覧の項目をカスタマイズするには、[**カスタマイズ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-153">If you want to customize any of the items in the following list, select **Customize**.</span></span>

    -   <span data-ttu-id="5fd0d-154">アプリケーションに関連付けられているファイルの種類の関連付けを編集します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-154">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="5fd0d-155">ストリーミング用の仮想パッケージを準備します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-155">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="5fd0d-156">ストリーミングにより、仮想アプリケーションパッケージがターゲットコンピューターで実行されるときのエクスペリエンスが向上しました。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-156">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="5fd0d-157">このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-157">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="5fd0d-158">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-158">Click **Next**.</span></span>

11. <span data-ttu-id="5fd0d-159">[**ショートカットの編集**] ページでは、パッケージ内のさまざまなアプリケーションに関連付けられるファイルの種類の関連付け (FTA) をオプションで構成できます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-159">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="5fd0d-160">新しい FTA を作成するには、左側のウィンドウで、カスタマイズするアプリケーションを選択して展開し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-160">To create a new FTA, in the left pane, select and expand the application that you want to customize, and then click **Add**.</span></span> <span data-ttu-id="5fd0d-161">[**ファイルの種類の関連付けの追加**] ダイアログボックスで、新しい FTA に必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-161">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="5fd0d-162">アプリケーションの下で、[**ショートカット**] を選択して、アプリケーションに関連付けられているショートカット情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-162">Under the application, select **Shortcuts** to review the shortcut information associated with an application.</span></span> <span data-ttu-id="5fd0d-163">[**場所**] ウィンドウで、アイコンファイル情報を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-163">In the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="5fd0d-164">既存の FTA を編集するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-164">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="5fd0d-165">FTA を削除するには、FTA を選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-165">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="5fd0d-166">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-166">Click **Next**.</span></span>

12. <span data-ttu-id="5fd0d-167">[**ストリーミング**] ページで、各プログラムを実行して、ターゲットコンピューターで最適化し、より効率的に実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-167">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="5fd0d-168">すべてのアプリケーションが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-168">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="5fd0d-169">すべてのアプリケーションが実行されたら、各アプリケーションを閉じて、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-169">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="5fd0d-170">注</span><span class="sxs-lookup"><span data-stu-id="5fd0d-170">Note</span></span>**  
   <span data-ttu-id="5fd0d-171">この手順の実行中にアプリケーションの読み込みを中止する場合は、 **[アプリケーションの起動**] ダイアログボックスで [**停止**] をクリックし、いずれかのチェックボックスをオンにし、[すべての**アプリケーションを停止**] または [**このアプリケーションのみを停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-171">If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select one of the check boxes, **Stop all applications** or **Stop this application only**.</span></span>



13. <span data-ttu-id="5fd0d-172">[**ターゲット OS** ] ページで、このパッケージを実行できるオペレーティングシステムを指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-172">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="5fd0d-173">環境でサポートされているすべてのオペレーティングシステムでこのパッケージを実行できるようにするには、[**このパッケージをすべてのオペレーティングシステムで実行できるよう**にする] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-173">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="5fd0d-174">特定のオペレーティングシステムでのみ実行されるようにこのパッケージを構成するには、[**次のオペレーティングシステムでのみこのパッケージを実行**する] チェックボックスをオンにして、このパッケージを実行できるオペレーティングシステムを選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-174">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="5fd0d-175">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-175">Click **Next**.</span></span>

14. <span data-ttu-id="5fd0d-176">[**パッケージの作成**] ページでパッケージを保存せずに変更するには、[**パッケージエディターを使用してパッケージを保存しないでパッケージを変更するには、続行する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-176">On the **Create Package** page, to modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="5fd0d-177">このオプションを選択すると、Sequencer コンソールでパッケージが開き、保存する前にパッケージを変更できるようになります。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-177">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="5fd0d-178">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-178">Click **Next**.</span></span>

   <span data-ttu-id="5fd0d-179">パッケージを直ちに保存するには、[既定で**パッケージを保存**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-179">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="5fd0d-180">必要に応じて、[**コメント**] を選択して、パッケージに関連付けられたコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-180">Optionally, select **Comments** to add comments that will be associated with the package.</span></span> <span data-ttu-id="5fd0d-181">コメントは、パッケージについてのバージョンとその他の情報を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-181">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="5fd0d-182">既定の**保存場所**も表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-182">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="5fd0d-183">既定の場所を変更するには、[**参照**] をクリックし、新しい場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-183">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="5fd0d-184">圧縮されていないパッケージサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-184">The uncompressed package size is displayed.</span></span> <span data-ttu-id="5fd0d-185">パッケージサイズが 4 GB (非圧縮) を超えていて、パッケージをターゲットコンピューターにストリーミングする予定の場合は、[**パッケージの圧縮**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-185">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="5fd0d-186">**[作成]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-186">Click **Create**.</span></span>

15. <span data-ttu-id="5fd0d-187">[**完了**] ページで、[成功した**仮想アプリケーションパッケージレポート**] ウィンドウに表示される情報を確認した後、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-187">On the **Completion** page, after you have reviewed the information that is displayed in the **Successful Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="5fd0d-188">[成功した**仮想アプリケーションパッケージレポート**] ウィンドウに表示される情報は、 **Reports.xml**という名前のファイルで、この手順の手順14で指定したディレクトリでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-188">The information displayed in the **Successful Virtual Application Package Report** pane is also available in the directory specified in step 14 of this procedure, in a file named **Reports.xml**.</span></span>

   <span data-ttu-id="5fd0d-189">このパッケージは、sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-189">The package is now available in the sequencer.</span></span> <span data-ttu-id="5fd0d-190">パッケージプロパティを編集するには、[ **\ [パッケージ名 \] の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-190">Click **Edit \[Package Name\]** to edit the package properties.</span></span> <span data-ttu-id="5fd0d-191">パッケージの変更の詳細については、「[既存の仮想アプリケーションパッケージを変更する (app-v 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-191">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

   **<span data-ttu-id="5fd0d-192">重要</span><span class="sxs-lookup"><span data-stu-id="5fd0d-192">Important</span></span>**  
   <span data-ttu-id="5fd0d-193">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="5fd0d-193">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



## <span data-ttu-id="5fd0d-194">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5fd0d-194">Related topics</span></span>


[<span data-ttu-id="5fd0d-195">Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="5fd0d-195">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="5fd0d-196">順序を指定するアプリケーションの種類を決定する方法 (App-v 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="5fd0d-196">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









