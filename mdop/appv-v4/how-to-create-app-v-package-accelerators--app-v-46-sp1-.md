---
title: App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)
description: App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 585e692e-cebb-48ac-93ab-b2e7eb7ae7ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eb806ccf04fcd5ae7db87c5de21e85217739fcbc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817637"
---
# <span data-ttu-id="9d1e3-103">App-V パッケージ アクセラレータを作成する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="9d1e3-103">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="9d1e3-104">App-v パッケージアクセラレータを使用して、新しい仮想アプリケーションパッケージを自動的に生成することができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="9d1e3-105">パッケージアクセラレータの作成が正常に完了したら、パッケージアクセラレータを再利用して共有できます。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-105">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="9d1e3-106">パッケージアクセラレータの詳細については、「app-v[パッケージアクセラレータについて (app-v 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-106">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span> <span data-ttu-id="9d1e3-107">App-v パッケージアクセラレータの作成は、高度なタスクです。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-107">Creating App-V Package Accelerators is an advanced task.</span></span> <span data-ttu-id="9d1e3-108">パッケージアクセラレータには、パスワードとユーザー固有の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-108">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="9d1e3-109">そのため、パッケージアクセラレータと関連するインストールメディアを安全な場所に保存する必要があります。また、パッケージアクセラレータを作成した後で、アプリを作成した後で、app-v パッケージアクセラレータが適用されたときにその発行元を確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-109">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V Package Accelerator is applied.</span></span>

<span data-ttu-id="9d1e3-110">場合によっては、パッケージアクセラレータを作成するときに、Sequencer を実行しているコンピューターにローカルでアプリケーションをインストールすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-110">In some situations, to create the Package Accelerator, you might have to install the application locally on the computer running the Sequencer.</span></span> <span data-ttu-id="9d1e3-111">まず、インストールメディアを使ってパッケージアクセラレータを作成し、必要なファイルが不足している場合は、Sequencer を実行しているコンピューターにローカルでアプリケーションをインストールしてから、パッケージアクセラレータを作成します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-111">First try to create the Package Accelerator by using the installation media, and if there are a number of missing files that are required, install the application locally to the computer running the Sequencer, and then create the Package Accelerator.</span></span>

**<span data-ttu-id="9d1e3-112">重要</span><span class="sxs-lookup"><span data-stu-id="9d1e3-112">Important</span></span>**  
<span data-ttu-id="9d1e3-113">次の手順を始める前に、次の操作を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-113">Before you begin the following procedure, you should do the following:</span></span>

-   <span data-ttu-id="9d1e3-114">Sequencer を実行しているコンピューターにローカルでパッケージアクセラレータを作成するために使用する仮想アプリケーションパッケージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-114">Copy the virtual application package that you must use to create the Package Accelerator locally to the computer running the Sequencer.</span></span>

-   <span data-ttu-id="9d1e3-115">仮想アプリケーションパッケージに関連付けられているすべての必要なインストールファイルを、Sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-115">Copy all required installation files associated with the virtual application package to the computer running the Sequencer.</span></span>



**<span data-ttu-id="9d1e3-116">重要</span><span class="sxs-lookup"><span data-stu-id="9d1e3-116">Important</span></span>**  
<span data-ttu-id="9d1e3-117">免責事項: Microsoft Application Virtualization Sequencer は、パッケージアクセラレータの作成に使用しているソフトウェアアプリケーションのライセンス権限を付与していません。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-117">Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="9d1e3-118">お客様は、本アプリケーションのすべてのエンドユーザライセンス条項を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-118">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="9d1e3-119">ソフトウェアアプリケーションのライセンス条項によって、Application Virtualization Sequencer を使用したパッケージアクセラレータの作成が許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-119">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="9d1e3-120">App-v パッケージアクセラレータを作成するには</span><span class="sxs-lookup"><span data-stu-id="9d1e3-120">To create an App-V Package Accelerator</span></span>**

