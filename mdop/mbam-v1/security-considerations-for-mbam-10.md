---
title: MBAM 1.0 のセキュリティに関する考慮事項
description: MBAM 1.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826194"
---
# <span data-ttu-id="6e7d6-103">MBAM 1.0 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="6e7d6-103">Security Considerations for MBAM 1.0</span></span>


<span data-ttu-id="6e7d6-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="6e7d6-105">詳細については、この記事のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-105">For more information, follow the links in this article.</span></span>

## <span data-ttu-id="6e7d6-106">一般的なセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="6e7d6-106">General security considerations</span></span>


**<span data-ttu-id="6e7d6-107">セキュリティのリスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-107">Understand the security risks.</span></span>** <span data-ttu-id="6e7d6-108">MBAM の最も重大なリスクは、許可されていないユーザーが BitLocker 暗号化を再構成して、MBAM クライアントで BitLocker 暗号化キーデータを取得できるということです。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-108">The most serious risk to MBAM is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="6e7d6-109">ただし、サービス拒否攻撃のために、しばらくの間、MBAM 機能が失われても、通常は致命的な影響はありません。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-109">However, the loss of MBAM functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="6e7d6-110">**コンピューターを物理的に保護**します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-110">**Physically secure your computers**.</span></span> <span data-ttu-id="6e7d6-111">セキュリティは物理的なセキュリティがない状態では完了しません。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-111">Security is incomplete without physical security.</span></span> <span data-ttu-id="6e7d6-112">MBAM サーバーに物理的にアクセスできるすべての人が、クライアントベース全体を攻撃する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-112">Anyone with physical access to an MBAM Server could potentially attack the entire client base.</span></span> <span data-ttu-id="6e7d6-113">物理的な攻撃が発生する可能性がある場合は、リスクが高いと考えられ、適切に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-113">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="6e7d6-114">MBAM サーバは、アクセスを管理することで、物理的に安全なサーバ室に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-114">MBAM servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="6e7d6-115">オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="6e7d6-116">**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="6e7d6-117">セキュリティ通知サービス () をサブスクライブすることにより、オペレーティングシステム、Microsoft SQL Server、MBAM の新しい更新について常に情報を受け取ることが <https://go.microsoft.com/fwlink/p/?LinkId=28819> できます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="6e7d6-118">**強力なパスワードを使用するか、語句を渡し**ます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="6e7d6-119">すべての MBAM および MBAM 管理者アカウントには、必ず15文字以上の強力なパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="6e7d6-120">空のパスワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-120">Never use blank passwords.</span></span> <span data-ttu-id="6e7d6-121">パスワードの概念の詳細については、TechNet の「アカウントのパスワードとポリシー」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="6e7d6-122">MBAM のアカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="6e7d6-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="6e7d6-123">ユーザーアカウントの管理については、ドメイングローバルグループを作成し、ユーザーアカウントを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-123">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="6e7d6-124">次に、MBAM サーバー上の必要な MBAM ローカルグループにドメインのグローバルアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="6e7d6-125">ActiveDirectoryDomainServices グループ</span><span class="sxs-lookup"><span data-stu-id="6e7d6-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="6e7d6-126">MBAM セットアップ中に自動的にグループが作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-126">No groups are created automatically during MBAM Setup.</span></span> <span data-ttu-id="6e7d6-127">ただし、MBAM 操作を管理するには、次の ActiveDirectoryDomainServices グローバルグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-127">However, you should create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e7d6-128">グループ名</span><span class="sxs-lookup"><span data-stu-id="6e7d6-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="6e7d6-129">詳細</span><span class="sxs-lookup"><span data-stu-id="6e7d6-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-130">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-131">このグループを作成して、mbam セットアップで作成された MBAM Advanced ヘルプデスクユーザーのローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-132">MBAM コンプライアンス監査データベースアクセス</span><span class="sxs-lookup"><span data-stu-id="6e7d6-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-133">このグループを作成して、mbam セットアップで作成された MBAM コンプライアンス監査 DB Access ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-134">MBAM ハードウェアユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-134">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-135">このグループを作成して、mbam セットアップで作成された MBAM Hardware Users ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-135">Create this group to manage members of the MBAM Hardware Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-136">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-136">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-137">このグループを作成すると、MBAM セットアップで作成された MBAM ヘルプデスクユーザーのローカルグループのメンバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-137">Create this group to manage members of the MBAM Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-138">MBAM 回復とハードウェアデータベースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6e7d6-138">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-139">このグループを作成して、mbam セットアップで作成された MBAM Recovery と Hardware DB Access ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-139">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-140">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-140">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-141">このグループを作成して、mbam セットアップで作成された MBAM Report Users ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-141">Create this group to manage members of the MBAM Report Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-142">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="6e7d6-142">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-143">このグループを作成して、MBAM セットアップで作成された MBAM システム管理者ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-143">Create this group to manage members of the MBAM System Administrators local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-144">BitLocker 暗号化の除外</span><span class="sxs-lookup"><span data-stu-id="6e7d6-144">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-145">このグループを作成して、ログオン先のコンピューターで開始する BitLocker 暗号化から除外する必要があるユーザーアカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-145">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6e7d6-146">MBAM サーバーのローカルグループ</span><span class="sxs-lookup"><span data-stu-id="6e7d6-146">MBAM Server Local Groups</span></span>

