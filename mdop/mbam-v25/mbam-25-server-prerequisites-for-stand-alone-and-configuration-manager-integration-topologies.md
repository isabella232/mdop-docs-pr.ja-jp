---
title: スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件
description: スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825997"
---
# <span data-ttu-id="64345-103">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-103">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span>


<span data-ttu-id="64345-104">Microsoft BitLocker の管理と監視 (MBAM) のインストールを開始する前に、このトピックで説明されている前提条件を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-104">Before starting the Microsoft BitLocker Administration and Monitoring (MBAM) installation, you must complete the prerequisites listed in this topic.</span></span> <span data-ttu-id="64345-105">これらの前提条件は、MBAM スタンドアロントポロジと System Center Configuration Manager の統合トポロジに適用されます。</span><span class="sxs-lookup"><span data-stu-id="64345-105">These prerequisites apply to the MBAM Stand-alone topology and System Center Configuration Manager Integration topology.</span></span>

<span data-ttu-id="64345-106">System Center Configuration Manager を使用して MBAM を展開する場合は、「Mbam 2.5 Server の前提条件」で示されている、[構成マネージャーの統合トポロジにのみ適用](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)される追加の前提条件を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-106">If you are deploying MBAM with System Center Configuration Manager, you must complete additional prerequisites, which are listed in [MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="64345-107">MBAM でサポートされているハードウェアとオペレーティングシステムの一覧については、「 [mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64345-107">For a list of the supported hardware and operating systems for MBAM, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

**<span data-ttu-id="64345-108">重要</span><span class="sxs-lookup"><span data-stu-id="64345-108">Important</span></span>**  
<span data-ttu-id="64345-109">MBAM なしで BitLocker を使用していた場合は、ドライブの暗号化を解除し、tpm を使って TPM をクリアする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-109">If BitLocker was used without MBAM, you must decrypt the drive and then clear TPM using tpm.msc.</span></span> <span data-ttu-id="64345-110">クライアント PC が既に暗号化されていて、TPM 所有者パスワードが作成されている場合、MBAM は TPM の所有権を取得できません。</span><span class="sxs-lookup"><span data-stu-id="64345-110">MBAM cannot take ownership of TPM if the client PC is already encrypted and the TPM owner password created.</span></span>



