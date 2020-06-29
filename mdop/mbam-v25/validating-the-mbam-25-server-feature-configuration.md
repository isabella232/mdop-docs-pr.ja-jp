---
title: MBAM 2.5 サーバー機能の構成の確認
description: MBAM 2.5 サーバー機能の構成の確認
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827084"
---
# MBAM 2.5 サーバー機能の構成の確認


Microsoft BitLocker の管理と監視 (MBAM) 2.5 サーバー機能の展開が完了したら、展開を検証してすべての機能が正常に構成されていることを確認することをお勧めします。 展開したトポロジ (スタンドアロンまたは System Center Configuration Manager の統合) と一致する手順を使用します。

## スタンドアロントポロジを使用して MBAM サーバー展開を検証する


スタンドアロントポロジを使って、MBAM サーバーの展開を検証するには、次の手順を使用します。

**スタンドアロンの MBAM サーバー展開を検証するには**

1.  Mbam 機能が展開されている各サーバーで、[**コントロールパネル**プログラム] の [ &gt; **Programs** &gt; **プログラムと機能**] をクリックします。 **Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。

    **注**  
    検証を実行するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。



2.  回復データベースが構成されているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースが構成されていることを確認します。

3.  コンプライアンスと監査データベースが構成されているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータスデータベース**が構成されていることを確認します。

4.  レポート機能が構成されているサーバーで、管理者の資格情報を使って web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。

    SQL Server Reporting Services サイトインスタンスの既定のホームの場所は次のとおりです。

    http (s)// &lt; *mbamレポート名* &gt; : &lt; *port* &gt; /レポート名

    実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定したインスタンスを選択します。

5.  **[Microsoft BitLocker 管理と監視**] という名前のレポートフォルダーに、 **MaltaDataSource**という名前のデータソースと言語フォルダーが含まれていることを確認します。 データソースには、言語を表す名前 (たとえば、en-us) のフォルダーが含まれています。 レポートは、言語フォルダーにあります。

    **注**  
    SQL Server Reporting Services (SSRS) が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http (s)// &lt; *mbamレポート servername* &gt; : &lt; *port* &gt; /レポート \ _ &lt; *ssrsinstancename*&gt;



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. [Web サイトの管理と監視] 機能が構成されているサーバーで、**サーバーマネージャー**を実行し、**役割**を参照して、[ **Web サーバー (iis)** ] &gt; **インターネットインフォメーションサービス (iis) マネージャー**を選択します。

7. [**接続**] で、[ * &lt; コンピューター &gt; 名*] を参照し **、[** &gt; **Microsoft BitLocker 管理と監視**] を選びます。 次の内容が表示されていることを確認します。

   -   **Mbam管理サービス**

   -   **MBAMComplianceStatusService**

   -   **Mbamrecoveryandハードウェアサービス**

8. 管理と監視の Web サイトとセルフサービスポータルが構成されているサーバーで、管理者の資格情報を使って web ブラウザーを開きます。

9. 次の web サイトを参照して、正常に読み込まれていることを確認します。

   -   https (s)/ &lt; *mbam管理 servername* &gt; : &lt; *port*/ &gt; helpデスク/-ナビゲーションとレポートの各リンクを確認する

   -   http (s):/ &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /selfservice/

   **注**  
   ネットワーク暗号化されていない既定のポートでサーバー機能を構成していることを前提としています。 異なるポートまたは仮想ディレクトリにサーバー機能を構成した場合は、次のようにして適切なポートを含むように Url を変更します。

   http (s)// &lt; *host name* &gt; : &lt; *port*/ &gt; helpデスク/

   http (s)// &lt; *host name* &gt; : &lt; *port* &gt; / &lt; *virtualdirectory*&gt;/

   サーバー機能がネットワーク暗号化で構成されていた場合は、http://を https://に変更します。



10. 次の web サービスを参照して、正しく読み込まれていることを確認します。 サービスが実行中であることを示すページが表示されますが、このページにはメタデータは表示されません。

    -   http (s):/ &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /mbam管理サービス/管理サービス

    -   http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMUserSupportService/UserSupportService.svc

    -   http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMComplianceStatusService/StatusReportingService.svc

    -   http (s)// &lt; *mbam管理 servername* &gt; : &lt; *port* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc

## Configuration Manager の統合トポロジを使用して MBAM サーバー展開を検証する


