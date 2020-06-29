---
title: プロジェクト テンプレートを作成して使用する方法
description: プロジェクト テンプレートを作成して使用する方法
author: dansimp
ms.assetid: e5ac1dc8-a88f-4b16-8e3c-df07ef5e4c3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de3471eca39d3804e8c5f070c5ec37560fae5dc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814250"
---
# <span data-ttu-id="f2dd3-103">プロジェクト テンプレートを作成して使用する方法</span><span class="sxs-lookup"><span data-stu-id="f2dd3-103">How to Create and Use a Project Template</span></span>


<span data-ttu-id="f2dd3-104">App-v 5.1 プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連付けられている一般的に適用される設定を保存することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-104">You can use an App-V 5.1 project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="f2dd3-105">これらの設定は、環境に新しい仮想アプリケーションパッケージを作成するときに適用できます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-105">These settings can then be applied when you create new virtual application packages in your environment.</span></span> <span data-ttu-id="f2dd3-106">プロジェクトテンプレートを使うと、仮想アプリケーションパッケージの作成プロセスを効率化することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-106">Using a project template can streamline the process of creating virtual application packages.</span></span>

**<span data-ttu-id="f2dd3-107">注</span><span class="sxs-lookup"><span data-stu-id="f2dd3-107">Note</span></span>**  
<span data-ttu-id="f2dd3-108">パッケージのアップグレード中に、場合によっては、App-v 5.1 プロジェクトテンプレートを適用することができます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-108">You can, and often should apply an App-V 5.1 project template during a package upgrade.</span></span> <span data-ttu-id="f2dd3-109">たとえば、カスタムの除外リストを使ってアプリケーションをシーケンスした場合、関連付けられたテンプレートを作成して保存してから、シーケンス処理されたアプリケーションのアップグレード中に使用できるようにすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-109">For example, if you sequenced an application with a custom exclusion list, it is recommended that an associated template is created and saved for later use while upgrading the sequenced application.</span></span>



<span data-ttu-id="f2dd3-110">App-v 5.1 のプロジェクトテンプレートは、app-v の5.1 アプリケーションアクセラレータがアプリケーション固有であり、App-v の5.1 プロジェクトテンプレートを複数のアプリケーションに適用できるため、app-v 5.1 アプリケーションアクセラレータとは異なります。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-110">App-V 5.1 project templates differ from App-V 5.1 Application Accelerators because App-V 5.1 Application Accelerators are application-specific, and App-V 5.1 project templates can be applied to multiple applications.</span></span>

<span data-ttu-id="f2dd3-111">新しいテンプレートを作成して適用するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-111">Use the following procedures to create and apply a new template.</span></span>

**<span data-ttu-id="f2dd3-112">プロジェクトテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="f2dd3-112">To create a project template</span></span>**

1.  <span data-ttu-id="f2dd3-113">Sequencer を実行しているコンピューターで app-v 5.1 sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-113">To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  **<span data-ttu-id="f2dd3-114">注</span><span class="sxs-lookup"><span data-stu-id="f2dd3-114">Note</span></span>**  
    <span data-ttu-id="f2dd3-115">現在、仮想アプリケーションパッケージが App-v 5.1 Sequencer コンソールで開かれている場合は、手順3に進んでください。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-115">If the virtual application package is currently open in the App-V 5.1 Sequencer console, skip to step 3 of this procedure.</span></span>



~~~
To open the existing virtual application package that contains the settings you want to save with the App-V 5.1 project template, click **File** / **Open**, and then click **Edit Package**. On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open. Click **Edit**.
~~~

3. <span data-ttu-id="f2dd3-116">App-v 5.1 Sequencer コンソールでテンプレートファイルを保存するには、[ファイルを**File**  /  **テンプレートとして保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-116">In the App-V 5.1 Sequencer console, to save the template file, click **File** / **Save As Template**.</span></span> <span data-ttu-id="f2dd3-117">新しいテンプレートと共に保存される設定を確認したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-117">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="f2dd3-118">新しい App-v 5.1 プロジェクトテンプレートに関連付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-118">Specify a name that will be associated with the new App-V 5.1 project template.</span></span> <span data-ttu-id="f2dd3-119">[保存] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-119">Click Save.</span></span>

   <span data-ttu-id="f2dd3-120">新しい App-v 5.1 プロジェクトテンプレートは、この手順の手順3で指定したディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-120">The new App-V 5.1 project template is saved in the directory specified in step 3 of this procedure.</span></span>

**<span data-ttu-id="f2dd3-121">プロジェクトテンプレートを適用するには</span><span class="sxs-lookup"><span data-stu-id="f2dd3-121">To apply a project template</span></span>**

1.  **<span data-ttu-id="f2dd3-122">重要</span><span class="sxs-lookup"><span data-stu-id="f2dd3-122">Important</span></span>**  
    <span data-ttu-id="f2dd3-123">プロジェクトテンプレートを使用して、パッケージアクセラレータと組み合わせて仮想アプリケーションパッケージを作成することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-123">Creating a virtual application package using a project template in conjunction with a Package Accelerator is not supported.</span></span>



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="f2dd3-124">App-v 5.1 プロジェクトテンプレートを使用して新しい仮想アプリケーションパッケージを作成またはアップグレードするには **、[**  /  **テンプレートから新規**作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-124">To create or upgrade a new virtual application package by using an App-V 5.1 project template, click **File** / **New From Template**.</span></span>

3. <span data-ttu-id="f2dd3-125">使用するプロジェクトテンプレートを選択するには、プロジェクトテンプレートが保存されているディレクトリを参照し、プロジェクトテンプレートを選択して、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-125">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

   <span data-ttu-id="f2dd3-126">新しい仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-126">Create the new virtual application package.</span></span> <span data-ttu-id="f2dd3-127">指定したテンプレートと共に保存された設定が、作成する新しい仮想アプリケーションパッケージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-127">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span>

   <span data-ttu-id="f2dd3-128">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-128">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f2dd3-129">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-129">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="f2dd3-130">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="f2dd3-130">Got an App-V issue?</span></span>** <span data-ttu-id="f2dd3-131">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="f2dd3-131">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="f2dd3-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f2dd3-132">Related topics</span></span>


[<span data-ttu-id="f2dd3-133">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="f2dd3-133">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









