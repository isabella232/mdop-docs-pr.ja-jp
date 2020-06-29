---
title: 使用状況レポートをセットアップまたは無効にする方法
description: 使用状況レポートをセットアップまたは無効にする方法
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816547"
---
# <span data-ttu-id="62dde-103">使用状況レポートをセットアップまたは無効にする方法</span><span class="sxs-lookup"><span data-stu-id="62dde-103">How to Set Up or Disable Usage Reporting</span></span>


<span data-ttu-id="62dde-104">Application Virtualization Server 管理コンソールで次の手順を使用して、データベースに格納するアプリケーションの仮想化システムの利用状況情報の期間 (月数) を指定できます。</span><span class="sxs-lookup"><span data-stu-id="62dde-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the duration (in months) of Application Virtualization System usage information you want to store in the database.</span></span>

<span data-ttu-id="62dde-105">**注** 使用状況の情報を保存するには、[**プロバイダーパイプライン**] タブの [**ログの使用情報**] チェックボックスをオンにする必要があります。このタブを表示するには、[**プロバイダーポリシーの結果**] ウィンドウでプロバイダーポリシーを右クリックし、[**プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="62dde-105">**Note** To store usage information, you must select the **Log Usage Information** check box on the **Provider Pipeline** tab. To display this tab, right-click the provider policy in the **Provider Policies Results** pane and select **Properties**.</span></span>

 

**<span data-ttu-id="62dde-106">利用状況レポートを設定するには</span><span class="sxs-lookup"><span data-stu-id="62dde-106">To set up usage reporting</span></span>**

1.  <span data-ttu-id="62dde-107">左側のウィンドウで [Application Virtualization System] ノードを右クリックし、[**システムオプション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="62dde-107">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="62dde-108">[**データベース**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="62dde-108">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="62dde-109">[**使用を継続する (月数)** ] または [**すべての使用を維持**] ラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="62dde-109">Select the **Keep Usage For (Months)** or **Keep All Usage** radio button.</span></span>

4.  <span data-ttu-id="62dde-110">使用期間を月単位で指定する場合は、1 ~ 120 の数値を入力します (既定値は6か月)。</span><span class="sxs-lookup"><span data-stu-id="62dde-110">If you choose to specify usage duration in months, enter a number from 1 to 120 (default value is 6 months).</span></span> <span data-ttu-id="62dde-111">[すべての**使用を保持**] を選択すると、指定したサイズ制限に達するまでデータベースが拡張されます。</span><span class="sxs-lookup"><span data-stu-id="62dde-111">If you select **Keep All Usage**, the database will grow until it reaches the specified size limit.</span></span>

5.  <span data-ttu-id="62dde-112">[**適用**] または [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62dde-112">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="62dde-113">使用状況レポートを無効にするには</span><span class="sxs-lookup"><span data-stu-id="62dde-113">To disable usage reporting</span></span>**

1.  <span data-ttu-id="62dde-114">[**プロバイダーポリシー** ] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="62dde-114">Click the **Provider Policies** node.</span></span>

2.  <span data-ttu-id="62dde-115">[**プロバイダーポリシー** ] を右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="62dde-115">Right-click **Provider Policy** and select **Properties**.</span></span>

3.  <span data-ttu-id="62dde-116">[**プロバイダーパイプライン**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="62dde-116">Select the **Provider Pipeline** tab.</span></span>

4.  <span data-ttu-id="62dde-117">[**ログの使用情報**] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="62dde-117">Clear the **Log Usage Information** check box.</span></span>

5.  <span data-ttu-id="62dde-118">[**適用**] または [ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="62dde-118">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="62dde-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="62dde-119">Related topics</span></span>


[<span data-ttu-id="62dde-120">サーバー管理コンソールで Application Virtualization システムをカスタマイズする方法</span><span class="sxs-lookup"><span data-stu-id="62dde-120">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="62dde-121">データベース サイズをセットアップまたは無効にする方法</span><span class="sxs-lookup"><span data-stu-id="62dde-121">How to Set Up or Disable Database Size</span></span>](how-to-set-up-or-disable-database-size.md)

 

 





