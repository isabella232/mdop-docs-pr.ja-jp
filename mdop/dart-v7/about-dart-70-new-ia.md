---
title: DaRT 7.0 について
description: DaRT 7.0 について
author: dansimp
ms.assetid: 217ffafc-6d73-4b80-88d9-71870460d4ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cd647b2f596ce88ce38580f08422ff8f92b35c06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823274"
---
# <span data-ttu-id="fa1df-103">DaRT 7.0 について</span><span class="sxs-lookup"><span data-stu-id="fa1df-103">About DaRT 7.0</span></span>


<span data-ttu-id="fa1df-104">Microsoft 診断/回復ツールセット (DaRT) 7 を使用すると、Windows ベースのデスクトップのトラブルシューティングと修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 helps you troubleshoot and repair Windows-based desktops.</span></span> <span data-ttu-id="fa1df-105">これには、開始できないデスクトップも含まれます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-105">This includes those desktops that cannot be started.</span></span> <span data-ttu-id="fa1df-106">DaRT は、Windows 回復環境 (WinRE) を拡張するための強力なツールセットです。</span><span class="sxs-lookup"><span data-stu-id="fa1df-106">DaRT is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="fa1df-107">DaRT を使用することで、問題を分析して、たとえばコンピューターのイベントログやシステムレジストリを調べることで、その原因を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span>

<span data-ttu-id="fa1df-108">DaRT には、原因を特定した後すぐに問題を解決するためのツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="fa1df-108">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="fa1df-109">たとえば、DaRT のツールを使用すると、インストールされている Windows オペレーティングシステムを起動できないか、起動しない場合でも、問題のあるデバイスドライバーを無効にしたり、ホットフィックスを削除したり、削除したファイルを復元したり、コンピューターをマルウェアでスキャンしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-109">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="fa1df-110">DaRT は、32ビットまたは64ビットのいずれかのバージョンの Windows 7 を実行しているコンピューターをすばやく回復するのに役立ちます。通常は、コンピュータを再イメージした場合よりも短時間で行われます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-110">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 7, typically in less time than it would take to reimage the computer.</span></span>

## <span data-ttu-id="fa1df-111">DaRT 7 のリカバリイメージについて</span><span class="sxs-lookup"><span data-stu-id="fa1df-111">About the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="fa1df-112">DaRT の機能により、統合された WinRE と、DaRT が提供する一連のツールとの統合に基づいた回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-112">Functionality in DaRT lets you create a recovery image that is based on WinRE combined with a set of tools that DaRT provides.</span></span> <span data-ttu-id="fa1df-113">DaRT リカバリ画像は WinRE を活用します。これにより、**診断/回復ツールセット**のウィンドウにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-113">The DaRT recovery image takes advantage of WinRE, from which you can access the **Diagnostics and Recovery Toolset** window.</span></span>

<span data-ttu-id="fa1df-114">Dart リカバリ**画像ウィザード**を使用して、dart リカバリ画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="fa1df-114">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="fa1df-115">既定では、ウィザードによって、DaRT70 という名前の国際的な標準化機構 (ISO) 画像ファイルがデスクトップ上に作成されますが、別の場所とファイル名を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-115">By default, the wizard creates an International Organization for Standardization (ISO) image file on your desktop that is named DaRT70.iso, although you can specify a different location and file name.</span></span> <span data-ttu-id="fa1df-116">ウィザードでは、画像を CD または DVD に書き込むこともできます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-116">The wizard also lets you burn the image to a CD or DVD.</span></span> <span data-ttu-id="fa1df-117">ウィザードが完了したら、USB フラッシュドライブに回復イメージを保存するか、リモートパーティションまたは回復パーティションの作成に使用できる形式で保存することができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-117">After you have finished the wizard, you can save the recovery image to a USB flash drive or save it in a format that you can use to create a remote partition or a recovery partition.</span></span>

