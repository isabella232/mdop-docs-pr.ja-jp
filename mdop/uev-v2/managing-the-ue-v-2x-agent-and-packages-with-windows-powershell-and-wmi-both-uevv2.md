---
title: Windows PowerShell と WMI で UE-V Agent とパッケージを管理する
description: Windows PowerShell と WMI で UE-V Agent とパッケージを管理する
author: dansimp
ms.assetid: 56e6780b-8b2c-4717-91c8-2af63062ab75
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6a709d2c66266cf33b8e89ddd905aa0f21eb7dfe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826804"
---
# <span data-ttu-id="12d29-103">Windows PowerShell と WMI で UE-V Agent とパッケージを管理する</span><span class="sxs-lookup"><span data-stu-id="12d29-103">Managing the UE-V 2.x Agent and Packages with Windows PowerShell and WMI</span></span>


<span data-ttu-id="12d29-104">Windows Management Instrumentation (WMI) と Windows PowerShell を使用して、Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 エージェントの構成と同期動作を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="12d29-104">You can use Windows Management Instrumentation (WMI) and Windows PowerShell to manage Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent configuration and synchronization behavior.</span></span> <span data-ttu-id="12d29-105">UE-V PowerShell コマンドレットの完全な一覧については、「 [ue-v 2 コマンドレットリファレンス](https://go.microsoft.com/fwlink/?LinkId=393495)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="12d29-105">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/?LinkId=393495) (https://go.microsoft.com/fwlink/?LinkId=393495).</span></span>

**<span data-ttu-id="12d29-106">Windows PowerShell を使用して UE-V Agent を展開するには</span><span class="sxs-lookup"><span data-stu-id="12d29-106">To deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="12d29-107">UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。</span><span class="sxs-lookup"><span data-stu-id="12d29-107">Stage the UE-V installer file in an accessible network share.</span></span>

    **<span data-ttu-id="12d29-108">注</span><span class="sxs-lookup"><span data-stu-id="12d29-108">Note</span></span>**  
    <span data-ttu-id="12d29-109">AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。</span><span class="sxs-lookup"><span data-stu-id="12d29-109">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="12d29-110">Windows Installer パッケージ、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。</span><span class="sxs-lookup"><span data-stu-id="12d29-110">Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="12d29-111">インストールファイルを使用して、後で UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d29-111">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="12d29-112">UE-V Agent をインストールするには、次の Windows PowerShell コマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-112">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**<span data-ttu-id="12d29-113">Windows PowerShell を使用して UE-V Agent を構成するには</span><span class="sxs-lookup"><span data-stu-id="12d29-113">To configure the UE-V Agent by using Windows PowerShell</span></span>**

1. <span data-ttu-id="12d29-114">Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="12d29-114">Open a Windows PowerShell window.</span></span> <span data-ttu-id="12d29-115">*コンピューターのパラメーターを*使用してコンピューターのすべてのユーザーに影響を与えるコンピューター設定を管理するには、管理者権限のあるアカウントでウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="12d29-115">To manage computer settings that affect all users of the computer by using the *Computer* parameter, open the window with an account that has administrator rights.</span></span>

2. <span data-ttu-id="12d29-116">次の Windows PowerShell コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-116">Use the following Windows PowerShell commands to configure the agent.</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="12d29-117">Windows PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="12d29-117">Windows PowerShell command</span></span></th>
   <th align="left"><span data-ttu-id="12d29-118">説明</span><span class="sxs-lookup"><span data-stu-id="12d29-118">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="12d29-119">有効な UE-V Agent 設定を取得します。</span><span class="sxs-lookup"><span data-stu-id="12d29-119">Gets the effective UE-V Agent settings.</span></span> <span data-ttu-id="12d29-120">ユーザー固有の設定はコンピューターの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="12d29-120">User-specific settings have precedence over the computer settings.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p><span data-ttu-id="12d29-121">現在のユーザーのみの UE-V Agent settings の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="12d29-121">Gets the UE-V Agent settings values for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-122">コンピューター上のすべてのユーザーの UE-V Agent 構成設定の値を取得します。</span><span class="sxs-lookup"><span data-stu-id="12d29-122">Gets the UE-V Agent configuration settings values for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-123">各構成設定の詳細を取得します。</span><span class="sxs-lookup"><span data-stu-id="12d29-123">Gets the details for each configuration setting.</span></span> <span data-ttu-id="12d29-124">設定が構成されている場所、または既定値を使用するかどうかを表示します。</span><span class="sxs-lookup"><span data-stu-id="12d29-124">Displays where the setting is configured or if it uses the default value.</span></span> <span data-ttu-id="12d29-125">現在の設定が有効であるかどうかが表示されます。</span><span class="sxs-lookup"><span data-stu-id="12d29-125">Is displayed if the current setting is valid.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-126">[会社の設定] センターに表示される [ヘルプ] リンクのテキストを設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-126">Sets the text that is displayed in the Company Settings Center for the help link.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-127">[ヘルプ] リンクの [会社設定センター] のリンクの URL を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-127">Sets the URL of the link in the Company Settings Center for the help link.</span></span> <span data-ttu-id="12d29-128">任意の URL プロトコルを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="12d29-128">Any URL protocol can be used.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-129">コンピューター上のすべてのユーザーの Windows アプリを同期しないように UE-V エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-129">Configures the UE-V Agent to not synchronize any Windows apps for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-130">現在のコンピューターユーザーの Windows アプリを同期しないように UE-V エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-130">Configures the UE-V Agent to not synchronize any Windows apps for the current computer user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-131">コンピューター上のすべてのユーザーに対して初めてエージェントを実行したときの通知を表示するように、UE-V Agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-131">Configures the UE-V Agent to display notification the first time the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-132">コンピューター上のすべてのユーザーに対して初めてエージェントを実行するときに、UE-V Agent が通知を表示しないように構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-132">Configures the UE-V Agent to not display notification the first time that the agent runs for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-133">設定の同期が遅延したときに、コンピューター上のすべてのユーザーに対して UE-V Agent が通知されるように構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-133">Configures the UE-V Agent to notify all users on the computer when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="12d29-134"><em>Disablesettingシム portnotify パラメーターを使って </em> 通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-134">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-135">設定の同期が遅延したときに、現在のユーザーに通知するように UE-V Agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-135">Configures the UE-V Agent to notify the current user when settings synchronization is delayed.</span></span></p>
   <p><span data-ttu-id="12d29-136"><em>Disablesettingシム portnotify パラメーターを使って </em> 通知を無効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-136">Use the <em>DisableSettingsImportNotify</em> parameter to disable notification.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-137">コンピューターのすべてのユーザーに対して、Windows アプリの一覧によって明示的に無効になっていないすべての Windows アプリを同期するように UE-V Agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-137">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for all users of the computer.</span></span> <span data-ttu-id="12d29-138">詳細については、「 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> WINDOWS PowerShell と WMI を使用して Ue-v の UevAppxPackage 設定の場所テンプレートを管理 </a> する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12d29-138">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="12d29-139"><em> </em> Windows アプリリストによって明示的に有効になっている windows アプリのみを同期するように ue-v agent を構成するには、DisableSyncUnlistedWindows8Apps パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-139">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-140">コンピューター上の現在のユーザーの Windows アプリリストによって明示的に無効になっていないすべての Windows アプリを同期するように UE-V Agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-140">Configures the UE-V Agent to synchronize all Windows apps that are not explicitly disabled by the Windows app list for the current user on the computer.</span></span> <span data-ttu-id="12d29-141">詳細については、「 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> WINDOWS PowerShell と WMI を使用して Ue-v の UevAppxPackage 設定の場所テンプレートを管理 </a> する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12d29-141">For more information, see &quot;Get-UevAppxPackage&quot; in <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</a>.</span></span></p>
   <p><span data-ttu-id="12d29-142"><em> </em> Windows アプリリストによって明示的に有効になっている windows アプリのみを同期するように ue-v agent を構成するには、DisableSyncUnlistedWindows8Apps パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-142">Use the <em>DisableSyncUnlistedWindows8Apps</em> parameter to configure the UE-V Agent to synchronize only Windows apps that are explicitly enabled by the Windows App List.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-143">コンピューター上のすべてのユーザーに対して UE-V を無効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-143">Disables UE-V for all the users on the computer.</span></span></p>
   <p><span data-ttu-id="12d29-144">EnableSync パラメーターを使って、 <em> </em> 有効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-144">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-145">コンピューターの現在のユーザーに対して UE-V を無効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-145">Disables UE-V for the current user on the computer.</span></span></p>
   <p><span data-ttu-id="12d29-146">EnableSync パラメーターを使って、 <em> </em> 有効または有効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-146">Use the <em>EnableSync</em> parameter to enable or re-enable.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-147">コンピューターのすべてのユーザーの通知領域の UE-V アイコンを有効にします。</span><span class="sxs-lookup"><span data-stu-id="12d29-147">Enables the UE-V icon in the notification area for all users of the computer.</span></span></p>
   <p><span data-ttu-id="12d29-148">アイコンを <em> </em> 無効にするには、DisableTrayIcon パラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-148">Use the <em>DisableTrayIcon</em> parameter to disable the icon.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-149">設定パッケージファイルサイズが、コンピューター上のすべてのユーザーに対して定義されたしきい値に達したときに報告するように、UE-V agent を構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-149">Configures the UE-V agent to report when a settings package file size reaches the defined threshold for all users on the computer.</span></span> <span data-ttu-id="12d29-150">しきい値パッケージサイズ (バイト単位) を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-150">Sets the threshold package size in bytes.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-151">設定パッケージファイルサイズが定義されたしきい値に達したときに報告するように UE-V エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-151">Configures the UE-V agent to report when a settings package file size reaches the defined threshold.</span></span> <span data-ttu-id="12d29-152">現在のユーザーのパッケージサイズの警告しきい値を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-152">Sets the package size warning threshold for the current user.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-153">コンピューターのすべてのユーザーに対してユーザーに通知するまでの時間 (秒単位) を指定します</span><span class="sxs-lookup"><span data-stu-id="12d29-153">Specifies the time in seconds before the user is notified for all users of the computer</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-154">現在のユーザーの通知が送信されるまでの時間 (秒単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-154">Specifies the time in seconds before notification for the current user is sent.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-155">コンピューターのすべてのユーザーに対して、コンピューターごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="12d29-155">Defines a per-computer settings storage location for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-156">ユーザーごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="12d29-156">Defines a per-user settings storage location.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-157">コンピューターのすべてのユーザーの設定テンプレートカタログのパスを設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-157">Sets the settings template catalog path for all users of the computer.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-158">コンピューターのすべてのユーザー (SyncProvider または None) の同期方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-158">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-159">現在のユーザーの同期方法を設定します。 SyncProvider または None。</span><span class="sxs-lookup"><span data-stu-id="12d29-159">Sets the synchronization method for the current user: SyncProvider or None.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-160">コンピューターのすべてのユーザーに対して同期のタイムアウト (ミリ秒単位) を設定します</span><span class="sxs-lookup"><span data-stu-id="12d29-160">Sets the synchronization time-out in milliseconds for all users of the computer</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-161">現在のユーザーの同期タイムアウトを設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-161">Set the synchronization time-out for the current user.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-162">コンピューター上のすべてのユーザーに対して指定された設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="12d29-162">Clears the specified setting for all users on the computer.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-163">現在のユーザーのみに指定された設定をクリアします。</span><span class="sxs-lookup"><span data-stu-id="12d29-163">Clears the specified setting for the current user only.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-164">UE-V コンピューターの構成を設定移行ファイルにエクスポートします。</span><span class="sxs-lookup"><span data-stu-id="12d29-164">Exports the UE-V computer configuration to a settings migration file.</span></span> <span data-ttu-id="12d29-165">ファイル名拡張子は uev である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d29-165">The file name extension must be .uev.</span></span></p>
   <p><span data-ttu-id="12d29-166">この <code>Export</code> コマンドレットは、Computer パラメーターで構成可能なすべての Ue-v agent 設定をエクスポートし <em> </em> ます。</span><span class="sxs-lookup"><span data-stu-id="12d29-166">The <code>Export</code> cmdlet exports all UE-V Agent settings that are configurable with the <em>Computer</em> parameter.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p><span data-ttu-id="12d29-167">設定移行ファイルから UE-V のコンピューター構成をインポートします。</span><span class="sxs-lookup"><span data-stu-id="12d29-167">Imports the UE-V computer configuration from a settings migration file.</span></span> <span data-ttu-id="12d29-168">ファイル名拡張子は uev である必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d29-168">The file name extension must be .uev.</span></span></p></td>
   </tr>
   </tbody>
   </table>



**<span data-ttu-id="12d29-169">Windows PowerShell を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復するには</span><span class="sxs-lookup"><span data-stu-id="12d29-169">To export UE-V package settings and repair UE-V templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="12d29-170">管理者として Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="12d29-170">Open a Windows PowerShell window as an administrator.</span></span>

2.  <span data-ttu-id="12d29-171">次の Windows PowerShell コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-171">Use the following Windows PowerShell commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="12d29-172">Windows PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="12d29-172">Windows PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="12d29-173">説明</span><span class="sxs-lookup"><span data-stu-id="12d29-173">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="12d29-174">エクスポート-UevPackage MicrosoftCalculator6 x</span><span class="sxs-lookup"><span data-stu-id="12d29-174">Export-UevPackage MicrosoftCalculator6.pkgx</span></span></p></td>
    <td align="left"><p><span data-ttu-id="12d29-175">Microsoft の電卓パッケージファイルから設定を抽出し、XML で判読可能な形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="12d29-175">Extracts the settings from a Microsoft Calculator package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="12d29-176">修復-UevTemplateIndex</span><span class="sxs-lookup"><span data-stu-id="12d29-176">Repair-UevTemplateIndex</span></span></p></td>
    <td align="left"><p><span data-ttu-id="12d29-177">UE-V 設定の場所テンプレートのインデックスを修復します。</span><span class="sxs-lookup"><span data-stu-id="12d29-177">Repairs the index of the UE-V settings location templates.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="12d29-178">WMI を使用して UE-V エージェントを構成するには</span><span class="sxs-lookup"><span data-stu-id="12d29-178">To configure the UE-V Agent by using WMI</span></span>**

1.  <span data-ttu-id="12d29-179">ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="12d29-179">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="12d29-180">管理者は、このインターフェイスを使用して、コマンドラインで UE-V エージェントを構成し、一般的な構成タスクを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="12d29-180">Administrators can use this interface to configure the UE-V agent at the command line and automate typical configuration tasks.</span></span>

    <span data-ttu-id="12d29-181">管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="12d29-181">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="12d29-182">次の WMI コマンドを使用して、エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-182">Use the following WMI commands to configure the agent.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="12d29-183">説明</span><span class="sxs-lookup"><span data-stu-id="12d29-183">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p><span data-ttu-id="12d29-184">アクティブな UE-V Agent の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="12d29-184">Displays the active UE-V Agent settings.</span></span> <span data-ttu-id="12d29-185">ユーザー固有の設定はコンピューターの設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="12d29-185">User-specific settings have precedence over the computer settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-186">ユーザーに対して定義されている UE-V エージェント構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="12d29-186">Displays the UE-V Agent configuration that is defined for a user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-187">コンピューターに対して定義されている UE-V エージェント構成を表示します。</span><span class="sxs-lookup"><span data-stu-id="12d29-187">Displays the UE-V Agent configuration that is defined for a computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-188">各構成項目の詳細を表示します。</span><span class="sxs-lookup"><span data-stu-id="12d29-188">Displays the details for each configuration item.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><span data-ttu-id="12d29-189">$config。Put ()</span><span class="sxs-lookup"><span data-stu-id="12d29-189">$config.Put()</span></span></p></td>
    <td align="left"><p><span data-ttu-id="12d29-190">コンピューターごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="12d29-190">Defines a per-computer settings storage location.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-191">ユーザーごとの設定の保存場所を定義します。</span><span class="sxs-lookup"><span data-stu-id="12d29-191">Defines a per-user settings storage location.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-192">コンピューターのすべてのユーザーに対して同期のタイムアウトをミリ秒単位で設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-192">Sets the synchronization time-out in milliseconds for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-193">設定パッケージファイルサイズが定義されたしきい値に達したときに報告するように UE-V エージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="12d29-193">Configures the UE-V Agent to report when a settings package file size reaches a defined threshold.</span></span> <span data-ttu-id="12d29-194">コンピューターのすべてのユーザーに対して、しきい値パッケージのファイルサイズ (バイト単位) を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-194">Set the threshold package file size in bytes for all users of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-195">コンピューターのすべてのユーザー (SyncProvider または None) の同期方法を設定します。</span><span class="sxs-lookup"><span data-stu-id="12d29-195">Sets the synchronization method for all users of the computer: SyncProvider or None.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-196">特定のコンピューター単位の設定を有効にするには、設定をオフにして、 <em> </em> 設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="12d29-196">To enable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="12d29-197">ユーザーごとの設定には UserConfiguration を使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-197">Use UserConfiguration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-198">特定のコンピューター単位の設定を無効にするには、設定をオフにして、 <em> </em> 設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="12d29-198">To disable a specific per-computer setting, clear the setting, and use <em>$null</em> as the setting value.</span></span> <span data-ttu-id="12d29-199">ユーザーごとの設定にはユーザー構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-199">Use User Configuration for per-user settings.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-200">特定のコンピューター単位の設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="12d29-200">Updates a specific per-computer setting.</span></span> <span data-ttu-id="12d29-201">設定をクリアするには <em> 、 </em> 設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="12d29-201">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code><span data-ttu-id="12d29-202">$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</span><span class="sxs-lookup"><span data-stu-id="12d29-202">$config.&lt;setting name&gt; = &lt;setting value&gt;</span></span></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-203">コンピューターのすべてのユーザーに対して、特定のユーザーごとの設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="12d29-203">Updates a specific per-user setting for all users of the computer.</span></span> <span data-ttu-id="12d29-204">設定をクリアするには <em> 、 </em> 設定値として $null を使います。</span><span class="sxs-lookup"><span data-stu-id="12d29-204">To clear the setting, use <em>$null</em> as the setting value.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**<span data-ttu-id="12d29-205">WMI を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復するには</span><span class="sxs-lookup"><span data-stu-id="12d29-205">To export UE-V package settings and repair UE-V templates by using WMI</span></span>**

1.  <span data-ttu-id="12d29-206">UE-V は、次の WMI コマンドのセットを提供します。</span><span class="sxs-lookup"><span data-stu-id="12d29-206">UE-V provides the following set of WMI commands.</span></span> <span data-ttu-id="12d29-207">管理者は、このインターフェイスを使用して、パッケージをエクスポートするか、UE-V テンプレートを修復することができます。</span><span class="sxs-lookup"><span data-stu-id="12d29-207">Administrators can use this interface to export a package or repair UE-V templates.</span></span>

2.  <span data-ttu-id="12d29-208">次の WMI コマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="12d29-208">Use the following WMI commands.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="12d29-209">WMI コマンド</span><span class="sxs-lookup"><span data-stu-id="12d29-209">WMI command</span></span></th>
    <th align="left"><span data-ttu-id="12d29-210">説明</span><span class="sxs-lookup"><span data-stu-id="12d29-210">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-211">パッケージファイルから設定を抽出し、その設定を XML で判読可能な形式に変換します。</span><span class="sxs-lookup"><span data-stu-id="12d29-211">Extracts the settings from a package file and converts them into a human-readable format in XML.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p><span data-ttu-id="12d29-212">UE-V 設定の場所テンプレートのインデックスを修復します。</span><span class="sxs-lookup"><span data-stu-id="12d29-212">Repairs the index of the UE-V settings location templates.</span></span> <span data-ttu-id="12d29-213">管理者として実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="12d29-213">Must be run as administrator.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## <span data-ttu-id="12d29-214">関連トピック</span><span class="sxs-lookup"><span data-stu-id="12d29-214">Related topics</span></span>


[<span data-ttu-id="12d29-215">Windows PowerShell と WMI を使用した UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="12d29-215">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="12d29-216">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="12d29-216">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









