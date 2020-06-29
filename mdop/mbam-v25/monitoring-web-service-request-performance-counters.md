---
title: Web サービス要求のパフォーマンス カウンターの監視
description: Web サービス要求のパフォーマンス カウンターの監視
author: dansimp
ms.assetid: bdb812a1-465a-4098-b4c0-cb99890d1b0d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2db96e3375562b48d289ea5a21dc7e89b800d1ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823877"
---
# <span data-ttu-id="c3175-103">Web サービス要求のパフォーマンス カウンターの監視</span><span class="sxs-lookup"><span data-stu-id="c3175-103">Monitoring Web Service Request Performance Counters</span></span>


<span data-ttu-id="c3175-104">Microsoft BitLocker の管理と監視 (MBAM) では、次の web サービスに送信された要求のパフォーマンスを記録するパフォーマンスカウンターが提供されています。</span><span class="sxs-lookup"><span data-stu-id="c3175-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides performance counters that record the performance of requests that are sent to the following web services:</span></span>

-   <span data-ttu-id="c3175-105">**Statusreportingservice. svc** –コンプライアンスの状態の要求を受信するサービス</span><span class="sxs-lookup"><span data-stu-id="c3175-105">**StatusReportingService.svc** – service that receives requests for compliance status</span></span>

-   <span data-ttu-id="c3175-106">**Coreservice .svc** –キーの回復試行の要求を受信するサービス</span><span class="sxs-lookup"><span data-stu-id="c3175-106">**CoreService.svc** – service that receives requests for key recovery attempts</span></span>

## <span data-ttu-id="c3175-107">MBAM が提供するパフォーマンスカウンター</span><span class="sxs-lookup"><span data-stu-id="c3175-107">Performance counters that MBAM provides</span></span>


<span data-ttu-id="c3175-108">MBAM には、StatusReportingService と CoreService web サービスによって実装されるパブリックメソッドごとに、次のパフォーマンスカウンターが用意されています。</span><span class="sxs-lookup"><span data-stu-id="c3175-108">MBAM provides the following performance counters for each of the public methods that is implemented by its StatusReportingService and CoreService web services:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c3175-109">パフォーマンスカウンターの種類</span><span class="sxs-lookup"><span data-stu-id="c3175-109">Type of performance counter</span></span></th>
<th align="left"><span data-ttu-id="c3175-110">説明</span><span class="sxs-lookup"><span data-stu-id="c3175-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3175-111">要求の合計数</span><span class="sxs-lookup"><span data-stu-id="c3175-111">Total number of requests</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3175-112">サーバーの起動時または再起動時にゼロから始まるインクリメントカウントを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3175-112">Provides an incrementing count that starts from zero when the server is started or restarted.</span></span></p>
<p><span data-ttu-id="c3175-113">システムアクティビティの全体的なビューを提供します。</span><span class="sxs-lookup"><span data-stu-id="c3175-113">Provides an overall view of system activity.</span></span> <span data-ttu-id="c3175-114">自動ツールで監視して、サーバーの正常性を確保し、カウンターが指定された期間にわたって継続的にインクリメントされることを検証することができます。</span><span class="sxs-lookup"><span data-stu-id="c3175-114">Can be monitored by automated tools to ensure the health of the server and to validate that the counter continually increments over a specified period of time.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3175-115">1秒あたりの要求数</span><span class="sxs-lookup"><span data-stu-id="c3175-115">Requests per second</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3175-116">Mbam クライアントベースでサポートされている MBAM サーバーの現在のスループットを示します。</span><span class="sxs-lookup"><span data-stu-id="c3175-116">Indicates the current throughput of the MBAM Server as it supports the MBAM client base.</span></span></p>
<p><span data-ttu-id="c3175-117">サイト管理者が次のことをできるようにします。</span><span class="sxs-lookup"><span data-stu-id="c3175-117">Enables site administrators to:</span></span></p>
<ul>
<li><p><span data-ttu-id="c3175-118">MBAM クライアントの数とその報告頻度に基づいて、1秒あたりの要求の平均数を計算します。</span><span class="sxs-lookup"><span data-stu-id="c3175-118">Calculate the average number of requests per second, based on the number of MBAM Clients and their reporting frequency.</span></span></p></li>
<li><p><span data-ttu-id="c3175-119">1秒あたりの要求数が、1秒あたりの合計要求数に大きく関連していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c3175-119">Validate that the number of requests per second broadly correlates with the calculated average number of requests per second.</span></span> <span data-ttu-id="c3175-120">重大な差異は、MBAM クライアントがクライアントベースの割合でインストールされていないか、MBAM グループポリシーオブジェクトが正常に展開されていないことを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c3175-120">A significant variance can indicate that the MBAM Client isn't installed on a percentage of the client base or that an MBAM Group Policy Object hasn't been successfully deployed.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3175-121">要求期間</span><span class="sxs-lookup"><span data-stu-id="c3175-121">Request duration</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3175-122">要求の期間 (ミリ秒単位) を記録します。</span><span class="sxs-lookup"><span data-stu-id="c3175-122">Records the duration of requests in milliseconds.</span></span></p>
<p><span data-ttu-id="c3175-123">このカウンターは各要求の期間によって更新されますが、Windows パフォーマンスモニターでは、定期的に (通常は1秒ごとに) サンプリングされるため、値の可変性がいくつか表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="c3175-123">Although this counter is updated with the duration of each request, Windows Performance Monitor samples it only periodically (typically every second), so you might see some variability in the value.</span></span> <span data-ttu-id="c3175-124">このため、パフォーマンスモニターによって表示される平均値の使用を検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3175-124">For this reason, consider using the average value displayed by Performance Monitor.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c3175-125">パフォーマンスカウンターの結果と推奨事項</span><span class="sxs-lookup"><span data-stu-id="c3175-125">Performance counter results and recommendations</span></span>


