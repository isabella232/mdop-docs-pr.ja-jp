---
title: 分散サーバーに MBAM をインストールして構成する方法
description: 分散サーバーに MBAM をインストールして構成する方法
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824057"
---
# 分散サーバーに MBAM をインストールして構成する方法


このトピックの手順では、分散サーバー上のスタンドアロントポロジで Microsoft BitLocker 管理と監視 (MBAM) 2.0 をインストールする方法について説明します。 推奨されるアーキテクチャとデータベースおよび機能の説明を示す図を表示するには、「 [MBAM 2.0 サーバーインフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)」を参照してください。 Configuration Manager トポロジを使用して Microsoft BitLocker の管理と監視をインストールするには、「 [Configuration manager で MBAM を展開](deploying-mbam-with-configuration-manager-mbam2.md)する」を参照してください。

各サーバー機能には、いくつかの前提条件があります。 前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)と[Mbam 2.0 でサポートさ](mbam-20-supported-configurations-mbam-2.md)れている構成」を参照してください。 さらに、一部の機能では、インストールプロセス中に機能を正常に展開するために特定の情報を提供する必要があります。 MBAM 展開を開始する前に、 [mbam 2.0 サーバー展開の計画](planning-for-mbam-20-server-deployment-mbam-2.md)も確認する必要があります。

**注**  
セットアップログファイルを取得するには、Msiexec.exe パッケージと [ **/l** location] オプションを使用して mbam をインストールする必要があり &lt; &gt; ます。 指定した場所にログファイルが作成されます。

追加のセットアップログファイルは、MBAM をインストールしているユーザーのサーバー上の% temp% フォルダーに作成されます。



## <a href="" id="deploying-mbam-server-features-"></a>MBAM サーバー機能の展開


次の手順では、一般的な MBAM 機能をインストールする方法について説明します。

**MBAM サーバーインストールウィザードを起動するには**

1.  Microsoft BitLocker の管理と監視をインストールするサーバーで**MBAMSetup.exe**を実行して、mbam インストールウィザードを起動します。

2.  [**ようこそ**] ページで、必要に応じて [**カスタマーエクスペリエンス向上プログラム**] を選択し、[**開始**] をクリックします。

3.  Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。

4.  [**トポロジの選択**] ページで、**スタンドアロン**トポロジを選択し、[**次へ**] をクリックします。

    **注**  
    Configuration Manager の統合トポロジで MBAM をインストールする場合は、「 [Configuration manager で MBAM を展開](deploying-mbam-with-configuration-manager-mbam2.md)する」を参照してください。



5.  インストールする機能を選びます。 既定では、すべての MBAM 機能がインストール対象として選択されています。 他の場所でインストールする機能をオフにします。 同じコンピューターにインストールされる機能は、同時にインストールする必要があります。 MBAM 機能は次の順序でインストールする必要があります。

    -   回復用データベース

    -   コンプライアンスと監査データベース

    -   コンプライアンスと監査レポート

    -   セルフサービスポータル

    -   管理と監視サーバー

    -   MBAM グループポリシーテンプレート

    **注**  
    インストールウィザードによってインストールの前提条件がチェックされ、不足している前提条件が表示されます。 すべての前提条件が満たされている場合は、インストールが続行されます。 見つからない前提条件が検出された場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックする必要があります。 すべての前提条件が現在満たされている場合は、インストールが再開されます。



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**回復データベースをインストールするには**

1.  [**回復データベースの構成**] ページで、管理/監視サーバー機能を実行するコンピューターの名前を指定します。 管理と監視のサーバー機能が展開されると、そのドメインアカウントを使用してデータベースに接続されます。

2.  **[Next]** をクリックして続行します。

3.  SQL Server インスタンスの名前と、回復データを格納するデータベースの名前を指定します。 また、データベースが配置される場所とログ情報が配置される場所の両方を指定する必要があります。

4.  [**次へ**] をクリックして、mbam セットアップウィザードを続行します。

