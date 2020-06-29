---
title: MBAM 2.0 のリリース ノート
description: MBAM 2.0 のリリース ノート
author: dansimp
ms.assetid: c3f16cf3-94f2-47ac-b3a4-3dc505c6a8dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d5d3c7d539cf2828d28c1844321bc34ab7736ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825587"
---
# <span data-ttu-id="ee9a7-103">MBAM 2.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="ee9a7-103">Release Notes for MBAM 2.0</span></span>


<span data-ttu-id="ee9a7-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="ee9a7-105">Microsoft BitLockerAdministration および Monitoring (MBAM) 2.0 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-105">Read these release notes thoroughly before you install Microsoft BitLockerAdministration and Monitoring(MBAM)2.0.</span></span> <span data-ttu-id="ee9a7-106">これらのリリースノートには、BitLockerAdministration と Monitoring 2.0 を正常にインストールするために必要な情報が含まれています。また、製品ドキュメントでは提供されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-106">These release notes contain information that is required to successfully install BitLockerAdministration and Monitoring2.0 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="ee9a7-107">リリースノートとその他の MBAM 2.0 のドキュメントの違いが異なる場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-107">If there is a difference between these release notes and other MBAM2.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="ee9a7-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-known-issues"></a> <span data-ttu-id="ee9a7-109">MBAM 2.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="ee9a7-109">MBAM2.0 Known Issues</span></span>


<span data-ttu-id="ee9a7-110">このセクションには、MBAM 2.0 のリリースノートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-110">This section contains release notes for MBAM2.0.</span></span>

### <span data-ttu-id="ee9a7-111">Microsoft System Center Configuration Manager 2007 で MBAM を実行すると、[コンピューター名] フィールドが BitLocker コンピューターのコンプライアンスおよび BitLocker Enterprise コンプライアンスの詳細レポートに表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="ee9a7-111">Computer Name field may not appear in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007</span></span>

<span data-ttu-id="ee9a7-112">Configuration Manager 2007 で MBAM を使用している場合、[コンピューター名] フィールドは、BitLocker コンピューターのコンプライアンスと BitLocker Enterprise コンプライアンスの詳細レポートで空白になることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-112">The Computer Name field may be blank in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you use MBAM with Configuration Manager 2007.</span></span>

<span data-ttu-id="ee9a7-113">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-113">WORKAROUND: None.</span></span>

### <span data-ttu-id="ee9a7-114">スタンドアロンの MBAM サーバーインフラストラクチャをアップグレードした後、エンタープライズコンプライアンスレポートの更新に失敗する</span><span class="sxs-lookup"><span data-stu-id="ee9a7-114">Enterprise Compliance Report fails to update after you upgrade the Stand-alone MBAM server infrastructure</span></span>

<span data-ttu-id="ee9a7-115">MBAM スタンドアロントポロジを使用していて、サーバーインフラストラクチャをバージョン1.0 から2.0 にアップグレードした場合、エンタープライズコンプライアンスレポートの更新に失敗します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-115">If you are using the MBAM Stand-alone topology, and you upgrade the server infrastructure from version 1.0 to 2.0, the Enterprise Compliance Report fails to update.</span></span>

<span data-ttu-id="ee9a7-116">対応策: アップグレード後に、コンプライアンスと監査データベースに対して次のスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-116">WORKAROUND: After the upgrade, run the following script on the Compliance and Audit Database:</span></span>