<span data-ttu-id="c3175-126">空き容量がある MBAM サーバーに新しい MBAM クライアントを追加すると、要求数が1秒あたり増加することを期待しています。</span><span class="sxs-lookup"><span data-stu-id="c3175-126">As you add new MBAM Clients to an MBAM Server with spare capacity, expect to see an increase in the number of requests per second.</span></span> <span data-ttu-id="c3175-127">この増加は、新しいクライアントコンピューターの数に比例します。</span><span class="sxs-lookup"><span data-stu-id="c3175-127">This increase will be proportional to the number of new client computers.</span></span> <span data-ttu-id="c3175-128">平均要求期間は、比較的静的なまま維持されます。</span><span class="sxs-lookup"><span data-stu-id="c3175-128">The average request duration will remain relatively static.</span></span> <span data-ttu-id="c3175-129">サーバーが最大キャパシティに近づくと、1秒あたりの要求が平準化され、平均要求期間が長くなります。</span><span class="sxs-lookup"><span data-stu-id="c3175-129">As the server nears its maximum capacity, the requests per second start to level out, and the average request duration starts to get longer.</span></span>

<span data-ttu-id="c3175-130">MBAM サーバーがクライアントベースをサポートしているかどうかが心配な場合は、クライアントコンピューターのさまざまなコレクション間で MBAM を段階的に導入することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3175-130">If you are concerned about whether your MBAM Servers can support your client base, consider deploying MBAM in phases across different collections of client computers.</span></span> <span data-ttu-id="c3175-131">クライアントコンピューターの各コレクションに MBAM を展開するときは、パフォーマンスカウンターのスナップショットを取得して、新しい各クライアントコレクションへの展開の相対的な影響を確認することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c3175-131">As you deploy MBAM to each collection of client computers, we recommend that you take snapshots of the performance counters to see the relative impact of deploying to each new client collection.</span></span> <span data-ttu-id="c3175-132">1秒あたりの要求数がレベルオフになり、平均要求期間が長くなった場合は、次のいずれかの操作を行って、MBAM サーバーインフラストラクチャを拡張することを検討してください。</span><span class="sxs-lookup"><span data-stu-id="c3175-132">If the number of requests per second starts to level off and the average request duration increases, consider enhancing your MBAM Server infrastructure by doing one of the following:</span></span>

-   <span data-ttu-id="c3175-133">MBAM データベースを専用の Microsoft SQL Server または SQL Server クラスターに移動する</span><span class="sxs-lookup"><span data-stu-id="c3175-133">Moving the MBAM database onto a dedicated Microsoft SQL Server or SQL Server cluster</span></span>

-   <span data-ttu-id="c3175-134">複数のインターネットインフォメーションサービス (IIS) web サーバーでのロードバランシング MBAM</span><span class="sxs-lookup"><span data-stu-id="c3175-134">Load-balancing MBAM across multiple Internet Information Services (IIS) web servers</span></span>

-   <span data-ttu-id="c3175-135">より強力なサーバーハードウェアでの MBAM の展開</span><span class="sxs-lookup"><span data-stu-id="c3175-135">Deploying MBAM on more powerful server hardware</span></span>

## <span data-ttu-id="c3175-136">パフォーマンスカウンターの表示</span><span class="sxs-lookup"><span data-stu-id="c3175-136">Viewing performance counters</span></span>


<span data-ttu-id="c3175-137">MBAM パフォーマンスカウンターを表示するための推奨ツールは、windows に付属している Windows のパフォーマンスモニターです。</span><span class="sxs-lookup"><span data-stu-id="c3175-137">The recommended tool for viewing MBAM performance counters is Windows Performance Monitor, which comes with Windows.</span></span> <span data-ttu-id="c3175-138">Windows PowerShell を使用している場合は、表示する前にカウンターを有効にする必要はありません。これらは、Windows PowerShell の**enable-webapplication**コマンドレットによって自動的に登録されるためです。</span><span class="sxs-lookup"><span data-stu-id="c3175-138">If you are using Windows PowerShell, you don’t need to enable the counters before viewing them, as they are automatically registered by the Windows PowerShell **Enable-webapplication** cmdlet.</span></span>

<span data-ttu-id="c3175-139">パフォーマンスカウンターの表示方法の詳細については、「 [MBAM パフォーマンスカウンターを表示する方法](https://go.microsoft.com/fwlink/?LinkId=393457)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c3175-139">For detailed instructions on how to view performance counters, see [How to View MBAM Performance Counters](https://go.microsoft.com/fwlink/?LinkId=393457).</span></span>



## <span data-ttu-id="c3175-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c3175-140">Related topics</span></span>


[<span data-ttu-id="c3175-141">MBAM 2.5 の保守</span><span class="sxs-lookup"><span data-stu-id="c3175-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)

 

 


## <span data-ttu-id="c3175-142">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="c3175-142">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="c3175-143">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="c3175-143">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="c3175-144">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="c3175-144">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>


