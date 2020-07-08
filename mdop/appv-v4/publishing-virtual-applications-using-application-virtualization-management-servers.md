---
title: Application Virtualization Management Server を使用した仮想アプリケーションの公開
description: Application Virtualization Management Server を使用した仮想アプリケーションの公開
author: dansimp
ms.assetid: f3d79284-3f82-4ca3-b741-1a80b61490da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01b85d73ed0a6a8bf723be381e947fbbc003bf6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815767"
---
# Application Virtualization Management Server を使用した仮想アプリケーションの公開


Application Virtualization Server ベースの展開では、配置済みの仮想アプリケーションパッケージの順序付け、テスト、展開が行われ、アプリケーションの仮想化管理サーバーで使用されるメインコンテンツ共有にコピーされます。 アプリケーションの仮想化管理サーバーにパッケージをインポートした後は、それらをエンドユーザーに公開することができます。

**注** コンテンツ共有は、サーバーの接続されているディスクストレージに配置されている必要があります。 ネットワークへの影響があるため、SAN や DFS 共有などのネットワークストレージデバイスを使用することは慎重に検討する必要があります。

 

アプリケーションは Active Directory グループにプロビジョニングされます。 通常、Application Virtualization 管理者は、公開する各仮想アプリケーションの Active Directory グループを作成し、そのグループに適切なユーザーを追加します。 ユーザーがワークステーションにログオンすると、アプリケーションの仮想化クライアントは既定で、ログオンしているユーザーの資格情報を使用して発行の更新を実行します。 ユーザーは、ショートカットが配置されている場所からアプリケーションを起動することができます。 アプリケーションの仮想化管理者は、アプリケーションのシーケンス中にクライアントシステム上のショートカットの場所と数を決定します。

**注** *公開更新*は、アプリケーションの仮想化クライアントで定義されている Application virtualization Server への呼び出しで、エンドユーザーが使用するためにどの仮想アプリケーションのショートカットがクライアントに送信されるかを決定します。

 

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[クライアントで仮想アプリケーションを公開する方法](how-to-publish-a-virtual-application-on-the-client.md)

[Application Virtualization システム コンポーネントの概要](overview-of-the-application-virtualization-system-components.md)

[Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





