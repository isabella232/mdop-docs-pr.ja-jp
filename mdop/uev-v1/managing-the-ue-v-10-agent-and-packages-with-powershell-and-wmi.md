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
# PowerShell と WMI を使用した UE-V 1.0 エージェントの管理


WMI と PowerShell を使用して、Microsoft User Experience Virtualization (UE-V) エージェントの構成と同期動作を管理することができます。

**PowerShell で UE-V agent を展開する方法**

1.  UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。

    **注**  
    AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。 Windows Installer ファイルのバージョン、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。 インストールファイルを使用して後から UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。



2.  エージェントをインストールするには、次の PowerShell コマンドのいずれかを使用します。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**PowerShell を使用して UE-V Agent を構成する方法**

1.  管理者権限を持つアカウントを使用して、PowerShell ウィンドウを開くことができます。 次のコマンドを使用して、UE-V PowerShell モジュールをインポートします。

    ``` syntax
    Import-module UEV
    ```

2.  次の PowerShell コマンドを使用して、エージェントを構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell コマンド</strong></p></td>
    <td align="left"><p><strong>説明</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Get-UevConfiguration</p>
    <p></p></td>
    <td align="left"><p>有効な UE-V agent の設定を表示します。 ユーザー固有の設定はコンピューターの設定よりも優先されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Get-UevConfiguration-CurrentComputerUser</p>
    <p></p></td>
    <td align="left"><p>現在のユーザーのみの UE-V agent settings の値を表示します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Get-UevConfiguration-コンピューター</p></td>
    <td align="left"><p>コンピューター上のすべてのユーザーの UE-V agent 構成設定の値を表示します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-コンピューターの設定 Storagepath &lt; パス _settings_storage_location&gt;</p></td>
    <td align="left"><p>コンピューターごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UevConfiguration-CurrentComputerUser-SettingsStoragePath の &lt; _settings_storage_location&gt;</p></td>
    <td align="left"><p>ユーザーごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-コンピューター-SyncTimeoutInMilliseconds &lt; タイムアウト (ミリ秒)&gt;</p></td>
    <td align="left"><p>同期タイムアウトをミリ秒単位で設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds &lt; タイムアウト (ミリ秒)&gt;</p></td>
    <td align="left"><p>現在のユーザーの同期タイムアウトを設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-コンピューター-Maxパッケージ Izeinbytes &lt; size (バイト単位)&gt;</p></td>
    <td align="left"><p>設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成します。 しきい値のパッケージサイズをバイト単位で設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UevConfiguration-CurrentComputerUser-Maxパッケージ Izeinbytes &lt; size (バイト単位)&gt;</p></td>
    <td align="left"><p>現在のユーザーに対してパッケージサイズの警告のしきい値を設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration – Computer – &lt; catalog To SettingsTemplateCatalogPath path&gt;</p></td>
    <td align="left"><p>設定テンプレートカタログのパスを設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UevConfiguration-コンピューター-SyncMethod の &lt; 同期方法&gt;</p></td>
    <td align="left"><p>同期方法 (OfflineFiles または None) を設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-CurrentComputerUser-SyncMethod の &lt; 同期方法&gt;</p></td>
    <td align="left"><p>現在のユーザー: OfflineFiles または None の同期方法を設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UEVConfiguration-Computer – Enablesettingシム Portnotify</p></td>
    <td align="left"><p>[ユーザー設定のインポート] の遅延が発生した場合に通知が表示されるようにします。</p>
    <p>-Disablesettingシム Portnotify を使用して通知を無効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-Enablesettingシム通知</p></td>
    <td align="left"><p>ユーザー設定のインポートが延期された場合に、現在のユーザーに対して通知を有効にします。</p>
    <p>-Disablesettingシム Portnotify を使用して通知を無効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UEVConfiguration-コンピューター-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>ユーザーに通知するまでの時間 (秒単位) を指定する</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>現在のユーザーに通知するまでの時間 (秒単位) を指定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Set-UevConfiguration – Computer – DisableSync</p></td>
    <td align="left"><p>コンピューター上のすべてのユーザーに対して UE-V を無効にします。</p>
    <p>– EnableSync を使用して、有効または有効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration – CurrentComputerUser-DisableSync</p></td>
    <td align="left"><p>コンピューター上の現在のユーザーに対して UE-V を無効にします。</p>
    <p>– EnableSync を使用して、有効または有効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>クリア-UevConfiguration –コンピューターの &lt; 設定名&gt;</p></td>
    <td align="left"><p>コンピューター上のすべてのユーザーの特定の設定をクリアします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>クリア-UevConfiguration – CurrentComputerUser &lt; 設定名&gt;</p></td>
    <td align="left"><p>現在のユーザーに対してのみ、特定の設定をクリアします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>エクスポート-UevConfiguration &lt; settings 移行ファイル&gt;</p></td>
    <td align="left"><p>UE-V のコンピューター構成を設定移行ファイルにエクスポートします。 ファイルの拡張子は "uev" である必要があります。</p>
    <p>エクスポートコマンドレットは、-computer パラメーターで構成可能なすべての UE-V agent 設定をエクスポートします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>インポート-UevConfiguration &lt; settings 移行ファイル&gt;</p></td>
    <td align="left"><p>設定移行ファイル (uev ファイル) から UE-V のコンピューター構成をインポートします。</p></td>
    </tr>
    </tbody>
    </table>



**PowerShell を使用して UE-V パッケージ設定をエクスポートして UE-V テンプレートを修復する方法**

1.  管理者として PowerShell ウィンドウを開きます。 次のコマンドを使用して、UE-V PowerShell モジュールをインポートします。

    ``` syntax
    Import-module UEV
    ```

2.  次の PowerShell コマンドを使用して、エージェントを構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell コマンド</strong></p></td>
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



**WMI を使用して UE-V Agent を構成する方法**

1.  ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。 管理者は、このインターフェイスを使用して、コマンドラインから UE-V エージェントを構成し、一般的な構成タスクを自動化することができます。

    管理者権限を持つアカウントを使用して、PowerShell ウィンドウを開くことができます。

2.  次の WMI コマンドを使用して、エージェントを構成します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">PowerShell コマンド</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>WmiObject-名前空間 root\Microsoft\UEV 構成</p>
    <p></p></td>
    <td align="left"><p>アクティブな UE-V agent の設定を表示します。 ユーザー固有の設定はコンピューターの設定よりも優先されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV UserConfiguration</p></td>
    <td align="left"><p>ユーザーに対して定義されている UE-V agent 構成を表示します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p></td>
    <td align="left"><p>コンピューターに対して定義されている UE-V エージェント構成を表示します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>コンピューターごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV UserConfiguration</p>
    <p>$config。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>ユーザーごとの設定の保存場所を定義します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>同期タイムアウトをミリ秒単位で設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。Maxパッケージ Izeinbytes = &lt; size_in_bytes&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>設定パッケージのファイルサイズが定義されたしきい値に達したときに報告するように UE-V agent を構成します。 しきい値パッケージのファイルサイズをバイト単位で設定します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。SyncMethod = &lt; sync_method&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>同期方法 (OfflineFiles または None) を設定します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>特定のコンピューター単位の設定を更新します。 設定をクリアするには、設定値として $null を使います。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config。 &lt;設定名の &gt;  =  &lt; 設定値&gt;</p>
    <p>$config。Put ()</p></td>
    <td align="left"><p>特定のユーザーごとの設定を更新します。 設定をクリアするには、設定値として $null を使います。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## 関連トピック


[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)









