---
title: 管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法
description: 管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法
author: dansimp
ms.assetid: 2a67402e-3119-40ea-a247-24d166af1ced
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2332f674f10a9b60aa1cee814c6eac4ddbe4f5af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814034"
---
# <span data-ttu-id="2b570-103">管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2b570-103">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>

<span data-ttu-id="2b570-104">次の手順を使用して、データベースサーバーと管理サーバーを異なるコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b570-104">Use the following procedure to install the database server and management server on different computers.</span></span> <span data-ttu-id="2b570-105">データベースサーバーをインストールする予定のコンピューターでは、サポートされているバージョンの Microsoft SQL が実行されている必要があります。インストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="2b570-105">The computer you plan to install the database server on must be running a supported version of Microsoft SQL or the installation will fail.</span></span>

> [!NOTE]
> <span data-ttu-id="2b570-106">展開が完了すると、管理者がこれらのデータベースに接続できるように、 **MICROSOFT SQL Server 名**、**インスタンス名**、**データベース名**が必要になります。</span><span class="sxs-lookup"><span data-stu-id="2b570-106">After you complete the deployment, the **Microsoft SQL Server name**, **instance name** and **database name** will be required by the administrator installing the service to be able to connect to these databases.</span></span>

## <span data-ttu-id="2b570-107">管理データベースと管理サーバーを別々のコンピューターにインストールするには</span><span class="sxs-lookup"><span data-stu-id="2b570-107">To install the management database and the management server on separate computers</span></span>

1. <span data-ttu-id="2b570-108">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2b570-108">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="2b570-109">App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b570-109">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="2b570-110">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-110">Click **Install**.</span></span>
1. <span data-ttu-id="2b570-111">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-111">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="2b570-112">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b570-112">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="2b570-113">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b570-113">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="2b570-114">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-114">Click **Next**.</span></span>
1. <span data-ttu-id="2b570-115">[**機能の選択**] ページで、[ **Management Server データベース**] チェックボックスをオンにしてインストールするコンポーネントを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-115">On the **Feature Selection** page, select the components you want to install by selecting the **Management Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="2b570-116">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-116">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="2b570-117">[**新しい管理サーバーデータベースの新規作成] ページ**で、必要に応じて既定の選択内容をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-117">On the initial **Create New Management Server Database page**, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="2b570-118">カスタムの SQL Server インスタンスを使用している場合は、[**カスタムインスタンスの使用**] を選択し、インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b570-118">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.\</span></span>
    <span data-ttu-id="2b570-119">カスタムデータベース名を使用している場合は、[**カスタム構成**] を選択し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b570-119">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="2b570-120">次に [**新しい管理サーバーデータベースの作成**] ページで、[**リモートコンピューターを使用**する] を選び、次の形式でリモートコンピューターアカウントを入力します。 **Domain\\MachineAccount**</span><span class="sxs-lookup"><span data-stu-id="2b570-120">On the next **Create New Management Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b570-121">管理サーバーを同じコンピューターに展開する場合は、[**このローカルコンピューターを使用**する] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b570-121">If you plan to deploy the management server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="2b570-122">次の形式を使用して、管理サーバーの**インストール管理者**のユーザー名を指定します。 **Domain\\AdministratorLoginName**</span><span class="sxs-lookup"><span data-stu-id="2b570-122">Specify the user name for the management server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="2b570-123">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-123">Click **Next**.</span></span>
1. <span data-ttu-id="2b570-124">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-124">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="2b570-125">レポートデータベースとレポートサーバーを別々のコンピューターにインストールするには</span><span class="sxs-lookup"><span data-stu-id="2b570-125">To install the reporting database and the reporting server on separate computers</span></span>

1. <span data-ttu-id="2b570-126">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2b570-126">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span> <span data-ttu-id="2b570-127">App-v 5.1 server のインストールを開始するには、右クリックして、管理者として**appv\_server\_setup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b570-127">To start the App-V 5.1 server installation right-click and run **appv\_server\_setup.exe** as an administrator.</span></span> <span data-ttu-id="2b570-128">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-128">Click **Install**.</span></span>
1. <span data-ttu-id="2b570-129">[はじめ**に] ページで**、ライセンス条項を確認して同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-129">On the **Getting Started** page, review and accept the license terms, and click **Next**.</span></span>
1. <span data-ttu-id="2b570-130">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b570-130">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates, select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="2b570-131">Microsoft 更新プログラムを無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b570-131">To disable Microsoft updates, select **I don't want to use Microsoft Update**.</span></span> <span data-ttu-id="2b570-132">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-132">Click **Next**.</span></span>
1. <span data-ttu-id="2b570-133">[**機能の選択**] ページで、[**レポートサーバーデータベース**] チェックボックスをオンにして、インストールするコンポーネントを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-133">On the **Feature Selection** page, select the components you want to install by selecting the **Reporting Server Database** checkbox and click **Next**.</span></span>
1. <span data-ttu-id="2b570-134">[**インストール場所**] ページで、既定の場所をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-134">On the **Installation Location** page, accept the default location and click **Next**.</span></span>
1. <span data-ttu-id="2b570-135">[最初に**新しいレポートサーバーデータベースを作成**する] ページで、必要に応じて既定の選択内容をそのまま使用し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-135">On the initial **Create New Reporting Server Database** page, accept the default selections if appropriate, and click **Next**.</span></span>

    <span data-ttu-id="2b570-136">カスタムの SQL Server インスタンスを使用している場合は、[**カスタムインスタンスの使用**] を選択し、インスタンスの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b570-136">If you are using a custom SQL Server instance, then select **Use a custom instance** and type the name of the instance.</span></span>
    <span data-ttu-id="2b570-137">カスタムデータベース名を使用している場合は、[**カスタム構成**] を選択し、データベース名を入力します。</span><span class="sxs-lookup"><span data-stu-id="2b570-137">If you are using a custom database name, then select **Custom configuration** and type the database name.</span></span>

