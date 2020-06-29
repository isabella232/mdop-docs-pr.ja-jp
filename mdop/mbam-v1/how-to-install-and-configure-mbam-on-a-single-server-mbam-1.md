---
title: 単一サーバーに MBAM をインストールして構成する方法
description: 単一サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 55841c63-bad9-44e7-b7fd-ea7037febbd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 225f66493ceafce5461df3fcc6f701e9a2922a5f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824097"
---
# <span data-ttu-id="9abb9-103">単一サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="9abb9-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="9abb9-104">このトピックの手順では、1つのサーバー上の Microsoft BitLocker 管理および監視 (MBAM) 機能の完全インストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on a single server.</span></span>

<span data-ttu-id="9abb9-105">各サーバー機能には、いくつかの前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="9abb9-106">前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートさ](mbam-10-supported-configurations.md)れている構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9abb9-106">To verify that you have met the prerequisites and the hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="9abb9-107">また、一部の機能には、インストールプロセス中に機能を正常に展開するために提供する必要がある情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="9abb9-107">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="9abb9-108">また、MBAM 展開を始める前に、 [mbam 1.0 の環境の準備](preparing-your-environment-for-mbam-10.md)を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-108">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM deployment.</span></span>

<span data-ttu-id="9abb9-109">**注** セットアップログファイルを取得するには、 **msiexec.exe**パッケージと **/l** location オプションを使用して mbam をインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-109">**Note** To obtain the setup log files, you must install MBAM by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="9abb9-110">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="9abb9-111">追加のセットアップログファイルは、MBAM をインストールしているユーザーの% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-111">Additional setup log files are created in the %temp% folder of the user who is installing MBAM.</span></span>

 

## <span data-ttu-id="9abb9-112">1台のサーバーに MBAM サーバー機能をインストールするには</span><span class="sxs-lookup"><span data-stu-id="9abb9-112">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="9abb9-113">次の手順では、一般的な MBAM 機能をインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-113">The following steps describe how to install general MBAM features.</span></span>

<span data-ttu-id="9abb9-114">**注** 32ビットサーバーでは32ビットセットアップ、64ビットサーバーでは64ビットセットアップを使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="9abb9-114">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="9abb9-115">MBAM Server 機能のインストールを開始するには</span><span class="sxs-lookup"><span data-stu-id="9abb9-115">To start MBAM Server features installation</span></span>**

1.  <span data-ttu-id="9abb9-116">MBAM インストールウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-116">Start the MBAM installation wizard.</span></span> <span data-ttu-id="9abb9-117">[ようこそ] ページで [**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-117">Click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="9abb9-118">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="9abb9-119">既定では、すべての MBAM 機能がインストール対象として選択されています。</span><span class="sxs-lookup"><span data-stu-id="9abb9-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="9abb9-120">同じコンピューターにインストールされる機能は、同時にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-120">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="9abb9-121">他の場所でインストールする機能をオフにします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-121">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="9abb9-122">MBAM 機能は、次の順序でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-122">You must install the MBAM features in the following order:</span></span>

    -   <span data-ttu-id="9abb9-123">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="9abb9-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="9abb9-124">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="9abb9-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="9abb9-125">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="9abb9-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="9abb9-126">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="9abb9-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="9abb9-127">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="9abb9-127">MBAM Group Policy Template</span></span>

    <span data-ttu-id="9abb9-128">**注** インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-128">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="9abb9-129">すべての前提条件が満たされている場合は、インストールが続行されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-129">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="9abb9-130">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-130">If a missing prerequisite is detected, you must resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="9abb9-131">すべての前提条件が満たされると、インストールが再開されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-131">After all prerequisites are met, the installation resumes.</span></span>

     

