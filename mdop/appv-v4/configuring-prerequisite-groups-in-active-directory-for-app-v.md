---
title: App-V 用に Active Directory の前提条件グループを構成する
description: App-V 用に Active Directory の前提条件グループを構成する
author: dansimp
ms.assetid: 0010d534-46c0-44a3-b5c1-621b4d5e2c31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa1ab6393dee20203b715311d4e1dfdc4c22c679
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821864"
---
# <span data-ttu-id="5fff3-103">App-V 用に Active Directory の前提条件グループを構成する</span><span class="sxs-lookup"><span data-stu-id="5fff3-103">Configuring Prerequisite Groups in Active Directory for App-V</span></span>


<span data-ttu-id="5fff3-104">Microsoft Application Virtualization (App-v) Management サーバーをインストールする前に、Active Directory で次のオブジェクトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fff3-104">Before you install the Microsoft Application Virtualization (App-V) Management Server, you must create the following objects in Active Directory.</span></span> <span data-ttu-id="5fff3-105">App-v は Active Directory グループを使って、アプリケーションと管理機能へのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="5fff3-105">App-V uses Active Directory groups to control access to applications and administrative functions.</span></span> <span data-ttu-id="5fff3-106">これらのグループは、サーバーのインストールプロセスおよびアプリケーションの公開時に使用します。</span><span class="sxs-lookup"><span data-stu-id="5fff3-106">You will use these groups during the server installation process and when publishing applications.</span></span>

## <span data-ttu-id="5fff3-107">Active Directory でアプリケーションの仮想化に必要なグループを設定する</span><span class="sxs-lookup"><span data-stu-id="5fff3-107">Configuring Prerequisite Groups in Active Directory for Application Virtualization</span></span>


<span data-ttu-id="5fff3-108">次の表は、App-v のインストールに必要な Active Directory グループを示しています。</span><span class="sxs-lookup"><span data-stu-id="5fff3-108">This table lists the Active Directory groups that are required for installing App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5fff3-109">オブジェクト</span><span class="sxs-lookup"><span data-stu-id="5fff3-109">Object</span></span></th>
<th align="left"><span data-ttu-id="5fff3-110">説明</span><span class="sxs-lookup"><span data-stu-id="5fff3-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5fff3-111">組織単位 (OU)</span><span class="sxs-lookup"><span data-stu-id="5fff3-111">Organizational Unit (OU)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fff3-112">App-v に必要な特定のグループに対して Active Directory で OU を作成します。</span><span class="sxs-lookup"><span data-stu-id="5fff3-112">Create an OU in Active Directory for the specific groups required for App-V.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5fff3-113">App-v 管理グループ</span><span class="sxs-lookup"><span data-stu-id="5fff3-113">App-V Administrative Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fff3-114">App-v 管理サーバーのインストール中に、管理コンソールへの管理アクセスを制御するために、App-v 管理者グループとして使用する Active Directory グループを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fff3-114">During installation of the App-V Management Server, you must select an Active Directory group to use as the App-V Administrators group to control administrative access to the Management Console.</span></span> <span data-ttu-id="5fff3-115">App-v 管理者のセキュリティグループを作成し、管理コンソールを使う必要があるユーザーごとにこのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="5fff3-115">Create a security group for App-V administrators, and add to this group every user who needs to use the Management Console.</span></span> <span data-ttu-id="5fff3-116">このグループは、App-v Management Server installer から直接作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="5fff3-116">You cannot create this group directly from the App-V Management Server installer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5fff3-117">App-v Users グループ</span><span class="sxs-lookup"><span data-stu-id="5fff3-117">App-V Users Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fff3-118">App-v 機能にアクセスするすべてのユーザーアカウントは、一般的なプラットフォームアクセス用に1つのグループに関連付けられたプロバイダーポリシーのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="5fff3-118">App-V requires that every User account that accesses App-V functions be a member of a provider policy associated with a single group for general platform access.</span></span> <span data-ttu-id="5fff3-119">既存のグループを使用するたとえば、すべてのユーザーが App-v へのアクセス権を持っている場合、または新しいグループを作成する場合は、ドメインユーザー。</span><span class="sxs-lookup"><span data-stu-id="5fff3-119">Use an existing group; for example, Domain Users, if all users are to have access to App-V, or create a new group.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5fff3-120">アプリケーショングループ</span><span class="sxs-lookup"><span data-stu-id="5fff3-120">Application Groups</span></span></p></td>
<td align="left"><p><span data-ttu-id="5fff3-121">App-v は、個々のアプリケーションを Active Directory グループと共に使用する権利を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="5fff3-121">App-V associates the right to use an individual application with an Active Directory group.</span></span> <span data-ttu-id="5fff3-122">各アプリケーションの Active Directory グループを作成し、必要に応じてこれらのグループにユーザーを割り当てて、アプリケーションへのユーザーアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="5fff3-122">Create an Active Directory group for each application, and assign users to these groups as needed to control user access to the applications.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5fff3-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5fff3-123">Related topics</span></span>


[<span data-ttu-id="5fff3-124">Application Virtualization の展開要件</span><span class="sxs-lookup"><span data-stu-id="5fff3-124">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)

[<span data-ttu-id="5fff3-125">App-V Management Server 用に Windows Server 2008 を構成する方法</span><span class="sxs-lookup"><span data-stu-id="5fff3-125">How to Configure Windows Server 2008 for App-V Management Servers</span></span>](how-to-configure-windows-server-2008-for-app-v-management-servers.md)

 

 





