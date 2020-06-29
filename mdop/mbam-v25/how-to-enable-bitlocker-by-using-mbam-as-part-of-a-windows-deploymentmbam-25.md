---
title: Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法
description: Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826227"
---
# <span data-ttu-id="6f05c-103">Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="6f05c-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>


<span data-ttu-id="6f05c-104">このトピックでは、Windows イメージングおよび展開プロセスの一部として MBAM を使用して、エンドユーザーのコンピューターで BitLocker を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-104">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="6f05c-105">ドライブのロックを解除できないことを示す、(インストールフェーズが終了した後に) 黒い画面が表示される場合は、「windows[と構成マネージャーのセットアップ後、windows 10 バージョン1511で BitLocker を事前に使用](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-105">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="6f05c-106">前提条件:</span><span class="sxs-lookup"><span data-stu-id="6f05c-106">Prerequisites:</span></span>**

-   <span data-ttu-id="6f05c-107">既存の Windows イメージ展開プロセス-Microsoft 展開ツールキット (MDT)、Microsoft System Center Configuration Manager、またはその他のイメージングツールまたはプロセスが存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-107">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="6f05c-108">TPM が BIOS で有効になっており、OS に対して表示されている必要がある</span><span class="sxs-lookup"><span data-stu-id="6f05c-108">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="6f05c-109">MBAM サーバーインフラストラクチャが配置され、アクセス可能である必要がある</span><span class="sxs-lookup"><span data-stu-id="6f05c-109">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="6f05c-110">BitLocker で必要なシステムパーティションを作成する必要がある</span><span class="sxs-lookup"><span data-stu-id="6f05c-110">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="6f05c-111">MBAM が完全に BitLocker を有効にするには、イメージング中にコンピューターがドメインに参加している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-111">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="6f05c-112">Windows 展開の一部として MBAM 2.5 SP1 を使用して BitLocker を有効にするには</span><span class="sxs-lookup"><span data-stu-id="6f05c-112">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="6f05c-113">MBAM 2.5 SP1 では、Windows の展開中に BitLocker を有効にするための推奨される方法は、PowerShell スクリプトを使用することです `Invoke-MbamClientDeployment.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="6f05c-113">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="6f05c-114">この `Invoke-MbamClientDeployment.ps1` スクリプトは、イメージングプロセス中に BitLocker を enacts します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-114">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="6f05c-115">BitLocker ポリシーによって要求された場合、MBAM agent は、ドメインユーザーがイメージング後に最初にログオンしたときに、ドメインユーザーが PIN またはパスワードを作成するように直ちに確認します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-115">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="6f05c-116">MDT、System Center Configuration Manager、または単体のイメージングプロセスで使いやすくなりました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-116">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="6f05c-117">PowerShell 2.0 以上と互換性がある</span><span class="sxs-lookup"><span data-stu-id="6f05c-117">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="6f05c-118">TPM キーの保護機能を使用して OS ボリュームを暗号化する</span><span class="sxs-lookup"><span data-stu-id="6f05c-118">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="6f05c-119">BitLocker 事前プロビジョニングの完全なサポート</span><span class="sxs-lookup"><span data-stu-id="6f05c-119">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="6f05c-120">必要に応じて FDDs を暗号化する</span><span class="sxs-lookup"><span data-stu-id="6f05c-120">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="6f05c-121">Windows 7 用のエスクロー TPM OwnerAuth、MBAM は、エスクローの TPM を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-121">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="6f05c-122">Windows 8.1、Windows 10 RTM、Windows 10 バージョン1511では、TPM OwnerAuth のエスクローがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6f05c-122">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="6f05c-123">Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-123">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="6f05c-124">Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-124">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="6f05c-125">詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-125">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="6f05c-126">エスクローの回復キーと回復キーパッケージ</span><span class="sxs-lookup"><span data-stu-id="6f05c-126">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="6f05c-127">暗号化の状態を直ちに報告する</span><span class="sxs-lookup"><span data-stu-id="6f05c-127">Report encryption status immediately</span></span>

   -   <span data-ttu-id="6f05c-128">新しい WMI プロバイダー</span><span class="sxs-lookup"><span data-stu-id="6f05c-128">New WMI providers</span></span>

   -   <span data-ttu-id="6f05c-129">詳細なログ記録</span><span class="sxs-lookup"><span data-stu-id="6f05c-129">Detailed logging</span></span>

   -   <span data-ttu-id="6f05c-130">堅牢なエラー処理</span><span class="sxs-lookup"><span data-stu-id="6f05c-130">Robust error handling</span></span>

   <span data-ttu-id="6f05c-131">`Invoke-MbamClientDeployment.ps1` [Microsoft.com ダウンロードセンター](https://www.microsoft.com/download/details.aspx?id=54439)からスクリプトをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-131">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="6f05c-132">これは、展開システムで呼び出され、MBAM サーバーで BitLocker ドライブの暗号化を構成し、回復キーを記録するための主要なスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="6f05c-132">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="6f05c-133">**MBAM の WMI 展開方法:** 以下の WMI メソッドは、MBAM 2.5 SP1 で追加され、PowerShell スクリプトを使用した BitLocker の有効化をサポートしてい `Invoke-MbamClientDeployment.ps1` ます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-133">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="6f05c-134">**Mbam \ _MACHINE WMI クラス** 
   **PrepareTpmAndEscrowOwnerAuth:** MBAM 回復サービスを使用して、TPM OwnerAuth を読み取り、MBAM 回復データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-134">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="6f05c-135">TPM が所有されておらず、自動プロビジョニングがオンになっていない場合は、TPM OwnerAuth を生成し、所有権を取得します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-135">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="6f05c-136">失敗した場合は、トラブルシューティングのためにエラーコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-136">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="6f05c-137">**注**Windows 10 バージョン1607以降では、Windows のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-137">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="6f05c-138">Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-138">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="6f05c-139">詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-139">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="6f05c-140">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f05c-140">Parameter</span></span> | <span data-ttu-id="6f05c-141">説明</span><span class="sxs-lookup"><span data-stu-id="6f05c-141">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="6f05c-142">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-142">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="6f05c-143">MBAM 回復サービスのエンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6f05c-143">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="6f05c-144">一般的なエラーメッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-144">Here are a list of common error messages:</span></span>

| <span data-ttu-id="6f05c-145">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="6f05c-145">Common return values</span></span> | <span data-ttu-id="6f05c-146">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="6f05c-146">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="6f05c-147">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f05c-147">S_OK</span></span>**<br /><span data-ttu-id="6f05c-148">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="6f05c-148">0 (0x0)</span></span> | <span data-ttu-id="6f05c-149">メソッドが正常に処理されました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-149">The method was successful.</span></span> |
| **<span data-ttu-id="6f05c-150">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="6f05c-150">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="6f05c-151">2147746304 (0x80040200)</span><span class="sxs-lookup"><span data-stu-id="6f05c-151">2147746304 (0x80040200)</span></span> | <span data-ttu-id="6f05c-152">TPM がコンピューターに存在しないか、BIOS 構成で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="6f05c-152">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="6f05c-153">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="6f05c-153">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="6f05c-154">2147746305 (0x80040201)</span><span class="sxs-lookup"><span data-stu-id="6f05c-154">2147746305 (0x80040201)</span></span> | <span data-ttu-id="6f05c-155">TPM が正しい状態ではありません (有効、アクティブ化、所有者インストールが許可されています)。</span><span class="sxs-lookup"><span data-stu-id="6f05c-155">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="6f05c-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="6f05c-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="6f05c-157">2147746306 (0x80040202)</span><span class="sxs-lookup"><span data-stu-id="6f05c-157">2147746306 (0x80040202)</span></span> | <span data-ttu-id="6f05c-158">自動プロビジョニングが保留になっているため、MBAM は TPM の所有権を取得できません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-158">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="6f05c-159">自動プロビジョニングが完了したら、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-159">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="6f05c-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="6f05c-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="6f05c-161">2147746307 (0x80040203)</span><span class="sxs-lookup"><span data-stu-id="6f05c-161">2147746307 (0x80040203)</span></span> | <span data-ttu-id="6f05c-162">MBAM は、TPM 所有者認証の値を読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-162">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="6f05c-163">この値は、エスクローが正常に完了した後に削除された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-163">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="6f05c-164">Windows 7 では、TPM が他のユーザーによって所有されている場合、MBAM は値を読み取ることができません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-164">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="6f05c-165">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="6f05c-165">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="6f05c-166">2147746308 (0x80040204)</span><span class="sxs-lookup"><span data-stu-id="6f05c-166">2147746308 (0x80040204)</span></span> | <span data-ttu-id="6f05c-167">TPM を適切な状態に設定するには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-167">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="6f05c-168">場合によっては、手動でコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-168">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="6f05c-169">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="6f05c-169">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="6f05c-170">2147746309 (0x80040205)</span><span class="sxs-lookup"><span data-stu-id="6f05c-170">2147746309 (0x80040205)</span></span> | <span data-ttu-id="6f05c-171">TPM を適切な状態に設定するには、コンピューターをシャットダウンして再び有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-171">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="6f05c-172">場合によっては、手動でコンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-172">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="6f05c-173">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="6f05c-173">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="6f05c-174">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="6f05c-174">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="6f05c-175">リモートエンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-175">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="6f05c-176">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6f05c-176">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="6f05c-177">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="6f05c-177">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="6f05c-178">リモートエンドポイントが存在しないか、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-178">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="6f05c-179">\* \* WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="6f05c-179">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="6f05c-180">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="6f05c-180">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="6f05c-181">リモートエンドポイントが要求を処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-181">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="6f05c-182">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="6f05c-182">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="6f05c-183">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="6f05c-183">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="6f05c-184">リモートエンドポイントにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-184">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="6f05c-185">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="6f05c-185">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="6f05c-186">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="6f05c-186">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="6f05c-187">リモートエンドポイントからエラーを含むメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-187">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="6f05c-188">適切なサービスエンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-188">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="6f05c-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="6f05c-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="6f05c-190">エンドポイントアドレス URL が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-190">The endpoint address URL is not valid.</span></span> <span data-ttu-id="6f05c-191">URL は "http" または "https" で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-191">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="6f05c-192">**レポートの状態:** MBAM ステータスレポートサービスを使用して、ボリュームのコンプライアンスステータスを読み取り、MBAM コンプライアンスステータスデータベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-192">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="6f05c-193">状態には、暗号強度、プロテクターの種類、プロテクターの状態、暗号化状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-193">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="6f05c-194">失敗した場合は、トラブルシューティングのためにエラーコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-194">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="6f05c-195">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f05c-195">Parameter</span></span> | <span data-ttu-id="6f05c-196">説明</span><span class="sxs-lookup"><span data-stu-id="6f05c-196">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="6f05c-197">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-197">ReportingServiceEndPoint</span></span> | <span data-ttu-id="6f05c-198">MBAM ステータスレポートサービスのエンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6f05c-198">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="6f05c-199">一般的なエラーメッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-199">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="6f05c-200">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="6f05c-200">Common return values</span></span> | <span data-ttu-id="6f05c-201">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="6f05c-201">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="6f05c-202">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f05c-202">S_OK</span></span>**<br /> <span data-ttu-id="6f05c-203">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="6f05c-203">0 (0x0)</span></span> | <span data-ttu-id="6f05c-204">メソッドが成功しました</span><span class="sxs-lookup"><span data-stu-id="6f05c-204">The method was successful</span></span> |
   | **<span data-ttu-id="6f05c-205">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="6f05c-205">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="6f05c-206">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="6f05c-206">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="6f05c-207">リモートエンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-207">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="6f05c-208">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6f05c-208">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="6f05c-209">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="6f05c-209">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="6f05c-210">リモートエンドポイントが存在しないか、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-210">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="6f05c-211">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="6f05c-211">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="6f05c-212">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="6f05c-212">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="6f05c-213">リモートエンドポイントが要求を処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-213">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="6f05c-214">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="6f05c-214">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="6f05c-215">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="6f05c-215">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="6f05c-216">リモートエンドポイントにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-216">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="6f05c-217">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="6f05c-217">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="6f05c-218">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="6f05c-218">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="6f05c-219">リモートエンドポイントからエラーを含むメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-219">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="6f05c-220">適切なサービスエンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-220">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="6f05c-221">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="6f05c-221">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="6f05c-222">2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="6f05c-222">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="6f05c-223">エンドポイントアドレス URL が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-223">The endpoint address URL is not valid.</span></span> <span data-ttu-id="6f05c-224">URL は "http" または "https" で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-224">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="6f05c-225">**Mbam \ _VOLUME WMI Class** **EscrowRecoveryKey:** ボリュームの回復数値パスワードとキーパッケージを読み取り、mbam 回復サービスを使用して、それらを mbam 回復データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-225">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="6f05c-226">失敗した場合は、トラブルシューティングのためにエラーコードが返されます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-226">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="6f05c-227">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f05c-227">Parameter</span></span> | <span data-ttu-id="6f05c-228">説明</span><span class="sxs-lookup"><span data-stu-id="6f05c-228">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="6f05c-229">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-229">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="6f05c-230">MBAM 回復サービスのエンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="6f05c-230">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="6f05c-231">一般的なエラーメッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-231">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="6f05c-232">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="6f05c-232">Common return values</span></span> | <span data-ttu-id="6f05c-233">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="6f05c-233">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="6f05c-234">S_OK</span><span class="sxs-lookup"><span data-stu-id="6f05c-234">S_OK</span></span>**<br /><span data-ttu-id="6f05c-235">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="6f05c-235">0 (0x0)</span></span> | <span data-ttu-id="6f05c-236">メソッドが成功しました</span><span class="sxs-lookup"><span data-stu-id="6f05c-236">The method was successful</span></span> |
   | **<span data-ttu-id="6f05c-237">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="6f05c-237">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="6f05c-238">2150694912 (0x80310000)</span><span class="sxs-lookup"><span data-stu-id="6f05c-238">2150694912 (0x80310000)</span></span> | <span data-ttu-id="6f05c-239">ボリュームがロックされています。</span><span class="sxs-lookup"><span data-stu-id="6f05c-239">The volume is locked.</span></span> |
   | **<span data-ttu-id="6f05c-240">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6f05c-240">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="6f05c-241">2150694963 (0x80310033)</span><span class="sxs-lookup"><span data-stu-id="6f05c-241">2150694963 (0x80310033)</span></span> | <span data-ttu-id="6f05c-242">ボリュームの数値パスワード保護機能が見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-242">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="6f05c-243">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="6f05c-243">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="6f05c-244">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="6f05c-244">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="6f05c-245">リモートエンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-245">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="6f05c-246">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="6f05c-246">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="6f05c-247">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="6f05c-247">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="6f05c-248">リモートエンドポイントが存在しないか、見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-248">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="6f05c-249">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="6f05c-249">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="6f05c-250">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="6f05c-250">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="6f05c-251">リモートエンドポイントが要求を処理できませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-251">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="6f05c-252">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="6f05c-252">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="6f05c-253">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="6f05c-253">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="6f05c-254">リモートエンドポイントにアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="6f05c-254">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="6f05c-255">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="6f05c-255">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="6f05c-256">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="6f05c-256">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="6f05c-257">リモートエンドポイントからエラーを含むメッセージを受信しました。</span><span class="sxs-lookup"><span data-stu-id="6f05c-257">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="6f05c-258">適切なサービスエンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-258">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="6f05c-259">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="6f05c-259">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="6f05c-260">2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="6f05c-260">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="6f05c-261">エンドポイントアドレス URL が有効ではありません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-261">The endpoint address URL is not valid.</span></span> <span data-ttu-id="6f05c-262">URL は "http" または "https" で始める必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-262">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="6f05c-263">Microsoft 展開ツールキット (MDT) と PowerShell を使用して MBAM を展開する</span><span class="sxs-lookup"><span data-stu-id="6f05c-263">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="6f05c-264">MDT で、新しい展開共有を作成するか、既存の展開共有を開きます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-264">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="6f05c-265">注</span><span class="sxs-lookup"><span data-stu-id="6f05c-265">Note</span></span>**  
       <span data-ttu-id="6f05c-266">`Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、任意のイメージングプロセスまたはツールで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-266">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="6f05c-267">このセクションでは、MDT を使用してこれを統合する方法について説明します。手順は、他のプロセスやツールとの統合に似ています。</span><span class="sxs-lookup"><span data-stu-id="6f05c-267">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="6f05c-268">注意</span><span class="sxs-lookup"><span data-stu-id="6f05c-268">Caution</span></span>**  
       <span data-ttu-id="6f05c-269">BitLocker の事前プロビジョニング (WinPE) を使用していて、TPM 所有者認証値を維持する場合は、 `SaveWinPETpmOwnerAuth.wsf` インストールが完全なオペレーティングシステムに再起動される直前に、WinPE にスクリプトを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-269">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="6f05c-270">このスクリプトを使っていない場合は、再起動時に TPM 所有者認証値が失われます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-270">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="6f05c-271">展開 `Invoke-MbamClientDeployment.ps1` する\*\* &lt; &gt; \\ スクリプトを共有\*\*します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-271">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="6f05c-272">事前プロビジョニングを使用している場合は、 `SaveWinPETpmOwnerAuth.wsf` ファイルを\*\* &lt; deploymentshare &gt; ¥¥のスクリプト\*\*にコピーします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-272">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="6f05c-273">MBAM 2.5 SP1 クライアントアプリケーションを展開共有のアプリケーションノードに追加します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-273">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="6f05c-274">[**アプリケーション**] ノードで [**新しいアプリケーション**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-274">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="6f05c-275">[**ソースファイルを含むアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-275">Select **Application with Source Files**.</span></span> <span data-ttu-id="6f05c-276">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-276">Click **Next**.</span></span>

       3.  <span data-ttu-id="6f05c-277">[**アプリケーション名**] に「mbam 2.5 SP1 クライアント」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-277">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="6f05c-278">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-278">Click **Next**.</span></span>

       4.  <span data-ttu-id="6f05c-279">が保存されているディレクトリに移動 `MBAMClientSetup-<Version>.msi` します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-279">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="6f05c-280">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-280">Click **Next**.</span></span>

       5.  <span data-ttu-id="6f05c-281">作成するディレクトリとして「MBAM 2.5 SP1 クライアント」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-281">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="6f05c-282">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-282">Click **Next**.</span></span>

       6.  <span data-ttu-id="6f05c-283">コマンドラインで Enter キーを押す `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 。</span><span class="sxs-lookup"><span data-stu-id="6f05c-283">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="6f05c-284">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-284">Click **Next**.</span></span>

       7.  <span data-ttu-id="6f05c-285">残りの既定値をそのまま使用して、アプリケーションの新規作成ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-285">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="6f05c-286">MDT で、展開共有の名前を右クリックし、[**プロパティ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-286">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="6f05c-287">[**ルール**] タブをクリックします。次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-287">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="6f05c-288">[OK] をクリックしてウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-288">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="6f05c-289">[タスクシーケンス] ノードで、Windows 展開に使用する既存のタスクシーケンスを編集します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-289">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="6f05c-290">必要に応じて、新しいタスクシーケンスを作成するには、[**タスクシーケンス**] ノードを右クリックし、[**新しいタスクシーケンス**] を選択して、ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-290">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="6f05c-291">選択したタスクシーケンスの [**タスクシーケンス**] タブで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-291">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="6f05c-292">[**プレインストール**] フォルダーの下で、bitlocker を有効にする (使用されているスペースのみを暗号化する) 場合は、[ **Bitlocker を有効にする (オフライン)** ] オプションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-292">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="6f05c-293">事前プロビジョニングを使用して TPM OwnerAuth を保持し、MBAM が後でエスクローできるようにするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6f05c-293">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="6f05c-294">**オペレーティングシステムのインストール**手順を確認する</span><span class="sxs-lookup"><span data-stu-id="6f05c-294">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="6f05c-295">新しい**Run コマンドライン**ステップを追加する</span><span class="sxs-lookup"><span data-stu-id="6f05c-295">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="6f05c-296">手順に名前を指定する**TPM OwnerAuth を保持**する</span><span class="sxs-lookup"><span data-stu-id="6f05c-296">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="6f05c-297">コマンドラインを注に設定し `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **ます。** windows 10 バージョン1607以降では、WINDOWS のみが TPM の所有権を取得できます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-297">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="6f05c-298">Addiiton では、TPM のプロビジョニング時に Windows は TPM 所有者パスワードを保持しません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-298">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="6f05c-299">詳細については、 [TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-299">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="6f05c-300">[**状態の復元**] フォルダーで、[ **BitLocker を有効にする**] タスクを削除します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-300">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="6f05c-301">[**カスタムタスク**] の下の [**状態の復元**] フォルダーで、新しい**インストールアプリケーション**タスクを作成し、「 **mbam Agent をインストール**する」という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-301">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="6f05c-302">[**単一のアプリケーションをインストール**する] ラジオボタンをクリックし、前に作成した mbam 2.5 SP1 クライアントアプリケーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-302">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="6f05c-303">[**カスタムタスク**] の下の [**状態の復元**] フォルダーで、次の設定を使用して (Mbam 2.5 SP1 クライアントアプリケーションの実行後に) 新しい**PowerShell スクリプト**タスクを作成します (お使いの環境に応じてパラメーターを更新します)。</span><span class="sxs-lookup"><span data-stu-id="6f05c-303">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="6f05c-304">名前: MBAM の BitLocker を構成する</span><span class="sxs-lookup"><span data-stu-id="6f05c-304">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="6f05c-305">PowerShell スクリプト:</span><span class="sxs-lookup"><span data-stu-id="6f05c-305">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="6f05c-306">引き</span><span class="sxs-lookup"><span data-stu-id="6f05c-306">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="6f05c-307">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-307">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-308">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="6f05c-308">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-309">MBAM 回復サービスのエンドポイント</span><span class="sxs-lookup"><span data-stu-id="6f05c-309">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="6f05c-310">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-310">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-311">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6f05c-311">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-312">MBAM ステータスレポートサービスのエンドポイント</span><span class="sxs-lookup"><span data-stu-id="6f05c-312">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="6f05c-313">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="6f05c-313">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-314">省略可能。</span><span class="sxs-lookup"><span data-stu-id="6f05c-314">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-315">暗号化方法 (既定: AES 128)</span><span class="sxs-lookup"><span data-stu-id="6f05c-315">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="6f05c-316">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="6f05c-316">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-317">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-317">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-318">データボリュームとエスクローデータボリューム回復キーを暗号化するように指定する</span><span class="sxs-lookup"><span data-stu-id="6f05c-318">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="6f05c-319">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="6f05c-319">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-320">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-320">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-321">暗号化が完了するまで待機することを指定します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-321">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="6f05c-322">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="6f05c-322">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-323">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-323">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-324">展開スクリプトが中断された暗号化を再開しないように指定する</span><span class="sxs-lookup"><span data-stu-id="6f05c-324">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="6f05c-325">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="6f05c-325">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-326">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-326">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-327">TPM 所有者の認証エスクローエラーを無視するように指定します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-327">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="6f05c-328">これは、MBAM が TPM 所有者認証を読み取ることができないシナリオで使用する必要があります。たとえば、TPM 自動プロビジョニングが有効になっている場合</span><span class="sxs-lookup"><span data-stu-id="6f05c-328">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="6f05c-329">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="6f05c-329">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-330">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-331">ボリューム回復キーのエスクローエラーを無視するように指定する</span><span class="sxs-lookup"><span data-stu-id="6f05c-331">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="6f05c-332">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="6f05c-332">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-333">スイッチ</span><span class="sxs-lookup"><span data-stu-id="6f05c-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="6f05c-334">状態レポートエラーを無視するように指定する</span><span class="sxs-lookup"><span data-stu-id="6f05c-334">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="6f05c-335">Windows 展開の一部として MBAM 2.5 またはそれ以前のバージョンを使用して BitLocker を有効にするには</span><span class="sxs-lookup"><span data-stu-id="6f05c-335">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="6f05c-336">MBAM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-336">Install the MBAM Client.</span></span> <span data-ttu-id="6f05c-337">手順については、「[コマンドラインを使用して MBAM クライアントを展開する方法](how-to-deploy-the-mbam-client-by-using-a-command-line.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-337">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="6f05c-338">コンピューターをドメインに参加させる (推奨)。</span><span class="sxs-lookup"><span data-stu-id="6f05c-338">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="6f05c-339">コンピューターがドメインに参加していない場合は、MBAM キーの回復サービスに回復パスワードは保存されません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-339">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="6f05c-340">既定では、MBAM は、回復キーが保存されていない限り、暗号化を実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-340">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="6f05c-341">MBAM サーバーに回復キーが保存される前に、コンピューターが回復モードで起動した場合、回復方法はありません。また、コンピューターを再イメージする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-341">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="6f05c-342">管理者としてコマンドプロンプトを開き、MBAM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-342">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="6f05c-343">次のコマンドを入力して、サービスを**手動**または**オンデマンド**に設定します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-343">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="6f05c-344">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="6f05c-344">net stop mbamagent</span></span>**

    **<span data-ttu-id="6f05c-345">sc config mbamagent start = demand</span><span class="sxs-lookup"><span data-stu-id="6f05c-345">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="6f05c-346">MBAM クライアントがグループポリシー設定を無視するようにレジストリ値を設定します。代わりに、[暗号化] を設定して、Windows がそのクライアントコンピューターに展開された時刻を開始します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-346">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    <span data-ttu-id="6f05c-347">**注意** この手順では、Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-347">**Caution** This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="6f05c-348">レジストリエディターを誤って使用すると、Windows の再インストールが必要になる重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-348">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="6f05c-349">レジストリエディターの不正使用によって生じた問題を解決することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f05c-349">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="6f05c-350">レジストリエディターは、各自の責任において使用してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-350">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="6f05c-351">TPM を**オペレーティングシステムのみの暗号化**用に設定して、Regedit.exe を実行してから、レジストリキーテンプレートを、c/c + MDOP ¥でインポートします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-351">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="6f05c-352">Regedit.exe で、HKLM\\SOFTWARE\\Microsoft\\MBAM にアクセスし、次の表に示す設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-352">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        <span data-ttu-id="6f05c-353">**注** MBAM に関連するグループポリシー設定またはレジストリ値は、次のように設定できます。</span><span class="sxs-lookup"><span data-stu-id="6f05c-353">**Note** You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="6f05c-354">これらの設定は、以前に設定された値を無視します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-354">These settings will override previously set values.</span></span>

        <span data-ttu-id="6f05c-355">レジストリエントリ構成の設定</span><span class="sxs-lookup"><span data-stu-id="6f05c-355">Registry entry Configuration settings</span></span>

        <span data-ttu-id="6f05c-356">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="6f05c-356">DeploymentTime</span></span>

        <span data-ttu-id="6f05c-357">0 = オフ</span><span class="sxs-lookup"><span data-stu-id="6f05c-357">0 = Off</span></span>

        <span data-ttu-id="6f05c-358">1 = 展開時のポリシー設定 (既定) を使用– Windows がクライアントコンピューターに展開されたときに暗号化を有効にするには、この設定を使います。</span><span class="sxs-lookup"><span data-stu-id="6f05c-358">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="6f05c-359">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="6f05c-359">UseKeyRecoveryService</span></span>

        <span data-ttu-id="6f05c-360">0 = キーエスクローを使用しません (この場合、次の2つのレジストリエントリは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="6f05c-360">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="6f05c-361">1 = キー回復システムでキーエスクローを使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="6f05c-361">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="6f05c-362">これは、MBAM が回復キーを保存できるようにするための推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="6f05c-362">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="6f05c-363">コンピューターは、MBAM キーの回復サービスと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f05c-363">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="6f05c-364">続行する前に、コンピューターがサービスと通信できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-364">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="6f05c-365">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="6f05c-365">KeyRecoveryOptions</span></span>

        <span data-ttu-id="6f05c-366">0 = 回復キーのみをアップロードする</span><span class="sxs-lookup"><span data-stu-id="6f05c-366">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="6f05c-367">1 = 回復キーとキー回復パッケージ (既定) をアップロードする</span><span class="sxs-lookup"><span data-stu-id="6f05c-367">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="6f05c-368">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="6f05c-368">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="6f05c-369">この値は、キー回復サービスを実行しているサーバーの URL (http:// &lt; コンピューター名/MBAMRecoveryAndHardwareService/CoreService.svc. など) に設定します。 &gt;</span><span class="sxs-lookup"><span data-stu-id="6f05c-369">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="6f05c-370">Mbam クライアントの展開中に、MBAM クライアントがシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-370">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="6f05c-371">この再起動の準備ができたら、管理者としてコマンドプロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-371">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="6f05c-372">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="6f05c-372">net start mbamagent</span></span>**

7.  <span data-ttu-id="6f05c-373">コンピューターが再起動し、BIOS からプロンプトが表示されたら、TPM の変更を承諾します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-373">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="6f05c-374">Windows クライアントオペレーティングシステムのイメージングプロセスで、暗号化を開始する準備ができたら、コマンドプロンプトを管理者として開き、次のコマンドを入力して、[開始] を [**自動**] に設定し、Mbam クライアントエージェントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-374">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="6f05c-375">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="6f05c-375">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="6f05c-376">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="6f05c-376">net start mbamagent</span></span>**

9.  <span data-ttu-id="6f05c-377">バイパスレジストリ値を削除するには、Regedit.exe を実行し、HKLM\\SOFTWARE\\Microsoft レジストリエントリに移動します。</span><span class="sxs-lookup"><span data-stu-id="6f05c-377">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="6f05c-378">**Mbam**ノードを右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f05c-378">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="6f05c-379">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6f05c-379">Related topics</span></span>

[<span data-ttu-id="6f05c-380">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="6f05c-380">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="6f05c-381">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="6f05c-381">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <span data-ttu-id="6f05c-382">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-382">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6f05c-383">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-383">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="6f05c-384">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6f05c-384">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
