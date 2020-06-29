---
title: Configuration Manager と共に MBAM をインストールする方法
description: Configuration Manager と共に MBAM をインストールする方法
author: dansimp
ms.assetid: fd0832e4-3b79-4e56-9550-d2f396be6d09
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a556ce961e6a423caecdd0766cf8623383897b58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825127"
---
# <span data-ttu-id="27e92-103">Configuration Manager と共に MBAM をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="27e92-103">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="27e92-104">このセクションでは、configuration manager を使用して MBAM をインストールする手順について説明します。推奨される構成は、「はじめに」の「 [mbam-Configuration manager](getting-started---using-mbam-with-configuration-manager.md)での使用」で説明しています。</span><span class="sxs-lookup"><span data-stu-id="27e92-104">This section describes the steps to install MBAM with Configuration Manager by using the recommended configuration, which is illustrated in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="27e92-105">手順は次のタスクに分類されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-105">The steps are divided into the following tasks:</span></span>

-   <span data-ttu-id="27e92-106">Configuration Manager サーバーに MBAM をインストールして構成する</span><span class="sxs-lookup"><span data-stu-id="27e92-106">Install and configure MBAM on the Configuration Manager Server</span></span>

-   <span data-ttu-id="27e92-107">データベースサーバーに回復データベースと監査データベースをインストールする</span><span class="sxs-lookup"><span data-stu-id="27e92-107">Install the Recovery and Audit Databases on the Database Server</span></span>

-   <span data-ttu-id="27e92-108">管理と監視サーバーにサーバー機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="27e92-108">Install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>

<span data-ttu-id="27e92-109">インストールを開始する前に、必要な mof ファイルを編集または作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e92-109">Before you begin the installation, ensure that you have edited or created the necessary mof files.</span></span> <span data-ttu-id="27e92-110">手順については、「 [Mof ファイルを作成または編集する方法](how-to-create-or-edit-the-mof-files.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27e92-110">For instructions, see [How to Create or Edit the mof Files](how-to-create-or-edit-the-mof-files.md).</span></span>

<span data-ttu-id="27e92-111">**重要** 既定以外の SQL Server Reporting Services (SSRS) インスタンスを使用している場合、次のコマンドラインを使用して、SSRS という名前付きインスタンスを指定して、MBAM セットアップを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-111">**Important** If you are using a non-default SQL Server Reporting Services (SSRS) instance, you must start the MBAM Setup by using the following command line to specify the SSRS named instance:</span></span>

`MbamSetup.exe CM_SSRS_INSTANCE_NAME=<NamedInstance>`

 

**<span data-ttu-id="27e92-112">Configuration Manager サーバーに MBAM をインストールするには</span><span class="sxs-lookup"><span data-stu-id="27e92-112">To install MBAM on the Configuration Manager Server</span></span>**

1.  <span data-ttu-id="27e92-113">Configuration Manager サーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="27e92-113">On the Configuration Manager Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

    <span data-ttu-id="27e92-114">**注** セットアップログファイルを取得するには、Msiexec.exe パッケージと **/l** location オプションを使用して構成マネージャーをインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="27e92-114">**Note** To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install Configuration Manager.</span></span> <span data-ttu-id="27e92-115">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-115">Log files are created in the location that you specify.</span></span>

    <span data-ttu-id="27e92-116">追加のセットアップログファイルは、Configuration Manager をインストールしているユーザーのコンピューター上の% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-116">Additional setup log files are created in the %temp% folder on the computer of the user who is installing Configuration Manager.</span></span>

     

