---
title: アプリケーションの仮想化アプリケーションで UE-V を使用する
description: アプリケーションの仮想化アプリケーションで UE-V を使用する
author: dansimp
ms.assetid: 4644b810-fc48-4fd0-96e4-2fc6cd64d8ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221d21c5815b36b57a04a0299352e5fe64f657c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827274"
---
# <span data-ttu-id="8f34a-103">アプリケーションの仮想化アプリケーションで UE-V を使用する</span><span class="sxs-lookup"><span data-stu-id="8f34a-103">Using UE-V 2.x with Application Virtualization Applications</span></span>


<span data-ttu-id="8f34a-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 は、App-v パッケージまたは UE-V のテンプレートに必要な変更を加えずに、Microsoft Application Virtualization (App-v) アプリケーションをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f34a-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 support Microsoft Application Virtualization (App-V) applications without any required modifications to either the App-V package or the UE-V template.</span></span> <span data-ttu-id="8f34a-105">ただし、仮想化された App-v アプリケーションで直接 UE-V Generator を実行することはできないため、追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f34a-105">However, an additional step is required because you cannot run the UE-V Generator directly on a virtualized App-V application.</span></span> <span data-ttu-id="8f34a-106">代わりに、アプリケーションをローカルにインストールして、テンプレートを生成し、仮想化されたアプリケーションにテンプレートを適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f34a-106">Instead, you must install the application locally, generate the template, and then apply the template to the virtualized application.</span></span> <span data-ttu-id="8f34a-107">UE-V は、app-v 4.5、App-v 4.6、および App-v 5.0 パッケージをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="8f34a-107">UE-V supports App-V 4.5, App-V 4.6, and App-V 5.0 packages.</span></span>

## <span data-ttu-id="8f34a-108">App-v アプリケーションの UE-V 設定の同期</span><span class="sxs-lookup"><span data-stu-id="8f34a-108">UE-V settings synchronization for App-V applications</span></span>


<span data-ttu-id="8f34a-109">UE-V は、アプリケーションがローカルにインストールされているか、またはアプリケーションがローカルにインストールされているかにかかわらず、アプリがプログラム名によって開かれているかどうかを監視します。</span><span class="sxs-lookup"><span data-stu-id="8f34a-109">UE-V monitors when an application opens by the program name and, optionally, by file version numbers and product version numbers, whether the application is installed locally or virtually by using App-V.</span></span> <span data-ttu-id="8f34a-110">UE-V は、アプリケーションが起動すると、App-v のプロセスを監視し、ユーザーの設定の記憶域のパスに保存されているすべての設定を適用して、アプリケーションを正常に起動できるようにします。</span><span class="sxs-lookup"><span data-stu-id="8f34a-110">When the application starts, UE-V monitors the App-V process, applies any settings that are stored in the user's settings storage path, and then enables the application to start normally.</span></span> <span data-ttu-id="8f34a-111">UE-V では、app-v アプリケーションを監視し、関連するファイルとレジストリパスを仮想化された場所に自動的に変換します。これは、アプリ間の物理的な場所とは異なります。</span><span class="sxs-lookup"><span data-stu-id="8f34a-111">UE-V monitors App-V applications and automatically translates the relevant file and registry paths to the virtualized location as opposed to the physical location outside the App-V computing environment.</span></span>

 **<span data-ttu-id="8f34a-112">仮想化されたアプリケーションの設定の同期を実装するには</span><span class="sxs-lookup"><span data-stu-id="8f34a-112">To implement settings synchronization for a virtualized application</span></span>**

1.  <span data-ttu-id="8f34a-113">UE-V Generator を実行して、コンピューター間で設定を同期するローカルにインストールされたアプリケーションの設定を収集します。</span><span class="sxs-lookup"><span data-stu-id="8f34a-113">Run the UE-V Generator to collect the settings of the locally installed application whose settings you want to synchronize between computers.</span></span> <span data-ttu-id="8f34a-114">このプロセスでは、設定場所テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="8f34a-114">This process creates a settings location template.</span></span> <span data-ttu-id="8f34a-115">Microsoft Office 2010 テンプレートなどの組み込みテンプレートを使用している場合は、この手順をスキップしてください。</span><span class="sxs-lookup"><span data-stu-id="8f34a-115">If you use a built-in template such as the Microsoft Office 2010 template, skip this step.</span></span> <span data-ttu-id="8f34a-116">UE-V Generator の実行について詳しくは、「[カスタムアプリケーションの ue-v の展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8f34a-116">For more information about running the UE-V Generator, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#createcustomtemplates).</span></span>

2.  <span data-ttu-id="8f34a-117">まだ実行していない場合は、App-v アプリケーションパッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8f34a-117">Install the App-V application package if you have not already done so.</span></span>

3.  <span data-ttu-id="8f34a-118">設定テンプレートカタログの場所にテンプレートを発行するか、Windows PowerShell コマンドレットを使用してテンプレートを手動でインストールし `Register-UEVTemplate` ます。</span><span class="sxs-lookup"><span data-stu-id="8f34a-118">Publish the template to the location of your settings template catalog or manually install the template by using the `Register-UEVTemplate` Windows PowerShell cmdlet.</span></span>

    <span data-ttu-id="8f34a-119">**注** 新しく作成したテンプレートを設定テンプレートカタログに発行する場合、同期プロバイダーが設定を更新するまで、クライアントはテンプレートを受け取りません。</span><span class="sxs-lookup"><span data-stu-id="8f34a-119">**Note** If you publish the newly created template to the settings template catalog, the client does not receive the template until the sync provider updates the settings.</span></span> <span data-ttu-id="8f34a-120">このプロセスを手動で開始するには、**タスクスケジューラ**を開き、[**タスクスケジューラライブラリ**]、[ **Microsoft**]、[ **ue-v**] の順に展開します。</span><span class="sxs-lookup"><span data-stu-id="8f34a-120">To manually start this process, open **Task Scheduler**, expand **Task Scheduler Library**, expand **Microsoft**, and expand **UE-V**.</span></span> <span data-ttu-id="8f34a-121">[結果] ウィンドウで、[**テンプレートの自動更新**] を右クリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8f34a-121">In the results pane, right-click **Template Auto Update**, and then click **Run**.</span></span>

     

4.  <span data-ttu-id="8f34a-122">App-v パッケージを起動します。</span><span class="sxs-lookup"><span data-stu-id="8f34a-122">Start the App-V package.</span></span>






## <span data-ttu-id="8f34a-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8f34a-123">Related topics</span></span>


[<span data-ttu-id="8f34a-124">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="8f34a-124">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





