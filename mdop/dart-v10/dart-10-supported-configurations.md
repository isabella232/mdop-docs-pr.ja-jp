---
title: DaRT 10 でサポートされる構成
description: DaRT 10 でサポートされる構成
author: dansimp
ms.assetid: a07d6562-1fa9-499f-829c-9cc487ede0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 414b9d5cb7bf78dcfeda3fafc1c476e367709446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813138"
---
# DaRT 10 でサポートされる構成


このトピックでは、お客様の環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 10 をインストールして実行するために必要な、必須ソフトウェアとサポートされる構成要件を示します。 DaRT 10 を実行するために必要なオペレーティングシステム要件とシステム要件の両方が指定されています。 DaRT リカバリ画像の作成について考慮する必要がある前提条件については、「 [dart 10 リカバリイメージの作成の計画](planning-to-create-the-dart-10-recovery-image.md)」をご覧ください。

以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。

DaRT は、次の2つのいずれかの方法でインストールできます。 すべての機能を IT 管理者のコンピューターにインストールして、DaRT の実行に関連するすべてのタスクを実行することができます。 または、管理者のコンピューターで、回復イメージを作成する DaRT 機能のみをインストールして、DaRT (つまり DaRT リモート接続ビュアー) を実行するために使用された機能をヘルプデスクコンピューターにインストールすることもできます。

## DaRT 10 の必須ソフトウェア


DaRT をインストールする前に、次の前提条件が満たされていることを確認してください。

### 管理者コンピューターの前提条件

以下の表に、DaRT 10 とすべての DaRT ツールをインストールするときの管理者コンピューターのインストール前提条件を示します。

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
<td align="left"><p><strong>Windows 開発キットまたはソフトウェア開発キット (オプション)</strong></p></td>
<td align="left"><p>クラッシュアナライザーでは、windows ドライバーキットの Windows 10 デバッグツールを使って、メモリダンプファイルを解析する必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 10 64 ビットまたは32ビット ISO イメージ</strong></p></td>
<td align="left"><p>DaRT には windows 10 メディアの Windows 回復環境 (Windows RE) イメージが必要です。 作成する DaRT 回復イメージの種類に応じて、32ビット版または64ビット版の Windows 10 をダウンロードします。 環境で両方のシステムの種類をサポートしている場合は、両方のバージョンの Windows 10 をダウンロードします。</p></td>
</tr>
</tbody>
</table>

 

### ヘルプデスクコンピューターの前提条件

次の表は、DaRT 10 リモート接続ビューアーを実行しているときの、ヘルプデスクコンピューターのインストールの前提条件を示しています。

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
<td align="left"><p><strong>DaRT 10 リモート接続ビューアー</strong></p></td>
<td align="left"><p>Windows 10 オペレーティングシステムにインストールされている必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Debugging Tools for Windows</strong></p></td>
<td align="left"><p>クラッシュ解析ツールをインストールする場合にのみ必須</p></td>
</tr>
</tbody>
</table>

 

### エンドユーザーコンピューターの前提条件

Windows 10 オペレーティングシステム以外のエンドユーザーコンピューターにインストールする必要がある必須のソフトウェアはありません。

## <a href="" id="---------dart-10-operating-system-requirements"></a> DaRT 10 オペレーティングシステム要件


### 管理者のコンピューターのシステム要件

次の表は、DaRT 10 管理者コンピューターのインストールでサポートされているオペレーティングシステムを示しています。

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
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> DaRT ヘルプデスクコンピュータのシステム要件

ヘルプデスクでコンピューターのリモートトラブルシューティングを行うことを許可している場合は、リモート接続ビューアーをヘルプデスクコンピューターにインストールしておく必要があります。 必要に応じて、クラッシュ分析ツールをヘルプデスクコンピューターにインストールできます。

DaRT 10 では、dart 7.0、DaRT 8.0、DaRt 8.1、または DaRT 10 リモート接続ビューアーを使って、DaRT 10 コンピュータに接続することができます。 Dart 7.0、DaRT 8.0、DaRt 8.1 では、リモート接続ビューアーにそれぞれ Windows 7、Windows 8、または Windows 8.1 オペレーティングシステムが必要ですが、DaRT 10 リモート接続ビューアーには Windows 10 が必要です。 DaRT 10 リモート接続ビューアーとその他のすべての DaRT 10 ツールは、Windows 10 を実行しているコンピュータにのみインストールできます。

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
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 (リモート接続ビューアー10.0 のみ)</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
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
<td align="left"><p>2 GB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 R2</p></td>
<td align="left"><p>標準、エンタープライズ、データセンター</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>1.0 GB</p></td>
</tr>
</tbody>
</table>

 

DaRT には、エンドユーザのコンピュータに関する以下の最小ハードウェア要件もあります。

CD または DVD のドライブまたは USB ポート: CD、DVD、または USB を使用して、企業内で DaRT を展開する場合にのみ必要です。

BIOS は、CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するためにサポートされています。

### <a href="" id="-------------dart-10-end-user-computer-system-requirements"></a> DaRT 10 エンドユーザーコンピューターのシステム要件

DaRT 10 の [診断と回復] のツールセットウィンドウでは、DaRT で利用可能なシステムメモリの容量と共に、エンドユーザーのコンピューターで次のいずれかのオペレーティングシステムを使用する必要があります。

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
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>64 ビット</p></td>
<td align="left"><p>2 GB</p></td>
<td align="left"><p>2.5 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>すべてのエディション</p></td>
<td align="left"><p>なし</p></td>
<td align="left"><p>32 ビット</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>1.5 GB</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[DaRT 10 の展開計画](planning-to-deploy-dart-10.md)

 

 





