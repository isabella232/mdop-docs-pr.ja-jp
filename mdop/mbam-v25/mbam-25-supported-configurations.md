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
ms.openlocfilehash: 262cd8c259dc37b291cdaf02caf0e20b7515d38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823894"
---
# <span data-ttu-id="432c8-103">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="432c8-103">MBAM 2.5 Supported Configurations</span></span>


<span data-ttu-id="432c8-104">Microsoft BitLocker 管理と監視 (MBAM) 2.5 は、スタンドアロントポロジで、または MBAM を System Center Configuration Manager に統合した構成マネージャーの統合トポロジで実行できます。</span><span class="sxs-lookup"><span data-stu-id="432c8-104">You can run Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a Stand-alone topology or in a Configuration Manager Integration topology that integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="432c8-105">運用環境でいずれかのトポロジに推奨される構成を使用している場合、MBAM は最大 50万 MBAM クライアントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="432c8-105">If you use the recommended configuration for either topology in a production environment, MBAM supports up to 500,000 MBAM clients.</span></span> <span data-ttu-id="432c8-106">各トポロジの各サーバー上で構成される推奨アーキテクチャと機能については、「 [MBAM 2.5 向けの高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-106">For information about the recommended architecture and features that are configured on each server for each topology, see [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

<span data-ttu-id="432c8-107">構成マネージャーの統合トポロジに固有のその他の構成については、「MBAM でサポートされて[いる Configuration manager のバージョン](#bkmk-cm-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-107">For additional configurations that are specific to the Configuration Manager Integration topology, see [Versions of Configuration Manager that MBAM supports](#bkmk-cm-ramreqs).</span></span>

**<span data-ttu-id="432c8-108">注</span><span class="sxs-lookup"><span data-stu-id="432c8-108">Note</span></span>**  
<span data-ttu-id="432c8-109">Microsoft は、現在のサービスパックと、場合によっては、直前のサービスパックのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="432c8-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="432c8-110">お使いの製品のサポートタイムラインについては、[ライフサイクルでサポートさ](https://go.microsoft.com/fwlink/p/?LinkId=31975)れているサービスパックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="432c8-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="432c8-111">Microsoft サポートライフサイクルポリシーの詳細については、 [Microsoft サポートライフサイクルのサポートポリシー](https://go.microsoft.com/fwlink/p/?LinkId=31976)に関する FAQ を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



## <span data-ttu-id="432c8-112">MBAM でサポートされる言語</span><span class="sxs-lookup"><span data-stu-id="432c8-112">MBAM Supported Languages</span></span>


<span data-ttu-id="432c8-113">次の表は、mbam クライアント (セルフサービスポータルを含む) と mbam 2.5 と mbam 2.5 SP1 でサポートされている言語を示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-113">The following tables show the languages that are supported for the MBAM Client (including the Self-Service Portal) and the MBAM Server in MBAM 2.5 and MBAM 2.5 SP1.</span></span>

**<span data-ttu-id="432c8-114">MBAM 2.5 SP1 でサポートされる言語:</span><span class="sxs-lookup"><span data-stu-id="432c8-114">Supported Languages in MBAM 2.5 SP1:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-115">クライアント言語</span><span class="sxs-lookup"><span data-stu-id="432c8-115">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="432c8-116">サーバーの言語</span><span class="sxs-lookup"><span data-stu-id="432c8-116">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-117">チェコ語 (チェコ共和国) .cs-CZ</span><span class="sxs-lookup"><span data-stu-id="432c8-117">Czech (Czech Republic) cs-CZ</span></span></p>
<p><span data-ttu-id="432c8-118">デンマーク語 (デンマーク) da-DK</span><span class="sxs-lookup"><span data-stu-id="432c8-118">Danish (Denmark) da-DK</span></span></p>
<p><span data-ttu-id="432c8-119">オランダ語 (オランダ) nl-NL</span><span class="sxs-lookup"><span data-stu-id="432c8-119">Dutch (Netherlands) nl-NL</span></span></p>
<p><span data-ttu-id="432c8-120">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="432c8-120">English (United States) en-US</span></span></p>
<p><span data-ttu-id="432c8-121">フィンランド語 (フィンランド) fi</span><span class="sxs-lookup"><span data-stu-id="432c8-121">Finnish (Finland) fi-FI</span></span></p>
<p><span data-ttu-id="432c8-122">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="432c8-122">French (France) fr-FR</span></span></p>
<p><span data-ttu-id="432c8-123">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="432c8-123">German (Germany) de-DE</span></span></p>
<p><span data-ttu-id="432c8-124">ギリシャ語 (ギリシャ) el-GR</span><span class="sxs-lookup"><span data-stu-id="432c8-124">Greek (Greece) el-GR</span></span></p>
<p><span data-ttu-id="432c8-125">ハンガリー語 (ハンガリー) hu-HU</span><span class="sxs-lookup"><span data-stu-id="432c8-125">Hungarian (Hungary) hu-HU</span></span></p>
<p><span data-ttu-id="432c8-126">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="432c8-126">Italian (Italy) it-IT</span></span></p>
<p><span data-ttu-id="432c8-127">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="432c8-127">Japanese (Japan) ja-JP</span></span></p>
<p><span data-ttu-id="432c8-128">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="432c8-128">Korean (Korea) ko-KR</span></span></p>
<p><span data-ttu-id="432c8-129">ノルウェー語、ブークモール (ノルウェー) nb-いいえ</span><span class="sxs-lookup"><span data-stu-id="432c8-129">Norwegian, Bokmål (Norway) nb-NO</span></span></p>
<p><span data-ttu-id="432c8-130">ポーランド語 (ポーランド) pl-PL</span><span class="sxs-lookup"><span data-stu-id="432c8-130">Polish (Poland) pl-PL</span></span></p>
<p><span data-ttu-id="432c8-131">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="432c8-131">Portuguese (Brazil) pt-BR</span></span></p>
<p><span data-ttu-id="432c8-132">ポルトガル語 (ポルトガル) の pt-PT</span><span class="sxs-lookup"><span data-stu-id="432c8-132">Portuguese (Portugal) pt-PT</span></span></p>
<p><span data-ttu-id="432c8-133">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="432c8-133">Russian (Russia) ru-RU</span></span></p>
<p><span data-ttu-id="432c8-134">スロバキア語 (スロバキア) sk-SK</span><span class="sxs-lookup"><span data-stu-id="432c8-134">Slovak (Slovakia) sk-SK</span></span></p>
<p><span data-ttu-id="432c8-135">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="432c8-135">Spanish (Spain) es-ES</span></span></p>
<p><span data-ttu-id="432c8-136">スウェーデン語 (スウェーデン) sv-SE</span><span class="sxs-lookup"><span data-stu-id="432c8-136">Swedish (Sweden) sv-SE</span></span></p>
<p><span data-ttu-id="432c8-137">トルコ語 (トルコ) tr-TR</span><span class="sxs-lookup"><span data-stu-id="432c8-137">Turkish (Turkey) tr-TR</span></span></p>
<p><span data-ttu-id="432c8-138">スロベニア語 (スロベニア) sl-SI</span><span class="sxs-lookup"><span data-stu-id="432c8-138">Slovenian (Slovenia) sl-SI</span></span></p>
<p><span data-ttu-id="432c8-139">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="432c8-139">Simplified Chinese (PRC) zh-CN</span></span></p>
<p><span data-ttu-id="432c8-140">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="432c8-140">Traditional Chinese (Taiwan) zh-TW</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="432c8-141">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="432c8-141">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="432c8-142">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="432c8-142">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="432c8-143">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="432c8-143">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="432c8-144">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="432c8-144">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="432c8-145">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="432c8-145">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="432c8-146">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="432c8-146">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="432c8-147">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="432c8-147">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="432c8-148">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="432c8-148">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="432c8-149">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="432c8-149">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="432c8-150">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="432c8-150">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="432c8-151">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="432c8-151">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="432c8-152">MBAM 2.5 でサポートされる言語:</span><span class="sxs-lookup"><span data-stu-id="432c8-152">Supported Languages in MBAM 2.5:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-153">クライアント言語</span><span class="sxs-lookup"><span data-stu-id="432c8-153">Client Languages</span></span></th>
<th align="left"><span data-ttu-id="432c8-154">サーバーの言語</span><span class="sxs-lookup"><span data-stu-id="432c8-154">Server Languages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="432c8-155">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="432c8-155">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="432c8-156">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="432c8-156">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="432c8-157">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="432c8-157">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="432c8-158">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="432c8-158">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="432c8-159">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="432c8-159">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="432c8-160">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="432c8-160">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="432c8-161">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="432c8-161">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="432c8-162">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="432c8-162">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="432c8-163">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="432c8-163">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="432c8-164">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="432c8-164">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="432c8-165">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="432c8-165">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="432c8-166">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="432c8-166">English (United States) en-US</span></span></p></li>
<li><p><span data-ttu-id="432c8-167">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="432c8-167">French (France) fr-FR</span></span></p></li>
<li><p><span data-ttu-id="432c8-168">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="432c8-168">German (Germany) de-DE</span></span></p></li>
<li><p><span data-ttu-id="432c8-169">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="432c8-169">Italian (Italy) it-IT</span></span></p></li>
<li><p><span data-ttu-id="432c8-170">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="432c8-170">Japanese (Japan) ja-JP</span></span></p></li>
<li><p><span data-ttu-id="432c8-171">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="432c8-171">Korean (Korea) ko-KR</span></span></p></li>
<li><p><span data-ttu-id="432c8-172">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="432c8-172">Portuguese (Brazil) pt-BR</span></span></p></li>
<li><p><span data-ttu-id="432c8-173">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="432c8-173">Russian (Russia) ru-RU</span></span></p></li>
<li><p><span data-ttu-id="432c8-174">スペイン語 (スペイン) es-ES</span><span class="sxs-lookup"><span data-stu-id="432c8-174">Spanish (Spain) es-ES</span></span></p></li>
<li><p><span data-ttu-id="432c8-175">簡体字中国語 (PRC) zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="432c8-175">Simplified Chinese (PRC) zh-CN</span></span></p></li>
<li><p><span data-ttu-id="432c8-176">繁体字中国語 (台湾) zh-cn&platform-TW</span><span class="sxs-lookup"><span data-stu-id="432c8-176">Traditional Chinese (Taiwan) zh-TW</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="432c8-177">MBAM サーバーシステム要件</span><span class="sxs-lookup"><span data-stu-id="432c8-177">MBAM Server system requirements</span></span>


### <span data-ttu-id="432c8-178">MBAM サーバーオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="432c8-178">MBAM Server operating system requirements</span></span>

<span data-ttu-id="432c8-179">同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="432c8-179">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="432c8-180">たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。</span><span class="sxs-lookup"><span data-stu-id="432c8-180">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="432c8-181">次の表は、MBAM サーバーのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-181">The following table lists the operating systems that are supported for the MBAM Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-182">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="432c8-182">Operating system</span></span></th>
<th align="left"><span data-ttu-id="432c8-183">エディション</span><span class="sxs-lookup"><span data-stu-id="432c8-183">Edition</span></span></th>
<th align="left"><span data-ttu-id="432c8-184">Service pack</span><span class="sxs-lookup"><span data-stu-id="432c8-184">Service pack</span></span></th>
<th align="left"><span data-ttu-id="432c8-185">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="432c8-185">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-186">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="432c8-186">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-187">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-187">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="432c8-188">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-188">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-189">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="432c8-189">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-190">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-190">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-191">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-191">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-192">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="432c8-192">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-193">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-193">Standard or Datacenter</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="432c8-194">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-194">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-195">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="432c8-195">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-196">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-196">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-197">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-197">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-198">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-198">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="432c8-199">エンタープライズドメインには、少なくとも1つの Windows Server 2008 (またはそれ以降) のドメインコントローラーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="432c8-199">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span>

### <a href="" id="bkmk-stand-alone-ramreqs"></a><span data-ttu-id="432c8-200">MBAM サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="432c8-200">MBAM Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="432c8-201">これらの要件は、MBAM スタンドアロンのトポロジを対象としています。</span><span class="sxs-lookup"><span data-stu-id="432c8-201">These requirements are for the MBAM Stand-alone topology.</span></span> <span data-ttu-id="432c8-202">Configuration Manager の統合トポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク領域の要件-Configuration Manager の統合トポロジ](#bkmk-cm-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-202">For the requirements for the Configuration Manager Integration topology, see [MBAM Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-203">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="432c8-203">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="432c8-204">最小要件</span><span class="sxs-lookup"><span data-stu-id="432c8-204">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="432c8-205">推奨要件</span><span class="sxs-lookup"><span data-stu-id="432c8-205">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-206">処理者</span><span class="sxs-lookup"><span data-stu-id="432c8-206">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-207">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="432c8-207">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-208">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="432c8-208">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-209">RAM</span><span class="sxs-lookup"><span data-stu-id="432c8-209">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-210">8 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-210">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-211">12 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-211">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-212">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="432c8-212">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-213">1 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-213">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-214">2 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-214">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-ramreqs"></a><span data-ttu-id="432c8-215">MBAM サーバープロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ</span><span class="sxs-lookup"><span data-stu-id="432c8-215">MBAM Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="432c8-216">次の表は、Configuration Manager の統合トポロジを使用している場合に、MBAM サーバーのサーバープロセッサ、RAM、およびディスク領域の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-216">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span> <span data-ttu-id="432c8-217">スタンドアロントポロジの要件については、「 [Mbam サーバープロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ](#bkmk-stand-alone-ramreqs)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="432c8-217">For the requirements for the Stand-alone topology, see [MBAM Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-218">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="432c8-218">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="432c8-219">最小要件</span><span class="sxs-lookup"><span data-stu-id="432c8-219">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="432c8-220">推奨要件</span><span class="sxs-lookup"><span data-stu-id="432c8-220">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-221">処理者</span><span class="sxs-lookup"><span data-stu-id="432c8-221">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-222">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="432c8-222">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-223">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="432c8-223">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-224">RAM</span><span class="sxs-lookup"><span data-stu-id="432c8-224">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-225">4 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-225">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-226">8 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-226">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-227">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="432c8-227">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-228">1 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-228">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-229">2 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-229">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cmversions"></a><span data-ttu-id="432c8-230">MBAM でサポートされている Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="432c8-230">Versions of Configuration Manager that MBAM supports</span></span>

<span data-ttu-id="432c8-231">MBAM は、次のバージョンの Configuration Manager をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="432c8-231">MBAM supports the following versions of Configuration Manager.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-232">サポートされているバージョン</span><span class="sxs-lookup"><span data-stu-id="432c8-232">Supported version</span></span></th>
<th align="left"><span data-ttu-id="432c8-233">Service pack</span><span class="sxs-lookup"><span data-stu-id="432c8-233">Service pack</span></span></th>
<th align="left"><span data-ttu-id="432c8-234">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="432c8-234">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-235">Microsoft System Center Configuration Manager (現在のブランチ)、1902までのバージョン</span><span class="sxs-lookup"><span data-stu-id="432c8-235">Microsoft System Center Configuration Manager (Current Branch), versions up to 1902</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-236">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-236">64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-237">Microsoft System Center Configuration Manager 1806</span><span class="sxs-lookup"><span data-stu-id="432c8-237">Microsoft System Center Configuration Manager 1806</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-238">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-238">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-239">Microsoft System Center Configuration Manager (LTSB-バージョン 1606)</span><span class="sxs-lookup"><span data-stu-id="432c8-239">Microsoft System Center Configuration Manager (LTSB - version 1606)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-240">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-240">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-241">Microsoft System Center 2012 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="432c8-241">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-242">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-242">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-243">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-243">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-244">Microsoft System Center Configuration Manager 2007 R2 以降</span><span class="sxs-lookup"><span data-stu-id="432c8-244">Microsoft System Center Configuration Manager 2007 R2 or later</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-245">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-245">64-bit</span></span></p>

<span data-ttu-id="432c8-246">&gt;<strong>注 </strong> Configuration Manager 2007 R2 は32ビットですが、64ビット MBAM ソフトウェアと一致させるためには、64ビットのオペレーティングシステムにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="432c8-246">&gt;<strong>Note</strong> Although Configuration Manager 2007 R2 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span>
</td>
</tr>
</tbody>
</table>



<span data-ttu-id="432c8-247">Configuration Manager サーバーでサポートされている構成の一覧については、使用している Configuration Manager のバージョンに対応した TechNet ドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-247">For a list of supported configurations for the Configuration Manager Server, see the appropriate TechNet documentation for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="432c8-248">MBAM には、Configuration Manager サーバーに関する追加のシステム要件はありません。</span><span class="sxs-lookup"><span data-stu-id="432c8-248">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="432c8-249">SQL Server データベースの要件</span><span class="sxs-lookup"><span data-stu-id="432c8-249">SQL Server database requirements</span></span>

<span data-ttu-id="432c8-250">次の表には、回復データベース、コンプライアンスおよび監査データベース、レポート機能など、MBAM Server 機能でサポートされている Microsoft SQL Server バージョンの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="432c8-250">The following table lists the Microsoft SQL Server versions that are supported for the MBAM Server features, which include the Recovery Database, Compliance and Audit Database, and the Reports feature.</span></span> <span data-ttu-id="432c8-251">必須バージョンは、スタンドアロンまたは Configuration Manager の統合トポロジに適用されます。</span><span class="sxs-lookup"><span data-stu-id="432c8-251">The required versions apply to the Stand-alone or the Configuration Manager Integration topologies.</span></span>

<span data-ttu-id="432c8-252">Sql Server は、 **sql \ _Latin1 \ _General \ _CP1 \ _CI \ _AS**にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="432c8-252">You must install SQL Server with the **SQL\_Latin1\_General\_CP1\_CI\_AS** collation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-253">SQL Server のバージョン</span><span class="sxs-lookup"><span data-stu-id="432c8-253">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="432c8-254">エディション</span><span class="sxs-lookup"><span data-stu-id="432c8-254">Edition</span></span></th>
<th align="left"><span data-ttu-id="432c8-255">Service pack</span><span class="sxs-lookup"><span data-stu-id="432c8-255">Service pack</span></span></th>
<th align="left"><span data-ttu-id="432c8-256">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="432c8-256">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-257">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="432c8-257">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-258">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-258">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-259">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-259">64-bit</span></span></p></td><br/><tr class="even">
<td align="left"><p><span data-ttu-id="432c8-260">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="432c8-260">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-261">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-261">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-262">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-262">SP1</span></span></p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p><span data-ttu-id="432c8-263">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-263">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-264">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="432c8-264">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-265">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-265">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-266">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="432c8-266">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-267">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-267">64-bit</span></span></p></td>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-268">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="432c8-268">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-269">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-269">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-270">読み</span><span class="sxs-lookup"><span data-stu-id="432c8-270">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-271">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-271">64-bit</span></span></p></td>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-272">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="432c8-272">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-273">Standard または Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-273">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-274">読み</span><span class="sxs-lookup"><span data-stu-id="432c8-274">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-275">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-275">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

**<span data-ttu-id="432c8-276">注</span><span class="sxs-lookup"><span data-stu-id="432c8-276">Note</span></span>**  
<span data-ttu-id="432c8-277">SQL 2016 をサポートするには、MDOP の2017年3月のサービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=54967 ます。また、sql 2017 をサポートするには、mdop 用の7月の2018サービスリリースをインストールする必要があり https://www.microsoft.com/download/details.aspx?id=57157 ます。</span><span class="sxs-lookup"><span data-stu-id="432c8-277">In order to support SQL 2016 you must install the March 2017 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=54967  and to support SQL 2017 you must install the July 2018 Servicing Release for MDOP https://www.microsoft.com/download/details.aspx?id=57157.</span></span> <span data-ttu-id="432c8-278">一般的に、最新のサービス更新プログラムには、すべてのバグ修正と新機能が含まれているため、常に最新の状態を維持できます。</span><span class="sxs-lookup"><span data-stu-id="432c8-278">In general stay current by always using the most recent servicing update as it also includes all bugfixes and new features.</span></span>


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a><span data-ttu-id="432c8-279">SQL Server プロセッサ、RAM、ディスク容量の要件–スタンドアロントポロジ</span><span class="sxs-lookup"><span data-stu-id="432c8-279">SQL Server processor, RAM, and disk space requirements – Stand-alone topology</span></span>

<span data-ttu-id="432c8-280">次の表は、スタンドアロントポロジを使用している場合の SQL Server コンピューターに推奨されるサーバープロセッサ、RAM、およびディスク容量の要件を示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-280">The following table lists the recommended server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Stand-alone topology.</span></span> <span data-ttu-id="432c8-281">これらの要件はガイドとして使用してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-281">Use these requirements as a guide.</span></span> <span data-ttu-id="432c8-282">特定の要件は、企業でサポートしているクライアントコンピューターの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="432c8-282">Your specific requirements will vary based on the number of client computers you are supporting in your enterprise.</span></span> <span data-ttu-id="432c8-283">Configuration Manager の統合トポロジの要件については、「 [SQL Server プロセッサ、RAM、ディスク領域の要件-Configuration manager の統合トポロジ](#bkmk-cm-sql-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-283">To view the requirements for the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements - Configuration Manager Integration Topology](#bkmk-cm-sql-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-284">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="432c8-284">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="432c8-285">最小要件</span><span class="sxs-lookup"><span data-stu-id="432c8-285">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="432c8-286">推奨要件</span><span class="sxs-lookup"><span data-stu-id="432c8-286">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-287">処理者</span><span class="sxs-lookup"><span data-stu-id="432c8-287">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-288">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="432c8-288">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-289">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="432c8-289">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-290">RAM</span><span class="sxs-lookup"><span data-stu-id="432c8-290">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-291">8 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-291">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-292">12 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-292">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-293">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="432c8-293">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-294">5 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-294">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-295">5 GB 以上</span><span class="sxs-lookup"><span data-stu-id="432c8-295">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-cm-sql-ramreqs"></a><span data-ttu-id="432c8-296">SQL Server プロセッサ、RAM、ディスク容量の要件-Configuration Manager の統合トポロジ</span><span class="sxs-lookup"><span data-stu-id="432c8-296">SQL Server processor, RAM, and disk space requirements - Configuration Manager Integration topology</span></span>

<span data-ttu-id="432c8-297">次の表は、Configuration Manager の統合トポロジを使用しているときの、Microsoft SQL Server コンピューターのサーバープロセッサ、RAM、ディスク容量の要件を示しています。「 [SQL Server プロセッサ、ram、ディスク容量の要件–スタンドアロントポロジ](#bkmk-sql-stand-alone-ramreqs)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-297">The following table lists the server processor, RAM, and disk space requirements for the Microsoft SQL Server computer when you are using the Configuration Manager Integration topology, see [SQL Server Processor, RAM, and Disk Space Requirements – Stand-alone Topology](#bkmk-sql-stand-alone-ramreqs).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-298">ハードウェア項目</span><span class="sxs-lookup"><span data-stu-id="432c8-298">Hardware item</span></span></th>
<th align="left"><span data-ttu-id="432c8-299">最小要件</span><span class="sxs-lookup"><span data-stu-id="432c8-299">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="432c8-300">推奨要件</span><span class="sxs-lookup"><span data-stu-id="432c8-300">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-301">処理者</span><span class="sxs-lookup"><span data-stu-id="432c8-301">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-302">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="432c8-302">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-303">2.33 GHz 以上</span><span class="sxs-lookup"><span data-stu-id="432c8-303">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-304">RAM</span><span class="sxs-lookup"><span data-stu-id="432c8-304">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-305">4 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-305">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-306">8 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-306">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-307">空きディスク領域</span><span class="sxs-lookup"><span data-stu-id="432c8-307">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-308">5 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-308">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-309">5 GB</span><span class="sxs-lookup"><span data-stu-id="432c8-309">5 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="432c8-310">MBAM クライアントシステム要件</span><span class="sxs-lookup"><span data-stu-id="432c8-310">MBAM Client system requirements</span></span>


### <span data-ttu-id="432c8-311">クライアントのオペレーティングシステム要件</span><span class="sxs-lookup"><span data-stu-id="432c8-311">Client operating system requirements</span></span>

<span data-ttu-id="432c8-312">同じ1行のオペレーティングシステムで MBAM クライアントと MBAM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="432c8-312">We strongly recommend that you run the MBAM Client and MBAM Server on the same line of operating systems.</span></span> <span data-ttu-id="432c8-313">たとえば、windows 10 windows Server 2016、windows 8.1 with windows Server 2012 R2 などを使用します。</span><span class="sxs-lookup"><span data-stu-id="432c8-313">For example, Windows 10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

<span data-ttu-id="432c8-314">次の表は、MBAM クライアントのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-314">The following table lists the operating systems that are supported for MBAM Client installation.</span></span> <span data-ttu-id="432c8-315">同じ要件は、スタンドアロンおよび構成マネージャーの統合トポロジにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="432c8-315">The same requirements apply to the Stand-alone and the Configuration Manager Integration topologies.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-316">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="432c8-316">Operating system</span></span></th>
<th align="left"><span data-ttu-id="432c8-317">エディション</span><span class="sxs-lookup"><span data-stu-id="432c8-317">Edition</span></span></th>
<th align="left"><span data-ttu-id="432c8-318">Service pack</span><span class="sxs-lookup"><span data-stu-id="432c8-318">Service pack</span></span></th>
<th align="left"><span data-ttu-id="432c8-319">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="432c8-319">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
    <td align="left"><p><span data-ttu-id="432c8-320">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="432c8-320">Windows 10 IoT</span></span></p></td>
    <td align="left"><p><span data-ttu-id="432c8-321">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-321">Enterprise</span></span></p></td>
    <td align="left"><p></p></td>
    <td align="left"><p><span data-ttu-id="432c8-322">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-322">32-bit or 64-bit</span></span></p></td>
</tr><br/><tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-323">Windows 10</span><span class="sxs-lookup"><span data-stu-id="432c8-323">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-324">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-324">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-325">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-325">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-326">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="432c8-326">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-327">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-327">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-328">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-328">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-329">Windows 7</span><span class="sxs-lookup"><span data-stu-id="432c8-329">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-330">Enterprise または Ultimate</span><span class="sxs-lookup"><span data-stu-id="432c8-330">Enterprise or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-331">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-331">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-332">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-332">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-333">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="432c8-333">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-334">Windows 8.1 および Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-334">Windows 8.1 and Windows 10 Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-335">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-335">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="432c8-336">クライアント RAM の要件</span><span class="sxs-lookup"><span data-stu-id="432c8-336">Client RAM requirements</span></span>

<span data-ttu-id="432c8-337">MBAM クライアントのインストールに固有の RAM 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="432c8-337">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="432c8-338">MBAM グループポリシーのシステム要件</span><span class="sxs-lookup"><span data-stu-id="432c8-338">MBAM Group Policy system requirements</span></span>


<span data-ttu-id="432c8-339">次の表は、MBAM グループポリシーテンプレートのインストールでサポートされているオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="432c8-339">The following table lists the operating systems that are supported for MBAM Group Policy Templates installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="432c8-340">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="432c8-340">Operating system</span></span></th>
<th align="left"><span data-ttu-id="432c8-341">エディション</span><span class="sxs-lookup"><span data-stu-id="432c8-341">Edition</span></span></th>
<th align="left"><span data-ttu-id="432c8-342">Service pack</span><span class="sxs-lookup"><span data-stu-id="432c8-342">Service pack</span></span></th>
<th align="left"><span data-ttu-id="432c8-343">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="432c8-343">System architecture</span></span></th>
</tr>
</thead>
<tbody>
 <tr class="even">
      <td align="left"><p><span data-ttu-id="432c8-344">Windows 10 IoT</span><span class="sxs-lookup"><span data-stu-id="432c8-344">Windows 10 IoT</span></span></p></td>
      <td align="left"><p><span data-ttu-id="432c8-345">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-345">Enterprise</span></span></p></td>
      <td align="left"><p></p></td>
      <td align="left"><p><span data-ttu-id="432c8-346">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-346">32-bit or 64-bit</span></span></p></td>
 </tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-347">Windows 10</span><span class="sxs-lookup"><span data-stu-id="432c8-347">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-348">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-348">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-349">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-349">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-350">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="432c8-350">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-351">Enterprise</span><span class="sxs-lookup"><span data-stu-id="432c8-351">Enterprise</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-352">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-352">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-353">Windows 7</span><span class="sxs-lookup"><span data-stu-id="432c8-353">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-354">Enterprise、または Ultimate</span><span class="sxs-lookup"><span data-stu-id="432c8-354">Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-355">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-355">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-356">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-356">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-357">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="432c8-357">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-358">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-358">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-359">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-359">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="432c8-360">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="432c8-360">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-361">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-361">Standard or Datacenter</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="432c8-362">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-362">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="432c8-363">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="432c8-363">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-364">標準、エンタープライズ、またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="432c8-364">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-365">SP1</span><span class="sxs-lookup"><span data-stu-id="432c8-365">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="432c8-366">64 ビット</span><span class="sxs-lookup"><span data-stu-id="432c8-366">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

## <span data-ttu-id="432c8-367">Azure IaaS の MBAM</span><span class="sxs-lookup"><span data-stu-id="432c8-367">MBAM In Azure IaaS</span></span>

<span data-ttu-id="432c8-368">MBAM サーバーは、上記のサポート対象のすべての OS バージョンでサービス (IaaS) として展開することができます。また、オンプレミスでホストされている Active Directory または Azure IaaS にホストされている active directory に接続することもできます。</span><span class="sxs-lookup"><span data-stu-id="432c8-368">The MBAM server can be deployed in Azure Infrastructure as a Service (IaaS) on any of the supported OS versions listed above, connecting to an Active Directory hosted on premises or an Active Directory also hosted in Azure IaaS.</span></span>  <span data-ttu-id="432c8-369">Azure IaaS で Active Directory をセットアップして構成する方法については、[こちらをご覧](https://msdn.microsoft.com/library/azure/jj156090.aspx)ください。</span><span class="sxs-lookup"><span data-stu-id="432c8-369">Documentation for setting up and configuring Active Directory on Azure IaaS is [here](https://msdn.microsoft.com/library/azure/jj156090.aspx).</span></span>

<span data-ttu-id="432c8-370">MBAM クライアントは仮想マシンではサポートされておらず、Azure IaaS でもサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="432c8-370">The MBAM client is not supported on virtual machines and is also not supported on Azure IaaS.</span></span>


## <span data-ttu-id="432c8-371">サービスリリース</span><span class="sxs-lookup"><span data-stu-id="432c8-371">Service releases</span></span> 

- [<span data-ttu-id="432c8-372">2016年4月の修正プログラム</span><span class="sxs-lookup"><span data-stu-id="432c8-372">April 2016 hotfix</span></span>](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="432c8-373">2016年9月</span><span class="sxs-lookup"><span data-stu-id="432c8-373">September 2016</span></span>](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [<span data-ttu-id="432c8-374">2016 年 12 月</span><span class="sxs-lookup"><span data-stu-id="432c8-374">December 2016</span></span>](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [<span data-ttu-id="432c8-375">2017 年 3 月</span><span class="sxs-lookup"><span data-stu-id="432c8-375">March 2017</span></span>](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [<span data-ttu-id="432c8-376">2017 年 6 月</span><span class="sxs-lookup"><span data-stu-id="432c8-376">June 2017</span></span>](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="432c8-377">2017 年 9 月</span><span class="sxs-lookup"><span data-stu-id="432c8-377">September 2017</span></span>](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [<span data-ttu-id="432c8-378">2018 年 3 月</span><span class="sxs-lookup"><span data-stu-id="432c8-378">March 2018</span></span>](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="432c8-379">2018年7月</span><span class="sxs-lookup"><span data-stu-id="432c8-379">July 2018</span></span>](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [<span data-ttu-id="432c8-380">2019年5月</span><span class="sxs-lookup"><span data-stu-id="432c8-380">May 2019</span></span>](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## <span data-ttu-id="432c8-381">関連トピック</span><span class="sxs-lookup"><span data-stu-id="432c8-381">Related topics</span></span>


[<span data-ttu-id="432c8-382">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="432c8-382">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="432c8-383">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="432c8-383">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)




## <span data-ttu-id="432c8-384">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="432c8-384">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="432c8-385">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="432c8-385">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="432c8-386">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="432c8-386">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




