---
title: MBAM 2.0 のセキュリティ上の考慮事項
description: MBAM 2.0 のセキュリティ上の考慮事項
author: dansimp
ms.assetid: 0aa5c6e2-d92c-4e30-9f6a-b48abb667ae5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 04dc9b667faddecab629b50f4c5d909fd7b2829e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823914"
---
# <span data-ttu-id="c0f06-103">MBAM 2.0 のセキュリティ上の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c0f06-103">MBAM 2.0 Security Considerations</span></span>


<span data-ttu-id="c0f06-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="c0f06-105">詳細については、この記事に記載されているリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f06-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="c0f06-106">一般的なセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="c0f06-106">General Security Considerations</span></span>


**<span data-ttu-id="c0f06-107">セキュリティのリスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-107">Understand the security risks.</span></span>** <span data-ttu-id="c0f06-108">Microsoft BitLocker の管理と監視の最も重大なリスクは、BitLocker 暗号化を再構成し、MBAM クライアントで BitLocker 暗号化キーデータを取得できる、承認されていないユーザーがその機能をハイジャックする可能性があるということです。</span><span class="sxs-lookup"><span data-stu-id="c0f06-108">The most serious risk from Microsoft BitLocker Administration and Monitoring is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="c0f06-109">ただし、サービス拒否攻撃のために MBAM 機能が短期間で失われても、メール、ネットワーク通信、ライト、停電などのように、通常、壊滅的な影響を受けることはありません。</span><span class="sxs-lookup"><span data-stu-id="c0f06-109">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, e-mail, network communications, light, and power.</span></span>

<span data-ttu-id="c0f06-110">**コンピューターを物理的に保護**します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-110">**Physically secure your computers**.</span></span> <span data-ttu-id="c0f06-111">物理的なセキュリティがない場合は、セキュリティは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c0f06-111">There is no security without physical security.</span></span> <span data-ttu-id="c0f06-112">MBAM サーバーに物理的にアクセスできる攻撃者は、クライアントベース全体を攻撃するためにそれを使用する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-112">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="c0f06-113">すべての潜在的な物理的な攻撃は、高リスクと見なされ、適切に軽減する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-113">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="c0f06-114">MBAM サーバは、アクセスを制御できる安全なサーバールームに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-114">MBAM servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="c0f06-115">オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="c0f06-116">**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="c0f06-117">セキュリティ通知サービス () をサブスクライブすることにより、オペレーティングシステム、Microsoft SQL Server、MBAM の新しい更新について常に情報を受け取ることが <https://go.microsoft.com/fwlink/?LinkId=28819> できます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

<span data-ttu-id="c0f06-118">**強力なパスワードを使用するか、語句を渡し**ます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="c0f06-119">すべての MBAM および MBAM 管理者アカウントには、必ず15文字以上の強力なパスワードを使用してください。</span><span class="sxs-lookup"><span data-stu-id="c0f06-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="c0f06-120">空のパスワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="c0f06-120">Never use blank passwords.</span></span> <span data-ttu-id="c0f06-121">パスワードの概念の詳細については、TechNet の「アカウントのパスワードとポリシー」を参照してください <https://go.microsoft.com/fwlink/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="c0f06-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/?LinkId=30009>).</span></span>

