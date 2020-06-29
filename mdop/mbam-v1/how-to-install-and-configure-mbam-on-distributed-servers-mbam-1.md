---
title: 分散サーバーに MBAM をインストールして構成する方法
description: 分散サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825657"
---
# <span data-ttu-id="059a6-103">分散サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="059a6-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="059a6-104">このトピックの手順では、分散サーバー上の Microsoft BitLocker 管理および監視 (MBAM) 機能の完全なインストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="059a6-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on distributed servers.</span></span>

<span data-ttu-id="059a6-105">各サーバー機能には、いくつかの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="059a6-106">前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートさ](mbam-10-supported-configurations.md)れている構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="059a6-106">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="059a6-107">さらに、一部の機能では、インストールプロセス中に機能を正常に展開するために特定の情報を提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-107">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span>

**<span data-ttu-id="059a6-108">注</span><span class="sxs-lookup"><span data-stu-id="059a6-108">Note</span></span>**  
<span data-ttu-id="059a6-109">セットアップログファイルを取得するには、 **msiexec.exe**パッケージと \*\*/l &lt; location &gt; \*\*オプションを使用して mbam をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-109">To obtain the setup log files, you have to install MBAM by using the **msiexec** package and the **/l &lt;location&gt;** option.</span></span> <span data-ttu-id="059a6-110">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="059a6-111">追加のセットアップログファイルは、MBAM インストールを実行しているユーザーの% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-111">Additional setup log files are created in the %temp% folder of the user that runs the MBAM installation.</span></span>



## <a href="" id="deploy-the-mbam-server-features-"></a><span data-ttu-id="059a6-112">MBAM Server 機能を導入する</span><span class="sxs-lookup"><span data-stu-id="059a6-112">Deploy the MBAM Server features</span></span>


<span data-ttu-id="059a6-113">次の手順では、一般的な MBAM 機能をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="059a6-113">The following steps describe how to install the general MBAM features.</span></span>

**<span data-ttu-id="059a6-114">注</span><span class="sxs-lookup"><span data-stu-id="059a6-114">Note</span></span>**  
<span data-ttu-id="059a6-115">32ビットサーバーでは32ビットセットアップ、64ビットサーバーでは64ビットセットアップを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="059a6-115">Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>



