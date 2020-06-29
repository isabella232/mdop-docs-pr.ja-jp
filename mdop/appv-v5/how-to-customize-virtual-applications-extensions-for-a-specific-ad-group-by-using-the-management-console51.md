---
title: 管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法
description: 管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法
author: dansimp
ms.assetid: dd71df05-512f-4eb4-a55f-e5b93601323d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bf086da3fbb6938a4fc602af5ab63adb1621532
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814258"
---
# <span data-ttu-id="0082d-103">管理コンソールを使用して特定の AD グループの仮想アプリケーションの拡張機能をカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="0082d-103">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>


<span data-ttu-id="0082d-104">Active Directory (AD) グループの仮想アプリケーション拡張機能をカスタマイズするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0082d-104">Use the following procedure to customize the virtual application extensions for an Active Directory (AD) group.</span></span>

**<span data-ttu-id="0082d-105">AD グループの仮想アプリケーションの拡張機能をカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="0082d-105">To customize virtual applications extensions for an AD group</span></span>**

1.  <span data-ttu-id="0082d-106">構成するパッケージを表示するには、App-v 5.1 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0082d-106">To view the package that you want to configure, open the App-V 5.1 Management Console.</span></span> <span data-ttu-id="0082d-107">特定のユーザーグループに割り当てられている構成を表示するには、パッケージを選択し、パッケージ名を右クリックして、[ **active directory アクセスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0082d-107">To view the configuration that is assigned to a given user group, select the package, and right-click the package name and select **Edit active directory access**.</span></span> <span data-ttu-id="0082d-108">または、パッケージを選択し、**広告アクセス**ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-108">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="0082d-109">広告グループをカスタマイズするには、**アクセス権のある広告エンティティ**の一覧からグループを検索します。</span><span class="sxs-lookup"><span data-stu-id="0082d-109">To customize an AD group, you can find the group from the list of **AD Entities with Access**.</span></span> <span data-ttu-id="0082d-110">次に、[**割り当てられた構成**] ウィンドウのドロップダウンボックスを使用して、[**カスタム**] を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-110">Then, using the drop-down box in the **Assigned Configuration** pane, select **Custom**, and then click **EDIT**.</span></span>

3.  <span data-ttu-id="0082d-111">特定のアプリケーションのすべての拡張機能を無効にするには、[**有効に**する] をオフにします。</span><span class="sxs-lookup"><span data-stu-id="0082d-111">To disable all extensions for a given application, clear **ENABLE**.</span></span>

    <span data-ttu-id="0082d-112">選択したアプリケーションに新しいショートカットを追加するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**新しいショートカットの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0082d-112">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane, and select **Add new shortcut**.</span></span> <span data-ttu-id="0082d-113">ショートカットを削除するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**ショートカットの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0082d-113">To remove a shortcut, right-click the application in the **SHORTCUTS** pane, and select **Remove Shortcut**.</span></span> <span data-ttu-id="0082d-114">既存のショートカットを編集するには、アプリケーションを右クリックし、[**ショートカットの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0082d-114">To edit an existing shortcut, right-click the application, and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="0082d-115">その他のアプリケーションの拡張子を表示するには、[**詳細設定**] をクリックし、[**構成のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-115">To view any other application extensions, click **Advanced**, and click **Export Configuration**.</span></span> <span data-ttu-id="0082d-116">ファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-116">Type in a filename and click **Save**.</span></span> <span data-ttu-id="0082d-117">パッケージに関連付けられているすべてのアプリケーション拡張機能は、構成ファイルを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="0082d-117">You can view all application extensions that are associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="0082d-118">その他のアプリケーションの拡張子を編集するには、構成ファイルを変更し、[インポート] をクリックして [**この構成を上書き**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-118">To edit additional application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="0082d-119">変更したファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0082d-119">Select the modified file and click **Open**.</span></span> <span data-ttu-id="0082d-120">ダイアログボックスで、[**上書き**] をクリックして処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="0082d-120">In the dialog, click **Overwrite** to complete the process.</span></span>

    <span data-ttu-id="0082d-121">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0082d-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0082d-122">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0082d-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0082d-123">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0082d-123">Got an App-V issue?</span></span>** <span data-ttu-id="0082d-124">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0082d-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0082d-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0082d-125">Related topics</span></span>


[<span data-ttu-id="0082d-126">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="0082d-126">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





