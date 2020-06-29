---
title: App-V 5.1 Client をアンインストールする方法
description: App-V 5.1 Client をアンインストールする方法
author: dansimp
ms.assetid: 21f2d946-fc9f-4cd3-899b-ac52b3fbc306
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9338bef6b8a3123f9b8f49036427121987e7aa9f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813658"
---
# App-V 5.1 Client をアンインストールする方法


コンピューターから Microsoft Application Virtualization (App-v) 5.1 クライアントをアンインストールするには、次の手順を使用します。 App-v 5.1 クライアントをアンインストールすると、クライアントを実行しているコンピューターに公開されているすべてのパッケージも削除されます。 アンインストール操作が完了しない場合、パッケージは、App-v 5.1 クライアントを実行しているコンピューターに再公開する必要があります。

**重要**  
アンインストール手順を実行する前に、App-v 5.1 クライアントサービスが実行されていることを確認する必要があります。



**App-v 5.1 クライアントをアンインストールするには**

1.  コントロールパネルで、[**プログラム**]、[プログラムのアンインストール] の順にダブルクリックし、[  /  **Uninstall a Program** **Microsoft Application Virtualization Client**] をダブルクリックします。

2.  ダイアログボックスが表示されたら、[**はい**] をクリックしてアンインストールプロセスを続行します。

    **重要**  
    アンインストールプロセスをキャンセルまたは中断することはできません。



3.  進行状況バーに残りの時間が表示されます。 この手順が完了したら、アンインストールプロセスを完了するために、関連するすべてのドライバーを停止できるように、コンピューターを再起動する必要があります。

    **注**  
    コマンドラインを使用して、次のスイッチ ( **/uninstall**) で app-v 5.1 クライアントをアンインストールすることもできます。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.1 の展開](deploying-app-v-51.md)









