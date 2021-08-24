---
title: SQL スクリプトを使用した APP-V 4.5 データベースの作成
description: SQL スクリプトを使用した APP-V 4.5 データベースの作成
author: dansimp
ms.assetid: 6cd0b180-163e-463f-a658-939ab9a7cfa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c119f1d43a70cce04dd6151697318f7cf6a8d1f2
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910592"
---
# <a name="creating-app-v-45-databases-using-sql-scripting"></a>SQL スクリプトを使用した APP-V 4.5 データベースの作成


**Whoソリューションの目的は何ですか?** アプリケーション仮想化 (App-V) 4.5 データベースを管理する情報技術の専門家。

**このガイドは、どのように役立ちますか?** このソリューションは、インストールする管理者が SQL Server に対する "sysadmin" 権限を持っていない場合に Microsoft Application Virtualization Server をインストールする手順について説明し、文書化しています。

## <a name="overview"></a>概要


Microsoft Application Virtualization 4.5 (App-V) をインストールする場合の課題の 1 つは、インストール プログラムが、サーバー機能をインストールするユーザーがローカル コンピューター管理者であるだけでなく、データ ストアをホストする SQL サーバーに対する SQL 管理者特権を持つものと見なしている点です。 この要件は、データベースと適切な役割とアクセス許可がインストールの一部として作成されるという事実に基づいて行います。 ただし、ほとんどの企業では、SQLサーバーは、App-V をインストールするインフラストラクチャ チームとは別に管理されます。 これらのセキュリティ要件を満たすと、インフラストラクチャ管理者SQL App-V をインストールする適切な権限を与えるのが困難になります。同様に、SQL管理者は、インフラストラクチャ チームに製品をインストールするために必要な特権を持つ必要はありません。

現時点では、App-V のインストールを試みる管理者には、"sysadmin" SQL必要があります。 以前のバージョンの製品では、SQL 管理者が一時的な "sysadmin" アカウントを作成するか、インストール中に存在して資格情報に "sysadmin" 権限を与えるセットアップが許可されています。 このリリースでは、すべての管理者がインフラストラクチャの実装時に使用するためのスクリプトがリリースされた製品に用意されています。

このホワイトペーパーでは、インストールを SQL データベースの作成と App-V サーバー機能のインストールという 2 つのタスクに分けてインストールする必要があるシナリオについて説明します。 管理者SQLは、SQL スクリプトを確認し、他のデータベースとの競合を解決したり、他のツールとの統合をサポートしたりするために変更を加える可能性があります。 スクリプトの結果、SQL 管理者がデータベースを準備して、インフラストラクチャ管理者に SQL サーバーに対する高度な権限を付与する必要がなSQLです。 これは、セキュリティ ポリシーで禁止される環境で重要です。

### <a name="sql-database-creation-process"></a>SQL Database作成プロセス

SQLスクリプトを使用すると、SQL 管理者は必要なデータベースを作成し、App-V 管理者が環境を正常にインストールおよび管理するための特権を設定できます。 これらのタスクを完了するための手順については、このドキュメントの後半で説明します。

このプロセスでは、データベースの作成および構成アクションと実際の App-V インストールが分離されます。

**管理者に提供SQL情報**

-   App-V ADになるグループの名前

-   App-V 管理サーバーがインストールされるサーバーの名前

**インフラストラクチャ管理者に返される情報**

-   データベース サーバーまたはインスタンスの名前と App-V データベースの名前

データベースの準備が完了すると、App-V 管理者は、管理者特権を使用せずに App-V SQL実行できます。

### <a name="using-the-sql-setup-scripts"></a>セットアップ スクリプトSQL使用する

**要件**

選択した抽出場所のルートにある support\\createdb フォルダーにあるスクリプトを使用するための要件の一覧を次に示します。

-   スクリプトは、実行するコンピューター上の書き込み可能な場所にコピーする必要があります (コピー後に、必ずこれらのスクリプトから読み取り専用属性を削除してください)、SQL クライアント ツールをそのコンピューターに読み込む必要があります (osql は、ローカル コンピューターでサンプル バッチ ファイルを実行する場合にのみ必要です)。

-   このSQL Server認証をサポートWindows必要があります。

-   エージェント サービスがSQL ServerインスタンスSQL確認します。

-   スクリプトが実行されるコンピューター上SQL管理者 (sysadmin) であるドメイン アカウントでログオンします。

スクリプトは、ログオンしているユーザーのドメイン資格情報の下で実行されます。