```sql
-- =============================================
-- Script Template
-- =============================================

DECLARE @DatabaseName nvarchar(255);
SET @DatabaseName = DB_NAME()

USE msdb;

DECLARE @JobID BINARY(16)
SELECT @JobID = job_id
FROM msdb.dbo.sysjobs
WHERE (name = N'CreateCache')

if (@JobID IS NOT NULL)
BEGIN
    EXEC dbo.sp_delete_job
         @job_name = N'CreateCache';
END

EXEC dbo.sp_add_job
    @job_name = N'CreateCache',
    @enabled = 1;

EXEC dbo.sp_add_jobstep
     @job_name = N'CreateCache',
     @step_name = N'Copy Data',
     @subsystem = N'TSQL',
     @command = N'EXEC [ComplianceCore].UpdateCache',
     @database_name = @DatabaseName,
     @retry_attempts = 5,
     @retry_interval = 5;


EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 010000,
     @active_end_time = 020000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 070000,
     @active_end_time = 080000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 130000,
     @active_end_time = 140000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1pm';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 190000,
     @active_end_time = 200000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7pm';

EXEC dbo.sp_add_jobserver
     @job_name = N'CreateCache';
```

### <span data-ttu-id="ee9a7-117">ヘルプデスクポータルのレポートでは、SSL が SSRS で構成されていない場合は警告が表示される</span><span class="sxs-lookup"><span data-stu-id="ee9a7-117">Reports in the Help Desk Portal display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="ee9a7-118">SQL Server Reporting Services (SSRS) が Secure Socket Layer (SSL) を使用するように構成されていない場合、MBAM サーバーをインストールするときに、レポートの URL は HTTPS ではなく、HTTP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-118">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="ee9a7-119">次に、ヘルプデスクポータルを参照してレポートを選択すると、"セキュリティで保護されたコンテンツのみが表示されます" というメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-119">If you then browse to the Help Desk Portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="ee9a7-120">回避策: レポートを表示するには、[**すべてのコンテンツを表示**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-120">WORKAROUND: To show the report, click **Show All Content**.</span></span> <span data-ttu-id="ee9a7-121">この問題に対処するには、SQL Server Reporting Services がインストールされている MBAM コンピューターにアクセスし、 **Reporting Services 構成マネージャー**を実行してから、[ **WEB サービスの URL**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-121">To address this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="ee9a7-122">サーバーに適切な SSL 証明書を選択し、適切な SSL ポート (既定のポートは 443) を入力して、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-122">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="ee9a7-123">Configuration Manager データベースの既定以外のインスタンスはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ee9a7-123">Non-default instances of the Configuration Manager database are not supported</span></span>

<span data-ttu-id="ee9a7-124">MBAM は、Configuration Manager 2007 と SystemCenter2012 ConfigurationManager の Configuration Manager データベースの既定のインスタンスのみを検索します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-124">MBAM looks only for the default instance of the Configuration Manager database in Configuration Manager 2007 and SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="ee9a7-125">既定以外のインスタンスを使用している場合、MBAM をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-125">If you use a non-default instance, you cannot install MBAM.</span></span>

<span data-ttu-id="ee9a7-126">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-126">WORKAROUND: None.</span></span>

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a><span data-ttu-id="ee9a7-127">コンプライアンスの概要レポートで [戻る] をクリックすると、エラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="ee9a7-127">Clicking “Back” in the Compliance Summary report might throw an error</span></span>

<span data-ttu-id="ee9a7-128">コンプライアンスの概要レポートにドリルダウンして、SSRS レポートの [**戻る**] リンクをクリックすると、エラーがスローされることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-128">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="ee9a7-129">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-129">WORKAROUND: None.</span></span>

### <span data-ttu-id="ee9a7-130">使用領域のみの暗号化が正常に動作しない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-130">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="ee9a7-131">MBAM クライアントをインストールした後で初めてコンピューターを暗号化する場合、使用領域のみの暗号化を実装するグループポリシーオブジェクトを設定していると、MBAM は、ディスクの使用領域だけを暗号化するのではなく、ディスク全体を誤って暗号化します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-131">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="ee9a7-132">MBAM クライアントをインストールするときにコンピューターが既に暗号化されていて、同じグループポリシーオブジェクトを設定している場合、暗号化は正常に動作し、コンピューター上で使用されているディスク領域だけが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-132">If a computer is already encrypted when you install the MBAM Client, and you have set the same Group Policy Object, the encryption works correctly and encrypts only the used disk space on your computer.</span></span>

