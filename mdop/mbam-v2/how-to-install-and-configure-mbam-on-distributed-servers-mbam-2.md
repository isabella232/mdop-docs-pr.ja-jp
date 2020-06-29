---
title: 分散サーバーに MBAM をインストールして構成する方法
description: 分散サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824057"
---
# <span data-ttu-id="d37eb-103">分散サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="d37eb-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="d37eb-104">このトピックの手順では、分散サーバー上のスタンドアロントポロジで Microsoft BitLocker 管理と監視 (MBAM) 2.0 をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in the Stand-alone topology on distributed servers.</span></span> <span data-ttu-id="d37eb-105">推奨されるアーキテクチャとデータベースおよび機能の説明を示す図を表示するには、「 [MBAM 2.0 サーバーインフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-105">To see a diagram of the recommended architecture, along with a description of the databases and features, see [Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md).</span></span> <span data-ttu-id="d37eb-106">Configuration Manager トポロジを使用して Microsoft BitLocker の管理と監視をインストールするには、「 [Configuration manager で MBAM を展開](deploying-mbam-with-configuration-manager-mbam2.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-106">To install Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="d37eb-107">各サーバー機能には、いくつかの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-107">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="d37eb-108">前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)と[Mbam 2.0 でサポートさ](mbam-20-supported-configurations-mbam-2.md)れている構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-108">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="d37eb-109">さらに、一部の機能では、インストールプロセス中に機能を正常に展開するために特定の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-109">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="d37eb-110">MBAM 展開を開始する前に、 [mbam 2.0 サーバー展開の計画](planning-for-mbam-20-server-deployment-mbam-2.md)も確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-110">You should also review [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md) before you start the MBAM deployment.</span></span>

**<span data-ttu-id="d37eb-111">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-111">Note</span></span>**  
<span data-ttu-id="d37eb-112">セットアップログファイルを取得するには、Msiexec.exe パッケージと [ **/l** location] オプションを使用して mbam をインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-112">To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="d37eb-113">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-113">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="d37eb-114">追加のセットアップログファイルは、MBAM をインストールしているユーザーのサーバー上の% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-114">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <a href="" id="deploying-mbam-server-features-"></a><span data-ttu-id="d37eb-115">MBAM サーバー機能の展開</span><span class="sxs-lookup"><span data-stu-id="d37eb-115">Deploying MBAM Server Features</span></span>


<span data-ttu-id="d37eb-116">次の手順では、一般的な MBAM 機能をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-116">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="d37eb-117">MBAM サーバーインストールウィザードを起動するには</span><span class="sxs-lookup"><span data-stu-id="d37eb-117">To start the MBAM Server installation wizard</span></span>**

