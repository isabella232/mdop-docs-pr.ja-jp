---
title: App-V 5.0 のアーキテクチャの概要
description: App-V 5.0 のアーキテクチャの概要
author: dansimp
ms.assetid: fdf8b841-918f-4672-b352-0f2b9519581b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0ec105ffcc3213e488615603484b2de6bafce4d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814555"
---
# App-V 5.0 のアーキテクチャの概要


Microsoft Application Virtualization (App-v) 5.0 の展開を簡素化するには、次の情報を参考にしてください。

## アーキテクチャの概要


一般的なアプリ-V 5.0 の実装は、次の要素で構成されます。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要素</th>
<th align="left">詳細情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 Management Server</p></td>
<td align="left"><p>App-v 5.0 Management サーバーには、app-v 5.0 インフラストラクチャの全体的な管理機能が用意されています。 さらに、環境に管理サーバーの複数のインスタンスをインストールすることもできます。これには次のような利点があります。</p>
<ul>
<li><p>フォールトトレランスと高可用性–2つの別々のコンピューターに、5.0 アプリをインストールして構成することは、サーバーの1つが利用できない場合やオフラインの場合に役立ちます。</p>
<p>また、複数のコンピューターに管理サーバーをインストールすることで、App-v 5.0 の可用性を高めることもできます。 このシナリオでは、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</p></li>
<li><p>スケーラビリティ–高負荷をサポートするために必要に応じて、他の管理サーバーを追加することができます。たとえば、ロードバランサーの背後に複数のサーバーをインストールすることができます。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 公開サーバー</p></td>
<td align="left"><p>App-v 5.0 公開サーバーには、仮想アプリケーションのホスティングとストリーミングの機能が用意されています。 発行サーバーでは、データベース接続は必要ありません。次のプロトコルがサポートされています。</p>
<ul>
<li><p>HTTP と HTTPS</p></li>
</ul>
<p>また、複数のコンピューターに発行サーバーをインストールすることで、App-v 5.0 の可用性を向上させることもできます。 また、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 5.0 レポートサーバー</p></td>
<td align="left"><p>App-v 5.0 レポートサーバーを使用すると、承認されたユーザーは、app-v 5.0 インフラストラクチャを管理するのに役立つ、既存の App-v 5.0 レポートとアドホックレポートを実行して表示することができます。 レポートサーバーには、App-v 5.0 レポートデータベースへの接続が必要です。 また、複数のコンピューターにレポートサーバーをインストールすることで、App-v 5.0 の可用性を高めることもできます。 また、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-v 5.0 クライアント</p></td>
<td align="left"><p>App-v 5.0 を使用して作成されたパッケージを、ターゲットコンピューターで実行するには、App-v 5.0 クライアントを使用します。</p></td>
</tr>
</tbody>
</table>

 

**注** 電子ソフトウェアの配布 (ESD) で App-v 5.0 を使用している場合、app-v 5.0 Management server を使用する必要はありませんが、App-v 5.0 のレポート機能とストリーミング機能を利用することはできます。

 






## 関連トピック


[App-V 5.0 をお使いになる前に](getting-started-with-app-v-50--rtm.md)

 

 





