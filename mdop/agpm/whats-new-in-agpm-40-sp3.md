---
title: AGPM 4.0 SP3 の新機能
description: AGPM 4.0 SP3 の新機能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 44e7dc6c5de75ae3a5e5def638974bae20ad2a1e
ms.sourcegitcommit: 594b6e431af98562e0b806e224d2c5c7e07d2c77
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "10895771"
---
# <span data-ttu-id="b9160-103">AGPM 4.0 SP3 の新機能</span><span class="sxs-lookup"><span data-stu-id="b9160-103">What's New in AGPM 4.0 SP3</span></span>


<span data-ttu-id="b9160-104">このコンテンツでは、Microsoft Advanced グループポリシー管理 (AGPM) 4.0 Service Pack3 (SP3) の拡張機能とサポートされる構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9160-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="b9160-105">このコンテンツと他の AGPM ドキュメントの間に違いがある場合は、このコンテンツには権限があることを考慮して、他のドキュメントを置き換えることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="b9160-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="b9160-106">新機能</span><span class="sxs-lookup"><span data-stu-id="b9160-106">What’s new</span></span>


<span data-ttu-id="b9160-107">AGPM 4.0 SP3 は、次の機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="b9160-107">AGPM4.0 SP3 supports the following features and functionality.</span></span>

### <span data-ttu-id="b9160-108">Windows 10 のサポート</span><span class="sxs-lookup"><span data-stu-id="b9160-108">Support for Windows10</span></span>

<span data-ttu-id="b9160-109">AGPM 4.0 SP3 では、Windows 10 と Windows Server 2016 オペレーティングシステムのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b9160-109">AGPM4.0 SP3 adds support for the Windows10 and Windows Server 2016 operating systems.</span></span>

### <span data-ttu-id="b9160-110">PowerShell のサポート</span><span class="sxs-lookup"><span data-stu-id="b9160-110">Support for PowerShell</span></span>

<span data-ttu-id="b9160-111">AGPM 4.0 SP3 では、PowerShell コマンドレットのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b9160-111">AGPM4.0 SP3 adds support for PowerShell cmdlets.</span></span> <span data-ttu-id="b9160-112">説明や構文など、AGPM 4.0 SP3 で利用できるコマンドレットの一覧については、「 [Windows PowerShell による Microsoft デスクトップ最適化パックオートメーション](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="b9160-112">For a list of the cmdlets available in AGPM4.0 SP3, including descriptions and syntax, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps).</span></span>

### <span data-ttu-id="b9160-113">顧客のフィードバックと修正プログラムのロールアップ</span><span class="sxs-lookup"><span data-stu-id="b9160-113">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="b9160-114">AGPM 4.0 SP3 には、Microsoft Advanced のグループポリシー管理 4.0 SP2 までのすべての修正プログラムが含まれています。また、AGPM 4.0 SP2 以降で検出された問題に関する修正プログラムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9160-114">AGPM 4.0 SP3 includes a rollup of all fixes up to and including Microsoft Advanced Group Policy Management 4.0 SP2 and any fixes for issues found since AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="b9160-115">構成パラメーターを再入力せずに、AGPM 4.0 SP3 にアップグレードする機能</span><span class="sxs-lookup"><span data-stu-id="b9160-115">Ability to upgrade to AGPM4.0 SP3 without re-entering configuration parameters</span></span>

