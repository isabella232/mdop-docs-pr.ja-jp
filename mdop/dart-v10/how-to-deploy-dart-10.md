---
title: DaRT 10 を展開する方法
description: DaRT 10 を展開する方法
author: dansimp
ms.assetid: 13e8ba20-21c3-4870-94ed-6d3106d69f21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9e78f55e238cce16798525915487e4b753d92e6c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813074"
---
# <span data-ttu-id="ff524-103">DaRT 10 を展開する方法</span><span class="sxs-lookup"><span data-stu-id="ff524-103">How to Deploy DaRT 10</span></span>


<span data-ttu-id="ff524-104">次の手順では、お使いの環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 10 を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ff524-104">The following instructions explain how to deploy Microsoft Diagnostics and Recovery Toolset (DaRT) 10 in your environment.</span></span> <span data-ttu-id="ff524-105">DaRT ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ff524-105">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span> <span data-ttu-id="ff524-106">すべての機能を1つの管理者コンピューターにインストールすることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="ff524-106">It is assumed that you are installing all functionality on one administrator computer.</span></span> <span data-ttu-id="ff524-107">たとえば、電子的なソフトウェア配布システムを使用して複数のコンピューターに DaRT 10 を展開またはアンインストールする必要がある場合は、コマンドラインインストールオプションを使用する方が簡単です。</span><span class="sxs-lookup"><span data-stu-id="ff524-107">If you need to deploy or uninstall DaRT 10 on multiple computers, using an electronic software distribution system, for example, it might be easier to use command line installation options.</span></span> <span data-ttu-id="ff524-108">使用できるコマンドラインオプションの説明と例については、このセクションで説明します。</span><span class="sxs-lookup"><span data-stu-id="ff524-108">Descriptions and examples of the available command line options are provided in this section.</span></span>

<span data-ttu-id="ff524-109">**重要** DaRT をインストールする前に、 [dart 10 のサポートされ](dart-10-supported-configurations.md)ている構成を参照して、すべての必須ソフトウェアをインストールしていること、およびコンピューターがシステム要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff524-109">**Important** Before you install DaRT, see [DaRT 10 Supported Configurations](dart-10-supported-configurations.md) to ensure that you have installed all of the prerequisite software and that the computer meets the minimum system requirements.</span></span> <span data-ttu-id="ff524-110">DaRT をインストールするコンピューターでは、Windows 10 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ff524-110">The computer onto which you install DaRT must be running Windows 10.</span></span>

 

<span data-ttu-id="ff524-111">DaRT は、次の2つの異なる構成のいずれかを使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ff524-111">You can install DaRT using one of two different configurations:</span></span>

-   <span data-ttu-id="ff524-112">DaRT およびすべての DaRT ツールを管理者コンピュータにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff524-112">Install DaRT and all of the DaRT tools on the administrator computer.</span></span>

-   <span data-ttu-id="ff524-113">管理者のコンピューターにインストールする DaRT 回復イメージの作成に必要なツールのみをインストールしてから、**リモート接続ビューアー**をインストールし、必要に応じて、ヘルプデスクコンピューターに**クラッシュアナライザー**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff524-113">Install on the administrator computer only the tools that you need to create the DaRT recovery image, and then install the **Remote Connection Viewer** and, optionally, **Crash Analyzer** on a help desk computer.</span></span>

<span data-ttu-id="ff524-114">DaRT インストールファイルは、32ビット版と64ビット版の両方で利用できます。</span><span class="sxs-lookup"><span data-stu-id="ff524-114">The DaRT installation file is available in both 32-bit and 64-bit versions.</span></span> <span data-ttu-id="ff524-115">作成している回復イメージのコンピューターアーキテクチャではなく、DaRT 回復イメージウィザードを実行しているコンピューターのアーキテクチャと一致するバージョンをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff524-115">Install the version that matches the architecture of the computer on which you are running the DaRT Recovery Image wizard, not the computer architecture of the recovery image that you are creating.</span></span>

<span data-ttu-id="ff524-116">いずれかのバージョンの DaRT インストールファイルを使って、32ビットまたは64ビットのコンピュータの回復イメージを作成することはできますが、32ビットと64ビットの両方のコンピューターに対して1つの回復イメージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="ff524-116">You can use either version of the DaRT installation file to create a recovery image for either 32-bit or 64-bit computers, but you cannot create one recovery image for both 32-bit and 64-bit computers.</span></span>

**<span data-ttu-id="ff524-117">管理者コンピューターに DaRT とすべての DaRT ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ff524-117">To install DaRT and all DaRT tools on an administrator computer</span></span>**

1.  <span data-ttu-id="ff524-118">DaRT 10 インストーラファイルの32ビットまたは64ビットバージョンをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="ff524-118">Download the 32-bit or 64-bit version of the DaRT 10 installer file.</span></span> <span data-ttu-id="ff524-119">DaRT をインストールしていて、DaRT リカバリ画像ウィザードを実行しているコンピューターと一致するアーキテクチャを選択します。</span><span class="sxs-lookup"><span data-stu-id="ff524-119">Choose the architecture that matches the computer on which you are installing DaRT and running the DaRT Recovery Image wizard.</span></span>

