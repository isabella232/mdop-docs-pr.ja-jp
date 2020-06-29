---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 697cd78d-962c-411e-901a-2e9220ba6552
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bd0d43f2eea95fe71225a50e7fa68d4fb1c35485
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825064"
---
# <span data-ttu-id="55846-103">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="55846-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="55846-104">Microsoft BitLocker の管理と監視 (MBAM) を使用して暗号化されたオペレーティングシステムドライブを移動すると、トラステッドプラットフォームモジュール (TPM) チップの変更のために、以前のコンピューターで使用されていた PIN がドライブで受け入れられなくなります。</span><span class="sxs-lookup"><span data-stu-id="55846-104">When you move an operating system drive that is encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), the drive will not accept the PIN that was used in a previous computer because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="55846-105">移動したドライブを使用するには、回復キー ID を取得して回復パスワードを取得する方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="55846-105">To use the moved drive, you will need a way to obtain the recovery key ID to retrieve the recovery password.</span></span> <span data-ttu-id="55846-106">次の手順を使用して、移動したドライブを回復します。</span><span class="sxs-lookup"><span data-stu-id="55846-106">Use the following procedure to recover a drive that has moved.</span></span>

**<span data-ttu-id="55846-107">移動したドライブを復元するには</span><span class="sxs-lookup"><span data-stu-id="55846-107">To recover a moved drive</span></span>**

1.  <span data-ttu-id="55846-108">移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードでコンピューターを起動するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="55846-108">On the computer that contains the moved drive, start the computer in Windows recovery environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="55846-109">コンピューターが WinRE または DaRT で開始されると、Microsoft BitLocker の管理と監視は、移動されたオペレーティングシステムドライブをデータドライブとして扱います。</span><span class="sxs-lookup"><span data-stu-id="55846-109">Once the computer has been started with WinRE or DaRT, Microsoft BitLocker Administration and Monitoring will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="55846-110">その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="55846-110">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="55846-111">**注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックし、回復キー ID を表示するための回復モードを入力することができます。</span><span class="sxs-lookup"><span data-stu-id="55846-111">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="55846-112">回復キー ID を使用して回復パスワードを取得し、管理と監視の web サイトからドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="55846-112">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="55846-113">移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、ドライブのロックを解除し、開始プロセスを完了した後に、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55846-113">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after unlocking the drive and completing the start process.</span></span> <span data-ttu-id="55846-114">WinRE モードでは、コマンドプロンプトを開き、 **manage-bde**ツールを使ってドライブの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="55846-114">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="55846-115">このツールを使うのは、元の TPM チップがなくても TPM と PIN の保護機能を削除する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="55846-115">Using this tool is the only way to remove the TPM plus PIN protector without the original TPM chip.</span></span>

5.  <span data-ttu-id="55846-116">削除が完了したら、コンピューターを通常どおりに起動します。</span><span class="sxs-lookup"><span data-stu-id="55846-116">Once the removal is completed, start the computer normally.</span></span> <span data-ttu-id="55846-117">MBAM agent は、新しいコンピューターの TPM plus PIN を使ってドライブを暗号化するポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="55846-117">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="55846-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55846-118">Related topics</span></span>


[<span data-ttu-id="55846-119">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="55846-119">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





