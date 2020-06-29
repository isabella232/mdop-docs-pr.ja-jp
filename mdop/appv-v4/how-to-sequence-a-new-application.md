---
title: 新しいアプリケーションをシーケンス処理する方法
description: 新しいアプリケーションをシーケンス処理する方法
author: dansimp
ms.assetid: e01e98cd-2378-478f-9739-f72c465bf79a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aab769256116e2635edbc4bcf55d212e3a2152f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816667"
---
# <span data-ttu-id="054fb-103">新しいアプリケーションをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="054fb-103">How to Sequence a New Application</span></span>


<span data-ttu-id="054fb-104">Application Virtualization (App-v) Sequencer は、仮想環境で実行できるアプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="054fb-104">The Application Virtualization (App-V) Sequencer creates applications that can be run in a virtual environment.</span></span> <span data-ttu-id="054fb-105">App-v Sequencer は、アプリケーションのインストールとセットアップのプロセスを監視し、仮想環境でアプリケーションを実行するために必要な情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="054fb-105">The App-V Sequencer monitors the installation and setup process for an application, and it records the information necessary for the application to run in a virtual environment.</span></span> <span data-ttu-id="054fb-106">また、App-v Sequencer を使用して、すべてのユーザーに適用されるファイルや構成、ユーザーがカスタマイズできるファイルや構成を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="054fb-106">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="054fb-107">アプリケーションをシーケンス処理するときに、順序を指定するコンピューターのローカルドライブにパッケージを保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-107">When you sequence an application, you should save the package to a drive that is local to the computer you are sequencing on.</span></span>

<span data-ttu-id="054fb-108">シーケンス処理されたアプリケーションは、仮想環境で実行されるため、インストールまたはターゲットコンピューターで実行されている可能性のある他のアプリケーションから分離されているため、オペレーティングシステムとやり取りしません。</span><span class="sxs-lookup"><span data-stu-id="054fb-108">A sequenced application does not interact with the operating system because each application runs in a virtual environment and is isolated from other applications that might be installed or running on the target computer.</span></span> <span data-ttu-id="054fb-109">この分離によってアプリケーションの競合が大幅に削減され、アプリケーションの展開前に必要なテストの量が減少します。</span><span class="sxs-lookup"><span data-stu-id="054fb-109">This isolation dramatically reduces application conflicts and decreases the required amount of application pre-deployment testing.</span></span>

<span data-ttu-id="054fb-110">アプリケーションのシーケンスが正常に完了すると、そのアプリケーションは App-v の Sequencer コンソールで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="054fb-110">After you successfully sequence the application, it is available in the App-V Sequencer Console.</span></span> <span data-ttu-id="054fb-111">セーフモードでの App-v sequencer の実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="054fb-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>

**<span data-ttu-id="054fb-112">新しいアプリケーションの順序を作成するには</span><span class="sxs-lookup"><span data-stu-id="054fb-112">To sequence a new application</span></span>**

1.  <span data-ttu-id="054fb-113">新しい仮想アプリケーションの順序を指定するには、アプリケーションの仮想化ドライブを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-113">You must create the Application Virtualization drive to sequence a new virtual application.</span></span> <span data-ttu-id="054fb-114">アプリケーションの仮想化ドライブを作成するには、アプリケーションの順序を指定しているときにファイルを保存するために使用できる場所に Q:\\ ドライブをマップします。</span><span class="sxs-lookup"><span data-stu-id="054fb-114">To create the Application Virtualization drive, map the Q:\\ drive to a location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="054fb-115">次に、Q:\\ ドライブで順序を指定するように計画するアプリケーションごとに個別のディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-115">You must then create individual directories for each application you plan to sequence on the Q:\\ drive.</span></span> <span data-ttu-id="054fb-116">アプリケーションをシーケンスする前に、仮想アプリケーションターゲットフォルダーを作成するか、この手順の手順5で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="054fb-116">You can create the virtual application target folders before you sequence an application, or you can create it in step 5 of this procedure.</span></span>

2.  <span data-ttu-id="054fb-117">App-v sequencer コンソールを起動するには、app-v sequencer を実行しているコンピューターで、[プログラムの**開始**] microsoft application virtualization sequencer を選択し  /  **Programs**  /  **Microsoft Application Virtualization**  /  **Microsoft Application Virtualization Sequencer**ます。</span><span class="sxs-lookup"><span data-stu-id="054fb-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="054fb-118">**シーケンスウィザード**を開始するには、[**ファイル**] の [  /  **新しいパッケージ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="054fb-118">To start the **Sequencing Wizard**, select **File** / **New Package**.</span></span>

