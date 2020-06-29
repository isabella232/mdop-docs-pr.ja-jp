---
title: MBAM 2.5 データベースを構成する方法
description: MBAM 2.5 データベースを構成する方法
author: dansimp
ms.assetid: 66e1c81b-f785-4398-9175-bb5f112c2a35
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c11cb58d8fd9266bd0322e4cf9aa96256b7fbb6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826624"
---
# <span data-ttu-id="46f6b-103">MBAM 2.5 データベースを構成する方法</span><span class="sxs-lookup"><span data-stu-id="46f6b-103">How to Configure the MBAM 2.5 Databases</span></span>


<span data-ttu-id="46f6b-104">このトピックでは、次の機能を使用して、Microsoft BitLocker 管理および監視 (MBAM) 2.5 コンプライアンスと監査データベースおよび回復データベースを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-104">This topic explains how to configure the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Compliance and Audit Database and the Recovery Database by using:</span></span>

-   <span data-ttu-id="46f6b-105">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="46f6b-105">A Windows PowerShell cmdlet</span></span>

-   <span data-ttu-id="46f6b-106">MBAM サーバー構成ウィザード</span><span class="sxs-lookup"><span data-stu-id="46f6b-106">The MBAM Server Configuration wizard</span></span>

<span data-ttu-id="46f6b-107">手順は、 [MBAM 2.5 の高レベルアーキテクチャ](high-level-architecture-for-mbam-25.md)の推奨アーキテクチャに基づいています。</span><span class="sxs-lookup"><span data-stu-id="46f6b-107">The instructions are based on the recommended architecture in [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md).</span></span>

**<span data-ttu-id="46f6b-108">構成を開始する前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="46f6b-108">Before you start the configuration:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="46f6b-109">ステップ</span><span class="sxs-lookup"><span data-stu-id="46f6b-109">Step</span></span></th>
<th align="left"><span data-ttu-id="46f6b-110">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="46f6b-110">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46f6b-111">MBAM の推奨アーキテクチャを確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-111">Review the recommended architecture for MBAM.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="46f6b-112">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="46f6b-112">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46f6b-113">MBAM のサポートされている構成を確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-113">Review the supported configurations for MBAM.</span></span></p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="46f6b-114">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="46f6b-114">MBAM 2.5 Supported Configurations</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46f6b-115">各サーバーに必要な前提条件を完了します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-115">Complete the required prerequisites on each server.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="46f6b-116">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="46f6b-116">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)"><span data-ttu-id="46f6b-117">MBAM 2.5 Server の前提条件構成マネージャーの統合トポロジにのみ適用されます </a> (該当する場合)。</span><span class="sxs-lookup"><span data-stu-id="46f6b-117">MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology</a> (if applicable)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46f6b-118">Mbam サーバー機能の構成を計画している各サーバーに MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-118">Install the MBAM Server software on each server where you plan to configure an MBAM Server feature.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="46f6b-119">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-119">Note</span></span></strong><br/><p><span data-ttu-id="46f6b-120">Windows PowerShell またはエクスポートされたデータ層アプリケーション (DAC) パッケージを使用して、リモートの SQL Server コンピューターにデータベースをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="46f6b-120">You can install the databases to a remote SQL Server computer by using Windows PowerShell or an exported data-tier application (DAC) package.</span></span> <span data-ttu-id="46f6b-121">DAC パッケージの詳細については、「 <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)"> データ層アプリケーション」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="46f6b-121">For more information about DAC packages, see <a href="https://technet.microsoft.com/library/ee210546.aspx" data-raw-source="[Data-tier Applications](https://technet.microsoft.com/library/ee210546.aspx)">Data-tier Applications</a>.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)"><span data-ttu-id="46f6b-122">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="46f6b-122">Installing the MBAM 2.5 Server Software</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46f6b-123">Windows powershell コマンドレットを使用して MBAM Server 機能を構成する場合は、Windows PowerShell を使用するための前提条件を確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-123">Review the prerequisites for using Windows PowerShell if you plan to use Windows PowerShell cmdlets to configure MBAM Server features.</span></span></p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"><span data-ttu-id="46f6b-124">Windows PowerShell を使用した MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="46f6b-124">Configuring MBAM 2.5 Server Features by Using Windows PowerShell</span></span></a></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="46f6b-125">Windows PowerShell を使用してデータベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="46f6b-125">To configure the databases by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="46f6b-126">構成を開始する前に、「Windows PowerShell を使用して Windows PowerShell を使用するための前提条件を確認する」を参照して、 [MBAM 2.5 Server の機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md)するを参照してください。</span><span class="sxs-lookup"><span data-stu-id="46f6b-126">Before you start the configuration, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md) to review the prerequisites for using Windows PowerShell.</span></span>