4.  <span data-ttu-id="9abb9-132">ネットワーク通信のセキュリティを構成するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-132">You are prompted to configure the network communication security.</span></span> <span data-ttu-id="9abb9-133">MBAM は、回復とハードウェアデータベース、管理/監視サーバー、クライアント間の通信を暗号化することができます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-133">MBAM can encrypt the communication between the Recovery and Hardware Database, the Administration and Monitoring Server, and the clients.</span></span> <span data-ttu-id="9abb9-134">通信を暗号化することにした場合、暗号化に使用される証明書がプロビジョニングされた証明書を選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-134">If you decide to encrypt the communication, you are asked to select the authority-provisioned certificate that will be used for encryption.</span></span>

5.  <span data-ttu-id="9abb9-135">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-135">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="9abb9-136">MBAM セットアップウィザードには、選択した機能のインストールページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-136">The MBAM Setup wizard will display the installation pages for the selected features.</span></span>

**<span data-ttu-id="9abb9-137">MBAM サーバー機能を展開するには</span><span class="sxs-lookup"><span data-stu-id="9abb9-137">To deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="9abb9-138">[**回復とハードウェアデータベースの構成**] ウィンドウで、SQL Server のインスタンスと、回復とハードウェアのデータを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-138">In the **Configure the Recovery and Hardware database** window, specify the instance of SQL Server and the name of the database that will store the recovery and hardware data.</span></span> <span data-ttu-id="9abb9-139">また、データベースファイルの場所とログ情報の場所の両方を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-139">You must also specify both the database files location and the log information location.</span></span>

2.  <span data-ttu-id="9abb9-140">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-140">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="9abb9-141">[**コンプライアンスと監査データベースの構成**] ウィンドウで、SQL Server のインスタンスと、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-141">In the **Configure the Compliance and Audit database** window, specify the instance of the SQL Server and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="9abb9-142">次に、データベースファイルの場所とログ情報の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-142">Then, specify the database files location and the log information location.</span></span>

4.  <span data-ttu-id="9abb9-143">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-143">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="9abb9-144">[**コンプライアンスおよび監査レポート**] ウィンドウで、使用するレポートサービスインスタンスを指定し、データベースにアクセスするためのドメインユーザーアカウントを提供します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-144">In the **Compliance and Audit Reports** window, specify the report service instance that will be used and provide a domain user account for accessing the database.</span></span> <span data-ttu-id="9abb9-145">これは、この用途専用にプロビジョニングされたユーザーアカウントである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-145">This should be a user account that is provisioned specifically for this use.</span></span> <span data-ttu-id="9abb9-146">ユーザーアカウントは、MBAM Reports Users グループで利用可能なすべてのデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-146">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="9abb9-147">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-147">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="9abb9-148">[**管理と監視サーバーの構成**] ウィンドウで、[**ポートバインディング**]、[ **Host Name** (オプション)]、[mbam 管理および監視サーバー] の**インストールパス**を入力します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-148">In the **Configure the Administration and Monitoring Server** window, enter the **Port Binding**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server.</span></span>

    <span data-ttu-id="9abb9-149">**警告** 指定するポート番号は、一意のホストヘッダー名が指定されていない限り、管理/監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-149">**Warning** The port number that you specify must be an unused port number on the Administration and Monitoring server, unless a unique host header name is specified.</span></span>

     

8.  <span data-ttu-id="9abb9-150">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-150">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="9abb9-151">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-151">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="9abb9-152">[Microsoft Update] オプションでは、Windows の自動更新が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="9abb9-152">The Microsoft Updates option does not turn on the Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="9abb9-153">セットアップウィザードで必要な機能情報が収集されると、MBAM インストールを開始する準備ができました。</span><span class="sxs-lookup"><span data-stu-id="9abb9-153">When the Setup wizard has collected the necessary feature information, the MBAM installation is ready to start.</span></span> <span data-ttu-id="9abb9-154">インストール設定を確認または変更する場合は、[**戻る**] をクリックしてウィザードを前の画面に移動します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-154">Click **Back** to move back through the wizard if you want to review or change your installation settings.</span></span> <span data-ttu-id="9abb9-155">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-155">Click **Install** to begin the installation.</span></span> <span data-ttu-id="9abb9-156">[**キャンセル**] をクリックしてセットアップを終了します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-156">Click **Cancel** to exit Setup.</span></span> <span data-ttu-id="9abb9-157">セットアップによって、MBAM 機能がインストールされ、インストールが完了したことが通知されます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-157">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

