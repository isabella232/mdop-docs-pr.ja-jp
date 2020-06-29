---
title: スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法
description: スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法
author: dansimp
ms.assetid: 3f83c335-d976-4abd-b8f8-d7f5e50b4318
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f2cce96f914f65e7432b5ed9e7c5ecb1a6306990
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814011"
---
# <span data-ttu-id="24feb-103">スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="24feb-103">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="24feb-104">次の手順を使用して、管理サーバーをスタンドアロンコンピューターにインストールし、データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="24feb-104">Use the following procedure to install the management server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="24feb-105">スタンドアロンコンピューターに管理サーバーをインストールしてデータベースに接続するには</span><span class="sxs-lookup"><span data-stu-id="24feb-105">To install the management server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="24feb-106">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="24feb-106">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="24feb-107">App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="24feb-107">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="24feb-108">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-108">Click **Install**.</span></span>

2.  <span data-ttu-id="24feb-109">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-109">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="24feb-110">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24feb-110">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="24feb-111">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="24feb-111">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="24feb-112">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-112">Click **Next**.</span></span>

4.  <span data-ttu-id="24feb-113">[**機能の選択**] ページで、[**管理サーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-113">On the **Feature Selection** page, select the **Management Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="24feb-114">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-114">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="24feb-115">[**既存の管理データベースの構成**] ページで、[**リモート Sql Server を使用**する] を選び、Microsoft sql sql を実行しているコンピューターのコンピューター名 ( **SqlServerMachine**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="24feb-115">On the **Configure Existing Management Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL SQL, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="24feb-116">注</span><span class="sxs-lookup"><span data-stu-id="24feb-116">Note</span></span>**  
    <span data-ttu-id="24feb-117">Microsoft SQL Server が同じサーバーに展開されている場合は、[**ローカル Sql server を使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="24feb-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this management server will use, for example **AppvManagement**.
~~~

7. <span data-ttu-id="24feb-118">[ **Management Server 構成の構成**] ページで、管理コンソールに接続する AD グループまたはアカウント (たとえば、 **MyDomain\\MyUser**や**MyDomain\\AdminGroup**) を指定します。</span><span class="sxs-lookup"><span data-stu-id="24feb-118">On the **Configure Management Server Configuration** page, specify the AD group or account that will connect to the management console for administrative purposes for example **MyDomain\\MyUser** or **MyDomain\\AdminGroup**.</span></span> <span data-ttu-id="24feb-119">指定したアカウントまたは広告グループは、管理コンソールを使用してサーバーを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="24feb-119">The account or AD group you specify will be enabled to manage the server through the management console.</span></span> <span data-ttu-id="24feb-120">インストール後に管理コンソールを使用して、ユーザーまたはグループを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="24feb-120">You can add additional users or groups using the management console after installation</span></span>

   <span data-ttu-id="24feb-121">管理サービスに使用する**Web サイト名**を指定します。</span><span class="sxs-lookup"><span data-stu-id="24feb-121">Specify the **Website Name** that you want to use for the management service.</span></span> <span data-ttu-id="24feb-122">カスタム名を指定していない場合は、既定値をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="24feb-122">Accept the default if you do not have a custom name.</span></span> <span data-ttu-id="24feb-123">ポートの**バインド**で、使用する一意のポート番号を指定します (例**12345**)。</span><span class="sxs-lookup"><span data-stu-id="24feb-123">For the **Port Binding**, specify a unique port number to be used, for example **12345**.</span></span>

8. <span data-ttu-id="24feb-124">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="24feb-124">Click **Install**.</span></span>

9. <span data-ttu-id="24feb-125">セットアップが正常に完了したことを確認するには、web ブラウザーを開いて、次の URL を入力し http://managementserver:portnumber/Console ます。</span><span class="sxs-lookup"><span data-stu-id="24feb-125">To confirm that the setup has completed successfully, open a web browser, and type the following URL: http://managementserver:portnumber/Console.</span></span> <span data-ttu-id="24feb-126">インストールに成功した場合は、エラーメッセージや警告が表示されることなく、**管理コンソール**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="24feb-126">If the installation was successful, you should see the **Management Console** appear without any error messages or warnings being displayed.</span></span>

   <span data-ttu-id="24feb-127">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="24feb-127">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="24feb-128">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="24feb-128">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="24feb-129">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="24feb-129">Got an App-V issue?</span></span>** <span data-ttu-id="24feb-130">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="24feb-130">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="24feb-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="24feb-131">Related topics</span></span>


[<span data-ttu-id="24feb-132">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="24feb-132">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)