2.  <span data-ttu-id="46f6b-127">**Mbamamdatabase** Windows PowerShell コマンドレットを使用して、データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-127">Use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the databases.</span></span> <span data-ttu-id="46f6b-128">この Windows PowerShell コマンドレットに関する情報を取得するには、「 **get-ヘルプの有効化-MbamDatabase**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-128">To get information about this Windows PowerShell cmdlet, type **Get-Help Enable-MbamDatabase**.</span></span>

**<span data-ttu-id="46f6b-129">ウィザードを使用してコンプライアンスデータベースおよび監査データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="46f6b-129">To configure the Compliance and Audit Database by using the wizard</span></span>**

1. <span data-ttu-id="46f6b-130">データベースを構成するサーバーで、 **Mbam サーバー構成**ウィザードを起動します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-130">On the server where you want to configure the databases, start the **MBAM Server Configuration** wizard.</span></span> <span data-ttu-id="46f6b-131">[**スタート**] メニューから [ **Mbam Server 構成**] を選択して、ウィザードを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="46f6b-131">You can select **MBAM Server Configuration** from the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="46f6b-132">[**新しい機能の追加**] をクリックし、[**コンプライアンスと監査データベース**および**データベース復元**] を選択して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-132">Click **Add New Features**, select **Compliance and Audit Database** and **Recovery Database**, and then click **Next**.</span></span> <span data-ttu-id="46f6b-133">ウィザードは、データベースのすべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-133">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="46f6b-134">前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-134">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="46f6b-135">それ以外の場合は、不足している前提条件を解決し、[**前提条件の確認] をもう一度**クリックします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-135">Otherwise, resolve any missing prerequisites, and then click **Check prerequisites again**.</span></span>

