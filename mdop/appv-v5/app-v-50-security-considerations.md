---
title: App-V 5.0 のセキュリティに関する考慮事項
description: App-V 5.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 1e7292a0-7972-4b4f-85a9-eaf33f6c563a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fcd740345be7f532502b8996d8d2b1f4437ed6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814810"
---
# <span data-ttu-id="cf81a-103">App-V 5.0 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="cf81a-103">App-V 5.0 Security Considerations</span></span>


<span data-ttu-id="cf81a-104">このトピックでは、アプリ-V 5.0 に関するアカウントとグループ、ログファイル、およびその他のセキュリティ関連の考慮事項について簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for App-V 5.0.</span></span>

**<span data-ttu-id="cf81a-105">重要</span><span class="sxs-lookup"><span data-stu-id="cf81a-105">Important</span></span>**  
<span data-ttu-id="cf81a-106">App-v 5.0 はセキュリティ製品ではないため、セキュリティ保護された環境に対する保証は提供されません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-106">App-V 5.0 is not a security product and does not provide any guarantees for a secure environment.</span></span>



## <span data-ttu-id="cf81a-107">PackageStoreAccessControl (PSAC) 機能は廃止されました</span><span class="sxs-lookup"><span data-stu-id="cf81a-107">PackageStoreAccessControl (PSAC) feature has been deprecated</span></span>


<span data-ttu-id="cf81a-108">2014年6月の発効。 Microsoft Application Virtualization (App-v) 5.0 Service Pack 2 (SP2) で導入された PackageStoreAccessControl (PSAC) 機能は、シングルユーザー環境とマルチユーザー環境の両方で廃止されました。</span><span class="sxs-lookup"><span data-stu-id="cf81a-108">Effective as of June, 2014, the PackageStoreAccessControl (PSAC) feature that was introduced in Microsoft Application Virtualization (App-V) 5.0 Service Pack 2 (SP2) has been deprecated in both single-user and multi-user environments.</span></span>

## <span data-ttu-id="cf81a-109">一般的なセキュリティの考慮事項</span><span class="sxs-lookup"><span data-stu-id="cf81a-109">General security considerations</span></span>


**<span data-ttu-id="cf81a-110">セキュリティのリスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-110">Understand the security risks.</span></span>** <span data-ttu-id="cf81a-111">App-v 5.0 に対する最も重大なリスクは、権限のないユーザーによって機能がハイジャックされ、App-v 5.0 クライアントでキーデータを再構成できるということです。</span><span class="sxs-lookup"><span data-stu-id="cf81a-111">The most serious risk to App-V 5.0 is that its functionality could be hijacked by an unauthorized user who could then reconfigure key data on App-V 5.0 clients.</span></span> <span data-ttu-id="cf81a-112">サービス拒否攻撃によって短期間の App-v 5.0 機能が失われた場合、通常、重大な影響はありません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-112">The loss of App-V 5.0 functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="cf81a-113">**コンピューターを物理的に保護**します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-113">**Physically secure your computers**.</span></span> <span data-ttu-id="cf81a-114">セキュリティは物理的なセキュリティがない状態では完了しません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-114">Security is incomplete without physical security.</span></span> <span data-ttu-id="cf81a-115">App-v 5.0 サーバーに物理的にアクセスできるすべての人が、クライアントベース全体を攻撃する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-115">Anyone with physical access to an App-V 5.0 server could potentially attack the entire client base.</span></span> <span data-ttu-id="cf81a-116">物理的な攻撃が発生する可能性がある場合は、リスクが高いと考えられ、適切に軽減されます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-116">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="cf81a-117">App-v 5.0 サーバーは、アクセスを管理することで、物理的にセキュリティ保護されたサーバールームに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-117">App-V 5.0 servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="cf81a-118">オペレーティングシステムによってコンピューターがロックされている場合、またはセキュアなスクリーンセーバーを使用している場合は、管理者が物理的に存在しない場合は、これらのコンピューターをセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-118">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="cf81a-119">**すべてのコンピューターに最新のセキュリティ更新プログラムを適用**します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-119">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="cf81a-120">オペレーティングシステム、Microsoft SQL Server、および App-v 5.0 向けの最新の更新プログラムについて常に情報を受け取るには、セキュリティ通知サービス () に加入して <https://go.microsoft.com/fwlink/p/?LinkId=28819> ください。</span><span class="sxs-lookup"><span data-stu-id="cf81a-120">To stay informed about the latest updates for operating systems, Microsoft SQL Server, and App-V 5.0, subscribe to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="cf81a-121">**強力なパスワードを使用するか、語句を渡し**ます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-121">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="cf81a-122">すべての App-v 5.0 および App-v 5.0 管理者アカウントでは、常に15文字以上の強力なパスワードを使用します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-122">Always use strong passwords with 15 or more characters for all App-V 5.0 and App-V 5.0 administrator accounts.</span></span> <span data-ttu-id="cf81a-123">空のパスワードは使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="cf81a-123">Never use blank passwords.</span></span> <span data-ttu-id="cf81a-124">パスワードの概念の詳細については、TechNet の「アカウントのパスワードとポリシー」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="cf81a-124">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="cf81a-125">App-v 5.0 のアカウントとグループ</span><span class="sxs-lookup"><span data-stu-id="cf81a-125">Accounts and groups in App-V 5.0</span></span>