<span data-ttu-id="ee9a7-133">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="ee9a7-134">コンピューターのコンプライアンスレポートで暗号強度が正しく表示されない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-134">Cipher strength displays incorrectly on the Computer Compliance report</span></span>

<span data-ttu-id="ee9a7-135">**[ドライブの暗号化方法の選択] および [暗号強度**] グループポリシーオブジェクトで特定の暗号強度を設定しなかった場合、暗号強度で既定の128ビット暗号化が使用されている場合でも、構成マネージャーの統合トポロジ内のコンピューターのコンプライアンスレポートでは、暗号強度に対して "unknown" が常に表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-135">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager Integration topology always displays “unknown” for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="ee9a7-136">グループポリシーオブジェクトで特定の暗号強度を設定すると、レポートに正しい暗号強度が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-136">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="ee9a7-137">回避策: **[ドライブの暗号化方法を選択してください] および [暗号強度**] グループポリシーオブジェクトで、常に特定の暗号強度を設定します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-137">WORKAROUND: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="ee9a7-138">ドライブの種類別のコンプライアンスの状態の配布構成項目の更新後に古いデータが表示される</span><span class="sxs-lookup"><span data-stu-id="ee9a7-138">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="ee9a7-139">SystemCenter2012 ConfigurationManager で MBAM 構成項目を更新すると、BitLocker Enterprise コンプライアンスダッシュボードの [コンプライアンスの状態] バーグラフに、古いバージョンの構成項目からの情報を基にしたデータが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-139">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="ee9a7-140">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-140">WORKAROUND: None.</span></span> <span data-ttu-id="ee9a7-141">MBAM 構成項目の変更はサポートされていません。また、レポートは予期したとおりに表示されない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-141">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="ee9a7-142">セキュリティの構成を強化すると、レポートが正しく表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="ee9a7-142">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="ee9a7-143">Internet Explorer の [セキュリティ強化の構成] (ESC) が有効になっている場合、MBAM サーバーでレポートを表示しようとすると、"アクセス拒否" というメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-143">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an “Access Denied” message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="ee9a7-144">既定では、web コンテンツとアプリケーションスクリプトを介して発生する可能性のある攻撃に対してサーバーの脅威が減ることで、サーバーを保護するために ESC が有効になっています。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-144">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="ee9a7-145">回避策: MBAM サーバーでレポートを表示しようとしたときに "アクセス拒否" メッセージが表示される場合は、グループポリシーオブジェクトを設定するか、イメージ内の既定値を手動で変更して、強化されたセキュリティ構成を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-145">WORKAROUND: If the “Access Denied” message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="ee9a7-146">また、ESC が有効になっていない別のコンピューターからレポートを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-146">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="ee9a7-147">SQL Server 2008 から SQL Server 2012 にアップグレードした場合、MBAM サーバーのインストールが失敗する</span><span class="sxs-lookup"><span data-stu-id="ee9a7-147">MBAM Server installation fails when you upgrade from SQL Server 2008 to SQL Server 2012</span></span>

