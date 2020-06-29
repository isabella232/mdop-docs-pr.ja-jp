---
title: MBAM 管理者ロールを管理する方法
description: MBAM 管理者ロールを管理する方法
author: dansimp
ms.assetid: 813ac0c4-3cf9-47af-b4cb-9395fd915e5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14e9128904b448b20e0596a2630627b7ca8e711d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825117"
---
# <span data-ttu-id="dfe71-103">MBAM 管理者ロールを管理する方法</span><span class="sxs-lookup"><span data-stu-id="dfe71-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="dfe71-104">Microsoft BitLocker の管理と監視 (MBAM) のセットアップが完了したら、すべてのサーバー機能で、管理者ユーザーにアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe71-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users will have to be granted access to them.</span></span> <span data-ttu-id="dfe71-105">ベストプラクティスとして、Microsoft BitLocker 管理および監視サーバー機能を管理または使用する管理者は、ドメインサービスセキュリティグループに割り当てる必要があります。その場合は、これらのグループを適切な MBAM 管理ローカルグループに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe71-105">As a best practice, administrators who will manage or use Microsoft BitLocker Administration and Monitoring Server features should be assigned to Domain Services security groups, and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="dfe71-106">MBAM 管理者の役割のメンバーシップを管理するには</span><span class="sxs-lookup"><span data-stu-id="dfe71-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="dfe71-107">Active Directory ドメインサービスのセキュリティグループに管理ユーザーを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="dfe71-107">Assign administrative users to security groups in ActiveDirectory Domain Services.</span></span>

2.  <span data-ttu-id="dfe71-108">使用している各機能に対して、ActiveDirectory セキュリティグループを MBAM サーバー上の MBAM 管理ローカルグループの役割に追加します。</span><span class="sxs-lookup"><span data-stu-id="dfe71-108">Add ActiveDirectory security groups to the roles for MBAM administrative local groups on the MBAM server for the respective features.</span></span>

    -   <span data-ttu-id="dfe71-109">**Mbam システム管理者**は、Mbam 管理と監視 web サイトのすべての mbam 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dfe71-109">**MBAM System Administrators** have access to all MBAM features in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="dfe71-110">**Mbam ヘルプデスクユーザー**は、mbam 管理と監視の web サイトで TPM およびドライブの回復オプションにアクセスできますが、いずれかのオプションを使用する場合は、すべてのフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="dfe71-110">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="dfe71-111">**Mbam レポートユーザー**は、Mbam 管理と監視 web サイトのコンプライアンスおよび監査レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="dfe71-111">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="dfe71-112">**Mbam Advanced のヘルプデスクユーザー**は、mbam 管理と監視の web サイトで TPM およびドライブの回復オプションにアクセスできますが、どちらのオプションを使用する場合でも、すべてのフィールドに入力する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="dfe71-112">**MBAM Advanced Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="dfe71-113">Microsoft BitLocker の管理と監視の役割の詳細については、「 [MBAM 2.0 管理者ロールの計画](planning-for-mbam-20-administrator-roles-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="dfe71-113">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

## <span data-ttu-id="dfe71-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="dfe71-114">Related topics</span></span>


[<span data-ttu-id="dfe71-115">MBAM 2.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="dfe71-115">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





