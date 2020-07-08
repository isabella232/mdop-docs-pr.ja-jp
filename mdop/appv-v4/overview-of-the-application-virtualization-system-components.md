---
title: Application Virtualization システム コンポーネントの概要
description: Application Virtualization システム コンポーネントの概要
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816054"
---
# Application Virtualization システム コンポーネントの概要


次の表では、Microsoft Application Virtualization 管理システムの主要コンポーネントについて説明します。 これらのシステムコンポーネントの展開の詳細については、「 [Application Virtualization Server ベースのシナリオ](application-virtualization-server-based-scenario.md)」を参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">コンポーネント</th>
<th align="left">機能</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Management Server</p></td>
<td align="left"><p>パッケージコンテンツのストリーミングと、アプリケーションの仮想化クライアントへのショートカットとファイルの種類の関連付けの発行を担当するコンポーネント。</p></td>
<td align="left"><p>Application Virtualization Management Server では、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースがサポートされています。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>コンテンツ </strong> フォルダー</p></td>
<td align="left"><p>ストリーミング用のアプリケーション仮想化パッケージの場所。</p></td>
<td align="left"><p>このフォルダーは、Application Virtualization Management Server の [共有] に配置できます。 このフォルダーは、ストレージエリアネットワーク (SAN) 上に配置することもできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理コンソール</p></td>
<td align="left"><p>Microsoft Application Virtualization Server 管理用の MMC 3.0 スナップイン管理ユーティリティ。</p></td>
<td align="left"><p>このコンポーネントは、Microsoft Application Virtualization サーバーにインストールすることも、MMC 3.0 との別のワークステーションにインストールすることもできます。NET 2.0 がインストールされています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization Management Web サービス</p></td>
<td align="left"><p>アプリケーションの仮想化データストアへの読み取り/書き込み要求の通信を担当するコンポーネント。</p></td>
<td align="left"><p>このコンポーネントは、Microsoft Application Virtualization サーバーまたは IIS がインストールされている別のコンピューターにインストールできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization データストア</p></td>
<td align="left"><p>SQL データベースに保存され、Application Virtualization インフラストラクチャに関連するすべての情報を保存する責任を負うコンポーネント。</p></td>
<td align="left"><p>この情報には、アプリケーションのすべてのレコード、アプリケーションの割り当て、アプリケーションの仮想化環境の管理に必要なグループが含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization Streaming Server</p></td>
<td align="left"><p>Application virtualization Management Server へのリンクが WAN と見なされる、ブランチオフィスのクライアントにストリーミングするためのアプリケーション仮想化パッケージをホストするコンポーネント。</p></td>
<td align="left"><p>このサーバーにはストリーミング機能のみが含まれており、Application Virtualization 管理コンソールでも、Application Virtualization 管理 Web サービスも提供されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Sequencer</p></td>
<td align="left"><p>アプリケーションのインストールを監視して、仮想アプリケーションパッケージを作成するために使用されるコンポーネント。</p></td>
<td align="left"><p>出力は、アプリケーションのアイコン、パッケージ定義情報を含む OSD ファイル、パッケージマニフェストファイル、およびアプリケーションプログラムのコンテンツファイルを含む SFT ファイルで構成されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization クライアント</p></td>
<td align="left"><p>Application Virtualization デスクトップクライアントにインストールされたコンポーネント、またはリモートデスクトップサービス (以前のターミナルサービス) 用の Application Virtualization クライアントで、仮想化されたアプリケーションの仮想環境を提供します。</p></td>
<td align="left"><p>Microsoft Application Virtualization クライアントは、パッケージのストリーミングをキャッシュに管理し、公開の更新、トランスポート、およびすべてのアプリケーションの仮想化サーバーとの操作を管理します。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[Application Virtualization Management Server を使用した仮想アプリケーションの公開](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





