---
title: インストールする AGPM のバージョンの選択
description: インストールする AGPM のバージョンの選択
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: f8a69fb323d9f47c5b906ac3abc6ec59376ee6f7
ms.sourcegitcommit: 0a7dee11289780336d9c24ebbf27c5c1ffee441c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905604"
---
# <span data-ttu-id="b7094-103">インストールする AGPM のバージョンの選択</span><span class="sxs-lookup"><span data-stu-id="b7094-103">Choosing Which Version of AGPM to Install</span></span>


<span data-ttu-id="b7094-104">Microsoft の高度なグループポリシー管理 (AGPM) の各リリースでは、Windows オペレーティングシステムの特定のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="b7094-104">Each release of MicrosoftAdvanced Group Policy Management (AGPM) supports specific versions of the Windows operating system.</span></span> <span data-ttu-id="b7094-105">同じ1行のオペレーティングシステムで AGPM クライアントと AGPM サーバーを実行することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b7094-105">We strongly recommend that you run the AGPM Client and AGPM Server on the same line of operating systems.</span></span> <span data-ttu-id="b7094-106">たとえば、windows 10 では windows Server 2016、windows 8.1 は windows Server2012 R2 などです。</span><span class="sxs-lookup"><span data-stu-id="b7094-106">For example, Windows 10 with Windows Server 2016, Windows8.1 with Windows Server2012 R2, and so on.</span></span>

<span data-ttu-id="b7094-107">このドメインのオペレーティングシステムの最新バージョンに AGPM サーバーをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b7094-107">We recommend that you install the AGPM Server on the most recent version of the operating system in the domain.</span></span> <span data-ttu-id="b7094-108">AGPM グループポリシー管理コンソール (GPMC) を使用して、グループポリシーオブジェクト (Gpo) のバックアップと復元を行います。</span><span class="sxs-lookup"><span data-stu-id="b7094-108">AGPM uses the Group Policy Management Console (GPMC) to back up and restore Group Policy Objects (GPOs).</span></span> <span data-ttu-id="b7094-109">新しいバージョンの GPMC は、以前のバージョンでは利用できないその他のポリシー設定を提供するため、最新バージョンのオペレーティングシステムを使用して、さらに多くのポリシー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="b7094-109">Because newer versions of the GPMC provide additional policy settings that are not available in earlier versions, you can manage more policy settings by using the most recent version of the operating system.</span></span>

<span data-ttu-id="b7094-110">すべてのバージョンの AGPM は、AGPM が実行されているオペレーティングシステムと同じバージョンまたはそれ以前のバージョンで導入されたポリシー設定のみを管理できます。</span><span class="sxs-lookup"><span data-stu-id="b7094-110">All versions of AGPM can manage only the policy settings that were introduced in the same version or an earlier version of the operating system on which AGPM is running.</span></span> <span data-ttu-id="b7094-111">たとえば、Windows Server 2012 に AGPM 4.0 SP2 をインストールした場合、Windows Server 2012 以前で導入されたポリシー設定を管理することはできますが、後で導入されたポリシー設定は Windows 8.1 または Windows Server2012 R2 で管理することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-111">For example, if you install AGPM4.0 SP2 on Windows Server 2012, you can manage policy settings that were introduced in Windows Server 2012 or earlier, but you cannot manage policy settings that were introduced later, in Windows8.1 or Windows Server2012 R2.</span></span>

<span data-ttu-id="b7094-112">AGPM サーバー上の GPMC のバージョンが、管理者がグループポリシーを管理するために使用するコンピューター上のバージョンよりも古い場合、AGPM サーバーでは、古いバージョンの GPMC で利用できないポリシー設定を保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-112">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store any policy settings that are not available in the older version of the GPMC.</span></span> <span data-ttu-id="b7094-113">Windows に含まれるグループ ポリシーの設定のスプレッドシートについては、[Windows および Windows Server のグループ ポリシー設定のリファレンスに関するページ](https://go.microsoft.com/fwlink/p/?LinkId=613627)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b7094-113">For a spreadsheet of Group Policy settings included in Windows, see [Group Policy Settings Reference for Windows and Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=613627).</span></span>

## <span data-ttu-id="b7094-114">AGPM 4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="b7094-114">AGPM4.0 SP3</span></span>


<span data-ttu-id="b7094-115">Windows 10 を実行しているコンピューターで Gpo を管理している場合は、AGPM 4.0 SP3 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7094-115">If you are using computers that are running Windows 10 to manage GPOs, you must use AGPM 4.0 SP3.</span></span> <span data-ttu-id="b7094-116">Windows 10 オペレーティングシステムを実行しているコンピューターには、以前のバージョンの AGPM をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-116">You cannot install earlier versions of AGPM on computers that are running the Windows 10 operating system.</span></span>

