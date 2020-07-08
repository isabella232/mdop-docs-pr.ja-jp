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
ms.openlocfilehash: d9ab2c102a43701bfdeaac49359b4ca3c4a063fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825977"
---
# SQL スクリプトを使用した APP-V 4.5 データベースの作成


**このソリューションの目的** Application Virtualization (App-v) 4.5 データベースを管理する it 技術者。

**このガイドはどのように役立つのでしょうか。** この解決策では、管理者のインストールで SQL Server に "sysadmin" 権限が付与されていない場合に、Microsoft Application Virtualization Server をインストールする手順について説明します。

## 概要


Microsoft Application Virtualization 4.5 (App-v) をインストールする際の問題の1つとして、インストールプログラムでは、サーバー機能をインストールするユーザーはローカルコンピューターの管理者であると同時に、データストアをホストする SQL server の SQL 管理者権限を持つ必要があると見なされます。 この要件は、データベースがインストールの一部として作成されたものであり、適切な役割とアクセス許可が作成されていることに基づいています。 ただし、ほとんどの企業では、SQL server は、App-v をインストールするインフラストラクチャチームとは別に管理されます。 これらのセキュリティ要件により、SQL 管理者は、App-v の適切な権限をインストールすることが困難になります。同様に、SQL 管理者には、インフラストラクチャチームの製品をインストールするために必要な権限がありません。

現時点では、App-v をインストールしようとしている管理者は、SQL "sysadmin" 権限を持っている必要があります。 以前のバージョンの製品では、SQL 管理者は、一時的な "sysadmin" アカウントを作成するか、インストール中に "sysadmin" 権限を持つ資格情報を提供するように設定することができます。 このリリースでは、すべての管理者がインフラストラクチャを実装するときに使用するために、リリースされた製品でスクリプトを提供しています。

このホワイトペーパーでは、インストールを2つの別々のタスク (SQL データベースの作成、アプリ-V server 機能のインストール) に分ける必要があるシナリオについて説明します。 SQL 管理者は、SQL スクリプトを確認し、他のデータベースとの競合を解決したり、他のツールとの統合をサポートしたりするように変更を加えることができます。 スクリプトの結果として、sql 管理者は、sql server の高度な権限を付与する必要がないように、データベースの準備を行うことができます。 これは、セキュリティポリシーによって禁止されている環境で重要です。

### SQL データベースの作成プロセス

SQL スクリプトを使用すると、SQL 管理者が必要なデータベースを作成できるようにしたり、アプリの管理者が環境を正常にインストールして管理するための権限を設定したりすることができます。 これらのタスクを完了する手順は、このドキュメントの後半に記載されています。

このプロセスでは、データベースの作成と構成のアクションが、実際の App-v インストールから分離されます。

**SQL 管理者に提供される情報**

-   App-v 管理者の権限を持つ広告グループの名前

-   App-v Management Server をインストールするサーバーの名前

**インフラストラクチャ管理者に返す情報**

-   データベースサーバーまたはインスタンスの名前と、App-v データベースの名前

データベースの準備が完了したら、App-v 管理者は、SQL 管理者権限を持たずに app-v のインストールを実行できます。

### SQL セットアップスクリプトを使用する

**要件**

選択した抽出位置のルートの support\\createdb フォルダーにあるスクリプトを使用するための要件の一覧を次に示します。

-   スクリプトは、実行先のコンピューター上の書き込み可能な場所にコピーする必要があります (コピーされた後にこれらのスクリプトから読み取り専用属性を削除してください)。 SQL クライアントツールは、そのコンピューターに読み込む必要があります (osql は、ローカルコンピューターでサンプルのバッチファイルを実行する場合のみ必要です)。

-   SQL Server は Windows 認証をサポートしている必要があります。

-   SQL Server インスタンスと SQL エージェントサービスが実行されていることを確認します。

-   スクリプトが実行されるコンピューターの SQL 管理者 (sysadmin) であるドメインアカウントでログオンします。

スクリプトは、ログオンしているユーザーのドメイン資格情報で実行されます。

**SQL スクリプトを使用したデータベースの作成**

**SQL 管理者が実行するタスク:**

1.  選択した抽出場所のルートから、スクリプトが実行されるコンピューターに、support\\createdb フォルダーに含まれているスクリプトをコピーします。 スクリプトを正しく実行するためには次のファイルが必要であり、次の順序で呼び出す必要があります。

    -   データベース。 sql

    -   ロール. sql

    -   表 \ _CODES

    -   関数 \ _before \ _tables

    -   表 .sql

    -   関数 .sql

    -   views

    -   手順 .sql

    -   triggers

    -   データ \ _codes .sql

    -   データ \ _messages .sql

    -   データ \ _defaults .sql

    -   通知 \ _jobs

    -   dbversion .sql

