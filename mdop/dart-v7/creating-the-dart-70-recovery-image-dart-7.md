---
title: DaRT 7.0 の回復イメージの作成
description: DaRT 7.0 の回復イメージの作成
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823284"
---
# <span data-ttu-id="e2bb8-103">DaRT 7.0 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="e2bb8-103">Creating the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="e2bb8-104">Microsoft 診断/回復ツールセット (DaRT) 7 には、Windows で使用される**Dart Recovery イメージウィザード**が含まれており、これを使って、起動可能な国際標準化機関 (ISO) 画像を作成します。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="e2bb8-105">ISO 画像は、CD の生のコンテンツを表すファイルです。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

## <span data-ttu-id="e2bb8-106">DaRT Recovery イメージウィザードを使用して回復イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="e2bb8-106">Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="e2bb8-107">DaRT リカバリ画像ウィザードによって作成された ISO には、問題のあるコンピュータを起動できる DaRT リカバリ画像が含まれています。これは、それ以外の方法でも起動できます。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-107">The ISO created by the DaRT Recovery Image Wizard contains the DaRT recovery image that lets you boot into a problem computer, even if it might otherwise not start.</span></span> <span data-ttu-id="e2bb8-108">DaRT にコンピューターを起動した後、さまざまな DaRT ツールを実行して、コンピュータの診断と修復を試すことができます。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-108">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span>

<span data-ttu-id="e2bb8-109">書き込み可能な CD または DVD に ISO を書き込んだり、USB フラッシュドライブに保存したり、リモートパーティションまたは回復パーティションから DaRT を起動するために使用できる形式で保存したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-109">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span> <span data-ttu-id="e2bb8-110">詳細については、「 [DaRT 7.0 回復イメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-110">For more information, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="e2bb8-111">**注** コンピューターに CD-RW ドライブが含まれている場合、ウィザードは、ISO イメージを空の CD または DVD に書き込むことを提供します。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-111">**Note** If your computer includes a CD-RW drive, the wizard offers to burn the ISO image to a blank CD or DVD.</span></span> <span data-ttu-id="e2bb8-112">使用しているコンピューターに、ウィザードでサポートされているドライブが含まれていない場合は、CD または DVD に書き込み可能なほとんどのプログラムを使用して、ISO イメージを CD または DVD に書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-112">If your computer does not include a drive that is supported by the wizard, you can burn the ISO image onto a CD or DVD by using most programs that can burn a CD or DVD.</span></span>

 

<span data-ttu-id="e2bb8-113">ISO イメージからブーブート CD または DVD を作成するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-113">To create a bootable CD or DVD from the ISO image, you must have:</span></span>

-   <span data-ttu-id="e2bb8-114">CD-RW ドライブ。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-114">A CD-RW drive.</span></span>

-   <span data-ttu-id="e2bb8-115">書き込み可能な CD または DVD (書き込み可能なドライブでサポートされている形式)。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-115">A recordable CD or DVD (in a format supported by the recordable drive).</span></span>

-   <span data-ttu-id="e2bb8-116">書き込み可能ドライブをサポートし、CD または DVD への直接 ISO イメージの書き込みをサポートするソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-116">Software that supports the recordable drive and supports burning an ISO image directly to CD or DVD.</span></span>

    <span data-ttu-id="e2bb8-117">**重要** すべての種類の書き込み可能なメディアから起動できないコンピューターがあるため、サポートする必要があるすべての種類のコンピューターで、作成した CD または DVD をテストします。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-117">**Important** Test the CD or DVD that you create on all the different kinds of computers that you intend to support because some computers cannot start from all kinds of recordable media.</span></span>

     

<span data-ttu-id="e2bb8-118">USB フラッシュドライブ (UFD) に ISO 画像を保存するには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-118">To save the ISO image to a USB flash drive (UFD), you must have:</span></span>

-   <span data-ttu-id="e2bb8-119">正しい書式の UFD。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-119">A correctly formatted UFD.</span></span>

-   <span data-ttu-id="e2bb8-120">ISO イメージをマウントするために使用できるプログラム。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-120">A program that you can use to mount the ISO image.</span></span>

[<span data-ttu-id="e2bb8-121">DaRT の回復イメージ ウィザードを使用して回復イメージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e2bb8-121">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## <span data-ttu-id="e2bb8-122">時間限定の回復イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="e2bb8-122">Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="e2bb8-123">生成された特定の日数にのみ使用できる DaRT 回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-123">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="e2bb8-124">これを行うには、コマンドプロンプトで**DaRT リカバリイメージウィザード**を実行し、日数を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e2bb8-124">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

[<span data-ttu-id="e2bb8-125">期限付きの回復イメージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="e2bb8-125">How to Create a Time Limited Recovery Image</span></span>](how-to-create-a-time-limited-recovery-image-dart-7.md)

## <span data-ttu-id="e2bb8-126">DaRT7 回復イメージの作成に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="e2bb8-126">Other resources for creating the DaRT7 recovery image</span></span>


-   [<span data-ttu-id="e2bb8-127">DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="e2bb8-127">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





