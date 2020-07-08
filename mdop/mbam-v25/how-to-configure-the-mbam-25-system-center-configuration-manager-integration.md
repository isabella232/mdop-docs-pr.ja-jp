---
title: MBAM 2.5 System Center Configuration Manager 統合を構成する方法
description: MBAM 2.5 System Center Configuration Manager 統合を構成する方法
author: dansimp
ms.assetid: 2b8a4c13-1dad-41e8-89ac-6889c5f7e051
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7c6fb0a0b06399baf1dc6493a40d17e76a51741f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812443"
---
# MBAM 2.5 System Center Configuration Manager 統合を構成する方法


このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) を構成して、MBAM を Configuration Manager と統合する System Center Configuration Manager 統合トポロジを使用する方法について説明します。

以下を使用して Configuration Manager の統合を構成する方法について説明します。

-   Windows PowerShell コマンドレット

-   MBAM サーバー構成ウィザード

手順は、 [MBAM 2.5 の高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)の推奨アーキテクチャに基づいています。

**構成を開始する前に、次の操作を行います。**

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
<td align="left"><p><a href="high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md" data-raw-source="[High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)">Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要</a></p></td>
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
<td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p>
<div class="alert">
<strong>注</strong><br/><p>このトポロジでは、MBAM サーバーソフトウェアをインストールするコンピューターに Configuration Manager コンソールをインストールする必要があります。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell の前提条件を確認します (Windows PowerShell コマンドレットを使用して MBAM を構成する場合にのみ該当します)。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
</tr>
</tbody>
</table>



**Windows PowerShell を使用して Configuration Manager の統合を構成するには**

1.  構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。

2.  **MbamCMIntegration** Windows PowerShell コマンドレットを使用して、レポートを構成します。 このコマンドレットに関する情報を取得するには、「 **MbamCMIntegration**」と入力します。

**ウィザードを使用して System Center Configuration Manager の統合を構成するには**

1.  System Center Configuration Manager の統合機能を構成するサーバーで、MBAM サーバー構成ウィザードを起動します。 [**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。

2.  [**新しい機能の追加**] をクリックし、[ **System Center Configuration Manager の統合**] を選択して、[**次へ**] をクリックします。

    このウィザードは、構成マネージャーの統合に関するすべての前提条件が満たされていることを確認します。

3.  前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。 それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。

4.  ウィザードでフィールドの値を入力するには、次の説明を使用します。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">フィールド</th>
    <th align="left">説明</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>SQL Server Reporting Services サーバー</strong></p></td>
    <td align="left"><p>レポートサービスポイントの役割を持つサーバーの完全修飾ドメイン名 (FQDN)。 MBAM Configuration Manager レポートが展開されるサーバーです。</p>
    <p>サーバーを指定しない場合、Configuration Manager レポートはローカルサーバーに展開されます。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><strong>SQL Server Reporting Services インスタンス</strong></p></td>
    <td align="left"><p>Configuration Manager レポートが展開される SQL Server Reporting Services (SSRS) インスタンスの名前です。</p>
    <p>インスタンスを指定しない場合、Configuration Manager レポートは既定の SSRS インスタンス名に展開されます。 サーバーで System Center 2012 構成マネージャーがインストールされている場合、入力した値は無視されます。</p></td>
    </tr>
    </tbody>
    </table>



5.  [**概要**] ページで、追加される機能を確認します。

    **注**  
    作成したエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。



6.  [**追加**] をクリックして Configuration Manager の統合機能をサーバーに追加し、[**閉じる**] をクリックします。



## 関連トピック


[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

[MBAM 2.5 サーバー機能の構成の確認](validating-the-mbam-25-server-feature-configuration.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






