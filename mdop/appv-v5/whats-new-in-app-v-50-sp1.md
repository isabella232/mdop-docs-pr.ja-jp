---
title: App-V 5.0 SP1 の新機能
description: App-V 5.0 SP1 の新機能
author: dansimp
ms.assetid: e97c2dbb-7b40-46a0-8137-9ee4fc2bd071
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2542d0cc5a544d26b3279b24063cf3ef428b9f39
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813218"
---
# App-V 5.0 SP1 の新機能


このセクションは、既に App-v に精通していて、App-v 5.0 SP1 の変更内容を確認したいユーザーを対象としています。 まだ App-v に精通していない場合は、まず「 [app-v 5.0 の計画](planning-for-app-v-50-rc.md)」を参照してください。

## 標準機能の変更点


以下のセクションでは、App-v 5.0 SP1 の標準機能の変更に関する情報について説明します。

### サポートされている言語に対する変更

詳細については、「 [app-v 5.0 SP1 につい](about-app-v-50-sp1.md)て」を参照してください。

新しい言語パックの詳細については、次の一覧を参照してください。

-   App-v 5.0 SP1 言語パックは、すべての App-v 5.0 コンポーネントの**appv\_xxx\_setup.exe**インストーラーにバンドルされています。

-   インストーラーを実行すると、対象のコンピューターで実行されている関連オペレーティングシステムのロケールに基づいて、適切な言語パックが自動的にインストールされます。

-   追加の言語パックが必要な場合は、次のコマンドを実行して、インストーラーからこれらの言語パックを抽出する必要があり `appv_xxx_setup.exe /Layout /LayoutDir=”<path>”` ます。 これを実行すると、インストーラーの内容が指定した場所に抽出されます。

-   適切な言語パックの Windows インストールファイルを適用して、目的の言語パックをインストールする必要があります。 たとえば、 **appv\_hib\_LP\_jmmb\_x86.msi**や**appv\_hib\_LP\_jmmb\_x64.msi**では、 **hib**はコンポーネントを指し、 **jmmb**はロケールを指します。

## Microsoft 表紙の強化されたサポート


**アプリケーションの仮想5.0 化用 Microsoft Office 2010 シーケンスキット**–ユーザーに対して、仮想化されたバージョンの Microsoft 表紙を使用した一貫したエクスペリエンスを提供します。 **Application Virtualization 5.0 用の Microsoft office 2010 シーケンスキット**は、 **Microsoft Office 2010 展開キット (app-v)** と組み合わせて使用されるほか、必要な microsoft 表紙ライセンスサービスも提供します。






## 関連トピック


[App-V 5.0 について](about-app-v-50.md)

 

 





