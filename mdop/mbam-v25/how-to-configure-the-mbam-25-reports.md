---
title: MBAM 2.5 レポートを構成する方法
description: MBAM 2.5 レポートを構成する方法
author: dansimp
ms.assetid: ec462879-0253-4d9c-83c7-a9bcad479725
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b372bd6bc38a3729aef43354ecf19b2619b7856
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826617"
---
# <span data-ttu-id="6f7bd-103">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6f7bd-103">How to Configure the MBAM 2.5 Reports</span></span>


<span data-ttu-id="6f7bd-104">このトピックでは、次の機能を使用して、Microsoft BitLocker の管理と監視 (MBAM) 2.5 レポート機能を構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Reports feature by using:</span></span>

-   <span data-ttu-id="6f7bd-105">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6f7bd-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="6f7bd-106">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="6f7bd-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="6f7bd-107">手順は、 [MBAM 2.5 の高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)の推奨アーキテクチャに基づいています。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="6f7bd-108">構成を開始する前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6f7bd-109">ステップ</span><span class="sxs-lookup"><span data-stu-id="6f7bd-109">Step</span></span></th>
<th align="left"><span data-ttu-id="6f7bd-110">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="6f7bd-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f7bd-111">MBAM の推奨アーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="6f7bd-112">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="6f7bd-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f7bd-113">MBAM のサポートされている構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="6f7bd-114">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="6f7bd-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f7bd-115">各サーバーに必要な前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="6f7bd-116">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="6f7bd-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="6f7bd-117">MBAM 2.5 Server の前提条件構成マネージャーの統合トポロジにのみ適用されます </a> (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f7bd-118">Mbam サーバー機能の構成を計画している各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="6f7bd-119">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="6f7bd-119">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f7bd-120">Windows powershell コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-120">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="6f7bd-121">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="6f7bd-121">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="6f7bd-122">Windows PowerShell を使用してレポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="6f7bd-122">To configure the Reports by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="6f7bd-123">構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-123">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="6f7bd-124">**MbamReport** Windows PowerShell コマンドレットを使用して、レポートを構成します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-124">Use the **Enable-MbamReport** Windows PowerShell cmdlet to configure the Reports.</span></span> <span data-ttu-id="6f7bd-125">この Windows PowerShell コマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamReport**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-125">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamReport**.</span></span>

**<span data-ttu-id="6f7bd-126">ウィザードを使用してレポートを構成するには</span><span class="sxs-lookup"><span data-stu-id="6f7bd-126">To configure the Reports by using the wizard</span></span>**

