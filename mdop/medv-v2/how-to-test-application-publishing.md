---
title: アプリケーションの公開をテストする方法
description: アプリケーションの公開をテストする方法
author: dansimp
ms.assetid: 17ba2e12-50a0-4f41-8300-f61f09db9f6c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 8dffb4f79ac89c7d419b27640f4f05364bd69e5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826914"
---
# <span data-ttu-id="36a7c-103">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="36a7c-103">How to Test Application Publishing</span></span>


<span data-ttu-id="36a7c-104">初回のセットアップが完了した後、次のタスクを実行することで、アプリケーションの発行機能が予期したとおりに動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="36a7c-104">After your test of first time setup finishes, you can verify that the application publishing functionality is working as expected by performing the following tasks.</span></span>

<a href="" id="bkmk-apppub"></a>**<span data-ttu-id="36a7c-105">アプリケーションの発行をテストするには</span><span class="sxs-lookup"><span data-stu-id="36a7c-105">To test application publishing</span></span>**

1.  <span data-ttu-id="36a7c-106">発行用に指定したアプリケーションが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-106">Verify that the applications that you specified for publishing are visible.</span></span>

    <span data-ttu-id="36a7c-107">[**スタート**] をクリックし、[**すべてのプログラム**] をクリックして、指定したアプリケーションを検索します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-107">Click **Start** and then click **All Programs** and search for the specified applications.</span></span>

    <span data-ttu-id="36a7c-108">場合によっては、ホストコンピューターに1回、またはゲスト上に1回だけ同じアプリケーションをインストールすることがあります。</span><span class="sxs-lookup"><span data-stu-id="36a7c-108">In some cases, you might have the same application installed two times, one time on the host computer and one time on the guest.</span></span> <span data-ttu-id="36a7c-109">同じ名前を持つ公開されたアプリケーションがホストの [**スタート**] メニューの同じ場所に公開されている場合は、仮想マシン名をショートカット名に追加することで、ホストアプリケーションのショートカットと区別されます。</span><span class="sxs-lookup"><span data-stu-id="36a7c-109">If a published application that has the same name is published to the same location on the host **Start** menu, it is distinguished from the host application shortcut by adding the virtual machine name to the shortcut name.</span></span> <span data-ttu-id="36a7c-110">たとえば、"MEDVHost1" という名前の仮想マシンの場合、ホストアプリケーションは "Notepad" であり、公開されたアプリケーションは "Notepad (MEDVHost1)" のようになります。</span><span class="sxs-lookup"><span data-stu-id="36a7c-110">For example, for a virtual machine named “MEDVHost1”, a host application might be "Notepad" and a published application might be "Notepad (MEDVHost1)".</span></span>

2.  <span data-ttu-id="36a7c-111">アプリケーションが意図したとおりに機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-111">Verify that the applications function as intended.</span></span>

    <span data-ttu-id="36a7c-112">ホストコンピューターで、公開したアプリケーションを起動し、ゲスト上の Windows XP SP3 でそれらが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-112">On the host computer, start the applications that you published and verify that they open in Windows XP SP3 on the guest.</span></span> <span data-ttu-id="36a7c-113">アプリケーションは、ホストコンピューターのデスクトップに Windows XP スタイルのウィンドウとして表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="36a7c-113">The application must appear in a Windows XP-style window on the host computer desktop.</span></span>

3.  <span data-ttu-id="36a7c-114">該当する場合は、ドキュメントのリダイレクションが意図したとおりに機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-114">If applicable, verify that document redirection functions as intended.</span></span>

    <span data-ttu-id="36a7c-115">ゲスト上の公開されたアプリケーションがホストシステムドライブ上のフォルダーを開く必要がある場合は、指定したフォルダーを開くことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="36a7c-115">If a published application on the guest has to open a folder on the host system drive, ensure that it can open the specified folder.</span></span>

    <span data-ttu-id="36a7c-116">**重要** Windows 仮想 PC では、既に共有されているフォルダーからの共有の作成はサポートされていないため、ネットワーク上にある [マイドキュメント] フォルダーなど、共有フォルダーから開いているドキュメントについては、リダイレクトは行われません。</span><span class="sxs-lookup"><span data-stu-id="36a7c-116">**Important** Because Windows Virtual PC does not support creating a share from a folder that is already shared, redirection does not occur for any documents that open from a shared folder, such as a My Documents folder that is located on the network.</span></span> <span data-ttu-id="36a7c-117">詳細については、「[操作のトラブルシューティング](operations-troubleshooting-medv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a7c-117">For more information, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="36a7c-118">公開されたアプリケーションがインストールされ、正常に機能していることを確認したら、アプリケーションを MED-V ワークスペースから追加または削除できるかどうかをテストできます。</span><span class="sxs-lookup"><span data-stu-id="36a7c-118">After you have verified that published applications are installed and functioning correctly, you can test whether applications can be added or removed from the MED-V workspace.</span></span>

**<span data-ttu-id="36a7c-119">アプリケーションを追加または削除できることをテストするには</span><span class="sxs-lookup"><span data-stu-id="36a7c-119">To test that an application can be added or removed</span></span>**

1.  <span data-ttu-id="36a7c-120">MED-V ワークスペースからアプリケーションを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-120">Add or remove an application from the MED-V workspace.</span></span>

    <span data-ttu-id="36a7c-121">MED-V ワークスペースにアプリケーションを追加して削除する方法については、「 [Med-v ワークスペースに展開](managing-applications-deployed-to-med-v-workspaces.md)されたアプリケーションを管理する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a7c-121">For information about how to add and remove applications from a MED-V workspace, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

2.  <span data-ttu-id="36a7c-122">アプリケーションを追加した場合は、「[アプリケーションの発行をテスト](#bkmk-apppub)する」の手順を繰り返して、新しいアプリケーションが意図したとおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-122">If you added an application, repeat the steps in [To Test Application Publishing](#bkmk-apppub) to verify that the new application functions as intended.</span></span>

3.  <span data-ttu-id="36a7c-123">アプリケーションを削除した場合は、[**スタート**] をクリックし、[**すべてのプログラム**] をクリックして、削除したアプリケーションが表示されなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="36a7c-123">If you removed an application, click **Start** and then click **All Programs** and verify that any applications that you removed are no longer listed.</span></span>

<span data-ttu-id="36a7c-124">**注** アプリケーションのパブリケーション設定を確認するときに問題が発生した場合は、「[操作のトラブルシューティング](operations-troubleshooting-medv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36a7c-124">**Note** If you encounter any problems when verifying your application publication settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="36a7c-125">アプリケーションの発行のテストが完了したら、他の MED-V ワークスペースの構成をテストして、意図したとおりに機能するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="36a7c-125">After you have completed testing application publishing, you can test other MED-V workspace configurations to verify that they function as intended.</span></span>

<span data-ttu-id="36a7c-126">MED-V ワークスペースパッケージのテストが完了し、意図したとおりに機能していることを確認したら、MED-V ワークスペースを企業に展開できます。</span><span class="sxs-lookup"><span data-stu-id="36a7c-126">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="36a7c-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="36a7c-127">Related topics</span></span>

[<span data-ttu-id="36a7c-128">URL のリダイレクトをテストする方法</span><span class="sxs-lookup"><span data-stu-id="36a7c-128">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="36a7c-129">初回使用時のセットアップの設定を確認する方法</span><span class="sxs-lookup"><span data-stu-id="36a7c-129">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="36a7c-130">MED-V ワークスペース パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="36a7c-130">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





