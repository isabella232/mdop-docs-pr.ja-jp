---
title: クラッシュ アナライザーを使用したシステム障害の診断
description: クラッシュ アナライザーを使用したシステム障害の診断
author: dansimp
ms.assetid: 170d40ef-4edb-4a32-a349-c285c0ea5e56
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c5f8b7e189de024d7ceb84f8cfc151dc82d56ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823467"
---
# <span data-ttu-id="d1975-103">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="d1975-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="d1975-104">Microsoft 診断/回復ツールセット (DaRT) 7 の Crash Analyzer を使用すると、Windows ベースのコンピューターでクラッシュダンプファイルをデバッグして、関連するコンピューターのエラーを診断することができます。</span><span class="sxs-lookup"><span data-stu-id="d1975-104">The Crash Analyzer in Microsoft Diagnostics and Recovery Toolset (DaRT)7 lets you debug a crash dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="d1975-105">クラッシュアナライザーは、Windows 用 Microsoft デバッグツールを使って、コンピューターの障害の原因となったドライバーのクラッシュダンプファイルを調べます。</span><span class="sxs-lookup"><span data-stu-id="d1975-105">The Crash Analyzer uses the Microsoft Debugging Tools for Windows to examine a crash dump file for the driver that caused the computer to fail.</span></span>

## <span data-ttu-id="d1975-106">エンドユーザーのコンピューターでクラッシュアナライザーを実行する</span><span class="sxs-lookup"><span data-stu-id="d1975-106">Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="d1975-107">通常、問題が発生しているエンドユーザーコンピューターの [診断/回復ツールセット] ウィンドウでクラッシュアナライザーを実行します。</span><span class="sxs-lookup"><span data-stu-id="d1975-107">Typically, you run Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="d1975-108">クラッシュアナライザーは、問題のあるコンピューター上の Windows 用デバッグツールを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="d1975-108">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="d1975-109">[ディレクトリパス] ダイアログボックスが空の場合は、場所を入力するか、Windows 用のデバッグツールの場所 (Microsoft からファイルをダウンロードできます) を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-109">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="d1975-110">また、シンボルファイルが配置されている場所へのパスも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-110">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="d1975-111">DaRT 回復イメージを作成したときに、Windows 用 Microsoft デバッグツールとシンボルファイルが含まれていた場合は、問題のあるコンピューターでクラッシュアナライザーを実行するときに、これらのツールを使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-111">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, they should be available when you run the Crash Analyzer on the problem computer.</span></span>

[<span data-ttu-id="d1975-112">エンドユーザーのコンピューターでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="d1975-112">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-7.md)

## <span data-ttu-id="d1975-113">エンドユーザーコンピューター以外のコンピューターで Crash Analyzer をスタンドアロンモードで実行する</span><span class="sxs-lookup"><span data-stu-id="d1975-113">Run the Crash Analyzer in stand-alone mode on a computer other than an end-user computer</span></span>


<span data-ttu-id="d1975-114">クラッシュアナライザーは、問題のあるコンピューター上の Windows 用デバッグツールを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="d1975-114">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="d1975-115">[ディレクトリパス] ダイアログボックスが空の場合は、場所を入力するか、Windows 用のデバッグツールの場所 (Microsoft からファイルをダウンロードできます) を参照する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-115">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="d1975-116">また、シンボルファイルが配置されている場所へのパスも指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-116">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="d1975-117">DaRT 回復イメージの作成時に、Windows 用の Microsoft デバッグツールとシンボルファイルが含まれていない場合、または、ディスクサイズまたはネットワーク接続の問題によって、それらを取得できない場合は、問題のコンピューターからダンプファイルをコピーし、スタンドアロンバージョンの Crash Analyzer がインストールされているコンピューターで分析します。(ヘルプデスクの管理者のコンピューターなど)。</span><span class="sxs-lookup"><span data-stu-id="d1975-117">If you did not include the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, then you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

[<span data-ttu-id="d1975-118">エンドユーザーのコンピューター以外のコンピューターでスタンドアロン モードでクラッシュ アナライザーを実行する方法</span><span class="sxs-lookup"><span data-stu-id="d1975-118">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-7.md)

## <span data-ttu-id="d1975-119">クラッシュアナライザーがシンボルファイルにアクセスできることを確認する</span><span class="sxs-lookup"><span data-stu-id="d1975-119">Ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="d1975-120">通常、デバッグ情報は、実行可能ファイルとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="d1975-120">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="d1975-121">応答を停止したアプリケーションをデバッグするとき (たとえば、クラッシュした場合)、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d1975-121">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="d1975-122">クラッシュアナライザーを実行すると、シンボルファイルが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="d1975-122">Symbol files are automatically downloaded when you run Crash Analyzer.</span></span> <span data-ttu-id="d1975-123">コンピューターがインターネットに接続されていない場合、またはネットワークでコンピューターが HTTP プロキシサーバーにアクセスする必要がある場合、シンボルファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="d1975-123">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

[<span data-ttu-id="d1975-124">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="d1975-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)

## <span data-ttu-id="d1975-125">クラッシュアナライザーによるシステム障害の診断に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="d1975-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="d1975-126">DaRT 7.0 の操作</span><span class="sxs-lookup"><span data-stu-id="d1975-126">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





