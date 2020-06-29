---
title: セルフサービス ポータルの通知テキストを有効または無効にする方法
description: セルフサービス ポータルの通知テキストを有効または無効にする方法
author: dansimp
ms.assetid: e786685b-ffdb-4557-ae71-e79528097264
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 06090ede47d36a7d1be5a05769f75304e67cbd53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824464"
---
# <span data-ttu-id="e718b-103">セルフサービス ポータルの通知テキストを有効または無効にする方法</span><span class="sxs-lookup"><span data-stu-id="e718b-103">How to Turn the Self-Service Portal Notice Text On or Off</span></span>


<span data-ttu-id="e718b-104">セルフサービスポータルの通知テキストのオンとオフを切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="e718b-104">You can turn the Self-Service Portal notice text on or off.</span></span> <span data-ttu-id="e718b-105">既定では、通知テキストはオンになっています。</span><span class="sxs-lookup"><span data-stu-id="e718b-105">By default, the notice text is turned on.</span></span> <span data-ttu-id="e718b-106">通知テキストを設定するには、「[セルフサービスポータルのブランド設定とセッションタイムアウトの設定方法](how-to-set-the-self-service-portal-branding-and-session-time-out.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e718b-106">To set the notice text, see [How to Set the Self-Service Portal Branding and Session Time-out](how-to-set-the-self-service-portal-branding-and-session-time-out.md).</span></span>

<span data-ttu-id="e718b-107">**注** 次の手順では、 *selfservice*がセルフサービスポータルの既定の仮想ディレクトリ名です。</span><span class="sxs-lookup"><span data-stu-id="e718b-107">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="e718b-108">セルフサービスポータルを構成したときに、別の名前が使用されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e718b-108">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="e718b-109">通知テキストをオフにするには</span><span class="sxs-lookup"><span data-stu-id="e718b-109">To turn off the notice text</span></span>**

1.  <span data-ttu-id="e718b-110">セルフサービスポータルを構成したサーバーで、[**サイト**の管理]、[ &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **サービス** &gt; **アプリケーション設定**の監視] の各サイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="e718b-110">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="e718b-111">[**名前**] 列で、[ **displaynotice**] を選択し、値を**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="e718b-111">In the **Name** column, select **DisplayNotice**, and set the value to **false**.</span></span>



## <span data-ttu-id="e718b-112">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e718b-112">Related topics</span></span>


[<span data-ttu-id="e718b-113">組織のセルフサービス ポータルのカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="e718b-113">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 

## <span data-ttu-id="e718b-114">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="e718b-114">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e718b-115">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="e718b-115">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e718b-116">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="e718b-116">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



