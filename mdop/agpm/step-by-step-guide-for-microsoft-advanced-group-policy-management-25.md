---
title: Microsoft Advanced Group Policy Management 2.5 ステップ バイ ステップ ガイド
description: Microsoft Advanced Group Policy Management 2.5 ステップ バイ ステップ ガイド
author: dansimp
ms.assetid: 454298c9-0fab-497a-9808-c0246a4c8db5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 67925e417e4fb1f5398dfd030f366936f1d36909
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820194"
---
# <span data-ttu-id="ba45a-103">Microsoft Advanced Group Policy Management 2.5 ステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="ba45a-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 2.5</span></span>


<span data-ttu-id="ba45a-104">このステップバイステップガイドでは、グループポリシー管理コンソール (GPMC) と Microsoft Advanced グループポリシー管理 (AGPM) を使用した、グループポリシー管理の高度な手法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="ba45a-105">AGPM によって GPMC の機能が向上し、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="ba45a-106">グループポリシーオブジェクト (Gpo) を管理するためのアクセス許可を委任するための標準的な役割を、複数のグループポリシー管理者に対して行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators.</span></span>

-   <span data-ttu-id="ba45a-107">グループポリシー管理者が、運用環境に展開する前に、Gpo をオフラインで作成して変更できるようにするアーカイブ。</span><span class="sxs-lookup"><span data-stu-id="ba45a-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="ba45a-108">以前のバージョンの GPO にロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-108">The ability to roll back to any previous version of a GPO.</span></span>

-   <span data-ttu-id="ba45a-109">グループポリシーの管理者が互いの作業を誤って上書きしないように、Gpo のチェックイン/チェックアウト機能。</span><span class="sxs-lookup"><span data-stu-id="ba45a-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="ba45a-110">AGPM シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="ba45a-110">AGPM scenario overview</span></span>


