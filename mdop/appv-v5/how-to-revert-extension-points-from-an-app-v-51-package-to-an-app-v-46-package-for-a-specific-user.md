---
title: 特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
author: dansimp
ms.assetid: bd53c5d6-7fd2-4816-b03b-d59da0a35819
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: a69d6fb5b180161f39aa89e03b52227f32ce4879
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813731"
---
# 特定のユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法


次の手順を使用して、ユーザー構成ファイルを使用して、App-v 5.1 パッケージを App-v ファイル形式に戻します。

**パッケージを元に戻すには**

1.  App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とのショート5.1 カットは、次の移行方法を使用して、app-v [4.6 パッケージから特定のユーザーに対して拡張ポイントをアプリ-v 5.1 に移行する方法について説明](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)しています。

    変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; **

2.  昇格されたコマンドプロンプトで、次のように入力します。

    PS &gt; **Publish-AppVClientPackage $pkg –** &lt; ユーザー構成ファイルへの dynamicuserconfigurationpath パス&gt;

3.  公開更新を実行するか、アプリ-V 4.6 の次のスケジュールされた発行更新を待ちます。 FTAs またはショートカットを使用してアプリケーションを開きます。 アプリケーションは、App-v 4.6 を使って開くようになりました。

    **注**  
    App-v 5.1 パッケージが不要になった場合は、app-v 5.1 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)









