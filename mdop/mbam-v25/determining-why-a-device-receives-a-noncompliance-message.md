---
title: デバイスがコンプライアンス非対応メッセージを受信する理由の特定
description: デバイスがコンプライアンス非対応メッセージを受信する理由の特定
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824574"
---
# <span data-ttu-id="4c583-103">デバイスがコンプライアンス非対応メッセージを受信する理由の特定</span><span class="sxs-lookup"><span data-stu-id="4c583-103">Determining why a Device Receives a Noncompliance Message</span></span>


<span data-ttu-id="4c583-104">以下の違反コードは、WMI によって提供され、特定のデバイスが非準拠として MBAM によって報告される理由について説明します。</span><span class="sxs-lookup"><span data-stu-id="4c583-104">The following noncompliance codes are provided by WMI and describe the reasons why a particular device is reported by MBAM as noncompliant.</span></span>

<span data-ttu-id="4c583-105">WMI の表示には、推奨される方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="4c583-105">You can use your preferred method to view WMI.</span></span> <span data-ttu-id="4c583-106">PowerShell を使用している場合は、 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` powershell プロンプトから実行し、理由違反を検索します。</span><span class="sxs-lookup"><span data-stu-id="4c583-106">If you use PowerShell, run `gwmi -class mbam_volume -Namespace root\microsoft\mbam` from a PowerShell prompt and search for ReasonsForNoncompliance.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4c583-107">コンプライアンス以外のコード</span><span class="sxs-lookup"><span data-stu-id="4c583-107">Non-Compliance Code</span></span></th>
<th align="left"><span data-ttu-id="4c583-108">準拠していない理由</span><span class="sxs-lookup"><span data-stu-id="4c583-108">Reason for Non-Compliance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-109">0</span><span class="sxs-lookup"><span data-stu-id="4c583-109">0</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-110">AES 256 ではない暗号強度。</span><span class="sxs-lookup"><span data-stu-id="4c583-110">Cipher strength not AES 256.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-111">件</span><span class="sxs-lookup"><span data-stu-id="4c583-111">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-112">MBAM ポリシーでは、このボリュームは暗号化する必要がありますが、暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="4c583-112">MBAM Policy requires this volume to be encrypted but it is not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-113">両面</span><span class="sxs-lookup"><span data-stu-id="4c583-113">2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-114">MBAM ポリシーの場合、このボリュームは暗号化されないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c583-114">MBAM Policy requires this volume to NOT be encrypted, but it is.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-115">-</span><span class="sxs-lookup"><span data-stu-id="4c583-115">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-116">MBAM ポリシーでは、このボリュームは TPM プロテクターを使用する必要がありますが、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="4c583-116">MBAM Policy requires this volume use a TPM protector, but it does not.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-117">4d</span><span class="sxs-lookup"><span data-stu-id="4c583-117">4</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-118">MBAM ポリシーには、このボリュームで TPM + PIN プロテクターを使用する必要がありますが、そうではありません。</span><span class="sxs-lookup"><span data-stu-id="4c583-118">MBAM Policy requires this volume use a TPM+PIN protector, but it does not.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-119">個</span><span class="sxs-lookup"><span data-stu-id="4c583-119">5</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-120">MBAM ポリシーでは、TPM コンピューター以外では準拠して報告できません。</span><span class="sxs-lookup"><span data-stu-id="4c583-120">MBAM Policy does not allow non TPM machines to report as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-121">=</span><span class="sxs-lookup"><span data-stu-id="4c583-121">6</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-122">ボリュームには TPM プロテクターがありますが、TPM は表示されません (BIOS で TPM を無効にした後に、回復キーを使用してブートしますか?)。</span><span class="sxs-lookup"><span data-stu-id="4c583-122">Volume has a TPM protector but the TPM is not visible (booted with recover key after disabling TPM in BIOS?).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-123">日</span><span class="sxs-lookup"><span data-stu-id="4c583-123">7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-124">MBAM ポリシーにはパスワードプロテクターを使用する必要がありますが、このボリュームにはありません。</span><span class="sxs-lookup"><span data-stu-id="4c583-124">MBAM Policy requires this volume use a password protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-125">個</span><span class="sxs-lookup"><span data-stu-id="4c583-125">8</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-126">MBAM ポリシーには、パスワード保護機能を使用せず、パスワード保護機能が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c583-126">MBAM Policy requires this volume NOT use a password protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-127">ファイブ</span><span class="sxs-lookup"><span data-stu-id="4c583-127">9</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-128">MBAM ポリシーには、このボリュームで自動ロック解除プロテクターを使用する必要がありますが、どちらも指定されていません。</span><span class="sxs-lookup"><span data-stu-id="4c583-128">MBAM Policy requires this volume use an auto-unlock protector, but it does not have one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-129">常用</span><span class="sxs-lookup"><span data-stu-id="4c583-129">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-130">MBAM ポリシーでは、このボリュームは自動ロック解除機能を使用しないが、1つだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="4c583-130">MBAM Policy requires this volume NOT use an auto-unlock protector, but it has one.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-131">折り</span><span class="sxs-lookup"><span data-stu-id="4c583-131">11</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-132">ポリシーの競合が検出されたため、MBAM がこのボリュームを準拠として報告できません。</span><span class="sxs-lookup"><span data-stu-id="4c583-132">Policy conflict detected preventing MBAM from reporting this volume as compliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-133">以内</span><span class="sxs-lookup"><span data-stu-id="4c583-133">12</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-134">システムボリュームは、OS のボリュームを暗号化するために必要ですが、表示されません。</span><span class="sxs-lookup"><span data-stu-id="4c583-134">A system volume is needed to encrypt the OS volume but it is not present.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-135">14</span><span class="sxs-lookup"><span data-stu-id="4c583-135">13</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-136">ボリュームの保護は一時停止されます。</span><span class="sxs-lookup"><span data-stu-id="4c583-136">Protection is suspended for the volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-137">14</span><span class="sxs-lookup"><span data-stu-id="4c583-137">14</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-138">AutoUnlock unsafe (OS のボリュームが暗号化されている場合を除く)。</span><span class="sxs-lookup"><span data-stu-id="4c583-138">AutoUnlock unsafe unless the OS volume is encrypted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4c583-139">マート</span><span class="sxs-lookup"><span data-stu-id="4c583-139">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-140">ポリシーには最低 cypher 強度が必要です。 XTS は AES-128 ビット、実際の cypher 強度はこれより弱くなります。</span><span class="sxs-lookup"><span data-stu-id="4c583-140">Policy requires minimum cypher strength is XTS-AES-128 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4c583-141">16</span><span class="sxs-lookup"><span data-stu-id="4c583-141">16</span></span></p></td>
<td align="left"><p><span data-ttu-id="4c583-142">ポリシーには最低 cypher 強度が必要です。 XTS は AES-256 ビット、実際の cypher 強度はこれより弱くなります。</span><span class="sxs-lookup"><span data-stu-id="4c583-142">Policy requires minimum cypher strength is XTS-AES-256 bit, actual cypher strength is weaker than that.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4c583-143">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4c583-143">Related topics</span></span>


[<span data-ttu-id="4c583-144">MBAM 2.5 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="4c583-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="4c583-145">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="4c583-145">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span>](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## <span data-ttu-id="4c583-146">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="4c583-146">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4c583-147">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="4c583-147">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4c583-148">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="4c583-148">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





