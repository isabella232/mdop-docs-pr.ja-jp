---
title: パッケージ アクセラレータを作成する方法
description: パッケージ アクセラレータを作成する方法
author: dansimp
ms.assetid: b61f3581-7933-443e-b872-a96bed9ff8d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6893f2e9bb9db473d285026015c3399fb0074015
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814266"
---
# <span data-ttu-id="e6a02-103">パッケージ アクセラレータを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e6a02-103">How to Create a Package Accelerator</span></span>


<span data-ttu-id="e6a02-104">App-v 5.1 パッケージアクセラレータでは、新しい仮想アプリケーションパッケージが自動的に生成されます。</span><span class="sxs-lookup"><span data-stu-id="e6a02-104">App-V 5.1 package accelerators automatically generate new virtual application packages.</span></span>

**<span data-ttu-id="e6a02-105">注</span><span class="sxs-lookup"><span data-stu-id="e6a02-105">Note</span></span>**  
<span data-ttu-id="e6a02-106">PowerShell を使用して、パッケージアクセラレータを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e6a02-106">You can use PowerShell to create a package accelerator.</span></span> <span data-ttu-id="e6a02-107">詳細については[、「PowerShell を使用してパッケージアクセラレータを作成する方法](how-to-create-a-package-accelerator-by-using-powershell51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e6a02-107">For more information see [How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell51.md).</span></span>



<span data-ttu-id="e6a02-108">パッケージアクセラレータを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-108">Use the following procedure to create a package accelerator.</span></span>

**<span data-ttu-id="e6a02-109">重要</span><span class="sxs-lookup"><span data-stu-id="e6a02-109">Important</span></span>**  
<span data-ttu-id="e6a02-110">パッケージアクセラレータには、パスワードとユーザー固有の情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e6a02-110">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="e6a02-111">そのため、パッケージアクセラレータと関連するインストールメディアを安全な場所に保存する必要があります。また、パッケージアクセラレータを作成した後で、アプリを作成した後で、app-v 5.1 パッケージアクセラレータが適用されたときに、発行元を確認できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-111">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.1 Package Accelerator is applied.</span></span>



**<span data-ttu-id="e6a02-112">重要</span><span class="sxs-lookup"><span data-stu-id="e6a02-112">Important</span></span>**  
<span data-ttu-id="e6a02-113">次の手順を始める前に、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-113">Before you begin the following procedure, you should perform the following:</span></span>

-   <span data-ttu-id="e6a02-114">Sequencer を実行しているコンピューターにローカルでパッケージアクセラレータを作成するために使用する仮想アプリケーションパッケージをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-114">Copy the virtual application package that you will use to create the package accelerator locally to the computer running the sequencer.</span></span>

-   <span data-ttu-id="e6a02-115">仮想アプリケーションパッケージに関連付けられているすべての必要なインストールファイルを、sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-115">Copy all required installation files associated with the virtual application package to the computer running the sequencer.</span></span>



**<span data-ttu-id="e6a02-116">パッケージアクセラレータを作成するには</span><span class="sxs-lookup"><span data-stu-id="e6a02-116">To create a package accelerator</span></span>**

1.  **<span data-ttu-id="e6a02-117">重要</span><span class="sxs-lookup"><span data-stu-id="e6a02-117">Important</span></span>**  
    <span data-ttu-id="e6a02-118">App-v 5.1 Sequencer は、パッケージアクセラレータの作成に使用しているソフトウェアアプリケーションのライセンス権限を付与しません。</span><span class="sxs-lookup"><span data-stu-id="e6a02-118">The App-V 5.1 Sequencer does not grant any license rights to the software application you are using to create the Package Accelerator.</span></span> <span data-ttu-id="e6a02-119">使用しているアプリケーションのすべてのエンドユーザーライセンス条項を遵守する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-119">You must abide by all end user license terms for the application you are using.</span></span> <span data-ttu-id="e6a02-120">ソフトウェアアプリケーションのライセンス条項によって、App-v 5.1 Sequencer を使ってパッケージアクセラレータを作成できるかどうかを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-120">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using App-V 5.1 Sequencer.</span></span>



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="e6a02-121">App-v 5.1**パッケージアクセラレータの作成**ウィザードを起動するには、app-v 5.1 sequencer コンソールで、[**ツール**] [アクセラレータの作成] をクリックし  /  **Create Accelerator**ます。</span><span class="sxs-lookup"><span data-stu-id="e6a02-121">To start the App-V 5.1 **Create Package Accelerator** wizard, in the App-V 5.1 sequencer console, click **Tools** / **Create Accelerator**.</span></span>

