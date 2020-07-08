---
title: UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元
description: UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元
author: dansimp
ms.assetid: 254a16b1-f186-44a4-8e22-49a4ee87c734
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31ae83e0a44f98b66a9930f8c5db2231992a4700
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812378"
---
# UE-V 1.0 を使用して同期されたアプリケーションと Windows の設定の復元


Microsoft User Experience Virtualization (UE-V) の WMI および PowerShell 機能により、設定パッケージを復元することができます。 WMI コマンドと PowerShell コマンドを使用すると、アプリケーションと Windows の設定を、UE-V Agent をインストールした後にアプリケーションを初めて起動したときにコンピューター上にあった設定値に復元することができます。 この復元アクションは、アプリケーションごとまたは Windows の設定ごとに実行されます。 設定は、次回アプリケーションが実行されるとき、またはユーザーがオペレーティングシステムにログオンしたときに復元されます。

**PowerShell を使用してアプリケーション設定と Windows 設定を復元するには**

1.  Windows PowerShell ウィンドウを開きます。 Microsoft UE-V PowerShell モジュールをインポートするには、次のコマンドを入力します。

    ``` syntax
    Import-module UEV
    ```

2.  次の PowerShell コマンドレットを入力して、アプリケーションの設定と Windows の設定を復元します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell コマンドレット</strong></th>
    <th align="left"><strong>説明</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Restore-UevUserSetting</p></td>
    <td align="left"><p>アプリケーションのユーザー設定を復元するか、Windows 設定のグループを復元します</p></td>
    </tr>
    </tbody>
    </table>

     

**WMI を使用してアプリケーション設定と Windows 設定を復元するには**

1.  PowerShell ウィンドウを開きます。

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
    <td align="left"><p>Root\Microsoft\UEV の呼び出しメソッド-名前空間の UserSettings-Name RestoreByTemplateId-ArgumentList &lt; template_ID&gt;</p></td>
    <td align="left"><p>アプリケーションのユーザー設定を復元するか、Windows 設定のグループを復元します</p></td>
    </tr>
    </tbody>
    </table>

     

## 関連トピック


[UE-V 1.0 の管理](administering-ue-v-10.md)

[UE-V 1.0 の操作](operations-for-ue-v-10.md)

 

 





