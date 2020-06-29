---
title: MBAM 2.5 のインストールに関する問題のトラブルシューティング
description: MBAM 2.5 のインストールに関する問題のトラブルシューティングを行う方法について説明します。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812866"
---
# <span data-ttu-id="27fbd-103">MBAM 2.5 のインストールに関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="27fbd-103">Troubleshooting MBAM 2.5 installation problems</span></span>

<span data-ttu-id="27fbd-104">この記事では、スタンドアロン構成での Microsoft BitLocker 管理および監視 (MBAM) 2.5 インストールの問題のトラブルシューティング方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-104">This article introduces how to troubleshoot Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 installation issues in a standalone configuration.</span></span>

## <span data-ttu-id="27fbd-105">トラブルシューティング用の MBAM ログファイルの参照</span><span class="sxs-lookup"><span data-stu-id="27fbd-105">Referring MBAM log files for troubleshooting</span></span>

<span data-ttu-id="27fbd-106">MBAM サーバーのインストール、クライアントのインストール、イベントのログが含まれます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-106">MBAM includes logging for server installation, client installation, and events.</span></span> <span data-ttu-id="27fbd-107">このログは、トラブルシューティングのために参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-107">This logging should be referred to for troubleshooting.</span></span> 
 
### <span data-ttu-id="27fbd-108">MBAM サーバーインストールログファイル</span><span class="sxs-lookup"><span data-stu-id="27fbd-108">MBAM server installation log files</span></span>

<span data-ttu-id="27fbd-109">MBAMServerSetup.exe は、MBAM のインストール中に、ユーザーの% temp% フォルダーに次のログファイルを生成します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-109">MBAMServerSetup.exe generates the following log files in the user’s %temp% folder during MBAM installation:</span></span><br /> **<span data-ttu-id="27fbd-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 番号> .log</span><span class="sxs-lookup"><span data-stu-id="27fbd-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 numbers>.log</span></span>**

<span data-ttu-id="27fbd-111">MBAMServerSetup.exe は、MBAM セットアップおよび MBAM サーバー機能のインストール時に実行された操作をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-111">MBAMServerSetup.exe logs the actions that were taken during MBAM setup and MBAM server feature installation:</span></span><br /> **<span data-ttu-id="27fbd-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi</span><span class="sxs-lookup"><span data-stu-id="27fbd-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log</span></span>**

<span data-ttu-id="27fbd-113">MBAMServerSetup.exe、インストール中に実行されたその他の操作を記録します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-113">MBAMServerSetup.exe logs additional actions that were taken during installation.</span></span>

### <span data-ttu-id="27fbd-114">MBAM クライアントインストールログファイル</span><span class="sxs-lookup"><span data-stu-id="27fbd-114">MBAM client installation log file</span></span>

<span data-ttu-id="27fbd-115">クライアントのインストールは、% temp% フォルダーの次のログファイル (またはクライアントのインストール方法に応じて、カスタムの場所) に記録されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-115">The client installation is recorded in the following log file in the %temp% folder (or a custom location, depending on how the client was installed):</span></span> <br />**<span data-ttu-id="27fbd-116">MSI.DLL \<five random characters\></span><span class="sxs-lookup"><span data-stu-id="27fbd-116">MSI\<five random characters\>.log</span></span>**

<span data-ttu-id="27fbd-117">このログには、MBAM クライアントのインストール中に実行されるアクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-117">This log contains the actions that are taken during MBAM client installation.</span></span>
 
### <span data-ttu-id="27fbd-118">MBAM クライアントイベント-ログチャネル</span><span class="sxs-lookup"><span data-stu-id="27fbd-118">MBAM client event-logging channel</span></span>

<span data-ttu-id="27fbd-119">MBAM には、個別のイベントログチャネルがあります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-119">MBAM has separate event-logging channels.</span></span> <span data-ttu-id="27fbd-120">管理、分析、オペレーションの各ログファイルは、イベントビューアーの [**アプリケーションとサービスログ**] にあり  >  **Microsoft**  >  ます。 Microsoft**Windows**  >  **mbam**。</span><span class="sxs-lookup"><span data-stu-id="27fbd-120">The Admin, Analytical, and Operational log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span>

<span data-ttu-id="27fbd-121">次の表では、各イベントログについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-121">The following table provides a brief description of each event log.</span></span>
 
|<span data-ttu-id="27fbd-122">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="27fbd-122">Event log</span></span>| <span data-ttu-id="27fbd-123">説明</span><span class="sxs-lookup"><span data-stu-id="27fbd-123">Description</span></span>|
|----------|-------|
|<span data-ttu-id="27fbd-124">Microsoft-Windows-MBAM/Admin</span><span class="sxs-lookup"><span data-stu-id="27fbd-124">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="27fbd-125">エラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="27fbd-125">Contains error messages</span></span>|
|<span data-ttu-id="27fbd-126">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="27fbd-126">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="27fbd-127">詳細なログ情報が含まれています</span><span class="sxs-lookup"><span data-stu-id="27fbd-127">Contains advanced logging information</span></span>|
|<span data-ttu-id="27fbd-128">Microsoft-Windows-MBAM/Operational</span><span class="sxs-lookup"><span data-stu-id="27fbd-128">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="27fbd-129">成功メッセージを含む</span><span class="sxs-lookup"><span data-stu-id="27fbd-129">Contains success messages</span></span>|

### <span data-ttu-id="27fbd-130">MBAM サーバーイベント-ログチャネル</span><span class="sxs-lookup"><span data-stu-id="27fbd-130">MBAM server event-logging channel</span></span>

<span data-ttu-id="27fbd-131">ログファイルは、イベントビューアーの [**アプリケーションとサービス**] の下にある [  >  **Microsoft**  >  **Windows**  >  **mbam**] をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-131">The log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span> <span data-ttu-id="27fbd-132">次の表は、MBAM 2.5 で導入されたサーバーイベントログを示しています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-132">The following table includes server event logs that were introduced in MBAM 2.5:</span></span>

|<span data-ttu-id="27fbd-133">イベント ログ</span><span class="sxs-lookup"><span data-stu-id="27fbd-133">Event log</span></span>| <span data-ttu-id="27fbd-134">説明</span><span class="sxs-lookup"><span data-stu-id="27fbd-134">Description</span></span>|
|--------|-------------|
|<span data-ttu-id="27fbd-135">Microsoft-Windows-MBAM/Admin</span><span class="sxs-lookup"><span data-stu-id="27fbd-135">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="27fbd-136">エラーメッセージが表示される</span><span class="sxs-lookup"><span data-stu-id="27fbd-136">Contains error messages</span></span>|
|<span data-ttu-id="27fbd-137">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="27fbd-137">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="27fbd-138">詳細なログ情報が含まれています</span><span class="sxs-lookup"><span data-stu-id="27fbd-138">Contains advanced logging information</span></span>|
|<span data-ttu-id="27fbd-139">Microsoft-Windows-MBAM/Operational</span><span class="sxs-lookup"><span data-stu-id="27fbd-139">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="27fbd-140">成功メッセージを含む</span><span class="sxs-lookup"><span data-stu-id="27fbd-140">Contains success messages</span></span>|

