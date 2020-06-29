---
title: シーケンス処理された仮想アプリケーション パッケージをアップグレードする方法
description: シーケンス処理された仮想アプリケーション パッケージをアップグレードする方法
author: dansimp
ms.assetid: ffa989f3-6621-4c59-9599-e3c3b3332f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45f7b3370e7989bfa860c25fd4ac81f2c2eb0959
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816484"
---
# <span data-ttu-id="2e76f-103">シーケンス処理された仮想アプリケーション パッケージをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="2e76f-103">How to Upgrade a Sequenced Virtual Application Package</span></span>


<span data-ttu-id="2e76f-104">Application Virtualization (App-v) Sequencer を使用して、既存の仮想アプリケーションを新しいバージョンにアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-104">You can upgrade an existing virtual application to a new version by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="2e76f-105">アップグレードプロセスは、新しい仮想アプリケーションの作成に似ています。</span><span class="sxs-lookup"><span data-stu-id="2e76f-105">The upgrade process is similar to creating a new virtual application.</span></span> <span data-ttu-id="2e76f-106">アップグレード用に既存の仮想アプリケーションを開いて、必要な更新を行った後、更新された仮想アプリケーションをパッケージルートディレクトリ内の新しい場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e76f-106">You must open the existing virtual application for an upgrade, make the necessary updates, and then save the updated virtual application to a new location in the package root directory.</span></span> <span data-ttu-id="2e76f-107">また、App-v Sequencer コンソールを使用して、アップグレードを実行せずに既存の仮想アプリケーションに変更を加えることもできます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-107">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade.</span></span> <span data-ttu-id="2e76f-108">ただし、このメソッドを使用して仮想アプリケーションのファイルシステムを変更することはできません。これは、アプリによって関連付けられた sft ファイルが実際にデコードされないためです。</span><span class="sxs-lookup"><span data-stu-id="2e76f-108">However, you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="2e76f-109">たとえば、[**ファイル**] メニューの [**開く**] を選択すると、アプリ内で既存の仮想アプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-109">For example; you can open an existing virtual application in the App-V Sequencer Console by selecting **Open** on the **File** menu.</span></span> <span data-ttu-id="2e76f-110">**パッケージ名**と関連付けられている**コメント**を更新したり、仮想ファイルシステムと仮想レジストリを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-110">You can update the **Package Name** and the associated **Comments**, and you can make changes to the virtual file system and virtual registry.</span></span> <span data-ttu-id="2e76f-111">Windows インストーラーファイルを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-111">You can also create a Windows Installer file.</span></span>

<span data-ttu-id="2e76f-112">**注意** 既存の仮想アプリケーションパッケージをアップグレードする場合は、以前のバージョンの Windows Installer (.msi) ファイルを参照しないようにしてください。以前のバージョンの sft ファイルはアップグレード中に変更されます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-112">**Caution** You should not reference a previous version of the Windows Installer (.msi) file when you upgrade an existing virtual application package because the previous version of the .sft file will be modified during the upgrade.</span></span>

 

<span data-ttu-id="2e76f-113">既存の仮想アプリケーションをアップグレードするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-113">Use the following procedure to upgrade an existing virtual application.</span></span>

**<span data-ttu-id="2e76f-114">既存の仮想アプリケーションをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="2e76f-114">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="2e76f-115">App-v sequencer コンソールを起動するには、app-v sequencer を実行しているコンピューターで、[プログラムの**開始**] microsoft application virtualization Sequencer を選択し / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**ます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-115">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start**/**Programs**/**Microsoft Application Virtualization**/**Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="2e76f-116">既存の仮想アプリケーションを開くには、app-v コンソールで [ **File** / **パッケージのアップグレード用に**ファイルを開く] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-116">To open the existing virtual application, in the App-V Console, select **File**/**Open for Package Upgrade**.</span></span> <span data-ttu-id="2e76f-117">[**パッケージのアップグレード用に開く**] ダイアログボックスを使って、アップグレード用に開く関連の SPRJ ファイルを見つけます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-117">Use the **Open For Package Upgrade** dialog box to locate the associated SPRJ file you want to open for upgrade.</span></span>

3.  <span data-ttu-id="2e76f-118">更新されたパッケージのデコード先の場所を指定するには、[**フォルダーの参照**] ダイアログボックスを使用して場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-118">To specify the location of where the updated package will be decoded, browse to the location by using the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="2e76f-119">これは、関連付けられた SFT ファイルで指定されたパッケージルートディレクトリの作成場所です。</span><span class="sxs-lookup"><span data-stu-id="2e76f-119">This is the location where the package root directory will be created as specified in the associated SFT file.</span></span> <span data-ttu-id="2e76f-120">指定するディレクトリは、仮想アプリケーションの元のバージョンが保存されている場所とは別の場所である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e76f-120">The directory that you specify must be a different location from where the original version of the virtual application is saved.</span></span> <span data-ttu-id="2e76f-121">新しいターゲットフォルダーがまだ作成されていない場合は、[**新しいフォルダー**の作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-121">You can click **Make New Folder** if the new target folder has not been created yet.</span></span> <span data-ttu-id="2e76f-122">フォルダーを作成するには、Application Virtualization ドライブのルートを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e76f-122">You should select the root of the Application Virtualization drive to create the folder.</span></span> <span data-ttu-id="2e76f-123">パッケージの更新されたバージョンを作成すると、ディレクトリ名に続けて番号が付けられます。たとえば、"**.1**" は Q:\\ ドライブにあるディレクトリ名に追加されます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-123">When you create the updated version of the package, it will be denoted with a sequential addition to the directory name—for example, “**.1**” will be added to the directory name located on the Q:\\ drive.</span></span>

    <span data-ttu-id="2e76f-124">**重要** 指定するディレクトリは、Q:\\ ドライブのパッケージルートディレクトリに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e76f-124">**Important** The directory that you specify must be located in the package root directory on the Q:\\ drive.</span></span> <span data-ttu-id="2e76f-125">新しいフォルダーを作成することも、元の仮想アプリケーションが保存されているディレクトリの下にサブフォルダーを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-125">You can create a new folder, or you can create a subfolder under the directory where the original virtual application is saved.</span></span> <span data-ttu-id="2e76f-126">新しいフォルダーに割り当てられた名前は、8 8 文字以下にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e76f-126">The name assigned to the new folder must not be longer than 8 eight characters.</span></span>

     

4.  <span data-ttu-id="2e76f-127">シーケンスウィザードを開くには、[**ツール** / **シーケンスウィザード**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-127">To open the Sequencing Wizard, select **Tools**/**Sequencing Wizard**.</span></span> <span data-ttu-id="2e76f-128">[**パッケージ情報**] ページで、必要に応じて新しい**パッケージ名**を指定し、更新された仮想アプリケーションに関連付けられるオプションのコメントを追加します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-128">On the **Package Information** page, optionally specify the new **Package Name** and add optional comments that will be associated with the updated virtual application.</span></span> <span data-ttu-id="2e76f-129">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-129">Click **Next**.</span></span>

