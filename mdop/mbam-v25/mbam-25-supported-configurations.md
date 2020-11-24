---
title: MBAM 2.5 がサポートされる構成
description: MBAM 2.5 がサポートされる構成
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 8ed7915e33c5e4735a7c58674ed5f7d6da8e9a06
ms.sourcegitcommit: 9087f0a1b5bd3f81a9b790d5e39fdf39c18a2411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182929"
---
# MBAM 2.5 がサポートされる構成


Microsoft BitLocker 管理と監視 (MBAM) 2.5 は、スタンドアロントポロジで、または MBAM を System Center Configuration Manager に統合した構成マネージャーの統合トポロジで実行できます。 運用環境でいずれかのトポロジに推奨される構成を使用している場合、MBAM は最大 50万 MBAM クライアントをサポートします。 各トポロジの各サーバー上で構成される推奨アーキテクチャと機能については、「 [MBAM 2.5 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)」を参照してください。

構成マネージャーの統合トポロジに固有のその他の構成については、「MBAM でサポートされて [いる Configuration manager のバージョン](#bkmk-cm-ramreqs)」を参照してください。

**備考**  
Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、 [ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。



## MBAM でサポートされる言語


次の表は、mbam クライアント (Self-Service ポータルを含む) と mbam 2.5 および mbam 2.5 SP1 でサポートされている言語を示しています。

**MBAM 2.5 SP1 でサポートされる言語:**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">クライアント言語</th>
<th align="left">サーバーの言語</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>チェコ語 (チェコ共和国) .cs-CZ</p>
<p>デンマーク語 (デンマーク) da-DK</p>
<p>オランダ語 (オランダ) nl-NL</p>
<p>英語 (米国) en-us</p>
<p>フィンランド語 (フィンランド) fi</p>
<p>フランス語 (フランス) fr-fr</p>
<p>ドイツ語 (ドイツ) デデュープ</p>
<p>ギリシャ語 (ギリシャ) el-GR</p>
<p>ハンガリー語 (ハンガリー) hu-HU</p>
<p>イタリア語 (イタリア) it IT IT</p>
<p>日本語 (日本) ja-jp</p>
<p>韓国語 (韓国) ko-KR</p>
<p>ノルウェー語、ブークモール (ノルウェー) nb-いいえ</p>
<p>ポーランド語 (ポーランド) pl-PL</p>
<p>ポルトガル語 (ブラジル) pt-BR</p>
<p>ポルトガル語 (ポルトガル) の pt-PT</p>
<p>ロシア語 (ロシア) ru-RU</p>
<p>スロバキア語 (スロバキア) sk-SK</p>
<p>スペイン語 (スペイン) es-ES</p>
<p>スウェーデン語 (スウェーデン) sv-SE</p>
<p>トルコ語 (トルコ) tr-TR</p>
<p>スロベニア語 (スロベニア) sl-SI</p>
<p>簡体字中国語 (PRC) zh-cn&platform-CN</p>
<p>繁体字中国語 (台湾) zh-cn&platform-TW</p></td>
<td align="left"><ul>
<li><p>英語 (米国) en-us</p></li>
<li><p>フランス語 (フランス) fr-fr</p></li>
<li><p>ドイツ語 (ドイツ) デデュープ</p></li>
<li><p>イタリア語 (イタリア) it IT IT</p></li>
<li><p>日本語 (日本) ja-jp</p></li>
<li><p>韓国語 (韓国) ko-KR</p></li>
<li><p>ポルトガル語 (ブラジル) pt-BR</p></li>
<li><p>ロシア語 (ロシア) ru-RU</p></li>
<li><p>スペイン語 (スペイン) es-ES</p></li>
<li><p>簡体字中国語 (PRC) zh-cn&platform-CN</p></li>
<li><p>繁体字中国語 (台湾) zh-cn&platform-TW</p></li>
</ul></td>
</tr>
</tbody>
</table>



**MBAM 2.5 でサポートされる言語:**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">クライアント言語</th>
<th align="left">サーバーの言語</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>英語 (米国) en-us</p></li>
<li><p>フランス語 (フランス) fr-fr</p></li>
<li><p>ドイツ語 (ドイツ) デデュープ</p></li>
<li><p>イタリア語 (イタリア) it IT IT</p></li>
<li><p>日本語 (日本) ja-jp</p></li>
<li><p>韓国語 (韓国) ko-KR</p></li>
<li><p>ポルトガル語 (ブラジル) pt-BR</p></li>
<li><p>ロシア語 (ロシア) ru-RU</p></li>
<li><p>スペイン語 (スペイン) es-ES</p></li>
<li><p>簡体字中国語 (PRC) zh-cn&platform-CN</p></li>
<li><p>繁体字中国語 (台湾) zh-cn&platform-TW</p></li>
</ul></td>
<td align="left"><ul>
<li><p>英語 (米国) en-us</p></li>
<li><p>フランス語 (フランス) fr-fr</p></li>
<li><p>ドイツ語 (ドイツ) デデュープ</p></li>
<li><p>イタリア語 (イタリア) it IT IT</p></li>
<li><p>日本語 (日本) ja-jp</p></li>
<li><p>韓国語 (韓国) ko-KR</p></li>
<li><p>ポルトガル語 (ブラジル) pt-BR</p></li>
<li><p>ロシア語 (ロシア) ru-RU</p></li>
<li><p>スペイン語 (スペイン) es-ES</p></li>
<li><p>簡体字中国語 (PRC) zh-cn&platform-CN</p></li>
<li><p>繁体字中国語 (台湾) zh-cn&platform-TW</p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> MBAM サーバーシステム要件


### MBAM サーバーオペレーティングシステム要件

同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。 たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。

次の表は、MBAM サーバーのインストールでサポートされているオペレーティングシステムを示しています。

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
<td align="left"><p>Windows Server 2019</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>



エンタープライズドメインには、少なくとも1つの Windows Server 2008 (またはそれ以降) のドメインコントローラーが含まれている必要があります。

### <a href="" id="bkmk-stand-alone-ramreqs"></a>MBAM サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ

これらの要件は、MBAM スタンドアロンのトポロジを対象としています。 Configuration Manager の統合トポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク領域の要件-Configuration Manager の統合トポロジ](#bkmk-cm-ramreqs)」を参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェア項目</th>
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



### <a href="" id="bkmk-cm-ramreqs"></a>MBAM サーバープロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ

次の表は、Configuration Manager の統合トポロジを使用している場合に、MBAM サーバーのサーバープロセッサ、RAM、およびディスク領域の要件を示しています。 スタンドアロントポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ](#bkmk-stand-alone-ramreqs)」をご覧ください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェア項目</th>
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
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a>MBAM でサポートされている Configuration Manager のバージョン

MBAM は、次のバージョンの Configuration Manager をサポートしています。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">サポートされているバージョン</th>
<th align="left">Service pack</th>
<th align="left">システムアーキテクチャ</th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager (現在のブランチ)、1902までのバージョン</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>

<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 1806</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager (LTSB-バージョン 1606)</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 構成マネージャー</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2 以降</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p>

&gt;<strong>注 </strong> Configuration Manager 2007 R2 は32ビットですが、64ビット MBAM ソフトウェアと一致させるためには、64ビットのオペレーティングシステムにインストールする必要があります。
</td>
</tr>
</tbody>
</table>



Configuration Manager サーバーでサポートされている構成の一覧については、使用している Configuration Manager のバージョンに対応した TechNet ドキュメントを参照してください。 MBAM には、Configuration Manager サーバーに関する追加のシステム要件はありません。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server データベースの要件

次の表には、回復データベース、コンプライアンスおよび監査データベース、レポート機能など、MBAM Server 機能でサポートされている Microsoft SQL Server バージョンの一覧を示します。 必須バージョンは、スタンドアロンまたは Configuration Manager の統合トポロジに適用されます。

Sql Server は、 **sql \ _Latin1 \ _General \ _CP1 \ _CI \ _AS** にインストールする必要があります。

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
<td align="left"><p>Microsoft SQL Server 2019</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td><br/><tr class="even">
<td align="left"><p>Microsoft SQL Server 2017</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td><br/><tr class="even">
<td align="left"><p>Microsoft SQL Server 2016</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>SP1</p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p>64 ビット</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64 ビット</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>64 ビット</p></td>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>Standard または Enterprise</p></td>
<td align="left"><p>読み</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

**備考**  
MBAM には、サポートされている最大の互換性レベルとして140があります。 SQL Server 2019 で作成された新規データベースの既定の互換性レベルは150で、データベースの作成後に ALTER DATABASE コマンドを使用して、140以下に変更する必要があります。 SQL server 2017 以降から移行された既存のデータベースは、以前の互換性レベルのままであり、変更する必要はありません。

SQL 2016 をサポートするには、MDOP の2017年3月のサービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=54967  ます。また、sql 2017 をサポートするには、mdop 用の7月の2018サービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=57157 ます。 一般的に、最新のサービス更新プログラムには、すべてのバグ修正と新機能が含まれているため、常に最新の状態を維持できます。


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a>SQL Server プロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ

次の表は、スタンドアロントポロジを使用している場合の SQL Server コンピューターに推奨されるサーバープロセッサ、RAM、およびディスク容量の要件を示しています。 これらの要件はガイドとして使用してください。 特定の要件は、企業でサポートしているクライアントコンピューターの数によって異なります。 Configuration Manager の統合トポロジの要件については、「 [SQL Server プロセッサ、RAM、ディスク領域の要件-Configuration manager の統合トポロジ](#bkmk-cm-sql-ramreqs)」を参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェア項目</th>
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



### <a href="" id="bkmk-cm-sql-ramreqs"></a>SQL Server プロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ

次の表は、Configuration Manager の統合トポロジを使用しているときの、Microsoft SQL Server コンピューターのサーバープロセッサ、RAM、ディスク容量の要件を示しています。「 [SQL Server プロセッサ、ram、ディスク容量の要件–スタンドアロントポロジ](#bkmk-sql-stand-alone-ramreqs)」を参照してください。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ハードウェア項目</th>
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
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>空きディスク領域</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM クライアントシステム要件


### クライアントのオペレーティングシステム要件

同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。 たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。

次の表は、MBAM クライアントのインストールでサポートされているオペレーティングシステムを示しています。 同じ要件は、スタンドアロンおよび構成マネージャーの統合トポロジにも適用されます。

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
<tr class="even">
    <td align="left"><p>Windows 10 IoT</p></td>
    <td align="left"><p>Enterprise</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr><br/><tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>Enterprise</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>Enterprise</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>Enterprise または Ultimate</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8.1 および Windows 10 Enterprise</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>クライアント RAM の要件

MBAM クライアントのインストールに固有の RAM 要件はありません。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM グループポリシーのシステム要件


次の表は、MBAM グループポリシーテンプレートのインストールでサポートされているオペレーティングシステムを示しています。

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
 <tr class="even">
      <td align="left"><p>Windows 10 IoT</p></td>
      <td align="left"><p>Enterprise</p></td>
      <td align="left"><p></p></td>
      <td align="left"><p>32 ビットまたは 64 ビット</p></td>
 </tr>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>Enterprise</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>Enterprise</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>Enterprise、または Ultimate</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 ビットまたは 64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準またはデータセンター</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 ビット</p></td>
</tr>
</tbody>
</table>

## Azure IaaS の MBAM

MBAM サーバーは、上記のサポート対象のすべての OS バージョンでサービス (IaaS) として展開することができます。また、オンプレミスでホストされている Active Directory または Azure IaaS にホストされている active directory に接続することもできます。  Azure IaaS で Active Directory をセットアップして構成する方法については、 [こちらをご覧](https://msdn.microsoft.com/library/azure/jj156090.aspx)ください。

MBAM クライアントは仮想マシンではサポートされておらず、Azure IaaS でもサポートされていません。


## サービスリリース 

- [2016年4月の修正プログラム](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [2016年9月](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [2016 年 12 月](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [2017 年 3 月](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [2017 年 6 月](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [2017 年 9 月](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [2018 年 3 月](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [2018年7月](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [2019年5月](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## 関連トピック


[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

[MBAM 2.5 に対応する環境の準備](preparing-your-environment-for-mbam-25.md)




## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




