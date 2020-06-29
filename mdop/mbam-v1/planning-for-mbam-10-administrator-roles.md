---
title: MBAM 1.0 管理者ロールの計画
description: MBAM 1.0 管理者ロールの計画
author: dansimp
ms.assetid: 95be0eb4-25e9-43ca-a8e7-27373d35544d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 104d650824330ea990881c520a7811511f496dd1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825887"
---
# <span data-ttu-id="9de4d-103">MBAM 1.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="9de4d-103">Planning for MBAM 1.0 Administrator Roles</span></span>


<span data-ttu-id="9de4d-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) で利用できる管理者の役割と、ローカルグループが作成されているサーバーの場所について説明します。</span><span class="sxs-lookup"><span data-stu-id="9de4d-104">This topic includes and describes the administrator roles that are available in Microsoft BitLocker Administration and Monitoring (MBAM), as well as the server locations where the local groups are created.</span></span>

## <span data-ttu-id="9de4d-105">MBAM 管理者ロール</span><span class="sxs-lookup"><span data-stu-id="9de4d-105">MBAM Administrator roles</span></span>


<a href="" id="---------------mbam-system-administrators"></a> **<span data-ttu-id="9de4d-106">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="9de4d-106">MBAM System Administrators</span></span>**  
<span data-ttu-id="9de4d-107">この役割の管理者は、すべての MBAM 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-107">Administrators in this role have access to all MBAM features.</span></span> <span data-ttu-id="9de4d-108">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-108">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-hardware-users"></a> **<span data-ttu-id="9de4d-109">MBAM ハードウェアユーザー</span><span class="sxs-lookup"><span data-stu-id="9de4d-109">MBAM Hardware Users</span></span>**  
<span data-ttu-id="9de4d-110">この役割の管理者は、MBAM からハードウェア機能機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-110">Administrators in this role have access to the Hardware Capability features from MBAM.</span></span> <span data-ttu-id="9de4d-111">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-111">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam-helpdesk-users"></a> **<span data-ttu-id="9de4d-112">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="9de4d-112">MBAM Helpdesk Users</span></span>**  
<span data-ttu-id="9de4d-113">この役割の管理者は、MBAM のヘルプデスク機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-113">Administrators in this role have access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="9de4d-114">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-114">The local group for this role is installed on the Administration and Monitoring Server.</span></span>

<a href="" id="---------------mbam--report-users"></a> **<span data-ttu-id="9de4d-115">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="9de4d-115">MBAM Report Users</span></span>**  
<span data-ttu-id="9de4d-116">このロールの管理者は、MBAM からコンプライアンスと監査レポート機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-116">Administrators in this role have access to the Compliance and Audit Reports feature from MBAM.</span></span> <span data-ttu-id="9de4d-117">この役割のローカルグループは、管理/監視サーバー、コンプライアンスおよび監査データベース、コンプライアンスおよび監査レポートをホストしているサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-117">The local group for this role is installed on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports.</span></span>

<a href="" id="---------------mbam--advanced-helpdesk-users"></a> **<span data-ttu-id="9de4d-118">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="9de4d-118">MBAM Advanced Helpdesk Users</span></span>**  
<span data-ttu-id="9de4d-119">この役割の管理者は、MBAM のヘルプデスク機能へのアクセスを強化しています。</span><span class="sxs-lookup"><span data-stu-id="9de4d-119">Administrators in this role have increased access to the Helpdesk features from MBAM.</span></span> <span data-ttu-id="9de4d-120">この役割のローカルグループは、管理/監視サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-120">The local group for this role is installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="9de4d-121">ユーザーが MBAM ヘルプデスクユーザーと MBAM Advanced ヘルプデスクユーザーの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーアクセス許可によって、MBAM ヘルプデスクのユーザーアクセス許可が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="9de4d-121">If a user is a member of both MBAM Helpdesk Users and MBAM Advanced Helpdesk Users, the MBAM Advanced Helpdesk Users permissions will overwrite the MBAM Helpdesk User permissions.</span></span>

<span data-ttu-id="9de4d-122">**重要** レポートを表示するには、管理者ユーザーは、管理/監視サーバー、コンプライアンスおよび監査データベース、およびコンプライアンスとレポート機能をホストするサーバー上の**Mbam レポートユーザー**セキュリティグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9de4d-122">**Important** To view the reports, an administrative user must be a member of the **MBAM Report Users** security group on the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Reports feature.</span></span> <span data-ttu-id="9de4d-123">ベストプラクティスとして、管理サーバーと監視サーバーの両方、またはコンプライアンスとレポートをホストしているサーバー上で、local **Mbam Report Users**セキュリティグループの権限を持つ Active Directory でセキュリティグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="9de4d-123">As a best practice, create a security group in Active Directory with rights on the local **MBAM Report Users** security group on both the Administration and Monitoring Server and on the server that hosts the Compliance and Reports.</span></span>

 

## <span data-ttu-id="9de4d-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9de4d-124">Related topics</span></span>


[<span data-ttu-id="9de4d-125">MBAM 1.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="9de4d-125">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)

 

 