4. <span data-ttu-id="46f6b-136">次の説明を使用して、ウィザードにフィールド値を入力します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-136">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="46f6b-137">フィールド</span><span class="sxs-lookup"><span data-stu-id="46f6b-137">Field</span></span></th>
   <th align="left"><span data-ttu-id="46f6b-138">説明</span><span class="sxs-lookup"><span data-stu-id="46f6b-138">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="46f6b-139">SQL Server 名</span><span class="sxs-lookup"><span data-stu-id="46f6b-139">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-140">コンプライアンスと監査データベースを構成しているサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="46f6b-140">Name of the server where you are configuring the Compliance and Audit Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="46f6b-141">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-141">Note</span></span></strong><br/><p><span data-ttu-id="46f6b-142">Microsoft SQL Server ポートで受信トラフィックを有効にするには、コンプライアンスおよび監査データベースコンピューターで例外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-142">You must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="46f6b-143">既定のポート番号は1433です。</span><span class="sxs-lookup"><span data-stu-id="46f6b-143">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="46f6b-144">SQL Server データベースインスタンス</span><span class="sxs-lookup"><span data-stu-id="46f6b-144">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-145">コンプライアンスと監査データが保存されるデータベースインスタンスの名前です。</span><span class="sxs-lookup"><span data-stu-id="46f6b-145">Name of the database instance where the compliance and audit data will be stored.</span></span> <span data-ttu-id="46f6b-146">データベース情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-146">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="46f6b-147">データベース名</span><span class="sxs-lookup"><span data-stu-id="46f6b-147">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-148">コンプライアンスデータを格納するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="46f6b-148">Name of the database that will store the compliance data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="46f6b-149">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-149">Note</span></span></strong><br/><p><span data-ttu-id="46f6b-150">以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-150">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="46f6b-151">読み取り/書き込みアクセスドメインユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="46f6b-151">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-152">このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。このデータベースのデータとレポートにアクセスできるように、web アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-152">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="46f6b-153">このフィールドにユーザーを入力する場合は、[ <strong> </strong> <strong> web アプリケーションの構成] ページの [web サービスアプリケーションプールドメインアカウント] フィールドの値と同じ値である必要があり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="46f6b-153">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="46f6b-154">このフィールドにグループを入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-154">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="46f6b-155">読み取り専用アクセスドメインのユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="46f6b-155">Read-only access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-156">このデータベースに読み取り専用のアクセス許可が与えられているユーザーまたはグループの名前。レポートがこのデータベースのコンプライアンスデータにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-156">Name of the user or group that will have read-only permission to this database to enable the reports to access the compliance data in this database.</span></span></p>
   <p><span data-ttu-id="46f6b-157">このフィールドにユーザーを入力する場合は、[ <strong> </strong> レポートの構成] ページの [コンプライアンスおよび監査データベースドメインアカウント] フィールドで指定したユーザーと同じユーザーである必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="46f6b-157">If you enter a user in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
   <p><span data-ttu-id="46f6b-158">このフィールドにグループを入力した場合、[ <strong> レポートの構成] ページの [コンプライアンスと監査データベースのドメインアカウント] フィールドで指定した値は、 </strong> <strong> </strong> このフィールドで指定したグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-158">If you enter a group in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



5. <span data-ttu-id="46f6b-159">次のセクションに進み、回復用データベースを構成します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-159">Continue to the next section to configure the Recovery Database.</span></span>

**<span data-ttu-id="46f6b-160">ウィザードを使用して回復データベースを構成するには</span><span class="sxs-lookup"><span data-stu-id="46f6b-160">To configure the Recovery Database by using the wizard</span></span>**

1. <span data-ttu-id="46f6b-161">次の説明を使用して、ウィザードにフィールド値を入力します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-161">Using the following descriptions, enter the field values in the wizard:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="46f6b-162">フィールド</span><span class="sxs-lookup"><span data-stu-id="46f6b-162">Field</span></span></th>
   <th align="left"><span data-ttu-id="46f6b-163">説明</span><span class="sxs-lookup"><span data-stu-id="46f6b-163">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="46f6b-164">SQL Server 名</span><span class="sxs-lookup"><span data-stu-id="46f6b-164">SQL Server name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-165">回復用データベースを構成するサーバーの名前。</span><span class="sxs-lookup"><span data-stu-id="46f6b-165">Name of the server where you are configuring the Recovery Database.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="46f6b-166">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-166">Note</span></span></strong><br/><p><span data-ttu-id="46f6b-167">Microsoft SQL Server ポートで受信トラフィックを有効にするには、回復データベースコンピューターで例外を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-167">You must add an exception on the Recovery Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="46f6b-168">既定のポート番号は1433です。</span><span class="sxs-lookup"><span data-stu-id="46f6b-168">The default port number is 1433.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="46f6b-169">SQL Server データベースインスタンス</span><span class="sxs-lookup"><span data-stu-id="46f6b-169">SQL Server database instance</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-170">回復データが保存されるデータベースインスタンスの名前。</span><span class="sxs-lookup"><span data-stu-id="46f6b-170">Name of the database instance where the recovery data will be stored.</span></span> <span data-ttu-id="46f6b-171">データベース情報を配置する場所も指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-171">You must also specify where the database information will be located.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="46f6b-172">データベース名</span><span class="sxs-lookup"><span data-stu-id="46f6b-172">Database name</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-173">回復データを格納するデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="46f6b-173">Name of the database that will store the recovery data.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="46f6b-174">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-174">Note</span></span></strong><br/><p><span data-ttu-id="46f6b-175">以前のバージョンの MBAM からアップグレードする場合は、前の展開で使用した名前と同じデータベース名を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-175">If you are upgrading from a previous version of MBAM, you must use the same database name as the name that was used in your previous deployment.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="46f6b-176">読み取り/書き込みアクセスドメインユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="46f6b-176">Read/write access domain user or group</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="46f6b-177">このデータベースの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。このデータベースのデータとレポートにアクセスできるように、web アプリケーションを有効にします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-177">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span></p>
   <p><span data-ttu-id="46f6b-178">このフィールドにユーザーを入力する場合は、[ <strong> </strong> <strong> web アプリケーションの構成] ページの [web サービスアプリケーションプールドメインアカウント] フィールドの値と同じ値である必要があり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="46f6b-178">If you enter a user in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
   <p><span data-ttu-id="46f6b-179">このフィールドにグループを入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="46f6b-179">If you enter a group in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="46f6b-180">入力が完了したら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-180">When you finish your entries, click **Next**.</span></span>

   <span data-ttu-id="46f6b-181">ウィザードは、データベースのすべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-181">The wizard checks that all prerequisites for the databases have been met.</span></span>

