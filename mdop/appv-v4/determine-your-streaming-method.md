---
title: ストリーミング方法の選択
description: ストリーミング方法の選択
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821667"
---
# ストリーミング方法の選択


ユーザーが公開プロセスによってコンピューター上に配置されたアイコンをダブルクリックすると、アプリケーションの仮想化クライアントはストリーミングソースの場所から仮想アプリケーションパッケージコンテンツを取得します。

**注** 
*ストリーミング*は、主要な機能ブロックから始まり、必要に応じて追加のブロックを取得して、シーケンス処理されたアプリケーションパッケージからコンテンツを取得するプロセスを記述するために使われる用語です。

 

ストリーミングソースの場所は、通常、ユーザーのコンピューターによってアクセスできるサーバーです。ただし、Microsoft Endpoint Configuration Manager などの一部の電子配布システムでは、ユーザーのコンピューターに SFT ファイルを配布し、そのコンピューターのキャッシュからローカルで仮想アプリケーションパッケージをストリーミングすることができます。

**注** 仮想パッケージのストリーミングソースの場所は、サーバーではないコンピューターで設定することができます。 これは、サーバーがない小規模の支店で特に便利です。

 

順序付けされたアプリケーションの保存に使用できるストリーミングソースについては、次の表を参照してください。

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
<td align="left"><p>ファイル</p></td>
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
<li><p>HTTPS プロトコルを使用した強化されたセキュリティをサポートします。</p></li>
<li><p>インターネット経由のリモートコンピューターへのストリーミングをサポートしています</p></li>
<li><p>開くことができるのはファイアウォール内の1つのポートのみです。</p></li>
<li><p>高いスケーラビリティ</p></li>
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
<li><p>ファイアウォール内の1つのポートのみ開く (RTSPS のみ)</p></li>
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


[電子ソフトウェア配布ベースのシナリオ](electronic-software-distribution-based-scenario.md)

[電子ソフトウェア配布ベースのシナリオ概要](electronic-software-distribution-based-scenario-overview.md)

[公開方法の選択](determine-your-publishing-method.md)

 

 





