---
title: DaRT 8.0 について
description: DaRT 8.0 について
author: dansimp
ms.assetid: ce91efd6-7d78-44cb-bb8f-1f43f768ebaa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e70816425dc4775b11596b91d7b5c0045830c6ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821284"
---
# <span data-ttu-id="fe268-103">DaRT 8.0 について</span><span class="sxs-lookup"><span data-stu-id="fe268-103">About DaRT 8.0</span></span>


<span data-ttu-id="fe268-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 を使用すると、Windows ベースのコンピューターのトラブルシューティングと修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="fe268-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 helps you troubleshoot and repair Windows-based computers.</span></span> <span data-ttu-id="fe268-105">これには、開始できないコンピューターも含まれます。</span><span class="sxs-lookup"><span data-stu-id="fe268-105">This includes those computers that cannot be started.</span></span> <span data-ttu-id="fe268-106">DaRT 8.0 は、Windows 回復環境 (WinRE) を拡張するための強力なツールセットです。</span><span class="sxs-lookup"><span data-stu-id="fe268-106">DaRT 8.0 is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="fe268-107">DaRT を使用することで、問題を分析して、たとえばコンピューターのイベントログやシステムレジストリを調べることで、その原因を特定することができます。</span><span class="sxs-lookup"><span data-stu-id="fe268-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span> <span data-ttu-id="fe268-108">DaRT は、プライマリパーティションや論理ドライブなどのパーティションを含む基本的なハードディスクの回復とボリュームの回復をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="fe268-108">DaRT supports the recovery of basic hard disks that contain partitions, for example, primary partitions and logical drives, and supports the recovery of volumes.</span></span>

<span data-ttu-id="fe268-109">**注** DaRT は、ダイナミックディスクの回復をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="fe268-109">**Note** DaRT does not support the recovery of dynamic disks.</span></span>

 

<span data-ttu-id="fe268-110">DaRT には、原因を特定した後すぐに問題を解決するためのツールも用意されています。</span><span class="sxs-lookup"><span data-stu-id="fe268-110">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="fe268-111">たとえば、DaRT のツールを使用すると、インストールされている Windows オペレーティングシステムを起動できないか、起動しない場合でも、問題のあるデバイスドライバーを無効にしたり、ホットフィックスを削除したり、削除したファイルを復元したり、コンピューターをマルウェアでスキャンしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="fe268-111">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="fe268-112">DaRT は、32ビットバージョンまたは64ビットバージョンの Windows 8 を実行しているコンピューターをすばやく回復するのに役立ちます。通常は、コンピュータを再イメージした場合よりも短時間で完了します。</span><span class="sxs-lookup"><span data-stu-id="fe268-112">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span>

<span data-ttu-id="fe268-113">DaRT の機能により、回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fe268-113">Functionality in DaRT lets you create a recovery image.</span></span> <span data-ttu-id="fe268-114">回復イメージは Windows 回復環境 (Windows RE) を起動します。これにより、**診断と回復のツールセット**ウィンドウを開始して、DaRT ツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="fe268-114">The recovery image starts Windows Recovery Environment (Windows RE), from which you can start the **Diagnostics and Recovery Toolset** window and access the DaRT tools.</span></span>

<span data-ttu-id="fe268-115">Dart リカバリ**画像ウィザード**を使用して、dart リカバリ画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="fe268-115">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="fe268-116">既定では、ウィザードは国際標準化機構 (ISO) 画像ファイルと Windows Imaging 形式 (WIM) ファイルを作成し、CD、DVD、または USB にイメージを書き込みます。</span><span class="sxs-lookup"><span data-stu-id="fe268-116">By default, the wizard creates an International Organization for Standardization (ISO) image file and a Windows Imaging Format (WIM) file and let you burn the image to a CD, DVD, or USB.</span></span> <span data-ttu-id="fe268-117">イメージは、エンドユーザーのコンピューターにローカルで展開することも、ローカルのハードドライブのリモートネットワークパーティションまたは回復パーティションから展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe268-117">You can deploy the image locally at end user’s computers, or you can deploy it from a remote network partition or a recovery partition on the local hard drive.</span></span>

## <a href="" id="what-s-new-in-dart-8-0"></a><span data-ttu-id="fe268-118">DaRT 8.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="fe268-118">What’s new in DaRT 8.0</span></span>


<span data-ttu-id="fe268-119">DaRT 8.0 は、32ビットバージョンまたは64ビットバージョンの Windows 8 を実行しているコンピューターをすばやく回復するのに役立ちます。通常、コンピューターの再起動にかかる時間よりも短い時間がかかります。</span><span class="sxs-lookup"><span data-stu-id="fe268-119">DaRT 8.0 can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span> <span data-ttu-id="fe268-120">DaRT 8.0 には次の新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="fe268-120">DaRT 8.0 has the following new features.</span></span>

### <span data-ttu-id="fe268-121">Windows 8 または Windows Server 2012 を使用して DaRT イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="fe268-121">Create DaRT images by using Windows 8 or Windows Server 2012</span></span>

