---
title: 単一サーバーに MBAM をインストールして構成する方法
description: 単一サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53e170f421bdce8dd6f771af3902af627a15a085
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824067"
---
# <span data-ttu-id="a3382-103">単一サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="a3382-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="a3382-104">このトピックの手順では、1台のサーバー上のスタンドアロントポロジに Microsoft BitLocker 管理と監視 (MBAM) をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3382-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology on a single server.</span></span> <span data-ttu-id="a3382-105">単一サーバー構成は、テスト環境でのみ使用します。</span><span class="sxs-lookup"><span data-stu-id="a3382-105">Use the single-server configuration only in a test environment.</span></span> <span data-ttu-id="a3382-106">運用環境では、2つ以上のサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="a3382-106">For production environments, use two or more servers.</span></span> <span data-ttu-id="a3382-107">Configuration Manager トポロジを使用して Microsoft BitLocker の管理と監視をインストールする場合は、「 [Configuration manager で MBAM を展開](deploying-mbam-with-configuration-manager-mbam2.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3382-107">If you are installing Microsoft BitLocker Administration and Monitoring by using the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="a3382-108">次の図は、単一サーバーアーキテクチャの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="a3382-108">The following diagram shows an example of a single-server architecture.</span></span> <span data-ttu-id="a3382-109">データベースと機能の詳細については、「 [MBAM 2.0 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-20-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3382-109">For a description of the databases and features, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

![mbam 2 single server deployment トポロジ](images/mbam2-1-server.gif)

<span data-ttu-id="a3382-111">各サーバー機能には、いくつかの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-111">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="a3382-112">前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)と[Mbam 2.0 でサポートさ](mbam-20-supported-configurations-mbam-2.md)れている構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3382-112">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="a3382-113">また、一部の機能には、インストールプロセス中に機能を正常に展開するために提供する必要がある情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="a3382-113">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="a3382-114">また、MBAM 展開を開始する前に、 [mbam 2.0 の環境の準備](preparing-your-environment-for-mbam-20-mbam-2.md)を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-114">You should also review [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md) before you start MBAM deployment.</span></span>

**<span data-ttu-id="a3382-115">注</span><span class="sxs-lookup"><span data-stu-id="a3382-115">Note</span></span>**  
<span data-ttu-id="a3382-116">セットアップログファイルを取得するには、Msiexec.exe パッケージと [ **/l** &lt; location] オプションを使用して &gt; mbam をインストールします。</span><span class="sxs-lookup"><span data-stu-id="a3382-116">To obtain the setup log files, you have use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="a3382-117">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-117">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="a3382-118">追加のセットアップログファイルは、MBAM をインストールしているユーザーのサーバー上の% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-118">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <span data-ttu-id="a3382-119">1台のサーバーに MBAM サーバー機能をインストールするには</span><span class="sxs-lookup"><span data-stu-id="a3382-119">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="a3382-120">次の手順では、一般的な MBAM 機能をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a3382-120">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="a3382-121">MBAM サーバー機能のインストールを開始するには</span><span class="sxs-lookup"><span data-stu-id="a3382-121">To start the MBAM Server features installation</span></span>**

