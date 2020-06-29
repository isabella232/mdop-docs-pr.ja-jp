---
title: 新しいアプリケーションをシーケンス処理する方法 (App-V 4.6)
description: 新しいアプリケーションをシーケンス処理する方法 (App-V 4.6)
author: dansimp
ms.assetid: f2c398c6-9200-4be3-b502-e00386fcd150
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a36021adf45f0f4c80ab08bcabbf9f18bf6e66b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816697"
---
# <span data-ttu-id="3afb7-103">新しいアプリケーションをシーケンス処理する方法 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="3afb7-103">How to Sequence a New Application (App-V 4.6)</span></span>


<span data-ttu-id="3afb7-104">次の手順を使用して、Application Virtualization (App-v) Sequencer を使用して新しい仮想アプリケーションを作成します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-104">Use the following procedure to create a new virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="3afb7-105">また、App-v Sequencer を使用して、すべてのユーザーに適用されるファイルや構成、ユーザーがカスタマイズできるファイルや構成を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-105">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="3afb7-106">アプリケーションのシーケンスが正常に完了すると、アプリは app-v Sequencer で利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-106">After you successfully sequence the application, it is available in the App-V Sequencer.</span></span>

**<span data-ttu-id="3afb7-107">重要</span><span class="sxs-lookup"><span data-stu-id="3afb7-107">Important</span></span>**  
<span data-ttu-id="3afb7-108">シーケンス中に、sequencer を実行しているコンピューターが windows Vista または windows 7 を実行していて、仮想環境以外で再起動が開始された場合 (たとえば、[**スタートアップの開始**] をクリックすると表示されます)、windows のシャットダウンを  /  **Shut Down**防ぐプログラムを閉じるように求められたら、[**キャンセル**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-108">During sequencing, if the computer running the sequencer is running Windows Vista or Windows 7, and a restart is initiated outside of the virtual environment, for example, by clicking **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows from shutting down.</span></span> <span data-ttu-id="3afb7-109">[**強制終了**] をクリックすると、パッケージの作成に失敗し、コンピューターが再起動します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-109">If you click **Force shut down**, the package creation will fail, and the computer will restart.</span></span> <span data-ttu-id="3afb7-110">[**キャンセル**] をクリックすると、sequencer はアプリケーションのシーケンス中に再起動を正常に記録します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-110">When you click **Cancel**, the sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="3afb7-111">新しいアプリケーションの順序を作成するには</span><span class="sxs-lookup"><span data-stu-id="3afb7-111">To sequence a new application</span></span>**

1.  <span data-ttu-id="3afb7-112">App-v ドライブを作成するには、アプリケーションの順序指定中にファイルを保存するために使用できる場所として、ドライブ Q を構成します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-112">To create the App-V drive, configure drive Q as the location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="3afb7-113">次に、ドライブ Q の順序を指定するように計画しているアプリケーションごとに個別のディレクトリを作成する必要があります。アプリケーションをシーケンスする前に、仮想アプリケーションターゲットフォルダーを作成するか、この手順の手順5で作成することができます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-113">You must then create individual directories for each application that you plan to sequence on drive Q. You can create the virtual application targeted folders before you sequence an application, or you can create them in step 5 of this procedure.</span></span>

    **<span data-ttu-id="3afb7-114">注</span><span class="sxs-lookup"><span data-stu-id="3afb7-114">Note</span></span>**  
    <span data-ttu-id="3afb7-115">指定するアプリ V ドライブは、対象のコンピューターでアクセス可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-115">The App-V drive you specify must be accessible on targeted computers.</span></span> <span data-ttu-id="3afb7-116">ドライブ Q にアクセスできない場合は、別のドライブ文字を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-116">If drive Q is not accessible, you can choose a different drive letter.</span></span>



2.  <span data-ttu-id="3afb7-117">App-v sequencer コンソールを起動するには、app-v sequencer を実行しているコンピューターで、[プログラムの**開始**] microsoft application virtualization sequencer を選択し  /  **Programs**  /  **Microsoft Application Virtualization**  /  **Microsoft Application Virtualization Sequencer**ます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="3afb7-118">シーケンスウィザードを開始するには、[**パッケージの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-118">To start the Sequencing Wizard, click **Create a Package**.</span></span>

3.  <span data-ttu-id="3afb7-119">[**パッケージ情報**] ページで、仮想アプリケーションに割り当てる**パッケージ名**を指定します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="3afb7-120">関連付けられた Windows インストーラーファイルを生成するには、パッケージ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="3afb7-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="3afb7-121">また、パッケージに割り当てられ、仮想アプリケーションに関する詳細情報を提供する、オプションのコメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="3afb7-122">[**詳細オプション**] ページを表示するには、[**詳細な監視オプションの表示**] を選択し、[**次へ**] をクリックします。それ以外の場合は、手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**, and then click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="3afb7-123">[**詳細オプション**] ページで、[microsoft update でのシーケンス中にアプリケーションの更新を許可する] を [**監視中に microsoft update を実行することを許可**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-123">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="3afb7-124">このオプションを選択した場合は、監視フェーズ中に Microsoft 更新プログラムをインストールできます。また、関連付けられている更新プログラムをインストールするには、それらの更新を承諾する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-124">If you select this option, Microsoft Updates can be installed during the monitoring phase, and you have to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="3afb7-125">サポートされているダイナミックリンクライブラリ (.dll) ファイルを、連続した RAM として使うように再マップするには、[ **dll**の再配置] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-125">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="3afb7-126">このオプションを選択すると、メモリが節約され、パフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-126">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="3afb7-127">多くのアプリケーションはこのオプションをサポートしていませんが、Terminal Server のシナリオなどの RAM が限られている環境で役立ちます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-127">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="3afb7-128">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-128">Click **Next**.</span></span>

5.  <span data-ttu-id="3afb7-129">[**モニターのインストール**] ページで、アプリケーションをインストールする準備ができたら、[**監視の開始**] をクリックし、[**フォルダーの参照**] ダイアログボックスで、アプリケーションがインストールされるディレクトリをドライブ Q で指定します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-129">On the **Monitor Installation** page, when you are ready to install the application, click **Begin Monitoring**, and in the **Browse for Folder** dialog box, specify the directory on drive Q where the application will be installed.</span></span> <span data-ttu-id="3afb7-130">ドライブ Q を構成しておらず、application virtualization ドライブに別のドライブ文字を使用している場合は、この手順の手順1で指定したドライブ文字を選択します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-130">If you did not configure drive Q and used a different drive letter for the application virtualization drive, select the drive letter you specified in step 1 of this procedure.</span></span> <span data-ttu-id="3afb7-131">アプリケーションの仮想化ドライブで作成されていないフォルダーにアプリケーションをインストールするには、[**新しいフォルダーの作成**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-131">To install the application to a folder that has not been created on the application virtualization drive, click **Make New Folder**.</span></span> <span data-ttu-id="3afb7-132">フォルダーを指定した後、Sequencer がシーケンス処理のためにコンピューターを構成する間待機します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-132">After you specify the folder, wait while the Sequencer configures the computer for sequencing.</span></span>

    **<span data-ttu-id="3afb7-133">重要</span><span class="sxs-lookup"><span data-stu-id="3afb7-133">Important</span></span>**  
    <span data-ttu-id="3afb7-134">シーケンスした各アプリケーションは、仮想アプリケーションドライブ上の個別のディレクトリにインストールする必要があります。また、関連付けられたフォルダー名は8文字以内である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3afb7-134">You must install each application that you sequence into a separate directory on the virtual application drive, and the associated folder name must not be longer than eight characters.</span></span>



~~~
After the computer has been configured for sequencing, install the application so that the App-V Sequencer can monitor the installation; when you are finished, click **Stop Monitoring**, and then click **Next**.
~~~

6. <span data-ttu-id="3afb7-135">必要に応じて、[**アプリケーションの構成**] ページで、仮想アプリケーションに関連付けるショートカットとファイルの種類の関連付けを構成します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-135">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="3afb7-136">新しいファイルの種類の関連付けまたはショートカットを追加するには、[**追加**] をクリックし、[**アプリケーションの追加**] ダイアログボックスで新しい要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-136">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="3afb7-137">既存のショートカットまたはファイルの種類の関連付けを削除するには、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-137">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="3afb7-138">既存の要素を編集するには、変更する要素を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-138">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="3afb7-139">[**アプリケーションの編集**] ダイアログボックスで構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-139">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="3afb7-140">[**保存**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-140">Click **Save**, and then click **Next**.</span></span>

7. <span data-ttu-id="3afb7-141">[**アプリケーションの起動**] ページで、アプリケーションを起動して、パッケージが正しくインストールされ、ストリーミング用に最適化されていることを確認するには、パッケージを選択し、[**起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-141">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package, and then click **Launch**.</span></span> <span data-ttu-id="3afb7-142">この手順は、アプリをターゲットコンピューターで初めて実行する方法を構成する場合や、アプリが app-v クライアントで利用できるようになる前に関連付けられているライセンス契約に同意する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="3afb7-142">This step is useful for configuring how the application initially runs on targeted computers and for accepting any associated license agreements before the package becomes available to App-V clients.</span></span> <span data-ttu-id="3afb7-143">このパッケージに複数のアプリケーションが関連付けられている場合は、[**すべて起動**] を選択して、すべてのアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-143">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="3afb7-144">パッケージをシーケンスするには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3afb7-144">To sequence the package, click **Next**.</span></span>

8. <span data-ttu-id="3afb7-145">パッケージの作成が正常に完了したら、app-v Sequencer コンソールで [**ファイル**の保存] を選択し、  /  **Save**パッケージを保存する名前と仮想ドライブの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3afb7-145">After you have successfully created the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the virtual drive location where the package will be saved.</span></span>

   <span data-ttu-id="3afb7-146">必要に応じて、関連付けられた Windows インストーラーファイル (**.msi**) を作成して、仮想アプリケーションパッケージをターゲットコンピューターにインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-146">You can optionally create an associated Windows Installer file (**.msi**) to install the virtual application package on targeted computers.</span></span> <span data-ttu-id="3afb7-147">Windows インストーラーファイルを作成するには、Sequencer でパッケージを開き、[**ツール**] の [MSI の作成] を選択し  /  **Create MSI**ます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-147">To create a Windows Installer file, open the package in the Sequencer and select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="3afb7-148">Windows Installer ファイルが作成され、仮想アプリケーションパッケージが保存されているディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="3afb7-148">The Windows Installer file will be created and saved in the directory where the virtual application package is saved.</span></span>

   **<span data-ttu-id="3afb7-149">重要</span><span class="sxs-lookup"><span data-stu-id="3afb7-149">Important</span></span>**  
   <span data-ttu-id="3afb7-150">仮想アプリケーションパッケージを正常に作成した後、sequencer を実行しているコンピューターで仮想アプリケーションパッケージを実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="3afb7-150">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer running the sequencer.</span></span>



## <span data-ttu-id="3afb7-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3afb7-151">Related topics</span></span>


[<span data-ttu-id="3afb7-152">仮想アプリケーション パッケージをアップグレードする方法 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="3afb7-152">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>](how-to-upgrade-a-virtual-application-package--app-v-46-.md)









