---
title: Microsoft Advanced Group Policy Management 3.0 ステップ バイ ステップ ガイド
description: Microsoft Advanced Group Policy Management 3.0 ステップ バイ ステップ ガイド
author: dansimp
ms.assetid: d067f465-d7c8-4f6d-b311-66b9b06874f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b4efa5075027e99a3e50a344aafcdf6f6f69a147
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818327"
---
# <span data-ttu-id="94be7-103">Microsoft Advanced Group Policy Management 3.0 ステップ バイ ステップ ガイド</span><span class="sxs-lookup"><span data-stu-id="94be7-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="94be7-104">このステップバイステップガイドでは、グループポリシー管理コンソール (GPMC) と Microsoft Advanced グループポリシー管理 (AGPM) を使用した、グループポリシー管理の高度な手法を示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-104">This step-by-step guide demonstrates advanced techniques for Group Policy management using the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="94be7-105">AGPM によって GPMC の機能が向上し、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="94be7-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="94be7-106">グループポリシーオブジェクト (Gpo) を複数のグループポリシー管理者に委任するための標準的な役割、および運用環境で Gpo へのアクセスを委任する機能。</span><span class="sxs-lookup"><span data-stu-id="94be7-106">Standard roles for delegating permissions to manage Group Policy objects (GPOs) to multiple Group Policy administrators, as well as the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="94be7-107">グループポリシー管理者が、運用環境に展開する前に、Gpo をオフラインで作成して変更できるようにするアーカイブ。</span><span class="sxs-lookup"><span data-stu-id="94be7-107">An archive to enable Group Policy administrators to create and modify GPOs offline before deploying them to a production environment.</span></span>

-   <span data-ttu-id="94be7-108">以前のバージョンの GPO にロールバックして、アーカイブに保存されているバージョンの数を制限することができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-108">The ability to roll back to any previous version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="94be7-109">グループポリシーの管理者が互いの作業を誤って上書きしないように、Gpo のチェックイン/チェックアウト機能。</span><span class="sxs-lookup"><span data-stu-id="94be7-109">Check-in/check-out capability for GPOs to ensure that Group Policy administrators do not inadvertently overwrite each other's work.</span></span>

## <span data-ttu-id="94be7-110">AGPM シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="94be7-110">AGPM scenario overview</span></span>


<span data-ttu-id="94be7-111">このシナリオでは、AGPM の各役割に対して個別のユーザーアカウントを使用して、さまざまなレベルの権限を持つ複数のグループポリシー管理者が環境内でグループポリシーを管理する方法を示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-111">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment with multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="94be7-112">具体的には、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="94be7-112">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="94be7-113">Domain Admins グループのメンバーであるアカウントを使用して、AGPM サーバーをインストールし、アカウントまたはグループに AGPM 管理者の役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94be7-113">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="94be7-114">AGPM ロールを割り当てるアカウントを使用し、AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="94be7-114">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="94be7-115">AGPM 管理者の役割を持つアカウントを使用して、他のアカウントに役割を割り当てることによって、Gpo への AGPM アクセスと代理人アクセスを構成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-115">Using an account with the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="94be7-116">編集者の役割を持つアカウントを使用して、GPO の作成を要求します。これにより、承認者の役割を持つアカウントを使用して承認します。</span><span class="sxs-lookup"><span data-stu-id="94be7-116">Using an account with the Editor role, request the creation of a GPO, which you then approve using an account with the Approver role.</span></span> <span data-ttu-id="94be7-117">エディターアカウントを使用して、アーカイブから GPO をチェックアウトして、GPO を編集し、GPO をアーカイブにチェックインして、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="94be7-117">With the Editor account, check the GPO out of the archive, edit the GPO, check the GPO into the archive, and request deployment.</span></span>

-   <span data-ttu-id="94be7-118">承認者の役割を持つアカウントを使用して、GPO を確認し、運用環境に展開します。</span><span class="sxs-lookup"><span data-stu-id="94be7-118">Using an account with the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="94be7-119">エディターロールを持つアカウントを使用して、GPO テンプレートを作成し、それを出発点として使用して新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-119">Using an account with the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="94be7-120">承認者の役割を持つアカウントを使用して、GPO を削除および復元します。</span><span class="sxs-lookup"><span data-stu-id="94be7-120">Using an account with the Approver role, delete and restore a GPO.</span></span>

