---
title: MBAM 1.0 の展開チェックリスト
description: MBAM 1.0 の展開チェックリスト
author: dansimp
ms.assetid: 7e00be23-36a0-4b0f-8663-3c4f2c71546d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 96725183af2cb4e3d86d3f42973452c598497773
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812538"
---
# <span data-ttu-id="fb2b8-103">MBAM 1.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="fb2b8-103">MBAM 1.0 Deployment Checklist</span></span>


<span data-ttu-id="fb2b8-104">このチェックリストは、Microsoft BitLocker の管理と監視 (MBAM) を簡単に展開できるように設計されています。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-104">This checklist is designed to facilitate your deployment of Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

**<span data-ttu-id="fb2b8-105">注</span><span class="sxs-lookup"><span data-stu-id="fb2b8-105">Note</span></span>**  
<span data-ttu-id="fb2b8-106">このチェックリストは推奨手順の概要を示し、MBAM 機能を展開するときに考慮する必要がある概要の項目の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-106">This checklist outlines the recommended steps and provides a high-level list of items to consider when you deploy the MBAM features.</span></span> <span data-ttu-id="fb2b8-107">このチェックリストをスプレッドシートプログラムにコピーして、特定のニーズに合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-107">We recommend that you copy this checklist into a spreadsheet program and customize it for your specific needs.</span></span>



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
<th align="left"><span data-ttu-id="fb2b8-108">タスク</span><span class="sxs-lookup"><span data-stu-id="fb2b8-108">Task</span></span></th>
<th align="left"><span data-ttu-id="fb2b8-109">参照先</span><span class="sxs-lookup"><span data-stu-id="fb2b8-109">References</span></span></th>
<th align="left"><span data-ttu-id="fb2b8-110">備考</span><span class="sxs-lookup"><span data-stu-id="fb2b8-110">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-111">計画フェーズを完了して、MBAM 展開用のコンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-111">Complete the planning phase to prepare the computing environment for MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="mbam-10-planning-checklist.md" data-raw-source="[MBAM 1.0 Planning Checklist](mbam-10-planning-checklist.md)"><span data-ttu-id="fb2b8-112">MBAM 1.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="fb2b8-112">MBAM 1.0 Planning Checklist</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-113">MBAM 機能がインストールされていることを確認するために、MBAM サポートされている構成の情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-113">Review the information on MBAM supported configurations to make sure that your selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="fb2b8-114">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="fb2b8-114">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-115">Mbam サーバー機能を次の順序で展開するには、MBAM セットアップを実行します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-115">Run MBAM Setup to deploy MBAM Server features in the following order:</span></span></p>
<ol>
<li><p><span data-ttu-id="fb2b8-116">回復とハードウェアデータベース</span><span class="sxs-lookup"><span data-stu-id="fb2b8-116">Recovery and Hardware Database</span></span></p></li>
<li><p><span data-ttu-id="fb2b8-117">コンプライアンスステータスデータベース</span><span class="sxs-lookup"><span data-stu-id="fb2b8-117">Compliance Status Database</span></span></p></li>
<li><p><span data-ttu-id="fb2b8-118">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="fb2b8-118">Compliance Audit and Reports</span></span></p></li>
<li><p><span data-ttu-id="fb2b8-119">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="fb2b8-119">Administration and Monitoring Server</span></span></p></li>
<li><p><span data-ttu-id="fb2b8-120">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="fb2b8-120">MBAM Group Policy Template</span></span></p></li>
</ol>
<div class="alert">
<strong><span data-ttu-id="fb2b8-121">注</span><span class="sxs-lookup"><span data-stu-id="fb2b8-121">Note</span></span></strong><br/><p><span data-ttu-id="fb2b8-122">各機能がインストールされているサーバーの名前を追跡します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-122">Keep track of the names of the servers each feature is installed on.</span></span> <span data-ttu-id="fb2b8-123">この情報は、インストールプロセス全体で使用されます。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-123">You will use this information throughout the installation process.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="deploying-the-mbam-10-server-infrastructure.md" data-raw-source="[Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md)"><span data-ttu-id="fb2b8-124">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="fb2b8-124">Deploying the MBAM 1.0 Server Infrastructure</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-125">計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、適切なローカル MBAM サーバー機能の管理者グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-125">Add Active Directory Domain Services security groups created during the planning phase to the appropriate local MBAM Server feature administrators groups on the appropriate servers.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="fb2b8-126">MBAM 1.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> Mbam 管理者ロールの管理方法</span><span class="sxs-lookup"><span data-stu-id="fb2b8-126">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-127">必要な MBAM グループポリシーオブジェクトを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-127">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="fb2b8-128">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="fb2b8-128">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="fb2b8-129">MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="fb2b8-129">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="fb2b8-130">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="fb2b8-130">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="fb2b8-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fb2b8-131">Related topics</span></span>


[<span data-ttu-id="fb2b8-132">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="fb2b8-132">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)