<span data-ttu-id="6e7d6-147">MBAM セットアップは、MBAM 操作をサポートするローカルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-147">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="6e7d6-148">MBAM セキュリティとデータアクセス権限を構成するために、適切な MBAM ローカルグループに ActiveDirectoryDomainServices グローバルグループを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-148">You should add the ActiveDirectoryDomainServices Global Groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e7d6-149">グループ名</span><span class="sxs-lookup"><span data-stu-id="6e7d6-149">Group Name</span></span></th>
<th align="left"><span data-ttu-id="6e7d6-150">詳細</span><span class="sxs-lookup"><span data-stu-id="6e7d6-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-151">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-151">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-152">このグループのメンバーは、Microsoft BitLocker の管理と監視のヘルプデスク機能へのアクセスが拡張されています。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-152">Members of this group have expanded access to the Helpdesk features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-153">MBAM コンプライアンス監査データベースアクセス</span><span class="sxs-lookup"><span data-stu-id="6e7d6-153">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-154">このグループには、MBAM コンプライアンス監査データベースへのアクセス権を持つコンピューターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-154">This group contains the machines that have access to the MBAM Compliance Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-155">MBAM ハードウェアユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-155">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-156">このグループのメンバーは、Microsoft BitLocker の管理と監視の一部のハードウェア機能機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-156">Members of this group have access to some of the Hardware Capability features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-157">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-157">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-158">このグループのメンバーは、Microsoft BitLocker の管理と監視の一部のヘルプデスク機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-158">Members of this group have access to some of the Helpdesk features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-159">MBAM 回復とハードウェアデータベースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="6e7d6-159">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-160">このグループには、MBAM 回復とハードウェアデータベースへのアクセス権を持つコンピューターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-160">This group contains the computers that have access to the MBAM Recovery and Hardware Database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e7d6-161">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-161">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-162">このグループのメンバーは、Microsoft BitLocker の管理と監視に関するコンプライアンスおよび監査レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-162">Members of this group have access to the Compliance and Audit reports from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e7d6-163">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="6e7d6-163">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e7d6-164">このグループのメンバーは、Microsoft BitLocker の管理と監視のすべての機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-164">Members of this group have access to all the features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6e7d6-165">SSRS レポートアクセスアカウント</span><span class="sxs-lookup"><span data-stu-id="6e7d6-165">SSRS Reports Access Account</span></span>

<span data-ttu-id="6e7d6-166">SQL Server Reporting Services (SSRS) レポートサービスアカウントは、SSRS で利用可能な MBAM レポートを実行するためのセキュリティコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-166">The SQL Server Reporting Services (SSRS) Reports Service Account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="6e7d6-167">このアカウントは、MBAM セットアップ中に構成されます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-167">This account is configured during MBAM Setup.</span></span>

## <span data-ttu-id="6e7d6-168">MBAM ログファイル</span><span class="sxs-lookup"><span data-stu-id="6e7d6-168">MBAM Log Files</span></span>


<span data-ttu-id="6e7d6-169">MBAM のセットアップ時に、次の MBAM セットアップログファイルが、インストールしたユーザーの% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-169">During MBAM Setup, the following MBAM Setup log files are created in the %temp% folder of the user who installs the</span></span>

