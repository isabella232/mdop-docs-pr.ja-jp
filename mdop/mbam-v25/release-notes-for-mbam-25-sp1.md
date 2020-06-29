---
title: MBAM 2.5 SP1 のリリース ノート
description: MBAM 2.5 SP1 のリリース ノート
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824987"
---
# <span data-ttu-id="dc052-103">MBAM 2.5 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="dc052-103">Release Notes for MBAM 2.5 SP1</span></span>


<span data-ttu-id="dc052-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="dc052-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="dc052-105">Microsoft BitLocker 管理および監視 (MBAM) 2.5 SP1 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="dc052-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="dc052-106">これらのリリースノートには、MBAM を正常にインストールするために必要な情報が含まれており、製品のマニュアルに記載されていない情報が含まれていることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc052-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="dc052-107">これらのリリースノートが、他の MBAM 2.5 SP1 のドキュメントと異なる場合は、最新の変更について、権限を持つことを検討してください。</span><span class="sxs-lookup"><span data-stu-id="dc052-107">If these release notes differ from other MBAM 2.5 SP1 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="dc052-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="dc052-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> <span data-ttu-id="dc052-109">MBAM 2.5 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="dc052-109">MBAM 2.5 SP1 known issues</span></span>


<span data-ttu-id="dc052-110">このセクションには、MBAM 2.5 SP1 のリリースノートが記載されています。</span><span class="sxs-lookup"><span data-stu-id="dc052-110">This section contains release notes for MBAM 2.5 SP1.</span></span>

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a><span data-ttu-id="dc052-111">PowerShell の読み取り-AD \ \* コマンドレットは、ユーザーが十分な権限を持っていない場合はフィードバックを提供しません</span><span class="sxs-lookup"><span data-stu-id="dc052-111">PowerShell Read-AD\* cmdlets do not provide feedback if user does not have sufficient rights</span></span>

<span data-ttu-id="dc052-112">PowerShell を使用しようとしているユーザーが、MBAM サーバーのコマンドレットで、Active Directory の回復情報を読み取るか、TPM 情報を読み取る権限がない場合、コマンドレットによってエラーや警告がユーザーに提供されることはありません。</span><span class="sxs-lookup"><span data-stu-id="dc052-112">If a user trying to use the PowerShell Read-AD\* cmdlets for the MBAM Server does not have user rights to read the Active Directory recovery information or to read the TPM information, the cmdlets will not provide the user with any error or warning.</span></span>

<span data-ttu-id="dc052-113">**回避策:** 必要なユーザー権限がある場合にのみ、PowerShell の読み取り広告 \ \* コマンドレットを使います。</span><span class="sxs-lookup"><span data-stu-id="dc052-113">**Workaround:** Only use the PowerShell Read-AD\* cmdlets if you have the required user rights.</span></span>

### <span data-ttu-id="dc052-114">MBAM Active Directory (AD) 移行コマンドレットでボリューム回復情報が取得されない</span><span class="sxs-lookup"><span data-stu-id="dc052-114">MBAM Active Directory (AD) Migration cmdlets do not retrieve volume recovery information</span></span>

<span data-ttu-id="dc052-115">MBAM Active Directory (AD) 移行コマンドレットでは、スラッシュ文字 (/) が OU 名の一部である場合に、組織単位 (Ou) 内のコンピューターのボリューム回復情報を取得できません。</span><span class="sxs-lookup"><span data-stu-id="dc052-115">MBAM Active Directory (AD) Migration cmdlets fail to retrieve volume recovery information for computers in organizational units (OUs) if the forward slash character (/) is part of the OU name.</span></span> <span data-ttu-id="dc052-116">このエラーが発生すると、パイプラインの終了エラーが発生したため、AD の重複は繰り返されません。</span><span class="sxs-lookup"><span data-stu-id="dc052-116">Repeated AD pulls will fail with a pipeline terminating error when this error is encountered.</span></span>

