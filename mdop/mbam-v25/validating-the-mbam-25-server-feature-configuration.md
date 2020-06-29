---
title: MBAM 2.5 サーバー機能の構成の確認
description: MBAM 2.5 サーバー機能の構成の確認
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827084"
---
# <span data-ttu-id="daac4-103">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="daac4-103">Validating the MBAM 2.5 Server Feature Configuration</span></span>


<span data-ttu-id="daac4-104">Microsoft BitLocker の管理と監視 (MBAM) 2.5 サーバー機能の展開が完了したら、展開を検証してすべての機能が正常に構成されていることを確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="daac4-104">When you finish the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server feature deployment, we recommend that you validate the deployment to ensure that all features have been successfully configured.</span></span> <span data-ttu-id="daac4-105">展開したトポロジ (スタンドアロンまたは System Center Configuration Manager の統合) と一致する手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="daac4-105">Use the procedure that matches the topology (Stand-alone or System Center Configuration Manager Integration) that you deployed.</span></span>

## <span data-ttu-id="daac4-106">スタンドアロントポロジを使用して MBAM サーバー展開を検証する</span><span class="sxs-lookup"><span data-stu-id="daac4-106">Validating the MBAM Server deployment with the Stand-alone topology</span></span>


<span data-ttu-id="daac4-107">スタンドアロントポロジを使って、MBAM サーバーの展開を検証するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="daac4-107">Use the following steps to validate your MBAM Server deployment with the Stand-alone topology.</span></span>

**<span data-ttu-id="daac4-108">スタンドアロンの MBAM サーバー展開を検証するには</span><span class="sxs-lookup"><span data-stu-id="daac4-108">To validate a Stand-alone MBAM Server deployment</span></span>**

