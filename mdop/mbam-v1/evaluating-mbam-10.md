---
title: MBAM 1.0 の評価
description: MBAM 1.0 の評価
author: dansimp
ms.assetid: a1e2b674-eda9-4e1c-9b4c-e748470c71f2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: f09b06af52f5738fd50bfe727987b760d98552d9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825254"
---
# <span data-ttu-id="e581c-103">MBAM 1.0 の評価</span><span class="sxs-lookup"><span data-stu-id="e581c-103">Evaluating MBAM 1.0</span></span>


<span data-ttu-id="e581c-104">Microsoft BitLocker の管理と監視 (MBAM) を運用環境に展開する前に、ラボ環境で評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-104">Before you deploy Microsoft BitLocker Administration and Monitoring (MBAM) into a production environment, you should evaluate it in a lab environment.</span></span> <span data-ttu-id="e581c-105">このトピックの情報を使用して、評価目的に限って、1つのサーバーラボ環境で MBAM を設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e581c-105">You can use the information in this topic to set up MBAM in a single server lab environment for evaluation purposes only.</span></span>

<span data-ttu-id="e581c-106">実際の展開手順は、「 [1 台のサーバーに MBAM をインストールして構成する方法](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)」で説明されているシナリオと非常に似ていますが、このトピックには、mbam 評価環境を最小限に設定できるようにするための追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="e581c-106">While the actual deployment steps are very similar to the scenario that is described in [How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md), this topic contains additional information to enable you to set up an MBAM evaluation environment in the least amount of time.</span></span>

## <span data-ttu-id="e581c-107">ラボ環境のセットアップ</span><span class="sxs-lookup"><span data-stu-id="e581c-107">Set up the Lab Environment</span></span>


<span data-ttu-id="e581c-108">テスト環境で評価するために MBAM の非運用インスタンスを設定する場合でも、展開の前提条件とハードウェアとソフトウェアの要件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-108">Even when you set up a non-production instance of MBAM to evaluate in a lab environment, you should still verify that you have met the deployment prerequisites and the hardware and software requirements.</span></span> <span data-ttu-id="e581c-109">詳細については、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e581c-109">For more information, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="e581c-110">MBAM 評価版の展開を始める前に、 [mbam 1.0 の環境の準備](preparing-your-environment-for-mbam-10.md)も確認しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-110">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM evaluation deployment.</span></span>

