---
title: 管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法
description: 管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法
author: dansimp
ms.assetid: 02afd6d6-4c33-4c0b-bd88-ae167b786fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1522045fced411164ac4fd36af41d46ab61ad6f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814026"
---
# <span data-ttu-id="1c7e6-103">管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="1c7e6-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>


<span data-ttu-id="1c7e6-104">次の手順を使用して、データベースサーバーと管理サーバーを異なるコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="1c7e6-105">データベースサーバーをインストールする予定のコンピューターでは、サポートされているバージョンの Microsoft SQL が実行されている必要があります。インストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

**<span data-ttu-id="1c7e6-106">注</span><span class="sxs-lookup"><span data-stu-id="1c7e6-106">Note</span></span>**  
<span data-ttu-id="1c7e6-107">展開が完了すると、管理者がこれらのデータベースに接続できるように、 **MICROSOFT SQL Server 名**、**インスタンス名**、**データベース名**が必要になります。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-107">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>



**<span data-ttu-id="1c7e6-108">管理データベースと管理サーバーを別々のコンピューターにインストールするには</span><span class="sxs-lookup"><span data-stu-id="1c7e6-108">To install the management database and the management server on separate computers</span></span>**

1.  <span data-ttu-id="1c7e6-109">アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-109">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="1c7e6-110">App-v 5.0 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-110">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="1c7e6-111">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-111">Click **Install**.</span></span>

2.  <span data-ttu-id="1c7e6-112">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-112">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="1c7e6-113">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-113">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="1c7e6-114">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-114">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="1c7e6-115">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-115">Click **Next**.</span></span>

4.  <span data-ttu-id="1c7e6-116">[**機能の選択**] ページで、[ **Management Server データベース**] チェックボックスをオンにしてインストールするコンポーネントを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-116">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="1c7e6-117">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-117">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="1c7e6-118">[**新しい管理サーバーデータベースの新規作成] ページ**で、必要に応じて既定の選択内容をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-118">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="1c7e6-119">カスタムの SQL Server インスタンスを使用している場合は、[**カスタムインスタンスの使用**] を選択し、インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-119">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="1c7e6-120">カスタムデータベース名を使用している場合は、[**カスタム構成**] を選択し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-120">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="1c7e6-121">次に [**新しい管理サーバーデータベースの作成**] ページで、[**リモートコンピューターを使用**する] を選び、次の形式でリモートコンピューターアカウントを入力します。 **Domain\\MachineAccount**</span><span class="sxs-lookup"><span data-stu-id="1c7e6-121">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="1c7e6-122">注</span><span class="sxs-lookup"><span data-stu-id="1c7e6-122">Note</span></span>**  
    <span data-ttu-id="1c7e6-123">管理サーバーを同じコンピューターに展開する場合は、[**このローカルコンピューターを使用**する] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-123">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="1c7e6-124">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-124">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="1c7e6-125">レポートデータベースとレポートサーバーを別々のコンピューターにインストールするには</span><span class="sxs-lookup"><span data-stu-id="1c7e6-125">To install the reporting database and the reporting server on separate computers</span></span>**

1.  <span data-ttu-id="1c7e6-126">アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-126">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="1c7e6-127">App-v 5.0 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-127">To start the App-V 5.0 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="1c7e6-128">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-128">Click **Install**.</span></span>

2.  <span data-ttu-id="1c7e6-129">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>

3.  <span data-ttu-id="1c7e6-130">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="1c7e6-131">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-131">To disable Microsoft updates, select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="1c7e6-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-132">Click **Next**.</span></span>

4.  <span data-ttu-id="1c7e6-133">[**機能の選択**] ページで、[**レポートサーバーデータベース**] チェックボックスをオンにして、インストールするコンポーネントを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>

5.  <span data-ttu-id="1c7e6-134">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>

6.  <span data-ttu-id="1c7e6-135">[最初に**新しいレポートサーバーデータベースを作成**する] ページで、必要に応じて既定の選択内容をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="1c7e6-136">カスタムの SQL Server インスタンスを使用している場合は、[**カスタムインスタンスの使用**] を選択し、インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>

    <span data-ttu-id="1c7e6-137">カスタムデータベース名を使用している場合は、[**カスタム構成**] を選択し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