2.  <span data-ttu-id="ff524-120">DaRT 10 をダウンロードしたフォルダーから、お使いのシステム要件に対応する**MSDaRT.msi**インストールファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="ff524-120">From the folder into which you downloaded DaRT 10, run the **MSDaRT.msi** installation file that corresponds to your system requirements.</span></span>

3.  <span data-ttu-id="ff524-121">[ **Microsoft DaRT 10 セットアップウィザードへようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff524-121">On the **Welcome to the Microsoft DaRT 10 Setup Wizard** page, click **Next**.</span></span>

4.  <span data-ttu-id="ff524-122">Microsoft ソフトウェアライセンス条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff524-122">Accept the Microsoft Software License Terms, and then click **Next**.</span></span>

5.  <span data-ttu-id="ff524-123">[ **Microsoft update** ] ページで [**更新プログラムを確認するときに Microsoft Update を使用する**] を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff524-123">On the **Microsoft Update** page, select **Use Microsoft Update when I check for updates**, and then click **Next**.</span></span>

6.  <span data-ttu-id="ff524-124">**[インストールフォルダーの選択**] ページでフォルダーを選ぶか、[**次**へ] をクリックして、既定のインストール場所に DaRT をインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff524-124">On the **Select Installation Folder** page, select a folder, or click **Next** to install DaRT in the default installation location.</span></span>

7.  <span data-ttu-id="ff524-125">[ **Setup Options** ] ページで、インストールする dart 機能を選択するか、[**次**へ] をクリックして dart をすべての機能とともにインストールします。</span><span class="sxs-lookup"><span data-stu-id="ff524-125">On the **Setup Options** page, select the DaRT features that you want to install, or click **Next** to install DaRT with all of the features.</span></span>

8.  <span data-ttu-id="ff524-126">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ff524-126">To start the installation, click **Install**.</span></span>

9.  <span data-ttu-id="ff524-127">インストールが正常に完了したら、[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="ff524-127">After the installation has completed successfully, click **Finish** to exit the wizard.</span></span>

## <span data-ttu-id="ff524-128">コマンドプロンプトを使用して、管理者のコンピューターに DaRT とすべての DaRT ツールをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ff524-128">To install DaRT and all DaRT tools on an administrator computer by using a command prompt</span></span>


<span data-ttu-id="ff524-129">DaRT をインストールまたはアンインストールする際には、コマンドプロンプトからインストールファイルを実行するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="ff524-129">When you install or uninstall DaRT, you have the option of running the installation files at the command prompt.</span></span> <span data-ttu-id="ff524-130">このセクションでは、コマンドプロンプトで DaRT をインストールまたはアンインストールするときに指定できるさまざまなオプションの例をいくつか説明します。</span><span class="sxs-lookup"><span data-stu-id="ff524-130">This section describes some examples of different options that you can specify when you install or uninstall DaRT at the command prompt.</span></span>

<span data-ttu-id="ff524-131">次の例は、すべての DaRT 機能をインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff524-131">The following example shows how to install all DaRT functionality.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles, DaRTRecoveryImage,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="ff524-132">次の例は、DaRT Recovery イメージウィザードのみをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff524-132">The following example shows how to install only the DaRT Recovery Image wizard.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles, ,DaRTRecoveryImage
```

<span data-ttu-id="ff524-133">次の例は、Crash Analyzer と DaRT リモート接続ビューアーのみをインストールする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="ff524-133">The following example shows how to install only the Crash Analyzer and the DaRT Remote Connection Viewer.</span></span>

``` syntax
msiexec /i MSDaRT.msi ADDLOCAL=CommonFiles,CrashAnalyzer,RemoteViewer 
```

<span data-ttu-id="ff524-134">次の例では、Windows インストーラーのセットアップログを作成します。</span><span class="sxs-lookup"><span data-stu-id="ff524-134">The following example creates a setup log for the Windows Installer.</span></span> <span data-ttu-id="ff524-135">これは、デバッグに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="ff524-135">This is valuable for debugging.</span></span>

``` syntax
msiexec.exe /i MSDaRT.msi /l*v log.txt 
```

<span data-ttu-id="ff524-136">**注** /Qn または/qb を追加してサイレントインストールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ff524-136">**Note** You can add /qn or /qb to perform a silent installation.</span></span>

 

**<span data-ttu-id="ff524-137">DaRT のインストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="ff524-137">To validate the DaRT installation</span></span>**

1.  <span data-ttu-id="ff524-138">[**スタート**] をクリックし、[**診断/回復ツールセット**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ff524-138">Click **Start**, and select **Diagnostics and Recovery Toolset**.</span></span>

    <span data-ttu-id="ff524-139">[**診断/回復ツールセット**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="ff524-139">The **Diagnostics and Recovery Toolset** window opens.</span></span>

2.  <span data-ttu-id="ff524-140">インストール用に選択したすべての DaRT ツールが正常にインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ff524-140">Check that all of the DaRT tools that you selected for installation were successfully installed.</span></span>

## <span data-ttu-id="ff524-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ff524-141">Related topics</span></span>


[<span data-ttu-id="ff524-142">管理者用コンピューターへの DaRT 10 の展開</span><span class="sxs-lookup"><span data-stu-id="ff524-142">Deploying DaRT 10 to Administrator Computers</span></span>](deploying-dart-10-to-administrator-computers.md)

 

 