<span data-ttu-id="cf81a-126">ユーザーアカウントの管理については、ドメイングローバルグループを作成し、ユーザーアカウントを追加することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="cf81a-126">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="cf81a-127">次に、ドメインのグローバルアカウントを、app-v 5.0 サーバー上の必要な App-v 5.0 ローカルグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-127">Then, add the domain global accounts to the necessary App-V 5.0 local groups on the App-V 5.0 servers.</span></span>

**<span data-ttu-id="cf81a-128">注</span><span class="sxs-lookup"><span data-stu-id="cf81a-128">Note</span></span>**  
<span data-ttu-id="cf81a-129">公開サーバーに接続する必要がある app-v クライアントコンピューターアカウントは、発行サーバーの**Users**ローカルグループに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-129">App-V client computer accounts that need to connect to the publishing server must be part of the publishing server’s **Users** local group.</span></span> <span data-ttu-id="cf81a-130">既定では、ドメイン内のすべてのコンピューターは、 **users**ローカルグループの一部である [権限のある**ユーザー** ] グループに含まれています。</span><span class="sxs-lookup"><span data-stu-id="cf81a-130">By default, all computers in the domain are part of the **Authorized Users** group, which is part of the **Users** local group.</span></span>



### <a href="" id="-------------app-v-5-0-server-security"></a> <span data-ttu-id="cf81a-131">App-v 5.0 server security</span><span class="sxs-lookup"><span data-stu-id="cf81a-131">App-V 5.0 server security</span></span>

<span data-ttu-id="cf81a-132">App-v 5.0 のセットアップ中に、自動的にグループが作成されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-132">No groups are created automatically during App-V 5.0 Setup.</span></span> <span data-ttu-id="cf81a-133">App-v 5.0 サーバーの操作を管理するには、次の Active Directory ドメインサービスのグローバルグループを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-133">You should create the following Active Directory Domain Services global groups to manage App-V 5.0 server operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cf81a-134">グループ名</span><span class="sxs-lookup"><span data-stu-id="cf81a-134">Group name</span></span></th>
<th align="left"><span data-ttu-id="cf81a-135">詳細</span><span class="sxs-lookup"><span data-stu-id="cf81a-135">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf81a-136">App-v 管理管理グループ</span><span class="sxs-lookup"><span data-stu-id="cf81a-136">App-V Management Admin group</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf81a-137">App-v 5.0 management server を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-137">Used to manage the App-V 5.0 management server.</span></span> <span data-ttu-id="cf81a-138">このグループは、App-v 5.0 Management Server のインストール中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-138">This group is created during the App-V 5.0 Management Server installation.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="cf81a-139">重要</span><span class="sxs-lookup"><span data-stu-id="cf81a-139">Important</span></span></strong><br/><p><span data-ttu-id="cf81a-140">インストールを完了した後、管理コンソールを使用してグループを作成する方法はありません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-140">There is no method to create the group using the management console after you have completed the installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cf81a-141">管理サービスアカウントのデータベース読み取り/書き込み</span><span class="sxs-lookup"><span data-stu-id="cf81a-141">Database read/write for Management Service account</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf81a-142">管理データベースへの読み取り/書き込みアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-142">Provides read/write access to the management database.</span></span> <span data-ttu-id="cf81a-143">このアカウントは、App-v 5.0 管理データベースのインストール中に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-143">This account should be created during the App-V 5.0 management database installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf81a-144">App-v 管理サービスのインストール管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="cf81a-144">App-V Management Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="cf81a-145">注</span><span class="sxs-lookup"><span data-stu-id="cf81a-145">Note</span></span></strong><br/><p><span data-ttu-id="cf81a-146">これは、管理データベースがサービスとは別にインストールされている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="cf81a-146">This is only required if management database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="cf81a-147">管理データベースのスキーマバージョンテーブルへのパブリックアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-147">Provides public access to schema-version table in management database.</span></span> <span data-ttu-id="cf81a-148">このアカウントは、App-v 5.0 管理データベースのインストール中に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-148">This account should be created during the App-V 5.0 management database installation.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cf81a-149">App-v Reporting Service のインストール管理者アカウント</span><span class="sxs-lookup"><span data-stu-id="cf81a-149">App-V Reporting Service install admin account</span></span></p>
<div class="alert">
<strong><span data-ttu-id="cf81a-150">注</span><span class="sxs-lookup"><span data-stu-id="cf81a-150">Note</span></span></strong><br/><p><span data-ttu-id="cf81a-151">これは、レポートデータベースがサービスとは別にインストールされている場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="cf81a-151">This is only required if reporting database is being installed separately from the service.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="cf81a-152">レポートデータベースのスキーマバージョンテーブルへのパブリックアクセス。</span><span class="sxs-lookup"><span data-stu-id="cf81a-152">Public access to schema-version table in reporting database.</span></span> <span data-ttu-id="cf81a-153">このアカウントは、App-v 5.0 レポートデータベースのインストール中に作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-153">This account should be created during the App-V 5.0 reporting database installation.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="cf81a-154">以下の追加情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="cf81a-154">Consider the following additional information:</span></span>

