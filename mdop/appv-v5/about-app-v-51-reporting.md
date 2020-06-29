---
title: App-V 5.1 のレポート機能について
description: App-V 5.1 のレポート機能について
author: dansimp
ms.assetid: 385dca00-7178-4e35-8d86-c58867ebd65c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 827343d538238ca638b57a74ae5d2d74bc6c5968
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814954"
---
# <span data-ttu-id="65799-103">App-V 5.1 のレポート機能について</span><span class="sxs-lookup"><span data-stu-id="65799-103">About App-V 5.1 Reporting</span></span>

<span data-ttu-id="65799-104">Microsoft Application Virtualization (App-v) 5.1 には、App-v 5.1 クライアントを実行しているコンピューターと仮想アプリケーションパッケージの使用状況に関する情報を収集するために役立つ組み込みのレポート機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="65799-104">Microsoft Application Virtualization (App-V) 5.1 includes a built-in reporting feature that helps you collect information about computers running the App-V 5.1 client as well as information about virtual application package usage.</span></span> <span data-ttu-id="65799-105">この情報を使用して、集中化されたデータベースからレポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="65799-105">You can use this information to generate reports from a centralized database.</span></span>

## <a href="" id="---------app-v-5-1-reporting-overview"></a> <span data-ttu-id="65799-106">App-v 5.1 レポートの概要</span><span class="sxs-lookup"><span data-stu-id="65799-106">App-V 5.1 Reporting Overview</span></span>

<span data-ttu-id="65799-107">次の一覧には、App-v 5.1 でレポートするためのエンドツーエンドの上位レベルのワークフローが表示されています。</span><span class="sxs-lookup"><span data-stu-id="65799-107">The following list displays the end–to-end high-level workflow for reporting in App-V 5.1.</span></span>

1. <span data-ttu-id="65799-108">App-v 5.1 レポートサーバーには、次の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="65799-108">The App-V 5.1 Reporting server has the following prerequisites:</span></span>

    - <span data-ttu-id="65799-109">インターネットインフォメーションサービス (IIS) web サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="65799-109">Internet Information Service (IIS) web server role</span></span>

    - <span data-ttu-id="65799-110">Windows 認証の役割 ([ **IIS/セキュリティ**] の下)</span><span class="sxs-lookup"><span data-stu-id="65799-110">Windows Authentication role (under **IIS / Security**)</span></span>

    - <span data-ttu-id="65799-111">Sql Server Reporting Services (SSRS) で SQL Server をインストールして実行する</span><span class="sxs-lookup"><span data-stu-id="65799-111">SQL Server installed and running with SQL Server Reporting Services (SSRS)</span></span>

    <span data-ttu-id="65799-112">SQL Server Reporting Services が実行されていることを確認するには、 `http://localhost/Reports` app-v 5.1 レポートをホストするサーバーの管理者として web ブラウザーで表示します。</span><span class="sxs-lookup"><span data-stu-id="65799-112">To confirm SQL Server Reporting Services is running, view `http://localhost/Reports` in a web browser as administrator on the server that will host App-V 5.1 Reporting.</span></span> <span data-ttu-id="65799-113">SQL Server Reporting Services のホームページが表示されます。</span><span class="sxs-lookup"><span data-stu-id="65799-113">The SQL Server Reporting Services Home page should display.</span></span>

