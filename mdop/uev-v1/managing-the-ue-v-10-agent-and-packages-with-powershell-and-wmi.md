---
title: PowerShell と WMI を使用した UE-V 1.0 エージェントの管理
description: PowerShell と WMI を使用した UE-V 1.0 エージェントの管理
author: dansimp
ms.assetid: c8989b01-1769-4e69-82b1-4aadb261d2d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79268e3384aaaf08bdd4e9b92d74b039ce96596a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819297"
---
# <span data-ttu-id="2f445-103">PowerShell と WMI を使用した UE-V 1.0 エージェントの管理</span><span class="sxs-lookup"><span data-stu-id="2f445-103">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>


<span data-ttu-id="2f445-104">WMI と PowerShell を使用して、Microsoft User Experience Virtualization (UE-V) エージェントの構成と同期動作を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="2f445-104">You can use WMI and PowerShell to manage Microsoft User Experience Virtualization (UE-V) Agent configuration and synchronization behavior.</span></span>

**<span data-ttu-id="2f445-105">PowerShell で UE-V agent を展開する方法</span><span class="sxs-lookup"><span data-stu-id="2f445-105">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="2f445-106">UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。</span><span class="sxs-lookup"><span data-stu-id="2f445-106">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="2f445-107">注</span><span class="sxs-lookup"><span data-stu-id="2f445-107">Note</span></span>**  
    <span data-ttu-id="2f445-108">AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。</span><span class="sxs-lookup"><span data-stu-id="2f445-108">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="2f445-109">Windows Installer ファイルのバージョン、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。</span><span class="sxs-lookup"><span data-stu-id="2f445-109">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="2f445-110">インストールファイルを使用して後から UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f445-110">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="2f445-111">エージェントをインストールするには、次の PowerShell コマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="2f445-111">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="2f445-112">PowerShell を使用して UE-V Agent を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2f445-112">How to configure the UE-V Agent with PowerShell</span></span>**

