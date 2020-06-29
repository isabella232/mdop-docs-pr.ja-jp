---
title: DaRT 7.0 の回復イメージの作成計画
description: DaRT 7.0 の回復イメージの作成計画
author: dansimp
ms.assetid: e5d49bee-ae4e-467b-9976-c1203f6355f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c370d2a69ec8ccea217696045e64e9a0ae724815
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821334"
---
# <span data-ttu-id="30dfb-103">DaRT 7.0 の回復イメージの作成計画</span><span class="sxs-lookup"><span data-stu-id="30dfb-103">Planning to Create the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="30dfb-104">Microsoft 診断/回復ツールセット (DaRT) 7 の回復イメージを作成する計画がある場合は、このセクションの情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30dfb-104">Use the information in this section when you plan for creating the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="30dfb-105">DaRT 7 の回復イメージの作成を計画する</span><span class="sxs-lookup"><span data-stu-id="30dfb-105">Planning to Create the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="30dfb-106">DaRT リカバリ画像を作成する場合は、イメージに含めるツールを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dfb-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="30dfb-107">この決定を行うときは、さまざまな DaRT ツールへのアクセス権がエンドユーザーによって異なる可能性があることを覚えておいてください。</span><span class="sxs-lookup"><span data-stu-id="30dfb-107">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="30dfb-108">DaRT ツールの詳細については、「 [dart 7.0 でのツールの概要](overview-of-the-tools-in-dart-70-new-ia.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30dfb-108">For more information about the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span> <span data-ttu-id="30dfb-109">セキュリティで保護された回復イメージの作成に役立つ詳細については、「 [DaRT 7.0 のセキュリティに関する考慮事項](security-considerations-for-dart-70-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30dfb-109">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 7.0](security-considerations-for-dart-70-dart-7.md).</span></span>

<span data-ttu-id="30dfb-110">DaRT リカバリ画像を作成する場合は、追加のドライバまたはファイルを含めるかどうかも指定します。</span><span class="sxs-lookup"><span data-stu-id="30dfb-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="30dfb-111">DaRT リカバリ画像に含める追加のドライバーまたはファイルの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="30dfb-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

## <span data-ttu-id="30dfb-112">前提条件</span><span class="sxs-lookup"><span data-stu-id="30dfb-112">Prerequisites</span></span>


<span data-ttu-id="30dfb-113">DaRT リカバリ画像を作成するには、次の項目が必要または推奨されます。</span><span class="sxs-lookup"><span data-stu-id="30dfb-113">The following items are required or recommended for creating the DaRT recovery image:</span></span>

-   <span data-ttu-id="30dfb-114">Windows 7 のソースファイル</span><span class="sxs-lookup"><span data-stu-id="30dfb-114">Windows 7 source files</span></span>

    <span data-ttu-id="30dfb-115">Windows 7 DVD または Windows 7 のソースファイルのパスを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dfb-115">You must provide the path of a Windows 7 DVD or of Windows 7 source files.</span></span> <span data-ttu-id="30dfb-116">DaRT 回復イメージを作成するには、Windows 7 のソースファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="30dfb-116">Windows 7 source files are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="30dfb-117">プラットフォーム用の Windows デバッグツール</span><span class="sxs-lookup"><span data-stu-id="30dfb-117">Windows Debugging Tools for your platform</span></span>

    <span data-ttu-id="30dfb-118">**クラッシュアナライザー**を実行して、コンピューターがクラッシュした原因を特定するには、Windows デバッグツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="30dfb-118">Windows Debugging Tools are required when you run **Crash Analyzer** to determine the cause of a computer crash.</span></span> <span data-ttu-id="30dfb-119">DaRT リカバリ画像を作成するときに、Windows のデバッグツールのパスを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="30dfb-119">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="30dfb-120">必要に応じて、Windows デバッグツールをダウンロードできます。 [windows 用のデバッグツールをダウンロードしてインストール](https://go.microsoft.com/fwlink/?LinkId=99934)します。</span><span class="sxs-lookup"><span data-stu-id="30dfb-120">If it is necessary, you can download the Windows Debugging Tools here: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

-   <span data-ttu-id="30dfb-121">オプション:**単体システム Sweeper**定義</span><span class="sxs-lookup"><span data-stu-id="30dfb-121">Optional: **Standalone System Sweeper** definitions</span></span>

    <span data-ttu-id="30dfb-122">このツールを実行するときには、**スタンドアロンシステム Sweeper**の最新の定義が必要です。</span><span class="sxs-lookup"><span data-stu-id="30dfb-122">The latest definitions for the **Standalone System Sweeper** are required when you run this tool.</span></span> <span data-ttu-id="30dfb-123">**スタンドアロンシステム Sweeper**を実行するときに定義をダウンロードすることもできますが、DaRT 回復イメージを作成するときに最新の定義をダウンロードすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="30dfb-123">Although you can download the definitions when you run **Standalone System Sweeper**, we recommend that you download the latest definitions at the time you create the DaRT recovery image.</span></span> <span data-ttu-id="30dfb-124">この方法でも、問題のあるコンピューターにネットワーク接続がない場合でも、最新の定義を使用してツールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="30dfb-124">In this manner, you can still run the tool with the latest definitions even if the problem computer does not have network connectivity.</span></span>

-   <span data-ttu-id="30dfb-125">オプション: **Crash Analyzer**で使用する Windows のシンボルファイル</span><span class="sxs-lookup"><span data-stu-id="30dfb-125">Optional: Windows symbols files for use with **Crash Analyzer**</span></span>

    <span data-ttu-id="30dfb-126">通常、デバッグ情報は、実行可能ファイルとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="30dfb-126">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="30dfb-127">応答を停止したアプリケーションをデバッグするとき (たとえば、クラッシュした場合)、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="30dfb-127">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span> <span data-ttu-id="30dfb-128">詳細については、「[クラッシュアナライザーによるシステム障害の診断](diagnosing-system-failures-with-crash-analyzer--dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="30dfb-128">For more information, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md).</span></span>

## <span data-ttu-id="30dfb-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="30dfb-129">Related topics</span></span>


[<span data-ttu-id="30dfb-130">DaRT 7.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="30dfb-130">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





