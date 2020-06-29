---
title: App-V 5.0 SP3 でサポートされる構成
description: App-V 5.0 SP3 でサポートされる構成
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814794"
---
# App-V 5.0 SP3 でサポートされる構成


このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.0 SP3 をインストールして実行するための要件について説明します。

## App-v Server のシステム要件


このセクションでは、すべての App-v Server コンポーネントのオペレーティングシステムとハードウェアの要件を示します。

### サポートされていないアプリ-V 5.0 SP3 サーバーのシナリオ

App-v 5.0 SP3 サーバーでは、次のシナリオはサポートされていません。

-   Microsoft Windows Server Core を実行しているコンピューターへの展開。

-   以前のバージョンの App-v 5.0 SP3 サーバーコンポーネントを実行するコンピューターへの展開。 App-v 5.0 SP3 は、アプリ-V 4.5 軽量ストリーミングサーバー (LWS) サーバーでのみインストールできます。 App-v 4.5 Application Virtualization Management Service (HWS) サーバーを使ったアプリの展開は、サポートされていません。

-   Microsoft SQL Server Express edition を実行しているコンピューターへの展開。

-   管理サーバーデータベースまたはレポートデータベースのリモート展開。 インストーラーは、Microsoft SQL Server を実行しているコンピューターで直接実行する必要があります。

-   ドメインコントローラーへの展開。

-   短いパス。 短いパスを使用する予定の場合は、新しいボリュームを作成する必要があります。

### 管理サーバーのオペレーティングシステム要件

次の表は、app-v 5.0 SP3 Management server のインストールでサポートされているオペレーティングシステムを示しています。

**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

**重要** リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。

 

### <a href="" id="management-server-hardware-requirements-"></a>管理サーバーのハードウェア要件

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 1 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### 管理サーバーのデータベース要件

次の表は、App-v 5.0 SP3 Management データベースのインストールでサポートされている SQL Server のバージョンを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server のバージョン</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>

 

### 発行サーバーのオペレーティングシステム要件

次の表は、app-v 5.0 SP3 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a>発行サーバーのハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### レポートサーバーのオペレーティングシステム要件

次の表は、app-v 5.0 SP3 Reporting server のインストールでサポートされているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a>レポートサーバーのハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク空き容量

### レポートサーバーデータベースの要件

次の表は、App-v 5.0 SP3 レポートデータベースのインストールでサポートされている SQL Server のバージョンを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server のバージョン</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a>App-v クライアントシステム要件


次の表は、App-v 5.0 SP3 クライアントのインストールでサポートされているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 8.1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>

 

次のような App-v クライアントインストールシナリオはサポートされていません。記載されている場合を除きます。

-   Windows Server を実行しているコンピューター

-   App-v 4.6 SP1 またはそれ以前のバージョンを実行しているコンピューター

-   App-v 5.0 SP3 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。

### <a href="" id="app-v-client-hardware-requirements-"></a>App-v クライアントハードウェア要件

次の一覧は、App-v 5.0 SP3 クライアントのインストールでサポートされているハードウェア構成を示しています。

-   プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ

-   RAM: 1 GB (32 ビット) または 2 GB (64 ビット)

-   ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。

## リモートデスクトップサービスクライアントシステム要件


次の表は、App-v 5.0 SP3 リモートデスクトップサービス (RDS) クライアントのインストールでサポートされているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

 

### リモートデスクトップサービスクライアントハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク空き容量

## Sequencer システム要件


次の表は、App-v 5.0 SP3 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server2012 R2</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8.1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットと 64 ビット</p></td>
</tr>
</tbody>
</table>

 

### Sequencer ハードウェア要件

ハードウェア要件については、Windows または Windows Server のマニュアルを参照してください。 App-v は、追加のハードウェア要件を追加しません。

## <a href="" id="bkmk-supp-ver-sccm"></a>サポートされている System Center Configuration Manager のバージョン


App-v クライアントでは、次のバージョンの System Center Configuration Manager がサポートされています。

-   MicrosoftSystemCenter2012 ConfigurationManager

-   System Center 2012 R2 Configuration Manager

-   System Center 2012 R2 Configuration Manager SP1

Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。






## 関連トピック


[App-V の展開計画](planning-to-deploy-app-v.md)

[APP-V 5.0 SP3 の前提条件](app-v-50-sp3-prerequisites.md)

 

 





