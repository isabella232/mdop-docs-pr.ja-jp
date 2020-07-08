---
title: App-V 5.1 の保守
description: App-V 5.1 の保守
author: dansimp
ms.assetid: 5abd17d3-e8af-4261-b914-741ae116b0e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 431ad65507a5699358159c73eaf9f3cf0dee33b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813611"
---
# App-V 5.1 の保守


必要な計画をすべて完了した後、App-v 5.1 の展開を完了したら、次の情報を使用して、App-v 5.1 インフラストラクチャを維持することができます。

## <a href="" id="move-the-app-v-5-1-server-"></a>App-v 5.1 サーバーを移動する


App-v 5.1 サーバーは、app-v 5.1 データベースに接続します。 そのため、ネットワーク上の任意のコンピューターに管理コンポーネントをインストールして、それを App-v 5.1 データベースに接続することができます。

[APP-V サーバーを別のコンピューターに移動する方法](how-to-move-the-app-v-server-to-another-computer51.md)

## <a href="" id="determine-if-an-app-v-5-1-application-is-running-virtualized-"></a>App-v 5.1 アプリケーションが仮想化されているかどうかを確認する


アプリが、app-v 5.1 以降で実行されているかどうかを判断する独立系ソフトウェアベンダー (ISV) は、既定の名前** &lt; &gt; 空間で AppVVirtual**という名前のオブジェクトを開く必要があります。 たとえば、Windows API **Getcurrentprocessid ()** を使って、4052などの現在のプロセスの ID を取得できます。次に、 **4052 AppVVirtual**という名前のイベントオブジェクトを、読み取りアクセスの既定の名前空間で**openevent ()** を使って正常に開くことができます。その場合、アプリケーションは仮想です。 **Openevent ()** 呼び出しに失敗した場合、アプリケーションは仮想ではありません。

さらに、特定の API の呼び出しを明示的に仮想化したい場合や、特定の 5.1 API で呼び出さない場合は、AppEntSubsystems32.dll モジュールに実装されている**VirtualizeCurrentThread () 関数と Current** **adis**関数を使うことができます。 これは、その呼び出しが仮想化されている必要があるかどうかを示す、下流のコンポーネントのヒントを提供します。






## App-v 5.1 を管理するためのその他のリソース


[APP-V 5.1 の操作](operations-for-app-v-51.md)

 

 





