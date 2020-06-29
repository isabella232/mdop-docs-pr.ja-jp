---
title: Administration and Monitoring Web サイトの使用方法
description: Administration and Monitoring Web サイトの使用方法
author: dansimp
ms.assetid: bb96a4e8-d4f4-4e6f-b7db-82d96998bfa6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b9597e29a5a7a6236cb351d8d6d1f682edce3cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813043"
---
# <span data-ttu-id="86614-103">Administration and Monitoring Web サイトの使用方法</span><span class="sxs-lookup"><span data-stu-id="86614-103">How to Use the Administration and Monitoring Website</span></span>


<span data-ttu-id="86614-104">ヘルプデスクとも呼ばれる管理と監視の Web サイトは、BitLocker ドライブ暗号化の管理インターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="86614-104">The Administration and Monitoring Website, also referred to as the Help Desk, is an administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="86614-105">次のセクションで説明するように、この web サイトを使用して、レポートの確認、エンドユーザーのドライブの回復、エンドユーザーの TPMs の管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="86614-105">Use the website to review reports, recover end users’ drives, and manage end users’ TPMs, as described in the following sections.</span></span>

<span data-ttu-id="86614-106">**注** スタンドアロントポロジで MBAM を使用している場合は、管理と監視の Web サイトからすべてのレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="86614-106">**Note** If you are using MBAM in the Stand-alone topology, you view all reports from the Administration and Monitoring Website.</span></span> <span data-ttu-id="86614-107">Configuration Manager の統合トポロジを使用している場合は、管理と監視の Web サイトから引き続き表示される回復監査レポートを除き、すべてのレポートを Configuration Manager で表示します。</span><span class="sxs-lookup"><span data-stu-id="86614-107">If you are using the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit report, which you continue to view from the Administration and Monitoring Website.</span></span> <span data-ttu-id="86614-108">レポートの詳細については、「 [MBAM 2.5 による BitLocker 準拠の監視と報告](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="86614-108">For more information about reports, see [Monitoring and Reporting BitLocker Compliance with MBAM 2.5](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md).</span></span>

 

## <span data-ttu-id="86614-109">管理と監視の Web サイトを使用するために必要な役割</span><span class="sxs-lookup"><span data-stu-id="86614-109">Required roles for using the Administration and Monitoring Website</span></span>


<span data-ttu-id="86614-110">管理と監視の Web サイトの特定の領域にアクセスするには、次のいずれかのロールを持っている必要があります。これらは、Active Directory で作成したグループです。</span><span class="sxs-lookup"><span data-stu-id="86614-110">To access specific areas of the Administration and Monitoring Website, you must have one of the following roles, which are groups that you create in Active Directory.</span></span> <span data-ttu-id="86614-111">これらのグループには任意の名前を使用できます。</span><span class="sxs-lookup"><span data-stu-id="86614-111">You can use any name for these groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86614-112">Account</span><span class="sxs-lookup"><span data-stu-id="86614-112">Account</span></span></th>
<th align="left"><span data-ttu-id="86614-113">説明</span><span class="sxs-lookup"><span data-stu-id="86614-113">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86614-114">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="86614-114">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-115">管理と監視の Web サイトのすべての領域へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86614-115">Provides access to all areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="86614-116">このロールを持っているユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーのみを入力します。</span><span class="sxs-lookup"><span data-stu-id="86614-116">Users who have this role enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="86614-117">MBAM ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのユーザーグループの権限よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="86614-117">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86614-118">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="86614-118">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-119">管理と監視の Web サイトの TPM およびドライブの回復領域へのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86614-119">Provides access to the Manage TPM and Drive Recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="86614-120">この役割を持つユーザーは、いずれかの領域を使用する場合は、エンドユーザーのドメインとアカウント名を含むすべてのフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="86614-120">Individuals who have this role must fill in all fields, including the end-user’s domain and account name, when they use either area.</span></span></p>
<p><span data-ttu-id="86614-121">MBAM ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのユーザーグループの権限よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="86614-121">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86614-122">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="86614-122">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-123"><strong> </strong> 管理と監視の web サイトの [レポート] 領域にあるレポートへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86614-123">Provides access to the reports in the <strong>Reports</strong> area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="86614-124">管理と監視の Web サイトで実行できるタスク</span><span class="sxs-lookup"><span data-stu-id="86614-124">Tasks you can perform on the Administration and Monitoring Website</span></span>


<span data-ttu-id="86614-125">次の表は、管理と監視の Web サイトで実行できるタスクの概要と、各タスクに関する詳細情報へのリンクを示しています。</span><span class="sxs-lookup"><span data-stu-id="86614-125">The following table summarizes the tasks you can perform on the Administration and Monitoring Website and provides links to more information about each task.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86614-126">タスク</span><span class="sxs-lookup"><span data-stu-id="86614-126">Task</span></span></th>
<th align="left"><span data-ttu-id="86614-127">タスクにアクセスする Web サイトの領域</span><span class="sxs-lookup"><span data-stu-id="86614-127">Area of the Website where you access the task</span></span></th>
<th align="left"><span data-ttu-id="86614-128">説明</span><span class="sxs-lookup"><span data-stu-id="86614-128">Description</span></span></th>
<th align="left"><span data-ttu-id="86614-129">詳細情報</span><span class="sxs-lookup"><span data-stu-id="86614-129">For more information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86614-130">レポートの表示</span><span class="sxs-lookup"><span data-stu-id="86614-130">View reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-131">レポート</span><span class="sxs-lookup"><span data-stu-id="86614-131">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-132">レポートを実行して、BitLocker の使用率、コンプライアンス、およびキー回復アクティビティを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="86614-132">Enables you to run reports to monitor BitLocker usage, compliance, and key recovery activity.</span></span> <span data-ttu-id="86614-133">レポートには、企業のコンプライアンス、個々のコンピューター、特定のコンピューターの回復キーまたは TPM OwnerAuth パッケージを要求したユーザーに関するデータが用意されています。</span><span class="sxs-lookup"><span data-stu-id="86614-133">Reports provide data about enterprise compliance, individual computers, and who requested recovery keys or the TPM OwnerAuth package for a specific computer.</span></span></p></td>
<td align="left"><p><a href="viewing-mbam-25-reports-for-the-stand-alone-topology.md" data-raw-source="[Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md)"><span data-ttu-id="86614-134">MBAM 2.5 レポートの表示 (スタンドアロン トポロジ)</span><span class="sxs-lookup"><span data-stu-id="86614-134">Viewing MBAM 2.5 Reports for the Stand-alone Topology</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86614-135">紛失または盗難されたコンピューターの BitLocker 暗号化の状態を確認する</span><span class="sxs-lookup"><span data-stu-id="86614-135">Determine the BitLocker encryption status of lost or stolen computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-136">レポート</span><span class="sxs-lookup"><span data-stu-id="86614-136">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-137">コンピューターが紛失したり盗まれたりした場合に、ボリュームが暗号化されていたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="86614-137">Determine if a volume was encrypted if the computer is lost or stolen.</span></span></p></td>
<td align="left"><p><a href="how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md" data-raw-source="[How to Determine BitLocker Encryption State of Lost Computers](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)"><span data-ttu-id="86614-138">紛失したコンピューターの BitLocker 暗号化の状態を確認する方法</span><span class="sxs-lookup"><span data-stu-id="86614-138">How to Determine BitLocker Encryption State of Lost Computers</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86614-139">紛失したドライブを回復する</span><span class="sxs-lookup"><span data-stu-id="86614-139">Recover lost drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-140">ドライブの回復</span><span class="sxs-lookup"><span data-stu-id="86614-140">Drive Recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-141">次のようなドライブを回復します。</span><span class="sxs-lookup"><span data-stu-id="86614-141">Recover drives that are:</span></span></p>
<ul>
<li><p><span data-ttu-id="86614-142">回復モードの場合</span><span class="sxs-lookup"><span data-stu-id="86614-142">In recovery mode</span></span></p></li>
<li><p><span data-ttu-id="86614-143">が移動されました</span><span class="sxs-lookup"><span data-stu-id="86614-143">Have been moved</span></span></p></li>
<li><p><span data-ttu-id="86614-144">は破損しています</span><span class="sxs-lookup"><span data-stu-id="86614-144">Are corrupted</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><a href="how-to-recover-a-drive-in-recovery-mode-mbam-25.md" data-raw-source="[How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)"><span data-ttu-id="86614-145">回復モードでドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="86614-145">How to Recover a Drive in Recovery Mode</span></span></a></p></li>
<li><p><a href="how-to-recover-a-moved-drive-mbam-25.md" data-raw-source="[How to Recover a Moved Drive](how-to-recover-a-moved-drive-mbam-25.md)"><span data-ttu-id="86614-146">移動されたドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="86614-146">How to Recover a Moved Drive</span></span></a></p></li>
<li><p><a href="how-to-recover-a-corrupted-drive-mbam-25.md" data-raw-source="[How to Recover a Corrupted Drive](how-to-recover-a-corrupted-drive-mbam-25.md)"><span data-ttu-id="86614-147">破損しているドライブを回復する方法</span><span class="sxs-lookup"><span data-stu-id="86614-147">How to Recover a Corrupted Drive</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86614-148">TPM ロックアウトをリセットする</span><span class="sxs-lookup"><span data-stu-id="86614-148">Reset a TPM lockout</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-149">TPM を管理する</span><span class="sxs-lookup"><span data-stu-id="86614-149">Manage TPM</span></span></p></td>
<td align="left"><p><span data-ttu-id="86614-150">MBAM クライアントによって収集された TPM データへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="86614-150">Provides access to TPM data that has been collected by the MBAM Client.</span></span> <span data-ttu-id="86614-151">TPM ロックアウトでは、管理と監視の Web サイトを使って、必要なパスワードファイルを取得し、TPM のロックを解除します。</span><span class="sxs-lookup"><span data-stu-id="86614-151">In a TPM lockout, use the Administration and Monitoring Website to retrieve the necessary password file to unlock the TPM.</span></span></p></td>
<td align="left"><p><a href="how-to-reset-a-tpm-lockout-mbam-25.md" data-raw-source="[How to Reset a TPM Lockout](how-to-reset-a-tpm-lockout-mbam-25.md)"><span data-ttu-id="86614-152">TPM ロックアウトをリセットする方法</span><span class="sxs-lookup"><span data-stu-id="86614-152">How to Reset a TPM Lockout</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="86614-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="86614-153">Related topics</span></span>


[<span data-ttu-id="86614-154">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="86614-154">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="86614-155">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="86614-155">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="86614-156">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="86614-156">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="86614-157">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="86614-157">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