### <span data-ttu-id="e581c-111">MBAM 評価版の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="e581c-111">Plan for an MBAM Evaluation Deployment</span></span>

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
<th align="left"><span data-ttu-id="e581c-112">タスク</span><span class="sxs-lookup"><span data-stu-id="e581c-112">Task</span></span></th>
<th align="left"><span data-ttu-id="e581c-113">参照先</span><span class="sxs-lookup"><span data-stu-id="e581c-113">References</span></span></th>
<th align="left"><span data-ttu-id="e581c-114">備考</span><span class="sxs-lookup"><span data-stu-id="e581c-114">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-115">展開計画を開始する前に、MBAM の概要情報を確認して、製品について基本的な理解を深めてください。</span><span class="sxs-lookup"><span data-stu-id="e581c-115">Review the Getting Started information about MBAM to gain a basic understanding of the product before you begin your deployment planning.</span></span></p></td>
<td align="left"><p><a href="getting-started-with-mbam-10.md" data-raw-source="[Getting Started with MBAM 1.0](getting-started-with-mbam-10.md)"><span data-ttu-id="e581c-116">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="e581c-116">Getting Started with MBAM 1.0</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p></p>
<p><span data-ttu-id="e581c-117">MBAM インストール用にコンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="e581c-117">Prepare your computing environment for the MBAM installation.</span></span> <span data-ttu-id="e581c-118">これを行うには、MBAM データベースをホストする SQL Server インスタンスで、透過データ暗号化 (TDE) を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-118">To do so, you must enable the Transparent Data Encryption (TDE) on the SQL Server instances that will host MBAM databases.</span></span> <span data-ttu-id="e581c-119">ラボ環境で TDE を有効にするには、MBAM が使用する SQL Server のインスタンスでホストされている master データベースに対して実行する .sql ファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="e581c-119">To enable TDE in your lab environment, you can create a .sql file to run against the master database that is hosted on the instance of the SQL Server that MBAM will use.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e581c-120">注</span><span class="sxs-lookup"><span data-stu-id="e581c-120">Note</span></span></strong><br/><p><span data-ttu-id="e581c-121">次の例を使用して、使用しているラボ環境の .sql ファイルを作成して、MBAM データベースをホストする SQL Server インスタンスの TDE をすばやく有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="e581c-121">You can use the following example to create a .sql file for your lab environment to quickly enable TDE on the SQL Server instance that will host the MBAM databases.</span></span> <span data-ttu-id="e581c-122">これらの SQL Server コマンドは、ローカルに署名された SQL Server 証明書を使用して、TDE を有効にします。</span><span class="sxs-lookup"><span data-stu-id="e581c-122">These SQL Server commands will enable TDE by using a locally signed SQL Server certificate.</span></span> <span data-ttu-id="e581c-123">TDE 証明書とそれに関連付けられた暗号化キーを、C:\Backup のローカルバックアップパスの例にバックアップしてください <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="e581c-123">Make sure to back up the TDE certificate and its associated encryption key to the example local backup path of <em>C:\Backup</em>.</span></span> <span data-ttu-id="e581c-124">データベースを復元する場合、または、証明書とキーを TDE 暗号化が設定されている別のサーバーに移動する場合は、TDE 証明書とキーが必要です。</span><span class="sxs-lookup"><span data-stu-id="e581c-124">The TDE certificate and key are required when recover the database or move the certificate and key to another server that has TDE encryption in place.</span></span></p>
</div>
<div>

