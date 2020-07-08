---
title: App-V 5.1 でサポートされる構成
description: App-V 5.1 でサポートされる構成
author: dansimp
ms.assetid: 8b8db63b-f71c-4ae9-80e7-a6752334e1f6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/02/2020
ms.openlocfilehash: fbda364de66b1f7b8730dca38f864a84f7848e58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814723"
---
# App-V 5.1 でサポートされる構成

>適用対象: Windows 10 バージョン 1607;Window Server 2019;Windows Server 2016Windows Server 2012 R2Windows Server 2012Windows Server 2008 R2 (拡張セキュリティ更新プログラム)

このトピックでは、お客様の環境に Microsoft Application Virtualization (App-v) 5.1 をインストールして実行するための要件について説明します。

## App-v Server のシステム要件

このセクションでは、すべての App-v Server コンポーネントのオペレーティングシステムとハードウェアの要件を示します。

### サポートされていない App-v 5.1 サーバーのシナリオ

App-v 5.1 サーバーでは、次のシナリオはサポートされていません。

-   Microsoft Windows Server Core を実行しているコンピューターへの展開。

-   以前のバージョンの App-v 5.1 サーバーコンポーネントを実行しているコンピューターへの展開。 App-v 5.1 は、アプリ-V 4.5 軽量ストリーミングサーバー (LWS) サーバーでのみインストールできます。 App-v 4.5 Application Virtualization Management Service (HWS) サーバーを使ったアプリの展開は、サポートされていません。

-   Microsoft SQL Server Express edition を実行しているコンピューターへの展開。

-   ドメインコントローラーへの展開。

-   短いパス。 短いパスを使用する予定の場合は、新しいボリュームを作成する必要があります。

### 管理サーバーのオペレーティングシステム要件

次の表は、App-v 5.1 Management server のインストールでサポートされているオペレーティングシステムを示しています。

> [!NOTE]
> Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。

 | オペレーティング システム                 | Service Pack | システムアーキテクチャ |
|----------------------------------|--------------|---------------------|
| Microsoft Windows Server 2019    |              |        64 ビット       |
| Microsoft Windows Server 2016    |              |        64 ビット       |
| Microsoft Windows Server 2012 R2 |              |        64 ビット       |
| Microsoft Windows Server 2012    |              |        64 ビット       |
| Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates)|      SP1     |        64 ビット       |
 

**重要** リモートデスクトップ共有 (RDS) が有効になっているコンピューターへの管理サーバーの役割の展開はサポートされていません。

 

### <a href="" id="management-server-hardware-requirements-"></a>管理サーバーのハードウェア要件

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 1 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### 管理サーバーのデータベース要件

次の表は、App-v 5.1 Management データベースのインストールでサポートされている SQL Server のバージョンを示しています。

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
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2019</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>

<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2017</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2016</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p>SP2</p></td>
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

SQL server 2016 以降のユーザー構成ファイルの詳細については、[サポートの記事](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f)を参照してください。

### 発行サーバーのオペレーティングシステム要件

次の表は、App-v 5.1 発行サーバーのインストールでサポートされているオペレーティングシステムを示しています。

| オペレーティング システム                 | Service Pack | システムアーキテクチャ |
|----------------------------------|--------------|---------------------|
| Microsoft Windows Server 2019    |              |        64 ビット       |
| Microsoft Windows Server 2016    |              |        64 ビット       |
| Microsoft Windows Server 2012 R2 |              |        64 ビット       |
| Microsoft Windows Server 2012    |              |        64 ビット       |
| Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates) |      SP1     |        64 ビット       |

### <a href="" id="publishing-server-hardware-requirements-"></a>発行サーバーのハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### レポートサーバーのオペレーティングシステム要件

次の表は、App-v 5.1 Reporting server のインストールでサポートされているオペレーティングシステムを示しています。

| オペレーティング システム                 | Service Pack | システムアーキテクチャ |
|----------------------------------|--------------|---------------------|
| Microsoft Windows Server 2019    |              |        64 ビット       |
| Microsoft Windows Server 2016    |              |        64 ビット       |
| Microsoft Windows Server 2012 R2 |              |        64 ビット       |
| Microsoft Windows Server 2012    |              |        64 ビット       |
| Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates) |      SP1     |        64 ビット       |

### <a href="" id="reporting-server-hardware-requirements-"></a>レポートサーバーのハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク空き容量

### レポートサーバーデータベースの要件

次の表は、App-v 5.1 Reporting database のインストールでサポートされている SQL Server のバージョンを示しています。

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
<td align="left"><p>Microsoft SQL Server 2017</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2016</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p>SP2</p></td>
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

次の表は、App-v 5.1 クライアントのインストールでサポートされているオペレーティングシステムを示しています。

