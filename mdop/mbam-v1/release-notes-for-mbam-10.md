---
title: MBAM 1.0 のリリース ノート
description: MBAM 1.0 のリリース ノート
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826027"
---
# <span data-ttu-id="559cc-103">MBAM 1.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="559cc-103">Release Notes for MBAM 1.0</span></span>


**<span data-ttu-id="559cc-104">これらのリリースノートで特定の問題を検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="559cc-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="559cc-105">Microsoft BitLocker の管理と監視 (MBAM) をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="559cc-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

<span data-ttu-id="559cc-106">これらのリリースノートには、MBAM の正常なインストールに必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="559cc-106">These release notes contain information that is required to successfully install MBAM.</span></span> <span data-ttu-id="559cc-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="559cc-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="559cc-108">リリースノートとその他の MBAM ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="559cc-108">If there is a difference between these release notes and other MBAM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="559cc-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="559cc-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="559cc-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="559cc-110">About the Product Documentation</span></span>


<span data-ttu-id="559cc-111">MBAM ドキュメントの詳細については、「Microsoft TechNet の MBAM ホームページ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="559cc-111">For information about MBAM documentation, see the MBAM home page on Microsoft TechNet.</span></span>

<span data-ttu-id="559cc-112">MBAM ドキュメントのダウンロード可能なコピーを入手するには、 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft ダウンロードセンターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="559cc-112">To obtain a downloadable copy of the MBAM documentation, see <https://go.microsoft.com/fwlink/p/?LinkId=225356> on the Microsoft Download Center.</span></span>

## <span data-ttu-id="559cc-113">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="559cc-113">Provide Feedback</span></span>


<span data-ttu-id="559cc-114">当社では、MBAM についてのご意見をお寄せしています。</span><span class="sxs-lookup"><span data-stu-id="559cc-114">We are interested in your feedback on MBAM.</span></span> <span data-ttu-id="559cc-115">にフィードバックを送信でき <mdopdocs@microsoft.com> ます。</span><span class="sxs-lookup"><span data-stu-id="559cc-115">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="559cc-116">**注** このメールアドレスはサポートチャネルではありませんが、お客様のフィードバックは、今後のドキュメントや製品リリースの将来の変更を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="559cc-116">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="559cc-117">MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="559cc-117">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="559cc-118">新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="559cc-118">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="559cc-119">MBAM 1.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="559cc-119">Known Issues with MBAM 1.0</span></span>


<span data-ttu-id="559cc-120">このセクションには、MBAM セットアップとインストールに関する既知の問題に関するリリースノートが記載されています。</span><span class="sxs-lookup"><span data-stu-id="559cc-120">This section contains release notes about the known issues with MBAM setup and installation.</span></span>

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a><span data-ttu-id="559cc-121">セットアップ時に [証明書を使用してネットワーク通信を暗号化する] オプションを選択した場合、既存のデータベース接続と依存アプリケーションが機能しなくなることがある</span><span class="sxs-lookup"><span data-stu-id="559cc-121">If you select the “Use a certificate to encrypt the network communication” option during Setup, existing database connections and dependent applications can stop functioning</span></span>

<span data-ttu-id="559cc-122">回復とハードウェアデータベースまたはコンプライアンスステータスデータベース機能のいずれかをインストールした後は、**暗号化されたネットワーク通信**用に mbam を構成できます。</span><span class="sxs-lookup"><span data-stu-id="559cc-122">You can configure MBAM for **Encrypted network communication** after you install either the Recovery and Hardware Database or the Compliance Status Database features.</span></span> <span data-ttu-id="559cc-123">暗号化されたネットワーク通信用に MBAM を設定すると、MBAM Setup は、該当するデータベースと、管理/監視サーバーとコンプライアンスおよび監査レポートサーバー機能の両方の間の通信に Secure Sockets Layer (SSL) を使用するように SQL Server データベースエンジンのインスタンスを構成します。</span><span class="sxs-lookup"><span data-stu-id="559cc-123">If you choose to configure MBAM for Encrypted network communication, MBAM Setup configures the instance of the SQL Server Database Engine to use Secure Sockets Layer (SSL) for communication between the applicable database and both the Administration and Monitoring Server and the Compliance and Audit Report Server features.</span></span>

