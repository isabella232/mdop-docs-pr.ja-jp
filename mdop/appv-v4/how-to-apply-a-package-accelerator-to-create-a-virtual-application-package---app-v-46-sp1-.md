---
title: パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (App-v 4.6 SP1)
description: パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (App-v 4.6 SP1)
author: dansimp
ms.assetid: ca0bd514-2bbf-4130-8c77-98d991cbe016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce6960fb95cce7f5e0eeb111412f27f945b0c1a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821384"
---
# <span data-ttu-id="914c9-103">パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (App-v 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="914c9-103">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="914c9-104">App-v パッケージアクセラレータを使用して、新しい仮想アプリケーションパッケージを自動的に生成することができます。</span><span class="sxs-lookup"><span data-stu-id="914c9-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="914c9-105">パッケージアクセラレータの詳細については、「app-v[パッケージアクセラレータについて (app-v 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="914c9-105">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="914c9-106">重要</span><span class="sxs-lookup"><span data-stu-id="914c9-106">Important</span></span>**  
<span data-ttu-id="914c9-107">免責事項: Application Virtualization Sequencer は、パッケージアクセラレータの作成に使用するソフトウェアアプリケーションのライセンス権限を与えません。</span><span class="sxs-lookup"><span data-stu-id="914c9-107">Disclaimer: The Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="914c9-108">お客様は、本アプリケーションのすべてのエンドユーザライセンス条項を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-108">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="914c9-109">ソフトウェアアプリケーションのライセンス条項によって、Application Virtualization Sequencer を使用したパッケージアクセラレータの作成が許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-109">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="914c9-110">注</span><span class="sxs-lookup"><span data-stu-id="914c9-110">Note</span></span>**  
<span data-ttu-id="914c9-111">この手順を開始する前に、App-v Sequencer を実行しているコンピューターに、必要なパッケージアクセラレータをローカルにコピーします。</span><span class="sxs-lookup"><span data-stu-id="914c9-111">Before starting this procedure, copy the required Package Accelerator locally to the computer running the App-V Sequencer.</span></span> <span data-ttu-id="914c9-112">また、Sequencer を実行しているコンピューターのローカルディレクトリに、パッケージの必要なインストールファイルをすべてコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-112">You should also copy all required installation files for the package to a local directory on the computer running the Sequencer.</span></span> <span data-ttu-id="914c9-113">このディレクトリは、この手順の手順5で指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-113">This is the directory that you have to specify in step 5 of this procedure.</span></span>



<span data-ttu-id="914c9-114">パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="914c9-114">Use the following procedure to create a virtual application package by using a Package Accelerator.</span></span>

**<span data-ttu-id="914c9-115">App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成するには</span><span class="sxs-lookup"><span data-stu-id="914c9-115">To create a virtual application package by using an App-V Package Accelerator</span></span>**

