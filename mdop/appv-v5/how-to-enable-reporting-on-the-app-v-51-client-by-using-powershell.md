---
title: PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法
description: PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法
author: dansimp
ms.assetid: c4c58be6-cc50-44f6-bf4f-8346fc5d0c0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1d8c0d5e1930020ed1ce354f806f8917a9644e02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814074"
---
# <span data-ttu-id="bc3ca-103">PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="bc3ca-103">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>


<span data-ttu-id="bc3ca-104">レポート用に App-v 5.1 を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-104">Use the following procedure to configure the App-V 5.1 for reporting.</span></span>

**<span data-ttu-id="bc3ca-105">レポート用に App-v 5.1 クライアントを実行しているコンピューターを構成するには</span><span class="sxs-lookup"><span data-stu-id="bc3ca-105">To configure the computer running the App-V 5.1 client for reporting</span></span>**

1. <span data-ttu-id="bc3ca-106">App-v 5.1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-106">Install the App-V 5.1 client.</span></span> <span data-ttu-id="bc3ca-107">クライアントのインストールの詳細については、「 [App-v クライアントを展開する方法」を](how-to-deploy-the-app-v-client-51gb18030.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-107">For more information about installing the client see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md).</span></span>

2. <span data-ttu-id="bc3ca-108">App-v 5.1 クライアントをインストールしたら、 **AppvClientConfiguration** PowerShell を使用して、適切なレポート構成設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-108">After you have installed the App-V 5.1 client, use the **Set-AppvClientConfiguration** PowerShell to configure appropriate Reporting Configuration settings:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="bc3ca-109">設定</span><span class="sxs-lookup"><span data-stu-id="bc3ca-109">Setting</span></span></th>
   <th align="left"><span data-ttu-id="bc3ca-110">説明</span><span class="sxs-lookup"><span data-stu-id="bc3ca-110">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bc3ca-111">ReportingEnabled</span><span class="sxs-lookup"><span data-stu-id="bc3ca-111">ReportingEnabled</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-112">クライアントが情報をレポートサーバーに返すことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-112">Enables the client to return information to a reporting server.</span></span> <span data-ttu-id="bc3ca-113">この設定は、クライアントがクライアントのレポートデータを収集するために必要です。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-113">This setting is required for the client to collect the reporting data on the client.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bc3ca-114">ReportingServerURL</span><span class="sxs-lookup"><span data-stu-id="bc3ca-114">ReportingServerURL</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-115">クライアント情報が保存されている、レポートサーバー上の場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-115">Specifies the location on the reporting server where client information is saved.</span></span> <span data-ttu-id="bc3ca-116">たとえば、http:// &lt; reportingservername &gt; : &lt; reportingservername 番号 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-116">For example, http://&lt;reportingservername&gt;:&lt;reportingportnumber&gt;.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="bc3ca-117">注</span><span class="sxs-lookup"><span data-stu-id="bc3ca-117">Note</span></span></strong><br/><p><span data-ttu-id="bc3ca-118">これは、レポートサーバーのセットアップ時に割り当てられたポート番号です</span><span class="sxs-lookup"><span data-stu-id="bc3ca-118">This is the port number that was assigned during the Reporting Server setup</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bc3ca-119">レポート開始時刻</span><span class="sxs-lookup"><span data-stu-id="bc3ca-119">Reporting Start Time</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-120">これは、クライアントが自動的にデータをサーバーに送信するようにスケジュールするように設定されています。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-120">This is set to schedule the client to automatically send the data to the server.</span></span> <span data-ttu-id="bc3ca-121">この設定は、レポートデータが送信を開始する時間を示します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-121">This setting will indicate the hour at which the reporting data will start to send.</span></span> <span data-ttu-id="bc3ca-122">24時間形式で、0-23 の間には数値がかかります。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-122">It is in the 24 hour format and will take a number between 0-23.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bc3ca-123">ReportingRandomDelay</span><span class="sxs-lookup"><span data-stu-id="bc3ca-123">ReportingRandomDelay</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-124">レポートサーバーに送信されるデータの最大遅延 (分単位) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-124">Specifies the maximum delay (in minutes) for data to be sent to the reporting server.</span></span> <span data-ttu-id="bc3ca-125">スケジュールされたタスクが開始されると、クライアントは0と ReportingRandomDelay の間のランダムな遅延を生成し、データを送信する前に指定された期間待機します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-125">When the scheduled task is started, the client generates a random delay between 0 and ReportingRandomDelay and will wait the specified duration before sending data.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bc3ca-126">ReportingInterval</span><span class="sxs-lookup"><span data-stu-id="bc3ca-126">ReportingInterval</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-127">クライアントがデータをレポートサーバーに再送信するために使用する再試行間隔を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-127">Specifies the retry interval that the client will use to resend data to the reporting server.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="bc3ca-128">Reportingdatacachlimit</span><span class="sxs-lookup"><span data-stu-id="bc3ca-128">ReportingDataCacheLimit</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-129">レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-129">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="bc3ca-130">サイズは、メモリ内のキャッシュに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-130">The size applies to the cache in memory.</span></span> <span data-ttu-id="bc3ca-131">上限に達すると、ログファイルがロールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-131">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="bc3ca-132">Reportingの各の Locksize</span><span class="sxs-lookup"><span data-stu-id="bc3ca-132">ReportingDataBlockSize</span></span></p></td>
   <td align="left"><p><span data-ttu-id="bc3ca-133">レポート情報を格納する XML キャッシュの最大サイズ (MB) を指定します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-133">Specifies the maximum size in megabytes (MB) of the XML cache for storing reporting information.</span></span> <span data-ttu-id="bc3ca-134">サイズは、メモリ内のキャッシュに適用されます。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-134">The size applies to the cache in memory.</span></span> <span data-ttu-id="bc3ca-135">上限に達すると、ログファイルがロールオーバーされます。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-135">When the limit is reached, the log file will roll over.</span></span></p></td>
   </tr>
   </tbody>
   </table>



3. <span data-ttu-id="bc3ca-136">適切な設定が構成された後、App-v 5.1 クライアントを実行しているコンピューターはデータを自動的に収集し、データをレポートサーバーに送ります。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-136">After the appropriate settings have been configured, the computer running the App-V 5.1 client will automatically collect data and will send the data back to the reporting server.</span></span>

   <span data-ttu-id="bc3ca-137">さらに、管理者は、 **AppvClientReport** PowerShell コマンドレットを使用して、手動でオンデマンド方式でデータを戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-137">Additionally, administrators can manually send the data back in an on-demand manner using the **Send-AppvClientReport** PowerShell cmdlet.</span></span>

   <span data-ttu-id="bc3ca-138">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-138">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="bc3ca-139">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-139">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="bc3ca-140">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="bc3ca-140">Got an App-V issue?</span></span>** <span data-ttu-id="bc3ca-141">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="bc3ca-141">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="bc3ca-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bc3ca-142">Related topics</span></span>


[<span data-ttu-id="bc3ca-143">PowerShell を使用した App-V 5.1 の管理</span><span class="sxs-lookup"><span data-stu-id="bc3ca-143">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)