11. <span data-ttu-id="9abb9-158">[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-158">Click **Finish** to exit the wizard.</span></span>

12. <span data-ttu-id="9abb9-159">MBAM server 機能をインストールしたら、MBAM ロールにユーザーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-159">After you install MBAM server features, you must add users to the MBAM roles.</span></span> <span data-ttu-id="9abb9-160">詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9abb9-160">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="9abb9-161">インストール後の構成を実行するには</span><span class="sxs-lookup"><span data-stu-id="9abb9-161">To perform post installation configuration</span></span>**

1.  <span data-ttu-id="9abb9-162">セットアップが完了したら、MBAM 管理 web サイトの機能にユーザーがアクセスできるようにユーザーロールを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-162">After Setup is finished, you must add user roles so that you can give users access to features in the MBAM administration website.</span></span> <span data-ttu-id="9abb9-163">管理と監視サーバーで、次のローカルグループにユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-163">On the Administration and Monitoring Server, add users to the following local groups:</span></span>

    -   <span data-ttu-id="9abb9-164">**Mbam ハードウェアユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのハードウェア機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-164">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="9abb9-165">**Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトでドライブの回復と TPM 機能の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-165">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="9abb9-166">ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。</span><span class="sxs-lookup"><span data-stu-id="9abb9-166">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="9abb9-167">**Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトでドライブの回復と TPM 機能の管理に高度なアクセス権を持っています。</span><span class="sxs-lookup"><span data-stu-id="9abb9-167">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="9abb9-168">上級のヘルプデスクユーザーの場合、ドライブの回復には [キー ID] フィールドのみが必要です。</span><span class="sxs-lookup"><span data-stu-id="9abb9-168">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="9abb9-169">TPM ユーザーを管理するには、[コンピュータードメイン] フィールドと [コンピューター名] フィールドのみを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-169">For Manage TPM users, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="9abb9-170">管理および監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスと監査レポートをホストしているコンピューターで、次のローカルグループにユーザーを追加して、MBAM 管理 web サイトのレポート機能にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-170">On the Administration and Monitoring Server, Compliance and Audit Database, and on the computer that hosts the Compliance and Audit Reports, add users to the following local group to enable them to access the Reports feature in the MBAM administration website:</span></span>

    -   <span data-ttu-id="9abb9-171">**Mbam レポートユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのレポート機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-171">**MBAM Report Users**: Members of this local group can access the Reports features in the MBAM administration website.</span></span>

    <span data-ttu-id="9abb9-172">**注** **Mbam Report Users**ローカルグループの同じユーザーメンバーシップまたはグループメンバーシップは、管理および監視サーバー機能、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートがインストールされているすべてのコンピューターで維持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-172">**Note** Identical user membership or group membership of the **MBAM Report Users** local group must be maintained on all computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

    <span data-ttu-id="9abb9-173">すべてのコンピューターで同一のメンバーシップを維持するには、ドメインセキュリティグループを作成し、そのドメイングループを各ローカル MBAM レポートユーザーグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-173">To maintain identical memberships on all computers, you should create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="9abb9-174">この操作を行うときに、ドメイングループを使用してグループメンバーシップを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-174">When you do this, you can manage the group memberships by using the domain group.</span></span>

     

## <span data-ttu-id="9abb9-175">MBAM サーバー機能のインストールを検証する</span><span class="sxs-lookup"><span data-stu-id="9abb9-175">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="9abb9-176">MBAM インストールが完了したら、インストールによって BitLocker の管理に必要なすべての必要な MBAM 機能が正常に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-176">When the MBAM installation is complete, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="9abb9-177">MBAM サービスが機能していることを確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-177">Use the following procedure to confirm that the MBAM service is functional:</span></span>

**<span data-ttu-id="9abb9-178">MBAM サーバー機能のインストールを検証するには</span><span class="sxs-lookup"><span data-stu-id="9abb9-178">To validate MBAM Server feature installation</span></span>**

1. <span data-ttu-id="9abb9-179">MBAM 機能が展開されている各サーバーで、[**コントロールパネル]** を開きます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-179">On each server where an MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="9abb9-180">[**プログラム**]、[**プログラムと機能**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-180">Click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="9abb9-181">**Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-181">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="9abb9-182">注</span><span class="sxs-lookup"><span data-stu-id="9abb9-182">Note</span></span>**  
   <span data-ttu-id="9abb9-183">インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-183">To validate the installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>

     

2. <span data-ttu-id="9abb9-184">回復とハードウェアデータベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-184">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="9abb9-185">コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスと監査データベース**がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-185">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance and Audit Database** is installed.</span></span>

4. <span data-ttu-id="9abb9-186">コンプライアンスと監査レポートがインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-186">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="9abb9-187">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamレポートサーバー &gt; </em> /レポートにあります。</span><span class="sxs-lookup"><span data-stu-id="9abb9-187">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="9abb9-188">実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定したインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-188">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="9abb9-189">「**マルタ法令遵守レポート**」という名前のフォルダーが表示されていること、および5つのレポートと1つのデータソースが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-189">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="9abb9-190">注</span><span class="sxs-lookup"><span data-stu-id="9abb9-190">Note</span></span>**  
   <span data-ttu-id="9abb9-191">SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http:/\* &lt; nameofmbamreportsserver &gt; */レポート \ _* &lt; srsinstancename &gt; \*</span><span class="sxs-lookup"><span data-stu-id="9abb9-191">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>

     

5. <span data-ttu-id="9abb9-192">管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照し、[ **Web サーバー (iis)**] を選択して、[**インターネットインフォメーションサービス (iis) マネージャー** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9abb9-192">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and click **Internet Information Services (IIS) Manager**</span></span>

6. <span data-ttu-id="9abb9-193">[**接続**] で、[ \* &lt; computername &gt; \*] に移動し、[**サイト**] を選択して、[ **Microsoft BitLocker 管理と監視**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-193">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="9abb9-194">**MbamMBAMComplianceStatusService service**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-194">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="9abb9-195">管理と監視機能がインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、MBAM web サイトの次の場所を参照して、正常に読み込まれることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-195">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges, and then browse to the following locations in the MBAM website to verify that they load successfully:</span></span>

   -   <span data-ttu-id="9abb9-196">*http:// &lt; computername/ &gt; defaultdefault.aspx*とナビゲーションおよびレポートの各リンクを確認する</span><span class="sxs-lookup"><span data-stu-id="9abb9-196">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="9abb9-197">http:// &lt; computername &gt; /mbam管理サービス/管理サービス</span><span class="sxs-lookup"><span data-stu-id="9abb9-197">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="9abb9-198">http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="9abb9-198">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="9abb9-199">http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="9abb9-199">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="9abb9-200">注</span><span class="sxs-lookup"><span data-stu-id="9abb9-200">Note</span></span>**  
   <span data-ttu-id="9abb9-201">通常、サービスは、ネットワーク暗号化されていない既定のポート80にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9abb9-201">Typically, the services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="9abb9-202">サービスが別のポートにインストールされている場合は、Url を変更して適切なポートを追加します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-202">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="9abb9-203">たとえば、http://\* &lt; computername &gt; : &lt; port &gt; \*/default¥ .aspx または http:// <em> &lt; hostheadername &gt; / </em> default.aspx。</span><span class="sxs-lookup"><span data-stu-id="9abb9-203">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx.</span></span>

   <span data-ttu-id="9abb9-204">サービスがネットワーク暗号化と共にインストールされている場合は、http://を https://に変更します。</span><span class="sxs-lookup"><span data-stu-id="9abb9-204">If the services are installed with network encryption, change http:// to https://.</span></span>

     

## <span data-ttu-id="9abb9-205">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9abb9-205">Related topics</span></span>


[<span data-ttu-id="9abb9-206">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="9abb9-206">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