**<span data-ttu-id="059a6-116">MBAM サーバー機能を展開するには</span><span class="sxs-lookup"><span data-stu-id="059a6-116">To Deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="059a6-117">MBAM インストールウィザードを起動し、[ようこそ] ページで [**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-117">Start the MBAM installation wizard, and click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="059a6-118">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="059a6-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="059a6-119">既定では、すべての MBAM 機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="059a6-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="059a6-120">他の場所でインストールする機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="059a6-120">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="059a6-121">同じコンピューターにインストールする機能は、すべて同時にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-121">Features that you want to install on the same computer must be installed all at the same time.</span></span> <span data-ttu-id="059a6-122">MBAM 機能は、次の順序でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-122">MBAM features must be installed in the following order:</span></span>

    -   <span data-ttu-id="059a6-123">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="059a6-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="059a6-124">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="059a6-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="059a6-125">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="059a6-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="059a6-126">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="059a6-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="059a6-127">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="059a6-127">MBAM Group Policy Template</span></span>

    **<span data-ttu-id="059a6-128">注</span><span class="sxs-lookup"><span data-stu-id="059a6-128">Note</span></span>**  
    <span data-ttu-id="059a6-129">インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-129">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="059a6-130">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-130">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="059a6-131">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-131">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="059a6-132">すべての前提条件が満たされている場合は、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-132">If all prerequisites are met this time, the installation will resume.</span></span>



4.  <span data-ttu-id="059a6-133">MBAM セットアップウィザードには、選択した機能のインストールページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-133">The MBAM Setup wizard will display the installation pages for the selected features.</span></span> <span data-ttu-id="059a6-134">以下のセクションでは、各機能のインストール手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="059a6-134">The following sections describe the installation procedures for each feature.</span></span>

    **<span data-ttu-id="059a6-135">注</span><span class="sxs-lookup"><span data-stu-id="059a6-135">Note</span></span>**  
    <span data-ttu-id="059a6-136">通常、各機能は個別のサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="059a6-136">Typically, each feature is installed on a separate server.</span></span> <span data-ttu-id="059a6-137">1台のサーバーに複数の機能をインストールする場合は、次の手順の一部を変更または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="059a6-137">If you want to install multiple features on a single server, you may change or eliminate some of the following steps.</span></span>



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   <span data-ttu-id="059a6-138">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-138">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

6. <span data-ttu-id="059a6-139">選択された MBAM 機能の情報が完了したら、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="059a6-139">When the selected MBAM feature information is complete, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="059a6-140">インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。</span><span class="sxs-lookup"><span data-stu-id="059a6-140">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="059a6-141">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-141">Click **Install** to begin the installation.</span></span> <span data-ttu-id="059a6-142">[**キャンセル**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="059a6-142">Click **Cancel** to exit the Wizard.</span></span> <span data-ttu-id="059a6-143">選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="059a6-143">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

7. <span data-ttu-id="059a6-144">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="059a6-144">Click **Finish** to exit the wizard.</span></span>

8. <span data-ttu-id="059a6-145">MBAM サーバー機能をインストールした後、適切な MBAM ロールにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="059a6-145">Add users to appropriate MBAM roles, after the MBAM server features are installed..</span></span> <span data-ttu-id="059a6-146">詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="059a6-146">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="059a6-147">インストール後の構成</span><span class="sxs-lookup"><span data-stu-id="059a6-147">Post-installation configuration</span></span>**

1.  <span data-ttu-id="059a6-148">MBAM セットアップが終了したら、ユーザーが MBAM 管理 web サイトの機能にアクセスできるようにするには、ユーザーロールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-148">After MBAM Setup is finished, you must add user Roles before users can access to features in the MBAM administration website.</span></span> <span data-ttu-id="059a6-149">管理および監視サーバーで、次のローカルグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="059a6-149">On the Administration and Monitoring Server, add users to the following local groups.</span></span>

    -   <span data-ttu-id="059a6-150">**Mbam ハードウェアユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのハードウェア機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="059a6-150">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="059a6-151">**Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのドライブの回復と、トラステッドプラットフォームモジュール (TPM) 機能の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="059a6-151">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage Trusted Platform Modules (TPM) features in the MBAM administration website.</span></span> <span data-ttu-id="059a6-152">ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="059a6-152">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="059a6-153">**Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトでドライブの回復と TPM 機能の管理に高度なアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="059a6-153">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="059a6-154">上級のヘルプデスクユーザーの場合、ドライブの回復には [キー ID] フィールドのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="059a6-154">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="059a6-155">[TPM の管理] では、[コンピュータードメイン] フィールドと [コンピューター名] フィールドのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-155">In Manage TPM, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="059a6-156">管理および監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスと監査レポートをホストしているサーバー上で、次のローカルグループにユーザーを追加して、MBAM 管理 web サイトでレポート機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="059a6-156">On the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="059a6-157">**Mbam レポートユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのレポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="059a6-157">**MBAM Report Users**: Members of this local group can access the Reports in the MBAM administration website.</span></span>

    **<span data-ttu-id="059a6-158">注</span><span class="sxs-lookup"><span data-stu-id="059a6-158">Note</span></span>**  
    <span data-ttu-id="059a6-159">Mbam 管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスと監査レポートがインストールされているすべてのコンピューターで、 **Mbam レポートユーザー**のローカルグループの同一ユーザーまたはグループメンバーシップを維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-159">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="059a6-160">MBAM サーバー機能のインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="059a6-160">Validate the MBAM Server feature installation</span></span>


<span data-ttu-id="059a6-161">MBAM サーバー機能のインストールが完了したら、インストールによって MBAM の必要な機能が正しく設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-161">When the MBAM Server feature installation is complete, you should validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="059a6-162">次の手順を使用して、MBAM サービスが機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-162">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="059a6-163">MBAM インストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="059a6-163">To validate an MBAM installation</span></span>**

1. <span data-ttu-id="059a6-164">MBAM 機能が展開されている各サーバーで、[**コントロールパネル**] を開き、[**プログラム**]、[**プログラムと機能**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-164">On each server, where an MBAM feature is deployed, open **Control Panel**, click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="059a6-165">**Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-165">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="059a6-166">注</span><span class="sxs-lookup"><span data-stu-id="059a6-166">Note</span></span>**  
   <span data-ttu-id="059a6-167">MBAM インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="059a6-167">To validate the MBAM installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="059a6-168">回復とハードウェアデータベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-168">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="059a6-169">コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータス**データベースがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-169">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status** database is installed.</span></span>

4. <span data-ttu-id="059a6-170">コンプライアンスと監査レポートがインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。</span><span class="sxs-lookup"><span data-stu-id="059a6-170">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="059a6-171">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamreportsserver/レポートで参照でき &gt; </em> ます。</span><span class="sxs-lookup"><span data-stu-id="059a6-171">The default Home location of a SQL Server Reporting Services site instance can be found at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="059a6-172">実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定したインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="059a6-172">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="059a6-173">「**マルタ法令遵守レポート**」という名前のフォルダーが表示されていること、および5つのレポートと1つのデータソースが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-173">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="059a6-174">注</span><span class="sxs-lookup"><span data-stu-id="059a6-174">Note</span></span>**  
   <span data-ttu-id="059a6-175">SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http:/\* &lt; nameofmbamreportsserver &gt; */レポート \ _* &lt; srsinstancename &gt; \*</span><span class="sxs-lookup"><span data-stu-id="059a6-175">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



5. <span data-ttu-id="059a6-176">管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照し、[ **Web サーバー (iis)**] を選択して、[**インターネットインフォメーションサービス (iis) マネージャー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-176">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="059a6-177">[**接続**の場所\* &lt; &gt; ] で、[\***サイト**] をクリックし、[ **Microsoft BitLocker の管理と監視**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="059a6-177">In **Connections** browse to *&lt;computername&gt;*, click **Sites**, and click **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="059a6-178">**MbamMBAMComplianceStatusService service**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-178">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

6. <span data-ttu-id="059a6-179">管理と監視機能がインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、MBAM web サイトの次の場所を参照して、正しく読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="059a6-179">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges and browse to the following locations in the MBAM web site, to verify that they load successfully:</span></span>

   -   <span data-ttu-id="059a6-180">*http:// &lt; computername/ &gt; defaultdefault.aspx*とナビゲーションおよびレポートの各リンクを確認する</span><span class="sxs-lookup"><span data-stu-id="059a6-180">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="059a6-181">http:// &lt; computername &gt; /mbam管理サービス/管理サービス</span><span class="sxs-lookup"><span data-stu-id="059a6-181">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="059a6-182">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="059a6-182">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="059a6-183">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="059a6-183">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="059a6-184">注</span><span class="sxs-lookup"><span data-stu-id="059a6-184">Note</span></span>**  
   <span data-ttu-id="059a6-185">通常、サービスは、ネットワーク暗号化されていない既定のポート80にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="059a6-185">Typically, services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="059a6-186">サービスが別のポートにインストールされている場合は、Url を変更して適切なポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="059a6-186">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="059a6-187">たとえば、http://\* &lt; computername &gt; : &lt; &gt; port\*/default/dns または http:// <em> &lt; hostheadername &gt; / </em> default.aspx</span><span class="sxs-lookup"><span data-stu-id="059a6-187">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx</span></span>

   <span data-ttu-id="059a6-188">サービスがネットワーク暗号化と共にインストールされていた場合は、http://を https://に変更します。</span><span class="sxs-lookup"><span data-stu-id="059a6-188">If the services were installed with network encryption, change http:// to https://.</span></span>



~~~
Verify that each web page loads successfully.
~~~

## <span data-ttu-id="059a6-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="059a6-189">Related topics</span></span>


[<span data-ttu-id="059a6-190">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="059a6-190">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)









