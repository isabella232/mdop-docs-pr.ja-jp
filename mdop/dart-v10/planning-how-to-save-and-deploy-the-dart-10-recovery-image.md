---
title: DaRT 10 の回復イメージの保存および展開方法の計画
description: DaRT 10 の回復イメージの保存および展開方法の計画
author: dansimp
ms.assetid: 9a3e5413-2621-49ce-8bd2-992616691703
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bbaa8c4160970de90561f5ff8cedcefd08ca1dd7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822987"
---
# <span data-ttu-id="55043-103">DaRT 10 の回復イメージの保存および展開方法の計画</span><span class="sxs-lookup"><span data-stu-id="55043-103">Planning How to Save and Deploy the DaRT 10 Recovery Image</span></span>


<span data-ttu-id="55043-104">次の方法を使用して、Microsoft Diagnostics and Recovery ツールセット (DaRT) 10 の回復イメージを保存して展開することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-104">You can save and deploy the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image by using the following methods.</span></span> <span data-ttu-id="55043-105">使用する方法を決定する際には、それぞれの長所と短所を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="55043-105">When you are determining the method that you will use, consider the advantages and disadvantages of each.</span></span> <span data-ttu-id="55043-106">また、インフラストラクチャとサポートスタッフも検討してください。</span><span class="sxs-lookup"><span data-stu-id="55043-106">You should also consider your infrastructure and support staff.</span></span> <span data-ttu-id="55043-107">小規模なインフラストラクチャをお持ちの場合は、リムーバブルメディアを使用して DaRT 10 を展開することをお勧めします。復元イメージは、ローカルのハードドライブにインストールすると常に使用できるためです。</span><span class="sxs-lookup"><span data-stu-id="55043-107">If you have a small infrastructure, you might want to deploy DaRT 10 by using removable media, since the recovery image will always be available if you install it to the local hard drive.</span></span>

<span data-ttu-id="55043-108">組織で Active Directory ドメインサービス (AD DS) を使用している場合、Windows DS を使用して、回復イメージをネットワークサービスとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-108">If your organization uses Active Directory Domain Services (AD DS), you may want to deploy recovery images as a network service by using Windows DS.</span></span> <span data-ttu-id="55043-109">回復イメージは、接続されているすべてのコンピューターでいつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="55043-109">Recovery images are always available to any connected computer.</span></span> <span data-ttu-id="55043-110">Windows DS から複数の画像を展開して、すべてを1か所で管理することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-110">You can deploy multiple images from Windows DS and maintain them all in one place.</span></span>

<span data-ttu-id="55043-111">**注** 組織で複数の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-111">**Note** You may want to use more than one method in your organization.</span></span> <span data-ttu-id="55043-112">たとえば、ほとんどの状況についてはリモートのパーティションから DaRT を起動し、エンドユーザーのコンピューターがネットワークに接続できない場合は USB フラッシュドライブを使用できます。</span><span class="sxs-lookup"><span data-stu-id="55043-112">For example, you can boot into DaRT from a remote partition for most situations and have a USB flash drive available in case the end-user computer cannot connect to the network.</span></span>

 

