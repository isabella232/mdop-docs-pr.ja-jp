---
title: DaRT 8.1 について
description: DaRT 8.1 について
author: dansimp
ms.assetid: dcaddc57-0111-4a9d-8be9-f5ada0eefa7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 29c7522b4f5a5da3b451b23f2fd200db44bb9481
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821264"
---
# <span data-ttu-id="e57f2-103">DaRT 8.1 について</span><span class="sxs-lookup"><span data-stu-id="e57f2-103">About DaRT 8.1</span></span>


<span data-ttu-id="e57f2-104">Microsoft 診断/回復ツールセット (DaRT) 8.1 には、このトピックで説明されている次の機能強化が用意されています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.1 provides the following enhancements, which are described in this topic.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="e57f2-105">新機能</span><span class="sxs-lookup"><span data-stu-id="e57f2-105">What’s new</span></span>


-   **<span data-ttu-id="e57f2-106">WIMBoot のサポート</span><span class="sxs-lookup"><span data-stu-id="e57f2-106">Support for WIMBoot</span></span>**

    <span data-ttu-id="e57f2-107">診断/回復ツールセット8.1 は、次の条件が満たされた場合に、Windows イメージファイル起動 (WIMBoot) 環境をサポートします。</span><span class="sxs-lookup"><span data-stu-id="e57f2-107">Diagnostics and Recovery Toolset 8.1 supports the Windows image file boot (WIMBoot) environment if these conditions are met:</span></span>

    -   <span data-ttu-id="e57f2-108">WIMBoot は、Windows 8.1 Update 1 以降に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-108">WIMBoot is based on Windows 8.1 Update 1 or later.</span></span>

    -   <span data-ttu-id="e57f2-109">DaRT 8.1 イメージは、Windows 8.1 Update 1 以降で作成されています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-109">The DaRT 8.1 image is built on Windows 8.1 Update 1 or later.</span></span>

    <span data-ttu-id="e57f2-110">WIMBoot の詳細については、「 [Windows イメージファイルブート (WIMBoot) の概要](https://go.microsoft.com/fwlink/?LinkId=517536)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e57f2-110">For more information about WIMBoot, see [Windows Image File Boot (WIMBoot) Overview](https://go.microsoft.com/fwlink/?LinkId=517536).</span></span>

-   **<span data-ttu-id="e57f2-111">Windows Server 2012 R2 および Windows 8.1 のサポート</span><span class="sxs-lookup"><span data-stu-id="e57f2-111">Support for Windows Server 2012 R2 and Windows 8.1</span></span>**

    <span data-ttu-id="e57f2-112">DaRT 画像を作成するには、Windows Server 2012 R2 または Windows 8.1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="e57f2-112">You can create DaRT images by using Windows Server 2012 R2 or Windows 8.1.</span></span>

    **<span data-ttu-id="e57f2-113">注</span><span class="sxs-lookup"><span data-stu-id="e57f2-113">Note</span></span>**  
    <span data-ttu-id="e57f2-114">以前のバージョンの Windows Server と Windows オペレーティングシステムの場合は、引き続き以前のバージョンの DaRT を使用してください。</span><span class="sxs-lookup"><span data-stu-id="e57f2-114">For earlier versions of the Windows Server and Windows operating systems, continue to use the earlier versions of DaRT.</span></span>



-   **<span data-ttu-id="e57f2-115">カスタマー フィードバック</span><span class="sxs-lookup"><span data-stu-id="e57f2-115">Customer feedback</span></span>**

    <span data-ttu-id="e57f2-116">DaRT 8.1 には、DaRT 8.0 SP1 のリリース以降に発生した問題に対処する更新が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-116">DaRT 8.1 includes updates that address issues found since the DaRT 8.0 SP1 release.</span></span>

-   **<span data-ttu-id="e57f2-117">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="e57f2-117">Windows Defender</span></span>**

    <span data-ttu-id="e57f2-118">Windows 8.1 の windows Defender には、保護が強化されています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-118">Windows Defender in Windows 8.1 includes improved protection.</span></span> <span data-ttu-id="e57f2-119">この変更によって、Windows Defender での DaRT の使い方に影響はありません。</span><span class="sxs-lookup"><span data-stu-id="e57f2-119">The changes do not impact how you use DaRT with Windows Defender.</span></span>

## <span data-ttu-id="e57f2-120">要件</span><span class="sxs-lookup"><span data-stu-id="e57f2-120">Requirements</span></span>


-   **<span data-ttu-id="e57f2-121">Windows アセスメント & 開発キット8.1</span><span class="sxs-lookup"><span data-stu-id="e57f2-121">Windows Assessment and Development Kit 8.1</span></span>**

    <span data-ttu-id="e57f2-122">Windows アセスメント & 開発キット (ADK) 8.1 は、DaRT 回復イメージウィザードの必須条件です。</span><span class="sxs-lookup"><span data-stu-id="e57f2-122">Windows Assessment and Development Kit (ADK) 8.1 is a required prerequisite for the DaRT Recovery Image Wizard.</span></span> <span data-ttu-id="e57f2-123">Windows ADK 8.1 には、Windows イメージのカスタマイズ、展開、およびサービスのために使用される展開ツールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-123">Windows ADK 8.1 contains deployment tools that are used to customize, deploy, and service Windows images.</span></span> <span data-ttu-id="e57f2-124">また、Windows Preinstallation Environment (Windows PE) も含まれています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-124">It also contains the Windows Preinstallation Environment (Windows PE).</span></span>

    **<span data-ttu-id="e57f2-125">注</span><span class="sxs-lookup"><span data-stu-id="e57f2-125">Note</span></span>**  
    <span data-ttu-id="e57f2-126">リモート接続ビューアーまたはクラッシュアナライザーのみをインストールする場合は、Windows ADK 8.1 は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e57f2-126">Windows ADK 8.1 is not required if you are installing only Remote Connection Viewer or Crash Analyzer.</span></span>



~~~
To download Windows ADK 8.1, see [Windows Assessment and Deployment Kit (Windows ADK) for Windows 8.1](https://www.microsoft.com/download/details.aspx?id=39982) in the Microsoft Download Center.
~~~

-   **<span data-ttu-id="e57f2-127">Microsoft .NET Framework 4.5.1</span><span class="sxs-lookup"><span data-stu-id="e57f2-127">Microsoft .NET Framework 4.5.1</span></span>**

    <span data-ttu-id="e57f2-128">DaRT 8.1 には、.NET Framework 4.5.1 がインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e57f2-128">DaRT 8.1 requires that .NET Framework 4.5.1 is installed.</span></span> <span data-ttu-id="e57f2-129">ダウンロードについては、Microsoft ダウンロードセンターの[Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e57f2-129">To download, see [Microsoft.NET Framework 4.5.1](https://go.microsoft.com/fwlink/?LinkId=329038) in the Microsoft Download Center.</span></span>

-   **<span data-ttu-id="e57f2-130">Windows 8.1 デバッグツール</span><span class="sxs-lookup"><span data-stu-id="e57f2-130">Windows 8.1 Debugging Tools</span></span>**

    <span data-ttu-id="e57f2-131">DaRT 8.1 でクラッシュ解析ツールを使用するには、Windows 8.1 用ソフトウェア開発キットで利用できる必要なデバッグツールが必要です。</span><span class="sxs-lookup"><span data-stu-id="e57f2-131">To use the Crash Analyzer tool in DaRT 8.1, you need the required debugging tools, which are available in the Software Development Kit for Windows 8.1.</span></span>

    <span data-ttu-id="e57f2-132">ダウンロードについては、Microsoft ダウンロードセンターの[windows 8.1 用 Windows ソフトウェア開発キット (SDK)](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e57f2-132">To download, see [Windows Software Development Kit (SDK) for Windows 8.1](https://msdn.microsoft.com/library/windows/desktop/bg162891.aspx) in the Microsoft Download Center.</span></span>

## <span data-ttu-id="e57f2-133">使用可能な言語</span><span class="sxs-lookup"><span data-stu-id="e57f2-133">Language availability</span></span>


<span data-ttu-id="e57f2-134">DaRT 8.1 は以下の言語で利用できます。</span><span class="sxs-lookup"><span data-stu-id="e57f2-134">DaRT 8.1 is available in the following languages:</span></span>

-   <span data-ttu-id="e57f2-135">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="e57f2-135">English (United States) en-US</span></span>

-   <span data-ttu-id="e57f2-136">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="e57f2-136">French (France) fr-FR</span></span>

-   <span data-ttu-id="e57f2-137">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="e57f2-137">Italian (Italy) it-IT</span></span>

-   <span data-ttu-id="e57f2-138">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="e57f2-138">German (Germany) de-DE</span></span>

-   <span data-ttu-id="e57f2-139">スペイン語、インターナショナルソート (スペイン) es</span><span class="sxs-lookup"><span data-stu-id="e57f2-139">Spanish, International Sort (Spain) es-ES</span></span>

-   <span data-ttu-id="e57f2-140">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="e57f2-140">Korean (Korea) ko-KR</span></span>

-   <span data-ttu-id="e57f2-141">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="e57f2-141">Japanese (Japan) ja-JP</span></span>

-   <span data-ttu-id="e57f2-142">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="e57f2-142">Portuguese (Brazil) pt-BR</span></span>

-   <span data-ttu-id="e57f2-143">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="e57f2-143">Russian (Russia) ru-RU</span></span>

-   <span data-ttu-id="e57f2-144">繁体字中国語 zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="e57f2-144">Chinese Traditional zh-TW</span></span>

-   <span data-ttu-id="e57f2-145">簡体字中国語 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="e57f2-145">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="e57f2-146">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="e57f2-146">How to Get MDOP Technologies</span></span>


<span data-ttu-id="e57f2-147">DaRT 8.1 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="e57f2-147">DaRT 8.1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="e57f2-148">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="e57f2-148">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="e57f2-149">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="e57f2-149">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="e57f2-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e57f2-150">Related topics</span></span>


[<span data-ttu-id="e57f2-151">DaRT 8.1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="e57f2-151">Release Notes for DaRT 8.1</span></span>](release-notes-for-dart-81.md)