<span data-ttu-id="ee9a7-148">SQL Server 2008 から SQL Server 2012 にアップグレードして、コンプライアンスおよび監査データベースまたは回復データベースをインストールしようとすると、インストールが失敗してロールバックされます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-148">If you upgrade from SQL Server 2008 to SQL Server 2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="ee9a7-149">このエラーは、必要な SQLCMD.exe ファイルが SQL アップグレード中に削除され、MBAM インストーラーで見つからないために発生します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-149">The failure occurs because the required SQLCMD.exe file was removed during the SQL upgrade and cannot be found by the MBAM installer.</span></span> <span data-ttu-id="ee9a7-150">MSI ログファイルの行は、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-150">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="ee9a7-151">RunDbInstallScript 回復データベース CA: BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery データベース ca: dbInstance-xxxxxx\\I01RunDbInstallScript Recovery データベース CA: sqlScript-_Recovery at ¥ \ _and \ _HardwareRunDbInstallScript 回復用データベース CA: defaultFileName-MBAM \ _Recovery \ _and \ _HardwareRunDbInstallScript 回復データベース CA: defaultDataPath-F:\\MSSQL\\MSSQL10. をしてください。I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath-K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01 "" という管理および Monitoring\\ Setup\\ key_and _Recovery recoveryDefaultDataPath \ _Hardware "DefaultFileName =" MBAM \ _Recovery \ _and \ _Hardware "F:\\MSSQL\\MSSQL10. =" (\ \ \ \ "="I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript Recovery Db CA: 回復データベースの実行を開始します。回復用データベースのインストール scriptRunDbInstallScript 回復用データベース ca 例外: 回復用データベースのインストールカスタムアクションコマンドライン出力例外: 指定したファイルが見つからない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-151">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="ee9a7-152">MBAM Server Windows Installer では、HKLM\\Software\\Microsoft\\Microsoft SQL Server ¥¥¥¥¥¥¥¥の [Path 文字列] の値を確認することで、SQLCMD.exe パスをハードコーディングすることができます。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-152">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="ee9a7-153">Sql Server 2008 から SQL Server 2012 への移行中にキーは引き続き存在しますが、SQL アップグレードのプロセスによってファイルが削除されたため、データ値によって参照されるパスに SQLCMD.exe ファイルが含まれていません。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-153">The key is still present during the migration from SQL Server 2008 to SQL Server 2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQL upgrade process removed the file.</span></span>

<span data-ttu-id="ee9a7-154">回避策: HKLM\\Software\\Microsoft\\Microsoft SQL server \\ 100\\ ¥¥の名前を**Path \ _old**に一時的に変更してから、Mbam Server Windows インストーラーを再実行します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-154">WORKAROUND: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path string value to **Path\_old**, and then re-run the MBAM Server Windows Installer.</span></span> <span data-ttu-id="ee9a7-155">インストールが正常に完了し、SQL Server 2012 でデータベースが作成されたら、 **_Old path**の値を**path**に変更します。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-155">When the installation completes successfully and creates the databases in SQL Server 2012, rename the **Path\_old** value to **Path**.</span></span>

## <span data-ttu-id="ee9a7-156">MBAM 2.0 の修正プログラムとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="ee9a7-156">Hotfixes and Knowledge Base articles for MBAM2.0</span></span>


