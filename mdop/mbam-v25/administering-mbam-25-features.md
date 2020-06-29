---
title: MBAM 2.5 機能の管理
description: MBAM 2.5 機能の管理
author: dansimp
ms.assetid: ca15f818-cf07-4437-8ffa-425af603a3c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a365442c11479563d43159e6ef9859c252ce28b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824197"
---
# <span data-ttu-id="7fe32-103">MBAM 2.5 機能の管理</span><span class="sxs-lookup"><span data-stu-id="7fe32-103">Administering MBAM 2.5 Features</span></span>


<span data-ttu-id="7fe32-104">必要な計画をすべて完了して、Microsoft BitLocker の管理と監視 (MBAM) を展開した後、このセクションの情報で、インストール後の日常的な Microsoft BitLocker の管理と監視の操作タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="7fe32-104">After completing all necessary planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker encryption across the enterprise The information in this section describes post-installation day-to-day Microsoft BitLocker Administration and Monitoring feature operations tasks.</span></span>

## <span data-ttu-id="7fe32-105">BitLocker 暗号化の除外を管理する</span><span class="sxs-lookup"><span data-stu-id="7fe32-105">Manage BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="7fe32-106">MBAM は、必要のない、またはドライブを暗号化する必要がある特定のユーザーに対して、暗号化の除外を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="7fe32-106">MBAM lets you grant encryption exemptions to specific users who do not need or want their drives encrypted.</span></span> <span data-ttu-id="7fe32-107">通常、コンピューターの除外は、開発やテストで使用されているコンピューター、または BitLocker をサポートしていない古いコンピューターなど、会社が暗号化する必要がないコンピューターを持っている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="7fe32-107">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="7fe32-108">場合によっては、特定のコンピューターが暗号化されていないことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="7fe32-108">In some cases, local law may also require that certain computers are not encrypted.</span></span>

[<span data-ttu-id="7fe32-109">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="7fe32-109">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)

## <span data-ttu-id="7fe32-110">コントロールパネルの BitLocker 暗号化オプションと BitLocker ドライブ暗号化項目について</span><span class="sxs-lookup"><span data-stu-id="7fe32-110">Understand the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>


<span data-ttu-id="7fe32-111">MBAM は、[**システムとセキュリティ**] の下に表示される、[BitLocker 暗号化オプション] というカスタムコントロールパネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="7fe32-111">MBAM provides a custom control panel, called BitLocker Encryption Options, that appears under **System and Security**.</span></span> <span data-ttu-id="7fe32-112">MBAM コントロールパネルを使用すると、暗号化された固定ドライブとリムーバブルドライブのロックを解除し、PIN またはパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="7fe32-112">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span>

<span data-ttu-id="7fe32-113">**注** このカスタマイズされたコントロールパネルは、既定の Windows BitLocker コントロールパネルに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="7fe32-113">**Note** This customized control panel does not replace the default Windows BitLocker control panel.</span></span>

 

[<span data-ttu-id="7fe32-114">コントロール パネルの [BitLocker 暗号化のオプション] 項目と [BitLocker ドライブ暗号化] 項目について</span><span class="sxs-lookup"><span data-stu-id="7fe32-114">Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

## <span data-ttu-id="7fe32-115">MBAM 機能の管理に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="7fe32-115">Other Resources for Administering MBAM Features</span></span>


[<span data-ttu-id="7fe32-116">MBAM 2.5 の操作</span><span class="sxs-lookup"><span data-stu-id="7fe32-116">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

## <span data-ttu-id="7fe32-117">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="7fe32-117">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="7fe32-118">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="7fe32-118">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="7fe32-119">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="7fe32-119">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