**コンプライアンスと監査データベースをインストールするには**

1.  [**コンプライアンスと監査データベースの構成**] ページで、レポートのデータベースへのアクセスに使用するユーザーアカウントを指定します。

2.  管理/監視サーバーを実行しているコンピューターと、コンプライアンスおよび監査レポートを実行するコンピューターの名前を指定します。 管理と監視、コンプライアンスおよび監査レポートサーバーが展開されたら、ドメインアカウントを使用してデータベースに接続します。

    **注**  
    コンプライアンスと監査レポート機能を使わずにコンプライアンスおよび監査データベースをインストールする場合は、コンプライアンスと監査データベースコンピューターで例外を追加して、Microsoft SQL Server ポートで受信トラフィックを有効にする必要があります。 既定のポート番号は1433です。



3.  SQL Server インスタンスの名前と、コンプライアンスおよび監査データを格納するデータベースの名前を指定します。 また、データベースとログ情報を配置する場所も指定する必要があります。

4.  [**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。

**コンプライアンスと監査レポートをインストールするには**

1.  [**コンプライアンスおよび監査レポートの構成**] ページで、 &lt; &gt; コンプライアンスと監査データベースがインストールされているリモートの SQL Server インスタンス名 (例、ServerName) を指定します。

    **注**  
    管理および監視サーバーなしでコンプライアンスレポートと監査レポートをインストールする場合は、コンプライアンスと監査レポートコンピューターで例外を追加して、レポートサーバーのポートで受信トラフィックを有効にする必要があります (既定のポートは 80)。



2.  コンプライアンスおよび監査データベースの名前を指定します。 既定では、データベース名は MBAM コンプライアンスの状態ですが、コンプライアンスと監査データベースをインストールするときに名前を変更することはできます。

3.  **[Next]** をクリックして続行します。

4.  コンプライアンスと監査レポートをインストールする SQL Server Reporting Services のインスタンスを選択します。 ドメインユーザーアカウントとパスワードを入力して、コンプライアンスデータベースおよび監査データベースにアクセスします。 有効期限が切れないように、このアカウントのパスワードを設定します。 ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。

5.  [**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。

**セルフサービスポータルをインストールするには**

1.  [**セルフサービスポータルの構成**] ページで、必要に応じてセルフサービスポータルと管理サーバーと監視サーバー間の通信を暗号化できます。 通信を暗号化するためのオプションを選択した場合は、暗号化に使用する証明機関がプロビジョニングした証明書を選択するように求められます。

2.  **[Next]** をクリックして続行します。

3.  コンプライアンスと監査データベースがインストールされている SQL Server のリモートインスタンス (たとえば、 * &lt; ServerName &gt; *) を指定します。

4.  コンプライアンスおよび監査データベースの名前を指定します。 既定では、データベース名は MBAM コンプライアンスの状態です。 ただし、コンプライアンスと監査データベースをインストールするときに、名前を変更することができます。

5.  **[Next]** をクリックして続行します。

6.  回復データベースがインストールされている SQL Server のリモートインスタンス (たとえば、 * &lt; ServerName &gt; *) を指定します。

7.  回復データベースの名前を指定します。 既定では、データベース名は**Mbam 回復とハードウェア**です。 ただし、回復データベース機能をインストールするときに、名前を変更することができます。

8.  **[Next]** をクリックして続行します。

9.  [**ポート番号**]、[**ホスト名**] (省略可能)、Mbam 管理および監視サーバーの**インストールパス**を入力します。

    **注**  
    一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。 Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。



10. 必要に応じてセルフサービスポータルのサービスプリンシパル名 (SPN) を登録するには、[**このコンピューターのサービスプリンシパル名 (spn) を Active Directory との間で登録する] (Windows 認証に必要)** を選びます。 このチェックボックスをオンにすると、MBAM セットアップは既存の Spn を登録しようとしません。また、MBAM インストールの前後に SPN を手動で登録することができます。 SPN を手動で登録する方法については、「手動での[spn の登録](https://go.microsoft.com/fwlink/?LinkId=286758)」をご覧ください。

11. [**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。

12. コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。

13. 選択された MBAM 機能の情報が入力されると、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。 インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。 [**インストール**] をクリックして、インストールを開始します。 [**キャンセル**] をクリックしてウィザードを終了します。 選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。

14. [**完了**] をクリックしてウィザードを終了します。

    **注**  
    アプリをインストールした後でセルフサービスポータルを構成するには、会社名やその他の会社固有の情報が含まれるセルフサービスポータルを作成します。手順については、「[セルフサービスポータルのブランドを設定する](how-to-brand-the-self-service-portal.md)」を参照してください。



15. クライアントコンピューターが Microsoft コンテンツ配信ネットワーク (CDN) にアクセスできる場合、セルフサービスポータルで特定の JavaScript ファイルへの必要なアクセス権が付与されると、セルフサービスポータルのインストールが完了します。 クライアントコンピューターに Microsoft CDN へのアクセス許可がない場合は、次のセクションの手順を実行して、アクセシビリティの高いソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成します。

**エンドユーザーが Microsoft コンテンツ配信ネットワークにアクセスできないときにセルフサービスポータルを構成するには**

1. クライアントコンピューターが Microsoft コンテンツ配信ネットワーク (CDN) にアクセスできる場合、セルフサービスポータルで特定の JavaScript ファイルへの必要なアクセス権が付与されると、セルフサービスポータルのインストールが完了します。 クライアントコンピューターに Microsoft CDN へのアクセス許可がない場合は、このセクションの残りの手順を実行して、アクセシビリティの高いソースから JavaScript ファイルを参照するようにセルフサービスポータルを構成します。

2. Microsoft CDN から4つの JavaScript ファイルをダウンロードします。

   -   jQuery-1.7.2.min.js[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)

   -   MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)

   -   MicrosoftMvcAjax.js[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)

   -   MicrosoftMvcValidation.js <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. JavaScript ファイルをセルフサービスポータルの**Scripts**ディレクトリにコピーします。 このディレクトリは、 <em> &lt; mbam セルフサービスインストールディレクトリ &gt; \\ </em> セルフサービス Website\\Scripts. にあります。

4. **インターネットインフォメーションサービス (IIS) マネージャー**を開きます。

5. **Sites** &gt; **Microsoft BitLocker の管理と監視**を展開し、[ **selfservice**] を強調表示します。

   **注**  
   *Selfservice*は、既定の仮想ディレクトリ名です。 インストール時にこのディレクトリに別の名前を選択した場合は、次の手順の残りの「 *Selfservice* 」を、選択した名前で置き換えてください。



6. 中央のウィンドウで、[アプリケーションの**設定**] をダブルクリックします。

7. 次の一覧の各項目について、 &lt; 仮想ディレクトリを/ &gt; Selfservice/(またはインストール時に選択した名前) に置き換えることによって、新しい場所を参照するようにアプリケーションの設定を編集します。 たとえば、仮想ディレクトリのパスは、/selfservice/スクリプト/jquery-1.7.2.min.js に似ています。

   -   jQueryPath:/ &lt; virtual directory/ &gt; スクリプト/jQuery-1.7.2.min.js

   -   MicrosoftAjaxPath:/ &lt; virtual directory/ &gt; スクリプト/MicrosoftAjax.js

   -   MicrosoftMvcAjaxPath:/ &lt; virtual directory/ &gt; スクリプト/MicrosoftMvcAjax.js

   -   Microsoft Mvcvalidationpath:/ &lt; 仮想ディレクトリ/ &gt; スクリプト/MicrosoftMvcValidation.js

**管理と監視のサーバー機能をインストールするには**

1. MBAM は、Web サービスと管理サーバーおよび監視サーバー間の通信を暗号化できます。 通信を暗号化するためのオプションを選択した場合は、暗号化に使用する証明機関がプロビジョニングした証明書を選択するように求められます。

2. **[Next]** をクリックして続行します。

3. コンプライアンスと監査データベースがインストールされている SQL Server のリモートインスタンス (例: * &lt; ServerName &gt; *) を指定します。

4. コンプライアンスおよび監査データベースの名前を指定します。 既定では、データベース名は MBAM コンプライアンスの状態です。 ただし、コンプライアンスと監査データベースをインストールするときに、名前を変更することができます。

5. **[Next]** をクリックして続行します。

6. 回復データベースがインストールされている SQL Server のリモートインスタンス (例: * &lt; ServerName &gt; *) を指定します。

7. 回復データベースの名前を指定します。 既定では、データベース名は**Mbam 回復とハードウェア**です。 ただし、回復データベース機能をインストールするときに、名前を変更することができます。

8. **[Next]** をクリックして続行します。

9. SQL Server Reporting Services (SRS) サイトの "ホーム" の URL を指定します。 SQL Server Reporting Services サイトインスタンスの既定のホームの場所は次のとおりです。

   http:// <em> &lt; nameofmbamレポートサーバーの &gt; / </em> ReportServer

   **注**  
   SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http://* &lt; nameofmbamreportsserver/reportserver &gt; *_* &lt; srsinstancename &gt; *。



10. **[Next]** をクリックして続行します。

11. [**ポート番号**]、[**ホスト名**] (省略可能)、Mbam 管理および監視サーバーの**インストールパス**を入力します。

    **注**  
    一意のホストヘッダー名を指定しない限り、指定したポート番号は、管理および監視サーバーで未使用のポート番号である必要があります。 Windows ファイアウォールを使用している場合は、ポートが自動的に開かれます。



12. 必要に応じてセルフサービスポータルのサービスプリンシパル名 (SPN) を登録するには、[**このコンピューターのサービスプリンシパル名 (spn) を Active Directory との間で登録する] (Windows 認証に必要)** を選びます。 このチェックボックスをオンにすると、MBAM セットアップは既存の Spn を登録しようとしません。また、MBAM インストールの前後に SPN を手動で登録することができます。 SPN を手動で登録する方法については、「手動での[spn の登録](https://go.microsoft.com/fwlink/?LinkId=286758)」をご覧ください。

13. [**次へ**] をクリックして、Microsoft BitLocker の管理と監視のセットアップウィザードを続行します。

14. コンピューターのセキュリティを維持するために Microsoft Update を使用するかどうかを指定し、[**次へ**] をクリックします。

15. 選択された MBAM 機能の情報が入力されると、セットアップウィザードを使用して MBAM インストールを開始する準備ができました。 インストールの設定を確認または変更する必要がある場合は、[**戻る**] をクリックしてウィザードを移動します。 [**インストール**] をクリックしてインストールします。 [**キャンセル**] をクリックしてウィザードを終了します。 選択した MBAM 機能がインストールされ、インストールが完了したことが通知されます。

16. [**完了**] をクリックしてウィザードを終了します。

**インストール後の構成を実行するには**

1.  管理および監視サーバーで、ユーザーを次のローカルグループに追加して、MBAM 管理および監視 web サイトの機能にアクセスできるようにします。

    -   **Mbam ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam 管理と監視 web サイトでドライブの回復と TPM 機能の管理を行うことができます。 ドライブの回復と TPM の管理のすべてのフィールドは、ヘルプデスクのユーザーに必須のフィールドです。

    -   **Mbam Advanced ヘルプデスクユーザー**: このローカルグループのメンバーは、Mbam の管理と監視の web サイトで、ドライブの回復と TPM の管理機能への高度なアクセス権を持っています。 上級のヘルプデスクユーザーの場合、ドライブの回復には [キー ID] フィールドのみが必要です。 [ **TPM の管理**] では、[**コンピュータードメイン**] フィールドと [**コンピューター名**] フィールドのみを指定する必要があります。

2.  管理と監視のサーバーをホストしているサーバー、およびコンプライアンスと監査のデータベースをホストしているサーバー、およびコンプライアンスと監査のレポートをホストしているサーバーで、ユーザーを次のローカルグループに追加して、MBAM 管理および監視 web サイトでレポート機能にアクセスできるようにします。

    -   **Mbam レポートユーザー**: このローカルグループのメンバーは、Mbam 管理と監視 web サイトのレポートにアクセスできます。

    **注**  
    Mbam 管理と監視サーバーの機能、コンプライアンスおよび監査データベース、コンプライアンスと監査レポートがインストールされているすべてのコンピューターで、 **Mbam レポートユーザー**のローカルグループの同一ユーザーまたはグループメンバーシップを維持する必要があります。



## MBAM サーバー機能のインストールを検証する


Microsoft BitLocker の管理および監視サーバー機能のインストールが完了したら、インストールによって MBAM の必要なすべての機能が正しく設定されていることを確認することをお勧めします。 次の手順を使用して、Microsoft BitLocker の管理と監視サービスが機能していることを確認します。

**MBAM サーバーのインストールを検証するには**

1. MBAM 機能が展開されている各サーバーで、[**コントロールパネル**] を開き、[**プログラム**]、[**プログラムと機能**] の順に選択します。 **Microsoft BitLocker の管理と監視**が [**プログラムと機能**] の一覧に表示されることを確認します。

   **注**  
   MBAM インストールを検証するには、各サーバーのローカルコンピューターの管理者資格情報を持つドメインアカウントを使用する必要があります。



2. 回復データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam 回復とハードウェア**データベースがインストールされていることを確認します。

3. コンプライアンスと監査データベースがインストールされているサーバーで、SQL Server Management Studio を開き、 **Mbam コンプライアンスステータスデータベース**がインストールされていることを確認します。

4. コンプライアンスと監査レポートがインストールされているサーバーで、管理者の資格情報で web ブラウザーを開き、SQL Server Reporting Services サイトの [ホーム] を参照します。

   SQL Server Reporting Services サイトインスタンスの既定のホームの場所は、http:// <em> &lt; nameofmbamserver/レポートにあり &gt; </em> ます。 実際の URL を確認するには、Reporting Services 構成マネージャーツールを使用して、セットアップ時に指定されたインスタンスを選択します。

   **Microsoft BitLocker の管理と監視**という名前のレポートフォルダーに**MaltaDataSource**というデータソースが含まれていることを確認します。これには、 **en-us**フォルダーに4つのレポートが含まれていることを確認します。

   **注**  
   SQL Server Reporting Services が名前付きインスタンスとして構成されている場合、URL は次のようになります。 http:/* &lt; nameofmbamreportsserver &gt; */レポート \ _* &lt; srsinstancename &gt; *



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. 管理と監視機能がインストールされているサーバーで、**サーバーマネージャー**を実行し、[**ロール**] を参照します。 [ **Web サーバー (iis)**] を選択し、[**インターネットインフォメーションサービス (iis) マネージャー**] をクリックします。

6. [**接続**] で、[ * &lt; computername &gt; *] に移動し、[**サイト**] を選択して、[ **Microsoft BitLocker 管理と監視**] を選択します。 **MbamMBAMComplianceStatusService service**、 **MBAMComplianceStatusService**、 **mbamrecoveryandなサービス**が表示されていることを確認します。

7. 管理と監視機能とセルフサービスポータルがインストールされているサーバーで、管理者の資格情報を使用して web ブラウザーを開き、次の場所を参照して正常に読み込まれることを確認します。

   **注**  
   ".Svc" で終わる Url は、web サイトを表示しません。 Success は、"このサービスのメタデータの公開が現在無効になっています" またはコードの情報によって示されます。 他のエラーメッセージが表示された場合、またはページが見つからない場合は、ページが正常に読み込まれません。



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. 各 web ページが正常に読み込まれることを確認します。

## 関連トピック


[MBAM 2.0 サーバー インフラストラクチャの展開](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