2.  ファイルを確認し、必要に応じて変更し `database.sql` ます。 既定の設定では、データベースに "APPVIRTDB" という名前が付いています。

    -   必要に応じて、が使用されるのインスタンスをに置き換え `APPVIRTDB` `database name` ます。

    -   `FILENAME`スクリプト内のプロパティを、データベースを作成する SQL Server の適切なパスに変更します。

3.  必要に応じて、 `database name [APPVIRTDB]` データベースの .sql ファイルで `roles.sql` 使用されていたファイルの内容を確認して変更します。

****

### バッチファイルを使用してプロセスを自動化する方法の例

この2つのサンプルバッチファイルを使用すると、次のような方法で SQL スクリプトが実行されます。

1.  **Create\_schema.bat (1)**

    -   データベース。 sql

    -   ロール. sql

2.  **Create\_tables.bat (2)**

    -   表 \ _CODES

    -   関数 \ _before \ _tables

    -   表 .sql

    -   関数 .sql

    -   views

    -   手順 .sql

    -   triggers

    -   データ \ _codes .sql

    -   データ \ _messages .sql

    -   データ \ _defaults .sql

    -   通知 \ _jobs

    -   dbversion .sql

**注**  
スクリプトを変更するときは慎重に考慮する必要があります。また、適切な知識を持っているユーザーだけが実行する必要があります。 また、表示されるサンプルファイルは、次のように変更する必要があります。 **create\_schema.bat**、 **create\_tables.bat**、 **.sql**、および**roles**。 その他のすべてのファイルを変更しないようにする必要があります。これにより、データベースが正しく作成されないことがあります。これにより、App-v サービスのインストールに失敗する可能性があります。



この2つのサンプルバッチファイルは、コンピューター上の他の SQL スクリプトのコピー先と同じディレクトリに配置する必要があります。

1.  サンプルの**create\_schema.bat**ファイルを実行してデータベースを作成します。 このスクリプトは、完了までに数秒かかりますので、中断する必要はありません。

    -   コピー先のディレクトリから [create schema.bat ファイルを実行します。 書式: "Create\_schema.bat `SQLSERVERNAME` "

        ![AppV46SQLcreatebat](images/appv46sqlcreatebat.bmp)

    -   このスクリプトが新しい "APPVIRTDB" データベースの作成中に失敗した場合は、上記のようにログを確認して問題を修正します。 以降の試行が適切に動作するようにするために、スクリプトの一部を実行して作成されたデータベースを削除する必要があります。

2.  ファイルを実行して `create_tables.bat` データベース内のテーブルを作成します。 このスクリプトは、完了までに数秒かかりますので、中断する必要はありません。

    -   コピーされたディレクトリから create\_tables.bat ファイルを実行します。 書式: "create\_tables.bat `SQLSERVERNAME DBNAME` "

        ![app-v 4.6 sql create\-table.bat](images/appv46sqlcreate-tablebat.gif)

        テーブルの作成時にスクリプトが失敗した場合は、上記のようにログを確認して問題を修正します。 データベースを削除して create\_schema.bat 実行してから、create\_tables.bat ファイルを実行しようとするたびに実行する必要があります。

### App-v データベースのアクセス許可を設定する

アプリのインストール、展開、継続的な管理のために、新しいデータベースに対する特定の権限と役割を持つ SQL server 上で、次のアカウントを作成する必要があります。

-   SQL Server 上の App-v 管理グループのログインを作成し、"domain\\App-V Admins" ("domain" と "App-v Admins" は、自分の環境を反映するために変更されます) APPVIRTDB データベースを作成し、それを SFTAdmin と SFTEveryone database role に追加します。

    ![app-v 4.6 sql スクリプト: 権限とロールを設定する](images/appv46sqlscriptsetpermsroles.gif)

-   グローバルレベルで "VIEW ANY DEFINITION" アクセス許可を与える (Microsoft Application Virtualization Management Server のセットアッププロセスでは、管理サーバーのログインが既に存在することを確認できます)。 [MS SQL 2005] の下で、.master に含まれるメタデータに対するアクセス制限が追加されました。 前の手順で作成したユーザーには、サーバーのインストールに必要な権限が既定で付与されることはありません。 以前に作成したログインプロパティ-Securables のプロパティを開き &gt; ます。 次のスクリーンショットのように、データベースインスタンスを追加して、"すべての定義を表示" に "GRANT" を有効にします。

    ![app-v 4.6 sql スクリプト表示の権限を付与する](images/appv46sqlscriptviewanydef.gif)

-   前の手順で作成したログインの役割 \ _ASSIGNMENTS テーブルに役割を追加して、Application Virtualization 管理コンソールへのアクセスを許可します。役割 = "ADMIN" とグループ \ _ref = "domain\\App-V administrator" ("domain" と "App-info Admins") は、自分の環境を反映するように変更されます)。

    ![app-v 4.6 sql スクリプトの役割の割り当て](images/appv46sqlscriptroleassign.gif)

