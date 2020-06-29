---
title: エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: 10334800-ff8e-43ac-a9c2-d28807473ec2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4abf1ba2ae1a0cb1dfb129c1f5a26e11f5045290
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822667"
---
# <span data-ttu-id="680fe-103">エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="680fe-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="680fe-104">問題が発生しているエンドユーザーのコンピューターの [**診断/回復ツールセット**] ウィンドウから**クラッシュアナライザー**を実行するには、Windows 用 Microsoft デバッグツールとシンボルファイルがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="680fe-104">To run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing problems, you must have the Microsoft Debugging Tools for Windows and the symbol files installed.</span></span> <span data-ttu-id="680fe-105">Windows デバッグツールをダウンロードするには、「 [windows 用デバッグツール](https://go.microsoft.com/fwlink/?LinkId=266248)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="680fe-105">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span>

**<span data-ttu-id="680fe-106">エンドユーザーコンピューターでクラッシュアナライザーを実行するには</span><span class="sxs-lookup"><span data-stu-id="680fe-106">To run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="680fe-107">エンドユーザーコンピューターの [**診断/回復ツールセット**] ウィンドウで、[**クラッシュアナライザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="680fe-107">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="680fe-108">Windows 用 Microsoft デバッグツールに必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="680fe-108">Provide the required information for the Microsoft Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="680fe-109">シンボルファイルに必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="680fe-109">Provide the required information for the symbol files.</span></span> <span data-ttu-id="680fe-110">シンボルファイルの詳細については、「 [Crash Analyzer がシンボルファイルにアクセスできるようにする方法](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="680fe-110">For more information about symbol files, see [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md).</span></span>

4.  <span data-ttu-id="680fe-111">メモリダンプファイルに必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="680fe-111">Provide the required information for a memory dump file.</span></span> <span data-ttu-id="680fe-112">メモリダンプファイルの場所を確認するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="680fe-112">To determine the location of the memory dump file:</span></span>

    1.  <span data-ttu-id="680fe-113">[**システムのプロパティ**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="680fe-113">Open the **System Properties** window.</span></span>

    2.  <span data-ttu-id="680fe-114">[**スタート**] をクリックし、 **sysdm.cpl**入力して、 **enter**キーを押します。</span><span class="sxs-lookup"><span data-stu-id="680fe-114">Click **Start**, type **sysdm.cpl**, and then press **Enter**.</span></span>

    3.  <span data-ttu-id="680fe-115">**[詳細設定]** タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="680fe-115">Click the **Advanced** tab.</span></span>

    4.  <span data-ttu-id="680fe-116">[**起動と回復**] 領域で、[**設定**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="680fe-116">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="680fe-117">[**システムのプロパティ**] ウィンドウにアクセスできない場合は、Microsoft 診断/回復ツールセット (DaRT) 10 の**検索**ツールを使用して、エンドユーザーのコンピューターでダンプファイルを検索することができます。</span><span class="sxs-lookup"><span data-stu-id="680fe-117">If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in Microsoft Diagnostics and Recovery Toolset (DaRT) 10.</span></span>

    <span data-ttu-id="680fe-118">**クラッシュアナライザー**は、メモリダンプファイルをスキャンし、問題の原因を報告します。</span><span class="sxs-lookup"><span data-stu-id="680fe-118">The **Crash Analyzer** scans the memory dump file and reports a probable cause of the problem.</span></span> <span data-ttu-id="680fe-119">エラーの詳細については、特定のメモリダンプメッセージと説明、エラーの発生時に読み込まれたドライバー、分析の完全な出力などを参照してください。</span><span class="sxs-lookup"><span data-stu-id="680fe-119">You can view more information about the failure, such as the specific memory dump message and description, the drivers loaded at the time of the failure, and the full output of the analysis.</span></span>

5.  <span data-ttu-id="680fe-120">問題を解決するための適切な戦略を特定します。</span><span class="sxs-lookup"><span data-stu-id="680fe-120">Identify the appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="680fe-121">この方法では、DaRT 10 の**コンピューター管理**ツールの [**サービスとドライバー** ] ノードを使用して、エラーの原因となったデバイスドライバーの無効化または更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="680fe-121">The strategy may require disabling or updating the device driver that caused the failure by using the **Services and Drivers** node of the **Computer Management** tool in DaRT 10.</span></span>

## <span data-ttu-id="680fe-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="680fe-122">Related topics</span></span>


[<span data-ttu-id="680fe-123">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="680fe-123">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="680fe-124">DaRT 10 の操作</span><span class="sxs-lookup"><span data-stu-id="680fe-124">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





