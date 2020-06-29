---
title: 旧バージョンの MBAM からのアップグレード
description: 旧バージョンの MBAM からのアップグレード
author: dansimp
ms.assetid: 73b425cf-9cd9-4ebc-a35e-1b3bf18596ce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af45d193a5e8001288e70389ff220cb5d8269918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823807"
---
# <span data-ttu-id="c3acc-103">旧バージョンの MBAM からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="c3acc-103">Upgrading from Previous Versions of MBAM</span></span>


<span data-ttu-id="c3acc-104">Microsoft BitLocker の管理と監視 (MBAM) を MBAM 2.0 にアップグレードするには、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-104">You can upgrade Microsoft BitLocker Administration and Monitoring (MBAM) to MBAM2.0, with the Stand-alone topology or Configuration Manager topology, by doing the following:</span></span>

-   <span data-ttu-id="c3acc-105">**インプレースサーバーの置き換え**– Mbam サーバーをアップグレードするには、インストーラまたはコントロールパネルのいずれかを使用して mbam を手動でアンインストールしてから、mbam 2.0 インフラストラクチャをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-105">**Manual in-place server replacement** – To upgrade the MBAM Server, manually uninstall MBAM by using either the installer or Control Panel, and then install the MBAM2.0 infrastructure.</span></span> <span data-ttu-id="c3acc-106">データベースを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-106">You do not have to remove the databases.</span></span> <span data-ttu-id="c3acc-107">MBAM 1.0 サーバーをアンインストールすると、MBAM データベースはそのまま残ります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-107">Uninstalling the MBAM 1.0 Server leaves the MBAM databases intact.</span></span> <span data-ttu-id="c3acc-108">MBAM 1.0 で使用されていたものと同じデータベースを指定した場合、MBAM 2.0 のインストールでは、データベース内の MBAM 1.0 データは保持され、MBAM 2.0 で動作するようにデータベースが変換されます。</span><span class="sxs-lookup"><span data-stu-id="c3acc-108">If you specify the same databases that MBAM 1.0 was using, the MBAM2.0 installation retains MBAM 1.0 data in the databases and converts the databases to work with MBAM2.0.</span></span>

-   <span data-ttu-id="c3acc-109">**分散クライアントアップグレード**-スタンドアロンの mbam トポロジを使用している場合は、mbam 2.0 サーバーインフラストラクチャをインストールした後に、Mbam クライアントを段階的にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="c3acc-109">**Distributed Client Upgrade** - If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="c3acc-110">MBAM 2.0 サーバーによって、既存のクライアントのバージョンが検出され、2.0 クライアントにアップグレードするために必要な手順が実行されます。</span><span class="sxs-lookup"><span data-stu-id="c3acc-110">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

    <span data-ttu-id="c3acc-111">Mbam 2.0 サーバーインフラストラクチャをアップグレードした後、MBAM 1.0 クライアントは、escrowing の回復データを正常に2.0 報告し続けますが、コンプライアンスは MBAM 1.0 のポリシーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="c3acc-111">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="c3acc-112">クライアントコンピューターで MBAM 2.0 ポリシーに準拠したコンプライアンスを正確に報告するには、クライアントを MBAM 2.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-112">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="c3acc-113">クライアントは、以前のクライアントをアンインストールせずに MBAM 2.0 クライアントにアップグレードできます。クライアントは、MBAM 2.0 ポリシーの適用と報告を開始します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-113">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

    <span data-ttu-id="c3acc-114">MBAM を Configuration Manager で使用している場合は、MBAM 1.0 クライアントを MBAM 2.0 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-114">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

## <span data-ttu-id="c3acc-115">2 Server アーキテクチャから MBAM をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="c3acc-115">Upgrading MBAM from a Two-Server Architecture</span></span>


<span data-ttu-id="c3acc-116">次の手順を使用して、以前のバージョンの MBAM からアップグレードします。これは、1つのサーバーが Microsoft SQL Server コンポーネントをホストしていて、もう一方のサーバーが web サイトとサービスをホストしている場合です。</span><span class="sxs-lookup"><span data-stu-id="c3acc-116">Use the following instructions to upgrade from a previous version of MBAM when you are using a two-server architecture, where one server is hosting the Microsoft SQL Server components, and the other server is hosting the websites and services.</span></span>

**<span data-ttu-id="c3acc-117">2 server アーキテクチャから MBAM をアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="c3acc-117">To upgrade MBAM from a two-server architecture</span></span>**

1.  <span data-ttu-id="c3acc-118">SQL Server 機能があるサーバーで、[コントロールパネル] の [**プログラムと機能**] を選択し、[ **Microsoft BitLocker の管理と監視**] をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-118">On the server with the SQL Server features, in Control Panel, select **Programs and Features**, and then uninstall **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="c3acc-119">回復データベースとコンプライアンスおよび監査データベースは変更されません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-119">The Recovery Database and Compliance and Audit database remain unchanged.</span></span>