<span data-ttu-id="b7094-117">表1に、AGPM 4.0 SP3 をインストールできるオペレーティングシステムと、AGPM 4.0 SP3 を使って管理できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b7094-117">Table 1 lists the operating systems on which you can install AGPM4.0 SP3, and the policy settings that you can manage by using AGPM4.0 SP3.</span></span>

**<span data-ttu-id="b7094-118">表 1: AGPM 4.0 SP3 でサポートされているオペレーティングシステムとポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b7094-118">Table 1: AGPM 4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="b7094-119">AGPM サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-119">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-120">AGPM クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-120">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-121">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="b7094-121">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-122">Windows Server 2019 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7094-122">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-123">Windows Server 2019 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7094-123">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-124">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-124">Supported</span></span></p></td>
</tr>
 <tr class="even">
<td align="left"><p><span data-ttu-id="b7094-125">Windows Server 2019 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7094-125">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-126">Windows Server 2019 または Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7094-126">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-127">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-127">Supported</span></span></p></td>
</tr>
<tr class="edd">
<td align="left"><p><span data-ttu-id="b7094-128">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="b7094-128">Windows Server2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-129">Windows 10</span><span class="sxs-lookup"><span data-stu-id="b7094-129">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-130">KB 4015786 で説明されている警告でサポートされています <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></span><span class="sxs-lookup"><span data-stu-id="b7094-130">Supported with the caveats outlined in <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)">KB 4015786</span></span></a>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-131">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-131">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-132">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-132">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-133">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-133">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-134">Windows Server2012 R2、Windows Server 2012、または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-134">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-135">Windows Server 2012 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-135">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-136">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-136">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-137">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-137">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-138">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-139">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-139">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-140">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-140">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-141">Windows Server2008 または Windows Vista Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b7094-141">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-142">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-142">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-143">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-143">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-144">Windows Server 2012、Windows Server2008R2、Windows 8、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-144">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-145">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="b7094-145">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-146">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-146">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-147">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-147">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-148">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-148">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7094-149">AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="b7094-149">AGPM4.0 SP2</span></span>


<span data-ttu-id="b7094-150">Windows Server2012 R2 または Windows 8.1 が実行されているコンピューターを使って Gpo を管理している場合は、AGPM 4.0 SP2 を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b7094-150">If you are using computers that are running Windows Server2012 R2 or Windows8.1 to manage GPOs, you must use AGPM4.0 SP2.</span></span> <span data-ttu-id="b7094-151">これらのオペレーティングシステムを実行しているコンピューターには、以前のバージョンの AGPM をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-151">You cannot install earlier versions of AGPM on computers that are running those operating systems.</span></span>

<span data-ttu-id="b7094-152">表1に、AGPM 4.0 SP2 をインストールできるオペレーティングシステムと、AGPM 4.0 SP2 を使用して管理できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b7094-152">Table 1 lists the operating systems on which you can install AGPM4.0 SP2, and the policy settings that you can manage by using AGPM4.0 SP2.</span></span>

**<span data-ttu-id="b7094-153">表 2: AGPM 4.0 SP2 でサポートされているオペレーティングシステムとポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b7094-153">Table 2: AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="b7094-154">AGPM サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-154">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-155">AGPM クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-155">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-156">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="b7094-156">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-157">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-157">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-158">Windows Server2012 R2 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-158">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-159">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-160">Windows Server2012 R2、Windows Server 2012、または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-160">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-161">Windows Server 2012 または Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="b7094-161">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-162">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-162">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-163">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-163">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-164">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-164">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-165">サポートされますが、Windows 8.1 でのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-165">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-166">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-166">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-167">Windows Server2008 または Windows Vista Service Pack 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="b7094-167">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-168">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や環境設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-168">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-169">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-169">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-170">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-170">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-171">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="b7094-171">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-172">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-172">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-173">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-173">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-174">サポートされますが、windows Server2012 R2、Windows Server 2012、Windows Server2008R2、Windows 8.1、または Windows7 でのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-174">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7094-175">AGPM 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-175">AGPM4.0 SP1</span></span>


<span data-ttu-id="b7094-176">表2に、AGPM 4.0 SP1 をインストールできるオペレーティングシステムと、AGPM 4.0 SP1 を使って管理できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b7094-176">Table 2 lists the operating systems on which you can install AGPM 4.0 SP1, and the policy settings that you can manage by using AGPM4.0 SP1.</span></span>

**<span data-ttu-id="b7094-177">表 3: AGPM 4.0 SP1 でサポートされているオペレーティングシステムとポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b7094-177">Table 3: AGPM4.0 SP1 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="b7094-178">AGPM サーバーでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-179">AGPM クライアントでサポートされている構成</span><span class="sxs-lookup"><span data-stu-id="b7094-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="b7094-180">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="b7094-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-181">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b7094-181">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-182">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="b7094-182">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-183">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-184">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-184">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-185">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-185">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-186">サポートされますが、Windows 8.1 のみに存在するポリシー設定または設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-186">Supported, but cannot edit policy settings or preference items that exist only in Windows 8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-187">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-187">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-188">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-188">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-189">サポートされますが、Windows Server2008R2、または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-189">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-190">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-191">Windows Server 2012、Windows Server2008R2、または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-191">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-192">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-192">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-193">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-194">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-194">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-195">サポートされますが、Windows Server2008R2、または Windows7 にのみ存在するポリシー設定または設定項目を報告したり、編集したりすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-195">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7094-196">AGPM 4.0</span><span class="sxs-lookup"><span data-stu-id="b7094-196">AGPM4.0</span></span>