3. <span data-ttu-id="e6a02-122">[**パッケージの選択**] ページで、パッケージアクセラレータの作成に使用する既存の仮想アプリケーションパッケージを指定するには、[**参照**] をクリックし、既存の仮想アプリケーションパッケージ (appv ファイル) を探します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-122">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.appv file).</span></span>

   **<span data-ttu-id="e6a02-123">ヒント</span><span class="sxs-lookup"><span data-stu-id="e6a02-123">Tip</span></span>**  
   <span data-ttu-id="e6a02-124">ローカルで使用する仮想アプリケーションパッケージに関連付けられているファイルを、Sequencer を実行しているコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-124">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="e6a02-125">[**インストールファイル**] ページで、元の仮想アプリケーションパッケージの作成に使用したインストールファイルが保存されているフォルダーを指定するには、[**参照**] をクリックし、インストールファイルが格納されているディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-125">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="e6a02-126">ヒント</span><span class="sxs-lookup"><span data-stu-id="e6a02-126">Tip</span></span>**  
   <span data-ttu-id="e6a02-127">Sequencer を実行しているコンピューターに、必要なインストールファイルを含むフォルダーをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-127">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



5. <span data-ttu-id="e6a02-128">アプリケーションが既に sequencer を実行しているコンピューターにインストールされている場合は、インストールファイルを指定するには、[**ローカルシステムにインストールされたファイル**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-128">If the application is already installed on the computer running the sequencer, to specify the installation file, select **Files installed on local system**.</span></span> <span data-ttu-id="e6a02-129">このオプションを使うには、アプリケーションが既定のインストール場所に既にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-129">To use this option, the application must already be installed in the default installation location.</span></span>

6. <span data-ttu-id="e6a02-130">[**情報の収集**] ページで、このウィザードの [**インストールファイル**] ページで指定した場所に見つからなかったファイルを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-130">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="e6a02-131">表示されたファイルが必要ない場合は、[**これらのファイルを削除**する] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-131">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="e6a02-132">ファイルが必要な場合は、[**前へ**] をクリックし、必要なファイルを [**インストールファイル**] ページで指定したディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-132">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="e6a02-133">注</span><span class="sxs-lookup"><span data-stu-id="e6a02-133">Note</span></span>**  
   <span data-ttu-id="e6a02-134">不要なファイルを削除するか、[**前**へ] をクリックして、このウィザードの次のページに進むために必要なファイルを特定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-134">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



7. <span data-ttu-id="e6a02-135">[**ファイルの選択**] ページで、検出されたファイルを慎重に確認し、パッケージアクセラレータから削除する必要があるファイルをクリアします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-135">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the package accelerator.</span></span> <span data-ttu-id="e6a02-136">アプリケーションを正常に実行するために必要なファイルのみを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-136">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

8. <span data-ttu-id="e6a02-137">[**アプリケーションの確認**] ページで、パッケージをビルドするために必要なすべてのインストールファイルが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-137">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="e6a02-138">パッケージアクセラレータを使って新しいパッケージを作成すると、[**アプリケーション**] ウィンドウに表示されるすべてのインストールファイルが、パッケージを作成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="e6a02-138">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="e6a02-139">必要に応じて、追加のインストーラファイルを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-139">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="e6a02-140">不要なインストールファイルを削除するには、インストーラファイルを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-140">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="e6a02-141">インストーラーに関連付けられているプロパティを編集するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-141">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="e6a02-142">この手順で指定したインストールファイルは、パッケージアクセラレータを使って新しい仮想アプリケーションパッケージを作成するときに必要になります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-142">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="e6a02-143">表示された情報を確認したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-143">After you have confirmed the information displayed, click **Next**.</span></span>

9. <span data-ttu-id="e6a02-144">**[ガイダンスの選択**] ページで、パッケージアクセラレータに関する情報が含まれているファイルを指定するには、[**参照**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-144">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="e6a02-145">たとえば、このファイルには、Sequencer を実行するコンピューターの構成方法、ターゲットコンピューターのアプリケーションの必須情報、一般的なメモなどの情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e6a02-145">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="e6a02-146">パッケージアクセラレータが正常に適用されるために必要なすべての情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-146">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="e6a02-147">選択するファイルは、リッチテキスト形式 (.rtf) またはテキストファイル (.txt) 形式である必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-147">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="e6a02-148">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-148">Click **Next**.</span></span>

10. <span data-ttu-id="e6a02-149">[**パッケージアクセラレータの作成**] ページで、パッケージアクセラレータの保存場所を指定するには、[**参照**] をクリックし、ディレクトリを選択します。</span><span class="sxs-lookup"><span data-stu-id="e6a02-149">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

11. <span data-ttu-id="e6a02-150">[**完了**] ページで、[**パッケージアクセラレータの作成**] ウィザードを閉じるには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e6a02-150">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="e6a02-151">重要</span><span class="sxs-lookup"><span data-stu-id="e6a02-151">Important</span></span>**  
   <span data-ttu-id="e6a02-152">パッケージアクセラレータが可能な限りセキュリティで保護されるようにするために、パッケージアクセラレータが適用されたときに発行元を確認できるように、常にパッケージアクセラレータにデジタル署名する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e6a02-152">To help ensure that the package accelerator is as secure as possible, and so that the publisher can be verified when the package accelerator is applied, you should always digitally sign the package accelerator.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="e6a02-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e6a02-153">Related topics</span></span>


[<span data-ttu-id="e6a02-154">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="e6a02-154">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="e6a02-155">APP-V パッケージ アクセラレータを使用して仮想アプリケーション パッケージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e6a02-155">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)









