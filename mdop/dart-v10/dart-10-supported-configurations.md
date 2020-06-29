---
title: DaRT 10 でサポートされる構成
description: DaRT 10 でサポートされる構成
author: dansimp
ms.assetid: a07d6562-1fa9-499f-829c-9cc487ede0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 414b9d5cb7bf78dcfeda3fafc1c476e367709446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813138"
---
# <span data-ttu-id="db732-103">DaRT 10 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="db732-103">DaRT 10 Supported Configurations</span></span>


<span data-ttu-id="db732-104">このトピックでは、お客様の環境に Microsoft Diagnostics and Recovery ツールセット (DaRT) 10 をインストールして実行するために必要な、必須ソフトウェアとサポートされる構成要件を示します。</span><span class="sxs-lookup"><span data-stu-id="db732-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 10 in your environment.</span></span> <span data-ttu-id="db732-105">DaRT 10 を実行するために必要なオペレーティングシステム要件とシステム要件の両方が指定されています。</span><span class="sxs-lookup"><span data-stu-id="db732-105">Both the operating system requirements and the system requirements that are required to run DaRT 10 are specified.</span></span> <span data-ttu-id="db732-106">DaRT リカバリ画像の作成について考慮する必要がある前提条件については、「 [dart 10 リカバリイメージの作成の計画](planning-to-create-the-dart-10-recovery-image.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db732-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 10 Recovery Image](planning-to-create-the-dart-10-recovery-image.md).</span></span>

<span data-ttu-id="db732-107">以降のリリースに適用されるサポートされている構成については、該当するリリースのドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="db732-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="db732-108">DaRT は、次の2つのいずれかの方法でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="db732-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="db732-109">すべての機能を IT 管理者のコンピューターにインストールして、DaRT の実行に関連するすべてのタスクを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="db732-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="db732-110">または、管理者のコンピューターで、回復イメージを作成する DaRT 機能のみをインストールして、DaRT (つまり DaRT リモート接続ビュアー) を実行するために使用された機能をヘルプデスクコンピューターにインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="db732-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <span data-ttu-id="db732-111">DaRT 10 の必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="db732-111">DaRT 10 prerequisite software</span></span>


<span data-ttu-id="db732-112">DaRT をインストールする前に、次の前提条件が満たされていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="db732-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="db732-113">管理者コンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="db732-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="db732-114">以下の表に、DaRT 10 とすべての DaRT ツールをインストールするときの管理者コンピューターのインストール前提条件を示します。</span><span class="sxs-lookup"><span data-stu-id="db732-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 10 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db732-115">受講</span><span class="sxs-lookup"><span data-stu-id="db732-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="db732-116">詳細</span><span class="sxs-lookup"><span data-stu-id="db732-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db732-117">Windows アセスメント & 開発キット (ADK)</span><span class="sxs-lookup"><span data-stu-id="db732-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db732-118">DaRT リカバリ画像ウィザードに必要。</span><span class="sxs-lookup"><span data-stu-id="db732-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="db732-119">Windows イメージのカスタマイズ、展開、サービスのために使用される展開ツールが含まれており、Windows Preinstallation Environment (Windows PE) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="db732-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="db732-120">ADK は、リモート接続ビューアーと Crash Analyzer のどちらかまたは両方をインストールする場合には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="db732-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db732-121">Windows 開発キットまたはソフトウェア開発キット (オプション)</span><span class="sxs-lookup"><span data-stu-id="db732-121">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db732-122">クラッシュアナライザーでは、windows ドライバーキットの Windows 10 デバッグツールを使って、メモリダンプファイルを解析する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db732-122">Crash Analyzer requires the Windows 10 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db732-123">Windows 10 64 ビットまたは32ビット ISO イメージ</span><span class="sxs-lookup"><span data-stu-id="db732-123">Windows 10 64-bit or 32-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db732-124">DaRT には windows 10 メディアの Windows 回復環境 (Windows RE) イメージが必要です。</span><span class="sxs-lookup"><span data-stu-id="db732-124">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 10 media.</span></span> <span data-ttu-id="db732-125">作成する DaRT 回復イメージの種類に応じて、32ビット版または64ビット版の Windows 10 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="db732-125">Download the 32-bit or 64-bit version of Windows 10, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="db732-126">環境で両方のシステムの種類をサポートしている場合は、両方のバージョンの Windows 10 をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="db732-126">If you support both system types in your environment, download both versions of Windows 10.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="db732-127">ヘルプデスクコンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="db732-127">Help desk computer prerequisites</span></span>

