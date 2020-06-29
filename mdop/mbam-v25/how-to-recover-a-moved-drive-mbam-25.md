---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823344"
---
# <span data-ttu-id="48092-103">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="48092-103">How to Recover a Moved Drive</span></span>
<span data-ttu-id="48092-104">このトピックでは、管理と監視の Web サイト (ヘルプデスクとも呼ばれます) を使用して、Microsoft BitLocker の管理と監視 (MBAM) によって暗号化された後に移動したオペレーティングシステムドライブを回復する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48092-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to recover an operating system drive that was moved after being encrypted by Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="48092-105">ドライブが移動されると、トラステッドプラットフォームモジュール (TPM) チップが変更されたため、前のコンピューターで使用されていた PIN が受け入れられなくなります。</span><span class="sxs-lookup"><span data-stu-id="48092-105">When a drive is moved, it no longer accepts the PIN that was used in the previous computer because the Trusted Platform Module (TPM) chip has changed.</span></span> <span data-ttu-id="48092-106">移動したドライブを回復するには、回復キー ID を取得して回復パスワードを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48092-106">To recover the moved drive, you must obtain the recovery key ID to retrieve the recovery password.</span></span>

<span data-ttu-id="48092-107">移動したドライブを回復するには、管理と監視の Web サイトの [**ドライブの回復**] 領域を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48092-107">To recover a moved drive, you must use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="48092-108">[**ドライブ回復**] 領域にアクセスするには、Mbam ヘルプデスクユーザーロールまたは Mbam Advanced ヘルプデスクユーザーの役割が割り当てられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="48092-108">To access the **Drive Recovery** area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="48092-109">これらの役割の詳細については、「 [MBAM 2.5 のグループとアカウントの計画](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48092-109">For more information about these roles, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

**<span data-ttu-id="48092-110">移動したドライブを復元するには</span><span class="sxs-lookup"><span data-stu-id="48092-110">To recover a moved drive</span></span>**
1.  <span data-ttu-id="48092-111">移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードでコンピューターを起動するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="48092-111">On the computer that contains the moved drive, start the computer in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="48092-112">コンピューターが WinRE または DaRT で開始されると、MBAM は、移動されたオペレーティングシステムドライブを固定データドライブとして扱います。</span><span class="sxs-lookup"><span data-stu-id="48092-112">After the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a fixed data drive.</span></span> <span data-ttu-id="48092-113">その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="48092-113">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="48092-114">**注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックし、回復キー ID を表示するための回復モードを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="48092-114">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="48092-115">回復キー ID を使用して回復パスワードを取得し、管理と監視の Web サイトからドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="48092-115">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring Website.</span></span> <span data-ttu-id="48092-116">手順については、「[回復モードでドライブを回復する方法](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48092-116">For instructions, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md).</span></span>

    <span data-ttu-id="48092-117">移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="48092-117">If the moved drive was configured to use a TPM chip on the original computer, complete the following additional steps.</span></span> <span data-ttu-id="48092-118">それ以外の場合は、回復プロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="48092-118">Otherwise, the recovery process is complete.</span></span>

4.  <span data-ttu-id="48092-119">ドライブのロックを解除して開始プロセスを完了したら、WinRE モードでコマンドプロンプトを開き、コマンドを使って `manage-bde` ドライブの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="48092-119">After unlocking the drive and completing the start process, open a command prompt in WinRE mode and use the `manage-bde` command to decrypt the drive.</span></span> <span data-ttu-id="48092-120">このツールを使うのは、元の TPM チップがなくても TPM を PIN の保護機能に加えて削除する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="48092-120">Using this tool is the only way to remove the TPM plus the PIN protector without the original TPM chip.</span></span> <span data-ttu-id="48092-121">コマンドの詳細については `manage-bde` 、「[管理-bde](https://go.microsoft.com/fwlink/?LinkId=393567)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48092-121">For information about the `manage-bde` command, see [Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567).</span></span>

5.  <span data-ttu-id="48092-122">削除が完了したら、コンピューターを通常どおりに起動します。</span><span class="sxs-lookup"><span data-stu-id="48092-122">When the removal is completed, start the computer normally.</span></span> <span data-ttu-id="48092-123">MBAM agent は、このポリシーを適用して、新しいコンピューターの TPM プラス PIN を使ってドライブを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="48092-123">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus the PIN.</span></span>



## <span data-ttu-id="48092-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="48092-124">Related topics</span></span>


[<span data-ttu-id="48092-125">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="48092-125">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="48092-126">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="48092-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="48092-127">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="48092-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="48092-128">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="48092-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