2. <span data-ttu-id="65799-114">App-v 5.1 レポートサーバーと関連データベースをインストールします。</span><span class="sxs-lookup"><span data-stu-id="65799-114">Install the App-V 5.1 reporting server and associated database.</span></span> <span data-ttu-id="65799-115">レポートサーバーのインストールの詳細については、「[レポートサーバーをスタンドアロンコンピューターにインストールしてデータベースに接続する方法」を](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-115">For more information about installing the reporting server see [How to install the Reporting Server on a Standalone Computer and Connect it to the Database](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md).</span></span> <span data-ttu-id="65799-116">App-v 5.1 クライアントを実行しているコンピューターが、レポートサーバーにデータを送信する時刻を構成します。</span><span class="sxs-lookup"><span data-stu-id="65799-116">Configure the time when the computer running the App-V 5.1 client should send data to the reporting server.</span></span>

3. <span data-ttu-id="65799-117">構成マネージャーなどの電子ソフトウェア配布システムを使用してレポートを表示していない場合は、SQL Server Reporting Service でレポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="65799-117">If you are not using an electronic software distribution system such as Configuration Manager to view reports then you can define reports in SQL Server Reporting Service.</span></span> <span data-ttu-id="65799-118">事前に定義された SSRS レポートを[ダウンロードセンター](https://go.microsoft.com/fwlink/?LinkId=397255)からダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="65799-118">Download predefined SSRS Reports from the [Download Center](https://go.microsoft.com/fwlink/?LinkId=397255).</span></span>

    > [!NOTE]
    > <span data-ttu-id="65799-119">Configuration Manager との統合を App-v 5.1 と共に使用している場合、ほとんどのレポートは、App-v 5.1 ではなく構成マネージャーから生成されます。</span><span class="sxs-lookup"><span data-stu-id="65799-119">If you are using the Configuration Manager integration with App-V 5.1, most reports are generated from Configuration Manager rather than from App-V 5.1.</span></span>

4. <span data-ttu-id="65799-120">管理者として App-v 5.1 PowerShell モジュールをインポートした後 `Import-Module AppvClient` 、app-v 5.1 クライアントを有効にします。</span><span class="sxs-lookup"><span data-stu-id="65799-120">After importing the App-V 5.1 PowerShell module using `Import-Module AppvClient` as administrator, enable the App-V 5.1 client.</span></span> <span data-ttu-id="65799-121">このサンプル PowerShell コマンドレットでは、App-v 5.1 レポートを有効にできます。</span><span class="sxs-lookup"><span data-stu-id="65799-121">This sample PowerShell cmdlet enables App-V 5.1 reporting:</span></span>

    ```powershell
    Set-AppvClientConfiguration –reportingserverurl <url>:<port> -reportingenabled 1 – ReportingStartTime <0-23> - ReportingRandomDelay <#min>
    ```

    <span data-ttu-id="65799-122">App-v 5.1 レポートデータをすぐに送信するには、 `Send-AppvClientReport` app-v 5.1 クライアントで実行します。</span><span class="sxs-lookup"><span data-stu-id="65799-122">To immediately send App-V 5.1 report data, run `Send-AppvClientReport` on the App-V 5.1 client.</span></span>

    <span data-ttu-id="65799-123">レポートが有効になっている App-v 5.1 クライアントのインストールの詳細については、「[クライアント構成の設定につい](about-client-configuration-settings51.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-123">For more information about installing the App-V 5.1 client with reporting enabled see [About Client Configuration Settings](about-client-configuration-settings51.md).</span></span> <span data-ttu-id="65799-124">Windows PowerShell を使用して App-v 5.1 のレポートを管理する方法については、「 [Powershell を使用して app-v 5.1 クライアントでレポートを有効にする方法](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-124">To administer App-V 5.1 Reporting with Windows PowerShell, see [How to Enable Reporting on the App-V 5.1 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md).</span></span>

5. <span data-ttu-id="65799-125">レポートサーバーは、App-v 5.1 クライアントからデータを受信した後、データをレポートデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="65799-125">After the reporting server receives the data from the App-V 5.1 client it sends the data to the reporting database.</span></span> <span data-ttu-id="65799-126">データベースがクライアントデータを受信して処理すると、成功応答がレポートサーバーに送信され、その後、通知が App-v 5.1 クライアントに送信されます。</span><span class="sxs-lookup"><span data-stu-id="65799-126">When the database receives and processes the client data, a successful reply is sent to the reporting server and then a notification is sent to the App-V 5.1 client.</span></span>

6. <span data-ttu-id="65799-127">App-v 5.1 クライアントは、正常に完了通知を受け取ると、データキャッシュを空にして容量を節約します。</span><span class="sxs-lookup"><span data-stu-id="65799-127">When the App-V 5.1 client receives the success notification, it empties the data cache to conserve space.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65799-128">既定では、サーバーがデータの受信を確認した後、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="65799-128">By default the cache is cleared after the server confirms receipt of data.</span></span> <span data-ttu-id="65799-129">データキャッシュを保存するようにクライアントを手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="65799-129">You can manually configure the client to save the data cache.</span></span>

<span data-ttu-id="65799-130">App-v 5.1 クライアントデバイスがサーバーからの正常な通知を受け取らない場合、キャッシュにデータが保持され、次に構成される間隔でデータを再送信しようとします。</span><span class="sxs-lookup"><span data-stu-id="65799-130">If the App-V 5.1 client device does not receive a success notification from the server, it retains data in the cache and tries to resend data at the next configured interval.</span></span> <span data-ttu-id="65799-131">クライアントは引き続きデータを収集してキャッシュに追加します。</span><span class="sxs-lookup"><span data-stu-id="65799-131">Clients continue to collect data and add it to the cache.</span></span>

### <a href="" id="-------------app-v-5-1-reporting-server-frequently-asked-questions"></a> <span data-ttu-id="65799-132">App-v 5.1 レポートサーバーについてよく寄せられる質問</span><span class="sxs-lookup"><span data-stu-id="65799-132">App-V 5.1 reporting server frequently asked questions</span></span>

<span data-ttu-id="65799-133">次の表は、App-v 5.1 レポートについてよく寄せられる質問に対する回答を示しています。</span><span class="sxs-lookup"><span data-stu-id="65799-133">The following table displays answers to common questions about App-V 5.1 reporting</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="65799-134">質問</span><span class="sxs-lookup"><span data-stu-id="65799-134">Question</span></span></th>
<th align="left"><span data-ttu-id="65799-135">詳細情報</span><span class="sxs-lookup"><span data-stu-id="65799-135">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="65799-136">レポート情報がレポートデータベースに送信される頻度はどのようなものですか?</span><span class="sxs-lookup"><span data-stu-id="65799-136">What is the frequency that reporting information is sent to the reporting database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="65799-137">頻度は、App-v 5.1 クライアントを実行しているコンピューターでレポートタスクがどのように構成されているかによって異なります。</span><span class="sxs-lookup"><span data-stu-id="65799-137">The frequency depends on how the reporting task is configured on the computer running the App-V 5.1 client.</span></span> <span data-ttu-id="65799-138">レポートデータを送信する頻度と間隔を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-138">You must configure the frequency / interval for sending the reporting data.</span></span> <span data-ttu-id="65799-139">既定では、app-v 5.1 レポートは有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="65799-139">App-V 5.1 Reporting is not enabled by default.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="65799-140">レポートサーバーデータベースにはどのような情報が格納されますか?</span><span class="sxs-lookup"><span data-stu-id="65799-140">What information is stored in the reporting server database?</span></span></p></td>
<td align="left"><p><span data-ttu-id="65799-141">次の一覧は、レポートデータベースに保存されている内容を示しています。</span><span class="sxs-lookup"><span data-stu-id="65799-141">The following list displays what is stored in the reporting database:</span></span></p>
<ul>
<li><p><span data-ttu-id="65799-142">App-v 5.1 クライアントを実行しているコンピューターで実行されているオペレーティングシステム: ホスト名、バージョン、service pack、種類-クライアント/サーバー、プロセッサアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="65799-142">The operating system running on the computer running the App-V 5.1 client: host name, version, service pack, type - client/server, processor architecture.</span></span></p></li>
<li><p><span data-ttu-id="65799-143">App-v 5.1 クライアント情報: バージョン。</span><span class="sxs-lookup"><span data-stu-id="65799-143">App-V 5.1 Client information: version.</span></span></p></li>
<li><p><span data-ttu-id="65799-144">公開されているパッケージの一覧: GUID、バージョン GUID、name。</span><span class="sxs-lookup"><span data-stu-id="65799-144">Published package list: GUID, version GUID, name.</span></span></p></li>
<li><p><span data-ttu-id="65799-145">アプリケーションの使用状況の情報: name、version、streaming server、user (domain\alias)、パッケージバージョン GUID、起動状態と時刻、シャットダウン時間。</span><span class="sxs-lookup"><span data-stu-id="65799-145">Application usage information: name, version, streaming server, user (domain\alias), package version GUID, launch status and time, shutdown time.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="65799-146">レポートサーバーに送信される情報の平均量は何ですか。</span><span class="sxs-lookup"><span data-stu-id="65799-146">What is the average volume of information that is sent to the reporting server?</span></span></p></td>
<td align="left"><p><span data-ttu-id="65799-147">事によりけりです。</span><span class="sxs-lookup"><span data-stu-id="65799-147">It depends.</span></span> <span data-ttu-id="65799-148">次のリストは、レポートサーバーに送信されたデータの3つのセットを示しています。</span><span class="sxs-lookup"><span data-stu-id="65799-148">The following list displays the three sets of the data sent to the reporting server:</span></span></p>
<ol>
<li><p><span data-ttu-id="65799-149">オペレーティングシステムと App-v 5.1 クライアント情報。</span><span class="sxs-lookup"><span data-stu-id="65799-149">Operating system, and App-V 5.1 client information.</span></span> <span data-ttu-id="65799-150">このデータが送信されるたびに、最大150バイト。</span><span class="sxs-lookup"><span data-stu-id="65799-150">~150 Bytes, every time this data is sent.</span></span></p></li>
<li><p><span data-ttu-id="65799-151">公開されたパッケージの一覧。</span><span class="sxs-lookup"><span data-stu-id="65799-151">Published package list.</span></span> <span data-ttu-id="65799-152">30パッケージの場合は ~ 7 KB。</span><span class="sxs-lookup"><span data-stu-id="65799-152">~7 KB for 30 packages.</span></span> <span data-ttu-id="65799-153">これは、パッケージリストが公開更新によって更新された場合にのみ送信されます。この処理はあまり行われません。変更がない場合、この情報は送信されません。</span><span class="sxs-lookup"><span data-stu-id="65799-153">This is sent only when the package list is updated with a publishing refresh, which is done infrequently; if there is no change, this information is not sent.</span></span></p></li>
<li><p><span data-ttu-id="65799-154">仮想アプリケーションの利用状況情報–1イベントあたり 0.25 KB。</span><span class="sxs-lookup"><span data-stu-id="65799-154">Virtual application usage information – about 0.25KB per event.</span></span> <span data-ttu-id="65799-155">情報を送信する前に両方が発生した場合に、開始と終了のカウントが1つのイベントとしてカウントされます。</span><span class="sxs-lookup"><span data-stu-id="65799-155">Opening and closing count as one event if both occur before sending the information.</span></span> <span data-ttu-id="65799-156">スケジュールされたタスクを使って送信する場合、最後に正常にアップロードされたデータのみがサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="65799-156">When sending using a scheduled task, only the data since the last successful upload is sent to the server.</span></span> <span data-ttu-id="65799-157">PowerShell コマンドレットを使用して手動で送信する場合は、次にデータを再送信する必要があるかどうかを制御するオプションの引数があります。その引数は <strong> DeleteOnSuccess です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="65799-157">If sending manually through the PowerShell cmdlet, there is an optional argument that controls if the data needs to be re-sent next time around – that argument is <strong>DeleteOnSuccess</strong>.</span></span></p>
<p></p>
<p><span data-ttu-id="65799-158">たとえば、20個のアプリケーションを開いて閉じ、レポート情報を毎日送信する予定の場合、一般的な1日のトラフィックは 0.15 KB + 20 x 0.25 KB、または 5KB/ユーザーについてのことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="65799-158">So for example, if twenty applications are opened and closed and reporting information is scheduled to be sent daily, the typical daily traffic should be about 0.15KB + 20 x 0.25KB, or about 5KB/user</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="65799-159">レポートのスケジュールを設定できますか?</span><span class="sxs-lookup"><span data-stu-id="65799-159">Can reporting be scheduled?</span></span></p></td>
<td align="left"><p><span data-ttu-id="65799-160">はい、できます。</span><span class="sxs-lookup"><span data-stu-id="65799-160">Yes.</span></span> <span data-ttu-id="65799-161">PowerShell コマンドレット (Send-AppvClientReport) を使って手動でレポートを送信する以外に <strong> </strong> 、タスクを自動的に実行するようにスケジュール設定することができます。</span><span class="sxs-lookup"><span data-stu-id="65799-161">Besides manually sending reporting using PowerShell Cmdlets (<strong>Send-AppvClientReport</strong>), the task can be scheduled so it will happen automatically.</span></span> <span data-ttu-id="65799-162">レポートのスケジュールを設定するには、次の2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="65799-162">There are two ways to schedule the reporting:</span></span></p>
<ol>
<li><p><span data-ttu-id="65799-163">PowerShell コマンドレット AppvClientConfiguration を使用し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="65799-163">Using PowerShell cmdlets - <strong>Set-AppvClientConfiguration</strong>.</span></span> <span data-ttu-id="65799-164">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65799-164">For example:</span></span></p>
<p><span data-ttu-id="65799-165">Set-AppvClientConfiguration-ReportingEnabled 1-Reportingenabled<a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span><span class="sxs-lookup"><span data-stu-id="65799-165">Set-AppvClientConfiguration -ReportingEnabled 1 - ReportingServerURL <a href="http://any.com/appv-reporting" data-raw-source="http://any.com/appv-reporting">http://any.com/appv-reporting</span></span></a></p>
<p></p>
<p><span data-ttu-id="65799-166">クライアント構成の設定の完全な一覧については、「 <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)"> </a> <strong> reportingenabled </strong> 、 <strong> reportingenabled </strong> 、 <strong> reportingdatac、reportingenabled </strong> <strong> locksize </strong> 、 <strong> reportingenabled </strong> 、 <strong> ReportingRandomDelay </strong> 、 <strong> reportingenabled </strong> の各エントリを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-166">For a complete list of client configuration settings see <a href="about-client-configuration-settings51.md" data-raw-source="[About Client Configuration Settings](about-client-configuration-settings51.md)">About Client Configuration Settings</a> and look for the following entries: <strong>ReportingEnabled</strong>, <strong>ReportingServerURL</strong>, <strong>ReportingDataCacheLimit</strong>, <strong>ReportingDataBlockSize</strong>, <strong>ReportingStartTime</strong>, <strong>ReportingRandomDelay</strong>, <strong>ReportingInterval</strong>.</span></span></p>
<p></p></li>
<li><p><span data-ttu-id="65799-167">グループポリシーを使用する。</span><span class="sxs-lookup"><span data-stu-id="65799-167">By using Group Policy.</span></span> <span data-ttu-id="65799-168">ドメインコントローラーを使用して配布されている場合、設定は前の一覧と同じです。</span><span class="sxs-lookup"><span data-stu-id="65799-168">If distributed using the domain controller, the settings are the same as previously listed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="65799-169">注</span><span class="sxs-lookup"><span data-stu-id="65799-169">Note</span></span></strong><br/><p><span data-ttu-id="65799-170">グループポリシー設定は、PowerShell を使用して構成されたローカル設定よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="65799-170">Group Policy settings override local settings configured using PowerShell.</span></span></p>
</div>
<div>
</div></li>
</ol></td>
</tr>
</tbody>
</table>

## <a href="" id="---------app-v-5-1-client-reporting"></a> <span data-ttu-id="65799-171">App-v 5.1 クライアントレポート</span><span class="sxs-lookup"><span data-stu-id="65799-171">App-V 5.1 Client Reporting</span></span>

<span data-ttu-id="65799-172">App-v 5.1 レポートを使用するには、App-v 5.1 クライアントをインストールして構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-172">To use App-V 5.1 reporting you must install and configure the App-V 5.1 client.</span></span> <span data-ttu-id="65799-173">クライアントがインストールされたら、 **AppVClientConfiguration** PowerShell コマンドレットまたは**ADMX テンプレート**を使用してレポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="65799-173">After the client has been installed, use the **Set-AppVClientConfiguration** PowerShell cmdlet or the **ADMX Template** to configure reporting.</span></span> <span data-ttu-id="65799-174">レポート機能のコマンドレットは、次のリンクを使用して使用できます。また、[**レポート**] の前にあります。</span><span class="sxs-lookup"><span data-stu-id="65799-174">The reporting feature cmdlets are available by using the following link and are prefaced by **Reporting**.</span></span> <span data-ttu-id="65799-175">クライアント構成の設定の完全な一覧については、「[クライアント構成の設定につい](about-client-configuration-settings51.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-175">For a complete list of client configuration settings see [About Client Configuration Settings](about-client-configuration-settings51.md).</span></span> <span data-ttu-id="65799-176">次のセクションでは、PowerShell を使用した App-v 5.1 クライアントレポート構成の例を示します。</span><span class="sxs-lookup"><span data-stu-id="65799-176">The following section provides examples of App-V 5.1 client reporting configuration using PowerShell.</span></span>

### <span data-ttu-id="65799-177">PowerShell を使用して App-v クライアントレポートを構成する</span><span class="sxs-lookup"><span data-stu-id="65799-177">Configuring App-V Client reporting using PowerShell</span></span>

<span data-ttu-id="65799-178">次の例は、PowerShell パラメーターを使用して、App-v 5.1 クライアントのレポート機能を構成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="65799-178">The following examples show how PowerShell parameters can configure the reporting features of the App-V 5.1 client.</span></span>

> [!NOTE]
> <span data-ttu-id="65799-179">次の構成タスクは、App-v 5.1 ADMX テンプレートのグループポリシー設定を使用して構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="65799-179">The following configuration task can also be configured using Group Policy settings in the App-V 5.1 ADMX template.</span></span> <span data-ttu-id="65799-180">ADMX テンプレートの使用方法について詳しくは、「 [Admx テンプレートとグループポリシーを使用して app-v 5.1 クライアント構成を変更する方法](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="65799-180">For more information about using the ADMX template, see [How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md).</span></span>

<span data-ttu-id="65799-181">**レポートを有効にし、app-v 5.1 クライアントを実行しているコンピューターでデータ収集を開始するに**は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="65799-181">**To enable reporting and to initiate data collection on the computer running the App-V 5.1 client**:</span></span>

```powershell
Set-AppVClientConfiguration –ReportingEnabled 1
```

<span data-ttu-id="65799-182">**データを特定のレポートサーバーに自動的に送信するようにクライアントを構成するには、次の操作を**行います。</span><span class="sxs-lookup"><span data-stu-id="65799-182">**To configure the client to automatically send data to a specific reporting server**:</span></span>

```powershell
Set-AppVClientConfiguration –ReportingServerURL http://MyReportingServer:MyPort/ -ReportingStartTime 20 -ReportingInterval 1 -ReportingRandomDelay 30 -ReportingInterval 1 -ReportingRandomDelay 30
```

<span data-ttu-id="65799-183">この例では、レポートデータをレポートサーバーの URL に自動的に送信するようにクライアントを構成し **http://MyReportingServer:MyPort/** ます。</span><span class="sxs-lookup"><span data-stu-id="65799-183">This example configures the client to automatically send the reporting data to the reporting server URL **http://MyReportingServer:MyPort/**.</span></span> <span data-ttu-id="65799-184">さらに、レポートデータは、セッションに生成されるランダム遅延に応じて、8:00 と 8:30 PM の間で毎日送信されます。</span><span class="sxs-lookup"><span data-stu-id="65799-184">Additionally, the reporting data will be sent daily between 8:00 and 8:30 PM, depending on the random delay generated for the session.</span></span>

<span data-ttu-id="65799-185">**クライアントのデータキャッシュのサイズを制限するに**は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="65799-185">**To limit the size of the data cache on the client**:</span></span>

```powershell
Set-AppvClientConfiguration –ReportingDataCacheLimit 100
```

<span data-ttu-id="65799-186">アプリ-V 5.1 クライアントを実行しているコンピューター上のレポートキャッシュの最大サイズを 100 MB に構成します。</span><span class="sxs-lookup"><span data-stu-id="65799-186">Configures the maximum size of the reporting cache on the computer running the App-V 5.1 client to 100 MB.</span></span> <span data-ttu-id="65799-187">データをサーバーに送信する前に、キャッシュの制限に達した場合、ログはロールオーバーになり、データは必要に応じて上書きされます。</span><span class="sxs-lookup"><span data-stu-id="65799-187">If the cache limit is reached before the data is sent to the server, then the log rolls over and data will be overwritten as necessary.</span></span>

<span data-ttu-id="65799-188">**クライアントとサーバーの間でネットワーク経由で転送されるデータブロックサイズを構成するには、次の操作を**行います。</span><span class="sxs-lookup"><span data-stu-id="65799-188">**To configure the data block size transmitted across the network between the client and the server**:</span></span>

```powershell
Set-AppvClientConfiguration –ReportingDataBlockSize 10240
```

<span data-ttu-id="65799-189">クライアントが 10240 MB に送信するデータブロックの最大値を指定します。</span><span class="sxs-lookup"><span data-stu-id="65799-189">Specifies the maximum data block that the client sends to 10240 MB.</span></span>

### <span data-ttu-id="65799-190">収集されるデータの種類</span><span class="sxs-lookup"><span data-stu-id="65799-190">Types of data collected</span></span>

<span data-ttu-id="65799-191">次の表は、App-v 5.1 レポートを使って収集できる情報の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="65799-191">The following table displays the types of information you can collect by using App-V 5.1 reporting.</span></span>

|<span data-ttu-id="65799-192">クライアント情報</span><span class="sxs-lookup"><span data-stu-id="65799-192">Client Information</span></span>  |<span data-ttu-id="65799-193">パッケージ情報</span><span class="sxs-lookup"><span data-stu-id="65799-193">Package Information</span></span>  |<span data-ttu-id="65799-194">アプリケーションの使用状況</span><span class="sxs-lookup"><span data-stu-id="65799-194">Application Usage</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="65799-195">ホスト名</span><span class="sxs-lookup"><span data-stu-id="65799-195">Host Name</span></span> |<span data-ttu-id="65799-196">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="65799-196">Package Name</span></span>|<span data-ttu-id="65799-197">開始時刻と終了時刻</span><span class="sxs-lookup"><span data-stu-id="65799-197">Start and End Times</span></span>|
|<span data-ttu-id="65799-198">App-v 5.1 クライアントのバージョン</span><span class="sxs-lookup"><span data-stu-id="65799-198">App-V 5.1 Client Version</span></span> |<span data-ttu-id="65799-199">パッケージバージョン</span><span class="sxs-lookup"><span data-stu-id="65799-199">Package Version</span></span>|<span data-ttu-id="65799-200">実行状態</span><span class="sxs-lookup"><span data-stu-id="65799-200">Run Status</span></span>|
|<span data-ttu-id="65799-201">プロセッサのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="65799-201">Processor Architecture</span></span> |<span data-ttu-id="65799-202">パッケージソース</span><span class="sxs-lookup"><span data-stu-id="65799-202">Package Source</span></span>|<span data-ttu-id="65799-203">シャットダウンの状態</span><span class="sxs-lookup"><span data-stu-id="65799-203">Shutdown State</span></span>|
|<span data-ttu-id="65799-204">オペレーティングシステムのバージョン</span><span class="sxs-lookup"><span data-stu-id="65799-204">Operating System Version</span></span>|<span data-ttu-id="65799-205">キャッシュ割合</span><span class="sxs-lookup"><span data-stu-id="65799-205">Percent Cached</span></span>|<span data-ttu-id="65799-206">アプリケーション名</span><span class="sxs-lookup"><span data-stu-id="65799-206">Application Name</span></span>|
|<span data-ttu-id="65799-207">Service Pack レベル</span><span class="sxs-lookup"><span data-stu-id="65799-207">Service Pack Level</span></span>| |<span data-ttu-id="65799-208">アプリケーションのバージョン</span><span class="sxs-lookup"><span data-stu-id="65799-208">Application Version</span></span>|
|<span data-ttu-id="65799-209">オペレーティングシステムの種類</span><span class="sxs-lookup"><span data-stu-id="65799-209">Operating System Type</span></span>| |<span data-ttu-id="65799-210">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="65799-210">Username</span></span>|
| | |<span data-ttu-id="65799-211">接続グループ</span><span class="sxs-lookup"><span data-stu-id="65799-211">Connection Group</span></span>|

<span data-ttu-id="65799-212">クライアントは、このデータを**xml**形式で収集して保存します。</span><span class="sxs-lookup"><span data-stu-id="65799-212">The client collects and saves this data in an **.xml** format.</span></span> <span data-ttu-id="65799-213">データキャッシュは既定で非表示になっており、XML ファイルを開くには管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="65799-213">The data cache is hidden by default and requires administrator rights to open the XML file.</span></span>

### <span data-ttu-id="65799-214">サーバーにデータを送信する</span><span class="sxs-lookup"><span data-stu-id="65799-214">Sending data to the server</span></span>

<span data-ttu-id="65799-215">App-v 5.1 クライアントを実行しているコンピューターを構成して、指定したレポートサーバーにデータが自動的に送信されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="65799-215">You can configure the computer that is running the App-V 5.1 client to automatically send data to the specified reporting server.</span></span> <span data-ttu-id="65799-216">サーバーを指定するには、 **AppvClientConfiguration**コマンドレットを使用して次の設定を行います。</span><span class="sxs-lookup"><span data-stu-id="65799-216">To specify the server use the **Set-AppvClientConfiguration** cmdlet with the following settings:</span></span>

- <span data-ttu-id="65799-217">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="65799-217">ReportingEnabled</span></span>
- <span data-ttu-id="65799-218">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="65799-218">ReportingServerURL</span></span>
- <span data-ttu-id="65799-219">ReportingStartTime</span><span class="sxs-lookup"><span data-stu-id="65799-219">ReportingStartTime</span></span>
- <span data-ttu-id="65799-220">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="65799-220">ReportingInterval</span></span>
- <span data-ttu-id="65799-221">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="65799-221">ReportingRandomDelay</span></span>

<span data-ttu-id="65799-222">前の設定を構成したら、スケジュールされたタスクを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-222">After you configure the previous settings, you must create a scheduled task.</span></span> <span data-ttu-id="65799-223">スケジュールされたタスクは、 **Reportingserverurl**設定で指定されたサーバーに接続し、転送が開始されます。</span><span class="sxs-lookup"><span data-stu-id="65799-223">The scheduled task will contact the server specified by the **ReportingServerURL** setting and will initiate the transfer.</span></span> <span data-ttu-id="65799-224">スケジュールされた時間外にデータを手動で送信する場合は、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="65799-224">If you want to manually send data outside of the scheduled times, use the following PowerShell cmdlet:</span></span>

```powershell
Send-AppVClientReport –URL http://MyReportingServer:MyPort/ -DeleteOnSuccess
```

<span data-ttu-id="65799-225">レポートサーバーが以前に構成されている場合は、 **– URL**パラメーターを省略できます。</span><span class="sxs-lookup"><span data-stu-id="65799-225">If the reporting server has been previously configured, then the **–URL** parameter can be omitted.</span></span> <span data-ttu-id="65799-226">または、データを別の場所に送信する必要がある場合は、別の URL を指定して、このデータコレクションに対して構成された**Reportingserverurl**をオーバーライドします。</span><span class="sxs-lookup"><span data-stu-id="65799-226">Alternatively, if the data should be sent to an alternate location, specify a different URL to override the configured **ReportingServerURL** for this data collection.</span></span>

<span data-ttu-id="65799-227">**-DeleteOnSuccess**パラメーターは、転送が成功した場合にデータキャッシュをクリアすることを示します。</span><span class="sxs-lookup"><span data-stu-id="65799-227">The **-DeleteOnSuccess** parameter indicates that if the transfer is successful, then the data cache is cleared.</span></span> <span data-ttu-id="65799-228">指定しない場合、キャッシュは消去されません。</span><span class="sxs-lookup"><span data-stu-id="65799-228">If this is not specified, then the cache will not be cleared.</span></span>

### <span data-ttu-id="65799-229">手動のデータ収集</span><span class="sxs-lookup"><span data-stu-id="65799-229">Manual Data Collection</span></span>

<span data-ttu-id="65799-230">また、 **AppVClientReport**コマンドレットを使用して手動でデータを収集することもできます。</span><span class="sxs-lookup"><span data-stu-id="65799-230">You can also use the **Send-AppVClientReport** cmdlet to manually collect data.</span></span> <span data-ttu-id="65799-231">このソリューションは、既存のレポートサーバーの場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="65799-231">This solution is helpful with or without an existing reporting server.</span></span> <span data-ttu-id="65799-232">次のリストは、レポートサーバーを使用してデータを収集するか、またはレポートサーバーを使わないかに関する情報を示します。</span><span class="sxs-lookup"><span data-stu-id="65799-232">The following list displays information about collecting data with or without a reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="65799-233">レポートサーバーでの操作</span><span class="sxs-lookup"><span data-stu-id="65799-233">With a Reporting Server</span></span></th>
<th align="left"><span data-ttu-id="65799-234">レポートサーバーがない場合</span><span class="sxs-lookup"><span data-stu-id="65799-234">Without a Reporting Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="65799-235">既存の App-v 5.1 レポートサーバーがある場合は、カスタマイズされたスケジュールタスクまたはスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="65799-235">If you have an existing App-V 5.1 reporting Server, create a customized scheduled task or script.</span></span> <span data-ttu-id="65799-236">クライアントが指定した場所に、目的の頻度でデータを送信することを指定します。</span><span class="sxs-lookup"><span data-stu-id="65799-236">Specify that the client send the data to the specified location with the desired frequency.</span></span></p></td>
<td align="left"><p><span data-ttu-id="65799-237">既存の App-v 5.1 レポートサーバーがない場合は、– URL パラメーターを使用して、 <strong> </strong> 指定した共有にデータを送信します。</span><span class="sxs-lookup"><span data-stu-id="65799-237">If you do not have an existing App-V 5.1 reporting Server, use the <strong>–URL</strong> parameter to send the data to a specified share.</span></span> <span data-ttu-id="65799-238">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65799-238">For example:</span></span></p>
<p><code>Send-AppVClientReport –URL \Myshare\MyData\ -DeleteOnSuccess</code></p>
<p><span data-ttu-id="65799-239">前の例では、 <strong> &lt; &gt; -URL パラメーターで指定された \MyShare\MyData/強力な場所にレポートデータを送信し <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="65799-239">The previous example will send the reporting data to <strong>\MyShare\MyData&lt;/strong&gt; location indicated by the <strong>-URL</strong> parameter.</span></span> <span data-ttu-id="65799-240">データが送信されると、キャッシュが消去されます。</span><span class="sxs-lookup"><span data-stu-id="65799-240">After the data has been sent, the cache is cleared.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="65799-241">注</span><span class="sxs-lookup"><span data-stu-id="65799-241">Note</span></span></strong><br/><p><span data-ttu-id="65799-242">レポートサーバー以外の場所を指定した場合、データは .xml 形式で送信され、 <strong> </strong> 追加の処理は行われません。</span><span class="sxs-lookup"><span data-stu-id="65799-242">If a location other than the Reporting Server is specified, the data is sent using <strong>.xml</strong> format with no additional processing.</span></span></p>
</div>
<div>
</div></td>
</tr>
</tbody>
</table>

### <span data-ttu-id="65799-243">レポートの作成</span><span class="sxs-lookup"><span data-stu-id="65799-243">Creating Reports</span></span>

<span data-ttu-id="65799-244">App-v 5.1 を使ってレポート情報を取得し、レポートを作成するには、次のいずれかの方法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-244">To retrieve report information and create reports using App-V 5.1 you must use one of the following methods:</span></span>

- <span data-ttu-id="65799-245">Microsoft sql **Server Reporting services (SSRS)** -microsoft Sql Server reporting services は、Microsoft sql server で利用できます。</span><span class="sxs-lookup"><span data-stu-id="65799-245">**Microsoft SQL Server Reporting Services (SSRS)** - Microsoft SQL Server Reporting Services is available with Microsoft SQL Server.</span></span> <span data-ttu-id="65799-246">SSRS は、App-v 5.1 レポートサーバーをインストールするときにはインストールされません。</span><span class="sxs-lookup"><span data-stu-id="65799-246">SSRS is not installed when you install the App-V 5.1 reporting server.</span></span> <span data-ttu-id="65799-247">関連するレポートを生成するには、別途展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-247">It must be deployed separately to generate the associated reports.</span></span>

    <span data-ttu-id="65799-248">[MICROSOFT SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596)の使用に関する詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-248">Use the following link for more information about using [Microsoft SQL Server Reporting Services](https://go.microsoft.com/fwlink/?LinkId=285596).</span></span>

- <span data-ttu-id="65799-249">**スクリプティング**–レポートは、app-v 5.1 レポートデータベースに対して直接スクリプトを使って生成できます。</span><span class="sxs-lookup"><span data-stu-id="65799-249">**Scripting** – You can generate reports by scripting directly against the App-V 5.1 reporting database.</span></span> <span data-ttu-id="65799-250">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="65799-250">For example:</span></span>

    **<span data-ttu-id="65799-251">ストアドプロシージャ:</span><span class="sxs-lookup"><span data-stu-id="65799-251">Stored Procedure:</span></span>**

    <span data-ttu-id="65799-252">**Spprocessclientreport**は、深夜または 12:00 AM で実行するようにスケジュールされています。</span><span class="sxs-lookup"><span data-stu-id="65799-252">**spProcessClientReport** is scheduled to run at midnight or 12:00 AM.</span></span>

    <span data-ttu-id="65799-253">Microsoft SQL Server のスケジュールされたストアドプロシージャを実行するには、Microsoft SQL Server エージェントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-253">To run the Microsoft SQL Server Scheduled Stored procedure, the Microsoft SQL Server Agent must be running.</span></span> <span data-ttu-id="65799-254">Microsoft SQL Server エージェントが**自動起動**に設定されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-254">You should ensure that the Microsoft SQL Server Agent is set to **AutoStart**.</span></span> <span data-ttu-id="65799-255">詳細については、「 [AUTOSTART Sql Server Agent (Sql Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="65799-255">For more information see [Autostart SQL Server Agent (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=287045).</span></span>

    <span data-ttu-id="65799-256">このストアドプロシージャは、App-v 5.1 データベーススクリプトを使用する場合にも作成されます。</span><span class="sxs-lookup"><span data-stu-id="65799-256">The stored procedure is also created when using the App-V 5.1 database scripts.</span></span>

<span data-ttu-id="65799-257">また、レポートサーバーの web サービスの**最大同時接続数**が、可用性に影響を与えることなく、サーバーが管理できる値に設定されていることも確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="65799-257">You should also ensure that the reporting server web service's **Maximum Concurrent Connections** is set to a value that the server will be able to manage without impacting availability.</span></span> <span data-ttu-id="65799-258">**レポート Web サービス**の推奨される**最大の接続**数は**1万**です。</span><span class="sxs-lookup"><span data-stu-id="65799-258">The recommended number of **Maximum Concurrent Connections** for the **Reporting Web Service** is **10,000**.</span></span>

## <span data-ttu-id="65799-259">関連トピック</span><span class="sxs-lookup"><span data-stu-id="65799-259">Related topics</span></span>

[<span data-ttu-id="65799-260">App-V 5.1 Server の展開</span><span class="sxs-lookup"><span data-stu-id="65799-260">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

[<span data-ttu-id="65799-261">スタンドアロン コンピューターにレポート サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="65799-261">How to install the Reporting Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-reporting-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)
