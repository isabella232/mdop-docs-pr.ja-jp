---
title: PowerShell を使用して展開構成ファイルを適用する方法
description: PowerShell を使用して展開構成ファイルを適用する方法
author: dansimp
ms.assetid: 5df5d5bc-6c72-4087-8b93-d6d4b502a1f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b6764f07dfe8cff1fb30c354937a405202468428
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814443"
---
# PowerShell を使用して展開構成ファイルを適用する方法


動的展開構成ファイルは、パッケージが公開される前に、パッケージが追加されたとき、または App-v 5.0 クライアントを実行しているコンピューターに設定されたときに適用されます。 このファイルは、App-v 5.0 クライアントを実行しているコンピューター上のすべてのユーザーに対してパッケージの既定の設定を構成します。 このセクションでは、展開構成ファイルを使用するために使用する手順について説明します。 この手順は、次の例に基づいており、コンピューターに次のパッケージと構成ファイルが存在することを前提としています。

**c:\\Packages\\Contoso\\MyApp.appv**

**c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

**PowerShell を使用して展開構成ファイルを適用するには**

-   特定のコンピューターでパッケージを実行するすべてのユーザーに対して、PowerShell コンソールを使用して、パッケージを実行するすべてのユーザーの新しい既定の構成セットを指定するには、次のように入力します。

    **AppVClientPackage – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**

    **注**  
    このコマンドは、結果として得られたオブジェクトを $pkg にキャプチャします。 パッケージがコンピューターに既に存在している場合は、 **AppVclientPackage**コマンドレットを使用して展開構成ドキュメントを適用できます。

    **Set-AppVClientPackage – Name Myapp – Path c:\\Packages\\Contoso\\MyApp.appv-DynamicDeploymentConfiguration c:\\Packages\\Contoso\\DynamicConfigurations\\deploymentconfig.xml**



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)









