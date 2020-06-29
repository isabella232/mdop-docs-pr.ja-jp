---
title: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
description: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
author: dansimp
ms.assetid: 4f4bec1b-df3e-40ee-b431-291440268d64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95fb843b230804417e375946814a585d1d681634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824474"
---
# <span data-ttu-id="67e89-103">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="67e89-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="67e89-104">次のことを確認するには、管理と監視の Web サイトでこの手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="67e89-104">Use this procedure with the Administration and Monitoring Website to determine the following:</span></span>

-   <span data-ttu-id="67e89-105">紛失または盗難されたコンピューターの最後の既知の BitLocker 暗号化状態</span><span class="sxs-lookup"><span data-stu-id="67e89-105">The last known BitLocker encryption status of lost or stolen computers</span></span>

-   <span data-ttu-id="67e89-106">紛失または盗難のコンピューター上のボリュームが暗号化されているかどうか</span><span class="sxs-lookup"><span data-stu-id="67e89-106">Whether the volumes on a lost or stolen computer were encrypted</span></span>

<span data-ttu-id="67e89-107">このタスクを完了するには、管理と監視の Web サイトの [**レポート**] 領域にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e89-107">To complete this task, you need access to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="67e89-108">この領域へのアクセス権を取得するには、MBAM レポートのユーザーロールが割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67e89-108">To get access to this area, you must be assigned the MBAM Report Users role.</span></span> <span data-ttu-id="67e89-109">これらの役割は、作成時に異なる名前を指定した可能性があります。</span><span class="sxs-lookup"><span data-stu-id="67e89-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="67e89-110">詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="67e89-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="67e89-111">**注** デバイスのコンプライアンスは、企業が展開した BitLocker ポリシーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="67e89-111">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="67e89-112">デバイスの BitLocker 暗号化の状態を確認する前に、展開されたポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="67e89-112">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

 

**<span data-ttu-id="67e89-113">紛失したコンピューターの最後の既知の BitLocker 暗号化の状態を確認するには</span><span class="sxs-lookup"><span data-stu-id="67e89-113">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="67e89-114">Web ブラウザーを開き、**管理と監視の Web サイト**に移動します。</span><span class="sxs-lookup"><span data-stu-id="67e89-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="67e89-115">左側のウィンドウで [**レポート**] を選択し、[レポート] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="67e89-115">In the left pane, select **Reports** to open the Reports page.</span></span>

3.  <span data-ttu-id="67e89-116">[**コンピューターのコンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="67e89-116">Select the **Computer Compliance Report**.</span></span>

4.  <span data-ttu-id="67e89-117">右側のウィンドウのフィルターフィールドを使って検索結果を絞り込んでから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67e89-117">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="67e89-118">検索結果は、検索クエリの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="67e89-118">Results are shown under your search query.</span></span>

5.  <span data-ttu-id="67e89-119">紛失したデバイスのポリシーによって決定される適切な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="67e89-119">Take the appropriate action, as determined by your policy for lost devices.</span></span>



## <span data-ttu-id="67e89-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="67e89-120">Related topics</span></span>


[<span data-ttu-id="67e89-121">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="67e89-121">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="67e89-122">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="67e89-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="67e89-123">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="67e89-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="67e89-124">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="67e89-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