<span data-ttu-id="dc052-117">**技術的な詳細:** コマンドの実行時に、次のエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-117">**Technical Details:** You will see this error when running the command:</span></span>

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

<span data-ttu-id="dc052-118">さらに、例外スタックトレース `Error[0].Exception.StackTrace` は次のようになります。</span><span class="sxs-lookup"><span data-stu-id="dc052-118">In addition, the Exception stack trace `Error[0].Exception.StackTrace` will look like this:</span></span>

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

<span data-ttu-id="dc052-119">**回避策:** この問題を解決するには、次のいずれかのタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc052-119">**Workaround:** Perform one of these tasks to resolve this situation:</span></span>

-   <span data-ttu-id="dc052-120">OU の名前を変更して、スラッシュ文字を削除してから、スクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc052-120">Rename the OU to remove the forward slash character and then run the script.</span></span>

-   <span data-ttu-id="dc052-121">問題のある OU をバックアッププロセスから除外するには、名前にスラッシュ文字が含まれていない Ou の一覧を探します。</span><span class="sxs-lookup"><span data-stu-id="dc052-121">To exclude any problematic OU from the backup process, find a list of OUs whose names do not contain the forward slash character.</span></span> <span data-ttu-id="dc052-122">これらの Ou で、一度に1つずつスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="dc052-122">Run the script on these OUs, one OU at a time.</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="dc052-123">Pc で TPM + PIN プロテクターを設定すると、MBAM でボリュームの暗号化に失敗し、エラーが報告される</span><span class="sxs-lookup"><span data-stu-id="dc052-123">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="dc052-124">エンドユーザーがタブレットデバイスで TPM + PIN プロテクターを設定しようとすると、MBAM が暗号化に失敗し、エラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-124">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="dc052-125">この問題は、タブレットデバイスがプレブート環境キーボードを持っていないために発生します。</span><span class="sxs-lookup"><span data-stu-id="dc052-125">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="dc052-126">**回避策:**[**タブレットでのプレブートキーボード入力を必要とする BitLocker 認証の有効化**を有効にする] グループポリシー設定</span><span class="sxs-lookup"><span data-stu-id="dc052-126">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="dc052-127">この設定は、BitLocker グループポリシー設定であり、MBAM グループポリシーテンプレートでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="dc052-127">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="dc052-128">すべてのサービスアカウントにユーザープリンシパル名が必要</span><span class="sxs-lookup"><span data-stu-id="dc052-128">User principal name is required for all service accounts</span></span>

