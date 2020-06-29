---
title: スタンドアロン配信シナリオの概要
description: スタンドアロン配信シナリオの概要
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815307"
---
# スタンドアロン配信シナリオの概要


スタンドアロン配信シナリオは、低帯域幅接続または接続なしのいずれかの環境に適したアプリケーション仮想化ソリューションであり、一元管理されたサーバーからアプリケーションをストリーミングするアプリケーションの仮想化デスクトップクライアントの機能を制限します。 このような環境では、ユーザーがリモートで作業することが多くあり、デバイス所有者が Windows Installer ファイルを使用してアプリケーションをインストールします。

Application Virtualization Sequencer を使用して、Windows インストーラファイルを含むシーケンス付きのアプリケーションを作成することができます。 これらのパッケージには、仮想化されたアプリケーション、公開情報、クライアントシステムにパッケージをインストールするために必要なインストーラールーチンが含まれています。 インストーラーは、仮想アプリケーションパッケージを Microsoft Application Virtualization デスクトップクライアントに追加します。 文書情報は、WAN を介してアプリケーションをストリーミングするのではなく、ローカルの場所から読み込むように構成されています。 ユーザーは、一時的にネットワークに接続して、Windows インストーラファイルを取得したり、DVD から実行したりすることができます。

単体配信シナリオでは、ユーザーに次のような利点があります。

-   簡単な展開操作。

-   ネットワークとサーバーは、実行時には必要ありません。

-   アプリケーションはプレキャッシュされていて、すべてのユーザーが使用できます。

単体配信シナリオには、次のような制限があります。

-   組み込みの自動レポート機能は利用できません。レポートは、外部レポートツールを使用して生成する必要があります。

-   アプリケーションは、元の Windows インストーラーファイルと同じように、手動でクライアントに配信する必要があります。

## 関連トピック


[Application Virtualization Client を手動でインストールする方法](how-to-manually-install-the-application-virtualization-client.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

 

 