<span data-ttu-id="b7094-197">表3に、AGPM 4.0 をインストールできるオペレーティングシステムと、AGPM 4.0 を使って管理できるポリシー設定を示します。</span><span class="sxs-lookup"><span data-stu-id="b7094-197">Table 3 lists the operating systems on which you can install AGPM 4.0, and the policy settings that you can manage by using AGPM4.0.</span></span>

**<span data-ttu-id="b7094-198">表 4: AGPM 4.0 でサポートされているオペレーティングシステムとポリシー設定</span><span class="sxs-lookup"><span data-stu-id="b7094-198">Table 4: AGPM4.0 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7094-199">AGPM サーバーでサポートされているオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="b7094-199">Supported operating systems for the AGPM Server</span></span></th>
<th align="left"><span data-ttu-id="b7094-200">AGPM クライアントでサポートされているオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="b7094-200">Supported operating systems for the AGPM Client</span></span></th>
<th align="left"><span data-ttu-id="b7094-201">AGPM のサポート</span><span class="sxs-lookup"><span data-stu-id="b7094-201">AGPM Support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-202">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-202">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-203">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-203">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-204">サポートされています</span><span class="sxs-lookup"><span data-stu-id="b7094-204">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-205">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-205">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-206">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-206">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-207">サポートされていますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や設定項目は編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-207">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-208">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-208">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-209">Windows Server2008R2 または Windows7</span><span class="sxs-lookup"><span data-stu-id="b7094-209">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-210">サポートされていないアプリ</span><span class="sxs-lookup"><span data-stu-id="b7094-210">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-211">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-211">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-212">Windows Server2008 または Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-212">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-213">サポートされますが、Windows Server2008R2 または Windows7 にのみ存在するポリシー設定や基本設定項目は報告または編集できません。</span><span class="sxs-lookup"><span data-stu-id="b7094-213">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7094-214">AGPM 4.0 より前の AGPM のバージョン</span><span class="sxs-lookup"><span data-stu-id="b7094-214">Versions of AGPM that precede AGPM4.0</span></span>


<span data-ttu-id="b7094-215">表4は、AGPM 4.0 より前のバージョンの AGPM をインストールできるオペレーティングシステムを示しています。</span><span class="sxs-lookup"><span data-stu-id="b7094-215">Table 4 lists the operating systems on which you can install the versions of AGPM that precede AGPM4.0.</span></span> <span data-ttu-id="b7094-216">オペレーティングシステムが表示されない場合は、そのオペレーティングシステムに AGPM をインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b7094-216">If an operating system is not listed, you cannot install AGPM on that operating system.</span></span>

**<span data-ttu-id="b7094-217">表 5: AGPM 4.0 より前のバージョンの AGPM でサポートされているオペレーティングシステム</span><span class="sxs-lookup"><span data-stu-id="b7094-217">Table 5: Supported operating systems for versions of AGPM that precede AGPM4.0</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b7094-218">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="b7094-218">Operating system</span></span></th>
<th align="left"><span data-ttu-id="b7094-219">インストールできる AGPM のバージョン</span><span class="sxs-lookup"><span data-stu-id="b7094-219">Version of AGPM that can be installed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-220">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="b7094-220">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-221">3.0</span><span class="sxs-lookup"><span data-stu-id="b7094-221">3.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-222">Windows Vista SP1</span><span class="sxs-lookup"><span data-stu-id="b7094-222">Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-223">3.0</span><span class="sxs-lookup"><span data-stu-id="b7094-223">3.0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b7094-224">Windows Vista (サービスパックがインストールされていない場合) (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="b7094-224">WindowsVista with no service pack installed (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-225">2.5</span><span class="sxs-lookup"><span data-stu-id="b7094-225">2.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b7094-226">Windows Server2003 (32 ビット)</span><span class="sxs-lookup"><span data-stu-id="b7094-226">Windows Server2003 (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="b7094-227">2.5</span><span class="sxs-lookup"><span data-stu-id="b7094-227">2.5</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="b7094-228">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="b7094-228">How to Get MDOP Technologies</span></span>


<span data-ttu-id="b7094-229">AGPM 4.0 SP2 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="b7094-229">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="b7094-230">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="b7094-230">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="b7094-231">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="b7094-231">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="b7094-232">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b7094-232">Related topics</span></span>


[<span data-ttu-id="b7094-233">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="b7094-233">Advanced Group Policy Management</span></span>](index.md)

 

 