**スクリプトを使用したデータベースSQL作成**

**管理者が実行するSQL:**

1.  support\\createdb フォルダーに含まれるスクリプトを、選択した抽出場所のルートから、スクリプトが実行されるコンピューターにコピーします。 スクリプトを適切に実行するには、次のファイルが必要であり、以下に示す順序で呼び出す必要があります。

    -   database.sql

    -   roles.sql

    -   table\_CODES.sql

    -   functions\_before\_tables.sql

    -   tables.sql

    -   functions.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   alerts\_jobs.sql

    -   dbversion.sql

2.  必要に応じて、ファイルを確認して変更 `database.sql` します。 既定の設定では、データベースに "APPVIRTDB" という名前が付きます。

    -   必要に応じて、インスタンスを `APPVIRTDB` 使用 `database name` するインスタンスに置き換える必要があります。

    -   スクリプト内 `FILENAME` のプロパティを、データベースが作成されるSQL Serverパスを使用して変更します。

3.  必要に応じて、database.sql ファイルで使用されたファイル `database name [APPVIRTDB]` `roles.sql` 内を確認して変更します。

****

### <a name="example-of-how-to-automate-the-process-using-batch-files"></a>バッチ ファイルを使用してプロセスを自動化する方法の例

使用する場合、提供されている 2 つのサンプル バッチ ファイルは、SQLスクリプトを実行します。

1.  **Create\_schema.bat (1)**

    -   database.sql

    -   roles.sql

2.  **Create\_tables.bat (2)**

    -   table\_CODES.sql

    -   functions\_before\_tables.sql

    -   tables.sql

    -   functions.sql

    -   views.sql

    -   procedures.sql

    -   triggers.sql

    -   data\_codes.sql

    -   data\_messages.sql

    -   data\_defaults.sql

    -   alerts\_jobs.sql

    -   dbversion.sql

**備考**  
スクリプトを変更する場合は慎重に検討する必要があります。適切な知識を持つユーザーだけが行う必要があります。 また、次のサンプル ファイルのみを変更する必要**があります**。create\_schema.bat、create\_tables.bat、database.sql、および**roles.sql**です。 ** ** **** データベースが誤って作成され、App-V サービスのインストールが失敗する可能性があります。他のすべてのファイルを変更する必要があります。



2 つのサンプル バッチ ファイルは、残りのスクリプトがコンピューターにコピーされた同SQLディレクトリに配置する必要があります。

1.  サンプル ファイルを実行 **create\_schema.bat** データベースを作成します。 このスクリプトの完了には数秒かかるので、中断する必要があります。

    -   コピー先のディレクトリschema.batファイルの作成を実行します。 構文は次のとおりです `SQLSERVERNAME` 。"Create\_schema.bat"

        ![AppV46SQLcreatebat。](images/appv46sqlcreatebat.bmp)

    -   新しい "APPVIRTDB" データベースの作成中にこのスクリプトが失敗した場合は、示されているログを確認して問題を修正します。 後続の試行が正常に動作するには、スクリプトの部分的な実行で作成されたデータベースを削除する必要があります。

2.  ファイルを `create_tables.bat` 実行して、データベースにテーブルを作成します。 このスクリプトの完了には数秒かかるので、中断する必要があります。

    -   コピーされたcreate\_tables.batファイルを実行します。 構文は次のとおりです `SQLSERVERNAME DBNAME` 。"create\_tables.bat"

        ![app-v 4.6 sql create\-table.bat。](images/appv46sqlcreate-tablebat.gif)

        テーブルの作成中にスクリプトが失敗した場合は、示されているログを確認して問題を修正します。 以降のすべての試行でデータベース を削除し、create\_schema.batファイルを実行する前に、create\_tables.bat実行する必要があります。

### <a name="setting-permissions-on-the-app-v-database"></a>App-V データベースに対するアクセス許可の設定

次のアカウントは、app-V 環境のインストール、展開、および継続的な管理のために、新しいデータベースに対する特定のアクセス許可と役割を持つ SQL サーバー上に作成する必要があります。

-   SQL Server の App-V 管理者グループと、"domain\\App-V Admins" ("domain" と "App-V Admins" が独自の環境を反映するように変更される) の APP-V 管理者グループのログインを作成し、SFTAdmin および SFTEveryone データベースの役割に追加します。

    ![app-v 4.6 sql スクリプト セットのアクセス許可と役割。](images/appv46sqlscriptsetpermsroles.gif)

