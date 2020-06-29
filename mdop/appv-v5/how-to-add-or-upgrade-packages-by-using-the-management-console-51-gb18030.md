---
title: 管理コンソールを使用してパッケージを追加またはアップグレードする方法
description: 管理コンソールを使用してパッケージを追加またはアップグレードする方法
author: dansimp
ms.assetid: 62417b63-06b2-437c-8584-523e1dea97c3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4ac458a5e33b83e19d72fee39cf837aa6bd57bc5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814483"
---
# <span data-ttu-id="95bb9-103">管理コンソールを使用してパッケージを追加またはアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="95bb9-103">How to Add or Upgrade Packages by Using the Management Console</span></span>


<span data-ttu-id="95bb9-104">次の手順に従って、パッケージをアプリ-V 5.1 管理コンソールに追加またはアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-104">You can the following procedure to add or upgrade a package to the App-V 5.1 Management Console.</span></span> <span data-ttu-id="95bb9-105">管理コンソールに既に存在するパッケージをアップグレードするには、次の手順に従って、同じパッケージ**名**を使用してアップグレードされたパッケージをインポートします。</span><span class="sxs-lookup"><span data-stu-id="95bb9-105">To upgrade a package that already exists in the Management Console, use the following steps and import the upgraded package using the same package **Name**.</span></span>

**<span data-ttu-id="95bb9-106">管理コンソールにパッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="95bb9-106">To add a package to the Management Console</span></span>**

1.  <span data-ttu-id="95bb9-107">管理コンソールディスプレイのナビゲーションウィンドウで [**パッケージ**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="95bb9-107">Click the **Packages** tab in the navigation pane of the Management Console display.</span></span>

    <span data-ttu-id="95bb9-108">コンソールには、各パッケージに関する状態情報と共にサーバーに追加されたパッケージの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-108">The console displays the list of packages that have been added to the server along with status information about each package.</span></span> <span data-ttu-id="95bb9-109">パッケージを選択すると、パッケージの詳細情報が [**パッケージ**] ウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-109">When a package is selected, detailed information about the package is displayed in the **PACKAGES** pane.</span></span>

    <span data-ttu-id="95bb9-110">[**グループ**解除] ドロップダウンリストボックスをクリックし、コンソールでパッケージをどのように表示するかを指定します。</span><span class="sxs-lookup"><span data-stu-id="95bb9-110">Click the **Ungrouped** drop-down list box and specify how the packages are to be displayed in the console.</span></span> <span data-ttu-id="95bb9-111">関連する列見出しをクリックして、パッケージを並べ替えることもできます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-111">You can also click the associated column header to sort the packages.</span></span>

2.  <span data-ttu-id="95bb9-112">追加するパッケージを指定するには、[**パッケージの追加またはアップグレード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95bb9-112">To specify the package you want to add, click **Add or Upgrade Packages**.</span></span>

3.  <span data-ttu-id="95bb9-113">追加するパッケージの完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="95bb9-113">Type the full path to the package that you want to add.</span></span> <span data-ttu-id="95bb9-114">UNC または HTTP パス形式 ( **\\\\servername\\sharename\\foldername\\packagename.appv**など) を使用し、[ **http://server.1234/file.appv** **追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="95bb9-114">Use the UNC or HTTP path format, for example **\\\\servername\\sharename\\foldername\\packagename.appv** or **http://server.1234/file.appv**, and then click **Add**.</span></span>

    <span data-ttu-id="95bb9-115">**重要** ファイル名拡張子が**appv**のパッケージを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="95bb9-115">**Important** You must select a package with the **.appv** file name extension.</span></span>

     

4.  <span data-ttu-id="95bb9-116">ページには、 \*\* &lt; &gt; Packagename を追加\*\*している状態のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-116">The page displays the status message **Adding &lt;Packagename&gt;**.</span></span> <span data-ttu-id="95bb9-117">[**インポートの状態**] をクリックして、インポートしたパッケージの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="95bb9-117">Click **IMPORT STATUS** to check the status of a package that you have imported.</span></span>

    <span data-ttu-id="95bb9-118">[ **OK]** をクリックしてパッケージを追加し、[**パッケージの追加**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-118">Click **OK** to add the package and close the **Add Package** page.</span></span> <span data-ttu-id="95bb9-119">インポート中にエラーが発生した場合は、パッケージの**インポート**ページで [**詳細**] をクリックして、詳細を参照してください。</span><span class="sxs-lookup"><span data-stu-id="95bb9-119">If there was an error during the import, click **Detail** on the **Package Import** page for more information.</span></span> <span data-ttu-id="95bb9-120">新しく追加されたパッケージが [**パッケージ**] ウィンドウで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="95bb9-120">The newly added package is now available in the **PACKAGES** pane.</span></span>

5.  <span data-ttu-id="95bb9-121">[**閉じる**] をクリックして、[**パッケージの追加またはアップグレード**] ページを閉じます。</span><span class="sxs-lookup"><span data-stu-id="95bb9-121">Click **Close** to close the **Add or Upgrade Packages** page.</span></span>

    <span data-ttu-id="95bb9-122">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="95bb9-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="95bb9-123">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="95bb9-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="95bb9-124">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="95bb9-124">Got an App-V issue?</span></span>** <span data-ttu-id="95bb9-125">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="95bb9-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="95bb9-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="95bb9-126">Related topics</span></span>


[<span data-ttu-id="95bb9-127">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="95bb9-127">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





