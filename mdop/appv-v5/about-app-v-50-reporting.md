---
title: App-V 5.0 のレポート機能について
description: App-V 5.0 のレポート機能について
author: dansimp
ms.assetid: 27c33dda-f017-41e3-8a78-1b681543ec4f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a29585886aa20233f49c85101cff570a098c69ba
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815024"
---
# <span data-ttu-id="17544-103">App-V 5.0 のレポート機能について</span><span class="sxs-lookup"><span data-stu-id="17544-103">About App-V 5.0 Reporting</span></span>


<span data-ttu-id="17544-104">Microsoft Application Virtualization (App-v) 5.0 には、App-v 5.0 クライアントを実行しているコンピューターと仮想アプリケーションパッケージの使用状況に関する情報を収集するために役立つ組み込みのレポート機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="17544-104">Microsoft Application Virtualization (App-V) 5.0 includes a built-in reporting feature that helps you collect information about computers running the App-V 5.0 client as well as information about virtual application package usage.</span></span> <span data-ttu-id="17544-105">この情報を使用して、集中化されたデータベースからレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="17544-105">You can use this information to generate reports from a centralized database.</span></span>

## <a href="" id="---------app-v-5-0-reporting-overview"></a> <span data-ttu-id="17544-106">App-v 5.0 レポートの概要</span><span class="sxs-lookup"><span data-stu-id="17544-106">App-V 5.0 Reporting Overview</span></span>


<span data-ttu-id="17544-107">次の一覧には、App-v 5.0 でレポートするためのエンドツーエンドの上位レベルのワークフローが表示されています。</span><span class="sxs-lookup"><span data-stu-id="17544-107">The following list displays the end–to-end high-level workflow for reporting in App-V 5.0.</span></span>

1.  <span data-ttu-id="17544-108">Microsoft Application Virtualization (App-v) 5.0 レポートサーバーには、次の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="17544-108">The Microsoft Application Virtualization (App-V) 5.0 Reporting server has the following prerequisites:</span></span>

    -   <span data-ttu-id="17544-109">インターネットインフォメーションサービス (IIS) web サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="17544-109">Internet Information Service (IIS) web server role</span></span>

    -   <span data-ttu-id="17544-110">Windows 認証の役割 ([ **IIS/セキュリティ**] の下)</span><span class="sxs-lookup"><span data-stu-id="17544-110">Windows Authentication role (under **IIS / Security**)</span></span>

    -   <span data-ttu-id="17544-111">Sql Server Reporting Services (SSRS) で SQL Server をインストールして実行する</span><span class="sxs-lookup"><span data-stu-id="17544-111">SQL Server installed and running with SQL Server Reporting Services (SSRS)</span></span>

    <span data-ttu-id="17544-112">SQL Server Reporting Services が実行されていることを確認するには、 `http://localhost/Reports` app-v 5.0 レポートをホストするサーバーの管理者として web ブラウザーで表示します。</span><span class="sxs-lookup"><span data-stu-id="17544-112">To confirm SQL Server Reporting Services is running, view `http://localhost/Reports` in a web browser as administrator on the server that will host App-V 5.0 Reporting.</span></span> <span data-ttu-id="17544-113">SQL Server Reporting Services のホームページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17544-113">The SQL Server Reporting Services Home page should display.</span></span>