7.  <span data-ttu-id="1c7e6-138">[次の**新しいレポートサーバーデータベースを作成**する] ページで、[**リモートコンピューターを使用**する] を選び、次の形式でリモートコンピューターアカウントを入力します。 **Domain\\MachineAccount**</span><span class="sxs-lookup"><span data-stu-id="1c7e6-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    **<span data-ttu-id="1c7e6-139">注</span><span class="sxs-lookup"><span data-stu-id="1c7e6-139">Note</span></span>**  
    <span data-ttu-id="1c7e6-140">レポートサーバーを同じコンピューターに展開する場合は、[**このローカルコンピューターを使用**する] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-140">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>



~~~
Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**. Click **Next**.
~~~

8. <span data-ttu-id="1c7e6-141">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-141">To start the installation, click **Install**.</span></span>

**<span data-ttu-id="1c7e6-142">App-v 5.0 データベーススクリプトを使って、管理データベースとレポートデータベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="1c7e6-142">To install the management and reporting databases using App-V 5.0 database scripts</span></span>**

1.  <span data-ttu-id="1c7e6-143">アプリをインストールするコンピューターに、App-v 5.0 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-143">Copy the App-V 5.0 server installation files to the computer on which you want to install it on.</span></span>

2.  <span data-ttu-id="1c7e6-144">App-v 5.0 データベーススクリプトを抽出するには、コマンドプロンプトを開いて、インストールファイルが保存されている場所を指定し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-144">To extract the App-V 5.0 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="1c7e6-145">**appv\_server\_setup.exe** **/レイアウト** **/Layoutdir = "installationextractionlocation"**。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-145">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR=”InstallationExtractionLocation”**.</span></span>

3.  <span data-ttu-id="1c7e6-146">抽出が完了した後、App-v 5.0 データベーススクリプトと手順 readme ファイルにアクセスするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-146">After the extraction has been completed, to access the App-V 5.0 database scripts and instructions readme file:</span></span>

    -   <span data-ttu-id="1c7e6-147">App-v 5.0 管理データベーススクリプトと手順 readme は、次のフォルダーにあります。 **installationextractionlocation**  \\  **データベーススクリプト**  \\  **管理データベース**。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-147">The App-V 5.0 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>

    -   <span data-ttu-id="1c7e6-148">App-v 5.0 レポートデータベーススクリプトと手順 readme は、次のフォルダーにあります。 **installationextractionlocation**  \\  **データベーススクリプト**  \\  **レポートデータベース**。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-148">The App-V 5.0 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

4.  <span data-ttu-id="1c7e6-149">各データベースについて、スクリプトを共有にコピーし、readme ファイルの手順に従って変更します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-149">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    **<span data-ttu-id="1c7e6-150">注</span><span class="sxs-lookup"><span data-stu-id="1c7e6-150">Note</span></span>**  
    <span data-ttu-id="1c7e6-151">スクリプトに含まれる必要な Sid の変更の詳細については、「 [App-v データベースをインストールする方法」と「PowerShell を使用して、関連付けられたセキュリティ識別子を変換する方法](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-151">For more information about modifying the required SIDs contained in the scripts see, [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md).</span></span>



5.  <span data-ttu-id="1c7e6-152">Microsoft SQL Server を実行しているコンピューターでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

    <span data-ttu-id="1c7e6-153">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-153">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="1c7e6-154">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-154">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="1c7e6-155">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="1c7e6-155">Got an App-V issue?</span></span>** <span data-ttu-id="1c7e6-156">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="1c7e6-156">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="1c7e6-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1c7e6-157">Related topics</span></span>


[<span data-ttu-id="1c7e6-158">APP-V 5.0 の展開</span><span class="sxs-lookup"><span data-stu-id="1c7e6-158">Deploying App-V 5.0</span></span>](deploying-app-v-50.md)









