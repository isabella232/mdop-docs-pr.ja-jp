---
title: スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法
description: スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法
author: dansimp
ms.assetid: 11f07750-4045-4c8d-a583-7d70c9e9aa7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67866714ff6ae60097d9b368fd0eaf361b08eec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813971"
---
# <span data-ttu-id="e7e74-103">スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="e7e74-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>

<span data-ttu-id="e7e74-104">次の手順を使用して、スタンドアロンコンピューターにレポートサーバーをインストールし、データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

<span data-ttu-id="e7e74-105">**重要**次の手順を実行する前に、「 [app-v 5.1 レポート](about-app-v-51-reporting.md)」を参照して理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e74-105">**Important** Before performing the following procedure you should read and understand [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

## <span data-ttu-id="e7e74-106">スタンドアロンコンピューターにレポートサーバーをインストールしてデータベースに接続するには</span><span class="sxs-lookup"><span data-stu-id="e7e74-106">To install the reporting server on a standalone computer and connect it to the database</span></span>

1. <span data-ttu-id="e7e74-107">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-107">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="e7e74-108">App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-108">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="e7e74-109">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-109">Click **Install**.</span></span>

2. <span data-ttu-id="e7e74-110">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-110">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3. <span data-ttu-id="e7e74-111">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-111">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="e7e74-112">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-112">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="e7e74-113">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-113">Click **Next**.</span></span>

4. <span data-ttu-id="e7e74-114">[**機能の選択**] ページで、[**レポートサーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-114">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5. <span data-ttu-id="e7e74-115">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-115">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6. <span data-ttu-id="e7e74-116">[**既存のレポートデータベースの構成**] ページで、[**リモート SQL server を使用**する] を選び、Microsoft sql server を実行しているコンピューターのコンピューター名 ( **SqlServerMachine**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-116">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e7e74-117">Microsoft SQL Server が同じサーバーに展開されている場合は、[**ローカル Sql server を使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="e7e74-117">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>

    <span data-ttu-id="e7e74-118">SQL Server インスタンスの場合は、[**既定のインスタンスの使用**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-118">For the SQL Server Instance, select **Use the default instance**.</span></span> <span data-ttu-id="e7e74-119">Microsoft SQL Server のカスタムインスタンスを使用している場合は、[**カスタムインスタンスの使用**] を選択し、インスタンスの名前を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e74-119">If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.</span></span>

    <span data-ttu-id="e7e74-120">このレポートサーバーで使用する**SQL Server データベース名**を指定します (例**AppvReporting**)。</span><span class="sxs-lookup"><span data-stu-id="e7e74-120">Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.</span></span>

7. <span data-ttu-id="e7e74-121">[**レポートサーバー構成の構成**] ページで、</span><span class="sxs-lookup"><span data-stu-id="e7e74-121">On the **Configure Reporting Server Configuration** page.</span></span>

   - <span data-ttu-id="e7e74-122">レポートサービスに使用する Web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-122">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="e7e74-123">カスタム名を指定しない場合は、既定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="e7e74-123">Leave the default unchanged if you do not have a custom name.</span></span>

   - <span data-ttu-id="e7e74-124">**ポートバインディング**には、 **55555**などの app-v 5.1 で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-124">For the **Port binding**, specify a unique port number that will be used by App-V 5.1, for example **55555**.</span></span> <span data-ttu-id="e7e74-125">指定したポートが別の web サイトで使用されていないことも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e7e74-125">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="e7e74-126">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="e7e74-126">Click **Install**.</span></span>

**<span data-ttu-id="e7e74-127">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="e7e74-127">Got an App-V issue?</span></span>** <span data-ttu-id="e7e74-128">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="e7e74-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="e7e74-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e7e74-129">Related topics</span></span>

[<span data-ttu-id="e7e74-130">App-V 5.1 のレポート機能について</span><span class="sxs-lookup"><span data-stu-id="e7e74-130">About App-V 5.1 Reporting</span></span>](about-app-v-51-reporting.md)

[<span data-ttu-id="e7e74-131">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="e7e74-131">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="e7e74-132">PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="e7e74-132">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)
