---
title: クライアントのイベント ログ
description: クライアントのイベント ログ
author: dansimp
ms.assetid: d5c2f270-db6a-45f1-8557-8c6fb28fd568
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7324d07bf018944fcbe24168bba2e9abea9cea41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824194"
---
# <span data-ttu-id="6c58c-103">クライアントのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="6c58c-103">Client Event Logs</span></span>

<span data-ttu-id="6c58c-104">MBAM クライアントイベントログは、イベントビューアー (アプリケーションとサービスログ) にあります。 Microsoft – Windows – MBAM 操作のパス。</span><span class="sxs-lookup"><span data-stu-id="6c58c-104">MBAM Client event logs are located in Event Viewer – Applications and Services Logs – Microsoft – Windows – MBAM - Operational path.</span></span>
<span data-ttu-id="6c58c-105">次の表は、MBAM クライアントで発生する可能性のあるイベント Id を示しています。</span><span class="sxs-lookup"><span data-stu-id="6c58c-105">The following table contains event IDs that can occur on the MBAM Client.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6c58c-106">イベント ID</span><span class="sxs-lookup"><span data-stu-id="6c58c-106">Event ID</span></span></th>
<th align="left"><span data-ttu-id="6c58c-107">チャネル</span><span class="sxs-lookup"><span data-stu-id="6c58c-107">Channel</span></span></th>
<th align="left"><span data-ttu-id="6c58c-108">イベントの記号</span><span class="sxs-lookup"><span data-stu-id="6c58c-108">Event symbol</span></span></th>
<th align="left"><span data-ttu-id="6c58c-109">メッセージ</span><span class="sxs-lookup"><span data-stu-id="6c58c-109">Message</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-110">件</span><span class="sxs-lookup"><span data-stu-id="6c58c-110">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-111">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-111">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-112">Volumeenactの成功</span><span class="sxs-lookup"><span data-stu-id="6c58c-112">VolumeEnactmentSuccessful</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-113">MBAM ポリシーが正常に適用されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-113">The MBAM policies were applied successfully.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-114">両面</span><span class="sxs-lookup"><span data-stu-id="6c58c-114">2</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-115">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-115">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-116">Volumeenactのエラー</span><span class="sxs-lookup"><span data-stu-id="6c58c-116">VolumeEnactmentFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-117">MBAM ポリシーの適用中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-117">An error occurred while applying MBAM policies.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-118">-</span><span class="sxs-lookup"><span data-stu-id="6c58c-118">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-119">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-119">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-120">Transferstatusdatasucの場合</span><span class="sxs-lookup"><span data-stu-id="6c58c-120">TransferStatusDataSuccessful</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-121">暗号化の状態データが正常に送信されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-121">The encryption status data was sent successfully.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-122">4d</span><span class="sxs-lookup"><span data-stu-id="6c58c-122">4</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-123">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-123">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-124">TransferStatusDataFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-124">TransferStatusDataFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-125">暗号化状態データの送信中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-125">An error occurred while sending encryption status data.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-126">個</span><span class="sxs-lookup"><span data-stu-id="6c58c-126">8</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-127">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-127">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-128">SystemVolumeNotFound</span><span class="sxs-lookup"><span data-stu-id="6c58c-128">SystemVolumeNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-129">システムボリュームがありません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-129">The system volume is missing.</span></span> <span data-ttu-id="6c58c-130">オペレーティングシステムドライブを暗号化するには、SystemVolume が必要です。</span><span class="sxs-lookup"><span data-stu-id="6c58c-130">SystemVolume is needed to encrypt the operating system drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-131">ファイブ</span><span class="sxs-lookup"><span data-stu-id="6c58c-131">9</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-132">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-132">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-133">TPMNotFound</span><span class="sxs-lookup"><span data-stu-id="6c58c-133">TPMNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-134">TPM ハードウェアがありません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-134">The TPM hardware is missing.</span></span> <span data-ttu-id="6c58c-135">Tpm は、任意の TPM プロテクターでオペレーティングシステムドライブを暗号化するために必要です。</span><span class="sxs-lookup"><span data-stu-id="6c58c-135">TPM is needed to encrypt the operating system drive with any TPM protector.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-136">常用</span><span class="sxs-lookup"><span data-stu-id="6c58c-136">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-137">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-137">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-138">MachineHWExempted</span><span class="sxs-lookup"><span data-stu-id="6c58c-138">MachineHWExempted</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-139">コンピューターは暗号化から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6c58c-139">The computer is exempted from Encryption.</span></span> <span data-ttu-id="6c58c-140">マシンのハードウェア状態: 除外</span><span class="sxs-lookup"><span data-stu-id="6c58c-140">Machine’s hardware status: Exempted</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-141">折り</span><span class="sxs-lookup"><span data-stu-id="6c58c-141">11</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-142">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-142">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-143">MachineHWUnknown</span><span class="sxs-lookup"><span data-stu-id="6c58c-143">MachineHWUnknown</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-144">コンピューターは暗号化から除外されます。</span><span class="sxs-lookup"><span data-stu-id="6c58c-144">The computer is exempted from encryption.</span></span> <span data-ttu-id="6c58c-145">マシンのハードウェア状態: 不明</span><span class="sxs-lookup"><span data-stu-id="6c58c-145">Machine’s hardware status: Unknown</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-146">以内</span><span class="sxs-lookup"><span data-stu-id="6c58c-146">12</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-147">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-147">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-148">HWCheckFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-148">HWCheckFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-149">ハードウェアの除外チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-149">Hardware exemption check failed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-150">14</span><span class="sxs-lookup"><span data-stu-id="6c58c-150">13</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-151">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-151">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-152">Userisex</span><span class="sxs-lookup"><span data-stu-id="6c58c-152">UserIsExempted</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-153">ユーザーは暗号化されません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-153">The user is exempt from encryption.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-154">14</span><span class="sxs-lookup"><span data-stu-id="6c58c-154">14</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-155">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-155">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-156">UserIsWaiting</span><span class="sxs-lookup"><span data-stu-id="6c58c-156">UserIsWaiting</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-157">ユーザーが除外を要求しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-157">The user requested an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-158">マート</span><span class="sxs-lookup"><span data-stu-id="6c58c-158">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-159">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-159">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-160">UserExemptionCheckFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-160">UserExemptionCheckFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-161">ユーザーの除外チェックに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-161">User exemption check failed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-162">16</span><span class="sxs-lookup"><span data-stu-id="6c58c-162">16</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-163">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-163">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-164">UserPostponed</span><span class="sxs-lookup"><span data-stu-id="6c58c-164">UserPostponed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-165">ユーザーが暗号化処理を延期した。</span><span class="sxs-lookup"><span data-stu-id="6c58c-165">The user postponed the encryption process.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-166">17</span><span class="sxs-lookup"><span data-stu-id="6c58c-166">17</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-167">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-167">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-168">TPMInitializationFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-168">TPMInitializationFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-169">TPM の初期化に失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-169">TPM initialization failed.</span></span> <span data-ttu-id="6c58c-170">ユーザーが BIOS の変更を拒否しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-170">The user rejected the BIOS changes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-171">才</span><span class="sxs-lookup"><span data-stu-id="6c58c-171">18</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-172">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-172">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-173">CoreServiceDown</span><span class="sxs-lookup"><span data-stu-id="6c58c-173">CoreServiceDown</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-174">MBAM Recovery およびハードウェアサービスに接続できません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-174">Unable to connect to the MBAM Recovery and Hardware service.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-175">#</span><span class="sxs-lookup"><span data-stu-id="6c58c-175">19</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-176">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-176">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-177">CoreServiceUp</span><span class="sxs-lookup"><span data-stu-id="6c58c-177">CoreServiceUp</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-178">MBAM Recovery とハードウェアサービスに正常に接続されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-178">Successfully connected to the MBAM Recovery and Hardware service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-179">超える</span><span class="sxs-lookup"><span data-stu-id="6c58c-179">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-180">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-180">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-181">ポリシーの不一致</span><span class="sxs-lookup"><span data-stu-id="6c58c-181">PolicyMismatch</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-182">MBAM ポリシーが競合しているか、破損しています。</span><span class="sxs-lookup"><span data-stu-id="6c58c-182">The MBAM policy is in conflict or corrupt.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-183">2004</span><span class="sxs-lookup"><span data-stu-id="6c58c-183">21</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-184">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-184">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-185">競合している Osvolumepolicies</span><span class="sxs-lookup"><span data-stu-id="6c58c-185">ConflictingOSVolumePolicies</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-186">OS のボリューム暗号化ポリシーが競合していることを検出しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-186">Detected OS volume encryption policies conflict.</span></span> <span data-ttu-id="6c58c-187">OS ドライブプロテクターに関連する BitLocker および MBAM ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c58c-187">Check BitLocker and MBAM policies related to OS drive protectors.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-188">22</span><span class="sxs-lookup"><span data-stu-id="6c58c-188">22</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-189">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-189">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-190">すべての Fddvolumeポリシーの競合</span><span class="sxs-lookup"><span data-stu-id="6c58c-190">ConflictingFDDVolumePolicies</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-191">データドライブのボリューム暗号化ポリシーが競合していることを検出しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-191">Detected Fixed Data Drive volume encryption policies conflict.</span></span> <span data-ttu-id="6c58c-192">FDD drive プロテクターに関連する BitLocker および MBAM ポリシーを確認します。</span><span class="sxs-lookup"><span data-stu-id="6c58c-192">Check BitLocker and MBAM policies related to FDD drive protectors.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-193">日</span><span class="sxs-lookup"><span data-stu-id="6c58c-193">27</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-194">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-194">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-195">暗号化 Dra</span><span class="sxs-lookup"><span data-stu-id="6c58c-195">EncryptionFailedNoDra</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-196">暗号化中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-196">An error occurred while encrypting.</span></span> <span data-ttu-id="6c58c-197">Windows 8.1 以前のコンピューターでは、FIPS モードでデータ回復エージェント (DRA) プロテクターが必要です。</span><span class="sxs-lookup"><span data-stu-id="6c58c-197">A Data Recovery Agent (DRA) protector is required in FIPS mode for pre-Windows 8.1 machines.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-198">日</span><span class="sxs-lookup"><span data-stu-id="6c58c-198">28</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-199">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-199">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-200">TpmOwnerAuthEscrowed</span><span class="sxs-lookup"><span data-stu-id="6c58c-200">TpmOwnerAuthEscrowed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-201">TPM OwnerAuth が預託たりされました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-201">The TPM OwnerAuth has been escrowed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-202">29</span><span class="sxs-lookup"><span data-stu-id="6c58c-202">29</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-203">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-203">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-204">RecoveryKeyEscrowed</span><span class="sxs-lookup"><span data-stu-id="6c58c-204">RecoveryKeyEscrowed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-205">ボリュームの BitLocker 回復キーが預託たりされました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-205">The BitLocker recovery key for the volume has been escrowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-206">求める</span><span class="sxs-lookup"><span data-stu-id="6c58c-206">30</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-207">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-207">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-208">RecoveryKeyReset</span><span class="sxs-lookup"><span data-stu-id="6c58c-208">RecoveryKeyReset</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-209">ボリュームの BitLocker 回復キーが更新されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-209">The BitLocker recovery key for the volume has been updated.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-210">31</span><span class="sxs-lookup"><span data-stu-id="6c58c-210">31</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-211">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-211">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-212">EnforcePolicyDateSet</span><span class="sxs-lookup"><span data-stu-id="6c58c-212">EnforcePolicyDateSet</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-213">ボリュームの [ポリシーの日付を適用] の <em> &lt; 日付 &gt; </em> が設定されている</span><span class="sxs-lookup"><span data-stu-id="6c58c-213">The enforce policy date, <em>&lt;date&gt;</em>, has been set for the volume</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-214">32</span><span class="sxs-lookup"><span data-stu-id="6c58c-214">32</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-215">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-215">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-216">EnforcePolicyDateCleared</span><span class="sxs-lookup"><span data-stu-id="6c58c-216">EnforcePolicyDateCleared</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-217">ボリュームの [ポリシーの日付を適用] の日付 <em> &lt; &gt; </em> が消去されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-217">The enforce policy date, <em>&lt;date&gt;</em>, has been cleared for the volume.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-218">33</span><span class="sxs-lookup"><span data-stu-id="6c58c-218">33</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-219">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-219">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-220">TpmLockOutResetSucceeded</span><span class="sxs-lookup"><span data-stu-id="6c58c-220">TpmLockOutResetSucceeded</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-221">TPM ロックアウトが正常にリセットされました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-221">Successfully reset TPM lockout.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-222">34</span><span class="sxs-lookup"><span data-stu-id="6c58c-222">34</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-223">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-223">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-224">TpmLockOutResetFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-224">TpmLockOutResetFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-225">TPM ロックアウトのリセットに失敗しました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-225">Failed to reset TPM lockout.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-226">35</span><span class="sxs-lookup"><span data-stu-id="6c58c-226">35</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-227">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-227">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-228">TpmOwnerAuthRetrievalSucceeded</span><span class="sxs-lookup"><span data-stu-id="6c58c-228">TpmOwnerAuthRetrievalSucceeded</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-229">MBAM サービスから TPM OwnerAuth が正常に取得されました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-229">Successfully retrieved TPM OwnerAuth from MBAM services.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-230">36</span><span class="sxs-lookup"><span data-stu-id="6c58c-230">36</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-231">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-231">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-232">TpmOwnerAuthRetrievalFailed</span><span class="sxs-lookup"><span data-stu-id="6c58c-232">TpmOwnerAuthRetrievalFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-233">MBAM サービスから TPM OwnerAuth を取得できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6c58c-233">Failed to retrieve TPM OwnerAuth from MBAM services.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-234">37</span><span class="sxs-lookup"><span data-stu-id="6c58c-234">37</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-235">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-235">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-236">の使い方に失敗しました</span><span class="sxs-lookup"><span data-stu-id="6c58c-236">WmiProviderDllSearchPathUpdateFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-237">WMI プロバイダーの DLL 検索パスを更新できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6c58c-237">Failed to update the DLL search path for WMI provider.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-238">38</span><span class="sxs-lookup"><span data-stu-id="6c58c-238">38</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-239">管理者</span><span class="sxs-lookup"><span data-stu-id="6c58c-239">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-240">TimedOutWaitingForWmiProvider</span><span class="sxs-lookup"><span data-stu-id="6c58c-240">TimedOutWaitingForWmiProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-241">エージェントの停止-MBAM WMI プロバイダーインスタンスを待機しています。</span><span class="sxs-lookup"><span data-stu-id="6c58c-241">Agent Stopping - Timed-out waiting for MBAM WMI Provider Instance.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-242">39</span><span class="sxs-lookup"><span data-stu-id="6c58c-242">39</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-243">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-243">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-244">RemovableDriveMounted</span><span class="sxs-lookup"><span data-stu-id="6c58c-244">RemovableDriveMounted</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-245">リムーバブルドライブがマウントされました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-245">Removable drive was mounted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-246">40</span><span class="sxs-lookup"><span data-stu-id="6c58c-246">40</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-247">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-247">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-248">Removableドライブのマウント解除</span><span class="sxs-lookup"><span data-stu-id="6c58c-248">RemovableDriveDismounted</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-249">リムーバブルドライブがアンマウントされました。</span><span class="sxs-lookup"><span data-stu-id="6c58c-249">Removable drive was unmounted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-250">41</span><span class="sxs-lookup"><span data-stu-id="6c58c-250">41</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-251">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-251">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-252">失敗した通信に到達可能</span><span class="sxs-lookup"><span data-stu-id="6c58c-252">FailedToEnactEndpointUnreachable</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-253">MBAM 回復およびハードウェアサービスのブロックに接続できない場合、MBAM ポリシーはボリュームに正常に適用されません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-253">Failure to connect to the MBAM Recovery and Hardware service prevented MBAM policies from being applied successfully to the volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6c58c-254">42</span><span class="sxs-lookup"><span data-stu-id="6c58c-254">42</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-255">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-255">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-256">FailedToEnactLockedVolume</span><span class="sxs-lookup"><span data-stu-id="6c58c-256">FailedToEnactLockedVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-257">ロックされているボリューム状態では、MBAM ポリシーがボリュームに正常に適用されません。</span><span class="sxs-lookup"><span data-stu-id="6c58c-257">Locked volume state prevented MBAM policies from being applied successfully to the volume.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6c58c-258">43</span><span class="sxs-lookup"><span data-stu-id="6c58c-258">43</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-259">実施</span><span class="sxs-lookup"><span data-stu-id="6c58c-259">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-260">Transferstatusdatafのアクセス到達可能</span><span class="sxs-lookup"><span data-stu-id="6c58c-260">TransferStatusDataFailedEndpointUnreachable</span></span></p></td>
<td align="left"><p><span data-ttu-id="6c58c-261">MBAM コンプライアンスとステータスサービスへの接続に失敗したため、暗号化状態データの転送ができませんでした。</span><span class="sxs-lookup"><span data-stu-id="6c58c-261">Failure to connect to the MBAM Compliance and Status service prevented the transfer of encryption status data.</span></span></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="6c58c-262">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6c58c-262">Related topics</span></span>
[<span data-ttu-id="6c58c-263">MBAM 2.5 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="6c58c-263">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="6c58c-264">サーバーのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="6c58c-264">Server Event Logs</span></span>](server-event-logs.md)

 


## <span data-ttu-id="6c58c-265">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6c58c-265">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6c58c-266">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6c58c-266">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6c58c-267">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6c58c-267">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





