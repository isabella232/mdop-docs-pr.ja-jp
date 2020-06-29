---
title: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
description: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826704"
---
# <span data-ttu-id="17f01-103">セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法</span><span class="sxs-lookup"><span data-stu-id="17f01-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="17f01-104">セルフサービスポータルは、IT 管理者が Microsoft BitLocker の管理と監視 (MBAM) 2.5 の展開の一部として構成した web サイトです。</span><span class="sxs-lookup"><span data-stu-id="17f01-104">The Self-Service Portal is a website that IT administrators configure as part of their Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 deployment.</span></span> <span data-ttu-id="17f01-105">この web サイトでは、エンドユーザーが Windows をロックした状態で、自分のコンピューターに個別にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="17f01-105">The website enables end users to independently regain access to their computers if they get locked out of Windows.</span></span> <span data-ttu-id="17f01-106">セルフサービスポータルでは、ヘルプデスクスタッフの支援は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="17f01-106">The Self-Service Portal requires no assistance from Help Desk staff.</span></span>

<span data-ttu-id="17f01-107">次の手順は、エンドユーザーの観点から記述されていますが、IT 管理者が理解している場合に役立つ可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17f01-107">The following instructions are written from the perspective of end users, but the information may be useful for IT administrators to understand.</span></span>

<span data-ttu-id="17f01-108">**重要** エンドユーザーは、セルフサービスポータルを使用してキーを回復するために、少なくとも1回は (リモートではなく) コンピューターに物理的にログオンしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f01-108">**Important** An end user must have physically logged on to the computer (not remotely) at least one time successfully to be able to recover their key using the Self-Service Portal.</span></span> <span data-ttu-id="17f01-109">それ以外の場合は、ヘルプデスクポータルを使用してキーの回復を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="17f01-109">Otherwise, they must use the Helpdesk Portal for key recovery.</span></span>

 

<span data-ttu-id="17f01-110">エンドユーザーが次の場合に、ロックアウトが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="17f01-110">End users may experience lockouts if they:</span></span>

-   <span data-ttu-id="17f01-111">パスワードまたは PIN を忘れた場合</span><span class="sxs-lookup"><span data-stu-id="17f01-111">Forget their password or PIN</span></span>

-   <span data-ttu-id="17f01-112">オペレーティングシステムのファイル、BIOS、またはトラステッドプラットフォームモジュール (TPM) を変更する</span><span class="sxs-lookup"><span data-stu-id="17f01-112">Change operating system files, the BIOS, or the Trusted Platform Module (TPM)</span></span>

<span data-ttu-id="17f01-113">**注** IT 管理者が IIS セッション状態のタイムアウトを構成した場合、タイムアウトの前に、セルフサービスポータルの60秒間にメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f01-113">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed in the Self-Service Portal 60 seconds prior to the time-out.</span></span>

 

**<span data-ttu-id="17f01-114">セルフサービスポータルを使用してコンピューターへのアクセスを回復するには</span><span class="sxs-lookup"><span data-stu-id="17f01-114">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="17f01-115">"**回復**キー id" フィールドに、コンピューターの [bitlocker 回復] 画面に表示される32桁の bitlocker キー ID のうち、最小値の8を入力します。</span><span class="sxs-lookup"><span data-stu-id="17f01-115">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span> <span data-ttu-id="17f01-116">最初の8桁の数字が複数のキーと一致する場合は、回復キー ID のすべての32桁を入力する必要があることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f01-116">If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

2.  <span data-ttu-id="17f01-117">[**理由**] フィールドで、回復キーの要求の理由を選択します。</span><span class="sxs-lookup"><span data-stu-id="17f01-117">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="17f01-118">[**キーの取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17f01-118">Click **Get Key**.</span></span> <span data-ttu-id="17f01-119">Bitlocker 回復キーが [ **Bitlocker 回復キー** ] フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="17f01-119">Your BitLocker recovery key is displayed in the **Your BitLocker Recovery Key** field.</span></span>

4.  <span data-ttu-id="17f01-120">コンピューターの [BitLocker 回復] 画面に48桁のコードを入力して、コンピューターへのアクセスを回復します。</span><span class="sxs-lookup"><span data-stu-id="17f01-120">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>



## <span data-ttu-id="17f01-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17f01-121">Related topics</span></span>


[<span data-ttu-id="17f01-122">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="17f01-122">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="17f01-123">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="17f01-123">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="17f01-124">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="17f01-124">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="17f01-125">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="17f01-125">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