-   <span data-ttu-id="cf81a-155">パッケージ共有へのアクセス-共有が管理サーバーと同じコンピューター上に存在する場合、**ネットワーク**サービスは共有に対する読み取りアクセス許可を必要とします。</span><span class="sxs-lookup"><span data-stu-id="cf81a-155">Access to the package shares - If a share exists on the same computer as the management Server, the **Network** service requires read access to the share.</span></span> <span data-ttu-id="cf81a-156">また、各 App-v クライアントコンピューターには、パッケージ共有への読み取りアクセス権が必要です。</span><span class="sxs-lookup"><span data-stu-id="cf81a-156">In addition, each App-V client computer must have read access to the package share.</span></span>

    **<span data-ttu-id="cf81a-157">注</span><span class="sxs-lookup"><span data-stu-id="cf81a-157">Note</span></span>**  
    <span data-ttu-id="cf81a-158">以前のバージョンの App-v では、パッケージ共有はコンテンツ共有と呼ばれていました。</span><span class="sxs-lookup"><span data-stu-id="cf81a-158">In previous versions of App-V, package share was referred to as content share.</span></span>



-   <span data-ttu-id="cf81a-159">管理サーバーで発行サーバーを登録する-発行サーバーが管理サーバーに登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-159">Registering publishing servers with Management Server - A publishing server must be registered with the Management server.</span></span> <span data-ttu-id="cf81a-160">たとえば、発行サーバーのコンピューターアカウントが管理サービス API を呼び出すことができるように、データベースに追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cf81a-160">For example, it must be added to the database, so that the Publishing server machine accounts are able to call into the Management service API.</span></span>

### <a href="" id="-------------app-v-5-0-package-security"></a> <span data-ttu-id="cf81a-161">App-v 5.0 パッケージセキュリティ</span><span class="sxs-lookup"><span data-stu-id="cf81a-161">App-V 5.0 package security</span></span>

<span data-ttu-id="cf81a-162">以下は、仮想化されたパッケージのセキュリティを確保する方法を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-162">The following will help you plan how to ensure that virtualized packages are secure.</span></span>

-   <span data-ttu-id="cf81a-163">アプリケーションインストーラーがアクセス制御リスト (ACL) をファイルまたはディレクトリに適用すると、その ACL はパッケージ内で保持されません。</span><span class="sxs-lookup"><span data-stu-id="cf81a-163">If an application installer applies an access control list (ACL) to a file or directory, then that ACL is not persisted in the package.</span></span> <span data-ttu-id="cf81a-164">パッケージが展開されると、ファイルまたはディレクトリがユーザーによって変更された場合は、 **% userprofile%** の acl を継承するか、またはターゲットコンピューターのディレクトリの acl を継承します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-164">When the package is deployed, if the file or directory is modified by a user it will either inherit the ACL in the **%userprofile%** or inherit the ACL of the target computer’s directory.</span></span> <span data-ttu-id="cf81a-165">前者のケースは、ファイルまたはディレクトリが仮想ファイルシステムの場所に存在しない場合に発生します。後者のケースは、ファイルまたはディレクトリが仮想ファイルシステムの場所 ( **% windir%** など) に存在する場合に発生します。</span><span class="sxs-lookup"><span data-stu-id="cf81a-165">The former case occurs if the file or directory does not exist in a virtual file system location; the latter case occurs if the file or directory exists in a virtual file system location, for example **%windir%**.</span></span>

## <a href="" id="---------app-v-5-0-log-files"></a> <span data-ttu-id="cf81a-166">App-v 5.0 ログファイル</span><span class="sxs-lookup"><span data-stu-id="cf81a-166">App-V 5.0 log files</span></span>


<span data-ttu-id="cf81a-167">App-v 5.0 のセットアップ中に、セットアップログファイルは、インストールユーザーの **% temp%** フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="cf81a-167">During App-V 5.0 Setup, setup log files are created in the **%temp%** folder of the installing user.</span></span>