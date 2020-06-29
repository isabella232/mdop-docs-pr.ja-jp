---
title: MBAM 2.5 の計画チェックリスト
description: MBAM 2.5 の計画チェックリスト
author: dansimp
ms.assetid: ffe11eb8-44db-4886-8300-6dffec8bcfa4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 505f2890d67f36056ab5bb87df2a894473cd3306
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826544"
---
# <span data-ttu-id="eece9-103">MBAM 2.5 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="eece9-103">MBAM 2.5 Planning Checklist</span></span>


<span data-ttu-id="eece9-104">次のチェックリストを使用して、Microsoft BitLocker の管理と監視 (MBAM) 展開のためのコンピューティング環境の準備に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="eece9-104">You can use the following checklists to help you prepare your computing environment for the Microsoft BitLocker Administration and Monitoring (MBAM) deployment.</span></span> <span data-ttu-id="eece9-105">このチェックリストには、展開を計画するときに考慮する必要がある大まかな項目の一覧が用意されています。</span><span class="sxs-lookup"><span data-stu-id="eece9-105">The checklists provide a high-level list of items to consider when planning the deployment.</span></span> <span data-ttu-id="eece9-106">スタンドアロントポロジと構成マネージャーの統合トポロジについては、個別のチェックリストが用意されています。</span><span class="sxs-lookup"><span data-stu-id="eece9-106">There are separate checklists for the Stand-alone topology and the Configuration Manager Integration topology.</span></span> <span data-ttu-id="eece9-107">目的のチェックリストをスプレッドシートにコピーして、使用するためにカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="eece9-107">You might want to copy the desired checklist into a spreadsheet and customize it for your use.</span></span>