**<span data-ttu-id="6e7d6-170">MBAM サーバーセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="6e7d6-170">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="6e7d6-171">MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ</span><span class="sxs-lookup"><span data-stu-id="6e7d6-171">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="6e7d6-172">MBAM セットアップおよび MBAM サーバー機能のインストール中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-172">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="6e7d6-173">InstallComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="6e7d6-173">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="6e7d6-174">MBAM コンプライアンスステータスデータベースの設定を作成するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-174">Logs the actions taken to create the MBAM Compliance Status database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="6e7d6-175">InstallKeyComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="6e7d6-175">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="6e7d6-176">MBAM 回復とハードウェアデータベースを作成するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-176">Logs the actions taken to create the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="6e7d6-177">Addhelpdbauditusers .log</span><span class="sxs-lookup"><span data-stu-id="6e7d6-177">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="6e7d6-178">MBAM コンプライアンスステータスデータベースで SQL Server ログインを作成するために実行されたアクションをログに記録し、レポート用のデータベースへのヘルプデスク web サービスを承認します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-178">Logs the actions taken to create the SQL Server logins on the MBAM Compliance Status database and authorize helpdesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="6e7d6-179">Addhelpdbusers .log</span><span class="sxs-lookup"><span data-stu-id="6e7d6-179">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="6e7d6-180">Web サービスをデータベースに対して承認するために実行された操作を、キーの回復のためにログに記録し、MBAM 回復とハードウェアデータベースへのログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-180">Logs the actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="6e7d6-181">AddKeyComplianceDbUsers</span><span class="sxs-lookup"><span data-stu-id="6e7d6-181">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="6e7d6-182">Web サービスを認証するために実行されたアクションを、コンプライアンスレポート用の MBAM コンプライアンスステータスデータベースに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-182">Logs the actions taken to authorize web services to MBAM Compliance Status database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="6e7d6-183">Addrecoveryandハードウェア Dbusers .log</span><span class="sxs-lookup"><span data-stu-id="6e7d6-183">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="6e7d6-184">Web サービスを MBAM 回復とハードウェアデータベースに対して、キーの回復用に承認するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-184">Logs the actions taken to authorize web services to MBAM Recovery and Hardware database for key recovery.</span></span>

<span data-ttu-id="6e7d6-185">**注** MBAM セットアップログファイルを追加するには、 **msiexec**パッケージと **/l** location オプションを使用して、Microsoft BitLocker の管理と監視をインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-185">**Note** In order to obtain additional MBAM Setup log files, you must install Microsoft BitLocker Administration and Monitoring by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="6e7d6-186">指定した場所でログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-186">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="6e7d6-187">MBAM クライアントのセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="6e7d6-187">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="6e7d6-188">MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ</span><span class="sxs-lookup"><span data-stu-id="6e7d6-188">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="6e7d6-189">MBAM クライアントのインストール中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-189">Logs the actions taken during MBAM Client installation.</span></span>

## <span data-ttu-id="6e7d6-190">MBAM データベースの除外の考慮事項</span><span class="sxs-lookup"><span data-stu-id="6e7d6-190">MBAM Database TDE considerations</span></span>


<span data-ttu-id="6e7d6-191">SQL Server 2008 で利用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスに必要なインストール必須要件です。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-191">The Transparent Data Encryption (TDE) feature available in SQL Server 2008 is a required installation prerequisite for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="6e7d6-192">TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-192">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="6e7d6-193">TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化の選択肢として適しています。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-193">TDE is a well-suited choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="6e7d6-194">TDE は、2つの Windows 機能 (暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化) に似ていますが、どちらもハードドライブ上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-194">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="6e7d6-195">TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-195">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="6e7d6-196">データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-196">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="6e7d6-197">そのため、データベース暗号化キー (DEK) を保護するために使用された証明書がバックアップされ、データベースのバックアップで維持されるように、特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-197">Thus, special care must be taken to ensure that the certificate that was used to protect the Database Encryption Key (DEK) is backed up and maintained with the database backup.</span></span> <span data-ttu-id="6e7d6-198">証明書がない場合、データは解読されません。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-198">Without a certificate, the data will be unreadable.</span></span> <span data-ttu-id="6e7d6-199">データベースと共に証明書をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-199">Back up the certificate along with the database.</span></span> <span data-ttu-id="6e7d6-200">各証明書のバックアップには、2つのファイルが必要です。これらのファイルはどちらもアーカイブする必要があります。セキュリティのためにデータベースバックアップファイルから個別にアーカイブすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-200">Each certificate backup should have two files; both of these files should be archived .It is best to archive them separately from the database backup file for security.</span></span>

<span data-ttu-id="6e7d6-201">MBAM データベースインスタンスの TDE を有効にする方法の例については、「 [mbam 1.0 の評価](evaluating-mbam-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-201">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 1.0](evaluating-mbam-10.md).</span></span>

<span data-ttu-id="6e7d6-202">SQLServer 2008 の TDE の詳細については、「 [SQL Server 2008 Enterprise Edition のデータベース暗号化](https://go.microsoft.com/fwlink/?LinkId=269703)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6e7d6-202">For more information about TDE in SQLServer 2008, see [Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703).</span></span>

## <span data-ttu-id="6e7d6-203">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6e7d6-203">Related topics</span></span>


[<span data-ttu-id="6e7d6-204">MBAM 1.0 のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="6e7d6-204">Security and Privacy for MBAM 1.0</span></span>](security-and-privacy-for-mbam-10.md)

 

 





