---
title: クラッシュ アナライザーを使用したシステム障害の診断
description: クラッシュ アナライザーを使用したシステム障害の診断
author: dansimp
ms.assetid: ce3d3186-54fb-45b2-b5ce-9bb7841db28f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: abb9d1ec99236199e0866a3b23219dd412bc9da6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824544"
---
# <span data-ttu-id="88fda-103">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="88fda-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="88fda-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 の**Crash Analyzer**を使用すると、Windows ベースのコンピューターでメモリダンプファイルをデバッグして、関連するコンピューターのエラーを診断することができます。</span><span class="sxs-lookup"><span data-stu-id="88fda-104">The **Crash Analyzer** in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 lets you debug a memory dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="88fda-105">**クラッシュアナライザー**は、Windows 用 Microsoft デバッグツールを使って、コンピューターに障害を引き起こしたドライバーのメモリダンプファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="88fda-105">The **Crash Analyzer** uses the Microsoft Debugging Tools for Windows to examine a memory dump file for the driver that caused the computer to fail.</span></span> <span data-ttu-id="88fda-106">Crash Analyzer は、エンドユーザーのコンピューターまたはエンドユーザーコンピューター以外のコンピューター上のスタンドアロンモードで実行できます。</span><span class="sxs-lookup"><span data-stu-id="88fda-106">You can run the Crash Analyzer on an end-user computer or in stand-alone mode on a computer other than an end-user computer.</span></span>

## <span data-ttu-id="88fda-107">エンドユーザーコンピューターで Crash Analyzer を実行する</span><span class="sxs-lookup"><span data-stu-id="88fda-107">Run the Crash Analyzer on an end-user-computer</span></span>


<span data-ttu-id="88fda-108">通常、問題が発生しているエンドユーザーコンピューターの [**診断/回復ツールセット**] ウィンドウから**クラッシュアナライザー**を実行します。</span><span class="sxs-lookup"><span data-stu-id="88fda-108">Typically, you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing the problem.</span></span> <span data-ttu-id="88fda-109">**クラッシュアナライザー**は、問題のあるコンピューター上の Windows 用デバッグツールを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="88fda-109">The **Crash Analyzer** tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="88fda-110">[ディレクトリパス] ダイアログボックスが空の場合は、場所を入力するか、Windows 用のデバッグツールの場所を参照する必要があります (Microsoft からファイルをダウンロードできます)。</span><span class="sxs-lookup"><span data-stu-id="88fda-110">If the directory path dialog box is empty, you must enter the location, or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="88fda-111">また、シンボルファイルが配置されている場所へのパスも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="88fda-111">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="88fda-112">DaRT 8.0 の回復イメージを作成したときに、Windows 用 Microsoft デバッグツールとシンボルファイルが含まれている場合、問題のあるコンピューターで**クラッシュアナライザー**を実行するときに、ツールとシンボルファイルを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="88fda-112">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT 8.0 recovery image, the Tools and symbol files should be available when you run the **Crash Analyzer** on the problem computer.</span></span> <span data-ttu-id="88fda-113">DaRT の回復イメージに含まれていない場合、または、ディスクサイズまたはネットワーク接続の問題によってそれらを取得できない場合は、次のセクションで説明するように、エンドユーザーのコンピューター以外のコンピューターでクラッシュアナライザーをスタンドアロンモードで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="88fda-113">If you did not include them in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, you can alternatively run the Crash Analyzer in stand-alone mode on a computer other than the end user’s computer, as described in the following section.</span></span>

[<span data-ttu-id="88fda-114">エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="88fda-114">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)

## <a href="" id="run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-s-computer"></a><span data-ttu-id="88fda-115">エンドユーザーのコンピューター以外のコンピューターで、Crash Analyzer をスタンドアロンモードで実行する</span><span class="sxs-lookup"><span data-stu-id="88fda-115">Run the Crash Analyzer in stand-alone mode on a computer other than an end user’s computer</span></span>


<span data-ttu-id="88fda-116">通常、問題が発生しているエンドユーザーのコンピューターで**クラッシュアナライザー**を実行しますが、スタンドアロンモードでは、エンドユーザーコンピューター以外のコンピューターでもクラッシュアナライザーを実行できます。</span><span class="sxs-lookup"><span data-stu-id="88fda-116">Although you typically run **Crash Analyzer** on the end-user computer that is experiencing the problem, you can also run the Crash Analyzer in stand-alone mode, on a computer other than an end-user computer.</span></span> <span data-ttu-id="88fda-117">DaRT 回復イメージに Windows デバッグツールが含まれていない場合や、ディスクサイズやネットワーク接続の問題により、デバッグツールを取得できない場合は、このオプションを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="88fda-117">You might choose this option if you did not include the Windows Debugging Tools in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining the Debugging Tools.</span></span> <span data-ttu-id="88fda-118">この場合、問題のあるコンピューターからダンプファイルをコピーして、スタンドアロンバージョンの**Crash Analyzer**がインストールされているコンピューター (ヘルプデスクエージェントのコンピューターなど) で分析することができます。</span><span class="sxs-lookup"><span data-stu-id="88fda-118">In this case, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of **Crash Analyzer** installed, such as on a help desk agent’s computer.</span></span>

[<span data-ttu-id="88fda-119">エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="88fda-119">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-8.md)

## <span data-ttu-id="88fda-120">クラッシュアナライザーがシンボルファイルにアクセスできることを確認する方法</span><span class="sxs-lookup"><span data-stu-id="88fda-120">How to ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="88fda-121">応答を停止したアプリケーションをデバッグするには、プログラムとは別のシンボルファイルへのアクセスが必要です。</span><span class="sxs-lookup"><span data-stu-id="88fda-121">To debug applications that have stopped responding, you need access to the symbol file, which is separate from the program.</span></span> <span data-ttu-id="88fda-122">クラッシュアナライザーを実行すると、シンボルファイルは自動的にダウンロードされますが、問題のあるコンピューターがインターネットにアクセスできない場合があります。</span><span class="sxs-lookup"><span data-stu-id="88fda-122">Although symbol files are automatically downloaded when you run Crash Analyzer, there might be times when the problem computer does not have access to the Internet.</span></span> <span data-ttu-id="88fda-123">シンボルファイルへのアクセスが保証されるようにするには、いくつかの方法があります。</span><span class="sxs-lookup"><span data-stu-id="88fda-123">There are several ways to ensure that you have guaranteed access to symbol files.</span></span>

[<span data-ttu-id="88fda-124">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="88fda-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

## <span data-ttu-id="88fda-125">クラッシュアナライザーによるシステム障害の診断に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="88fda-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="88fda-126">DaRT 8.0 の操作</span><span class="sxs-lookup"><span data-stu-id="88fda-126">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

 

 