2.  <span data-ttu-id="17544-114">App-v 5.0 レポートサーバーと関連データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="17544-114">Install the App-V 5.0 reporting server and associated database.</span></span> <span data-ttu-id="17544-115">レポートサーバーのインストールの詳細については、「[レポートサーバーをスタンドアロンコンピューターにインストールしてデータベースに接続する方法」を](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-115">For more information about installing the reporting server see [How to install the Reporting Server on a Standalone Computer and Connect it to the Database](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md).</span></span> <span data-ttu-id="17544-116">App-v 5.0 クライアントを実行しているコンピューターが、レポートサーバーにデータを送信する時刻を構成します。</span><span class="sxs-lookup"><span data-stu-id="17544-116">Configure the time when the computer running the App-V 5.0 client should send data to the reporting server.</span></span>

3.  <span data-ttu-id="17544-117">構成マネージャーなどの電子ソフトウェア配布システムを使用してレポートを表示していない場合は、SQL Server Reporting Service でレポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="17544-117">If you are not using an electronic software distribution system such as Configuration Manager to view reports then you can define reports in SQL Server Reporting Service.</span></span> <span data-ttu-id="17544-118">定義済みの appvshort レポートをダウンロードセンターからダウンロード <https://go.microsoft.com/fwlink/?LinkId=397255> します。</span><span class="sxs-lookup"><span data-stu-id="17544-118">Download predefined appvshort Reports from the Download Center at <https://go.microsoft.com/fwlink/?LinkId=397255>.</span></span>

    <span data-ttu-id="17544-119">**注** Configuration Manager との統合を App-v 5.0 と共に使用している場合、ほとんどのレポートは、App-v 5.0 ではなく構成マネージャーから生成されます。</span><span class="sxs-lookup"><span data-stu-id="17544-119">**Note** If you are using the Configuration Manager integration with App-V 5.0, most reports are generated from Configuration Manager rather than from App-V 5.0.</span></span>

     

4.  <span data-ttu-id="17544-120">管理者として App-v 5.0 PowerShell モジュールをインポートした後 `Import-Module AppvClient` 、app-v 5.0 クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17544-120">After importing the App-V 5.0 PowerShell module using `Import-Module AppvClient` as administrator, enable the App-V 5.0 client.</span></span> <span data-ttu-id="17544-121">このサンプル PowerShell コマンドレットでは、App-v 5.0 レポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="17544-121">This sample PowerShell cmdlet enables App-V 5.0 reporting:</span></span>

    ``` syntax
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    <span data-ttu-id="17544-122">App-v 5.0 レポートデータをすぐに送信するには、 `Send-AppvClientReport` app-v 5.0 クライアントで実行します。</span><span class="sxs-lookup"><span data-stu-id="17544-122">To immediately send App-V 5.0 report data, run `Send-AppvClientReport` on the App-V 5.0 client.</span></span>

    <span data-ttu-id="17544-123">レポートが有効になっている App-v 5.0 クライアントのインストールの詳細については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-123">For more information about installing the App-V 5.0 client with reporting enabled see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span> <span data-ttu-id="17544-124">Windows PowerShell を使用して App-v 5.0 のレポートを管理する方法については、「 [Powershell を使用して app-v 5.0 クライアントでレポートを有効にする方法](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-124">To administer App-V 5.0 Reporting with Windows PowerShell, see [How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md).</span></span>

5.  <span data-ttu-id="17544-125">レポートサーバーは、App-v 5.0 クライアントからデータを受信した後、データをレポートデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="17544-125">After the reporting server receives the data from the App-V 5.0 client it sends the data to the reporting database.</span></span> <span data-ttu-id="17544-126">データベースがクライアントデータを受信して処理すると、成功応答がレポートサーバーに送信され、その後、通知が App-v 5.0 クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="17544-126">When the database receives and processes the client data, a successful reply is sent to the reporting server and then a notification is sent to the App-V 5.0 client.</span></span>

6.  <span data-ttu-id="17544-127">App-v 5.0 クライアントは、正常に完了通知を受け取ると、データキャッシュを空にして容量を節約します。</span><span class="sxs-lookup"><span data-stu-id="17544-127">When the App-V 5.0 client receives the success notification, it empties the data cache to conserve space.</span></span>

    <span data-ttu-id="17544-128">**注** 既定では、サーバーがデータの受信を確認した後、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="17544-128">**Note** By default the cache is cleared after the server confirms receipt of data.</span></span> <span data-ttu-id="17544-129">データキャッシュを保存するようにクライアントを手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="17544-129">You can manually configure the client to save the data cache.</span></span>

     

~~~
If the App-V 5.0 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval. Clients continue to collect data and add it to the cache.
~~~

### <a href="" id="-------------app-v-5-0-reporting-server-frequently-asked-questions"></a> <span data-ttu-id="17544-130">App-v 5.0 レポートサーバーについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="17544-130">App-V 5.0 reporting server frequently asked questions</span></span>

<span data-ttu-id="17544-131">次の表は、App-v 5.0 レポートについてよく寄せられる質問に対する回答を示しています。</span><span class="sxs-lookup"><span data-stu-id="17544-131">The following table displays answers to common questions about App-V 5.0 reporting</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17544-132">質問</span><span class="sxs-lookup"><span data-stu-id="17544-132">Question</span></span></th>
<th align="left"><span data-ttu-id="17544-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="17544-133">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-134">レポート情報がレポートデータベースに送信される頻度はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="17544-134">What is the frequency that reporting information is sent to the reporting database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-135">頻度は、App-v 5.0 クライアントを実行しているコンピューターでレポートタスクがどのように構成されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="17544-135">The frequency depends on how the reporting task is configured on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="17544-136">レポートデータを送信する頻度と間隔を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-136">You must configure the frequency / interval for sending the reporting data.</span></span> <span data-ttu-id="17544-137">既定では、app-v 5.0 レポートは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="17544-137">App-V 5.0 Reporting is not enabled by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17544-138">レポートサーバーデータベースにはどのような情報が格納されますか?</span><span class="sxs-lookup"><span data-stu-id="17544-138">What information is stored in the reporting server database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-139">次の一覧は、レポートデータベースに保存されている内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="17544-139">The following list displays what is stored in the reporting database:</span></span></p>
<ul>
<li><p><span data-ttu-id="17544-140">App-v 5.0 クライアントを実行しているコンピューターで実行されているオペレーティングシステム: ホスト名、バージョン、service pack、種類-クライアント/サーバー、プロセッサアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="17544-140">The operating system running on the computer running the App-V 5.0 client: host name, version, service pack, type - client/server, processor architecture.</span></span></p></li>
<li><p><span data-ttu-id="17544-141">App-v 5.0 クライアント情報: バージョン。</span><span class="sxs-lookup"><span data-stu-id="17544-141">App-V 5.0 Client information: version.</span></span></p></li>
<li><p><span data-ttu-id="17544-142">公開されているパッケージの一覧: GUID、バージョン GUID、name。</span><span class="sxs-lookup"><span data-stu-id="17544-142">Published package list: GUID, version GUID, name.</span></span></p></li>
<li><p><span data-ttu-id="17544-143">アプリケーションの使用状況の情報: name、version、streaming server、user (domain\alias)、パッケージバージョン GUID、起動状態と時刻、シャットダウン時間。</span><span class="sxs-lookup"><span data-stu-id="17544-143">Application usage information: name, version, streaming server, user (domain\alias), package version GUID, launch status and time, shutdown time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-144">レポートサーバーに送信される情報の平均量は何ですか。</span><span class="sxs-lookup"><span data-stu-id="17544-144">What is the average volume of information that is sent to the reporting server?</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-145">事によりけりです。</span><span class="sxs-lookup"><span data-stu-id="17544-145">It depends.</span></span> <span data-ttu-id="17544-146">次のリストは、レポートサーバーに送信されたデータの3つのセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="17544-146">The following list displays the three sets of the data sent to the reporting server:</span></span></p>
<ol>
<li><p><span data-ttu-id="17544-147">オペレーティングシステムと App-v 5.0 クライアント情報。</span><span class="sxs-lookup"><span data-stu-id="17544-147">Operating system, and App-V 5.0 client information.</span></span> <span data-ttu-id="17544-148">このデータが送信されるたびに、最大150バイト。</span><span class="sxs-lookup"><span data-stu-id="17544-148">~150 Bytes, every time this data is sent.</span></span></p></li>
<li><p><span data-ttu-id="17544-149">公開されたパッケージの一覧。</span><span class="sxs-lookup"><span data-stu-id="17544-149">Published package list.</span></span> <span data-ttu-id="17544-150">30パッケージの場合は ~ 7 KB。</span><span class="sxs-lookup"><span data-stu-id="17544-150">~7 KB for 30 packages.</span></span> <span data-ttu-id="17544-151">これは、パッケージリストが公開更新によって更新された場合にのみ送信されます。この処理はあまり行われません。変更がない場合、この情報は送信されません。</span><span class="sxs-lookup"><span data-stu-id="17544-151">This is sent only when the package list is updated with a publishing refresh, which is done infrequently; if there is no change, this information is not sent.</span></span></p></li>
<li><p><span data-ttu-id="17544-152">仮想アプリケーションの利用状況情報–1イベントあたり 0.25 KB。</span><span class="sxs-lookup"><span data-stu-id="17544-152">Virtual application usage information – about 0.25KB per event.</span></span> <span data-ttu-id="17544-153">情報を送信する前に両方が発生した場合に、開始と終了のカウントが1つのイベントとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="17544-153">Opening and closing count as one event if both occur before sending the information.</span></span> <span data-ttu-id="17544-154">スケジュールされたタスクを使って送信する場合、最後に正常にアップロードされたデータのみがサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="17544-154">When sending using a scheduled task, only the data since the last successful upload is sent to the server.</span></span> <span data-ttu-id="17544-155">PowerShell コマンドレットを使用して手動で送信する場合は、次にデータを再送信する必要があるかどうかを制御するオプションの引数があります。その引数は <strong> DeleteOnSuccess です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="17544-155">If sending manually through the PowerShell cmdlet, there is an optional argument that controls if the data needs to be re-sent next time around – that argument is <strong>DeleteOnSuccess</strong>.</span></span></p>
<p></p>
<p><span data-ttu-id="17544-156">たとえば、20個のアプリケーションを開いて閉じ、レポート情報を毎日送信する予定の場合、一般的な1日のトラフィックは 0.15 KB + 20 x 0.25 KB、または 5KB/ユーザーについてのことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="17544-156">So for example, if twenty applications are opened and closed and reporting information is scheduled to be sent daily, the typical daily traffic should be about 0.15KB + 20 x 0.25KB, or about 5KB/user</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17544-157">レポートのスケジュールを設定できますか?</span><span class="sxs-lookup"><span data-stu-id="17544-157">Can reporting be scheduled?</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-158">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="17544-158">Yes.</span></span> <span data-ttu-id="17544-159">PowerShell コマンドレット (Send-AppvClientReport) を使って手動でレポートを送信する以外に <strong> </strong> 、タスクを自動的に実行するようにスケジュール設定することができます。</span><span class="sxs-lookup"><span data-stu-id="17544-159">Besides manually sending reporting using PowerShell Cmdlets (<strong>Send-AppvClientReport</strong>), the task can be scheduled so it will happen automatically.</span></span> <span data-ttu-id="17544-160">レポートのスケジュールを設定するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="17544-160">There are two ways to schedule the reporting:</span></span></p>
<ol>
<li><p><span data-ttu-id="17544-161">PowerShell コマンドレット AppvClientConfiguration を使用し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17544-161">Using PowerShell cmdlets - <strong>Set-AppvClientConfiguration</strong>.</span></span> <span data-ttu-id="17544-162">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="17544-162">For example:</span></span></p>
<p><span data-ttu-id="17544-163">Set-AppvClientConfiguration-ReportingEnabled 1-Reportingenabled<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span><span class="sxs-lookup"><span data-stu-id="17544-163">Set-AppvClientConfiguration -ReportingEnabled 1 - ReportingServerURL <a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span></span></a></p>
<p></p>
<p><span data-ttu-id="17544-164">クライアント構成の設定の完全な一覧については、「 <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)"> </a> <strong> reportingenabled </strong> 、 <strong> reportingenabled </strong> 、 <strong> reportingdatac、reportingenabled </strong> <strong> locksize </strong> 、 <strong> reportingenabled </strong> 、 <strong> ReportingRandomDelay </strong> 、 <strong> reportingenabled </strong> の各エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-164">For a complete list of client configuration settings see <a href="about-client-configuration-settings.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings.md)">About Client Configuration Settings</a> and look for the following entries: <strong>ReportingEnabled</strong>, <strong>ReportingServerURL</strong>, <strong>ReportingDataCacheLimit</strong>, <strong>ReportingDataBlockSize</strong>, <strong>ReportingStartTime</strong>, <strong>ReportingRandomDelay</strong>, <strong>ReportingInterval</strong>.</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="17544-165">グループポリシーを使用する。</span><span class="sxs-lookup"><span data-stu-id="17544-165">By using Group Policy.</span></span> <span data-ttu-id="17544-166">ドメインコントローラーを使用して配布されている場合、設定は前の一覧と同じです。</span><span class="sxs-lookup"><span data-stu-id="17544-166">If distributed using the domain controller, the settings are the same as previously listed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="17544-167">注</span><span class="sxs-lookup"><span data-stu-id="17544-167">Note</span></span></strong><br/><p><span data-ttu-id="17544-168">グループポリシー設定は、PowerShell を使用して構成されたローカル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="17544-168">Group Policy settings override local settings configured using PowerShell.</span></span></p>
</div>
<div>

</div></li>
</ol></td>
</tr>
</tbody>
</table>
 


## <a href="" id="---------app-v-5-0-client-reporting"></a> <span data-ttu-id="17544-169">App-v 5.0 クライアントレポート</span><span class="sxs-lookup"><span data-stu-id="17544-169">App-V 5.0 Client Reporting</span></span>


<span data-ttu-id="17544-170">App-v 5.0 レポートを使用するには、App-v 5.0 クライアントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-170">To use App-V 5.0 reporting you must install and configure the App-V 5.0 client.</span></span> <span data-ttu-id="17544-171">クライアントがインストールされたら、 **AppVClientConfiguration** PowerShell コマンドレットまたは**ADMX テンプレート**を使用してレポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="17544-171">After the client has been installed, use the **Set-AppVClientConfiguration** PowerShell cmdlet or the **ADMX Template** to configure reporting.</span></span> <span data-ttu-id="17544-172">レポート機能のコマンドレットは、次のリンクを使用して使用できます。また、[**レポート**] の前にあります。</span><span class="sxs-lookup"><span data-stu-id="17544-172">The reporting feature cmdlets are available by using the following link and are prefaced by **Reporting**.</span></span> <span data-ttu-id="17544-173">クライアント構成の設定の完全な一覧については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-173">For a complete list of client configuration settings see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span> <span data-ttu-id="17544-174">次のセクションでは、PowerShell を使用した App-v 5.0 クライアントレポート構成の例を示します。</span><span class="sxs-lookup"><span data-stu-id="17544-174">The following section provides examples of App-V 5.0 client reporting configuration using PowerShell.</span></span>

### <span data-ttu-id="17544-175">PowerShell を使用して App-v クライアントレポートを構成する</span><span class="sxs-lookup"><span data-stu-id="17544-175">Configuring App-V Client reporting using PowerShell</span></span>

<span data-ttu-id="17544-176">次の例は、PowerShell パラメーターを使用して、App-v 5.0 クライアントのレポート機能を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="17544-176">The following examples show how PowerShell parameters can configure the reporting features of the App-V 5.0 client.</span></span>

**<span data-ttu-id="17544-177">注</span><span class="sxs-lookup"><span data-stu-id="17544-177">Note</span></span>**  
<span data-ttu-id="17544-178">次の構成タスクは、App-v 5.0 ADMX テンプレートのグループポリシー設定を使用して構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="17544-178">The following configuration task can also be configured using Group Policy settings in the App-V 5.0 ADMX template.</span></span> <span data-ttu-id="17544-179">ADMX テンプレートの使用方法について詳しくは、「 [Admx テンプレートとグループポリシーを使用して app-v 5.0 クライアント構成を変更する方法](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="17544-179">For more information about using the ADMX template, see [How to Modify App-V 5.0 Client Configuration Using the ADMX Template and Group Policy](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md).</span></span>
 


<span data-ttu-id="17544-180">**レポートを有効にし、app-v 5.0 クライアントを実行しているコンピューターでデータ収集を開始するに**は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17544-180">**To enable reporting and to initiate data collection on the computer running the App-V 5.0 client**:</span></span>

`Set-AppVClientConfiguration –ReportingEnabled 1`

<span data-ttu-id="17544-181">**データを特定のレポートサーバーに自動的に送信するようにクライアントを構成するには、次の操作を**行います。</span><span class="sxs-lookup"><span data-stu-id="17544-181">**To configure the client to automatically send data to a specific reporting server**:</span></span>

``` syntax
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30
```

`-ReportingInterval 1 -ReportingRandomDelay 30`

<span data-ttu-id="17544-182">この例では、レポートデータをレポートサーバーの URL に自動的に送信するようにクライアントを構成し <strong> http://MyReportingServer:MyPort/ </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17544-182">This example configures the client to automatically send the reporting data to the reporting server URL <strong>http://MyReportingServer:MyPort/</strong>.</span></span> <span data-ttu-id="17544-183">さらに、レポートデータは、セッションに生成されるランダム遅延に応じて、8:00 と 8:30 PM の間で毎日送信されます。</span><span class="sxs-lookup"><span data-stu-id="17544-183">Additionally, the reporting data will be sent daily between 8:00 and 8:30 PM, depending on the random delay generated for the session.</span></span>

<span data-ttu-id="17544-184">**クライアントのデータキャッシュのサイズを制限するに**は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="17544-184">**To limit the size of the data cache on the client**:</span></span>

`Set-AppvClientConfiguration –ReportingDataCacheLimit 100`

<span data-ttu-id="17544-185">アプリ-V 5.0 クライアントを実行しているコンピューター上のレポートキャッシュの最大サイズを 100 MB に構成します。</span><span class="sxs-lookup"><span data-stu-id="17544-185">Configures the maximum size of the reporting cache on the computer running the App-V 5.0 client to 100 MB.</span></span> <span data-ttu-id="17544-186">データをサーバーに送信する前に、キャッシュの制限に達した場合、ログはロールオーバーになり、データは必要に応じて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="17544-186">If the cache limit is reached before the data is sent to the server, then the log rolls over and data will be overwritten as necessary.</span></span>

<span data-ttu-id="17544-187">**クライアントとサーバーの間でネットワーク経由で転送されるデータブロックサイズを構成するには、次の操作を**行います。</span><span class="sxs-lookup"><span data-stu-id="17544-187">**To configure the data block size transmitted across the network between the client and the server**:</span></span>

`Set-AppvClientConfiguration –ReportingDataBlockSize 10240`

<span data-ttu-id="17544-188">クライアントが 10240 MB に送信するデータブロックの最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="17544-188">Specifies the maximum data block that the client sends to 10240 MB.</span></span>

### <span data-ttu-id="17544-189">収集されるデータの種類</span><span class="sxs-lookup"><span data-stu-id="17544-189">Types of data collected</span></span>

<span data-ttu-id="17544-190">次の表は、App-v 5.0 レポートを使って収集できる情報の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="17544-190">The following table displays the types of information you can collect by using App-V 5.0 reporting.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17544-191">クライアント情報</span><span class="sxs-lookup"><span data-stu-id="17544-191">Client Information</span></span></th>
<th align="left"><span data-ttu-id="17544-192">パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="17544-192">Package Information</span></span></th>
<th align="left"><span data-ttu-id="17544-193">アプリケーションの使用状況</span><span class="sxs-lookup"><span data-stu-id="17544-193">Application Usage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-194">ホスト名</span><span class="sxs-lookup"><span data-stu-id="17544-194">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-195">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="17544-195">Package Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-196">開始時刻と終了時刻</span><span class="sxs-lookup"><span data-stu-id="17544-196">Start and End Times</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17544-197">App-v 5.0 クライアントのバージョン</span><span class="sxs-lookup"><span data-stu-id="17544-197">App-V 5.0 Client Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-198">パッケージバージョン</span><span class="sxs-lookup"><span data-stu-id="17544-198">Package Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-199">実行状態</span><span class="sxs-lookup"><span data-stu-id="17544-199">Run Status</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-200">プロセッサのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="17544-200">Processor Architecture</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-201">パッケージソース</span><span class="sxs-lookup"><span data-stu-id="17544-201">Package Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-202">シャットダウンの状態</span><span class="sxs-lookup"><span data-stu-id="17544-202">Shutdown State</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17544-203">オペレーティングシステムのバージョン</span><span class="sxs-lookup"><span data-stu-id="17544-203">Operating System Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-204">キャッシュ割合</span><span class="sxs-lookup"><span data-stu-id="17544-204">Percent Cached</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-205">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="17544-205">Application Name</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-206">Service Pack レベル</span><span class="sxs-lookup"><span data-stu-id="17544-206">Service Pack Level</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="17544-207">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="17544-207">Application Version</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17544-208">オペレーティングシステムの種類</span><span class="sxs-lookup"><span data-stu-id="17544-208">Operating System Type</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="17544-209">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="17544-209">Username</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="17544-210">接続グループ</span><span class="sxs-lookup"><span data-stu-id="17544-210">Connection Group</span></span></p></td>
</tr>
</tbody>
</table>
 


<span data-ttu-id="17544-211">クライアントは、このデータを**xml**形式で収集して保存します。</span><span class="sxs-lookup"><span data-stu-id="17544-211">The client collects and saves this data in an **.xml** format.</span></span> <span data-ttu-id="17544-212">データキャッシュは既定で非表示になっており、XML ファイルを開くには管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="17544-212">The data cache is hidden by default and requires administrator rights to open the XML file.</span></span>

### <span data-ttu-id="17544-213">サーバーにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="17544-213">Sending data to the server</span></span>

<span data-ttu-id="17544-214">App-v 5.0 クライアントを実行しているコンピューターを構成して、指定したレポートサーバーにデータが自動的に送信されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="17544-214">You can configure the computer that is running the App-V 5.0 client to automatically send data to the specified reporting server.</span></span> <span data-ttu-id="17544-215">サーバーを指定するには、 **AppvClientConfiguration**コマンドレットを使用して次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="17544-215">To specify the server use the **Set-AppvClientConfiguration** cmdlet with the following settings:</span></span>

-   <span data-ttu-id="17544-216">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="17544-216">ReportingEnabled</span></span>

-   <span data-ttu-id="17544-217">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="17544-217">ReportingServerURL</span></span>

-   <span data-ttu-id="17544-218">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="17544-218">ReportingStartTime</span></span>

-   <span data-ttu-id="17544-219">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="17544-219">ReportingInterval</span></span>

-   <span data-ttu-id="17544-220">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="17544-220">ReportingRandomDelay</span></span>

<span data-ttu-id="17544-221">前の設定を構成したら、スケジュールされたタスクを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-221">After you configure the previous settings, you must create a scheduled task.</span></span> <span data-ttu-id="17544-222">スケジュールされたタスクは、 **Reportingserverurl**設定で指定されたサーバーに接続し、転送が開始されます。</span><span class="sxs-lookup"><span data-stu-id="17544-222">The scheduled task will contact the server specified by the **ReportingServerURL** setting and will initiate the transfer.</span></span> <span data-ttu-id="17544-223">スケジュールされた時間外にデータを手動で送信する場合は、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="17544-223">If you want to manually send data outside of the scheduled times, use the following PowerShell cmdlet:</span></span>

`Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess`

<span data-ttu-id="17544-224">レポートサーバーが以前に構成されている場合は、 **– URL**パラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="17544-224">If the reporting server has been previously configured, then the **–URL** parameter can be omitted.</span></span> <span data-ttu-id="17544-225">または、データを別の場所に送信する必要がある場合は、別の URL を指定して、このデータコレクションに対して構成された**Reportingserverurl**をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="17544-225">Alternatively, if the data should be sent to an alternate location, specify a different URL to override the configured **ReportingServerURL** for this data collection.</span></span>

<span data-ttu-id="17544-226">**-DeleteOnSuccess**パラメーターは、転送が成功した場合にデータキャッシュをクリアすることを示します。</span><span class="sxs-lookup"><span data-stu-id="17544-226">The **-DeleteOnSuccess** parameter indicates that if the transfer is successful, then the data cache is cleared.</span></span> <span data-ttu-id="17544-227">指定しない場合、キャッシュは消去されません。</span><span class="sxs-lookup"><span data-stu-id="17544-227">If this is not specified, then the cache will not be cleared.</span></span>

### <span data-ttu-id="17544-228">手動のデータ収集</span><span class="sxs-lookup"><span data-stu-id="17544-228">Manual Data Collection</span></span>

<span data-ttu-id="17544-229">また、 **AppVClientReport**コマンドレットを使用して手動でデータを収集することもできます。</span><span class="sxs-lookup"><span data-stu-id="17544-229">You can also use the **Send-AppVClientReport** cmdlet to manually collect data.</span></span> <span data-ttu-id="17544-230">このソリューションは、既存のレポートサーバーの場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="17544-230">This solution is helpful with or without an existing reporting server.</span></span> <span data-ttu-id="17544-231">次のリストは、レポートサーバーを使用してデータを収集するか、またはレポートサーバーを使わないかに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="17544-231">The following list displays information about collecting data with or without a reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17544-232">レポートサーバーでの操作</span><span class="sxs-lookup"><span data-stu-id="17544-232">With a Reporting Server</span></span></th>
<th align="left"><span data-ttu-id="17544-233">レポートサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="17544-233">Without a Reporting Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17544-234">既存の App-v 5.0 レポートサーバーがある場合は、カスタマイズされたスケジュールタスクまたはスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="17544-234">If you have an existing App-V 5.0 reporting Server, create a customized scheduled task or script.</span></span> <span data-ttu-id="17544-235">クライアントが指定した場所に、目的の頻度でデータを送信することを指定します。</span><span class="sxs-lookup"><span data-stu-id="17544-235">Specify that the client send the data to the specified location with the desired frequency.</span></span></p></td>
<td align="left"><p><span data-ttu-id="17544-236">既存の App-v 5.0 レポートサーバーがない場合は、– URL パラメーターを使用して、 <strong> </strong> 指定した共有にデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="17544-236">If you do not have an existing App-V 5.0 reporting Server, use the <strong>–URL</strong> parameter to send the data to a specified share.</span></span> <span data-ttu-id="17544-237">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="17544-237">For example:</span></span></p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p><span data-ttu-id="17544-238">前の例では、 <strong> &lt; &gt; -URL パラメーターで指定された \MyShare\MyData/強力な場所にレポートデータを送信し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17544-238">The previous example will send the reporting data to <strong>\MyShare\MyData&lt;/strong&gt; location indicated by the <strong>-URL</strong> parameter.</span></span> <span data-ttu-id="17544-239">データが送信されると、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="17544-239">After the data has been sent, the cache is cleared.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="17544-240">注</span><span class="sxs-lookup"><span data-stu-id="17544-240">Note</span></span></strong><br/><p><span data-ttu-id="17544-241">レポートサーバー以外の場所を指定した場合、データは .xml 形式で送信され、 <strong> </strong> 追加の処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="17544-241">If a location other than the Reporting Server is specified, the data is sent using <strong>.xml</strong> format with no additional processing.</span></span></p>
</div>
<div>
 
</div></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="17544-242">レポートの作成</span><span class="sxs-lookup"><span data-stu-id="17544-242">Creating Reports</span></span>

<span data-ttu-id="17544-243">App-v 5.0 を使ってレポート情報を取得し、レポートを作成するには、次のいずれかの方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-243">To retrieve report information and create reports using App-V 5.0 you must use one of the following methods:</span></span>

-   <span data-ttu-id="17544-244">Microsoft sql **Server Reporting services (SSRS)** -microsoft Sql Server reporting services は、Microsoft sql server で利用できます。</span><span class="sxs-lookup"><span data-stu-id="17544-244">**Microsoft SQL Server Reporting Services (SSRS)** - Microsoft SQL Server Reporting Services is available with Microsoft SQL Server.</span></span> <span data-ttu-id="17544-245">SSRS は、App-v 5.0 レポートサーバーをインストールするときにはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="17544-245">SSRS is not installed when you install the App-V 5.0 reporting server.</span></span> <span data-ttu-id="17544-246">関連するレポートを生成するには、別途展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-246">It must be deployed separately to generate the associated reports.</span></span>

    <span data-ttu-id="17544-247">[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)の使用に関する詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-247">Use the following link for more information about using [Microsoft SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596).</span></span>

-   <span data-ttu-id="17544-248">**スクリプティング**–レポートは、app-v 5.0 レポートデータベースに対して直接スクリプトを使って生成できます。</span><span class="sxs-lookup"><span data-stu-id="17544-248">**Scripting** – You can generate reports by scripting directly against the App-V 5.0 reporting database.</span></span> <span data-ttu-id="17544-249">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="17544-249">For example:</span></span>

    **<span data-ttu-id="17544-250">ストアドプロシージャ:</span><span class="sxs-lookup"><span data-stu-id="17544-250">Stored Procedure:</span></span>**

    <span data-ttu-id="17544-251">**Spprocessclientreport**は、深夜または 12:00 AM で実行するようにスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="17544-251">**spProcessClientReport** is scheduled to run at midnight or 12:00 AM.</span></span>

    <span data-ttu-id="17544-252">Microsoft SQL Server のスケジュールされたストアドプロシージャを実行するには、Microsoft SQL Server エージェントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-252">To run the Microsoft SQL Server Scheduled Stored procedure, the Microsoft SQL Server Agent must be running.</span></span> <span data-ttu-id="17544-253">Microsoft SQL Server エージェントが**自動起動**に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-253">You should ensure that the Microsoft SQL Server Agent is set to **AutoStart**.</span></span> <span data-ttu-id="17544-254">詳細については、「 [AUTOSTART Sql Server Agent (Sql Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17544-254">For more information see [Autostart SQL Server Agent (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045).</span></span>

    <span data-ttu-id="17544-255">このストアドプロシージャは、App-v 5.0 データベーススクリプトを使用する場合にも作成されます。</span><span class="sxs-lookup"><span data-stu-id="17544-255">The stored procedure is also created when using the App-V 5.0 database scripts.</span></span>

<span data-ttu-id="17544-256">また、レポートサーバーの web サービスの**最大同時接続数**が、可用性に影響を与えることなく、サーバーが管理できる値に設定されていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17544-256">You should also ensure that the reporting server web service’s **Maximum Concurrent Connections** is set to a value that the server will be able to manage without impacting availability.</span></span> <span data-ttu-id="17544-257">**レポート Web サービス**の推奨される**最大の接続**数は**1万**です。</span><span class="sxs-lookup"><span data-stu-id="17544-257">The recommended number of **Maximum Concurrent Connections** for the **Reporting Web Service** is **10,000**.</span></span>






## <span data-ttu-id="17544-258">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17544-258">Related topics</span></span>


[<span data-ttu-id="17544-259">App-V 5.0 Server の展開</span><span class="sxs-lookup"><span data-stu-id="17544-259">Deploying the App-V 5.0 Server</span></span>](deploying-the-app-v-50-server.md)

[<span data-ttu-id="17544-260">スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="17544-260">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database.md)

 

 





