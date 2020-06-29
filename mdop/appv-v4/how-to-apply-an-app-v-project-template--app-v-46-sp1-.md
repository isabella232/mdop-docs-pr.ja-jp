---
title: App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)
description: App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 8ef120ab-8cfb-438c-8136-671167b7bd9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5b5f04f3f31838bfb13c19eee5f2314c3a3d291f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821374"
---
# <span data-ttu-id="278b9-103">App-V プロジェクト テンプレートを適用する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="278b9-103">How to Apply an App-V Project Template (App-V 4.6 SP1)</span></span>


<span data-ttu-id="278b9-104">App-v プロジェクトテンプレートを使用して、既存の仮想アプリケーションパッケージに関連する一般的な設定を新しい仮想アプリケーションパッケージに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="278b9-104">You can use an App-V project template to apply common settings associated with an existing virtual application package to a new virtual application package.</span></span> <span data-ttu-id="278b9-105">App-v プロジェクトテンプレートを使用すると、アプリケーションのシーケンス処理を開始する前に、共通の設定を構成することで、仮想アプリケーションパッケージの作成プロセスを効率化できます。</span><span class="sxs-lookup"><span data-stu-id="278b9-105">Using App-V project templates can help streamline the process of creating virtual application packages by configuring common settings before you begin sequencing an application.</span></span>

<span data-ttu-id="278b9-106">**注** 新しい仮想アプリケーションパッケージを作成する場合にのみ、App-v プロジェクトテンプレートを適用できます。</span><span class="sxs-lookup"><span data-stu-id="278b9-106">**Note** You can only apply an App-V project template when you are creating a new virtual application package.</span></span> <span data-ttu-id="278b9-107">既存の仮想アプリケーションパッケージへのプロジェクトテンプレートの適用はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="278b9-107">Applying project templates to existing virtual application packages is not supported.</span></span> <span data-ttu-id="278b9-108">さらに、プロジェクトテンプレートをパッケージアクセラレータと組み合わせて使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="278b9-108">Additionally, you cannot use a project template in conjunction with a Package Accelerator.</span></span>

 

<span data-ttu-id="278b9-109">App-v プロジェクトテンプレートの作成について詳しくは、「app-v[プロジェクトテンプレートを作成する (app-v 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="278b9-109">For more information about creating App-V project templates, see [How to Create an App-V Project Template (App-V 4.6 SP1)](how-to-create-an-app-v-project-template--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="278b9-110">App-v プロジェクトテンプレートを適用するには</span><span class="sxs-lookup"><span data-stu-id="278b9-110">To apply an App-V project template</span></span>**

1.  <span data-ttu-id="278b9-111">Microsoft application virtualization sequencer を起動するには、app-v sequencer がインストールされているコンピューターで、[すべてのプログラムを**起動**する] をクリックし  /  **All Programs**  /  ます。**microsoft**application virtualization  /  **microsoft application virtualization Sequencer**。</span><span class="sxs-lookup"><span data-stu-id="278b9-111">To start the Microsoft Application Virtualization Sequencer, on the computer on which App-V Sequencer is installed, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="278b9-112">App-v プロジェクトテンプレートを使用して新しい仮想アプリケーションパッケージを作成するには、 **File**[  /  **テンプレートからのファイルの新規**作成] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="278b9-112">To create a new virtual application package by using an App-V project template, click **File** / **New From Template**.</span></span>

3.  <span data-ttu-id="278b9-113">使用するプロジェクトテンプレートを選択するには、プロジェクトテンプレートが保存されているディレクトリを参照し、プロジェクトテンプレートを選択して、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="278b9-113">To select the project template that you want to use, browse to the directory where the project template is saved, select the project template, and then click **Open**.</span></span>

4.  <span data-ttu-id="278b9-114">新しい仮想アプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="278b9-114">Create the new virtual application package.</span></span> <span data-ttu-id="278b9-115">指定したテンプレートと共に保存された設定が、作成する新しい仮想アプリケーションパッケージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="278b9-115">The settings saved with the specified template will be applied to the new virtual application package that you are creating.</span></span> <span data-ttu-id="278b9-116">新しい仮想アプリケーションパッケージの作成の詳細については、「[シーケンスするアプリケーションの種類 (app-v 4.6 SP1) を決定する方法](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)」および該当する手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="278b9-116">For more information about creating a new virtual application package, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md), and select the appropriate procedure.</span></span>

## <span data-ttu-id="278b9-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="278b9-117">Related topics</span></span>


[<span data-ttu-id="278b9-118">Application Virtualization Sequencer のタスク (APP-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="278b9-118">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="278b9-119">App-V プロジェクト テンプレートを作成する方法 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="278b9-119">How to Create an App-V Project Template (App-V 4.6 SP1)</span></span>](how-to-create-an-app-v-project-template--app-v-46-sp1-.md)

 

 