## <span data-ttu-id="c0f06-122">MBAM のアカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="c0f06-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="c0f06-123">ユーザーアカウントを管理するためのベストプラクティスは、ドメイングローバルグループを作成し、ユーザーアカウントを追加することです。</span><span class="sxs-lookup"><span data-stu-id="c0f06-123">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="c0f06-124">次に、MBAM サーバー上の必要な MBAM ローカルグループにドメインのグローバルアカウントを追加します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="c0f06-125">ActiveDirectoryDomainServices グループ</span><span class="sxs-lookup"><span data-stu-id="c0f06-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="c0f06-126">MBAM セットアッププロセス中に、Active Directory グループは自動的に作成されません。</span><span class="sxs-lookup"><span data-stu-id="c0f06-126">No Active Directory groups are created automatically during the MBAM setup process.</span></span> <span data-ttu-id="c0f06-127">ただし、MBAM 操作を管理するには、次の ActiveDirectoryDomainServices グローバルグループを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c0f06-127">However, it is recommended that you create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0f06-128">グループ名</span><span class="sxs-lookup"><span data-stu-id="c0f06-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="c0f06-129">詳細</span><span class="sxs-lookup"><span data-stu-id="c0f06-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-130">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-131">このグループを作成して、MBAM セットアップで作成された MBAM Advanced ヘルプデスクユーザーのローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-132">MBAM コンプライアンス監査データベースアクセス</span><span class="sxs-lookup"><span data-stu-id="c0f06-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-133">Mbam セットアップで作成された MBAM コンプライアンス監査 DB Access ローカルグループのメンバーを管理するには、このグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-134">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-134">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-135">このグループを作成すると、MBAM セットアップで作成された MBAM ヘルプデスクユーザーのローカルグループのメンバーを管理できます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-135">Create this group to manage members of the MBAM Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-136">MBAM 回復とハードウェアデータベースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c0f06-136">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-137">このグループを作成して、MBAM セットアップで作成された MBAM Recovery とハードウェア DB Access ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-137">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-138">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-138">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-139">Mbam セットアップで作成された MBAM レポートのローカルグループのメンバーを管理するには、このグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-139">Create this group to manage members of the MBAM Report Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-140">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="c0f06-140">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-141">このグループを作成して、MBAM セットアップで作成した MBAM システム管理者ローカルグループのメンバーを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-141">Create this group to manage members of the MBAM System Administrators local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-142">BitLocker 暗号化の除外</span><span class="sxs-lookup"><span data-stu-id="c0f06-142">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-143">このグループを作成して、ログオン先のコンピューターで開始する BitLocker 暗号化から除外する必要があるユーザーアカウントを管理します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-143">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------mbam-server-local-groups"></a> <span data-ttu-id="c0f06-144">MBAM サーバーのローカルグループ</span><span class="sxs-lookup"><span data-stu-id="c0f06-144">MBAM Server Local Groups</span></span>

<span data-ttu-id="c0f06-145">MBAM セットアップは、MBAM 操作をサポートするローカルグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-145">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="c0f06-146">MBAM セキュリティとデータアクセス権限を構成するために、適切な MBAM ローカルグループに ActiveDirectoryDomainServices グローバルグループを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-146">You should add the ActiveDirectoryDomainServices global groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0f06-147">グループ名</span><span class="sxs-lookup"><span data-stu-id="c0f06-147">Group Name</span></span></th>
<th align="left"><span data-ttu-id="c0f06-148">詳細</span><span class="sxs-lookup"><span data-stu-id="c0f06-148">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-149">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-149">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-150">このグループのメンバーは、MBAM からのヘルプデスク機能へのアクセス権を強化しています。</span><span class="sxs-lookup"><span data-stu-id="c0f06-150">Members of this group have increased access to the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-151">MBAM コンプライアンス監査データベースアクセス</span><span class="sxs-lookup"><span data-stu-id="c0f06-151">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-152">MBAM コンプライアンスおよび監査データベースへのアクセス権を持つコンピューターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0f06-152">Contains the machines that have access to the MBAM Compliance and Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-153">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-153">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-154">このグループのメンバーは、MBAM のヘルプデスクの一部の機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-154">Members of this group have access to some of the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-155">MBAM 回復とハードウェアデータベースへのアクセス</span><span class="sxs-lookup"><span data-stu-id="c0f06-155">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-156">MBAM 回復データベースへのアクセス権を持つコンピューターが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c0f06-156">Contains the machines that have access to the MBAM Recovery Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0f06-157">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="c0f06-157">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-158">このグループのメンバーは、MBAM からのコンプライアンスおよび監査レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-158">Members of this group have access to the Compliance and Audit reports from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0f06-159">MBAM システム管理者</span><span class="sxs-lookup"><span data-stu-id="c0f06-159">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0f06-160">このグループのメンバーは、すべての MBAM 機能にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-160">Members of this group have access to all MBAM features.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c0f06-161">SSRS レポートサービスアカウント</span><span class="sxs-lookup"><span data-stu-id="c0f06-161">SSRS Reports Service Account</span></span>