Configuration Manager の統合トポロジを使用して、MBAM 展開を検証するには、次の手順を使用します。 使用している Configuration Manager のバージョンと一致する検証手順を実行します。

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a>System Center 2012 構成マネージャーを使用して MBAM サーバー展開を検証する

System Center 2012 構成マネージャーで MBAM を使用している場合に、次の手順を実行して、MBAM サーバーの展開を検証します。

**Configuration Manager Integration MBAM 展開を検証するには: System Center 2012 構成マネージャー**

1.  System Center 2012 構成マネージャーが展開されているサーバーで、[**コントロールパネル**] の [**プログラムと機能**] を開き、 **Microsoft BitLocker の管理と監視**が表示されることを確認します。

    **注**  
    構成を検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。



2.  Configuration Manager コンソールで、[**アセット And コンプライアンス**ワークスペース &gt; **デバイスコレクション**] をクリックし、 **mbam サポートコンピューター**という新しいコレクションが表示されていることを確認します。

3.  Configuration Manager コンソールで、[ **Monitoring** workspace &gt; **レポート** &gt; **レポート**( &gt; **mbam**)] をクリックします。

4.  **Mbam**フォルダーに、異なる言語を表す名前のサブフォルダーが含まれていること、および各言語のサブフォルダーに次のレポートが表示されていることを確認します。

    -   BitLocker コンピューターのコンプライアンス

    -   BitLocker エンタープライズコンプライアンスダッシュボード

    -   BitLocker Enterprise コンプライアンスの詳細

    -   BitLocker Enterprise コンプライアンスの概要

5.  Configuration Manager コンソールで、[**資産とコンプライアンス**ワークスペースの &gt; **コンプライアンス設定**] の &gt; **構成基準**をクリックし、構成基準として**BitLocker 保護**が表示されていることを確認します。

6.  Configuration Manager コンソールで、[**資産とコンプライアンス**ワークスペースの &gt; **コンプライアンス設定**] &gt; **構成項目**をクリックし、次の新しい構成項目が表示されていることを確認します。

    -   BitLocker 固定データドライブの保護

    -   BitLocker オペレーティングシステムドライブの保護

### Configuration Manager 2007 を使用して MBAM サーバー展開を検証する

MBAM を Configuration Manager 2007 で使用している場合に、次の手順を使用して、MBAM サーバーの展開を検証します。

**Configuration Manager 統合 MBAM サーバー展開を検証するには (Configuration Manager 2007)**

1.  Configuration Manager 2007 が展開されているサーバーで、[**コントロールパネル**] の [**プログラムと機能**] を開き、 **Microsoft BitLocker の管理と監視**が表示されることを確認します。

    **注**  
    構成を検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。



2.  Configuration Manager コンソールで、[**サイトデータベース &lt; SiteCode &gt;  -  &lt; 名 &gt; 、 &lt; SiteName &gt; )、コンピューターの管理**] の順番にクリックし、「 **mbam サポートされているコンピューター** 」という新しいコレクションが表示されていることを確認します。

3.  Configuration Manager コンソールで、[ **reporting** &gt; **reporting Services** &gt; ** \\\\ &lt; &gt; ServerName** &gt; **レポートフォルダー** &gt; **mbam**] をクリックします。

    **Mbam**フォルダーに、異なる言語を表す名前のサブフォルダーが含まれていること、および各言語のサブフォルダーに次のレポートが表示されていることを確認します。

    -   BitLocker コンピューターのコンプライアンス

    -   BitLocker エンタープライズコンプライアンスダッシュボード

    -   BitLocker Enterprise コンプライアンスの詳細

    -   BitLocker Enterprise コンプライアンスの概要

4.  Configuration Manager コンソールで、[ **Desired configuration Management** &gt; **configuration**baseline] をクリックし、構成基準の**BitLocker 保護**が表示されていることを確認します。

5.  Configuration Manager コンソールで、[ **Desired configuration Management** &gt; **configuration items**] をクリックし、次の新しい構成アイテムが表示されていることを確認します。

    -   BitLocker 固定データドライブの保護

    -   BitLocker オペレーティングシステムドライブの保護



## 関連トピック


[MBAM 2.5 サーバー機能の構成](configuring-the-mbam-25-server-features.md)


## MBAM の提案をお寄せください。
- [ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。 
- MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。






