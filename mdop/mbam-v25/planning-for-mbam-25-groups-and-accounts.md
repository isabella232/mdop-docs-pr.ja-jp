---
title: MBAM 2.5 グループとアカウントの計画
description: MBAM 2.5 グループとアカウントの計画
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825804"
---
# <span data-ttu-id="9acce-103">MBAM 2.5 グループとアカウントの計画</span><span class="sxs-lookup"><span data-stu-id="9acce-103">Planning for MBAM 2.5 Groups and Accounts</span></span>


<span data-ttu-id="9acce-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) データベース、レポート、および web アプリケーションのセキュリティとアクセス権を提供するために、Active Directory ドメインサービス (AD DS) で作成する必要がある役割とアカウントの一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9acce-104">This topic lists the roles and accounts that you must create in Active Directory Domain Services (AD DS) to provide security and access rights for the Microsoft BitLocker Administration and Monitoring (MBAM) databases, reports, and web applications.</span></span> <span data-ttu-id="9acce-105">各ロールとアカウントについて、MBAM サーバー構成ウィザードの対応するフィールドが提供されています。</span><span class="sxs-lookup"><span data-stu-id="9acce-105">For each role and account, the corresponding field in the MBAM Server Configuration wizard is provided.</span></span> <span data-ttu-id="9acce-106">これらのアカウントに対応する Windows PowerShell コマンドレットとパラメーターの一覧については、「 [Windows Powershell を使用して MBAM 2.5 サーバー機能を構成](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9acce-106">For a list of Windows PowerShell cmdlets and parameters that correspond to these accounts, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts).</span></span>

**<span data-ttu-id="9acce-107">注</span><span class="sxs-lookup"><span data-stu-id="9acce-107">Note</span></span>**  
<span data-ttu-id="9acce-108">MBAM は、管理されたサービスアカウントの使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="9acce-108">MBAM does not support the use of managed service accounts.</span></span>



## <span data-ttu-id="9acce-109">データベースアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-109">Database accounts</span></span>


<span data-ttu-id="9acce-110">コンプライアンスと監査データベースおよび回復データベースの次のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9acce-110">Create the following accounts for the Compliance and Audit Database and the Recovery Database.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9acce-111">アカウント名と目的</span><span class="sxs-lookup"><span data-stu-id="9acce-111">Account name and purpose</span></span></th>
<th align="left"><span data-ttu-id="9acce-112">アカウントの種類</span><span class="sxs-lookup"><span data-stu-id="9acce-112">Account type</span></span></th>
<th align="left"><span data-ttu-id="9acce-113">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</span><span class="sxs-lookup"><span data-stu-id="9acce-113">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="9acce-114">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</span><span class="sxs-lookup"><span data-stu-id="9acce-114">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9acce-115">コンプライアンスと監査データベースと復元データベースの読み取り/書き込みのユーザーまたはレポートのグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-115">Compliance and Audit Database and Recovery Database read/write user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-116">ユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-116">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-117">読み取り/書き込みアクセスドメインユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-117">Read/write access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-118">コンプライアンスと監査データベースへの読み取り/書き込みアクセス許可を持つドメインユーザーまたはグループ。また、web アプリケーションがこれらのデータベースのデータとレポートにアクセスできるようにするための回復データベースです。</span><span class="sxs-lookup"><span data-stu-id="9acce-118">Domain user or group that has read/write access to the Compliance and Audit Database and the Recovery Database to enable the web applications to access the data and reports in these databases.</span></span></p>
<p><span data-ttu-id="9acce-119">このフィールドにユーザー名を入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値と同じ値にする必要があり </strong> <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="9acce-119">If you enter a user name in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
<p><span data-ttu-id="9acce-120">このフィールドにグループ名を入力した場合、[ <strong> Web アプリケーションの構成] ページの [web サービスアプリケーションプールのドメインアカウント] フィールドの値は、 </strong> <strong> </strong> このフィールドに入力するグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-120">If you enter a group name in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9acce-121">コンプライアンスおよび監査データベース読み取り専用ユーザーまたはレポート用グループ</span><span class="sxs-lookup"><span data-stu-id="9acce-121">Compliance and Audit Database read-only user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-122">ユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-122">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-123">読み取り専用アクセスドメインのユーザーまたはグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-123">Read-only access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-124">コンプライアンスと監査データベースへの読み取り専用アクセスが許可されているユーザーまたはグループの名前。レポートがこのデータベースのコンプライアンスと監査データにアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="9acce-124">Name of the user or group that will have read-only access to the Compliance and Audit Database to enable the reports to access the compliance and audit data in this database.</span></span></p>
<p><span data-ttu-id="9acce-125">このフィールドにユーザー名を入力した場合、[ <strong> </strong> レポートの構成] ページの [コンプライアンスおよび監査データベースドメインアカウント] フィールドで指定したユーザーと同じユーザー名を入力する必要があり <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="9acce-125">If you enter a user name in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
<p><span data-ttu-id="9acce-126">このフィールドにグループ名を入力した場合、[ <strong> レポートの構成] ページの [コンプライアンスと監査データベースのドメインアカウント] フィールドで指定した値は、 </strong> <strong> </strong> このフィールドで指定したグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-126">If you enter a group name in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="9acce-127">レポートアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-127">Reporting accounts</span></span>


<span data-ttu-id="9acce-128">レポート機能に対して次のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9acce-128">Create the following accounts for the Reports feature.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9acce-129">アカウント名/目的</span><span class="sxs-lookup"><span data-stu-id="9acce-129">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="9acce-130">アカウントの種類</span><span class="sxs-lookup"><span data-stu-id="9acce-130">Account type</span></span></th>
<th align="left"><span data-ttu-id="9acce-131">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</span><span class="sxs-lookup"><span data-stu-id="9acce-131">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="9acce-132">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</span><span class="sxs-lookup"><span data-stu-id="9acce-132">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9acce-133">レポート読み取り専用ドメインアクセスグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-133">Reports read-only domain access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-134">Group</span><span class="sxs-lookup"><span data-stu-id="9acce-134">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-135">レポート役割のドメイングループ</span><span class="sxs-lookup"><span data-stu-id="9acce-135">Reporting role domain group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-136">管理および監視 Web サイトのレポートに対して読み取り専用のアクセス権を持つドメインユーザーグループを指定します。</span><span class="sxs-lookup"><span data-stu-id="9acce-136">Specifies the domain user group that has read-only access to the reports in the Administration and Monitoring Website.</span></span> <span data-ttu-id="9acce-137">指定するグループは、web アプリが有効になっているときに、レポートの読み取り専用アクセスグループパラメーターとして指定したグループと同じグループである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-137">The group you specify must be the same group you specified for the Reports Read Only Access Group parameter when the web apps are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9acce-138">コンプライアンスと監査データベースドメインのユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-138">Compliance and Audit Database domain user account</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-139">ユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-139">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-140">コンプライアンスと監査データベースのドメインアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-140">Compliance and Audit Database domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-141">ローカル SQL Server Reporting Services インスタンスがコンプライアンスと監査データベースにアクセスするために使用するドメインユーザーアカウントとパスワード。</span><span class="sxs-lookup"><span data-stu-id="9acce-141">Domain user account and password that the local SQL Server Reporting Services instance uses to access the Compliance and Audit Database.</span></span> <span data-ttu-id="9acce-142">このアカウントに <strong> </strong> は、SQL Server Reporting Services サーバーへのバッチ権限としてログオンする権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="9acce-142">This account requires <strong>Log On as Batch</strong> rights to the SQL Server Reporting Services server.</span></span></p>
<p><span data-ttu-id="9acce-143">[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値がユーザー名である場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-143">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user name, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="9acce-144">[ <strong> データベースの構成] ページの [読み取り専用アクセスドメインユーザーまたはグループ] フィールドに入力した値 </strong> <strong> がグループ名である場合 </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-144">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group name, the value that you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="9acce-145">有効期限が切れないように、このアカウントのパスワードを設定します。</span><span class="sxs-lookup"><span data-stu-id="9acce-145">Configure the password for this account to never expire.</span></span> <span data-ttu-id="9acce-146">ユーザーアカウントは、MBAM Reports Users グループで利用できるすべてのデータにアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-146">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a><span data-ttu-id="9acce-147">管理と監視 Web サイト (ヘルプデスク) アカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-147">Administration and Monitoring Website (Help Desk) accounts</span></span>


<span data-ttu-id="9acce-148">管理と監視の Web サイトに次のアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="9acce-148">Create the following accounts for the Administration and Monitoring Website.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9acce-149">アカウント名/目的</span><span class="sxs-lookup"><span data-stu-id="9acce-149">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="9acce-150">アカウントの種類</span><span class="sxs-lookup"><span data-stu-id="9acce-150">Account type</span></span></th>
<th align="left"><span data-ttu-id="9acce-151">このアカウントに対応する MBAM サーバー構成ウィザードフィールド</span><span class="sxs-lookup"><span data-stu-id="9acce-151">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="9acce-152">このアカウントに対応する MBAM サーバー構成ウィザードのフィールドの説明</span><span class="sxs-lookup"><span data-stu-id="9acce-152">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9acce-153">Web サービスアプリケーションプールドメインアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-153">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-154">ユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-154">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-155">Web サービスアプリケーションプールドメインアカウント</span><span class="sxs-lookup"><span data-stu-id="9acce-155">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-156">Web アプリケーションのアプリケーションプールによって使用されるドメインユーザーアカウント。</span><span class="sxs-lookup"><span data-stu-id="9acce-156">Domain user account to be used by the application pool for the web applications.</span></span></p>
<p><span data-ttu-id="9acce-157">[ <strong> データベースの構成] ページの [読み取り/書き込み権限ドメインユーザーまたはグループ] フィールドにユーザー名を入力した場合は、 </strong> <strong> </strong> このフィールドに同じ値を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-157">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="9acce-158">[ <strong> データベースの構成] ページの [読み取り/書き込みアクセスドメインユーザーまたはグループ] フィールドにグループ名を入力した場合 </strong> <strong> </strong> 、このフィールドに入力する値は、そのグループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-158">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="9acce-159">資格情報を指定しない場合、以前に有効になっていた web アプリケーションに指定された資格情報が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9acce-159">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="9acce-160">すべての web アプリケーションは、同じアプリケーションプールの資格情報を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-160">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="9acce-161">Web アプリケーションごとに異なる資格情報を指定すると、最後に指定された値が使用されます。</span><span class="sxs-lookup"><span data-stu-id="9acce-161">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="9acce-162">重要</span><span class="sxs-lookup"><span data-stu-id="9acce-162">Important</span></span></strong><br/><p><span data-ttu-id="9acce-163">セキュリティを向上させるには、資格情報で指定されているアカウントに、制限付きのユーザー権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="9acce-163">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9acce-164">MBAM Advanced ヘルプデスクユーザーアクセスグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-164">MBAM Advanced Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-165">Group</span><span class="sxs-lookup"><span data-stu-id="9acce-165">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-166">MBAM Advanced ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-166">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-167">管理と監視の Web サイトのすべての回復領域にメンバーがアクセスできるドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="9acce-167">Domain user group whose members have access to all recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="9acce-168">この役割を持つユーザーは、エンドユーザーがドライブを回復するときに、エンドユーザーのドメインとユーザー名ではなく、回復キーのみを入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-168">Users who have this role have to enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="9acce-169">Mbam ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのグループ権限よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9acce-169">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9acce-170">MBAM ヘルプデスクユーザーアクセスグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-170">MBAM Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-171">Group</span><span class="sxs-lookup"><span data-stu-id="9acce-171">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-172">MBAM ヘルプデスクユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-172">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-173">「MBAM 管理および監視 Web サイトの TPM およびドライブ回復の領域を管理する」にアクセスできるメンバーのドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="9acce-173">Domain user group whose members have access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="9acce-174">この役割を持つユーザーは、いずれかのオプションを使用する場合は、エンドユーザーのドメインとアカウント名を含むすべてのフィールドに入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9acce-174">Individuals who have this role must fill-in all fields, including the end-user’s domain and account name, when they use either option.</span></span></p>
<p><span data-ttu-id="9acce-175">Mbam ヘルプデスクユーザーグループと MBAM Advanced ヘルプデスクユーザーグループの両方のメンバーである場合、MBAM Advanced ヘルプデスクのユーザーグループの権限は、MBAM ヘルプデスクのグループ権限よりも優先されます。</span><span class="sxs-lookup"><span data-stu-id="9acce-175">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9acce-176">MBAM レポートユーザーアクセスグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-176">MBAM Report Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-177">Group</span><span class="sxs-lookup"><span data-stu-id="9acce-177">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-178">MBAM レポートユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-178">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-179">管理および監視 Web サイトの [レポート] 領域のレポートに対する読み取り専用アクセス権を持つメンバーのドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="9acce-179">Domain user group whose members have read-only access to the reports in the Reports area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9acce-180">MBAM データ移行ユーザーグループ</span><span class="sxs-lookup"><span data-stu-id="9acce-180">MBAM Data Migration User Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-181">Group</span><span class="sxs-lookup"><span data-stu-id="9acce-181">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-182">MBAM データ移行ユーザー</span><span class="sxs-lookup"><span data-stu-id="9acce-182">MBAM Data Migration Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="9acce-183">Mbam サーバー上で実行されている MBAM 回復とハードウェアサービスを使用して、メンバーが MBAM にデータを書き込む権限を持つ、オプションのドメインユーザーグループ。</span><span class="sxs-lookup"><span data-stu-id="9acce-183">Optional domain user group whose members have permissions to write data to MBAM by using the MBAM Recovery and Hardware Service running on the MBAM server.</span></span> <span data-ttu-id="9acce-184">通常、このアカウントは、書き込み/Mbam \* コマンドレットと共に使用され、回復と TPM データを Active Directory から MBAM データベースに書き込みます。</span><span class="sxs-lookup"><span data-stu-id="9acce-184">This account is generally used with the Write-Mbam\* cmdlets to write recovery and TPM data from Active Directory into the MBAM database.</span></span></p>
<p><span data-ttu-id="9acce-185">詳細については、「 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> mbam 2.5 セキュリティに関する考慮事項」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="9acce-185">For more information, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="9acce-186">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9acce-186">Related topics</span></span>


[<span data-ttu-id="9acce-187">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="9acce-187">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="9acce-188">MBAM 2.5 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="9acce-188">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)



## <span data-ttu-id="9acce-189">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="9acce-189">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9acce-190">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9acce-190">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9acce-191">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="9acce-191">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





