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
ms.openlocfilehash: 7415cf7a97edc646653df552723667bac8d25fdc
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910692"
---
# <a name="internet-facing-server-scenarios-for-perimeter-networks"></a>境界ネットワークのインターネットに接続されたサーバーのシナリオ


App-V 4.5 では、企業ネットワークに接続されていないユーザーやネットワークから切断したユーザーが App-V を使用できる、インターネットに接続するサーバー シナリオがサポートされています。 次の図に示すように、インターネットでのセキュリティで保護されたプロトコル (RTSPS と HTTPS) の使用だけがサポートされています。

![app-v ファイアウォールの配置図。](images/appvfirewalls.gif)

インターネットに接続するソリューションは、ISA Server を使用してセットアップできます。ここで、App-V インフラストラクチャは内部ネットワーク上に次の方法で置きます。

-   ICO ファイルと OSD ファイルをホストしている IIS サーバーの Web 発行ルールを作成し、必要に応じてストリーミング用のパッケージを内部ネットワーク上に作成します。 詳細な手順については、 を参照してください <https://go.microsoft.com/fwlink/?LinkId=151982> 。

-   App-V Web 管理サーバー (RTSPS) のサーバー発行ルールを作成します。 詳細な手順については、 を参照してください [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 。

次の図に示すように、インフラストラクチャがクライアントと ISA Server の間、または ISA Server と内部ネットワークの間に他のファイアウォールを実装している場合は、トラフィックのフローをサポートするために RTSPS (TCP 322) と HTTPS (TCP 443) ファイアウォールルールの両方を作成する必要があります。 また、ISA Server と内部ネットワークの間にファイアウォールが実装されている場合は、ドメイン メンバーに必要な既定のトラフィックがファイアウォール (DNS、LDAP、Kerberos、SMB/CIFS) を通過できる必要があります。

![app-v 境界ネットワークファイアウォール図。](images/appvperimeternetworkfirewall.gif)

ファイアウォール ソリューションは環境によって異なりますので、このトピックで示すガイダンスでは、境界ネットワークでインターネットに接続する App-V 環境を構成するために必要なトラフィックについて説明します。 この情報には、推奨される内部ネットワーク サーバーも含まれます。

境界ネットワークに次のサーバーを配置します。

-   App-V 管理サーバー

-   発行およびストリーミング用の IIS サーバー

**備考**  
管理サーバーと IIS サーバーを個別のコンピューターに配置するベスト プラクティスです。

 

内部ネットワークに次のサーバーを配置します。

-   コンテンツ サーバー

-   データ ストア (SQL Server)

-   Active Directory ドメイン コントローラー

## <a name="traffic-requirements"></a>トラフィック要件


次の表に、インターネットと境界ネットワーク、境界ネットワークから内部ネットワークへの通信のトラフィック要件を示します。

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
<td align="left"><p>RTSPS (更新パッケージとストリーミング パッケージの発行)</p></td>
<td align="left"><p>既定では TCP 322。これは、App-V 管理サーバーで変更できます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HTTPS (発行 ICO および OSD ファイルとストリーミング パッケージ)</p></td>
<td align="left"><p>既定では TCP 443。これは IIS 構成で変更できます。</p></td>
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
<td align="left"><p>TCP 1433 は既定ですが、既定で構成SQL Server。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SMB/CIFS</p></td>
<td align="left"><p>コンテンツ ディレクトリが管理サーバーまたは IIS サーバーからリモートに存在する場合 (推奨)。</p></td>
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
<td align="left"><p>内部リソースの名前解決のために (境界ネットワーク サーバーでホストのファイルを使用すると削除できます)</p></td>
</tr>
</tbody>
</table>

 

 

 





