---
title: MBAM 2.0 の展開チェックリスト
description: MBAM 2.0 の展開チェックリスト
author: dansimp
ms.assetid: 7905d31d-f21c-4683-b9c4-95b815e08fab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d8d0ce1a3ff48d4bf2f84e61b4a578b170264a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826437"
---
# <span data-ttu-id="1b6d1-103">MBAM 2.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="1b6d1-103">MBAM 2.0 Deployment Checklist</span></span>


<span data-ttu-id="1b6d1-104">このチェックリストは、スタンドアロンのトポロジを使用して、Microsoft BitLocker の管理と監視 (MBAM) 展開を行うときに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-104">This checklist can be used to help you during Microsoft BitLocker Administration and Monitoring (MBAM) deployment with a Stand-alone topology.</span></span>

**<span data-ttu-id="1b6d1-105">注</span><span class="sxs-lookup"><span data-stu-id="1b6d1-105">Note</span></span>**  
<span data-ttu-id="1b6d1-106">このチェックリストは、推奨される手順と、Microsoft BitLocker の管理機能と監視機能を展開するときに考慮する項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-106">This checklist outlines the recommended steps and a high-level list of items to consider when deploying Microsoft BitLocker Administration and Monitoring features.</span></span> <span data-ttu-id="1b6d1-107">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-107">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>



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
<th align="left"><span data-ttu-id="1b6d1-108">タスク</span><span class="sxs-lookup"><span data-stu-id="1b6d1-108">Task</span></span></th>
<th align="left"><span data-ttu-id="1b6d1-109">参照先</span><span class="sxs-lookup"><span data-stu-id="1b6d1-109">References</span></span></th>
<th align="left"><span data-ttu-id="1b6d1-110">備考</span><span class="sxs-lookup"><span data-stu-id="1b6d1-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-111">計画フェーズを完了して、MBAM 展開用のコンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-planning-checklist-mbam-2.md" data-raw-source="[MBAM 2.0 Planning Checklist](mbam-20-planning-checklist-mbam-2.md)"><span data-ttu-id="1b6d1-112">MBAM 2.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="1b6d1-112">MBAM 2.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-113">MBAM でサポートされている構成情報を確認して、お使いのクライアントとサーバーのコンピューターが MBAM 機能のインストールでサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-113">Review the MBAM supported configurations information to make sure selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="1b6d1-114">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="1b6d1-114">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-115">Mbam サーバー機能を次の順序で展開するには、MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="1b6d1-116">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="1b6d1-116">Recovery Database</span></span></p></li>
<li><p><span data-ttu-id="1b6d1-117">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="1b6d1-117">Compliance and Audit Database</span></span></p></li>
<li><p><span data-ttu-id="1b6d1-118">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="1b6d1-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="1b6d1-119">セルフサービスサーバー</span><span class="sxs-lookup"><span data-stu-id="1b6d1-119">Self-Service Server</span></span></p></li>
<li><p><span data-ttu-id="1b6d1-120">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="1b6d1-120">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="1b6d1-121">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="1b6d1-121">MBAM Group Policy template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="1b6d1-122">注</span><span class="sxs-lookup"><span data-stu-id="1b6d1-122">Note</span></span></strong><br/><p><span data-ttu-id="1b6d1-123">各機能がインストールされているサーバーの名前を追跡します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-123">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="1b6d1-124">この情報は、インストールプロセス全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-124">This information will be used throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-20-server-infrastructure-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md)"><span data-ttu-id="1b6d1-125">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="1b6d1-125">Deploying the MBAM 2.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-126">計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、適切なローカル MBAM サーバー機能の管理者グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-126">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="1b6d1-127">MBAM 2.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> Mbam 管理者ロールの管理方法</span><span class="sxs-lookup"><span data-stu-id="1b6d1-127">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-128">必要な MBAM グループポリシーオブジェクトを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-128">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="1b6d1-129">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="1b6d1-129">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="1b6d1-130">MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="1b6d1-130">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="1b6d1-131">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="1b6d1-131">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="1b6d1-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1b6d1-132">Related topics</span></span>


[<span data-ttu-id="1b6d1-133">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="1b6d1-133">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)