<span data-ttu-id="b9160-116">次の表に示すように、agpm クライアントまたは AGPM サーバーを AGPM 4.0 SP3 にアップグレードすることができます。この場合は、AGPM 4.0 以降の構成パラメーターを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9160-116">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP3 without being prompted to re-enter configuration parameters (called the Smart Upgrade) only from AGPM4.0 and later, as shown in the following table.</span></span> <span data-ttu-id="b9160-117">表に示されているように、他のバージョンの AGPM から AGPM 4.0 SP3 にアップグレードする場合は、従来のアップグレードを使用する必要があります。これには、構成パラメーターを再入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b9160-117">If you are upgrading to AGPM4.0 SP3 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="b9160-118">AGPM の各バージョンは特定のオペレーティングシステムに関連付けられているため、「[インストールする agpm のバージョンを選択](https://go.microsoft.com/fwlink/?LinkId=254350)する」を参照して、agpm をアップグレードする前に、適切なオペレーティングシステムにアップグレードしてください。</span><span class="sxs-lookup"><span data-stu-id="b9160-118">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="b9160-119">AGPM 4.0 SP3 でサポートされているアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-119">AGPM 4.0 SP3 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="b9160-120">アップグレードできる AGPM バージョン</span><span class="sxs-lookup"><span data-stu-id="b9160-120">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-121">2.5</span><span class="sxs-lookup"><span data-stu-id="b9160-121">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-122">3.0</span><span class="sxs-lookup"><span data-stu-id="b9160-122">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-123">4.0</span><span class="sxs-lookup"><span data-stu-id="b9160-123">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-124">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="b9160-124">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-125">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="b9160-125">4.0 SP2</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="b9160-126">4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="b9160-126">4.0 SP3</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-127">2.5</span><span class="sxs-lookup"><span data-stu-id="b9160-127">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-128">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-128">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-129">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-129">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-130">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-130">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-131">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-131">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-132">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-132">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-133">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-133">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-134">3.0</span><span class="sxs-lookup"><span data-stu-id="b9160-134">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-135">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-135">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-136">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-136">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-137">従来のアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-137">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-138">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-138">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-139">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-139">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-140">インストールがブロックされている</span><span class="sxs-lookup"><span data-stu-id="b9160-140">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-141">4.0</span><span class="sxs-lookup"><span data-stu-id="b9160-141">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-142">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-142">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-143">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-143">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-144">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-144">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-145">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-145">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-146">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-146">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-147">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-147">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="b9160-148">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-149">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-149">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-150">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-150">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-151">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-152">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-152">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-153">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-153">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-154">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-154">Smart Upgrade</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-155">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="b9160-155">4.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-156">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-156">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-157">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-158">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-159">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-159">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-160">該当なし</span><span class="sxs-lookup"><span data-stu-id="b9160-160">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-161">スマートアップグレード</span><span class="sxs-lookup"><span data-stu-id="b9160-161">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b9160-162">サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b9160-162">Supported configurations</span></span>


<span data-ttu-id="b9160-163">AGPM 4.0 SP3 では、次の表の構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b9160-163">AGPM4.0 SP3 supports the configurations in the following table.</span></span> <span data-ttu-id="b9160-164">AGPM では混合構成がサポートされますが、windows Server 2016、windows 8.1 with windows Server 2012 R2 など、同じオペレーティングシステムラインで AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b9160-164">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

**<span data-ttu-id="b9160-165">AGPM 4.0 SP3 でサポートされているオペレーティングシステムとポリシーの設定</span><span class="sxs-lookup"><span data-stu-id="b9160-165">AGPM4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="b9160-166">AGPM サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b9160-166">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b9160-167">AGPM クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b9160-167">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b9160-168">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="b9160-168">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-169">Windows Server 2019 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9160-169">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-170">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9160-170">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-171">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b9160-171">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-172">Windows Server 2016 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9160-172">Windows Server 2016 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-173">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9160-173">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-174">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b9160-174">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-175">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b9160-175">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-176">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b9160-176">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-177">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b9160-177">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-178">Windows Server2012 R2、Windows Server 2012、または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b9160-178">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-179">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b9160-179">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-180">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b9160-180">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-181">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b9160-181">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-182">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b9160-182">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-183">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b9160-183">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-184">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b9160-184">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-185">Windows Server2008 または Windows Vista Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b9160-185">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-186">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b9160-186">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b9160-187">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b9160-187">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-188">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b9160-188">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-189">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="b9160-189">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b9160-190">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b9160-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-191">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b9160-191">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b9160-192">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="b9160-192">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b9160-193">AGPM 4.0 SP3 をインストールするための前提条件</span><span class="sxs-lookup"><span data-stu-id="b9160-193">Prerequisites for installing AGPM4.0 SP3</span></span>

<span data-ttu-id="b9160-194">次の表では、.NET Framework 4.5.1、PowerShell 3.0、またはリモートサーバー管理ツールの GPMC が見つからない場合の、AGPM 4.0 SP3 クライアントとサーバーインストーラーの動作について説明します。</span><span class="sxs-lookup"><span data-stu-id="b9160-194">The following table describes the behavior of AGPM4.0 SP3 Client and Server installers when the .NET Framework4.5.1, PowerShell 3.0, or the GPMC in the Remote Server Administration Tools is missing.</span></span>

| <span data-ttu-id="b9160-195">AGPM クライアント</span><span class="sxs-lookup"><span data-stu-id="b9160-195">AGPM Client</span></span>            |                                                                                                 |                                                                            | <span data-ttu-id="b9160-196">AGPM サーバー</span><span class="sxs-lookup"><span data-stu-id="b9160-196">AGPM Server</span></span>                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="b9160-197">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b9160-197">Operating system</span></span>       | <span data-ttu-id="b9160-198">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b9160-198">.NET Framework</span></span>                                                                                  | <span data-ttu-id="b9160-199">PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9160-199">PowerShell</span></span>                                                                 | <span data-ttu-id="b9160-200">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="b9160-200">Remote Server Administration Tools</span></span>                                              | <span data-ttu-id="b9160-201">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="b9160-201">.NET Framework</span></span>                                                                                  | <span data-ttu-id="b9160-202">リモート サーバー管理ツール</span><span class="sxs-lookup"><span data-stu-id="b9160-202">Remote Server Administration Tools</span></span>                                              |
| <span data-ttu-id="b9160-203">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b9160-203">Windows 10</span></span>             | <span data-ttu-id="b9160-204">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-204">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-205">Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b9160-205">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-206">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-206">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-207">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-207">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-208">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-208">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="b9160-209">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b9160-209">Windows 8.1</span></span>            | <span data-ttu-id="b9160-210">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-210">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-211">Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b9160-211">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-212">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-212">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-213">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-213">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-214">GPMC が有効になっていないか、インストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-214">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="b9160-215">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b9160-215">Windows Server 2012 R2</span></span> | <span data-ttu-id="b9160-216">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-216">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-217">Powershell 3.0 がインストールされていない場合、インストーラーはインストールをブロックします。</span><span class="sxs-lookup"><span data-stu-id="b9160-217">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-218">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9160-218">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   | <span data-ttu-id="b9160-219">.NET Framework 4.5.1 が有効になっていない場合、またはインストールされていない場合は、インストーラーによってインストールがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="b9160-219">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="b9160-220">GPMC が有効になっていない場合は、インストール中にインストーラーによって有効になります。</span><span class="sxs-lookup"><span data-stu-id="b9160-220">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   |

 

## <span data-ttu-id="b9160-221">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="b9160-221">How to Get MDOP Technologies</span></span>


<span data-ttu-id="b9160-222">AGPM 4.0 SP3 は、MDOP 2015 以降の Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b9160-222">AGPM 4.0 SP3 is a part of the Microsoft Desktop Optimization Pack (MDOP) since MDOP 2015.</span></span> <span data-ttu-id="b9160-223">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="b9160-223">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="b9160-224">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="b9160-224">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="b9160-225">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b9160-225">Related topics</span></span>


[<span data-ttu-id="b9160-226">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="b9160-226">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="b9160-227">Microsoft Advanced Group Policy Management (AGPM) 4.0 SP3 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="b9160-227">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[<span data-ttu-id="b9160-228">インストールする AGPM のバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="b9160-228">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





