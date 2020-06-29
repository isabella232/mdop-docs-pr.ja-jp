---
title: MBAM 2.5 のリリース ノート
description: MBAM 2.5 のリリース ノート
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824984"
---
# <span data-ttu-id="2cbec-103">MBAM 2.5 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="2cbec-103">Release Notes for MBAM 2.5</span></span>


<span data-ttu-id="2cbec-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="2cbec-105">Microsoft BitLocker 管理と監視 (MBAM) 2.5 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="2cbec-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5.</span></span> <span data-ttu-id="2cbec-106">これらのリリースノートには、MBAM を正常にインストールするために必要な情報が含まれており、製品のマニュアルに記載されていない情報が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="2cbec-107">これらのリリースノートが他の MBAM 2.5 ドキュメントと異なる場合は、最新の変更については、次の点を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="2cbec-107">If these release notes differ from other MBAM 2.5 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="2cbec-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="2cbec-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-known-issues"></a> <span data-ttu-id="2cbec-109">MBAM 2.5 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2cbec-109">MBAM 2.5 known issues</span></span>


<span data-ttu-id="2cbec-110">このセクションには、MBAM 2.5 のリリースノートが記載されています。</span><span class="sxs-lookup"><span data-stu-id="2cbec-110">This section contains release notes for MBAM 2.5.</span></span>

### <span data-ttu-id="2cbec-111">Web ブラウザーが管理者として予期せずに実行される</span><span class="sxs-lookup"><span data-stu-id="2cbec-111">Web browser unintentionally run as administrator</span></span>

<span data-ttu-id="2cbec-112">MBAM サーバー構成ツールのヘルプリンクを使用すると、ブラウザーウィンドウが管理者権限で開かれる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-112">Help links in the MBAM Server Configuration tool can cause browser windows to open with administrator rights.</span></span>

<span data-ttu-id="2cbec-113">**回避策:** Internet Explorer 強化セキュリティの構成 (IESC) を有効にするか、web ブラウザーを閉じてから他のサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-113">**Workaround:** Enable Internet Explorer Enhanced Security Configuration (IESC) or close your web browser before navigating to other sites.</span></span>

<span data-ttu-id="2cbec-114">**注** これは、MBAM 2.5 SP1 で修正されています。</span><span class="sxs-lookup"><span data-stu-id="2cbec-114">**Note** This is fixed in MBAM 2.5 SP1.</span></span>

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> <span data-ttu-id="2cbec-115">MBAM は、AES 256 ビット暗号化キーとディフューザーで暗号化されたクライアントに準拠していないと報告</span><span class="sxs-lookup"><span data-stu-id="2cbec-115">MBAM reports as noncompliant a client encrypted with AES 256-bit encryption keys and Diffuser</span></span>

<span data-ttu-id="2cbec-116">コンピューターに MBAM 2.5 クライアントがインストールされていて、AES 256 ビットをディフューザーの暗号強度で使用して暗号化されている場合、mbam コンプライアンスレポートでは、MBAM クライアントは準拠していないと報告されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-116">If a computer has the MBAM 2.5 client installed and is encrypted by using the AES 256-bit with Diffuser cipher strength, the MBAM client is reported as noncompliant in the MBAM compliance reports.</span></span>

<span data-ttu-id="2cbec-117">**回避策:**[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)に修正プログラムをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2cbec-117">**Workaround:** Install the hotfix at [KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972).</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="2cbec-118">Pc で TPM + PIN プロテクターを設定すると、MBAM でボリュームの暗号化に失敗し、エラーが報告される</span><span class="sxs-lookup"><span data-stu-id="2cbec-118">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="2cbec-119">エンドユーザーがタブレットデバイスで TPM + PIN プロテクターを設定しようとすると、MBAM が暗号化に失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-119">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="2cbec-120">この問題は、タブレットデバイスがプレブート環境キーボードを持っていないために発生します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-120">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="2cbec-121">**回避策:**[**タブレットでのプレブートキーボード入力を必要とする BitLocker 認証の有効化**を有効にする] グループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="2cbec-121">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="2cbec-122">この設定は、BitLocker グループポリシー設定であり、MBAM グループポリシーテンプレートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="2cbec-122">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="2cbec-123">すべてのサービスアカウントにユーザープリンシパル名が必要</span><span class="sxs-lookup"><span data-stu-id="2cbec-123">User principal name is required for all service accounts</span></span>

<span data-ttu-id="2cbec-124">MBAM のすべてのサービスアカウントにユーザープリンシパル名 (UPN) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-124">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="2cbec-125">アカウントの UPN の作成に失敗した場合、構成プロセス中に、ユーザーまたはグループが Active Directory で見つからなかったことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-125">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="2cbec-126">**回避策:** サービスアカウントに UPN を追加します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-126">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="2cbec-127">クライアントコンピューターが Microsoft Ajax コンテンツ配信ネットワークにアクセスできない場合は、セルフサービスポータルで追加の構成が必要</span><span class="sxs-lookup"><span data-stu-id="2cbec-127">Self-Service Portal requires additional configuration if client computers cannot access Microsoft Ajax Content Delivery Network</span></span>

