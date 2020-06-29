---
title: リモート コンピューターに公開サーバーをインストールする方法
description: リモート コンピューターに公開サーバーをインストールする方法
author: dansimp
ms.assetid: 1c903f78-0558-458d-a149-d5f6fb55aefb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a085d68305057538228599e35dd9500957342ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813979"
---
# <span data-ttu-id="69470-103">リモート コンピューターに公開サーバーをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="69470-103">How to Install the Publishing Server on a Remote Computer</span></span>


<span data-ttu-id="69470-104">公開サーバーを別のコンピューターにインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="69470-104">Use the following procedure to install the publishing server on a separate computer.</span></span> <span data-ttu-id="69470-105">次の手順を実行する前に、データベースと管理サーバーが利用可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="69470-105">Before you perform the following procedure, ensure the database and management server are available.</span></span>

**<span data-ttu-id="69470-106">公開サーバーを別のコンピューターにインストールするには</span><span class="sxs-lookup"><span data-stu-id="69470-106">To install the publishing server on a separate computer</span></span>**

1. <span data-ttu-id="69470-107">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="69470-107">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="69470-108">App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="69470-108">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="69470-109">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-109">Click **Install**.</span></span>

2. <span data-ttu-id="69470-110">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="69470-111">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69470-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="69470-112">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="69470-112">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="69470-113">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-113">Click **Next**.</span></span>

4. <span data-ttu-id="69470-114">[**機能の選択**] ページで、[**発行サーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-114">On the **Feature Selection** page, select the **Publishing Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="69470-115">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="69470-116">[**発行サーバー構成の構成**] ページで、次の項目を指定します。</span><span class="sxs-lookup"><span data-stu-id="69470-116">On the **Configure Publishing Server Configuration** page, specify the following items:</span></span>

   -   <span data-ttu-id="69470-117">発行サーバーが接続する管理サービスの URL です。</span><span class="sxs-lookup"><span data-stu-id="69470-117">The URL for the management service that the publishing server will connect to.</span></span> <span data-ttu-id="69470-118">たとえば、と **http://ManagementServerName:12345** します。</span><span class="sxs-lookup"><span data-stu-id="69470-118">For example, **http://ManagementServerName:12345**.</span></span>

   -   <span data-ttu-id="69470-119">発行サービスに使用する web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="69470-119">Specify the website name that you want to use for the publishing service.</span></span> <span data-ttu-id="69470-120">カスタム名を指定していない場合は、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="69470-120">Accept the default if you do not have a custom name.</span></span>

   -   <span data-ttu-id="69470-121">**ポートバインディング**には、 **54321**などの app-v 5.1 で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="69470-121">For the **Port Binding**, specify a unique port number that will be used by App-V 5.1, for example **54321**.</span></span>

7. <span data-ttu-id="69470-122">[**インストールの準備ができ**ました] ページで、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-122">On the **Ready to Install** page, click **Install**.</span></span>

8. <span data-ttu-id="69470-123">インストールが完了したら、発行サーバーを管理サーバーに登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69470-123">After the installation is complete, the publishing server must be registered with the management server.</span></span> <span data-ttu-id="69470-124">App-v 5.1 管理コンソールで、次の手順を使用してサーバーを登録します。</span><span class="sxs-lookup"><span data-stu-id="69470-124">In the App-V 5.1 management console, use the following steps to register the server:</span></span>

   1.  <span data-ttu-id="69470-125">App-v 5.1 management server コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="69470-125">Open the App-V 5.1 management server console.</span></span>

   2.  <span data-ttu-id="69470-126">左側のウィンドウで、[**サーバー**] を選び、[**新しいサーバーの登録**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="69470-126">In the left pane, select **Servers**, and then select **Register New Server**.</span></span>

   3.  <span data-ttu-id="69470-127">このサーバーの名前と説明を入力し (必要な場合)、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69470-127">Type the name of this server and a description (if required) and click **Add**.</span></span>

9. <span data-ttu-id="69470-128">発行サーバーが正常に実行されているかどうかを確認するには、パッケージを管理サーバーにインポートし、パッケージを AD グループに entitle して、パッケージを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69470-128">To verify if the publishing server is running correctly, you should import a package to the management server, entitle the package to an AD group, and publish the package.</span></span> <span data-ttu-id="69470-129">インターネットブラウザーを使用して、次の URL を開き <strong> http://publishingserver:pubport </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="69470-129">Using an internet browser, open the following URL: <strong>http://publishingserver:pubport</strong>.</span></span> <span data-ttu-id="69470-130">サーバーが正常に実行されている場合は、次のような情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="69470-130">If the server is running correctly information similar to the following will be displayed:</span></span>

   ```xml
   <Publishing Protocol="1.0">
     <Packages>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" VersionId="5d03c08f-51dc-4026-8cf9-15ebe3d65a72" PackageUrl="\\server\share\file.appv" />
     </Packages>
     <NoGroup>
       <Package PackageId="28115343-06e2-44dc-a327-3a0b9b868bda" />
     </NoGroup>
   </Publishing>
   ```

   <span data-ttu-id="69470-131">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="69470-131">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="69470-132">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="69470-132">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="69470-133">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="69470-133">Got an App-V issue?</span></span>** <span data-ttu-id="69470-134">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="69470-134">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="69470-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="69470-135">Related topics</span></span>


[<span data-ttu-id="69470-136">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="69470-136">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

 

 