2.  <span data-ttu-id="c3acc-120">バージョン MBAM 2.0 の**MBAMSetup.exe**を実行します。必要に応じて、**カスタマーエクスペリエンス向上プログラム**を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-120">Run **MBAMSetup.exe** for version MBAM 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="c3acc-121">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-121">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="c3acc-122">[**トポロジの選択**] ページで、**スタンドアロン**または**System Center Configuration Manager 統合**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-122">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="c3acc-123">[**インストールする機能の選択**] ページで、[**セルフサービスサーバー** ] および [**管理と監視**] のサーバー機能をオフにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-123">On the **Select features to install** page, clear the **Self-Service Server** and **Administration and Monitoring Server** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="c3acc-124">前提条件チェックが終了するまで待ち、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-124">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="c3acc-125">見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-125">If a missing prerequisite is detected, resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="c3acc-126">[ **MBAM データベースへのアクセスに使用するアカウントを指定**してください] ページで、サイトとサービスをホストするサーバーのコンピューター名を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-126">On the **Provide account used to access the MBAM databases** page, provide the computer name for the server that will host the sites and services, and then click **Next**.</span></span>

8.  <span data-ttu-id="c3acc-127">[**回復データベースの構成**] ページで、SQL Server インスタンス名と、回復データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-127">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="c3acc-128">また、データベースファイルとログ情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-128">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="c3acc-129">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-129">Click **Next** to continue.</span></span>

10. <span data-ttu-id="c3acc-130">[**コンプライアンスと監査データベースの構成**] ページで、SQL Server インスタンスの名前と、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-130">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span>

11. <span data-ttu-id="c3acc-131">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-131">Click **Next** to continue.</span></span>

12. <span data-ttu-id="c3acc-132">[**コンプライアンスおよび監査レポートの構成**] ページで、コンプライアンスと監査レポートをインストールする SQL Server Reporting Services インスタンスを指定し、ドメインユーザーアカウントとパスワードを入力して、コンプライアンスと監査データベースにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-132">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password to access the Compliance and Audit database.</span></span> <span data-ttu-id="c3acc-133">有効期限が切れないように、このアカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-133">Configure the password for this account to never expire.</span></span> <span data-ttu-id="c3acc-134">ユーザーアカウントは、MBAM Reports Users グループで利用可能なすべてのデータにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c3acc-134">The user account can access all data available to the MBAM Reports Users group.</span></span>

13. <span data-ttu-id="c3acc-135">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-135">Click **Next** to continue.</span></span>

14. <span data-ttu-id="c3acc-136">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-136">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="c3acc-137">これにより、Windows で自動更新が有効になりません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-137">This does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="c3acc-138">この製品または別の製品の Microsoft Update を以前に使用することを選択した場合、Microsoft Update ページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-138">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

15. <span data-ttu-id="c3acc-139">[**インストールの概要**] ページで、インストールされる機能を確認してから、[**インストール**] をクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-139">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

**<span data-ttu-id="c3acc-140">管理と監視のサーバー機能をアンインストールして、アップグレードを完了するには</span><span class="sxs-lookup"><span data-stu-id="c3acc-140">To uninstall the Administration and Monitoring Server features and to complete the upgrade</span></span>**

1.  <span data-ttu-id="c3acc-141">管理と監視のサーバー機能をホストしているコンピューターで、[コントロールパネル] の [**プログラムと機能**] を選択し、mbam をアンインストールして、以前にインストールされた web サイトとサービスを削除します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-141">On the computer that hosts the Administration and Monitoring Server features, in Control Panel, select **Programs and Features**, and then uninstall MBAM to remove the previously installed websites and services.</span></span>