<span data-ttu-id="55043-113">次の表では、組織で DaRT を使用する方法の利点と欠点をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="55043-113">The following table shows some advantages and disadvantages of each method of using DaRT in your organization.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55043-114">DaRT で起動する方法</span><span class="sxs-lookup"><span data-stu-id="55043-114">Method to Boot into DaRT</span></span></th>
<th align="left"><span data-ttu-id="55043-115">長所</span><span class="sxs-lookup"><span data-stu-id="55043-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="55043-116">短所</span><span class="sxs-lookup"><span data-stu-id="55043-116">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="55043-117">リムーバブルメディア</span><span class="sxs-lookup"><span data-stu-id="55043-117">Removable Media</span></span></strong></p>
<p><span data-ttu-id="55043-118">回復イメージは CD、DVD、または USB のドライブに書き込まれ、サポートスタッフは、それらの回復ツールを不安定なコンピューターに移動できるようになります。</span><span class="sxs-lookup"><span data-stu-id="55043-118">The recovery image is written to a CD, DVD, or USB drive to enable support staff to take the recovery tools with them to the unstable computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-119">マスターブートレコード (MBR) が破損していて、ハードディスクにアクセスできず、ネットワーク接続がない場合にサポートされているシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="55043-119">Supports scenarios in which the master boot record (MBR) is corrupted and you cannot access the hard disk and supports cases in which there is no network connection.</span></span></p>
<p><span data-ttu-id="55043-120">さまざまなレベルのサポートを提供するために、さまざまなツールを使用して複数の回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-120">Enables you to create multiple recovery images with different tools to provide different levels of support.</span></span></p>
<p><span data-ttu-id="55043-121">リムーバブルメディアへの回復イメージの書き込み用の組み込みツールを提供します。</span><span class="sxs-lookup"><span data-stu-id="55043-121">Provides a built-in tool for burning recovery images to removable media.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-122">DaRT を起動するには、エンドユーザのコンピュータのサポートスタッフが物理的に必要です。</span><span class="sxs-lookup"><span data-stu-id="55043-122">Requires that support staff are physically at the end-user computer to boot into DaRT.</span></span></p>
<p><span data-ttu-id="55043-123">32ビットと64ビットのコンピューターのさまざまな構成で複数のメディアを作成するには、時間とメンテナンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="55043-123">Requires time and maintenance to create multiple media with different configurations for 32-bit and 64-bit computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="55043-124">リモート (ネットワーク) パーティションから</span><span class="sxs-lookup"><span data-stu-id="55043-124">From a remote (network) partition</span></span></strong></p>
<p><span data-ttu-id="55043-125">回復イメージは、Windows 展開サービス (Windows DS) などのネットワークブートサーバーでホストされます。これにより、ユーザーまたはサポートスタッフはオンデマンドでコンピューターにそれをストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="55043-125">The recovery image is hosted on a network boot server like Windows Deployment Services (Windows DS), which allows users or support staff to stream it to computers on demand.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-126">ネットワークブートサーバーにアクセスできるすべてのコンピューターで利用できます。</span><span class="sxs-lookup"><span data-stu-id="55043-126">Available to all computers that have access to the network boot server.</span></span></p>
<p><span data-ttu-id="55043-127">回復イメージはセントラルサーバーでホストされるため、一元管理された更新が可能です。</span><span class="sxs-lookup"><span data-stu-id="55043-127">Recovery images are hosted on a central server, which enables centralized updates.</span></span></p>
<p><span data-ttu-id="55043-128">一元管理されたヘルプデスクスタッフは、リモート接続を使用して修復を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="55043-128">Centralized help desk staff can provide repairs by using remote connectivity.</span></span></p>
<p><span data-ttu-id="55043-129">クライアントにはローカル記憶域は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="55043-129">No local storage requirement on the clients.</span></span></p>
<p><span data-ttu-id="55043-130">特定のサポートレベルに応じて、さまざまなツールを使用して複数の回復イメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="55043-130">Ability to create multiple recovery images with different tools for specific support levels.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-131">通常のユーザーが DaRT 回復イメージのみを開始できるように、Windows DS インフラストラクチャをセキュリティで保護する必要がありますが、完全なオペレーティングシステムのイメージングプロセスではありません。</span><span class="sxs-lookup"><span data-stu-id="55043-131">The need to secure Windows DS infrastructure to ensure that regular users can start only the DaRT recovery image and not the full operating system imaging process.</span></span></p>
<p></p>
<p></p>
<p><span data-ttu-id="55043-132">エンドユーザーコンピューターが実行時にネットワークに接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55043-132">Requires that the end-user computer is connected to the network at runtime.</span></span></p>
<p><span data-ttu-id="55043-133">ネットワーク全体に回復イメージを提供する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55043-133">Requires that the recovery image is brought across the network.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="55043-134">ローカルハードドライブの回復パーティションから</span><span class="sxs-lookup"><span data-stu-id="55043-134">From a recovery partition on the local hard drive</span></span></strong></p>
<p><span data-ttu-id="55043-135">回復イメージは、手動で、または System Center Configuration Manager などの電子ソフトウェア配布システムを使用して、ローカルのハードドライブにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="55043-135">The recovery image is installed on a local hard drive either manually or by using electronic software distribution systems like System Center Configuration Manager.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-136">回復イメージは、コンピューター上で事前にステージングされているため、いつでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="55043-136">The recovery image is always available because it is pre-staged on the computer.</span></span></p>
<p><span data-ttu-id="55043-137">一元管理されたヘルプデスクスタッフは、リモート接続を使用してサポートを提供できます。</span><span class="sxs-lookup"><span data-stu-id="55043-137">Centralized help desk staff can provide support by using Remote Connection.</span></span></p>
<p><span data-ttu-id="55043-138">回復イメージは一元管理されて展開されます。</span><span class="sxs-lookup"><span data-stu-id="55043-138">The recovery image is centrally managed and deployed.</span></span></p>
<p><span data-ttu-id="55043-139">Windows BitLocker ドライブ暗号化によって保護されているコンピューターでの、追加の回復キー要求は削除されます。</span><span class="sxs-lookup"><span data-stu-id="55043-139">Additional recovery key requests on computers that are protected by Windows BitLocker drive encryption are eliminated.</span></span></p></td>
<td align="left"><p><span data-ttu-id="55043-140">ローカルストレージが必要です。</span><span class="sxs-lookup"><span data-stu-id="55043-140">Local storage is required.</span></span></p>
<p><span data-ttu-id="55043-141">障害が発生したブートパーティションのリスクを軽減するには、回復イメージの配置用の専用の暗号化されていないパーティションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="55043-141">A dedicated, unencrypted partition for recovery image placement is recommended to reduce the risk of a failed boot partition.</span></span></p>
<p><span data-ttu-id="55043-142">DaRT を更新する場合は、1つのパーティション (ネットワーク上) またはリムーバブルデバイスではなく、企業内のすべてのコンピューターを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55043-142">When updating DaRT, you must update all computers in your enterprise instead of just one partition (on the network) or removable device.</span></span></p>
<p><span data-ttu-id="55043-143">BitLocker を有効にした後で回復イメージを展開する場合は、追加の考慮事項が必要です。</span><span class="sxs-lookup"><span data-stu-id="55043-143">Additional consideration is required if you deploy the recovery image after BitLocker has been enabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="55043-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55043-144">Related topics</span></span>


[<span data-ttu-id="55043-145">DaRT 10 の展開計画</span><span class="sxs-lookup"><span data-stu-id="55043-145">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 





