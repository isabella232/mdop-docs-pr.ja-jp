---
title: Application Virtualization のシステム要件
description: Application Virtualization のシステム要件
author: dansimp
ms.assetid: a2798dd9-168e-45eb-8103-e12e128fae7c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c160a7532b521bb41570b419b22b9e7daaec2987
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819517"
---
# Application Virtualization のシステム要件


このトピックでは、Microsoft Application Virtualization (App-v) Management Server とストリーミングサーバーのハードウェアおよびソフトウェアの最小要件について説明します。

## Application Virtualization 管理およびストリーミングサーバー


次の一覧には、App-v Management Server と App-v Streaming Server の最低限の推奨ハードウェアおよびソフトウェア要件が記載されています。

### ハードウェア要件

-   プロセッサー-Intel Pentium III、1 GHz

-   RAM: 512 MB

-   ディスク領域: 200 MB のハードディスク領域。コンテンツディレクトリは含まれません。

### ソフトウェア要件

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
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹は、App-v 4.5 SP1 および SP2 にのみ適用されます。

## データストア


次の一覧には、別のサーバーにデータストアをインストールするときに使用するコンピューターの最低限の推奨されるハードウェアとソフトウェアの要件が記載されています。 データストアは、Application Virtualization Management Server にのみ必要です。

### ハードウェア要件

-   プロセッサー-Intel Pentium III、850 MHz

-   RAM: 512 MB

-   ディスク領域: 200 MB のハードディスク空き容量

### ソフトウェア要件

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
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹は、App-v 4.5 SP1 および SP2 にのみ適用されます。

-   データベース: Microsoft SQL Server2000 SP3a または SP4、SQL Server2005 SP1、SP2、または SP3、または SQL Server2008、service pack または SP1 または SQL Server2008 R2 (32 ビットまたは64ビット)。

-   Microsoft データアクセスコンポーネント— MDAC 2.7

-   ドメインコントローラー (Active Directory ドメインサービスまたは Windows NT 4.0 ベースのプライマリドメインコントローラー (PDC) としての中央認証機関としての対応

## 管理 Web サービス


次の一覧は、アプリケーションの仮想化管理 Web サービスが別のコンピューターにインストールされている場合の、最低限の推奨されるハードウェアとソフトウェアの要件を示しています。

### ハードウェア要件

-   プロセッサー-Intel Pentium III、800 MHz

-   RAM: 256 MB

-   ディスク容量:50 MB のハードディスク空き容量

### ソフトウェア要件

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
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Enterprise Edition または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹は、App-v 4.5 SP1 および SP2 にのみ適用されます。

-   インターネットインフォメーションサービス-インターネットインフォメーションサービス (IIS) 6.0 (Microsoft ASP.NET、IIS 7 で構成されています)

-   Microsoft .NET Framework 2.0

## 管理コンソール


次の一覧には、別のコンピューターにインストールした場合に、Application Virtualization 管理コンソールで推奨される最低限のハードウェアとソフトウェアの要件が記載されています。

### ハードウェア要件

-   プロセッサー-Intel Pentium III、450 MHz

-   RAM: 256 MB

-   ディスク領域: 200 MB のハードディスク空き容量

### ソフトウェア要件

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
<td align="left"><p>プロフェッショナルエディション</p></td>
<td align="left"><p>SP2 または SP3</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>ビジネス、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p>Service pack、SP1、または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>プロフェッショナル、エンタープライズ、または究極のエディション</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>Standard Edition、Enterprise Edition、または Datacenter Edition</p></td>
<td align="left"><p>Service pack または SP2 がない</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p>SP1 または SP2</p></td>
<td align="left"><p>x86 または x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準、エンタープライズ、または Datacenter Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹は、App-v 4.5 SP1 および SP2 にのみ適用されます。

-   Microsoft 管理コンソール (MMC 3.0 以降)

-   Microsoft .NET Framework 2.0 SP2 (最小)

    **重要** 少なくとも、app-v の管理コンソールを実行しているコンピューターに app-v hotfix KB980850 またはそれ以降の App-v ホットフィックスをインストールする必要がある場合は、最小要件は .NET Framework 2.0 SP2 です。

     

## 関連トピック


[Application Virtualization Client のハードウェア要件とソフトウェア要件](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization Sequencer のハードウェア要件とソフトウェア要件](application-virtualization-sequencer-hardware-and-software-requirements.md)

[サーバー ベースの展開用にサーバーを構成する方法](how-to-configure-servers-for-server-based-deployment.md)

[サーバーおよびシステム コンポーネントをインストールする方法](how-to-install-the-servers-and-system-components.md)

[サーバーおよびシステム コンポーネントをアップグレードする方法](how-to-upgrade-the-servers-and-system-components.md)

 

 





