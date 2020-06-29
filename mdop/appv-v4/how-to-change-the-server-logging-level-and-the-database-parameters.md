---
title: サーバー ログ レベルとデータベース パラメーターを変更する方法
description: サーバー ログ レベルとデータベース パラメーターを変更する方法
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818034"
---
# サーバー ログ レベルとデータベース パラメーターを変更する方法


次の手順を使用して、Application Virtualization Server 管理コンソールからログレベルとデータベースログのパラメーターを変更できます。

次のログレベルを使用できます。

-   トランザクションのみ

-   致命的なエラー

-   エラー

-   警告/エラー

-   情報/警告/エラー

-   詳細

**注** **冗長**モードの使用時に生成されたログファイルのサイズにより、このレベルのログセットでは運用サーバーを実行しないことをお勧めします。

 

データベースのログ記録パラメーターによって、データベースドライバーの種類、アクセス資格情報、ログデータベースの場所が決定されます。

**管理サーバーのログレベルを変更するには**

1.  [**サーバーグループ**] ノードをクリックして、サーバーグループを表示します。

2.  サーバーグループを右クリックし、[**プロパティ**] を選択します。

3.  [**プロパティ**] ダイアログボックスで、[**ログ**] タブを選択します。

4.  [**サーバーグループのプロパティ**] ダイアログボックスで、サーバーを選び、[**編集**] をクリックします。

5.  [ **Add/Edit Log Module** ] ダイアログボックスで、[ **Event Type** ] ドロップダウンリストから [logging level] を選びます。

6.  **[OK]** をクリックします。

7.  [**サーバーグループのプロパティ**] ダイアログボックスで、[ **OK]** または [**適用**] をクリックします。

**ストリーミングサーバーのログレベルを変更するには**

1.  ログレベルを変更するには、次のレジストリキーの値を編集します。

    -   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel

2.  次の値のいずれかを選択して、ログレベルを設定します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">値</th>
    <th align="left">ログレベル</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>0</p></td>
    <td align="left"><p>トランザクションのみ</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>件</p></td>
    <td align="left"><p>致命的なエラー</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>両面</p></td>
    <td align="left"><p>エラー</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>-</p></td>
    <td align="left"><p>警告/エラー</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>4d</p></td>
    <td align="left"><p>情報/警告/エラー</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>個</p></td>
    <td align="left"><p>詳細</p></td>
    </tr>
    </tbody>
    </table>

     

**データベースログのパラメーターを変更するには**

1.  [**サーバーグループ**] ノードをクリックして、サーバーグループを表示します。

2.  サーバーグループを右クリックし、[**プロパティ**] を選択します。

3.  [**プロパティ**] ダイアログボックスで、[**ログ**] タブを選択します。

4.  [**サーバーグループのプロパティ**] ダイアログボックスで、サーバーを選び、[**編集**] をクリックします。

5.  [ **Add/Edit Log Module** ] ダイアログボックスで、[**データベースドライバー** ] ドロップダウンリストからデータベースドライバーを選びます。

6.  **DNS ホスト名**を入力します。

7.  [**ポートを動的に決定**する] チェックボックスをオンにするか、[**ポート**] フィールドにポート番号を入力します。

8.  対応するフィールドに**サービス名**を入力します。

9.  **[OK]** をクリックします。

10. [**サーバーグループのプロパティ**] ダイアログボックスで、[ **OK]** または [**適用**] をクリックします。

## 関連トピック


[サーバー管理コンソールで Application Virtualization システムをカスタマイズする方法](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





