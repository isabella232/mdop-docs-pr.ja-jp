---
title: MBAM 1.0 がサポートされる構成
description: MBAM 1.0 がサポートされる構成
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825937"
---
# MBAM 1.0 がサポートされる構成


このトピックでは、お使いの環境に Microsoft BitLocker 管理と監視 (MBAM) をインストールして実行するために必要な要件を示します。

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM サーバーシステム要件


### サーバーオペレーティングシステム要件

次の表は、Microsoft BitLocker の管理と監視のサーバーインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server 2008</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター、または Web サーバー</p></td>
<td align="left"><p>SP2 のみ</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター、または Web サーバー</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



**Warning**  
MBAM サービス、レポート、データベースのドメインコントローラーコンピューターへのインストールはサポートされていません。



### <a href="" id="server-random-access-memory--ram--requirements-"></a>サーバーランダムアクセスメモリ (RAM) 要件

MBAM サーバーのインストールに固有の RAM 要件はありません。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server データベースの要件

次の表は、MBAM サーバー機能のインストールでサポートされている SQL Server のバージョンを示しています。

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
<th align="left">MBAM サーバー機能</th>
<th align="left">SQL Server のバージョン</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>コンプライアンスと監査レポート</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、Standard、Enterprise、Datacenter、または Developer Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>回復とハードウェアデータベース</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、Enterprise、Datacenter、または Developer Edition</p>
<div class="alert">
<strong>重要</strong><br/><p>SQL Server Standard エディションは、MBAM 回復とハードウェアデータベースサーバー機能のインストールではサポートされていません。</p>
</div>
<div>

</div></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>コンプライアンスと監査データベース</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、Standard、Enterprise、Datacenter、または Developer Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM クライアントシステム要件


### クライアントのオペレーティングシステム要件

次の表は、MBAM クライアントのインストールでサポートされているオペレーティングシステムを示しています。

**注**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>Enterprise Edition</p></td>
<td align="left"><p>なし、SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>究極のエディション</p></td>
<td align="left"><p>なし、SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>クライアント RAM の要件

MBAM クライアントのインストールに固有の RAM 要件はありません。

## 関連トピック


[MBAM 1.0 の展開計画](planning-to-deploy-mbam-10.md)

[MBAM 1.0 展開の前提条件](mbam-10-deployment-prerequisites.md)









