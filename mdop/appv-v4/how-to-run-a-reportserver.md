---
title: レポートを実行する方法
description: レポートを実行する方法
author: dansimp
ms.assetid: 72a5419b-aa65-4e60-b23e-3751186b7aed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739d8e2c86a2264dc8194b507eebf19b7ee88328
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816717"
---
# <span data-ttu-id="c7314-103">レポートを実行する方法</span><span class="sxs-lookup"><span data-stu-id="c7314-103">How to Run a Report</span></span>


<span data-ttu-id="c7314-104">レポートの実行プロセスは、レポートの種類に関係なく同じです。</span><span class="sxs-lookup"><span data-stu-id="c7314-104">The process for running a report is the same regardless of the report type.</span></span> <span data-ttu-id="c7314-105">Application Virtualization Server 管理コンソールでレポートの種類を選択すると、ウィンドウに選択したレポートの簡単な説明が表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7314-105">When you select a report type in the Application Virtualization Server Management Console, the window displays a brief description of the selected report.</span></span>

<span data-ttu-id="c7314-106">**注** レポートは自動的には実行されません。出力データを生成するには、明示的に実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c7314-106">**Note** Reports are not run automatically; you must run them explicitly to generate output data.</span></span> <span data-ttu-id="c7314-107">レポートの実行にかかる時間の長さは、データストアで収集されたデータの量によって決まります。</span><span class="sxs-lookup"><span data-stu-id="c7314-107">The length of time it takes to run a report is determined by the amount of data collected in the data store.</span></span>

 

**<span data-ttu-id="c7314-108">レポートを実行するには</span><span class="sxs-lookup"><span data-stu-id="c7314-108">To run a report</span></span>**

1.  <span data-ttu-id="c7314-109">ナビゲーションウィンドウで [**レポート**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7314-109">Click the **Reports** node in the navigation pane.</span></span>

2.  <span data-ttu-id="c7314-110">目的のレポートを右クリックし、ポップアップメニューから [**レポートの実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7314-110">Right-click the desired report, and select **Run Report** from the pop-up menu.</span></span>

3.  <span data-ttu-id="c7314-111">レポートの実行に必要なページは、レポートの種類によって異なります。</span><span class="sxs-lookup"><span data-stu-id="c7314-111">The pages you must complete to run a report vary depending on the type of report.</span></span> <span data-ttu-id="c7314-112">レポートを実行するには、次の一覧から適切なページを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7314-112">To run a report, complete the appropriate pages from the following list:</span></span>

    1.  <span data-ttu-id="c7314-113">レポート**期間**のラジオボタンを選択して、レポートの実行頻度を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7314-113">Select a **Report Period** radio button to specify the frequency for running the report.</span></span>

    2.  <span data-ttu-id="c7314-114">レポートに含める日付の範囲を決定するには、各フィールドに開始日と終了日を指定します。</span><span class="sxs-lookup"><span data-stu-id="c7314-114">Specify the start date and end date in the respective fields to determine the range of dates included in the report.</span></span> <span data-ttu-id="c7314-115">これらの日付を手動で入力するか、calendar 関数を使用して日付を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="c7314-115">You can enter these dates manually or use the calendar function and select the dates.</span></span>

    3.  <span data-ttu-id="c7314-116">[**サーバー**]、[**サーバーグループ**]、または [**エンタープライズ**] ラジオボタンを選択し、対応するドロップダウンリストから [有効] というサーバーグループとサーバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="c7314-116">Select the **Server**, **Server Group**, or **Enterprise** radio button, and then select the server group and server from the corresponding drop-down list and field as enabled.</span></span>

    4.  <span data-ttu-id="c7314-117">アプリケーションのドロップダウンリストから目的のアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="c7314-117">Select the desired application from the drop-down list of applications.</span></span>

4.  <span data-ttu-id="c7314-118">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7314-118">Click **Finish**.</span></span>

## <span data-ttu-id="c7314-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7314-119">Related topics</span></span>


[<span data-ttu-id="c7314-120">Application Virtualization レポートの種類</span><span class="sxs-lookup"><span data-stu-id="c7314-120">Application Virtualization Report Types</span></span>](application-virtualization-report-types.md)

[<span data-ttu-id="c7314-121">レポートを作成する方法</span><span class="sxs-lookup"><span data-stu-id="c7314-121">How to Create a Report</span></span>](how-to-create-a-reportserver.md)

[<span data-ttu-id="c7314-122">レポートを削除する方法</span><span class="sxs-lookup"><span data-stu-id="c7314-122">How to Delete a Report</span></span>](how-to-delete-a-reportserver.md)

[<span data-ttu-id="c7314-123">レポートをエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="c7314-123">How to Export a Report</span></span>](how-to-export-a-reportserver.md)

[<span data-ttu-id="c7314-124">レポートを印刷する方法</span><span class="sxs-lookup"><span data-stu-id="c7314-124">How to Print a Report</span></span>](how-to-print-a-reportserver.md)

 

 





