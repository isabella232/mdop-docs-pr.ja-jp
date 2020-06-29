---
title: Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する
description: Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812882"
---
# Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 では、ユーザーエクスペリエンスの仮想化と適用される設定を定義するために XML 設定の場所テンプレートを使用しています。 UE-V には、標準設定の場所テンプレートのセットが含まれています。 また、カスタム設定の場所テンプレートを作成できる UE-V Generator ツールも含まれています。 設定場所テンプレートを作成して展開した後は、Windows PowerShell と Windows Management Instrumentation (WMI) を使って、これらのテンプレートを管理できます。 UE-V PowerShell コマンドレットの完全な一覧については、「 [ue-v 2 コマンドレットリファレンス](https://go.microsoft.com/fwlink/p/?LinkId=393495)(」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=393495) 。

## Windows PowerShell を使用して UE-V 2 設定の場所テンプレートを管理する


UE-V の WMI および Windows PowerShell 機能には、設定場所テンプレートの有効化、無効化、登録、更新、および登録解除の機能が含まれています。 これらの機能を使用すると、テンプレートの登録、更新、または登録解除のプロセスを、UE-V Agent で自動化することができます。 また、WMI コマンドと Windows PowerShell コマンドを使用して、手動でテンプレートを登録することもできます。 これらの機能を電子的なソフトウェア配布ソリューション、グループポリシー、またはスクリプトなどの自動化された展開方法と組み合わせて使用することで、そのプロセスをさらに自動化することができます。

設定場所テンプレートの更新、登録、または登録解除を行うには、管理者権限が必要です。 テンプレートを有効または無効にするには、管理者権限は必要ありません。

***<em>Windows PowerShell を使用して設定場所テンプレートを管理するにはell</em>***

1.  管理者権限を持つアカウントを使用して、Windows PowerShell コマンドプロンプトを開きます。

2.  次の Windows PowerShell コマンドレットを使用して、UE-V 設定の場所テンプレートを登録および管理します。

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
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p>コンピューターに登録されているすべての設定場所テンプレートを一覧表示します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p>アプリケーション名またはテンプレート名に文字列が含まれているコンピューターに登録されているすべての設定場所テンプレートを一覧表示し &lt; &gt; ます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p>テンプレート ID に文字列が含まれているコンピューターに登録されているすべての設定の場所テンプレートを一覧表示し &lt; &gt; ます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p>アプリケーションまたはテンプレートの名前、またはテンプレート ID に文字列が含まれているコンピューターに登録されているすべての設定場所テンプレートを一覧表示し &lt; &gt; ます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>テンプレート ID に依存するプログラムの名前とバージョン情報を取得します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p>Windows アプリの有効な一覧を取得します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p>コンピューターに対して構成されている Windows アプリの一覧を取得します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>現在のユーザーに対して構成されている Windows アプリの一覧を取得します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>相対パスまたはワイルドカード文字を使用して、UE-V を使って1つまたは複数の設定場所テンプレートを登録します。 テンプレートが登録されると、UE-V は、テンプレートが登録されているコンピューター間のテンプレートで定義された設定を同期します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>リテラルパスを使用して、1つまたは複数の設定場所テンプレートを UE-V に登録します。このテンプレートでは、ワイルドカード文字として解釈することはできません。 テンプレートが登録されると、UE-V は、テンプレートが登録されているコンピューター間のテンプレートで定義された設定を同期します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>UE-V を使用して、設定場所テンプレートの登録を解除します。 テンプレートの登録を解除すると、UE-V は、テンプレートで定義されているコンピューター間の設定を同期しなくなります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p>UE-V を使用して、設定場所テンプレートの登録をすべて解除します。 テンプレートの登録を解除すると、UE-V は、テンプレートで定義されているコンピューター間の設定を同期しなくなります。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>テンプレートの最新バージョンを使用して、1つまたは複数の設定場所テンプレートを更新します。 ファイルパスには、相対パスまたはワイルドカード文字を使用します。 新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>テンプレートの最新バージョンを使用して、1つまたは複数の設定場所テンプレートを更新します。 テンプレートファイルには完全なパスを使用します。ここでは、ワイルドカード文字として解釈できる文字はありません。 新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧から Windows アプリを削除します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧からすべての Windows アプリを削除します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧からすべての Windows アプリを削除します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>コンピューターの現在のユーザーの設定場所テンプレートを無効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>コンピューターの現在のユーザーの設定場所テンプレートを有効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを有効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを有効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>1つまたは複数の設定場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。 相対パスとワイルドカード文字を使うことができます。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>1つまたは複数の設定場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。 パスには、テンプレートファイルへのフルパスを指定する必要がありますが、ワイルドカード文字は含まれません。</p></td>
    </tr>
    </tbody>
    </table>



UE-V Windows PowerShell 機能を使用すると、企業に展開される設定テンプレートのグループを管理できます。 Windows PowerShell を使用してテンプレートのグループを管理するには、次の手順を使用します。

**Windows PowerShell を使用して設定場所テンプレートのグループを管理するには**

1.  目的の設定の場所テンプレートを変更または更新します。

2.  設定の場所テンプレートを変更または更新する場合は、ローカルコンピューターからアクセスできるフォルダーに設定場所テンプレートを展開します。

3.  ローカルコンピューターで、管理者権限で Windows PowerShell ウィンドウを開きます。

4.  次のコマンドを入力して、以前に登録されたすべてのバージョンのテンプレートの登録を解除します。

    ``` syntax
    Unregister-UevTemplate -All
    ```

    このコマンドは、コンピューター上のすべてのアクティブなテンプレートの登録を解除します。

