---
title: MBAM 2.0 の計画チェックリスト
description: MBAM 2.0 の計画チェックリスト
author: dansimp
ms.assetid: 16b27c27-5f5e-41e2-b526-89a036672fb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 89af2f63efa202bc3b09dda2b0401e7a980789c9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822627"
---
# <span data-ttu-id="db80d-103">MBAM 2.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="db80d-103">MBAM 2.0 Planning Checklist</span></span>


<span data-ttu-id="db80d-104">このチェックリストは、Microsoft BitLocker の管理と監視 (MBAM) 展開のために、コンピューティング環境の準備を計画するために使用できます。</span><span class="sxs-lookup"><span data-stu-id="db80d-104">This checklist can be used to help you plan for preparing your computing environment for Microsoft BitLocker Administration and Monitoring (MBAM) deployment.</span></span>

<span data-ttu-id="db80d-105">**注** このチェックリストは、Microsoft BitLocker の管理と監視の展開を計画する際に考慮する必要のある手順と、考慮すべき項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="db80d-105">**Note** This checklist outlines the recommended steps and a high-level list of items to consider when planning for an Microsoft BitLocker Administration and Monitoring deployment.</span></span> <span data-ttu-id="db80d-106">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db80d-106">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="db80d-107">タスク</span><span class="sxs-lookup"><span data-stu-id="db80d-107">Task</span></span></th>
<th align="left"><span data-ttu-id="db80d-108">参照先</span><span class="sxs-lookup"><span data-stu-id="db80d-108">References</span></span></th>
<th align="left"><span data-ttu-id="db80d-109">備考</span><span class="sxs-lookup"><span data-stu-id="db80d-109">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-110">展開計画を開始する前に、MBAM の概要情報を確認して、製品について基本的な理解を深めてください。</span><span class="sxs-lookup"><span data-stu-id="db80d-110">Review the getting started information about MBAM to gain a basic understanding of the product before beginning deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)"><span data-ttu-id="db80d-111">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="db80d-111">Getting Started with MBAM 2.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-112">MBAM 2.0 の展開前提条件を計画し、コンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="db80d-112">Plan for MBAM 2.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)"><span data-ttu-id="db80d-113">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="db80d-113">MBAM 2.0 Deployment Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-114">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="db80d-114">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="db80d-115">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="db80d-115">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-116">必要な ActiveDirectoryDomainServices セキュリティグループの計画と作成を行い、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="db80d-116">Plan for and create necessary ActiveDirectoryDomainServices security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="db80d-117">MBAM 2.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="db80d-117">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-118">Mbam 2.0 でサポートされている構成のドキュメントを確認して、MBAM インストールシステム要件を満たすハードウェアが利用できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="db80d-118">Review the MBAM 2.0 Supported Configurations documentation to ensure that hardware that meets MBAM installation system requirements is available.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="db80d-119">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="db80d-119">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-120">MBAM サーバー機能の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="db80d-120">Plan for deploying MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)"><span data-ttu-id="db80d-121">MBAM 2.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="db80d-121">Planning for MBAM 2.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-122">MBAM クライアント展開の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="db80d-122">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="db80d-123">MBAM 2.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="db80d-123">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="db80d-124">テスト環境で展開計画を検証する。</span><span class="sxs-lookup"><span data-stu-id="db80d-124">Validate your deployment plan in a test environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-20-mbam-2.md" data-raw-source="[Evaluating MBAM 2.0](evaluating-mbam-20-mbam-2.md)"><span data-ttu-id="db80d-125">MBAM 2.0 の評価</span><span class="sxs-lookup"><span data-stu-id="db80d-125">Evaluating MBAM 2.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="db80d-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db80d-126">Related topics</span></span>


[<span data-ttu-id="db80d-127">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="db80d-127">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

 

 