-   <span data-ttu-id="559cc-124">SQL Server データベースエンジンのインスタンスが SSL を使用するように構成されていない場合は、MBAM セットアップでその処理が構成されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-124">If the instance of the SQL Server Database Engine is not already configured to use SSL, MBAM Setup configures it to do so.</span></span> <span data-ttu-id="559cc-125">これにより、SQL Server データベースエンジンのインスタンスで MBAM 以外のデータベースを使用しようとしているアプリケーションが、データベースと通信できなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="559cc-125">This can prevent applications that try to use non-MBAM databases on the instance of the SQL Server Database Engine from communicating with their databases.</span></span>

-   <span data-ttu-id="559cc-126">SQL Server データベースエンジンのインスタンスが既に SSL を使用するように構成されている場合は、ユーザーがセットアップ時に選択した証明書を使用するように構成されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-126">If the instance of the SQL Server Database Engine is already configured to use SSL, it is configured to use the certificate that the user selected during setup.</span></span> <span data-ttu-id="559cc-127">この証明書が既に使用されていたものと異なる場合は、SQL Server データベースエンジンのインスタンスで SQL Server データベースを使用するアプリケーションが実行されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="559cc-127">If this certificate differs from the one that was already in use, it can prevent applications that use SQL Server databases on the instance of the SQL Server Database Engine from running.</span></span>

<span data-ttu-id="559cc-128">**回避策:**-</span><span class="sxs-lookup"><span data-stu-id="559cc-128">**WORKAROUND:** None</span></span>

### <span data-ttu-id="559cc-129">ローカル管理者アカウントを使用している場合、インストール中に MBAM セットアップが失敗する</span><span class="sxs-lookup"><span data-stu-id="559cc-129">MBAM Setup fails during installation when you use a local Administrator account</span></span>

<span data-ttu-id="559cc-130">ローカル管理者アカウントを使用している場合、MBAM セットアップが失敗します。</span><span class="sxs-lookup"><span data-stu-id="559cc-130">MBAM Setup fails when you use a local Administrator account.</span></span> <span data-ttu-id="559cc-131">ログファイルには、次の情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="559cc-131">The log file contains the following information:</span></span>

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

<span data-ttu-id="559cc-132">**回避策:** MBAM をインストールする場合は、サーバーコンピューターの管理者資格情報を持つドメインアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="559cc-132">**WORKAROUND:** Use a domain account with administrative credentials on the server computer when you install MBAM.</span></span>

### <span data-ttu-id="559cc-133">MBAM セットアップ [ネットワーク通信を暗号化しない] を選択した場合、SSL を使用しないように SQL Server データベースエンジンのインスタンスを再設定します。</span><span class="sxs-lookup"><span data-stu-id="559cc-133">MBAM Setup reconfigures the instance of the SQL Server Database Engine to not use SSL if you select “Do not encrypt network communication”</span></span>

<span data-ttu-id="559cc-134">回復とハードウェアのデータベースまたはコンプライアンスステータスのデータベースのいずれかをインストールする場合は、[暗号化された**ネットワーク通信**] を選択して、[セットアップ] を使って mbam を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="559cc-134">When you install either the Recovery and Hardware Database or the Compliance Status Database, you can use Setup to configure MBAM by selecting **Encrypted network communication**.</span></span> <span data-ttu-id="559cc-135">ネットワーク通信を暗号化しないことにした場合、MBAM セットアップは、SSL を使用しないように SQL Server データベースエンジンのインスタンスを再構成します。</span><span class="sxs-lookup"><span data-stu-id="559cc-135">If you decide not to encrypt the network communication, MBAM Setup reconfigures the instance of the SQL Server Database Engine so that it does not use SSL.</span></span>

