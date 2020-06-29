---
title: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
description: エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法
author: dansimp
ms.assetid: 27c1e1c6-123a-4f8a-b7d2-5bddc9ca3249
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 485823c17d650323ca68cccf1308ac8ec9e5212b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822584"
---
# <span data-ttu-id="3e97c-103">エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="3e97c-103">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>


<span data-ttu-id="3e97c-104">Windows 用 Microsoft デバッグツールまたはエンドユーザーコンピューター上のシンボルファイルにアクセスできない場合は、問題のあるコンピューターからダンプファイルをコピーして、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューター (Microsoft 診断/回復ツールセット (DaRT) 10 を含むヘルプデスクコンピューターなど) で分析できます。</span><span class="sxs-lookup"><span data-stu-id="3e97c-104">If you cannot access the Microsoft Debugging Tools for Windows or the symbol files on the end-user computer, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a help desk computer that contains Microsoft Diagnostics and Recovery Toolset (DaRT) 10.</span></span>

<span data-ttu-id="3e97c-105">Crash Analyzer をスタンドアロンモードで実行するには、問題のあるコンピューターからメモリダンプファイルをコピーして、**クラッシュアナライザー**がインストールされている別のコンピューター (ヘルプデスクコンピューターなど) で分析します。</span><span class="sxs-lookup"><span data-stu-id="3e97c-105">To run Crash Analyzer in stand-alone mode, you copy the memory dump file from the problem computer and analyze it on another computer, such as a help desk computer, that has the **Crash Analyzer** installed.</span></span>

**<span data-ttu-id="3e97c-106">スタンドアロンモードでクラッシュアナライザーを実行するには</span><span class="sxs-lookup"><span data-stu-id="3e97c-106">To run the Crash Analyzer in stand-alone mode</span></span>**

1.  <span data-ttu-id="3e97c-107">DaRT 10 がインストールされているコンピューターで、[**スタート**] をクリックし、「 **crash analyzer**」と入力して、[**クラッシュアナライザー**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e97c-107">On a computer that has DaRT 10 installed, click **Start**, type **Crash Analyzer**, and then click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="3e97c-108">「[エンドユーザーコンピューターでクラッシュアナライザーを実行する方法](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-10.md)」の説明に従って、ウィザードの手順に従います。</span><span class="sxs-lookup"><span data-stu-id="3e97c-108">Follow the steps in the wizard, as described in [How to Run the Crash Analyzer on an End-user Computer](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-10.md).</span></span>

## <span data-ttu-id="3e97c-109">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3e97c-109">Related topics</span></span>


[<span data-ttu-id="3e97c-110">DaRT 10 の操作</span><span class="sxs-lookup"><span data-stu-id="3e97c-110">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

[<span data-ttu-id="3e97c-111">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="3e97c-111">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="3e97c-112">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="3e97c-112">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)

 

 





