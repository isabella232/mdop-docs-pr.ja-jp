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
# <span data-ttu-id="de411-103">App-V の SQL データベースを別の SQL Server に移行する方法</span><span class="sxs-lookup"><span data-stu-id="de411-103">How to Migrate the App-V SQL Database to a Different SQL Server</span></span>


<span data-ttu-id="de411-104">次の手順では、Microsoft Application Virtualization (App-v) Management サーバーの SQL データベースを別の SQL Server に移行する方法について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="de411-104">The following procedures describe in detail how to migrate the SQL database of the Microsoft Application Virtualization (App-V) Management Server to a different SQL Server.</span></span>

<span data-ttu-id="de411-105">**重要** この手順を実行するには、App-v server サービスが停止している必要があります。これにより、エンドユーザーはアプリケーションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="de411-105">**Important** This procedure requires that the App-V server service is stopped and this will prevent end-users from using their applications.</span></span>

 

**<span data-ttu-id="de411-106">App-v SQL データベースのバックアップを作成するには</span><span class="sxs-lookup"><span data-stu-id="de411-106">To back up the App-V SQL database</span></span>**

1.  <span data-ttu-id="de411-107">Services.msc プログラムを開き、移行するデータベースを使用するすべての管理サーバーで、App-v Management Server サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="de411-107">Open the Services.msc program and stop the App-V Management Server service on all Management Servers that use the database to be migrated.</span></span>

2.  <span data-ttu-id="de411-108">App-v データベースが配置されているコンピューターで、SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="de411-108">On the computer where the App-V database is located, open SQL Server Management Studio.</span></span>

3.  <span data-ttu-id="de411-109">[**データベース**] ノードを展開し、app-v データベース (既定の名前は APPVIRT) を探します。</span><span class="sxs-lookup"><span data-stu-id="de411-109">Expand the **Databases** node and locate the App-V database (default name is APPVIRT).</span></span>