## <span data-ttu-id="64345-111">必須の MBAM ロールとアカウント</span><span class="sxs-lookup"><span data-stu-id="64345-111">Required MBAM roles and accounts</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-112">受講</span><span class="sxs-lookup"><span data-stu-id="64345-112">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-113">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-114">Active Directory ドメインサービス (AD DS) で作成されたグループ</span><span class="sxs-lookup"><span data-stu-id="64345-114">Groups created in Active Directory Domain Services (AD DS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-115"><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> </a> これらのグループとアカウントの説明については、「mbam 2.5 のグループとアカウントの計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64345-115">See <a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)">Planning for MBAM 2.5 Groups and Accounts</a> for a description of these groups and accounts.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64345-116">回復データベースの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-116">Prerequisites for the Recovery Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-117">受講</span><span class="sxs-lookup"><span data-stu-id="64345-117">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-118">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-118">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-119">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="64345-119">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-120">SQL_Latin1_General_CP1_CI_AS の照合を使用して Microsoft SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="64345-120">Install Microsoft SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="64345-121"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="64345-121">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-122">必須の SQL Server 権限</span><span class="sxs-lookup"><span data-stu-id="64345-122">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-123">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="64345-123">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-124">SQL Server インスタンスのログインサーバーの役割:</span><span class="sxs-lookup"><span data-stu-id="64345-124">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-125">dbcreator</span><span class="sxs-lookup"><span data-stu-id="64345-125">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="64345-126">processadmin</span><span class="sxs-lookup"><span data-stu-id="64345-126">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="64345-127">SQL Server Reporting Services インスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="64345-127">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-128">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="64345-128">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="64345-129">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="64345-129">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-130">オプション-SQL Server で使用できる透過データ暗号化 (TDE) 機能をインストールする</span><span class="sxs-lookup"><span data-stu-id="64345-130">Optional - Install the Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-131">TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業に適用される法律、規制、ガイドラインを遵守するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64345-131">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="64345-132">注</span><span class="sxs-lookup"><span data-stu-id="64345-132">Note</span></span></strong><br/><p><span data-ttu-id="64345-133">TDE は、データベース情報のリアルタイムの暗号化解除を実行します。</span><span class="sxs-lookup"><span data-stu-id="64345-133">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="64345-134">つまり、SQL Server データベースの回復キー情報を表示していて、データベースに対するアクセス許可を持つアカウントでログオンしている場合は、回復キーの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64345-134">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="64345-135">TDE の詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティの考慮事項」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="64345-135">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-136">SQL Server データベースエンジンサービス</span><span class="sxs-lookup"><span data-stu-id="64345-136">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-137">MBAM Server のインストール中に SQL Server データベースエンジンサービスをインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-137">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-138">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="64345-138">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-139">Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell を回復データベースサーバーにインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64345-139">Windows PowerShell does not have to be installed on the Recovery Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64345-140">コンプライアンスおよび監査データベースの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-140">Prerequisites for the Compliance and Audit Database</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-141">受講</span><span class="sxs-lookup"><span data-stu-id="64345-141">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-142">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-142">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-143">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="64345-143">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-144">SQL_Latin1_General_CP1_CI_AS の照合順序で SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="64345-144">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="64345-145"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="64345-145">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-146">必須の SQL Server 権限</span><span class="sxs-lookup"><span data-stu-id="64345-146">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-147">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="64345-147">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-148">SQL Server インスタンスのログインサーバーの役割:</span><span class="sxs-lookup"><span data-stu-id="64345-148">SQL Server instance login server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-149">dbcreator</span><span class="sxs-lookup"><span data-stu-id="64345-149">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="64345-150">processadmin</span><span class="sxs-lookup"><span data-stu-id="64345-150">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="64345-151">SQL Server Reporting Services インスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="64345-151">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-152">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="64345-152">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="64345-153">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="64345-153">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-154">オプション-透過データ暗号化 (TDE) 機能を SQL Server にインストールする</span><span class="sxs-lookup"><span data-stu-id="64345-154">Optional - Install the Transparent Data Encryption (TDE) feature in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-155">TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業に適用される法律、規制、ガイドラインを遵守するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="64345-155">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with laws, regulations, and guidelines that apply to various industries.</span></span></p>
<p><span data-ttu-id="64345-156">TDE は、データベース情報のリアルタイムの暗号化解除を実行します。</span><span class="sxs-lookup"><span data-stu-id="64345-156">TDE performs real-time decryption of database information.</span></span> <span data-ttu-id="64345-157">つまり、SQL Server データベースの回復キー情報を表示していて、データベースに対するアクセス許可を持つアカウントでログオンしている場合は、回復キーの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="64345-157">This means that, if you are viewing recovery key information in the SQL Server database and you are logged on under an account that has permissions to the database, the recovery key information is visible.</span></span> <span data-ttu-id="64345-158">TDE の詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティの考慮事項」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="64345-158">To read more about TDE, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-159">SQL Server データベースエンジンサービス</span><span class="sxs-lookup"><span data-stu-id="64345-159">SQL Server Database Engine Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-160">MBAM Server のインストール中に SQL Server データベースエンジンサービスをインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-160">SQL Server Database Engine Services must be installed and running during MBAM Server installation.</span></span> <span data-ttu-id="64345-161">ただし、SQL Server はリモートで実行できます。MBAM サーバソフトウェアをインストールしているのと同じサーバ上にある必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64345-161">However, SQL Server can be running remotely; it doesn’t have to be on the same server on which you are installing the MBAM Server software.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-162">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="64345-162">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-163">Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell をコンプライアンスおよび監査データベースサーバーにインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64345-163">Windows PowerShell does not have to be installed on the Compliance and Audit Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64345-164">レポートの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-164">Prerequisites for the Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-165">受講</span><span class="sxs-lookup"><span data-stu-id="64345-165">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-166">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-166">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-167">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="64345-167">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-168">SQL_Latin1_General_CP1_CI_AS の照合順序で SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="64345-168">Install SQL Server with SQL_Latin1_General_CP1_CI_AS collation.</span></span></p>
<p><span data-ttu-id="64345-169"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="64345-169">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-170">SQL Server Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="64345-170">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-171">SSRS は、MBAM サーバのインストール中にインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-171">SSRS must be installed and running during the MBAM Server installation.</span></span></p>
<p><span data-ttu-id="64345-172">&quot; &quot; 未構成または SharePoint モードではなく、ネイティブモードで SSRS を構成 &quot; &quot; します。</span><span class="sxs-lookup"><span data-stu-id="64345-172">Configure SSRS in &quot;native&quot; mode and not in unconfigured or &quot;SharePoint&quot; mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-173">SSRS インスタンスの権限–レポートが構成されているサーバーとは別のサーバーにデータベースをインストールする場合のみ、レポートを構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="64345-173">SSRS instance rights – required for configuring Reports only if you are installing databases on a separate server from the server where Reports are configured.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-174">必要なインスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="64345-174">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="64345-175">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="64345-175">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="64345-176">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="64345-176">Publish Reports</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-177">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="64345-177">Windows PowerShell 3.0 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-178">Windows PowerShell を使用してリモートコンピューターからデータベースを構成している場合は、windows PowerShell をこのデータベースサーバーにインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="64345-178">Windows PowerShell does not have to be installed on this Database server if you are using Windows PowerShell to configure the database from a remote computer.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a><span data-ttu-id="64345-179">管理および監視サーバーの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-179">Prerequisites for the Administration and Monitoring Server</span></span>


