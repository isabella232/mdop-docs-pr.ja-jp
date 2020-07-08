---
title: Configuration Manager 統合機能の前提条件
description: Configuration Manager 統合機能の前提条件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825014"
---
# Configuration Manager 統合機能の前提条件


System Center Configuration Manager の統合トポロジで MBAM を展開する場合は、「 [mbam 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」で説明されているように、3サーバーアーキテクチャをお勧めします。 このアーキテクチャでは、50万クライアントコンピューターをサポートできます。

**重要**  
Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。



## Configuration Manager の統合機能の一般的な前提条件


Configuration Manager を使用して MBAM をインストールする場合、スタンドアロントポロジの前提条件に加えて、次の追加の前提条件が必要になります。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">受講</th>
<th align="left">追加情報</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サーバーは、Configuration Manager システムのプライマリサイトです。</p></td>
<td align="left"><p>なし</p></td>
</tr>
<tr class="even">
<td align="left"><p>ハードウェアインベントリクライアントエージェントは、Configuration Manager サーバー上にあります。</p></td>
<td align="left"><p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 構成マネージャーでハードウェアインベントリを構成する方法」を参照してください </a> 。</p>
<p>Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> サイトのハードウェアインベントリを構成する方法」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用している Configuration Manager のバージョンに応じて、次のいずれかが有効になります。</p>
<ul>
<li><p>コンプライアンス設定-(System Center 2012 構成マネージャー)</p></li>
<li><p>必要な構成管理 (DCM) クライアントエージェント– (構成マネージャー 2007)</p></li>
</ul></td>
<td align="left"><p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 構成マネージャーでコンプライアンス設定を構成する」を参照してください </a> 。</p>
<p>Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> Desired Configuration Management Client Agent プロパティ」をご覧ください </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Reporting services ポイントは、構成マネージャーで定義されます。 SQL Server Reporting Services (SSRS) の場合は必須です。</p></td>
<td align="left"><p>System Center 2012 構成マネージャーについては、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> 構成マネージャーでレポートを作成するための前提条件」を参照してください </a> 。</p>
<p>Configuration Manager 2007 については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> SQL Reporting services 用のレポートサービスポイントを作成する方法」を参照してください </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 2007 には Microsoft .NET Framework 2.0 が必要です</p></td>
<td align="left"><p>Configuration Manager 2007 の必要な構成管理 (DCM) クライアントエージェントは、コンプライアンスを報告するために .NET Framework 2.0 を必要とします。</p>
<div class="alert">
<strong>注</strong><br/><p>.NET Framework 3.5 をインストールすると、.NET Framework 2.0 が自動的にインストールされます。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## Configuration Manager で MBAM をインストールするのに必要な権限


Configuration Manager を使用して MBAM をインストールするには、次の表に示されている最低限の権限を持つセキュリティロールを持つ、構成マネージャーの管理者ユーザーがいる必要があります。 また、この表には、MBAM サーバーをインストールするために、基本的なコンピューターの管理者権限以外に必要な権限が表示されています。

**次の表のアクセス許可は、両方の Configuration Manager のバージョンに適用されます。**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">MBAM サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server インスタンスのログインサーバーの役割:-dbcreator-processadmin</p></td>
<td align="left"><p>- 回復データベース-監査データベース</p></td>
</tr>
<tr class="even">
<td align="left"><p>SSRS インスタンスの権限:-フォルダーの作成-レポートの発行</p></td>
<td align="left"><p>- System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



**System Center 2012 Configuration Manager**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">Configuration Manager サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サイトの権限:-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager コレクションの権限:-作成-削除-読み取り-修正-構成アイテムの展開</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 構成項目の権限:-作成-削除-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



**Configuration Manager 2007**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">アクセス許可</th>
<th align="left">Configuration Manager サーバー機能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager サイトの権限:-読み取り</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager コレクションの権限:-作成-削除-読み取り専用リソース</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 構成項目の権限:-作成-削除-読み取り-配布</p></td>
<td align="left"><p>System Center Configuration Manager の統合</p></td>
</tr>
</tbody>
</table>



## .Mof ファイルに必要な変更


MBAM Configuration manager のレポートを通じて、クライアントコンピューターが BitLocker のコンプライアンスの詳細を報告できるようにするためには、System Center 2012 構成マネージャーおよび Microsoft System Center Configuration Manager 2007 用の構成の .mof ファイルと Sms \ _def ファイルを編集する必要があります。 手順については、「Mbam 2.5 Server の前提条件」を参照してください。これ[は、Configuration Manager の統合トポロジにのみ適用](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)されます。



## 関連トピック


[スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