4.  <span data-ttu-id="de411-110">データベースを右クリックして、[**タスク**] を選択し、[**バックアップ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-110">Right-click the database and select **Tasks** and then select **Back Up**.</span></span>

5.  <span data-ttu-id="de411-111">**回復モデル**が**SIMPLE**に設定されていることを確認し、**バックアップの種類**が [**完全**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de411-111">Verify that **Recovery model** is set to **SIMPLE** and the **Backup type** is set to **Full**.</span></span> <span data-ttu-id="de411-112">必要に応じて、**バックアップセット**と**インストール先**の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="de411-112">Change the **Backup set** and **Destination** settings if it is necessary.</span></span>

6.  <span data-ttu-id="de411-113">[ **OK** ] をクリックしてデータベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="de411-113">Click **OK** to back up the database.</span></span> <span data-ttu-id="de411-114">バックアップが正常に完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-114">After the backup has completed successfully, click **OK**.</span></span>

7.  <span data-ttu-id="de411-115">Windows エクスプローラーを開き、データベースのバックアップファイルを含むフォルダー (APPVIRT など) を参照します。拡張子.</span><span class="sxs-lookup"><span data-stu-id="de411-115">Open Windows Explorer and browse to the folder that contains the database backup file, for example APPVIRT.BAK.</span></span> <span data-ttu-id="de411-116">SQL Server が実行されているターゲットコンピューターにデータベースバックアップファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="de411-116">Copy the database backup file to the destination computer that is running SQL Server.</span></span>

**<span data-ttu-id="de411-117">ターゲットコンピューターに App-v SQL データベースを復元するには</span><span class="sxs-lookup"><span data-stu-id="de411-117">To restore the App-V SQL database to the destination computer</span></span>**

1.  <span data-ttu-id="de411-118">送信先コンピューターで SQL Server Management Studio を開き、[**データベース**] ノードを右クリックし、[**データベースの復元**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-118">On the destination computer, open SQL Server Management Studio, right-click the **Databases** node and select **Restore Database**.</span></span>

2.  <span data-ttu-id="de411-119">[**復元のためのソース**] で、[**デバイスから**] を選択し、[**...**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-119">Under **Source for Restore**, choose **From device** and then click the “**…**”</span></span> <span data-ttu-id="de411-120"> ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-120">button.</span></span>

3.  <span data-ttu-id="de411-121">[**バックアップの指定**] ダイアログボックスで、**バックアップメディア**が [**ファイル**] に設定されていることを確認し、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-121">In the **Specify Backup** dialog box, make sure that the **Backup Media** is set to **File** and then click **Add**.</span></span>

4.  <span data-ttu-id="de411-122">SQL Server が実行されている元のコンピューターからコピーしたバックアップファイルを選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-122">Select the backup file that you copied from the original computer that is running SQL Server, and then click **OK**.</span></span>

5.  <span data-ttu-id="de411-123">[ **OK]** をクリックして、復元するバックアップセットをクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-123">Click **OK** and then click to select the backup set to restore.</span></span>

6.  <span data-ttu-id="de411-124">[**復元先**] の下で、[データベース] のドロップダウンをクリックして、「APPVIRT」などの**よう**に、app-v データベース名を選びます。</span><span class="sxs-lookup"><span data-stu-id="de411-124">Under **Destination for restore**, click the drop-down for **To database** and select the App-V database name, for example APPVIRT.</span></span>

7.  <span data-ttu-id="de411-125">[ **OK** ] をクリックして復元を開始します。</span><span class="sxs-lookup"><span data-stu-id="de411-125">Click **OK** to start the restore.</span></span> <span data-ttu-id="de411-126">復元が正常に完了したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-126">After the restore has completed successfully, click **OK**.</span></span>

8.  <span data-ttu-id="de411-127">[**セキュリティ**] ノードを展開し、[**ログイン**] を右クリックして、[**新しいログイン**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="de411-127">Expand the **Security** node, right-click **Logins** and select **New Login**.</span></span>

9.  <span data-ttu-id="de411-128">[ **Login Name** ] フィールドに、DOMAIN\\SERVERNAME $ の形式で、App-v Management Server のネットワークサービスアカウントの詳細を入力します。</span><span class="sxs-lookup"><span data-stu-id="de411-128">In the **Login Name** field, enter the Network Service account details for the App-V Management Server in the format of DOMAIN\\SERVERNAME$.</span></span>

10. <span data-ttu-id="de411-129">[**全般**] ページの [**既定のデータベース**] で、[APPVIRT] などの [app-v データベース名] を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-129">On the **General** page under **Default database** select the App-V database name, for example, APPVIRT, and then click **OK**.</span></span>

11. <span data-ttu-id="de411-130">[**ページの選択**] で、[**ユーザーマッピング**] ページをクリックして選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-130">Under **Select a page**, click to select the **User Mapping** page.</span></span> <span data-ttu-id="de411-131">[**このログインにマップ**されているユーザー] で、[**マップ**] 列のチェックボックスをオンにして、app-v データベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-131">Under **Users mapped to this login**, click the check box in the **Map** column to select the App-V database.</span></span>

12. <span data-ttu-id="de411-132">[ \*\* &lt; Appvdatabasename &gt; のデータベースロールメンバーシップ\*\*] で、[ **SFTEveryone** ] をクリックして選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-132">Under **Database role membership for: &lt;appvdatabasename&gt;**, click to select **SFTEveryone** and then click **OK**.</span></span>

13. <span data-ttu-id="de411-133">SQL Server が実行されている新しいコンピューターの Windows ファイアウォールが、アプリによるシステムへのアクセスを許可するように構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de411-133">Make sure that the Windows Firewall on the new computer that is running SQL Server is configured to allow the App-V Management Server to access the system.</span></span> <span data-ttu-id="de411-134">[**管理ツール**] の下で、 **Windows ファイアウォールと高度なセキュリティ**プログラムを使用して、SQL Server で使用されているポートの**受信規則**を作成します (既定は port 1433)。</span><span class="sxs-lookup"><span data-stu-id="de411-134">Under **Administrative Tools**, use the **Windows Firewall with Advanced Security** program to create an **Inbound Rule** for the port that is used by SQL Server (default is port 1433).</span></span>

**<span data-ttu-id="de411-135">App-v SQL Server エージェントジョブを移行するには</span><span class="sxs-lookup"><span data-stu-id="de411-135">To migrate the App-V SQL Server Agent jobs</span></span>**

1.  <span data-ttu-id="de411-136">Sql server が実行されている元のコンピューターで、sql server Management Studio で [ **Sql Server エージェント**] ノードを展開し、[**ジョブ**] ノードを展開します。</span><span class="sxs-lookup"><span data-stu-id="de411-136">On the original computer that is running SQL Server, in SQL Server Management Studio, expand the **SQL Server Agent** node, and then expand the **Jobs** node.</span></span>

2.  <span data-ttu-id="de411-137">次の4つの App-v ジョブを右クリックし、[as Script Job] (|) を選びます。 **作成 |** 各スクリプトをフォルダーに保存し、各スクリプトにわかりやすい名前を付けます。</span><span class="sxs-lookup"><span data-stu-id="de411-137">Right-click the following four App-V jobs and select **Script Job as | CREATE to | File**, and save each script to a folder and give each script a descriptive name.</span></span>

    -   **<span data-ttu-id="de411-138">Softgrid Database (appvdbname) の使用状況の履歴を確認する</span><span class="sxs-lookup"><span data-stu-id="de411-138">Softgrid Database (appvdbname) Check Usage History</span></span>**

    -   **<span data-ttu-id="de411-139">Softgrid Database (appvdbname) 孤立したセッションを閉じる</span><span class="sxs-lookup"><span data-stu-id="de411-139">Softgrid Database (appvdbname) Close Orphaned Sessions</span></span>**

    -   **<span data-ttu-id="de411-140">Softgrid Database (appvdbname) サイズの制限を適用する</span><span class="sxs-lookup"><span data-stu-id="de411-140">Softgrid Database (appvdbname) Enforce Size Limit</span></span>**

    -   **<span data-ttu-id="de411-141">Softgrid Database (appvdbname) Alert/Job の状態を監視する</span><span class="sxs-lookup"><span data-stu-id="de411-141">Softgrid Database (appvdbname) Monitor Alert/Job Status</span></span>**

3.  <span data-ttu-id="de411-142">4つのスクリプトファイル (.sql) を、SQL Server を実行しているターゲットコンピューターにコピーして、SQL Server Management Studio を開きます。</span><span class="sxs-lookup"><span data-stu-id="de411-142">Copy the four script files (.sql) to the destination computer that is running SQL Server and open SQL Server Management Studio.</span></span>

4.  <span data-ttu-id="de411-143">Windows エクスプローラーで、各 .sql ファイルを右クリックし、[**実行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-143">In Windows Explorer, right-click each .sql file and then click **Run**.</span></span> <span data-ttu-id="de411-144">各スクリプトは、SQL Server Management Studio のクエリウィンドウで開きます。</span><span class="sxs-lookup"><span data-stu-id="de411-144">Each script will open in a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="de411-145">各スクリプトの [**実行**] をクリックして、それぞれが正常に完了したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="de411-145">Click **Execute** for each script and verify that each is completed successfully.</span></span>

5.  <span data-ttu-id="de411-146">**SQL Server エージェント**ノードの下にある [**ジョブ**] ノードを更新して、4つのジョブが正常に作成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de411-146">Refresh the **Jobs** node under the **SQL Server Agent** node and confirm that the four jobs are created successfully.</span></span>

**<span data-ttu-id="de411-147">App-v 管理サーバーの構成を更新するには</span><span class="sxs-lookup"><span data-stu-id="de411-147">To update the configuration of the App-V Management Server</span></span>**

1.  <span data-ttu-id="de411-148">App-v 管理サーバーで、次のレジストリキーを変更します。</span><span class="sxs-lookup"><span data-stu-id="de411-148">On the App-V Management Server, modify the following registry keys:</span></span>

    -   <span data-ttu-id="de411-149">**Sqlservername**  =  &lt;newservername&gt;</span><span class="sxs-lookup"><span data-stu-id="de411-149">**SQLServerName** = &lt;newservername&gt;</span></span>

    -   <span data-ttu-id="de411-150">**SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;</span><span class="sxs-lookup"><span data-stu-id="de411-150">**SQLServerPort** = &lt;newserverport&gt;</span></span>

    <span data-ttu-id="de411-151">次に、App-v server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="de411-151">Then restart the App-V server service.</span></span>

2.  <span data-ttu-id="de411-152">[参照] を選択して、App-v Management Server のインストールディレクトリの下にあるファイルを検索します (既定は c/c/l System Center App Virt Management server¥ Virt Management Service)。</span><span class="sxs-lookup"><span data-stu-id="de411-152">Browse to find the file SftMgmt.udl under the App-V Management Server installation directory (default is C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service).</span></span> <span data-ttu-id="de411-153">ファイルを右クリックし、[**開く**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-153">Right-click the file and select **Open**.</span></span>

3.  <span data-ttu-id="de411-154">[**接続**] タブで、SQL Server を実行しているインポート先コンピューターの名前を入力し、[**接続のテスト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-154">On the **Connection** tab, enter the name of the destination computer that is running SQL Server, and then click **Test Connection**.</span></span> <span data-ttu-id="de411-155">テストが成功したら、[ **ok** ] をクリックし、[ **ok** ] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-155">When the test is successful, click **OK** and then click **OK** again.</span></span>

4.  <span data-ttu-id="de411-156">4.5 SP2 より前のバージョンの App-v Management Server のバージョンの場合は、SQL ログ設定を更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de411-156">For App-V Management Server versions before 4.5 SP2, you must update the SQL Logging settings.</span></span> <span data-ttu-id="de411-157">[**サーバーグループ**] で、サーバーがメンバーであるサーバーグループを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-157">Under **Server Groups**, right-click the server group the server is a member of and select **Properties**.</span></span>

5.  <span data-ttu-id="de411-158">[**ログ**] タブで、[ **SQL データベース**] エントリをクリックし、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-158">On the **Logging** tab click to select the **SQL Database** entry and then click **Edit**.</span></span>

6.  <span data-ttu-id="de411-159">**DNS ホスト名**を、SQL Server を実行している新しいコンピューターのホスト名に変更して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="de411-159">Change the **DNS Host Name** to the host name of the new computer that is running SQL Server and then click **OK**.</span></span> <span data-ttu-id="de411-160">[ **OK]** を2回クリックして、app-v server サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="de411-160">Click **OK** two times more, and then restart the App-V server service.</span></span>

7.  <span data-ttu-id="de411-161">App-v 管理コンソールを開き、[**アプリケーション**] ノードを右クリックして、[**更新**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="de411-161">Open the App-V Management Console, right-click the **Applications** node and select **Refresh**.</span></span> <span data-ttu-id="de411-162">アプリケーションの一覧は以前と同じように表示される必要があります。</span><span class="sxs-lookup"><span data-stu-id="de411-162">The list of applications should be displayed as before.</span></span>

 

 





