---
title: 管理コンソールを使用してパッケージを公開する方法
description: 管理コンソールを使用してパッケージを公開する方法
author: dansimp
ms.assetid: 7c6930fc-5c89-4519-a901-512dae155fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 832dd95edbb0f4cd6b6ae242a81859141ebcb279
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813786"
---
# <span data-ttu-id="2e221-103">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="2e221-103">How to Publish a Package by Using the Management Console</span></span>


<span data-ttu-id="2e221-104">次の手順を使用して、App-v 5.0 パッケージを公開します。</span><span class="sxs-lookup"><span data-stu-id="2e221-104">Use the following procedure to publish an App-V 5.0 package.</span></span> <span data-ttu-id="2e221-105">パッケージを公開すると、App-v 5.0 クライアントを実行しているコンピューターでは、そのパッケージ内のアプリケーションにアクセスして実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e221-105">Once you publish a package, computers that are running the App-V 5.0 client can access and run the applications in that package.</span></span>

<span data-ttu-id="2e221-106">**注** 管理者のみがパッケージを公開または非公開にする機能を有効にする機能 (以下で説明) は、App-v 5.0 SP3 以降でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e221-106">**Note** The ability to enable only administrators to publish or unpublish packages (described below) is supported starting in App-V 5.0 SP3.</span></span>

 

**<span data-ttu-id="2e221-107">App-v 5.0 パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="2e221-107">To publish an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="2e221-108">App V 5.0 管理コンソールで、</span><span class="sxs-lookup"><span data-stu-id="2e221-108">In the App-V 5.0 Management console.</span></span> <span data-ttu-id="2e221-109">公開するパッケージの名前を右クリックし、[**発行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e221-109">right-click the name of the package to be published, and select **Publish**.</span></span>

2.  <span data-ttu-id="2e221-110">[**状態**] 列を確認して、パッケージが公開されていることを確認し、使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="2e221-110">Review the **Status** column to verify that the package has been published and is now available.</span></span> <span data-ttu-id="2e221-111">パッケージが使用可能な場合は、[**発行済み**] 状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e221-111">If the package is available, the status **published** is displayed.</span></span>

    <span data-ttu-id="2e221-112">パッケージが正常に公開されていない場合は、[**非公開**] という状態が表示され、パッケージが使用できない理由を説明するエラーテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e221-112">If the package is not published successfully, the status **unpublished** is displayed, along with error text that explains why the package is not available.</span></span>

**<span data-ttu-id="2e221-113">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="2e221-113">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="2e221-114">次のグループポリシーオブジェクトノードに移動します。</span><span class="sxs-lookup"><span data-stu-id="2e221-114">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="2e221-115">**コンピューターの構成 &gt;ポリシー &gt; 管理用テンプレート &gt; システム &gt; アプリ-V の &gt; 公開**。</span><span class="sxs-lookup"><span data-stu-id="2e221-115">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="2e221-116">[**管理者として発行する**] グループポリシーの設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2e221-116">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="2e221-117">または、PowerShell を使用してこの項目を設定するには、 [Powershell を使用してスタンドアロンコンピューターで実行されている app-v 5.0 パッケージを管理する方法](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)に関する説明を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e221-117">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="2e221-118">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="2e221-118">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="2e221-119">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2e221-119">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="2e221-120">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="2e221-120">Got an App-V issue?</span></span>** <span data-ttu-id="2e221-121">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2e221-121">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="2e221-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2e221-122">Related topics</span></span>


[<span data-ttu-id="2e221-123">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="2e221-123">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="2e221-124">管理コンソールを使用してパッケージへのアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2e221-124">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

 

 