<span data-ttu-id="fe268-122">DaRT 8.0 では、Windows®8または Windows Server®2012を使って DaRT 画像を作成することができます。</span><span class="sxs-lookup"><span data-stu-id="fe268-122">DaRT 8.0 enables you to create DaRT images using either Windows® 8 or Windows Server® 2012.</span></span> <span data-ttu-id="fe268-123">Windows 8 と Windows Server 2012 より前のバージョンの Windows の場合、お客様は以前のバージョンの DaRT を引き続き使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe268-123">For versions of Windows earlier than Windows 8 and Windows Server 2012, customers should continue to use earlier versions of DaRT.</span></span>

### <span data-ttu-id="fe268-124">1台のコンピューターから32と64ビットの両方の画像を生成する</span><span class="sxs-lookup"><span data-stu-id="fe268-124">Generate both 32- and 64-bit images from one computer</span></span>

<span data-ttu-id="fe268-125">DaRT 8.0 を使用すると、コンピューターが32または64ビットコンピュータかどうかに関係なく、DaRT を実行している1台のコンピュータから32ビットと64ビットの両方の画像を生成できます。</span><span class="sxs-lookup"><span data-stu-id="fe268-125">DaRT 8.0 enables you to generate both 32-bit and 64-bit images from a single computer that is running DaRT, regardless of whether the computer is a 32-bit or 64-bit computer.</span></span> <span data-ttu-id="fe268-126">DaRT7 では、作成された画像は、DaRT を実行しているコンピューターと同じビットである必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe268-126">In DaRT7, the image that was created had to be the same, bit-wise, as the computer that was running DaRT.</span></span>

### <span data-ttu-id="fe268-127">BIOS または UEFI インターフェイスのいずれかを使用しているコンピューターをサポートする1つの画像を作成する</span><span class="sxs-lookup"><span data-stu-id="fe268-127">Create one image that supports computers that have either a BIOS or UEFI interface</span></span>

<span data-ttu-id="fe268-128">統合された拡張ファームウェアインターフェイス (UEFI) と BIOS インターフェイスの両方に対する DaRT 8.0 のサポートでは、いずれかのインターフェイスを備えたコンピューターで動作する1つの画像のみを作成できます。</span><span class="sxs-lookup"><span data-stu-id="fe268-128">DaRT 8.0’s support for both the Unified Extensible Firmware Interface (UEFI) and BIOS interfaces enables you to create just one image that works with computers that have either interface.</span></span>

### <span data-ttu-id="fe268-129">パーティション分割に GUID パーティションテーブル (GPT) を使用する</span><span class="sxs-lookup"><span data-stu-id="fe268-129">Use a GUID partition table (GPT) for partitioning</span></span>

<span data-ttu-id="fe268-130">DaRT 8.0 ツールでは、Windows 8 GPT ディスクがサポートされるようになりました。これにより、従来のマスターブートレコード (MBR) のパーティション構成よりも、ディスクをパーティション化するためのより柔軟なメカニズムが提供されます。</span><span class="sxs-lookup"><span data-stu-id="fe268-130">DaRT 8.0 tools now support Windows 8 GPT disks, which provide a more flexible mechanism for partitioning disks than the older master boot record (MBR) partitioning scheme.</span></span> <span data-ttu-id="fe268-131">DaRT 8.0 ツールは、引き続き MBR のパーティショニングをサポートします。</span><span class="sxs-lookup"><span data-stu-id="fe268-131">DaRT 8.0 tools continue to support MBR partitioning.</span></span>

### <span data-ttu-id="fe268-132">Windows 8 と Windows Server 2012 をローカルのハードディスクにインストールする</span><span class="sxs-lookup"><span data-stu-id="fe268-132">Install Windows 8 and Windows Server 2012 on the local hard disk</span></span>

<span data-ttu-id="fe268-133">DaRT 8.0 ツールは、Windows 8 と Windows Server 2012 がローカルのハードディスクにインストールされている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fe268-133">DaRT 8.0 tools can be used only when Windows 8 and Windows Server 2012 are installed on the local hard disk.</span></span> <span data-ttu-id="fe268-134">現時点では、Windows To Go はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="fe268-134">Currently, there is no support for Windows To Go.</span></span>

### <a href="" id="-------------dart-8-0-release-notes"></a> <span data-ttu-id="fe268-135">DaRT 8.0 リリースノート</span><span class="sxs-lookup"><span data-stu-id="fe268-135">DaRT 8.0 release notes</span></span>

<span data-ttu-id="fe268-136">詳細と、ドキュメントに組み込まれていない最新ニュースについては、「 [DaRT 8.0 のリリースノート](release-notes-for-dart-80--dart-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fe268-136">For more information, and for late-breaking news that did not make it into the documentation, see the [Release Notes for DaRT 8.0](release-notes-for-dart-80--dart-8.md).</span></span>

## <span data-ttu-id="fe268-137">DaRT 8.0 の入手方法</span><span class="sxs-lookup"><span data-stu-id="fe268-137">How to Get DaRT 8.0</span></span>


<span data-ttu-id="fe268-138">この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe268-138">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="fe268-139">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="fe268-139">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="fe268-140">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="fe268-140">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="fe268-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe268-141">Related topics</span></span>


[<span data-ttu-id="fe268-142">DaRT 8.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="fe268-142">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="fe268-143">DaRT 8.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="fe268-143">Release Notes for DaRT 8.0</span></span>](release-notes-for-dart-80--dart-8.md)

 

 