<span data-ttu-id="ba45a-111">このシナリオでは、AGPM の各役割に対して個別のユーザーアカウントを使用して、さまざまなレベルの権限を持つ複数のグループポリシー管理者が環境内でグループポリシーを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="ba45a-112">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="ba45a-113">Domain Admins グループのメンバーであるアカウントを使用して、AGPM サーバーをインストールし、アカウントまたはグループに AGPM 管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="ba45a-114">AGPM ロールを割り当てるアカウントを使用し、AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="ba45a-115">AGPM 管理者の役割を持つアカウントを使用して、他のアカウントに役割を割り当てることによって、Gpo への AGPM アクセスと代理人アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="ba45a-116">編集者の役割を持つアカウントを使用して、GPO の作成を要求します。これにより、承認者の役割を持つアカウントを使用して承認します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="ba45a-117">エディターアカウントを使用して、アーカイブから GPO をチェックアウトして、GPO を編集し、GPO をアーカイブにチェックインして、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="ba45a-118">承認者の役割を持つアカウントを使用して、GPO を確認し、運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="ba45a-119">エディターロールを持つアカウントを使用して、GPO テンプレートを作成し、それを出発点として使用して新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="ba45a-120">承認者の役割を持つアカウントを使用して、GPO を削除および復元します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![グループポリシーオブジェクトの開発プロセス](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="ba45a-122">要件</span><span class="sxs-lookup"><span data-stu-id="ba45a-122">Requirements</span></span>


<span data-ttu-id="ba45a-123">AGPM をインストールするコンピューターは、次の要件を満たしている必要があります。このシナリオで使用するには、アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

### <span data-ttu-id="ba45a-124">AGPM サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="ba45a-124">AGPM Server requirements</span></span>

<span data-ttu-id="ba45a-125">AGPM サーバー2.5 には、service pack がインストールされていないか、Windows Server® 2003 (32 ビットバージョン) と GPMC を含む WindowsVista® (32 ビット版) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba45a-125">AGPM Server2.5 requires WindowsVista® (32-bit version) with no service packs installed or Windows Server®2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="ba45a-126">また、AGPM サーバーをインストールするには、ドメイン管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-126">Additionally, you must be a member of the Domain Admins group to install AGPM Server.</span></span>

<span data-ttu-id="ba45a-127">AGPM サーバーまたは AGPM でサポートされている最新バージョンの GPMC を持つメンバーサーバーまたはドメインコントローラーに、AGPM サーバーをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-127">You should install AGPM Server on a member server or domain controller with the most recent version of the GPMC that is available to you and supported by AGPM.</span></span> <span data-ttu-id="ba45a-128">AGPM では、GPMC を使って Gpo のバックアップと復元を行います。また、新しいバージョンの GPMC は、以前のバージョンでは利用できないその他のポリシー設定を提供します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-128">AGPM uses the GPMC to back up and restore GPOs, and newer versions of the GPMC provide additional policy settings not available in preceding versions.</span></span> <span data-ttu-id="ba45a-129">AGPM サーバー上の GPMC のバージョンが、管理者がグループポリシーを管理するために使用するコンピューター上のバージョンよりも古い場合、AGPM サーバーでは、古いバージョンの GPMC では使用できないポリシー設定を保存することはできません。</span><span class="sxs-lookup"><span data-stu-id="ba45a-129">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store those policy settings not available in the older version of the GPMC.</span></span>

<span data-ttu-id="ba45a-130">特に、AGPM サーバーで Windows Server2003 と共に使用されている GPMC のバージョンが実行されていて、グループポリシー管理者のコンピューターで Windows Vista とそれに付随した GPMC のバージョンが実行されている場合、ほとんどのポリシー設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-130">Specifically, if your AGPM Server is running Windows Server2003 and the version of the GPMC that accompanied it, and your Group Policy administrators’ computers are running WindowsVista and the version of the GPMC that accompanied it, you can still manage most policy settings.</span></span> <span data-ttu-id="ba45a-131">ただし、windows Server 2003 の gpmc (フォルダーリダイレクション、ワイヤレスネットワーク (IEEE 802.11)、展開されたプリンターなど) のポリシー設定は、管理者がユーザーのコンピューター上で AGPM を使って構成できる場合でも、AGPM サーバーによって保存されることはできません。</span><span class="sxs-lookup"><span data-stu-id="ba45a-131">However, policy settings from the GPMC in Windows Vista that are not available in the GPMC in Windows Server 2003—such as those related to folder redirection, wireless networking (IEEE 802.11), and deployed printers—cannot be stored by the AGPM Server, even though administrators can configure them using AGPM on their computers.</span></span>

<span data-ttu-id="ba45a-132">グループポリシー管理者が実行している前のバージョンよりも古いバージョンの GPMC のコンピューターに AGPM サーバーをインストールする必要がある場合は、「グループポリシーの設定」を参照してください。どのオペレーティングシステムで利用可能なポリシー設定かの詳細が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-132">If you must install AGPM Server on a computer with an older version of GPMC than your Group Policy administrators are running, see the Group Policy Settings Reference for details about which policy settings are available with which operating systems.</span></span> <span data-ttu-id="ba45a-133">グループポリシー設定のリファレンスをダウンロードするには、を参照してください <https://go.microsoft.com/fwlink/?LinkID=106147> 。</span><span class="sxs-lookup"><span data-stu-id="ba45a-133">To download the Group Policy Settings Reference, see <https://go.microsoft.com/fwlink/?LinkID=106147>.</span></span>

<span data-ttu-id="ba45a-134">**注** Windows Server2003 を実行している AGPM サーバーまたは GPOVault サーバーから、WindowsVista を実行している AGPM サーバーにアーカイブを移行することはできません。</span><span class="sxs-lookup"><span data-stu-id="ba45a-134">**Note** Archives cannot be migrated from an AGPM Server or a GPOVault Server running Windows Server2003 to an AGPM Server running WindowsVista.</span></span>

<span data-ttu-id="ba45a-135">Windows Server2003 の場合、AGPM サーバーをインストールするコンピューターに GPOVault Server がインストールされている場合は、インストールを開始する前に GPOVault Server をアンインストールしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-135">For Windows Server2003, if GPOVault Server is installed on the computer on which you want to install AGPM Server, it is recommended that you do not uninstall GPOVault Server before beginning the installation.</span></span> <span data-ttu-id="ba45a-136">AGPM サーバーのインストールでは、GPOVault Server をアンインストールし、既存の GPOVault アーカイブデータを AGPM アーカイブに自動的に転送します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-136">The installation of AGPM Server will uninstall GPOVault Server and automatically transfer your existing GPOVault archive data to an AGPM archive.</span></span>

 

### <span data-ttu-id="ba45a-137">AGPM クライアントの要件</span><span class="sxs-lookup"><span data-stu-id="ba45a-137">AGPM Client requirements</span></span>

<span data-ttu-id="ba45a-138">AGPM クライアント2.5 には、service pack がインストールされていないか、Windows Server2003 (32 ビットバージョン) と GPMC を含む WindowsVista (32 ビット版) が必要です。</span><span class="sxs-lookup"><span data-stu-id="ba45a-138">AGPM Client2.5 requires WindowsVista (32-bit version) with no service packs installed or Windows Server2003 (32-bit version), as well as the GPMC.</span></span> <span data-ttu-id="ba45a-139">Agpm クライアントは、AGPM サーバーを実行しているコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-139">AGPM Client can be installed on a computer running AGPM Server.</span></span>

### <span data-ttu-id="ba45a-140">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="ba45a-140">Scenario requirements</span></span>

<span data-ttu-id="ba45a-141">このシナリオを始める前に、4つのユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-141">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="ba45a-142">このシナリオでは、これらの各アカウントに、AGPM 管理者 (フルコントロール)、承認者、編集者、および校閲者といういずれかの AGPM ロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-142">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="ba45a-143">これらのアカウントでは、電子メールメッセージの送受信が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-143">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="ba45a-144">AGPM 管理者、承認者、(必要に応じて) エディターの各役割を持つアカウントに**リンク gpo**のアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-144">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="ba45a-145">**注** 
[ **Gpo のリンク**] 権限は、既定でドメイン管理者とエンタープライズ管理者のメンバーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-145">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="ba45a-146">追加のユーザーまたはグループ (AGPM 管理者または承認者の役割を持つアカウントなど) に**リンク gpo**のアクセス許可を割り当てるには、ドメインのノードをクリックし、[**委任**] タブをクリックし、[ **gpo のリンク**]、[**追加**] の順にクリックして、アクセス許可を割り当てるユーザーまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-146">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

<span data-ttu-id="ba45a-147">このシナリオでは、さまざまなアカウントでアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-147">For this scenario, you perform actions with different accounts.</span></span> <span data-ttu-id="ba45a-148">指示に従って各アカウントでログオンするか、[別のユーザー**として実行**] コマンドを使用して、指定されたアカウントで GPMC を起動することができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-148">You can either log on with each account as indicated, or you can use the **Run as** command to start the GPMC with the indicated account.</span></span>

<span data-ttu-id="ba45a-149">**注** Windows Server2003 の GPMC で [ **Run as** ] コマンドを使用するには、[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシー管理**] を右クリックし、[ **run as**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-149">**Note** To use the **Run as** command with GPMC on Windows Server2003, click **Start**, point to **Administrative Tools**, right-click **Group Policy Management**, and click **Run as**.</span></span> <span data-ttu-id="ba45a-150">**次のユーザー**をクリックして、アカウントの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-150">Click **The following user** and enter credentials for an account.</span></span>

<span data-ttu-id="ba45a-151">Windows Vista の GPMC で [ **run as** ] コマンドを使用するには、[**スタート**] ボタンをクリックして、[**実行**] をポイントし、「 **runas/user:** <em> DomainName\\UserName </em> **"mmc%windir%\\system32\\gpmc.msc"**」と入力して、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-151">To use the **Run as** command with GPMC on Windows Vista, click the **Start** button, point to **Run**, and type **runas /user:**<em>DomainName\\UserName</em>**"mmc %windir%\\system32\\gpmc.msc"**, and click **OK**.</span></span> <span data-ttu-id="ba45a-152">メッセージが表示されたら、アカウントのパスワードを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-152">Type the password for the account when prompted.</span></span>

 

## <span data-ttu-id="ba45a-153">AGPM のインストールと構成の手順</span><span class="sxs-lookup"><span data-stu-id="ba45a-153">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="ba45a-154">AGPM をインストールして構成するには、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-154">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="ba45a-155">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ba45a-155">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="ba45a-156">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="ba45a-156">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="ba45a-157">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-157">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="ba45a-158">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-158">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="ba45a-159">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="ba45a-159">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="ba45a-160">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="ba45a-160">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="ba45a-161">この手順では、AGPM サービスを実行するメンバーサーバーまたはドメインコントローラーに AGPM サーバーをインストールし、アーカイブを構成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-161">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="ba45a-162">すべての AGPM 操作は、この Windows サービスを通じて管理され、サービスの資格情報を使って実行されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-162">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="ba45a-163">AGPM サーバーによって管理されるアーカイブは、そのサーバーまたは同じフォレスト内の別のサーバー上でホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-163">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="ba45a-164">AGPM サービスをホストするコンピューターに AGPM サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-164">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="ba45a-165">Domain Admins グループのメンバーであるアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-165">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="ba45a-166">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシー管理-サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-166">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="ba45a-167">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-167">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="ba45a-168">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-168">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="ba45a-169">[**アプリケーションパス**] ダイアログボックスで、AGPM サーバーをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-169">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="ba45a-170">AGPM サーバーがインストールされているコンピューターは、AGPM サービスをホストし、アーカイブを管理します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-170">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="ba45a-171">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-171">Click **Next**.</span></span>

6.  <span data-ttu-id="ba45a-172">[**アーカイブパス**] ダイアログボックスで、AGPM サーバーとの相対的なアーカイブの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-172">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="ba45a-173">アーカイブパスは、AGPM サーバー上のフォルダーを指すことができますが、この AGPM サーバーで管理されているすべての Gpo と履歴データを格納するのに十分な領域がある場所を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-173">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="ba45a-174">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-174">Click **Next**.</span></span>

7.  <span data-ttu-id="ba45a-175">[ **Agpm サービスアカウント**] ダイアログボックスで、agpm サービスを実行するサービスアカウントを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-175">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="ba45a-176">[**アーカイブの所有者**] ダイアログボックスで、AGPM 管理者 (フルコントロール) の役割を最初に割り当てるアカウントまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-176">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="ba45a-177">この AGPM 管理者は、agpm ロールと権限を他のグループポリシー管理者に割り当てることができます (AGPM 管理者の役割を含む)。</span><span class="sxs-lookup"><span data-stu-id="ba45a-177">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="ba45a-178">このシナリオでは、AGPM 管理者の役割で利用するアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-178">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="ba45a-179">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-179">Click **Next**.</span></span>

9.  <span data-ttu-id="ba45a-180">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-180">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="ba45a-181">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="ba45a-181">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="ba45a-182">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-182">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="ba45a-183">サービスの設定を変更する方法については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba45a-183">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="ba45a-184">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="ba45a-184">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="ba45a-185">各グループポリシー管理者 (Gpo の作成、編集、展開、確認、削除) には、Gpo を管理するために使用するコンピューターに AGPM クライアントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-185">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="ba45a-186">このシナリオでは、少なくとも1台のコンピューターに AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-186">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="ba45a-187">グループポリシー管理を実行しないエンドユーザーのコンピューターに AGPM クライアントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ba45a-187">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="ba45a-188">グループポリシー管理者のコンピューターに AGPM クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-188">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="ba45a-189">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-189">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="ba45a-190">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-190">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="ba45a-191">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-191">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="ba45a-192">[**アプリケーションパス**] ダイアログボックスで、AGPM クライアントをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-192">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="ba45a-193">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-193">Click **Next**.</span></span>

5.  <span data-ttu-id="ba45a-194">[ **Agpm サーバー** ] ダイアログボックスで、接続先の agpm サーバーの完全修飾コンピューター名とポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-194">In the **AGPM Server** dialog box, type the fully-qualified computer name and the port for the AGPM Server to which to connect.</span></span> <span data-ttu-id="ba45a-195">AGPM サービスの既定のポートは4600です。</span><span class="sxs-lookup"><span data-stu-id="ba45a-195">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="ba45a-196">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-196">Click **Next**.</span></span>

6.  <span data-ttu-id="ba45a-197">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-197">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="ba45a-198">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-198">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="ba45a-199">AGPM は、各グループポリシーオブジェクト (GPO) のすべてのバージョンを格納します。この GPO は、AGPM が変更の制御を提供します。これは、グループポリシー管理者が、展開されたバージョンの各 GPO に影響を与えずに、オフラインで Gpo を表示したり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-199">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="ba45a-200">この手順では、AGPM サーバー接続を構成し、すべてのグループポリシー管理者が同じ AGPM サーバーに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-200">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="ba45a-201">(複数の AGPM サーバーを構成する方法について詳しくは、「高度なグループポリシー管理のヘルプ」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="ba45a-201">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="ba45a-202">すべてのグループポリシー管理者に対して AGPM サーバー接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-202">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="ba45a-203">AGPM クライアントをインストールしたコンピューターで、アーカイブの所有者として選択したユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-203">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="ba45a-204">このユーザーは、AGPM 管理者 (フルコントロール) の役割を持っています。</span><span class="sxs-lookup"><span data-stu-id="ba45a-204">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="ba45a-205">[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックして、**グループポリシー管理コンソール (GPMC)** を開きます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-205">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the **Group Policy Management Console (GPMC)**.</span></span>

3.  <span data-ttu-id="ba45a-206">[**グループポリシー管理コンソール**] ツリーで、すべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-206">In the **Group Policy Management Console** tree, edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="ba45a-207">[**グループポリシーオブジェクトエディター** ] ウィンドウで、 **[ユーザーの構成**]、[**管理用テンプレート**]、[ **Windows コンポーネント**] の順番にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-207">In the **Group Policy Object Editor** window, click **User Configuration**, **Administrative Templates**, and **Windows Components**.</span></span>

5.  <span data-ttu-id="ba45a-208">[ **Windows コンポーネント**] の下に [ **AGPM** ] が表示されない場合:</span><span class="sxs-lookup"><span data-stu-id="ba45a-208">If **AGPM** is not listed under **Windows Components**:</span></span>

    1.  <span data-ttu-id="ba45a-209">[**管理用テンプレート**] を右クリックし、[**テンプレートの追加と削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-209">Right-click **Administrative Templates** and select **Add/Remove Templates**.</span></span>

    2.  <span data-ttu-id="ba45a-210">[**追加**] をクリックして、[ **agpm** ] または [ **agpm**] を選択し、[**開く**] をクリックして、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-210">Click **Add**, select **agpm.admx** or **agpm.adm**, click **Open**, and then click **Close**.</span></span>

6.  <span data-ttu-id="ba45a-211">[ **Windows コンポーネント**] で、[ **AGPM**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-211">Under **Windows Components**, double-click **AGPM**.</span></span>

7.  <span data-ttu-id="ba45a-212">詳細ウィンドウで、[ **AGPM サーバー (すべてのドメイン)**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-212">In the details pane, double-click **AGPM Server (all domains)**.</span></span>

8.  <span data-ttu-id="ba45a-213">[ **AGPM Server (すべてのドメイン) のプロパティ**] ウィンドウで、[**有効**] を選び、アーカイブをホストしているサーバーの完全修飾コンピューター名とポート (server.contoso.com:4600 など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-213">In the **AGPM Server (all domains) Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, server.contoso.com:4600) for the server hosting the archive.</span></span> <span data-ttu-id="ba45a-214">AGPM サービスによって使用されるポートは、ポート4600です。</span><span class="sxs-lookup"><span data-stu-id="ba45a-214">The port used by the AGPM Service is port 4600.</span></span>

9.  <span data-ttu-id="ba45a-215">[ **OK**] をクリックし、[**グループポリシーオブジェクトエディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-215">Click **OK**, and then close the **Group Policy Object Editor** window.</span></span> <span data-ttu-id="ba45a-216">グループポリシーが更新されると、各グループポリシーの管理者に対して AGPM サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-216">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="ba45a-217">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-217">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="ba45a-218">AGPM 管理者 (フルコントロール) として、エディターが GPO を作成、展開、または削除しようとしたときに、要求を含む電子メールメッセージが送信される承認者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-218">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="ba45a-219">また、これらのメッセージの送信元のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-219">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="ba45a-220">AGPM の電子メール通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-220">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="ba45a-221">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-221">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ba45a-222">詳細ウィンドウで、[ **Domain Delegation** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-222">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="ba45a-223">[**差出人**] フィールドに、通知を送信するための AGPM の電子メールエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-223">In the **From** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="ba45a-224">[**宛先**] フィールドに、承認者の役割を割り当てるユーザーアカウントの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-224">In the **To** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="ba45a-225">[ **Smtp server** ] フィールドに、有効な smtp メールサーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-225">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="ba45a-226">[**ユーザー名**] フィールドと [**パスワード**] フィールドに、SMTP サービスへのアクセス権を持つユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-226">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span>

7.  <span data-ttu-id="ba45a-227">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-227">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="ba45a-228">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="ba45a-228">Step 5: Delegate access</span></span>

<span data-ttu-id="ba45a-229">AGPM 管理者 (フルコントロール) として、Gpo へのドメインレベルのアクセスを委任し、各グループポリシー管理者のアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-229">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="ba45a-230">**注** また、ドメインレベルではなく、GPO レベルでアクセスを委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-230">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="ba45a-231">詳細については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ba45a-231">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="ba45a-232">**重要** グループポリシー作成者グループのメンバーシップを制限して、Gpo へのアクセスの AGPM 管理を回避することができないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-232">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="ba45a-233">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="ba45a-233">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="ba45a-234">ドメイン全体のすべての Gpo へのアクセスを委任するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-234">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="ba45a-235">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-235">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="ba45a-236">[ **Domain Delegation** ] タブで、[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-236">On the **Domain Delegation** tab, click the **Advanced** button.</span></span>

3.  <span data-ttu-id="ba45a-237">[**アクセス許可**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-237">In the **Permissions** dialog box:</span></span>

    1.  <span data-ttu-id="ba45a-238">グループポリシー管理者のユーザーアカウントをクリックし、[**承認者**] チェックボックスをオンにして、その役割をアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-238">Click the user account of a Group Policy administrator, and then select the **Approver** check box to assign that role to the account.</span></span> <span data-ttu-id="ba45a-239">[**エディター** ] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-239">Clear the **Editor** check box.</span></span> <span data-ttu-id="ba45a-240">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="ba45a-240">(This role includes the Reviewer role.)</span></span>

    2.  <span data-ttu-id="ba45a-241">別のグループポリシー管理者のユーザーアカウントをクリックし、[**編集**] チェックボックスをオンにして、その役割をアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-241">Click the user account of another Group Policy administrator, and then select the **Editor** check box to assign that role to the account.</span></span> <span data-ttu-id="ba45a-242">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="ba45a-242">(This role includes the Reviewer role.)</span></span>

    3.  <span data-ttu-id="ba45a-243">3番目のアカウントをクリックし、[**校閲**者] チェックボックスをオンにして、そのグループポリシー管理者のアカウントに校閲者の役割のみを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-243">Click a third account and then select the **Reviewer** check box to assign only the Reviewer role to the account of that Group Policy administrator.</span></span> <span data-ttu-id="ba45a-244">[**エディター** ] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-244">Clear the **Editor** check box.</span></span>

    4.  <span data-ttu-id="ba45a-245">[**詳細設定**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-245">Click the **Advanced** button.</span></span>

4.  <span data-ttu-id="ba45a-246">**[詳細なセキュリティ設定**] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-246">In the **Advanced Security Settings** dialog box:</span></span>

    1.  <span data-ttu-id="ba45a-247">グループポリシーの管理者を選択し、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-247">Select a Group Policy administrator, and then click **Edit**.</span></span>

    2.  <span data-ttu-id="ba45a-248">[**適用先**] で、**このオブジェクトと入れ子になったオブジェクト**を選択し、[**アクセス許可\*\*\*\*エントリ**] ダイアログボックスで [ **OK** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-248">For **Apply onto**, select **This object and nested objects**, and then click **OK** in the **Permission** **Entry** dialog box.</span></span>

    3.  <span data-ttu-id="ba45a-249">グループポリシーの管理者ごとに、この手順を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-249">Repeat for each Group Policy administrator.</span></span>

5.  <span data-ttu-id="ba45a-250">[**詳細なセキュリティ設定**] ダイアログボックスで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-250">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

6.  <span data-ttu-id="ba45a-251">[**アクセス許可**] ダイアログボックスで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-251">In the **Permissions** dialog box, click **OK**.</span></span>

## <span data-ttu-id="ba45a-252">Gpo を管理する手順</span><span class="sxs-lookup"><span data-stu-id="ba45a-252">Steps for managing GPOs</span></span>


<span data-ttu-id="ba45a-253">AGPM を使って Gpo を作成、編集、確認、展開するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-253">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="ba45a-254">さらに、テンプレートを作成し、GPO を削除して、削除された GPO を復元します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-254">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="ba45a-255">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-255">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="ba45a-256">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="ba45a-256">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="ba45a-257">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="ba45a-257">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="ba45a-258">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-258">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="ba45a-259">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="ba45a-259">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="ba45a-260">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-260">Step 1: Create a GPO</span></span>

<span data-ttu-id="ba45a-261">複数のグループポリシー管理者がいる環境では、編集者の役割を持つユーザーは新しい Gpo の作成を要求することができますが、新しい GPO の作成が運用環境に影響を与えるため、そのような要求は、承認者の役割を持つユーザーによって承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-261">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="ba45a-262">この手順では、新しい GPO の作成を要求するために、編集者の役割を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-262">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="ba45a-263">承認者の役割を持つアカウントを使用して、この要求を承認し、GPO の作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-263">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="ba45a-264">AGPM で管理される新しい GPO の作成を要求するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-264">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="ba45a-265">AGPM クライアントをインストールしたコンピューターで、AGPM のエディターロールが割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-265">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="ba45a-266">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-266">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="ba45a-267">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-267">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="ba45a-268">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-268">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="ba45a-269">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-269">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="ba45a-270">新しい GPO の名前として「 **Mygpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-270">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="ba45a-271">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-271">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="ba45a-272">[**ライブの作成**] をクリックすると、新しい GPO が承認されたときにすぐに運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-272">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="ba45a-273">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-273">Click **Submit**.</span></span>

5.  <span data-ttu-id="ba45a-274">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-274">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-275">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-275">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="ba45a-276">保留中の要求を承認して GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-276">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="ba45a-277">AGPM クライアントをインストールしたコンピューターで、AGPM で承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-277">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="ba45a-278">アカウントのメールの受信トレイを開き、GPO を作成するための編集要求を含む、AGPM エイリアスからのメールメッセージを受信していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-278">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="ba45a-279">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-279">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="ba45a-280">[**コンテンツ**] タブで、[**保留中**] タブをクリックして、保留中の gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-280">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="ba45a-281">[ **Mygpo**] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-281">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="ba45a-282">GPO の作成の承認を確認するには、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-282">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="ba45a-283">GPO が [**コントロール**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-283">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="ba45a-284">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="ba45a-284">Step 2: Edit a GPO</span></span>

<span data-ttu-id="ba45a-285">Gpo を使って、コンピューターやユーザーの設定を構成し、多くのコンピューターまたはユーザーに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-285">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="ba45a-286">この手順では、編集者の役割を持つアカウントを使用して、アーカイブから GPO をチェックアウトし、その gpo をオフラインで編集して、編集した GPO をアーカイブにチェックインして、GPO の展開を運用環境に要求します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-286">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="ba45a-287">このシナリオでは、パスワードの長さが8文字以上であることを要求するように、GPO の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-287">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="ba45a-288">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-288">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="ba45a-289">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-289">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="ba45a-290">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-290">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="ba45a-291">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理されている gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-291">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="ba45a-292">[ **Mygpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-292">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="ba45a-293">チェックアウトされているときに、GPO の**履歴**に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-293">Type a comment to be displayed in the **History** of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="ba45a-294">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-294">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-295">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-295">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="ba45a-296">GPO をオフラインで編集し、パスワードの最小文字数を構成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-296">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="ba45a-297">[**コントロール**] タブで、[ **mygpo**] を右クリックし、[**編集**] をクリックして [**グループポリシーオブジェクトエディター** ] ウィンドウを開き、GPO のオフラインコピーに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-297">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="ba45a-298">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-298">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="ba45a-299">[**コンピューターの構成**] で、[ **Windows の設定**]、[**セキュリティ設定**]、[**アカウントポリシー**] の順にダブルクリックして、[**パスワードポリシー**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-299">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Password Policy**.</span></span>

    2.  <span data-ttu-id="ba45a-300">詳細ウィンドウで、[**パスワードの最小文字数**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-300">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="ba45a-301">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、文字数を**8**に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-301">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="ba45a-302">[**グループポリシーオブジェクトエディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-302">Close the **Group Policy Object Editor** window.</span></span>

**<span data-ttu-id="ba45a-303">GPO をアーカイブにチェックインするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-303">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="ba45a-304">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**チェックイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-304">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="ba45a-305">コメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-305">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="ba45a-306">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-306">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-307">[**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-307">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="ba45a-308">GPO の展開を運用環境に要求するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-308">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="ba45a-309">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-309">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="ba45a-310">このアカウントは承認者または AGPM 管理者ではないため、展開の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-310">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="ba45a-311">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-311">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="ba45a-312">GPO の**履歴**に表示するコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-312">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="ba45a-313">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-313">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-314">[**保留中**] タブの gpo の一覧に**mygpo**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-314">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="ba45a-315">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="ba45a-315">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="ba45a-316">この手順では、承認者は、承認が必要かどうかを判断するために、承認者として、また GPO の設定を作成し、設定を分析します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-316">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="ba45a-317">GPO を評価した後、その GPO を運用環境に展開し、ドメインまたは組織単位 (OU) にリンクさせて、そのドメインまたは OU 内のコンピューターのグループポリシーが更新されたときに有効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-317">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="ba45a-318">GPO の設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-318">To review settings in the GPO</span></span>**

1.  <span data-ttu-id="ba45a-319">AGPM クライアントをインストールしたコンピューターで、AGPM で承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-319">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="ba45a-320">(他のすべての役割に含まれている校閲者の役割を持つすべてのグループポリシー管理者が、GPO の設定を確認できます。)</span><span class="sxs-lookup"><span data-stu-id="ba45a-320">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2.  <span data-ttu-id="ba45a-321">アカウントのメールの受信トレイを開き、GPO を展開するためのエディター要求で AGPM エイリアスからのメールメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-321">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3.  <span data-ttu-id="ba45a-322">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="ba45a-323">[詳細] ウィンドウの [**コンテンツ**] タブで、[**保留中**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-323">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5.  <span data-ttu-id="ba45a-324">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-324">Double-click **MyGPO** to display its history.</span></span>

6.  <span data-ttu-id="ba45a-325">最新バージョンの MyGPO の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-325">Review the settings in the most recent version of MyGPO:</span></span>

    1.  <span data-ttu-id="ba45a-326">[**履歴**] ウィンドウで、最新のタイムスタンプが設定されている GPO のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] をクリックして、gpo の設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-326">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

    2.  <span data-ttu-id="ba45a-327">Web ブラウザーで、[**すべて表示**] をクリックして、GPO のすべての設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-327">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span>

    3.  <span data-ttu-id="ba45a-328">ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-328">Close the browser.</span></span>

7.  <span data-ttu-id="ba45a-329">最新バージョンの MyGPO と、アーカイブにチェックインされた最初のバージョンを比較します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-329">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

    1.  <span data-ttu-id="ba45a-330">[**履歴**] ウィンドウで、最新のタイムスタンプが付いた GPO のバージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-330">In the **History** window, click the GPO version with the most recent timestamp.</span></span> <span data-ttu-id="ba45a-331">Ctrl キーを押し**ながら**、**チェックイン**されている状態の最も古い GPO バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-331">Press **CTRL** and click the oldest GPO version that has a state of **Checked In**.</span></span>

    2.  <span data-ttu-id="ba45a-332">[**差分**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-332">Click the **Differences** button.</span></span> <span data-ttu-id="ba45a-333">[**アカウントポリシー] および [パスワードポリシー** ] セクションが緑色で、先頭が**\ [+ \]** で強調表示されています。この設定は、GPO の後者のバージョンでのみ構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-333">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

    3.  <span data-ttu-id="ba45a-334">[**アカウントポリシー**] の [パスワードポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-334">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="ba45a-335">[**パスワードの長さ**] の設定は緑で、その前に**\ [+ \]** が強調表示されています。これは、GPO の後者のバージョンでのみ構成されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="ba45a-335">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

    4.  <span data-ttu-id="ba45a-336">Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-336">Close the Web browser.</span></span>

**<span data-ttu-id="ba45a-337">GPO を運用環境に展開するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-337">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="ba45a-338">[**保留中**] タブで、[ **mygpo** ] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-338">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="ba45a-339">GPO の履歴に含めるコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-339">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="ba45a-340">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-340">Click **Yes**.</span></span> <span data-ttu-id="ba45a-341">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-341">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-342">この GPO は、運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-342">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="ba45a-343">GPO をドメインまたは組織単位にリンクするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-343">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="ba45a-344">GPMC で、構成した GPO を適用するドメインまたは OU を右クリックし、[**既存の gpo にリンク**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-344">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="ba45a-345">[ **GPO の選択**] ダイアログボックスで、[ **mygpo**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-345">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="ba45a-346">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="ba45a-346">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="ba45a-347">この手順では、編集者の役割を持つアカウントを使用して、新しい Gpo を作成するための開始点として使用するテンプレート (編集できない静的バージョンの GPO) を作成し、そのテンプレートに基づいて新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-347">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="ba45a-348">テンプレートは、同じ設定の多くを含む複数の Gpo をすばやく作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="ba45a-348">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="ba45a-349">既存の GPO に基づいてテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-349">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="ba45a-350">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-350">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="ba45a-351">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-351">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="ba45a-352">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-352">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="ba45a-353">[ **Mygpo**] を右クリックし、[**テンプレートとして保存**] をクリックして、現在 mygpo に設定されているすべての設定が組み込まれているテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-353">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="ba45a-354">テンプレートの名前として「 **MyTemplate** 」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-354">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="ba45a-355">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-355">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-356">新しいテンプレートが [**テンプレート**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-356">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="ba45a-357">AGPM で管理される新しい GPO の作成を要求するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-357">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="ba45a-358">[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-358">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="ba45a-359">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-359">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="ba45a-360">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-360">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="ba45a-361">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-361">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="ba45a-362">新しい GPO の名前として「 **Myothergpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-362">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="ba45a-363">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-363">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="ba45a-364">[**ライブの作成**] をクリックすると、新しい GPO は承認されるとすぐに運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-364">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="ba45a-365">[ **GPO テンプレート] から**[ **MyTemplate**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-365">For **From GPO template**, select **MyTemplate**.</span></span>

    6.  <span data-ttu-id="ba45a-366">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-366">Click **Submit**.</span></span>

4.  <span data-ttu-id="ba45a-367">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-367">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-368">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-368">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="ba45a-369">承認者の役割が割り当てられているアカウントを使用して、 [「手順 1: gpo を作成](#bkmk-manage1)する」の手順に従って、gpo を作成する保留中の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-369">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="ba45a-370">MyTemplate には、MyGPO で構成したすべての設定が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="ba45a-370">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="ba45a-371">MyOtherGPO は MyTemplate を使用して作成されたため、最初は、MyTemplate が作成された時点で、MyGPO に含まれていたすべての設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ba45a-371">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="ba45a-372">これを確認するには、MyOtherGPO と MyTemplate を比較するための差分レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-372">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="ba45a-373">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-373">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="ba45a-374">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-374">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="ba45a-375">[ **Myothergpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-375">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="ba45a-376">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-376">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="ba45a-377">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-377">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-378">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-378">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="ba45a-379">GPO をオフラインで編集して、アカウントのロックアウト期間を構成するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-379">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="ba45a-380">[**コントロール**] タブで、[ **myothergpo**] を右クリックし、[**編集**] をクリックして [**グループポリシーオブジェクトエディター** ] ウィンドウを開き、GPO のオフラインコピーに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-380">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Object Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="ba45a-381">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-381">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="ba45a-382">[**コンピューターの構成**] で、[ **Windows の設定**] をダブルクリックし、[**セキュリティ設定**] をダブルクリックし、[**アカウントポリシー**] をダブルクリックして、[**アカウントのロックアウトポリシー**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-382">Under **Computer Configuration**, double-click **Windows Settings**, double-click **Security Settings**, double-click **Account Policies**, and double-click **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="ba45a-383">詳細ウィンドウで、[**アカウントのロックアウトの期間**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-383">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="ba45a-384">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、期間を**30**分に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-384">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="ba45a-385">[**グループポリシーオブジェクトエディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-385">Close the **Group Policy Object Editor** window.</span></span>

<span data-ttu-id="ba45a-386">[「手順 2: GPO を編集](#bkmk-manage2)する」の手順に従って、myothergpo をアーカイブに確認し、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-386">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="ba45a-387">MyOtherGPO を MyGPO と比較することも、差分レポートを使用して MyTemplate にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-387">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="ba45a-388">レビュー担当者の役割を含むすべてのアカウント (AGPM 管理者 \ [フルコントロール \]、承認者、編集者、または校閲者) は、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-388">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="ba45a-389">GPO を別の GPO とテンプレートに比較するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-389">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="ba45a-390">MyGPO と MyOtherGPO を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-390">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="ba45a-391">[**コントロール**] タブで、[ **mygpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-391">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="ba45a-392">**Ctrl**キーを押してから、[ **myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-392">Press **CTRL** and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="ba45a-393">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[ **HTML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-393">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="ba45a-394">MyOtherGPO と MyTemplate を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="ba45a-394">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="ba45a-395">[**コントロール**] タブで、[ **myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-395">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="ba45a-396">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[**テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-396">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="ba45a-397">[ **MyTemplate** And **HTML レポート**] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-397">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="ba45a-398">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="ba45a-398">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="ba45a-399">この手順では、GPO を削除するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-399">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="ba45a-400">GPO を削除するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-400">To delete a GPO</span></span>**

1.  <span data-ttu-id="ba45a-401">AGPM クライアントがインストールされているコンピューターで、承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-401">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="ba45a-402">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-402">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="ba45a-403">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-403">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="ba45a-404">[ **Mygpo**] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-404">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="ba45a-405">[**アーカイブと運用] から [gpo の削除**] をクリックして、アーカイブのバージョンと、展開されたバージョンの gpo の両方を運用環境で削除します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-405">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="ba45a-406">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-406">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="ba45a-407">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-407">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-408">GPO は [**コントロール**] タブから削除され、[**ごみ箱**] タブに表示され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-408">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="ba45a-409">場合によっては、GPO を削除した後に、まだ必要であることがわかっていることがあります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-409">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="ba45a-410">この手順では、削除された GPO を復元するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-410">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="ba45a-411">削除された GPO を復元するには</span><span class="sxs-lookup"><span data-stu-id="ba45a-411">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="ba45a-412">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-412">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="ba45a-413">[ **Mygpo**] を右クリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-413">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="ba45a-414">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-414">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="ba45a-415">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-415">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-416">GPO は [**ごみ箱**] タブから削除され、[**コントロール**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-416">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="ba45a-417">**注** GPO をアーカイブに復元しても、運用環境に自動的に再配置されることはありません。</span><span class="sxs-lookup"><span data-stu-id="ba45a-417">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="ba45a-418">GPO を運用環境に戻すには、「[手順 3: gpo を確認して展開](#bkmk-manage3)する」のように gpo を展開します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-418">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="ba45a-419">GPO の編集と展開を行った後に、GPO の最近の変更によって問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="ba45a-419">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="ba45a-420">この手順では、前のバージョンの GPO にロールバックするための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-420">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="ba45a-421">GPO の履歴で任意のバージョンにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-421">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="ba45a-422">コメントとラベルを使用して既知の適切なバージョンを識別したり、特定の変更が行われた日時を確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-422">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="ba45a-423">以前のバージョンの GPO にロールバックするには</span><span class="sxs-lookup"><span data-stu-id="ba45a-423">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="ba45a-424">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-424">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="ba45a-425">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="ba45a-425">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="ba45a-426">展開するバージョンを右クリックし、[**展開**] をクリックして、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-426">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="ba45a-427">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-427">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="ba45a-428">[**履歴**] ウィンドウで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-428">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="ba45a-429">**注** 再展開されたバージョンが目的のバージョンであることを確認するには、2つのバージョンの差異レポートを調べます。</span><span class="sxs-lookup"><span data-stu-id="ba45a-429">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="ba45a-430">GPO の [**履歴**] ウィンドウで、2つのバージョンを選択して右クリックし、[**相違**点] をポイントして、[ **HTML レポート**] または [ **XML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ba45a-430">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





