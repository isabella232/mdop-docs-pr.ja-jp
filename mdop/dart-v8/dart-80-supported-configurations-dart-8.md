---
title: DaRT 8.0 でサポートされる構成
description: DaRT 8.0 でサポートされる構成
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823927"
---
# <span data-ttu-id="e1bde-103">DaRT 8.0 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e1bde-103">DaRT 8.0 Supported Configurations</span></span>


<span data-ttu-id="e1bde-104">このトピックでは、お客様の環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 8.0 をインストールして実行するために必要な、必須ソフトウェアとサポートされる構成要件を示します。</span><span class="sxs-lookup"><span data-stu-id="e1bde-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 in your environment.</span></span> <span data-ttu-id="e1bde-105">DaRT 8.0 を実行するために必要なオペレーティングシステム要件とシステム要件の両方が指定されています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-105">Both the operating system requirements and the system requirements that are required to run DaRT 8.0 are specified.</span></span> <span data-ttu-id="e1bde-106">DaRT リカバリ画像の作成について考慮する必要がある前提条件については、「 [dart 8.0 リカバリイメージの作成の計画](planning-to-create-the-dart-80-recovery-image-dart-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 8.0 Recovery Image](planning-to-create-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="e1bde-107">以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="e1bde-108">DaRT は、次の2つのいずれかの方法でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e1bde-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="e1bde-109">すべての機能を IT 管理者のコンピューターにインストールして、DaRT の実行に関連するすべてのタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="e1bde-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="e1bde-110">または、管理者のコンピューターで、回復イメージを作成する DaRT 機能のみをインストールして、DaRT (つまり DaRT リモート接続ビュアー) を実行するために使用された機能をヘルプデスクコンピューターにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e1bde-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <a href="" id="---------dart-8-0-prerequisite-software"></a> <span data-ttu-id="e1bde-111">DaRT 8.0 の必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e1bde-111">DaRT 8.0 prerequisite software</span></span>


<span data-ttu-id="e1bde-112">DaRT をインストールする前に、次の前提条件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="e1bde-113">管理者コンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="e1bde-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="e1bde-114">以下の表に、DaRT 8.0 およびすべての DaRT ツールをインストールするときの管理者コンピューターのインストール前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="e1bde-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 8.0 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1bde-115">受講</span><span class="sxs-lookup"><span data-stu-id="e1bde-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e1bde-116">詳細</span><span class="sxs-lookup"><span data-stu-id="e1bde-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1bde-117">Windows アセスメント & 開発キット (ADK)</span><span class="sxs-lookup"><span data-stu-id="e1bde-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-118">DaRT リカバリ画像ウィザードに必要。</span><span class="sxs-lookup"><span data-stu-id="e1bde-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="e1bde-119">Windows イメージのカスタマイズ、展開、サービスのために使用される展開ツールが含まれており、Windows Preinstallation Environment (Windows PE) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="e1bde-120">ADK は、リモート接続ビューアーと Crash Analyzer のどちらかまたは両方をインストールする場合には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e1bde-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e1bde-121">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e1bde-121">.NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-122">DaRT リカバリ画像ウィザードで必要。</span><span class="sxs-lookup"><span data-stu-id="e1bde-122">Required by the DaRT Recovery Image wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1bde-123">Windows 開発キットまたはソフトウェア開発キット (オプション)</span><span class="sxs-lookup"><span data-stu-id="e1bde-123">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-124">クラッシュアナライザーでは、windows ドライバーキットの Windows 8 デバッグツールを使って、メモリダンプファイルを解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bde-124">Crash Analyzer requires the Windows 8 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e1bde-125">Windows 8 64 ビット ISO イメージ</span><span class="sxs-lookup"><span data-stu-id="e1bde-125">Windows 8 64-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-126">DaRT には windows 8 メディアの windows 回復環境 (Windows RE) イメージが必要です。</span><span class="sxs-lookup"><span data-stu-id="e1bde-126">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 8 media.</span></span> <span data-ttu-id="e1bde-127">作成する DaRT 回復イメージの種類に応じて、32ビット版または64ビット版の Windows 8 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e1bde-127">Download the 32-bit or 64-bit version of Windows 8, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="e1bde-128">環境で両方のシステムの種類をサポートしている場合は、両方のバージョンの Windows 8 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="e1bde-128">If you support both system types in your environment, download both versions of Windows 8.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e1bde-129">ヘルプデスクコンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="e1bde-129">Help desk computer prerequisites</span></span>

<span data-ttu-id="e1bde-130">次の表は、DaRT 8.0 リモート接続ビューアーを実行しているときの、ヘルプデスクコンピューターのインストールの前提条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-130">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 8.0 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1bde-131">受講</span><span class="sxs-lookup"><span data-stu-id="e1bde-131">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e1bde-132">詳細</span><span class="sxs-lookup"><span data-stu-id="e1bde-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1bde-133">DaRT 8.0 リモート接続ビューアー</span><span class="sxs-lookup"><span data-stu-id="e1bde-133">DaRT 8.0 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-134">Windows 8 オペレーティングシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bde-134">Must be installed on a Windows 8 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="e1bde-135">NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="e1bde-135">NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-136">DaRT リカバリ画像ウィザードで必要</span><span class="sxs-lookup"><span data-stu-id="e1bde-136">Required by the DaRT Recovery Image wizard</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="e1bde-137">Debugging Tools for Windows</span><span class="sxs-lookup"><span data-stu-id="e1bde-137">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="e1bde-138">クラッシュ解析ツールをインストールする場合にのみ必須</span><span class="sxs-lookup"><span data-stu-id="e1bde-138">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e1bde-139">エンドユーザーコンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="e1bde-139">End-user computer prerequisites</span></span>

<span data-ttu-id="e1bde-140">Windows 8 オペレーティングシステム以外のエンドユーザーコンピューターにインストールする必要がある必須のソフトウェアはありません。</span><span class="sxs-lookup"><span data-stu-id="e1bde-140">There is no prerequisite software that must be installed on end-user computers, other than the Windows 8 operating system.</span></span>

## <a href="" id="---------dart-operating-system-requirements"></a> <span data-ttu-id="e1bde-141">DaRT オペレーティングシステムの要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-141">DaRT operating system requirements</span></span>


### <span data-ttu-id="e1bde-142">管理者のコンピューターのシステム要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-142">Administrator computer system requirements</span></span>

<span data-ttu-id="e1bde-143">次の表は、DaRT 管理者のコンピューターのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-143">The following table lists the operating systems that are supported for the DaRT administrator computer installation.</span></span>

<span data-ttu-id="e1bde-144">**注** 管理者のコンピューターにインストールする追加のツールに十分な領域を割り当てていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-144">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="e1bde-145">**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="e1bde-145">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="e1bde-146">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-146">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="e1bde-147">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e1bde-147">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1bde-148">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="e1bde-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e1bde-149">エディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="e1bde-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e1bde-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e1bde-151">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e1bde-151">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="e1bde-152">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-152">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="e1bde-153">DaRT を実行するための RAM 要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-153">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-154">Windows8</span><span class="sxs-lookup"><span data-stu-id="e1bde-154">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-155">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-155">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-156">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-156">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-157">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-158">2 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-158">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-159">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-159">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1bde-160">Windows8</span><span class="sxs-lookup"><span data-stu-id="e1bde-160">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-161">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-161">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-162">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-162">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-163">32 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-163">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-164">1 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-164">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-165">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-165">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-166">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e1bde-166">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-167">標準、エンタープライズ、データセンター</span><span class="sxs-lookup"><span data-stu-id="e1bde-167">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-168">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-168">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-169">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-169">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-170">512 MB</span><span class="sxs-lookup"><span data-stu-id="e1bde-170">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-171">1. 0 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-171">1 .0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="e1bde-172">DaRT ヘルプデスクコンピュータのシステム要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-172">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="e1bde-173">ヘルプデスクでコンピューターのリモートトラブルシューティングを行うことを許可している場合は、リモート接続ビューアーをヘルプデスクコンピューターにインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bde-173">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="e1bde-174">必要に応じて、クラッシュ分析ツールをヘルプデスクコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e1bde-174">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="e1bde-175">DaRT 8.0 では、DaRT 7.0 または DaRT 8.0 のリモート接続ビューアーを使用して、ヘルプデスクワーカーが DaRT 8.0 コンピューターに接続することを可能にします。</span><span class="sxs-lookup"><span data-stu-id="e1bde-175">DaRT 8.0 enables a help desk worker to connect to a DaRT 8.0 computer by using either the DaRT 7.0 or DaRT 8.0 Remote Connection Viewer.</span></span> <span data-ttu-id="e1bde-176">DaRT 7.0 リモート接続ビューアーには Windows 7 オペレーティングシステムが必要ですが、DaRT 8.0 リモート接続ビューアーには Windows 8 が必要です。</span><span class="sxs-lookup"><span data-stu-id="e1bde-176">The DaRT 7.0 Remote Connection Viewer requires a Windows 7 operating system, while the DaRT 8.0 Remote Connection Viewer requires Windows 8.</span></span> <span data-ttu-id="e1bde-177">DaRT 8.0 リモート接続ビューアーとその他のすべての DaRT 8.0 ツールは、Windows 8 を実行しているコンピュータにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e1bde-177">The DaRT 8.0 Remote Connection Viewer and all other DaRT 8.0 tools can be installed only on a computer running Windows 8.</span></span>

<span data-ttu-id="e1bde-178">次の表は、DaRT ヘルプデスクのコンピューターのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-178">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1bde-179">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="e1bde-179">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e1bde-180">エディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-180">Edition</span></span></th>
<th align="left"><span data-ttu-id="e1bde-181">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e1bde-181">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e1bde-182">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e1bde-182">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="e1bde-183">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-183">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="e1bde-184">DaRT を実行するための RAM 要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-184">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-185">Windows8</span><span class="sxs-lookup"><span data-stu-id="e1bde-185">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-186">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-186">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-187">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-187">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-188">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-188">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-189">2 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-189">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-190">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-190">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1bde-191">Windows8 (リモート接続ビューアー8.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="e1bde-191">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-192">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-192">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-193">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-193">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-194">32 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-194">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-195">1 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-195">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-196">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-196">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-197">Windows 7 (リモート接続ビューアー7.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="e1bde-197">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-198">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-198">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-199">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="e1bde-199">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-200">64ビットまたは32ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-200">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-201">1 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-201">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-202">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-202">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1bde-203">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e1bde-203">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-204">標準、エンタープライズ、データセンター</span><span class="sxs-lookup"><span data-stu-id="e1bde-204">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-205">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-205">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-206">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-206">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-207">51</span><span class="sxs-lookup"><span data-stu-id="e1bde-207">51</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-208">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-208">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e1bde-209">DaRT には、エンドユーザのコンピュータに関する以下の最小ハードウェア要件もあります。</span><span class="sxs-lookup"><span data-stu-id="e1bde-209">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="e1bde-210">CD または DVD のドライブまたは USB ポート: CD、DVD、または USB を使用して、企業内で DaRT を展開する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="e1bde-210">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="e1bde-211">BIOS は、CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="e1bde-211">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> <span data-ttu-id="e1bde-212">DaRT エンドユーザコンピューターのシステム要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-212">DaRT end-user computer system requirements</span></span>

<span data-ttu-id="e1bde-213">DaRT の [診断と回復] のツールセットウィンドウでは、DaRT で利用可能なシステムメモリの容量と共に、エンドユーザーのコンピューターで次のいずれかのオペレーティングシステムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e1bde-213">The Diagnostics and Recovery Toolset window in DaRT requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e1bde-214">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="e1bde-214">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e1bde-215">エディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-215">Edition</span></span></th>
<th align="left"><span data-ttu-id="e1bde-216">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e1bde-216">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e1bde-217">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e1bde-217">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="e1bde-218">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-218">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="e1bde-219">RAM の要件</span><span class="sxs-lookup"><span data-stu-id="e1bde-219">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-220">Windows8</span><span class="sxs-lookup"><span data-stu-id="e1bde-220">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-221">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-221">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-222">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-222">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-223">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-223">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-224">2 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-224">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-225">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-225">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e1bde-226">Windows8</span><span class="sxs-lookup"><span data-stu-id="e1bde-226">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-227">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="e1bde-227">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-228">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-228">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-229">32 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-229">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-230">1 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-230">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-231">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-231">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e1bde-232">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="e1bde-232">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-233">標準、エンタープライズ、データセンター</span><span class="sxs-lookup"><span data-stu-id="e1bde-233">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-234">なし</span><span class="sxs-lookup"><span data-stu-id="e1bde-234">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-235">64 ビット</span><span class="sxs-lookup"><span data-stu-id="e1bde-235">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-236">512 MB</span><span class="sxs-lookup"><span data-stu-id="e1bde-236">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="e1bde-237">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="e1bde-237">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e1bde-238">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e1bde-238">Related topics</span></span>


[<span data-ttu-id="e1bde-239">DaRT 8.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="e1bde-239">Planning to Deploy DaRT 8.0</span></span>](planning-to-deploy-dart-80-dart-8.md)

 

 