<span data-ttu-id="db732-128">次の表は、DaRT 10 リモート接続ビューアーを実行しているときの、ヘルプデスクコンピューターのインストールの前提条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="db732-128">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 10 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db732-129">受講</span><span class="sxs-lookup"><span data-stu-id="db732-129">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="db732-130">詳細</span><span class="sxs-lookup"><span data-stu-id="db732-130">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db732-131">DaRT 10 リモート接続ビューアー</span><span class="sxs-lookup"><span data-stu-id="db732-131">DaRT 10 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db732-132">Windows 10 オペレーティングシステムにインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db732-132">Must be installed on a Windows 10 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db732-133">Debugging Tools for Windows</span><span class="sxs-lookup"><span data-stu-id="db732-133">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db732-134">クラッシュ解析ツールをインストールする場合にのみ必須</span><span class="sxs-lookup"><span data-stu-id="db732-134">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="db732-135">エンドユーザーコンピューターの前提条件</span><span class="sxs-lookup"><span data-stu-id="db732-135">End-user computer prerequisites</span></span>

<span data-ttu-id="db732-136">Windows 10 オペレーティングシステム以外のエンドユーザーコンピューターにインストールする必要がある必須のソフトウェアはありません。</span><span class="sxs-lookup"><span data-stu-id="db732-136">There is no prerequisite software that must be installed on end-user computers, other than the Windows 10 operating system.</span></span>

## <a href="" id="---------dart-10-operating-system-requirements"></a> <span data-ttu-id="db732-137">DaRT 10 オペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="db732-137">DaRT 10 operating system requirements</span></span>


### <span data-ttu-id="db732-138">管理者のコンピューターのシステム要件</span><span class="sxs-lookup"><span data-stu-id="db732-138">Administrator computer system requirements</span></span>

<span data-ttu-id="db732-139">次の表は、DaRT 10 管理者コンピューターのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="db732-139">The following table lists the operating systems that are supported for the DaRT 10 administrator computer installation.</span></span>

<span data-ttu-id="db732-140">**注** 管理者のコンピューターにインストールする追加のツールに十分な領域を割り当てていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="db732-140">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="db732-141">**注** Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="db732-141">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="db732-142">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="db732-142">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="db732-143">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="db732-143">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

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
<th align="left"><span data-ttu-id="db732-144">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="db732-144">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db732-145">エディション</span><span class="sxs-lookup"><span data-stu-id="db732-145">Edition</span></span></th>
<th align="left"><span data-ttu-id="db732-146">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db732-146">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db732-147">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="db732-147">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db732-148">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="db732-148">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db732-149">DaRT を実行するための RAM 要件</span><span class="sxs-lookup"><span data-stu-id="db732-149">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-150">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db732-150">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-151">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-151">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-152">なし</span><span class="sxs-lookup"><span data-stu-id="db732-152">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-153">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-153">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-154">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-154">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-155">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-155">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db732-156">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db732-156">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-157">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-157">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-158">なし</span><span class="sxs-lookup"><span data-stu-id="db732-158">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-159">32 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-159">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-160">1 GB</span><span class="sxs-lookup"><span data-stu-id="db732-160">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-161">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-161">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="db732-162">DaRT ヘルプデスクコンピュータのシステム要件</span><span class="sxs-lookup"><span data-stu-id="db732-162">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="db732-163">ヘルプデスクでコンピューターのリモートトラブルシューティングを行うことを許可している場合は、リモート接続ビューアーをヘルプデスクコンピューターにインストールしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="db732-163">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="db732-164">必要に応じて、クラッシュ分析ツールをヘルプデスクコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="db732-164">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="db732-165">DaRT 10 では、dart 7.0、DaRT 8.0、DaRt 8.1、または DaRT 10 リモート接続ビューアーを使って、DaRT 10 コンピュータに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="db732-165">DaRT 10 enables a help desk worker to connect to a DaRT 10 computer by using either the DaRT 7.0, DaRT 8.0, DaRt 8.1, or DaRT 10 Remote Connection Viewer.</span></span> <span data-ttu-id="db732-166">Dart 7.0、DaRT 8.0、DaRt 8.1 では、リモート接続ビューアーにそれぞれ Windows 7、Windows 8、または Windows 8.1 オペレーティングシステムが必要ですが、DaRT 10 リモート接続ビューアーには Windows 10 が必要です。</span><span class="sxs-lookup"><span data-stu-id="db732-166">The DaRT 7.0, DaRT 8.0 and DaRt 8.1, Remote Connection Viewers require Windows 7, Windows 8, or Windows 8.1 operating systems respectively, while the DaRT 10 Remote Connection Viewer requires Windows 10.</span></span> <span data-ttu-id="db732-167">DaRT 10 リモート接続ビューアーとその他のすべての DaRT 10 ツールは、Windows 10 を実行しているコンピュータにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="db732-167">The DaRT 10 Remote Connection Viewer and all other DaRT 10 tools can be installed only on a computer running Windows 10.</span></span>

