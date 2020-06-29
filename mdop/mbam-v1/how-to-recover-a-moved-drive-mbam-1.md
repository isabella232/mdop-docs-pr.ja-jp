---
title: 移動されたドライブを回復する方法
description: 移動されたドライブを回復する方法
author: dansimp
ms.assetid: 0c7199d8-9463-4f44-9af3-b70eceeaff1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e73e0878a3102d56494feb33efa69182029988c2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812930"
---
# <span data-ttu-id="a16bd-103">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="a16bd-103">How to Recover a Moved Drive</span></span>


<span data-ttu-id="a16bd-104">Microsoft BitLocker の管理と監視 (MBAM) を使って以前に暗号化されたオペレーティングシステムドライブを移動する場合は、特定の問題を解決する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16bd-104">When you move an operating system drive that has been previously encrypted by using Microsoft BitLocker Administration and Monitoring (MBAM), you must resolve certain issues.</span></span> <span data-ttu-id="a16bd-105">PIN が新しいコンピューターに接続された後、ドライブは、前のコンピューターで使用されていたスタートアップ PIN を受け入れません。</span><span class="sxs-lookup"><span data-stu-id="a16bd-105">After a PIN is attached to the new computer, the drive will not accept the start-up PIN that was used in previous computer.</span></span> <span data-ttu-id="a16bd-106">トラステッドプラットフォームモジュール (TPM) チップに変更があったため、PIN は無効とみなされます。</span><span class="sxs-lookup"><span data-stu-id="a16bd-106">The system considers the PIN to be invalid because of the change to the Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="a16bd-107">移動したドライブを使用するには、回復キー ID を取得して回復パスワードを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16bd-107">You must obtain a recovery key ID to retrieve the recovery password in order to use the moved drive.</span></span> <span data-ttu-id="a16bd-108">この操作を行うには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-108">To do this, use the following procedure.</span></span>

**<span data-ttu-id="a16bd-109">移動したドライブを復元するには</span><span class="sxs-lookup"><span data-stu-id="a16bd-109">To recover a moved drive</span></span>**

1.  <span data-ttu-id="a16bd-110">移動したドライブが含まれているコンピューターで、Windows 回復環境 (WinRE) モードを開始するか、Microsoft 診断/回復ツールセット (DaRT) を使用してコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-110">On the computer that contains the moved drive, start in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="a16bd-111">コンピューターが WinRE または DaRT で開始されると、MBAM は、移動されたオペレーティングシステムドライブをデータドライブとして扱います。</span><span class="sxs-lookup"><span data-stu-id="a16bd-111">Once the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a data drive.</span></span> <span data-ttu-id="a16bd-112">その後、MBAM はドライブの回復パスワード ID を表示し、回復パスワードを要求します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-112">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="a16bd-113">**注** 場合によっては、[スタートアッププロセス中に**PIN を忘れ**た場合] をクリックして回復モードに入ることができます。</span><span class="sxs-lookup"><span data-stu-id="a16bd-113">**Note** In some cases, you might be able to click **I forget the PIN** during the startup process to enter the recovery mode.</span></span> <span data-ttu-id="a16bd-114">これにより、回復キー ID も表示されます。</span><span class="sxs-lookup"><span data-stu-id="a16bd-114">This also displays the recovery key ID.</span></span>

     

3.  <span data-ttu-id="a16bd-115">MBAM 管理 web サイトで、回復キー ID を使用して回復パスワードを取得し、ドライブのロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-115">On the MBAM administration website, use the recovery key ID to retrieve the recovery password and unlock the drive.</span></span>

4.  <span data-ttu-id="a16bd-116">移動したドライブが元のコンピューター上の TPM チップを使用するように構成されている場合は、ドライブのロックを解除し、開始プロセスを完了した後に、追加の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a16bd-116">If the moved drive was configured to use a TPM chip on the original computer, you must take additional steps after you unlock the drive and complete the start process.</span></span> <span data-ttu-id="a16bd-117">WinRE モードでは、コマンドプロンプトを開き、 **manage-bde**ツールを使ってドライブの暗号化を解除します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-117">In WinRE mode, open a command prompt and use the **manage-bde** tool to decrypt the drive.</span></span> <span data-ttu-id="a16bd-118">このツールを使用するのは、元の TPM チップがなくても TPM と PIN の保護を削除する唯一の方法です。</span><span class="sxs-lookup"><span data-stu-id="a16bd-118">The use of this tool is the only way to remove the TPM-plus-PIN protection without the original TPM chip.</span></span>

5.  <span data-ttu-id="a16bd-119">削除が完了したら、システムを通常どおりに起動します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-119">After the removal is complete, start the system normally.</span></span> <span data-ttu-id="a16bd-120">MBAM agent は、新しいコンピューターの TPM plus PIN を使ってドライブを暗号化するポリシーを適用します。</span><span class="sxs-lookup"><span data-stu-id="a16bd-120">The MBAM agent will proceed to enforce the policy to encrypt the drive with the new computer’s TPM plus PIN.</span></span>

## <span data-ttu-id="a16bd-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a16bd-121">Related topics</span></span>


[<span data-ttu-id="a16bd-122">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="a16bd-122">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)

 

 





