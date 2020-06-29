---
title: APP-V 5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法
description: APP-V 5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法
author: dansimp
ms.assetid: f5ab426a-f49a-47b3-93f3-b9d60aada8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 282207b5424442950e88c40a372194e9def768cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814323"
---
# <span data-ttu-id="fe61a-103">APP-V 5.1 管理コンソールを使用してカスタム構成ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fe61a-103">How to Create a Custom Configuration File by Using the App-V 5.1 Management Console</span></span>


<span data-ttu-id="fe61a-104">動的構成を使用して、特定のユーザーに対して App-v 5.1 パッケージをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe61a-104">You can use a dynamic configuration to customize an App-V 5.1 package for a specific user.</span></span> <span data-ttu-id="fe61a-105">ただし、ファイルを使用するには、まず動的ユーザー構成 (.xml) ファイルまたは動的な展開構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe61a-105">However, you must first create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use the files.</span></span> <span data-ttu-id="fe61a-106">ファイルの作成は、高度な手動操作です。</span><span class="sxs-lookup"><span data-stu-id="fe61a-106">Creation of the file is an advanced manual operation.</span></span> <span data-ttu-id="fe61a-107">動的ユーザー構成ファイルの一般的な情報については、「 [app-v 5.1 の動的構成につい](about-app-v-51-dynamic-configuration.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe61a-107">For general information about dynamic user configuration files, see, [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md).</span></span>

<span data-ttu-id="fe61a-108">次の手順を使用して、App-v 5.1 管理コンソールを使用して動的なユーザー構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fe61a-108">Use the following procedure to create a Dynamic User Configuration file by using the App-V 5.1 Management console.</span></span>

**<span data-ttu-id="fe61a-109">動的ユーザー構成ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="fe61a-109">To create a Dynamic User Configuration file</span></span>**

1.  <span data-ttu-id="fe61a-110">表示するパッケージの名前を右クリックし、[ **active directory アクセスの編集**] を選択して、特定のユーザーグループに割り当てられている構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="fe61a-110">Right-click the name of the package that you want to view and select **Edit active directory access** to view the configuration that is assigned to a given user group.</span></span> <span data-ttu-id="fe61a-111">または、パッケージを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe61a-111">Alternatively, select the package, and click **Edit**.</span></span>

2.  <span data-ttu-id="fe61a-112">**アクセス権のある広告エンティティ**のリストを使用して、カスタマイズする広告グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="fe61a-112">Using the list of **AD Entities with Access**, select the AD group that you want to customize.</span></span> <span data-ttu-id="fe61a-113">選択されていない場合は、ドロップダウンリストから [**カスタム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fe61a-113">Select **Custom** from the drop-down list, if it is not already selected.</span></span> <span data-ttu-id="fe61a-114">[ **Edit** ] という名前のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe61a-114">A link named **Edit** will be displayed.</span></span>

3.  <span data-ttu-id="fe61a-115">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe61a-115">Click **Edit**.</span></span> <span data-ttu-id="fe61a-116">広告グループに割り当てられている動的なユーザー構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fe61a-116">The Dynamic User Configuration that is assigned to the AD Group will be displayed.</span></span>

4.  <span data-ttu-id="fe61a-117">[**詳細設定**] をクリックし、[**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe61a-117">Click **Advanced**, and then click **Export Configuration**.</span></span> <span data-ttu-id="fe61a-118">ファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe61a-118">Type in a filename and click **Save**.</span></span> <span data-ttu-id="fe61a-119">これで、ファイルを編集してユーザーのパッケージを構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fe61a-119">Now you can edit the file to configure a package for a user.</span></span>

    **<span data-ttu-id="fe61a-120">注</span><span class="sxs-lookup"><span data-stu-id="fe61a-120">Note</span></span>**  
    <span data-ttu-id="fe61a-121">Windows Server で実行中に構成をエクスポートするには、"IE 強化セキュリティ構成" を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe61a-121">To export a configuration while running on Windows Server, you must disable "IE Enhanced Security Configuration".</span></span> <span data-ttu-id="fe61a-122">この機能が有効になっていて、[ダウンロードをブロックする] に設定されている場合、App-v Server からダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="fe61a-122">If this is enabled and set to block downloads, you cannot download anything from the App-V Server.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="fe61a-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe61a-123">Related topics</span></span>


[<span data-ttu-id="fe61a-124">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="fe61a-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