1.  <span data-ttu-id="2f445-113">管理者権限を持つアカウントを使用して、PowerShell ウィンドウを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2f445-113">Use an account with administrator rights to open a PowerShell window.</span></span> <span data-ttu-id="2f445-114">次のコマンドを使用して、UE-V PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2f445-114">Import the UE-V PowerShell module by using the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="2f445-115">次の PowerShell コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f445-115">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="2f445-116">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="2f445-116">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="2f445-117">説明</span><span class="sxs-lookup"><span data-stu-id="2f445-117">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-118">Get-UevConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-118">Get-UevConfiguration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="2f445-119">有効な UE-V agent の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-119">View the effective UE-V agent settings.</span></span> <span data-ttu-id="2f445-120">ユーザー固有の設定はコンピューターの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2f445-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-121">Get-UevConfiguration-CurrentComputerUser</span><span class="sxs-lookup"><span data-stu-id="2f445-121">Get-UevConfiguration - CurrentComputerUser</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="2f445-122">現在のユーザーのみの UE-V agent settings の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-122">View the UE-V agent settings values for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-123">Get-UevConfiguration-コンピューター</span><span class="sxs-lookup"><span data-stu-id="2f445-123">Get-UevConfiguration -Computer</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-124">コンピューター上のすべてのユーザーの UE-V agent 構成設定の値を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-124">View the UE-V agent configuration settings values for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-125">Set-UevConfiguration-コンピューターの設定 Storagepath &lt; パス _settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-125">Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-126">コンピューターごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f445-126">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-127">Set-UevConfiguration-CurrentComputerUser-SettingsStoragePath の &lt; _settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-127">Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-128">ユーザーごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f445-128">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-129">Set-UevConfiguration-コンピューター-SyncTimeoutInMilliseconds &lt; タイムアウト (ミリ秒)&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-129">Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-130">同期タイムアウトをミリ秒単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-130">Set the synchronization timeout in milliseconds</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-131">Set-UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds &lt; タイムアウト (ミリ秒)&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-131">Set-UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-132">現在のユーザーの同期タイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-132">Set the synchronization timeout for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-133">Set-UevConfiguration-コンピューター-Maxパッケージ Izeinbytes &lt; size (バイト単位)&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-133">Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-134">設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f445-134">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="2f445-135">しきい値のパッケージサイズをバイト単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-135">Set the threshold package size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-136">Set-UevConfiguration-CurrentComputerUser-Maxパッケージ Izeinbytes &lt; size (バイト単位)&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-136">Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-137">現在のユーザーに対してパッケージサイズの警告のしきい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-137">Set the package size warning threshold for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-138">Set-UevConfiguration – Computer – &lt; catalog To SettingsTemplateCatalogPath path&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-138">Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-139">設定テンプレートカタログのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-139">Set the settings template catalog path.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-140">Set-UevConfiguration-コンピューター-SyncMethod の &lt; 同期方法&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-140">Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-141">同期方法 (OfflineFiles または None) を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-141">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-142">Set-UevConfiguration-CurrentComputerUser-SyncMethod の &lt; 同期方法&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-142">Set-UevConfiguration -CurrentComputerUser -SyncMethod &lt;sync method&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-143">現在のユーザー: OfflineFiles または None の同期方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-143">Set the synchronization method for the current user: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-144">Set-UEVConfiguration-Computer – Enablesettingシム Portnotify</span><span class="sxs-lookup"><span data-stu-id="2f445-144">Set-UEVConfiguration -Computer –EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-145">[ユーザー設定のインポート] の遅延が発生した場合に通知が表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2f445-145">Enable notification to occur when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="2f445-146">-Disablesettingシム Portnotify を使用して通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-146">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-147">Set-UEVConfiguration-CurrentComputerUser-Enablesettingシム通知</span><span class="sxs-lookup"><span data-stu-id="2f445-147">Set-UEVConfiguration - CurrentComputerUser -EnableSettingsImportNotify</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-148">ユーザー設定のインポートが延期された場合に、現在のユーザーに対して通知を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-148">Enable notification for the current user when the import of user settings is delayed.</span></span></p>
    <p><span data-ttu-id="2f445-149">-Disablesettingシム Portnotify を使用して通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-149">Use –DisableSettingsImportNotify to disable notification.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-150">Set-UEVConfiguration-コンピューター-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="2f445-150">Set-UEVConfiguration -Computer -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-151">ユーザーに通知するまでの時間 (秒単位) を指定する</span><span class="sxs-lookup"><span data-stu-id="2f445-151">Specify the time in seconds before the user is notified</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-152">Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</span><span class="sxs-lookup"><span data-stu-id="2f445-152">Set-UEVConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-153">現在のユーザーに通知するまでの時間 (秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-153">Specify the time in seconds before notification for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-154">Set-UevConfiguration – Computer – DisableSync</span><span class="sxs-lookup"><span data-stu-id="2f445-154">Set-UevConfiguration –Computer –DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-155">コンピューター上のすべてのユーザーに対して UE-V を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-155">Disable UE-V for all the users on the computer.</span></span></p>
    <p><span data-ttu-id="2f445-156">– EnableSync を使用して、有効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-156">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-157">Set-UevConfiguration – CurrentComputerUser-DisableSync</span><span class="sxs-lookup"><span data-stu-id="2f445-157">Set-UevConfiguration –CurrentComputerUser -DisableSync</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-158">コンピューター上の現在のユーザーに対して UE-V を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-158">Disable UE-V for the current user on the computer.</span></span></p>
    <p><span data-ttu-id="2f445-159">– EnableSync を使用して、有効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="2f445-159">Use –EnableSync to enable or re-enable.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-160">クリア-UevConfiguration –コンピューターの &lt; 設定名&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-160">Clear-UevConfiguration –Computer -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-161">コンピューター上のすべてのユーザーの特定の設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="2f445-161">Clear a specific setting for all users on the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-162">クリア-UevConfiguration – CurrentComputerUser &lt; 設定名&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-162">Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-163">現在のユーザーに対してのみ、特定の設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="2f445-163">Clear a specific setting for the current user only.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-164">エクスポート-UevConfiguration &lt; settings 移行ファイル&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-164">Export-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-165">UE-V のコンピューター構成を設定移行ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f445-165">Export the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="2f445-166">ファイルの拡張子は "uev" である必要があります。</span><span class="sxs-lookup"><span data-stu-id="2f445-166">The extension of the file must be “.uev”.</span></span></p>
    <p><span data-ttu-id="2f445-167">エクスポートコマンドレットは、-computer パラメーターで構成可能なすべての UE-V agent 設定をエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="2f445-167">The export cmdlet exports all UE-V agent settings that are configurable with the -computer parameter.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-168">インポート-UevConfiguration &lt; settings 移行ファイル&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-168">Import-UevConfiguration &lt;settings migration file&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-169">設定移行ファイル (uev ファイル) から UE-V のコンピューター構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="2f445-169">Import the UE-V computer configuration from a settings migration file (.uev file).</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="2f445-170">PowerShell を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復する方法</span><span class="sxs-lookup"><span data-stu-id="2f445-170">How to export UE-V package settings and repair UE-V templates with PowerShell</span></span>**