**<span data-ttu-id="eece9-108">MBAM 展開用の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="eece9-108">Planning checklist for an MBAM deployment</span></span>**

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
<th align="left"><span data-ttu-id="eece9-109">タスク</span><span class="sxs-lookup"><span data-stu-id="eece9-109">Task</span></span></th>
<th align="left"><span data-ttu-id="eece9-110">参照先</span><span class="sxs-lookup"><span data-stu-id="eece9-110">References</span></span></th>
<th align="left"><span data-ttu-id="eece9-111">備考</span><span class="sxs-lookup"><span data-stu-id="eece9-111">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-112">展開計画を開始する前に、「はじめに」の情報を確認して &quot; &quot; 、製品について理解してください。</span><span class="sxs-lookup"><span data-stu-id="eece9-112">Review the &quot;Getting started&quot; information to understand the product before you start deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-25.md" data-raw-source="[Getting Started with MBAM 2.5](getting-started-with-mbam-25.md)"><span data-ttu-id="eece9-113">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="eece9-113">Getting Started with MBAM 2.5</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-114">MBAM 展開の推奨される高レベルアーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-114">Review the recommended high-level architecture for an MBAM deployment.</span></span> <span data-ttu-id="eece9-115">また、MBAM 展開の個々の部分 (データベース、web サイト、レポート) のイラストと説明を確認したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="eece9-115">You might also want to review an illustration and description of the individual parts (databases, websites, Reports) of an MBAM deployment.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="eece9-116">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="eece9-116">High-Level Architecture for MBAM 2.5</span></span></a></p>
<p><a href="illustrated-features-of-an-mbam-25-deployment.md" data-raw-source="[Illustrated Features of an MBAM 2.5 Deployment](illustrated-features-of-an-mbam-25-deployment.md)"><span data-ttu-id="eece9-117">MBAM 2.5 展開の機能の図</span><span class="sxs-lookup"><span data-stu-id="eece9-117">Illustrated Features of an MBAM 2.5 Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-118">MBAM スタンドアロンおよび Configuration Manager の統合トポロジの前提条件を確認して完了します。</span><span class="sxs-lookup"><span data-stu-id="eece9-118">Review and complete the prerequisites for the MBAM Stand-alone and Configuration Manager Integration topologies.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="eece9-119">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="eece9-119">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-120">Configuration Manager の統合トポロジを使用する予定がある場合は、このトポロジのみに適用されるその他の前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="eece9-120">If you plan to use the Configuration Manager Integration topology, complete the additional prerequisites that apply only to this topology.</span></span></p></td>
<td align="left"><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="eece9-121">Configuration Manager 統合トポロジのみに適用される MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="eece9-121">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-122">MBAM クライアントの MBAM 2.5 の前提条件を確認して、会議を行います。</span><span class="sxs-lookup"><span data-stu-id="eece9-122">Review and meet the MBAM 2.5 prerequisites for the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="prerequisites-for-mbam-25-clients.md" data-raw-source="[Prerequisites for MBAM 2.5 Clients](prerequisites-for-mbam-25-clients.md)"><span data-ttu-id="eece9-123">MBAM 2.5 クライアントの前提条件</span><span class="sxs-lookup"><span data-stu-id="eece9-123">Prerequisites for MBAM 2.5 Clients</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-124">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="eece9-124">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-group-policy-requirements.md" data-raw-source="[Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md)"><span data-ttu-id="eece9-125">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="eece9-125">Planning for MBAM 2.5 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-126">必要な ActiveDirectoryDomainServices セキュリティグループを計画して作成します。</span><span class="sxs-lookup"><span data-stu-id="eece9-126">Plan for and create the necessary ActiveDirectoryDomainServices security groups.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"><span data-ttu-id="eece9-127">MBAM 2.5 グループとアカウントの計画</span><span class="sxs-lookup"><span data-stu-id="eece9-127">Planning for MBAM 2.5 Groups and Accounts</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-128">MBAM web サイトのセキュリティを保護する方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="eece9-128">Plan how you will secure the MBAM websites.</span></span></p></td>
<td align="left"><p><a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"><span data-ttu-id="eece9-129">MBAM Web サイトをセキュリティで保護する方法の計画</span><span class="sxs-lookup"><span data-stu-id="eece9-129">Planning How to Secure the MBAM Websites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-130">MBAM サポートされている構成を確認して、ハードウェアがインストールシステムの要件を満たしていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-130">Review the MBAM Supported Configurations to ensure that your hardware meets the installation system requirements.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="eece9-131">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="eece9-131">MBAM 2.5 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-132">MBAM Server 機能の展開に関する考慮事項を確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-132">Review the considerations for deploying the MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-server-deployment.md" data-raw-source="[Planning for MBAM 2.5 Server Deployment](planning-for-mbam-25-server-deployment.md)"><span data-ttu-id="eece9-133">MBAM 2.5 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="eece9-133">Planning for MBAM 2.5 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-134">MBAM クライアントの展開に関する考慮事項を確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-134">Review the considerations for deploying the MBAM Client.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-client-deployment.md" data-raw-source="[Planning for MBAM 2.5 Client Deployment](planning-for-mbam-25-client-deployment.md)"><span data-ttu-id="eece9-135">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="eece9-135">Planning for MBAM 2.5 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-136">高可用性構成で MBAM を展開するための要件と手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-136">Review the requirements and steps to deploy MBAM in a highly available configuration.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-25-high-availability.md" data-raw-source="[Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md)"><span data-ttu-id="eece9-137">MBAM 2.5 の高可用性のための計画</span><span class="sxs-lookup"><span data-stu-id="eece9-137">Planning for MBAM 2.5 High Availability</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-138">トラステッドプラットフォームモジュール、ログファイル、透過データ暗号化に関連する MBAM セキュリティの考慮事項について確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-138">Review the MBAM security considerations that pertain to the Trusted Platform Module, log files, and transparent data encryption.</span></span></p></td>
<td align="left"><p><a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"><span data-ttu-id="eece9-139">MBAM 2.5 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="eece9-139">MBAM 2.5 Security Considerations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="eece9-140">必要に応じて、テスト環境で MBAM を評価する手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="eece9-140">Optionally, review the steps to evaluate MBAM in a test environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-25-in-a-test-environment.md" data-raw-source="[Evaluating MBAM 2.5 in a Test Environment](evaluating-mbam-25-in-a-test-environment.md)"><span data-ttu-id="eece9-141">テスト環境での MBAM 2.5 の評価</span><span class="sxs-lookup"><span data-stu-id="eece9-141">Evaluating MBAM 2.5 in a Test Environment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="eece9-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="eece9-142">Related topics</span></span>


[<span data-ttu-id="eece9-143">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="eece9-143">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 

 
## <span data-ttu-id="eece9-144">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="eece9-144">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="eece9-145">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="eece9-145">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="eece9-146">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="eece9-146">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