1. <span data-ttu-id="914c9-116">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="914c9-116">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="914c9-117">**新しいパッケージの作成ウィザード**を開始するには、[**新しい仮想アプリケーションパッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-117">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="914c9-118">パッケージを作成するには、[**パッケージアクセラレータを使用してパッケージを作成**する] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-118">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3. <span data-ttu-id="914c9-119">[**パッケージアクセラレータの選択**] ページで、新しい仮想アプリケーションパッケージの作成に使用するパッケージアクセラレータを指定するには、[**参照**] をクリックして、使用するパッケージアクセラレータを見つけます。</span><span class="sxs-lookup"><span data-stu-id="914c9-119">On the **Select Package Accelerator** page, to specify the Package Accelerator that will be used to create the new virtual application package, click **Browse** to locate the Package Accelerator that you want to use.</span></span> <span data-ttu-id="914c9-120">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-120">Click **Next**.</span></span>

   **<span data-ttu-id="914c9-121">重要</span><span class="sxs-lookup"><span data-stu-id="914c9-121">Important</span></span>**  
   <span data-ttu-id="914c9-122">パッケージアクセラレータの発行元を検証できず、有効なデジタル署名が含まれていない場合は、[**セキュリティの警告**] ダイアログボックスで、[**実行**] をクリックする前に、パッケージアクセラレータのソースを信頼していることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-122">If the publisher of the Package Accelerator cannot be verified and does not contain a valid digital signature, in the **Security Warning** dialog box, you must confirm that you trust the source of the Package Accelerator before you click **Run**.</span></span>



4. <span data-ttu-id="914c9-123">[**ガイダンス**] ページで、情報ウィンドウに表示される公開ガイダンス情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="914c9-123">On the **Guidance** page, review the publishing guidance information displayed in the information pane.</span></span> <span data-ttu-id="914c9-124">表示される情報は、パッケージアクセラレータの作成時に追加され、パッケージの作成と発行に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="914c9-124">The information displayed was added when the Package Accelerator was created and contains information about creating and publishing the package.</span></span> <span data-ttu-id="914c9-125">ガイダンス情報をテキスト (.txt) ファイルにエクスポートするには、[**エクスポート**] をクリックし、ファイルを保存する場所を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-125">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5. <span data-ttu-id="914c9-126">[**インストールファイルの選択**] ページで、パッケージに必要なすべてのインストールファイルを含むローカルフォルダーを作成するには、[**新しいフォルダー**の作成] をクリックして、フォルダーを保存する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="914c9-126">On the **Select Installation Files** page, to create a local folder that contains all required installation files for the package, click **Make New Folder** and specify where the folder should be saved.</span></span> <span data-ttu-id="914c9-127">フォルダーに割り当てる名前も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-127">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="914c9-128">必要なインストールファイルをすべて指定した場所にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-128">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="914c9-129">インストールファイルを含むフォルダーが、Sequencer を実行しているコンピューターに既に存在する場合は、[**参照**] をクリックして、フォルダーを選びます。</span><span class="sxs-lookup"><span data-stu-id="914c9-129">If the folder that contains the installation files already exists on the computer running the Sequencer, click **Browse** to select the folder.</span></span>

   <span data-ttu-id="914c9-130">または、このコンピューター上のディレクトリにインストールファイルを既にコピーしている場合は、[**新しいフォルダーの作成**] をクリックし、インストールファイルが保存されているフォルダーを参照して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-130">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

   **<span data-ttu-id="914c9-131">注</span><span class="sxs-lookup"><span data-stu-id="914c9-131">Note</span></span>**  
   <span data-ttu-id="914c9-132">次の種類のサポートされているインストールファイルを指定できます。</span><span class="sxs-lookup"><span data-stu-id="914c9-132">You can specify the following types of supported installation files:</span></span>

   -   <span data-ttu-id="914c9-133">Windows インストーラーファイル (**.msi**</span><span class="sxs-lookup"><span data-stu-id="914c9-133">Windows Installer files(**.msi**</span></span>

   -   <span data-ttu-id="914c9-134">.cab ファイル</span><span class="sxs-lookup"><span data-stu-id="914c9-134">.cab files</span></span>

   -   <span data-ttu-id="914c9-135">ファイル名拡張子が .zip の圧縮されたファイル</span><span class="sxs-lookup"><span data-stu-id="914c9-135">Compressed files with a .zip file name extension</span></span>

   -   <span data-ttu-id="914c9-136">実際のアプリケーションファイル</span><span class="sxs-lookup"><span data-stu-id="914c9-136">The actual application files</span></span>

   <span data-ttu-id="914c9-137">次の種類のファイルはサポートされていません。 **.msp**および <strong> .exe </strong> ファイル。</span><span class="sxs-lookup"><span data-stu-id="914c9-137">The following file types are not supported: **.msp** and<strong>.exe</strong> files.</span></span> <span data-ttu-id="914c9-138">**.Exe**ファイルを指定した場合は、インストールファイルを手動で抽出する必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-138">If you specify an **.exe** file you must extract the installation files manually.</span></span>



~~~
If the Package Accelerator requires an application be installed prior to applying the Package Accelerator and you have installed the application, on the **Local Installation** page, select the check box **I have installed all applications**, and then click **Next**.
~~~

6. <span data-ttu-id="914c9-139">[**パッケージ名**] ページで、パッケージに関連付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="914c9-139">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="914c9-140">指定された名前は、App-v 管理コンソールでパッケージを識別します。</span><span class="sxs-lookup"><span data-stu-id="914c9-140">The name specified identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="914c9-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-141">Click **Next**.</span></span>

7. <span data-ttu-id="914c9-142">[**パッケージの作成**] ページで、パッケージに関連付けられるコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="914c9-142">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="914c9-143">コメントには、作成するパッケージについての識別情報が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-143">The comments should contain identifying information about the package you are creating.</span></span> <span data-ttu-id="914c9-144">パッケージが作成された場所を確認するには、[**保存場所**] に表示される情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="914c9-144">To confirm the location where the package is created, review the information displayed in **Save Location**.</span></span> <span data-ttu-id="914c9-145">パッケージを圧縮するには、[**パッケージの圧縮**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="914c9-145">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="914c9-146">パッケージがネットワーク上でストリーミングされる場合、またはパッケージサイズが 4 GB を超える場合は、[**パッケージの圧縮**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="914c9-146">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="914c9-147">パッケージを作成するには、[**作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-147">To create the package, click **Create**.</span></span> <span data-ttu-id="914c9-148">パッケージの作成が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-148">After the package has been created, click **Next**.</span></span>

8. <span data-ttu-id="914c9-149">[**ソフトウェアの構成**] ページで、Sequencer を有効にしてパッケージに含まれるアプリケーションを構成するには、[**ソフトウェアの構成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="914c9-149">On the **Configure Software** page, to enable the Sequencer to configure the applications contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="914c9-150">この手順は、関連付けられているライセンス契約など、ターゲットコンピューター上でアプリケーションを実行するために完了する必要がある関連付けられたタスクを構成する場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="914c9-150">This step is useful for configuring any associated tasks that must be completed to run the application on target computers, such as configuring any associated license agreements.</span></span>

   <span data-ttu-id="914c9-151">[ソフトウェアの**構成**] を選ぶと、この手順の一部として、Sequencer によって次の項目が構成されます。</span><span class="sxs-lookup"><span data-stu-id="914c9-151">If you select **Configure Software**, the following items are configured by the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="914c9-152">**パッケージを読み込み**ます。</span><span class="sxs-lookup"><span data-stu-id="914c9-152">**Load Package**.</span></span> <span data-ttu-id="914c9-153">Sequencer は、パッケージに関連付けられているファイルを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="914c9-153">The Sequencer loads the files associated with the package.</span></span> <span data-ttu-id="914c9-154">パッケージのデコードには、数秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="914c9-154">It can take several seconds to up to an hour to decode the package.</span></span>

   -   <span data-ttu-id="914c9-155">**各プログラムを実行**します。</span><span class="sxs-lookup"><span data-stu-id="914c9-155">**Run Each Program**.</span></span> <span data-ttu-id="914c9-156">必要に応じて、パッケージに含まれているプログラムを実行します。</span><span class="sxs-lookup"><span data-stu-id="914c9-156">Optionally run the programs contained in the package.</span></span> <span data-ttu-id="914c9-157">この手順は、ターゲットコンピューターにパッケージを展開して実行する前に、関連付けられているライセンスまたは構成タスクを実行してアプリケーションを実行するために必要な作業を完了するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="914c9-157">This step is helpful for completing any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="914c9-158">すべてのプログラムを一度に実行するには、1つ以上のプログラムを選択し、[**すべて実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-158">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="914c9-159">特定のプログラムを実行するには、実行するプログラムを選択し、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-159">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="914c9-160">必要な構成タスクを完了して、アプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="914c9-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="914c9-161">すべてのプログラムが実行されるまでに数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="914c9-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="914c9-162">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-162">Click **Next**.</span></span>

   -   <span data-ttu-id="914c9-163">**パッケージを保存**します。</span><span class="sxs-lookup"><span data-stu-id="914c9-163">**Save Package**.</span></span> <span data-ttu-id="914c9-164">Sequencer はパッケージを保存します。</span><span class="sxs-lookup"><span data-stu-id="914c9-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="914c9-165">**プライマリ機能ブロック**。</span><span class="sxs-lookup"><span data-stu-id="914c9-165">**Primary Feature Block**.</span></span> <span data-ttu-id="914c9-166">Sequencer は、プライマリ機能ブロックを再構築することで、ストリーミング用にパッケージを最適化します。</span><span class="sxs-lookup"><span data-stu-id="914c9-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="914c9-167">アプリケーションを構成しない場合は、[**この手順をスキップ**] をクリックして、手順9に進み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="914c9-168">[**完了**] ページで、[**仮想アプリケーションパッケージレポート**] ウィンドウに表示されている情報を確認した後、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-168">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="914c9-169">このパッケージは、Sequencer で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="914c9-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="914c9-170">パッケージのプロパティを編集するには、[ **\ [パッケージ名 \] の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="914c9-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="914c9-171">パッケージの変更の詳細については、「[既存の仮想アプリケーションパッケージを変更する (app-v 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="914c9-171">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

## <span data-ttu-id="914c9-172">関連トピック</span><span class="sxs-lookup"><span data-stu-id="914c9-172">Related topics</span></span>


[<span data-ttu-id="914c9-173">Application Virtualization Sequencer の構成 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="914c9-173">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="914c9-174">App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="914c9-174">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)









