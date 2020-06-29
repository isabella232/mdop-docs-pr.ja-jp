---
title: データベース サイズをセットアップまたは無効にする方法
description: データベース サイズをセットアップまたは無効にする方法
author: dansimp
ms.assetid: 4abaf349-132d-4186-8873-a0e515593b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cbb041920e2680d51b01926f144eba595fe28d05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816564"
---
# <span data-ttu-id="ebec8-103">データベース サイズをセットアップまたは無効にする方法</span><span class="sxs-lookup"><span data-stu-id="ebec8-103">How to Set Up or Disable Database Size</span></span>


<span data-ttu-id="ebec8-104">Application Virtualization Server 管理コンソールで次の手順を使用して、データベースに格納するアプリケーションの仮想化システムの利用状況のサイズ (MB 単位) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the size (in MB) of Application Virtualization System usage that you want to store in the database.</span></span>

<span data-ttu-id="ebec8-105">保存されているデータのサイズが、指定された制限値の 95% (ハイウォーターマーク) に達すると、システムは利用状況データの10% を削除します。データの85% を残します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-105">When the size of the stored data reaches 95% (the high watermark) of the specified limit, the system will delete 10% of the usage data, leaving 85% of the data.</span></span> <span data-ttu-id="ebec8-106">パッケージとアプリケーションの利用状況データは削除されます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-106">Package and application usage data will be deleted.</span></span> <span data-ttu-id="ebec8-107">データベースのサイズが大きくなり、ハイウォーターマークに近づいている場合は、この制限に達したことを通知する警告メッセージが SQL Server ログに送信されます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-107">When the database grows large enough and approaches the high watermark, a warning message is sent to the SQL Server log to inform you that this limit has been reached.</span></span> <span data-ttu-id="ebec8-108">この警告が必要なのは、クリーンアップアクションがレポートの出力に影響する可能性があるためです。</span><span class="sxs-lookup"><span data-stu-id="ebec8-108">This warning is necessary because the cleanup action can affect the output of the reports.</span></span> <span data-ttu-id="ebec8-109">また、データベースの最大サイズを大きくする必要があるかどうかを決定したり、保持する使用量データの月数を減らしたり、ログレベルを下げることができます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-109">It will also help you decide whether you need to increase the maximum database size, reduce the number of months of usage data to be kept, or turn down the logging level.</span></span>

<span data-ttu-id="ebec8-110">**注** [**サイズ制限なし**] と [**すべての使用**] オプションが用意されているため、使用状況のレポートとデータベースのクリーンアップを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-110">**Note** The **No Size Limit** and **Keep All Usage** options are provided so that you can disable usage reporting and database cleanup.</span></span> <span data-ttu-id="ebec8-111">これらの項目を選択すると、データベースのトランザクションログもクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-111">Selecting these items will clean up the database transaction log as well.</span></span> <span data-ttu-id="ebec8-112">(コミットされた Microsoft SQL Server トランザクションはすべてデータベースログから削除されます)。</span><span class="sxs-lookup"><span data-stu-id="ebec8-112">(All committed Microsoft SQL Server transactions will be removed from the database log.)</span></span>

 

**<span data-ttu-id="ebec8-113">データベースのサイズを設定するには</span><span class="sxs-lookup"><span data-stu-id="ebec8-113">To set up database size</span></span>**

1.  <span data-ttu-id="ebec8-114">左側のウィンドウで [Application Virtualization System] ノードを右クリックし、[**システムオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-114">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="ebec8-115">[**データベース**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-115">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="ebec8-116">[**データベースの最大サイズ (MB)** ] または [**サイズ制限なし**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-116">Select the **Maximum Database Size (MB)** or **No Size Limit** radio button.</span></span>

4.  <span data-ttu-id="ebec8-117">データベースサイズを指定する場合は、512 ~ 4096 MB の数値を入力することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ebec8-117">If you choose to specify a database size, best practices recommend that you enter a number between 512 and 4096 MB.</span></span> <span data-ttu-id="ebec8-118">既定のサイズは 1024 MB であり、データベースサイズを増やす必要がある場合は、入力できる最大値は2147483647です。</span><span class="sxs-lookup"><span data-stu-id="ebec8-118">The default size is 1024 MB and if you need to increase the database size, the maximum value you can enter is 2,147,483,647.</span></span> <span data-ttu-id="ebec8-119">[**サイズ制限なし**] を選択した場合、データベースはディスクサイズの制限に達するまで拡大されます。</span><span class="sxs-lookup"><span data-stu-id="ebec8-119">If you select **No Size Limit**, the database will grow until it reaches the disk size limit.</span></span>

5.  <span data-ttu-id="ebec8-120">[**適用**] または [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebec8-120">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="ebec8-121">データベースサイズの制限を無効にするには</span><span class="sxs-lookup"><span data-stu-id="ebec8-121">To disable database size limits</span></span>**

1.  <span data-ttu-id="ebec8-122">[**スコープ**] ウィンドウで [Application Virtualization System] ノードを右クリックし、[**システムオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-122">Right-click the Application Virtualization System node in the **Scope** pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="ebec8-123">[**データベース**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-123">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="ebec8-124">[**サイズ制限なし**] を選択し、**すべての使用法**ボタンを保持します。</span><span class="sxs-lookup"><span data-stu-id="ebec8-124">Select the **No Size Limit** and **Keep All Usage** radio buttons.</span></span>

4.  <span data-ttu-id="ebec8-125">[**適用**] または [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ebec8-125">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="ebec8-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ebec8-126">Related topics</span></span>


[<span data-ttu-id="ebec8-127">サーバー管理コンソールで Application Virtualization システムをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="ebec8-127">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="ebec8-128">使用状況レポートをセットアップまたは無効にする方法</span><span class="sxs-lookup"><span data-stu-id="ebec8-128">How to Set Up or Disable Usage Reporting</span></span>](how-to-set-up-or-disable-usage-reporting.md)

 

 