</div>
<pre class="syntax" space="preserve"><code>USE master;
GO
CREATE MASTER KEY ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;;
GO
CREATE CERTIFICATE tdeCert WITH SUBJECT = &#39;TDE Certificate&#39;;
GO
BACKUP CERTIFICATE tdeCert TO FILE = &#39;C:\Backup\TDECertificate.cer&#39;
   WITH PRIVATE KEY (
         FILE = &#39;C:\Backup\TDECertificateKey.pvk&#39;,
         ENCRYPTION BY PASSWORD = &#39;P@55w0rd&#39;);
GO</code></pre></td>
<td align="left"><p><a href="mbam-10-deployment-prerequisites.md" data-raw-source="[MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md)"><span data-ttu-id="e581c-125">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="e581c-125">MBAM 1.0 Deployment Prerequisites</span></span></a></p>
<p><a href="https://go.microsoft.com/fwlink/?LinkId=269703" data-raw-source="[Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703)"><span data-ttu-id="e581c-126">SQL Server 2008 Enterprise Edition のデータベース暗号化</span><span class="sxs-lookup"><span data-stu-id="e581c-126">Database Encryption in SQL Server 2008 Enterprise Edition</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-127">MBAM グループポリシー要件を計画して構成します。</span><span class="sxs-lookup"><span data-stu-id="e581c-127">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-group-policy-requirements.md" data-raw-source="[Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md)"><span data-ttu-id="e581c-128">MBAM 1.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="e581c-128">Planning for MBAM 1.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-129">必要な Active Directory ドメインサービスセキュリティグループを計画して作成し、MBAM ローカルセキュリティグループのメンバーシップ要件を計画します。</span><span class="sxs-lookup"><span data-stu-id="e581c-129">Plan for and create the necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="e581c-130">MBAM 1.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="e581c-130">Planning for MBAM 1.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-131">MBAM サーバー機能の展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="e581c-131">Plan for MBAM Server feature deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-server-deployment.md" data-raw-source="[Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md)"><span data-ttu-id="e581c-132">MBAM 1.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="e581c-132">Planning for MBAM 1.0 Server Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-133">MBAM クライアントの展開を計画します。</span><span class="sxs-lookup"><span data-stu-id="e581c-133">Plan for MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-client-deployment.md" data-raw-source="[Planning for MBAM 1.0 Client Deployment](planning-for-mbam-10-client-deployment.md)"><span data-ttu-id="e581c-134">MBAM 1.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="e581c-134">Planning for MBAM 1.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="e581c-135">MBAM 評価版の展開を実行する</span><span class="sxs-lookup"><span data-stu-id="e581c-135">Perform an MBAM Evaluation Deployment</span></span>

<span data-ttu-id="e581c-136">MBAM のインストールのために、必要な計画とソフトウェアの前提条件のインストールが完了したら、MBAM 評価の展開を開始できます。</span><span class="sxs-lookup"><span data-stu-id="e581c-136">After you complete the necessary planning and software prerequisite installations to prepare your computing environment for an MBAM installation, you can begin the MBAM evaluation deployment.</span></span>

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
<td align="left"><p><span data-ttu-id="e581c-137">MBAM でサポートされている構成情報を確認して、使用しているクライアントとサーバーコンピューターが MBAM 機能のインストールでサポートされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="e581c-137">Review the MBAM supported configurations information to make sure that the selected client and server computers are supported for the MBAM feature installation.</span></span></p></td>
<td align="left"><p><a href="mbam-10-supported-configurations.md" data-raw-source="[MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md)"><span data-ttu-id="e581c-138">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="e581c-138">MBAM 1.0 Supported Configurations</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-139">MBAM セットアップを実行して、評価目的で MBAM Server 機能を1台のサーバーに展開します。</span><span class="sxs-lookup"><span data-stu-id="e581c-139">Run MBAM Setup to deploy MBAM Server features on a single server for evaluation purposes.</span></span></p></td>
<td align="left"><p><a href="how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md" data-raw-source="[How to Install and Configure MBAM on a Single Server](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)"><span data-ttu-id="e581c-140">単一サーバーに MBAM をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="e581c-140">How to Install and Configure MBAM on a Single Server</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-141">計画フェーズで作成した Active Directory ドメインサービスセキュリティグループを、新しい MBAM サーバー上の適切なローカルの MBAM サーバー機能ローカルグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="e581c-141">Add the Active Directory Domain Services security groups that you created during the planning phase to the appropriate local MBAM Server feature local groups on the new MBAM server.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-10-administrator-roles.md" data-raw-source="[Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md)"><span data-ttu-id="e581c-142">MBAM 1.0 管理者ロールの計画 </a> と <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)"> Mbam 管理者ロールの管理方法</span><span class="sxs-lookup"><span data-stu-id="e581c-142">Planning for MBAM 1.0 Administrator Roles</a> and <a href="how-to-manage-mbam-administrator-roles-mbam-1.md" data-raw-source="[How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md)">How to Manage MBAM Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-143">必要な MBAM グループポリシーオブジェクトを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="e581c-143">Create and deploy the required MBAM Group Policy Objects.</span></span></p></td>
<td align="left"><p><a href="deploying-mbam-10-group-policy-objects.md" data-raw-source="[Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md)"><span data-ttu-id="e581c-144">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="e581c-144">Deploying MBAM 1.0 Group Policy Objects</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="e581c-145">MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="e581c-145">Deploy the MBAM Client software.</span></span></p></td>
<td align="left"><p><a href="deploying-the-mbam-10-client.md" data-raw-source="[Deploying the MBAM 1.0 Client](deploying-the-mbam-10-client.md)"><span data-ttu-id="e581c-146">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="e581c-146">Deploying the MBAM 1.0 Client</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="e581c-147">MBAM 評価用にラボコンピューターを構成する</span><span class="sxs-lookup"><span data-stu-id="e581c-147">Configure Lab Computers for MBAM Evaluation</span></span>


<span data-ttu-id="e581c-148">MBAM クライアントステータスレポートの頻度設定は、レジストリエディターを使って変更できます。</span><span class="sxs-lookup"><span data-stu-id="e581c-148">You can change the frequency settings on the MBAM Client status reporting by using Registry Editor.</span></span> <span data-ttu-id="e581c-149">ただし、これらの変更はテスト目的でのみ使用してください。</span><span class="sxs-lookup"><span data-stu-id="e581c-149">However, these modifications should be used for testing purposes only.</span></span>

