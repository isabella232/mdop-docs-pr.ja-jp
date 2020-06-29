---
title: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
description: 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法
ms.assetid: 2a43ca1b-6847-4dd1-ade2-336ac4ac6af0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 62542e5cd0b9dcb55f6e8f3db4d4f43c011a2839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813730"
---
# 特定のコンピューター上の全ユーザーの拡張ポイントを App-V 5.0 パッケージから App-V 4.6 パッケージに戻す方法

*注:** App-V 4.6 はメインストリームサポートを終了しました。 次の例は、App-v 4.6 SP3 クライアントが既にインストールされていることを前提としています。

次の手順を使用して、展開構成ファイルを使用して、アプリ-V 5.0 パッケージの拡張ポイントを App-v 4.6 ファイル形式に戻します。

**パッケージを元に戻すには**

1.  App-v 4.6 パッケージがユーザーに公開されていることを確認します。ただし、FTAs とショートカットは、次の移行方法を使用して、アプリ-v [4.6 パッケージから、特定のコンピューター上のすべてのユーザーに対して、変換さ5.0 れた app-v 5.0 パッケージに拡張ポイントを移行する方法](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)を示しています。

    変換されたパッケージの展開構成ファイルの**Userconfiguration**セクションでポリシーを設定するには、 **userconfiguration**セクションに対して次の更新を行います。 **ManagingAuthority TakeoverExtensionPointsFrom46 = "FALSE" PackageName = &lt; パッケージ ID &gt; **

2.  昇格されたコマンドプロンプトで、次のように入力します。

    PS &gt; **Set-AppvClientPackage $Pkg –動的** &lt; 展開構成ファイルへの dynamicdeploymentconfiguration path&gt;

    PS &gt; **Publish-AppVClientPackage $Pkg – DynamicUserConfigurationType useDeploymentConfiguration**

3.  公開更新を実行するか、アプリ-V 4.6 SP2 パッケージの次にスケジュールされている発行の更新を待ちます。

    FTAs またはショートカットを使用してアプリケーションを開きます。 アプリケーションは、App-v 4.6 を使って開くようになりました。

    **注**  
    App-v 5.0 パッケージが不要になった場合は、app-v 5.0 パッケージの発行を取り消すことができます。また、拡張ポイントは自動的に App V 4.6 に戻ります。



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)