1.  <span data-ttu-id="a3382-122">MBAM をインストールするサーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="a3382-122">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="a3382-123">[**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3382-123">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="a3382-124">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-124">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="a3382-125">[**トポロジの選択**] ページで、**スタンドアロン**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3382-125">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="a3382-126">[**インストールする機能の選択**] ページで、インストールする機能を選びます。</span><span class="sxs-lookup"><span data-stu-id="a3382-126">On the **Select features to install** page, select the features that you want to install.</span></span> <span data-ttu-id="a3382-127">既定では、すべての MBAM 機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="a3382-127">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="a3382-128">同じコンピューターにインストールされる機能は、同時にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-128">Features that are to be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="a3382-129">任意の場所にインストールする機能のチェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="a3382-129">Clear the check boxes for any features that you want to install elsewhere.</span></span> <span data-ttu-id="a3382-130">MBAM 機能は次の順序でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-130">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="a3382-131">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="a3382-131">Recovery Database</span></span>

    -   <span data-ttu-id="a3382-132">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="a3382-132">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="a3382-133">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="a3382-133">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="a3382-134">セルフサービスサーバー</span><span class="sxs-lookup"><span data-stu-id="a3382-134">Self-Service Server</span></span>

    -   <span data-ttu-id="a3382-135">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="a3382-135">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="a3382-136">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="a3382-136">MBAM Group Policy template</span></span>

    **<span data-ttu-id="a3382-137">注</span><span class="sxs-lookup"><span data-stu-id="a3382-137">Note</span></span>**  
    <span data-ttu-id="a3382-138">インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-138">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="a3382-139">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-139">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="a3382-140">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-140">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="a3382-141">すべての前提条件が現在満たされている場合は、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-141">If all prerequisites are met this time, the installation resumes.</span></span>



6.  <span data-ttu-id="a3382-142">[**ネットワーク通信セキュリティの構成**] ページで、管理および監視サーバーとクライアントの Web サービス間の通信を暗号化するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3382-142">On the **Configure network communication security** page, choose whether to encrypt the communication between the Web Services on the Administration and Monitoring Server and the clients.</span></span> <span data-ttu-id="a3382-143">通信を暗号化することにした場合は、暗号化に使用する証明機関がプロビジョニングした証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3382-143">If you decide to encrypt the communication, select the certification authority-provisioned certificate to use for encryption.</span></span> <span data-ttu-id="a3382-144">このページで選択できるようにするには、この手順を実行する前に証明書を作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-144">The certificate must be created prior to this step to enable you to select it on this page.</span></span>

    **<span data-ttu-id="a3382-145">注</span><span class="sxs-lookup"><span data-stu-id="a3382-145">Note</span></span>**  
    <span data-ttu-id="a3382-146">このページは、 **[インストールする機能の選択**] ページでセルフサービスポータルまたは管理/監視サーバー機能を選んだ場合にのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-146">This page appears only if you selected the Self-Service Portal or the Administration and Monitoring Server feature on the **Select features to install** page.</span></span>



7.  <span data-ttu-id="a3382-147">[**次へ**] をクリックし、次の手順に進んで Mbam サーバー機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="a3382-147">Click **Next**, and then continue to the next set of steps to configure the MBAM Server features.</span></span>

**<span data-ttu-id="a3382-148">MBAM サーバー機能を構成するには</span><span class="sxs-lookup"><span data-stu-id="a3382-148">To configure the MBAM Server features</span></span>**

1.  <span data-ttu-id="a3382-149">[**回復データベースの構成**] ページで、SQL Server インスタンス名と、回復データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3382-149">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="a3382-150">また、データベースファイルが配置される場所とログ情報が配置される場所の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-150">You must also specify both where the database files will be located and where the log information will be located.</span></span>

2.  <span data-ttu-id="a3382-151">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-151">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="a3382-152">[**コンプライアンスと監査データベースの構成**] ページで、SQL Server インスタンスの名前と、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="a3382-152">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="a3382-153">また、データベースファイルを配置する場所とログ情報を配置する場所を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-153">You must also specify where the database files will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="a3382-154">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-154">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="a3382-155">[**コンプライアンスと監査レポートを構成**する] ページで、コンプライアンスと監査レポートをインストールする SQL Server Reporting Services インスタンスを指定し、コンプライアンスと監査データベースにアクセスするためのドメインユーザーアカウントとパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3382-155">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password for accessing the Compliance and Audit database.</span></span> <span data-ttu-id="a3382-156">有効期限が切れないように、このアカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3382-156">Configure the password for this account to never expire.</span></span> <span data-ttu-id="a3382-157">ユーザーアカウントは、MBAM Reports Users グループで利用可能なすべてのデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-157">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="a3382-158">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-158">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="a3382-159">[**セルフサービスポータルの構成**] ページで、セルフサービスポータルのポート番号、ホスト名、仮想ディレクトリ名、インストールパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3382-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    **<span data-ttu-id="a3382-160">注</span><span class="sxs-lookup"><span data-stu-id="a3382-160">Note</span></span>**  
    <span data-ttu-id="a3382-161">一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-161">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="a3382-162">Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="a3382-162">If you are using Windows Firewall, the port will be opened automatically.</span></span>



8.  <span data-ttu-id="a3382-163">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-163">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="a3382-164">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3382-164">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="a3382-165">これにより、Windows で自動更新が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="a3382-165">This does not turn on Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="a3382-166">[**管理と監視サーバーの構成**] ページで、ヘルプデスクの web サイトのポート番号、ホスト名、仮想ディレクトリ名、インストールパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="a3382-166">On the **Configure the Administration and Monitoring Server** page, enter the port number, host name, virtual directory name, and installation path for the Help Desk website.</span></span>

    **<span data-ttu-id="a3382-167">注</span><span class="sxs-lookup"><span data-stu-id="a3382-167">Note</span></span>**  
    <span data-ttu-id="a3382-168">一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-168">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="a3382-169">Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。</span><span class="sxs-lookup"><span data-stu-id="a3382-169">If you are using Windows Firewall, the port will be opened automatically.</span></span>



11. <span data-ttu-id="a3382-170">[**インストールの概要**] ページで、インストールされる機能の一覧を確認し、[**インストール**] をクリックして、mbam 機能のインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="a3382-170">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="a3382-171">インストール設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを前の画面に移動するか、[**キャンセル**] をクリックしてセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="a3382-171">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="a3382-172">セットアップによって、MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="a3382-172">Setup installs the MBAM features and notifies you that the installation is complete.</span></span>

12. <span data-ttu-id="a3382-173">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="a3382-173">Click **Finish** to exit the wizard.</span></span> <span data-ttu-id="a3382-174">Microsoft BitLocker の管理と監視サーバーの機能をインストールしたら、次のセクションに進んで、Microsoft BitLocker の管理と監視の役割にユーザーを追加する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a3382-174">After the Microsoft BitLocker Administration and Monitoring Server features have been installed, continue to the next section and complete the steps have to add users to the Microsoft BitLocker Administration and Monitoring roles.</span></span> <span data-ttu-id="a3382-175">ロールの詳細については、「 [MBAM 2.0 管理者ロールの計画](planning-for-mbam-20-administrator-roles-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3382-175">For more information about roles, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

**<span data-ttu-id="a3382-176">インストール後の構成を実行するには</span><span class="sxs-lookup"><span data-stu-id="a3382-176">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="a3382-177">管理/監視サーバーで、MBAM ヘルプデスクの web サイト機能へのアクセス権を付与するには、次のローカルグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="a3382-177">On the Administration and Monitoring Server, add users to the following local groups to give them access to the MBAM Help Desk website features:</span></span>

    -   <span data-ttu-id="a3382-178">**Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam 管理と監視 web サイトでドライブの回復と TPM 機能の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a3382-178">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="a3382-179">ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="a3382-179">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="a3382-180">**Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam の管理と監視の web サイトで、ドライブの回復と TPM の管理機能への高度なアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="a3382-180">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="a3382-181">上級のヘルプデスクユーザーの場合、ドライブの回復には [**キー ID** ] フィールドのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="a3382-181">For Advanced Helpdesk Users, only the **Key ID** field is required in Drive Recovery.</span></span> <span data-ttu-id="a3382-182">[TPM の管理] では、[**コンピュータードメイン**] フィールドと [**コンピューター名**] フィールドのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-182">In Manage TPM, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="a3382-183">管理および監視サーバーで、ユーザーを次のローカルグループに追加して、MBAM 管理および監視 web サイトのレポート機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="a3382-183">On the Administration and Monitoring Server, add users to the following local group to enable them to access the Reports feature on the MBAM Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="a3382-184">**Mbam レポートユーザー**: このローカルグループのメンバーは、Mbam 管理および監視 web サイトのレポート機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a3382-184">**MBAM Report Users**: Members of this local group can access the Reports features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="a3382-185">会社名、通知テキスト、その他の会社固有の情報が含まれるセルフサービスポータルのブランドを設定します。</span><span class="sxs-lookup"><span data-stu-id="a3382-185">Brand the Self-Service Portal with your company name, notice text, and other company-specific information.</span></span> <span data-ttu-id="a3382-186">手順については、「[セルフサービスポータルのブランドを設定する方法](how-to-brand-the-self-service-portal.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a3382-186">For instructions, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md).</span></span>

    **<span data-ttu-id="a3382-187">注</span><span class="sxs-lookup"><span data-stu-id="a3382-187">Note</span></span>**  
    <span data-ttu-id="a3382-188">Mbam **Report Users**ローカルグループの同一ユーザーまたはグループメンバーシップは、Mbam 管理および監視サーバー機能、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートがインストールされているすべてのコンピューターで維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-188">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span> <span data-ttu-id="a3382-189">これを行うには、ドメインセキュリティグループを作成し、そのドメイングループを各ローカル MBAM Report Users グループに追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a3382-189">The recommended way to do this is to create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="a3382-190">このプロセスを使用する場合は、ドメイングループを通じてグループメンバーシップを管理します。</span><span class="sxs-lookup"><span data-stu-id="a3382-190">When you use this process, manage the group memberships by way of the domain group.</span></span>



