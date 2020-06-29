---
title: App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法
description: App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817934"
---
# <span data-ttu-id="8d287-103">App-V 用に Microsoft SQL Server ミラーリングのサポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8d287-103">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>


<span data-ttu-id="8d287-104">Microsoft Application Virtualization (App-v) 環境で Microsoft SQL Server データベースのミラーリングを使用するように構成するには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="8d287-104">You can use the following procedure to configure your Microsoft Application Virtualization (App-V) environment to use Microsoft SQL Server database mirroring.</span></span> <span data-ttu-id="8d287-105">データベースミラーリングの構成は、障害回復とフェールオーバーのシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8d287-105">Configuring database mirroring can help with disaster recovery and failover scenarios.</span></span> <span data-ttu-id="8d287-106">App-v 4.5 SP2 では、Microsoft SQL Server 2005 と SQL Server 2008 で現在利用できるデータベースミラーリングのすべてのモードがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8d287-106">App-V 4.5 SP2 supports all modes of database mirroring currently available for Microsoft SQL Server 2005 and SQL Server 2008.</span></span>

**<span data-ttu-id="8d287-107">注</span><span class="sxs-lookup"><span data-stu-id="8d287-107">Note</span></span>**  
<span data-ttu-id="8d287-108">この手順は、Microsoft SQL Server との SQL Server データベースとデータベースのミラーリングのセットアップと構成に精通している管理者向けに記述されています。そのため、アプリに固有の構成設定のみが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8d287-108">This procedure is written for administrators who are familiar with setting up and configuring SQL Server databases and database mirroring with Microsoft SQL Server, and therefore covers only the specific configuration settings that are unique to App-V.</span></span>



**<span data-ttu-id="8d287-109">Microsoft SQL Server データベースのミラーリングを使用するように App-v 環境を構成するには</span><span class="sxs-lookup"><span data-stu-id="8d287-109">To configure your App-V environment to use Microsoft SQL Server database mirroring</span></span>**

