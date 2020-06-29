---
title: MBAM 1.0 展開の前提条件
description: MBAM 1.0 展開の前提条件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822664"
---
# <span data-ttu-id="3438c-103">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-103">MBAM 1.0 Deployment Prerequisites</span></span>


<span data-ttu-id="3438c-104">Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするために必要な前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="3438c-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you meet the necessary prerequisites to install the product.</span></span> <span data-ttu-id="3438c-105">このセクションには、MBAM クライアントとサーバー機能を展開する前に、コンピューティング環境を正常に準備するための情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="3438c-105">This section contains information to help you successfully prepare your computing environment before you deploy the MBAM Clients and Server features.</span></span>

## <span data-ttu-id="3438c-106">MBAM Server 機能のインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-106">Installation prerequisites for MBAM Server features</span></span>


<span data-ttu-id="3438c-107">MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-107">Each of the MBAM server features has specific prerequisites that must be met before they can be successfully installed.</span></span> <span data-ttu-id="3438c-108">MBAM セットアップインストールを開始する前に、すべての前提条件が満たされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="3438c-108">MBAM Setup verifies if all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="3438c-109">管理および監視サーバーのインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-109">Installation prerequisites for Administration and Monitoring Server</span></span>

<span data-ttu-id="3438c-110">次の表には、MBAM 管理および監視サーバーのインストールの前提条件が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3438c-110">The following table contains the installation prerequisites for the MBAM Administration and Monitoring Server:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3438c-111">受講</span><span class="sxs-lookup"><span data-stu-id="3438c-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="3438c-112">詳細</span><span class="sxs-lookup"><span data-stu-id="3438c-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3438c-113">Windows ServerWeb サーバーの役割</span><span class="sxs-lookup"><span data-stu-id="3438c-113">Windows ServerWeb Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3438c-114">この役割は、mbam 管理および監視サーバー機能でサポートされているサーバーオペレーティングシステムに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-114">This role must be added to a server operating system supported for the mbam Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3438c-115">Web サーバー (IIS) 管理ツール</span><span class="sxs-lookup"><span data-stu-id="3438c-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3438c-116">IIS 管理スクリプトとツール</span><span class="sxs-lookup"><span data-stu-id="3438c-116">IIS Management Scripts and Tools</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3438c-117">Web サーバーの役割サービス</span><span class="sxs-lookup"><span data-stu-id="3438c-117">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3438c-118">一般的な HTTP 機能:</span><span class="sxs-lookup"><span data-stu-id="3438c-118">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="3438c-119">静的なコンテンツ</span><span class="sxs-lookup"><span data-stu-id="3438c-119">Static Content</span></span></p></li>
<li><p><span data-ttu-id="3438c-120">既定のドキュメント</span><span class="sxs-lookup"><span data-stu-id="3438c-120">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="3438c-121">アプリケーション開発:</span><span class="sxs-lookup"><span data-stu-id="3438c-121">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="3438c-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3438c-122">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="3438c-123">.NET の拡張性</span><span class="sxs-lookup"><span data-stu-id="3438c-123">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="3438c-124">ISAPI 拡張機能</span><span class="sxs-lookup"><span data-stu-id="3438c-124">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="3438c-125">ISAPI フィルター</span><span class="sxs-lookup"><span data-stu-id="3438c-125">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="3438c-126">証券</span><span class="sxs-lookup"><span data-stu-id="3438c-126">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="3438c-127">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="3438c-127">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="3438c-128">フィルターを要求する</span><span class="sxs-lookup"><span data-stu-id="3438c-128">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3438c-129">Windows Server の機能</span><span class="sxs-lookup"><span data-stu-id="3438c-129">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3438c-130">Microsoft .NET Framework 3.5.1 の機能:</span><span class="sxs-lookup"><span data-stu-id="3438c-130">Microsoft .NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="3438c-131">.NET Framework 3.5.1</span><span class="sxs-lookup"><span data-stu-id="3438c-131">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="3438c-132">WCF のアクティブ化</span><span class="sxs-lookup"><span data-stu-id="3438c-132">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="3438c-133">HTTP アクティベーション</span><span class="sxs-lookup"><span data-stu-id="3438c-133">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="3438c-134">HTTP 以外のアクティベーション</span><span class="sxs-lookup"><span data-stu-id="3438c-134">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="3438c-135">Windows プロセス アクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="3438c-135">Windows Process Activation Service</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="3438c-136">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="3438c-136">Process Model</span></span></p></li>
<li><p><span data-ttu-id="3438c-137">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="3438c-137">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="3438c-138">構成 Api</span><span class="sxs-lookup"><span data-stu-id="3438c-138">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3438c-139">**注** サポートされているオペレーティングシステムの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3438c-139">**Note** For a list of supported operating systems, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="3438c-140">コンプライアンスおよび監査レポートのインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-140">Installation prerequisites for the Compliance and Audit Reports</span></span>

<span data-ttu-id="3438c-141">コンプライアンスレポートおよび監査レポートは、サポートされているバージョンの SQLServer にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-141">The Compliance and Audit Reports must be installed on a supported version of SQLServer.</span></span> <span data-ttu-id="3438c-142">この機能のインストールの前提条件には、SQL Server Reporting Services (SSRS) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3438c-142">Installation prerequisites for this feature include SQL Server Reporting Services (SSRS).</span></span>

