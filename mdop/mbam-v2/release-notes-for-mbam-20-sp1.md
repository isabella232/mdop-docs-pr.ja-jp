---
title: MBAM 2.0 SP1 のリリース ノート
description: MBAM 2.0 SP1 のリリース ノート
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825584"
---
# <span data-ttu-id="2b71e-103">MBAM 2.0 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="2b71e-103">Release Notes for MBAM 2.0 SP1</span></span>


<span data-ttu-id="2b71e-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="2b71e-105">Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="2b71e-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="2b71e-106">これらのリリースノートには、BitLocker の管理と2.0 監視を行うために必要な情報が記載されています。また、これらの情報には、製品ドキュメントでは提供されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b71e-106">These release notes contain information that is required to successfully install BitLocker Administration and Monitoring 2.0 SP1, and they contain information that is not available in the product documentation.</span></span> <span data-ttu-id="2b71e-107">これらのリリースノートとその他の MBAM 2.0 SP1 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-107">If there is a difference between these release notes and other MBAM 2.0 SP1 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="2b71e-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="2b71e-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> <span data-ttu-id="2b71e-109">MBAM 2.0 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2b71e-109">MBAM 2.0 SP1 known issues</span></span>


<span data-ttu-id="2b71e-110">このセクションでは、MBAM 2.0 SP1 の既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-110">This section contains known issues for MBAM 2.0 SP1.</span></span>

### <span data-ttu-id="2b71e-111">Configuration Manager の統合トポロジを使用した MBAM から MBAM 2.0 SP1 へのアップグレードは、Configuration Manager オブジェクトを手動で削除する必要がある</span><span class="sxs-lookup"><span data-stu-id="2b71e-111">Upgrade of MBAM with Configuration Manager Integrated topology to MBAM 2.0 SP1 requires manual removal of Configuration Manager objects</span></span>

<span data-ttu-id="2b71e-112">MBAM を Configuration Manager で使用していて、MBAM 2.0 SP1 にアップグレードする場合は、MBAM インストールの一部として構成マネージャーにインストールされたすべての Configuration Manager オブジェクトを手動で削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-112">If you are using MBAM with Configuration Manager, and you want to upgrade to MBAM 2.0 SP1, you must manually remove all of the Configuration Manager objects that were installed into Configuration Manager as a part of the MBAM installation.</span></span> <span data-ttu-id="2b71e-113">手動で削除する必要があるオブジェクトは、MBAM レポート、MBAM サポートされているコンピューターのコレクション、および BitLocker 保護構成基準と関連する構成項目です。</span><span class="sxs-lookup"><span data-stu-id="2b71e-113">The objects that you must manually remove are the MBAM reports, MBAM Supported Computers collection, and the BitLocker Protection Configuration Baseline and its associated configuration items.</span></span>

<span data-ttu-id="2b71e-114">**回避策**: 次の手順を実行して、Configuration Manager オブジェクトをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-114">**Workaround**: Upgrade the Configuration Manager objects by completing the following steps:</span></span>

