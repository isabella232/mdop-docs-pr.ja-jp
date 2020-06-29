---
title: パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法
description: パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法
author: dansimp
ms.assetid: 49d6c3f2-68b8-4c69-befa-7598a8737d05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 396cceaf9a3bde661200be2771a85596a512732f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817134"
---
# <span data-ttu-id="b5c06-103">パフォーマンス カウンターを使用して App-V Client のキャッシュを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b5c06-103">How to Manage the App-V Client Cache Using Performance Counters</span></span>


<span data-ttu-id="b5c06-104">次の手順を使用して、Application Virtualization (App-v) クライアントキャッシュで利用可能な空き領域を調べることができます。これにより、パフォーマンスモニターを使用して情報をグラフィカルに表示することができます。</span><span class="sxs-lookup"><span data-stu-id="b5c06-104">You can use the following procedure to determine how much free space is available in the Application Virtualization (App-V) client cache by using Performance Monitor to display the information graphically.</span></span> <span data-ttu-id="b5c06-105">この情報は、クライアントコンピューターで "App Virt Client Cache" という名前のパフォーマンスカウンターを使ってキャプチャされ、次のカウンターが含まれます。 "キャッシュサイズ (MB)," キャッシュの空き領域 (MB) "と"% の空き領域を増やす "というカウンターがあります。</span><span class="sxs-lookup"><span data-stu-id="b5c06-105">This information is captured on the client computer by a performance counter called “App Virt Client Cache,” and it includes the following counters: “Cache size (MB),” “Cache free space (MB),” and “% free space.”</span></span>

**<span data-ttu-id="b5c06-106">クライアントキャッシュスペース使用量を確認するには</span><span class="sxs-lookup"><span data-stu-id="b5c06-106">To determine client cache space usage</span></span>**

1.  <span data-ttu-id="b5c06-107">管理者としてコマンドプロンプトを開くか、[**開始**]、[**実行**] の**perfmon.exe**入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5c06-107">Open a command prompt as administrator, or click **Start**, **Run**, type **perfmon.exe**, and click **OK**.</span></span>

2.  <span data-ttu-id="b5c06-108">使用している Windows オペレーティングシステムに応じて、MMC ウィンドウが開いたら、パフォーマンスモニターまたはシステムモニターツールをクリックします。</span><span class="sxs-lookup"><span data-stu-id="b5c06-108">Depending on the Windows operating system being used, click the Performance Monitor or System Monitor tool after the MMC window opens.</span></span>

3.  <span data-ttu-id="b5c06-109">カウンターを追加するには、グラフの領域を右クリックし、[**カウンターの追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="b5c06-109">To add counters, right-click the graph area and select **Add Counters**.</span></span>

4.  <span data-ttu-id="b5c06-110">ドロップダウンをクリックして利用可能なカウンターの一覧を表示し、スクロールして [ **App Virt Client Cache**] を見つけ、3つのカウンターを追加します。</span><span class="sxs-lookup"><span data-stu-id="b5c06-110">Click the drop-down to display the list of available counters, scroll to find **App Virt Client Cache**, and then add the three counters.</span></span>

    <span data-ttu-id="b5c06-111">**重要** App-v のパフォーマンスカウンターは、32ビットの DLL に実装されているため、そのためには、次のコマンドを使用して、32ビットバージョンのパフォーマンスモニター ( **mmc/32 perfmon.exe**) を起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b5c06-111">**Important** The App-V performance counters are implemented in a 32-bit DLL, so to see them, you must use the following command to start the 32-bit version of Performance Monitor: **mmc /32 perfmon.msc**.</span></span> <span data-ttu-id="b5c06-112">このコマンドは、監視されているコンピューターで直接実行する必要があります。また、64ビットオペレーティングシステムを実行しているリモートコンピューターを監視するために使うことはできません。</span><span class="sxs-lookup"><span data-stu-id="b5c06-112">This command must be run directly on the computer being monitored and cannot be used to monitor a remote computer running a 64-bit operating system.</span></span>

     

## <span data-ttu-id="b5c06-113">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b5c06-113">Related topics</span></span>


[<span data-ttu-id="b5c06-114">コマンド ラインを使用して仮想アプリケーションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="b5c06-114">How to Manage Virtual Applications by Using the Command Line</span></span>](how-to-manage-virtual-applications-by-using-the-command-line.md)

 

 