<span data-ttu-id="2cbec-128">クライアントコンピューターに Microsoft Ajax コンテンツ配信ネットワーク (CDN) へのアクセス権がなく、特定の JavaScript ファイルに必要なアクセス権をセルフサービスポータルに提供している場合は、アクセス可能なソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-128">If your client computers do not have access to the Microsoft Ajax Content Delivery Network (CDN), which gives the Self-Service Portal the access that it requires to certain JavaScript files, you must configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span> <span data-ttu-id="2cbec-129">クライアントコンピューターが CDN にアクセスできないときにセルフサービスポータルを構成していない場合は、会社名とログオン時に使用したアカウントのみが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-129">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which you logged on is displayed.</span></span> <span data-ttu-id="2cbec-130">エラーメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2cbec-130">No error message appears.</span></span>

<span data-ttu-id="2cbec-131">**回避策:** MBAM 2.5 SP1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="2cbec-131">**Workaround:** Install MBAM 2.5 SP1.</span></span> <span data-ttu-id="2cbec-132">または、次の手順に従ってセルフサービスポータルを構成するか、[クライアントコンピューターが Microsoft コンテンツ配信ネットワークにアクセスできないときにセルフサービスポータルを構成する方法](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)に従います。</span><span class="sxs-lookup"><span data-stu-id="2cbec-132">or configure the Self-Service Portal by following these instructions: [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>

### <span data-ttu-id="2cbec-133">IIS を .NET Framework 4.5 にアップグレードした後、セルフサービスポータルと管理と監視の Web サイトが開かない</span><span class="sxs-lookup"><span data-stu-id="2cbec-133">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="2cbec-134">インターネットインフォメーションサービス (IIS) を Microsoft .NET Framework 4.5 にアップグレードすると、セルフサービスポータルと管理と監視の Web サイトが開かなくなります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-134">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="2cbec-135">**回避策:**[「.Net Framework 4.0 をインストールした後のエラーメッセージ」を参照してください。 "' HttpModule ' 型を読み込めませんでした](https://go.microsoft.com/fwlink/?LinkId=393568)。</span><span class="sxs-lookup"><span data-stu-id="2cbec-135">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="2cbec-136">レポートが構成されていない場合に、管理と監視の Web サイトに "レポートが見つかりません" というエラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="2cbec-136">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="2cbec-137">管理と監視の Web サイトを構成して、最初にレポート機能を構成せずにレポートを表示しようとすると、レポートが見つからないことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-137">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="2cbec-138">**回避策:** Web アプリケーションを構成する前に、レポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-138">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="2cbec-139">管理と監視の Web サイトにあるレポートで、SSL が SSRS で構成されていない場合は警告が表示される</span><span class="sxs-lookup"><span data-stu-id="2cbec-139">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="2cbec-140">SQL Server Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーを構成するときに、レポート機能の URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-140">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="2cbec-141">その後、管理と監視の Web サイトを開き、レポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-141">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="2cbec-142">**回避策:** レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cbec-142">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="2cbec-143">この問題を解決するには、SQL Server Reporting Services がインストールされている MBAM コンピューターにアクセスし、 **Reporting Services 構成マネージャー**を実行して、[ **WEB サービスの URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cbec-143">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="2cbec-144">サーバーに適切な SSL 証明書を選択し、適切な SSL ポート (既定のポートは 443) を入力して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2cbec-144">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="2cbec-145">BitLocker のコンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="2cbec-145">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="2cbec-146">BitLocker のコンプライアンスサマリーレポートにドリルダウンし、SSRS レポートの [**戻る**] リンクをクリックすると、エラーがスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-146">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="2cbec-147">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="2cbec-147">**Workaround:** None.</span></span>

### <span data-ttu-id="2cbec-148">使用領域のみの暗号化が正常に動作しない</span><span class="sxs-lookup"><span data-stu-id="2cbec-148">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="2cbec-149">MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシー設定を構成していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-149">If you encrypt a computer for the first time after you install the MBAM Client, and you have configured a Group Policy setting to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="2cbec-150">MBAM クライアントをインストールするときにのみ使用されるスペースでコンピューターが暗号化されていて、同じグループポリシー設定を構成している場合、MBAM はドライブが正しく暗号化されていることを報告します。ドライブは再暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="2cbec-150">If a computer is already encrypted with Used Space Only when you install the MBAM Client, and you have configured the same Group Policy setting, MBAM reports that the drive is encrypted correctly, and does not try to re-encrypt the drive.</span></span>

<span data-ttu-id="2cbec-151">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="2cbec-151">**Workaround:** None.</span></span>

### <span data-ttu-id="2cbec-152">BitLocker コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="2cbec-152">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="2cbec-153">**[ドライブの暗号化方法を選択**してください] グループポリシーオブジェクトで特定の暗号強度を設定していない場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジの BitLocker コンピューターのコンプライアンスレポートでは、暗号強度に対して "unknown" が常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-153">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="2cbec-154">グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-154">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="2cbec-155">**回避策:\*\*\*\*[ドライブの暗号化方法と暗号強度**のグループポリシーオブジェクトを選択してください] で、常に特定の暗号強度を設定します。</span><span class="sxs-lookup"><span data-stu-id="2cbec-155">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="2cbec-156">ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される</span><span class="sxs-lookup"><span data-stu-id="2cbec-156">Compliance Status Distribution by Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="2cbec-157">SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-157">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="2cbec-158">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="2cbec-158">**Workaround:** None.</span></span> <span data-ttu-id="2cbec-159">MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-159">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="2cbec-160">強化されたセキュリティ構成により、レポートにエラーメッセージが誤って表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="2cbec-160">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="2cbec-161">Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"アクセス拒否" というエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="2cbec-161">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="2cbec-162">既定では、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対してサーバーの脅威が減ることで、サーバーを保護するために ESC が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="2cbec-162">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="2cbec-163">**回避策:** MBAM サーバーでレポートを表示しようとしたときに "アクセス拒否" というエラーメッセージが表示される場合は、グループポリシーオブジェクトを設定するか、イメージ内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-163">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="2cbec-164">また、ESC が有効になっていない別のコンピューターからレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="2cbec-164">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a><span data-ttu-id="2cbec-165">MBAM 2.5 の修正プログラムとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="2cbec-165">Hotfixes and Knowledge Base articles for MBAM 2.5</span></span>


<span data-ttu-id="2cbec-166">次の表は、MBAM 2.5 の修正プログラムとサポート技術情報の記事を示しています。</span><span class="sxs-lookup"><span data-stu-id="2cbec-166">This table lists the hotfixes and KB articles for MBAM 2.5.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="2cbec-167">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="2cbec-167">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="2cbec-168">タイトル</span><span class="sxs-lookup"><span data-stu-id="2cbec-168">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="2cbec-169">リンク</span><span class="sxs-lookup"><span data-stu-id="2cbec-169">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cbec-170">2975636</span><span class="sxs-lookup"><span data-stu-id="2cbec-170">2975636</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-171">Microsoft BitLocker 管理および監視2.5 の修正プログラムパッケージ1</span><span class="sxs-lookup"><span data-stu-id="2cbec-171">Hotfix Package 1 for Microsoft BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)"><span data-ttu-id="2cbec-172">support.microsoft.com/kb/2975636/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-172">support.microsoft.com/kb/2975636/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cbec-173">3015477</span><span class="sxs-lookup"><span data-stu-id="2cbec-173">3015477</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-174">BitLocker 管理および監視2.5 の修正プログラムパッケージ2</span><span class="sxs-lookup"><span data-stu-id="2cbec-174">Hotfix Package 2 for BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)"><span data-ttu-id="2cbec-175">support.microsoft.com/kb/3015477</span><span class="sxs-lookup"><span data-stu-id="2cbec-175">support.microsoft.com/kb/3015477</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cbec-176">3011022</span><span class="sxs-lookup"><span data-stu-id="2cbec-176">3011022</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-177">SSRS インスタンスの名前にアンダースコアが含まれている場合、MBAM 2.5 のインストールまたは構成マネージャーのレポートが失敗する</span><span class="sxs-lookup"><span data-stu-id="2cbec-177">MBAM 2.5 installation or Configuration Manager reporting fails if the name of SSRS instance contains an underscore</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)"><span data-ttu-id="2cbec-178">support.microsoft.com/kb/3011022/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-178">support.microsoft.com/kb/3011022/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cbec-179">2756402</span><span class="sxs-lookup"><span data-stu-id="2cbec-179">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-180">MBAM クライアントでイベント ID 4 およびエラーコード0x8004100E が表示されない</span><span class="sxs-lookup"><span data-stu-id="2cbec-180">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="2cbec-181">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-181">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cbec-182">2639518</span><span class="sxs-lookup"><span data-stu-id="2cbec-182">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-183">MBAM で Enterprise またはコンピューターのコンプライアンスレポートを開くときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="2cbec-183">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="2cbec-184">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-184">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cbec-185">2870842</span><span class="sxs-lookup"><span data-stu-id="2cbec-185">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-186">SQL Server 2008 での Configuration Manager の統合シナリオ中に MBAM 2.0 セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="2cbec-186">MBAM 2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="2cbec-187">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-187">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cbec-188">2975472</span><span class="sxs-lookup"><span data-stu-id="2cbec-188">2975472</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cbec-189">多くの MBAM クライアントが MBAM 回復データベースに接続されている場合の SQL デッドロック</span><span class="sxs-lookup"><span data-stu-id="2cbec-189">SQL deadlocks when many MBAM clients connect to the MBAM recovery database</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)"><span data-ttu-id="2cbec-190">support.microsoft.com/kb/2975472/EN-US</span><span class="sxs-lookup"><span data-stu-id="2cbec-190">support.microsoft.com/kb/2975472/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="2cbec-191">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2cbec-191">Related topics</span></span>


[<span data-ttu-id="2cbec-192">MBAM 2.5 の概要</span><span class="sxs-lookup"><span data-stu-id="2cbec-192">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="2cbec-193">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="2cbec-193">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2cbec-194">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="2cbec-194">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="2cbec-195">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="2cbec-195">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