1.  <span data-ttu-id="2b71e-115">次の手順で説明するように、既存のコンプライアンスデータを外部ファイルにバックアップします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-115">Back up existing compliance data to an external file, as described in the following steps.</span></span>

    <span data-ttu-id="2b71e-116">**注** 既存のすべての BitLocker コンプライアンスデータは、Configuration Manager で既存のベースラインを削除すると削除されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-116">**Note** All existing BitLocker compliance data will be deleted when you delete the existing baseline in Configuration Manager.</span></span> <span data-ttu-id="2b71e-117">データは随時再生成されますが、コンプライアンスデータが再生成される前に、特定のコンピューターのコンプライアンスデータが必要になった場合に備えて、データのコピーを保存することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-117">The data will be regenerated over time, but it is recommended that you save a copy of the data in case you need the compliance data for a particular computer before the compliance data has been regenerated.</span></span>

     

    1.  <span data-ttu-id="2b71e-118">BitLocker のコンプライアンスデータの履歴を保存するには、[ **Bitlocker Enterprise コンプライアンスの詳細**] レポートを開きます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-118">To save historical BitLocker compliance data, open the **BitLocker Enterprise Compliance Details** Report.</span></span>

    2.  <span data-ttu-id="2b71e-119">レポートの [**保存**] アイコンをクリックし、[ **Excel**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-119">Click the **Save** icon in the report and select **Excel**.</span></span>

        <span data-ttu-id="2b71e-120">保存されたレポートには、コンピューター名、ドメイン名、コンプライアンスの状態、除外、デバイスユーザー、コンプライアンスステータスの詳細、最終連絡先の日付/時刻などのデータが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-120">The saved report will contain data such as the computer name, domain name, compliance status, exemption, device users, compliance status details, and last contact date/time.</span></span> <span data-ttu-id="2b71e-121">詳細なボリューム情報や暗号化の強度など、一部の情報は保存されません。</span><span class="sxs-lookup"><span data-stu-id="2b71e-121">Some information, such as detailed volume information and encryption strength, are not saved.</span></span>

2.  <span data-ttu-id="2b71e-122">**Mbam**インストーラーを使用して、サーバーから**mbam**をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-122">Uninstall **MBAM** from the server by using the **MBAM** installer.</span></span>

3.  <span data-ttu-id="2b71e-123">次のオブジェクトを Configuration Manager から手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-123">Manually delete the following objects from Configuration Manager:</span></span>

    -   <span data-ttu-id="2b71e-124">MBAM サポートされているコンピューターコレクション</span><span class="sxs-lookup"><span data-stu-id="2b71e-124">MBAM Supported Computers collection</span></span>

    -   <span data-ttu-id="2b71e-125">BitLocker の保護のベースライン</span><span class="sxs-lookup"><span data-stu-id="2b71e-125">BitLocker Protection baseline</span></span>

    -   <span data-ttu-id="2b71e-126">BitLocker オペレーティングシステムのドライブ保護構成項目</span><span class="sxs-lookup"><span data-stu-id="2b71e-126">BitLocker Operating System Drive Protection configuration item</span></span>

    -   <span data-ttu-id="2b71e-127">BitLocker 固定データドライブ保護構成項目</span><span class="sxs-lookup"><span data-stu-id="2b71e-127">BitLocker Fixed Data Drives Protection configuration item</span></span>

4.  <span data-ttu-id="2b71e-128">Configuration Manager SQL Server Reporting Services サイトで、[MBAM Reports] フォルダーを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-128">Manually delete the MBAM Reports folder in the Configuration Manager SQL Server Reporting Services site.</span></span> <span data-ttu-id="2b71e-129">これには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-129">To do this:</span></span>

    1.  <span data-ttu-id="2b71e-130">Internet Explorer を使用して、http://(cmserver/レポート) などのレポートサービスポイントを参照し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-130">Use Internet Explorer to browse to the reporting services point, for example, http://&lt;yourcmserver&gt;/reports.</span></span>

    2.  <span data-ttu-id="2b71e-131">適切な Configuration Manager サイトコードのリンクをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-131">Click the appropriate Configuration Manager site code link.</span></span>

    3.  <span data-ttu-id="2b71e-132">MBAM フォルダーを削除します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-132">Delete the MBAM folder.</span></span>

5.  <span data-ttu-id="2b71e-133">MBAM サーバーインストーラーを使って Configuration Manager の統合オブジェクトを再インストールします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-133">Use the MBAM Server installer to reinstall the Configuration Manager Integration objects.</span></span> <span data-ttu-id="2b71e-134">クライアントコンピューターは、時間を経て BitLocker コンプライアンスデータをもう一度アップロードし始めます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-134">The client computers will begin to upload BitLocker compliance data again over time.</span></span>

### <span data-ttu-id="2b71e-135">セルフサービスポータルの [送信] ボタンがインターネット Explorer10 で動作しない</span><span class="sxs-lookup"><span data-stu-id="2b71e-135">Submit button on Self-Service Portal does not work in Internet Explorer10</span></span>

<span data-ttu-id="2b71e-136">インターネット Explorer10 を使用して管理と監視の Web サイトにアクセスしても、web サイトの [**送信**] ボタンが機能しません。</span><span class="sxs-lookup"><span data-stu-id="2b71e-136">When you use Internet Explorer10 to access the Administration and Monitoring Website, the **Submit** button on the website does not work.</span></span>

<span data-ttu-id="2b71e-137">**対応策**: 管理と監視の web サイトをインストールしたサーバーで、 [ASP.NET browser 定義ファイルの修正プログラム](https://go.microsoft.com/fwlink/?LinkId=317798)をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-137">**Workaround**: On the server where you installed the Administration and Monitoring Website, install [Hotfix for ASP.NET browser definition files](https://go.microsoft.com/fwlink/?LinkId=317798).</span></span>

### <span data-ttu-id="2b71e-138">国際ドメイン名はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b71e-138">International domain names are not supported</span></span>

<span data-ttu-id="2b71e-139">MBAM 2.0 SP1 は、国際ドメイン名をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="2b71e-139">MBAM 2.0 SP1 does not support international domain names.</span></span>

<span data-ttu-id="2b71e-140">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="2b71e-140">**Workaround**: None.</span></span>

### <span data-ttu-id="2b71e-141">管理と監視の web サイトにあるレポートで、SSL が SSRS で構成されていない場合は警告が表示される</span><span class="sxs-lookup"><span data-stu-id="2b71e-141">Reports in the Administration and Monitoring website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="2b71e-142">SQLServer Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーをインストールするときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-142">If SQLServer Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="2b71e-143">次に、管理と監視の web サイトを参照してレポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-143">If you then browse to the Administration and Monitoring website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="2b71e-144">**対応策**: この問題を修正するには、SQLServer Reporting services がインストールされている mbam サーバー上の**Reporting Services 構成マネージャー**で SSL を構成します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-144">**Workaround**: To correct this issue, configure SSL in **Reporting Services Configuration Manager** on the MBAM server where SQLServer Reporting Services is installed.</span></span> <span data-ttu-id="2b71e-145">管理と監視サーバーの web サイトをアンインストールしてから再インストールします。</span><span class="sxs-lookup"><span data-stu-id="2b71e-145">Uninstall and then reinstall the Administration and Monitoring Server website.</span></span>

### <span data-ttu-id="2b71e-146">コンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="2b71e-146">Clicking Back in the Compliance Summary report might create an error</span></span>

<span data-ttu-id="2b71e-147">コンプライアンスの概要レポートにドリルダウンしている場合、SSRS レポートの [**戻る**] リンクをクリックすると、エラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-147">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might occur.</span></span>

<span data-ttu-id="2b71e-148">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="2b71e-148">**Workaround**: None.</span></span>

### <span data-ttu-id="2b71e-149">使用領域のみの暗号化が正常に動作しない</span><span class="sxs-lookup"><span data-stu-id="2b71e-149">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="2b71e-150">MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシーオブジェクトを設定していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-150">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only Encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="2b71e-151">MBAM クライアントをインストールする前に、使われているスペースのみの暗号化でコンピューターが暗号化されていて、同じ使用スペース専用の暗号化グループポリシーオブジェクトを設定している場合、MBAM は設定を認識し、コンプライアンスレポートで暗号化を正しく報告します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-151">If a computer is already encrypted with Used Space Only Encryption before you install the MBAM Client, and you have set the same Used Space Only Encryption Group Policy Object, MBAM recognizes the setting and reports the encryption correctly in the compliance reports.</span></span>

<span data-ttu-id="2b71e-152">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="2b71e-152">**Workaround**: None.</span></span>

### <span data-ttu-id="2b71e-153">コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="2b71e-153">Cipher strength displays incorrectly in the Computer Compliance report</span></span>

<span data-ttu-id="2b71e-154">**[ドライブの暗号化方法の選択] と [暗号強度**] のグループポリシーオブジェクトで特定の暗号強度を設定しない場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジ内のコンピューターのコンプライアンスレポートは常に、暗号強度の**不明な**状態で表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-154">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager integrated topology always displays **Unknown** for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="2b71e-155">グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-155">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="2b71e-156">**回避策**: **[ドライブの暗号化方法を選択してください] および [暗号強度**] グループポリシーオブジェクトで、常に特定の暗号強度を設定します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-156">**Workaround**: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="2b71e-157">ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される</span><span class="sxs-lookup"><span data-stu-id="2b71e-157">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="2b71e-158">SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-158">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="2b71e-159">**回避策**: なし。</span><span class="sxs-lookup"><span data-stu-id="2b71e-159">**Workaround**: None.</span></span> <span data-ttu-id="2b71e-160">MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-160">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="2b71e-161">セキュリティの構成を強化すると、レポートが正しく表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="2b71e-161">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="2b71e-162">Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"**アクセス拒否**" というメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-162">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an **Access Denied** message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="2b71e-163">既定では、強化されたセキュリティ構成は、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対するサーバーの脅威を減らすことによって、サーバーを保護するために有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2b71e-163">By default, Enhanced Security Configuration is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="2b71e-164">**対応策**: Mbam サーバーでレポートを表示しようとしたときに、**アクセス拒否**メッセージが表示される場合は、グループポリシーオブジェクトを設定するか、または画像内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-164">**Workaround**: If the **Access Denied** message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="2b71e-165">または、強化されたセキュリティ構成が有効になっていない別のコンピューターからレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-165">You can also alternatively view the reports from another computer on which Enhanced Security Configuration is not enabled.</span></span>

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> <span data-ttu-id="2b71e-166">SQLServer2008 から SQLServer2012 にアップグレードすると、MBAM サーバーのインストールが失敗する</span><span class="sxs-lookup"><span data-stu-id="2b71e-166">MBAM Server installation fails when you upgrade from SQLServer2008 to SQLServer2012</span></span>

<span data-ttu-id="2b71e-167">SQLServer2008 から SQLServer2012 にアップグレードして、コンプライアンスおよび監査データベースまたは回復データベースをインストールしようとすると、インストールが失敗してロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="2b71e-167">If you upgrade from SQLServer2008 to SQLServer2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="2b71e-168">このエラーは、必須の SQLCMD.exe ファイルが SQLServer のアップグレード中に削除され、MBAM インストーラーで見つからないために発生します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-168">The failure occurs because the required SQLCMD.exe file was removed during the SQLServer upgrade, and it cannot be found by the MBAM installer.</span></span> <span data-ttu-id="2b71e-169">MSI ログファイルの行は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="2b71e-169">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="2b71e-170">RunDbInstallScript 回復データベース CA: BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery データベース ca: dbInstance-xxxxxx\\I01RunDbInstallScript Recovery データベース CA: sqlScript-_Recovery at ¥ \ _and \ _HardwareRunDbInstallScript 回復用データベース CA: defaultFileName-MBAM \ _Recovery \ _and \ _HardwareRunDbInstallScript 回復データベース CA: defaultDataPath-F:\\MSSQL\\MSSQL10. をしてください。I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath-K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01 "" という管理および Monitoring\\ Setup\\ key_and _Recovery recoveryDefaultDataPath \ _Hardware "DefaultFileName =" MBAM \ _Recovery \ _and \ _Hardware "F:\\MSSQL\\MSSQL10. =" (\ \ \ \ "="I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript Recovery Db CA: 回復データベースの実行を開始します。回復用データベースのインストール scriptRunDbInstallScript 回復用データベース ca 例外: 回復用データベースのインストールカスタムアクションコマンドライン出力例外: 指定したファイルが見つからない</span><span class="sxs-lookup"><span data-stu-id="2b71e-170">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="2b71e-171">MBAM Server Windows Installer は、HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup. の下にあるレジストリの Path 文字列の値を確認することにより、SQLCMD.exe パスをハードコーディングしています。</span><span class="sxs-lookup"><span data-stu-id="2b71e-171">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="2b71e-172">このキーは、SQLServer2008 から SQLServer2012 への移行時にも表示されますが、データ値によって参照されるパスには、ファイルが削除されているため、SQLCMD.exe ファイルは含まれません。</span><span class="sxs-lookup"><span data-stu-id="2b71e-172">The key is still present during the migration from SQLServer2008 to SQLServer2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQLupgrade process removed the file.</span></span>

<span data-ttu-id="2b71e-173">**回避策**: HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 文字列値の名前を**path \ _old**に一時的に変更してから、Mbam サーバーで Windows インストーラーを実行します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-173">**Workaround**: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path string value to **Path\_old**, and then run Windows Installer on the MBAM Server again.</span></span> <span data-ttu-id="2b71e-174">インストールが正常に完了し、SQLServer2012 でデータベースが作成されたら、 **_Old path**の名前を**path**に変更します。</span><span class="sxs-lookup"><span data-stu-id="2b71e-174">When the installation completes successfully and creates the databases in SQLServer2012, rename **Path\_old** to **Path**.</span></span>

## <span data-ttu-id="2b71e-175">MBAM 2.0 SP1 のホットフィックスとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="2b71e-175">Hotfixes and Knowledge Base articles for MBAM 2.0 SP1</span></span>


<span data-ttu-id="2b71e-176">このセクションには、MBAM 2.0 SP1 の修正プログラムとサポート技術情報の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2b71e-176">This section contains hotfixes and KB articles for MBAM 2.0 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="2b71e-177">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="2b71e-177">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="2b71e-178">タイトル</span><span class="sxs-lookup"><span data-stu-id="2b71e-178">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="2b71e-179">リンク</span><span class="sxs-lookup"><span data-stu-id="2b71e-179">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-180">2831166</span><span class="sxs-lookup"><span data-stu-id="2b71e-180">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-181">Microsoft BitLocker の管理と監視 (MBAM) 2.0 のインストールで、 &quot; 既にインストールされている System CENTER CM オブジェクトがエラーになる&quot;</span><span class="sxs-lookup"><span data-stu-id="2b71e-181">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="2b71e-182">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-182">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-183">2870849</span><span class="sxs-lookup"><span data-stu-id="2b71e-183">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-184">MBAM 2.0 セルフサービスポータルを使用して、ユーザーが BitLocker 回復キーを取得できない</span><span class="sxs-lookup"><span data-stu-id="2b71e-184">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="2b71e-185">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-185">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-186">2756402</span><span class="sxs-lookup"><span data-stu-id="2b71e-186">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-187">MBAM クライアントでイベント ID 4 およびエラーコード0x8004100E が表示されない</span><span class="sxs-lookup"><span data-stu-id="2b71e-187">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="2b71e-188">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-188">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-189">2620287</span><span class="sxs-lookup"><span data-stu-id="2b71e-189">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-190">MBAM で [レポート] タブをクリックしたときに表示される "/レポート" というエラーメッセージ "サーバーエラー"</span><span class="sxs-lookup"><span data-stu-id="2b71e-190">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="2b71e-191">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-191">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-192">2639518</span><span class="sxs-lookup"><span data-stu-id="2b71e-192">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-193">MBAM で Enterprise またはコンピューターのコンプライアンスレポートを開くときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="2b71e-193">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="2b71e-194">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-194">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-195">2620269</span><span class="sxs-lookup"><span data-stu-id="2b71e-195">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-196">MBAM Enterprise レポートが更新されない</span><span class="sxs-lookup"><span data-stu-id="2b71e-196">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="2b71e-197">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-197">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-198">2712461</span><span class="sxs-lookup"><span data-stu-id="2b71e-198">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-199">ドメインコントローラーでの MBAM のインストールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="2b71e-199">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="2b71e-200">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-200">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-201">2876732</span><span class="sxs-lookup"><span data-stu-id="2b71e-201">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-202">MBAM 2.0 の単体または Configuration Manager の統合セットアップ中にエラーコード0x80071a90 が表示される</span><span class="sxs-lookup"><span data-stu-id="2b71e-202">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="2b71e-203">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-203">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-204">2754259</span><span class="sxs-lookup"><span data-stu-id="2b71e-204">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-205">MBAM とセキュリティで保護されたネットワーク通信</span><span class="sxs-lookup"><span data-stu-id="2b71e-205">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="2b71e-206">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-206">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-207">2870842</span><span class="sxs-lookup"><span data-stu-id="2b71e-207">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-208">SQL Server 2008 での Configuration Manager の統合シナリオ中に MBAM 2.0 セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="2b71e-208">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="2b71e-209">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-209">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-210">2668533</span><span class="sxs-lookup"><span data-stu-id="2b71e-210">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-211">SQL SSRS が適切に構成されていない場合、MBAM セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="2b71e-211">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="2b71e-212">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-212">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-213">2870847</span><span class="sxs-lookup"><span data-stu-id="2b71e-213">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-214">MBAM 2.0 のセットアップで &quot; &#39;Reporting Services ポイント&#39; ロールの Configuration Manager サーバーの役割設定を取得するときにエラーが発生する&quot;</span><span class="sxs-lookup"><span data-stu-id="2b71e-214">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="2b71e-215">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-215">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-216">2870839</span><span class="sxs-lookup"><span data-stu-id="2b71e-216">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-217">Mbam 2.0 Enterprise レポートが、SQL ジョブ CreateCache エラーのために MBAM 2.0 スタンドアロントポロジで更新されない</span><span class="sxs-lookup"><span data-stu-id="2b71e-217">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="2b71e-218">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-218">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-219">2620269</span><span class="sxs-lookup"><span data-stu-id="2b71e-219">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-220">MBAM Enterprise レポートが更新されない</span><span class="sxs-lookup"><span data-stu-id="2b71e-220">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="2b71e-221">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-221">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2b71e-222">2935997</span><span class="sxs-lookup"><span data-stu-id="2b71e-222">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-223">MBAM サポートされているコンピューターのコンプライアンスレポートにサポートされない製品が含まれている</span><span class="sxs-lookup"><span data-stu-id="2b71e-223">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="2b71e-224">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-224">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2b71e-225">2612822</span><span class="sxs-lookup"><span data-stu-id="2b71e-225">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="2b71e-226">MBAM でコンピューターレコードが拒否される</span><span class="sxs-lookup"><span data-stu-id="2b71e-226">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="2b71e-227">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="2b71e-227">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2b71e-228">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2b71e-228">Related topics</span></span>


[<span data-ttu-id="2b71e-229">MBAM 2.0 SP1 の概要</span><span class="sxs-lookup"><span data-stu-id="2b71e-229">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)

 

 