-   <span data-ttu-id="559cc-136">SQL Server データベースエンジンのインスタンスが既に SSL を使用するように構成されている場合、MBAM セットアップは、SQL Server データベースエンジンのインスタンスの SSL を無効にします。</span><span class="sxs-lookup"><span data-stu-id="559cc-136">If the instance of the SQL Server Database Engine is already configured to use SSL, MBAM Setup disables SSL on the instance of the SQL Server Database Engine.</span></span> <span data-ttu-id="559cc-137">これにより、SQL Server データベースエンジンのインスタンスの MBAM データベースに関連していないデータベースを使用するアプリケーション間の通信のセキュリティが変更されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-137">This changes the communication security between the applications that use databases that are not related to MBAM databases on the instance of the SQL Server Database Engine.</span></span>

<span data-ttu-id="559cc-138">**回避策:**-</span><span class="sxs-lookup"><span data-stu-id="559cc-138">**WORKAROUND:** None</span></span>

### <span data-ttu-id="559cc-139">インターネットインフォメーションサービス (IIS) 管理スクリプトとツール web サーバー機能の前提条件が見つからない</span><span class="sxs-lookup"><span data-stu-id="559cc-139">Missing prerequisite for the Internet Information Services (IIS) Management Scripts and Tools web server feature</span></span>

<span data-ttu-id="559cc-140">MBAM セットアップは IIS 管理スクリプトとツール web サーバー機能に依存していますが、必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="559cc-140">MBAM Setup is dependent on the IIS Management Scripts and Tools web server feature, but it is not an enforced prerequisite.</span></span> <span data-ttu-id="559cc-141">サーバーのセットアップでは、この機能が見つからない場合に MBAM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="559cc-141">Server setup lets you install MBAM when this feature is missing.</span></span> <span data-ttu-id="559cc-142">ただし、これにより、backup service MBAM VSS Writer は、Windows Management Instrumentation (WMI) とインターネットインフォメーションサービス (IIS) プロバイダーを見つけることができないため、起動して停止します。</span><span class="sxs-lookup"><span data-stu-id="559cc-142">However, this will cause the backup service MBAM VSS Writer to start and then stop, because it cannot locate the Windows Management Instrumentation (WMI) and the Internet Information Services (IIS) provider.</span></span> <span data-ttu-id="559cc-143">この状態にはエラーメッセージはありません。ただし、イベントログで発生します。</span><span class="sxs-lookup"><span data-stu-id="559cc-143">There is no error message for this condition, except that which occurs in the event log.</span></span> <span data-ttu-id="559cc-144">IIS 管理スクリプトとツールを使用せずに MBAM をインストールすると、バックアップ操作が MBAM で実行されなくなります。</span><span class="sxs-lookup"><span data-stu-id="559cc-144">Installation of MBAM without IIS Management Scripts and Tools causes the backup operations not to run for MBAM.</span></span>

<span data-ttu-id="559cc-145">**回避策:** MBAM セットアップを開始する前に、IIS 管理スクリプトとツール web サーバー機能がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="559cc-145">**WORKAROUND:** Ensure that the IIS Management Scripts and Tools web server feature is installed before you start the MBAM Setup.</span></span>

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a><span data-ttu-id="559cc-146">セットアップが証明書を使用するように構成されているときに、MBAM セットアップが "選択された機能をインストールしています" フェーズで応答を停止する</span><span class="sxs-lookup"><span data-stu-id="559cc-146">MBAM Setup stops responding during the “Installing selected features” phase when setup is configured to use a certificate</span></span>

