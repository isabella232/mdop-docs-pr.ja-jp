---
title: MBAM 1.0 の計画チェックリスト
description: MBAM 1.0 の計画チェックリスト
author: dansimp
ms.assetid: e9439f16-d68b-48ed-99ce-5949356b180b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 08106dc457a4caa86ffdb0c65216e4567785db1c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825824"
---
# <span data-ttu-id="5f1e8-103">MBAM 1.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="5f1e8-103">MBAM 1.0 Planning Checklist</span></span>


<span data-ttu-id="5f1e8-104">このチェックリストを使用して、Microsoft BitLocker の管理と監視 (MBAM) 展開のためにコンピューティング環境を計画して準備することができます。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-104">You can use this checklist to plan and prepare your computing environment for Microsoft BitLocker Administration and Monitoring (MBAM) deployment.</span></span>

<span data-ttu-id="5f1e8-105">**注** このチェックリストは、MBAM 展開を計画する際に考慮する必要のある手順と、考慮すべき項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-105">**Note** This checklist outlines the recommended steps and a high-level list of items to consider when you plan for an MBAM deployment.</span></span> <span data-ttu-id="5f1e8-106">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-106">We recommend that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

 

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
<th align="left"><span data-ttu-id="5f1e8-107">タスク</span><span class="sxs-lookup"><span data-stu-id="5f1e8-107">Task</span></span></th>
<th align="left"><span data-ttu-id="5f1e8-108">参照先</span><span class="sxs-lookup"><span data-stu-id="5f1e8-108">References</span></span></th>
<th align="left"><span data-ttu-id="5f1e8-109">備考</span><span class="sxs-lookup"><span data-stu-id="5f1e8-109">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-110">展開計画を開始する前に、MBAM の "はじめに" 情報を確認して、製品の基本的な理解を深めます。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-110">Review the “getting started” information about MBAM to gain a basic understanding of the product before you begin the deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)"><span data-ttu-id="5f1e8-111">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="5f1e8-111">Getting Started with MBAM 1.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-112">MBAM 1.0 の展開前提条件を計画し、コンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-112">Plan for MBAM 1.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)"><span data-ttu-id="5f1e8-113">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="5f1e8-113">MBAM 1.0 Deployment Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-114">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-114">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)"><span data-ttu-id="5f1e8-115">MBAM 1.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="5f1e8-115">Planning for MBAM 1.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-116">必要な ActiveDirectoryDomainServices セキュリティグループの計画と作成を行い、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-116">Plan for and create necessary ActiveDirectoryDomainServices security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="5f1e8-117">MBAM 1.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="5f1e8-117">Planning for MBAM 1.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-118">Mbam 1.0 でサポートされている構成に関するドキュメントを参照して、MBAM インストールシステム要件を満たしているハードウェアを確認してください。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-118">Review the MBAM 1.0 Supported Configurations documentation to ensure hardware that meets MBAM installation system requirements is available.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="5f1e8-119">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="5f1e8-119">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-120">MBAM サーバー機能の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-120">Plan for MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)"><span data-ttu-id="5f1e8-121">MBAM 1.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="5f1e8-121">Planning for MBAM 1.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-122">MBAM クライアントの展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-122">Plan for MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)"><span data-ttu-id="5f1e8-123">MBAM 1.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="5f1e8-123">Planning for MBAM 1.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5f1e8-124">ラボ環境で展開計画を検証する。</span><span class="sxs-lookup"><span data-stu-id="5f1e8-124">Validate your deployment plan in a lab environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-10.md" data-raw-source="[Evaluating MBAM 1.0](evaluating-mbam-10.md)"><span data-ttu-id="5f1e8-125">MBAM 1.0 の評価</span><span class="sxs-lookup"><span data-stu-id="5f1e8-125">Evaluating MBAM 1.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="5f1e8-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5f1e8-126">Related topics</span></span>


[<span data-ttu-id="5f1e8-127">MBAM 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="5f1e8-127">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