<span data-ttu-id="64345-180">次の表は、MBAM 管理および監視サーバーのインストールの前提条件を示しています。</span><span class="sxs-lookup"><span data-stu-id="64345-180">The following table lists the installation prerequisites for the MBAM Administration and Monitoring Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-181">受講</span><span class="sxs-lookup"><span data-stu-id="64345-181">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-182">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-182">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-183">Windows Server Web サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="64345-183">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-184">この役割は、管理と監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-184">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-185">Web サーバー (IIS) 管理ツール</span><span class="sxs-lookup"><span data-stu-id="64345-185">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-186">[ <strong> IIS 管理スクリプトとツール] をクリックし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="64345-186">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="64345-187">SSL 証明書</span><span class="sxs-lookup"><span data-stu-id="64345-187">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="64345-188">省略可能。</span><span class="sxs-lookup"><span data-stu-id="64345-188">Optional.</span></span> <span data-ttu-id="64345-189">クライアントコンピューターと web サービスの間の通信をセキュリティで保護するために、信頼されたセキュリティ機関が署名した証明書を取得してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-189">To secure communication between the client computers and the web services, you must obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-190">Web サーバーの役割サービス</span><span class="sxs-lookup"><span data-stu-id="64345-190">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="64345-191">一般的な HTTP 機能:</span><span class="sxs-lookup"><span data-stu-id="64345-191">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="64345-192">静的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="64345-192">Static Content</span></span></p></li>
<li><p><span data-ttu-id="64345-193">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="64345-193">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="64345-194">アプリケーション開発:</span><span class="sxs-lookup"><span data-stu-id="64345-194">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="64345-195">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="64345-195">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="64345-196">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="64345-196">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="64345-197">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="64345-197">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="64345-198">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="64345-198">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="64345-199">証券</span><span class="sxs-lookup"><span data-stu-id="64345-199">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="64345-200">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="64345-200">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="64345-201">フィルターを要求する</span><span class="sxs-lookup"><span data-stu-id="64345-201">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-202">Windows Server の機能</span><span class="sxs-lookup"><span data-stu-id="64345-202">Windows Server Features</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="64345-203">.NET Framework 4.5 の機能:</span><span class="sxs-lookup"><span data-stu-id="64345-203">.NET Framework 4.5 features:</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="64345-204">.NET Framework 4.5 または4.6</span><span class="sxs-lookup"><span data-stu-id="64345-204">.NET Framework 4.5 or 4.6</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="64345-205">Windows Server 2016 </strong> - .net Framework 4.6 は、これらのバージョンの windows server 用に既にインストールされていますが、有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-205">Windows Server 2016</strong> - .NET Framework 4.6 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>  
<li><p><strong><span data-ttu-id="64345-206">Windows server 2012 または Windows Server 2012 R2 </strong> - .net Framework 4.5 は、これらのバージョンの windows server 用に既にインストールされていますが、有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-206">Windows Server 2012 or Windows Server 2012 R2</strong> - .NET Framework 4.5 is already installed for these versions of Windows Server, but you must enable it.</span></span></p></li>
<li><p><strong><span data-ttu-id="64345-207">Windows Server 2008 R2 </strong> - .net framework 4.5 は windows Server 2008 r2 には含まれていないため、 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> Microsoft .net framework 4.5 をダウンロードして別途インストールする必要があり </a> ます。</span><span class="sxs-lookup"><span data-stu-id="64345-207">Windows Server 2008 R2</strong> - .NET Framework 4.5 is not included with Windows Server 2008 R2, so you must <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)">download Microsoft .NET Framework 4.5</a> and install it separately.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="64345-208">注</span><span class="sxs-lookup"><span data-stu-id="64345-208">Note</span></span></strong><br/><p><span data-ttu-id="64345-209">MBAM 2.0 または MBAM 2.0 SP1 からアップグレードしていて、.NET Framework 4.5 をインストールする必要がある場合は、「 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> mbam 2.5 のリリースノート」を参照して </a> 、web サイトを作成するための追加の必要な手順を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64345-209">If you are upgrading from MBAM 2.0 or MBAM 2.0 SP1 and need to install .NET Framework 4.5, see <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)">Release Notes for MBAM 2.5</a> for an additional required step to make the websites work.</span></span></p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong><span data-ttu-id="64345-210">WCF のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="64345-210">WCF Activation</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="64345-211">HTTP アクティベーション</span><span class="sxs-lookup"><span data-stu-id="64345-211">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="64345-212">非 HTTP ライセンス認証 (Windows Server 2008、2012、2012 R2 の場合のみ)</span><span class="sxs-lookup"><span data-stu-id="64345-212">Non-HTTP Activation (Only for Windows Server 2008, 2012, and 2012 R2)</span></span></p>
<p></p></li>
</ul></li>
<li><p><strong><span data-ttu-id="64345-213">TCP ライセンス認証</span><span class="sxs-lookup"><span data-stu-id="64345-213">TCP Activation</span></span></strong></p></li>
</ul>
<p><strong><span data-ttu-id="64345-214">Windows プロセスアクティブ化サービス:</span><span class="sxs-lookup"><span data-stu-id="64345-214">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="64345-215">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="64345-215">Process Model</span></span></p></li>
<li><p><span data-ttu-id="64345-216">.NET Framework 環境</span><span class="sxs-lookup"><span data-stu-id="64345-216">.NET Framework Environment</span></span></p></li>
<li><p><span data-ttu-id="64345-217">構成 Api</span><span class="sxs-lookup"><span data-stu-id="64345-217">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-218">ASP.NET MVC 4.0</span><span class="sxs-lookup"><span data-stu-id="64345-218">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="64345-219">ASP.NET MVC 4 ダウンロード</span><span class="sxs-lookup"><span data-stu-id="64345-219">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-220">サービスプリンシパル名 (SPN)</span><span class="sxs-lookup"><span data-stu-id="64345-220">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-221">Web アプリケーションでは、web アプリケーションプールに使用するドメインアカウントの下に、仮想ホスト名の SPN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-221">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="64345-222">管理者権限で Active Directory ドメインサービスの Spn の作成が許可されている場合は、MBAM によって SPN が作成されます。</span><span class="sxs-lookup"><span data-stu-id="64345-222">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="64345-223"><a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Spn の </a> 作成に必要な権利については、「Setspn」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64345-223">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="64345-224">Spn を作成するための管理者権限がない場合は、次のコマンドを使用して、組織内の Active Directory 管理者に、SPN の作成を依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-224">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="64345-225">このコード例では、仮想ホスト名は mbamvirtual.contoso.com であり、web アプリケーションプールに使用されているドメインアカウントは contoso\mbamapppooluser.</span><span class="sxs-lookup"><span data-stu-id="64345-225">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="64345-226">注</span><span class="sxs-lookup"><span data-stu-id="64345-226">Note</span></span></strong><br/><p><span data-ttu-id="64345-227">負荷分散を設定する場合は、すべてのサーバーで同じアプリケーションプールアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="64345-227">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="64345-228">完全修飾、NetBIOS、カスタムのホスト名の Spn の登録について詳しくは、「 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> MBAM Web サイトをセキュリティで保護する方法を計画する」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="64345-228">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64345-229">セルフサービスポータルの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-229">Prerequisites for the Self-Service Portal</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-230">受講</span><span class="sxs-lookup"><span data-stu-id="64345-230">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-231">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-231">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-232">サポートされているバージョンの Windows Server</span><span class="sxs-lookup"><span data-stu-id="64345-232">Supported version of Windows Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-233"><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"> </a> サポートされているバージョン用の mbam 2.5 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="64345-233">See <a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 Supported Configurations</a> for supported versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-234">ASP.NET MVC 4.0</span><span class="sxs-lookup"><span data-stu-id="64345-234">ASP.NET MVC 4.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)"><span data-ttu-id="64345-235">ASP.NET MVC 4 ダウンロード</span><span class="sxs-lookup"><span data-stu-id="64345-235">ASP.NET MVC 4 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-236">Web サービス IIS 管理ツール</span><span class="sxs-lookup"><span data-stu-id="64345-236">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-237">サービスプリンシパル名 (SPN)</span><span class="sxs-lookup"><span data-stu-id="64345-237">Service Principal Name (SPN)</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-238">Web アプリケーションでは、web アプリケーションプールに使用するドメインアカウントの下に、仮想ホスト名の SPN を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-238">The web applications require an SPN for the virtual host name under the domain account that you use for the web application pools.</span></span></p>
<p><span data-ttu-id="64345-239">管理者権限で Active Directory ドメインサービスの Spn の作成が許可されている場合は、MBAM によって SPN が作成されます。</span><span class="sxs-lookup"><span data-stu-id="64345-239">If your administrative rights permit you to create SPNs in Active Directory Domain Services, MBAM creates the SPN for you.</span></span> <span data-ttu-id="64345-240"><a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Spn の </a> 作成に必要な権利については、「Setspn」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="64345-240">See <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)">Setspn</a> for information about the rights required to create SPNs.</span></span></p>
<p><span data-ttu-id="64345-241">Spn を作成するための管理者権限がない場合は、次のコマンドを使用して、組織内の組織の管理者に、SPN の作成を依頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="64345-241">If you do not have administrative rights to create SPNs, you must ask the Active Directory administrators in your organization administrators in your organization to create the SPN for you by using the following command.</span></span></p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p><span data-ttu-id="64345-242">このコード例では、仮想ホスト名は mbamvirtual.contoso.com であり、web アプリケーションプールに使用されているドメインアカウントは contoso\mbamapppooluser.</span><span class="sxs-lookup"><span data-stu-id="64345-242">In the code example, the virtual host name is mbamvirtual.contoso.com, and the domain account used for the web application pools is contoso\mbamapppooluser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="64345-243">注</span><span class="sxs-lookup"><span data-stu-id="64345-243">Note</span></span></strong><br/><p><span data-ttu-id="64345-244">負荷分散を設定する場合は、すべてのサーバーで同じアプリケーションプールアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="64345-244">If you are setting up Load Balancing, use the same application pool account on all servers.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="64345-245">完全修飾、NetBIOS、カスタムのホスト名の Spn の登録について詳しくは、「 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> MBAM Web サイトをセキュリティで保護する方法を計画する」をご覧ください </a> 。</span><span class="sxs-lookup"><span data-stu-id="64345-245">For more information about registering SPNs for fully qualified, NetBIOS, and custom host names, see <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)">Planning How to Secure the MBAM Websites</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="64345-246">管理ワークステーションの前提条件</span><span class="sxs-lookup"><span data-stu-id="64345-246">Prerequisites for the Management Workstation</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-247">受講</span><span class="sxs-lookup"><span data-stu-id="64345-247">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="64345-248">詳細</span><span class="sxs-lookup"><span data-stu-id="64345-248">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-249">MBAM クライアントをインストールする前に、MBAM グループポリシーテンプレートをダウンロードして、そのために、組織 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> </a> 内で BitLocker ドライブ暗号化用に実装する設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="64345-249">Before installing the MBAM Client, download the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and configure them with the settings that you want to implement in your enterprise for BitLocker Drive Encryption.</span></span></p></td>
<td align="left"><p><span data-ttu-id="64345-250">MBAM クライアントをインストールする前に、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="64345-250">Before installing the MBAM Client, do the following:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64345-251">操作</span><span class="sxs-lookup"><span data-stu-id="64345-251">What to do</span></span></th>
<th align="left"><span data-ttu-id="64345-252">手順を表示する場所</span><span class="sxs-lookup"><span data-stu-id="64345-252">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64345-253">MBAM グループポリシーテンプレートをコピーする</span><span class="sxs-lookup"><span data-stu-id="64345-253">Copy the MBAM Group Policy Templates</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="64345-254">MBAM 2.5 グループ ポリシー テンプレートのコピー</span><span class="sxs-lookup"><span data-stu-id="64345-254">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64345-255">グループポリシー設定を編集する</span><span class="sxs-lookup"><span data-stu-id="64345-255">Edit the Group Policy settings</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="64345-256">MBAM 2.5 グループ ポリシー設定の編集</span><span class="sxs-lookup"><span data-stu-id="64345-256">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## <span data-ttu-id="64345-257">関連トピック</span><span class="sxs-lookup"><span data-stu-id="64345-257">Related topics</span></span>


[<span data-ttu-id="64345-258">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="64345-258">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="64345-259">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="64345-259">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="64345-260">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="64345-260">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)




## <span data-ttu-id="64345-261">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="64345-261">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="64345-262">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="64345-262">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="64345-263">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="64345-263">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