2.  <span data-ttu-id="c3acc-142">バージョン2.0 の**MBAMSetup.exe**を実行します。必要に応じて、**カスタマーエクスペリエンス向上プログラム**を選択し、[**開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-142">Run the **MBAMSetup.exe** for version 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="c3acc-143">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-143">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="c3acc-144">[**トポロジの選択**] ページで、**スタンドアロン**または**System Center Configuration Manager 統合**トポロジを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-144">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="c3acc-145">[**インストールする機能の選択**] ページで、[**回復データベース**] と [**コンプライアンスと監査のデータベース**および監査**レポート**の機能] をオフにし、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-145">On the **Select features to install** page, clear the **Recovery Database** and **Compliance and Audit Database** and **Compliance and Audit Reports** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="c3acc-146">前提条件チェックが終了するまで待ち、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-146">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="c3acc-147">見つからない前提条件が検出された場合は、最初に不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-147">If a missing prerequisite is detected, resolve the missing prerequisites first, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="c3acc-148">[**ネットワーク通信セキュリティの構成**] ページで、web サイトとサービスに Secure Socket LAYER (SSL) 暗号化を使用するかどうかを選択します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-148">On the **Configure network communication security** page, choose whether to use Secure Socket Layer (SSL) encryption for the websites and services.</span></span> <span data-ttu-id="c3acc-149">通信を暗号化することにした場合は、暗号化に使用する証明機関 (CA) 証明書を選択します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-149">If you decide to encrypt the communication, select the certification authority (CA) certificate to use for encryption.</span></span>

    <span data-ttu-id="c3acc-150">**注** この手順を実行する前に証明書を作成して、このページで選択できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-150">**Note** The certificate must be created before this step to enable you to select it on this page.</span></span>

     

8.  <span data-ttu-id="c3acc-151">[**コンプライアンスステータスデータベースの場所の構成**] ページで、SQL Server インスタンスの名前と、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-151">On the **Configure the location of the Compliance Status database** page, specify the SQL Server instance name and the name of the database that stores the compliance and audit data.</span></span> <span data-ttu-id="c3acc-152">また、データベースファイルとログ情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-152">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="c3acc-153">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-153">Click **Next** to continue.</span></span>

10. <span data-ttu-id="c3acc-154">[**回復データベースの場所の構成**] ページで、SQL Server インスタンスの名前と回復データを格納するデータベースの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-154">On the **Configure the location of the Recovery Database** page, specify the SQL Server instance name and the name of the database that stores the recovery data.</span></span>

11. <span data-ttu-id="c3acc-155">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-155">Click **Next** to continue.</span></span>

12. <span data-ttu-id="c3acc-156">[**コンプライアンスおよび監査レポートの構成**] ページで、別のサーバーに構成したレポートインスタンスの URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-156">On the **Configure the Compliance and Audit Reports** page, enter the URL for the reporting instance that you configured on the other server.</span></span> <span data-ttu-id="c3acc-157">[**テスト**] ボタンを使用して、サイトに到達できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-157">Use the **Test** button to verify that you can reach the site.</span></span>

13. <span data-ttu-id="c3acc-158">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-158">Click **Next** to continue.</span></span>

14. <span data-ttu-id="c3acc-159">[**セルフサービスポータルの構成**] ページで、セルフサービスポータルのポート番号、ホスト名、仮想ディレクトリ名、インストールパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    <span data-ttu-id="c3acc-160">**注** 一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。</span><span class="sxs-lookup"><span data-stu-id="c3acc-160">**Note** The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span>

     

15. <span data-ttu-id="c3acc-161">[**管理と監視サーバーの構成**] ページで、ヘルプデスクの web サイトに必要な仮想ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-161">On the **Configure the Administration and Monitoring Server** page, specify the desired virtual directory for the Help Desk website.</span></span>

16. <span data-ttu-id="c3acc-162">コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c3acc-162">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="c3acc-163">この手順では、Windows で自動更新が有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-163">This step does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="c3acc-164">この製品または別の製品の Microsoft Update を以前に使用することを選択した場合、Microsoft Update ページは表示されません。</span><span class="sxs-lookup"><span data-stu-id="c3acc-164">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

17. <span data-ttu-id="c3acc-165">[**インストールの概要**] ページで、インストールされる機能を確認してから、[**インストール**] をクリックしてインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-165">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

18. <span data-ttu-id="c3acc-166">アップグレードが成功したことを確認するには、ドメイン内の別のコンピューターから各サイトにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-166">To validate that the upgrade was successful, verify that you can reach each site from another computer in the domain.</span></span>

## <span data-ttu-id="c3acc-167">エンドユーザーのコンピューター上の MBAM クライアントのアップグレード</span><span class="sxs-lookup"><span data-stu-id="c3acc-167">Upgrading the MBAM Client on End-User Computers</span></span>


<span data-ttu-id="c3acc-168">エンドユーザーコンピューターを MBAM 2.0 クライアントにアップグレードするには、各クライアントコンピューターで**MbamClientSetup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-168">To upgrade end-user computers to the MBAM 2.0 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="c3acc-169">インストーラーは、クライアントを MBAM 2.0 クライアントに自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-169">The installer automatically updates the Client to the MBAM 2.0 Client.</span></span> <span data-ttu-id="c3acc-170">MBAM クライアントは、電子ソフトウェア配布システム (Active Directory Domain Services または System Center Configuration Manager などのツール) を使用してインストールできます。</span><span class="sxs-lookup"><span data-stu-id="c3acc-170">You can install the MBAM Client through an electronic software distribution system, tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>

<span data-ttu-id="c3acc-171">クライアントのアップグレードを検証するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="c3acc-171">To validate the Client upgrade, do the following:</span></span>

1.  <span data-ttu-id="c3acc-172">構成済みのレポートサイクルが終了するまで待ち、SQL server コンピューターで**Sql Server Management Studio**を起動します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-172">Wait until the configured reporting cycle is finished, and then start **SQL Server Management Studio** on the SQL Server computer.</span></span>

2.  <span data-ttu-id="c3acc-173">SQL Server コンピューターで、 **Sql Server Management Studio**を起動します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-173">On the SQL Server computer, start **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="c3acc-174">[ **Recoveryandmachines (マシン**名) テーブルに、エンドユーザーのコンピューター名を示す行が含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3acc-174">Verify that the **RecoveryAndHardwareCore.Machines** table contains a row that shows the end-user’s computer name.</span></span>

## <span data-ttu-id="c3acc-175">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c3acc-175">Related topics</span></span>


[<span data-ttu-id="c3acc-176">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="c3acc-176">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





