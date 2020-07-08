---
title: テスト環境での MBAM 2.5 の評価
description: テスト環境での MBAM 2.5 の評価
author: dansimp
ms.assetid: 72959b7a-e55f-4797-91b3-5be23c8c2844
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d7ba8a62f5ddecf85fe56e04fc16a6bae374ba9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823154"
---
# テスト環境での MBAM 2.5 の評価


このトピックでは、単体または System Center Configuration Manager の統合トポロジで、Microsoft BitLocker の管理と監視 (MBAM) 2.5 を評価するためにテスト環境をセットアップする方法について説明します。

## スタンドアロントポロジを使用して MBAM 2.5 を評価する


スタンドアロントポロジを使用して MBAM を評価するには、次の表の情報を使用して MBAM サーバーソフトウェアをインストールし、テスト環境で MBAM サーバー機能を構成します。

**スタンドアロントポロジを使用して MBAM 2.5 を評価するには**

1. MBAM をインストールする前に、次の操作を行います。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>すべての必須ソフトウェアがインストールされていることを確認します。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>必要なハードウェア、RAM、その他の仕様を確認します。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>コマンドレットを使用して MBAM を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
   </tr>
   </tbody>
   </table>



2. MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">MBAM 2.5 データベースを構成する方法</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>レポート機能を構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">MBAM 2.5 レポートを構成する方法</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>Web アプリケーションを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">MBAM 2.5 Web アプリケーションを構成する方法</a></p></td>
   </tr>
   </tbody>
   </table>



3. クライアントコンピューターで、次の操作を行います。

   1.  クライアントコンピューターに MBAM クライアントをインストールします。

   2.  コンピューターに MBAM グループポリシーオブジェクト (Gpo) を適用します。

   3.  次のレジストリキーを設定して、MBAM クライアントで、一定の間隔ですばやく起動するように強制します。

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注**  
       これらのキーは、MBAM クライアントを毎分起動するため、テスト環境でのみ使用することをお勧めします。



   4.  **BitLocker 管理クライアントサービス**を再起動します。

## System Center 2012 Configuration Manager の統合トポロジを使用した MBAM 2.5 の評価


Configuration Manager の統合トポロジを使用して MBAM を評価するには、次の表の情報を使用して MBAM サーバーソフトウェアをインストールし、テスト環境で MBAM サーバー機能を構成します。 クライアントコンピューターに MBAM クライアントをインストールした後、MBAM クライアントでコンピューターの状態を [MBAM] にすばやく報告させる追加の手順を実行します。

**System Center 2012 Configuration Manager の統合トポロジを使用して MBAM 2.5 を評価するには**

1. MBAM をインストールする前に、必須ソフトウェアとサポートされている構成を確認してください。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>すべての必須ソフトウェアがインストールされていることを確認します。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>必要なハードウェア、RAM、その他の仕様を確認します。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>コマンドレットを使用して MBAM を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</p></td>
   <td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>.Mof ファイルを作成または編集します。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">Configuration.mof ファイルを編集する</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">Sms_def.mof ファイルを作成または編集する</a></p></td>
   </tr>
   </tbody>
   </table>



2. MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p>
   <div class="alert">
   <strong>注</strong><br/><p>Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。 DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">MBAM 2.5 データベースを構成する方法</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>レポート機能を構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">MBAM 2.5 レポートを構成する方法</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>Web アプリケーションを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">MBAM 2.5 Web アプリケーションを構成する方法</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>Configuration Manager オブジェクトをインストールするように System Center Configuration Manager を構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</a></p></td>
   </tr>
   </tbody>
   </table>



3. クライアントコンピューターで、次の操作を行います。

   1.  MBAM クライアントと Configuration Manager クライアントをクライアントコンピューターにインストールします。

   2.  MBAM グループポリシーオブジェクトをコンピューターに適用します。

   3.  次のレジストリキーを設定して、MBAM クライアントで、一定の間隔ですばやく起動するように強制します。

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注**  
       これらのキーは、MBAM クライアントを毎分起動するため、テスト環境でのみ使用することをお勧めします。



   4.  **BitLocker 管理クライアントサービス**を再起動します。

   5.  コントロールパネルで [**構成マネージャー**] を開き、[**操作**] タブをクリックします。

   6.  [**ハードウェアインベントリサイクル**] を選択し、[**今すぐ実行**] をクリックします。 この手順では、.mof ファイルにインポートした新しいクラスを使ってハードウェアインベントリを実行し、そのデータを Configuration Manager サーバーに送信します。

   7.  [**コンピューターポリシーの取得 & 評価サイクル**] を選択し、[**今すぐ実行**] をクリックして、そのクライアントコンピューターに関連するグループポリシーオブジェクトを適用します。



4. Configuration Manager コンソールで、次の操作を行います。

   1.  ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター**] を右クリックし、[**メンバーシップの更新**] をクリックし、[**はい**] をクリックして、クライアントコンピューターがそのメンバーシップを直ちに報告するように強制します。

   2.  ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター** ] をクリックして、クライアントコンピューターがコレクションに表示されることを確認します。

5. クライアントコンピューターのコントロールパネルで、もう一度**Configuration Manager**を開き、次の操作を行います。

   1.  [**操作**] タブをクリックし、[マシンポリシーの取得] を再実行して、**評価サイクル &** します。

   2.  [**構成**] タブをクリックして、BitLocker ベースラインを選択し、[**評価**] をクリックします。

