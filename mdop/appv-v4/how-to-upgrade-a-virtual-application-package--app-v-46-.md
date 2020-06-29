---
title: 仮想アプリケーション パッケージをアップグレードする方法 (App-V 4.6)
description: 仮想アプリケーション パッケージをアップグレードする方法 (App-V 4.6)
author: dansimp
ms.assetid: 3566227e-f3dc-4c32-af1f-e0211588118c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac722dc0e9ce1650f53d8dd22db5428d33cfcf13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816457"
---
# <span data-ttu-id="03fdb-103">仮想アプリケーション パッケージをアップグレードする方法 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="03fdb-103">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>


<span data-ttu-id="03fdb-104">次の手順を使用して、Application Virtualization (App-v) Sequencer を使用して既存の仮想アプリケーションをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-104">Use the following procedure to upgrade an existing virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="03fdb-105">また、アップグレードを実行せずに、既存の仮想アプリケーションを変更するには、App-v Sequencer コンソールを使用することもできますが、このメソッドを使用して仮想アプリケーションのファイルシステムに変更を加えることはできません。ただし、このメソッドを使って、アプリのファイルシステムを変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="03fdb-105">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade, but you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="03fdb-106">既存のパッケージの編集の詳細については、「[仮想アプリケーションパッケージを変更する (app-v 4.6)](how-to-modify-a-virtual-application-package--app-v-46-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="03fdb-106">For more information about editing an existing package, see [How to Modify a Virtual Application Package (App-V 4.6)](how-to-modify-a-virtual-application-package--app-v-46-.md).</span></span>

**<span data-ttu-id="03fdb-107">既存の仮想アプリケーションをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="03fdb-107">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="03fdb-108">App-v sequencer コンソールを起動するには、app-v sequencer を実行しているコンピューターで、[プログラムの**開始**] microsoft application virtualization Sequencer を選択し  /  **Programs**  /  **Microsoft Application Virtualization**  /  **Microsoft Application Virtualization Sequencer**ます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-108">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="03fdb-109">既存の仮想アプリケーションパッケージを開き、**シーケンスウィザード**を開始するには、[**パッケージのアップグレード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-109">To open the existing virtual application package and start the **Sequencing Wizard**, select **Upgrade a Package**.</span></span> <span data-ttu-id="03fdb-110">アップグレードするパッケージを見つけて、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-110">Locate the package you want to upgrade, and click **Open**.</span></span> <span data-ttu-id="03fdb-111">[**フォルダーの参照**] ダイアログボックスで、パッケージのアップグレードされたバージョンを配置する場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-111">In the **Browse For Folder** dialog box, specify the location where the upgraded version of the package will be placed.</span></span> <span data-ttu-id="03fdb-112">指定する場所は、アプリケーションの仮想化ドライブ (通常は Q:\\ ドライブ) として指定されたドライブに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="03fdb-112">This location specified must be located on the drive specified as the application virtualization drive, which is typically the Q:\\ drive.</span></span> <span data-ttu-id="03fdb-113">新しいフォルダーを作成するには、[**新しい**フォルダーの作成] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-113">To create a new folder, select **Make New Folder**.</span></span>

    <span data-ttu-id="03fdb-114">**警告** 既存の仮想アプリケーションのルートフォルダーを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03fdb-114">**Warning** You must specify the root folder of the existing virtual application.</span></span> <span data-ttu-id="03fdb-115">サブフォルダーを手動で作成しないと、アップグレードが失敗します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-115">Do not manually create a subfolder or the upgrade will fail.</span></span>

     

