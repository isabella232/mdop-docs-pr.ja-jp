---
title: MBAM での BitLocker 管理の実行
description: MBAM での BitLocker 管理の実行
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826497"
---
# <span data-ttu-id="16aac-103">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="16aac-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="16aac-104">Microsoft BitLocker の管理と監視 (MBAM) を計画して展開すると、それを構成して使用し、エンタープライズ BitLocker 暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="16aac-104">After planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="16aac-105">このセクションの情報は、Microsoft BitLocker の管理と監視を使用して実行される、インストール後の日常的な BitLocker 暗号化管理タスクについて説明しています。</span><span class="sxs-lookup"><span data-stu-id="16aac-105">The information in this section describes post-installation day-to-day BitLocker encryption management tasks that are accomplished by using Microsoft BitLocker Administration and Monitoring.</span></span>

## <span data-ttu-id="16aac-106">MBAM を使用して TPM ロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="16aac-106">Reset a TPM Lockout by Using MBAM</span></span>


<span data-ttu-id="16aac-107">トラステッドプラットフォームモジュール (TPM) は、主に暗号化キーを含む基本的なセキュリティ関連の関数を提供するために設計されたマイクロチップです。</span><span class="sxs-lookup"><span data-stu-id="16aac-107">A Trusted Platform Module (TPM) is a microchip that is designed to provide basic security-related functions, primarily involving encryption keys.</span></span> <span data-ttu-id="16aac-108">通常、TPM はコンピューターまたはノート pc のマザーボードにインストールされ、ハードウェアバスを使ってシステムの残りの部分と通信します。</span><span class="sxs-lookup"><span data-stu-id="16aac-108">The TPM is usually installed on the motherboard of a computer or laptop, and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="16aac-109">TPM が搭載されているコンピューターには、TPM のみが解読できるように、暗号化キーを作成して暗号化する機能があります。</span><span class="sxs-lookup"><span data-stu-id="16aac-109">Computers that incorporate a TPM have the ability to create cryptographic keys and encrypt them so that they can be decrypted only by the TPM.</span></span>

<span data-ttu-id="16aac-110">TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="16aac-110">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="16aac-111">TPM のロックが発生する前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="16aac-111">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="16aac-112">MBAM を使用して、管理と監視の web サイトで中央キー回復データシステムにアクセスできます。ここでは、コンピューター ID と関連付けられたユーザー識別子を指定すると、TPM 所有者パスワードファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="16aac-112">You can use MBAM to access the centralized Key Recovery data system in the Administration and Monitoring website, where you can retrieve a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

[<span data-ttu-id="16aac-113">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="16aac-113">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

## <span data-ttu-id="16aac-114">MBAM でドライブを回復する</span><span class="sxs-lookup"><span data-stu-id="16aac-114">Recover Drives with MBAM</span></span>


<span data-ttu-id="16aac-115">データの暗号化を処理している場合、特にエンタープライズ環境では、ハードウェア障害が発生した場合や、社員の変更があった場合、または暗号化キーを紛失した場合に、データをどのように回復できるかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="16aac-115">When you are dealing with the encryption of data, especially in an enterprise environment, consider how that data can be recovered in the event of a hardware failure, changes in personnel, or other situations in which encryption keys can be lost.</span></span>

<span data-ttu-id="16aac-116">MBAM の暗号化ドライブ回復機能を使用すると、データをキャプチャして保存できます。また、BitLocker が回復モードに移行したとき、または破損したときに、必要なツールを使用して BitLocker で保護されたボリュームにアクセスできるようになります。</span><span class="sxs-lookup"><span data-stu-id="16aac-116">The encrypted drive recovery features of MBAM ensure that data can be captured and stored and that the required tools are available to access a BitLocker-protected volume when BitLocker goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="16aac-117">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="16aac-117">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[<span data-ttu-id="16aac-118">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="16aac-118">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

[<span data-ttu-id="16aac-119">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="16aac-119">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

## <span data-ttu-id="16aac-120">MBAM を使用して紛失したコンピューターの BitLocker 暗号化の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="16aac-120">Determine BitLocker Encryption State of Lost Computers by Using MBAM</span></span>


<span data-ttu-id="16aac-121">MBAM を使用して、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を判断できます。</span><span class="sxs-lookup"><span data-stu-id="16aac-121">Using MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="16aac-122">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="16aac-122">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## <span data-ttu-id="16aac-123">セルフサービスポータルを使用してコンピューターへのアクセスを回復する</span><span class="sxs-lookup"><span data-stu-id="16aac-123">Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="16aac-124">エンドユーザーが BitLocker によって Windows のロックを解除した場合は、このセクションの手順を使用して、そのコンピューターにアクセスするための BitLocker 回復キーを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="16aac-124">If end users get locked out of Windows by BitLocker, they can use the instructions in this section to get a BitLocker recovery key to regain access to their computer.</span></span>

[<span data-ttu-id="16aac-125">セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法</span><span class="sxs-lookup"><span data-stu-id="16aac-125">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## <span data-ttu-id="16aac-126">MBAM での BitLocker 管理を実行するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="16aac-126">Other Resources for Performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="16aac-127">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="16aac-127">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





