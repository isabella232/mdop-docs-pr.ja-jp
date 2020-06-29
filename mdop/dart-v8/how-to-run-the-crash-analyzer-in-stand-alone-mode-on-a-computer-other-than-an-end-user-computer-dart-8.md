---
title: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: b2f87144-6379-478a-802b-9cfef5242f34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ebd3c50c373ba9687a3b7fcbbf34e86bd07c6207
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824374"
---
# <span data-ttu-id="bc791-103">エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="bc791-103">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>


<span data-ttu-id="bc791-104">Windows 用 Microsoft デバッグツールまたはエンドユーザーコンピューター上のシンボルファイルにアクセスできない場合は、問題のあるコンピューターからダンプファイルをコピーして、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューター (Microsoft 診断/回復ツールセット (DaRT) 8.0 が含まれているヘルプデスクコンピューターなど) で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="bc791-104">If you cannot access the Microsoft Debugging Tools for Windows or the symbol files on the end-user computer, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a help desk computer that contains Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span>

<span data-ttu-id="bc791-105">Crash Analyzer をスタンドアロンモードで実行するには、問題のあるコンピューターからメモリダンプファイルをコピーして、**クラッシュアナライザー**がインストールされている別のコンピューター (ヘルプデスクコンピューターなど) で分析します。</span><span class="sxs-lookup"><span data-stu-id="bc791-105">To run Crash Analyzer in stand-alone mode, you copy the memory dump file from the problem computer and analyze it on another computer, such as a help desk computer, that has the **Crash Analyzer** installed.</span></span>

**<span data-ttu-id="bc791-106">スタンドアロンモードでクラッシュアナライザーを実行するには</span><span class="sxs-lookup"><span data-stu-id="bc791-106">To run the Crash Analyzer in stand-alone mode</span></span>**

1.  <span data-ttu-id="bc791-107">DaRT 8.0 がインストールされているコンピューターで、[**スタート**] をクリックし、「 **crash analyzer**」と入力して、[**クラッシュアナライザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="bc791-107">On a computer that has DaRT 8.0 installed, click **Start**, type **Crash Analyzer**, and then click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="bc791-108">「[エンドユーザーコンピューターでクラッシュアナライザーを実行する方法](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)」の説明に従って、ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="bc791-108">Follow the steps in the wizard, as described in [How to Run the Crash Analyzer on an End-user Computer](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md).</span></span>

## <span data-ttu-id="bc791-109">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bc791-109">Related topics</span></span>


[<span data-ttu-id="bc791-110">DaRT 8.0 の操作</span><span class="sxs-lookup"><span data-stu-id="bc791-110">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="bc791-111">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="bc791-111">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-8.md)

[<span data-ttu-id="bc791-112">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="bc791-112">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

 

 





