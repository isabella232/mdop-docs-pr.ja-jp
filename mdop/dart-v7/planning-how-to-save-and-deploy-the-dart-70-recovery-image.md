---
title: DaRT 7.0 の回復イメージの保存および展開方法の計画
description: DaRT 7.0 の回復イメージの保存および展開方法の計画
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822797"
---
# DaRT 7.0 の回復イメージの保存および展開方法の計画


Microsoft 診断/回復ツールセット (DaRT) 7 の回復イメージの保存と展開を計画している場合は、このセクションの情報を使用してください。

## DaRT リカバリイメージの保存と展開の計画


DaRT リカバリ画像を保存して展開するには、次の方法を使用します。 使用する方法を決定する際には、それぞれの長所と短所を考慮してください。 また、企業での DaRT の使用方法についても検討してください。

**注** 組織では、複数の方法を使用することができます。 たとえば、ほとんどの状況についてはリモートのパーティションから DaRT を起動し、エンドユーザーのコンピューターがネットワークに接続できない場合は USB フラッシュドライブを使用できます。

 

次の表では、組織で DaRT を使用する方法の利点と欠点をいくつか示します。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">DaRT で起動する方法</th>
<th align="left">長所</th>
<th align="left">短所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CD または DVD から</p></td>
<td align="left"><p>マスターブートレコード (MBR) が破損していて、ハードディスクにアクセスできないシナリオがサポートされています。 また、ネットワーク接続がない場合もサポートします。</p>
<p>これは、以前のバージョンの DaRT を使用するユーザーにとって最も使い慣れた機能であり、CD-R または DVD は dart の回復イメージウィザードから直接書き込むことができ <strong> </strong> ます。</p></td>
<td align="left"><p>この CD または DVD へのアクセス権を持つユーザーが、DaRT で起動するために、エンドユーザーのコンピューターに物理的にアクセスしている必要があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>USB フラッシュドライブ (UFD) から</p></td>
<td align="left"><p>CD または DVD からの起動と同じように、CD または DVD ドライブを備えていないコンピューターのサポートも提供します。</p></td>
<td align="left"><p>DaRT でブートするために使用する前に、UFD の書式を設定する必要があります。 また、UFD へのアクセス権を持つユーザーは、DaRT で起動するために、エンドユーザーのコンピューターに物理的にアクセスする必要があります。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>リモート (ネットワーク) パーティションから</p></td>
<td align="left"><p>CD、DVD、または UFD がなくても DaRT を起動できます。 また、更新するファイルの場所が1つしかないため、DaRT を簡単にアップグレードできます。</p></td>
<td align="left"><p>エンドユーザーのコンピューターがネットワークに接続されていない場合は、機能しません。</p>
<p>エンドユーザーが広く利用できるようになり、回復イメージを作成するときに、追加のセキュリティの考慮事項が必要な場合があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>回復パーティションから</p></td>
<td align="left"><p>ネットワーク接続がない場合でも、CD、DVD、または UFD がなくても DaRT を起動できます。</p>
<p>また、Microsoft Endpoint Configuration Manager などの自動化された配布ツールを使用して、標準の Windows イメージプロセスの一部として実装し、管理することもできます。</p></td>
<td align="left"><p>DaRT を更新する場合は、1つのパーティション (ネットワーク上) またはデバイス (CD、DVD、または UFD) だけでなく、企業内のすべてのコンピューターを更新する必要があります。</p></td>
</tr>
</tbody>
</table>

 

## 関連トピック


[DaRT 7.0 の展開計画](planning-to-deploy-dart-70.md)

 

 





