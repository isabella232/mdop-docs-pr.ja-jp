---
title: MBAM 2.5 データベースを構成する方法
description: MBAM 2.5 データベースを構成する方法
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826624"
---
# MBAM 2.5 データベースを構成する方法


このトピックでは、次の機能を使用して、Microsoft BitLocker 管理および監視 (MBAM) 2.5 コンプライアンスと監査データベースおよび回復データベースを構成する方法について説明します。

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
<td align="left"><p>Mbam サーバー機能の構成を計画している各サーバーに MBAM サーバーソフトウェアをインストールします。</p>
<div class="alert">
<strong>注</strong><br/><p>Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。 DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows powershell コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
</tr>
</tbody>
</table>



**Windows PowerShell を使用してデータベースを構成するには**

1.  構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。

2.  **Mbamamdatabase** Windows PowerShell コマンドレットを使用して、データベースを構成します。 この Windows PowerShell コマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamDatabase**」と入力します。

**ウィザードを使用してコンプライアンスデータベースおよび監査データベースを構成するには**

1. データベースを構成するサーバーで、 **Mbam サーバー構成**ウィザードを起動します。 [**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。

2. [**新しい機能の追加**] をクリックし、[**コンプライアンスと監査データベース**および**データベース復元**] を選択して、[**次へ**] をクリックします。 ウィザードは、データベースのすべての前提条件が満たされていることを確認します。

3. 前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。 それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。

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
   <td align="left"><p><strong>SQL Server 名</strong></p></td>
   <td align="left"><p>コンプライアンスと監査データベースを構成しているサーバーの名前。</p>
   <div class="alert">
   <strong>注</strong><br/><p>Microsoft SQL Server ポートで受信トラフィックを有効にするには、コンプライアンスおよび監査データベースコンピューターで例外を追加する必要があります。 既定のポート番号は1433です。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server データベースインスタンス</strong></p></td>
   <td align="left"><p>コンプライアンスと監査データが保存されるデータベースインスタンスの名前です。 データベース情報を配置する場所も指定する必要があります。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>データベース名</strong></p></td>
   <td align="left"><p>コンプライアンスデータを格納するデータベースの名前。</p>
   <div class="alert">
   <strong>注</strong><br/><p>以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>読み取り/書き込みアクセスドメインユーザーまたはグループ</strong></p></td>
   <td align="left"><p>このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。このデータベースのデータとレポートにアクセスできるように、web アプリケーションを有効にします。</p>
   <p>このフィールドにユーザーを入力する場合は、[ <strong> </strong> <strong> web アプリケーションの構成] ページの [web サービスアプリケーションプールドメインアカウント] フィールドの値と同じ値である必要があり </strong> ます。</p>
   <p>このフィールドにグループを入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>読み取り専用アクセスドメインのユーザーまたはグループ</strong></p></td>
   <td align="left"><p>このデータベースに読み取り専用のアクセス許可が与えられているユーザーまたはグループの名前。レポートがこのデータベースのコンプライアンスデータにアクセスできるようにします。</p>
   <p>このフィールドにユーザーを入力する場合は、[ <strong> </strong> レポートの構成] ページの [コンプライアンスおよび監査データベースドメインアカウント] フィールドで指定したユーザーと同じユーザーである必要があり <strong> </strong> ます。</p>
   <p>このフィールドにグループを入力した場合、[ <strong> レポートの構成] ページの [コンプライアンスと監査データベースのドメインアカウント] フィールドで指定した値は、 </strong> <strong> </strong> このフィールドで指定したグループのメンバーである必要があります。</p></td>
   </tr>
   </tbody>
   </table>



5. 次のセクションに進み、回復用データベースを構成します。

**ウィザードを使用して回復データベースを構成するには**

1. 次の説明を使用して、ウィザードにフィールド値を入力します。

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
   <td align="left"><p><strong>SQL Server 名</strong></p></td>
   <td align="left"><p>回復用データベースを構成するサーバーの名前。</p>
   <div class="alert">
   <strong>注</strong><br/><p>Microsoft SQL Server ポートで受信トラフィックを有効にするには、回復データベースコンピューターで例外を追加する必要があります。 既定のポート番号は1433です。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>SQL Server データベースインスタンス</strong></p></td>
   <td align="left"><p>回復データが保存されるデータベースインスタンスの名前。 データベース情報を配置する場所も指定する必要があります。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong>データベース名</strong></p></td>
   <td align="left"><p>回復データを格納するデータベースの名前。</p>
   <div class="alert">
   <strong>注</strong><br/><p>以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong>読み取り/書き込みアクセスドメインユーザーまたはグループ</strong></p></td>
   <td align="left"><p>このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。このデータベースのデータとレポートにアクセスできるように、web アプリケーションを有効にします。</p>
   <p>このフィールドにユーザーを入力する場合は、[ <strong> </strong> <strong> web アプリケーションの構成] ページの [web サービスアプリケーションプールドメインアカウント] フィールドの値と同じ値である必要があり </strong> ます。</p>
   <p>このフィールドにグループを入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</p></td>
   </tr>
   </tbody>
   </table>



2. 入力が完了したら、[**次へ**] をクリックします。

   ウィザードは、データベースのすべての前提条件が満たされていることを確認します。

3. 前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。 それ以外の場合は、不足している前提条件を解決して、[**次へ**] をもう一度クリックします。

4. [**概要**] ページで、追加される機能を確認します。

   **注**  
   直前に行ったエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。



5. [**追加**] をクリックして、サーバー上に mbam データベースを追加し、[**閉じる**] をクリックします。



## 関連トピック


[サーバーのイベント ログ](server-event-logs.md)

[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)

[MBAM 2.5 レポートを構成する方法](how-to-configure-the-mbam-25-reports.md)

[MBAM 2.5 Web アプリケーションを構成する方法](how-to-configure-the-mbam-25-web-applications.md)

[MBAM 2.5 サーバー機能の構成の確認](validating-the-mbam-25-server-feature-configuration.md)



## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。 





