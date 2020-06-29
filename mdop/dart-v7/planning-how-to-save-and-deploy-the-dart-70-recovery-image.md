---
title: DaRT 7.0 の回復イメージの保存および展開方法の計画
description: DaRT 7.0 の回復イメージの保存および展開方法の計画
author: dansimp
ms.assetid: d96e9363-6186-4fc3-9b83-ba15ed9694a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c292633949865d4b3f5053700f4219db3f1cf465
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822797"
---
# <span data-ttu-id="8622b-103">DaRT 7.0 の回復イメージの保存および展開方法の計画</span><span class="sxs-lookup"><span data-stu-id="8622b-103">Planning How to Save and Deploy the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="8622b-104">Microsoft 診断/回復ツールセット (DaRT) 7 の回復イメージの保存と展開を計画している場合は、このセクションの情報を使用してください。</span><span class="sxs-lookup"><span data-stu-id="8622b-104">Use the information in this section when you plan for saving and deploying the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="8622b-105">DaRT リカバリイメージの保存と展開の計画</span><span class="sxs-lookup"><span data-stu-id="8622b-105">Planning How to Save and Deploy the DaRT Recovery Image</span></span>


<span data-ttu-id="8622b-106">DaRT リカバリ画像を保存して展開するには、次の方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="8622b-106">You can save and deploy the DaRT recovery image by using the following methods.</span></span> <span data-ttu-id="8622b-107">使用する方法を決定する際には、それぞれの長所と短所を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="8622b-107">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="8622b-108">また、企業での DaRT の使用方法についても検討してください。</span><span class="sxs-lookup"><span data-stu-id="8622b-108">Also, consider how you want to use DaRT in your enterprise.</span></span>

<span data-ttu-id="8622b-109">**注** 組織では、複数の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="8622b-109">**Note** You might want to use more than one method in your organization.</span></span> <span data-ttu-id="8622b-110">たとえば、ほとんどの状況についてはリモートのパーティションから DaRT を起動し、エンドユーザーのコンピューターがネットワークに接続できない場合は USB フラッシュドライブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="8622b-110">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="8622b-111">次の表では、組織で DaRT を使用する方法の利点と欠点をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="8622b-111">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8622b-112">DaRT で起動する方法</span><span class="sxs-lookup"><span data-stu-id="8622b-112">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="8622b-113">長所</span><span class="sxs-lookup"><span data-stu-id="8622b-113">Advantages</span></span></th>
<th align="left"><span data-ttu-id="8622b-114">短所</span><span class="sxs-lookup"><span data-stu-id="8622b-114">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8622b-115">CD または DVD から</span><span class="sxs-lookup"><span data-stu-id="8622b-115">From a CD or DVD</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-116">マスターブートレコード (MBR) が破損していて、ハードディスクにアクセスできないシナリオがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="8622b-116">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk.</span></span> <span data-ttu-id="8622b-117">また、ネットワーク接続がない場合もサポートします。</span><span class="sxs-lookup"><span data-stu-id="8622b-117">Also supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="8622b-118">これは、以前のバージョンの DaRT を使用するユーザーにとって最も使い慣れた機能であり、CD-R または DVD は dart の回復イメージウィザードから直接書き込むことができ <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="8622b-118">This is most familiar to users of earlier versions of DaRT, and a CD or DVD can be burned directly from the <strong>DaRT Recovery Image Wizard</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-119">この CD または DVD へのアクセス権を持つユーザーが、DaRT で起動するために、エンドユーザーのコンピューターに物理的にアクセスしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8622b-119">Requires that someone with access to the CD or DVD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8622b-120">USB フラッシュドライブ (UFD) から</span><span class="sxs-lookup"><span data-stu-id="8622b-120">From a USB flash drive (UFD)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-121">CD または DVD からの起動と同じように、CD または DVD ドライブを備えていないコンピューターのサポートも提供します。</span><span class="sxs-lookup"><span data-stu-id="8622b-121">Provides same advantages as booting from a CD or DVD and also provides support to computers that have no CD or DVD drive.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-122">DaRT でブートするために使用する前に、UFD の書式を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8622b-122">Requires you to format the UFD before you can use it to boot into DaRT.</span></span> <span data-ttu-id="8622b-123">また、UFD へのアクセス権を持つユーザーは、DaRT で起動するために、エンドユーザーのコンピューターに物理的にアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8622b-123">Also requires that someone with access to the UFD is physically at the end-user computer to boot into DaRT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8622b-124">リモート (ネットワーク) パーティションから</span><span class="sxs-lookup"><span data-stu-id="8622b-124">From a remote (network) partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-125">CD、DVD、または UFD がなくても DaRT を起動できます。</span><span class="sxs-lookup"><span data-stu-id="8622b-125">Lets you boot into DaRT without needing a CD, DVD, or UFD.</span></span> <span data-ttu-id="8622b-126">また、更新するファイルの場所が1つしかないため、DaRT を簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="8622b-126">Also allows for easy upgrades of DaRT because there is only one file location to update.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-127">エンドユーザーのコンピューターがネットワークに接続されていない場合は、機能しません。</span><span class="sxs-lookup"><span data-stu-id="8622b-127">Does not work if the end-user computer is not connected to the network.</span></span></p>
<p><span data-ttu-id="8622b-128">エンドユーザーが広く利用できるようになり、回復イメージを作成するときに、追加のセキュリティの考慮事項が必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="8622b-128">Widely available to end users and might require additional security considerations when you are creating the recovery image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8622b-129">回復パーティションから</span><span class="sxs-lookup"><span data-stu-id="8622b-129">From a recovery partition</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-130">ネットワーク接続がない場合でも、CD、DVD、または UFD がなくても DaRT を起動できます。</span><span class="sxs-lookup"><span data-stu-id="8622b-130">Lets you boot into DaRT without needing a CD, DVD, or UFD that includes instances in which there is no network connectivity.</span></span></p>
<p><span data-ttu-id="8622b-131">また、Microsoft Endpoint Configuration Manager などの自動化された配布ツールを使用して、標準の Windows イメージプロセスの一部として実装し、管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="8622b-131">Also, can be implemented and managed as part of your standard Windows image process by using automated distribution tools, such as Microsoft Endpoint Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8622b-132">DaRT を更新する場合は、1つのパーティション (ネットワーク上) またはデバイス (CD、DVD、または UFD) だけでなく、企業内のすべてのコンピューターを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8622b-132">When updating DaRT, requires you to update all computers in your enterprise instead of just one partition (on the network) or device (CD, DVD, or UFD).</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8622b-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8622b-133">Related topics</span></span>


[<span data-ttu-id="8622b-134">DaRT 7.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="8622b-134">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





