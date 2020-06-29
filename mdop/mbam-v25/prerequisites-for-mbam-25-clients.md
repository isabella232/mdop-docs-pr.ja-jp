---
title: MBAM 2.5 クライアントの前提条件
description: MBAM 2.5 クライアントの前提条件
author: dansimp
ms.assetid: fc230679-9c84-4b99-a77c-bae7e7bf8145
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: ac5e211e5ea038f47db3d5e68155eb5af38aa231
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826967"
---
# <span data-ttu-id="e4ad1-103">MBAM 2.5 クライアントの前提条件</span><span class="sxs-lookup"><span data-stu-id="e4ad1-103">Prerequisites for MBAM 2.5 Clients</span></span>


<span data-ttu-id="e4ad1-104">MBAM クライアントソフトウェアをエンドユーザーのコンピューターにインストールする前に、環境とクライアントコンピューターが次の前提条件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-104">Before you install the MBAM Client software on end users' computers, ensure that your environment and the client computers meet the following prerequisites.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e4ad1-105">受講</span><span class="sxs-lookup"><span data-stu-id="e4ad1-105">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="e4ad1-106">詳細</span><span class="sxs-lookup"><span data-stu-id="e4ad1-106">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e4ad1-107">エンタープライズドメインには、少なくとも1つの Windows Server 2008 (またはそれ以降) のドメインコントローラーが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-107">The enterprise domain must contain at least one Windows Server 2008 (or later) domain controller.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e4ad1-108">クライアントコンピューターは、エンタープライズイントラネットにログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-108">The client computer must be logged on to the enterprise intranet.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e4ad1-109">Windows 7 クライアントコンピューターのみ: 各クライアントには、トラステッドプラットフォームモジュール (TPM) 機能 (TPM 1.2 以降) が必要です。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-109">For Windows 7 client computers only: Each client must have Trusted Platform Module (TPM) capability (TPM 1.2 or later).</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e4ad1-110">Windows 8.1、Windows 10 RTM、または Windows 10 バージョン1511クライアントコンピューターのみ: MBAM で TPM 回復キーを保存および管理できるようにする場合は、TPM 自動プロビジョニング機能を無効にして、mbam を TPM の所有者として設定してから、MBAM を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-110">For Windows 8.1, Windows 10 RTM or Windows 10 version 1511 client computers only: If you want MBAM to be able to store and manage the TPM recovery keys, TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p>
<p><span data-ttu-id="e4ad1-111">MBAM 2.5 SP1 でのみ、TPM 自動プロビジョニングをオフにする必要はありませんが、tpm グループポリシーオブジェクトが Active Directory へのエスクロー TPM OwnerAuth に設定されていないことを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-111">In MBAM 2.5 SP1 only, you no longer need to turn off TPM auto-provisioning, but you must make sure that the TPM Group Policy Objects are set to not escrow TPM OwnerAuth to Active Directory.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md#bkmk-tpm" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm)"><span data-ttu-id="e4ad1-112">MBAM 2.5 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="e4ad1-112">MBAM 2.5 Security Considerations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e4ad1-113">Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-113">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="e4ad1-114">Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-114">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span></p>
<p><span data-ttu-id="e4ad1-115">MBAM 2.5 SP1 では、自動プロビジョニングを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-115">In MBAM 2.5 SP1, you must turn on auto-provisioning.</span></span></p>
</p></td>
<td align="left"><p><span data-ttu-id="e4ad1-116"><a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)"> </a> 詳細については、TPM 所有者パスワードを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-116">See <a href="https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password" data-raw-source="[TPM owner password](https://technet.microsoft.com/itpro/windows/keep-secure/change-the-tpm-owner-password)">TPM owner password</a> for further details.</span></span>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e4ad1-117">TPM チップは BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-117">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="e4ad1-118">詳細については、BIOS のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-118">See the BIOS documentation for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e4ad1-119">コンピューターのハードディスクには、少なくとも2つのパーティションが必要であり、NTFS ファイルシステムでフォーマットされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-119">The computer’s hard disk must have at least two partitions and must be formatted with the NTFS file system.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e4ad1-120">コンピューターのハードディスクには、TPM と互換性のある BIOS と、コンピューターの起動時に USB デバイスをサポートしている BIOS が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-120">The computer’s hard disk must have a BIOS that is compatible with TPM and that supports USB devices during computer startup.</span></span></p></td>
<td align="left"><div class="alert">
<strong><span data-ttu-id="e4ad1-121">注</span><span class="sxs-lookup"><span data-stu-id="e4ad1-121">Note</span></span></strong><br/><p><span data-ttu-id="e4ad1-122">キーボード、ビデオ、マウスが直接接続されていて、キーボード、ビデオ、マウス (KVM) スイッチで管理されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-122">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="e4ad1-123">KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-123">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e4ad1-124">プロキシを使っている場合は、システムコンテキストでそのプロキシが表示されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-124">If you use a proxy, it must be visible in the system context.</span></span> <span data-ttu-id="e4ad1-125">MBAM は、ユーザーコンテキストではなく、システムコンテキストで実行されます。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-125">MBAM runs under the system context, not the user context.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e4ad1-126">重要</span><span class="sxs-lookup"><span data-stu-id="e4ad1-126">Important</span></span>**  
<span data-ttu-id="e4ad1-127">MBAM で BitLocker を使用していた場合は、MBAM をインストールして、既存の TPM 情報を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-127">If BitLocker was used without MBAM, MBAM can be installed and utilize the existing TPM information.</span></span>




## <span data-ttu-id="e4ad1-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e4ad1-128">Related topics</span></span>


[<span data-ttu-id="e4ad1-129">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e4ad1-129">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

[<span data-ttu-id="e4ad1-130">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="e4ad1-130">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)


## <span data-ttu-id="e4ad1-131">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e4ad1-132">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="e4ad1-133">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="e4ad1-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






