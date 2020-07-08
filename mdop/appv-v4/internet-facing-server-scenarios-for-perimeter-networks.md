---
title: 境界ネットワークのインターネットに接続されたサーバーのシナリオ
description: 境界ネットワークのインターネットに接続されたサーバーのシナリオ
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816284"
---
# 境界ネットワークのインターネットに接続されたサーバーのシナリオ


App-v 4.5 は、ネットワークに接続されていない、またはネットワークから切断されたユーザーが引き続きアプリを使用できるようにする、インターネットに接続しているサーバーのシナリオをサポートします。 次の図に示すように、インターネット (RTSPS および HTTPS) でのセキュリティで保護されたプロトコルの使用のみがサポートされています。

![app-v ファイアウォールの配置図](images/appvfirewalls.gif)

ISA Server を使用して、次の方法で App-v インフラストラクチャが内部ネットワーク上にある ISA Server を使用して、インターネット向けソリューションをセットアップできます。

-   ICO ファイルと OSD ファイルをホストしている IIS サーバー用の Web 公開ルールを作成します。また、必要に応じて、ストリーミング用のパッケージを内部ネットワーク上に配置します。 詳細な手順については <https://go.microsoft.com/fwlink/?LinkId=151982> 、をご覧ください。

-   App-v Web Management Server (RTSPS) のサーバー公開ルールを作成します。 詳細な手順については [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 、をご覧ください。

次の図に示すように、クライアントと ISA Server の間、または ISA Server と内部ネットワークの間で、インフラストラクチャが他のファイアウォールを実装している場合は、RTSPS (TCP 322) と HTTPS (TCP 443) の両方のファイアウォールルールを作成して、トラフィックフローをサポートする必要があります。 また、ISA Server と内部ネットワークの間にファイアウォールが実装されている場合は、ドメインメンバーに必要な既定のトラフィックをファイアウォール (DNS、LDAP、Kerberos、SMB/CIFS) でトンネリングすることを許可する必要があります。

![app v 境界ネットワークファイアウォールの図](images/appvperimeternetworkfirewall.gif)

ファイアウォールの解決策は環境によって異なるため、このトピックで示されているガイダンスでは、インターネットに接続された App-v 環境を境界ネットワークで構成するために必要なトラフィックについて説明します。 この情報には、推奨される内部ネットワークサーバーも含まれます。

境界ネットワークに次のサーバーを配置します。

-   App-v Management Server

-   公開とストリーミング用の IIS サーバー

**注** 管理サーバーと IIS サーバーを別々のコンピューターに配置することをお勧めします。

 

次のサーバーを内部ネットワークに配置します。

-   Content server

-   データストア (SQL Server)

-   Active Directory ドメインコントローラー

## トラフィック要件


次の表に、インターネットおよび境界ネットワークと、境界ネットワークから内部ネットワークへの通信のトラフィック要件を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">インターネットから境界ネットワークへのトラフィック要件</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>RTSPS (公開の更新およびストリーミングパッケージ)</p></td>
<td align="left"><p>既定では TCP 322これは、App-v Management Server で変更できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS (ICO ファイルと OSD ファイル、ストリーミングパッケージ)</p></td>
<td align="left"><p>既定では TCP 443これは、IIS 構成で変更できます。</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">境界ネットワークから内部ネットワークへのトラフィック要件</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server</p></td>
<td align="left"><p>TCP 1433 は既定のままですが、SQL Server で構成できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>コンテンツディレクトリが管理サーバーまたは IIS サーバーからリモートで配置されている場合 (推奨)</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Kerberos</p></td>
<td align="left"><p>TCP および UDP 88</p></td>
</tr>
<tr class="even">
<td align="left"><p>LDAP</p></td>
<td align="left"><p>TCP および UDP 389</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DNS</p></td>
<td align="left"><p>内部リソースの名前解決 (境界ネットワークサーバー上のホストのファイルを使用して除去可能)</p></td>
</tr>
</tbody>
</table>

 

 

 