1.  <span data-ttu-id="9d1e3-121">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="9d1e3-122">App-v の**パッケージアクセラレータの作成**ウィザードを起動するには、[**ツール**] の [  /  **パッケージアクセラレータの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-122">To start the App-V **Create Package Accelerator** wizard, in the App-V Sequencer, click **Tools** / **Create Package Accelerator**.</span></span>

3.  <span data-ttu-id="9d1e3-123">[**パッケージの選択**] ページで、パッケージアクセラレータの作成に使用する既存の仮想アプリケーションパッケージを指定するには、[**参照**] をクリックし、既存の仮想アプリケーションパッケージ (sprj ファイル) を探します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-123">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.sprj file).</span></span>

    **<span data-ttu-id="9d1e3-124">ヒント</span><span class="sxs-lookup"><span data-stu-id="9d1e3-124">Tip</span></span>**  
    <span data-ttu-id="9d1e3-125">ローカルで使用する仮想アプリケーションパッケージに関連付けられているファイルを、Sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-125">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="9d1e3-126">[**インストールファイル**] ページで、元の仮想アプリケーションパッケージの作成に使用したインストールファイルが保存されているフォルダーを指定するには、[**参照**] をクリックし、インストールファイルが格納されているディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-126">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="9d1e3-127">ヒント</span><span class="sxs-lookup"><span data-stu-id="9d1e3-127">Tip</span></span>**  
   <span data-ttu-id="9d1e3-128">Sequencer を実行しているコンピューターに、必要なインストールファイルを含むフォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-128">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



~~~
If the application is already installed on the computer running the Sequencer, to specify the installation file, select **Files installed on local system**. To use this option, the application must already be installed in the default installation location.
~~~

5. <span data-ttu-id="9d1e3-129">[**情報の収集**] ページで、このウィザードの [**インストールファイル**] ページで指定した場所に見つからなかったファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-129">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="9d1e3-130">表示されたファイルが必要ない場合は、[**これらのファイルを削除**する] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-130">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="9d1e3-131">ファイルが必要な場合は、[**前へ**] をクリックし、必要なファイルを [**インストールファイル**] ページで指定したディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-131">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="9d1e3-132">注</span><span class="sxs-lookup"><span data-stu-id="9d1e3-132">Note</span></span>**  
   <span data-ttu-id="9d1e3-133">不要なファイルを削除するか、[**前**へ] をクリックして、このウィザードの次のページに進むために必要なファイルを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-133">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



6. <span data-ttu-id="9d1e3-134">[**ファイルの選択**] ページで、検出されたファイルを慎重に確認し、パッケージアクセラレータから削除する必要があるファイルをクリアします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-134">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the Package Accelerator.</span></span> <span data-ttu-id="9d1e3-135">アプリケーションを正常に実行するために必要なファイルのみを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-135">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

7. <span data-ttu-id="9d1e3-136">[**アプリケーションの確認**] ページで、パッケージをビルドするために必要なすべてのインストールファイルが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-136">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="9d1e3-137">パッケージアクセラレータを使って新しいパッケージを作成すると、[**アプリケーション**] ウィンドウに表示されるすべてのインストールファイルが、パッケージを作成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-137">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="9d1e3-138">必要に応じて、追加のインストーラファイルを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-138">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="9d1e3-139">不要なインストールファイルを削除するには、インストーラファイルを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-139">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="9d1e3-140">インストーラーに関連付けられているプロパティを編集するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-140">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="9d1e3-141">この手順で指定したインストールファイルは、パッケージアクセラレータを使って新しい仮想アプリケーションパッケージを作成するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-141">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="9d1e3-142">表示された情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-142">After you have confirmed the information displayed, click **Next**.</span></span>

8. <span data-ttu-id="9d1e3-143">**[ガイダンスの選択**] ページで、パッケージアクセラレータに関する情報が含まれているファイルを指定するには、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-143">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="9d1e3-144">たとえば、このファイルには、Sequencer を実行するコンピューターの構成方法、ターゲットコンピューターのアプリケーションの必須情報、一般的なメモなどの情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-144">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="9d1e3-145">パッケージアクセラレータが正常に適用されるために必要なすべての情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-145">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="9d1e3-146">選択するファイルは、リッチテキスト形式 (.rtf) またはテキストファイル (.txt) 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-146">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="9d1e3-147">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-147">Click **Next**.</span></span>

9. <span data-ttu-id="9d1e3-148">[**パッケージアクセラレータの作成**] ページで、パッケージアクセラレータの保存場所を指定するには、[**参照**] をクリックし、ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-148">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

10. <span data-ttu-id="9d1e3-149">[**完了**] ページで、[**パッケージアクセラレータの作成**] ウィザードを閉じるには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-149">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="9d1e3-150">重要</span><span class="sxs-lookup"><span data-stu-id="9d1e3-150">Important</span></span>**  
   <span data-ttu-id="9d1e3-151">パッケージアクセラレータが可能な限りセキュリティで保護されるようにするために、パッケージアクセラレータが適用されたときに発行元を確認できるように、常にパッケージアクセラレータにデジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d1e3-151">To help ensure that the Package Accelerator is as secure as possible, and so that the publisher can be verified when the Package Accelerator is applied, you should always digitally sign the Package Accelerator.</span></span>



## <span data-ttu-id="9d1e3-152">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9d1e3-152">Related topics</span></span>


<span data-ttu-id="9d1e3-153">Application Virtualization Sequencer を構成する (App-v 4.6 SP1)[パッケージアクセラレータを適用して仮想アプリケーションパッケージを作成する方法 (app-v 4.6 SP1)](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="9d1e3-153">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1) [How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span></span>









