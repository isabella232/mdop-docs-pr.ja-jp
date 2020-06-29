---
title: 分散サーバーに MBAM をインストールして構成する方法
description: 分散サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825657"
---
# 分散サーバーに MBAM をインストールして構成する方法


このトピックの手順では、分散サーバー上の Microsoft BitLocker 管理および監視 (MBAM) 機能の完全なインストールについて説明します。

各サーバー機能には、いくつかの前提条件があります。 前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートさ](mbam-10-supported-configurations.md)れている構成」を参照してください。 さらに、一部の機能では、インストールプロセス中に機能を正常に展開するために特定の情報を提供する必要があります。

**注**  
セットアップログファイルを取得するには、 **msiexec.exe**パッケージと **/l &lt; location &gt; **オプションを使用して mbam をインストールする必要があります。 指定した場所にログファイルが作成されます。

追加のセットアップログファイルは、MBAM インストールを実行しているユーザーの% temp% フォルダーに作成されます。



## <a href="" id="deploy-the-mbam-server-features-"></a>MBAM Server 機能を導入する


次の手順では、一般的な MBAM 機能をインストールする方法について説明します。

**注**  
32ビットサーバーでは32ビットセットアップ、64ビットサーバーでは64ビットセットアップを使用していることを確認してください。



**MBAM サーバー機能を展開するには**

1.  MBAM インストールウィザードを起動し、[ようこそ] ページで [**インストール**] をクリックします。

2.  Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。

3.  既定では、すべての MBAM 機能がインストール対象として選択されています。 他の場所でインストールする機能をオフにします。 同じコンピューターにインストールする機能は、すべて同時にインストールする必要があります。 MBAM 機能は、次の順序でインストールする必要があります。

    -   回復とハードウェアデータベース

    -   コンプライアンスと監査データベース

    -   コンプライアンス監査とレポート

    -   管理と監視サーバー

    -   MBAM グループポリシーテンプレート

    **注**  
    インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。 すべての前提条件が満たされている場合は、インストールが続行されます。 見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。 すべての前提条件が満たされている場合は、インストールが再開されます。



4.  MBAM セットアップウィザードには、選択した機能のインストールページが表示されます。 以下のセクションでは、各機能のインストール手順について説明します。

    **注**  
    通常、各機能は個別のサーバーにインストールされます。 1台のサーバーに複数の機能をインストールする場合は、次の手順の一部を変更または削除することができます。



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。

6. 選択された MBAM 機能の情報が完了したら、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。 インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。 インストールを開始するには、[**インストール**] をクリックします。 [**キャンセル**] をクリックしてウィザードを終了します。 選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。

7. [**完了**] をクリックしてウィザードを終了します。

8. MBAM サーバー機能をインストールした後、適切な MBAM ロールにユーザーを追加します。 詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。

**インストール後の構成**

1.  MBAM セットアップが終了したら、ユーザーが MBAM 管理 web サイトの機能にアクセスできるようにするには、ユーザーロールを追加する必要があります。 管理および監視サーバーで、次のローカルグループにユーザーを追加します。

    -   **Mbam ハードウェアユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのハードウェア機能にアクセスできます。

    -   **Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのドライブの回復と、トラステッドプラットフォームモジュール (TPM) 機能の管理を行うことができます。 ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。

    -   **Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトでドライブの回復と TPM 機能の管理に高度なアクセス権を持っています。 上級のヘルプデスクユーザーの場合、ドライブの回復には [キー ID] フィールドのみが必要です。 [TPM の管理] では、[コンピュータードメイン] フィールドと [コンピューター名] フィールドのみを指定する必要があります。

2.  管理および監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスと監査レポートをホストしているサーバー上で、次のローカルグループにユーザーを追加して、MBAM 管理 web サイトでレポート機能にアクセスできるようにします。

    -   **Mbam レポートユーザー**: このローカルグループのメンバーは、mbam 管理 web サイトのレポートにアクセスできます。

    **注**  
    Mbam 管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスと監査レポートがインストールされているすべてのコンピューターで、 **Mbam レポートユーザー**のローカルグループの同一ユーザーまたはグループメンバーシップを維持する必要があります。



## MBAM サーバー機能のインストールを検証する


MBAM サーバー機能のインストールが完了したら、インストールによって MBAM の必要な機能が正しく設定されていることを確認する必要があります。 次の手順を使用して、MBAM サービスが機能していることを確認します。

**MBAM インストールを検証するには**

1. MBAM 機能が展開されている各サーバーで、[**コントロールパネル**] を開き、[**プログラム**]、[**プログラムと機能**] の順にクリックします。 **Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。

   **注**  
   MBAM インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。



2. 回復とハードウェアデータベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。

3. コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータス**データベースがインストールされていることを確認します。

4. コンプライアンスと監査レポートがインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。

   SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamreportsserver/レポートで参照でき &gt; </em> ます。 実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定したインスタンスを選択します。

   「**マルタ法令遵守レポート**」という名前のフォルダーが表示されていること、および5つのレポートと1つのデータソースが含まれていることを確認します。

   **注**  
   SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http:/* &lt; nameofmbamreportsserver &gt; */レポート \ _* &lt; srsinstancename &gt; *



5. 管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照し、[ **Web サーバー (iis)**] を選択して、[**インターネットインフォメーションサービス (iis) マネージャー**] をクリックします。 [**接続**の場所* &lt; &gt; ] で、[***サイト**] をクリックし、[ **Microsoft BitLocker の管理と監視**] をクリックします。 **MbamMBAMComplianceStatusService service**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が表示されていることを確認します。

6. 管理と監視機能がインストールされているサーバーで、管理者権限を持つ web ブラウザーを開き、MBAM web サイトの次の場所を参照して、正しく読み込まれていることを確認します。

   -   *http:// &lt; computername/ &gt; defaultdefault.aspx*とナビゲーションおよびレポートの各リンクを確認する

   -   *http:// &lt; computername &gt; /mbam管理サービス/管理サービス*

   -   *http:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc*

   -   *http:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc*

   **注**  
   通常、サービスは、ネットワーク暗号化されていない既定のポート80にインストールされます。 サービスが別のポートにインストールされている場合は、Url を変更して適切なポートを追加します。 たとえば、http://* &lt; computername &gt; : &lt; &gt; port*/default/dns または http:// <em> &lt; hostheadername &gt; / </em> default.aspx

   サービスがネットワーク暗号化と共にインストールされていた場合は、http://を https://に変更します。



~~~
Verify that each web page loads successfully.
~~~

## 関連トピック


[MBAM 1.0 サーバー インフラストラクチャの展開](deploying-the-mbam-10-server-infrastructure.md)









