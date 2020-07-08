---
title: PowerShell を使用してクライアント構成を変更する方法
description: PowerShell を使用してクライアント構成を変更する方法
author: dansimp
ms.assetid: c3a59592-bb0d-43b6-8f4e-44f3a2d5b7ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 368a0d12c12e10a623afad3f9040ae01cee6cb38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813811"
---
# PowerShell を使用してクライアント構成を変更する方法


次の手順を使用して、App-v 5.1 クライアント構成を構成します。

**PowerShell を使用して App-v 5.1 クライアント構成を変更するには**

1.  PowerShell を使用してクライアント設定を構成するには、 **AppvClientConfiguration**コマンドレットを使用します。 PowerShell のインストールの詳細とコマンドレットの一覧については、「 [Powershell コマンドレットを読み込み、コマンドレットのヘルプを取得する方法](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-51.md)」を参照してください。

2.  クライアント構成を変更するには、PowerShell コマンドプロンプトを開き、必要なパラメーターを指定して次のコマンドレット**AppvClientConfiguration**を実行します。 以下に例を示します。

    `$config = Get-AppvClientConfiguration`

    `Set-AppvClientConfiguration $config`

    `Set-AppvClientConfiguration –AutoLoad 2`

    App-v**の提案をお寄せ**ください。 [ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。 **App-v の問題が発生しましたか?** App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。

## 関連トピック


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