1.  <span data-ttu-id="2f445-171">管理者として PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="2f445-171">Open a PowerShell window as an Administrator.</span></span> <span data-ttu-id="2f445-172">次のコマンドを使用して、UE-V PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="2f445-172">Import the UE-V PowerShell module with the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="2f445-173">次の PowerShell コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f445-173">Use the following PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="2f445-174">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="2f445-174">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="2f445-175">説明</span><span class="sxs-lookup"><span data-stu-id="2f445-175">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-176">エクスポート-UevPackage MicrosoftCalculator6 x</span><span class="sxs-lookup"><span data-stu-id="2f445-176">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-177">Microsoft の電卓パッケージファイルから設定を抽出し、XML で判読可能な形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="2f445-177">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-178">修復-UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="2f445-178">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-179">UE-V 設定の場所テンプレートのインデックスを修復します。</span><span class="sxs-lookup"><span data-stu-id="2f445-179">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="2f445-180">WMI を使用して UE-V Agent を構成する方法</span><span class="sxs-lookup"><span data-stu-id="2f445-180">How to configure the UE-V Agent with WMI</span></span>**

1.  <span data-ttu-id="2f445-181">ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="2f445-181">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="2f445-182">管理者は、このインターフェイスを使用して、コマンドラインから UE-V エージェントを構成し、一般的な構成タスクを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="2f445-182">Administrators can use this interface to configure the UE-V agent from the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="2f445-183">管理者権限を持つアカウントを使用して、PowerShell ウィンドウを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="2f445-183">Use an account with administrator rights to open a PowerShell window.</span></span>

2.  <span data-ttu-id="2f445-184">次の WMI コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="2f445-184">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="2f445-185">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="2f445-185">PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="2f445-186">説明</span><span class="sxs-lookup"><span data-stu-id="2f445-186">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-187">WmiObject-名前空間 root\Microsoft\UEV 構成</span><span class="sxs-lookup"><span data-stu-id="2f445-187">Get-WmiObject -Namespace root\Microsoft\UEV Configuration</span></span></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="2f445-188">アクティブな UE-V agent の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-188">View the active UE-V agent settings.</span></span> <span data-ttu-id="2f445-189">ユーザー固有の設定はコンピューターの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="2f445-189">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-190">WmiObject-Namespace root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-190">Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-191">ユーザーに対して定義されている UE-V agent 構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-191">View the UE-V agent configuration that is defined for user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-192">WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-192">Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-193">コンピューターに対して定義されている UE-V エージェント構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="2f445-193">View the UE-V agent configuration that is defined for computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-194">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-194">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-195">$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-195">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="2f445-196">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-196">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-197">コンピューターごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f445-197">Define a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-198">$config = WmiObject-Namespace root\Microsoft\UEV UserConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-198">$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-199">$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-199">$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</span></span></p>
    <p><span data-ttu-id="2f445-200">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-200">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-201">ユーザーごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="2f445-201">Define a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-202">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-202">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-203">$config。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-203">$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</span></span></p>
    <p><span data-ttu-id="2f445-204">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-204">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-205">同期タイムアウトをミリ秒単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-205">Set the synchronization timeout in milliseconds.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-206">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-206">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-207">$config。Maxパッケージ Izeinbytes = &lt; size_in_bytes&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-207">$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</span></span></p>
    <p><span data-ttu-id="2f445-208">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-208">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-209">設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="2f445-209">Configure the UE-V agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="2f445-210">しきい値パッケージのファイルサイズをバイト単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-210">Set the threshold package file size in bytes.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-211">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-211">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-212">$config。SyncMethod = &lt; sync_method&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-212">$config.SyncMethod = &lt;sync_method&gt;</span></span></p>
    <p><span data-ttu-id="2f445-213">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-213">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-214">同期方法 (OfflineFiles または None) を設定します。</span><span class="sxs-lookup"><span data-stu-id="2f445-214">Set the synchronization method: OfflineFiles or None.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="2f445-215">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-215">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-216">$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-216">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="2f445-217">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-217">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-218">特定のコンピューター単位の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="2f445-218">Update a specific per-computer setting.</span></span> <span data-ttu-id="2f445-219">設定をクリアするには、設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="2f445-219">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="2f445-220">$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</span><span class="sxs-lookup"><span data-stu-id="2f445-220">$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</span></span></p>
    <p><span data-ttu-id="2f445-221">$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</span><span class="sxs-lookup"><span data-stu-id="2f445-221">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><span data-ttu-id="2f445-222">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="2f445-222">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="2f445-223">特定のユーザーごとの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="2f445-223">Update a specific per-user setting.</span></span> <span data-ttu-id="2f445-224">設定をクリアするには、設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="2f445-224">To clear the setting, use $null as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## <span data-ttu-id="2f445-225">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2f445-225">Related topics</span></span>


[<span data-ttu-id="2f445-226">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="2f445-226">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="2f445-227">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="2f445-227">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)









