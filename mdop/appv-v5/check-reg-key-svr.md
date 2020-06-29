---
title: APP-V 5.x Server をインストールする前にレジストリ キーを確認する
description: APP-V 5.x Server をインストールする前にレジストリ キーを確認する
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814707"
---
# <span data-ttu-id="1ed12-103">APP-V 5.x Server をインストールする前にレジストリ キーを確認する</span><span class="sxs-lookup"><span data-stu-id="1ed12-103">Check Registry Keys before installing App-V 5.x Server</span></span>

<span data-ttu-id="1ed12-104">App-v Server を App-v 5.0 SP1 修正プログラムパッケージ3以降からアップグレードする場合は、このセクションの手順を実行してから、app-v Server をインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="1ed12-104">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in this section before installing the App-V 5.x Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ed12-105">この手順が必要な場合</span><span class="sxs-lookup"><span data-stu-id="1ed12-105">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ed12-106">.Msp ファイルを使用してインストールした後続の修正プログラムパッケージを使用して、App-v 5.0 SP1 からアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="1ed12-106">You are upgrading from App-V 5.0 SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ed12-107">この手順を実行する必要があるコンポーネント</span><span class="sxs-lookup"><span data-stu-id="1ed12-107">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ed12-108">アップグレードしている App-v Server コンポーネントのみ</span><span class="sxs-lookup"><span data-stu-id="1ed12-108">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ed12-109">この手順を実行する必要がある場合</span><span class="sxs-lookup"><span data-stu-id="1ed12-109">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ed12-110">App-v Server をアプリ-V 5.x にアップグレードする前に</span><span class="sxs-lookup"><span data-stu-id="1ed12-110">Before you upgrade the App-V Server to App-V 5.x</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ed12-111">必要な作業</span><span class="sxs-lookup"><span data-stu-id="1ed12-111">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ed12-112">次の表の情報を使用して、[ <code>HKLM\Software\Microsoft\AppV\Server</code> 元のサーバーインストールで指定した値を使用して、各レジストリキーの値を更新します] を選びます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-112">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="1ed12-113">この手順を完了すると、App-v 5.0 SP1 修正プログラムパッケージをインストールしたときに削除された可能性があるレジストリ値が復元されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-113">Completing this step restores registry values that may have been removed when App-V 5.0 SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="1ed12-114">ManagementDatabase キー</span><span class="sxs-lookup"><span data-stu-id="1ed12-114">ManagementDatabase key</span></span>**

<span data-ttu-id="1ed12-115">管理データベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-115">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ed12-116">キー名</span><span class="sxs-lookup"><span data-stu-id="1ed12-116">Key name</span></span></th>
<th align="left"><span data-ttu-id="1ed12-117">説明</span><span class="sxs-lookup"><span data-stu-id="1ed12-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="1ed12-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-119">ローカル以外の管理データベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-119">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="1ed12-120">値が必要な場合は、"1" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-120">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-121">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1ed12-121">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-122">管理データベースの名前。</span><span class="sxs-lookup"><span data-stu-id="1ed12-122">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-124">読み取り (パブリック) 管理データベースへのアクセスに使用するアカウント。</span><span class="sxs-lookup"><span data-stu-id="1ed12-124">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="1ed12-125">"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-125">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="1ed12-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-127">管理データベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="1ed12-127">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="1ed12-128">"1" に設定されているときに使われ <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-128">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-129">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="1ed12-129">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-130">管理データベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ed12-130">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="1ed12-131">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-131">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-133">管理データベースへの書き込み (管理者) アクセスのために使用されるアカウント。</span><span class="sxs-lookup"><span data-stu-id="1ed12-133">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="1ed12-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-135">管理データベースへの書き込み (管理者) アクセスのために使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="1ed12-135">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-137">管理サーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</span><span class="sxs-lookup"><span data-stu-id="1ed12-137">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-139">管理サーバー (ドメイン \ アカウント) のインストール管理者ログイン。</span><span class="sxs-lookup"><span data-stu-id="1ed12-139">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1ed12-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-141">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ed12-141">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="1ed12-142">1 </strong> –管理サービスはローカルコンピューターにあります。つまり、MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</span><span class="sxs-lookup"><span data-stu-id="1ed12-142">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ed12-143">0 </strong> - 管理サービスは、ローカルコンピューターとは別のコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="1ed12-143">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="1ed12-144">ManagementService キー</span><span class="sxs-lookup"><span data-stu-id="1ed12-144">ManagementService key</span></span>**