<span data-ttu-id="559cc-147">MBAM セットアップの [選択し**た機能をインストール**しています。をインストールしています。セットアップが終了しました。</span><span class="sxs-lookup"><span data-stu-id="559cc-147">MBAM Setup stops responding during the **Installing selected features** phase of setup.</span></span> <span data-ttu-id="559cc-148">これは、[**証明書を使用してネットワーク通信を暗号化する**] オプションを選択した後、回復とハードウェアデータベースまたはコンプライアンスステータスデータベースのインストール中に発生します。</span><span class="sxs-lookup"><span data-stu-id="559cc-148">This occurs during the installation of the Recovery and Hardware Database or the Compliance Status Database, after you select the **Use a certificate to encrypt the network communication** option.</span></span> <span data-ttu-id="559cc-149">さらに、SQL Server データベースエンジンのインスタンスがセットアップ時に指定された証明書にアクセスできない場合、MBAM セットアップは応答を停止します。</span><span class="sxs-lookup"><span data-stu-id="559cc-149">Furthermore, the MBAM Setup stops responding if the instance of the SQL Server Database Engine cannot access the certificate that was specified during setup.</span></span>

<span data-ttu-id="559cc-150">**回避策:** 証明書のアクセス許可を更新して、SQL Server データベースエンジンの該当するインスタンスの Windows サービスで証明書にアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="559cc-150">**WORKAROUND:** Update the permissions on the certificate, so that the Windows service for the applicable instance of the SQL Server Database Engine can access the certificate.</span></span> <span data-ttu-id="559cc-151">データベースエンジンで証明書を使用するために、SQL Server データベースエンジンのインスタンスを実行するアカウントを変更することもできます。</span><span class="sxs-lookup"><span data-stu-id="559cc-151">You can also change the account under which the instance of the SQL Server Database Engine runs, for the database engine to use the certificate.</span></span> <span data-ttu-id="559cc-152">証明書のアクセス許可を確認するには、コマンドプロンプトで次のコマンドを入力します。 **certutil-v-ストア MY**</span><span class="sxs-lookup"><span data-stu-id="559cc-152">To determine the permissions for the certificate, type the following command at the command prompt: **certutil -v -store MY**</span></span>

### <span data-ttu-id="559cc-153">SQL Server Reporting Services をインストールすると、MBAM セットアップが一時停止する</span><span class="sxs-lookup"><span data-stu-id="559cc-153">MBAM Setup pauses when you install SQL Server Reporting Services</span></span>

<span data-ttu-id="559cc-154">MBAM のインストール中に、SQL Server Reporting Services (SSRS) のインスタンスを選択すると、SSRS インスタンスが利用できないか、または正しく構成されていないと、MBAM セットアップが SSRS インスタンスと通信しようとしていて、最大1分間一時停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="559cc-154">During MBAM installation, when you select an instance of SQL Server Reporting Services (SSRS) and SSRS instance is not available or it is configured incorrectly, the MBAM Setup might pause for up to one minute while it attempts to communicate with the SSRS instance.</span></span>

<span data-ttu-id="559cc-155">**回避策:** セットアッププログラムが SSRS のインスタンスに接続しようとしている間、MBAM セットアップが再開されるまで、少なくとも1分待ちます。</span><span class="sxs-lookup"><span data-stu-id="559cc-155">**WORKAROUND:** Wait for at least one minute for MBAM Setup to resume while the Setup program attempts to contact the instance of SSRS.</span></span>

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a><span data-ttu-id="559cc-156">セットアップ後に管理と監視サーバーが実行されない</span><span class="sxs-lookup"><span data-stu-id="559cc-156">Administration and Monitoring Server does not run after setup</span></span>

<span data-ttu-id="559cc-157">MBAM セットアップで管理と監視のサーバー機能が正常にインストールされると、mbam 管理者の web サイトにアクセスしようとしたときに、エラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-157">After MBAM Setup successfully installs the Administration and Monitoring Server feature, MBAM displays error messages when you try to access the MBAM administrator website.</span></span> <span data-ttu-id="559cc-158">この問題は、次のいずれかの理由で発生します。</span><span class="sxs-lookup"><span data-stu-id="559cc-158">This issue occurs for one of the following reasons:</span></span>

-   <span data-ttu-id="559cc-159">MBAM インストール後に、管理サーバーと監視サーバーの1つ以上の前提条件が削除されました。</span><span class="sxs-lookup"><span data-stu-id="559cc-159">One or more prerequisites on the Administration and Monitoring Server were removed after the MBAM installation.</span></span>

-   <span data-ttu-id="559cc-160">1つ以上の前提条件がサーバーにインストールされた後、MBAM セットアップを実行する前に削除されました。</span><span class="sxs-lookup"><span data-stu-id="559cc-160">One or more prerequisites were installed on the server and later they were removed before running the MBAM Setup.</span></span>

<span data-ttu-id="559cc-161">**回避策:** MBAM のマニュアルを確認して、すべての MBAM 前提条件がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="559cc-161">**WORKAROUND:** Review the MBAM documentation and confirm that all MBAM prerequisites are installed.</span></span>

### <span data-ttu-id="559cc-162">セットアップ中に [ドキュメント] リンクをクリックすると、セットアップの完了後にアプリケーションエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="559cc-162">Clicking documentation links during Setup results in an application error after Setup is finished</span></span>

<span data-ttu-id="559cc-163">セットアップでドキュメントのリンクをクリックし、[**キャンセル]** または [**完了**] をクリックしてセットアッププログラムを閉じると、アプリケーションエラーメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-163">When you click a documentation link during setup and then close the Setup program by clicking **Cancel** or **Finish** after Setup has successfully finished, an application error message appears..</span></span> <span data-ttu-id="559cc-164">この問題は、Windows タスクスケジューラのアクセス違反エラーが原因で発生します。</span><span class="sxs-lookup"><span data-stu-id="559cc-164">The problem is caused by an access violation error in the Windows Task Scheduler.</span></span>

<span data-ttu-id="559cc-165">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="559cc-165">**WORKAROUND:** None.</span></span> <span data-ttu-id="559cc-166">このエラーは無視してかまいません。</span><span class="sxs-lookup"><span data-stu-id="559cc-166">You can ignore this error.</span></span>

### <span data-ttu-id="559cc-167">失敗した MBAM セットアップで新しいデータベースが削除されない</span><span class="sxs-lookup"><span data-stu-id="559cc-167">Failed MBAM Setup does not remove new databases</span></span>

<span data-ttu-id="559cc-168">MBAM セットアップに失敗した場合、セットアップで新しく作成したデータベースが削除されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="559cc-168">If the MBAM Setup fails, Setup might not remove the newly created databases.</span></span> <span data-ttu-id="559cc-169">これにより、以降のインストール時にエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="559cc-169">This can cause failures during subsequent installations.</span></span>

<span data-ttu-id="559cc-170">**回避策:** 以降のインストール時にデータベースインスタンスに別の名前を選択します。</span><span class="sxs-lookup"><span data-stu-id="559cc-170">**WORKAROUND:** Choose a different name for the database instance during the subsequent installation.</span></span>

### <span data-ttu-id="559cc-171">MBAM セットアップで、ネットワーク負荷分散の有効なクラスター証明書が認識されない</span><span class="sxs-lookup"><span data-stu-id="559cc-171">MBAM Setup does not recognize valid network load-balancing cluster certificates</span></span>

<span data-ttu-id="559cc-172">MBAM 管理と監視サーバーのインストール中に、[ネットワーク暗号化] オプションが選択されていると、クラスター証明書は有効な証明書として認識されません。</span><span class="sxs-lookup"><span data-stu-id="559cc-172">During the MBAM Administration and Monitoring Server installation, with the network encryption option selected, the cluster certificate is not recognized as a valid certificate.</span></span> <span data-ttu-id="559cc-173">データベースとの通信用の証明書がインストールされていても、負荷分散クラスターによる通信が拒否される場合は、有効として認識されます。</span><span class="sxs-lookup"><span data-stu-id="559cc-173">It is recognized as valid when the certificate for communication with the database is installed, but it is rejected for communication by the load-balancing cluster.</span></span>

<span data-ttu-id="559cc-174">**回避策:** 証明書に関連付けられている証明書失効リスト (CRL) がアクセス可能であることを確認するか、または CRL を使用して検証を必要としない証明書を使用します。</span><span class="sxs-lookup"><span data-stu-id="559cc-174">**WORKAROUND:** Confirm that the certificate revocation list (CRL) associated with the certificate is accessible, or use a certificate that does not require validation by using the CRL.</span></span>

## <span data-ttu-id="559cc-175">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="559cc-175">Release Notes Copyright Information</span></span>


<span data-ttu-id="559cc-176">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="559cc-176">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="559cc-177">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="559cc-177">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="559cc-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="559cc-178">Related topics</span></span>


[<span data-ttu-id="559cc-179">MBAM 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="559cc-179">About MBAM 1.0</span></span>](about-mbam-10.md)

 

 





