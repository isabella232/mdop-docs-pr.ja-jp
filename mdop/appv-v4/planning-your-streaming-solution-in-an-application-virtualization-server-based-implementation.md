---
title: Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画
description: Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815867"
---
# Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画


Application virtualization Management Server ベースの実装と組み合わせてアプリケーション仮想化ストリーミングサーバーを使用する場合は、いくつかの方法から選ぶことができます。これには、さまざまなインフラストラクチャが用意されています。 たとえば、フィールドブランチオフィスに既にサーバーがある場合は、それらのサーバー上でアプリケーションの仮想化 \ コンテンツ共有を配置し、そのコンテンツ共有をアプリケーションコンテンツソースとして使用するようにクライアントを構成することができます。 アプリケーションの仮想化管理サーバーのみを使用する場合 (たとえば、1つの office しか持っていない場合)、クライアントはそのサーバーからコンテンツをストリーミングできます。

サポートされているオプションには、ファイルサーバー、IIS サーバー、または Application Virtualization ストリーミングサーバーの使用があります。 また、既存のファイルサーバーまたは IIS サーバーに Application Virtualization Streaming Server をインストールすることもできます。 これらのさまざまなオプションの特性を次の表にまとめます。

**注** アクティブなアップグレード機能を使用すると、アプリケーションを現在実行しているユーザーに影響を与えずに、新しいバージョンのアプリケーションを App-v Management Server または Streaming Server に追加することができます。 次にユーザーがアプリケーションを起動したときに、app-v 管理サーバーまたはストリーミングサーバーからアプリケーションの最新バージョンが自動的に取得されます。 この機能を利用するには、RTSP (S) プロトコルを使用する必要があります。

 

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サーバーの種類</th>
<th align="left">プロトコル</th>
<th align="left">長所</th>
<th align="left">短所</th>
<th align="left">Links</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ファイル サーバー</p></td>
<td align="left"><p>SMB</p></td>
<td align="left"><ul>
<li><p>\ コンテンツ共有を使用して既存のファイルサーバーを構成するシンプルで低コストのソリューション</p></li>
</ul></td>
<td align="left"><ul>
<li><p>アクティブなアップグレードなし</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)">ファイル サーバーを構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>IIS サーバー</p></td>
<td align="left"><p>HTTP/HTTPS</p></td>
<td align="left"><ul>
<li><p>HTTPS プロトコルを使用した強化されたセキュリティのサポート</p></li>
<li><p>インターネット経由のリモートコンピューターへのストリーミングをサポートしています</p></li>
<li><p>開くことができるのはファイアウォール内の1つのポートのみです。</p></li>
<li><p>対応</p></li>
<li><p>使い慣れたプロトコル</p></li>
</ul></td>
<td align="left"><ul>
<li><p>IIS を管理する必要がある</p></li>
<li><p>アクティブなアップグレードなし</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)">IIS のサーバーを構成する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Application Virtualization ストリーミングサーバー</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>アクティブなアップグレード</p></li>
<li><p>RTSPS プロトコルを使用した強化されたセキュリティのサポート</p></li>
<li><p>開くことができるのはファイアウォール内の1つのポートのみです。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>デュアルインフラストラクチャ</p></li>
<li><p>サーバー管理の要件</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)">Application Virtualization Streaming Server を構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>Application Virtualization Management Server</p></td>
<td align="left"><p>RTSP/RTSPS</p></td>
<td align="left"><ul>
<li><p>アクティブなアップグレード</p></li>
<li><p>RTSPS プロトコルを使用した強化されたセキュリティのサポート</p></li>
<li><p>開くことができるのはファイアウォール内の1つのポートのみです。</p></li>
</ul></td>
<td align="left"><ul>
<li><p>デュアルインフラストラクチャ</p></li>
<li><p>サーバー管理の要件</p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">Application Virtualization Management Server を構成する方法</a></p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[Application Virtualization サーバー ベースのシナリオ](application-virtualization-server-based-scenario.md)

[Application Virtualization システム コンポーネントの概要](overview-of-the-application-virtualization-system-components.md)

[Application Virtualization Management Server を使用した仮想アプリケーションの公開](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





