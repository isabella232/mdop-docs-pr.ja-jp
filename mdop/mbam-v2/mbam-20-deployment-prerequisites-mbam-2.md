---
title: MBAM 2.0 展開の前提条件
description: MBAM 2.0 展開の前提条件
author: dansimp
ms.assetid: 57d1c2bb-5ea3-457e-badd-dd9206ff0f20
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ef7ee64a3661009f18e0963d738c57a59885cb20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826014"
---
# <span data-ttu-id="8924e-103">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-103">MBAM 2.0 Deployment Prerequisites</span></span>


<span data-ttu-id="8924e-104">Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするための前提条件を満たしていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-104">Before you start Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should ensure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="8924e-105">このセクションには、Microsoft BitLocker の管理および監視サーバーの機能とクライアントを展開する前に、コンピューティング環境の計画を成功させるために役立つ情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="8924e-105">This section contains information to help you successfully plan your computing environment before you deploy Microsoft BitLocker Administration and Monitoring Server features and Clients.</span></span> <span data-ttu-id="8924e-106">MBAM を Configuration Manager にインストールする場合は、「 [Configuration manager を使用して MBAM を展開する](planning-to-deploy-mbam-with-configuration-manager-2.md)場合の計画」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8924e-106">If you are installing MBAM with Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional prerequisites.</span></span>

## <span data-ttu-id="8924e-107">MBAM Server 機能のインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-107">Installation Prerequisites for MBAM Server Features</span></span>