**<span data-ttu-id="e581c-150">Warning</span><span class="sxs-lookup"><span data-stu-id="e581c-150">Warning</span></span>**  
<span data-ttu-id="e581c-151">このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="e581c-151">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="e581c-152">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-152">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="e581c-153">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="e581c-153">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="e581c-154">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="e581c-154">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="e581c-155">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="e581c-155">Change the registry at your own risk.</span></span>



### <a href="" id="modify-the-frequency-settings-on-mbam-client-status-reporting-"></a><span data-ttu-id="e581c-156">MBAM クライアントステータスレポートの頻度の設定を変更する</span><span class="sxs-lookup"><span data-stu-id="e581c-156">Modify the Frequency Settings on MBAM Client Status Reporting</span></span>

<span data-ttu-id="e581c-157">MBAM クライアントのスリープ解除とステータスレポートの頻度は、グループポリシーを使用するように設定されている場合、最小値で90分の値になります。</span><span class="sxs-lookup"><span data-stu-id="e581c-157">The MBAM Client wakeup and status reporting frequencies have a minimum value of 90 minutes when they are set to use Group Policy.</span></span> <span data-ttu-id="e581c-158">MBAM クライアントコンピューターでは、これらの頻度を変更することができます。これは、テストを高速化するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e581c-158">You can change these frequencies on MBAM client computers by editing the Windows registry to lower values, which will help speed up the testing.</span></span> <span data-ttu-id="e581c-159">MBAM クライアントステータスレポートの頻度の設定を変更するには、レジストリエディターを使用して**HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**に移動し、クライアントでサポートされている最小値として**ClientWakeupFrequency**と**statusreportingfrequency**の値を**1**に変更してから、BitLocker 管理クライアントサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e581c-159">To modify the frequency settings on MBAM Client status reporting, use a registry editor to navigate to **HKLM\\Software\\Policies\\FVE\\MDOPBitLockerManagement**, change the values for **ClientWakeupFrequency** and **StatusReportingFrequency** to **1** as the minimum client supported value, and then restart BitLocker Management Client Service.</span></span> <span data-ttu-id="e581c-160">この変更を行うと、MBAM クライアントでは1分ごとに報告されます。</span><span class="sxs-lookup"><span data-stu-id="e581c-160">When you make this change, the MBAM Client will report every minute.</span></span> <span data-ttu-id="e581c-161">レジストリで手動で設定する場合は、値を低に設定することができます。</span><span class="sxs-lookup"><span data-stu-id="e581c-161">You can set values this low only when you do so manually in the registry.</span></span>

### <a href="" id="modify-the-startup-delay-on-mbam-client-service-"></a><span data-ttu-id="e581c-162">MBAM クライアントサービスの起動遅延を変更する</span><span class="sxs-lookup"><span data-stu-id="e581c-162">Modify the Startup Delay on MBAM Client Service</span></span>

<span data-ttu-id="e581c-163">MBAM クライアントのスリープとステータスレポートの頻度に加えて、MBAM クライアントエージェントサービスがクライアントコンピューターで開始されると、最大90分のランダムな遅延が発生します。</span><span class="sxs-lookup"><span data-stu-id="e581c-163">In addition to the MBAM Client wakeup and status reporting frequencies, there is a random delay of up to 90 minutes when the MBAM Client agent service starts on client computers.</span></span> <span data-ttu-id="e581c-164">ランダム遅延を発生させたくない場合は、 **DWORD**値 " **nostartupdelay** of **HKLM\\Software\\Microsoft\\MBAM**" を作成し、その値を**1**に設定してから、BitLocker 管理クライアントサービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="e581c-164">If you do not want the random delay, create a **DWORD** value of **NoStartupDelay** under **HKLM\\Software\\Microsoft\\MBAM**, set its value to **1**, and then restart BitLocker Management Client Service.</span></span>

## <span data-ttu-id="e581c-165">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e581c-165">Related topics</span></span>


[<span data-ttu-id="e581c-166">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="e581c-166">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)