1.  <span data-ttu-id="8d287-110">データベースミラーリングの標準的なビジネスプラクティスに従って、App-v データベースの SQL Server データベースのミラーリングをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="8d287-110">Set up SQL Server database mirroring of the App-V database following your standard business practices for database mirroring.</span></span> <span data-ttu-id="8d287-111">Microsoft SQL Server データベースのミラーリングに関する一般的な情報については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8d287-111">Use the following links for general information about implementing Microsoft SQL Server database mirroring:</span></span>

    -   <span data-ttu-id="8d287-112">**MICROSOFT SQL 2005**:[データベースミラーリングのセットアップ](https://go.microsoft.com/fwlink/?LinkId=187478)(https://go.microsoft.com/fwlink/?LinkId=187478)</span><span class="sxs-lookup"><span data-stu-id="8d287-112">**Microsoft SQL 2005**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187478) (https://go.microsoft.com/fwlink/?LinkId=187478)</span></span>

    -   <span data-ttu-id="8d287-113">**MICROSOFT SQL 2008**:[データベースミラーリングのセットアップ](https://go.microsoft.com/fwlink/?LinkId=187477)(https://go.microsoft.com/fwlink/?LinkId=187477)</span><span class="sxs-lookup"><span data-stu-id="8d287-113">**Microsoft SQL 2008**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187477) (https://go.microsoft.com/fwlink/?LinkId=187477)</span></span>

    <span data-ttu-id="8d287-114">また、[データベースミラーリングのベストプラクティスとパフォーマンスに関する考慮事項](https://go.microsoft.com/fwlink/?LinkId=190270)( https://go.microsoft.com/fwlink/?LinkId=190270) .</span><span class="sxs-lookup"><span data-stu-id="8d287-114">In addition, you can find Best Practices information in [Database Mirroring Best Practices and Performance Considerations](https://go.microsoft.com/fwlink/?LinkId=190270) (https://go.microsoft.com/fwlink/?LinkId=190270).</span></span>

2.  <span data-ttu-id="8d287-115">ミラーリングをセットアップした後で、App-v データベースに状態 **(プリンシパル、同期済み)** が表示されていることを確認し、ミラーされたデータベースに状態 **(ミラー、同期済み、復元)** が表示されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d287-115">After mirroring has been set up, verify that the App-V database shows a status of **(Principal, Synchronized)**, and the mirrored database shows a status of **(Mirror, Synchronized / Restoring)**.</span></span> <span data-ttu-id="8d287-116">次の手順に進む前に、ミラーリングの問題を解決してください。</span><span class="sxs-lookup"><span data-stu-id="8d287-116">Resolve any mirroring issues before proceeding to the next step.</span></span> <span data-ttu-id="8d287-117">状態の監視に関する追加情報については、「[ミラーリング状態の監視](https://go.microsoft.com/fwlink/?LinkId=190279)()」をご覧ください https://go.microsoft.com/fwlink/?LinkId=190279) 。</span><span class="sxs-lookup"><span data-stu-id="8d287-117">For additional information about monitoring the status, see [Monitoring Mirroring Status](https://go.microsoft.com/fwlink/?LinkId=190279) (https://go.microsoft.com/fwlink/?LinkId=190279).</span></span>

3.  <span data-ttu-id="8d287-118">App-v データベースのミラーをホストする sql server コンピューターで、[account name \*\* &lt; domain &gt; \\ &lt; managementserverhostname &gt; $ \*\*] というアカウント名を使用して、app-v Management Server の network service アカウント用の sql server ログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="8d287-118">On the SQL Server computer that hosts the mirror of the App-V database, create the SQL Server Login for the network service account of the App-V Management Server by using the account name **&lt;domain&gt;\\&lt;ManagementServerHostName&gt;$**.</span></span>

4.  <span data-ttu-id="8d287-119">Microsoft SQL Server Native Client を App-v Management Server にインストールして、別のコンピューターにインストールされている場合は、App-v Management Web サービスを実行しているコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="8d287-119">Install the Microsoft SQL Server Native Client on the App-V Management Server, and on the computer running the App-V Management Web Service if installed on a different computer.</span></span> <span data-ttu-id="8d287-120">追加の App-v 管理サーバーを使用して、負荷分散のためにミラーリングされた SQL データベースに接続することを計画している場合は、これらのコンピューターにも Microsoft SQL Server Native Client をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-120">If you plan to have additional App-V Management Servers connect to the mirrored SQL database for load balancing, you must install the Microsoft SQL Server Native Client on those computers as well.</span></span> <span data-ttu-id="8d287-121">Microsoft ダウンロードセンター () で microsoft [Sql server 2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=187479)のページから Microsoft Sql Server Native Client をダウンロードでき https://go.microsoft.com/fwlink/?LinkId=187479) ます。</span><span class="sxs-lookup"><span data-stu-id="8d287-121">You can download the Microsoft SQL Server Native Client from the [Microsoft SQL Server 2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=187479) page in the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=187479).</span></span>

5.  <span data-ttu-id="8d287-122">レジストリキーの\**HKEY \ _LOCAL \ _MACHINE \** "\" というメッセージが表示されていることを確認してください。 \ \ または \ という名前のファイルが含まれていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d287-122">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerName** and make sure that it contains only the host name of the SQL Server.</span></span> <span data-ttu-id="8d287-123">たとえば、 *serverhostname\\instancename*のようにインスタンス名が含まれている場合は、インスタンス名を削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-123">If it includes an instance name, for example *serverhostname\\instancename*, the instance name must be removed.</span></span>

    **<span data-ttu-id="8d287-124">重要</span><span class="sxs-lookup"><span data-stu-id="8d287-124">Important</span></span>**  
    <span data-ttu-id="8d287-125">データベースのミラーリングが有効になっている場合、App-v Management Server は TCP/IP ネットワークライブラリを使って SQL Server と通信するため、インスタンス名を使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="8d287-125">The App-V Management Server uses the TCP/IP networking library to communicate with the SQL Server when database mirroring is enabled, and therefore instance names cannot be used.</span></span> <span data-ttu-id="8d287-126">代わりに、ポート番号をレジストリキーに指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-126">The port numbers must be specified in the registry keys instead.</span></span>



6.  <span data-ttu-id="8d287-127">レジストリキーの**HKEY \ _LOCAL \ _MACHINE**を確認し、sql Server コンピューターの sql に使用されているポート番号が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="8d287-127">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerPort** and make sure that it contains the port number that is used for SQL on the SQL Server computer.</span></span> <span data-ttu-id="8d287-128">名前付きインスタンスを使用している場合は、このキー値を名前付きインスタンスに使用するポートに設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-128">If you are using a named instance this key value must be set to the port that is used for the named instance.</span></span>

7.  <span data-ttu-id="8d287-129">レジストリキーの\**HKEY \ _LOCAL \ _MACHINE \** "\" のような名前を付けてください \ \ "\" のように、REG \ _SZ として、この値を、ミラーをホストする SQL Server のホスト名に設定します。</span><span class="sxs-lookup"><span data-stu-id="8d287-129">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerName** as REG\_SZ and then set the value to the host name of the SQL Server that hosts the mirror.</span></span>

8.  <span data-ttu-id="8d287-130">レジストリキーの\**HKEY \ _LOCAL \ _MACHINE \ "\** pc \" を DWORD として作成し、その値を、sql Server を実行しているコンピューター上で、ミラーをホストするために使用されているコンピューターの sql 用のポート番号に設定します。</span><span class="sxs-lookup"><span data-stu-id="8d287-130">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerPort** as DWORD and then set the value to the port number that is used for SQL on the computer that is running SQL Server to host the mirror.</span></span> <span data-ttu-id="8d287-131">ミラーの名前付きインスタンスを使用している場合は、このキー値を名前付きインスタンスで使うポート番号に設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-131">If you are using a named instance for the mirror this key value must be set to the port number that is used for the named instance.</span></span>

9.  <span data-ttu-id="8d287-132">App-v 管理 Web サービスを実行しているコンピューターで、ユニバーサルデータリンク (UDL) のテキストファイルを構成します。</span><span class="sxs-lookup"><span data-stu-id="8d287-132">On the computer that is running the App-V Management Web Service, configure the Universal Data Link (UDL) text file.</span></span> <span data-ttu-id="8d287-133">App-v がインストールされているディレクトリで、[ **Sftmgmt** ] をダブルクリックし、次の値を指定します。</span><span class="sxs-lookup"><span data-stu-id="8d287-133">In the directory where App-V is installed, double-click **SftMgmt.udl** and specify the following values:</span></span>

    -   <span data-ttu-id="8d287-134">[**プロバイダー** ] タブで、OLE DB プロバイダーの**SQL Server Native Client 10.0**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d287-134">On the **Provider** tab, select the OLE DB provider **SQL Server Native Client 10.0**.</span></span>

    -   <span data-ttu-id="8d287-135">[**次へ**] をクリックして、[**接続**] タブを選択します。[**サーバー名**] ボックスに、SQL server のサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d287-135">Click **Next** to select the **Connection** tab. In the **Server Name** box, enter the server name of the SQL Server.</span></span> <span data-ttu-id="8d287-136">次に、[ **WINDOWS NT の統合セキュリティを使用する**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8d287-136">Next, select **Use Windows NT Integrated Security**.</span></span> <span data-ttu-id="8d287-137">最後に、リストをクリックして**データベースを選択**し、[app-v データベース名] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8d287-137">Finally, click the list **Select the database**, and then select the App-V database name.</span></span>

    -   <span data-ttu-id="8d287-138">[**すべて**] タブをクリックし、エントリの**フェールオーバーパートナー**を選択します。</span><span class="sxs-lookup"><span data-stu-id="8d287-138">Click the **All** tab, and then select the entry **Failover Partner**.</span></span> <span data-ttu-id="8d287-139">[**値の編集**] をクリックし、フェールオーバー SQL server のサーバー名を入力します。</span><span class="sxs-lookup"><span data-stu-id="8d287-139">Click **Edit Value**, and then enter the server name of the failover SQL Server.</span></span> <span data-ttu-id="8d287-140">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="8d287-140">Click **OK**.</span></span>

    **<span data-ttu-id="8d287-141">重要</span><span class="sxs-lookup"><span data-stu-id="8d287-141">Important</span></span>**  
    <span data-ttu-id="8d287-142">App-v システムでは、Kerberos 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="8d287-142">The App-V system uses Kerberos authentication.</span></span> <span data-ttu-id="8d287-143">そのため、sql Server で Kerberos 認証が有効になっていて、sql Server サービスがドメインユーザーアカウントで実行されている場合は、SPN を手動で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8d287-143">Therefore, when you configure SQL mirroring where Kerberos Authentication is enabled on the SQL Server and the SQL Server service runs under a domain user account, you must manually configure an SPN.</span></span> <span data-ttu-id="8d287-144">詳細については、「[分散環境の App-v 管理を構成](https://go.microsoft.com/fwlink/?LinkId=203186)する」の記事の「SQL サービスでドメインベースのアカウントを使用する場合」を参照してください https://go.microsoft.com/fwlink/?LinkId=203186) 。</span><span class="sxs-lookup"><span data-stu-id="8d287-144">For more information, see “When SQL Service Uses Domain-Based Account” in the article [Configuring App-V Administration for a Distributed Environment](https://go.microsoft.com/fwlink/?LinkId=203186) (https://go.microsoft.com/fwlink/?LinkId=203186).</span></span>



10. <span data-ttu-id="8d287-145">データベースのミラーリングが正常に実行されていることを確認するには、フェールオーバーをテストし、App-v 管理サーバーが正常に機能していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8d287-145">To verify that database mirroring is running correctly, test the failover and confirm that the App-V Management Server continues to function correctly.</span></span>

    **<span data-ttu-id="8d287-146">重要</span><span class="sxs-lookup"><span data-stu-id="8d287-146">Important</span></span>**  
    <span data-ttu-id="8d287-147">操作を続行し、標準のビジネスプラクティスに従って、障害が発生した場合にシステムの操作が中断されないようにします。</span><span class="sxs-lookup"><span data-stu-id="8d287-147">Proceed with care, and follow your standard business practices to ensure that system operations are not disrupted in the event of a failure.</span></span>



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## <span data-ttu-id="8d287-148">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8d287-148">Related topics</span></span>


[<span data-ttu-id="8d287-149">Application Virtualization サーバー管理コンソールで管理タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="8d287-149">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









