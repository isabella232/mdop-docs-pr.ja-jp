---
title: App-V の SQL データベースを別の SQL Server に移行する方法
description: App-V の SQL データベースを別の SQL Server に移行する方法
author: dansimp
ms.assetid: 353892a1-9327-4489-a19c-4ec7bd1b736f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e3d84b0cb328873db3722ad3eb9af6a2b442fdcf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817074"
---
# App-V の SQL データベースを別の SQL Server に移行する方法


次の手順では、Microsoft Application Virtualization (App-v) Management サーバーの SQL データベースを別の SQL Server に移行する方法について詳しく説明します。

**重要** この手順を実行するには、App-v server サービスが停止している必要があります。これにより、エンドユーザーはアプリケーションを使用できなくなります。

 

**App-v SQL データベースのバックアップを作成するには**

1.  Services.msc プログラムを開き、移行するデータベースを使用するすべての管理サーバーで、App-v Management Server サービスを停止します。

2.  App-v データベースが配置されているコンピューターで、SQL Server Management Studio を開きます。

3.  [**データベース**] ノードを展開し、app-v データベース (既定の名前は APPVIRT) を探します。

4.  データベースを右クリックして、[**タスク**] を選択し、[**バックアップ**] を選択します。

5.  **回復モデル**が**SIMPLE**に設定されていることを確認し、**バックアップの種類**が [**完全**] に設定されていることを確認します。 必要に応じて、**バックアップセット**と**インストール先**の設定を変更します。

6.  [ **OK** ] をクリックしてデータベースをバックアップします。 バックアップが正常に完了したら、[ **OK]** をクリックします。

7.  Windows エクスプローラーを開き、データベースのバックアップファイルを含むフォルダー (APPVIRT など) を参照します。拡張子. SQL Server が実行されているターゲットコンピューターにデータベースバックアップファイルをコピーします。

**ターゲットコンピューターに App-v SQL データベースを復元するには**

1.  送信先コンピューターで SQL Server Management Studio を開き、[**データベース**] ノードを右クリックし、[**データベースの復元**] を選択します。

2.  [**復元のためのソース**] で、[**デバイスから**] を選択し、[**...**] をクリックします。  ボタンをクリックします。

3.  [**バックアップの指定**] ダイアログボックスで、**バックアップメディア**が [**ファイル**] に設定されていることを確認し、[**追加**] をクリックします。

4.  SQL Server が実行されている元のコンピューターからコピーしたバックアップファイルを選び、[ **OK]** をクリックします。

5.  [ **OK]** をクリックして、復元するバックアップセットをクリックします。

6.  [**復元先**] の下で、[データベース] のドロップダウンをクリックして、「APPVIRT」などの**よう**に、app-v データベース名を選びます。

7.  [ **OK** ] をクリックして復元を開始します。 復元が正常に完了したら、[ **OK]** をクリックします。

8.  [**セキュリティ**] ノードを展開し、[**ログイン**] を右クリックして、[**新しいログイン**] を選びます。

9.  [ **Login Name** ] フィールドに、DOMAIN\\SERVERNAME $ の形式で、App-v Management Server のネットワークサービスアカウントの詳細を入力します。

10. [**全般**] ページの [**既定のデータベース**] で、[APPVIRT] などの [app-v データベース名] を選び、[ **OK]** をクリックします。

11. [**ページの選択**] で、[**ユーザーマッピング**] ページをクリックして選択します。 [**このログインにマップ**されているユーザー] で、[**マップ**] 列のチェックボックスをオンにして、app-v データベースを選択します。

12. [ ** &lt; Appvdatabasename &gt; のデータベースロールメンバーシップ**] で、[ **SFTEveryone** ] をクリックして選択し、[ **OK]** をクリックします。

13. SQL Server が実行されている新しいコンピューターの Windows ファイアウォールが、アプリによるシステムへのアクセスを許可するように構成されていることを確認します。 [**管理ツール**] の下で、 **Windows ファイアウォールと高度なセキュリティ**プログラムを使用して、SQL Server で使用されているポートの**受信規則**を作成します (既定は port 1433)。

**App-v SQL Server エージェントジョブを移行するには**

1.  Sql server が実行されている元のコンピューターで、sql server Management Studio で [ **Sql Server エージェント**] ノードを展開し、[**ジョブ**] ノードを展開します。

2.  次の4つの App-v ジョブを右クリックし、[as Script Job] (|) を選びます。 **作成 |** 各スクリプトをフォルダーに保存し、各スクリプトにわかりやすい名前を付けます。

    -   **Softgrid Database (appvdbname) の使用状況の履歴を確認する**

    -   **Softgrid Database (appvdbname) 孤立したセッションを閉じる**

    -   **Softgrid Database (appvdbname) サイズの制限を適用する**

    -   **Softgrid Database (appvdbname) Alert/Job の状態を監視する**

3.  4つのスクリプトファイル (.sql) を、SQL Server を実行しているターゲットコンピューターにコピーして、SQL Server Management Studio を開きます。

4.  Windows エクスプローラーで、各 .sql ファイルを右クリックし、[**実行**] をクリックします。 各スクリプトは、SQL Server Management Studio のクエリウィンドウで開きます。 各スクリプトの [**実行**] をクリックして、それぞれが正常に完了したことを確認します。

5.  **SQL Server エージェント**ノードの下にある [**ジョブ**] ノードを更新して、4つのジョブが正常に作成されていることを確認します。

**App-v 管理サーバーの構成を更新するには**

1.  App-v 管理サーバーで、次のレジストリキーを変更します。

    -   **Sqlservername**  =  &lt;newservername&gt;

    -   **SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;

    次に、App-v server サービスを再起動します。

2.  [参照] を選択して、App-v Management Server のインストールディレクトリの下にあるファイルを検索します (既定は c/c/l System Center App Virt Management server¥ Virt Management Service)。 ファイルを右クリックし、[**開く**] を選択します。

3.  [**接続**] タブで、SQL Server を実行しているインポート先コンピューターの名前を入力し、[**接続のテスト**] をクリックします。 テストが成功したら、[ **ok** ] をクリックし、[ **ok** ] をもう一度クリックします。

4.  4.5 SP2 より前のバージョンの App-v Management Server のバージョンの場合は、SQL ログ設定を更新する必要があります。 [**サーバーグループ**] で、サーバーがメンバーであるサーバーグループを右クリックし、[**プロパティ**] を選択します。

5.  [**ログ**] タブで、[ **SQL データベース**] エントリをクリックし、[**編集**] をクリックします。

6.  **DNS ホスト名**を、SQL Server を実行している新しいコンピューターのホスト名に変更して、[ **OK]** をクリックします。 [ **OK]** を2回クリックして、app-v server サービスを再起動します。

7.  App-v 管理コンソールを開き、[**アプリケーション**] ノードを右クリックして、[**更新**] を選択します。 アプリケーションの一覧は以前と同じように表示される必要があります。

 

 





