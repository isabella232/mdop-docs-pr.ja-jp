---
title: 管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法
description: 管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法
author: dansimp
ms.assetid: c77e6662-7a18-4da1-8da8-b58068b65fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c5a8cd5c914d1ddd720ebfef318e3a094cdc6f0b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813619"
---
# <span data-ttu-id="0f5e0-103">管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法</span><span class="sxs-lookup"><span data-stu-id="0f5e0-103">How to View and Configure Applications and Default Virtual Application Extensions by Using the Management Console</span></span>


<span data-ttu-id="0f5e0-104">既定のパッケージの拡張子を表示して構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-104">Use the following procedure to view and configure default package extensions.</span></span>

**<span data-ttu-id="0f5e0-105">仮想アプリケーションの既定の拡張機能を表示して構成するには</span><span class="sxs-lookup"><span data-stu-id="0f5e0-105">To view and configure default virtual application extensions</span></span>**

1.  <span data-ttu-id="0f5e0-106">構成するパッケージを表示するには、App-v 5.0 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-106">To view the package that you want to configure, open the App-V 5.0 Management Console.</span></span> <span data-ttu-id="0f5e0-107">構成するパッケージを選択し、パッケージ名を右クリックして、[**既定の構成の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-107">Select the package that you want to configure, right-click the package name and select **edit default configuration**.</span></span>

2.  <span data-ttu-id="0f5e0-108">指定したパッケージに含まれているアプリケーションを表示するには、[**既定の構成**] ウィンドウで [**アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-108">To view the applications contained in the specified package, in the **Default Configuration** pane, click **Applications**.</span></span> <span data-ttu-id="0f5e0-109">パッケージのショートカットを表示するには、[**ショートカット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-109">To view the shortcuts for that package, click **Shortcuts**.</span></span> <span data-ttu-id="0f5e0-110">そのパッケージのファイルの種類の関連付けを表示するには、[**ファイルの種類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-110">To view the file type associations for that package, click **File Types**.</span></span>

3.  <span data-ttu-id="0f5e0-111">アプリケーションの拡張機能を有効にするには、[**有効に**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-111">To enable the application extensions, select **ENABLE**.</span></span>

    <span data-ttu-id="0f5e0-112">ショートカットを有効にするには、**ショートカットを有効**にします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-112">To enable shortcuts, select **ENABLE SHORTCUTS**.</span></span> <span data-ttu-id="0f5e0-113">選択したアプリケーションに新しいショートカットを追加するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**新しいショートカットの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-113">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane and select **Add new shortcut**.</span></span> <span data-ttu-id="0f5e0-114">ショートカットを削除するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**ショートカットの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-114">To remove a shortcut, right-click the application in the **SHORTCUTS** pane and select **Remove Shortcut**.</span></span> <span data-ttu-id="0f5e0-115">既存のショートカットを編集するには、アプリケーションを右クリックし、[**ショートカットの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-115">To edit an existing shortcut, right-click the application and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="0f5e0-116">その他のアプリケーションの拡張子を表示するには、[**詳細設定**] をクリックし、[**設定のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-116">To view any other application extensions, click **Advanced** and click **Export Configuration**.</span></span> <span data-ttu-id="0f5e0-117">ファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-117">Type in a filename and click **Save**.</span></span> <span data-ttu-id="0f5e0-118">パッケージに関連付けられているすべてのアプリケーション拡張機能は、構成ファイルを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-118">You can view all application extensions associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="0f5e0-119">他のアプリケーションの拡張子を編集するには、構成ファイルを変更し、[インポート] をクリックして、[**この構成を上書き**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-119">To edit other application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="0f5e0-120">変更したファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-120">Select the modified file and click **Open**.</span></span> <span data-ttu-id="0f5e0-121">ダイアログボックスで、[**上書き**] をクリックして処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-121">In the dialog box, click **Overwrite** to complete the process.</span></span>

    <span data-ttu-id="0f5e0-122">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0f5e0-123">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0f5e0-124">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0f5e0-124">Got an App-V issue?</span></span>** <span data-ttu-id="0f5e0-125">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0f5e0-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0f5e0-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0f5e0-126">Related topics</span></span>


[<span data-ttu-id="0f5e0-127">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="0f5e0-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