5.  次のコマンドを入力して、更新されたテンプレートを登録します。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    このコマンドによって、指定したテンプレートフォルダーにあるすべての設定場所テンプレートが登録されます。

### <a href="" id="win8applist"></a>Windows アプリの一覧

Windows アプリの一覧に Windows アプリの一覧を表示することで、そのアプリが設定の同期に対して有効または無効になるかどうかを指定します。 アプリは、パッケージファミリ名によって一覧に表示され、そのアプリで設定の同期を有効または無効にするかどうかを指定します。 これらの設定を、一覧表示されていない既定の同期動作設定と共に使用すると、Windows アプリを同期するかどうかを制御できます。

インストールされている Windows アプリのパッケージファミリ名を表示するには、Windows PowerShell コマンドプロンプトで次のように入力します。

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

Windows PowerShell のコマンドプロンプトで、コンピューターの設定をパッケージファミリ名、有効状態、有効なソースに同期できる Windows アプリの一覧を表示するには、次のように入力します。 `Get-UevAppxPackage`

**UevAppxPackage プロパティの定義**

<a href="" id="displayname"></a>**DisplayName**  
会社設定センターアプリケーションでユーザーに表示される名前です。 `DisplayName`プロパティはプロパティから派生し `PackageFamilyName` ます。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
現在のユーザー用にインストールされているパッケージの名前です。

<a href="" id="enabled"></a>**有効**  
アプリの設定を同期するように構成するかどうかを定義します。

<a href="" id="enabledsource"></a>**EnabledSource**  
アプリを有効または無効にする構成が設定されている場所。 指定できる値は、 *NotSet*、 *LocalMachine*、 *LocalUser*、 *policymachine*、 *policymachine*です。

<a href="" id="notset"></a>**NotSet**  
ポリシーはこのアプリを同期するように構成されていません。

<a href="" id="localmachine"></a>**LocalMachine**  
有効状態は、レジストリの [ローカルコンピューター] セクションで設定します。

<a href="" id="localuser"></a>**LocalUser**  
有効状態は、レジストリの [現在のユーザー] セクションで設定します。

<a href="" id="policymachine"></a>**PolicyMachine**  
有効状態は、レジストリの [ローカルコンピューター] セクションの [ポリシー] セクションで設定します。

Windows アプリのユーザーが設定した一覧を取得するには、Windows PowerShell コマンドプロンプトで次のように入力します。 `Get-UevAppxPackage –CurrentComputerUser`

コンピューターで構成された Windows アプリの一覧を取得するには、Windows PowerShell コマンドプロンプトで次のように入力します。 `Get-UevAppxPackage –Computer`

CurrentComputerUser または Computer のいずれかの場合、コマンドレットは、ユーザーまたはコンピューターレベルで構成されている Windows アプリの一覧を返します。

**プロパティの定義**

<a href="" id="displayname"></a>**DisplayName**  
会社設定センターアプリケーションでユーザーに表示される名前です。 `DisplayName`プロパティはプロパティから派生し `PackageFamilyName` ます。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
現在のユーザー用にインストールされているパッケージの名前です。

<a href="" id="enabled"></a>**有効**  
指定したスイッチ (**ユーザー**または**コンピューター**) に対して、アプリの設定を同期するように構成するかどうかを定義します。

<a href="" id="installed"></a>**インストール済み**  
アプリが、現在のユーザーに対して、"パッケージ" という名前のアプリがインストールされている場合は True です。

### WMI を使用して UE-V 2 設定場所テンプレートを管理する

ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。 管理者は、これらのインターフェイスを使って、Windows PowerShell から設定場所テンプレートを管理し、テンプレートの管理タスクを自動化することができます。

**WMI を使用して設定場所テンプレートを管理するには**

1.  管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。

2.  次の WMI コマンドを使用して、UE-V 設定の場所テンプレートを登録および管理します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p>コンピューターに登録されているすべての設定場所テンプレートを一覧表示します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p>テンプレート名に応じて、プログラムの名前とバージョン情報を取得します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p>Windows アプリの有効な一覧を取得します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-名前空間 root\Microsoft\UEV MachineConfiguredWindows8App</p></td>
    <td align="left"><p>コンピューターに対して構成されている Windows アプリの一覧を取得します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p>現在のユーザーに対して構成されている Windows アプリの一覧を取得します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p>設定場所テンプレートを UE-V に登録します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>UE-V を使用して、設定場所テンプレートの登録を解除します。 テンプレートの登録が解除されるとすぐに、UE-V はテンプレートで定義されている設定をコンピューター間で同期しなくなります。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>UE-V を使用して設定場所テンプレートを更新します。 新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>UE-V を使用して、1つ以上の設定場所テンプレートを無効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>UE-V を使用して設定場所テンプレートを有効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>コンピューターの Windows アプリリストで Windows アプリを有効にします。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>現在のユーザーの Windows アプリの一覧で Windows アプリを有効にします。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### Windows PowerShell を使用した UE-V エージェントの展開

**Windows PowerShell を使用して UE-V Agent を展開する方法**

1.  UE-V Agent インストールパッケージを、アクセス可能なネットワーク共有にステージします。

    **注**  
    AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。 Windows Installer パッケージ、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。 インストールファイルを使用して、後で UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。



2.  UE-V Agent をインストールするには、次の Windows PowerShell コマンドのいずれかを使用します。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**Ue-v のご提案をお寄せ**ください。 [ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。 **Ue-v の問題が発生した場合** Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。

## 関連トピック


[Windows PowerShell と WMI を使用した UE-V 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)