> [!NOTE]
> Windows 10 記念日リリース (1607 バージョン) では、app-v クライアントはボックス内にあり、以前のバージョンの App-v クライアントのインストールはブロックされます。

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
<td align="left"><p>Microsoft Windows 10 (1607 以前のバージョン)</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8.1</p></td>
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

-   App-v 5.1 リモートデスクトップサービスクライアントは、RDS 対応サーバーでのみサポートされます。

### <a href="" id="app-v-client-hardware-requirements-"></a>App-v クライアントハードウェア要件

次の一覧は、App-v 5.1 クライアントのインストールでサポートされているハードウェア構成を示しています。

-   プロセッサ: 1.4 GHz 以上32ビット (x86) または64ビット (x64) プロセッサ

-   RAM: 1 GB (32 ビット) または 2 GB (64 ビット)

-   ディスク: 100 MB インストールの場合、仮想化されたアプリケーションによって使用されるディスク領域は含まれません。

## リモートデスクトップサービスクライアントシステム要件


次の表は、App-v 5.1 リモートデスクトップサービス (RDS) クライアントのインストールでサポートされているオペレーティングシステムを示しています。

| オペレーティング システム                 | Service Pack | システムアーキテクチャ |
|----------------------------------|--------------|---------------------|
| Microsoft Windows Server 2019    |              |        64 ビット       |
| Microsoft Windows Server 2016    |              |        64 ビット       |
| Microsoft Windows Server 2012 R2 |              |        64 ビット       |
| Microsoft Windows Server 2012    |              |        64 ビット       |
| Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates) |      SP1     |        64 ビット       |

### リモートデスクトップサービスクライアントハードウェア要件

App-v では、Windows Server の場合以外に追加要件はありません。

-   プロセッサ: 1.4 GHz 以上、64ビット (x64) プロセッサ

-   RAM: 2 GB RAM (64 ビット)

-   ディスク領域: 200 MB のハードディスク空き容量

## Sequencer システム要件

次の表は、App-v 5.1 Sequencer のインストールでサポートされているオペレーティングシステムを示しています。

| オペレーティング システム                 | Service Pack | システムアーキテクチャ |
|----------------------------------|--------------|---------------------|
| Microsoft Windows Server 2019    |              |        64 ビット       |
| Microsoft Windows Server 2016    |              |        64 ビット       |
| Microsoft Windows Server 2012 R2 |              |        64 ビット       |
| Microsoft Windows Server 2012    |              |        64 ビット       |
| Microsoft Windows Server 2008 R2[拡張セキュリティ更新プログラム](https://www.microsoft.com/windows-server/extended-security-updates) |      SP1     |        64 ビット       |
| Microsoft Windows 10             |              | 32 ビットと 64 ビット   |
| Microsoft Windows 8.1            |              | 32 ビットと 64 ビット   |
| Microsoft Windows 7              |      SP1     | 32 ビットと 64 ビット   |

### Sequencer ハードウェア要件

ハードウェア要件については、Windows または Windows Server のマニュアルを参照してください。 App-v は、追加のハードウェア要件を追加しません。

## <a href="" id="bkmk-supp-ver-sccm"></a>サポートされている System Center Configuration Manager のバージョン

App-v クライアントでは、次のバージョンの System Center Configuration Manager がサポートされています。

-   MicrosoftSystemCenter2012 ConfigurationManager

-   System Center 2012 R2 Configuration Manager

-   System Center 2012 R2 Configuration Manager SP1

次の App-v および System Center Configuration Manager のバージョンマトリックスには、すべての正式にサポートされている App-v と構成マネージャーの組み合わせが表示されます。

> [!NOTE]
> App-v 4.5 と4.6 の両方が、メインストリームサポートを終了しました。

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v のバージョン</th>
<th align="left">System Center Configuration Manager 2007</th>
<th align="left">System Center 2012 Configuration Manager</th>
<th align="left">System Center 2012 Configuration Manager SP1</th>
<th align="left">System Center 2012 R2 Configuration Manager</th>
<th align="left">System Center 2012 R2 Configuration Manager SP1</th>
<th align="left">System Center 2012 Configuration Manager SP2</th>
<th align="left">System Center Configuration Manager バージョン1511</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 5.0 SP3</p></td>
<td align="left"><p>MSI ラッパーのみ</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>2012 SP1 CU4</p></td>
<td align="left"><p>2012 R2 CU1</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 5.1</p></td>
<td align="left"><p>MSI ラッパーのみ</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>2012 SP1 CU4</p></td>
<td align="left"><p>2012 R2 CU1</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
<td align="left"><p>あり</p></td>
</tr>
</tbody>
</table>

 

Configuration Manager と App-v の統合の詳細については、「 [Configuration manager を使用した app-v との統合の計画](https://technet.microsoft.com/library/jj822982.aspx)」を参照してください。

## 関連トピック

[App-V の展開計画](planning-to-deploy-app-v51.md)

[App-V 5.1 の前提条件](app-v-51-prerequisites.md)
