---
title: Application Virtualization Sequencer のハードウェア要件とソフトウェア要件
description: Application Virtualization Sequencer のハードウェア要件とソフトウェア要件
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819624"
---
# Application Virtualization Sequencer のハードウェア要件とソフトウェア要件


このトピックでは、Microsoft Application Virtualization (App-v) Sequencer を実行しているコンピューターの最低限の推奨されるハードウェアとソフトウェアの要件について説明します。

**重要** Sequencer がローカルシステムに行った変更のため、管理者特権を持つアカウントを使用して、App-v sequencer (**SFTSequencer.exe**) を実行する必要があります。 これらの変更には、C:\ の**ファイル**ディレクトリへのファイルの書き込み、レジストリの変更、サービスの開始と停止、ファイルのセキュリティ記述子の更新、アクセス許可の変更などがあります。

 

Sequencer をインストールする前に、各アプリケーションの順序を指定した後、クリーンなオペレーティングシステムイメージをシーケンスコンピューターに復元する必要があります。 Sequencer を実行しているコンピューターを復元するには、次のいずれかの方法を使用できます。

-   ハードドライブを再フォーマットして、オペレーティングシステムを再インストールします。

-   別のディスクイメージングソフトウェアを使用して、Sequencer イメージを実行しているコンピューターのハードドライブを復元します。

-   Microsoft Virtual PC イメージなどの仮想オペレーティングシステムイメージを元に戻します。 仮想マシンを使用すると、最小限の管理で簡単に再利用できるようになります。

次のリストは、App-v Sequencer を実行するために推奨されるハードウェア要件の概要を示しています。

要件は、Microsoft Application Virtualization (App-v) 4.6 SP2 の後に記載されています。その後に、App-v 4.6 SP2 より前のバージョンの要件が示されています。

### <a href="" id="hardware-requirements-"></a>ハードウェア要件

-   プロセッサ: Intel Pentium III、1 GHz (32 ビットまたは64ビット)。 シーケンス処理はシングルスレッドプロセスであり、デュアルプロセッサは利用できません。

-   メモリ: 1 GB 以上、2 GB 推奨。

-   ハードディスク:40 gb のハードディスク容量 (使用可能なハードディスク容量は最低 15 GB)。 順序を設定するアプリケーションで必要なハードディスク容量が少なくとも3回あることをお勧めします。

    **注** シーケンス処理には、負荷の高いディスク使用が必要です。 高速なディスク速度では、優先順位付けの時間を減らすことができます。

     

### App-v 4.6 SP2 のソフトウェア要件

次のリストは、App-v 4.6 SP2 Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。

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
<td align="left"><p>読み</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8</p></td>
<td align="left"><p>Pro または Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 and x64 (x86 と x64)</p></td>
</tr>
</tbody>
</table>

 

**注** Application Virtualization (App-v) 4.6 SP2 Sequencer では、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。

 

ターゲットコンピューターにインストールされているアプリケーションと同じアプリケーションを使って、Sequencer を実行しているコンピューターを構成する必要があります。

### App-v 4.6 SP2 より前のバージョンのソフトウェア要件

次の一覧は、App-v 4.6 SP2 より前のバージョンで Sequencer を実行するためにサポートされているオペレーティングシステムの概要を示しています。

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

### App-v 4.6 SP2 用のリモートデスクトップサービスのソフトウェア要件

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
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
</tbody>
</table>

 

**注** Application Virtualization (App-v) 4.6 SP2 リモートデスクトップサービスでは、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。

 

### App-V 4.6 SP2 より前のバージョンのリモートデスクトップサービスのソフトウェア要件

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
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP1 がない</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

**注** Application Virtualization (App-v) 4.6 SP2 リモートデスクトップサービスでは、これらのオペレーティングシステムの32ビットバージョンと64ビットバージョンがサポートされています。

 

## 関連トピック


[Application Virtualization Client のハードウェア要件とソフトウェア要件](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization のシステム要件](application-virtualization-system-requirements.md)

[Application Virtualization Sequencer をインストールする方法](how-to-install-the-application-virtualization-sequencer.md)

[Application Virtualization Sequencer をアップグレードする方法](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