-   このグループに"VIEW ANY DEFINITION" アクセス許可をグローバル レベルで付与します (これにより、Microsoft Application Virtualization Management Server セットアップ プロセスで、管理サーバーログインが既に存在することを確認できます)。 MS-SQL 2005 および master.db に含まれるメタデータに対する上記のアクセス制限が追加されました。 前の手順で作成したユーザーは、既定では、サーバーインストールに必要な権限を持たしません。 以前に作成したログインのプロパティである Login Properties- &gt; Securables を開きます。 次のスクリーンショットに示すように、データベース インスタンスを追加し、"定義を表示する" の "GRANT" を有効にしてください。

    ![app-v 4.6 sql script grant perm for view any def.](images/appv46sqlscriptviewanydef.gif)

-   前の手順で作成したログインの ROLE\_ASSIGNMENTS テーブルに役割を追加し、App-V 管理者がアプリケーション仮想化管理コンソールにアクセスし、role = "ADMIN" と group\_ref = "domain\\App-V Admins" ("domain" と "App-V Admins" が自分の環境を反映するように変更されます)。

    ![app-v 4.6 sql スクリプトの役割の割り当て。](images/appv46sqlscriptroleassign.gif)

-   管理サーバーのSQL Server App-V データベースのログインを作成します。 このアカウントは、データ ストアに接続するために Microsoft Application Virtualization Management Server によって使用され、ストリーミングされたアプリケーションのクライアント要求にサービスを提供する責任があります。 サーバーと管理サーバーのインストール先に応SQL Server 2 つのオプションがあります。

    1.  管理サーバーと SQL Server が同じコンピューターにインストールされる場合は、NT AUTHORITY\\NETWORK SERVICE のログインを追加し、SFTUser および SFTEveryone データベースの役割に追加します。

    2.  管理サーバーと SQL Server を別のコンピューターにインストールする場合は、"domain\\App-V Server Name$" ("App-V Server 名" は App-V 管理サーバーがインストールされるサーバーの名前) のログインを追加し、SFTUser および SFTEveryone データベースの役割に追加します。

-   [クエリ ウィンドウ] ウィンドウを開SQL、次のコマンドを実行SQL。

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    APPVIRTDB は、前の手順で SQL Server で作成された App-V データベースの名前であり、App-v サーバーのインストールを行うユーザーは "domain\\App-V Admins" のメンバーである必要があります ("domain" と "App-V Admins" は、独自の環境を反映するように変更されます)。

### <a name="tasks-to-be-performed-by-the-infrastructure-administrators"></a>インフラストラクチャ管理者が実行するタスク

1.  "App-V Admins" グループの管理者は、App-V をインストールする必要があります。

    前の手順で作成SQLデータベースを選択するには、SQL Server管理者からの情報を使用します。

2.  "App-V Admins" グループの管理者は、Application Virtualization Management Console にログインし、管理コンソールから次のオブジェクトを削除します。

    **Warning**  
    従来のセットアップでは、既存のデータベースに対してインストールを実行した場合に、データベースに設定されていない特定のレコードが設定されます。 次のオブジェクトを削除します。

    -   [サーバー グループ] の [既定のサーバー グループ] で、[アプリケーション仮想化管理サーバー] を削除します。

    -   [サーバー グループ] で、[既定のサーバー グループ] を削除します。

    -   [プロバイダー ポリシー] で、[既定のプロバイダー] を削除します。



3.  App-V admins グループの管理者は、次の情報を作成する必要があります。

    -   [プロバイダー ポリシー] で、新しいプロバイダー ポリシーを作成します。

    -   "既定のサーバー グループ" を作成する

        **備考**  
        使用しない場合でも、"Default Server" グループを作成する必要があります。 サーバー インストーラーは、サーバーを追加しようとするときにのみ"既定のサーバー グループ" を参照します。  "既定のサーバー グループ" がない場合、インストールは失敗します。 既定以外のサーバー グループを使用する場合は、それ以降の App-V 管理サーバーをインフラストラクチャに追加する場合は、「既定のサーバー グループ」を保持する必要があります。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## <a name="conclusion"></a>まとめ


結論として、このドキュメントの情報を使用すると、管理者は SQL 管理者と一緒に、組織内のセキュリティ部門と管理部門に対して機能する展開パスを開発できます。 このドキュメントを読み、文書化されたタスクをテストした後、管理者は、この種類の環境で App-V インフラストラクチャを実装する準備ができている必要があります。









