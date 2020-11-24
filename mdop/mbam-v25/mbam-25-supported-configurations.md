---
title: MBAM 2.5 がサポートされる構成
description: MBAM 2.5 がサポートされる構成
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 8ed7915e33c5e4735a7c58674ed5f7d6da8e9a06
ms.sourcegitcommit: 9087f0a1b5bd3f81a9b790d5e39fdf39c18a2411
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/23/2020
ms.locfileid: "11182929"
---
# <span data-ttu-id="641b2-103">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="641b2-103">MBAM 2.5 Supported Configurations</span></span>


<span data-ttu-id="641b2-104">Microsoft BitLocker 管理と監視 (MBAM) 2.5 は、スタンドアロントポロジで、または MBAM を System Center Configuration Manager に統合した構成マネージャーの統合トポロジで実行できます。</span><span class="sxs-lookup"><span data-stu-id="641b2-104">You can run Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a Stand-alone topology or in a Configuration Manager Integration topology that integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="641b2-105">運用環境でいずれかのトポロジに推奨される構成を使用している場合、MBAM は最大 50万 MBAM クライアントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="641b2-105">If you use the recommended configuration for either topology in a production environment, MBAM supports up to 500,000 MBAM clients.</span></span> <span data-ttu-id="641b2-106">各トポロジの各サーバー上で構成される推奨アーキテクチャと機能については、「 [MBAM 2.5 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-106">For information about the recommended architecture and features that are configured on each server for each topology, see [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<span data-ttu-id="641b2-107">構成マネージャーの統合トポロジに固有のその他の構成については、「MBAM でサポートされて [いる Configuration manager のバージョン](#bkmk-cm-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-107">For additional configurations that are specific to the Configuration Manager Integration topology, see [Versions of Configuration Manager that MBAM supports](#bkmk-cm-ramreqs).</span></span>

**<span data-ttu-id="641b2-108">備考</span><span class="sxs-lookup"><span data-stu-id="641b2-108">Note</span></span>**  
<span data-ttu-id="641b2-109">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="641b2-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="641b2-110">お使いの製品のサポートタイムラインについては、 [ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="641b2-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="641b2-111">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



## <span data-ttu-id="641b2-112">MBAM でサポートされる言語</span><span class="sxs-lookup"><span data-stu-id="641b2-112">MBAM Supported Languages</span></span>


<span data-ttu-id="641b2-113">次の表は、mbam クライアント (Self-Service ポータルを含む) と mbam 2.5 および mbam 2.5 SP1 でサポートされている言語を示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-113">The following tables show the languages that are supported for the MBAM Client (including the Self-Service Portal) and the MBAM Server in MBAM 2.5 and MBAM 2.5 SP1.</span></span>

**<span data-ttu-id="641b2-114">MBAM 2.5 SP1 でサポートされる言語:</span><span class="sxs-lookup"><span data-stu-id="641b2-114">Supported Languages in MBAM 2.5 SP1:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-115">クライアント言語</span><span class="sxs-lookup"><span data-stu-id="641b2-115">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="641b2-116">サーバーの言語</span><span class="sxs-lookup"><span data-stu-id="641b2-116">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-117">チェコ語 (チェコ共和国) .cs-CZ</span><span class="sxs-lookup"><span data-stu-id="641b2-117">Czech (Czech Republic) cs-CZ</span></span></p>
<p><span data-ttu-id="641b2-118">デンマーク語 (デンマーク) da-DK</span><span class="sxs-lookup"><span data-stu-id="641b2-118">Danish (Denmark) da-DK</span></span></p>
<p><span data-ttu-id="641b2-119">オランダ語 (オランダ) nl-NL</span><span class="sxs-lookup"><span data-stu-id="641b2-119">Dutch (Netherlands) nl-NL</span></span></p>
<p><span data-ttu-id="641b2-120">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="641b2-120">English (United States) en-US</span></span></p>
<p><span data-ttu-id="641b2-121">フィンランド語 (フィンランド) fi</span><span class="sxs-lookup"><span data-stu-id="641b2-121">Finnish (Finland) fi-FI</span></span></p>
<p><span data-ttu-id="641b2-122">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="641b2-122">French (France) fr-FR</span></span></p>
<p><span data-ttu-id="641b2-123">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="641b2-123">German (Germany) de-DE</span></span></p>
<p><span data-ttu-id="641b2-124">ギリシャ語 (ギリシャ) el-GR</span><span class="sxs-lookup"><span data-stu-id="641b2-124">Greek (Greece) el-GR</span></span></p>
<p><span data-ttu-id="641b2-125">ハンガリー語 (ハンガリー) hu-HU</span><span class="sxs-lookup"><span data-stu-id="641b2-125">Hungarian (Hungary) hu-HU</span></span></p>
<p><span data-ttu-id="641b2-126">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="641b2-126">Italian (Italy) it-IT</span></span></p>
<p><span data-ttu-id="641b2-127">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="641b2-127">Japanese (Japan) ja-JP</span></span></p>
<p><span data-ttu-id="641b2-128">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="641b2-128">Korean (Korea) ko-KR</span></span></p>
<p><span data-ttu-id="641b2-129">ノルウェー語、ブークモール (ノルウェー) nb-いいえ</span><span class="sxs-lookup"><span data-stu-id="641b2-129">Norwegian, Bokmål (Norway) nb-NO</span></span></p>
<p><span data-ttu-id="641b2-130">ポーランド語 (ポーランド) pl-PL</span><span class="sxs-lookup"><span data-stu-id="641b2-130">Polish (Poland) pl-PL</span></span></p>
<p><span data-ttu-id="641b2-131">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="641b2-131">Portuguese (Brazil) pt-BR</span></span></p>
<p><span data-ttu-id="641b2-132">ポルトガル語 (ポルトガル) の pt-PT</span><span class="sxs-lookup"><span data-stu-id="641b2-132">Portuguese (Portugal) pt-PT</span></span></p>
<p><span data-ttu-id="641b2-133">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="641b2-133">Russian (Russia) ru-RU</span></span></p>
<p><span data-ttu-id="641b2-134">スロバキア語 (スロバキア) sk-SK</span><span class="sxs-lookup"><span data-stu-id="641b2-134">Slovak (Slovakia) sk-SK</span></span></p>
<p><span data-ttu-id="641b2-135">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="641b2-135">Spanish (Spain) es-ES</span></span></p>
<p><span data-ttu-id="641b2-136">スウェーデン語 (スウェーデン) sv-SE</span><span class="sxs-lookup"><span data-stu-id="641b2-136">Swedish (Sweden) sv-SE</span></span></p>
<p><span data-ttu-id="641b2-137">トルコ語 (トルコ) tr-TR</span><span class="sxs-lookup"><span data-stu-id="641b2-137">Turkish (Turkey) tr-TR</span></span></p>
<p><span data-ttu-id="641b2-138">スロベニア語 (スロベニア) sl-SI</span><span class="sxs-lookup"><span data-stu-id="641b2-138">Slovenian (Slovenia) sl-SI</span></span></p>
<p><span data-ttu-id="641b2-139">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="641b2-139">Simplified Chinese (PRC) zh-CN</span></span></p>
<p><span data-ttu-id="641b2-140">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="641b2-140">Traditional Chinese (Taiwan) zh-TW</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="641b2-141">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="641b2-141">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="641b2-142">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="641b2-142">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="641b2-143">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="641b2-143">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="641b2-144">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="641b2-144">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="641b2-145">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="641b2-145">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="641b2-146">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="641b2-146">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="641b2-147">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="641b2-147">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="641b2-148">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="641b2-148">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="641b2-149">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="641b2-149">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="641b2-150">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="641b2-150">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="641b2-151">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="641b2-151">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="641b2-152">MBAM 2.5 でサポートされる言語:</span><span class="sxs-lookup"><span data-stu-id="641b2-152">Supported Languages in MBAM 2.5:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-153">クライアント言語</span><span class="sxs-lookup"><span data-stu-id="641b2-153">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="641b2-154">サーバーの言語</span><span class="sxs-lookup"><span data-stu-id="641b2-154">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="641b2-155">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="641b2-155">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="641b2-156">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="641b2-156">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="641b2-157">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="641b2-157">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="641b2-158">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="641b2-158">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="641b2-159">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="641b2-159">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="641b2-160">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="641b2-160">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="641b2-161">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="641b2-161">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="641b2-162">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="641b2-162">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="641b2-163">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="641b2-163">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="641b2-164">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="641b2-164">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="641b2-165">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="641b2-165">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="641b2-166">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="641b2-166">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="641b2-167">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="641b2-167">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="641b2-168">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="641b2-168">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="641b2-169">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="641b2-169">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="641b2-170">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="641b2-170">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="641b2-171">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="641b2-171">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="641b2-172">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="641b2-172">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="641b2-173">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="641b2-173">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="641b2-174">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="641b2-174">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="641b2-175">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="641b2-175">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="641b2-176">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="641b2-176">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="641b2-177">MBAM サーバーシステム要件</span><span class="sxs-lookup"><span data-stu-id="641b2-177">MBAM Server system requirements</span></span>


### <span data-ttu-id="641b2-178">MBAM サーバーオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="641b2-178">MBAM Server operating system requirements</span></span>

<span data-ttu-id="641b2-179">同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="641b2-179">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="641b2-180">たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。</span><span class="sxs-lookup"><span data-stu-id="641b2-180">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="641b2-181">次の表は、MBAM サーバーのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-181">The following table lists the operating systems that are supported for the MBAM Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-182">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="641b2-182">Operating system</span></span></th>
<th align="left"><span data-ttu-id="641b2-183">エディション</span><span class="sxs-lookup"><span data-stu-id="641b2-183">Edition</span></span></th>
<th align="left"><span data-ttu-id="641b2-184">Service pack</span><span class="sxs-lookup"><span data-stu-id="641b2-184">Service pack</span></span></th>
<th align="left"><span data-ttu-id="641b2-185">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="641b2-185">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-186">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b2-186">Windows Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-187">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-187">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="641b2-188">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-189">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="641b2-189">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-190">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-190">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="641b2-191">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-191">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-192">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="641b2-192">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-193">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-193">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-194">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-194">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-195">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="641b2-195">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-196">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-196">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="641b2-197">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-197">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-198">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="641b2-198">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-199">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-199">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-200">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-200">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-201">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-201">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="641b2-202">エンタープライズドメインには、少なくとも1つの Windows Server 2008 (またはそれ以降) のドメインコントローラーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="641b2-202">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span>

### <a href="" id="bkmk-stand-alone-ramreqs"></a><span data-ttu-id="641b2-203">MBAM サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="641b2-203">MBAM Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="641b2-204">これらの要件は、MBAM スタンドアロンのトポロジを対象としています。</span><span class="sxs-lookup"><span data-stu-id="641b2-204">These requirements are for the MBAM Stand-alone topology.</span></span> <span data-ttu-id="641b2-205">Configuration Manager の統合トポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク領域の要件-Configuration Manager の統合トポロジ](#bkmk-cm-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-205">For the requirements for the Configuration Manager Integration topology, see [MBAM Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-206">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="641b2-206">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="641b2-207">最小要件</span><span class="sxs-lookup"><span data-stu-id="641b2-207">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="641b2-208">推奨要件</span><span class="sxs-lookup"><span data-stu-id="641b2-208">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-209">処理者</span><span class="sxs-lookup"><span data-stu-id="641b2-209">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-210">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="641b2-210">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-211">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="641b2-211">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-212">RAM</span><span class="sxs-lookup"><span data-stu-id="641b2-212">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-213">8 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-213">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-214">12 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-214">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-215">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="641b2-215">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-216">1 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-216">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-217">2 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-217">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-ramreqs"></a><span data-ttu-id="641b2-218">MBAM サーバープロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ</span><span class="sxs-lookup"><span data-stu-id="641b2-218">MBAM Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="641b2-219">次の表は、Configuration Manager の統合トポロジを使用している場合に、MBAM サーバーのサーバープロセッサ、RAM、およびディスク領域の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-219">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span> <span data-ttu-id="641b2-220">スタンドアロントポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ](#bkmk-stand-alone-ramreqs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="641b2-220">For the requirements for the Stand-alone topology, see [MBAM Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-221">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="641b2-221">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="641b2-222">最小要件</span><span class="sxs-lookup"><span data-stu-id="641b2-222">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="641b2-223">推奨要件</span><span class="sxs-lookup"><span data-stu-id="641b2-223">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-224">処理者</span><span class="sxs-lookup"><span data-stu-id="641b2-224">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-225">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="641b2-225">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-226">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="641b2-226">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-227">RAM</span><span class="sxs-lookup"><span data-stu-id="641b2-227">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-228">4 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-228">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-229">8 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-229">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-230">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="641b2-230">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-231">1 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-231">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-232">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a><span data-ttu-id="641b2-233">MBAM でサポートされている Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="641b2-233">Versions of Configuration Manager that MBAM supports</span></span>

<span data-ttu-id="641b2-234">MBAM は、次のバージョンの Configuration Manager をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="641b2-234">MBAM supports the following versions of Configuration Manager.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-235">サポートされているバージョン</span><span class="sxs-lookup"><span data-stu-id="641b2-235">Supported version</span></span></th>
<th align="left"><span data-ttu-id="641b2-236">Service pack</span><span class="sxs-lookup"><span data-stu-id="641b2-236">Service pack</span></span></th>
<th align="left"><span data-ttu-id="641b2-237">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="641b2-237">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-238">Microsoft System Center Configuration Manager (現在のブランチ)、1902までのバージョン</span><span class="sxs-lookup"><span data-stu-id="641b2-238">Microsoft System Center Configuration Manager (Current Branch), versions up to 1902</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-239">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-239">64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-240">Microsoft System Center Configuration Manager 1806</span><span class="sxs-lookup"><span data-stu-id="641b2-240">Microsoft System Center Configuration Manager 1806</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-241">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-241">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-242">Microsoft System Center Configuration Manager (LTSB-バージョン 1606)</span><span class="sxs-lookup"><span data-stu-id="641b2-242">Microsoft System Center Configuration Manager (LTSB - version 1606)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-243">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-243">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-244">Microsoft System Center 2012 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="641b2-244">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-245">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-245">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-246">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-246">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-247">Microsoft System Center Configuration Manager 2007 R2 以降</span><span class="sxs-lookup"><span data-stu-id="641b2-247">Microsoft System Center Configuration Manager 2007 R2 or later</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-248">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-248">64-bit</span></span></p>

<span data-ttu-id="641b2-249">&gt;<strong>注 </strong> Configuration Manager 2007 R2 は32ビットですが、64ビット MBAM ソフトウェアと一致させるためには、64ビットのオペレーティングシステムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="641b2-249">&gt;<strong>Note</strong> Although Configuration Manager 2007 R2 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span>
</td>
</tr>
</tbody>
</table>



<span data-ttu-id="641b2-250">Configuration Manager サーバーでサポートされている構成の一覧については、使用している Configuration Manager のバージョンに対応した TechNet ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-250">For a list of supported configurations for the Configuration Manager Server, see the appropriate TechNet documentation for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="641b2-251">MBAM には、Configuration Manager サーバーに関する追加のシステム要件はありません。</span><span class="sxs-lookup"><span data-stu-id="641b2-251">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="641b2-252">SQL Server データベースの要件</span><span class="sxs-lookup"><span data-stu-id="641b2-252">SQL Server database requirements</span></span>

<span data-ttu-id="641b2-253">次の表には、回復データベース、コンプライアンスおよび監査データベース、レポート機能など、MBAM Server 機能でサポートされている Microsoft SQL Server バージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="641b2-253">The following table lists the Microsoft SQL Server versions that are supported for the MBAM Server features, which include the Recovery Database, Compliance and Audit Database, and the Reports feature.</span></span> <span data-ttu-id="641b2-254">必須バージョンは、スタンドアロンまたは Configuration Manager の統合トポロジに適用されます。</span><span class="sxs-lookup"><span data-stu-id="641b2-254">The required versions apply to the Stand-alone or the Configuration Manager Integration topologies.</span></span>

<span data-ttu-id="641b2-255">Sql Server は、 **sql \ _Latin1 \ _General \ _CP1 \ _CI \ _AS** にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="641b2-255">You must install SQL Server with the **SQL\_Latin1\_General\_CP1\_CI\_AS** collation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-256">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="641b2-256">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="641b2-257">エディション</span><span class="sxs-lookup"><span data-stu-id="641b2-257">Edition</span></span></th>
<th align="left"><span data-ttu-id="641b2-258">Service pack</span><span class="sxs-lookup"><span data-stu-id="641b2-258">Service pack</span></span></th>
<th align="left"><span data-ttu-id="641b2-259">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="641b2-259">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-260">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="641b2-260">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-261">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-261">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-262">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-262">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="641b2-263">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="641b2-263">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-264">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-264">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-265">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-265">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="641b2-266">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="641b2-266">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-267">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-267">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-268">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-268">SP1</span></span></p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p><span data-ttu-id="641b2-269">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-269">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-270">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="641b2-270">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-271">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-271">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-272">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="641b2-272">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-273">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-273">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-274">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="641b2-274">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-275">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-275">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-276">読み</span><span class="sxs-lookup"><span data-stu-id="641b2-276">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-277">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-277">64-bit</span></span></p></td>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-278">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="641b2-278">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-279">Standard または Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-279">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-280">読み</span><span class="sxs-lookup"><span data-stu-id="641b2-280">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-281">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-281">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

**<span data-ttu-id="641b2-282">備考</span><span class="sxs-lookup"><span data-stu-id="641b2-282">Note</span></span>**  
<span data-ttu-id="641b2-283">MBAM には、サポートされている最大の互換性レベルとして140があります。</span><span class="sxs-lookup"><span data-stu-id="641b2-283">MBAM has a maximum supported compatibility level of 140.</span></span> <span data-ttu-id="641b2-284">SQL Server 2019 で作成された新規データベースの既定の互換性レベルは150で、データベースの作成後に ALTER DATABASE コマンドを使用して、140以下に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="641b2-284">The default compatibility level for new databases created on SQL Server 2019 is 150 which will need to be altered to 140 or lower, using the ALTER DATABASE command, after the database has been created.</span></span> <span data-ttu-id="641b2-285">SQL server 2017 以降から移行された既存のデータベースは、以前の互換性レベルのままであり、変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="641b2-285">Existing databases migrated from SQL server 2017 or below will remain at their previous compatibility level and do not need to be altered.</span></span>

<span data-ttu-id="641b2-286">SQL 2016 をサポートするには、MDOP の2017年3月のサービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=54967  ます。また、sql 2017 をサポートするには、mdop 用の7月の2018サービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=57157 ます。</span><span class="sxs-lookup"><span data-stu-id="641b2-286">In order to support SQL 2016 you must install the March 2017 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=54967  and to support SQL 2017 you must install the July 2018 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=57157.</span></span> <span data-ttu-id="641b2-287">一般的に、最新のサービス更新プログラムには、すべてのバグ修正と新機能が含まれているため、常に最新の状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="641b2-287">In general stay current by always using the most recent servicing update as it also includes all bugfixes and new features.</span></span>


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a><span data-ttu-id="641b2-288">SQL Server プロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="641b2-288">SQL Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="641b2-289">次の表は、スタンドアロントポロジを使用している場合の SQL Server コンピューターに推奨されるサーバープロセッサ、RAM、およびディスク容量の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-289">The following table lists the recommended server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Stand-alone topology.</span></span> <span data-ttu-id="641b2-290">これらの要件はガイドとして使用してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-290">Use these requirements as a guide.</span></span> <span data-ttu-id="641b2-291">特定の要件は、企業でサポートしているクライアントコンピューターの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="641b2-291">Your specific requirements will vary based on the number of client computers you are supporting in your enterprise.</span></span> <span data-ttu-id="641b2-292">Configuration Manager の統合トポロジの要件については、「 [SQL Server プロセッサ、RAM、ディスク領域の要件-Configuration manager の統合トポロジ](#bkmk-cm-sql-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-292">To view the requirements for the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-sql-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-293">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="641b2-293">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="641b2-294">最小要件</span><span class="sxs-lookup"><span data-stu-id="641b2-294">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="641b2-295">推奨要件</span><span class="sxs-lookup"><span data-stu-id="641b2-295">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-296">処理者</span><span class="sxs-lookup"><span data-stu-id="641b2-296">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-297">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="641b2-297">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-298">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="641b2-298">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-299">RAM</span><span class="sxs-lookup"><span data-stu-id="641b2-299">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-300">8 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-300">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-301">12 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-301">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-302">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="641b2-302">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-303">5 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-303">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-304">5 GB 以上</span><span class="sxs-lookup"><span data-stu-id="641b2-304">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-sql-ramreqs"></a><span data-ttu-id="641b2-305">SQL Server プロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ</span><span class="sxs-lookup"><span data-stu-id="641b2-305">SQL Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="641b2-306">次の表は、Configuration Manager の統合トポロジを使用しているときの、Microsoft SQL Server コンピューターのサーバープロセッサ、RAM、ディスク容量の要件を示しています。「 [SQL Server プロセッサ、ram、ディスク容量の要件–スタンドアロントポロジ](#bkmk-sql-stand-alone-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-306">The following table lists the server processor, RAM, and disk space requirements for the Microsoft SQL Server computer when you are using the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-sql-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-307">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="641b2-307">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="641b2-308">最小要件</span><span class="sxs-lookup"><span data-stu-id="641b2-308">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="641b2-309">推奨要件</span><span class="sxs-lookup"><span data-stu-id="641b2-309">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-310">処理者</span><span class="sxs-lookup"><span data-stu-id="641b2-310">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-311">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="641b2-311">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-312">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="641b2-312">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-313">RAM</span><span class="sxs-lookup"><span data-stu-id="641b2-313">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-314">4 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-314">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-315">8 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-315">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-316">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="641b2-316">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-317">5 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-317">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-318">5 GB</span><span class="sxs-lookup"><span data-stu-id="641b2-318">5 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="641b2-319">MBAM クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="641b2-319">MBAM Client system requirements</span></span>


### <span data-ttu-id="641b2-320">クライアントのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="641b2-320">Client operating system requirements</span></span>

<span data-ttu-id="641b2-321">同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="641b2-321">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="641b2-322">たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。</span><span class="sxs-lookup"><span data-stu-id="641b2-322">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="641b2-323">次の表は、MBAM クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-323">The following table lists the operating systems that are supported for MBAM Client installation.</span></span> <span data-ttu-id="641b2-324">同じ要件は、スタンドアロンおよび構成マネージャーの統合トポロジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="641b2-324">The same requirements apply to the Stand-alone and the Configuration Manager Integration topologies.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-325">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="641b2-325">Operating system</span></span></th>
<th align="left"><span data-ttu-id="641b2-326">エディション</span><span class="sxs-lookup"><span data-stu-id="641b2-326">Edition</span></span></th>
<th align="left"><span data-ttu-id="641b2-327">Service pack</span><span class="sxs-lookup"><span data-stu-id="641b2-327">Service pack</span></span></th>
<th align="left"><span data-ttu-id="641b2-328">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="641b2-328">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
    <td align="left"><p><span data-ttu-id="641b2-329">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="641b2-329">Windows 10 IoT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="641b2-330">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-330">Enterprise</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p><span data-ttu-id="641b2-331">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-331">32-bit or 64-bit</span></span></p></td>
</tr><br/><tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-332">Windows 10</span><span class="sxs-lookup"><span data-stu-id="641b2-332">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-333">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-333">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-334">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-334">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-335">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="641b2-335">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-336">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-336">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-337">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-337">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-338">Windows 7</span><span class="sxs-lookup"><span data-stu-id="641b2-338">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-339">Enterprise または Ultimate</span><span class="sxs-lookup"><span data-stu-id="641b2-339">Enterprise or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-340">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-340">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-341">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-341">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-342">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="641b2-342">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-343">Windows 8.1 および Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-343">Windows 8.1 and Windows 10 Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-344">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-344">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="641b2-345">クライアント RAM の要件</span><span class="sxs-lookup"><span data-stu-id="641b2-345">Client RAM requirements</span></span>

<span data-ttu-id="641b2-346">MBAM クライアントのインストールに固有の RAM 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="641b2-346">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="641b2-347">MBAM グループポリシーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="641b2-347">MBAM Group Policy system requirements</span></span>


<span data-ttu-id="641b2-348">次の表は、MBAM グループポリシーテンプレートのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="641b2-348">The following table lists the operating systems that are supported for MBAM Group Policy Templates installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="641b2-349">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="641b2-349">Operating system</span></span></th>
<th align="left"><span data-ttu-id="641b2-350">エディション</span><span class="sxs-lookup"><span data-stu-id="641b2-350">Edition</span></span></th>
<th align="left"><span data-ttu-id="641b2-351">Service pack</span><span class="sxs-lookup"><span data-stu-id="641b2-351">Service pack</span></span></th>
<th align="left"><span data-ttu-id="641b2-352">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="641b2-352">System architecture</span></span></th>
</tr>
</thead>
<tbody>
 <tr class="even">
      <td align="left"><p><span data-ttu-id="641b2-353">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="641b2-353">Windows 10 IoT</span></span></p></td>
      <td align="left"><p><span data-ttu-id="641b2-354">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-354">Enterprise</span></span></p></td>
      <td align="left"><p></p></td>
      <td align="left"><p><span data-ttu-id="641b2-355">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-355">32-bit or 64-bit</span></span></p></td>
 </tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-356">Windows 10</span><span class="sxs-lookup"><span data-stu-id="641b2-356">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-357">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-357">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-358">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-358">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-359">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="641b2-359">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-360">Enterprise</span><span class="sxs-lookup"><span data-stu-id="641b2-360">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-361">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-361">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-362">Windows 7</span><span class="sxs-lookup"><span data-stu-id="641b2-362">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-363">Enterprise、または Ultimate</span><span class="sxs-lookup"><span data-stu-id="641b2-363">Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-364">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-364">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-365">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-365">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-366">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="641b2-366">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-367">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-367">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-368">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-368">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="641b2-369">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="641b2-369">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-370">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-370">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="641b2-371">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-371">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="641b2-372">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="641b2-372">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-373">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="641b2-373">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-374">SP1</span><span class="sxs-lookup"><span data-stu-id="641b2-374">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="641b2-375">64 ビット</span><span class="sxs-lookup"><span data-stu-id="641b2-375">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="641b2-376">Azure IaaS の MBAM</span><span class="sxs-lookup"><span data-stu-id="641b2-376">MBAM In Azure IaaS</span></span>

<span data-ttu-id="641b2-377">MBAM サーバーは、上記のサポート対象のすべての OS バージョンでサービス (IaaS) として展開することができます。また、オンプレミスでホストされている Active Directory または Azure IaaS にホストされている active directory に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="641b2-377">The MBAM server can be deployed in Azure Infrastructure as a Service (IaaS) on any of the supported OS versions listed above, connecting to an Active Directory hosted on premises or an Active Directory also hosted in Azure IaaS.</span></span>  <span data-ttu-id="641b2-378">Azure IaaS で Active Directory をセットアップして構成する方法については、 [こちらをご覧](https://msdn.microsoft.com/library/azure/jj156090.aspx)ください。</span><span class="sxs-lookup"><span data-stu-id="641b2-378">Documentation for setting up and configuring Active Directory on Azure IaaS is [here](https://msdn.microsoft.com/library/azure/jj156090.aspx).</span></span>

<span data-ttu-id="641b2-379">MBAM クライアントは仮想マシンではサポートされておらず、Azure IaaS でもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="641b2-379">The MBAM client is not supported on virtual machines and is also not supported on Azure IaaS.</span></span>


## <span data-ttu-id="641b2-380">サービスリリース</span><span class="sxs-lookup"><span data-stu-id="641b2-380">Service releases</span></span> 

- [<span data-ttu-id="641b2-381">2016年4月の修正プログラム</span><span class="sxs-lookup"><span data-stu-id="641b2-381">April 2016 hotfix</span></span>](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="641b2-382">2016年9月</span><span class="sxs-lookup"><span data-stu-id="641b2-382">September 2016</span></span>](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [<span data-ttu-id="641b2-383">2016 年 12 月</span><span class="sxs-lookup"><span data-stu-id="641b2-383">December 2016</span></span>](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [<span data-ttu-id="641b2-384">2017 年 3 月</span><span class="sxs-lookup"><span data-stu-id="641b2-384">March 2017</span></span>](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [<span data-ttu-id="641b2-385">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="641b2-385">June 2017</span></span>](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="641b2-386">2017 年 9 月</span><span class="sxs-lookup"><span data-stu-id="641b2-386">September 2017</span></span>](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [<span data-ttu-id="641b2-387">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="641b2-387">March 2018</span></span>](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="641b2-388">2018年7月</span><span class="sxs-lookup"><span data-stu-id="641b2-388">July 2018</span></span>](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="641b2-389">2019年5月</span><span class="sxs-lookup"><span data-stu-id="641b2-389">May 2019</span></span>](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## <span data-ttu-id="641b2-390">関連トピック</span><span class="sxs-lookup"><span data-stu-id="641b2-390">Related topics</span></span>


[<span data-ttu-id="641b2-391">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="641b2-391">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="641b2-392">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="641b2-392">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)




## <span data-ttu-id="641b2-393">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="641b2-393">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="641b2-394">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="641b2-394">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="641b2-395">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="641b2-395">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




