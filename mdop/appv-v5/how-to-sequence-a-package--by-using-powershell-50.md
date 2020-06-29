---
title: PowerShell を使用してパッケージをシーケンス処理する方法
description: PowerShell を使用してパッケージをシーケンス処理する方法
author: dansimp
ms.assetid: b41feed9-d1c5-48a3-940c-9a21d594f4f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbb9641ba75eda4d190892fa2bd0043c92ed9006
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813699"
---
# <span data-ttu-id="bad7f-103">PowerShell を使用してパッケージをシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="bad7f-103">How to Sequence a Package by Using PowerShell</span></span>


<span data-ttu-id="bad7f-104">PowerShell を使用して新しい App-v 5.0 パッケージを作成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-104">Use the following procedure to create a new App-V 5.0 package using PowerShell.</span></span>

<span data-ttu-id="bad7f-105">**注** この手順を実行する前に、sequencer を実行しているコンピューターに関連付けられているインストーラーファイルをコピーする必要があります。また、「[アプリ-V 5.0 sequencer とクライアント展開の計画](planning-for-the-app-v-50-sequencer-and-client-deployment.md)」の「sequencer」セクションを読み、理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="bad7f-105">**Note** Before you use this procedure you must copy the associated installer files to the computer running the sequencer and you have read and understand the sequencer section of [Planning for the App-V 5.0 Sequencer and Client Deployment](planning-for-the-app-v-50-sequencer-and-client-deployment.md).</span></span>

 

**<span data-ttu-id="bad7f-106">PowerShell を使用して新しい仮想アプリケーションを作成するには</span><span class="sxs-lookup"><span data-stu-id="bad7f-106">To create a new virtual application using PowerShell</span></span>**

1.  <span data-ttu-id="bad7f-107">App-v 5.0 sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="bad7f-107">Install the App-V 5.0 sequencer.</span></span> <span data-ttu-id="bad7f-108">Sequencer のインストールの詳細について[は、「sequencer をインストールする方法」を](how-to-install-the-sequencer-beta-gb18030.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bad7f-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md).</span></span>

2.  <span data-ttu-id="bad7f-109">PowerShell 本体を開くには、[**開始**] をクリックし、「 **powershell**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="bad7f-110">**[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span>

3.  <span data-ttu-id="bad7f-111">PowerShell コンソールを使用して、次のように入力します: **import-module appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="bad7f-111">Using the PowerShell console, type the following: **import-module appvsequencer**.</span></span>

4.  <span data-ttu-id="bad7f-112">パッケージを作成するには、 **AppvSequencerPackage**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-112">To create a package, use the **New-AppvSequencerPackage** cmdlet.</span></span> <span data-ttu-id="bad7f-113">パッケージを作成するには、次のパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad7f-113">The following parameters are required to create a package:</span></span>

    -   <span data-ttu-id="bad7f-114">**Name** -パッケージの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-114">**Name** - specifies the name of the package.</span></span>

    -   <span data-ttu-id="bad7f-115">**Primaryvirtualapplicationdirectory** -アプリケーションのインストールに使用するディレクトリへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-115">**PrimaryVirtualApplicationDirectory** - specifies the path to the directory that will be used to install the application.</span></span> <span data-ttu-id="bad7f-116">このパスは存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad7f-116">This path must exist.</span></span>

    -   <span data-ttu-id="bad7f-117">**Installer** -関連するアプリケーションインストーラーへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-117">**Installer** - specifies the path to the associated application installer.</span></span>

    -   <span data-ttu-id="bad7f-118">**Path** : パッケージの出力ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-118">**Path** - specifies the output directory for the package.</span></span>

    <span data-ttu-id="bad7f-119">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-119">For example:</span></span>

    **<span data-ttu-id="bad7f-120">New-AppvSequencerPackage –パッケージ &lt; &gt; ルート-primaryvirtualapplicationdirectory path へのパッケージルートへの名前の名前。 &lt; &gt; &lt; &gt; &lt; 出力パスのインストーラの実行可能ファイルへのインストーラーパス&gt;</span><span class="sxs-lookup"><span data-stu-id="bad7f-120">New-AppvSequencerPackage –Name &lt;name of Package&gt; -PrimaryVirtualApplicationDirectory &lt;path to the package root&gt; -Installer &lt;path to the installer executable&gt; -OutputPath &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="bad7f-121">Sequencer がパッケージを作成するまで待ちます。</span><span class="sxs-lookup"><span data-stu-id="bad7f-121">Wait for the sequencer to create the package.</span></span> <span data-ttu-id="bad7f-122">PowerShell を使用してパッケージを作成するには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="bad7f-122">Creating a package using PowerShell can take time.</span></span> <span data-ttu-id="bad7f-123">パッケージが正常に作成されなかった場合は、エラーが返されます。</span><span class="sxs-lookup"><span data-stu-id="bad7f-123">If the package was not created successfully an error will be returned.</span></span>

    <span data-ttu-id="bad7f-124">次の一覧は、 **AppvSequencerPackage**コマンドレットで使用できるその他のオプションのパラメーターを示しています。</span><span class="sxs-lookup"><span data-stu-id="bad7f-124">The following list displays additional optional parameters that can be used with **New-AppvSequencerPackage** cmdlet:</span></span>

    -   <span data-ttu-id="bad7f-125">AcceleratorFilePath –パッケージを生成するための、accelerator ファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-125">AcceleratorFilePath – specifies the path to the accelerator .cab file to generate a package.</span></span>

    -   <span data-ttu-id="bad7f-126">[インストールされているファイルのパス-ローカルにインストールされたファイルが保存される場所へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-126">InstalledFilesPath - specifies the path to where the local installed files of the application are saved.</span></span>

    -   <span data-ttu-id="bad7f-127">InstallMediaPath-インストールメディアが保存されている場所のパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-127">InstallMediaPath - specifies the path to where the installation media is</span></span>

    -   <span data-ttu-id="bad7f-128">TemplateFilePath: シーケンス処理をカスタマイズする場合は、テンプレートファイルへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-128">TemplateFilePath - specifies the path to a template file if you want to customize the sequencing process.</span></span>

    -   <span data-ttu-id="bad7f-129">FullLoad-アプリを開く前に、5.0 アプリを実行しているコンピューターにパッケージを完全にダウンロードする必要があることを指定します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-129">FullLoad - specifies that the package must be fully downloaded to the computer running the App-V 5.0 before it can be opened.</span></span>

    <span data-ttu-id="bad7f-130">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="bad7f-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="bad7f-131">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="bad7f-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="bad7f-132">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="bad7f-132">Got an App-V issue?</span></span>** <span data-ttu-id="bad7f-133">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bad7f-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bad7f-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bad7f-134">Related topics</span></span>


[<span data-ttu-id="bad7f-135">PowerShell を使用した App-V の管理</span><span class="sxs-lookup"><span data-stu-id="bad7f-135">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