1.  <span data-ttu-id="daac4-109">Mbam 機能が展開されている各サーバーで、[**コントロールパネル**プログラム] の [ &gt; **Programs** &gt; **プログラムと機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daac4-109">On each server where an MBAM feature is deployed, click **Control Panel** &gt; **Programs** &gt; **Programs and Features**.</span></span> <span data-ttu-id="daac4-110">**Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-110">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

    **<span data-ttu-id="daac4-111">注</span><span class="sxs-lookup"><span data-stu-id="daac4-111">Note</span></span>**  
    <span data-ttu-id="daac4-112">検証を実行するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daac4-112">To do the validation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="daac4-113">回復データベースが構成されているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースが構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-113">On the server where the Recovery Database is configured, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is configured.</span></span>

3.  <span data-ttu-id="daac4-114">コンプライアンスと監査データベースが構成されているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータスデータベース**が構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-114">On the server where the Compliance and Audit Database is configured, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is configured.</span></span>

4.  <span data-ttu-id="daac4-115">レポート機能が構成されているサーバーで、管理者の資格情報を使って web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。</span><span class="sxs-lookup"><span data-stu-id="daac4-115">On the server where the Reports feature is configured, open a web browser with administrative credentials and browse to the "Home" of the SQL Server Reporting Services site.</span></span>

    <span data-ttu-id="daac4-116">SQL Server Reporting Services サイトインスタンスの既定のホームの場所は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="daac4-116">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

    <span data-ttu-id="daac4-117">http (s)// &lt; *mbamレポート名* &gt; : &lt; *port* &gt; /レポート名</span><span class="sxs-lookup"><span data-stu-id="daac4-117">http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports.aspx</span></span>

    <span data-ttu-id="daac4-118">実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定したインスタンスを選択します。</span><span class="sxs-lookup"><span data-stu-id="daac4-118">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that you specified during setup.</span></span>

5.  <span data-ttu-id="daac4-119">**[Microsoft BitLocker 管理と監視**] という名前のレポートフォルダーに、 **MaltaDataSource**という名前のデータソースと言語フォルダーが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-119">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** as well as the language folders.</span></span> <span data-ttu-id="daac4-120">データソースには、言語を表す名前 (たとえば、en-us) のフォルダーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="daac4-120">The data source contains folders with names that represent languages (for example, en-us).</span></span> <span data-ttu-id="daac4-121">レポートは、言語フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="daac4-121">The reports are in the language folders.</span></span>

    **<span data-ttu-id="daac4-122">注</span><span class="sxs-lookup"><span data-stu-id="daac4-122">Note</span></span>**  
    <span data-ttu-id="daac4-123">SQL Server Reporting Services (SSRS) が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http (s)// &lt; *mbamレポート servername* &gt; : &lt; *port* &gt; /レポート \ _ &lt; *ssrsinstancename*&gt;</span><span class="sxs-lookup"><span data-stu-id="daac4-123">If SQL Server Reporting Services (SSRS) was configured as a named instance, the URL should resemble the following: http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports\_&lt;*SSRSInstanceName*&gt;</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. <span data-ttu-id="daac4-124">[Web サイトの管理と監視] 機能が構成されているサーバーで、**サーバーマネージャー**を実行し、**役割**を参照して、[ **Web サーバー (iis)** ] &gt; **インターネットインフォメーションサービス (iis) マネージャー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="daac4-124">On the server where the Administration and Monitoring Website feature is configured, run **Server Manager**, browse to **Roles**, and then select **Web Server (IIS)** &gt; **Internet Information Services (IIS) Manager**.</span></span>

7. <span data-ttu-id="daac4-125">[**接続**] で、[ \* &lt; コンピューター &gt; 名\*] を参照し **、[** &gt; **Microsoft BitLocker 管理と監視**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="daac4-125">In **Connections**, browse to *&lt;computer name&gt;* and select **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="daac4-126">次の内容が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-126">Verify that the following are listed:</span></span>

   -   **<span data-ttu-id="daac4-127">Mbam管理サービス</span><span class="sxs-lookup"><span data-stu-id="daac4-127">MBAMAdministrationService</span></span>**

   -   **<span data-ttu-id="daac4-128">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="daac4-128">MBAMComplianceStatusService</span></span>**

   -   **<span data-ttu-id="daac4-129">Mbamrecoveryandハードウェアサービス</span><span class="sxs-lookup"><span data-stu-id="daac4-129">MBAMRecoveryAndHardwareService</span></span>**

8. <span data-ttu-id="daac4-130">管理と監視の Web サイトとセルフサービスポータルが構成されているサーバーで、管理者の資格情報を使って web ブラウザーを開きます。</span><span class="sxs-lookup"><span data-stu-id="daac4-130">On the server where the Administration and Monitoring Website and Self-Service Portal are configured, open a web browser with administrative credentials.</span></span>

9. <span data-ttu-id="daac4-131">次の web サイトを参照して、正常に読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-131">Browse to the following websites to verify that they load successfully:</span></span>

   -   <span data-ttu-id="daac4-132">https (s)/ &lt; *mbam管理 servername* &gt; : &lt; *port*/ &gt; helpデスク/-ナビゲーションとレポートの各リンクを確認する</span><span class="sxs-lookup"><span data-stu-id="daac4-132">https(s)://&lt;*MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/HelpDesk/ - confirm each of the links for navigation and reports</span></span>

   -   <span data-ttu-id="daac4-133">http (s):/ &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /selfservice/</span><span class="sxs-lookup"><span data-stu-id="daac4-133">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/SelfService/</span></span>

   **<span data-ttu-id="daac4-134">注</span><span class="sxs-lookup"><span data-stu-id="daac4-134">Note</span></span>**  
   <span data-ttu-id="daac4-135">ネットワーク暗号化されていない既定のポートでサーバー機能を構成していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="daac4-135">It is assumed that you configured the server features on the default port without network encryption.</span></span> <span data-ttu-id="daac4-136">異なるポートまたは仮想ディレクトリにサーバー機能を構成した場合は、次のようにして適切なポートを含むように Url を変更します。</span><span class="sxs-lookup"><span data-stu-id="daac4-136">If you configured the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example:</span></span>

   <span data-ttu-id="daac4-137">http (s)// &lt; *host name* &gt; : &lt; *port*/ &gt; helpデスク/</span><span class="sxs-lookup"><span data-stu-id="daac4-137">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/HelpDesk/</span></span>

   <span data-ttu-id="daac4-138">http (s)// &lt; *host name* &gt; : &lt; *port* &gt; / &lt; *virtualdirectory*&gt;/</span><span class="sxs-lookup"><span data-stu-id="daac4-138">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/&lt;*virtualdirectory*&gt;/</span></span>

   <span data-ttu-id="daac4-139">サーバー機能がネットワーク暗号化で構成されていた場合は、http://を https://に変更します。</span><span class="sxs-lookup"><span data-stu-id="daac4-139">If the server features were configured with network encryption, change http:// to https://.</span></span>



10. <span data-ttu-id="daac4-140">次の web サービスを参照して、正しく読み込まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-140">Browse to the following web services to verify that they load successfully.</span></span> <span data-ttu-id="daac4-141">サービスが実行中であることを示すページが表示されますが、このページにはメタデータは表示されません。</span><span class="sxs-lookup"><span data-stu-id="daac4-141">A page opens to indicate that the service is running, but the page does not display any metadata.</span></span>

    -   <span data-ttu-id="daac4-142">http (s):/ &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /mbam管理サービス/管理サービス</span><span class="sxs-lookup"><span data-stu-id="daac4-142">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>

    -   <span data-ttu-id="daac4-143">http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="daac4-143">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>

    -   <span data-ttu-id="daac4-144">http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="daac4-144">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>

    -   <span data-ttu-id="daac4-145">http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="daac4-145">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>

## <span data-ttu-id="daac4-146">Configuration Manager の統合トポロジを使用して MBAM サーバー展開を検証する</span><span class="sxs-lookup"><span data-stu-id="daac4-146">Validating the MBAM Server deployment with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="daac4-147">Configuration Manager の統合トポロジを使用して、MBAM 展開を検証するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="daac4-147">Use the following steps to validate your MBAM deployment with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="daac4-148">使用している Configuration Manager のバージョンと一致する検証手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="daac4-148">Complete the validation steps that match the version of Configuration Manager that you are using.</span></span>

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a><span data-ttu-id="daac4-149">System Center 2012 構成マネージャーを使用して MBAM サーバー展開を検証する</span><span class="sxs-lookup"><span data-stu-id="daac4-149">Validating the MBAM Server deployment with System Center 2012 Configuration Manager</span></span>

<span data-ttu-id="daac4-150">System Center 2012 構成マネージャーで MBAM を使用している場合に、次の手順を実行して、MBAM サーバーの展開を検証します。</span><span class="sxs-lookup"><span data-stu-id="daac4-150">Use these steps to validate your MBAM Server deployment when you are using MBAM with System Center 2012 Configuration Manager.</span></span>

**<span data-ttu-id="daac4-151">Configuration Manager Integration MBAM 展開を検証するには: System Center 2012 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="daac4-151">To validate a Configuration Manager Integration MBAM Server deployment – System Center 2012 Configuration Manager</span></span>**

1.  <span data-ttu-id="daac4-152">System Center 2012 構成マネージャーが展開されているサーバーで、[**コントロールパネル**] の [**プログラムと機能**] を開き、 **Microsoft BitLocker の管理と監視**が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-152">On the server where System Center 2012 Configuration Manager is deployed, open **Programs and Features** in **Control Panel**, and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="daac4-153">注</span><span class="sxs-lookup"><span data-stu-id="daac4-153">Note</span></span>**  
    <span data-ttu-id="daac4-154">構成を検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daac4-154">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="daac4-155">Configuration Manager コンソールで、[**アセット And コンプライアンス**ワークスペース &gt; **デバイスコレクション**] をクリックし、 **mbam サポートコンピューター**という新しいコレクションが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-155">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Device Collections**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="daac4-156">Configuration Manager コンソールで、[ **Monitoring** workspace &gt; **レポート** &gt; **レポート**( &gt; **mbam**)] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daac4-156">In the Configuration Manager console, click the **Monitoring** workspace &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

4.  <span data-ttu-id="daac4-157">**Mbam**フォルダーに、異なる言語を表す名前のサブフォルダーが含まれていること、および各言語のサブフォルダーに次のレポートが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-157">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="daac4-158">BitLocker コンピューターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="daac4-158">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="daac4-159">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="daac4-159">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="daac4-160">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="daac4-160">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="daac4-161">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="daac4-161">BitLocker Enterprise Compliance Summary</span></span>

5.  <span data-ttu-id="daac4-162">Configuration Manager コンソールで、[**資産とコンプライアンス**ワークスペースの &gt; **コンプライアンス設定**] の &gt; **構成基準**をクリックし、構成基準として**BitLocker 保護**が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-162">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

6.  <span data-ttu-id="daac4-163">Configuration Manager コンソールで、[**資産とコンプライアンス**ワークスペースの &gt; **コンプライアンス設定**] &gt; **構成項目**をクリックし、次の新しい構成項目が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-163">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="daac4-164">BitLocker 固定データドライブの保護</span><span class="sxs-lookup"><span data-stu-id="daac4-164">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="daac4-165">BitLocker オペレーティングシステムドライブの保護</span><span class="sxs-lookup"><span data-stu-id="daac4-165">BitLocker Operating System Drive Protection</span></span>

### <span data-ttu-id="daac4-166">Configuration Manager 2007 を使用して MBAM サーバー展開を検証する</span><span class="sxs-lookup"><span data-stu-id="daac4-166">Validating the MBAM Server deployment with Configuration Manager 2007</span></span>

<span data-ttu-id="daac4-167">MBAM を Configuration Manager 2007 で使用している場合に、次の手順を使用して、MBAM サーバーの展開を検証します。</span><span class="sxs-lookup"><span data-stu-id="daac4-167">Use these steps to validate your MBAM Server deployment when you are using MBAM with Configuration Manager 2007.</span></span>

**<span data-ttu-id="daac4-168">Configuration Manager 統合 MBAM サーバー展開を検証するには (Configuration Manager 2007)</span><span class="sxs-lookup"><span data-stu-id="daac4-168">To validate a Configuration Manager Integration MBAM Server deployment – Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="daac4-169">Configuration Manager 2007 が展開されているサーバーで、[**コントロールパネル**] の [**プログラムと機能**] を開き、 **Microsoft BitLocker の管理と監視**が表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-169">On the server where Configuration Manager 2007 is deployed, open **Programs and Features** on **Control Panel** , and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="daac4-170">注</span><span class="sxs-lookup"><span data-stu-id="daac4-170">Note</span></span>**  
    <span data-ttu-id="daac4-171">構成を検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="daac4-171">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="daac4-172">Configuration Manager コンソールで、[**サイトデータベース &lt; SiteCode &gt;  -  &lt; 名 &gt; 、 &lt; SiteName &gt; )、コンピューターの管理**] の順番にクリックし、「 **mbam サポートされているコンピューター** 」という新しいコレクションが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-172">In the Configuration Manager console, click **Site Database &lt;SiteCode&gt; - &lt;ServerName&gt;, &lt;SiteName&gt;), Computer Management**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="daac4-173">Configuration Manager コンソールで、[ **reporting** &gt; **reporting Services** &gt; \*\* \\\\ &lt; &gt; ServerName\*\* &gt; **レポートフォルダー** &gt; **mbam**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="daac4-173">In the Configuration Manager console, click **Reporting** &gt; **Reporting Services** &gt; **\\\\&lt;ServerName&gt;** &gt; **Report Folders** &gt; **MBAM**.</span></span>

    <span data-ttu-id="daac4-174">**Mbam**フォルダーに、異なる言語を表す名前のサブフォルダーが含まれていること、および各言語のサブフォルダーに次のレポートが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-174">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="daac4-175">BitLocker コンピューターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="daac4-175">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="daac4-176">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="daac4-176">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="daac4-177">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="daac4-177">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="daac4-178">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="daac4-178">BitLocker Enterprise Compliance Summary</span></span>

4.  <span data-ttu-id="daac4-179">Configuration Manager コンソールで、[ **Desired configuration Management** &gt; **configuration**baseline] をクリックし、構成基準の**BitLocker 保護**が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-179">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

5.  <span data-ttu-id="daac4-180">Configuration Manager コンソールで、[ **Desired configuration Management** &gt; **configuration items**] をクリックし、次の新しい構成アイテムが表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="daac4-180">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="daac4-181">BitLocker 固定データドライブの保護</span><span class="sxs-lookup"><span data-stu-id="daac4-181">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="daac4-182">BitLocker オペレーティングシステムドライブの保護</span><span class="sxs-lookup"><span data-stu-id="daac4-182">BitLocker Operating System Drive Protection</span></span>



## <span data-ttu-id="daac4-183">関連トピック</span><span class="sxs-lookup"><span data-stu-id="daac4-183">Related topics</span></span>


[<span data-ttu-id="daac4-184">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="daac4-184">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)


## <span data-ttu-id="daac4-185">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="daac4-185">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="daac4-186">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="daac4-186">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="daac4-187">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="daac4-187">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






