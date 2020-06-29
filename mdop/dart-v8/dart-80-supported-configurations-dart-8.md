---
title: DaRT 8.0 でサポートされる構成
description: DaRT 8.0 でサポートされる構成
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823927"
---
# DaRT 8.0 でサポートされる構成


このトピックでは、お客様の環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 8.0 をインストールして実行するために必要な、必須ソフトウェアとサポートされる構成要件を示します。 DaRT 8.0 を実行するために必要なオペレーティングシステム要件とシステム要件の両方が指定されています。 DaRT リカバリ画像の作成について考慮する必要がある前提条件については、「 [dart 8.0 リカバリイメージの作成の計画](planning-to-create-the-dart-80-recovery-image-dart-8.md)」を参照してください。

以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。

DaRT は、次の2つのいずれかの方法でインストールできます。 すべての機能を IT 管理者のコンピューターにインストールして、DaRT の実行に関連するすべてのタスクを実行することができます。 または、管理者のコンピューターで、回復イメージを作成する DaRT 機能のみをインストールして、DaRT (つまり DaRT リモート接続ビュアー) を実行するために使用された機能をヘルプデスクコンピューターにインストールすることもできます。

## <a href="" id="---------dart-8-0-prerequisite-software"></a> DaRT 8.0 の必須ソフトウェア


DaRT をインストールする前に、次の前提条件が満たされていることを確認してください。

### 管理者コンピューターの前提条件

以下の表に、DaRT 8.0 およびすべての DaRT ツールをインストールするときの管理者コンピューターのインストール前提条件を示します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows アセスメント & 開発キット (ADK)</strong></p></td>
<td align="left"><p>DaRT リカバリ画像ウィザードに必要。 Windows イメージのカスタマイズ、展開、サービスのために使用される展開ツールが含まれており、Windows Preinstallation Environment (Windows PE) が含まれています。 ADK は、リモート接続ビューアーと Crash Analyzer のどちらかまたは両方をインストールする場合には必要ありません。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>.NET Framework 4.5</strong></p></td>
<td align="left"><p>DaRT リカバリ画像ウィザードで必要。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 開発キットまたはソフトウェア開発キット (オプション)</strong></p></td>
<td align="left"><p>クラッシュアナライザーでは、windows ドライバーキットの Windows 8 デバッグツールを使って、メモリダンプファイルを解析する必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Windows 8 64 ビット ISO イメージ</strong></p></td>
<td align="left"><p>DaRT には windows 8 メディアの windows 回復環境 (Windows RE) イメージが必要です。 作成する DaRT 回復イメージの種類に応じて、32ビット版または64ビット版の Windows 8 をダウンロードします。 環境で両方のシステムの種類をサポートしている場合は、両方のバージョンの Windows 8 をダウンロードします。</p></td>
</tr>
</tbody>
</table>

 

### ヘルプデスクコンピューターの前提条件

次の表は、DaRT 8.0 リモート接続ビューアーを実行しているときの、ヘルプデスクコンピューターのインストールの前提条件を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">詳細</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>DaRT 8.0 リモート接続ビューアー</strong></p></td>
<td align="left"><p>Windows 8 オペレーティングシステムにインストールされている必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>NET Framework 4.5</strong></p></td>
<td align="left"><p>DaRT リカバリ画像ウィザードで必要</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Debugging Tools for Windows</strong></p></td>
<td align="left"><p>クラッシュ解析ツールをインストールする場合にのみ必須</p></td>
</tr>
</tbody>
</table>

 

### エンドユーザーコンピューターの前提条件

Windows 8 オペレーティングシステム以外のエンドユーザーコンピューターにインストールする必要がある必須のソフトウェアはありません。

## <a href="" id="---------dart-operating-system-requirements"></a> DaRT オペレーティングシステムの要件


### 管理者のコンピューターのシステム要件

次の表は、DaRT 管理者のコンピューターのインストールでサポートされているオペレーティングシステムを示しています。

**注** 管理者のコンピューターにインストールする追加のツールに十分な領域を割り当てていることを確認してください。

 

**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。 お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。 Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
<th align="left">オペレーティング システムの要件</th>
<th align="left">DaRT を実行するための RAM 要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1. 0 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> DaRT ヘルプデスクコンピュータのシステム要件

ヘルプデスクでコンピューターのリモートトラブルシューティングを行うことを許可している場合は、リモート接続ビューアーをヘルプデスクコンピューターにインストールしておく必要があります。 必要に応じて、クラッシュ分析ツールをヘルプデスクコンピューターにインストールできます。

DaRT 8.0 では、DaRT 7.0 または DaRT 8.0 のリモート接続ビューアーを使用して、ヘルプデスクワーカーが DaRT 8.0 コンピューターに接続することを可能にします。 DaRT 7.0 リモート接続ビューアーには Windows 7 オペレーティングシステムが必要ですが、DaRT 8.0 リモート接続ビューアーには Windows 8 が必要です。 DaRT 8.0 リモート接続ビューアーとその他のすべての DaRT 8.0 ツールは、Windows 8 を実行しているコンピュータにのみインストールできます。

次の表は、DaRT ヘルプデスクのコンピューターのインストールでサポートされているオペレーティングシステムを示しています。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
<th align="left">オペレーティング システムの要件</th>
<th align="left">DaRT を実行するための RAM 要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8 (リモート接続ビューアー8.0 のみ)</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 (リモート接続ビューアー7.0 のみ)</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64ビットまたは32ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>51</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

DaRT には、エンドユーザのコンピュータに関する以下の最小ハードウェア要件もあります。

CD または DVD のドライブまたは USB ポート: CD、DVD、または USB を使用して、企業内で DaRT を展開する場合にのみ必要です。

BIOS は、CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するためにサポートされています。

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> DaRT エンドユーザコンピューターのシステム要件

DaRT の [診断と回復] のツールセットウィンドウでは、DaRT で利用可能なシステムメモリの容量と共に、エンドユーザーのコンピューターで次のいずれかのオペレーティングシステムを使用する必要があります。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">エディション</th>
<th align="left">Service Pack</th>
<th align="left">システムアーキテクチャ</th>
<th align="left">オペレーティング システムの要件</th>
<th align="left">RAM の要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>512 MB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[DaRT 8.0 の展開計画](planning-to-deploy-dart-80-dart-8.md)

 

 





