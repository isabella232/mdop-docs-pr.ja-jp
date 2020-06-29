---
title: MBAM 2.0 の評価
description: MBAM 2.0 の評価
author: dansimp
ms.assetid: bfc77eec-0fd7-4fec-9c78-6870afa87152
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7be883f44f5f09a904f619972ae3e7c35261d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824737"
---
# <span data-ttu-id="48d09-103">MBAM 2.0 の評価</span><span class="sxs-lookup"><span data-stu-id="48d09-103">Evaluating MBAM 2.0</span></span>


<span data-ttu-id="48d09-104">Microsoft BitLocker の管理と監視 (MBAM) を運用環境に展開する前に、テスト環境で評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d09-104">Before deploying Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a test environment.</span></span> <span data-ttu-id="48d09-105">このトピックに記載されている情報を使用して、評価目的のみを対象とした単一サーバーのテスト環境で、スタンドアロンのトポロジを使用して Microsoft BitLocker の管理と監視を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="48d09-105">The information in this topic can be used to set up Microsoft BitLocker Administration and Monitoring with a Stand-alone topology in a single-server test environment for evaluation purposes only.</span></span> <span data-ttu-id="48d09-106">運用環境では、単一サーバートポロジは推奨されません。</span><span class="sxs-lookup"><span data-stu-id="48d09-106">A single-server topology is not recommended for production environments.</span></span>

<span data-ttu-id="48d09-107">テスト環境に MBAM を導入する方法については、「 [MBAM を1台のサーバーにインストールして構成する方法](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48d09-107">For instructions on deploying MBAM in a test environment, see [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md).</span></span>

## <span data-ttu-id="48d09-108">テスト環境のセットアップ</span><span class="sxs-lookup"><span data-stu-id="48d09-108">Setting up the Test Environment</span></span>


<span data-ttu-id="48d09-109">テスト環境で評価するために MBAM の非運用インスタンスを設定する場合でも、前提条件とハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d09-109">Even though you are setting up a non-production instance of MBAM to evaluate in a test environment, you should still verify that you have met the prerequisites and hardware and software requirements.</span></span> <span data-ttu-id="48d09-110">インストールを開始する前に、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)、 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」、「 [Mbam 2.0 用の環境の準備](preparing-your-environment-for-mbam-20-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48d09-110">Before you start the installation, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md), [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md), and [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md).</span></span>

### <span data-ttu-id="48d09-111">MBAM 評価版の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="48d09-111">Plan for an MBAM Evaluation Deployment</span></span>

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
<th align="left"><span data-ttu-id="48d09-112">タスク</span><span class="sxs-lookup"><span data-stu-id="48d09-112">Task</span></span></th>
<th align="left"><span data-ttu-id="48d09-113">参照先</span><span class="sxs-lookup"><span data-stu-id="48d09-113">References</span></span></th>
<th align="left"><span data-ttu-id="48d09-114">備考</span><span class="sxs-lookup"><span data-stu-id="48d09-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-115">展開計画を開始する前に、MBAM の概要情報を確認して、製品について基本的な理解を深めてください。</span><span class="sxs-lookup"><span data-stu-id="48d09-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before beginning deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-20-mbam-2.md" data-raw-source="[Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md)"><span data-ttu-id="48d09-116">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="48d09-116">Getting Started with MBAM 2.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-117">MBAM 2.0 の展開前提条件を計画し、コンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="48d09-117">Plan for MBAM 2.0 Deployment Prerequisites and prepare your computing environment.</span></span></p></td>
<td align="left"><p><a href="mbam-20-deployment-prerequisites-mbam-2.md" data-raw-source="[MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md)"><span data-ttu-id="48d09-118">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="48d09-118">MBAM 2.0 Deployment Prerequisites</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-119">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="48d09-119">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="48d09-120">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="48d09-120">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-121">必要な ActiveDirectoryDomainServices セキュリティグループの計画と作成を行い、MBAM ローカルセキュリティグループメンバーシップの要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="48d09-121">Plan for and create necessary ActiveDirectoryDomainServices security groups, and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="48d09-122">MBAM 2.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="48d09-122">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-123">MBAM サーバー機能の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="48d09-123">Plan for deploying MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-server-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md)"><span data-ttu-id="48d09-124">MBAM 2.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="48d09-124">Planning for MBAM 2.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-125">MBAM クライアント展開の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="48d09-125">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="48d09-126">MBAM 2.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="48d09-126">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="48d09-127">MBAM 評価版の展開を実行する</span><span class="sxs-lookup"><span data-stu-id="48d09-127">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="48d09-128">MBAM のインストールのために、必要な計画とソフトウェアの前提条件のインストールが完了したら、MBAM 評価の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="48d09-128">After completing the necessary planning and software prerequisite installations to prepare your computing environment for the MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-129">MBAM でサポートされている構成情報を確認して、使用しているクライアントコンピューターおよびサーバーコンピューターで MBAM 機能のインストールがサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="48d09-129">Review the MBAM supported configurations information to make sure that selected client and server computers are supported for MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"><span data-ttu-id="48d09-130">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="48d09-130">MBAM 2.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-131">MBAM セットアップを実行して、評価目的で MBAM Server 機能を1台のサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="48d09-131">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-2.md)"><span data-ttu-id="48d09-132">単一サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="48d09-132">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-133">計画段階で作成した ActiveDirectoryDomainServices セキュリティグループを、新しい MBAM サーバー上の適切なローカルの MBAM サーバー機能ローカルグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="48d09-133">Add ActiveDirectoryDomainServices security groups, that you created during the planning phase, to the appropriate local MBAM Server feature local groups on the new MBAM Server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="48d09-134">MBAM 2.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)"> Mbam 管理者ロールの管理方法</span><span class="sxs-lookup"><span data-stu-id="48d09-134">Planning for MBAM 2.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-2.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-135">必要な MBAM グループポリシーオブジェクトを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="48d09-135">Create and deploy required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-20-group-policy-objects-mbam-2.md" data-raw-source="[Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md)"><span data-ttu-id="48d09-136">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="48d09-136">Deploying MBAM 2.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="48d09-137">MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="48d09-137">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-20-client-mbam-2.md" data-raw-source="[Deploying the MBAM 2.0 Client](deploying-the-mbam-20-client-mbam-2.md)"><span data-ttu-id="48d09-138">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="48d09-138">Deploying the MBAM 2.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="48d09-139">MBAM 評価用にラボコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="48d09-139">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="48d09-140">このセクションには、MBAM クライアントステータスレポートの速度を向上させるために使用できる情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="48d09-140">This section contains information that can be used to speed up the MBAM Client status reporting.</span></span> <span data-ttu-id="48d09-141">ただし、これらの変更はテスト目的でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="48d09-141">However, these modifications should be used for testing purposes only.</span></span>

