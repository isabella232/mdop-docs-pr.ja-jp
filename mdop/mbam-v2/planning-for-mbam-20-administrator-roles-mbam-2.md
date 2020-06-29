---
title: MBAM 2.0 管理者ロールの計画
description: MBAM 2.0 管理者ロールの計画
author: dansimp
ms.assetid: 6f813297-6479-42d3-a21b-896d54466b5b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a89a04c0ef074407dc3cd081d351d44023e65e70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824894"
---
# <span data-ttu-id="cd246-103">MBAM 2.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="cd246-103">Planning for MBAM 2.0 Administrator Roles</span></span>


<span data-ttu-id="cd246-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) およびローカルグループが作成されているサーバーの場所で利用できる管理者ロールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cd246-104">This topic lists and describes the available administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM) as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="cd246-105">MBAM 管理者ロール</span><span class="sxs-lookup"><span data-stu-id="cd246-105">MBAM Administrator Roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="cd246-106">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="cd246-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="cd246-107">この役割の管理者は、Microsoft BitLocker のすべての管理機能と監視機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd246-107">Administrators in this role have access to all Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="cd246-108">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd246-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="cd246-109">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="cd246-109">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="cd246-110">このロールの管理者は、MBAM からのヘルプデスク機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd246-110">Administrators in this role have access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="cd246-111">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd246-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-report-users"></a> **<span data-ttu-id="cd246-112">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="cd246-112">MBAM Report Users</span></span>**  
<span data-ttu-id="cd246-113">このロールの管理者は、MBAM からのコンプライアンスおよび監査レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cd246-113">Administrators in this role have access to the Compliance and Audit Reports from MBAM.</span></span> <span data-ttu-id="cd246-114">この役割のローカルグループは、管理/監視サーバー、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートをホストしているサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd246-114">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam-advanced-helpdesk-users"></a> **<span data-ttu-id="cd246-115">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="cd246-115">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="cd246-116">この役割の管理者は、MBAM からのヘルプデスク機能へのアクセス権を強化しています。</span><span class="sxs-lookup"><span data-stu-id="cd246-116">Administrators in this role have increased access to the Help Desk features from MBAM.</span></span> <span data-ttu-id="cd246-117">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd246-117">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="cd246-118">ユーザーが MBAM ヘルプデスクユーザーと MBAM Advanced ヘルプデスクユーザーの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーのアクセス許可は、MBAM ヘルプデスクのユーザーアクセス許可よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="cd246-118">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will override the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="cd246-119">**重要** レポートを表示するには、管理者ユーザーは、管理/監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスと監査レポート機能をホストしているサーバー上の**Mbam レポートユーザー**セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd246-119">**Important** To view reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports feature.</span></span> <span data-ttu-id="cd246-120">ベストプラクティスとして、ローカル**Mbam Report Users**セキュリティグループの権限を持つセキュリティグループを、管理と監視サーバーと、コンプライアンスと監査レポートをホストするサーバーの両方で作成します。</span><span class="sxs-lookup"><span data-stu-id="cd246-120">As a best practice, create a security group in Active Directory Domain Services with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and the server that hosts the Compliance and Audit Reports.</span></span>

 

## <span data-ttu-id="cd246-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cd246-121">Related topics</span></span>


[<span data-ttu-id="cd246-122">MBAM 2.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="cd246-122">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)

 

 





