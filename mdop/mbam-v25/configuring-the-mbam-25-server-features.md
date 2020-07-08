---
title: MBAM 2.5 サーバー機能の構成
description: MBAM 2.5 サーバー機能の構成
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823057"
---
# MBAM 2.5 サーバー機能の構成


[Mbam 2.5 サーバーソフトウェアをインストール](installing-the-mbam-25-server-software.md)した後、Microsoft BitLocker 管理および監視 (mbam) 2.5 サーバー機能を構成するための出発点として、この情報を使用してください。 MBAM を構成するには、次の2つの方法があります。

-   MBAM サーバー構成ウィザード

-   Windows PowerShell コマンドレット

## MBAM サーバー機能の構成を開始する前に


MBAM サーバー機能の構成を開始する前に、次の手順を確認して完了します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">ステップ</th>
<th align="left">手順を表示する場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MBAM の推奨アーキテクチャを確認します。</p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 のアーキテクチャの概要</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM のサポートされている構成を確認します。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>各サーバーに必要な前提条件を完了します。</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell を使用して MBAM Server 機能を構成するための前提条件を確認します (この方法を使用して MBAM サーバー機能を構成する場合)。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
</tr>
</tbody>
</table>

 

## MBAM サーバー機能を構成する手順


次の表の各行では、 [MBAM 2.5 の推奨される高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)に従って、個別のサーバーで構成する機能について説明します。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">インストールする機能</th>
<th align="left">手順を表示する場所</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>データベースを構成します。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">MBAM 2.5 データベースを構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>レポートを構成します。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">MBAM 2.5 レポートを構成する方法</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web アプリケーションを構成します。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">MBAM 2.5 Web アプリケーションを構成する方法</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>System Center Configuration Manager の統合を構成します (該当する場合)。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</a></p></td>
</tr>
</tbody>
</table>

 

MBAM サーバー機能の構成について詳しくは、「[サーバーイベントログ](server-event-logs.md)」をご覧ください。



## 関連トピック


MBAM 2.5 サーバー機能の構成
 

 
## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。




