---
title: MBAM 2.5 サーバーの展開計画
description: MBAM 2.5 サーバーの展開計画
author: dansimp
ms.assetid: 88774c89-31c8-4eb8-a845-a00bbec8c870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d2ecb510fab821118ce210577f9ffb83c39be050
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826214"
---
# MBAM 2.5 サーバーの展開計画


このトピックでは、MBAM スタンドアロンおよび Configuration Manager のトポロジ用に展開する機能の一覧を示し、展開する必要がある順序を示します。 各トポロジに推奨される構成があります。 ただし、拡張性の要件に応じて、MBAM server データベースと機能をさまざまな構成と複数のサーバー間で構成することができます。

## 両方のトポロジの計画に関する重要な考慮事項


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">考慮事項</th>
<th align="left">詳細または目的</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>展開を開始する前に、次の内容を確認します。</p>
<ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></li>
</ul></td>
<td align="left"><p>MBAM の各機能には、MBAM インストールを開始する前に満たす必要がある特定の前提条件があります。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MBAM の BitLocker 回復キーは、1回使用した後に有効期限が切れます。</p></td>
<td align="left"><p>1つの用途としては、管理と監視の Web サイト (ヘルプデスクとも呼ばれます)、セルフサービスポータル、または <strong> Windows PowerShell コマンドレットを使用して回復キーを取得したことを意味し </strong> ます。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>各機能を構成するコンピューターの名前を追跡します。 この情報は、構成プロセス全体で使用します。</p></td>
<td align="left"><p><a href="mbam-25-deployment-checklist.md" data-raw-source="[MBAM 2.5 Deployment Checklist](mbam-25-deployment-checklist.md)">この目的には、mbam 2.5 展開チェックリストを使用することができ </a> ます。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[MDOP MBAM (BitLocker 管理)] ノードのグループポリシー設定のみを構成します。 BitLocker ドライブ暗号化ノードのグループポリシー設定は変更しないでください。</p></td>
<td align="left"><p>BitLocker ドライブ暗号化ノードでグループポリシーの設定を変更すると、MBAM が機能しなくなります。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="planning-for-mbam-server-deployment---stand-alone-topology"></a>MBAM サーバー展開の計画–スタンドアロントポロジ


スタンドアロンのトポロジでは、3 ~ 4 台のサーバーの構成を使うことができますが、運用環境には2サーバー構成をお勧めします。

MBAM スタンドアロントポロジのサーバーインフラストラクチャには、次の機能が含まれています。これらの機能は、記載されている順序で構成する必要があります。

1.  データベース (コンプライアンスおよび監査データベースと復元データベース)

2.  レポート

3.  Web アプリケーション (および対応する web サービス)

    -   管理と監視の Web サイト

    -   セルフサービスポータル

これらの機能について詳しくは、「 [MBAM 2.5 の高レベルアーキテクチャとスタンドアロントポロジ](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)」をご覧ください。

## <a href="" id="planning-for-mbam-server-deployment---configuration-manager-topology"></a>MBAM サーバー展開の計画– Configuration Manager トポロジ


構成マネージャーの統合トポロジについては、運用環境には3サーバー構成をお勧めしますが、その他のサーバーの構成を使用することもできます。

MBAM Configuration Manager トポロジのサーバーインフラストラクチャには、次の機能が含まれています。これらの機能は、記載されている順序で構成または実行する必要があります。

1.  データベース (コンプライアンスおよび監査データベースと復元データベース)

2.  レポート

3.  Web アプリケーション (および対応する web サービス)

    -   管理と監視の Web サイト

    -   セルフサービスポータル

4.  System Center Configuration Manager の統合

これらの機能について詳しくは、「 [MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」をご覧ください。



## 関連トピック


[MBAM 2.5 の展開計画](planning-to-deploy-mbam-25.md)

[MBAM 2.5 サーバー インフラストラクチャの展開](deploying-the-mbam-25-server-infrastructure.md)

 

## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