6. Configuration Manager コンソールで、[エンタープライズコンプライアンスレポート] にクライアントコンピューターが表示されていることを確認します。次のようになります。

   1.  ナビゲーションウィンドウで、[**監視**] ワークスペースを選択します。

   2.  コンソールツリーで、[**概要** &gt; **レポート** &gt; **レポート** &gt; **mbam**] を展開します。

   3.  レポートを表示する言語を表すフォルダーを選択し、[結果] ウィンドウでレポートを選択します。

## System Center Configuration Manager 2007 の統合トポロジを使用して MBAM 2.5 を評価する


Configuration Manager の統合トポロジを使用して MBAM を評価するには、同じ手順に従って、実稼働環境での使用時に、テスト環境に MBAM をインストールして構成します。 クライアントコンピューターに MBAM クライアントをインストールした後は、このトピックの追加の手順を実行して、MBAM クライアントがコンピューターの状態を MBAM に簡単に報告できるようにします。

**Configuration Manager 2007 統合トポロジを使用して MBAM を評価するには**

1. MBAM をインストールする前に、次の操作を行います。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>すべての必須ソフトウェアがインストールされていることを確認します。</p></td>
   <td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</a></p>
   <p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>必要なハードウェア、RAM、その他の仕様を確認します。</p></td>
   <td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 がサポートされる構成</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>.Mof ファイルを作成または編集します。</p></td>
   <td align="left"><p><a href="edit-the-configurationmof-file-mbam-25.md" data-raw-source="[Edit the Configuration.mof File](edit-the-configurationmof-file-mbam-25.md)">Configuration.mof ファイルを編集する</a></p>
   <p><a href="create-or-edit-the-sms-defmof-file-mbam-25.md" data-raw-source="[Create or Edit the Sms_def.mof File](create-or-edit-the-sms-defmof-file-mbam-25.md)">Sms_def.mof ファイルを作成または編集する</a></p></td>
   </tr>
   </tbody>
   </table>



2. MBAM サーバーソフトウェアをインストールし、必要な機能を構成します。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">タスク</th>
   <th align="left">手順を表示する場所</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p>Mbam サーバー機能を構成する各サーバーに MBAM サーバーソフトウェアをインストールします。</p>
   <div class="alert">
   <strong>注</strong><br/><p>Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。 DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</p>
   </div>
   <div>

   </div></td>
   <td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">MBAM 2.5 サーバー ソフトウェアのインストール</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>コンプライアンスデータベースと監査データベース、および回復データベースを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">MBAM 2.5 データベースを構成する方法</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>レポート機能を構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">MBAM 2.5 レポートを構成する方法</a></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p>Web アプリケーションを構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">MBAM 2.5 Web アプリケーションを構成する方法</a></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p>Configuration Manager オブジェクトをインストールするように System Center Configuration Manager を構成します。</p></td>
   <td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">MBAM 2.5 System Center Configuration Manager 統合を構成する方法</a></p></td>
   </tr>
   </tbody>
   </table>



3. クライアントコンピューターで、次の操作を行います。

   1.  クライアントコンピューターに MBAM クライアントをインストールします。

   2.  MBAM グループポリシーオブジェクトをコンピューターに適用します。

   3.  次のレジストリキーを設定して、MBAM クライアントがより迅速に、またはより迅速にスリープ状態になるようにします。

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement
       "ClientWakeupFrequency"=dword:00000001
       "StatusReportingFrequency"=dword:00000001
       ```

       ``` syntax
       [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM]
       "NoStartupDelay"=dword:00000001
       ```

       **注**  
       これらのキーは、MBAM クライアントを1分間隔でウェイクアップするため、評価環境でのみ使用することをお勧めします。



   4.  **BitLocker 管理クライアントサービス**を再起動します。

   5.  コントロールパネルで [**構成マネージャー**] を開き、[**操作**] タブをクリックします。

   6.  [**コンピューターポリシーの取得 & 評価サイクル**] を選択し、[**今すぐ実行**] をクリックして、そのクライアントコンピューターに関連するグループポリシーオブジェクトを適用します。

   7.  [**ハードウェアインベントリサイクル**] を選択し、[**今すぐ実行**] をクリックします。 この手順では、.mof ファイルにインポートした新しいクラスを使ってハードウェアインベントリを実行し、そのデータを Configuration Manager サーバーに送信します。

4. Configuration Manager コンソールで、次の操作を行います。

   1.  ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター**] を右クリックし、[**メンバーシップの更新**] をクリックし、[**はい**] をクリックして、クライアントコンピューターがそのメンバーシップを直ちに報告するように強制します。

   2.  ナビゲーションウィンドウで、[ **Mbam サポートされているコンピューター** ] をクリックして、クライアントコンピューターがコレクションに表示されることを確認します。

5. クライアントコンピューターのコントロールパネルで、もう一度**Configuration Manager**を開き、次の操作を行います。

   1.  [**操作**] タブをクリックし、[マシンポリシーの取得] を再実行して、**評価サイクル &** します。

   2.  [**構成**] タブをクリックして、BitLocker ベースラインを選択し、[**評価**] をクリックします。

6. Configuration Manager コンソールで、次のように、[エンタープライズコンプライアンス] レポートにクライアントコンピューターが表示されることを確認します。

   1.  ナビゲーションウィンドウで、[**コンピューター管理**] &gt; **レポート** &gt; **サービス** &gt; ** &lt; サーバー名 &gt; mbam**を展開します。

   2.  **Mbam**ノードで、レポートを表示する言語を表すフォルダーを選択し、[結果] ウィンドウからレポートを選択します。


## 関連トピック


[MBAM 2.5 をお使いになる前に](getting-started-with-mbam-25.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。





