---
title: エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: 40af4ead-6588-4a81-8eaa-3dc00c397e1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 943e3956609ae7e24deaca4313036445802a8f7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823837"
---
# <span data-ttu-id="bc708-103">エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="bc708-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="bc708-104">通常、問題が発生しているエンドユーザーコンピューターの [診断/回復ツールセット] ウィンドウで、Microsoft 診断/回復ツールセット (DaRT) 7 クラッシュアナライザーを実行します。</span><span class="sxs-lookup"><span data-stu-id="bc708-104">Typically, you run Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="bc708-105">クラッシュアナライザーは、問題のあるコンピューター上の Windows 用デバッグツールを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="bc708-105">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="bc708-106">[ディレクトリパス] ダイアログボックスが空の場合は、場所を入力するか、Windows 用のデバッグツールの場所 (Microsoft からファイルをダウンロードできます) を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc708-106">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="bc708-107">また、シンボルファイルが配置されている場所へのパスも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bc708-107">You must also provide a path to where the symbol files are located.</span></span>

**<span data-ttu-id="bc708-108">エンドユーザーのコンピューターでクラッシュアナライザーを開いて実行するには</span><span class="sxs-lookup"><span data-stu-id="bc708-108">To open and run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="bc708-109">エンドユーザーコンピューターの [**診断/回復ツールセット**] ウィンドウで、[**クラッシュアナライザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc708-109">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="bc708-110">次の項目に必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="bc708-110">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="bc708-111">Windows 用 Microsoft デバッグツール</span><span class="sxs-lookup"><span data-stu-id="bc708-111">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="bc708-112">シンボルファイル</span><span class="sxs-lookup"><span data-stu-id="bc708-112">Symbol files</span></span>

        <span data-ttu-id="bc708-113">シンボルファイルの詳細については、「 [Crash Analyzer がシンボルファイルにアクセスできることを確認する方法](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc708-113">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="bc708-114">クラッシュダンプファイル</span><span class="sxs-lookup"><span data-stu-id="bc708-114">A crash dump file</span></span>

        <span data-ttu-id="bc708-115">クラッシュダンプファイルの場所を確認するには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bc708-115">Follow these steps to determine the location of the crash dump file:</span></span>

        1.  <span data-ttu-id="bc708-116">[**システムのプロパティ**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="bc708-116">Open the **System Properties** window.</span></span>

            <span data-ttu-id="bc708-117">[**スタート**] をクリックし、sysdm.cpl 入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="bc708-117">Click **Start**, type sysdm.cpl, and then press Enter.</span></span>

        2.  <span data-ttu-id="bc708-118">**[詳細設定]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc708-118">Click the **Advanced** tab.</span></span>

        3.  <span data-ttu-id="bc708-119">[**起動と回復**] 領域で、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc708-119">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="bc708-120">**注** [**システムのプロパティ**] ウィンドウにアクセスできない場合は、DaRT の**検索**ツールを使用して、エンドユーザーのコンピューターでダンプファイルを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="bc708-120">**Note** If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in DaRT.</span></span>

         

3.  <span data-ttu-id="bc708-121">クラッシュ**ダンプファイルがスキャンさ**れ、クラッシュの原因と思われるエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="bc708-121">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="bc708-122">クラッシュの詳細については、具体的なクラッシュメッセージと説明、クラッシュの発生時に読み込まれたドライバー、分析の完全な出力などを参照してください。</span><span class="sxs-lookup"><span data-stu-id="bc708-122">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="bc708-123">問題を解決するための適切な戦略を決定します。</span><span class="sxs-lookup"><span data-stu-id="bc708-123">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="bc708-124">これには、DaRT の**コンピューター管理**ツールの [**サービスとドライバー** ] ノードを使用して、クラッシュの原因となったデバイスドライバーの無効化または更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="bc708-124">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="bc708-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bc708-125">Related topics</span></span>


[<span data-ttu-id="bc708-126">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="bc708-126">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