<span data-ttu-id="8924e-108">Mbam 機能を正常にインストールするには、MBAM サーバーの各機能について特定の前提条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-108">Each of the MBAM Server features has specific prerequisites that must be met before the MBAM features can be successfully installed.</span></span> <span data-ttu-id="8924e-109">MBAM セットアップインストールを開始する前に、すべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="8924e-109">MBAM Setup checks that all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="8924e-110">管理および監視サーバーの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-110">Prerequisites for Administration and Monitoring Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-111">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-112">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8924e-113">Windows Server Web サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="8924e-113">Windows Server Web Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8924e-114">この役割は、管理と監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-114">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8924e-115">Web サーバー (IIS) 管理ツール</span><span class="sxs-lookup"><span data-stu-id="8924e-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8924e-116">[ <strong> IIS 管理スクリプトとツール] を選び </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="8924e-116">Select <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8924e-117">SSL 証明書</span><span class="sxs-lookup"><span data-stu-id="8924e-117">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="8924e-118">省略可能。</span><span class="sxs-lookup"><span data-stu-id="8924e-118">Optional.</span></span> <span data-ttu-id="8924e-119">クライアントと web サービス間の通信をセキュリティで保護するために、信頼されたセキュリティ機関が署名した証明書を取得してインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-119">To secure communication between the clients and the web services, you have to obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8924e-120">Web サーバーの役割サービス</span><span class="sxs-lookup"><span data-stu-id="8924e-120">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8924e-121">一般的な HTTP 機能:</span><span class="sxs-lookup"><span data-stu-id="8924e-121">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="8924e-122">静的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="8924e-122">Static Content</span></span></p></li>
<li><p><span data-ttu-id="8924e-123">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="8924e-123">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="8924e-124">アプリケーション開発:</span><span class="sxs-lookup"><span data-stu-id="8924e-124">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="8924e-125">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="8924e-125">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="8924e-126">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="8924e-126">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="8924e-127">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="8924e-127">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="8924e-128">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="8924e-128">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="8924e-129">証券</span><span class="sxs-lookup"><span data-stu-id="8924e-129">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="8924e-130">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="8924e-130">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="8924e-131">フィルターを要求する</span><span class="sxs-lookup"><span data-stu-id="8924e-131">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8924e-132">Windows Server の機能</span><span class="sxs-lookup"><span data-stu-id="8924e-132">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8924e-133">.NET Framework 3.5.1 の機能:</span><span class="sxs-lookup"><span data-stu-id="8924e-133">.NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="8924e-134">.NET Framework 3.5.1</span><span class="sxs-lookup"><span data-stu-id="8924e-134">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="8924e-135">WCF のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="8924e-135">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-136">HTTP アクティベーション</span><span class="sxs-lookup"><span data-stu-id="8924e-136">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="8924e-137">HTTP 以外のアクティベーション</span><span class="sxs-lookup"><span data-stu-id="8924e-137">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="8924e-138">Windows プロセスアクティブ化サービス:</span><span class="sxs-lookup"><span data-stu-id="8924e-138">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="8924e-139">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="8924e-139">Process Model</span></span></p></li>
<li><p><span data-ttu-id="8924e-140">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="8924e-140">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="8924e-141">構成 Api</span><span class="sxs-lookup"><span data-stu-id="8924e-141">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="8924e-142">注</span><span class="sxs-lookup"><span data-stu-id="8924e-142">Note</span></span>**  
<span data-ttu-id="8924e-143">サポートされているオペレーティングシステムの一覧については、「 [Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8924e-143">For a list of supported operating systems, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



### <span data-ttu-id="8924e-144">コンプライアンスおよび監査レポートの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-144">Prerequisites for the Compliance and Audit Reports</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-145">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-145">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-146">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-147">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="8924e-147">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="8924e-148"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8924e-148">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-149">次のような SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8924e-149">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-150">SQL_Latin1_General_CP1_CI_AS の照合</span><span class="sxs-lookup"><span data-stu-id="8924e-150">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-151">SQL Server Reporting Services (SSRS)</span><span class="sxs-lookup"><span data-stu-id="8924e-151">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-152">SSRS インスタンスの権限–レポートからデータベースを個別のサーバーにインストールする場合にのみ、レポートをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-152">SSRS instance rights – required for installing reports only if you are installing databases on a separate server from the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-153">必要なインスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="8924e-153">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-154">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="8924e-154">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="8924e-155">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="8924e-155">Publish Reports</span></span></p></li>
</ul>
<p><span data-ttu-id="8924e-156">SSRS は、MBAM サーバのインストール中にインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-156">SSRS must be installed and running during the MBAM Server installation.</span></span> <span data-ttu-id="8924e-157">SSRS は "ネイティブ" モードで、未構成または "SharePoint" モードでは構成されません。</span><span class="sxs-lookup"><span data-stu-id="8924e-157">Configure SSRS in “native” mode and not in unconfigured or “SharePoint” mode.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8924e-158">回復データベースの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-158">Prerequisites for the Recovery Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-159">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-159">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-160">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-160">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-161">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="8924e-161">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="8924e-162"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8924e-162">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-163">次のような SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8924e-163">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-164">SQL_Latin1_General_CP1_CI_AS の照合</span><span class="sxs-lookup"><span data-stu-id="8924e-164">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="8924e-165">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="8924e-165">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-166">必須の SQL Server 権限</span><span class="sxs-lookup"><span data-stu-id="8924e-166">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-167">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="8924e-167">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-168">SQL インスタンスログインサーバーの役割:</span><span class="sxs-lookup"><span data-stu-id="8924e-168">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-169">dbcreator</span><span class="sxs-lookup"><span data-stu-id="8924e-169">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="8924e-170">processadmin</span><span class="sxs-lookup"><span data-stu-id="8924e-170">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="8924e-171">SQL Server Reporting Services インスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="8924e-171">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-172">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="8924e-172">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="8924e-173">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="8924e-173">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-174">オプション-透過的なデータ暗号化 (TDE) 機能をインストールする (SQL Server で利用可能)</span><span class="sxs-lookup"><span data-stu-id="8924e-174">Optional - Install Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-175">TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業で確立された多くの法律、規制、ガイドラインに準拠するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8924e-175">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8924e-176">注</span><span class="sxs-lookup"><span data-stu-id="8924e-176">Note</span></span></strong><br/><p><span data-ttu-id="8924e-177">TDE は、データベース情報のリアルタイムの暗号化解除を実行します。つまり、ログオンしているアカウントに SQL Server テーブルの回復キー情報を表示しているときに、データベースへのアクセス許可が与えられている場合は、回復キーの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8924e-177">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="8924e-178">TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> mbam 2.0 セキュリティに関する考慮事項 </a> の詳細。</span><span class="sxs-lookup"><span data-stu-id="8924e-178">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8924e-179">コンプライアンスおよび監査データベースの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-179">Prerequisites for the Compliance and Audit Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-180">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-180">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-181">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-181">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-182">サポートされているバージョンの SQL Server</span><span class="sxs-lookup"><span data-stu-id="8924e-182">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="8924e-183"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8924e-183">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-184">次のような SQL Server をインストールします。</span><span class="sxs-lookup"><span data-stu-id="8924e-184">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-185">SQL_Latin1_General_CP1_CI_AS の照合</span><span class="sxs-lookup"><span data-stu-id="8924e-185">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="8924e-186">SQL Server 管理ツール</span><span class="sxs-lookup"><span data-stu-id="8924e-186">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-187">必須の SQL Server 権限</span><span class="sxs-lookup"><span data-stu-id="8924e-187">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-188">必要な権限:</span><span class="sxs-lookup"><span data-stu-id="8924e-188">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-189">SQL インスタンスログインサーバーの役割:</span><span class="sxs-lookup"><span data-stu-id="8924e-189">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-190">dbcreator</span><span class="sxs-lookup"><span data-stu-id="8924e-190">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="8924e-191">processadmin</span><span class="sxs-lookup"><span data-stu-id="8924e-191">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="8924e-192">SQL Server Reporting Services インスタンスの権限:</span><span class="sxs-lookup"><span data-stu-id="8924e-192">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-193">フォルダーを作成する</span><span class="sxs-lookup"><span data-stu-id="8924e-193">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="8924e-194">レポートを発行する</span><span class="sxs-lookup"><span data-stu-id="8924e-194">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-195">オプション-透過的データ暗号化 (TDE) 機能を SQL Server にインストールします。</span><span class="sxs-lookup"><span data-stu-id="8924e-195">Optional - Install Transparent Data Encryption (TDE) feature in SQL Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-196">TDE SQL Server 機能は、データとログファイルの入出力の暗号化と暗号化解除をリアルタイムで実行します。これは、さまざまな産業で確立された多くの法律、規制、ガイドラインに準拠するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8924e-196">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8924e-197">注</span><span class="sxs-lookup"><span data-stu-id="8924e-197">Note</span></span></strong><br/><p><span data-ttu-id="8924e-198">TDE は、データベース情報のリアルタイムの暗号化解除を実行します。つまり、ログオンしているアカウントに SQL Server テーブルの回復キー情報を表示しているときに、データベースへのアクセス許可が与えられている場合は、回復キーの情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="8924e-198">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="8924e-199">TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> mbam 2.0 セキュリティの考慮事項の詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-199">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-200">SQL Server では、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-200">SQL Server must have Database Engine Services installed and running during MBAM Server installation.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-201">SQL Server エージェントサービスが実行されていて、SQL Server の選択されたインスタンスで自動開始に設定されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-201">The SQL Server Agent service must be running and set to auto-start on the selected instances of SQL Server.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="8924e-202">セルフサービスポータルの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-202">Prerequisites for the Self-Service Portal</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-203">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-203">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-204">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-204">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-205">サポートされているバージョンの Windows Server</span><span class="sxs-lookup"><span data-stu-id="8924e-205">Supported version of Windows Server</span></span></p>
<p><span data-ttu-id="8924e-206"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)"> </a> サポートされているバージョン用の mbam 2.0 サポートされている構成</span><span class="sxs-lookup"><span data-stu-id="8924e-206">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-207">ASP.NET MVC 2.0</span><span class="sxs-lookup"><span data-stu-id="8924e-207">ASP.NET MVC 2.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)"><span data-ttu-id="8924e-208">ASP.NET MVC 2 ダウンロード</span><span class="sxs-lookup"><span data-stu-id="8924e-208">ASP.NET MVC 2 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8924e-209">Web サービス IIS 管理ツール</span><span class="sxs-lookup"><span data-stu-id="8924e-209">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8924e-210">MBAM クライアントの前提条件</span><span class="sxs-lookup"><span data-stu-id="8924e-210">Prerequisites for MBAM Clients</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8924e-211">受講</span><span class="sxs-lookup"><span data-stu-id="8924e-211">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="8924e-212">詳細</span><span class="sxs-lookup"><span data-stu-id="8924e-212">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8924e-213">Windows 7 クライアントには </strong> - 、トラステッドプラットフォームモジュール (TPM) 機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="8924e-213">Windows 7 clients only</strong> - must have Trusted Platform Module (TPM) capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-214">TPM バージョンは、1.2 以降である必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-214">TPM version must be 1.2 or later.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8924e-215">TPM チップは BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-215">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8924e-216">詳細については、BIOS のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8924e-216">For more information, see the BIOS documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8924e-217">Windows 8 クライアントのみ: MBAM の保存と管理には、tpm の自動プロビジョニング機能を無効にする必要があります。また、mbam は、mbam を </strong> 展開する前に tpm の所有者として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-217">Windows 8 clients only</strong>: To have MBAM store and manage the TPM recovery keys: TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span> <span data-ttu-id="8924e-218">TPM 自動プロビジョニング機能を無効にするには、「Disable-TpmAutoProvisioning」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="8924e-218">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<ul>
<li><p><span data-ttu-id="8924e-219">TPM 自動プロビジョニング機能を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-219">TPM auto-provisioning must be turned off.</span></span></p></li>
<li><p><span data-ttu-id="8924e-220">MBAM を展開する前に、MBAM を TPM の所有者として設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-220">MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="8924e-221">TPM 自動プロビジョニング機能を無効にするには、「Disable-TpmAutoProvisioning」を参照してください <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="8924e-221">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8924e-222">注</span><span class="sxs-lookup"><span data-stu-id="8924e-222">Note</span></span></strong><br/><p><span data-ttu-id="8924e-223">キーボード、ビデオ、マウスが直接接続されていて、キーボード、ビデオ、マウス (KVM) スイッチで管理されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="8924e-223">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="8924e-224">KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="8924e-224">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8924e-225">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8924e-225">Related topics</span></span>


[<span data-ttu-id="8924e-226">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="8924e-226">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="8924e-227">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="8924e-227">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)