<span data-ttu-id="3438c-143">SSRS は、MBAM server のインストール中にインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-143">SSRS must be installed and running during MBAM server installation.</span></span> <span data-ttu-id="3438c-144">また、SSRS は、"未構成" または "SharePoint" モードではなく、"ネイティブ" モードで構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-144">SSRS should also be configured in “native” mode, not in the “unconfigured” or “SharePoint” mode.</span></span>

<span data-ttu-id="3438c-145">**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3438c-145">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

### <span data-ttu-id="3438c-146">回復とハードウェアデータベースのインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-146">Installation prerequisites for the Recovery and Hardware Database</span></span>

<span data-ttu-id="3438c-147">回復とハードウェアのデータベースは、サポートされているバージョンの SQLServer にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-147">The Recovery and Hardware Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="3438c-148">SQL Server は、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-148">SQL Server must have Database Engine Services installed and running during the MBAM server installation.</span></span> <span data-ttu-id="3438c-149">Transparent Data Encryption (TDE) 機能を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-149">The Transparent Data Encryption (TDE) feature must be enabled.</span></span>

<span data-ttu-id="3438c-150">**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3438c-150">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

<span data-ttu-id="3438c-151">TDE SQLServer 機能は、データとログファイルのリアルタイムの入出力 (i/o) 暗号化と暗号化解除を実行します。</span><span class="sxs-lookup"><span data-stu-id="3438c-151">The TDE SQLServer feature performs real-time input/output (I/O) encryption and decryption of the data and log files.</span></span> <span data-ttu-id="3438c-152">TDE は、データとログファイルを含む "残りの部分" のデータを保護します。</span><span class="sxs-lookup"><span data-stu-id="3438c-152">TDE protects data that is "at rest,” which include the data and the log files.</span></span> <span data-ttu-id="3438c-153">これにより、さまざまな業界で確立されている多くの法律、規制、ガイドラインを遵守することができます。</span><span class="sxs-lookup"><span data-stu-id="3438c-153">It provides the ability to comply with many laws, regulations, and guidelines that are established in various industries.</span></span>

<span data-ttu-id="3438c-154">**注** TDE はデータベース情報のリアルタイムの復号化を実行するため、回復キー情報の SQL テーブルを表示するときに、ログインしているアカウントにデータベースへのアクセス許可があるかどうかを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="3438c-154">**Note** Because TDE performs real-time decryption of database information, the recovery key information will be visible if the account under which you are logged in has permissions to the database when you view the recovery key information SQL tables.</span></span>

 

### <span data-ttu-id="3438c-155">コンプライアンスと監査データベースのインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-155">Installation prerequisites for the Compliance and Audit Database</span></span>

<span data-ttu-id="3438c-156">コンプライアンスと監査データベースは、サポートされているバージョンの SQLServer にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-156">The Compliance and Audit Database must be installed on a supported version of SQLServer.</span></span>

<span data-ttu-id="3438c-157">SQL Server では、MBAM サーバーのインストール中にデータベースエンジンサービスをインストールして実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-157">SQL Server must have Database Engine Services installed and running during MBAM server installation.</span></span>

<span data-ttu-id="3438c-158">**注** サポートされているオペレーティングシステムと SQLServer のバージョンの一覧については、「 [Mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="3438c-158">**Note** For a list of supported operating systems and SQLServer versions, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="3438c-159">MBAM クライアントのインストールの前提条件</span><span class="sxs-lookup"><span data-stu-id="3438c-159">Installation prerequisites for MBAM Clients</span></span>


<span data-ttu-id="3438c-160">MBAM クライアントのインストールを開始する前に満たす必要がある必須要件は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="3438c-160">The necessary prerequisites that you must meet before you begin the MBAM Client installation are the following:</span></span>

-   <span data-ttu-id="3438c-161">トラステッドプラットフォームモジュール (TPM) v 1.2 機能</span><span class="sxs-lookup"><span data-stu-id="3438c-161">Trusted Platform Module (TPM) v1.2 capability</span></span>

-   <span data-ttu-id="3438c-162">TPM チップが BIOS で有効になっていて、オペレーティングシステムから resettable されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-162">The TPM chip must be turned on in the BIOS and it must be resettable from the operating system.</span></span> <span data-ttu-id="3438c-163">詳細については、BIOS のマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3438c-163">For more information, see the BIOS documentation.</span></span>

<span data-ttu-id="3438c-164">**警告** キーボード、ビデオ、マウス (KVM) スイッチではなく、キーボード、マウス、およびビデオがコンピューターに直接接続されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3438c-164">**Warning** Ensure that the keyboard, mouse, and video are directly connected to the computer, instead of to a keyboard, video, mouse (KVM) switch.</span></span> <span data-ttu-id="3438c-165">KVM スイッチでは、コンピュータの物理機能がハードウェアの物理的な存在を検出してしまう可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3438c-165">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span>

 

## <span data-ttu-id="3438c-166">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3438c-166">Related topics</span></span>


[<span data-ttu-id="3438c-167">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="3438c-167">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="3438c-168">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="3438c-168">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

 

 





