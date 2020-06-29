---
title: URL のリダイレクトをテストする方法
description: URL のリダイレクトをテストする方法
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824447"
---
# <span data-ttu-id="1afe0-103">URL のリダイレクトをテストする方法</span><span class="sxs-lookup"><span data-stu-id="1afe0-103">How to Test URL Redirection</span></span>


<span data-ttu-id="1afe0-104">初回のセットアップが完了した後、次のタスクを実行することで、URL リダイレクション機能が予期したとおりに動作していることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1afe0-104">After your test of first time setup finishes, you can verify that the URL redirection functionality is working as expected by performing the following tasks.</span></span>

<span data-ttu-id="1afe0-105">**重要** URL リダイレクションが適切に機能するには、MED-V ホストエージェントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1afe0-105">**Important** The MED-V Host Agent must be running for URL redirection to function correctly.</span></span>

<a href="" id="bkmk-urlredir"></a>**<span data-ttu-id="1afe0-106">URL リダイレクションをテストするには</span><span class="sxs-lookup"><span data-stu-id="1afe0-106">To test URL Redirection</span></span>**

1.  <span data-ttu-id="1afe0-107">ホストコンピューターで Internet Explorer ブラウザーを開き、リダイレクト用に指定した URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-107">Open an Internet Explorer browser in the host computer and enter a URL that you specified for redirection.</span></span>

2.  <span data-ttu-id="1afe0-108">ゲスト仮想マシンの Internet Explorer で web ページが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-108">Verify that the webpage is opened in Internet Explorer on the guest virtual machine.</span></span>

3.  <span data-ttu-id="1afe0-109">テストする URL ごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-109">Repeat this process for each URL that you want to test.</span></span>

**<span data-ttu-id="1afe0-110">URL を追加または削除できることをテストするには</span><span class="sxs-lookup"><span data-stu-id="1afe0-110">To test that a URL can be added or removed</span></span>**

1.  <span data-ttu-id="1afe0-111">MED-V ワークスペースの URL を追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-111">Add or remove a URL from the MED-V workspace.</span></span>

    <span data-ttu-id="1afe0-112">MED-V ワークスペースでのリダイレクトの Url の追加と削除の詳細については、「 [MED-V Url リダイレクションを管理](manage-med-v-url-redirection.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe0-112">For information about how to add and remove URLs for redirection on a MED-V workspace, see [Manage MED-V URL Redirection](manage-med-v-url-redirection.md).</span></span>

2.  <span data-ttu-id="1afe0-113">リダイレクトリストに URL を追加した場合は、「 [Url リダイレクションをテストする](#bkmk-urlredir)」の手順を繰り返して、新しい url が意図したようにリダイレクトされることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-113">If you added a URL to the redirection list, repeat the steps in [To Test URL Redirection](#bkmk-urlredir) to verify that the new URL redirects as intended.</span></span>

3.  <span data-ttu-id="1afe0-114">リダイレクトリストから URL を削除した場合は、次の手順に従って削除されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-114">If you removed a URL from the redirection list, verify that it is removed by following these steps:</span></span>

    1.  <span data-ttu-id="1afe0-115">ホストコンピューターで Internet Explorer ブラウザーを開き、[リダイレクション] の一覧から削除した URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-115">Open an Internet Explorer browser in the host computer and enter the URL that you removed from the redirection list.</span></span>

    2.  <span data-ttu-id="1afe0-116">ゲストの仮想マシンではなく、ホストコンピューターの Internet Explorer で web ページが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1afe0-116">Verify that the webpage is opened in Internet Explorer on the host computer instead of on the guest virtual machine.</span></span>

        <span data-ttu-id="1afe0-117">**注** URL リダイレクションの変更が行われるまでに数秒かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="1afe0-117">**Note** It can take several seconds for the URL redirection changes to take place.</span></span>

<span data-ttu-id="1afe0-118">**注** URL リダイレクション設定を確認するときに問題が発生した場合は、「[操作のトラブルシューティング](operations-troubleshooting-medv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1afe0-118">**Note** If you encounter any problems when verifying your URL redirection settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="1afe0-119">MED-V ワークスペースで URL リダイレクションのテストが完了したら、他の構成をテストして、意図したとおりに機能するかどうかを確認できます。</span><span class="sxs-lookup"><span data-stu-id="1afe0-119">After you have completed testing URL redirection in your MED-V workspace, you can test other configurations to verify that they function as intended.</span></span>

<span data-ttu-id="1afe0-120">MED-V ワークスペースパッケージのテストが完了し、意図したとおりに機能していることを確認したら、MED-V ワークスペースを企業に展開できます。</span><span class="sxs-lookup"><span data-stu-id="1afe0-120">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="1afe0-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1afe0-121">Related topics</span></span>

[<span data-ttu-id="1afe0-122">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="1afe0-122">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="1afe0-123">初回使用時のセットアップの設定を確認する方法</span><span class="sxs-lookup"><span data-stu-id="1afe0-123">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="1afe0-124">MED-V ワークスペース パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="1afe0-124">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