<span data-ttu-id="c0f06-162">SSRS レポートサービスアカウントは、SSRS で利用可能な MBAM レポートを実行するためのセキュリティコンテキストを提供します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-162">The SSRS Reports service account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="c0f06-163">これは、MBAM セットアップ中に構成されます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-163">It is configured during MBAM Setup.</span></span>

<span data-ttu-id="c0f06-164">SSRS レポートサービスアカウントを構成する場合は、ドメインユーザーアカウントを指定し、有効期限が切れないようにパスワードを構成します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-164">When you configure the SSRS Reports service account, specify a domain user account, and configure the password to never expire.</span></span>

<span data-ttu-id="c0f06-165">**注** MBAM の展開後にサービスアカウントの名前を変更する場合は、新しいサービスアカウントの資格情報を使用するようにレポートデータソースを再設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-165">**Note** If you change the name of the service account after you deploy MBAM, you must reconfigure the reporting data source to use the new service account credentials.</span></span> <span data-ttu-id="c0f06-166">そうしないと、ヘルプデスクポータルにアクセスできなくなります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-166">Otherwise, you will not be able to access the Help Desk Portal.</span></span>

 

## <a href="" id="---------mbam-log-files"></a> <span data-ttu-id="c0f06-167">MBAM ログファイル</span><span class="sxs-lookup"><span data-stu-id="c0f06-167">MBAM Log Files</span></span>


<span data-ttu-id="c0f06-168">MBAM セットアップ中に、インストールユーザーの% temp% フォルダーに、次の MBAM セットアップログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-168">The following MBAM Setup log files are created in the installing user’s %temp% folder during MBAM Setup:</span></span>

**<span data-ttu-id="c0f06-169">MBAM サーバーセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="c0f06-169">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="c0f06-170">MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ</span><span class="sxs-lookup"><span data-stu-id="c0f06-170">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="c0f06-171">MBAM セットアップおよび MBAM サーバー機能のインストール中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-171">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="c0f06-172">InstallComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="c0f06-172">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="c0f06-173">MBAM コンプライアンスと監査データベースの設定を作成するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-173">Logs actions taken to create the MBAM Compliance and Audit Database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="c0f06-174">InstallKeyComplianceDatabase</span><span class="sxs-lookup"><span data-stu-id="c0f06-174">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="c0f06-175">MBAM 回復データベースを作成するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-175">Logs actions taken to create the MBAM Recovery Database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="c0f06-176">Addhelpdbauditusers .log</span><span class="sxs-lookup"><span data-stu-id="c0f06-176">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="c0f06-177">MBAM コンプライアンスおよび監査データベース上で SQL Server ログインを作成するために実行されたアクションをログに記録し、レポートのデータベースに対してヘルプデスク web サービスを承認します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-177">Logs actions taken to create the SQL Server logins on the MBAM Compliance and Audit database and authorize the HelpDesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="c0f06-178">Addhelpdbusers .log</span><span class="sxs-lookup"><span data-stu-id="c0f06-178">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="c0f06-179">キーの回復のために web サービスをデータベースに承認するために実行されたアクションをログに記録し、MBAM 回復データベースへのログインを作成します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-179">Logs actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery Database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="c0f06-180">AddKeyComplianceDbUsers</span><span class="sxs-lookup"><span data-stu-id="c0f06-180">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="c0f06-181">Web サービスを認証するために実行された操作を、コンプライアンスレポートのための MBAM コンプライアンスおよび監査データベースに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-181">Logs actions taken to authorize web services to MBAM Compliance and Audit Database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="c0f06-182">Addrecoveryandハードウェア Dbusers .log</span><span class="sxs-lookup"><span data-stu-id="c0f06-182">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="c0f06-183">Web サービスをキー回復用の MBAM 回復データベースに承認するために実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-183">Logs actions taken to authorize web services to the MBAM Recovery database for key recovery.</span></span>