1. <span data-ttu-id="2b570-138">[次の**新しいレポートサーバーデータベースを作成**する] ページで、[**リモートコンピューターを使用**する] を選び、次の形式でリモートコンピューターアカウントを入力します。 **Domain\\MachineAccount**</span><span class="sxs-lookup"><span data-stu-id="2b570-138">On the next **Create New Reporting Server Database** page, select **Use a remote computer**, and type the remote machine account using the following format: **Domain\\MachineAccount**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b570-139">レポートサーバーを同じコンピューターに展開する場合は、[**このローカルコンピューターを使用**する] を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b570-139">If you plan to deploy the reporting server on the same computer you must select **Use this local computer**.</span></span>

1. <span data-ttu-id="2b570-140">次の形式を使用して、レポートサーバーの**インストール管理者**のユーザー名を指定します。 **Domain\\AdministratorLoginName**</span><span class="sxs-lookup"><span data-stu-id="2b570-140">Specify the user name for the reporting server **Install Administrator** using the following format: **Domain\\AdministratorLoginName**.</span></span> <span data-ttu-id="2b570-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-141">Click **Next**.</span></span>
1. <span data-ttu-id="2b570-142">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b570-142">To start the installation, click **Install**.</span></span>

## <span data-ttu-id="2b570-143">App-v 5.1 データベーススクリプトを使って、管理データベースとレポートデータベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="2b570-143">To install the management and reporting databases using App-V 5.1 database scripts</span></span>

1. <span data-ttu-id="2b570-144">アプリをインストールするコンピューターに、App-v 5.1 サーバーのインストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2b570-144">Copy the App-V 5.1 server installation files to the computer on which you want to install it on.</span></span>
1. <span data-ttu-id="2b570-145">App-v 5.1 データベーススクリプトを抽出するには、コマンドプロンプトを開いて、インストールファイルが保存されている場所を指定し、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b570-145">To extract the App-V 5.1 database scripts, open a command prompt and specify the location where the installation files are saved and run the following command:</span></span>

    <span data-ttu-id="2b570-146">**appv\_server\_setup.exe** **/レイアウト** **/Layoutdir = "installationextractionlocation"**。</span><span class="sxs-lookup"><span data-stu-id="2b570-146">**appv\_server\_setup.exe** **/LAYOUT** **/LAYOUTDIR="InstallationExtractionLocation"**.</span></span>

1. <span data-ttu-id="2b570-147">抽出が完了した後、App-v 5.1 データベーススクリプトと手順 readme ファイルにアクセスするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="2b570-147">After the extraction has been completed, to access the App-V 5.1 database scripts and instructions readme file:</span></span>

    - <span data-ttu-id="2b570-148">App-v 5.1 管理データベーススクリプトと手順 readme は、次のフォルダーにあります。 **installationextractionlocation**  \\  **データベーススクリプト**  \\  **管理データベース**。</span><span class="sxs-lookup"><span data-stu-id="2b570-148">The App-V 5.1 Management Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Management Database**.</span></span>
    - <span data-ttu-id="2b570-149">App-v 5.1 レポートデータベーススクリプトと手順 readme は、次のフォルダーにあります。 **installationextractionlocation**  \\  **データベーススクリプト**  \\  **レポートデータベース**。</span><span class="sxs-lookup"><span data-stu-id="2b570-149">The App-V 5.1 Reporting Database scripts and instructions readme are located in the following folder: **InstallationExtractionLocation** \\ **Database Scripts** \\ **Reporting Database**.</span></span>

1. <span data-ttu-id="2b570-150">各データベースについて、スクリプトを共有にコピーし、readme ファイルの手順に従って変更します。</span><span class="sxs-lookup"><span data-stu-id="2b570-150">For each database, copy the scripts to a share and modify them following the instructions in the readme file.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b570-151">スクリプトに含まれる必要な Sid の変更の詳細については、「 [PowerShell を使用して、App-v データベースをインストールして、関連付けられたセキュリティ識別子を変換する方法](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2b570-151">For more information about modifying the required SIDs contained in the scripts, see [How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell51.md).</span></span>

1. <span data-ttu-id="2b570-152">Microsoft SQL Server を実行しているコンピューターでスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b570-152">Run the scripts on the computer running Microsoft SQL Server.</span></span>

**<span data-ttu-id="2b570-153">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="2b570-153">Got an App-V issue?</span></span>** <span data-ttu-id="2b570-154">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="2b570-154">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="2b570-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2b570-155">Related topics</span></span>

[<span data-ttu-id="2b570-156">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="2b570-156">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
