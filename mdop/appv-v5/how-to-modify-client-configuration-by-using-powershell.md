---
title: PowerShell を使用してクライアント構成を変更する方法
description: PowerShell を使用してクライアント構成を変更する方法
author: dansimp
ms.assetid: 53ccb2cf-ef81-4310-a853-efcb395f006e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d3173944abfe2c2b3d30aa9654dae81f204a32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813827"
---
# PowerShell を使用してクライアント構成を変更する方法


次の手順を使用して、App-v 5.0 クライアント構成を構成します。

**PowerShell を使用して App-v 5.0 クライアント構成を変更するには**

1.  PowerShell を使用してクライアント設定を構成するには、 **AppvClientConfiguration**コマンドレットを使用します。

2.  クライアント構成を変更するには、PowerShell コマンドプロンプトを開き、必要なパラメーターを指定して次のコマンドレット**AppvClientConfiguration**を実行します。 以下に例を示します。

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.0 の操作](operations-for-app-v-50.md)

 

 





