---
title: ディスク デフラグ ツール実行中ダイアログ ボックス (App-V 4.6 SP1)
description: ディスク デフラグ ツール実行中ダイアログ ボックス (App-V 4.6 SP1)
author: dansimp
ms.assetid: 0ceb0897-377e-4754-a7ab-3bc2b5af1452
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ca56723dedb46ba87890ae62d476ca365b201c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821727"
---
# <span data-ttu-id="ab554-103">ディスク デフラグ ツール実行中ダイアログ ボックス (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="ab554-103">Defrag Running Dialog Box (App-V 4.6 SP1)</span></span>


<span data-ttu-id="ab554-104">ディスクデフラグサービスが実行されています。</span><span class="sxs-lookup"><span data-stu-id="ab554-104">The Disk Defragmenter service is running.</span></span> <span data-ttu-id="ab554-105">ディスクデフラグサービスはシステムリソースを消費するため、パフォーマンスが低下したり、仮想アプリケーションパッケージの作成にかかる時間が長くなったりする可能性があります。</span><span class="sxs-lookup"><span data-stu-id="ab554-105">The Disk Defragmenter service uses system resources and can cause degradation in performance or increase the time it takes to create virtual application package.</span></span>

<span data-ttu-id="ab554-106">シーケンス中にディスクデフラグサービスが実行されないようにするには、次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="ab554-106">Use the following procedure to stop the Disk Defragmenter service from running during sequencing.</span></span>

1.  <span data-ttu-id="ab554-107">App-v Sequencer を実行しているコンピューターで、[**スタート**] をクリックし、[**コンピューター**] を右クリックして、[**管理**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab554-107">On the computer running the App-V Sequencer, click **Start**, right-click **Computer**, and then click **Manage**.</span></span>

2.  <span data-ttu-id="ab554-108">コンピューターの**管理**コンソールで、[**サービスとアプリケーション**] をダブルクリックし、[**サービス**] をダブルクリックして、[**サービス**] を展開します。</span><span class="sxs-lookup"><span data-stu-id="ab554-108">In the **Computer Management** console, double-click **Services and Applications**, and then double-click **Services** to expand **Services**,.</span></span>

3.  <span data-ttu-id="ab554-109">リストで検索します。</span><span class="sxs-lookup"><span data-stu-id="ab554-109">Locate it in the list.</span></span> <span data-ttu-id="ab554-110">[**ディスクデフラグツール**] を右クリックし、[**その他のアクション**] をクリックし、[**停止**] をクリックしてディスクデフラグツールを停止し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ab554-110">Right-click **Disk Defragmenter**, click **More Actions**, click **Stop** to stop Disk Defragmenter, and then click **OK**.</span></span>

## <span data-ttu-id="ab554-111">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ab554-111">Related topics</span></span>


[<span data-ttu-id="ab554-112">ダイアログ ボックス (AppV 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="ab554-112">Dialog Boxes (AppV 4.6 SP1)</span></span>](dialog-boxes--appv-46-sp1-.md)

 

 





