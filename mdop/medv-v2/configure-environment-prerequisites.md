---
title: 環境の前提条件を構成する
description: 環境の前提条件を構成する
author: dansimp
ms.assetid: 7379e8e5-1cb2-4b8e-8acc-5c04e26f8c91
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8d6fc3b81f6dafbe709dd904b9fba6124d2f6b6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826447"
---
# 環境の前提条件を構成する


Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 を展開して実行するには、環境が以下の最低限の前提条件を満たしていることを確認する必要があります。

**Windows 7**

MED-V Host Agent と MED-V ワークスペースパッケージャーは、Windows 7 以降でのみサポートされます。

**Windows XP SP3**

MED-V ゲストエージェントは、Windows XP SP3 でのみサポートされます。

**.NET Framework 3.5 SP1**

MED-V ホストとゲストエージェント、および MED-V ワークスペースパッケージャーには、Microsoft .NET Framework 3.5 SP1 が必要です。

**重要** また、更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) () をインストールする必要があり https://go.microsoft.com/fwlink/?LinkId=204950) ます。これは、いくつかの既知のアプリケーション互換性の問題に対応しています。

 

**注** .NET Framework 3.5 SP1 と更新 KB959209 を手動でインストールして、MED-V で使用するために準備する Windows 仮想 PC イメージにする必要があります。 ただし、既定では、ホストコンピューターに Windows 7 をインストールすると、Microsoft .NET Framework 3.5 SP1 と更新プログラムが含まれます。

 

**Active Directory インフラストラクチャ**

グループポリシーは、Active Directory 環境でのオペレーティングシステム、アプリケーション、ユーザーの設定の一元管理と構成を提供します。

## 関連トピック


[インストールの前提条件を構成する](configure-installation-prerequisites.md)

[アーキテクチャの概要](high-level-architecturemedv2.md)

[MED-V 2.0 でサポートされる構成](med-v-20-supported-configurations.md)

 

 