5.  <span data-ttu-id="2e76f-130">[**インストールの監視**] ページで、新しいインストールの監視を開始するには、[**監視の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-130">On the **Monitor Installation** page, to begin monitoring the new installation, click **Begin Monitoring**.</span></span> <span data-ttu-id="2e76f-131">仮想環境の読み込みが完了したら、更新されたバージョンのアプリケーションをインストールするか、既存のアプリケーションに更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-131">After the virtual environment has finished loading, install the updated version of the application, or apply updates to the existing application.</span></span> <span data-ttu-id="2e76f-132">仮想アプリケーションの更新が完了したら、[**監視の停止**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-132">After you have finished updating the virtual application, click **Stop Monitoring**, and then click **Next**.</span></span>

6.  <span data-ttu-id="2e76f-133">[**仮想ファイルシステム (vfs) にマッピングする追加ファイル**] ページで、仮想ファイルシステム (vfs) に追加するファイルを指定するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-133">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="2e76f-134">追加するファイルを参照し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-134">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="2e76f-135">追加された既存のファイルを消去するには、[**リセット**] をクリックし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-135">To clear existing files that have been added, click **Reset**, and then click **Next**.</span></span>

7.  <span data-ttu-id="2e76f-136">[**アプリケーションの構成**] ページで、更新された仮想アプリケーションに関連付けるショートカットとファイルの種類の関連付けを構成します。</span><span class="sxs-lookup"><span data-stu-id="2e76f-136">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the updated virtual application.</span></span> <span data-ttu-id="2e76f-137">更新する要素を選択し、[**場所の編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-137">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="2e76f-138">[**ショートカットの場所**] ダイアログボックスで構成を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-138">Specify the configurations in the **Shortcut Locations** dialog box, and then click **Next**.</span></span>

8.  <span data-ttu-id="2e76f-139">[**アプリケーションの起動**] ページで、アプリケーションを起動してパッケージがストリーミング用に最適化されていることを確認するには、パッケージを選択し、[**起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-139">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="2e76f-140">この手順は、ターゲットコンピューターでのアプリケーションの最初の実行方法を構成する場合や、関連付けられているライセンス契約を受け入れてクライアントで利用できるようにする場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="2e76f-140">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="2e76f-141">このパッケージに複数のアプリケーションが関連付けられている場合は、[**すべて起動**] を選択して、すべてのアプリケーションを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-141">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="2e76f-142">仮想アプリケーションの新しいバージョンをシーケンスするには、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-142">To sequence the new version of the virtual application, click **Next**.</span></span>

9.  <span data-ttu-id="2e76f-143">完了してシーケンスウィザードを終了するには、[**シーケンスパッケージ**] ページで [**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-143">To finish and to close the Sequencing Wizard, on the **Sequence Package** page, click **Finish**.</span></span>

10. <span data-ttu-id="2e76f-144">仮想アプリケーションを正常に更新した後、パッケージを保存するには、App-v の Sequencer コンソールで、[**ファイル**] メニューの [**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2e76f-144">After you have successfully updated the virtual application, to save the package, in the App-V Sequencer Console, on the **File** menu, select **Save**.</span></span> <span data-ttu-id="2e76f-145">仮想アプリケーションには、手順3で指定したディレクトリでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="2e76f-145">The virtual application can be accessed in the directory specified in step 3.</span></span>

## <span data-ttu-id="2e76f-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e76f-146">Related topics</span></span>


[<span data-ttu-id="2e76f-147">Application Virtualization Sequencer のタスク</span><span class="sxs-lookup"><span data-stu-id="2e76f-147">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





