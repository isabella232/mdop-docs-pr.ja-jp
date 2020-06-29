---
title: MBAM 2.5 レポートを構成する方法
description: MBAM 2.5 レポートを構成する方法
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826617"
---
# MBAM 2.5 レポートを構成する方法


このトピックでは、次の機能を使用して、Microsoft BitLocker の管理と監視 (MBAM) 2.5 レポート機能を構成する方法について説明します。

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
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">MBAM 2.5 Server の前提条件構成マネージャーの統合トポロジにのみ適用されます </a> (該当する場合)。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Mbam サーバー機能の構成を計画している各サーバーに MBAM サーバーソフトウェアをインストールします。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows powershell コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
</tr>
</tbody>
</table>



**Windows PowerShell を使用してレポートを構成するには**

1.  構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。

2.  **MbamReport** Windows PowerShell コマンドレットを使用して、レポートを構成します。 この Windows PowerShell コマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamReport**」と入力します。

**ウィザードを使用してレポートを構成するには**

1. レポートを構成するサーバーで、 **Mbam サーバー構成**ウィザードを開始します。 [**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。

2. [**新しい機能の追加**] をクリックし、[**レポート**] を選択して、[**次へ**] をクリックします。 ウィザードは、レポートのすべての前提条件が満たされていることを確認します。

3. **[Next]** をクリックして続行します。

4. 次の説明を使用して、ウィザードにフィールド値を入力します。

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
   <td align="left"><p><strong>SQL Server Reporting Services インスタンス</strong></p></td>
   <td align="left"><p>レポートが構成される SQL Server Reporting Services のインスタンス。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>レポート役割のドメイングループ</strong></p></td>
   <td align="left"><p>管理および監視サーバー上のレポートにアクセスする権限がメンバーに付与されているドメインユーザーグループの名前。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>SQL Server 名</strong></p></td>
   <td align="left"><p>コンプライアンスと監査データベースが構成されているサーバーの名前。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server データベースインスタンス</strong></p></td>
   <td align="left"><p><em> </em> コンプライアンスと監査データベースが構成されている SQL Server (MSSQLSERVER など) のインスタンスの名前。</p>
   <div class="alert">
   <strong>注</strong><br/><p>レポートサーバーのポートで受信トラフィックを有効にするには、レポートコンピューターで例外を追加する必要があります (既定のポートは 80)。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>データベース名</strong></p></td>
   <td align="left"><p>コンプライアンスおよび監査データベースの名前。 既定では、データベース名は <strong> mbam コンプライアンスの状態ですが、 </strong> コンプライアンスと監査データベースを構成するときに名前を変更することはできます。</p>
   <div class="alert">
   <strong>注</strong><br/><p>以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>コンプライアンスと監査データベースのドメインアカウント</strong></p></td>
   <td align="left"><p>コンプライアンスおよび監査データベースにアクセスするためのドメインユーザーアカウントとパスワード。</p>
   <p>[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値がユーザーの場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</p>
   <p>[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値 </strong> <strong> がグループの場合 </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</p>
   <p>有効期限が切れないように、このアカウントのパスワードを設定します。 ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。</p></td>
   </tr>
   </tbody>
   </table>



5. 入力が完了したら、[**次へ**] をクリックします。

   ウィザードは、レポート機能のすべての前提条件が満たされていることを確認します。

6. **[Next]** をクリックして続行します。

7. [**概要**] ページで、追加される機能を確認します。

   **注**  
   直前に行ったエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。



8. [**追加**] をクリックして、サーバー上にレポートを追加し、[**閉じる**] をクリックします。



## 関連トピック


[サーバーのイベント ログ](server-event-logs.md)

[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

[MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)

[MBAM 2.5 サーバー機能の構成の確認](validating-the-mbam-25-server-feature-configuration.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






