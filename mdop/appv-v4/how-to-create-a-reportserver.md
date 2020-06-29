---
title: レポートを作成する方法
description: レポートを作成する方法
author: dansimp
ms.assetid: 70938167-d3b9-45ce-b459-a953c93769b0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92e2fbe592696563ab031e386b698df268bf57ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817704"
---
# <span data-ttu-id="72f56-103">レポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="72f56-103">How to Create a Report</span></span>


<span data-ttu-id="72f56-104">Application Virtualization Server 管理コンソールからレポートを作成するプロセスは、レポートの種類に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="72f56-104">The process for creating a report from the Application Virtualization Server Management Console is the same regardless of the report type.</span></span> <span data-ttu-id="72f56-105">レポートの種類を選択すると、選択したレポートの簡単な説明がウィンドウに表示されます。</span><span class="sxs-lookup"><span data-stu-id="72f56-105">When you select a report type, the window displays a brief description of the selected report.</span></span>

<span data-ttu-id="72f56-106">**注** レポートを作成するときに、レポートの実行時にデータを収集するために使用されるパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="72f56-106">**Note** When you create a report, you specify the parameters that are used for collecting the data when the report is run.</span></span> <span data-ttu-id="72f56-107">レポートを実行するまで、データは収集されません。</span><span class="sxs-lookup"><span data-stu-id="72f56-107">Until you run a report, no data is collected.</span></span>

 

**<span data-ttu-id="72f56-108">レポートを作成するには</span><span class="sxs-lookup"><span data-stu-id="72f56-108">To create a report</span></span>**

1.  <span data-ttu-id="72f56-109">新しいレポートウィザードを実行するには、[**レポート**] ノードを右クリックし、ポップアップメニューの [**新しいレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="72f56-109">Run the New Report Wizard by right-clicking the **Reports** node and selecting **New Report** from the pop-up menu.</span></span>

2.  <span data-ttu-id="72f56-110">新しいレポートウィザードの最初のページで、[**レポート名**] フィールドに名前を入力し、レポートのドロップダウンリストから**レポートの種類**を選びます。</span><span class="sxs-lookup"><span data-stu-id="72f56-110">On the first page of the New Report Wizard, enter a name in the **Report Name** field and select the **Report Type** from the drop-down list of reports.</span></span> <span data-ttu-id="72f56-111">選択したレポートに応じて、ウィザードの残りのページは、そのレポートの種類の要件に従って変更されます。</span><span class="sxs-lookup"><span data-stu-id="72f56-111">Depending on which report you select, the remaining pages in the wizard change according the requirements of that report type.</span></span> <span data-ttu-id="72f56-112">レポートを参照するページを検索するには、次のページのリストをスキャンします。</span><span class="sxs-lookup"><span data-stu-id="72f56-112">Scan the following list of pages to find the pages that refer to your report:</span></span>

    1.  <span data-ttu-id="72f56-113">[**レポート期間**] —ラジオボタンを選択して、レポートの実行頻度を指定します。</span><span class="sxs-lookup"><span data-stu-id="72f56-113">**Report Period**—Select a radio button to specify the frequency for running the report.</span></span>

    2.  <span data-ttu-id="72f56-114">[**サーバー**] — [**サーバー**]、[**サーバーグループ**]、または [**エンタープライズ**] ラジオボタンを選択し、対応するドロップダウンリストから [有効] というサーバーグループとサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="72f56-114">**Server**—Select the **Server**, **Server Group**, or **Enterprise** radio button, and then select the server group and server from the corresponding drop-down list and field as enabled.</span></span>

    3.  <span data-ttu-id="72f56-115">[**アプリケーション**] —利用可能なアプリケーションのドロップダウンリストからアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="72f56-115">**Application**—Select an application from the drop-down list of available applications.</span></span>

3.  <span data-ttu-id="72f56-116">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="72f56-116">Click **Finish**.</span></span>

## <span data-ttu-id="72f56-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="72f56-117">Related topics</span></span>


[<span data-ttu-id="72f56-118">Application Virtualization レポートの種類</span><span class="sxs-lookup"><span data-stu-id="72f56-118">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)

[<span data-ttu-id="72f56-119">レポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="72f56-119">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)

[<span data-ttu-id="72f56-120">レポートをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="72f56-120">How to Export a Report</span></span>](how-to-export-a-reportserver.md)

[<span data-ttu-id="72f56-121">レポートを印刷する方法</span><span class="sxs-lookup"><span data-stu-id="72f56-121">How to Print a Report</span></span>](how-to-print-a-reportserver.md)

[<span data-ttu-id="72f56-122">レポートを実行する方法</span><span class="sxs-lookup"><span data-stu-id="72f56-122">How to Run a Report</span></span>](how-to-run-a-reportserver.md)

 

 





