---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法
author: dansimp
ms.assetid: 64640b8e-de6b-4006-a33e-353d285af15e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: ce8d5cc0e79be46fd9680a3bea0236bbeb93ea83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813723"
---
# 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.1 パッケージから App-V 4.6 パッケージに戻す方法


次の手順を使用して、展開構成ファイルを使用して、アプリ-V 5.1 パッケージの拡張ポイントを App-v 4.6 ファイル形式に戻します。

**パッケージを元に戻すには**

1.  App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とショートカットは、次の移行方法を使用して、アプリ-v [4.6 パッケージから、特定のコンピューター上のすべてのユーザーに対して、変換さ5.1 れた app-v 5.1 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)を示しています。

    変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; **

2.  昇格されたコマンドプロンプトで、次のように入力します。

    PS &gt; **Set-AppvClientPackage $Pkg –動的** &lt; 展開構成ファイルへの dynamicdeploymentconfiguration path&gt;

    PS &gt; **Publish-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**

3.  公開更新を実行するか、または App-v 4.6 パッケージの次のスケジュールされた発行更新を待ちます。

    FTAs またはショートカットを使用してアプリケーションを開きます。 アプリケーションは、App-v 4.6 を使って開くようになりました。

    **注**  
    App-v 5.1 パッケージが不要になった場合は、app-v 5.1 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)