1. <span data-ttu-id="6f7bd-127">レポートを構成するサーバーで、 **Mbam サーバー構成**ウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-127">On the server where you want to configure the Reports, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="6f7bd-128">[**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-128">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="6f7bd-129">[**新しい機能の追加**] をクリックし、[**レポート**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-129">Click **Add New Features**, select **Reports**, and then click **Next**.</span></span> <span data-ttu-id="6f7bd-130">ウィザードは、レポートのすべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-130">The wizard checks that all prerequisites for the Reports have been met.</span></span>

3. <span data-ttu-id="6f7bd-131">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-131">Click **Next** to continue.</span></span>

4. <span data-ttu-id="6f7bd-132">次の説明を使用して、ウィザードにフィールド値を入力します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-132">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="6f7bd-133">フィールド</span><span class="sxs-lookup"><span data-stu-id="6f7bd-133">Field</span></span></th>
   <th align="left"><span data-ttu-id="6f7bd-134">説明</span><span class="sxs-lookup"><span data-stu-id="6f7bd-134">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-135">SQL Server Reporting Services インスタンス</span><span class="sxs-lookup"><span data-stu-id="6f7bd-135">SQL Server Reporting Services instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-136">レポートが構成される SQL Server Reporting Services のインスタンス。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-136">Instance of SQL Server Reporting Services where the Reports will be configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-137">レポート役割のドメイングループ</span><span class="sxs-lookup"><span data-stu-id="6f7bd-137">Reporting role domain group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-138">管理および監視サーバー上のレポートにアクセスする権限がメンバーに付与されているドメインユーザーグループの名前。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-138">Name of the domain Users group whose members have rights to access the reports on the Administration and Monitoring Server.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-139">SQL Server 名</span><span class="sxs-lookup"><span data-stu-id="6f7bd-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-140">コンプライアンスと監査データベースが構成されているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-140">Name of the server where the Compliance and Audit Database is configured.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-141">SQL Server データベースインスタンス</span><span class="sxs-lookup"><span data-stu-id="6f7bd-141">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-142"><em> </em> コンプライアンスと監査データベースが構成されている SQL Server (MSSQLSERVER など) のインスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-142">Name of the instance of SQL Server (for example, <em>MSSQLSERVER</em>) where the Compliance and Audit Database is configured.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="6f7bd-143">注</span><span class="sxs-lookup"><span data-stu-id="6f7bd-143">Note</span></span></strong><br/><p><span data-ttu-id="6f7bd-144">レポートサーバーのポートで受信トラフィックを有効にするには、レポートコンピューターで例外を追加する必要があります (既定のポートは 80)。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-144">You must add an exception on the Reports computer to enable inbound traffic on the port of the Reporting Server (the default port is 80).</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-145">データベース名</span><span class="sxs-lookup"><span data-stu-id="6f7bd-145">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-146">コンプライアンスおよび監査データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-146">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="6f7bd-147">既定では、データベース名は <strong> mbam コンプライアンスの状態ですが、 </strong> コンプライアンスと監査データベースを構成するときに名前を変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-147">By default, the database name is <strong>MBAM Compliance Status</strong>, although you can change the name when you configure the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="6f7bd-148">注</span><span class="sxs-lookup"><span data-stu-id="6f7bd-148">Note</span></span></strong><br/><p><span data-ttu-id="6f7bd-149">以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-149">If you are upgrading from a previous version of MBAM, you must use the same database name as the name used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="6f7bd-150">コンプライアンスと監査データベースのドメインアカウント</span><span class="sxs-lookup"><span data-stu-id="6f7bd-150">Compliance and Audit Database domain account</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="6f7bd-151">コンプライアンスおよび監査データベースにアクセスするためのドメインユーザーアカウントとパスワード。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-151">Domain user account and password to access the Compliance and Audit Database.</span></span></p>
   <p><span data-ttu-id="6f7bd-152">[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値がユーザーの場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-152">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user, you must enter that same value in this field.</span></span></p>
   <p><span data-ttu-id="6f7bd-153">[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値 </strong> <strong> がグループの場合 </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-153">If the value that you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group, the value that you enter in this field must be a member of that group.</span></span></p>
   <p><span data-ttu-id="6f7bd-154">有効期限が切れないように、このアカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-154">Configure the password for this account to never expire.</span></span> <span data-ttu-id="6f7bd-155">ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-155">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="6f7bd-156">入力が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-156">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="6f7bd-157">ウィザードは、レポート機能のすべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-157">The wizard checks that all prerequisites for the Reports feature have been met.</span></span>

6. <span data-ttu-id="6f7bd-158">**[Next]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-158">Click **Next** to continue.</span></span>

7. <span data-ttu-id="6f7bd-159">[**概要**] ページで、追加される機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-159">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="6f7bd-160">注</span><span class="sxs-lookup"><span data-stu-id="6f7bd-160">Note</span></span>**  
   <span data-ttu-id="6f7bd-161">直前に行ったエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-161">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



8. <span data-ttu-id="6f7bd-162">[**追加**] をクリックして、サーバー上にレポートを追加し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-162">Click **Add** to add the Reports on the server, and then click **Close**.</span></span>



## <span data-ttu-id="6f7bd-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6f7bd-163">Related topics</span></span>


[<span data-ttu-id="6f7bd-164">サーバーのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="6f7bd-164">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="6f7bd-165">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="6f7bd-165">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="6f7bd-166">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="6f7bd-166">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="6f7bd-167">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="6f7bd-167">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)


## <span data-ttu-id="6f7bd-168">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-168">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="6f7bd-169">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-169">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="6f7bd-170">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="6f7bd-170">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