<span data-ttu-id="c0f06-184">**注** MBAM セットアップログファイルを追加するには、msiexec.exe パッケージと/L location オプションを使用して MBAM をインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-184">**Note** In order to obtain additional MBAM Setup log files, you have to install MBAM by using the msiexec package and the /L &lt;location&gt; option.</span></span> <span data-ttu-id="c0f06-185">指定した場所でログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-185">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="c0f06-186">MBAM クライアントのセットアップログファイル</span><span class="sxs-lookup"><span data-stu-id="c0f06-186">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="c0f06-187">MSI <em> &lt; 5 ランダム文字 &gt; </em> ログ</span><span class="sxs-lookup"><span data-stu-id="c0f06-187">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="c0f06-188">MBAM クライアントのインストール中に実行されたアクションをログに記録します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-188">Logs the actions taken during MBAM Client installation.</span></span>

## <a href="" id="---------mbam-database-tde-considerations"></a> <span data-ttu-id="c0f06-189">MBAM データベースの除外の考慮事項</span><span class="sxs-lookup"><span data-stu-id="c0f06-189">MBAM Database TDE Considerations</span></span>


<span data-ttu-id="c0f06-190">SQL Server で使用できる透過データ暗号化 (TDE) 機能は、MBAM データベース機能をホストするデータベースインスタンスのオプションのインストールです。</span><span class="sxs-lookup"><span data-stu-id="c0f06-190">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="c0f06-191">TDE では、リアルタイムの完全なデータベースレベルの暗号化を実行できます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-191">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="c0f06-192">TDE は、法令遵守または企業データセキュリティ標準に準拠するために、一括暗号化に最適な選択肢です。</span><span class="sxs-lookup"><span data-stu-id="c0f06-192">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="c0f06-193">TDE は、2つの Windows 機能 (暗号化ファイルシステム (EFS) と BitLocker ドライブ暗号化) に似ていますが、どちらもハードドライブ上のデータを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c0f06-193">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="c0f06-194">TDE では、セルレベルの暗号化、EFS、または BitLocker は置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="c0f06-194">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="c0f06-195">データベースで TDE を有効にすると、すべてのバックアップが暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="c0f06-195">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="c0f06-196">そのため、データベース暗号化キーを保護するために使用された証明書がバックアップされ、データベースのバックアップと維持されるように、特別な注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-196">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="c0f06-197">この証明書 (または証明書) が失われると、データを読み取ることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c0f06-197">If this certificate (or certificates) is lost, the data will be unreadable.</span></span> <span data-ttu-id="c0f06-198">データベースと共に証明書をバックアップします。</span><span class="sxs-lookup"><span data-stu-id="c0f06-198">Back up the certificate along with the database.</span></span> <span data-ttu-id="c0f06-199">各証明書のバックアップには、2つのファイルが必要です。</span><span class="sxs-lookup"><span data-stu-id="c0f06-199">Each certificate backup should have two files.</span></span> <span data-ttu-id="c0f06-200">これらのファイルはどちらもアーカイブする必要があります (理想的には、セキュリティのためにデータベースのバックアップファイルとは別に用意されています)。</span><span class="sxs-lookup"><span data-stu-id="c0f06-200">Both of these files should be archived (ideally separately from the database backup file for security).</span></span> <span data-ttu-id="c0f06-201">または、拡張キー管理 (EKM) 機能の使用を検討してください (「拡張キー管理」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="c0f06-201">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys used for TDE.</span></span>

<span data-ttu-id="c0f06-202">MBAM データベースインスタンスの TDE を有効にする方法の例については、「 [mbam 2.0 の評価](evaluating-mbam-20-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f06-202">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 2.0](evaluating-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="c0f06-203">SQLServer 2008 の TDE の詳細については、「 [SQL Server の暗号化]( https://go.microsoft.com/fwlink/?LinkId=299883)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0f06-203">For more information about TDE in SQLServer 2008, see [SQL Server Encryption]( https://go.microsoft.com/fwlink/?LinkId=299883).</span></span>

## <span data-ttu-id="c0f06-204">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c0f06-204">Related topics</span></span>


[<span data-ttu-id="c0f06-205">MBAM 2.0 のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="c0f06-205">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)

 

 





