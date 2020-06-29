---
title: システム使用率レポート
description: システム使用率レポート
author: dansimp
ms.assetid: 4d490d15-2d1f-4f2c-99bb-0685447c0672
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fe7ff547d969c63ace234104c3e6b7146da2c113
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815254"
---
# <span data-ttu-id="5cb10-103">システム使用率レポート</span><span class="sxs-lookup"><span data-stu-id="5cb10-103">System Utilization Report</span></span>


<span data-ttu-id="5cb10-104">システム使用率レポートを使用して、システムの毎日の合計使用量をグラフ化します。</span><span class="sxs-lookup"><span data-stu-id="5cb10-104">Use the System Utilization Report to graph the total daily system usage.</span></span> <span data-ttu-id="5cb10-105">このレポートを使って、Application Virtualization システムの負荷を確認できます。</span><span class="sxs-lookup"><span data-stu-id="5cb10-105">You can use this report to determine the load on your Application Virtualization System.</span></span>

<span data-ttu-id="5cb10-106">このレポートでは、指定したサーバーまたはサーバーグループのレポート期間中の時間経過による使用状況を追跡します。</span><span class="sxs-lookup"><span data-stu-id="5cb10-106">This report tracks the usage over time during the reporting period for the specified server or for the server group.</span></span>

<span data-ttu-id="5cb10-107">システム使用率レポートには、次のシステム使用状況もグラフで示します。</span><span class="sxs-lookup"><span data-stu-id="5cb10-107">The System Utilization Report also graphs the following system usage:</span></span>

-   <span data-ttu-id="5cb10-108">曜日による使用</span><span class="sxs-lookup"><span data-stu-id="5cb10-108">Usage by day of the week</span></span>

-   <span data-ttu-id="5cb10-109">1日の時間単位の使用</span><span class="sxs-lookup"><span data-stu-id="5cb10-109">Usage by hour of the day</span></span>

<span data-ttu-id="5cb10-110">システム使用率レポートには、特定のユーザーに対するシステム全体の使用状況と合計セッション数の概要も表示されます。</span><span class="sxs-lookup"><span data-stu-id="5cb10-110">The System Utilization Report also includes a summary of the total system usage for specific users and total session counts.</span></span>

<span data-ttu-id="5cb10-111">レポートを作成するときに、レポートの実行時にデータを収集するために使用されるパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="5cb10-111">When you create a report, you specify the parameters that are used for collecting the data when the report is run.</span></span>

<span data-ttu-id="5cb10-112">レポートは自動的には実行されません。出力データを生成するには、明示的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb10-112">Reports are not run automatically; you must run them explicitly to generate output data.</span></span> <span data-ttu-id="5cb10-113">このレポートを実行するのにかかる時間の長さは、データストアで収集されたデータの量によって決まります。</span><span class="sxs-lookup"><span data-stu-id="5cb10-113">The length of time it takes to run this report is determined by the amount of data collected in the data store.</span></span>

<span data-ttu-id="5cb10-114">レポートを実行し、出力が Application Virtualization Server 管理コンソールに表示されたら、次の形式でレポートをエクスポートできます。</span><span class="sxs-lookup"><span data-stu-id="5cb10-114">After you run a report and the output is displayed in the Application Virtualization Server Management Console, you can export the report into the following formats:</span></span>

-   <span data-ttu-id="5cb10-115">Adobe Acrobat (PDF)</span><span class="sxs-lookup"><span data-stu-id="5cb10-115">Adobe Acrobat (PDF)</span></span>

-   <span data-ttu-id="5cb10-116">Microsoft Office Excel</span><span class="sxs-lookup"><span data-stu-id="5cb10-116">Microsoft Office Excel</span></span>

<span data-ttu-id="5cb10-117">**注** システムの使用状況レポートでデータを表示するには、クライアントから報告された App-v server 名が既定のサーバーグループに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb10-117">**Note** The App-V server name reported from the clients must be part of the Default Server Group in order for the System Utilization report to show data.</span></span> <span data-ttu-id="5cb10-118">たとえば、ネットワークロードバランサー (NLB) で複数のサーバーを使用している場合、[既定のサーバー] グループに NLB クラスター名を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5cb10-118">For example, if you are using multiple servers with a Network Load Balancer (NLB), you must add the NLB cluster name to the Default Server Group.</span></span>

 

## <span data-ttu-id="5cb10-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5cb10-119">Related topics</span></span>


[<span data-ttu-id="5cb10-120">レポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="5cb10-120">How to Create a Report</span></span>](how-to-create-a-reportserver.md)

[<span data-ttu-id="5cb10-121">レポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="5cb10-121">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)

[<span data-ttu-id="5cb10-122">レポートをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="5cb10-122">How to Export a Report</span></span>](how-to-export-a-reportserver.md)

[<span data-ttu-id="5cb10-123">レポートを印刷する方法</span><span class="sxs-lookup"><span data-stu-id="5cb10-123">How to Print a Report</span></span>](how-to-print-a-reportserver.md)

[<span data-ttu-id="5cb10-124">レポートを実行する方法</span><span class="sxs-lookup"><span data-stu-id="5cb10-124">How to Run a Report</span></span>](how-to-run-a-reportserver.md)

 

 