<span data-ttu-id="db732-168">次の表は、DaRT ヘルプデスクのコンピューターのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="db732-168">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

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
<th align="left"><span data-ttu-id="db732-169">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="db732-169">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db732-170">エディション</span><span class="sxs-lookup"><span data-stu-id="db732-170">Edition</span></span></th>
<th align="left"><span data-ttu-id="db732-171">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db732-171">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db732-172">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="db732-172">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db732-173">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="db732-173">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db732-174">DaRT を実行するための RAM 要件</span><span class="sxs-lookup"><span data-stu-id="db732-174">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-175">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db732-175">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-176">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-176">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-177">なし</span><span class="sxs-lookup"><span data-stu-id="db732-177">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-178">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-178">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-179">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-179">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-180">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-180">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db732-181">Windows 10 (リモート接続ビューアー10.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="db732-181">Windows10 (with Remote Connection Viewer 10.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-182">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-182">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-183">なし</span><span class="sxs-lookup"><span data-stu-id="db732-183">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-184">32 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-184">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-185">1 GB</span><span class="sxs-lookup"><span data-stu-id="db732-185">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-186">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-186">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-187">Windows8</span><span class="sxs-lookup"><span data-stu-id="db732-187">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-188">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-188">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-189">なし</span><span class="sxs-lookup"><span data-stu-id="db732-189">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-190">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-190">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-191">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-191">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-192">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-192">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db732-193">Windows8 (リモート接続ビューアー8.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="db732-193">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-194">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-194">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-195">なし</span><span class="sxs-lookup"><span data-stu-id="db732-195">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-196">32 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-196">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-197">1 GB</span><span class="sxs-lookup"><span data-stu-id="db732-197">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-198">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-198">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-199">Windows 7 (リモート接続ビューアー7.0 のみ)</span><span class="sxs-lookup"><span data-stu-id="db732-199">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-200">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-200">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-201">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="db732-201">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-202">64ビットまたは32ビット</span><span class="sxs-lookup"><span data-stu-id="db732-202">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-203">1 GB</span><span class="sxs-lookup"><span data-stu-id="db732-203">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-204">なし</span><span class="sxs-lookup"><span data-stu-id="db732-204">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db732-205">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db732-205">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-206">標準、エンタープライズ、データセンター</span><span class="sxs-lookup"><span data-stu-id="db732-206">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-207">なし</span><span class="sxs-lookup"><span data-stu-id="db732-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-208">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-208">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-209">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-209">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-210">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="db732-210">1.0 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-211">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="db732-211">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-212">標準、エンタープライズ、データセンター</span><span class="sxs-lookup"><span data-stu-id="db732-212">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-213">なし</span><span class="sxs-lookup"><span data-stu-id="db732-213">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-214">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-214">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-215">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-215">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-216">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="db732-216">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="db732-217">DaRT には、エンドユーザのコンピュータに関する以下の最小ハードウェア要件もあります。</span><span class="sxs-lookup"><span data-stu-id="db732-217">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="db732-218">CD または DVD のドライブまたは USB ポート: CD、DVD、または USB を使用して、企業内で DaRT を展開する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="db732-218">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="db732-219">BIOS は、CD または DVD、USB フラッシュドライブ、またはリモートまたは回復パーティションからコンピューターを起動するためにサポートされています。</span><span class="sxs-lookup"><span data-stu-id="db732-219">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-10-end-user-computer-system-requirements"></a> <span data-ttu-id="db732-220">DaRT 10 エンドユーザーコンピューターのシステム要件</span><span class="sxs-lookup"><span data-stu-id="db732-220">DaRT 10 end-user computer system requirements</span></span>

<span data-ttu-id="db732-221">DaRT 10 の [診断と回復] のツールセットウィンドウでは、DaRT で利用可能なシステムメモリの容量と共に、エンドユーザーのコンピューターで次のいずれかのオペレーティングシステムを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db732-221">The Diagnostics and Recovery Toolset window in DaRT 10 requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

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
<th align="left"><span data-ttu-id="db732-222">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="db732-222">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db732-223">エディション</span><span class="sxs-lookup"><span data-stu-id="db732-223">Edition</span></span></th>
<th align="left"><span data-ttu-id="db732-224">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db732-224">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db732-225">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="db732-225">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db732-226">オペレーティング システムの要件</span><span class="sxs-lookup"><span data-stu-id="db732-226">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db732-227">RAM の要件</span><span class="sxs-lookup"><span data-stu-id="db732-227">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db732-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db732-228">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-229">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-229">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-230">なし</span><span class="sxs-lookup"><span data-stu-id="db732-230">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-231">64 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-231">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="db732-232">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-233">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-233">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db732-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="db732-234">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-235">すべてのエディション</span><span class="sxs-lookup"><span data-stu-id="db732-235">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-236">なし</span><span class="sxs-lookup"><span data-stu-id="db732-236">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-237">32 ビット</span><span class="sxs-lookup"><span data-stu-id="db732-237">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-238">1 GB</span><span class="sxs-lookup"><span data-stu-id="db732-238">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db732-239">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db732-239">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="db732-240">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db732-240">Related topics</span></span>


[<span data-ttu-id="db732-241">DaRT 10 の展開計画</span><span class="sxs-lookup"><span data-stu-id="db732-241">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 





