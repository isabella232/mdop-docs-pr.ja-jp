---
title: PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理
description: PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812491"
---
# PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理


Microsoft User Experience Virtualization (UE-V) では、ユーザーエクスペリエンスの仮想化によってキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) を使用します。 UE-V には、標準設定の場所テンプレートのセットが含まれています。 また、カスタム設定の場所テンプレートを作成できる UE-V Generator ツールも含まれています。 設定場所テンプレートを作成して展開すると、PowerShell または WMI を使ってそれらのテンプレートを管理できます。

## WMI と PowerShell を使用して設定場所テンプレートを管理する


UE-V の WMI および PowerShell 機能には、設定場所テンプレートの有効化、無効化、登録、更新、および登録解除機能が含まれています。 これらの機能を使用すると、テンプレートの登録、更新、または登録解除のプロセスを、UE-V agent で自動化することができます。 また、WMI コマンドと PowerShell コマンドを使って手動でテンプレートを登録することもできます。 これらの機能を電子的なソフトウェア配布ソリューション、グループポリシー、またはスクリプトなどの自動化された展開方法と組み合わせて使用することで、そのプロセスをさらに自動化することができます。

設定場所テンプレートの更新、登録、または登録解除を行うには、管理者権限が必要です。 テンプレートを有効または無効にするには、管理者権限は必要ありません。

**PowerShell を使用して設定場所テンプレートを管理するには**

1.  管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。 **MICROSOFT Ue-v powershell**モジュールをインポートするには、PowerShell コマンドプロンプトで次のコマンドを入力します。

    ``` syntax
    Import-module UEV
    ```

2.  次の PowerShell コマンドレットを使用して、UE-V 設定の場所テンプレートを登録および管理します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell コマンド</strong></th>
    <th align="left"><strong>説明</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>取得-UevTemplate</p></td>
    <td align="left"><p>コンピューターに登録されているすべての設定場所テンプレートの一覧が表示されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>登録-UevTemplate</p></td>
    <td align="left"><p>設定場所テンプレートを UE-V に登録します。 テンプレートが登録されると、UE-V によってテンプレートが登録されているコンピューター間のテンプレートで定義された設定が同期されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>登録解除-UevTemplate</p></td>
    <td align="left"><p>UE-V を使用して、設定場所テンプレートの登録を解除します。 テンプレートの登録を解除すると、そのテンプレートで定義されている設定が、UE-V によってコンピューター間で同期されなくなります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>更新-UevTemplate</p></td>
    <td align="left"><p>テンプレートの最新バージョンを使用して、設定場所テンプレートを更新します。 新しいテンプレートには、既存のテンプレートよりも新しいバージョンが含まれている必要があります。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>無効-UevTemplate</p></td>
    <td align="left"><p>コンピューターの現在のユーザーの設定場所テンプレートを無効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Enable-UevTemplate</p></td>
    <td align="left"><p>コンピューターの現在のユーザーの設定場所テンプレートを有効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>テスト-UevTemplate</p></td>
    <td align="left"><p>指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</p></td>
    </tr>
    </tbody>
    </table>

     

UE-V PowerShell 機能を使用すると、エンタープライズで展開された設定テンプレートのグループを管理できます。 PowerShell を使用してテンプレートのグループを管理するには、次の操作を行います。

**PowerShell を使用して設定場所テンプレートのグループを管理するには**

1.  目的の設定の場所テンプレートを変更または更新します。

2.  ローカルコンピューターでアクセス可能なフォルダーに、目的の設定の場所テンプレートを配置します。

3.  ローカルコンピューターで、管理者権限で Windows PowerShell ウィンドウを開きます。

4.  次のコマンドを入力して、Microsoft UE-V PowerShell モジュールをインポートします。

    ``` syntax
    Import-module UEV
    ```

5.  次のコマンドを入力して、以前に登録されたすべてのバージョンのテンプレートの登録を解除します。

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    これにより、コンピューター上のすべてのアクティブなテンプレートの登録が解除されます。

6.  次のコマンドを入力して、更新されたテンプレートを登録します。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    指定されたテンプレートフォルダーにあるすべての設定場所テンプレートを登録します。

ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。 管理者は、これらのインターフェイスを使って、Windows PowerShell から設定場所テンプレートを管理し、テンプレートの管理タスクを自動化することができます。

**WMI を使用して設定場所テンプレートを管理するには**

1.  管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。

2.  次の WMI コマンドを使用して、UE-V 設定の場所テンプレートを登録および管理します。

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
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV SettingsLocationTemplate |Select-Object TemplateId、TemplateName、TemplateVersion、Enabled |書式設定-表-Autosize</p></td>
    <td align="left"><p>コンピューターに登録されているすべての設定場所テンプレートの一覧が表示されます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate-Name Register-ArgumentList &lt; template path&gt;</p></td>
    <td align="left"><p>設定場所テンプレートを UE-V に登録します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name UnregisterByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</p></td>
    <td align="left"><p>UE-V を使用して、設定場所テンプレートの登録を解除します。 テンプレートの登録を解除すると、そのテンプレートで定義されている設定が、UE-V によってコンピューター間で同期されなくなります。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name EnableByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</p></td>
    <td align="left"><p>UE-V を使用して設定場所テンプレートを有効にします</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name DisableByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</p></td>
    <td align="left"><p>UE-V を使用して設定場所テンプレートを無効にします</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name Update-ArgumentList &lt; template path&gt;</p></td>
    <td align="left"><p>UE-V を使用して設定場所テンプレートを更新します。 新しいテンプレートには、既存のテンプレートよりも高いバージョンが含まれている必要があります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name Validate-ArgumentList &lt; template path&gt;</p></td>
    <td align="left"><p>指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</p></td>
    </tr>
    </tbody>
    </table>

     

**PowerShell で UE-V agent を展開する方法**

1.  UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。

    **注** AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。 Windows Installer ファイルのバージョン、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。 インストールファイルを使用して後から UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。

     

2.  エージェントをインストールするには、次の PowerShell コマンドのいずれかを使用します。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## 関連トピック


[PowerShell と WMI を使用した UE-V 1.0 エージェントの管理](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





