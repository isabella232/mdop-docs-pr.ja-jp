---
title: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
description: セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826077"
---
# <span data-ttu-id="c7f81-103">セルフサービス ポータルを使用してコンピューターへのアクセス権を再取得する方法</span><span class="sxs-lookup"><span data-stu-id="c7f81-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="c7f81-104">パスワードまたは PIN を忘れてしまったか、オペレーティングシステムファイルを変更したか、BIOS またはトラステッドプラットフォームモジュール (TPM) を変更したために、エンドユーザーが BitLocker によって Windows をロックアウトしている場合は、セルフサービスポータルを使用して、ヘルプデスクに支援を求めることなく、Windows にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c7f81-104">If end users get locked out of Windows by BitLocker because they forgot their password or PIN, or because they changed operating system files or changed the BIOS or the Trusted Platform Module (TPM), they can use the Self-Service Portal to regain access to Windows without having to ask their Help Desk for assistance.</span></span>

<span data-ttu-id="c7f81-105">**注** IT 管理者が IIS セッション状態のタイムアウトを構成した場合、タイムアウトの前に60秒間のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7f81-105">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed 60 seconds prior to the time-out.</span></span>

 

<span data-ttu-id="c7f81-106">**注** これらの手順は、エンドユーザーの観点から記述されます。</span><span class="sxs-lookup"><span data-stu-id="c7f81-106">**Note** These instructions are written for and from the perspective of end users.</span></span>

 

**<span data-ttu-id="c7f81-107">セルフサービスポータルを使用してコンピューターへのアクセスを回復するには</span><span class="sxs-lookup"><span data-stu-id="c7f81-107">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="c7f81-108">"**回復**キー id" フィールドに、コンピューターの [bitlocker 回復] 画面に表示される32桁の bitlocker キー ID のうち、最小値の8を入力します。</span><span class="sxs-lookup"><span data-stu-id="c7f81-108">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span>

    <span data-ttu-id="c7f81-109">**注** 最初の8桁の数字が複数のキーと一致する場合は、回復キー ID のすべての32桁を入力する必要があることを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7f81-109">**Note** If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

     

2.  <span data-ttu-id="c7f81-110">[**理由**] フィールドで、回復キーの要求の理由を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7f81-110">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="c7f81-111">[**キーの取得**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7f81-111">Click **Get Key**.</span></span> <span data-ttu-id="c7f81-112">BitLocker 回復キーが "BitLocker 回復キー" フィールドに表示されます。</span><span class="sxs-lookup"><span data-stu-id="c7f81-112">Your BitLocker recovery key is displayed in the “Your BitLocker Recovery Key” field.</span></span>

4.  <span data-ttu-id="c7f81-113">コンピューターの [BitLocker 回復] 画面に48桁のコードを入力して、コンピューターへのアクセスを回復します。</span><span class="sxs-lookup"><span data-stu-id="c7f81-113">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>

## <span data-ttu-id="c7f81-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7f81-114">Related topics</span></span>


[<span data-ttu-id="c7f81-115">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="c7f81-115">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





