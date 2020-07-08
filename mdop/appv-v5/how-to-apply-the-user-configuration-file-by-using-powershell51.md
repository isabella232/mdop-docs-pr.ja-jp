---
title: PowerShell を使用してユーザー構成ファイルを適用する方法
description: PowerShell を使用してユーザー構成ファイルを適用する方法
author: dansimp
ms.assetid: 986e638c-4a0c-4a7e-be73-f4615e8b8000
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97b3db253993d6d855384ee5d9771a7f9ff5b64d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814427"
---
# PowerShell を使用してユーザー構成ファイルを適用する方法


動的ユーザー構成ファイルは、パッケージが特定のユーザーに公開されたときに適用され、パッケージの実行方法が決定されます。

ユーザー固有の構成ファイルを指定するには、次の手順を使用します。 次の手順は、例に基づいています。

**c:\\Packages\\Contoso\\MyApp.appv**

**ユーザー構成ファイルを適用するには**

1.  PowerShell コンソールを使用してコンピューターにパッケージを追加するには、次のコマンドを入力します。

    **AppVClientPackage c:\\Packages\\Contoso\\MyApp.appv を追加**します。

2.  次のコマンドを使用して、パッケージをユーザーに公開し、更新された動的なユーザー構成ファイルを指定します。

    **Publish-AppVClientPackage $pkg – DynamicUserConfigurationPath c:\\Packages\\Contoso\\config.xml**

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





