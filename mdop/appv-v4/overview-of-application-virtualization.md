---
title: Application Virtualization の概要
description: Application Virtualization の概要
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816064"
---
# Application Virtualization の概要


Microsoft Application Virtualization (App-v) を使うと、アプリケーションをコンピューターに直接インストールすることなく、エンドユーザーのコンピューターでアプリケーションを使用できるようになります。 これは、*アプリケーションの順序*付けと呼ばれるプロセスによって可能になります。これにより、各アプリケーションは、クライアントコンピューター上の独立した仮想環境で実行できます。 順序付けされたアプリケーションは、互いに分離されます。 これによりアプリケーションの競合がなくなりますが、アプリケーションはクライアントコンピューターと引き続き操作できます。

App-v クライアントは、エンドユーザーがコンピューターに公開された後にアプリケーションを操作できるようにするための機能です。 クライアントは、仮想化されたアプリケーションが各コンピューターで実行される仮想環境を管理します。 クライアントがコンピューターにインストールされた後、アプリケーションは*発行*と呼ばれるプロセスによってコンピューターから利用できるようにする必要があります。これにより、エンドユーザーは仮想アプリケーションを実行できるようになります。 公開プロセスでは、仮想アプリケーションのアイコンとショートカットをコンピューターにコピーします (通常は Windows デスクトップまたは [**スタート**] メニュー)。また、パッケージ定義とファイルの種類の関連付け情報もコンピューターにコピーします。 公開すると、エンドユーザーのコンピューターでもアプリケーションパッケージのコンテンツを利用できるようになります。

仮想アプリケーションパッケージのコンテンツは、1つまたは複数のアプリケーション仮想化サーバーにコピーできます。これにより、オンデマンドでクライアントにストリーミングしてローカルにキャッシュすることができます。 ファイルサーバーと Web サーバーをストリーミングサーバーとして使用することも、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布システムを使用している場合など、エンドユーザーのコンピューターに直接コピーすることもできます。 複数サーバーの実装では、すべてのストリーミングサーバーでパッケージコンテンツを保持し、最新の状態に維持するには、包括的なパッケージ管理ソリューションが必要です。 組織の規模によっては、世界中のエンドユーザーに対して多数の仮想アプリケーションを利用できるようにすることが必要な場合があります。 このパッケージを管理して、すべてのユーザーが適切なアプリケーションを使用できるようにするため、およびそれらにアクセスする必要がある場合は、重要な要件を満たす必要があります。

## Microsoft Application Virtualization システムの機能


次の表では、Microsoft Application Virtualization 管理システムの主な機能について説明します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">機能</th>
<th align="left">機能</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Management Server</p></td>
<td align="left"><p>パッケージコンテンツのストリーミングと、アプリケーション仮想化クライアントへのショートカットとファイルの種類の関連付けの公開を担当します。</p></td>
<td align="left"><p>Application Virtualization Management Server では、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースがサポートされています。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>コンテンツ </strong> フォルダー</p></td>
<td align="left"><p>ストリーミング用のアプリケーションの仮想化パッケージの場所を示します。</p></td>
<td align="left"><p>このフォルダーは、Application Virtualization Management Server の [共有] に配置できます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization 管理コンソール</p></td>
<td align="left"><p>この本体は、Microsoft Application Virtualization Server の管理に使用される MMC 3.0 スナップイン管理ツールです。</p></td>
<td align="left"><p>このツールは、Microsoft Application Virtualization server にインストールすることも、Microsoft 管理コンソール (MMC) 3.0 と Microsoft を含む別のワークステーションにインストールすることもできます。NETFramework 2.0 がインストールされています。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization Management Web サービス</p></td>
<td align="left"><p>読み取りおよび書き込み要求をアプリケーションの仮想化データストアに伝える責任を負います。</p></td>
<td align="left"><p>管理 Web サービスは、Microsoft Application Virtualization Management server または Microsoft インターネットインフォメーションサービス (IIS) がインストールされている別のコンピューターにインストールできます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization データストア</p></td>
<td align="left"><p>Application Virtualization インフラストラクチャに関連するすべての情報を保存することを担当する App-v SQL Server データベース。</p></td>
<td align="left"><p>この情報には、アプリケーションのすべてのレコード、アプリケーションの割り当て、アプリケーションの仮想化環境の管理に必要なグループが含まれます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization Streaming Server</p></td>
<td align="left"><p>Application virtualization Management Server へのリンクがワイドエリアネットワーク (WAN) 接続と見なされる、ブランチオフィスのクライアントにストリーミングするためのアプリケーション仮想化パッケージをホストする責任を負います。</p></td>
<td align="left"><p>このサーバーにはストリーミング機能のみが含まれており、Application Virtualization 管理コンソールでも、Application Virtualization 管理 Web サービスも提供されません。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Application Virtualization Sequencer</p></td>
<td align="left"><p>Sequencer は、仮想アプリケーションパッケージを作成するためにアプリケーションのインストールを監視およびキャプチャするために使われます。</p></td>
<td align="left"><p>出力は、アプリケーションのアイコン、パッケージ定義情報が格納されている .osd ファイル、パッケージマニフェストファイル、およびアプリケーションプログラムのコンテンツファイルを含む sft ファイルで構成されます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Application Virtualization クライアント</p></td>
<td align="left"><p>Application Virtualization デスクトップクライアントと、リモートデスクトップサービス用の Application Virtualization クライアントは、仮想化されたアプリケーションの仮想環境を提供し、管理します。</p></td>
<td align="left"><p>Microsoft Application Virtualization クライアントは、パッケージのストリーミングをキャッシュに管理し、公開の更新、トランスポート、およびすべてのアプリケーションの仮想化サーバーとの操作を管理します。</p></td>
</tr>
</tbody>
</table>

 

 

 





