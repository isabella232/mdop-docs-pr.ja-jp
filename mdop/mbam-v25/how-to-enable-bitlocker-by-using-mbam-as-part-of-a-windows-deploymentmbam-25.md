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
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626184"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a><span data-ttu-id="41091-103">Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="41091-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41091-104">これらの手順は、Configuration Manager BitLocker 管理には関係ではありません。</span><span class="sxs-lookup"><span data-stu-id="41091-104">These instructions do not pertain to Configuration Manager BitLocker Management.</span></span> <span data-ttu-id="41091-105">`Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、Configuration Manager の BitLocker 管理ではサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="41091-105">The `Invoke-MbamClientDeployment.ps1` PowerShell script is not supported for use with BitLocker Management in Configuration Manager.</span></span> <span data-ttu-id="41091-106">これには、Configuration Manager タスク シーケンス中の BitLocker 回復キーのエスクローが含まれます。</span><span class="sxs-lookup"><span data-stu-id="41091-106">This includes escrowing of BitLocker recovery keys during a Configuration Manager task sequence.</span></span> <span data-ttu-id="41091-107">さらに、Configuration Manager Current Branch 2103 から、Configuration Manager BitLocker Management は MBAM キー回復サービス サイトを使用してキーをエスクローしなくなりました。</span><span class="sxs-lookup"><span data-stu-id="41091-107">Furthermore, starting with Configuration Manager Current Branch 2103, Configuration Manager BitLocker Management no longer uses the MBAM key recovery services site to escrow keys.</span></span> <span data-ttu-id="41091-108">Configuration Manager Current Branch 2103 以降で PowerShell スクリプトを使用しようとすると、Configuration Manager サイトで重大な問題 `Invoke-MbamClientDeployment.ps1` が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41091-108">Attempting to use the `Invoke-MbamClientDeployment.ps1` PowerShell script with Configuration Manager Current Branch 2103 or newer can result in serious problems with the Configuration Manager site.</span></span> <span data-ttu-id="41091-109">既知の問題には、ポリシーストームを引き起こす可能性のあるすべてのデバイスを対象とした大量のポリシーの作成が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41091-109">Known problems include creation of a large amount of policy targeted to all devices which can cause policy storms.</span></span> <span data-ttu-id="41091-110">これにより、Configuration Manager のパフォーマンスが大幅に低下し、主に管理ポイントSQLパフォーマンスが低下します。</span><span class="sxs-lookup"><span data-stu-id="41091-110">This will lead to severe degradation of performance in Configuration Manager primarily in SQL and with Management Points.</span></span>

<span data-ttu-id="41091-111">このトピックでは、エンド ユーザーのコンピューターで BIT Windows Locker を有効にする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="41091-111">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="41091-112">ドライブのロックを解除できないことを示す黒い画面が再起動時 (インストール フェーズが終了した後) が表示される場合は、「Windows 10 バージョン[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)でプレプロビジョニング BitLocker を使用する場合は、以前の Windows バージョンが "セットアップ Windows と Configuration Manager" の手順の後で開始しない」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41091-112">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="41091-113">前提条件:</span><span class="sxs-lookup"><span data-stu-id="41091-113">Prerequisites:</span></span>**

