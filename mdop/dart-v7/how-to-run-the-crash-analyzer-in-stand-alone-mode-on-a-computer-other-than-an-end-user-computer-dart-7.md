---
title: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822787"
---
# <span data-ttu-id="10510-103">エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="10510-103">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>


<span data-ttu-id="10510-104">Windows 用 Microsoft デバッグツールまたはエンドユーザーコンピューター上のシンボルファイルにアクセスできない場合は、問題のあるコンピューターからダンプファイルをコピーし、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューター (ヘルプデスクの管理者のコンピューターなど) で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="10510-104">If you cannot access the Microsoft Debugging Tools for Windows or the symbol files on the end-user computer, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

**<span data-ttu-id="10510-105">スタンドアロンモードでクラッシュアナライザーを実行するには</span><span class="sxs-lookup"><span data-stu-id="10510-105">To run the Crash Analyzer in stand-alone mode</span></span>**

1.  <span data-ttu-id="10510-106">DaRT7 がインストールされているコンピューターで、[すべてのプログラムを**起動**する  /  **All Programs**  /  **Microsoft DaRT 7**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="10510-106">On a computer with DaRT7 installed, click **Start** / **All Programs** / **Microsoft DaRT 7**.</span></span>

2.  <span data-ttu-id="10510-107">次の項目に必要な情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="10510-107">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="10510-108">Windows 用 Microsoft デバッグツール</span><span class="sxs-lookup"><span data-stu-id="10510-108">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="10510-109">シンボルファイル</span><span class="sxs-lookup"><span data-stu-id="10510-109">Symbol files</span></span>

        <span data-ttu-id="10510-110">シンボルファイルの詳細については、「 [Crash Analyzer がシンボルファイルにアクセスできることを確認する方法](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10510-110">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="10510-111">クラッシュダンプファイル</span><span class="sxs-lookup"><span data-stu-id="10510-111">A crash dump file</span></span>

        <span data-ttu-id="10510-112">**注** DaRT7 の検索ツールを使用して、コピーしたクラッシュダンプファイルを特定します。</span><span class="sxs-lookup"><span data-stu-id="10510-112">**Note** Use the Search tool in DaRT7 to locate the copied crash dump file.</span></span>

         

3.  <span data-ttu-id="10510-113">クラッシュ**ダンプファイルがスキャンさ**れ、クラッシュの原因と思われるエラーが報告されます。</span><span class="sxs-lookup"><span data-stu-id="10510-113">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="10510-114">クラッシュの詳細については、具体的なクラッシュメッセージと説明、クラッシュの発生時に読み込まれたドライバー、分析の完全な出力などを参照してください。</span><span class="sxs-lookup"><span data-stu-id="10510-114">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="10510-115">問題を解決するための適切な戦略を決定します。</span><span class="sxs-lookup"><span data-stu-id="10510-115">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="10510-116">これには、DaRT の**コンピューター管理**ツールの [**サービスとドライバー** ] ノードを使用して、クラッシュの原因となったデバイスドライバーの無効化または更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="10510-116">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="10510-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="10510-117">Related topics</span></span>


[<span data-ttu-id="10510-118">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="10510-118">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