<span data-ttu-id="fa1df-118">DaRT を使用してエンドユーザーのコンピューターを起動する必要がある場合は、「 [Dart 回復イメージを使用してローカルコンピューターを回復する方法](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)」の指示に従ってください。</span><span class="sxs-lookup"><span data-stu-id="fa1df-118">When you have to use DaRT to startup an end-user computer that will not start, you can follow the instructions at [How to Recover Local Computers Using the DaRT Recovery Image](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="fa1df-119">DaRT のツールについて詳しくは、「 [dart 7.0 でのツールの概要](overview-of-the-tools-in-dart-70-new-ia.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="fa1df-119">For detailed information about the tools in DaRT, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

## <a href="" id="what-s-new-in-dart-7"></a><span data-ttu-id="fa1df-120">DaRT 7 の新機能</span><span class="sxs-lookup"><span data-stu-id="fa1df-120">What’s New in DaRT 7</span></span>


<span data-ttu-id="fa1df-121">DaRT7 は、以前のバージョンに含まれているすべてのシナリオを引き続きサポートし、3つの新しい展開オプションに加えて、新しいリモート接続機能も追加します。</span><span class="sxs-lookup"><span data-stu-id="fa1df-121">DaRT7 continues to support all the scenarios included in previous versions and it adds a new Remote Connection feature in addition to three new deployment options.</span></span>

### <span data-ttu-id="fa1df-122">DaRT 7 イメージの作成</span><span class="sxs-lookup"><span data-stu-id="fa1df-122">DaRT 7 Image Creation</span></span>

<span data-ttu-id="fa1df-123">DaRT ISO 画像の作成に使用するウィザードは、現在**Dart 回復イメージ**と呼ばれており、新しいリモート接続機能を有効または無効にするオプションがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="fa1df-123">The wizard that you use to create DaRT ISO images is now called **DaRT Recovery Image** and it now supports an option to enable or disable the new Remote Connection feature.</span></span> <span data-ttu-id="fa1df-124">リモート接続を使うと、ヘルプデスクエージェントは、リモートの場所から DaRT ツールを実行できます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-124">Remote Connection lets a helpdesk agent run the DaRT tools from a remote location.</span></span> <span data-ttu-id="fa1df-125">以前のリリースでは、DaRT ツールを実行するために、ヘルプデスクエージェントがエンドユーザーのコンピューターに物理的に存在している必要がありました。</span><span class="sxs-lookup"><span data-stu-id="fa1df-125">In previous releases, the helpdesk agent had to be physically present at the end-user computer to run the DaRT tools.</span></span>

<span data-ttu-id="fa1df-126">ウィザードでは、リモート接続機能のウェルカムメッセージをカスタマイズすることもできます (メッセージは、エンドユーザーがリモート接続ツールを実行したときに表示されます)。</span><span class="sxs-lookup"><span data-stu-id="fa1df-126">The wizard also lets you customize the Welcome message for the Remote Connection feature (the message is shown when end users run the Remote Connection tool).</span></span> <span data-ttu-id="fa1df-127">IT 管理者は、リモート接続で使うポート番号を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-127">IT Admins can also configure which Port Number should be used by Remote Connection.</span></span>

<span data-ttu-id="fa1df-128">**Dart リカバリイメージウィザード**またはリモート接続の詳細については、「 [Dart 7.0 リカバリイメージの作成](creating-the-dart-70-recovery-image-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa1df-128">For more information about the **DaRT Recovery Image Wizard** or Remote Connection, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="fa1df-129">DaRT 7 ISO 展開</span><span class="sxs-lookup"><span data-stu-id="fa1df-129">DaRT 7 ISO Deployment</span></span>

<span data-ttu-id="fa1df-130">DaRT7 では、CD または DVD への書き込みに加えて、DaRT の回復イメージを含む ISO を展開すると、次の3つの新しいオプションが追加されます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-130">In addition to burning to a CD or DVD, DaRT7 adds three new options when you deploy the ISO that contains the DaRT recovery image:</span></span>

-   <span data-ttu-id="fa1df-131">USB フラッシュドライブの展開</span><span class="sxs-lookup"><span data-stu-id="fa1df-131">USB flash drive deployment</span></span>

-   <span data-ttu-id="fa1df-132">リモートパーティションの展開</span><span class="sxs-lookup"><span data-stu-id="fa1df-132">Remote partition deployment</span></span>

-   <span data-ttu-id="fa1df-133">回復パーティションの展開</span><span class="sxs-lookup"><span data-stu-id="fa1df-133">Recovery partition deployment</span></span>

<span data-ttu-id="fa1df-134">[USB フラッシュドライブの展開] オプションを使用すると、CD または DVD ドライブを使用していないコンピューターでも DaRT を使用できます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-134">The USB flash drive deployment option lets a company use DaRT on computers that do not have CD or DVD drives available.</span></span> <span data-ttu-id="fa1df-135">回復とリモートパーティションオプションを使用すると、エンドユーザーは DaRT イメージに簡単にアクセスでき、リモート接続機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="fa1df-135">The recovery and remote partition options let end users have easy access to the DaRT image and to enable the Remote Connection functionality.</span></span>

<span data-ttu-id="fa1df-136">DaRT リカバリイメージの展開方法の詳細については、「 [dart 7.0 リカバリイメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fa1df-136">For more information about how to deploy DaRT recovery images, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="fa1df-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fa1df-137">Related topics</span></span>


[<span data-ttu-id="fa1df-138">DaRT 7.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="fa1df-138">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)

[<span data-ttu-id="fa1df-139">DaRT 7.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="fa1df-139">Release Notes for DaRT 7.0</span></span>](release-notes-for-dart-70-new-ia.md)

 

 