<span data-ttu-id="dc052-129">MBAM のすべてのサービスアカウントにユーザープリンシパル名 (UPN) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc052-129">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="dc052-130">アカウントの UPN の作成に失敗した場合、構成プロセス中に、ユーザーまたはグループが Active Directory で見つからなかったことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-130">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="dc052-131">**回避策:** サービスアカウントに UPN を追加します。</span><span class="sxs-lookup"><span data-stu-id="dc052-131">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="dc052-132">IIS を .NET Framework 4.5 にアップグレードした後、セルフサービスポータルと管理と監視の Web サイトが開かない</span><span class="sxs-lookup"><span data-stu-id="dc052-132">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="dc052-133">インターネットインフォメーションサービス (IIS) を Microsoft .NET Framework 4.5 にアップグレードすると、セルフサービスポータルと管理と監視の Web サイトが開かなくなります。</span><span class="sxs-lookup"><span data-stu-id="dc052-133">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="dc052-134">**回避策:**[「.Net Framework 4.0 をインストールした後のエラーメッセージ」を参照してください。 "' HttpModule ' 型を読み込めませんでした](https://go.microsoft.com/fwlink/?LinkId=393568)。</span><span class="sxs-lookup"><span data-stu-id="dc052-134">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="dc052-135">レポートが構成されていない場合に、管理と監視の Web サイトに "レポートが見つかりません" というエラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="dc052-135">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="dc052-136">管理と監視の Web サイトを構成して、最初にレポート機能を構成せずにレポートを表示しようとすると、レポートが見つからないことを示すエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-136">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="dc052-137">**回避策:** Web アプリケーションを構成する前に、レポート機能を構成します。</span><span class="sxs-lookup"><span data-stu-id="dc052-137">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="dc052-138">管理と監視の Web サイトにあるレポートで、SSL が SSRS で構成されていない場合は警告が表示される</span><span class="sxs-lookup"><span data-stu-id="dc052-138">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="dc052-139">SQL Server Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーを構成するときに、レポート機能の URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-139">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="dc052-140">その後、管理と監視の Web サイトを開き、レポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-140">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="dc052-141">**回避策:** レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc052-141">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="dc052-142">この問題を解決するには、SQL Server Reporting Services がインストールされている MBAM コンピューターにアクセスし、 **Reporting Services 構成マネージャー**を実行して、[ **WEB サービスの URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc052-142">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="dc052-143">サーバーに適切な SSL 証明書を選択し、適切な SSL ポート (既定のポートは 443) を入力して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc052-143">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="dc052-144">BitLocker のコンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="dc052-144">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="dc052-145">BitLocker のコンプライアンスサマリーレポートにドリルダウンし、SSRS レポートの [**戻る**] リンクをクリックすると、エラーがスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc052-145">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="dc052-146">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="dc052-146">**Workaround:** None.</span></span>

### <span data-ttu-id="dc052-147">BitLocker コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="dc052-147">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="dc052-148">**[ドライブの暗号化方法を選択**してください] グループポリシーオブジェクトで特定の暗号強度を設定していない場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジの BitLocker コンピューターのコンプライアンスレポートでは、暗号強度に対して "unknown" が常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-148">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="dc052-149">グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-149">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="dc052-150">**回避策:\*\*\*\*[ドライブの暗号化方法と暗号強度**のグループポリシーオブジェクトを選択してください] で、常に特定の暗号強度を設定します。</span><span class="sxs-lookup"><span data-stu-id="dc052-150">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="dc052-151">ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される</span><span class="sxs-lookup"><span data-stu-id="dc052-151">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="dc052-152">SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-152">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="dc052-153">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="dc052-153">**Workaround:** None.</span></span> <span data-ttu-id="dc052-154">MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="dc052-154">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="dc052-155">強化されたセキュリティ構成により、レポートにエラーメッセージが誤って表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="dc052-155">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="dc052-156">Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"アクセス拒否" というエラーメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="dc052-156">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="dc052-157">既定では、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対してサーバーの脅威が減ることで、サーバーを保護するために ESC が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="dc052-157">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="dc052-158">**回避策:** MBAM サーバーでレポートを表示しようとしたときに "アクセス拒否" というエラーメッセージが表示される場合は、グループポリシーオブジェクトを設定するか、イメージ内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="dc052-158">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="dc052-159">また、ESC が有効になっていない別のコンピューターからレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="dc052-159">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="dc052-160">Bitlocker XTS-AES 暗号化アルゴリズムのサポート</span><span class="sxs-lookup"><span data-stu-id="dc052-160">Support for Bitlocker XTS-AES encryption algorithm</span></span>
<span data-ttu-id="dc052-161">Bitlocker は、Windows 10 バージョン1511での XTS 暗号化アルゴリズムのサポートを追加しました。</span><span class="sxs-lookup"><span data-stu-id="dc052-161">Bitlocker added support for the XTS-AES encryption algorithm in Windows 10, version 1511.</span></span> <span data-ttu-id="dc052-162">HF02 を使用すると、MBAM によってこの Bitlocker オプションのクライアントサポートが追加され、HF04 にサーバー側のサポートが追加されました。</span><span class="sxs-lookup"><span data-stu-id="dc052-162">With HF02, MBAM added client support for this Bitlocker option and in HF04, the server-side support was added.</span></span> <span data-ttu-id="dc052-163">ただし、いくつかの既知の制限があります。</span><span class="sxs-lookup"><span data-stu-id="dc052-163">However, there is one known limitation:</span></span>

* <span data-ttu-id="dc052-164">お客様は、同じマシン上の OS とデータボリュームに同じ暗号化強度を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc052-164">Customers must use the same encryption strength for OS and data volumes on the same machine.</span></span>
<span data-ttu-id="dc052-165">異なる暗号化強度が使用されている場合、MBAM は**非準拠**としてコンピューターを報告します。</span><span class="sxs-lookup"><span data-stu-id="dc052-165">If different encryption strengths are used, MBAM will report the machine as **non-compliant**.</span></span>

### <span data-ttu-id="dc052-166">セルフサービスポータルによってキー ID エントリに "-" が自動的に追加される</span><span class="sxs-lookup"><span data-stu-id="dc052-166">Self-Service Portal automatically adds "-" on Key ID entry</span></span>
<span data-ttu-id="dc052-167">HF02 の場合、MBAM セルフサービスポータルによって、キー ID エントリの '-' が自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="dc052-167">As of HF02, the MBAM Self-Service Portal automatically adds the '-' on Key ID entry.</span></span>  
<span data-ttu-id="dc052-168">**注:** Javascript が有効になるようにサーバーを再構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dc052-168">**Note:** The Server has to be reconfigured for the Javascript to take effect.</span></span>

### <span data-ttu-id="dc052-169">MBAM 2.5 Sp1 レポートが機能しない、または正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="dc052-169">MBAM 2.5 Sp1 Reports does not work / render properly</span></span>
<span data-ttu-id="dc052-170">SSRS が SQL Server 2016 エディションでホストされている場合、[レポート] ページは適切に表示されません。</span><span class="sxs-lookup"><span data-stu-id="dc052-170">Reports Page does not render properly when SSRS is hosted on SQL Server 2016 edition.</span></span> 
<span data-ttu-id="dc052-171">たとえば、ヘルプデスクへの参照-レポートをクリックします。 (強調表示されている部分には "x" が表示されています) これをさらに詳しく調査するには、Fiddler を使用して4.0、レポートをクリックします。</span><span class="sxs-lookup"><span data-stu-id="dc052-171">For example – Browsing to Helpdesk – Clicking on Reports – ( Highlighted portion have “x” on it ) Digging this further with Fiddler – it does look like once we click on Reports – it calls the SSRS page with HTML 4.0 rendering format.</span></span>

<span data-ttu-id="dc052-172">**回避策:** サイトのマスタコードを見ると、X UA モードが IE8 として認識されました。</span><span class="sxs-lookup"><span data-stu-id="dc052-172">**Workaround:** Looking at the site.master code and noticed the X-UA mode was dictated as IE8.</span></span> <span data-ttu-id="dc052-173">IE8 が終わりを超えているため、お客様は IE11 を使用しています。</span><span class="sxs-lookup"><span data-stu-id="dc052-173">As IE8 is WAY past the end of life, and customer is using IE11.</span></span> <span data-ttu-id="dc052-174">以下のコードの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="dc052-174">Update the setting to the below code.</span></span> <span data-ttu-id="dc052-175">これにより、サイトが IE11 のレンダリングテクノロジを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="dc052-175">This allows the site to utilize IE11 rendering technologies</span></span>

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

<span data-ttu-id="dc052-176">元の設定:</span><span class="sxs-lookup"><span data-stu-id="dc052-176">Original setting is:</span></span> 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


<span data-ttu-id="dc052-177">これは、Chrome、Firefox などの他のブラウザーで問題が発生しなかった理由を示しています。</span><span class="sxs-lookup"><span data-stu-id="dc052-177">This is the reason why the issue was not seen with other browsers like Chrome, Firefox etc.</span></span>



## <span data-ttu-id="dc052-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dc052-178">Related topics</span></span>


[<span data-ttu-id="dc052-179">MBAM 2.5 の概要</span><span class="sxs-lookup"><span data-stu-id="dc052-179">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="dc052-180">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="dc052-180">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="dc052-181">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="dc052-181">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="dc052-182">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="dc052-182">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





