---
title: APP-V パッケージ アクセラレータを使用して仮想アプリケーション パッケージを作成する方法
description: APP-V パッケージ アクセラレータを使用して仮想アプリケーション パッケージを作成する方法
author: dansimp
ms.assetid: eae1e4f8-f14f-4bc8-9867-052561c37297
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 15376ae52a19b2d220f9ea0031f3ad5649ca487d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814274"
---
# <span data-ttu-id="b9fc6-103">APP-V パッケージ アクセラレータを使用して仮想アプリケーション パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="b9fc6-103">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>


**<span data-ttu-id="b9fc6-104">重要</span><span class="sxs-lookup"><span data-stu-id="b9fc6-104">Important</span></span>**  
<span data-ttu-id="b9fc6-105">App-v 5.1 Sequencer は、パッケージアクセラレータの作成に使用するソフトウェアアプリケーションのライセンス権限を付与しません。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-105">The App-V 5.1 Sequencer does not grant any license rights to the software application that you use to create the Package Accelerator.</span></span> <span data-ttu-id="b9fc6-106">使用しているアプリケーションのすべてのエンドユーザーライセンス条項を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-106">You must abide by all end user license terms for the application that you use.</span></span> <span data-ttu-id="b9fc6-107">ソフトウェアアプリケーションのライセンス条項によって、App-v 5.1 Sequencer でパッケージアクセラレータを作成できるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-107">It is your responsibility to make sure that the software application’s license terms allow you to create a Package Accelerator with the App-V 5.1 Sequencer.</span></span>



<span data-ttu-id="b9fc6-108">次の手順を使用して、App-v 5.1 パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-108">Use the following procedure to create a virtual application package with the App-V 5.1 Package Accelerator.</span></span>

**<span data-ttu-id="b9fc6-109">注</span><span class="sxs-lookup"><span data-stu-id="b9fc6-109">Note</span></span>**  
<span data-ttu-id="b9fc6-110">この手順を始める前に、アプリ-V 5.1 Sequencer を実行しているコンピューターに、必要なパッケージアクセラレータをローカルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-110">Before you start this procedure, copy the required Package Accelerator locally to the computer that runs the App-V 5.1 Sequencer.</span></span> <span data-ttu-id="b9fc6-111">また、Sequencer を実行しているコンピューターのローカルディレクトリに、パッケージの必要なすべてのインストールファイルをコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-111">You should also copy all required installation files for the package to a local directory on the computer that runs the Sequencer.</span></span> <span data-ttu-id="b9fc6-112">このディレクトリは、この手順の手順5で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-112">This is the directory that you have to specify in step 5 of this procedure.</span></span>



**<span data-ttu-id="b9fc6-113">App-v 5.1 パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="b9fc6-113">To create a virtual application package with an App-V 5.1 Package Accelerator</span></span>**

