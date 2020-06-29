---
title: UE-V 2. x で管理バックアップと復元を管理する
description: UE-V 2. x で管理バックアップと復元を管理する
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827387"
---
# UE-V 2. x で管理バックアップと復元を管理する


Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 の管理者は、アプリケーションと Windows の設定を元の状態に戻すことができます。 さらに、UE-V 2.1 では、ユーザーが新しいデバイスを採用したときに追加設定を復元することもできます。

## ユーザーが新しいデバイスを採用したときに、UE-V 2.1 または UE-V 2.1 SP1 の設定を復元する


ユーザーが新しいデバイスを採用したときに設定を復元するには、Set-UevTemplateProfile PowerShell コマンドレットを使用して、設定場所テンプレートを**バックアップ**または**ローミング (既定)** プロファイルに配置できます。 これにより、ユーザー設定に加えて、コンピューターの設定を新しいコンピューターと同期することができます。 バックアッププロファイルに割り当てられたテンプレートは、そのデバイスにバックアップされ、デバイスごとに構成されます。 テンプレートのバックアップ設定を行うには、Windows PowerShell で次のコマンドレットを使用します。

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   &lt;TemplateID &gt; は Ue-v テンプレート ID です

-   &lt;バックアップ &gt; はバックアップまたはローミングのいずれかになります。

ユーザーのドメイン、ユーザー名、およびデバイス名がすべて一致する場合、ユーザーのデバイスの UE-V を置き換えると、設定が自動的に復元されます。 すべての同期データとバックアップデータは、デバイス上で自動的に復元されます。

新しい PowerShell コマンドレットの Restore-UevBackup を使用して、別のデバイスから設定を復元することもできます。 新しいデバイスの設定パッケージを複製するには、Windows PowerShell の次のコマンドレットを使用します。

``` syntax
Restore-UevBackup –Machine <MachineName>
```

ここで、 &lt; MachineName &gt; はデバイスのコンピューター名です。

多くのアプリケーションが含まれている Office 2013 テンプレートなどのテンプレートは、すべて、ローミング (既定) またはバックアップされたプロファイルに含めることができます。 テンプレートスイート内の個々のアプリは、グループに従います。 Office 2013 の in box テンプレートには、ローミングとバックアップのみの設定が含まれています。 ローミングプロファイルにバックアップ専用の設定を含めることはできません。

バックアップ/復元機能の一部として、UE-V は、[設定] にロールバックするためのオプション**に追加されました。** このリリースでは、元の設定または LKG 設定のいずれかにロールバックすることができます。 LKG 設定を使用すると、ユーザーは設定の事前の中間状態に進んで安定したポイントにロールバックすることができます。

### UE-V を使用してテンプレートをバックアップ/復元する方法

以下は、UE-V の主要なバックアップと復元の構成要素です。

-   テンプレートプロファイル

-   設定の記憶域の場所テンプレート内の設定パッケージの場所

-   バックアップトリガー

-   設定の復元方法

**テンプレートプロファイル**

UE-V のテンプレートプロファイルは、テンプレートがデバイスに登録されたとき、または PowerShell/WMI 構成ユーティリティを使用して登録をポストしたときに定義されます。 プロファイルの種類には、次のものがあります。

-   ローミング (既定)

-   バックアップ

-   BackupOnly

他の指定がない限り、登録時にすべてのテンプレートがローミングプロファイルに含まれます。 これらのテンプレートは、対応するテンプレートが有効になっているすべての UE-V 対応デバイスに設定を同期します。

Set-UevTemplateProfile コマンドレットを使用して、PowerShell または WMI でバックアッププロファイルにテンプレートを追加することができます。 バックアッププロファイルのテンプレートは、これらの設定を、特別なデバイス名ディレクトリの設定の保存場所にバックアップします。 指定した設定は、この場所にバックアップされます。

テンプレート指定のバックアップには、明示的に復元しない限り、同期しないデバイス固有の設定のみが含まれます。 これらの設定は、Backedup 設定として、設定の保存場所のデバイス固有の設定パッケージの同じ場所に格納されます。 これらのテンプレートには、テンプレートに埋め込まれた特別な識別子があり、このプロファイルの一部として指定します。

**設定の記憶域の場所テンプレート内の設定パッケージの場所**

ローミングプロファイル設定は、設定の保存場所に保存されます。 バックアップまたは BackupOnly プロファイルに割り当てられたテンプレートは、特別なデバイス名ディレクトリの設定の保存場所に設定を保存します。 これらのプロファイルのテンプレートを持つ各デバイスには、独自のデバイス名があります。 UE-V はこれらのディレクトリをクリーンアップしません。

**バックアップトリガー**

Backup は、UE-V 同期をトリガーする同じイベントによってトリガーされます。

**設定の復元方法**

ユーザーのデバイスを復元すると、現在登録されているテンプレートの設定が、別のデバイスのバックアップフォルダーと、すべての同期された設定から現在のコンピューターに復元されます。 設定は次の2つの方法で復元されます。

-   **自動復元**

    ユーザーの UE-V 設定の記憶域のパス、ドメイン、コンピューター名が現在のユーザーと一致する場合は、そのユーザーのすべての設定が同期され、最新の設定のみが適用されます。 ユーザーが初めて新しいデバイスにログオンしたときに、これらの条件が満たされた場合、設定データがそのデバイスに適用されます。

    **注**  
    アクセシビリティと Windows デスクトップの設定では、ユーザーが Windows に再ログオンして適用する必要があります。



-   **手動復元**

    更新中にデバイスを復元してユーザーを支援したい場合は、Restore-UevBackup コマンドレットを使用することを選択できます。 このコマンドを実行すると、設定の保存場所からユーザーの設定がダウンロードされます。

## アプリケーションと Windows の設定を元の状態に復元する


WMI コマンドと Windows PowerShell コマンドを使用すると、アプリケーションと Windows の設定を、UE-V Agent をインストールした後に初めてアプリケーションを起動したときにコンピューター上の設定値に復元できます。 この復元アクションは、アプリケーションごとまたは Windows の設定ごとに実行されます。 設定は、次にアプリケーションを実行するときに復元されます。または、ユーザーがオペレーティングシステムにログオンしたときに設定が復元されます。

**Windows PowerShell for UE-V でアプリケーション設定と Windows 設定を復元するには**

1.  Windows PowerShell ウィンドウを開きます。

2.  次の Windows PowerShell コマンドレットを入力して、アプリケーションの設定と Windows の設定を復元します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>Windows PowerShell コマンドレット</strong></th>
    <th align="left"><strong>説明</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p>アプリケーションのユーザー設定を復元するか、Windows の設定のグループを復元します。</p></td>
    </tr>
    </tbody>
    </table>



**WMI を使用してアプリケーション設定と Windows 設定を復元するには**

1.  Windows PowerShell ウィンドウを開きます。

2.  次の WMI コマンドを入力して、アプリケーションの設定と Windows の設定を復元します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>WMI コマンド</strong></th>
    <th align="left"><strong>説明</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p>アプリケーションのユーザー設定を復元するか、Windows の設定のグループを復元します。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## 関連トピック


[Windows PowerShell と WMI を使用した UE-V 2. x の管理](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[UE-V 2. x の管理](administering-ue-v-2x-new-uevv2.md)









