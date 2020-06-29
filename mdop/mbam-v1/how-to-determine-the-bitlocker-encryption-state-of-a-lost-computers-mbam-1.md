---
title: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
description: 紛失したコンピューターの BitLocker 暗号化の状態を確認する方法
author: dansimp
ms.assetid: 9440890a-9c63-463b-9113-f46071446388
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9b977b20ecf219830609c3b1f646a29e6678448
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824294"
---
# <span data-ttu-id="6f223-103">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="6f223-103">How to Determine the BitLocker Encryption State of a Lost Computers</span></span>


<span data-ttu-id="6f223-104">Microsoft BitLocker 管理と監視 (MBAM) を使用すると、紛失または盗難されたコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。</span><span class="sxs-lookup"><span data-stu-id="6f223-104">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to determine the last known BitLocker encryption status of computers that are lost or stolen.</span></span> <span data-ttu-id="6f223-105">所有していないコンピューターでボリュームが暗号化されているかどうかを確認するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="6f223-105">Use the following procedure to determine whether the volumes have been encrypted on computers that are no longer in your possession.</span></span>

**<span data-ttu-id="6f223-106">コンピューターの最後の既知の BitLocker 暗号化の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="6f223-106">Determine a Computer's Last Known BitLocker Encryption state</span></span>**

1.  <span data-ttu-id="6f223-107">MBAM web サイトを開きます。</span><span class="sxs-lookup"><span data-stu-id="6f223-107">Open the MBAM website.</span></span>

    <span data-ttu-id="6f223-108">**注** MBAM web サイトの既定のアドレスは http://\* &lt; computername &gt; \*です。</span><span class="sxs-lookup"><span data-stu-id="6f223-108">**Note** The default address for the MBAM website is http://*&lt;computername&gt;*.</span></span> <span data-ttu-id="6f223-109">検索結果をすばやく表示するには、完全修飾サーバー名を使います。</span><span class="sxs-lookup"><span data-stu-id="6f223-109">Use the fully qualified server name for faster browsing results.</span></span>

     

2.  <span data-ttu-id="6f223-110">ナビゲーションウィンドウから [**レポート**] ノードを選択し、[**コンピューターのコンプライアンスレポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f223-110">Select the **Report** node from the navigation pane, and then select the **Computer Compliance Report**.</span></span>

3.  <span data-ttu-id="6f223-111">右側のウィンドウのフィルターフィールドを使って検索結果を絞り込んでから、[**検索**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f223-111">Use the filter fields in the right-side pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="6f223-112">検索クエリの下に結果が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f223-112">Results will be shown below your search query.</span></span>

4.  <span data-ttu-id="6f223-113">紛失したデバイスのポリシーによって決定された適切なアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f223-113">Take the appropriate action as determined by your policy for lost devices.</span></span>

    <span data-ttu-id="6f223-114">**注** デバイスのコンプライアンスは、展開された BitLocker ポリシーによって決まります。</span><span class="sxs-lookup"><span data-stu-id="6f223-114">**Note** Device compliance is determined by the deployed BitLocker policies.</span></span> <span data-ttu-id="6f223-115">デバイスの BitLocker 暗号化の状態を確認しようとしている場合は、これらの展開されたポリシーを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f223-115">You should verify these deployed policies when you are trying to determine the BitLocker encryption state of a device.</span></span>

     

## <span data-ttu-id="6f223-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6f223-116">Related topics</span></span>


[<span data-ttu-id="6f223-117">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="6f223-117">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





