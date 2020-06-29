---
title: DaRT 7.0 でサポートされる構成
description: DaRT 7.0 でサポートされる構成
author: dansimp
ms.assetid: e9ee87b0-3254-4625-b178-17b2f5b8f8c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4b074a061c402f86769e42d873e0119ac54080c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812691"
---
# DaRT 7.0 でサポートされる構成


お客様の環境は、Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 をインストールして実行できるように、ここで説明した構成要件を満たしている可能性があります。 次のような回復イメージとディスク領域の要件があります。

## DaRT 7 の回復イメージの要件


クロスプラットフォームの回復イメージの作成はサポートされていません。 次の表は、エンタープライズで作成して展開する必要がある回復イメージの種類を示しています。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">プラットフォームと DaRT のバージョン</th>
<th align="left">回復イメージの要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>64ビット DaRT 7.0</p></td>
<td align="left"><p>64ビット DaRT 回復イメージを作成して使用します。</p></td>
</tr>
<tr class="even">
<td align="left"><p>32ビット DaRT 7.0</p></td>
<td align="left"><p>32ビット DaRT 回復イメージを作成して使用します。</p></td>
</tr>
</tbody>
</table>

 

## DaRT 7 のエンドユーザコンピューターの要件


DaRT の [**診断/回復ツールセット**] ウィンドウでは、次のオペレーティングシステムのいずれかを dart で利用可能なシステムメモリ容量と共に使用する必要があります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">オペレーティング システム</th>
<th align="left">DaRT のシステム要件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7 64 ビット (2GB)</p></td>
<td align="left"><p>2.5 GB のシステムメモリ</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows7 32 ビット (1 GB)</p></td>
<td align="left"><p>1.5 GB のシステムメモリ</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 (512MB)</p></td>
<td align="left"><p>1 GB のシステムメモリ</p></td>
</tr>
</tbody>
</table>

 

DaRT には、以下の最低限のハードウェア要件もあります。

-   CD または DVD ドライブまたは USB ポート

    これは、CD、DVD、または USB を使用して企業内で DaRT を展開する場合に必要です。

-   CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するための BIOS のサポート

## 関連トピック


[DaRT 7.0 の展開計画](planning-to-deploy-dart-70.md)

 

 