<span data-ttu-id="1ed12-145">管理サーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ManagementService` します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-145">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ed12-146">キー名</span><span class="sxs-lookup"><span data-stu-id="1ed12-146">Key name</span></span></th>
<th align="left"><span data-ttu-id="1ed12-147">説明</span><span class="sxs-lookup"><span data-stu-id="1ed12-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-148">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-148">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-149">Active Directory ドメインサービス (AD DS) グループまたは、App-v (ドメイン \ アカウント) を管理する権限が与えられているアカウント。</span><span class="sxs-lookup"><span data-stu-id="1ed12-149">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-150">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="1ed12-150">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-151">管理データベースを含む SQL server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ed12-151">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="1ed12-152">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-152">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-153">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1ed12-153">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-154">管理データベースのあるリモート SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="1ed12-154">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="1ed12-155">この値が空白の場合は、ローカルコンピューターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-155">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="1ed12-156">ReportingDatabase キー</span><span class="sxs-lookup"><span data-stu-id="1ed12-156">ReportingDatabase key</span></span>**

<span data-ttu-id="1ed12-157">レポートデータベースをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-157">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ed12-158">キー名</span><span class="sxs-lookup"><span data-stu-id="1ed12-158">Key name</span></span></th>
<th align="left"><span data-ttu-id="1ed12-159">説明</span><span class="sxs-lookup"><span data-stu-id="1ed12-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="1ed12-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-161">ローカル以外のレポートデータベースにアクセスするためにパブリックアクセスアカウントが必要かどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-161">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="1ed12-162">値が必要な場合は、"1" に設定されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-162">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-163">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="1ed12-163">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-164">レポートデータベースの名前。</span><span class="sxs-lookup"><span data-stu-id="1ed12-164">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-166">レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウント。</span><span class="sxs-lookup"><span data-stu-id="1ed12-166">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="1ed12-167">"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-167">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="1ed12-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-169">レポートデータベースへの読み取り (パブリック) アクセスに使用されるアカウントのセキュリティ識別子 (SID)。</span><span class="sxs-lookup"><span data-stu-id="1ed12-169">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="1ed12-170">"1" に設定されているときに使われ <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> ます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-170">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-171">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="1ed12-171">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-172">レポートデータベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ed12-172">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="1ed12-173">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-173">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="1ed12-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-177">レポートサーバーのリモートコンピューターアカウント (ドメイン \ アカウント)。</span><span class="sxs-lookup"><span data-stu-id="1ed12-177">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="1ed12-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-179">[Reporting server (ドメイン \ アカウント)] のインストール管理者としてログインします。</span><span class="sxs-lookup"><span data-stu-id="1ed12-179">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="1ed12-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-181">有効な値は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1ed12-181">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="1ed12-182">1 </strong> –レポートサービスはローカルコンピューターにあります。つまり、REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT は空白です。</span><span class="sxs-lookup"><span data-stu-id="1ed12-182">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="1ed12-183">0 </strong> - レポートサービスは、ローカルコンピューターの別のコンピューターにあります。</span><span class="sxs-lookup"><span data-stu-id="1ed12-183">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="1ed12-184">ReportingService キー</span><span class="sxs-lookup"><span data-stu-id="1ed12-184">ReportingService key</span></span>**

<span data-ttu-id="1ed12-185">レポートサーバーをインストールする場合は、次のレジストリキーをに設定 `HKLM\Software\Microsoft\AppV\Server\ReportingService` します。</span><span class="sxs-lookup"><span data-stu-id="1ed12-185">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ed12-186">キー名</span><span class="sxs-lookup"><span data-stu-id="1ed12-186">Key name</span></span></th>
<th align="left"><span data-ttu-id="1ed12-187">説明</span><span class="sxs-lookup"><span data-stu-id="1ed12-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ed12-188">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="1ed12-188">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-189">レポートデータベースの SQL Server インスタンス。</span><span class="sxs-lookup"><span data-stu-id="1ed12-189">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="1ed12-190">この値が空白の場合、既定のデータベースインスタンスが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-190">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ed12-191">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="1ed12-191">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ed12-192">レポートデータベースのあるリモート SQL server の名前。</span><span class="sxs-lookup"><span data-stu-id="1ed12-192">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="1ed12-193">この値が空白の場合は、ローカルコンピューターが使用されます。</span><span class="sxs-lookup"><span data-stu-id="1ed12-193">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

