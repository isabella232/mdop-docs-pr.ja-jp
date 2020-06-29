---
title: 管理コンソールを使用してパッケージを公開する方法
description: 管理コンソールを使用してパッケージを公開する方法
author: dansimp
ms.assetid: e34d2bcf-15ac-4a75-9dc8-79380b36a25f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b0783a05f658da5e93603e26dc7e9581d26b81f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813770"
---
# <span data-ttu-id="5a4fe-103">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="5a4fe-103">How to Publish a Package by Using the Management Console</span></span>


<span data-ttu-id="5a4fe-104">次の手順を使用して、App-v 5.1 パッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-104">Use the following procedure to publish an App-V 5.1 package.</span></span> <span data-ttu-id="5a4fe-105">パッケージを公開すると、App-v 5.1 クライアントを実行しているコンピューターでは、そのパッケージ内のアプリケーションにアクセスして実行できます。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-105">Once you publish a package, computers that are running the App-V 5.1 client can access and run the applications in that package.</span></span>

<span data-ttu-id="5a4fe-106">**注** 管理者のみがパッケージを公開または非公開にする機能を有効にする機能 (以下で説明) は、App-v 5.0 SP3 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-106">**Note** The ability to enable only administrators to publish or unpublish packages (described below) is supported starting in App-V 5.0 SP3.</span></span>

 

**<span data-ttu-id="5a4fe-107">App-v 5.1 パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="5a4fe-107">To publish an App-V 5.1 package</span></span>**

1.  <span data-ttu-id="5a4fe-108">App V 5.1 管理コンソールで、</span><span class="sxs-lookup"><span data-stu-id="5a4fe-108">In the App-V 5.1 Management console.</span></span> <span data-ttu-id="5a4fe-109">公開するパッケージの名前をクリックまたは右クリックします。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-109">Click or right-click the name of the package to be published.</span></span> <span data-ttu-id="5a4fe-110">**[公開]** を選びます。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-110">Select **Publish**.</span></span>

2.  <span data-ttu-id="5a4fe-111">[**状態**] 列を確認して、パッケージが公開されていることを確認し、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-111">Review the **Status** column to verify that the package has been published and is now available.</span></span> <span data-ttu-id="5a4fe-112">パッケージが使用可能な場合は、[**発行済み**] 状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-112">If the package is available, the status **published** is displayed.</span></span>

    <span data-ttu-id="5a4fe-113">パッケージが正常に公開されていない場合は、[**非公開**] という状態が表示され、パッケージが使用できない理由を説明するエラーテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-113">If the package is not published successfully, the status **unpublished** is displayed, along with error text that explains why the package is not available.</span></span>

**<span data-ttu-id="5a4fe-114">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="5a4fe-114">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="5a4fe-115">次のグループポリシーオブジェクトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-115">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="5a4fe-116">**コンピューターの構成 &gt;ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 公開**。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-116">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="5a4fe-117">[**管理者として発行する**] グループポリシーの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-117">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="5a4fe-118">または、PowerShell を使用してこの項目を設定するには、 [Powershell を使用してスタンドアロンコンピューターで実行されている app-v 5.1 パッケージを管理する方法](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-118">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="5a4fe-119">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="5a4fe-120">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="5a4fe-121">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="5a4fe-121">Got an App-V issue?</span></span>** <span data-ttu-id="5a4fe-122">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="5a4fe-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="5a4fe-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5a4fe-123">Related topics</span></span>


[<span data-ttu-id="5a4fe-124">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="5a4fe-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="5a4fe-125">管理コンソールを使用してパッケージへのアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5a4fe-125">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-51.md)

 

 