### <span data-ttu-id="27fbd-141">MBAM web サービスログ</span><span class="sxs-lookup"><span data-stu-id="27fbd-141">MBAM web service logs</span></span>

<span data-ttu-id="27fbd-142">各 MBAM web サービスログは、ログ情報を SVCLOG ファイルに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-142">Each MBAM web service log writes logging information to an SVCLOG file.</span></span> <span data-ttu-id="27fbd-143">既定では、各 web サービスは、C:\inetpub\Microsoft BitLocker 管理 Solution\Logs フォルダーでその名前を使用するフォルダーの下にトレースファイルを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-143">By default, each web service writes the trace file under a folder that uses its name in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span>

<span data-ttu-id="27fbd-144">サービストレースビューアーツール (Microsoft Visual Studio の一部) を使うと、svclog トレースを確認できます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-144">You can use the service trace viewer tool (part of Microsoft Visual Studio) to review the svclog traces.</span></span>

## <span data-ttu-id="27fbd-145">暗号化と報告に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="27fbd-145">Troubleshooting encryption and reporting issues</span></span>

<span data-ttu-id="27fbd-146">このセクションには、サーバー機能、クライアント機能、構成設定、既知の問題に関するトラブルシューティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-146">This section contains troubleshooting information for server functionality, client functionality, configuration settings, and known issues:</span></span>
 
### <span data-ttu-id="27fbd-147">MBAM クライアントのインストール、グループポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="27fbd-147">MBAM client installation, Group Policy settings</span></span>

<span data-ttu-id="27fbd-148">クライアントコンピューターに MBAM エージェントがインストールされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-148">Determine whether the MBAM agent is installed on the client computer.</span></span> <span data-ttu-id="27fbd-149">MBAM をインストールすると、[BitLocker 管理クライアントサービス] という名前のサービスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-149">When MBAM is installed, it creates a service that is named BitLocker Management Client Service.</span></span> <span data-ttu-id="27fbd-150">このサービスは、自動的に開始するように構成されています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-150">This service is configured to start automatically.</span></span> <span data-ttu-id="27fbd-151">サービスが実行されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-151">Determine whether the service is running.</span></span>

<span data-ttu-id="27fbd-152">クライアントコンピューターに MBAM グループポリシー設定が適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-152">Make sure that MBAM Group Policy settings are applied on the client computer.</span></span> <span data-ttu-id="27fbd-153">クライアントコンピューターにグループポリシー設定が適用されている場合は、次のレジストリサブキーが作成されます。 **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**</span><span class="sxs-lookup"><span data-stu-id="27fbd-153">The following registry subkey is created if the Group Policy settings were applied on the client computer: **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**</span></span>

<span data-ttu-id="27fbd-154">このキーが存在し、グループポリシー設定ごとの値を使用して設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-154">Verify that this key exists and is populated by using values per Group Policy settings.</span></span>

### <span data-ttu-id="27fbd-155">最初の遅延期間の MBAM エージェント</span><span class="sxs-lookup"><span data-stu-id="27fbd-155">MBAM Agent in the initial delay period</span></span>

<span data-ttu-id="27fbd-156">MBAM クライアントでは、インストール後すぐに操作を開始することはできません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-156">The MBAM client doesn't start the operation immediately after installation.</span></span> <span data-ttu-id="27fbd-157">MBAM エージェントが操作を開始する前の初回ランダム遅延は 1 ~ 18 分です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-157">There is an initial random delay of 1–18 minutes before the MBAM Agent starts its operation.</span></span> <span data-ttu-id="27fbd-158">最初の遅延に加えて、少なくとも90分の遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-158">In addition to the initial delay, there is a delay of at least 90 minutes.</span></span> <span data-ttu-id="27fbd-159">(遅延時間は、クライアントの状態を確認する頻度に対して構成されているグループポリシー設定によって異なります)。したがって、クライアントが操作を開始するまでの合計遅延時間は、*ランダムな起動遅延*  +  *クライアントチェック頻度の遅延*です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-159">(The delay depends on the Group Policy settings that are configured for the frequency of checking the client status.) Therefore, the total delay before a client starts operation is *random startup delay* + *client checking frequency delay*.</span></span>

<span data-ttu-id="27fbd-160">Operational イベントログと管理イベントログが空白の場合、クライアントはまだ操作を開始せず、前に説明した遅延期間中です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-160">If the Operational and Admin event logs are blank, the client has not started the operation yet and is in the delay period that was mentioned earlier.</span></span> <span data-ttu-id="27fbd-161">遅延を回避するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-161">If you want to bypass the delay, follow these steps:</span></span>
 
1. <span data-ttu-id="27fbd-162">BitLocker 管理クライアントサービスサービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-162">Stop the BitLocker Management Client Service service.</span></span>

2. <span data-ttu-id="27fbd-163">**HKEY_LOCAL_MACHINE \software\microsoft\mbam** registry サブキーの下で、 **nostartupdelay**レジストリ値を作成し、その型を [ **REG_DWORD**] に設定して、その値を**1**に設定します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-163">Under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM** registry subkey, create the **NoStartupDelay** registry value, set its type to **REG_DWORD**, and then set its value to **1**.</span></span>