3. <span data-ttu-id="46f6b-182">前提条件の確認が正常に完了したら、[**次へ**] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-182">If the prerequisite check is successful, click **Next** to continue.</span></span> <span data-ttu-id="46f6b-183">それ以外の場合は、不足している前提条件を解決して、[**次へ**] をもう一度クリックします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-183">Otherwise, resolve any missing prerequisites, and then click **Next** again.</span></span>

4. <span data-ttu-id="46f6b-184">[**概要**] ページで、追加される機能を確認します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-184">On the **Summary** page, review the features that will be added.</span></span>

   **<span data-ttu-id="46f6b-185">注</span><span class="sxs-lookup"><span data-stu-id="46f6b-185">Note</span></span>**  
   <span data-ttu-id="46f6b-186">直前に行ったエントリの Windows PowerShell スクリプトを作成するには、[ **PowerShell スクリプトのエクスポート**] をクリックし、スクリプトを保存します。</span><span class="sxs-lookup"><span data-stu-id="46f6b-186">To create a Windows PowerShell script of the entries that you just made, click **Export PowerShell Script**, and then save the script.</span></span>



5. <span data-ttu-id="46f6b-187">[**追加**] をクリックして、サーバー上に mbam データベースを追加し、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46f6b-187">Click **Add** to add the MBAM databases on the server, and then click **Close**.</span></span>



## <span data-ttu-id="46f6b-188">関連トピック</span><span class="sxs-lookup"><span data-stu-id="46f6b-188">Related topics</span></span>


[<span data-ttu-id="46f6b-189">サーバーのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="46f6b-189">Server Event Logs</span></span>](server-event-logs.md)

[<span data-ttu-id="46f6b-190">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="46f6b-190">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

[<span data-ttu-id="46f6b-191">MBAM 2.5 レポートを構成する方法</span><span class="sxs-lookup"><span data-stu-id="46f6b-191">How to Configure the MBAM 2.5 Reports</span></span>](how-to-configure-the-mbam-25-reports.md)

[<span data-ttu-id="46f6b-192">MBAM 2.5 Web アプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="46f6b-192">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

[<span data-ttu-id="46f6b-193">MBAM 2.5 サーバー機能の構成の確認</span><span class="sxs-lookup"><span data-stu-id="46f6b-193">Validating the MBAM 2.5 Server Feature Configuration</span></span>](validating-the-mbam-25-server-feature-configuration.md)



## <span data-ttu-id="46f6b-194">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="46f6b-194">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="46f6b-195">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="46f6b-195">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="46f6b-196">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="46f6b-196">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