1.  <span data-ttu-id="b9fc6-114">App-v 5.1 sequencer を実行しているコンピューターで app-v の sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-114">To start the App-V Sequencer, on the computer that runs the App-V 5.1 Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="b9fc6-115">**新しいパッケージの作成ウィザード**を開始するには、[**新しい仮想アプリケーションパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-115">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="b9fc6-116">パッケージを作成するには、[**パッケージアクセラレータを使用してパッケージを作成**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-116">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3.  <span data-ttu-id="b9fc6-117">新しい仮想アプリケーションパッケージの作成に使用するパッケージアクセラレータを指定するには、[**パッケージアクセラレータの選択**] ページの [**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-117">To specify the package accelerator that will be used to create the new virtual application package, click **Browse** on the **Select Package Accelerator** page.</span></span> <span data-ttu-id="b9fc6-118">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-118">Click **Next**.</span></span>

    **<span data-ttu-id="b9fc6-119">重要</span><span class="sxs-lookup"><span data-stu-id="b9fc6-119">Important</span></span>**  
    <span data-ttu-id="b9fc6-120">パッケージアクセラレータの発行元を検証できず、有効なデジタル署名が含まれていない場合は、[**実行**] をクリックする前に、パッケージアクセラレータのソースを信頼していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-120">If the publisher of the package accelerator cannot be verified and does not contain a valid digital signature, then before you click **Run**, you must confirm that you trust the source of the package accelerator.</span></span> <span data-ttu-id="b9fc6-121">[**セキュリティの警告**] ダイアログボックスで選択を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-121">Confirm your choice in the **Security Warning** dialog box.</span></span>



4.  <span data-ttu-id="b9fc6-122">[**ガイダンス**] ページで、情報ウィンドウに表示される発行のガイダンス情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-122">On the **Guidance** page, review the publishing guidance information that is displayed in the information pane.</span></span> <span data-ttu-id="b9fc6-123">この情報は、パッケージアクセラレータの作成時に追加され、パッケージの作成と公開の方法についてのガイダンスが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-123">This information was added when the Package Accelerator was created and it contains guidance about how to create and publish the package.</span></span> <span data-ttu-id="b9fc6-124">ガイダンス情報をテキスト (.txt) ファイルにエクスポートするには、[**エクスポート**] をクリックし、ファイルを保存する場所を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-124">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5.  <span data-ttu-id="b9fc6-125">[**インストールファイルの選択**] ページで、[**新しいフォルダー**の作成] をクリックして、パッケージに必要なすべてのインストールファイルを含むローカルフォルダーを作成し、フォルダーを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-125">On the **Select Installation Files** page, click **Make New Folder** to create a local folder that contains all required installation files for the package, and specify where the folder should be saved.</span></span> <span data-ttu-id="b9fc6-126">フォルダーに割り当てる名前も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-126">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="b9fc6-127">必要なインストールファイルをすべて指定した場所にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-127">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="b9fc6-128">インストールファイルを含むフォルダーが、Sequencer を実行しているコンピューターに既に存在する場合は、[**参照**] をクリックして、フォルダーを選びます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-128">If the folder that contains the installation files already exists on the computer that runs the Sequencer, click **Browse** to select the folder.</span></span>

    <span data-ttu-id="b9fc6-129">または、このコンピューター上のディレクトリにインストールファイルを既にコピーしている場合は、[**新しいフォルダーの作成**] をクリックし、インストールファイルが保存されているフォルダーを参照して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-129">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

    **<span data-ttu-id="b9fc6-130">注</span><span class="sxs-lookup"><span data-stu-id="b9fc6-130">Note</span></span>**  
    <span data-ttu-id="b9fc6-131">次の種類のサポートされているインストールファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-131">You can specify the following types of supported installation files:</span></span>

    -   <span data-ttu-id="b9fc6-132">Windows インストーラーファイル (**.msi**)</span><span class="sxs-lookup"><span data-stu-id="b9fc6-132">Windows Installer files (**.msi**)</span></span>

    -   <span data-ttu-id="b9fc6-133">キャビネットファイル (.cab)</span><span class="sxs-lookup"><span data-stu-id="b9fc6-133">Cabinet files (.cab)</span></span>

    -   <span data-ttu-id="b9fc6-134">ファイル名拡張子が .zip の圧縮されたファイル</span><span class="sxs-lookup"><span data-stu-id="b9fc6-134">Compressed files with a .zip file name extension</span></span>

    -   <span data-ttu-id="b9fc6-135">実際のアプリケーションファイル</span><span class="sxs-lookup"><span data-stu-id="b9fc6-135">The actual application files</span></span>

    <span data-ttu-id="b9fc6-136">次の種類のファイルはサポートされていません。 **.msp**および **.exe**ファイル。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-136">The following file types are not supported: **.msp** and **.exe** files.</span></span> <span data-ttu-id="b9fc6-137">**.Exe**ファイルを指定した場合は、インストールファイルを手動で抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-137">If you specify an **.exe** file, you must extract the installation files manually.</span></span>



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. <span data-ttu-id="b9fc6-138">[**パッケージ名**] ページで、パッケージに関連付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-138">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="b9fc6-139">指定した名前は、App-v 管理コンソールでパッケージを識別します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-139">The name that you specify identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="b9fc6-140">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-140">Click **Next**.</span></span>

7. <span data-ttu-id="b9fc6-141">[**パッケージの作成**] ページで、パッケージに関連付けられるコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-141">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="b9fc6-142">コメントには、作成しているパッケージについての識別情報が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-142">The comments should contain identifying information about the package that you are creating.</span></span> <span data-ttu-id="b9fc6-143">パッケージが作成された場所を確認するには、[**保存場所**] に表示される情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-143">To confirm the location where the package is created, review the information that is displayed in **Save Location**.</span></span> <span data-ttu-id="b9fc6-144">パッケージを圧縮するには、[**パッケージの圧縮**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-144">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="b9fc6-145">パッケージがネットワーク上でストリーミングされる場合、またはパッケージサイズが 4 GB を超える場合は、[**パッケージの圧縮**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-145">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="b9fc6-146">パッケージを作成するには、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-146">To create the package, click **Create**.</span></span> <span data-ttu-id="b9fc6-147">パッケージが作成されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-147">After the package is created, click **Next**.</span></span>

8. <span data-ttu-id="b9fc6-148">[**ソフトウェアの構成**] ページで、パッケージに含まれているアプリケーションを Sequencer で構成できるようにするには、[**ソフトウェアの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-148">On the **Configure Software** page, to enable the Sequencer to configure the applications that are contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="b9fc6-149">この手順では、ターゲットコンピューターでアプリケーションを実行するために必要な、関連付けられたすべてのタスクを構成できます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-149">In this step you can configure any associated tasks that must be completed in order to run the application on the target computers.</span></span> <span data-ttu-id="b9fc6-150">たとえば、関連付けられているライセンス契約を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-150">For example, you can configure any associated license agreements.</span></span>

   <span data-ttu-id="b9fc6-151">[ソフトウェアの**構成**] を選択した場合、この手順の一部として、Sequencer を使用して次の項目を構成できます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-151">If you select **Configure Software**, the following items can be configured using the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="b9fc6-152">**パッケージを読み込み**ます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-152">**Load Package**.</span></span> <span data-ttu-id="b9fc6-153">Sequencer は、パッケージに関連付けられているファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-153">The Sequencer loads the files that are associated with the package.</span></span> <span data-ttu-id="b9fc6-154">パッケージのデコードには、数秒から1時間かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-154">It can take several seconds to an hour to decode the package.</span></span>

   -   <span data-ttu-id="b9fc6-155">**各プログラムを実行**します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-155">**Run Each Program**.</span></span> <span data-ttu-id="b9fc6-156">必要に応じて、パッケージに含まれているプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-156">Optionally run the programs that are contained in the package.</span></span> <span data-ttu-id="b9fc6-157">この手順は、対象のコンピューターにパッケージを展開して実行する前に、アプリの実行に必要な関連するすべてのライセンスまたは構成タスクを完了するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-157">This step is helpful to complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="b9fc6-158">一度にすべてのプログラムを実行するには、1つ以上のプログラムを選択し、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-158">To run all the programs at once, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="b9fc6-159">特定のプログラムを実行するには、実行するプログラムを選択し、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-159">To run specific programs, select the program or programs that you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="b9fc6-160">必要な構成タスクを完了して、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="b9fc6-161">すべてのプログラムが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="b9fc6-162">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-162">Click **Next**.</span></span>

   -   <span data-ttu-id="b9fc6-163">**パッケージを保存**します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-163">**Save Package**.</span></span> <span data-ttu-id="b9fc6-164">Sequencer はパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="b9fc6-165">**プライマリ機能ブロック**。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-165">**Primary Feature Block**.</span></span> <span data-ttu-id="b9fc6-166">Sequencer は、プライマリ機能ブロックを再構築することで、ストリーミング用にパッケージを最適化します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="b9fc6-167">アプリケーションを構成しない場合は、[**この手順をスキップ**] をクリックして、手順9に進み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="b9fc6-168">[**完了**] ページで、[**仮想アプリケーションパッケージレポート**] ウィンドウに表示される情報を確認した後、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-168">On the **Completion** page, after you review the information that is displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="b9fc6-169">このパッケージは、Sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="b9fc6-170">パッケージのプロパティを編集するには、[ **\ [パッケージ名 \] の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="b9fc6-171">パッケージの変更方法の詳細については、「[既存の仮想アプリケーションパッケージを変更する方法](how-to-modify-an-existing-virtual-application-package-beta.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-171">For more information about how to modify a package, see [How to Modify an Existing Virtual Application Package](how-to-modify-an-existing-virtual-application-package-beta.md).</span></span>

   <span data-ttu-id="b9fc6-172">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-172">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b9fc6-173">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-173">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b9fc6-174">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="b9fc6-174">Got an App-V issue?</span></span>** <span data-ttu-id="b9fc6-175">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b9fc6-175">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b9fc6-176">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b9fc6-176">Related topics</span></span>


[<span data-ttu-id="b9fc6-177">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="b9fc6-177">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









