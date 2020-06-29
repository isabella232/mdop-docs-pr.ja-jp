---
title: App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)
description: App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 7e87fba2-b72a-4bc9-92b8-220e25aae99a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4e264d5c41b663bc9c450dc642e2b26297ee7ea1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817647"
---
# <span data-ttu-id="c621a-103">App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="c621a-103">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="c621a-104">App-v プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連付けられた、一般的に適用される設定を保存できます。</span><span class="sxs-lookup"><span data-stu-id="c621a-104">You can use an App-V project template to save commonly applied settings associated with an existing virtual application package.</span></span> <span data-ttu-id="c621a-105">これらの設定は、仮想アプリケーションパッケージの作成プロセスを合理化するための新しい仮想アプリケーションパッケージを環境で作成するときに適用できます。</span><span class="sxs-lookup"><span data-stu-id="c621a-105">These settings can then be applied when you create new virtual application packages in your environment which can help streamline the process of creating virtual application packages.</span></span>

<span data-ttu-id="c621a-106">**注** 新しい仮想アプリケーションパッケージを作成する場合にのみ、App-v プロジェクトテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="c621a-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="c621a-107">既存の仮想アプリケーションパッケージへのプロジェクトテンプレートの適用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="c621a-107">Applying project templates to existing virtual application packages is not supported.</span></span>

 

<span data-ttu-id="c621a-108">App-v プロジェクトテンプレートの適用の詳細については、「app-v[プロジェクトテンプレートを適用する方法 (app-v 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c621a-108">For more information about applying an App-V project template, see [How to Apply an App-V Project Template (App-V 4.6 SP1)](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

<span data-ttu-id="c621a-109">App-v のプロジェクトテンプレートは、アプリケーション固有であり、app-v プロジェクトテンプレートを複数のアプリケーションに適用できるため、App-v アプリケーションアクセラレータとは異なります。</span><span class="sxs-lookup"><span data-stu-id="c621a-109">App-V project templates differ from App-V Application Accelerators because App-V Application Accelerators are application-specific, and App-V project templates can be applied to multiple applications.</span></span> <span data-ttu-id="c621a-110">また、パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する場合、プロジェクトテンプレートを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="c621a-110">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span>

<span data-ttu-id="c621a-111">次の一般的な設定は、App-v プロジェクトテンプレートと共に保存されます。</span><span class="sxs-lookup"><span data-stu-id="c621a-111">The following general settings are saved with an App-V project template:</span></span>

-   <span data-ttu-id="c621a-112">**高度な監視オプション**。</span><span class="sxs-lookup"><span data-stu-id="c621a-112">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="c621a-113">監視中に Microsoft Update が実行されるようにし**ます。**</span><span class="sxs-lookup"><span data-stu-id="c621a-113">Enables Microsoft Update to run during monitoring, Rebase **.dll’s**.</span></span>

-   <span data-ttu-id="c621a-114">**パッケージ展開の設定**。</span><span class="sxs-lookup"><span data-stu-id="c621a-114">**Package Deployment Settings**.</span></span> <span data-ttu-id="c621a-115">**プロトコル**、**ホスト名**、**ポート**、**パス**、**オペレーティングシステム**、**セキュリティ記述子の強制**、 **MSI の作成**、パッケージの**圧縮**が含まれます。</span><span class="sxs-lookup"><span data-stu-id="c621a-115">Contains **Protocol**, **Host Name**, **Port**, **Path**, **Operating Systems**, **Enforce Security Descriptors**, **Create MSI**, **Compress Package**.</span></span>

-   <span data-ttu-id="c621a-116">**[全般] オプション**。</span><span class="sxs-lookup"><span data-stu-id="c621a-116">**General Options**.</span></span> <span data-ttu-id="c621a-117">**Microsoft Windows Installer (MSI)** パッケージを生成し、**イベントの仮想化**、**サービスの仮想**化、**ファイル名へのパッケージバージョンの追加**を許可します。</span><span class="sxs-lookup"><span data-stu-id="c621a-117">Allows you to **Generate Microsoft Windows Installer (MSI)** package, **Allow Virtualization of Events**, **Allow Virtualization of Services**, **Append Package Version to Filename**.</span></span>

-   <span data-ttu-id="c621a-118">**除外項目**。</span><span class="sxs-lookup"><span data-stu-id="c621a-118">**Exclusion Items**.</span></span> <span data-ttu-id="c621a-119">除外パターンリストが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c621a-119">Contains the Exclusion pattern list.</span></span>

**<span data-ttu-id="c621a-120">プロジェクトテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="c621a-120">To create a project template</span></span>**

1.  <span data-ttu-id="c621a-121">App-v sequencer を実行しているコンピューターで app-v sequencer を起動するには、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="c621a-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="c621a-122">現在、仮想アプリケーションパッケージが App-v Sequencer で開かれている場合は、手順3に進んでください。</span><span class="sxs-lookup"><span data-stu-id="c621a-122">If the virtual application package is currently open in the App-V Sequencer, skip to step 3 of this procedure.</span></span> <span data-ttu-id="c621a-123">App-v プロジェクトテンプレートと共に保存する設定を含む既存の仮想アプリケーションパッケージを開くには、[**ファイル**を開く] をクリックし、  /  **Open** [**パッケージ**の**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c621a-123">To open the existing virtual application package that contains the settings you want to save with the App-V project template, click **File** / **Open** and click **Edit** **Package**.</span></span> <span data-ttu-id="c621a-124">[**パッケージの選択**] ページで [**参照**] をクリックし、開く仮想アプリケーションパッケージを探します。</span><span class="sxs-lookup"><span data-stu-id="c621a-124">On the **Select Package** page, click **Browse** and locate the virtual application package that you want to open.</span></span> <span data-ttu-id="c621a-125">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c621a-125">Click **Edit**.</span></span>

3.  <span data-ttu-id="c621a-126">App-v Sequencer コンソールで、[**ファイル**  /  **をテンプレートとして保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c621a-126">In the App-V Sequencer console, click **File** / **Save As Template**.</span></span> <span data-ttu-id="c621a-127">新しいテンプレートと共に保存される設定を確認したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c621a-127">After you have reviewed the settings that will be saved with the new template, click **OK**.</span></span> <span data-ttu-id="c621a-128">新しい App-v プロジェクトテンプレートに関連付ける名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c621a-128">Specify a name that will be associated with the new App-V project template.</span></span> <span data-ttu-id="c621a-129">**[保存]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c621a-129">Click **Save**.</span></span>

    <span data-ttu-id="c621a-130">新しい App-v プロジェクトテンプレートは、この手順の手順3で指定したディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="c621a-130">The new App-V project template is saved in the directory specified in step 3 of this procedure.</span></span>

## <span data-ttu-id="c621a-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c621a-131">Related topics</span></span>


[<span data-ttu-id="c621a-132">Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="c621a-132">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="c621a-133">App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="c621a-133">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-apply-an-app-v-project-template--app-v-46-sp1-.md)

 

 





