---
title: MBAM 2.0 がサポートされる構成
description: MBAM 2.0 がサポートされる構成
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823907"
---
# MBAM 2.0 がサポートされる構成


このトピックでは、スタンドアロントポロジを使用して、お客様の環境で Microsoft BitLocker 管理と監視 (MBAM) 2.0 をインストールして実行するための要件を示します。 以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。

Configuration Manager トポロジを使用して MBAM 2.0 をインストールし、システム要件の一覧を確認したい場合は、「 [Configuration manager で MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。

運用環境で MBAM を実行するために推奨される構成は、スケーラビリティの要件に応じて、2つのサーバーを使用することです。 この構成では、最大 20万 MBAM クライアントがサポートされています。 スタンドアロンの MBAM サーバーインフラストラクチャの画像と説明については、「 [mbam 2.0 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-20-mbam-2.md)」を参照してください。

**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。

 

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM サーバーシステム要件


### サーバーオペレーティングシステム要件

次の表は、Microsoft BitLocker の管理と監視のサーバーインストールでサポートされているオペレーティングシステムを示しています。

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
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsServer2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer2012</p></td>
<td align="left"><p>Standard Edition または Datacenter Edition</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

**注** MBAM サービス、レポート、データベースのドメインコントローラーコンピューターへのインストールはサポートされていません。

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a>サーバープロセッサ、RAM、ディスク容量の要件

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェアコンポーネント</th>
<th align="left">最小要件</th>
<th align="left">推奨要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>処理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a>SQLServer データベースの要件

次の表に、管理および監視サーバー機能のインストールでサポートされている SQLServer バージョンの一覧を示します。これには、回復データベース、コンプライアンスと監査データベース、コンプライアンスおよび監査レポートが含まれます。 また、データベースには、SQL Server 管理ツールをインストールする必要があります。

**注** MBAM は、SQL クラスタリング、ミラーリング、または可用性グループをネイティブでサポートしていません。 データベースをインストールするには、スタンドアロンの SQL Server で MBAM サーバーインストールを実行する必要があります。

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server のバージョン</th>
<th align="left">エディション</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftSQLServer2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftSQLServer2012</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェアコンポーネント</th>
<th align="left">最小要件</th>
<th align="left">推奨要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>処理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 以上</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> MBAM クライアントシステム要件


### クライアントのオペレーティングシステム要件

次の表は、Microsoft BitLocker の管理とクライアントのインストールの監視がサポートされているオペレーティングシステムを示しています。

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
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>Enterprise または Ultimate Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8 Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a>クライアント RAM の要件

Microsoft BitLocker の管理と監視クライアントインストールに固有の RAM 要件はありません。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM グループポリシーのシステム要件


次の表は、Microsoft BitLocker 管理およびグループポリシーテンプレートのインストールがサポートされているオペレーティングシステムの一覧です。

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
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>Enterprise、または Ultimate Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>Standard Edition または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[MBAM 2.0 の展開計画](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 展開の前提条件](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