<span data-ttu-id="48d09-142">**注** 以下のセクションでは、Windows レジストリの変更方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="48d09-142">**Note** The information in following section describes how to modify the Windows registry.</span></span> <span data-ttu-id="48d09-143">レジストリエディターを誤って使用すると、Windows の再インストールが必要になる深刻な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="48d09-143">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="48d09-144">Microsoft は、レジストリエディターの不正使用によって発生した問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="48d09-144">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="48d09-145">レジストリエディターは、各自の責任において使用してください。</span><span class="sxs-lookup"><span data-stu-id="48d09-145">Use Registry Editor at your own risk.</span></span>

 

### <span data-ttu-id="48d09-146">MBAM クライアントステータスレポートの頻度の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="48d09-146">Modify MBAM Client Status Reporting Frequency Settings</span></span>

<span data-ttu-id="48d09-147">MBAM クライアントのスリープ解除とステータスレポートの頻度は、グループポリシーを使用して設定した場合、最小値で90分に設定されます。</span><span class="sxs-lookup"><span data-stu-id="48d09-147">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set using Group Policy.</span></span> <span data-ttu-id="48d09-148">Windows レジストリを使用して、MBAM クライアントコンピューターでこれらの頻度を小さい値に変更して、テスト速度を向上させることができます。</span><span class="sxs-lookup"><span data-stu-id="48d09-148">You can use the Windows registry to change these frequencies to a lower value on MBAM client computers to help speed up testing.</span></span>

<span data-ttu-id="48d09-149">MBAM クライアントステータスレポートの頻度の設定を変更するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="48d09-149">To modify the MBAM Client status reporting frequency settings:</span></span>

1.  <span data-ttu-id="48d09-150">レジストリエディターを使用して**HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**に移動します。</span><span class="sxs-lookup"><span data-stu-id="48d09-150">Use a registry editor to navigate to **HKLM\\Software\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement**.</span></span>

2.  <span data-ttu-id="48d09-151">最小クライアントサポート値として、 **ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に変更します。</span><span class="sxs-lookup"><span data-stu-id="48d09-151">Change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client-supported value.</span></span> <span data-ttu-id="48d09-152">この変更により、MBAM クライアントは分ごとに報告されます。</span><span class="sxs-lookup"><span data-stu-id="48d09-152">This change causes the MBAM Client to report every minute.</span></span>

3.  <span data-ttu-id="48d09-153">**BitLocker 管理クライアントサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="48d09-153">Restart **BitLocker Management Client Service**.</span></span>

<span data-ttu-id="48d09-154">**注** この低い値を設定するには、レジストリで手動で設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48d09-154">**Note** To set values that are this low, you must set them in the registry manually.</span></span>

 

### <span data-ttu-id="48d09-155">MBAM クライアントサービスの起動遅延を変更する</span><span class="sxs-lookup"><span data-stu-id="48d09-155">Modify MBAM Client Service Startup Delay</span></span>

<span data-ttu-id="48d09-156">MBAM クライアントのスリープとステータスレポートの頻度に加えて、MBAM クライアントエージェントサービスがクライアントコンピューターで開始されると、最大90分のランダムな遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="48d09-156">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="48d09-157">ランダム遅延を発生させたくない場合は、 **DWORD**値 " **nostartupdelay** of **HKLM\\Software\\Microsoft\\MBAM**" を作成し、その値を**1**に設定してから、 **BitLocker 管理クライアントサービス**を再起動します。</span><span class="sxs-lookup"><span data-stu-id="48d09-157">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart **BitLocker Management Client Service**.</span></span>

## <span data-ttu-id="48d09-158">関連トピック</span><span class="sxs-lookup"><span data-stu-id="48d09-158">Related topics</span></span>


[<span data-ttu-id="48d09-159">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="48d09-159">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





