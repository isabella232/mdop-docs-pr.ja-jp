---
title: MBAM 2.0 機能の管理
description: MBAM 2.0 機能の管理
author: dansimp
ms.assetid: 065e0704-069e-4372-9b86-0b57dd7638dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35bb855e185ad8e3fa6880853938074cf6185a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823507"
---
# <span data-ttu-id="87292-103">MBAM 2.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="87292-103">Administering MBAM 2.0 Features</span></span>


<span data-ttu-id="87292-104">必要な計画をすべて完了して、Microsoft BitLocker の管理と監視 (MBAM) を展開した後、このセクションの情報で、インストール後の日常的な Microsoft BitLocker の管理と監視の操作タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="87292-104">After completing all necessary planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker encryption across the enterprise The information in this section describes post-installation day-to-day Microsoft BitLocker Administration and Monitoring feature operations tasks.</span></span>

## <span data-ttu-id="87292-105">MBAM 管理者の役割を管理する</span><span class="sxs-lookup"><span data-stu-id="87292-105">Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="87292-106">すべてのサーバー機能について MBAM セットアップが完了したら、管理者はそのユーザーへのアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87292-106">After MBAM Setup is complete for all server features, administrative users have to be granted access to them.</span></span> <span data-ttu-id="87292-107">ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory ドメインサービスのセキュリティグループに割り当てる必要があります。その場合は、これらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87292-107">As a best practice, administrators who will manage or use MBAM server features should be assigned to Active Directory Domain Services security groups, and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

[<span data-ttu-id="87292-108">MBAM 管理者ロールを管理する方法</span><span class="sxs-lookup"><span data-stu-id="87292-108">How to Manage MBAM Administrator Roles</span></span>](how-to-manage-mbam-administrator-roles-mbam-2.md)

## <span data-ttu-id="87292-109">BitLocker 暗号化の除外を管理する</span><span class="sxs-lookup"><span data-stu-id="87292-109">Manage BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="87292-110">MBAM は、必要のない、またはドライブを暗号化する必要がある特定のユーザーに対して、暗号化の除外を与えることができます。</span><span class="sxs-lookup"><span data-stu-id="87292-110">MBAM lets you grant encryption exemptions to specific users who do not need or want their drives encrypted.</span></span> <span data-ttu-id="87292-111">通常、コンピューターの除外は、開発やテストで使用されているコンピューター、または BitLocker をサポートしていない古いコンピューターなど、会社が暗号化する必要がないコンピューターを持っている場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="87292-111">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="87292-112">場合によっては、特定のコンピューターが暗号化されていないことが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="87292-112">In some cases, local law may also require that certain computers are not encrypted.</span></span>

[<span data-ttu-id="87292-113">ユーザーの BitLocker 暗号化の除外を管理する方法</span><span class="sxs-lookup"><span data-stu-id="87292-113">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)

## <span data-ttu-id="87292-114">コントロールパネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する</span><span class="sxs-lookup"><span data-stu-id="87292-114">Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="87292-115">MBAM は、[**システムとセキュリティ**] の下に表示される、[BitLocker 暗号化オプション] というカスタムコントロールパネルを提供します。</span><span class="sxs-lookup"><span data-stu-id="87292-115">MBAM provides a custom control panel, called BitLocker Encryption Options, that will appear under **System and Security**.</span></span> <span data-ttu-id="87292-116">MBAM コントロールパネルを使用すると、暗号化された固定ドライブとリムーバブルドライブのロックを解除し、PIN またはパスワードを管理することもできます。</span><span class="sxs-lookup"><span data-stu-id="87292-116">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span>

<span data-ttu-id="87292-117">**注** このカスタマイズされたコントロールパネルは、既定の Windows BitLocker コントロールパネルに代わるものではありません。</span><span class="sxs-lookup"><span data-stu-id="87292-117">**Note** This customized control panel does not replace the default Windows BitLocker control panel.</span></span>

 

[<span data-ttu-id="87292-118">コントロール パネルを使用して MBAM クライアントの BitLocker 暗号化オプションを管理する方法</span><span class="sxs-lookup"><span data-stu-id="87292-118">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-2.md)

## <span data-ttu-id="87292-119">MBAM 機能の管理に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="87292-119">Other Resources for Administering MBAM Features</span></span>


[<span data-ttu-id="87292-120">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="87292-120">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





