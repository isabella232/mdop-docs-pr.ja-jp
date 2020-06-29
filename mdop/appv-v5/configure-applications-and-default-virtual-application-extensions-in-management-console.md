---
title: 管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する
description: 管理コンソールを使用してアプリケーションと既定の仮想アプリケーション拡張機能を表示して構成する方法
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814706"
---
#   <span data-ttu-id="0e7e4-103">管理コンソールでアプリケーションと既定の仮想アプリケーションの拡張機能を構成する</span><span class="sxs-lookup"><span data-stu-id="0e7e4-103">Configure Applications and Default Virtual Application Extensions in Management Console</span></span>

<span data-ttu-id="0e7e4-104">既定のパッケージの拡張子を*表示*して*構成*するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-104">Use the following procedure to *view* and *configure* default package extensions.</span></span>

**<span data-ttu-id="0e7e4-105">仮想アプリケーションの既定の拡張機能を表示して構成するには</span><span class="sxs-lookup"><span data-stu-id="0e7e4-105">To view and configure default virtual application extensions</span></span>**

1.  <span data-ttu-id="0e7e4-106">構成するパッケージを表示するには、App-v 5.1 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-106">To view the package that you want to configure, open the App-V 5.1 Management Console.</span></span> <span data-ttu-id="0e7e4-107">構成するパッケージを選択し、パッケージ名を右クリックして、[**既定の構成の編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-107">Select the package that you want to configure, right-click the package name and select **edit default configuration**.</span></span>

2.  <span data-ttu-id="0e7e4-108">指定したパッケージに含まれているアプリケーションを表示するには、[**既定の構成**] ウィンドウで [**アプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-108">To view the applications contained in the specified package, in the **Default Configuration** pane, click **Applications**.</span></span> <span data-ttu-id="0e7e4-109">パッケージのショートカットを表示するには、[**ショートカット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-109">To view the shortcuts for that package, click **Shortcuts**.</span></span> <span data-ttu-id="0e7e4-110">そのパッケージのファイルの種類の関連付けを表示するには、[**ファイルの種類**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-110">To view the file type associations for that package, click **File Types**.</span></span>

3.  <span data-ttu-id="0e7e4-111">アプリケーションの拡張機能を有効にするには、[**有効に**する] を選びます。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-111">To enable the application extensions, select **ENABLE**.</span></span>

    <span data-ttu-id="0e7e4-112">ショートカットを有効にするには、**ショートカットを有効**にします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-112">To enable shortcuts, select **ENABLE SHORTCUTS**.</span></span> <span data-ttu-id="0e7e4-113">選択したアプリケーションに新しいショートカットを追加するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**新しいショートカットの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-113">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane and select **Add new shortcut**.</span></span> <span data-ttu-id="0e7e4-114">ショートカットを削除するには、[**ショートカット**] ウィンドウでアプリケーションを右クリックし、[**ショートカットの削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-114">To remove a shortcut, right-click the application in the **SHORTCUTS** pane and select **Remove Shortcut**.</span></span> <span data-ttu-id="0e7e4-115">既存のショートカットを編集するには、アプリケーションを右クリックし、[**ショートカットの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-115">To edit an existing shortcut, right-click the application and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="0e7e4-116">その他のアプリケーションの拡張子を表示するには、[**詳細設定**] をクリックし、[**設定のエクスポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-116">To view any other application extensions, click **Advanced** and click **Export Configuration**.</span></span> <span data-ttu-id="0e7e4-117">ファイル名を入力し、[**保存**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-117">Type in a filename and click **Save**.</span></span> <span data-ttu-id="0e7e4-118">パッケージに関連付けられているすべてのアプリケーション拡張機能は、構成ファイルを使って表示できます。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-118">You can view all application extensions associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="0e7e4-119">他のアプリケーションの拡張子を編集するには、構成ファイルを変更し、[インポート] をクリックして、[**この構成を上書き**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-119">To edit other application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="0e7e4-120">変更したファイルを選択し、[**開く**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-120">Select the modified file and click **Open**.</span></span> <span data-ttu-id="0e7e4-121">ダイアログボックスで、[**上書き**] をクリックして処理を完了します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-121">In the dialog box, click **Overwrite** to complete the process.</span></span>

><span data-ttu-id="0e7e4-122">**注**アップロードに失敗し、構成ファイルのサイズが4MB より上の場合は、サーバーで許可される最大ファイルサイズを大きくする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-122">**Note** If the upload fails and the size of your configuration file is above 4MB, you will need to increase the maximum file size allowed by the server.</span></span> <span data-ttu-id="0e7e4-123">これを行うには、構成ファイルのサイズよりも大きい値 (KB 単位) の maxRequestLength 属性を、26行目の httpRuntime 要素に追加し `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` ます。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-123">This can be done by adding the maxRequestLength attribute with a value greater than the size of your configuration file (in KB) to the httpRuntime element on line 26 of `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config`.</span></span>  
<span data-ttu-id="0e7e4-124">たとえば、をに変更すると、 `<httpRuntime targetFramework="4.5"/>` `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 最大サイズは 8 mb になります。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-124">For example, changing `<httpRuntime targetFramework="4.5"/>` to `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` will increase the maximum size to 8MB</span></span>


<span data-ttu-id="0e7e4-125">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0e7e4-126">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0e7e4-127">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0e7e4-127">Got an App-V issue?</span></span>** <span data-ttu-id="0e7e4-128">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0e7e4-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0e7e4-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0e7e4-129">Related topics</span></span>


[<span data-ttu-id="0e7e4-130">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="0e7e4-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