3. <span data-ttu-id="27fbd-164">[ **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**で、 **ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に設定します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-164">Under **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**, set the **ClientWakeupFrequency** and **StatusReportingFrequency** values to **1**.</span></span> <span data-ttu-id="27fbd-165">グループポリシーの更新がコンピューターにあると、これらの値は元の設定に戻ります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-165">These values will revert to their original settings after Group Policy updates are on the computer.</span></span>

4. <span data-ttu-id="27fbd-166">BitLocker 管理クライアントサービスサービスを開始します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-166">Start the BitLocker Management Client Service service.</span></span>

<span data-ttu-id="27fbd-167">サービスが開始された後、コンピューターにローカルにログインし、エラーがない場合は、1分以内にコンピューターを暗号化するように求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-167">After the service starts, if you log in locally on the computer and there are no errors, you should receive a request to encrypt the computer within one minute.</span></span> <span data-ttu-id="27fbd-168">要求を受信しない場合は、すべてのエラーエントリについて MBAM 管理ログを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-168">If you do not receive a request, you should review the MBAM Admin logs for any error entries.</span></span>

### <span data-ttu-id="27fbd-169">コンピューターに TPM デバイスがないか、BIOS で TPM デバイスが有効になっていません</span><span class="sxs-lookup"><span data-stu-id="27fbd-169">Computer does not have a TPM device, or the TPM device is not enabled in the BIOS</span></span>

<span data-ttu-id="27fbd-170">MBAM 管理イベントログを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-170">Review the MBAM Admin event log.</span></span> <span data-ttu-id="27fbd-171">MBAM 管理イベントログには、次のようなイベントエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-171">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

<span data-ttu-id="27fbd-172">TPM 管理 (tpm) を開いて、コンピューターに TPM デバイスがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-172">Open TPM Management (tpm.msc), and check whether the computer has a TPM device.</span></span> <span data-ttu-id="27fbd-173">Tpm にデバイスが表示されない場合は、デバイスマネージャー (devmgmt) を開いて、[セキュリティデバイス] の下にトラステッドプラットフォームモジュールがあるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-173">If tpm.msc does not show a device, open Device Manager (devmgmt.msc), and check for a Trusted Platform Module under Security Devices.</span></span> <span data-ttu-id="27fbd-174">トラステッドプラットフォームモジュールデバイスが表示されない場合は、次のいずれかの理由で該当する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-174">If you do not see a Trusted Platform Module device, this might be true for one of the following reasons:</span></span>

* <span data-ttu-id="27fbd-175">お使いのシステムには、トラステッドプラットフォームモジュール (TPM/セキュリティ) デバイスがありません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-175">Your system doesn't have a Trusted Platform Module (TPM/Security) device.</span></span>

* <span data-ttu-id="27fbd-176">TPM デバイスが BIOS で無効にされています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-176">The TPM device is disabled in the BIOS.</span></span>

* <span data-ttu-id="27fbd-177">BIOS で TPM デバイスが有効になっていますが、BIOS でオペレーティングシステム設定からの TPM デバイスの管理が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-177">TPM Device is enabled in the BIOS, but management of the TPM device from the operating system setting is disabled in the BIOS.</span></span>

* <span data-ttu-id="27fbd-178">TPM デバイス用の Microsoft ドライバーを使用していない。</span><span class="sxs-lookup"><span data-stu-id="27fbd-178">You aren't using a Microsoft driver for the TPM device.</span></span> <span data-ttu-id="27fbd-179">デバイスマネージャーに表示されているデバイスを確認して、Microsoft TPM デバイスドライバーを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-179">Review the devices that are listed in device manager to identify the Microsoft TPM device driver.</span></span>

<span data-ttu-id="27fbd-180">TPM デバイスで C:\Windows\System32\tpm.sys ドライバーを使用していない場合は、C:\Windows\Inf\tpm.inf ファイルを選択してドライバーを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-180">If the TPM device is not using the C:\Windows\System32\tpm.sys driver, you should update the driver by selecting the C:\Windows\Inf\tpm.inf file.</span></span>

### <span data-ttu-id="27fbd-181">コンピューターに有効なシステムパーティションがありません</span><span class="sxs-lookup"><span data-stu-id="27fbd-181">Computer does not have a valid SYSTEM partition</span></span>

<span data-ttu-id="27fbd-182">MBAM 管理イベントログを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-182">Review the MBAM Admin event log.</span></span> <span data-ttu-id="27fbd-183">MBAM 管理イベントログには、次のようなイベントエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-183">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

<span data-ttu-id="27fbd-184">BitLocker で暗号化を有効にするには、システムパーティションが必要です ([Windows 7 では、Bitlocker ドライブ暗号化](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)を有効にする方法についてよく寄せられる質問)。</span><span class="sxs-lookup"><span data-stu-id="27fbd-184">BitLocker requires a SYSTEM partition to enable encryption ([BitLocker Drive Encryption in Windows 7: Frequently Asked Questions](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)).</span></span>

<span data-ttu-id="27fbd-185">MBAM システムパーティションは自動的には作成されません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-185">MBAM doesn't create the system partition automatically.</span></span> <span data-ttu-id="27fbd-186">BitLocker ドライブ準備ユーティリティ (bdehdcfg.exe) を使用して、システムパーティションを作成し、必要なスタートアップファイルを移動することができます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-186">You can use the BitLocker drive preparation utility (bdehdcfg.exe) to create the system partition and move the required startup files.</span></span>

<span data-ttu-id="27fbd-187">たとえば、コマンド **% windir% \system32\bdeHdCfg.exe (ターゲットの既定サイズの300– quiet** ) を使うと、mbam を展開してドライブを暗号化する前に、ドライブをサイレントモードで準備することができます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-187">For example, you can use the command **%windir%\system32\bdeHdCfg.exe -target default -size 300 –quiet** to prepare the drive silently before you deploy MBAM to encrypt the drives.</span></span> <span data-ttu-id="27fbd-188">これには再起動が必要です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-188">This requires a restart.</span></span> <span data-ttu-id="27fbd-189">必要に応じて、アクションのスクリプトを作成することもできます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-189">You can also script the action if this is required.</span></span> <span data-ttu-id="27fbd-190">次のドキュメントでは、BitLocker ドライブ準備ツールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-190">The following document describes the BitLocker Drive Preparation Tool:</span></span>

[<span data-ttu-id="27fbd-191">BitLocker ドライブ準備ツールの説明</span><span class="sxs-lookup"><span data-stu-id="27fbd-191">Description of the BitLocker Drive Preparation Tool</span></span>](https://support.microsoft.com/help/933246)

### <span data-ttu-id="27fbd-192">ドライブは互換性のあるファイルシステムを持つように書式設定されていない</span><span class="sxs-lookup"><span data-stu-id="27fbd-192">Drives are not formatted to have a compatible file system</span></span>

<span data-ttu-id="27fbd-193">[BitLocker のファイルシステム要件につい](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)ては、TechNet の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-193">See the [TechNet article for file system requirements for BitLocker](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements).</span></span>

### <span data-ttu-id="27fbd-194">グループポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="27fbd-194">Group Policy conflict</span></span>

<span data-ttu-id="27fbd-195">MBAM 管理イベントログには、次のようなイベントエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-195">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

<span data-ttu-id="27fbd-196">グループポリシー設定を確認して、MBAM グループポリシー設定の間に競合している設定がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-196">Verify your Group Policy settings to make sure that you do not have a conflicting setting among the MBAM Group Policy settings.</span></span>

<span data-ttu-id="27fbd-197">グループポリシーは、MDOP MBAM テンプレートではなく、MDOP MBAM テンプレートを使って構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-197">You should configure Group Policy by using the MDOP MBAM template and not the BitLocker Drive Encryption template.</span></span>

<span data-ttu-id="27fbd-198">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-198">For example:</span></span>

<span data-ttu-id="27fbd-199">[オペレーティングシステムドライブの暗号化設定] で、プロテクターとして TPM を選択し、[**スタートアップの拡張 pin を許可**する] も選択しました。</span><span class="sxs-lookup"><span data-stu-id="27fbd-199">Under Operating system drive encryption settings, you selected TPM as the protector, and you also selected **Allow enhanced PINs for startup**.</span></span> <span data-ttu-id="27fbd-200">TPM のみの保護で PIN が必要にならないため、これらは設定が競合しています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-200">These are conflicting settings because TPM-only protection doesn't require a PIN.</span></span> <span data-ttu-id="27fbd-201">そのため、拡張ピンの設定を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-201">Therefore, you should disable the enhanced PINs setting.</span></span>

### <span data-ttu-id="27fbd-202">ユーザーが除外を要求した可能性があります</span><span class="sxs-lookup"><span data-stu-id="27fbd-202">User may have requested an exemption</span></span>

<span data-ttu-id="27fbd-203">コンピューターの構成機能 \ Components\MDOP MBAM (BitLocker 管理) \ Client Management \ ユーザーの免税ポリシーのグループポリシー設定を有効にした場合、除外を要求するオプションがユーザーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-203">If you enabled the Computer Configuration\Administrative Templates\Windows Components\MDOP MBAM (BitLocker Management)\Client Management\Configure user exemption policy Group Policy setting, users will be offered the option to request an exemption.</span></span>

<span data-ttu-id="27fbd-204">既定では、ユーザーが除外を要求した場合、除外は7日間有効になり、その間、ユーザーは暗号化の確認メッセージを受信しません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-204">By default, if the user requests an exemption, the exemption will be valid for 7 days, and the user will not receive prompts to encrypt during this period.</span></span> <span data-ttu-id="27fbd-205">(ポリシー構成中は既定値を増減できます)。除外期間が終了すると、ユーザーに暗号化の確認を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-205">(The default value can be increased or decreased during policy configuration.) After the exemption period is over, the user is prompted to encrypt.</span></span>

<span data-ttu-id="27fbd-206">コンピューターがユーザーの例外の対象になっている場合、MBAM 管理イベントログに次のエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-206">You will see the following entry in the MBAM Admin event log when a computer is under user exemption:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

<span data-ttu-id="27fbd-207">コンピューターのユーザーの除外を手動で無効にする場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-207">If you want to manually override user exemption for a computer, follow these steps:</span></span>
 
1. <span data-ttu-id="27fbd-208">次のレジストリサブキーで AllowUserExemption 値を**0**に設定します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-208">Set the AllowUserExemption value to **0** under the following registry subkey:</span></span> <br />
**<span data-ttu-id="27fbd-209">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="27fbd-209">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

2. <span data-ttu-id="27fbd-210">**Agentversion**、**エンコード Computername**、**インストールされている**ものを除き、次のレジストリサブキーの下にあるすべてのレジストリ値を削除します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-210">Delete all the registry values under the following registry subkey except for **AgentVersion**, **EncodedComputerName**, and **Installed**:</span></span><br />
**<span data-ttu-id="27fbd-211">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM</span><span class="sxs-lookup"><span data-stu-id="27fbd-211">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM</span></span>**

    <span data-ttu-id="27fbd-212">**注**変更を有効にするには、MBAM agent を再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-212">**Note** You must restart the MBAM agent for the changes to take effect.</span></span>

<span data-ttu-id="27fbd-213">コンピューターにグループポリシーを適用すると、これらの値が元の設定に戻る場合があることに注意してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-213">Be aware that after you apply Group Policy to the computer, these values may revert to their original settings.</span></span>

### <span data-ttu-id="27fbd-214">WMI の問題</span><span class="sxs-lookup"><span data-stu-id="27fbd-214">WMI issue</span></span>

<span data-ttu-id="27fbd-215">MBAM は、win32_encryptablevolume クラスのメソッドを使用して BitLocker を管理します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-215">MBAM uses methods of the win32_encryptablevolume class to manage BitLocker.</span></span> <span data-ttu-id="27fbd-216">このモジュールが登録されていないか破損している場合、MBAM クライアントは正しく動作しません。また、MBAM 管理イベントログに次のイベントエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-216">If this module is unregistered or corrupted, the MBAM client will not operate correctly, and you will see the following event entry in the MBAM Admin event log:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

<span data-ttu-id="27fbd-217">また、エラーコード0x8007007e で、回復とハードウェアのポリシーが適用されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-217">Additionally, you may notice that the Recovery and Hardware policies do not apply with Error Code 0x8007007e.</span></span> <span data-ttu-id="27fbd-218">これは、"指定されたモジュールが見つかりませんでした。" という意味です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-218">This translates to "The specified module could not be found."</span></span>

<span data-ttu-id="27fbd-219">この問題を解決するには、次のコマンドを使用して**win32_encryptablevolume**クラスを登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-219">To resolve this issue, you should reregister the **win32_encryptablevolume** class by using the following command:</span></span>

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <span data-ttu-id="27fbd-220">MBAM エージェントの通信に関する問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="27fbd-220">Troubleshooting MBAM Agent communication issues</span></span>

<span data-ttu-id="27fbd-221">このセクションには、MBAM エージェントの通信に関連する次の問題に関するトラブルシューティング情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-221">This section contains troubleshooting information for the following issues that are related to MBAM agent communication:</span></span>

### <span data-ttu-id="27fbd-222">MBAM サービスの URL が正しくありません</span><span class="sxs-lookup"><span data-stu-id="27fbd-222">Incorrect MBAM service URL</span></span>

<span data-ttu-id="27fbd-223">MBAM コンプライアンス状態のサービスまたは回復とハードウェアサービスの値が正しくない場合は、クライアントコンピューターの MBAM 管理イベントログに次のようなイベントエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-223">If the value of MBAM Compliance Status Service or Recovery and Hardware Service is incorrect, you'll see an event entry that resembles the following in the MBAM Admin event log on the client computer:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

<span data-ttu-id="27fbd-224">クライアントコンピューターの次のレジストリサブキーの下にある**Keyrecoveryserviceendpoint**と**statusreportingserviceendpoint**の値を確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-224">Verify the values of **KeyRecoveryServiceEndPoint** and **StatusReportingServiceEndpoint** under the following registry subkey on the client computer:</span></span> <br />
**<span data-ttu-id="27fbd-225">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="27fbd-225">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

<span data-ttu-id="27fbd-226">既定では、KeyRecoveryServiceEndPoint (MBAM Recovery および Hardware service endpoint) の URL は、次の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-226">By default, the URL for KeyRecoveryServiceEndPoint (MBAM Recovery and Hardware service endpoint) is in the following format:</span></span> <br />
**<span data-ttu-id="27fbd-227">http:// \<servername\> : \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="27fbd-227">http://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>**

<span data-ttu-id="27fbd-228">既定では、StatusReportingServiceEndpoint (MBAM Status reporting service エンドポイント) の URL は、次の形式になっています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-228">By default, the URL for StatusReportingServiceEndpoint (MBAM Status reporting service endpoint) is in the following format:</span></span><br />
**<span data-ttu-id="27fbd-229">http:// \<servername\> : \<port\> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="27fbd-229">http://\<servername\>:\<port\>/MBAMComplianceStatusService/StatusReportingService.svc</span></span>**

> [!Note]
> <span data-ttu-id="27fbd-230">URL にスペースを含めないでください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-230">There should be no spaces in the URL.</span></span>

<span data-ttu-id="27fbd-231">サービスの URL が正しくない場合は、次のグループポリシー設定でサービス URL を修正する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-231">If the service URL is incorrect, you should correct the service URL in the following Group Policy setting:</span></span>

<span data-ttu-id="27fbd-232">**コンピューターの構成**  > **ポリシー**  > **管理用テンプレート**  > **Windows コンポーネント**  > **MDOP MBAM (BitLocker 管理)**  > **クライアント管理**  > **MBAM サービスを設定する**</span><span class="sxs-lookup"><span data-stu-id="27fbd-232">**Computer configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDOP MBAM (BitLocker Management)** > **Client Management** > **Configure MBAM Services**</span></span>

### <span data-ttu-id="27fbd-233">MBAM 管理サーバーに影響を与える接続の問題</span><span class="sxs-lookup"><span data-stu-id="27fbd-233">Connectivity issue that affects the MBAM administration server</span></span>

<span data-ttu-id="27fbd-234">クライアントエージェントと MBAM 管理サーバーの間に接続の問題がある場合、MBAM agent はデータベースへの更新を投稿できません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-234">The MBAM agent will be unable to post any updates to the database if connectivity issues exist between the client agent and the MBAM administration server.</span></span> <span data-ttu-id="27fbd-235">この場合、クライアントコンピューターの MBAM 管理イベントログに接続エラーのエントリが表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-235">In this case, you will notice connectivity failure entries in the MBAM Admin event log on the client computer:</span></span>

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

<span data-ttu-id="27fbd-236">基本的なチェック:</span><span class="sxs-lookup"><span data-stu-id="27fbd-236">Basic checks:</span></span>

* <span data-ttu-id="27fbd-237">名前と IP で MBAM 管理サーバーに ping を行って、基本的な接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-237">Verify basic connectivity by pinging the MBAM administration server by name and IP.</span></span> <span data-ttu-id="27fbd-238">Telnet または portqry を使って、MBAM 管理 web サイトまたはサービスポートに接続できるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-238">Check whether you can connect to the MBAM administration website or service port by using telnet or portqry.</span></span>

* <span data-ttu-id="27fbd-239">MBAM 管理および監視サーバーで IIS サービスが実行されていること、および MBAM web サービスが MBAM クライアントコンピューター () で構成されている同じポートでリッスンしていることを確認し `netstat –ano | find "portnumber"` ます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-239">Verify that the IIS service is running on the MBAM administration and monitoring server and that the MBAM web service is listening on the same port that is configured on the MBAM client computer (`netstat –ano | find "portnumber"`).</span></span>

* <span data-ttu-id="27fbd-240">MBAM web サイト用に構成されているポート番号が IIS Manager (inetmgr) を使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-240">Verify that the port number that is configured for the MBAM website is using IIS Manager (inetmgr).</span></span> <span data-ttu-id="27fbd-241">ポート番号がクライアントがリッスンしているポート番号と同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-241">Make sure that the port number is the same as the port number on which the client is listening.</span></span> <span data-ttu-id="27fbd-242">ポート番号が別のアプリケーションによって共有されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-242">Make sure that the port number is not shared by another application.</span></span> <span data-ttu-id="27fbd-243">たとえば、サーバー上の別のアプリケーションでは、同じポートを使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="27fbd-243">For example, another application on the server should not be using the same port.</span></span>

* <span data-ttu-id="27fbd-244">ファイアウォールがある場合は、ファイアウォールまたはプロキシサーバーでポートが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-244">If there is a firewall, make sure that the port is open in the firewall or proxy server.</span></span>

* <span data-ttu-id="27fbd-245">クライアントとサーバーの間の通信がセキュリティで保護されている場合は、有効な SSL 証明書を使用していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-245">If the communication between client and server is secure, make sure that you are using a valid SSL certificate.</span></span>

* <span data-ttu-id="27fbd-246">Web サーバーと、データを挿入するために送信するデータベースサーバーとの間のネットワーク接続を確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-246">Verify network connectivity between the web server and the database server to which the data is sent for insertion.</span></span> <span data-ttu-id="27fbd-247">ODBC データソース管理を使用して、web サーバーからデータベースサーバーへのデータベース接続を確認できます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-247">You can check database connectivity from the web server to the database server by using ODBC Data Source Administrator.</span></span> <span data-ttu-id="27fbd-248">Sql server の接続のトラブルシューティング情報につい[ては、「Sql Server データベースエンジンへの接続に関するトラブルシューティング」を](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-248">Detailed SQL Server connection troubleshooting information is available in [How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx).</span></span>

#### <span data-ttu-id="27fbd-249">接続の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="27fbd-249">Troubleshooting the connectivity issue</span></span>

<span data-ttu-id="27fbd-250">クライアントで構成されているサービスの URL が正しいことを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-250">Make sure that the service URL that is configured on the client is correct.</span></span> <span data-ttu-id="27fbd-251">レジストリから KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**) の URL の値をコピーして、Internet Explorer で開きます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-251">Copy the value of the URL for KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**) from the registry, and open it in Internet Explorer.</span></span>

<span data-ttu-id="27fbd-252">同様に、StatusReportingServiceEndpoint の URL の値 (**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**) をコピーして、Internet Explorer で開きます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-252">Similarly, copy the value of the URL for StatusReportingServiceEndpoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**), and open it in Internet Explorer.</span></span>

> [!Note]
> <span data-ttu-id="27fbd-253">クライアントコンピューターから URL を参照できない場合は、クライアントから IIS を実行しているサーバーへの基本的なネットワーク接続をテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-253">If you cannot browse to the URL from the client computer, you should test basic network connectivity from the client to the server that is running IIS.</span></span> <span data-ttu-id="27fbd-254">前のセクションの「1、2、3、4」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-254">See points 1, 2, 3, and 4 in the previous section.</span></span>

<span data-ttu-id="27fbd-255">さらに、管理および監視サーバーのアプリケーションログでエラーを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-255">Additionally, review the Application logs on the administration and monitoring server for any errors.</span></span>

<span data-ttu-id="27fbd-256">クライアントとサーバー間のネットワークトレースを同時に行うことができます。トレースを確認して、クライアントエージェントと MBAM 管理サーバー間の接続エラーの原因を特定します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-256">You can make a concurrent network trace between the client and the server, and review the trace to determine the cause of connection failure between the client agent and the MBAM administration server.</span></span>

> [!Note]
> <span data-ttu-id="27fbd-257">クライアントコンピューターからサービス Url を参照できるが、MBAM 管理イベントログに接続エラーエントリがある場合は、管理サーバーとデータベースサーバーの間の接続エラーが原因である可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-257">If you can browse to the service URLs from the client computer and there are connectivity error entries in the MBAM admin event logs, this might be because of a connectivity failure between the administration server and the database server.</span></span>

<span data-ttu-id="27fbd-258">両方のサービス Url に正常にアクセスでき、クライアントと実行されているサーバーの間に接続がある場合は、IIS が動作しています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-258">If you can successfully browse to both service URLs, and there is connectivity between the client and the server that is running, IIS is working.</span></span> <span data-ttu-id="27fbd-259">ただし、IIS を実行しているサーバーとデータベースサーバーの間の通信に問題がある可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-259">However, there may be a problem in communication between the server that is running IIS and the database server.</span></span>

<span data-ttu-id="27fbd-260">ネットワークの問題またはデータベース接続文字列の設定が正しくないため、MBAM サービスがデータベースサーバーに接続できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-260">The MBAM services may be unable to connect to the database server because of a network issue or an incorrect database connection string setting.</span></span> <span data-ttu-id="27fbd-261">管理/監視サーバーでアプリケーションログを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-261">Review the Application logs on the administration and monitoring server.</span></span> <span data-ttu-id="27fbd-262">ソース ASP.NET 2.0.50727.0 からのエラーエントリまたは警告が表示されることがあります。これは、次のようなログエントリに似ています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-262">You might see errors entries or warnings from source ASP.NET 2.0.50727.0 that resemble the following log entry:</span></span>

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### <span data-ttu-id="27fbd-263">考えられる原因</span><span class="sxs-lookup"><span data-stu-id="27fbd-263">Possible causes</span></span>

##### <span data-ttu-id="27fbd-264">原因1</span><span class="sxs-lookup"><span data-stu-id="27fbd-264">Cause 1</span></span>

<span data-ttu-id="27fbd-265">管理および監視サーバーコンポーネントのインストール中に、管理者が無効なデータベースインスタンス名またはデータベース名を指定している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-265">The administrator may have specified an invalid database instance name/database name during installation of administration and monitoring server components.</span></span>

<span data-ttu-id="27fbd-266">IIS 管理コンソールを使用して、データベース接続文字列を確認して修正することができます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-266">You can verify and correct the database connection strings by using the IIS Management console.</span></span> <span data-ttu-id="27fbd-267">これを行うには、IIS Manager を開き、Microsoft BitLocker の管理と監視に移動します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-267">To do this, open IIS Manager, and browse to Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="27fbd-268">左側に表示される各サービスについて、次の手順に従ってデータベース接続文字列を変更します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-268">For each service that is listed on the left side, follow these steps to change the database connection strings:</span></span>

1. <span data-ttu-id="27fbd-269">[**機能] ビュー**で、[**接続文字列**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="27fbd-269">In **Features View**, double-select **Connection Strings**.</span></span>

2. <span data-ttu-id="27fbd-270">[**接続文字列**] ページで、変更する接続文字列を選びます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-270">On the **Connection Strings** page, select the connection string that you want to change.</span></span>

3. <span data-ttu-id="27fbd-271">[**操作**] ウィンドウで、[**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-271">In the **Actions** pane, select **Edit**.</span></span>

4. <span data-ttu-id="27fbd-272">[**接続文字列の編集**] ダイアログボックスで、変更するプロパティを変更して、[ **OK]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-272">In the **Edit Connection String** dialog box, change the properties that you want to change, and then select **OK**.</span></span>

##### <span data-ttu-id="27fbd-273">原因2</span><span class="sxs-lookup"><span data-stu-id="27fbd-273">Cause 2</span></span>

<span data-ttu-id="27fbd-274">ファイアウォールでブロックされている SQL Server ポート。</span><span class="sxs-lookup"><span data-stu-id="27fbd-274">SQL Server port blocked in firewall.</span></span> <span data-ttu-id="27fbd-275">SQL Server がリッスンするように構成されているポート番号を確認し、管理サーバーとデータベースサーバー間のファイアウォールでポートが開かれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-275">Verify the port number to which SQL Server is configured to listen, and make sure that the port is open in the firewall between the administration server and database server.</span></span>

##### <span data-ttu-id="27fbd-276">原因3</span><span class="sxs-lookup"><span data-stu-id="27fbd-276">Cause 3</span></span>

<span data-ttu-id="27fbd-277">SQL server の TCP/IP バインドが正しくありません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-277">Incorrect SQL server TCP/IP bindings.</span></span> <span data-ttu-id="27fbd-278">データベースサーバーの SQL Server 構成マネージャーで SQL TCP/IP バインドを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-278">Verify SQL TCP/IP bindings in SQL Server Configuration Manager on the database server.</span></span> <span data-ttu-id="27fbd-279">MBAM では、データベースへの接続に TCP/IP および名前付きパイププロトコルが有効になっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-279">MBAM requires that the TCP/IP and Named Pipes protocols are enabled to connect to the database.</span></span>

##### <span data-ttu-id="27fbd-280">原因4</span><span class="sxs-lookup"><span data-stu-id="27fbd-280">Cause 4</span></span>

<span data-ttu-id="27fbd-281">NT Authority\Network Service アカウントまたは MBAM 管理サーバーのコンピューターアカウントには、SQL データベースに接続するために必要な権限がありません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-281">The NT Authority\Network Service account or the MBAM Administration Server’s computer account doesn't have the required permissions to connect to the SQL database.</span></span>

<span data-ttu-id="27fbd-282">データベースサーバーにデータベースコンポーネントをインストールするときに、インストーラーは次の2つのローカルグループを作成します。 MBAM コンプライアンス監査データベースアクセスと MBAM 回復とハードウェアデータベースアクセス。</span><span class="sxs-lookup"><span data-stu-id="27fbd-282">During the installation of database components on the database server, the installer creates two local groups: MBAM Compliance Auditing DB Access and MBAM Recovery and Hardware DB Access.</span></span>

<span data-ttu-id="27fbd-283">NT Authority\Network サービスアカウント、MBAM 管理サーバーのコンピューターアカウント、およびデータベースコンポーネントをインストールしたユーザーは、これらのグループに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-283">The NT Authority\Network Service account, the MBAM administration server’s computer account, and the user who installs the database components are automatically added to these groups.</span></span>

<span data-ttu-id="27fbd-284">これらのグループには、インストール中にデータベースに必要なアクセス許可が付与されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-284">These groups are granted the required permissions on the database during the installation.</span></span> <span data-ttu-id="27fbd-285">このグループに参加しているすべてのユーザーは、データベースに対して必要なアクセス許可を自動的に受け取ります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-285">All users who are part of this group automatically receive the required permissions on the database.</span></span>

<span data-ttu-id="27fbd-286">次の条件の1つ以上が該当する場合、アクセス許可の問題が原因で、web サービスがデータベースサーバーに接続されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-286">The web service may not connect to the database server because of a permissions issue if one or more of the following conditions are true:</span></span>

* <span data-ttu-id="27fbd-287">前に説明したグループは、データベースサーバーのローカルグループから削除されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-287">The groups that were mentioned earlier are removed from the local groups on the database server.</span></span>

* <span data-ttu-id="27fbd-288">NT Authority\Network サービスアカウントと MBAM 管理サーバーのコンピューターアカウントは、これらのグループのメンバーではありません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-288">The NT Authority\Network Service account and the MBAM administration server’s computer account are not members of these groups.</span></span>

* <span data-ttu-id="27fbd-289">これらのグループには、データベースに対する必要なアクセス許可がありません。</span><span class="sxs-lookup"><span data-stu-id="27fbd-289">These groups do not have the required permissions on the database.</span></span>

<span data-ttu-id="27fbd-290">以前の条件のいずれかが満たされている場合、MBAM 管理および監視サーバーのアプリケーションログでアクセス許可に関連するエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-290">You will notice permissions-related errors in the Application logs on the MBAM administration and monitoring server if any of the previous conditions are true.</span></span> <span data-ttu-id="27fbd-291">その場合は、NT Authority\Network Service アカウントと MBAM 管理サーバーのコンピューターアカウントを手動で追加し、SQL Server Management Studio () を使用している SQL データベースサーバーでサーバー全体のパブリックロールを付与する必要があり https://msdn.microsoft.com/library/aa337562.aspx) ます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-291">In that case, you should manually add the NT Authority\Network Service account and MBAM administration server’s computer account and grant them a server-wide public role on the SQL database server that is using SQL Server Management Studio (https://msdn.microsoft.com/library/aa337562.aspx).</span></span>

#### <span data-ttu-id="27fbd-292">Web サービスのログを確認する</span><span class="sxs-lookup"><span data-stu-id="27fbd-292">Review the web service logs</span></span>

<span data-ttu-id="27fbd-293">MBAM 管理サーバーのアプリケーションログにイベントが記録されていない場合は、MBAM 管理と監視サーバーでホストされている MBAM web サービスの web サービスログ (svclog) を確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-293">If no events are logged in the Application logs on the MBAM administration server, it’s time to review the web service logs (.svclog) of the MBAM web service that is hosted on the MBAM administration and monitoring server.</span></span> <span data-ttu-id="27fbd-294">ログファイルを表示するには、サービストレースビューアーツール (SvcTraceViewer.exe) を使用する必要があり https://msdn.microsoft.com/library/ms732023.aspx ます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-294">You will have to use the Service Trace Viewer Tool (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx to view the log file.</span></span>

<span data-ttu-id="27fbd-295">主に、Recoveryandハードウェアサービスと ComplianceStatusService のサービストレースログを調査する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-295">You should primarily investigate the service trace logs of RecoveryandHardwareService and ComplianceStatusService.</span></span> <span data-ttu-id="27fbd-296">既定では、web サービスログは C:\inetpub\Microsoft BitLocker 管理 Solution\Logs フォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-296">By default, web service logs are located in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span> <span data-ttu-id="27fbd-297">各サービスは、それぞれのフォルダーの下に svclog ファイルを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-297">There, each service writes its .svclog file under its own folder.</span></span>

<span data-ttu-id="27fbd-298">サービスのトレースログで、エラーまたは警告エントリのアクティビティを確認します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-298">Review the activity in the service trace log for any error or warning entries.</span></span> <span data-ttu-id="27fbd-299">既定では、エラーエントリは赤で強調表示されています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-299">By default, error entries are highlighted in red.</span></span> <span data-ttu-id="27fbd-300">エラーエントリの詳細情報を表示するには、トレースビューアーの右側のウィンドウでエラーの説明を選択します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-300">Select the error description on the right pane of the trace viewer to view detailed information about the error entry.</span></span> <span data-ttu-id="27fbd-301">トレースログからのエラーエントリの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-301">The following is a sample error entry from the trace log:</span></span>

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## <span data-ttu-id="27fbd-302">MBAM インフラストラクチャの再インストールまたは再構成</span><span class="sxs-lookup"><span data-stu-id="27fbd-302">Re-installation or reconfiguration of MBAM infrastructure</span></span>

<span data-ttu-id="27fbd-303">MBAM インフラストラクチャを再インストールまたは再構成するには、次の点を把握しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-303">To re-install or reconfigure MBAM infrastructure, you must know the following things:</span></span>

* <span data-ttu-id="27fbd-304">アプリケーションプールアカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-304">Application Pool account</span></span>

* <span data-ttu-id="27fbd-305">MBAM Groups (ヘルプデスク、詳細、レポートユーザーグループ)</span><span class="sxs-lookup"><span data-stu-id="27fbd-305">MBAM Groups (Helpdesk, Advanced, Report Users Group)</span></span>

* <span data-ttu-id="27fbd-306">MBAM レポート URL</span><span class="sxs-lookup"><span data-stu-id="27fbd-306">MBAM Reports URL</span></span>

* <span data-ttu-id="27fbd-307">SQL Server 名とデータベース名</span><span class="sxs-lookup"><span data-stu-id="27fbd-307">SQL Server name and database names</span></span>

* <span data-ttu-id="27fbd-308">MBAM ReadWrite および ReadOnly アカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-308">MBAM ReadWrite and ReadOnly Accounts</span></span>

### <span data-ttu-id="27fbd-309">アプリケーションプールアカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-309">Application Pool account</span></span>

<span data-ttu-id="27fbd-310">アプリケーションプールアカウントを見つけるには、MBAM Web サーバーにログオンし、**インターネットインフォメーションサービス (IIS) マネージャー**を開いて、[**アプリケーションプール**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-310">To find the Application Pool account, log on to the MBAM Web Server, open **Internet Information Services (IIS) Manager**, and then select **Application Pools**:</span></span>

![アプリケーションプール](images/troubleshooting-MBAM-installation-1.png)

<span data-ttu-id="27fbd-312">このアカウントでサービスプリンシパル名 (SPN) を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-312">The Service Principal Name (SPN) must be set in this account.</span></span> <span data-ttu-id="27fbd-313">この設定は、MBAM の機能に非常に重要です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-313">This setting is very important to the functionality of MBAM.</span></span>

### <span data-ttu-id="27fbd-314">MBAM グループ (ヘルプデスク、詳細、レポートユーザーグループ、レポート URL)</span><span class="sxs-lookup"><span data-stu-id="27fbd-314">MBAM Groups (Helpdesk, Advanced, Report Users Group and Reports URL)</span></span>

![MBAM グループ](images/troubleshooting-MBAM-installation-2.png)

<span data-ttu-id="27fbd-316">これには、ヘルプデスクグループ、上級のヘルプデスクグループ、レポートユーザーグループ、MBAM レポート URL などの情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-316">This provides information such as Helpdesk Group, Advanced Helpdesk Group, Report Users group, and MBAM Reports URL.</span></span> <span data-ttu-id="27fbd-317">MBAM レポート URL は、MBAM セットアップで指定する必要があります。「http (s)://servername/ReportServer.」と入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-317">The MBAM Reports URL must be provided in the MBAM setup and should read as: http(s)://servername/ReportServer.</span></span>

### <span data-ttu-id="27fbd-318">SQL Server 名とデータベース (DB) 名</span><span class="sxs-lookup"><span data-stu-id="27fbd-318">SQL Server name and database (DB) names</span></span>

<span data-ttu-id="27fbd-319">MBAM Db をホストしている SQL Server 名とインスタンスを検索するには、MBAM Web (IIS) サーバーにログオンし、次のレジストリサブキーを参照します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-319">To find the SQL Server names and instances hosting the MBAM DBs, log on to the MBAM Web (IIS) server and browse to the folowing registry subkey:</span></span>

**<span data-ttu-id="27fbd-320">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM \ Web</span><span class="sxs-lookup"><span data-stu-id="27fbd-320">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web</span></span>**

![Regedit.exe](images/troubleshooting-MBAM-installation-3.png)

<span data-ttu-id="27fbd-322">強調表示されている部分は接続文字列です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-322">The highlighted portions are connection strings.</span></span> <span data-ttu-id="27fbd-323">SQL Server 名、データベース名、およびインスタンス (名前付きの場合) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-323">These should have the SQL Server name, database names, and instances (if named).</span></span>

### <span data-ttu-id="27fbd-324">MBAM ReadWrite および ReadOnly アカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-324">MBAM ReadWrite and ReadOnly accounts</span></span>

<span data-ttu-id="27fbd-325">この情報は、web サーバーの名前が既に存在する SQL Server データベースに表示されます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-325">This information will be in the SQL Server database, for which we already found the name from the web server.</span></span>

#### <span data-ttu-id="27fbd-326">ReadWrite アカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-326">ReadWrite account</span></span>

1. <span data-ttu-id="27fbd-327">SQL Management Studio にログインします。</span><span class="sxs-lookup"><span data-stu-id="27fbd-327">Log in to the SQL Management Studio.</span></span>

2. <span data-ttu-id="27fbd-328">[ **Mbam 回復とハードウェア**] を右クリックし、[**プロパティ**] を選択して、[**アクセス許可**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-328">Right-click **MBAM Recovery and Hardware**, select **Properties**, and then select **Permissions**.</span></span>

<span data-ttu-id="27fbd-329">たとえば、ラボアカウント名は**Mbamwrite**です。</span><span class="sxs-lookup"><span data-stu-id="27fbd-329">For example, The the lab account name is **MBAMWrite**.</span></span> <span data-ttu-id="27fbd-330">アプリケーションプールと ReadWrite のアカウントが同じになるように設定されています。</span><span class="sxs-lookup"><span data-stu-id="27fbd-330">The Application Pool and ReadWrite accounts are set to be the same.</span></span>

![SQL DB](images/troubleshooting-MBAM-installation-4.png)

![DB プロパティ](images/troubleshooting-MBAM-installation-5.png)

<span data-ttu-id="27fbd-333">SQL Management Studio で [**セキュリティ**]、[**ログイン**] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-333">Browse to **Security** and then **Logins** in SQL Management Studio.</span></span> <span data-ttu-id="27fbd-334">前のスクリーンショットに示されているアカウントに移動します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-334">Browse to the account shown in the previous screenshot.</span></span>

![SQL セキュリティ](images/troubleshooting-MBAM-installation-6.png)

<span data-ttu-id="27fbd-336">アカウントを右クリックし、[**プロパティマッピング**] に移動して、Mbam Recovery とハードウェアデータベースを探します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-336">Right-click the accounts, go to **Properties User Mapping**, and locate the MBAM Recovery and Hardware database:</span></span>

![ユーザーマッピング](images/troubleshooting-MBAM-installation-7.png)

#### <span data-ttu-id="27fbd-338">読み取り専用アカウント</span><span class="sxs-lookup"><span data-stu-id="27fbd-338">ReadOnly account</span></span>

<span data-ttu-id="27fbd-339">SSRS サーバーで SQL Server Reporting Services 構成マネージャーを開きます。</span><span class="sxs-lookup"><span data-stu-id="27fbd-339">Open SQL Server Reporting Services Configuration Manager on the SSRS Server.</span></span> <span data-ttu-id="27fbd-340">[**レポートマネージャーの url**] を選択し、次に**url**を参照します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-340">Select **Report Manager URL**, and then browse the **URLs**:</span></span>

![レポートマネージャー](images/troubleshooting-MBAM-installation-8.png)

<span data-ttu-id="27fbd-342">**Microsoft Bitlocker の管理と監視**を選択します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-342">Select **Microsoft Bitlocker Administration and Monitoring**:</span></span>

![Bitlocker の管理と監視](images/troubleshooting-MBAM-installation-9.png)

<span data-ttu-id="27fbd-344">[ **MaltaDatasource**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="27fbd-344">Select **MaltaDatasource**:</span></span>

![Db](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

<span data-ttu-id="27fbd-347">MaltaDataSource には ReadOnly アカウント名が必要であり、MBAM セットアップで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="27fbd-347">MaltaDataSource should have the ReadOnly Account name and should be used in MBAM setup.</span></span>

## <span data-ttu-id="27fbd-348">リファレンス</span><span class="sxs-lookup"><span data-stu-id="27fbd-348">Reference</span></span>

<span data-ttu-id="27fbd-349">詳細については、次の記事を参照してください。</span><span class="sxs-lookup"><span data-stu-id="27fbd-349">For more information, see the following articles:</span></span>

[<span data-ttu-id="27fbd-350">スタンドアロン構成で MBAM 2.5 を展開する</span><span class="sxs-lookup"><span data-stu-id="27fbd-350">Deploying MBAM 2.5 in a standalone configuration</span></span>](https://support.microsoft.com/help/3046555)

[<span data-ttu-id="27fbd-351">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="27fbd-351">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