3.  <span data-ttu-id="054fb-119">[**パッケージ情報**] ページで、仮想アプリケーションに割り当てる**パッケージ名**を指定します。</span><span class="sxs-lookup"><span data-stu-id="054fb-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="054fb-120">関連付けられた Windows インストーラーファイルを生成するには、パッケージ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="054fb-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="054fb-121">また、パッケージに割り当てられ、仮想アプリケーションに関する詳細情報を提供する、オプションのコメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="054fb-122">[**詳細オプション**] ページを表示するには、[**詳細な監視オプションの表示**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="054fb-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="054fb-123">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-123">Click **Next**.</span></span>

    **<span data-ttu-id="054fb-124">注</span><span class="sxs-lookup"><span data-stu-id="054fb-124">Note</span></span>**  
    <span data-ttu-id="054fb-125">[**詳細オプション**] ページを表示するには、[**詳細な監視オプションの表示**] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-125">To display the **Advanced Options** page, you must select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="054fb-126">**[詳細オプション**] ページが必要ない場合は、手順4に進みます。</span><span class="sxs-lookup"><span data-stu-id="054fb-126">If you do not require the **Advanced Options** page, skip to step 4.</span></span>



4.  <span data-ttu-id="054fb-127">[**詳細オプション**] ページで、仮想アプリケーションの**ブロックサイズ**を指定するには、目的のサイズを選びます。</span><span class="sxs-lookup"><span data-stu-id="054fb-127">On the **Advanced Options** page, to specify the **Block Size** for the virtual application, select the size you want.</span></span> <span data-ttu-id="054fb-128">ブロックサイズは、ネットワーク経由でパッケージをターゲットコンピューターにストリーミングするために、 **sft**ファイルがどのように分割されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="054fb-128">The block size determines how the **.sft** file will be divided for streaming the package across the network to target computers.</span></span> <span data-ttu-id="054fb-129">シーケンス中にアプリケーションを更新するように Microsoft Update に許可するには[**監視中に Microsoft Update を実行することを許可する**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="054fb-129">To allow Microsoft Update to update the application as it is being sequenced; select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="054fb-130">このオプションを選択した場合は、監視フェーズ中に Microsoft 更新プログラムをインストールすることができます。また、インストールするには、関連付けられている更新プログラムを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-130">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="054fb-131">サポートされているダイナミックリンクライブラリ (.dll) ファイルを、連続した RAM として使うように再マップするには、[ **dll**の再配置] を選択します。</span><span class="sxs-lookup"><span data-stu-id="054fb-131">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="054fb-132">このオプションを選択すると、メモリが節約され、パフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-132">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="054fb-133">多くのアプリケーションはこのオプションをサポートしていませんが、Terminal Server のシナリオなどの RAM が限られている環境で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="054fb-133">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="054fb-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-134">Click **Next**.</span></span>

5.  <span data-ttu-id="054fb-135">[**モニターのインストール**] ページで、アプリケーションのインストールを監視するには、[**監視の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-135">On the **Monitor Installation** page, to monitor the installation of an application, click **Begin Monitoring**.</span></span> <span data-ttu-id="054fb-136">[監視の**開始**] をクリックした後、アプリケーションをインストールする Q:\\ ドライブ上のディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="054fb-136">After you click **Begin Monitoring**, specify the directory on the Q:\\ drive where the application will be installed.</span></span> <span data-ttu-id="054fb-137">作成されていないフォルダーにアプリケーションをインストールするには、[**新しいフォルダーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-137">To install the application to a folder that has not been created, click **Make New Folder**.</span></span> <span data-ttu-id="054fb-138">順序を指定する各アプリケーションは、別々のディレクトリにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-138">You must install each application that you sequence into a separate directory.</span></span>

    **<span data-ttu-id="054fb-139">重要</span><span class="sxs-lookup"><span data-stu-id="054fb-139">Important</span></span>**  
    <span data-ttu-id="054fb-140">指定するフォルダー名は、8文字以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="054fb-140">The folder name you specify must not be longer than 8 characters.</span></span>



~~~
Wait for the virtual environment to load, and then install the application so that the App-V Sequencer can monitor the process. When you have completed the installation, click **Stop Monitoring** and then click **Next**.
~~~

6. <span data-ttu-id="054fb-141">[**仮想ファイルシステム (vfs) にマッピングする追加ファイル**] ページで、仮想ファイルシステム (vfs) に追加するファイルを指定するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-141">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="054fb-142">追加するファイルを参照し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-142">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="054fb-143">追加された既存のファイルを消去するには、[**リセット**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-143">To clear existing files that have been added, click **Reset** and then click **Next**.</span></span>

7. <span data-ttu-id="054fb-144">[**アプリケーションの構成**] ページで、仮想アプリケーションに関連付けるショートカットとファイルの種類の関連付けを構成します。</span><span class="sxs-lookup"><span data-stu-id="054fb-144">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="054fb-145">更新する要素を選択し、[**場所の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-145">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="054fb-146">[**ショートカットの場所**] ダイアログボックスで構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="054fb-146">Specify the configurations in the **Shortcut Locations** dialog box.</span></span> <span data-ttu-id="054fb-147">[ **OK]** をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-147">Click **OK** and then click **Next**.</span></span>

8. <span data-ttu-id="054fb-148">[**アプリケーションの起動**] ページで、アプリケーションを起動してパッケージがストリーミング用に最適化されていることを確認するには、パッケージを選択し、[**起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-148">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="054fb-149">この手順は、ターゲットコンピューターでのアプリケーションの最初の実行方法を構成する場合や、関連付けられているライセンス契約を受け入れてクライアントで利用できるようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="054fb-149">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="054fb-150">このパッケージに複数のアプリケーションが関連付けられている場合は、[**すべて起動**] を選択して、すべてのアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="054fb-150">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="054fb-151">パッケージをシーケンスするには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-151">To sequence the package, click **Next**.</span></span>

9. <span data-ttu-id="054fb-152">[**シーケンスパッケージ**] ページで、ウィザードを閉じるには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="054fb-152">On the **Sequence Package** page, to close the wizard, click **Finish**.</span></span>

10. <span data-ttu-id="054fb-153">パッケージの作成が完了したら、パッケージを保存するには、app-v Sequencer コンソールで、[**ファイル**の保存] を選択し、  /  **Save**パッケージの保存先の名前と場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="054fb-153">After you have successfully created the package, to save the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the location where the package will be saved.</span></span>

## <span data-ttu-id="054fb-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="054fb-154">Related topics</span></span>


[<span data-ttu-id="054fb-155">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="054fb-155">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









