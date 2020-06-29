---
title: Sequencer のハードウェア要件とソフトウェア要件
description: Sequencer のハードウェア要件とソフトウェア要件
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815534"
---
# Sequencer のハードウェア要件とソフトウェア要件


このトピックでは、Microsoft Application Virtualization (App-v) Sequencer を実行しているコンピューターの最低限の推奨されるハードウェアとソフトウェアの要件について説明します。

Sequencer をインストールする前に、各アプリケーションの順序を指定した後、クリーンなオペレーティングシステムイメージをシーケンスコンピューターに復元する必要があります。 Sequencer を実行しているコンピューターを復元するには、次のいずれかの方法を使用できます。

-   ハードドライブを再フォーマットして、オペレーティングシステムを再インストールします。

-   別のディスクイメージングソフトウェアを使用して、Sequencer イメージを実行しているコンピューターのハードドライブを復元します。

次のリストは、App-v Sequencer を実行するために推奨されるハードウェア要件の概要を示しています。

### <a href="" id="hardware-requirements-"></a>ハードウェア要件

-   プロセッサ: Intel Pentium III、1 GHz (32 ビットまたは64ビット)。 シーケンス処理はシングルスレッドプロセスであり、デュアルプロセッサは利用できません。

-   メモリ: 1 gb 以上、推奨される 2 GB。

-   ハードディスク:40 gb のハードディスク容量 (使用可能なハードディスク容量は最低 15 GB)。 順序を設定するアプリケーションで必要なハードディスク容量が少なくとも3回あることをお勧めします。

    **注** シーケンス処理には、負荷の高いディスク使用が必要です。 高速なディスク速度では、優先順位付けの時間を減らすことができます。

     

### ソフトウェア要件

次のリストは、Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。

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
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>Professional</p></td>
<td align="left"><p>SP2 または SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極</p></td>
<td align="left"><p>Service pack、SP1、または SP2 がない</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

¹ SP1 または SP2 を搭載した App-v 4.5 でサポートされているアプリ-V 4.6

**注** Application Virtualization (App-v) 4.6 Sequencer では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。

 

ターゲットコンピューターにインストールされているアプリケーションと同じアプリケーションを使って、Sequencer を実行しているコンピューターを構成する必要があります。

### リモートデスクトップサービスのソフトウェア要件

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
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、またはデータセンター</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

**注** Application Virtualization (App-v) 4.6 for Remote Desktop Services では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。

 

## 関連トピック


[Application Virtualization Sequencer の概要](application-virtualization-sequencer-overview.md)

 

 





