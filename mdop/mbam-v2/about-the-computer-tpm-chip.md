---
title: コンピューターの TPM チップについて
description: コンピューターの TPM チップについて
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823534"
---
# <span data-ttu-id="b2b9e-103">コンピューターの TPM チップについて</span><span class="sxs-lookup"><span data-stu-id="b2b9e-103">About the Computer TPM Chip</span></span>


<span data-ttu-id="b2b9e-104">BitLocker は、トラステッドプラットフォームモジュール (TPM) チップで使用する場合に追加の保護を提供します。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-104">BitLocker provides additional protection when it is used with a Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="b2b9e-105">TPM チップは、コンピューターの製造元によって多くの新しいコンピューターにインストールされるハードウェアコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-105">The TPM chip is a hardware component that is installed in many newer computers by the computer manufacturers.</span></span> <span data-ttu-id="b2b9e-106">Microsoft BitLocker の管理と監視 (MBAM) では、TPM チップに加えて BitLocker を使用して、データの保護を強化し、コンピューターが改ざんされていないことを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-106">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker, in addition to the TPM chip, to help provide additional protection of your data and to make sure that your computer has not been tampered with.</span></span>

## <span data-ttu-id="b2b9e-107">TPM のセットアップ方法</span><span class="sxs-lookup"><span data-stu-id="b2b9e-107">How to Set Up Your TPM</span></span>


<span data-ttu-id="b2b9e-108">使用しているコンピューターで BitLocker ドライブ暗号化ウィザードを起動すると、TPM が TPM チップを使用するように BitLocker を構成している場合、BitLocker は TPM チップをチェックします。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-108">When you start the BitLocker Drive Encryption wizard on your computer, BitLocker checks for a TPM chip if your organization has configured BitLocker to use a TPM chip.</span></span> <span data-ttu-id="b2b9e-109">BitLocker で互換性のある TPM チップが検出された場合は、TPM チップを使用できるようにするために、コンピューターの再起動を求めるメッセージが表示されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-109">If BitLocker finds a compatible TPM chip, you may be prompted to restart your computer to enable the TPM chip for use.</span></span> <span data-ttu-id="b2b9e-110">コンピューターが再起動したら、次の手順に従って、BIOS で TPM チップを構成します (BIOS は、コンピュータソフトウェアの Windows の以前のレイヤーです)。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-110">As soon as your computer has restarted, follow the instructions to configure the TPM chip in the BIOS (the BIOS is a pre-Windows layer of your computer software).</span></span>

<span data-ttu-id="b2b9e-111">BitLocker を構成した後、Windows の [コントロールパネル] の [BitLocker 暗号化オプション] ツールを開いて、[ **Tpm 管理**] を選択することにより、tpm チップに関するその他の情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-111">After BitLocker is configured, you can access additional information about the TPM chip by opening the BitLocker Encryption Options tool in the Windows Control Panel, and then selecting **TPM Administration**.</span></span>

<span data-ttu-id="b2b9e-112">**注** このツールにアクセスするには、コンピューターの管理者資格情報を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-112">**Note** You must have administrative credentials on your computer to access this tool.</span></span>

 

<span data-ttu-id="b2b9e-113">TPM のエラー、BIOS の変更、または特定の Windows の更新プログラムでは、BitLocker によってコンピューターがロックされ、ロック解除するためにヘルプデスクに連絡する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-113">In a TPM failure, a change in the BIOS, or certain Windows Updates, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="b2b9e-114">使用しているコンピューターの名前とコンピューターのドメインを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-114">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="b2b9e-115">ヘルプデスクでは、コンピューターのロックを解除するために使用できるパスワードファイルを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-115">Help Desk can give you a password file that can be used to unlock your computer.</span></span>

## <span data-ttu-id="b2b9e-116">TPM の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="b2b9e-116">Troubleshooting TPM Issues</span></span>


<span data-ttu-id="b2b9e-117">TPM のエラー、BIOS の変更、特定の Windows 更新が発生した場合、BitLocker はコンピューターをロックし、ヘルプデスクに連絡してロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-117">If a TPM failure, change in the BIOS, or certain Windows Updates occur, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="b2b9e-118">使用しているコンピューターの名前とコンピューターのドメインを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-118">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="b2b9e-119">ヘルプデスクでは、コンピューターのロックを解除するために使用できるパスワードファイルを提供できます。</span><span class="sxs-lookup"><span data-stu-id="b2b9e-119">The Help Desk can give you a password file that you can use to unlock your computer.</span></span>

## <span data-ttu-id="b2b9e-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b2b9e-120">Related topics</span></span>


[<span data-ttu-id="b2b9e-121">エンド ユーザーが BitLocker を管理するための支援</span><span class="sxs-lookup"><span data-stu-id="b2b9e-121">Helping End Users Manage BitLocker</span></span>](helping-end-users-manage-bitlocker.md)

[<span data-ttu-id="b2b9e-122">PIN またはパスワードの使用</span><span class="sxs-lookup"><span data-stu-id="b2b9e-122">Using Your PIN or Password</span></span>](using-your-pin-or-password.md)

 

 





