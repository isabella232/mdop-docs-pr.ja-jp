---
title: 電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画
description: 電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815857"
---
# 電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画


ESD システムと連携してストリーミングサーバーを使用して、アプリケーションコンテンツをエンドユーザーのコンピューターで利用できるようにする場合は、いくつかの方法を選ぶことができます。これには、既に配置されているインフラストラクチャを利用できます。 たとえば、お客様の ESD システムが、現場支店のサーバーでソフトウェア配布共有を使用している場合は、そのようなサーバー上でアプリケーションの仮想化 \ コンテンツ共有を配置し、そのコンテンツ共有をアプリケーションコンテンツソースとして使用するようにクライアントを構成することができます。 サポートされているオプションには、ファイルサーバーまたは IIS サーバーの使用があります。 また、既存のファイルサーバーまたは IIS サーバーに Application Virtualization Streaming Server をインストールすることもできます。

Application Virtualization Streaming Server は、Application Virtualization のアクティブなアップグレード機能をサポートします。 アクティブなアップグレード機能を使用すると、アプリケーションを現在実行しているユーザーに影響を与えずに、新しいバージョンのアプリケーションを App-v Management Server または Streaming Server に追加することができます。 次にユーザーがアプリケーションを起動したときに、app-v 管理サーバーまたはストリーミングサーバーからアプリケーションの最新バージョンが自動的に取得されます。 この機能を利用するには、RTSP (S) プロトコルを使用する必要があります。 Application Virtualization Streaming Server を使用しない場合は、ESD システムを使用して、アプリケーションパッケージのアップグレードを明示的に管理する必要があります。

**注** アプリケーションへのアクセスは Active Directory ドメインサービスのセキュリティグループによって制御されるため、各仮想アプリケーションのセキュリティグループを設定し、各グループに追加されるユーザーを管理するためのプロセスを計画する必要があります。 Application Virtualization システム管理者は、コンテンツ共有の下にあるアプリケーションディレクトリに Acl を適用することによって、これらの Active Directory グループを使用するように各ストリーミングサーバーを構成します。 Active Directory グループメンバーシップに基づくパッケージへのアクセスを制御します。

 

利用可能なストリーミングオプションの特性を次の表にまとめます。

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
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)">Application Virtualization Management Server を構成する方法</a></p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[ESD ベースの展開用にサーバーを構成する方法](how-to-configure-servers-for-esd-based-deployment.md)

[セキュリティと保護の概要](security-and-protection-overview.md)

[電子ソフトウェア配布を使用した仮想アプリケーションの公開](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





