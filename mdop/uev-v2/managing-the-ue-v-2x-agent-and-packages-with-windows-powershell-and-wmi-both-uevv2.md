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
# Windows PowerShell と WMI で UE-V Agent とパッケージを管理する


Windows Management Instrumentation (WMI) と Windows PowerShell を使用して、Microsoft User Experience Virtualization (UE-V) 2.0、2.1、および 2.1 SP1 エージェントの構成と同期動作を管理することができます。 UE-V PowerShell コマンドレットの完全な一覧については、「 [ue-v 2 コマンドレットリファレンス](https://go.microsoft.com/fwlink/?LinkId=393495)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=393495) 。

**Windows PowerShell を使用して UE-V Agent を展開するには**

1.  UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。

    **注**  
    AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。 Windows Installer パッケージ、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。 インストールファイルを使用して、後で UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。



2.  UE-V Agent をインストールするには、次の Windows PowerShell コマンドのいずれかを使用します。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**Windows PowerShell を使用して UE-V Agent を構成するには**

1. Windows PowerShell ウィンドウを開きます。 *コンピューターのパラメーターを*使用してコンピューターのすべてのユーザーに影響を与えるコンピューター設定を管理するには、管理者権限のあるアカウントでウィンドウを開きます。

2. 次の Windows PowerShell コマンドを使用して、エージェントを構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">Windows PowerShell コマンド</th>
   <th align="left">説明</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p>有効な UE-V Agent 設定を取得します。 ユーザー固有の設定はコンピューターの設定よりも優先されます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p>現在のユーザーのみの UE-V Agent settings の値を取得します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーの UE-V Agent 構成設定の値を取得します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p>各構成設定の詳細を取得します。 設定が構成されている場所、または既定値を使用するかどうかを表示します。 現在の設定が有効であるかどうかが表示されます。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p>[会社の設定] センターに表示される [ヘルプ] リンクのテキストを設定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p>[ヘルプ] リンクの [会社設定センター] のリンクの URL を設定します。 任意の URL プロトコルを使うことができます。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーの Windows アプリを同期しないように UE-V エージェントを構成します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>現在のコンピューターユーザーの Windows アプリを同期しないように UE-V エージェントを構成します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーに対して初めてエージェントを実行したときの通知を表示するように、UE-V Agent を構成します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーに対して初めてエージェントを実行するときに、UE-V Agent が通知を表示しないように構成します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>設定の同期が遅延したときに、コンピューター上のすべてのユーザーに対して UE-V Agent が通知されるように構成します。</p>
   <p><em>Disablesettingシム portnotify パラメーターを使って </em> 通知を無効にします。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>設定の同期が遅延したときに、現在のユーザーに通知するように UE-V Agent を構成します。</p>
   <p><em>Disablesettingシム portnotify パラメーターを使って </em> 通知を無効にします。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーに対して、Windows アプリの一覧によって明示的に無効になっていないすべての Windows アプリを同期するように UE-V Agent を構成します。 詳細については、「 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> WINDOWS PowerShell と WMI を使用して Ue-v の UevAppxPackage 設定の場所テンプレートを管理 </a> する」を参照してください。</p>
   <p><em> </em> Windows アプリリストによって明示的に有効になっている windows アプリのみを同期するように ue-v agent を構成するには、DisableSyncUnlistedWindows8Apps パラメーターを使用します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>コンピューター上の現在のユーザーの Windows アプリリストによって明示的に無効になっていないすべての Windows アプリを同期するように UE-V Agent を構成します。 詳細については、「 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> WINDOWS PowerShell と WMI を使用して Ue-v の UevAppxPackage 設定の場所テンプレートを管理 </a> する」を参照してください。</p>
   <p><em> </em> Windows アプリリストによって明示的に有効になっている windows アプリのみを同期するように ue-v agent を構成するには、DisableSyncUnlistedWindows8Apps パラメーターを使用します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーに対して UE-V を無効にします。</p>
   <p>EnableSync パラメーターを使って、 <em> </em> 有効または有効にします。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p>コンピューターの現在のユーザーに対して UE-V を無効にします。</p>
   <p>EnableSync パラメーターを使って、 <em> </em> 有効または有効にします。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーの通知領域の UE-V アイコンを有効にします。</p>
   <p>アイコンを <em> </em> 無効にするには、DisableTrayIcon パラメーターを使用します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>設定パッケージファイルサイズが、コンピューター上のすべてのユーザーに対して定義されたしきい値に達したときに報告するように、UE-V agent を構成します。 しきい値パッケージサイズ (バイト単位) を設定します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>設定パッケージファイルサイズが定義されたしきい値に達したときに報告するように UE-V エージェントを構成します。 現在のユーザーのパッケージサイズの警告しきい値を設定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーに対してユーザーに通知するまでの時間 (秒単位) を指定します</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>現在のユーザーの通知が送信されるまでの時間 (秒単位) を指定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーに対して、コンピューターごとの設定の保存場所を定義します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>ユーザーごとの設定の保存場所を定義します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーの設定テンプレートカタログのパスを設定します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザー (SyncProvider または None) の同期方法を設定します。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>現在のユーザーの同期方法を設定します。 SyncProvider または None。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>コンピューターのすべてのユーザーに対して同期のタイムアウト (ミリ秒単位) を設定します</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>現在のユーザーの同期タイムアウトを設定します。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>コンピューター上のすべてのユーザーに対して指定された設定をクリアします。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>現在のユーザーのみに指定された設定をクリアします。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>UE-V コンピューターの構成を設定移行ファイルにエクスポートします。 ファイル名拡張子は uev である必要があります。</p>
   <p>この <code>Export</code> コマンドレットは、Computer パラメーターで構成可能なすべての Ue-v agent 設定をエクスポートし <em> </em> ます。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>設定移行ファイルから UE-V のコンピューター構成をインポートします。 ファイル名拡張子は uev である必要があります。</p></td>
   </tr>
   </tbody>
   </table>



**Windows PowerShell を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復するには**

1.  管理者として Windows PowerShell ウィンドウを開きます。

2.  次の Windows PowerShell コマンドを使用して、エージェントを構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>Windows PowerShell コマンド</strong></p></td>
    <td align="left"><p><strong>説明</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>エクスポート-UevPackage MicrosoftCalculator6 x</p></td>
    <td align="left"><p>Microsoft の電卓パッケージファイルから設定を抽出し、XML で判読可能な形式に変換します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>修復-UevTemplateIndex</p></td>
    <td align="left"><p>UE-V 設定の場所テンプレートのインデックスを修復します。</p></td>
    </tr>
    </tbody>
    </table>



**WMI を使用して UE-V エージェントを構成するには**

1.  ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。 管理者は、このインターフェイスを使用して、コマンドラインで UE-V エージェントを構成し、一般的な構成タスクを自動化することができます。

    管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。

2.  次の WMI コマンドを使用して、エージェントを構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p>アクティブな UE-V Agent の設定を表示します。 ユーザー固有の設定はコンピューターの設定よりも優先されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p>ユーザーに対して定義されている UE-V エージェント構成を表示します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p>コンピューターに対して定義されている UE-V エージェント構成を表示します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p>各構成項目の詳細を表示します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>コンピューターごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>ユーザーごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>コンピューターのすべてのユーザーに対して同期のタイムアウトをミリ秒単位で設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>設定パッケージファイルサイズが定義されたしきい値に達したときに報告するように UE-V エージェントを構成します。 コンピューターのすべてのユーザーに対して、しきい値パッケージのファイルサイズ (バイト単位) を設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>コンピューターのすべてのユーザー (SyncProvider または None) の同期方法を設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>特定のコンピューター単位の設定を有効にするには、設定をオフにして、 <em> </em> 設定値として $null を使います。 ユーザーごとの設定には UserConfiguration を使用します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>特定のコンピューター単位の設定を無効にするには、設定をオフにして、 <em> </em> 設定値として $null を使います。 ユーザーごとの設定にはユーザー構成を使用します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>特定のコンピューター単位の設定を更新します。 設定をクリアするには <em> 、 </em> 設定値として $null を使います。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code>$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>コンピューターのすべてのユーザーに対して、特定のユーザーごとの設定を更新します。 設定をクリアするには <em> 、 </em> 設定値として $null を使います。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**WMI を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復するには**

1.  UE-V は、次の WMI コマンドのセットを提供します。 管理者は、このインターフェイスを使用して、パッケージをエクスポートするか、UE-V テンプレートを修復することができます。

2.  次の WMI コマンドを使用します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">WMI コマンド</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p>パッケージファイルから設定を抽出し、その設定を XML で判読可能な形式に変換します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p>UE-V 設定の場所テンプレートのインデックスを修復します。 管理者として実行する必要があります。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## 関連トピック


[Windows PowerShell と WMI を使用した UE-V 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)