-   <span data-ttu-id="41091-114">既存のイメージWindows展開プロセス (Microsoft Deployment Toolkit (MDT)、Microsoft System Center Configuration Manager、その他のイメージング ツールまたはプロセス) を配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-114">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="41091-115">TPM は BIOS で有効にし、OS から表示する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-115">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="41091-116">MBAM サーバー インフラストラクチャが配置され、アクセス可能である必要があります</span><span class="sxs-lookup"><span data-stu-id="41091-116">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="41091-117">BitLocker で必要なシステム パーティションを作成する必要があります</span><span class="sxs-lookup"><span data-stu-id="41091-117">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="41091-118">MBAM が BitLocker を完全に有効にする前に、コンピューターがイメージング中にドメインに参加している必要があります</span><span class="sxs-lookup"><span data-stu-id="41091-118">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="41091-119">MBAM 2.5 SP1 を使用して BitLocker を展開の一部としてWindowsするには</span><span class="sxs-lookup"><span data-stu-id="41091-119">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="41091-120">MBAM 2.5 SP1 では、PowerShell スクリプトを使用して、Windows展開中に BitLocker を有効にするための推奨される方法 `Invoke-MbamClientDeployment.ps1` です。</span><span class="sxs-lookup"><span data-stu-id="41091-120">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="41091-121">スクリプト `Invoke-MbamClientDeployment.ps1` は、イメージング プロセス中に BitLocker を実行します。</span><span class="sxs-lookup"><span data-stu-id="41091-121">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="41091-122">BitLocker ポリシーで要求された場合、MBAM エージェントは、イメージング後にドメイン ユーザーが最初にログオンするときに、すぐにドメイン ユーザーに PIN またはパスワードの作成を求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="41091-122">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="41091-123">MDT、System Center Configuration Managerスタンドアロンイメージングプロセスで使いやすい</span><span class="sxs-lookup"><span data-stu-id="41091-123">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="41091-124">PowerShell 2.0 以上と互換性がある</span><span class="sxs-lookup"><span data-stu-id="41091-124">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="41091-125">TPM キー プロテクタを使用して OS ボリュームを暗号化する</span><span class="sxs-lookup"><span data-stu-id="41091-125">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="41091-126">BitLocker の事前プロビジョニングを完全にサポート</span><span class="sxs-lookup"><span data-stu-id="41091-126">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="41091-127">必要に応じて FDD を暗号化する</span><span class="sxs-lookup"><span data-stu-id="41091-127">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="41091-128">Escrow TPM OwnerAuth Windows 7 の場合、MBAM はエスクローが発生するために TPM を所有している必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-128">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="41091-129">RT Windows 10 M Windows 8.1バージョン 1511 Windows 10バージョン 1511 では、TPM OwnerAuth のエスクローがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="41091-129">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="41091-130">バージョン Windows 10 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="41091-130">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="41091-131">addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="41091-131">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="41091-132">詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41091-132">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="41091-133">Escrow 回復キーと回復キー パッケージ</span><span class="sxs-lookup"><span data-stu-id="41091-133">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="41091-134">暗号化の状態を直ちに報告する</span><span class="sxs-lookup"><span data-stu-id="41091-134">Report encryption status immediately</span></span>

   -   <span data-ttu-id="41091-135">新しい WMI プロバイダー</span><span class="sxs-lookup"><span data-stu-id="41091-135">New WMI providers</span></span>

   -   <span data-ttu-id="41091-136">詳細なログ</span><span class="sxs-lookup"><span data-stu-id="41091-136">Detailed logging</span></span>

   -   <span data-ttu-id="41091-137">堅牢なエラー処理</span><span class="sxs-lookup"><span data-stu-id="41091-137">Robust error handling</span></span>

   <span data-ttu-id="41091-138">スクリプトは、ダウンロード `Invoke-MbamClientDeployment.ps1` センターから [Microsoft.com ダウンロードできます](https://www.microsoft.com/download/details.aspx?id=54439)。</span><span class="sxs-lookup"><span data-stu-id="41091-138">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="41091-139">これは、展開システムが BitLocker ドライブの暗号化を構成し、MBAM Server で回復キーを記録するために呼び出す主なスクリプトです。</span><span class="sxs-lookup"><span data-stu-id="41091-139">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="41091-140">**MBAM の WMI 展開方法:** PowerShell スクリプトを使用して BitLocker を有効にするための次の WMI メソッドが MBAM 2.5 SP1 `Invoke-MbamClientDeployment.ps1` に追加されました。</span><span class="sxs-lookup"><span data-stu-id="41091-140">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="41091-141">**MBAM\_Machine WMI クラス** 
   **PrepareTpmAndEscrowOwnerAuth:** TPM OwnerAuth を読み取り、MBAM 回復サービスを使用して MBAM 回復データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="41091-141">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="41091-142">TPM が所有されていない場合、自動プロビジョニングがオンではない場合は、TPM OwnerAuth が生成され、所有権が取得されます。</span><span class="sxs-lookup"><span data-stu-id="41091-142">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="41091-143">エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="41091-143">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="41091-144">**メモ**バージョン Windows 10 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="41091-144">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="41091-145">addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="41091-145">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="41091-146">詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41091-146">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="41091-147">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41091-147">Parameter</span></span> | <span data-ttu-id="41091-148">説明</span><span class="sxs-lookup"><span data-stu-id="41091-148">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="41091-149">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="41091-149">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="41091-150">MBAM 回復サービス エンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="41091-150">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="41091-151">一般的なエラー メッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41091-151">Here are a list of common error messages:</span></span>

| <span data-ttu-id="41091-152">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="41091-152">Common return values</span></span> | <span data-ttu-id="41091-153">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="41091-153">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="41091-154">S_OK</span><span class="sxs-lookup"><span data-stu-id="41091-154">S_OK</span></span>**<br /><span data-ttu-id="41091-155">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="41091-155">0 (0x0)</span></span> | <span data-ttu-id="41091-156">メソッドが成功しました。</span><span class="sxs-lookup"><span data-stu-id="41091-156">The method was successful.</span></span> |
| **<span data-ttu-id="41091-157">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="41091-157">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="41091-158">2147746304 (0x80040200)</span><span class="sxs-lookup"><span data-stu-id="41091-158">2147746304 (0x80040200)</span></span> | <span data-ttu-id="41091-159">TPM がコンピューターに存在しないか、BIOS 構成で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="41091-159">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="41091-160">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="41091-160">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="41091-161">2147746305 (0x80040201)</span><span class="sxs-lookup"><span data-stu-id="41091-161">2147746305 (0x80040201)</span></span> | <span data-ttu-id="41091-162">TPM が正しい状態ではありません (有効、アクティブ化、所有者のインストールが許可されます)。</span><span class="sxs-lookup"><span data-stu-id="41091-162">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="41091-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="41091-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="41091-164">2147746306 (0x80040202)</span><span class="sxs-lookup"><span data-stu-id="41091-164">2147746306 (0x80040202)</span></span> | <span data-ttu-id="41091-165">自動プロビジョニングが保留中のため、MBAM は TPM の所有権を取得できません。</span><span class="sxs-lookup"><span data-stu-id="41091-165">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="41091-166">自動プロビジョニングが完了したら、もう一度やり直してください。</span><span class="sxs-lookup"><span data-stu-id="41091-166">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="41091-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="41091-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="41091-168">2147746307 (0x80040203)</span><span class="sxs-lookup"><span data-stu-id="41091-168">2147746307 (0x80040203)</span></span> | <span data-ttu-id="41091-169">MBAM は TPM 所有者の承認値を読み取りできません。</span><span class="sxs-lookup"><span data-stu-id="41091-169">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="41091-170">値は、エスクローが成功した後に削除された可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41091-170">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="41091-171">7 Windows、TPM が他のユーザーによって所有されている場合、MBAM は値を読み取りできません。</span><span class="sxs-lookup"><span data-stu-id="41091-171">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="41091-172">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="41091-172">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="41091-173">2147746308 (0x80040204)</span><span class="sxs-lookup"><span data-stu-id="41091-173">2147746308 (0x80040204)</span></span> | <span data-ttu-id="41091-174">TPM を正しい状態に設定するには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-174">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="41091-175">コンピューターを手動で再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="41091-175">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="41091-176">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="41091-176">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="41091-177">2147746309 (0x80040205)</span><span class="sxs-lookup"><span data-stu-id="41091-177">2147746309 (0x80040205)</span></span> | <span data-ttu-id="41091-178">TPM を正しい状態に設定するには、コンピューターをシャットダウンしてオンに戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-178">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="41091-179">コンピューターを手動で再起動する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="41091-179">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="41091-180">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="41091-180">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="41091-181">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="41091-181">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="41091-182">リモート エンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="41091-182">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="41091-183">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="41091-183">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="41091-184">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="41091-184">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="41091-185">リモート エンドポイントが存在しないか、見つからなかった。</span><span class="sxs-lookup"><span data-stu-id="41091-185">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="41091-186">\*\*WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="41091-186">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="41091-187">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="41091-187">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="41091-188">リモート エンドポイントは要求を処理できません。</span><span class="sxs-lookup"><span data-stu-id="41091-188">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="41091-189">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="41091-189">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="41091-190">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="41091-190">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="41091-191">リモート エンドポイントに到達できません。</span><span class="sxs-lookup"><span data-stu-id="41091-191">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="41091-192">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="41091-192">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="41091-193">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="41091-193">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="41091-194">リモート エンドポイントから障害を含むメッセージが受信された。</span><span class="sxs-lookup"><span data-stu-id="41091-194">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="41091-195">正しいサービス エンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41091-195">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="41091-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="41091-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="41091-197">エンドポイント アドレス URL が無効です。</span><span class="sxs-lookup"><span data-stu-id="41091-197">The endpoint address URL is not valid.</span></span> <span data-ttu-id="41091-198">URL は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-198">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="41091-199">**ReportStatus:** MBAM 状態レポート サービスを使用して、ボリュームのコンプライアンス状態を読み取り、MBAM コンプライアンス状態データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="41091-199">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="41091-200">この状態には、暗号強度、プロテクタの種類、プロテクタの状態、暗号化状態が含まれます。</span><span class="sxs-lookup"><span data-stu-id="41091-200">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="41091-201">エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="41091-201">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="41091-202">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41091-202">Parameter</span></span> | <span data-ttu-id="41091-203">説明</span><span class="sxs-lookup"><span data-stu-id="41091-203">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="41091-204">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="41091-204">ReportingServiceEndPoint</span></span> | <span data-ttu-id="41091-205">MBAM 状態レポート サービス エンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="41091-205">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="41091-206">一般的なエラー メッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41091-206">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="41091-207">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="41091-207">Common return values</span></span> | <span data-ttu-id="41091-208">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="41091-208">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="41091-209">S_OK</span><span class="sxs-lookup"><span data-stu-id="41091-209">S_OK</span></span>**<br /> <span data-ttu-id="41091-210">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="41091-210">0 (0x0)</span></span> | <span data-ttu-id="41091-211">メソッドが成功しました</span><span class="sxs-lookup"><span data-stu-id="41091-211">The method was successful</span></span> |
   | **<span data-ttu-id="41091-212">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="41091-212">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="41091-213">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="41091-213">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="41091-214">リモート エンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="41091-214">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="41091-215">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="41091-215">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="41091-216">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="41091-216">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="41091-217">リモート エンドポイントが存在しないか、見つからなかった。</span><span class="sxs-lookup"><span data-stu-id="41091-217">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="41091-218">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="41091-218">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="41091-219">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="41091-219">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="41091-220">リモート エンドポイントは要求を処理できません。</span><span class="sxs-lookup"><span data-stu-id="41091-220">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="41091-221">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="41091-221">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="41091-222">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="41091-222">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="41091-223">リモート エンドポイントに到達できません。</span><span class="sxs-lookup"><span data-stu-id="41091-223">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="41091-224">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="41091-224">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="41091-225">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="41091-225">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="41091-226">リモート エンドポイントから障害を含むメッセージが受信された。</span><span class="sxs-lookup"><span data-stu-id="41091-226">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="41091-227">正しいサービス エンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41091-227">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="41091-228">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="41091-228">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="41091-229">2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="41091-229">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="41091-230">エンドポイント アドレス URL が無効です。</span><span class="sxs-lookup"><span data-stu-id="41091-230">The endpoint address URL is not valid.</span></span> <span data-ttu-id="41091-231">URL は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-231">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="41091-232">**MBAM\_Volume WMI クラス** **EscrowRecoveryKey:** ボリュームの回復数値パスワードとキー パッケージを読み取り、MBAM 回復サービスを使用して MBAM 回復データベースに送信します。</span><span class="sxs-lookup"><span data-stu-id="41091-232">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="41091-233">エラーが発生した場合は、トラブルシューティングのためにエラー コードが返されます。</span><span class="sxs-lookup"><span data-stu-id="41091-233">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="41091-234">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41091-234">Parameter</span></span> | <span data-ttu-id="41091-235">説明</span><span class="sxs-lookup"><span data-stu-id="41091-235">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="41091-236">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="41091-236">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="41091-237">MBAM 回復サービス エンドポイントを指定する文字列。</span><span class="sxs-lookup"><span data-stu-id="41091-237">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="41091-238">一般的なエラー メッセージの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="41091-238">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="41091-239">一般的な戻り値</span><span class="sxs-lookup"><span data-stu-id="41091-239">Common return values</span></span> | <span data-ttu-id="41091-240">エラー メッセージ</span><span class="sxs-lookup"><span data-stu-id="41091-240">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="41091-241">S_OK</span><span class="sxs-lookup"><span data-stu-id="41091-241">S_OK</span></span>**<br /><span data-ttu-id="41091-242">0 (0x0)</span><span class="sxs-lookup"><span data-stu-id="41091-242">0 (0x0)</span></span> | <span data-ttu-id="41091-243">メソッドが成功しました</span><span class="sxs-lookup"><span data-stu-id="41091-243">The method was successful</span></span> |
   | **<span data-ttu-id="41091-244">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="41091-244">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="41091-245">2150694912 (0x80310000)</span><span class="sxs-lookup"><span data-stu-id="41091-245">2150694912 (0x80310000)</span></span> | <span data-ttu-id="41091-246">ボリュームがロックされています。</span><span class="sxs-lookup"><span data-stu-id="41091-246">The volume is locked.</span></span> |
   | **<span data-ttu-id="41091-247">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="41091-247">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="41091-248">2150694963 (0x80310033)</span><span class="sxs-lookup"><span data-stu-id="41091-248">2150694963 (0x80310033)</span></span> | <span data-ttu-id="41091-249">ボリュームの数値パスワード プロテクタが見つかりませんでした。</span><span class="sxs-lookup"><span data-stu-id="41091-249">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="41091-250">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="41091-250">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="41091-251">2151481349 (0x803D0005)</span><span class="sxs-lookup"><span data-stu-id="41091-251">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="41091-252">リモート エンドポイントによってアクセスが拒否されました。</span><span class="sxs-lookup"><span data-stu-id="41091-252">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="41091-253">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="41091-253">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="41091-254">2151481357 (0x803D000D)</span><span class="sxs-lookup"><span data-stu-id="41091-254">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="41091-255">リモート エンドポイントが存在しないか、見つからなかった。</span><span class="sxs-lookup"><span data-stu-id="41091-255">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="41091-256">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="41091-256">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="41091-257">2151481357 (0x803D000F)</span><span class="sxs-lookup"><span data-stu-id="41091-257">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="41091-258">リモート エンドポイントは要求を処理できません。</span><span class="sxs-lookup"><span data-stu-id="41091-258">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="41091-259">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="41091-259">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="41091-260">2151481360 (0x803D0010)</span><span class="sxs-lookup"><span data-stu-id="41091-260">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="41091-261">リモート エンドポイントに到達できません。</span><span class="sxs-lookup"><span data-stu-id="41091-261">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="41091-262">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="41091-262">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="41091-263">2151481363 (0x803D0013)</span><span class="sxs-lookup"><span data-stu-id="41091-263">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="41091-264">リモート エンドポイントから障害を含むメッセージが受信された。</span><span class="sxs-lookup"><span data-stu-id="41091-264">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="41091-265">正しいサービス エンドポイントに接続していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="41091-265">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="41091-266">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="41091-266">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="41091-267">2151481376 (0x803D0020)</span><span class="sxs-lookup"><span data-stu-id="41091-267">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="41091-268">エンドポイント アドレス URL が無効です。</span><span class="sxs-lookup"><span data-stu-id="41091-268">The endpoint address URL is not valid.</span></span> <span data-ttu-id="41091-269">URL は "http" または "https" で始まる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-269">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="41091-270">Microsoft Deployment Toolkit (MDT) と PowerShell を使用して MBAM を展開する</span><span class="sxs-lookup"><span data-stu-id="41091-270">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="41091-271">MDT で、新しい展開共有を作成するか、既存の展開共有を開きます。</span><span class="sxs-lookup"><span data-stu-id="41091-271">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="41091-272">備考</span><span class="sxs-lookup"><span data-stu-id="41091-272">Note</span></span>**  
       <span data-ttu-id="41091-273">`Invoke-MbamClientDeployment.ps1`PowerShell スクリプトは、任意のイメージング プロセスまたはツールで使用できます。</span><span class="sxs-lookup"><span data-stu-id="41091-273">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="41091-274">このセクションでは、MDT を使用して統合する方法を示しますが、手順は他のプロセスやツールとの統合に似ています。</span><span class="sxs-lookup"><span data-stu-id="41091-274">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="41091-275">注意</span><span class="sxs-lookup"><span data-stu-id="41091-275">Caution</span></span>**  
       <span data-ttu-id="41091-276">BitLocker プレプロビジョニング (WinPE) を使用し、TPM 所有者の承認値を維持する場合は、インストールが完全なオペレーティング システムに再起動される直前に WinPE でスクリプトを追加する必要があります。 `SaveWinPETpmOwnerAuth.wsf`</span><span class="sxs-lookup"><span data-stu-id="41091-276">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="41091-277">このスクリプトを使用しない場合、再起動時に TPM 所有者の承認値が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="41091-277">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="41091-278">`Invoke-MbamClientDeployment.ps1` \*\* &lt; DeploymentShare &gt; \\Scripts にコピーします\*\*。</span><span class="sxs-lookup"><span data-stu-id="41091-278">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="41091-279">事前プロビジョニングを使用している場合は、ファイルを `SaveWinPETpmOwnerAuth.wsf` \*\* &lt; DeploymentShare &gt; \\Scripts にコピーします\*\*。</span><span class="sxs-lookup"><span data-stu-id="41091-279">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="41091-280">展開共有の [アプリケーション] ノードに MBAM 2.5 SP1 クライアント アプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="41091-280">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="41091-281">[アプリケーション] **ノードで、[** 新しいアプリケーション] **をクリックします**。</span><span class="sxs-lookup"><span data-stu-id="41091-281">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="41091-282">[ソース **ファイルを含むアプリケーション] を選択します**。</span><span class="sxs-lookup"><span data-stu-id="41091-282">Select **Application with Source Files**.</span></span> <span data-ttu-id="41091-283">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41091-283">Click **Next**.</span></span>

       3.  <span data-ttu-id="41091-284">[ **アプリケーション名]** に「MBAM 2.5 SP1 クライアント」と入力します。</span><span class="sxs-lookup"><span data-stu-id="41091-284">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="41091-285">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41091-285">Click **Next**.</span></span>

       4.  <span data-ttu-id="41091-286">を含むディレクトリを参照します `MBAMClientSetup-<Version>.msi` 。</span><span class="sxs-lookup"><span data-stu-id="41091-286">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="41091-287">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41091-287">Click **Next**.</span></span>

       5.  <span data-ttu-id="41091-288">作成するディレクトリに「MBAM 2.5 SP1 Client」と入力します。</span><span class="sxs-lookup"><span data-stu-id="41091-288">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="41091-289">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41091-289">Click **Next**.</span></span>

       6.  <span data-ttu-id="41091-290">コマンド `msiexec /i MBAMClientSetup-<Version>.msi /quiet` ラインで入力します。</span><span class="sxs-lookup"><span data-stu-id="41091-290">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="41091-291">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="41091-291">Click **Next**.</span></span>

       7.  <span data-ttu-id="41091-292">残りの既定値を受け入れて、新しいアプリケーション ウィザードを完了します。</span><span class="sxs-lookup"><span data-stu-id="41091-292">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="41091-293">MDT で、展開共有の名前を右クリックし、[プロパティ] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="41091-293">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="41091-294">[ルール] **タブをクリック** します。次の行を追加します。</span><span class="sxs-lookup"><span data-stu-id="41091-294">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="41091-295">[OK] をクリックしてウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="41091-295">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="41091-296">[タスク シーケンス] ノードで、展開に使用する既存のタスク Windowsします。</span><span class="sxs-lookup"><span data-stu-id="41091-296">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="41091-297">必要な場合は、[タスク シーケンス] ノードを右クリックし、[新\*\*\*\* しいタスク シーケンス] を\*\*\*\* 選択し、ウィザードを完了することで、新しいタスク シーケンスを作成できます。</span><span class="sxs-lookup"><span data-stu-id="41091-297">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="41091-298">選択した **タスク シーケンスの** [タスク シーケンス] タブで、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41091-298">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="41091-299">WinPE **で BitLocker** を有効にする場合は、[プレインストール] フォルダーでオプションのタスク [BitLocker を有効 **にする (オフライン)** を有効にします。これは、使用済み領域のみを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="41091-299">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="41091-300">事前プロビジョニングを使用するときに TPM OwnerAuth を保持し、MBAM が後でエスケープできるようにするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="41091-300">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="41091-301">[オペレーティング システム **のインストール] 手順を見** つける</span><span class="sxs-lookup"><span data-stu-id="41091-301">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="41091-302">その後に新 **しいコマンド ラインの実行** 手順を追加する</span><span class="sxs-lookup"><span data-stu-id="41091-302">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="41091-303">ステップに名前を **付け、TPM OwnerAuth を保持する**</span><span class="sxs-lookup"><span data-stu-id="41091-303">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="41091-304">コマンド ラインを `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **[メモ]** に設定します。Windows 10バージョン 1607 以降の場合、TPM のWindowsを取得できるのはユーザーのみです。</span><span class="sxs-lookup"><span data-stu-id="41091-304">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="41091-305">addiiton では、Windowsプロビジョニング時に TPM 所有者パスワードが保持されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="41091-305">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="41091-306">詳細については [、「TPM 所有者パスワード](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41091-306">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="41091-307">[状態の **復元] フォルダー** で **、[BitLocker の有効化] タスクを削除** します。</span><span class="sxs-lookup"><span data-stu-id="41091-307">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="41091-308">[カスタム タスク **] の [状態の** 復元] **フォルダー**で、新しい **[** アプリケーションのインストール] タスクを作成し、[MBAM エージェントのインストール **] という名前を付きます**。</span><span class="sxs-lookup"><span data-stu-id="41091-308">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="41091-309">[単 **一アプリケーションのインストール]** ラジオ ボタンをクリックし、前に作成した MBAM 2.5 SP1 クライアント アプリケーションを参照します。</span><span class="sxs-lookup"><span data-stu-id="41091-309">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="41091-310">[カスタム**タスク]** \*\*\*\* の [状態の復元] フォルダーで、次の設定を使用して新しい**PowerShell**スクリプト実行タスク (MBAM 2.5 SP1 クライアント アプリケーション ステップの後) を作成します (環境に応じてパラメーターを更新します)。</span><span class="sxs-lookup"><span data-stu-id="41091-310">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="41091-311">名前: MBAM 用に BitLocker を構成する</span><span class="sxs-lookup"><span data-stu-id="41091-311">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="41091-312">PowerShell スクリプト:</span><span class="sxs-lookup"><span data-stu-id="41091-312">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="41091-313">パラメーター:</span><span class="sxs-lookup"><span data-stu-id="41091-313">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="41091-314">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="41091-314">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-315">必須かどうか</span><span class="sxs-lookup"><span data-stu-id="41091-315">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-316">MBAM 回復サービス エンドポイント</span><span class="sxs-lookup"><span data-stu-id="41091-316">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="41091-317">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="41091-317">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-318">省略可能。</span><span class="sxs-lookup"><span data-stu-id="41091-318">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-319">MBAM 状態レポート サービス エンドポイント</span><span class="sxs-lookup"><span data-stu-id="41091-319">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="41091-320">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="41091-320">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-321">省略可能。</span><span class="sxs-lookup"><span data-stu-id="41091-321">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-322">暗号化方法 (既定: AES 128)</span><span class="sxs-lookup"><span data-stu-id="41091-322">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="41091-323">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="41091-323">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-324">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-324">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-325">データ ボリュームとエスクロー データ ボリュームの回復キーを暗号化する場合に指定する</span><span class="sxs-lookup"><span data-stu-id="41091-325">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="41091-326">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="41091-326">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-327">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-327">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-328">暗号化が完了するのを待つ場合に指定する</span><span class="sxs-lookup"><span data-stu-id="41091-328">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="41091-329">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="41091-329">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-330">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-331">展開スクリプトが一時停止された暗号化を再開しない</span><span class="sxs-lookup"><span data-stu-id="41091-331">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="41091-332">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="41091-332">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-333">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-334">TPM 所有者認証のエスクローエラーを無視するように指定します。</span><span class="sxs-lookup"><span data-stu-id="41091-334">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="41091-335">これは、TPM の自動プロビジョニングが有効になっている場合など、MBAM が TPM 所有者認証を読み取れないシナリオで使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-335">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="41091-336">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="41091-336">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-337">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-337">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-338">ボリューム回復キーのエスクローエラーを無視するように指定する</span><span class="sxs-lookup"><span data-stu-id="41091-338">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="41091-339">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="41091-339">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-340">スイッチ</span><span class="sxs-lookup"><span data-stu-id="41091-340">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="41091-341">状態報告の失敗を無視するように指定する</span><span class="sxs-lookup"><span data-stu-id="41091-341">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="41091-342">MBAM 2.5 以前を使用して BitLocker を展開の一部としてWindowsするには</span><span class="sxs-lookup"><span data-stu-id="41091-342">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="41091-343">MBAM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="41091-343">Install the MBAM Client.</span></span> <span data-ttu-id="41091-344">手順については、「コマンド ライン [を使用して MBAM クライアントを展開する方法」を参照してください](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="41091-344">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="41091-345">コンピューターをドメインに参加します (推奨)。</span><span class="sxs-lookup"><span data-stu-id="41091-345">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="41091-346">コンピューターがドメインに参加していない場合、回復パスワードは MBAM キー回復サービスに保存されません。</span><span class="sxs-lookup"><span data-stu-id="41091-346">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="41091-347">既定では、MBAM では、回復キーを格納できない限り、暗号化は許可されません。</span><span class="sxs-lookup"><span data-stu-id="41091-347">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="41091-348">回復キーが MBAM Server に保存される前にコンピューターが回復モードで開始した場合、回復方法は使用できません。コンピューターを再イメージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-348">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="41091-349">管理者としてコマンド プロンプトを開き、MBAM サービスを停止します。</span><span class="sxs-lookup"><span data-stu-id="41091-349">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="41091-350">次のコマンドを入力**して、サービス\*\*\*\*を手動**またはオンデマンドに設定します。</span><span class="sxs-lookup"><span data-stu-id="41091-350">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="41091-351">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="41091-351">net stop mbamagent</span></span>**

    **<span data-ttu-id="41091-352">sc config mbamagent start= demand</span><span class="sxs-lookup"><span data-stu-id="41091-352">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="41091-353">MBAM クライアントがグループ ポリシー設定を無視し、代わりに暗号化を設定して、Windows がクライアント コンピューターに展開される時刻を開始するようにレジストリ値を設定します。</span><span class="sxs-lookup"><span data-stu-id="41091-353">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    **<span data-ttu-id="41091-354">注意</span><span class="sxs-lookup"><span data-stu-id="41091-354">Caution</span></span>**  
    <span data-ttu-id="41091-355">この手順では、レジストリを変更する方法Windows説明します。</span><span class="sxs-lookup"><span data-stu-id="41091-355">This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="41091-356">レジストリ エディターを誤って使用すると、重大な問題が発生し、レジストリ エディターを再インストールする必要Windows。</span><span class="sxs-lookup"><span data-stu-id="41091-356">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="41091-357">レジストリ エディターの誤った使用に起因する問題を解決できる保証はありません。</span><span class="sxs-lookup"><span data-stu-id="41091-357">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="41091-358">レジストリ エディターは、ご自身のリスクで使用してください。</span><span class="sxs-lookup"><span data-stu-id="41091-358">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="41091-359">TPM for **オペレーティング**システムのみの暗号化を設定し、Regedit.exe を実行し、レジストリ キー テンプレートを C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg からインポートします。</span><span class="sxs-lookup"><span data-stu-id="41091-359">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="41091-360">このRegedit.exe HKLM\\SOFTWARE\\Microsoft\\MBAM に移動し、次の表に示す設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="41091-360">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        **<span data-ttu-id="41091-361">備考</span><span class="sxs-lookup"><span data-stu-id="41091-361">Note</span></span>**  
        <span data-ttu-id="41091-362">MBAM に関連するグループ ポリシー設定またはレジストリ値は、ここで設定できます。</span><span class="sxs-lookup"><span data-stu-id="41091-362">You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="41091-363">これらの設定は、以前に設定した値を上書きします。</span><span class="sxs-lookup"><span data-stu-id="41091-363">These settings will override previously set values.</span></span>

        <span data-ttu-id="41091-364">レジストリ エントリ構成の設定</span><span class="sxs-lookup"><span data-stu-id="41091-364">Registry entry Configuration settings</span></span>

        <span data-ttu-id="41091-365">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="41091-365">DeploymentTime</span></span>

        <span data-ttu-id="41091-366">0 = Off</span><span class="sxs-lookup"><span data-stu-id="41091-366">0 = Off</span></span>

        <span data-ttu-id="41091-367">1 = 展開時間ポリシー設定を使用する (既定) – この設定を使用して、クライアント コンピューターに展開Windows暗号化を有効にします。</span><span class="sxs-lookup"><span data-stu-id="41091-367">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="41091-368">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="41091-368">UseKeyRecoveryService</span></span>

        <span data-ttu-id="41091-369">0 = キーエスクローを使用しない (この場合、次の 2 つのレジストリ エントリは必要ありません)</span><span class="sxs-lookup"><span data-stu-id="41091-369">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="41091-370">1 = キー回復システムでキーエスクローを使用する (既定)</span><span class="sxs-lookup"><span data-stu-id="41091-370">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="41091-371">これは、MBAM が回復キーを格納できる推奨設定です。</span><span class="sxs-lookup"><span data-stu-id="41091-371">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="41091-372">コンピューターが MBAM キー回復サービスと通信できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="41091-372">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="41091-373">続行する前に、コンピューターがサービスと通信できると確認します。</span><span class="sxs-lookup"><span data-stu-id="41091-373">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="41091-374">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="41091-374">KeyRecoveryOptions</span></span>

        <span data-ttu-id="41091-375">0 = 回復キーのみをアップロードする</span><span class="sxs-lookup"><span data-stu-id="41091-375">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="41091-376">1 = Uploads Recovery Key and Key Recovery Package (既定値)</span><span class="sxs-lookup"><span data-stu-id="41091-376">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="41091-377">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="41091-377">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="41091-378">この値は、キー回復サービスを実行しているサーバーの URL (http:// コンピューター名 &lt; &gt; /MBAMRecoveryAndHardwareService/CoreService.svc など) に設定します。</span><span class="sxs-lookup"><span data-stu-id="41091-378">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="41091-379">MBAM クライアントは、MBAM クライアントの展開中にシステムを再起動します。</span><span class="sxs-lookup"><span data-stu-id="41091-379">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="41091-380">この再起動の準備ができたら、管理者としてコマンド プロンプトで次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="41091-380">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="41091-381">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="41091-381">net start mbamagent</span></span>**

7.  <span data-ttu-id="41091-382">コンピューターが再起動し、BIOS からメッセージが表示されたら、TPM の変更を受け入れる。</span><span class="sxs-lookup"><span data-stu-id="41091-382">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="41091-383">Windows クライアント オペレーティング システムイメージング プロセス中に、暗号化を開始する準備ができたら、管理者としてコマンド プロンプトを開き、次のコマンドを入力して開始を **[自動**] に設定し、MBAM クライアント エージェントを再起動します。</span><span class="sxs-lookup"><span data-stu-id="41091-383">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="41091-384">sc config mbamagent start= auto</span><span class="sxs-lookup"><span data-stu-id="41091-384">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="41091-385">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="41091-385">net start mbamagent</span></span>**

9.  <span data-ttu-id="41091-386">バイパス レジストリ値を削除するには、Regedit.exeを実行し、HKLM\\SOFTWARE\\Microsoft レジストリ エントリに移動します。</span><span class="sxs-lookup"><span data-stu-id="41091-386">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="41091-387">MBAM ノードを **右クリックし、[** 削除] を **クリックします**。</span><span class="sxs-lookup"><span data-stu-id="41091-387">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="41091-388">関連トピック</span><span class="sxs-lookup"><span data-stu-id="41091-388">Related topics</span></span>

[<span data-ttu-id="41091-389">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="41091-389">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="41091-390">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="41091-390">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a><span data-ttu-id="41091-391">MBAM の提案を受け取った場合</span><span class="sxs-lookup"><span data-stu-id="41091-391">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="41091-392">ここで提案を追加または投票 [します](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="41091-392">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="41091-393">MBAM の問題については [、MBAM TechNet フォーラムを使用します](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="41091-393">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