-   管理サーバーの SQL Server と App-v データベースのログインを作成します。 このアカウントは、Microsoft Application Virtualization Management Server がデータストアに接続するために使用され、ストリーミングされたアプリケーションに対するクライアント要求の処理を担当します。 SQL Server と管理サーバーをインストールする場所に応じて、次の2つのオプションがあります。

    1.  管理サーバーと SQL Server が同じコンピューターにインストールされる場合は、NT AUTHORITY\\NETWORK SERVICE のログインを追加して、SFTUser と SFTEveryone database ロールに追加します。

    2.  管理サーバーと SQL Server を異なるコンピューターにインストールする場合は、"domain\\App-V Server Name $" ("App-V Server Name $") のログインを追加して、SFTUser ロールと SFTEveryone database ロールにそのサーバーの名前が追加されるようにします。

-   SQL ウィンドウで [クエリ] ウィンドウを開いて、次の SQL を実行します。

    ``` syntax
    USE APPVIRTDB
    GRANT ALTER ON ROLE::SFTuser TO “domain\App-V Admins”
    ```

    ここで、APPVIRTDB は、前の手順で SQL Server で作成された App-v データベースの名前であり、アプリをインストールするユーザーは "domain\\App-V Admins" のメンバーである必要があります ("domain" と "App V Admins" は、自分の環境を反映するように変更されます)。

### インフラストラクチャ管理者によって実行されるタスク

1.  "App-v Admins" グループの管理者は、App-v をインストールする必要があります。

    SQL 管理者からの情報を使用して、前の手順で作成した SQL Server とデータベースを選択します。

2.  "App-v Admins" グループの管理者は、Application Virtualization 管理コンソールにログインし、管理コンソールから次のオブジェクトを削除します。

    **Warning**  
    これは、既存のデータベースに対してインストールを実行する場合、従来のセットアップによってデータベース内の特定のレコードに入力される必要があるためです。 次のオブジェクトを削除します。

    -   [サーバーグループ] の下で、"既定のサーバーグループ" というアプリケーション仮想化管理サーバーを削除します。

    -   [サーバーグループ] の [既定のサーバーグループの削除]

    -   "プロバイダーポリシー" で、"既定のプロバイダー" を削除します。



3.  App-v admins グループの管理者は次のものを作成する必要があります。

    -   [プロバイダーポリシー] の下で、新しいプロバイダーポリシーを作成する

    -   "既定のサーバーグループ" を作成する

        **注**  
        使用しない場合でも、"既定のサーバー" グループを作成する必要があります。 サーバーのインストーラーでは、サーバーを追加しようとしたときに、"既定のサーバーグループ" のみが検索されます。  "既定のサーバーグループ" が存在しない場合、インストールは失敗します。 既定以外のサーバーグループを使用することを計画している場合は、その後の App-v 管理サーバーをインフラストラクチャに追加する予定がある場合は、"既定のサーバーグループ" を保持する必要があるだけです。



~~~
-   Assign the App-V Users Group to the New Provider Policy created above

-   Under “Server Groups,” create a New Server Group, specifying the New Provider Policy

-   Under the New Server group, create a New Application Virtualization Management Server

    **Important**  
    Do not restart the service before completing all of the above steps!



-   Administrator restarts the Application Virtualization Management Server service.
~~~

## まとめ


このドキュメントに記載されている情報により、管理者は、組織内のセキュリティと管理部門に対応する展開パスを開発するために、SQL 管理者と作業を行うことができます。 このドキュメントを読み、文書化されたタスクをテストした後、管理者はこの種類の環境にアプリの app-v インフラストラクチャを実装する準備ができている必要があります。