1.  <span data-ttu-id="d37eb-118">Microsoft BitLocker の管理と監視をインストールするサーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-118">On the server where you want to install Microsoft BitLocker Administration and Monitoring, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="d37eb-119">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-119">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="d37eb-120">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-120">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="d37eb-121">[**トポロジの選択**] ページで、**スタンドアロン**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-121">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

    **<span data-ttu-id="d37eb-122">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-122">Note</span></span>**  
    <span data-ttu-id="d37eb-123">Configuration Manager の統合トポロジで MBAM をインストールする場合は、「 [Configuration manager で MBAM を展開](deploying-mbam-with-configuration-manager-mbam2.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-123">If you want to install MBAM with the Configuration Manager integrated topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>



5.  <span data-ttu-id="d37eb-124">インストールする機能を選びます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-124">Select the features that you want to install.</span></span> <span data-ttu-id="d37eb-125">既定では、すべての MBAM 機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="d37eb-125">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="d37eb-126">他の場所でインストールする機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-126">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="d37eb-127">同じコンピューターにインストールされる機能は、同時にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-127">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="d37eb-128">MBAM 機能は次の順序でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-128">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="d37eb-129">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="d37eb-129">Recovery Database</span></span>

    -   <span data-ttu-id="d37eb-130">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="d37eb-130">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="d37eb-131">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="d37eb-131">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="d37eb-132">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="d37eb-132">Self-Service Portal</span></span>

    -   <span data-ttu-id="d37eb-133">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="d37eb-133">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="d37eb-134">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="d37eb-134">MBAM Group Policy template</span></span>

    **<span data-ttu-id="d37eb-135">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-135">Note</span></span>**  
    <span data-ttu-id="d37eb-136">インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-136">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="d37eb-137">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="d37eb-138">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="d37eb-139">すべての前提条件が現在満たされている場合は、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-139">If all prerequisites are met this time, the installation resumes.</span></span>



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**<span data-ttu-id="d37eb-140">回復データベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d37eb-140">To install the Recovery Database</span></span>**

1.  <span data-ttu-id="d37eb-141">[**回復データベースの構成**] ページで、管理/監視サーバー機能を実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-141">On the **Configure the Recovery database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="d37eb-142">管理と監視のサーバー機能が展開されると、そのドメインアカウントを使用してデータベースに接続されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-142">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

2.  <span data-ttu-id="d37eb-143">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-143">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="d37eb-144">SQL Server インスタンスの名前と、回復データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-144">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="d37eb-145">また、データベースが配置される場所とログ情報が配置される場所の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-145">You must also specify both where the database will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="d37eb-146">[**次へ**] をクリックして、mbam セットアップウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-146">Click **Next** to continue with the MBAM Setup wizard.</span></span>

**<span data-ttu-id="d37eb-147">コンプライアンスと監査データベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d37eb-147">To install the Compliance and Audit Database</span></span>**

1.  <span data-ttu-id="d37eb-148">[**コンプライアンスと監査データベースの構成**] ページで、レポートのデータベースへのアクセスに使用するユーザーアカウントを指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-148">On the **Configure the Compliance and Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

2.  <span data-ttu-id="d37eb-149">管理/監視サーバーを実行しているコンピューターと、コンプライアンスおよび監査レポートを実行するコンピューターの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-149">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Compliance and Audit Reports.</span></span> <span data-ttu-id="d37eb-150">管理と監視、コンプライアンスおよび監査レポートサーバーが展開されたら、ドメインアカウントを使用してデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-150">After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they use their domain accounts to connect to the databases.</span></span>

    **<span data-ttu-id="d37eb-151">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-151">Note</span></span>**  
    <span data-ttu-id="d37eb-152">コンプライアンスと監査レポート機能を使わずにコンプライアンスおよび監査データベースをインストールする場合は、コンプライアンスと監査データベースコンピューターで例外を追加して、Microsoft SQL Server ポートで受信トラフィックを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-152">If you are installing the Compliance and Audit Database without the Compliance and Audit Reports feature, you must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="d37eb-153">既定のポート番号は1433です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-153">The default port number is 1433.</span></span>



3.  <span data-ttu-id="d37eb-154">SQL Server インスタンスの名前と、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-154">Specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="d37eb-155">また、データベースとログ情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-155">You must also specify where the database and log information will be located.</span></span>

4.  <span data-ttu-id="d37eb-156">[**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-156">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="d37eb-157">コンプライアンスと監査レポートをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d37eb-157">To install the Compliance and Audit Reports</span></span>**

1.  <span data-ttu-id="d37eb-158">[**コンプライアンスおよび監査レポートの構成**] ページで、 &lt; &gt; コンプライアンスと監査データベースがインストールされているリモートの SQL Server インスタンス名 (例、ServerName) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-158">On the **Configure the Compliance and Audit Reports** page, specify the remote SQL Server instance name (for example, &lt;ServerName&gt;) where the Compliance and Audit Database was installed.</span></span>

    **<span data-ttu-id="d37eb-159">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-159">Note</span></span>**  
    <span data-ttu-id="d37eb-160">管理および監視サーバーなしでコンプライアンスレポートと監査レポートをインストールする場合は、コンプライアンスと監査レポートコンピューターで例外を追加して、レポートサーバーのポートで受信トラフィックを有効にする必要があります (既定のポートは 80)。</span><span class="sxs-lookup"><span data-stu-id="d37eb-160">If you are installing the Compliance and Audit Reports without the Administration and Monitoring Server, you must add an exception on the Compliance and Audit Report computer to enable inbound traffic on the Reporting Server port (the default port is 80).</span></span>



2.  <span data-ttu-id="d37eb-161">コンプライアンスおよび監査データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-161">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="d37eb-162">既定では、データベース名は MBAM コンプライアンスの状態ですが、コンプライアンスと監査データベースをインストールするときに名前を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-162">By default, the database name is MBAM Compliance Status, although you can change the name when you install the Compliance and Audit Database.</span></span>

3.  <span data-ttu-id="d37eb-163">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-163">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="d37eb-164">コンプライアンスと監査レポートをインストールする SQL Server Reporting Services のインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-164">Select the instance of SQL Server Reporting Services where the Compliance and Audit Reports will be installed.</span></span> <span data-ttu-id="d37eb-165">ドメインユーザーアカウントとパスワードを入力して、コンプライアンスデータベースおよび監査データベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-165">Provide a domain user account and password to access the Compliance and Audit Database.</span></span> <span data-ttu-id="d37eb-166">有効期限が切れないように、このアカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-166">Configure the password for this account to never expire.</span></span> <span data-ttu-id="d37eb-167">ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-167">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span>

5.  <span data-ttu-id="d37eb-168">[**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-168">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="d37eb-169">セルフサービスポータルをインストールするには</span><span class="sxs-lookup"><span data-stu-id="d37eb-169">To install the Self-Service Portal</span></span>**

1.  <span data-ttu-id="d37eb-170">[**セルフサービスポータルの構成**] ページで、必要に応じてセルフサービスポータルと管理サーバーと監視サーバー間の通信を暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-170">On the **Configure the Self-Service Portal** page, you can optionally encrypt the communication between the Self-Service Portal and the Administration and Monitoring servers.</span></span> <span data-ttu-id="d37eb-171">通信を暗号化するためのオプションを選択した場合は、暗号化に使用する証明機関がプロビジョニングした証明書を選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-171">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2.  <span data-ttu-id="d37eb-172">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-172">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="d37eb-173">コンプライアンスと監査データベースがインストールされている SQL Server のリモートインスタンス (たとえば、 \* &lt; ServerName &gt; \*) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-173">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4.  <span data-ttu-id="d37eb-174">コンプライアンスおよび監査データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-174">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="d37eb-175">既定では、データベース名は MBAM コンプライアンスの状態です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-175">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="d37eb-176">ただし、コンプライアンスと監査データベースをインストールするときに、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-176">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5.  <span data-ttu-id="d37eb-177">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-177">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="d37eb-178">回復データベースがインストールされている SQL Server のリモートインスタンス (たとえば、 \* &lt; ServerName &gt; \*) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-178">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7.  <span data-ttu-id="d37eb-179">回復データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-179">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="d37eb-180">既定では、データベース名は**Mbam 回復とハードウェア**です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-180">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="d37eb-181">ただし、回復データベース機能をインストールするときに、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-181">However, you can change the name when you install the Recovery Database feature.</span></span>

8.  <span data-ttu-id="d37eb-182">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-182">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="d37eb-183">[**ポート番号**]、[**ホスト名**] (省略可能)、Mbam 管理および監視サーバーの**インストールパス**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-183">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="d37eb-184">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-184">Note</span></span>**  
    <span data-ttu-id="d37eb-185">一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-185">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="d37eb-186">Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-186">If you are using Windows Firewall, the port will be opened automatically.</span></span>



10. <span data-ttu-id="d37eb-187">必要に応じてセルフサービスポータルのサービスプリンシパル名 (SPN) を登録するには、[**このコンピューターのサービスプリンシパル名 (spn) を Active Directory との間で登録する] (Windows 認証に必要)** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-187">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="d37eb-188">このチェックボックスをオンにすると、MBAM セットアップは既存の Spn を登録しようとしません。また、MBAM インストールの前後に SPN を手動で登録することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-188">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="d37eb-189">SPN を手動で登録する方法については、「手動での[spn の登録](https://go.microsoft.com/fwlink/?LinkId=286758)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-189">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

11. <span data-ttu-id="d37eb-190">[**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-190">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

12. <span data-ttu-id="d37eb-191">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-191">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

13. <span data-ttu-id="d37eb-192">選択された MBAM 機能の情報が入力されると、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d37eb-192">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="d37eb-193">インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-193">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="d37eb-194">[**インストール**] をクリックして、インストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-194">Click **Install** to start the installation.</span></span> <span data-ttu-id="d37eb-195">[**キャンセル**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-195">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="d37eb-196">選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-196">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

14. <span data-ttu-id="d37eb-197">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-197">Click **Finish** to exit the wizard.</span></span>

    **<span data-ttu-id="d37eb-198">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-198">Note</span></span>**  
    <span data-ttu-id="d37eb-199">アプリをインストールした後でセルフサービスポータルを構成するには、会社名やその他の会社固有の情報が含まれるセルフサービスポータルを作成します。手順については、「[セルフサービスポータルのブランドを設定する](how-to-brand-the-self-service-portal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-199">To configure the Self-Service Portal after you installed it, brand the Self-Service Portal with your company name and other company-specific information, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md) for instructions.</span></span>



15. <span data-ttu-id="d37eb-200">クライアントコンピューターが Microsoft コンテンツ配信ネットワーク (CDN) にアクセスできる場合、セルフサービスポータルで特定の JavaScript ファイルへの必要なアクセス権が付与されると、セルフサービスポータルのインストールが完了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-200">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, you are finished with the Self-Service Portal installation.</span></span> <span data-ttu-id="d37eb-201">クライアントコンピューターに Microsoft CDN へのアクセス許可がない場合は、次のセクションの手順を実行して、アクセシビリティの高いソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-201">If the client computers does not have access to the Microsoft CDN, complete the steps in the next section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

**<span data-ttu-id="d37eb-202">エンドユーザーが Microsoft コンテンツ配信ネットワークにアクセスできないときにセルフサービスポータルを構成するには</span><span class="sxs-lookup"><span data-stu-id="d37eb-202">To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network</span></span>**

1. <span data-ttu-id="d37eb-203">クライアントコンピューターが Microsoft コンテンツ配信ネットワーク (CDN) にアクセスできる場合、セルフサービスポータルで特定の JavaScript ファイルへの必要なアクセス権が付与されると、セルフサービスポータルのインストールが完了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-203">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, the Self-Service Portal installation is completed.</span></span> <span data-ttu-id="d37eb-204">クライアントコンピューターに Microsoft CDN へのアクセス許可がない場合は、このセクションの残りの手順を実行して、アクセシビリティの高いソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-204">If the client computers do not have access to the Microsoft CDN, complete the remaining steps in this section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

2. <span data-ttu-id="d37eb-205">Microsoft CDN から4つの JavaScript ファイルをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-205">Download the four JavaScript files from the Microsoft CDN:</span></span>

   -   <span data-ttu-id="d37eb-206">jQuery-1.7.2.min.js[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span><span class="sxs-lookup"><span data-stu-id="d37eb-206">jQuery-1.7.2.min.js - [https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span></span>

   -   <span data-ttu-id="d37eb-207">MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span><span class="sxs-lookup"><span data-stu-id="d37eb-207">MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span></span>

   -   <span data-ttu-id="d37eb-208">MicrosoftMvcAjax.js[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span><span class="sxs-lookup"><span data-stu-id="d37eb-208">MicrosoftMvcAjax.js - [https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span></span>

   -   <span data-ttu-id="d37eb-209">MicrosoftMvcValidation.js</span><span class="sxs-lookup"><span data-stu-id="d37eb-209">MicrosoftMvcValidation.js -</span></span> <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. <span data-ttu-id="d37eb-210">JavaScript ファイルをセルフサービスポータルの**Scripts**ディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-210">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="d37eb-211">このディレクトリは、 <em> &lt; mbam セルフサービスインストールディレクトリ &gt; \\ </em> セルフサービス Website\\Scripts. にあります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-211">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

4. <span data-ttu-id="d37eb-212">**インターネットインフォメーションサービス (IIS) マネージャー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-212">Open **Internet Information Services (IIS) Manager**.</span></span>

5. <span data-ttu-id="d37eb-213">**Sites** &gt; **Microsoft BitLocker の管理と監視**を展開し、[ **selfservice**] を強調表示します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-213">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="d37eb-214">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-214">Note</span></span>**  
   <span data-ttu-id="d37eb-215">*Selfservice*は、既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-215">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="d37eb-216">インストール時にこのディレクトリに別の名前を選択した場合は、次の手順の残りの「 *Selfservice* 」を、選択した名前で置き換えてください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-216">If you chose a different name for this directory during installation, remember to replace *SelfService* in the rest of these instructions with the name you chose.</span></span>



6. <span data-ttu-id="d37eb-217">中央のウィンドウで、[アプリケーションの**設定**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-217">In the middle pane, double-click **Application Settings**.</span></span>

7. <span data-ttu-id="d37eb-218">次の一覧の各項目について、 &lt; 仮想ディレクトリを/ &gt; Selfservice/(またはインストール時に選択した名前) に置き換えることによって、新しい場所を参照するようにアプリケーションの設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-218">For each item in the following list, edit the application settings to reference the new location by replacing &lt;virtual directory&gt; with /SelfService/ (or the name you chose during installation).</span></span> <span data-ttu-id="d37eb-219">たとえば、仮想ディレクトリのパスは、/selfservice/スクリプト/jquery-1.7.2.min.js に似ています。</span><span class="sxs-lookup"><span data-stu-id="d37eb-219">For example, the virtual directory path will be similar to /selfservice/scripts/jquery-1.7.2.min.js.</span></span>

   -   <span data-ttu-id="d37eb-220">jQueryPath:/ &lt; virtual directory/ &gt; スクリプト/jQuery-1.7.2.min.js</span><span class="sxs-lookup"><span data-stu-id="d37eb-220">jQueryPath: /&lt;virtual directory&gt;/Scripts/ jQuery-1.7.2.min.js</span></span>

   -   <span data-ttu-id="d37eb-221">MicrosoftAjaxPath:/ &lt; virtual directory/ &gt; スクリプト/MicrosoftAjax.js</span><span class="sxs-lookup"><span data-stu-id="d37eb-221">MicrosoftAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftAjax.js</span></span>

   -   <span data-ttu-id="d37eb-222">MicrosoftMvcAjaxPath:/ &lt; virtual directory/ &gt; スクリプト/MicrosoftMvcAjax.js</span><span class="sxs-lookup"><span data-stu-id="d37eb-222">MicrosoftMvcAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcAjax.js</span></span>

   -   <span data-ttu-id="d37eb-223">Microsoft Mvcvalidationpath:/ &lt; 仮想ディレクトリ/ &gt; スクリプト/MicrosoftMvcValidation.js</span><span class="sxs-lookup"><span data-stu-id="d37eb-223">MicrosoftMvcValidationPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcValidation.js</span></span>

**<span data-ttu-id="d37eb-224">管理と監視のサーバー機能をインストールするには</span><span class="sxs-lookup"><span data-stu-id="d37eb-224">To install the Administration and Monitoring Server feature</span></span>**

1. <span data-ttu-id="d37eb-225">MBAM は、Web サービスと管理サーバーおよび監視サーバー間の通信を暗号化できます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-225">MBAM can encrypt the communication between the Web Services and the Administration and Monitoring servers.</span></span> <span data-ttu-id="d37eb-226">通信を暗号化するためのオプションを選択した場合は、暗号化に使用する証明機関がプロビジョニングした証明書を選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-226">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2. <span data-ttu-id="d37eb-227">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-227">Click **Next** to continue.</span></span>

3. <span data-ttu-id="d37eb-228">コンプライアンスと監査データベースがインストールされている SQL Server のリモートインスタンス (例: \* &lt; ServerName &gt; \*) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-228">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4. <span data-ttu-id="d37eb-229">コンプライアンスおよび監査データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-229">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="d37eb-230">既定では、データベース名は MBAM コンプライアンスの状態です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-230">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="d37eb-231">ただし、コンプライアンスと監査データベースをインストールするときに、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-231">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5. <span data-ttu-id="d37eb-232">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-232">Click **Next** to continue.</span></span>

6. <span data-ttu-id="d37eb-233">回復データベースがインストールされている SQL Server のリモートインスタンス (例: \* &lt; ServerName &gt; \*) を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-233">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7. <span data-ttu-id="d37eb-234">回復データベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-234">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="d37eb-235">既定では、データベース名は**Mbam 回復とハードウェア**です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-235">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="d37eb-236">ただし、回復データベース機能をインストールするときに、名前を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-236">However, you can change the name when you install the Recovery Database feature.</span></span>

8. <span data-ttu-id="d37eb-237">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-237">Click **Next** to continue.</span></span>

9. <span data-ttu-id="d37eb-238">SQL Server Reporting Services (SRS) サイトの "ホーム" の URL を指定します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-238">Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site.</span></span> <span data-ttu-id="d37eb-239">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="d37eb-239">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

   <span data-ttu-id="d37eb-240">http:// <em> &lt; nameofmbamレポートサーバーの &gt; / </em> ReportServer</span><span class="sxs-lookup"><span data-stu-id="d37eb-240">http://<em>&lt;NameofMBAMReportsServer&gt;/</em>ReportServer</span></span>

   **<span data-ttu-id="d37eb-241">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-241">Note</span></span>**  
   <span data-ttu-id="d37eb-242">SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http://\* &lt; nameofmbamreportsserver/reportserver &gt; *_* &lt; srsinstancename &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="d37eb-242">If SQL Server Reporting Services was configured as a named instance, the URL resembles the following: http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*.</span></span>



10. <span data-ttu-id="d37eb-243">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-243">Click **Next** to continue.</span></span>

11. <span data-ttu-id="d37eb-244">[**ポート番号**]、[**ホスト名**] (省略可能)、Mbam 管理および監視サーバーの**インストールパス**を入力します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-244">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="d37eb-245">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-245">Note</span></span>**  
    <span data-ttu-id="d37eb-246">一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-246">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="d37eb-247">Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-247">If you are using Windows Firewall, the port will be opened automatically.</span></span>



12. <span data-ttu-id="d37eb-248">必要に応じてセルフサービスポータルのサービスプリンシパル名 (SPN) を登録するには、[**このコンピューターのサービスプリンシパル名 (spn) を Active Directory との間で登録する] (Windows 認証に必要)** を選びます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-248">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="d37eb-249">このチェックボックスをオンにすると、MBAM セットアップは既存の Spn を登録しようとしません。また、MBAM インストールの前後に SPN を手動で登録することができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-249">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="d37eb-250">SPN を手動で登録する方法については、「手動での[spn の登録](https://go.microsoft.com/fwlink/?LinkId=286758)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="d37eb-250">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

13. <span data-ttu-id="d37eb-251">[**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-251">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

14. <span data-ttu-id="d37eb-252">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-252">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

15. <span data-ttu-id="d37eb-253">選択された MBAM 機能の情報が入力されると、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="d37eb-253">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="d37eb-254">インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-254">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="d37eb-255">[**インストール**] をクリックしてインストールします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-255">Click **Install** to being the installation.</span></span> <span data-ttu-id="d37eb-256">[**キャンセル**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-256">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="d37eb-257">選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-257">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

16. <span data-ttu-id="d37eb-258">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-258">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="d37eb-259">インストール後の構成を実行するには</span><span class="sxs-lookup"><span data-stu-id="d37eb-259">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="d37eb-260">管理および監視サーバーで、ユーザーを次のローカルグループに追加して、MBAM 管理および監視 web サイトの機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-260">On the Administration and Monitoring Server, add users to the following local groups to give them access to the features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="d37eb-261">**Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam 管理と監視 web サイトでドライブの回復と TPM 機能の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-261">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="d37eb-262">ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="d37eb-262">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="d37eb-263">**Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam の管理と監視の web サイトで、ドライブの回復と TPM の管理機能への高度なアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="d37eb-263">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="d37eb-264">上級のヘルプデスクユーザーの場合、ドライブの回復には [キー ID] フィールドのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="d37eb-264">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="d37eb-265">[ **TPM の管理**] では、[**コンピュータードメイン**] フィールドと [**コンピューター名**] フィールドのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-265">In **Manage TPM**, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="d37eb-266">管理と監視のサーバーをホストしているサーバー、およびコンプライアンスと監査のデータベースをホストしているサーバー、およびコンプライアンスと監査のレポートをホストしているサーバーで、ユーザーを次のローカルグループに追加して、MBAM 管理および監視 web サイトでレポート機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-266">On the server that hosts Administration and Monitoring Server and the Compliance and Audit Database and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="d37eb-267">**Mbam レポートユーザー**: このローカルグループのメンバーは、Mbam 管理と監視 web サイトのレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-267">**MBAM Report Users**: Members of this local group can access the reports on the MBAM Administration and Monitoring website.</span></span>

    **<span data-ttu-id="d37eb-268">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-268">Note</span></span>**  
    <span data-ttu-id="d37eb-269">Mbam 管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスと監査レポートがインストールされているすべてのコンピューターで、 **Mbam レポートユーザー**のローカルグループの同一ユーザーまたはグループメンバーシップを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-269">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="d37eb-270">MBAM サーバー機能のインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="d37eb-270">Validating the MBAM Server Feature Installation</span></span>


<span data-ttu-id="d37eb-271">Microsoft BitLocker の管理および監視サーバー機能のインストールが完了したら、インストールによって MBAM の必要なすべての機能が正しく設定されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-271">When Microsoft BitLocker Administration and Monitoring Server feature installation is completed, we recommend that you validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="d37eb-272">次の手順を使用して、Microsoft BitLocker の管理と監視サービスが機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-272">Use the following procedure to confirm that the Microsoft BitLocker Administration and Monitoring service is functional.</span></span>

**<span data-ttu-id="d37eb-273">MBAM サーバーのインストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="d37eb-273">To validate an MBAM Server installation</span></span>**

1. <span data-ttu-id="d37eb-274">MBAM 機能が展開されている各サーバーで、[**コントロールパネル**] を開き、[**プログラム**]、[**プログラムと機能**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-274">On each server where an MBAM feature is deployed, open **Control Panel**, select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="d37eb-275">**Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-275">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="d37eb-276">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-276">Note</span></span>**  
   <span data-ttu-id="d37eb-277">MBAM インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d37eb-277">To validate the MBAM installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="d37eb-278">回復データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-278">On the server where the Recovery Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="d37eb-279">コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータスデータベース**がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-279">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="d37eb-280">コンプライアンスと監査レポートがインストールされているサーバーで、管理者の資格情報で web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-280">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="d37eb-281">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamserver/レポートにあり &gt; </em> ます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-281">The default Home location of a SQL Server Reporting Services site instance can be found is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="d37eb-282">実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定されたインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-282">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that were specified during setup.</span></span>

   <span data-ttu-id="d37eb-283">**Microsoft BitLocker の管理と監視**という名前のレポートフォルダーに**MaltaDataSource**というデータソースが含まれていることを確認します。これには、 **en-us**フォルダーに4つのレポートが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-283">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="d37eb-284">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-284">Note</span></span>**  
   <span data-ttu-id="d37eb-285">SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http:/\* &lt; nameofmbamreportsserver &gt; */レポート \ _* &lt; srsinstancename &gt; \*</span><span class="sxs-lookup"><span data-stu-id="d37eb-285">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="d37eb-286">管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-286">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="d37eb-287">[ **Web サーバー (iis)**] を選択し、[**インターネットインフォメーションサービス (iis) マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="d37eb-287">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span>

6. <span data-ttu-id="d37eb-288">[**接続**] で、[ \* &lt; computername &gt; \*] に移動し、[**サイト**] を選択して、[ **Microsoft BitLocker 管理と監視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-288">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="d37eb-289">**MbamMBAMComplianceStatusService service**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-289">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="d37eb-290">管理と監視機能とセルフサービスポータルがインストールされているサーバーで、管理者の資格情報を使用して web ブラウザーを開き、次の場所を参照して正常に読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-290">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully.</span></span>

   **<span data-ttu-id="d37eb-291">注</span><span class="sxs-lookup"><span data-stu-id="d37eb-291">Note</span></span>**  
   <span data-ttu-id="d37eb-292">".Svc" で終わる Url は、web サイトを表示しません。</span><span class="sxs-lookup"><span data-stu-id="d37eb-292">The URLs ending in “.svc” do not display a website.</span></span> <span data-ttu-id="d37eb-293">Success は、"このサービスのメタデータの公開が現在無効になっています" またはコードの情報によって示されます。</span><span class="sxs-lookup"><span data-stu-id="d37eb-293">Success is indicated by the message “Metadata publishing for this service is currently disabled” or by information resembling code.</span></span> <span data-ttu-id="d37eb-294">他のエラーメッセージが表示された場合、またはページが見つからない場合は、ページが正常に読み込まれません。</span><span class="sxs-lookup"><span data-stu-id="d37eb-294">If you see some other error message or if the page cannot be found, the page has not loaded successfully.</span></span>



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. <span data-ttu-id="d37eb-295">各 web ページが正常に読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d37eb-295">Verify that each webpage loads successfully.</span></span>

## <span data-ttu-id="d37eb-296">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d37eb-296">Related topics</span></span>


[<span data-ttu-id="d37eb-297">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="d37eb-297">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









