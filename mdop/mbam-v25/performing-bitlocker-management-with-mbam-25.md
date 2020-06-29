---
title: MBAM 2.5 での BitLocker 管理の実行
description: MBAM 2.5 での BitLocker 管理の実行
author: dansimp
ms.assetid: 068f3ee0-300c-4083-ba18-7065eef997ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a0ee5802f945176914c56659e0ff7e34e93a969
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826007"
---
# <span data-ttu-id="01fcd-103">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="01fcd-103">Performing BitLocker Management with MBAM 2.5</span></span>


<span data-ttu-id="01fcd-104">Microsoft BitLocker の管理と監視 (MBAM) を計画して展開すると、それを構成して使用して、組織全体の BitLocker ドライブ暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-104">After planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker Drive Encryption across your enterprise.</span></span> <span data-ttu-id="01fcd-105">このセクションの情報は、Microsoft BitLocker の管理と監視を使用して実行される、インストール後の、日常的に行われる BitLocker 暗号化管理タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="01fcd-105">The information in this section describes post-installation, day-to-day BitLocker encryption management tasks that are accomplished by using Microsoft BitLocker Administration and Monitoring.</span></span>

## <span data-ttu-id="01fcd-106">TPM ロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="01fcd-106">Reset a TPM lockout</span></span>


<span data-ttu-id="01fcd-107">トラステッドプラットフォームモジュール (TPM) は、主に暗号化キーを含む基本的なセキュリティ関連の関数を提供するために設計されたマイクロチップです。</span><span class="sxs-lookup"><span data-stu-id="01fcd-107">A Trusted Platform Module (TPM) is a microchip that is designed to provide basic security-related functions, primarily involving encryption keys.</span></span> <span data-ttu-id="01fcd-108">通常、TPM はコンピューターのマザーボードにインストールされ、ホストバスアダプターを使ってシステムの残りの部分と通信します。</span><span class="sxs-lookup"><span data-stu-id="01fcd-108">The TPM is usually installed on the motherboard of a computer, and it communicates with the rest of the system by using a host bus adapter.</span></span> <span data-ttu-id="01fcd-109">TPM が搭載されているコンピューターでは、暗号化キーを作成して暗号化することで、TPM だけが暗号化解除されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-109">On computers that incorporate a TPM, you can create cryptographic keys and encrypt them so that they can be decrypted only by the TPM.</span></span>

<span data-ttu-id="01fcd-110">TPM ロックアウトは、ユーザーが誤った PIN を入力した回数が何度も超えた場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="01fcd-110">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="01fcd-111">TPM ロックの前に、ユーザーが不正な PIN を入力できる回数は、製造元によって異なります。</span><span class="sxs-lookup"><span data-stu-id="01fcd-111">The number of times that a user can enter an incorrect PIN before the TPM locks varies by manufacturer.</span></span> <span data-ttu-id="01fcd-112">MBAM を使用して、管理と監視の Web サイトで一元キーの回復データシステムにアクセスすることができます。ここでは、コンピューター ID と関連付けられているユーザー識別子を指定すると、TPM 所有者パスワードファイルを取得できます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-112">You can use MBAM to access the centralized key recovery data system on the Administration and Monitoring Website, where you can retrieve a TPM owner password file when you supply a computer ID and an associated user identifier.</span></span>

[<span data-ttu-id="01fcd-113">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-113">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-25.md)

## <span data-ttu-id="01fcd-114">ドライブを回復する</span><span class="sxs-lookup"><span data-stu-id="01fcd-114">Recover drives</span></span>


<span data-ttu-id="01fcd-115">データの暗号化を処理している場合、特にエンタープライズ環境では、ハードウェア障害が発生した場合や、社員の変更があった場合、または暗号化キーを紛失した場合に、データをどのように回復できるかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="01fcd-115">When you are dealing with the encryption of data, especially in an enterprise environment, consider how that data can be recovered in the event of a hardware failure, changes in personnel, or other situations in which encryption keys can be lost.</span></span>

<span data-ttu-id="01fcd-116">MBAM の暗号化されたドライブ回復機能を使用すると、データをキャプチャして保存できます。また、BitLocker が回復モードに移行したとき、または破損したときに、必要なツールを使用して BitLocker で保護されたボリュームにアクセスすることができます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-116">The encrypted drive recovery features in MBAM ensure that data can be captured and stored and that the required tools are available to access a BitLocker-protected volume when BitLocker goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="01fcd-117">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-117">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)

[<span data-ttu-id="01fcd-118">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-118">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-25.md)

[<span data-ttu-id="01fcd-119">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-119">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-25.md)

## <span data-ttu-id="01fcd-120">紛失したコンピューターの BitLocker 暗号化の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="01fcd-120">Determine BitLocker encryption state of lost computers</span></span>


<span data-ttu-id="01fcd-121">MBAM を使用することで、紛失または盗難したコンピューターの最後の既知の BitLocker 暗号化の状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-121">By using MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="01fcd-122">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-122">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)

## <span data-ttu-id="01fcd-123">セルフサービスポータルを使用してコンピューターへのアクセスを回復する</span><span class="sxs-lookup"><span data-stu-id="01fcd-123">Use the Self-Service Portal to regain access to a computer</span></span>


<span data-ttu-id="01fcd-124">エンドユーザーが BitLocker によって Windows のロックを解除した場合は、このセクションの手順を使用して、そのコンピューターにアクセスするための BitLocker 回復キーを取得することができます。</span><span class="sxs-lookup"><span data-stu-id="01fcd-124">If end users get locked out of Windows by BitLocker, they can use the instructions in this section to get a BitLocker recovery key to regain access to their computer.</span></span>

[<span data-ttu-id="01fcd-125">セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法</span><span class="sxs-lookup"><span data-stu-id="01fcd-125">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>](how-to-use-the-self-service-portal-to-regain-access-to-a-computer-mbam-25.md)



## <span data-ttu-id="01fcd-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="01fcd-126">Related topics</span></span>


[<span data-ttu-id="01fcd-127">MBAM 2.5 の操作</span><span class="sxs-lookup"><span data-stu-id="01fcd-127">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

 

## <span data-ttu-id="01fcd-128">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="01fcd-128">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="01fcd-129">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="01fcd-129">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="01fcd-130">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="01fcd-130">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