<span data-ttu-id="ee9a7-157">このセクションには、MBAM 2.0 の修正プログラムとサポート技術情報の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee9a7-157">This section contains hotfixes and KB articles for MBAM2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="ee9a7-158">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="ee9a7-158">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="ee9a7-159">タイトル</span><span class="sxs-lookup"><span data-stu-id="ee9a7-159">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="ee9a7-160">リンク</span><span class="sxs-lookup"><span data-stu-id="ee9a7-160">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-161">2831166</span><span class="sxs-lookup"><span data-stu-id="ee9a7-161">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-162">Microsoft BitLocker の管理と監視 (MBAM) 2.0 のインストールで、 &quot; 既にインストールされている System CENTER CM オブジェクトがエラーになる&quot;</span><span class="sxs-lookup"><span data-stu-id="ee9a7-162">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="ee9a7-163">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-163">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-164">2870849</span><span class="sxs-lookup"><span data-stu-id="ee9a7-164">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-165">MBAM 2.0 セルフサービスポータルを使用して、ユーザーが BitLocker 回復キーを取得できない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-165">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="ee9a7-166">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-166">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-167">2756402</span><span class="sxs-lookup"><span data-stu-id="ee9a7-167">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-168">MBAM クライアントでイベント ID 4 およびエラーコード0x8004100E が表示されない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-168">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="ee9a7-169">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-169">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-170">2620287</span><span class="sxs-lookup"><span data-stu-id="ee9a7-170">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-171">MBAM で [レポート] タブをクリックしたときに表示される "/レポート" というエラーメッセージ "サーバーエラー"</span><span class="sxs-lookup"><span data-stu-id="ee9a7-171">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="ee9a7-172">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-172">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-173">2639518</span><span class="sxs-lookup"><span data-stu-id="ee9a7-173">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-174">MBAM で Enterprise またはコンピューターのコンプライアンスレポートを開くときにエラーが発生する</span><span class="sxs-lookup"><span data-stu-id="ee9a7-174">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="ee9a7-175">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-175">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-176">2620269</span><span class="sxs-lookup"><span data-stu-id="ee9a7-176">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-177">MBAM Enterprise レポートが更新されない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-177">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="ee9a7-178">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-178">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-179">2712461</span><span class="sxs-lookup"><span data-stu-id="ee9a7-179">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-180">ドメインコントローラーでの MBAM のインストールはサポートされていません</span><span class="sxs-lookup"><span data-stu-id="ee9a7-180">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="ee9a7-181">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-181">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-182">2876732</span><span class="sxs-lookup"><span data-stu-id="ee9a7-182">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-183">MBAM 2.0 の単体または Configuration Manager の統合セットアップ中にエラーコード0x80071a90 が表示される</span><span class="sxs-lookup"><span data-stu-id="ee9a7-183">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="ee9a7-184">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-184">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-185">2754259</span><span class="sxs-lookup"><span data-stu-id="ee9a7-185">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-186">MBAM とセキュリティで保護されたネットワーク通信</span><span class="sxs-lookup"><span data-stu-id="ee9a7-186">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="ee9a7-187">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-187">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-188">2870842</span><span class="sxs-lookup"><span data-stu-id="ee9a7-188">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-189">SQL Server 2008 での Configuration Manager の統合シナリオ中に MBAM 2.0 セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="ee9a7-189">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="ee9a7-190">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-190">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-191">2668533</span><span class="sxs-lookup"><span data-stu-id="ee9a7-191">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-192">SQL SSRS が適切に構成されていない場合、MBAM セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="ee9a7-192">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="ee9a7-193">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-193">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-194">2870847</span><span class="sxs-lookup"><span data-stu-id="ee9a7-194">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-195">MBAM 2.0 のセットアップで &quot; &#39;Reporting Services ポイント&#39; ロールの Configuration Manager サーバーの役割設定を取得するときにエラーが発生する&quot;</span><span class="sxs-lookup"><span data-stu-id="ee9a7-195">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="ee9a7-196">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-196">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-197">2870839</span><span class="sxs-lookup"><span data-stu-id="ee9a7-197">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-198">Mbam 2.0 Enterprise レポートが、SQL ジョブ CreateCache エラーのために MBAM 2.0 スタンドアロントポロジで更新されない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-198">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="ee9a7-199">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-199">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-200">2620269</span><span class="sxs-lookup"><span data-stu-id="ee9a7-200">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-201">MBAM Enterprise レポートが更新されない</span><span class="sxs-lookup"><span data-stu-id="ee9a7-201">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="ee9a7-202">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-202">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ee9a7-203">2935997</span><span class="sxs-lookup"><span data-stu-id="ee9a7-203">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-204">MBAM サポートされているコンピューターのコンプライアンスレポートにサポートされない製品が含まれている</span><span class="sxs-lookup"><span data-stu-id="ee9a7-204">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="ee9a7-205">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-205">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ee9a7-206">2612822</span><span class="sxs-lookup"><span data-stu-id="ee9a7-206">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="ee9a7-207">MBAM でコンピューターレコードが拒否される</span><span class="sxs-lookup"><span data-stu-id="ee9a7-207">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="ee9a7-208">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="ee9a7-208">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ee9a7-209">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ee9a7-209">Related topics</span></span>


[<span data-ttu-id="ee9a7-210">MBAM 2.0 の概要</span><span class="sxs-lookup"><span data-stu-id="ee9a7-210">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

 

 





