---
title: スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法
description: スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法
author: dansimp
ms.assetid: d186bdb7-e522-4124-bc6d-7d5a41ba8266
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f20f1ce16c3f0168d1c797efd816d4125c0f1f53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813986"
---
# <span data-ttu-id="4227b-103">スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="4227b-103">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>


<span data-ttu-id="4227b-104">次の手順を使用して、スタンドアロンコンピューターにレポートサーバーをインストールし、データベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="4227b-104">Use the following procedure to install the reporting server on a standalone computer and connect it to the database.</span></span>

**<span data-ttu-id="4227b-105">重要</span><span class="sxs-lookup"><span data-stu-id="4227b-105">Important</span></span>**  
<span data-ttu-id="4227b-106">次の手順を実行する前に、「 [app-v 5.0 レポート](about-app-v-50-reporting.md)」を参照して理解しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="4227b-106">Before performing the following procedure you should read and understand [About App-V 5.0 Reporting](about-app-v-50-reporting.md).</span></span>



**<span data-ttu-id="4227b-107">スタンドアロンコンピューターにレポートサーバーをインストールしてデータベースに接続するには</span><span class="sxs-lookup"><span data-stu-id="4227b-107">To install the reporting server on a standalone computer and connect it to the database</span></span>**

1.  <span data-ttu-id="4227b-108">アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="4227b-108">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="4227b-109">App-v 5.0 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="4227b-109">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="4227b-110">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-110">Click **Install**.</span></span>

2.  <span data-ttu-id="4227b-111">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="4227b-112">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4227b-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="4227b-113">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4227b-113">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="4227b-114">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-114">Click **Next**.</span></span>

4.  <span data-ttu-id="4227b-115">[**機能の選択**] ページで、[**レポートサーバー** ] チェックボックスをオンにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-115">On the **Feature Selection** page, select the **Reporting Server** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="4227b-116">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="4227b-117">[**既存のレポートデータベースの構成**] ページで、[**リモート SQL server を使用**する] を選び、Microsoft sql server を実行しているコンピューターのコンピューター名 ( **SqlServerMachine**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="4227b-117">On the **Configure Existing Reporting Database** page, select **Use a remote SQL Server**, and type the machine name of the computer running Microsoft SQL Server, for example **SqlServerMachine**.</span></span>

    **<span data-ttu-id="4227b-118">注</span><span class="sxs-lookup"><span data-stu-id="4227b-118">Note</span></span>**  
    <span data-ttu-id="4227b-119">Microsoft SQL Server が同じサーバーに展開されている場合は、[**ローカル Sql server を使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="4227b-119">If the Microsoft SQL Server is deployed on the same server, select **Use local SQL Server**.</span></span>



~~~
For the SQL Server Instance, select **Use the default instance**. If you are using a custom Microsoft SQL Server instance, you must select **Use a custom instance** and then type the name of the instance.

Specify the **SQL Server Database name** that this reporting server will use, for example **AppvReporting**.
~~~

7. <span data-ttu-id="4227b-120">[**レポートサーバー構成の構成**] ページで、</span><span class="sxs-lookup"><span data-stu-id="4227b-120">On the **Configure Reporting Server Configuration** page.</span></span>

   -   <span data-ttu-id="4227b-121">レポートサービスに使用する Web サイト名を指定します。</span><span class="sxs-lookup"><span data-stu-id="4227b-121">Specify the Website Name that you want to use for the Reporting Service.</span></span> <span data-ttu-id="4227b-122">カスタム名を指定しない場合は、既定のままにしておきます。</span><span class="sxs-lookup"><span data-stu-id="4227b-122">Leave the default unchanged if you do not have a custom name.</span></span>

   -   <span data-ttu-id="4227b-123">**ポートバインディング**には、 **55555**などの app-v 5.0 で使用される一意のポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="4227b-123">For the **Port binding**, specify a unique port number that will be used by App-V 5.0, for example **55555**.</span></span> <span data-ttu-id="4227b-124">指定したポートが別の web サイトで使用されていないことも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4227b-124">You should also ensure that the port specified is not being used by another website.</span></span>

8. <span data-ttu-id="4227b-125">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="4227b-125">Click **Install**.</span></span>

   <span data-ttu-id="4227b-126">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="4227b-126">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="4227b-127">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="4227b-127">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="4227b-128">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="4227b-128">Got an App-V issue?</span></span>** <span data-ttu-id="4227b-129">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="4227b-129">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="4227b-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4227b-130">Related topics</span></span>


[<span data-ttu-id="4227b-131">App-V 5.0 のレポート機能について</span><span class="sxs-lookup"><span data-stu-id="4227b-131">About App-V 5.0 Reporting</span></span>](about-app-v-50-reporting.md)

[<span data-ttu-id="4227b-132">APP-V 5.0 の展開</span><span class="sxs-lookup"><span data-stu-id="4227b-132">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)

[<span data-ttu-id="4227b-133">PowerShell を使用して App-V 5.0 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="4227b-133">How to Enable Reporting on the App-V 5.0 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)