![グループポリシーオブジェクトの開発プロセス](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="94be7-122">要件</span><span class="sxs-lookup"><span data-stu-id="94be7-122">Requirements</span></span>


<span data-ttu-id="94be7-123">AGPM をインストールするコンピューターは、次の要件を満たしている必要があります。このシナリオで使用するには、アカウントを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-123">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="94be7-124">**注** AGPM 2.5 がインストールされていて、Windows Server®2003から Windows Server2008 または WindowsVista®にアップグレードしていて、サービスパックがインストールされていない場合は、AGPM 3.0 にアップグレードする前に、オペレーティングシステムをアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-124">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008 or WindowsVista® with no service packs installed to WindowsVista with Service Pack1, you must upgrade the operating system before you can upgrade to AGPM3.0.</span></span>

 

### <span data-ttu-id="94be7-125">AGPM サーバーの要件</span><span class="sxs-lookup"><span data-stu-id="94be7-125">AGPM Server requirements</span></span>

<span data-ttu-id="94be7-126">AGPM サーバー3.0 を使用するには、サービス Pack1 と、リモートサーバー管理ツール (RSAT) の GPMC をインストールした Windows Server2008 または WindowsVista が必要です。</span><span class="sxs-lookup"><span data-stu-id="94be7-126">AGPM Server3.0 requires Windows Server2008 or WindowsVista with Service Pack1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="94be7-127">32ビットと64ビットの両方のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94be7-127">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="94be7-128">AGPM サーバーをインストールする前に、ドメイン管理者グループのメンバーであり、特に記載されていない限り、次の Windows 機能が存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-128">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="94be7-129">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="94be7-129">GPMC</span></span>

    -   <span data-ttu-id="94be7-130">Windows Server 2008: 表示されない場合は、AGPM によって GPMC が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="94be7-130">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="94be7-131">Windows Vista の場合: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-131">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="94be7-132">詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkID=116179> 。</span><span class="sxs-lookup"><span data-stu-id="94be7-132">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="94be7-133">.NET Framework 3.5</span><span class="sxs-lookup"><span data-stu-id="94be7-133">.NET Framework 3.5</span></span>

<span data-ttu-id="94be7-134">次の Windows 機能は、AGPM サーバーによって必要とされます。存在しない場合は自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="94be7-134">The following Windows features are required by AGPM Server and will be automatically installed if not present:</span></span>

-   <span data-ttu-id="94be7-135">WCF のアクティベーションHTTP 以外のアクティベーション</span><span class="sxs-lookup"><span data-stu-id="94be7-135">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="94be7-136">Windows プロセス アクティブ化サービス</span><span class="sxs-lookup"><span data-stu-id="94be7-136">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="94be7-137">プロセスモデル</span><span class="sxs-lookup"><span data-stu-id="94be7-137">Process Model</span></span>

    -   <span data-ttu-id="94be7-138">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="94be7-138">.NET Environment</span></span>

    -   <span data-ttu-id="94be7-139">構成 Api</span><span class="sxs-lookup"><span data-stu-id="94be7-139">Configuration APIs</span></span>

### <span data-ttu-id="94be7-140">AGPM クライアントの要件</span><span class="sxs-lookup"><span data-stu-id="94be7-140">AGPM Client requirements</span></span>

<span data-ttu-id="94be7-141">AGPM クライアント3.0 には、Service Pack 1 と GPMC とのリモートサーバー管理ツール (RSAT) がインストールされている Windows Server2008 または WindowsVista が必要です。</span><span class="sxs-lookup"><span data-stu-id="94be7-141">AGPM Client3.0 requires Windows Server2008 or WindowsVista with Service Pack 1 and the GPMC from Remote Server Administration Tools (RSAT) installed.</span></span> <span data-ttu-id="94be7-142">32ビットと64ビットの両方のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="94be7-142">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="94be7-143">Agpm クライアントは、AGPM サーバーを実行しているコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="94be7-143">AGPM Client can be installed on a computer running AGPM Server.</span></span>

<span data-ttu-id="94be7-144">次の Windows 機能は、AGPM クライアントによって必要とされ、特に記載がない限り、存在しない場合は自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="94be7-144">The following Windows features are required by AGPM Client and will be automatically installed if not present unless otherwise noted:</span></span>

-   <span data-ttu-id="94be7-145">GPMC.MSC</span><span class="sxs-lookup"><span data-stu-id="94be7-145">GPMC</span></span>

    -   <span data-ttu-id="94be7-146">Windows Server 2008: 表示されない場合は、AGPM によって GPMC が自動的にインストールされます。</span><span class="sxs-lookup"><span data-stu-id="94be7-146">Windows Server 2008: The GPMC is automatically installed by AGPM if not present.</span></span>

    -   <span data-ttu-id="94be7-147">Windows Vista の場合: AGPM をインストールする前に、RSAT から GPMC をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-147">Windows Vista: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="94be7-148">詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkID=116179> 。</span><span class="sxs-lookup"><span data-stu-id="94be7-148">For more information, see <https://go.microsoft.com/fwlink/?LinkID=116179>.</span></span>

-   <span data-ttu-id="94be7-149">.NET Framework 3.0</span><span class="sxs-lookup"><span data-stu-id="94be7-149">.NET Framework 3.0</span></span>

### <span data-ttu-id="94be7-150">シナリオの要件</span><span class="sxs-lookup"><span data-stu-id="94be7-150">Scenario requirements</span></span>

<span data-ttu-id="94be7-151">このシナリオを始める前に、4つのユーザーアカウントを作成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-151">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="94be7-152">このシナリオでは、これらの各アカウントに、AGPM 管理者 (フルコントロール)、承認者、編集者、および校閲者といういずれかの AGPM ロールを割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94be7-152">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="94be7-153">これらのアカウントでは、電子メールメッセージの送受信が可能である必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-153">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="94be7-154">AGPM 管理者、承認者、(必要に応じて) エディターの各役割を持つアカウントに**リンク gpo**のアクセス許可を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94be7-154">Assign **Link GPOs** permission to the accounts with the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="94be7-155">**注** 
[ **Gpo のリンク**] 権限は、既定でドメイン管理者とエンタープライズ管理者のメンバーに割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="94be7-155">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="94be7-156">追加のユーザーまたはグループ (AGPM 管理者または承認者の役割を持つアカウントなど) に**リンク gpo**のアクセス許可を割り当てるには、ドメインのノードをクリックし、[**委任**] タブをクリックし、[ **gpo のリンク**]、[**追加**] の順にクリックして、アクセス許可を割り当てるユーザーまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-156">To assign **Link GPOs** permission to additional users or groups (such as accounts with the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which to assign the permission.</span></span>

 

## <span data-ttu-id="94be7-157">AGPM のインストールと構成の手順</span><span class="sxs-lookup"><span data-stu-id="94be7-157">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="94be7-158">AGPM をインストールして構成するには、次の手順を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-158">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="94be7-159">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="94be7-159">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="94be7-160">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="94be7-160">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="94be7-161">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="94be7-161">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="94be7-162">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="94be7-162">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="94be7-163">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="94be7-163">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="94be7-164">手順 1: AGPM サーバーをインストールする</span><span class="sxs-lookup"><span data-stu-id="94be7-164">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="94be7-165">この手順では、AGPM サービスを実行するメンバーサーバーまたはドメインコントローラーに AGPM サーバーをインストールし、アーカイブを構成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-165">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="94be7-166">すべての AGPM 操作は、この Windows サービスを通じて管理され、サービスの資格情報を使って実行されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-166">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="94be7-167">AGPM サーバーによって管理されるアーカイブは、そのサーバーまたは同じフォレスト内の別のサーバー上でホストすることができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-167">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="94be7-168">AGPM サービスをホストするコンピューターに AGPM サーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="94be7-168">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="94be7-169">Domain Admins グループのメンバーであるアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-169">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="94be7-170">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシー管理-サーバー**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94be7-170">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="94be7-171">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-171">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="94be7-172">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-172">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

5.  <span data-ttu-id="94be7-173">[**アプリケーションパス**] ダイアログボックスで、AGPM サーバーをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="94be7-173">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="94be7-174">AGPM サーバーがインストールされているコンピューターは、AGPM サービスをホストし、アーカイブを管理します。</span><span class="sxs-lookup"><span data-stu-id="94be7-174">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="94be7-175">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-175">Click **Next**.</span></span>

6.  <span data-ttu-id="94be7-176">[**アーカイブパス**] ダイアログボックスで、AGPM サーバーとの相対的なアーカイブの場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="94be7-176">In the **Archive Path** dialog box, select a location for the archive relative to the AGPM Server.</span></span> <span data-ttu-id="94be7-177">アーカイブパスは、AGPM サーバー上のフォルダーを指すことができますが、この AGPM サーバーで管理されているすべての Gpo と履歴データを格納するのに十分な領域がある場所を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-177">The archive path can point to a folder on the AGPM Server or elsewhere, but you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="94be7-178">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-178">Click **Next**.</span></span>

7.  <span data-ttu-id="94be7-179">[ **Agpm サービスアカウント**] ダイアログボックスで、agpm サービスを実行するサービスアカウントを選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-179">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

8.  <span data-ttu-id="94be7-180">[**アーカイブの所有者**] ダイアログボックスで、AGPM 管理者 (フルコントロール) の役割を最初に割り当てるアカウントまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-180">In the **Archive Owner** dialog box, select an account or group to which to initially assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="94be7-181">この AGPM 管理者は、agpm ロールと権限を他のグループポリシー管理者に割り当てることができます (AGPM 管理者の役割を含む)。</span><span class="sxs-lookup"><span data-stu-id="94be7-181">This AGPM Administrator can assign AGPM roles and permissions to other Group Policy administrators (including the role of AGPM Administrator).</span></span> <span data-ttu-id="94be7-182">このシナリオでは、AGPM 管理者の役割で利用するアカウントを選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-182">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="94be7-183">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-183">Click **Next**.</span></span>

9.  <span data-ttu-id="94be7-184">[**ポートの構成**] ダイアログボックスで、AGPM サービスがリッスンするポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-184">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="94be7-185">手動でポートの例外を構成するか、ルールを使用してポートの例外を構成する場合以外は、[**ファイアウォールにポートの例外を追加**する] チェックボックスをオフにしないでください。</span><span class="sxs-lookup"><span data-stu-id="94be7-185">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="94be7-186">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-186">Click **Next**.</span></span>

10. <span data-ttu-id="94be7-187">[**言語**の選択] ダイアログボックスで、AGPM サーバー用にインストールする1つ以上の表示言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-187">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="94be7-188">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="94be7-188">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="94be7-189">**注意** AGPM サービスの設定は、オペレーティングシステムの**管理ツール**と**サービス**を使って変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="94be7-189">**Caution** Do not modify settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="94be7-190">これにより、AGPM サービスが開始されないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-190">Doing so can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="94be7-191">サービスの設定を変更する方法については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94be7-191">For information on how to modify settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="94be7-192">手順 2: AGPM クライアントをインストールする</span><span class="sxs-lookup"><span data-stu-id="94be7-192">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="94be7-193">各グループポリシー管理者 (Gpo の作成、編集、展開、確認、削除) には、Gpo を管理するために使用するコンピューターに AGPM クライアントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-193">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="94be7-194">このシナリオでは、少なくとも1台のコンピューターに AGPM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="94be7-194">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="94be7-195">グループポリシー管理を実行しないエンドユーザーのコンピューターに AGPM クライアントをインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="94be7-195">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="94be7-196">グループポリシー管理者のコンピューターに AGPM クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="94be7-196">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="94be7-197">Microsoft デスクトップ最適化パック CD を起動し、画面の指示に従って [**高度なグループポリシーの管理**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="94be7-197">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="94be7-198">[**ようこそ**] ダイアログボックスで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-198">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="94be7-199">[ **Microsoft ソフトウェアライセンス条項**] ダイアログボックスで、条項に同意し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-199">In the **Microsoft Software License Terms** dialog box, accept the terms and click **Next**.</span></span>

4.  <span data-ttu-id="94be7-200">[**アプリケーションパス**] ダイアログボックスで、AGPM クライアントをインストールする場所を選択します。</span><span class="sxs-lookup"><span data-stu-id="94be7-200">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="94be7-201">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-201">Click **Next**.</span></span>

5.  <span data-ttu-id="94be7-202">[ **Agpm サーバー** ] ダイアログボックスで、agpm サーバーの完全修飾コンピューター名と接続先のポートを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-202">In the **AGPM Server** dialog box, type the fully-qualified computer name for the AGPM Server and the port to which to connect.</span></span> <span data-ttu-id="94be7-203">AGPM サービスの既定のポートは4600です。</span><span class="sxs-lookup"><span data-stu-id="94be7-203">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="94be7-204">手動でポートの例外を構成するか、ルールを使用してポートの例外を構成する場合以外は、[ **Microsoft 管理コンソールをファイアウォールで許可**する] チェックボックスをオフにしないようにします。</span><span class="sxs-lookup"><span data-stu-id="94be7-204">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="94be7-205">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-205">Click **Next**.</span></span>

6.  <span data-ttu-id="94be7-206">[**言語**の選択] ダイアログボックスで、AGPM クライアント用にインストールする1つ以上の表示言語を選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-206">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="94be7-207">[**インストール**] をクリックし、[**完了**] をクリックして、セットアップウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="94be7-207">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="94be7-208">手順 3: AGPM サーバー接続を構成する</span><span class="sxs-lookup"><span data-stu-id="94be7-208">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="94be7-209">AGPM は、各グループポリシーオブジェクト (GPO) のすべてのバージョンを格納します。この GPO は、AGPM が変更の制御を提供します。これは、グループポリシー管理者が、展開されたバージョンの各 GPO に影響を与えずに、オフラインで Gpo を表示したり、変更したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-209">AGPM stores all versions of each controlled Group Policy object (GPO)—a GPO for which AGPM provides change control—in a central archive, so Group Policy administrators can view and modify GPOs offline without immediately impacting the deployed version of each GPO.</span></span>

<span data-ttu-id="94be7-210">この手順では、AGPM サーバー接続を構成し、すべてのグループポリシー管理者が同じ AGPM サーバーに接続できるようにします。</span><span class="sxs-lookup"><span data-stu-id="94be7-210">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="94be7-211">(複数の AGPM サーバーを構成する方法について詳しくは、「高度なグループポリシー管理のヘルプ」をご覧ください。)</span><span class="sxs-lookup"><span data-stu-id="94be7-211">(For information about configuring multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="94be7-212">すべてのグループポリシー管理者に対して AGPM サーバー接続を構成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-212">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="94be7-213">AGPM クライアントをインストールしたコンピューターで、アーカイブの所有者として選択したユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-213">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="94be7-214">このユーザーは、AGPM 管理者 (フルコントロール) の役割を持っています。</span><span class="sxs-lookup"><span data-stu-id="94be7-214">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="94be7-215">[**スタート**] をクリックし、[**管理ツール**] をポイントして、[**グループポリシーの管理**] をクリックして GPMC を開きます。</span><span class="sxs-lookup"><span data-stu-id="94be7-215">Click **Start**, point to **Administrative Tools**, and click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="94be7-216">すべてのグループポリシー管理者に適用される GPO を編集します。</span><span class="sxs-lookup"><span data-stu-id="94be7-216">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="94be7-217">[**グループポリシー管理エディター** ] ウィンドウで、[**ユーザーの構成**]、[**ポリシー**]、[**管理用テンプレート**]、[ **Windows コンポーネント**]、[ **AGPM**] の順にダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-217">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="94be7-218">詳細ウィンドウで、[ **agpm: 既定の AGPM サーバーを指定してください (すべてのドメイン)**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-218">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="94be7-219">[**プロパティ**] ウィンドウで、[**有効**] を選び、アーカイブをホストしているサーバーの完全修飾コンピューター名とポート ( **server.contoso.com:4600**など) を入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-219">In the **Properties** window, select **Enabled** and type the fully-qualified computer name and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="94be7-220">既定では、AGPM サービスはポート4600を使用します。</span><span class="sxs-lookup"><span data-stu-id="94be7-220">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="94be7-221">[ **OK**] をクリックし、[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94be7-221">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="94be7-222">グループポリシーが更新されると、各グループポリシーの管理者に対して AGPM サーバー接続が構成されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-222">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="94be7-223">手順 4: 電子メール通知を構成する</span><span class="sxs-lookup"><span data-stu-id="94be7-223">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="94be7-224">AGPM 管理者 (フルコントロール) として、エディターが GPO を作成、展開、または削除しようとしたときに、要求を含む電子メールメッセージが送信される承認者の電子メールアドレスを指定します。</span><span class="sxs-lookup"><span data-stu-id="94be7-224">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message containing a request is sent when an Editor attempts to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="94be7-225">また、これらのメッセージの送信元のエイリアスを指定します。</span><span class="sxs-lookup"><span data-stu-id="94be7-225">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="94be7-226">AGPM の電子メール通知を構成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-226">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="94be7-227">詳細ウィンドウで、[ **Domain Delegation** ] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-227">In the details pane, click the **Domain Delegation** tab.</span></span>

2.  <span data-ttu-id="94be7-228">[**差出人の電子メールアドレス**] フィールドに、通知の送信先となる AGPM の電子メールエイリアスを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-228">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

3.  <span data-ttu-id="94be7-229">[**宛先の電子メールアドレス**] フィールドに、承認者の役割を割り当てるユーザーアカウントの電子メールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-229">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

4.  <span data-ttu-id="94be7-230">[ **Smtp server** ] フィールドに、有効な smtp メールサーバーを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-230">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

5.  <span data-ttu-id="94be7-231">[**ユーザー名**] フィールドと [**パスワード**] フィールドに、SMTP サービスへのアクセス権を持つユーザーの資格情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-231">In the **User name** and **Password** fields, type the credentials of a user with access to the SMTP service.</span></span> <span data-ttu-id="94be7-232">**[適用]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-232">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="94be7-233">手順 5: 代理人アクセス</span><span class="sxs-lookup"><span data-stu-id="94be7-233">Step 5: Delegate access</span></span>

<span data-ttu-id="94be7-234">AGPM 管理者 (フルコントロール) として、Gpo へのドメインレベルのアクセスを委任し、各グループポリシー管理者のアカウントに役割を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94be7-234">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="94be7-235">**注** また、ドメインレベルではなく、GPO レベルでアクセスを委任することもできます。</span><span class="sxs-lookup"><span data-stu-id="94be7-235">**Note** You can also delegate access at the GPO level rather than the domain level.</span></span> <span data-ttu-id="94be7-236">詳細については、「高度なグループポリシー管理のヘルプ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="94be7-236">For details, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="94be7-237">**重要** グループポリシー作成者グループのメンバーシップを制限して、Gpo へのアクセスの AGPM 管理を回避することができないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-237">**Important** You should restrict membership in the Group Policy Creator Owners group, so it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="94be7-238">(**グループポリシー管理コンソール**で、gpo を管理するフォレストとドメインの [**グループポリシーオブジェクト**] をクリックし、[**委任**] をクリックして、組織のニーズに合わせて設定を構成します)。</span><span class="sxs-lookup"><span data-stu-id="94be7-238">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="94be7-239">ドメイン全体のすべての Gpo へのアクセスを委任するには</span><span class="sxs-lookup"><span data-stu-id="94be7-239">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="94be7-240">[ **Domain Delegation** ] タブで、[**追加**] ボタンをクリックし、承認者として使用するグループポリシー管理者のユーザーアカウントを選択して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-240">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="94be7-241">[**グループまたはユーザーの追加**] ダイアログボックスで、**承認者**ロールを選択して、その役割をアカウントに割り当て、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-241">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="94be7-242">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="94be7-242">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="94be7-243">[**追加**] ボタンをクリックし、編集者として使用するグループポリシー管理者のユーザーアカウントを選んで、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-243">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="94be7-244">[**グループまたはユーザーの追加**] ダイアログボックスで、その役割をアカウントに割り当てるための**エディター**の役割を選び、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-244">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="94be7-245">(この役割にはレビュー担当者の役割が含まれます。)</span><span class="sxs-lookup"><span data-stu-id="94be7-245">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="94be7-246">[**追加**] ボタンをクリックし、校閲者として使用するグループポリシー管理者のユーザーアカウントを選んで、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-246">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="94be7-247">[**グループまたはユーザーの追加**] ダイアログボックスで、[**校閲者**] の役割を選択して、その役割のみをアカウントに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="94be7-247">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="94be7-248">Gpo を管理する手順</span><span class="sxs-lookup"><span data-stu-id="94be7-248">Steps for managing GPOs</span></span>


<span data-ttu-id="94be7-249">AGPM を使って Gpo を作成、編集、確認、展開するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-249">You must complete the following steps to create, edit, review, and deploy GPOs using AGPM.</span></span> <span data-ttu-id="94be7-250">さらに、テンプレートを作成し、GPO を削除して、削除された GPO を復元します。</span><span class="sxs-lookup"><span data-stu-id="94be7-250">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="94be7-251">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="94be7-251">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="94be7-252">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="94be7-252">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="94be7-253">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="94be7-253">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="94be7-254">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="94be7-254">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="94be7-255">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="94be7-255">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="94be7-256">手順 1: GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="94be7-256">Step 1: Create a GPO</span></span>

<span data-ttu-id="94be7-257">複数のグループポリシー管理者がいる環境では、編集者の役割を持つユーザーは新しい Gpo の作成を要求することができますが、新しい GPO の作成が運用環境に影響を与えるため、そのような要求は、承認者の役割を持つユーザーによって承認される必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-257">In an environment with multiple Group Policy administrators, those with the Editor role have the ability to request the creation of new GPOs, but such a request must be approved by someone with the Approver role because the creation of a new GPO impacts the production environment.</span></span>

<span data-ttu-id="94be7-258">この手順では、新しい GPO の作成を要求するために、編集者の役割を持つアカウントを使用します。</span><span class="sxs-lookup"><span data-stu-id="94be7-258">In this step, you use an account with the Editor role to request the creation of a new GPO.</span></span> <span data-ttu-id="94be7-259">承認者の役割を持つアカウントを使用して、この要求を承認し、GPO の作成を完了します。</span><span class="sxs-lookup"><span data-stu-id="94be7-259">Using an account with the Approver role, you approve this request and complete the creation of a GPO.</span></span>

**<span data-ttu-id="94be7-260">AGPM で管理される新しい GPO の作成を要求するには</span><span class="sxs-lookup"><span data-stu-id="94be7-260">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="94be7-261">AGPM クライアントをインストールしたコンピューターで、AGPM のエディターロールが割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-261">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="94be7-262">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-262">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="94be7-263">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-263">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="94be7-264">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="94be7-264">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="94be7-265">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-265">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="94be7-266">新しい GPO の名前として「 **Mygpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-266">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="94be7-267">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-267">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="94be7-268">[**ライブの作成**] をクリックすると、新しい GPO が承認されたときにすぐに運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-268">Click **Create live** so the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="94be7-269">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-269">Click **Submit**.</span></span>

5.  <span data-ttu-id="94be7-270">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-270">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-271">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-271">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="94be7-272">保留中の要求を承認して GPO を作成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-272">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="94be7-273">AGPM クライアントをインストールしたコンピューターで、AGPM で承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-273">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="94be7-274">アカウントのメールの受信トレイを開き、GPO を作成するための編集要求を含む、AGPM エイリアスからのメールメッセージを受信していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="94be7-274">Open the e-mail inbox for the account, and note that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="94be7-275">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-275">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="94be7-276">[**コンテンツ**] タブで、[**保留中**] タブをクリックして、保留中の gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-276">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="94be7-277">[ **Mygpo**] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-277">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="94be7-278">GPO の作成の承認を確認するには、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-278">Click **Yes** to confirm approval of the creation of the GPO.</span></span> <span data-ttu-id="94be7-279">GPO が [**コントロール**] タブに移動します。</span><span class="sxs-lookup"><span data-stu-id="94be7-279">The GPO is moved to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="94be7-280">手順 2: GPO を編集する</span><span class="sxs-lookup"><span data-stu-id="94be7-280">Step 2: Edit a GPO</span></span>

<span data-ttu-id="94be7-281">Gpo を使って、コンピューターやユーザーの設定を構成し、多くのコンピューターまたはユーザーに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-281">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="94be7-282">この手順では、編集者の役割を持つアカウントを使用して、アーカイブから GPO をチェックアウトし、その gpo をオフラインで編集して、編集した GPO をアーカイブにチェックインして、GPO の展開を運用環境に要求します。</span><span class="sxs-lookup"><span data-stu-id="94be7-282">In this step, you use an account with the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="94be7-283">このシナリオでは、パスワードの長さが8文字以上であることを要求するように、GPO の設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-283">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters in length.</span></span>

**<span data-ttu-id="94be7-284">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="94be7-284">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="94be7-285">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-285">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="94be7-286">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-286">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="94be7-287">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理されている gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-287">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="94be7-288">[ **Mygpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-288">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="94be7-289">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-289">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="94be7-290">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-290">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-291">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-291">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="94be7-292">GPO をオフラインで編集し、パスワードの最小文字数を構成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-292">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="94be7-293">[**コントロール**] タブで、[ **mygpo**] を右クリックし、[**編集**] をクリックして [**グループポリシー管理エディター** ] ウィンドウを開き、GPO のオフラインコピーに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="94be7-293">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="94be7-294">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-294">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="94be7-295">[**コンピューターの構成**] で、[**ポリシー**]、[ **Windows の設定**]、[**セキュリティの設定**]、[**アカウントポリシー**]、[**パスワードポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-295">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="94be7-296">詳細ウィンドウで、[**パスワードの最小文字数**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-296">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="94be7-297">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、文字数を**8**に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-297">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="94be7-298">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94be7-298">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="94be7-299">GPO をアーカイブにチェックインするには</span><span class="sxs-lookup"><span data-stu-id="94be7-299">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="94be7-300">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**チェックイン**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-300">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="94be7-301">コメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-301">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="94be7-302">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-302">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-303">[**コントロール**] タブでは、GPO の状態は**チェックイン済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-303">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="94be7-304">GPO の展開を運用環境に要求するには</span><span class="sxs-lookup"><span data-stu-id="94be7-304">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="94be7-305">[**コントロール**] タブで、[ **mygpo** ] を右クリックし、[**展開**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-305">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="94be7-306">このアカウントは承認者または AGPM 管理者ではないため、展開の要求を送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-306">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="94be7-307">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-307">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="94be7-308">GPO の履歴に表示するコメントを入力し、[**送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-308">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="94be7-309">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-309">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-310">[**保留中**] タブの gpo の一覧に**mygpo**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-310">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="94be7-311">手順 3: GPO を確認して展開する</span><span class="sxs-lookup"><span data-stu-id="94be7-311">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="94be7-312">この手順では、承認者は、承認が必要かどうかを判断するために、承認者として、また GPO の設定を作成し、設定を分析します。</span><span class="sxs-lookup"><span data-stu-id="94be7-312">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="94be7-313">GPO を評価した後、その GPO を運用環境に展開し、ドメインまたは組織単位 (OU) にリンクさせて、そのドメインまたは OU 内のコンピューターのグループポリシーが更新されたときに有効になるようにします。</span><span class="sxs-lookup"><span data-stu-id="94be7-313">After evaluating the GPO, you deploy it to the production environment and link it to a domain or an organizational unit (OU) so that it takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="94be7-314">GPO の設定を確認するには</span><span class="sxs-lookup"><span data-stu-id="94be7-314">To review settings in the GPO</span></span>**

1. <span data-ttu-id="94be7-315">AGPM クライアントをインストールしたコンピューターで、AGPM で承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-315">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="94be7-316">(他のすべての役割に含まれている校閲者の役割を持つすべてのグループポリシー管理者が、GPO の設定を確認できます。)</span><span class="sxs-lookup"><span data-stu-id="94be7-316">(Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.)</span></span>

2. <span data-ttu-id="94be7-317">アカウントのメールの受信トレイを開き、GPO を展開するためのエディター要求で AGPM エイリアスからのメールメッセージを受信したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="94be7-317">Open the e-mail inbox for the account and note that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="94be7-318">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-318">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="94be7-319">[詳細] ウィンドウの [**コンテンツ**] タブで、[**保留中**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-319">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="94be7-320">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-320">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="94be7-321">最新バージョンの MyGPO の設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="94be7-321">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="94be7-322">[**履歴**] ウィンドウで、最新のタイムスタンプが設定されている GPO のバージョンを右クリックし、[**設定**] をクリックし、[ **HTML レポート**] をクリックして、gpo の設定の概要を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-322">In the **History** window, right-click the GPO version with the most recent timestamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="94be7-323">Web ブラウザーで、[**すべて表示**] をクリックして、GPO のすべての設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-323">In the Web browser, click **show all** to display all of the settings in the GPO.</span></span> <span data-ttu-id="94be7-324">ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94be7-324">Close the browser.</span></span>

7. <span data-ttu-id="94be7-325">最新バージョンの MyGPO と、アーカイブにチェックインされた最初のバージョンを比較します。</span><span class="sxs-lookup"><span data-stu-id="94be7-325">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="94be7-326">[**履歴**] ウィンドウで、最新のタイムスタンプが付いた GPO バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-326">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="94be7-327">CTRL キーを押しながら、**コンピューターのバージョン**が \* \* \ \ \ \* \* \* の最も古い GPO バージョンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-327">Press CTRL and click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="94be7-328">[**差分**] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-328">Click the **Differences** button.</span></span> <span data-ttu-id="94be7-329">[**アカウントポリシー] および [パスワードポリシー** ] セクションが緑色で、先頭が**\ [+ \]** で強調表示されています。この設定は、GPO の後者のバージョンでのみ構成されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-329">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**, indicating that this setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="94be7-330">[**アカウントポリシー**] の [パスワードポリシー] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-330">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="94be7-331">[**パスワードの長さ**] の設定は緑で、その前に**\ [+ \]** が強調表示されています。これは、GPO の後者のバージョンでのみ構成されていることを示しています。</span><span class="sxs-lookup"><span data-stu-id="94be7-331">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="94be7-332">Web ブラウザーを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94be7-332">Close the Web browser.</span></span>

**<span data-ttu-id="94be7-333">GPO を運用環境に展開するには</span><span class="sxs-lookup"><span data-stu-id="94be7-333">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="94be7-334">[**保留中**] タブで、[ **mygpo** ] を右クリックし、[**承認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-334">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="94be7-335">GPO の履歴に含めるコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-335">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="94be7-336">**[はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-336">Click **Yes**.</span></span> <span data-ttu-id="94be7-337">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-337">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-338">この GPO は、運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-338">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="94be7-339">GPO をドメインまたは組織単位にリンクするには</span><span class="sxs-lookup"><span data-stu-id="94be7-339">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="94be7-340">GPMC で、構成した GPO を適用するドメインまたは OU を右クリックし、[**既存の gpo にリンク**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-340">In the GPMC, right-click the domain or an OU to which to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="94be7-341">[ **GPO の選択**] ダイアログボックスで、[ **mygpo**] をクリックし、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-341">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="94be7-342">手順 4: テンプレートを使用して GPO を作成する</span><span class="sxs-lookup"><span data-stu-id="94be7-342">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="94be7-343">この手順では、編集者の役割を持つアカウントを使用して、新しい Gpo を作成するための開始点として使用するテンプレート (編集できない静的バージョンの GPO) を作成し、そのテンプレートに基づいて新しい GPO を作成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-343">In this step, you use an account with the Editor role to create a template—an uneditable, static version of a GPO for use as a starting point for creating new GPOs—and then create a new GPO based upon that template.</span></span> <span data-ttu-id="94be7-344">テンプレートは、同じ設定の多くを含む複数の Gpo をすばやく作成する場合に便利です。</span><span class="sxs-lookup"><span data-stu-id="94be7-344">Templates are useful for quickly creating multiple GPOs that include many of the same settings.</span></span>

**<span data-ttu-id="94be7-345">既存の GPO に基づいてテンプレートを作成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-345">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="94be7-346">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-346">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="94be7-347">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-347">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="94be7-348">[詳細] ウィンドウの [**コンテンツ**] タブで、[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-348">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="94be7-349">[ **Mygpo**] を右クリックし、[**テンプレートとして保存**] をクリックして、現在 mygpo に設定されているすべての設定が組み込まれているテンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-349">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="94be7-350">テンプレートの名前として「 **MyTemplate** 」と入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-350">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="94be7-351">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-351">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-352">新しいテンプレートが [**テンプレート**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-352">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="94be7-353">AGPM で管理される新しい GPO の作成を要求するには</span><span class="sxs-lookup"><span data-stu-id="94be7-353">To request the creation of a new GPO managed through AGPM</span></span>**

1.  <span data-ttu-id="94be7-354">[**コントロール**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-354">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="94be7-355">[ **Change Control** ] ノードを右クリックし、[**新しい**コントロールされた GPO] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-355">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="94be7-356">[**新しいコントロール**された GPO] ダイアログボックスで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="94be7-356">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="94be7-357">要求のコピーを受信するには、[ **Cc** ] フィールドにメールアドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-357">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="94be7-358">新しい GPO の名前として「 **Myothergpo** 」と入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-358">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="94be7-359">新しい GPO にコメントを入力します。</span><span class="sxs-lookup"><span data-stu-id="94be7-359">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="94be7-360">[**ライブの作成**] をクリックすると、新しい GPO は承認されるとすぐに運用環境に展開されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-360">Click **Create live**, so the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="94be7-361">[ **GPO テンプレート] から**[ **MyTemplate**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="94be7-361">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="94be7-362">**[送信]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-362">Click **Submit**.</span></span>

4.  <span data-ttu-id="94be7-363">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-363">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-364">新しい GPO が [**保留中**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-364">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="94be7-365">承認者の役割が割り当てられているアカウントを使用して、 [「手順 1: gpo を作成](#bkmk-manage1)する」の手順に従って、gpo を作成する保留中の要求を承認します。</span><span class="sxs-lookup"><span data-stu-id="94be7-365">Use an account that has been assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="94be7-366">MyTemplate には、MyGPO で構成したすべての設定が組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="94be7-366">MyTemplate incorporates all of the settings that you configured in MyGPO.</span></span> <span data-ttu-id="94be7-367">MyOtherGPO は MyTemplate を使用して作成されたため、最初は、MyTemplate が作成された時点で、MyGPO に含まれていたすべての設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="94be7-367">Because MyOtherGPO was created using MyTemplate, it initially contains all of the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="94be7-368">これを確認するには、MyOtherGPO と MyTemplate を比較するための差分レポートを生成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-368">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="94be7-369">編集のためにアーカイブから GPO をチェックアウトするには</span><span class="sxs-lookup"><span data-stu-id="94be7-369">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="94be7-370">AGPM クライアントがインストールされているコンピューターで、AGPM のエディターの役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-370">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="94be7-371">[ **Myothergpo**] を右クリックし、 **[チェックアウト**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-371">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="94be7-372">チェックアウトされているときに、GPO の履歴に表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-372">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="94be7-373">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-373">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-374">[**コントロール**] タブでは、GPO の状態は**チェックアウト済み**として識別されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-374">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="94be7-375">GPO をオフラインで編集して、アカウントのロックアウト期間を構成するには</span><span class="sxs-lookup"><span data-stu-id="94be7-375">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="94be7-376">[**コントロール**] タブで、[ **myothergpo**] を右クリックし、[**編集**] をクリックして [**グループポリシー管理エディター** ] ウィンドウを開き、GPO のオフラインコピーに変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="94be7-376">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and make changes to an offline copy of the GPO.</span></span> <span data-ttu-id="94be7-377">このシナリオでは、パスワードの最小文字数を構成します。</span><span class="sxs-lookup"><span data-stu-id="94be7-377">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="94be7-378">[**コンピューターの構成**] で、 **[ポリシー**]、[ **Windows の設定**]、[セキュリティの**設定**]、[**アカウントポリシー**]、[**アカウントロックアウトのポリシー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-378">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="94be7-379">詳細ウィンドウで、[**アカウントのロックアウトの期間**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-379">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="94be7-380">[プロパティ] ウィンドウで、[**このポリシー設定を定義**する] チェックボックスをオンにし、期間を**30**分に設定して、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-380">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="94be7-381">[**グループポリシー管理エディター** ] ウィンドウを閉じます。</span><span class="sxs-lookup"><span data-stu-id="94be7-381">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="94be7-382">[「手順 2: GPO を編集](#bkmk-manage2)する」の手順に従って、myothergpo をアーカイブに確認し、展開を要求します。</span><span class="sxs-lookup"><span data-stu-id="94be7-382">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="94be7-383">MyOtherGPO を MyGPO と比較することも、差分レポートを使用して MyTemplate にすることもできます。</span><span class="sxs-lookup"><span data-stu-id="94be7-383">You can compare MyOtherGPO to MyGPO or to MyTemplate using difference reports.</span></span> <span data-ttu-id="94be7-384">レビュー担当者の役割を含むすべてのアカウント (AGPM 管理者 \ [フルコントロール \]、承認者、編集者、または校閲者) は、レポートを生成できます。</span><span class="sxs-lookup"><span data-stu-id="94be7-384">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="94be7-385">GPO を別の GPO とテンプレートに比較するには</span><span class="sxs-lookup"><span data-stu-id="94be7-385">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="94be7-386">MyGPO と MyOtherGPO を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="94be7-386">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="94be7-387">[**コントロール**] タブで、[ **mygpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-387">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="94be7-388">CTRL キーを押してから、[ **Myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-388">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="94be7-389">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[ **HTML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-389">Right-click **MyOtherGPO**, point to **Differences**, and click **HTML Report**.</span></span>

2.  <span data-ttu-id="94be7-390">MyOtherGPO と MyTemplate を比較するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="94be7-390">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="94be7-391">[**コントロール**] タブで、[ **myothergpo**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-391">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="94be7-392">[ **Myothergpo**] を右クリックし、[**相違点**] をポイントして、[**テンプレート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-392">Right-click **MyOtherGPO**, point to **Differences**, and click **Template**.</span></span>

    3.  <span data-ttu-id="94be7-393">[ **MyTemplate** And **HTML レポート**] を選択し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-393">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="94be7-394">手順 5: GPO を削除および復元する</span><span class="sxs-lookup"><span data-stu-id="94be7-394">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="94be7-395">この手順では、GPO を削除するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="94be7-395">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="94be7-396">GPO を削除するには</span><span class="sxs-lookup"><span data-stu-id="94be7-396">To delete a GPO</span></span>**

1.  <span data-ttu-id="94be7-397">AGPM クライアントがインストールされているコンピューターで、承認者の役割が割り当てられているユーザーアカウントでログオンします。</span><span class="sxs-lookup"><span data-stu-id="94be7-397">On a computer on which you have installed AGPM Client, log on with a user account that has been assigned the role of Approver.</span></span>

2.  <span data-ttu-id="94be7-398">[**グループポリシー管理コンソール**] ツリーで、gpo を管理するフォレストとドメインの [ **Change Control** ] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-398">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="94be7-399">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-399">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="94be7-400">[ **Mygpo**] を右クリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-400">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="94be7-401">[**アーカイブと運用] から [gpo の削除**] をクリックして、アーカイブのバージョンと、展開されたバージョンの gpo の両方を運用環境で削除します。</span><span class="sxs-lookup"><span data-stu-id="94be7-401">Click **Delete GPO from archive and production** to delete both the version in the archive as well as the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="94be7-402">GPO の監査トレールに表示されるコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-402">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="94be7-403">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-404">GPO は [**コントロール**] タブから削除され、[**ごみ箱**] タブに表示され、そこで復元または破棄することができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-404">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="94be7-405">場合によっては、GPO を削除した後に、まだ必要であることがわかっていることがあります。</span><span class="sxs-lookup"><span data-stu-id="94be7-405">Occasionally you may discover after deleting a GPO that it is still needed.</span></span> <span data-ttu-id="94be7-406">この手順では、削除された GPO を復元するための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="94be7-406">In this step, you act as an Approver to restore a GPO that has been deleted.</span></span>

**<span data-ttu-id="94be7-407">削除された GPO を復元するには</span><span class="sxs-lookup"><span data-stu-id="94be7-407">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="94be7-408">[**コンテンツ**] タブで、[**ごみ箱**] タブをクリックして、削除された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-408">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="94be7-409">[ **Mygpo**] を右クリックし、[**復元**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-409">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="94be7-410">GPO の履歴に表示するコメントを入力し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-410">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="94be7-411">AGPM の**進行**状況ウィンドウで全体の進行状況が完了していることが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-411">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-412">GPO は [**ごみ箱**] タブから削除され、[**コントロール**] タブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="94be7-412">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="94be7-413">**注** GPO をアーカイブに復元しても、運用環境に自動的に再配置されることはありません。</span><span class="sxs-lookup"><span data-stu-id="94be7-413">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="94be7-414">GPO を運用環境に戻すには、「[手順 3: gpo を確認して展開](#bkmk-manage3)する」のように gpo を展開します。</span><span class="sxs-lookup"><span data-stu-id="94be7-414">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="94be7-415">GPO の編集と展開を行った後に、GPO の最近の変更によって問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="94be7-415">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="94be7-416">この手順では、前のバージョンの GPO にロールバックするための承認者としての役割を果たします。</span><span class="sxs-lookup"><span data-stu-id="94be7-416">In this step, you act as an Approver to roll back to a previous version of the GPO.</span></span> <span data-ttu-id="94be7-417">GPO の履歴で任意のバージョンにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-417">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="94be7-418">コメントとラベルを使用して既知の適切なバージョンを識別したり、特定の変更が行われた日時を確認したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="94be7-418">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="94be7-419">以前のバージョンの GPO にロールバックするには</span><span class="sxs-lookup"><span data-stu-id="94be7-419">To roll back to a previous version of a GPO</span></span>**

1.  <span data-ttu-id="94be7-420">[**コンテンツ**] タブで、[**コントロール**] タブをクリックして、管理された gpo を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-420">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="94be7-421">[ **Mygpo** ] をダブルクリックして、その履歴を表示します。</span><span class="sxs-lookup"><span data-stu-id="94be7-421">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="94be7-422">展開するバージョンを右クリックし、[**展開**] をクリックして、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-422">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="94be7-423">**進行**状況ウィンドウで全体の進行状況が完了したことが示されたら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-423">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="94be7-424">[**履歴**] ウィンドウで、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-424">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="94be7-425">**注** 再展開されたバージョンが目的のバージョンであることを確認するには、2つのバージョンの差異レポートを調べます。</span><span class="sxs-lookup"><span data-stu-id="94be7-425">**Note** To verify that the version that has been redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="94be7-426">GPO の [**履歴**] ウィンドウで、2つのバージョンを選択して右クリックし、[**相違**点] をポイントして、[ **HTML レポート**] または [ **XML レポート**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="94be7-426">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





