---
title: 展開のトラブルシューティング
description: 展開のトラブルシューティング
author: dansimp
ms.assetid: 9ee980f2-4e77-4020-9f0e-8c2ffdc390ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe9677175c9538bc070d2adea17a96351397d9a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822897"
---
# <span data-ttu-id="c529c-103">展開のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c529c-103">Deployment Troubleshooting</span></span>


<span data-ttu-id="c529c-104">このトピックでは、Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 の展開に関する問題のトラブルシューティングに役立つ情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="c529c-104">This topic includes information to help you troubleshoot deployment issues in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="c529c-105">MED-V の展開に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c529c-105">Troubleshooting Issues in MED-V Deployment</span></span>


<span data-ttu-id="c529c-106">MED-V を展開すると、次の問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c529c-106">The following issue might occur when you deploy MED-V.</span></span> <span data-ttu-id="c529c-107">解決策は、この問題のトラブルシューティングに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="c529c-107">The solution helps troubleshoot this issue.</span></span>

**<span data-ttu-id="c529c-108">現在のユーザーに対して MED-V をインストールする場合、問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="c529c-108">Problems Occur if Installing MED-V for Current User Only.</span></span>** <span data-ttu-id="c529c-109">MED-V では、MED-V Workspace パッケージャー、MED-V ホストエージェント、およびすべてのユーザーの MED-V ワークスペースのインストールのみがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="c529c-109">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="c529c-110">現在のユーザー用にインストールすると、コンポーネントのインストール、および MED-V ワークスペースのセットアップでエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="c529c-110">Installing for the current user only causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>

**<span data-ttu-id="c529c-111">解決策</span><span class="sxs-lookup"><span data-stu-id="c529c-111">Solution</span></span>**

<span data-ttu-id="c529c-112">MED-V のコンポーネントをインストールするときは、option **ALLUSERS = ""** を使わないでください。</span><span class="sxs-lookup"><span data-stu-id="c529c-112">Never use the option **ALLUSERS=””** when installing the MED-V components.</span></span>

**<span data-ttu-id="c529c-113">MED-V では、仮想化スタックを排他的に使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c529c-113">MED-V Requires Exclusive Use of the Virtualization Stack.</span></span>** <span data-ttu-id="c529c-114">コンピューターで同時に実行できる仮想化スタックは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="c529c-114">Only one virtualization stack can be run at a time on a computer.</span></span> <span data-ttu-id="c529c-115">Windows 仮想 PC では仮想スタックを使用する必要があり、MED-V は Windows 仮想 PC に依存します。</span><span class="sxs-lookup"><span data-stu-id="c529c-115">Windows Virtual PC must use the virtual stack, and MED-V depends on Windows Virtual PC.</span></span> <span data-ttu-id="c529c-116">そのため、仮想スタックを使用する他のアプリケーションが実行されているときに、MED-V を展開または使用しようとすると、MED-V を実行できないか、正常にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="c529c-116">Therefore, if you try to deploy or use MED-V when other applications are running that use the virtual stack, MED-V cannot run or be successfully installed.</span></span>

**<span data-ttu-id="c529c-117">解決策</span><span class="sxs-lookup"><span data-stu-id="c529c-117">Solution</span></span>**

<span data-ttu-id="c529c-118">MED-V をインストールまたは実行する前に、仮想化スタックを使って実行されているすべてのアプリケーションを閉じます。</span><span class="sxs-lookup"><span data-stu-id="c529c-118">Close any application that is running that uses the virtualization stack before you install or run MED-V.</span></span>

**<span data-ttu-id="c529c-119">アンインストール後もショートカットが残っています。</span><span class="sxs-lookup"><span data-stu-id="c529c-119">Shortcuts Remain after Uninstall.</span></span>** <span data-ttu-id="c529c-120">既定では、MED-V をアンインストールすると、エンドユーザーの [**スタート**] メニューのショートカットが削除されます。</span><span class="sxs-lookup"><span data-stu-id="c529c-120">By default, when you uninstall MED-V, shortcuts in the end user’s **Start** menu are removed.</span></span> <span data-ttu-id="c529c-121">ただし、特定の状況では、ローミングプロファイルを実行しているエンドユーザーの場合、MED-V が公開されているアプリケーションへのショートカットは、エンドユーザーの [**スタート**] メニューに残ります。</span><span class="sxs-lookup"><span data-stu-id="c529c-121">However, in certain situations, such as for end users who are running roaming profiles, shortcuts to MED-V published applications remain in the end user’s **Start** menu.</span></span>

**<span data-ttu-id="c529c-122">解決策</span><span class="sxs-lookup"><span data-stu-id="c529c-122">Solution</span></span>**

<span data-ttu-id="c529c-123">[**スタート**] メニューの残りのショートカットを手動で削除するには、ショートカットを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c529c-123">To manually delete the remaining shortcuts on the **Start** menu, right-click the shortcuts, and then click **Remove**.</span></span>

**<span data-ttu-id="c529c-124">MED-V ワークスペースの [ログオンメッセージ] グループポリシー設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c529c-124">Disable Logon Message Group Policy Setting in the MED-V Workspace.</span></span>** <span data-ttu-id="c529c-125">Windows XP のログオンメッセージが MED-V ワークスペースで有効になっている場合、エンドユーザーは、MED-V 仮想アプリケーションを開くたびにログオンする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c529c-125">If the Windows XP logon message is enabled in the MED-V workspace, the end user must log on every time they want to open a MED-V virtual application.</span></span> <span data-ttu-id="c529c-126">これにより、ユーザーエクスペリエンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="c529c-126">This creates a poor user experience.</span></span>

**<span data-ttu-id="c529c-127">解決策</span><span class="sxs-lookup"><span data-stu-id="c529c-127">Solution</span></span>**

<span data-ttu-id="c529c-128">MED-V 仮想マシンで次のグループポリシー設定を無効にします。</span><span class="sxs-lookup"><span data-stu-id="c529c-128">Disable the following Group Policy settings in the MED-V virtual machine:</span></span>

**<span data-ttu-id="c529c-129">対話型ログオン: ログオン時のユーザーへのメッセージのテキスト</span><span class="sxs-lookup"><span data-stu-id="c529c-129">Interactive logon: Message text for users attempting to log on</span></span>**

**<span data-ttu-id="c529c-130">対話型ログオン: ログオン時のユーザーへのメッセージのタイトル</span><span class="sxs-lookup"><span data-stu-id="c529c-130">Interactive logon: Message title for users attempting to log on</span></span>**

## <span data-ttu-id="c529c-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c529c-131">Related topics</span></span>


[<span data-ttu-id="c529c-132">操作のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="c529c-132">Operations Troubleshooting</span></span>](operations-troubleshooting-medv2.md)

 

 





