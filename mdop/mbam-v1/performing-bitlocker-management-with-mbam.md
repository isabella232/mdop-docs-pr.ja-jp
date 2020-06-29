---
title: MBAM での BitLocker 管理の実行
description: MBAM での BitLocker 管理の実行
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825894"
---
# <span data-ttu-id="43f80-103">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="43f80-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="43f80-104">Microsoft BitLocker の管理と監視 (MBAM) を展開した後、MBAM を構成して使用し、エンタープライズ BitLocker 暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="43f80-104">After you deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="43f80-105">このセクションでは、インストール後に、MBAM を使って実行できる日常的な BitLocker 暗号化管理タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="43f80-105">This section describes post-installation, day-to-day BitLocker encryption management tasks that can be accomplished by using MBAM.</span></span>

## <span data-ttu-id="43f80-106">MBAM で TPM ロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="43f80-106">Reset a TPM Lockout with MBAM</span></span>


<span data-ttu-id="43f80-107">トラステッドプラットフォームモジュール (TPM) マイクロチップは、基本的なセキュリティ関連の機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="43f80-107">A Trusted Platform Module (TPM) microchip provides basic security-related functions.</span></span> <span data-ttu-id="43f80-108">これらの関数は主に、暗号化キーの使用によって実現されます。</span><span class="sxs-lookup"><span data-stu-id="43f80-108">These functions are accomplished primarily by the use of encryption keys.</span></span> <span data-ttu-id="43f80-109">通常、TPM はコンピューターまたはノート pc のマザーボードにインストールされ、ハードウェアバスを使ってシステムの残りの部分と通信します。</span><span class="sxs-lookup"><span data-stu-id="43f80-109">The TPM is typically installed on the motherboard of a computer or laptop and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="43f80-110">TPM が搭載されているコンピューターでは、TPM のみが解読できる暗号化キーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="43f80-110">Computers that incorporate a TPM can create cryptographic keys that can be decrypted only by the TPM.</span></span> <span data-ttu-id="43f80-111">TPM ロックアウトは、ユーザーが誤った PIN を何度も入力した場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="43f80-111">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="43f80-112">TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="43f80-112">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="43f80-113">MBAM 管理 web サイトのキー回復データシステムでは、TPM 所有者パスワードのリセットファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="43f80-113">The Key Recovery data system on the MBAM administration website enables you to obtain a reset TPM owner password file.</span></span>

[<span data-ttu-id="43f80-114">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="43f80-114">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-1.md)

## <span data-ttu-id="43f80-115">MBAM でドライブを回復する</span><span class="sxs-lookup"><span data-stu-id="43f80-115">Recover drives with MBAM</span></span>


<span data-ttu-id="43f80-116">ハードウェア障害が発生した場合や、ユーザーが変更した場合、または暗号化キーが失われた場合は、暗号化されたドライブからデータを回復する方法を理解していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="43f80-116">Make sure that you know how to attempt data recovery from encrypted drives in the event of hardware failure, changes in personnel, or other situations in which encryption keys are lost.</span></span> <span data-ttu-id="43f80-117">MBAM の暗号化されたドライブ回復機能は、ボリュームが回復モードになったとき、または破損したときに、BitLocker で保護されたボリュームにアクセスするために必要なデータと可用性のキャプチャと記憶域を提供します。</span><span class="sxs-lookup"><span data-stu-id="43f80-117">The Encrypted Drive Recovery features of MBAM provide the capture and storage of data and availability of tools required to access a BitLocker-protected volume when the volume goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="43f80-118">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="43f80-118">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[<span data-ttu-id="43f80-119">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="43f80-119">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-1.md)

[<span data-ttu-id="43f80-120">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="43f80-120">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-1.md)

## <span data-ttu-id="43f80-121">MBAM を使用して紛失したコンピューターの BitLocker 暗号化の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="43f80-121">Determine BitLocker Encryption State of lost computers by Using MBAM</span></span>


<span data-ttu-id="43f80-122">MBAM を使用する場合は、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="43f80-122">When you use MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="43f80-123">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="43f80-123">How to Determine the BitLocker Encryption State of a Lost Computers</span></span>](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## <span data-ttu-id="43f80-124">MBAM での BitLocker 管理を実行するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="43f80-124">Other resources for performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="43f80-125">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="43f80-125">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