3.  <span data-ttu-id="03fdb-116">[**パッケージ情報**] ページで、更新されたパッケージに割り当てる**パッケージ名**を指定します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-116">On the **Package Information** page, specify the **Package Name** that will be assigned to the updated package.</span></span> <span data-ttu-id="03fdb-117">関連付けられた Windows インストーラーファイルを生成するには、パッケージ名が必要です。</span><span class="sxs-lookup"><span data-stu-id="03fdb-117">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="03fdb-118">また、パッケージに割り当てられ、仮想アプリケーションに関する詳細情報 (たとえば、バージョン番号) を提供する、オプションのコメントを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="03fdb-118">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application—for example, a version number.</span></span> <span data-ttu-id="03fdb-119">[**詳細オプション**] ページを表示するには、[**詳細な監視オプションの表示**] を選択し、[**次へ**] をクリックします。それ以外の場合は、手順5に進みます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-119">To display the **Advanced Options** page, select **Show Advanced Monitoring Options** and click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="03fdb-120">[**詳細オプション**] ページで、[microsoft update でのシーケンス中にアプリケーションの更新を許可する] を [**監視中に microsoft update を実行することを許可**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-120">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="03fdb-121">このオプションを選択した場合は、監視フェーズ中に Microsoft 更新プログラムをインストールすることができます。また、インストールするには、関連付けられている更新プログラムを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="03fdb-121">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="03fdb-122">サポートされているダイナミックリンクライブラリ (.dll) ファイルを、連続した RAM として使うように再マップするには、[ **dll**の再配置] を選択します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-122">To remap the supported dynamic-link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="03fdb-123">このオプションを選択すると、メモリが節約され、パフォーマンスが向上する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="03fdb-123">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="03fdb-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-124">Click **Next**.</span></span>

5.  <span data-ttu-id="03fdb-125">[**インストールの監視**] ページで、アプリケーションを更新する準備ができたら、[**監視の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-125">On the **Monitor Installation** page, when you are ready to update the application, click **Begin Monitoring**.</span></span>

    <span data-ttu-id="03fdb-126">アプリケーションの更新プログラムが適用されたら、[**監視の停止**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-126">When the updates to the application have been applied, click **Stop Monitoring**.</span></span> <span data-ttu-id="03fdb-127">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-127">Click **Next**.</span></span>

6.  <span data-ttu-id="03fdb-128">必要に応じて、[**アプリケーションの構成**] ページで、仮想アプリケーションに関連付けるショートカットとファイルの種類の関連付けを構成します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-128">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="03fdb-129">新しいファイルの種類の関連付けまたはショートカットを追加するには、[**追加**] をクリックし、[**アプリケーションの追加**] ダイアログボックスで新しい要素を指定します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-129">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="03fdb-130">既存のショートカットまたはファイルの種類の関連付けを削除するには、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-130">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="03fdb-131">既存の要素を編集するには、変更する要素を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-131">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="03fdb-132">[**アプリケーションの編集**] ダイアログボックスで構成を指定します。</span><span class="sxs-lookup"><span data-stu-id="03fdb-132">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="03fdb-133">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-133">Click **Save**.</span></span> <span data-ttu-id="03fdb-134">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-134">Click **Next**.</span></span>

7.  <span data-ttu-id="03fdb-135">[**アプリケーションの起動**] ページで、アプリを起動して、パッケージが正しくインストールされ、ストリーミング用に最適化されていることを確認するには、パッケージを選択し、[**起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-135">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="03fdb-136">この手順は、アプリがターゲットコンピューター上で最初に実行される方法を構成する場合や、アプリが app-v クライアントで利用できるようになる前に、関連付けられているライセンス契約に同意する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="03fdb-136">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to App-V clients.</span></span> <span data-ttu-id="03fdb-137">このパッケージに複数のアプリケーションが関連付けられている場合は、[**すべて起動**] を選択して、すべてのアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-137">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="03fdb-138">パッケージをシーケンスするには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-138">To sequence the package, click **Next**.</span></span>

8.  <span data-ttu-id="03fdb-139">シーケンスウィザードを終了するには、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="03fdb-139">To close the Sequencing Wizard, click **Finish**.</span></span> <span data-ttu-id="03fdb-140">更新されたパッケージを保存するには、Sequencer コンソールで [**ファイル**  /  **名を付けて保存**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-140">To save the updated package, in the Sequencer Console, select **File** / **Save**.</span></span>

    <span data-ttu-id="03fdb-141">Windows Installer ファイル (.msi) を使用して更新されたパッケージを展開する予定がある場合は、次のようにして新しいパッケージを作成する必要があります。 Sequencer コンソールで、[**ツール**] の [  /  **msi の作成**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-141">If you plan to deploy the updated package by using a Windows Installer file (.msi), you must create new one as follows: in the Sequencer Console, select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="03fdb-142">新しい Windows Installer ファイルが作成され、更新された仮想アプリケーションパッケージが保存されているディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="03fdb-142">The new Windows Installer file will be created and saved in the directory where the updated virtual application package is saved.</span></span>

## <span data-ttu-id="03fdb-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="03fdb-143">Related topics</span></span>


[<span data-ttu-id="03fdb-144">新しいアプリケーションをシーケンス処理する方法 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="03fdb-144">How to Sequence a New Application (App-V 4.6)</span></span>](how-to-sequence-a-new-application--app-v-46-.md)

 

 





