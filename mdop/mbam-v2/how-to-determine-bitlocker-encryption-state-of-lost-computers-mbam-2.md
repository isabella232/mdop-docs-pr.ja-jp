---
title: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
description: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824614"
---
# <span data-ttu-id="b8afb-103">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="b8afb-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="b8afb-104">Microsoft BitLocker の管理と監視 (MBAM) を使用して、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。</span><span class="sxs-lookup"><span data-stu-id="b8afb-104">You can use Microsoft BitLocker Administration and Monitoring (MBAM) to determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span> <span data-ttu-id="b8afb-105">次の手順では、紛失や盗難があった場合に、コンピューター上のボリュームが暗号化されているかどうかを判断する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b8afb-105">The following procedure explains how to determine whether the volumes on a computer are encrypted if there is a loss or theft.</span></span>

**<span data-ttu-id="b8afb-106">紛失したコンピューターの最後の既知の BitLocker 暗号化の状態を確認するには</span><span class="sxs-lookup"><span data-stu-id="b8afb-106">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="b8afb-107">Web ブラウザーを開き、管理と監視の web サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="b8afb-107">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

    <span data-ttu-id="b8afb-108">**注** 注: 管理および監視 web サイトの既定のアドレスは http://\* &lt; computername &gt; \*です。</span><span class="sxs-lookup"><span data-stu-id="b8afb-108">**Note** Note: The default address for the Administration and Monitoring website is http://*&lt;computername&gt;*.</span></span> <span data-ttu-id="b8afb-109">完全修飾サーバー名を使用すると、閲覧の結果が速くなります。</span><span class="sxs-lookup"><span data-stu-id="b8afb-109">Using the fully qualified server name will yield faster browsing results.</span></span>

     

2.  <span data-ttu-id="b8afb-110">ナビゲーションウィンドウで**レポート**ノードを選択し、[コンピューターの**コンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b8afb-110">Selects the **Report** node from the navigation pane, and select the **Computer Compliance Report**.</span></span>

3.  <span data-ttu-id="b8afb-111">右側のウィンドウのフィルターフィールドを使って検索結果を絞り込んでから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b8afb-111">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="b8afb-112">検索クエリの下に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="b8afb-112">Results are shown below your search query.</span></span>

4.  <span data-ttu-id="b8afb-113">紛失したデバイスのポリシーによって決定される適切な操作を行います。</span><span class="sxs-lookup"><span data-stu-id="b8afb-113">Take the appropriate action, as determined by your policy for lost devices.</span></span>

    <span data-ttu-id="b8afb-114">**注** デバイスのコンプライアンスは、企業が展開した BitLocker ポリシーによって決定されます。</span><span class="sxs-lookup"><span data-stu-id="b8afb-114">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="b8afb-115">デバイスの BitLocker 暗号化の状態を確認する前に、展開されたポリシーを確認してください。</span><span class="sxs-lookup"><span data-stu-id="b8afb-115">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

     

## <span data-ttu-id="b8afb-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b8afb-116">Related topics</span></span>


[<span data-ttu-id="b8afb-117">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="b8afb-117">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