2.  <span data-ttu-id="27e92-117">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-117">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="27e92-118">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-118">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="27e92-119">[**トポロジの選択**] ページで、[ **System Center Configuration Manager の統合**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-119">On the **Topology Selection** page, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

5.  <span data-ttu-id="27e92-120">[**インストールする機能の選択**] ページで、[ **System Center Configuration Manager の統合**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27e92-120">On the **Select features to install** page, select **System Center Configuration Manager Integration**.</span></span>

    <span data-ttu-id="27e92-121">**注** [**前提条件の確認**] ページで、インストールウィザードによってインストールの前提条件がチェックされた後、[**次へ**] をクリックし、何も表示されないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27e92-121">**Note** On the **Checking Prerequisites** page, click **Next** after the installation wizard checks the prerequisites for your installation and confirms that none are missing.</span></span> <span data-ttu-id="27e92-122">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-122">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again.**</span></span>

     

6.  <span data-ttu-id="27e92-123">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-123">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="27e92-124">Microsoft Update を使用しても、Windows で自動更新が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="27e92-124">Using Microsoft Updates does not turn on Automatic Updates in Windows.</span></span>

7.  <span data-ttu-id="27e92-125">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-125">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="27e92-126">[**インストールの概要**] ページで、インストールされる機能の一覧を確認し、[**インストール**] をクリックして、mbam 機能のインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="27e92-126">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="27e92-127">インストール設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを前の画面に移動するか、[**キャンセル**] をクリックしてセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="27e92-127">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="27e92-128">セットアップによって、MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-128">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

9.  <span data-ttu-id="27e92-129">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="27e92-129">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="27e92-130">データベースサーバーに回復データベースと監査データベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="27e92-130">To install the Recovery and Audit Databases on the Database Server</span></span>**

1.  <span data-ttu-id="27e92-131">データベースサーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="27e92-131">On the Database Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="27e92-132">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-132">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="27e92-133">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-133">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="27e92-134">[**トポロジの選択**] ページで、 **System Center Configuration Manager 統合**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-134">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="27e92-135">インストールする機能の一覧から、[**データベースの回復**] と [**データベースの監査**] を選択し、残りの機能をクリアします。</span><span class="sxs-lookup"><span data-stu-id="27e92-135">From the list of features to install, select **Recovery Database** and **Audit Database**, and clear the remaining features.</span></span>

    <span data-ttu-id="27e92-136">**注** インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-136">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="27e92-137">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="27e92-138">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="27e92-139">すべての前提条件が現在満たされている場合は、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-139">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="27e92-140">[**回復データベースの構成**] ページで、管理/監視サーバー機能を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e92-140">On the **Configure the Recovery Database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="27e92-141">管理と監視のサーバー機能が展開されると、そのドメインアカウントを使用してデータベースに接続されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-141">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

7.  <span data-ttu-id="27e92-142">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-142">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="27e92-143">SQL Server インスタンスの名前と、回復データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e92-143">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="27e92-144">また、データベースが配置される場所とログ情報が配置される場所の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-144">You must also specify both where the database will be located and where the log information will be located.</span></span>

9.  <span data-ttu-id="27e92-145">[**次へ**] をクリックして、mbam セットアップインストールウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-145">Click **Next** to continue with the MBAM Setup installation wizard.</span></span>

10. <span data-ttu-id="27e92-146">[**監査データベースの構成**] ページで、レポートのデータベースにアクセスするために使用されるユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="27e92-146">On the **Configure the Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

11. <span data-ttu-id="27e92-147">管理/監視サーバーおよび監査レポートを実行するコンピューターのコンピューター名を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e92-147">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Audit Reports.</span></span> <span data-ttu-id="27e92-148">管理と監視、および監査レポート機能が展開されると、そのドメインアカウントを使用してデータベースに接続されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-148">After the Administration and Monitoring and the Audit Reports features are deployed, their domain accounts will be used to connect to the databases.</span></span>

    <span data-ttu-id="27e92-149">**注** 監査レポート機能なしで監査データベースをインストールする場合は、監査データベースコンピューターで例外を追加して、Microsoft SQL Server ポートで受信トラフィックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-149">**Note** If you are installing the Audit Database without the Audit Reports feature, you must add an exception on the Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="27e92-150">既定のポート番号は1433です。</span><span class="sxs-lookup"><span data-stu-id="27e92-150">The default port number is 1433.</span></span>

     

12. <span data-ttu-id="27e92-151">SQL Server インスタンスの名前と、監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="27e92-151">Specify the SQL Server instance name and the name of the database that will store the audit data.</span></span> <span data-ttu-id="27e92-152">また、データベースとログ情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-152">You must also specify where the database and log information will be located.</span></span>

13. <span data-ttu-id="27e92-153">[**インストール**] をクリックしてインストールを開始し、[**完了**] をクリックしてインストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="27e92-153">Click **Install** to start the installation, and then click **Finish** to complete the installation.</span></span>

**<span data-ttu-id="27e92-154">管理と監視サーバーにサーバー機能をインストールするには</span><span class="sxs-lookup"><span data-stu-id="27e92-154">To install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="27e92-155">管理および監視サーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="27e92-155">On the Administration and Monitoring Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="27e92-156">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-156">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="27e92-157">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="27e92-157">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="27e92-158">[**トポロジの選択**] ページで、 **System Center Configuration Manager 統合**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="27e92-158">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="27e92-159">インストールする機能の一覧から、[**管理/監視サーバー**と**セルフサービスポータル**] を選択し、残りの機能をクリアします。</span><span class="sxs-lookup"><span data-stu-id="27e92-159">From the list of features to install, select **Administration and Monitoring Server** and **Self-Service Portal**, and clear the remaining features.</span></span>

    <span data-ttu-id="27e92-160">**注** インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-160">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="27e92-161">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-161">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="27e92-162">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27e92-162">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="27e92-163">すべての前提条件が現在満たされている場合は、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="27e92-163">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="27e92-164">**「展開された**[サーバーに mbam をインストールして構成](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)する」の手順に従って、セルフサービスポータルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="27e92-164">Install the Self-Service Portal by following the steps in the **To install the Self-Service Portal** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

    <span data-ttu-id="27e92-165">**注** クライアントコンピューターが Microsoft コンテンツ配信ネットワーク (CDN) にアクセスできない場合は、セルフサービスポータルには、特定の JavaScript ファイルに必要なアクセス権が付与されます。「 **Microsoft コンテンツ配信ネットワークにアクセスできない場合**にセルフサービスポータルを構成する」セクションの手順を実行して、アクセシビリティの高いソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成する[方法につい](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)て説明します。</span><span class="sxs-lookup"><span data-stu-id="27e92-165">**Note** If the client computers will not have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, complete the steps in the **To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network** section [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md) to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

     

7.  <span data-ttu-id="27e92-166">「管理と監視サーバー**機能をインストールする**方法」の手順に従って、[分散サーバーに mbam をインストールして構成する](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)ことにより、管理および監視サーバー機能をインストールします。</span><span class="sxs-lookup"><span data-stu-id="27e92-166">Install the Administration and Monitoring Server features by following the steps in the **To install the Administration and Monitoring Server feature** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

8.  <span data-ttu-id="27e92-167">[**完了**] をクリックして、インストールを完了します。</span><span class="sxs-lookup"><span data-stu-id="27e92-167">Click **Finish** to complete the installation.</span></span>

## <span data-ttu-id="27e92-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="27e92-168">Related topics</span></span>


[<span data-ttu-id="27e92-169">Configuration Manager で MBAM のインストールを検証する方法</span><span class="sxs-lookup"><span data-stu-id="27e92-169">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

[<span data-ttu-id="27e92-170">Configuration Manager による MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="27e92-170">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





