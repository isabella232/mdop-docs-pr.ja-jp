---
title: MBAM 管理者ロールを管理する方法
description: MBAM 管理者ロールを管理する方法
author: dansimp
ms.assetid: c0f25a42-dbff-418d-a776-4fe23ee07d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d00b8ebf66d2b066afae33e67298691285ce9fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812970"
---
# <span data-ttu-id="23bd9-103">MBAM 管理者ロールを管理する方法</span><span class="sxs-lookup"><span data-stu-id="23bd9-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="23bd9-104">Microsoft BitLocker の管理と監視 (MBAM) のセットアップが完了したら、すべてのサーバー機能で、これらのサーバー機能へのアクセス権を管理ユーザーに付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bd9-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="23bd9-105">ベストプラクティスとして、MBAM server 機能を管理または使用する管理者は Active Directory のセキュリティグループに割り当てる必要があります。その後、それらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bd9-105">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="23bd9-106">MBAM 管理者の役割のメンバーシップを管理するには</span><span class="sxs-lookup"><span data-stu-id="23bd9-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="23bd9-107">ActiveDirectoryDomain Services のセキュリティグループに管理ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="23bd9-107">Assign administrative users to security groups in ActiveDirectoryDomain Services.</span></span>

2.  <span data-ttu-id="23bd9-108">ActiveDirectoryDomain サービスセキュリティグループを、Microsoft BitLocker 管理サーバーおよび監視サーバー上の MBAM 管理ローカルグループの役割に、それぞれの機能について追加します。</span><span class="sxs-lookup"><span data-stu-id="23bd9-108">Add ActiveDirectoryDomain Services security groups to the roles for MBAM administrative local groups on the Microsoft BitLocker Administration and Monitoring server for the respective features.</span></span> <span data-ttu-id="23bd9-109">ユーザーの役割は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="23bd9-109">The user roles are as follows:</span></span>

    -   <span data-ttu-id="23bd9-110">**Mbam システム管理者**は、mbam 管理 web サイトの Microsoft BitLocker 管理および監視機能のすべてにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23bd9-110">**MBAM System Administrators** have access to all Microsoft BitLocker Administration and Monitoring features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="23bd9-111">**Mbam ハードウェアユーザー**は、mbam 管理 web サイトのハードウェア互換性機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23bd9-111">**MBAM Hardware Users** have access to the Hardware Compatibility features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="23bd9-112">**Mbam ヘルプデスクユーザー**は、mbam 管理 web サイトの [TPM およびドライブの回復] オプションにアクセスできますが、いずれかのオプションを使用する場合は、すべてのフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="23bd9-112">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM administration website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="23bd9-113">**Mbam レポートユーザー**は、mbam 管理 web サイトのコンプライアンスおよび監査レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23bd9-113">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM administration website.</span></span>

    -   <span data-ttu-id="23bd9-114">**Mbam Advanced ヘルプデスクでは**、mbam 管理 web サイトの TPM およびドライブの回復オプションの管理にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="23bd9-114">**MBAM Advanced Helpdesk Uses** have access to the Manage TPM and Drive Recovery options in the MBAM administration website.</span></span> <span data-ttu-id="23bd9-115">これらのユーザーは、いずれかのオプションを使用する場合、すべてのフィールドに入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="23bd9-115">These users are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="23bd9-116">Microsoft BitLocker の管理と監視の役割の詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="23bd9-116">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

## <span data-ttu-id="23bd9-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="23bd9-117">Related topics</span></span>


[<span data-ttu-id="23bd9-118">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="23bd9-118">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