## <span data-ttu-id="a3382-191">MBAM サーバー機能のインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="a3382-191">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="a3382-192">Microsoft BitLocker の管理と監視のインストールが完了したら、BitLocker の管理に必要なすべての必要な MBAM 機能がインストールによって正常に設定されたことを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-192">When the Microsoft BitLocker Administration and Monitoring installation is completed, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="a3382-193">次の手順を使用して、MBAM サービスが機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-193">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="a3382-194">MBAM サーバー機能のインストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="a3382-194">To validate the MBAM Server feature installation</span></span>**

1. <span data-ttu-id="a3382-195">MBAM 機能が展開されている各サーバーで、[**コントロールパネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="a3382-195">On each server where a MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="a3382-196">[**プログラム**] を選択し、[**プログラムと機能**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="a3382-196">Select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="a3382-197">**Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-197">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="a3382-198">注</span><span class="sxs-lookup"><span data-stu-id="a3382-198">Note</span></span>**  
   <span data-ttu-id="a3382-199">インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a3382-199">To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="a3382-200">回復データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-200">On the server where the Recovery Database is installed, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="a3382-201">コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータスデータベース**がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-201">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio, and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="a3382-202">コンプライアンスと監査レポートがインストールされているサーバーで、管理者の資格情報で web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。</span><span class="sxs-lookup"><span data-stu-id="a3382-202">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="a3382-203">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamレポートサーバー &gt; </em> /レポートにあります。</span><span class="sxs-lookup"><span data-stu-id="a3382-203">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="a3382-204">実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定されたインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="a3382-204">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that are specified during setup.</span></span>

   <span data-ttu-id="a3382-205">Microsoft BitLocker の管理と監視という名前のレポートフォルダーに**MaltaDataSource**というデータソースが含まれていることを確認します。これには、 **en-us**フォルダーに4つのレポートが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-205">Confirm that a Reports folder named Microsoft BitLocker Administration and Monitoring contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="a3382-206">注</span><span class="sxs-lookup"><span data-stu-id="a3382-206">Note</span></span>**  
   <span data-ttu-id="a3382-207">SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http://\* &lt; nameofmbamレポート Server &gt; */レポート \ _* &lt; srsinstancename &gt; \*</span><span class="sxs-lookup"><span data-stu-id="a3382-207">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following: http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="a3382-208">管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照します。</span><span class="sxs-lookup"><span data-stu-id="a3382-208">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="a3382-209">[ **Web サーバー (iis)**] を選択し、[**インターネットインフォメーションサービス (iis) マネージャー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a3382-209">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager.**</span></span>

6. <span data-ttu-id="a3382-210">[**接続]** で、[ \* &lt; computername &gt; \*] に移動し、[**サイト**] を選択します。次に、[ **Microsoft BitLocker 管理と監視**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="a3382-210">In **Connections,** browse to *&lt;computername&gt;*, select **Sites**, and then select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="a3382-211">**Mbam管理サービス**、 **mbamusersupportservice**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が一覧に表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-211">Verify that **MBAMAdministrationService**, **MBAMUserSupportService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="a3382-212">管理と監視機能とセルフサービスポータルがインストールされているサーバーで、管理者の資格情報を使用して web ブラウザーを開き、次の場所を参照して正常に読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a3382-212">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully:</span></span>

   -   <span data-ttu-id="a3382-213">*http:// &lt; hostname/ &gt; helpデスク/defaultdefault.aspx*とナビゲーションおよびレポートの各リンクを確認する</span><span class="sxs-lookup"><span data-stu-id="a3382-213">*http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="a3382-214">http:// &lt; hostname &gt; /selfservice&gt;/</span><span class="sxs-lookup"><span data-stu-id="a3382-214">http://&lt;hostname&gt;/SelfService&gt;/</span></span>*

   -   *<span data-ttu-id="a3382-215">http:// &lt; computername &gt; /mbam管理サービス/管理サービス</span><span class="sxs-lookup"><span data-stu-id="a3382-215">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="a3382-216">http:// &lt; hostname &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="a3382-216">http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>*

   -   *<span data-ttu-id="a3382-217">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="a3382-217">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="a3382-218">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="a3382-218">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="a3382-219">注</span><span class="sxs-lookup"><span data-stu-id="a3382-219">Note</span></span>**  
   <span data-ttu-id="a3382-220">サーバー機能は、ネットワーク暗号化されていない既定のポートにインストールされていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a3382-220">It is assumed that the server features were installed on the default port without network encryption.</span></span> <span data-ttu-id="a3382-221">異なるポートまたは仮想ディレクトリにサーバー機能をインストールした場合は、url を変更して適切なポート ( *http:// &lt; hostname &gt; : &lt; port &gt; /HelpDesk/default.asp*x または*http:// &lt; hostname &gt; : &lt; port &gt; / &lt; virtualdirectory &gt; /defaultdefault.aspx* ) を追加します。</span><span class="sxs-lookup"><span data-stu-id="a3382-221">If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.asp*x or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*</span></span>

   <span data-ttu-id="a3382-222">サーバー機能がネットワーク暗号化と共にインストールされていた場合は、http://を https://に変更します。</span><span class="sxs-lookup"><span data-stu-id="a3382-222">If the server features were installed with network encryption, change http:// to https://.</span></span>



## <span data-ttu-id="a3382-223">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a3382-223">Related topics</span></span>


[<span data-ttu-id="a3382-224">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="a3382-224">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









