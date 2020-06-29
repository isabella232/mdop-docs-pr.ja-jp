---
title: APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法
description: APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法
author: dansimp
ms.assetid: 0d1f6768-be30-4682-8eeb-aa95918b24c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d54e68caa380025b2ff6f3ea79d30f275b589b30
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814330"
---
# <span data-ttu-id="fd3ec-103">APP-V 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法</span><span class="sxs-lookup"><span data-stu-id="fd3ec-103">How to Create a Custom Configuration File by Using the App-V 5.0 Management Console</span></span>


<span data-ttu-id="fd3ec-104">動的構成を使用して、特定のユーザーに対して App-v 5.0 パッケージをカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-104">You can use a dynamic configuration to customize an App-V 5.0 package for a specific user.</span></span> <span data-ttu-id="fd3ec-105">ただし、ファイルを使用するには、まず動的ユーザー構成 (.xml) ファイルまたは動的な展開構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-105">However, you must first create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use the files.</span></span> <span data-ttu-id="fd3ec-106">ファイルの作成は、高度な手動操作です。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-106">Creation of the file is an advanced manual operation.</span></span> <span data-ttu-id="fd3ec-107">動的ユーザー構成ファイルの一般的な情報については、「 [app-v 5.0 の動的構成につい](about-app-v-50-dynamic-configuration.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-107">For general information about dynamic user configuration files, see, [About App-V 5.0 Dynamic Configuration](about-app-v-50-dynamic-configuration.md).</span></span>

<span data-ttu-id="fd3ec-108">次の手順を使用して、App-v 5.0 管理コンソールを使用して動的なユーザー構成ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-108">Use the following procedure to create a Dynamic User Configuration file by using the App-V 5.0 Management console.</span></span>

**<span data-ttu-id="fd3ec-109">動的ユーザー構成ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="fd3ec-109">To create a Dynamic User Configuration file</span></span>**

1.  <span data-ttu-id="fd3ec-110">表示するパッケージの名前を右クリックし、[ **active directory アクセスの編集**] を選択して、特定のユーザーグループに割り当てられている構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-110">Right-click the name of the package that you want to view and select **Edit active directory access** to view the configuration that is assigned to a given user group.</span></span> <span data-ttu-id="fd3ec-111">または、パッケージを選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-111">Alternatively, select the package, and click **Edit**.</span></span>

2.  <span data-ttu-id="fd3ec-112">**アクセス権のある広告エンティティ**のリストを使用して、カスタマイズする広告グループを選びます。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-112">Using the list of **AD Entities with Access**, select the AD group that you want to customize.</span></span> <span data-ttu-id="fd3ec-113">選択されていない場合は、ドロップダウンリストから [**カスタム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-113">Select **Custom** from the drop-down list, if it is not already selected.</span></span> <span data-ttu-id="fd3ec-114">[ **Edit** ] という名前のリンクが表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-114">A link named **Edit** will be displayed.</span></span>

3.  <span data-ttu-id="fd3ec-115">**[編集]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-115">Click **Edit**.</span></span> <span data-ttu-id="fd3ec-116">広告グループに割り当てられている動的なユーザー構成が表示されます。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-116">The Dynamic User Configuration that is assigned to the AD Group will be displayed.</span></span>

4.  <span data-ttu-id="fd3ec-117">[**詳細設定**] をクリックし、[**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-117">Click **Advanced**, and then click **Export Configuration**.</span></span> <span data-ttu-id="fd3ec-118">ファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-118">Type in a filename and click **Save**.</span></span> <span data-ttu-id="fd3ec-119">これで、ファイルを編集してユーザーのパッケージを構成できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-119">Now you can edit the file to configure a package for a user.</span></span>

    <span data-ttu-id="fd3ec-120">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-120">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="fd3ec-121">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-121">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="fd3ec-122">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="fd3ec-122">Got an App-V issue?</span></span>** <span data-ttu-id="fd3ec-123">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="fd3ec-123">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="fd3ec-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fd3ec-124">Related topics</span></span>


[<span data-ttu-id="fd3ec-125">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="fd3ec-125">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





