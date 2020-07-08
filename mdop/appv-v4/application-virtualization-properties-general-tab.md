---
title: Application Virtualization プロパティの [全般] タブ
description: Application Virtualization プロパティの [全般] タブ
author: dansimp
ms.assetid: be7449d9-171a-4a11-9382-83b7008ccbdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ee00bfc7f70ee7b17da42aad61356540a7a0be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819687"
---
# Application Virtualization プロパティ: [全般] タブ


[ **Application Virtualization Properties** ] ダイアログボックスの **[全般**] タブを使用して、ログの設定とデータの場所を変更します。

このタブには、次の要素が含まれています。

<a href="" id="log-level"></a>**ログレベル**  
ドロップダウンリストからレベルを選択します。 既定のレベルは**情報**です。

<a href="" id="reset-log"></a>**ログのリセット**  
現在のログファイルをバックアップして、すぐに新しいログファイルを開始するには、このボタンをクリックします。

<a href="" id="location"></a>**位置情報**  
sftlog.txt ログファイルを保存する場所を入力するか参照します。 既定の場所は次のとおりです。

-   WindowsXP の場合は、Windows Server2003:*C:\\Documents および Settings\\All Users\\Application data¥ microsoft Application Virtualization Client*

-   Windows Vista、Windows 7、Windows Server2008、*C:\\ProgramData\\Microsoft\\Application Virtualization クライアント*の場合

<a href="" id="system-log-level"></a>**システムログレベル**  
ドロップダウンリストからレベルを選択します。 既定のレベルは**警告**です。

**注** システム**ログレベル**設定は、システムイベントログに送信されるメッセージのレベルを制御します。 ログに記録されたメッセージは、クライアントイベントログに記録されるメッセージと同じですが、クライアントイベントログの領域制限を持たない別の場所に格納されています。 システムイベントログにはスペースの制限がないため、詳細なログが必要な場合に最適です。

 

<a href="" id="global-data-directory"></a>**グローバルデータディレクトリ**  
ログファイルのディレクトリの場所を入力または参照します。 既定の場所は次のとおりです。

-   WindowsXP の場合は、Windows Server2003:*C:\\Documents および Settings\\All Users\\Application data¥ microsoft Application Virtualization Client*

-   Windows Vista、Windows 7、Windows Server2008、*C:\\ProgramData\\Microsoft\\Application Virtualization クライアント*の場合

<a href="" id="user-data-directory"></a>**ユーザーデータディレクトリ**  
ユーザー固有のデータが保存されているディレクトリの場所を入力または参照します。 既定値は% APPDATA% です。 このパスは、クライアントコンピューター上の有効な環境変数である必要があります。

## 関連トピック


[Client Management Console: Application Virtualization プロパティ](client-management-console-application-virtualization-properties.md)

 

 





