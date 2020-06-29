---
title: App-V 5.0 Sequencer および Client の展開計画
description: App-V 5.0 Sequencer および Client の展開計画
author: dansimp
ms.assetid: 57a604ad-90e1-4d32-86bb-eafff59aa43a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8c6f7c4d717acad014f079e51a7013a57766d9ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813466"
---
# <span data-ttu-id="6fbf8-103">App-V 5.0 Sequencer および Client の展開計画</span><span class="sxs-lookup"><span data-stu-id="6fbf8-103">Planning for the App-V 5.0 Sequencer and Client Deployment</span></span>


<span data-ttu-id="6fbf8-104">Microsoft Application Virtualization (App-v) 5.0 の使用を開始する前に、アプリ-V 5.0 sequencer、App-v 5.0 クライアントをインストールし、必要に応じて app-v 5.0 shared content store をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-104">Before you can start to use Microsoft Application Virtualization (App-V) 5.0, you must install the App-V 5.0 sequencer, the App-V 5.0 client, and optionally the App-V 5.0 shared content store.</span></span> <span data-ttu-id="6fbf8-105">以下のセクションでは、これらのインストールの計画について説明します。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-105">The following sections address planning for these installations.</span></span>

## <span data-ttu-id="6fbf8-106">App-v 5.0 sequencer の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="6fbf8-106">Planning for App-V 5.0 sequencer deployment</span></span>


<span data-ttu-id="6fbf8-107">App-v 5.0 は、シーケンスと呼ばれるプロセスを使って、仮想化されたアプリケーションとアプリケーションパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-107">App-V 5.0 uses a process called sequencing to create virtualized applications and application packages.</span></span> <span data-ttu-id="6fbf8-108">シーケンスには、App-v 5.0 sequencer を実行するコンピューターを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-108">Sequencing requires the use of a computer that runs the App-V 5.0 sequencer.</span></span>

<span data-ttu-id="6fbf8-109">**注** App-v 5.0 sequencer の新機能の詳細については、「 [app-v 5.0 の新](whats-new-in-app-v-50.md)機能」セクションの「 **Sequencer の変更点」を**参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-109">**Note** For information about the new functionality of App-V 5.0 sequencer, see the **Changes to the sequencer** section of [What's New in App-V 5.0](whats-new-in-app-v-50.md).</span></span>

 

<span data-ttu-id="6fbf8-110">App-v 5.0 sequencer を実行するコンピューターは、システムの最小要件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-110">The computer that runs the App-V 5.0 sequencer must meet the minimum system requirements.</span></span> <span data-ttu-id="6fbf8-111">これらの要件の一覧については、「 [app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-111">For a list of these requirements, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<span data-ttu-id="6fbf8-112">理想的には、仮想マシンとして実行されているコンピューターに sequencer をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-112">Ideally, you should install the sequencer on a computer running as a virtual machine.</span></span> <span data-ttu-id="6fbf8-113">これにより、sequencer を実行しているコンピューターをより簡単に "クリーン" 状態に戻すことができます。これにより、別のアプリケーションを順序付けることができます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-113">This enables you to more easily revert the computer running the sequencer to a “clean” state before sequencing another application.</span></span> <span data-ttu-id="6fbf8-114">仮想マシンを使用して sequencer をインストールする場合は、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-114">When you install the sequencer using a virtual machine, you should perform the following steps:</span></span>

1.  <span data-ttu-id="6fbf8-115">関連するすべての sequencer の前提条件をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-115">Install all associated sequencer prerequisites.</span></span>

2.  <span data-ttu-id="6fbf8-116">Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-116">Install the sequencer.</span></span>

3.  <span data-ttu-id="6fbf8-117">環境の "スナップショット" を取る。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-117">Take a “snapshot” of the environment.</span></span>

<span data-ttu-id="6fbf8-118">**重要** 会社のセキュリティチームが、シーケンス処理プランをレビューおよび承認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-118">**Important** You should have your corporate security team review and approve the sequencing process plan.</span></span> <span data-ttu-id="6fbf8-119">セキュリティ上の理由から、sequencer 操作は運用環境とは別のラボで保持する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-119">For security reasons, you should keep the sequencer operations in a lab that is separate from the production environment.</span></span> <span data-ttu-id="6fbf8-120">分離の配置は、ビジネス要件に基づいて、必要に応じてシンプルに、または包括的にすることができます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-120">The separation arrangement can be as simple or as comprehensive as necessary, based on your business requirements.</span></span> <span data-ttu-id="6fbf8-121">シーケンスコンピューターでは、完了したパッケージを運用サーバーにコピーするために、会社のネットワークに接続できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-121">The sequencing computers must be able to connect to the corporate network to copy finished packages to the production servers.</span></span> <span data-ttu-id="6fbf8-122">ただし、優先順位のコンピューターは通常、ウイルス対策による保護なしで運営されているため、企業ネットワーク上では保護されていない必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-122">However, because the sequencing computers are typically operated without antivirus protection, they must not be on the corporate network unprotected.</span></span> <span data-ttu-id="6fbf8-123">たとえば、ファイアウォールまたは分離されたネットワークセグメントの背後で操作できる場合があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-123">For example, you might be able to operate behind a firewall or on an isolated network segment.</span></span> <span data-ttu-id="6fbf8-124">分離された仮想ネットワークを共有するように構成されている仮想マシンを使用できる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-124">You might also be able to use virtual machines that are configured to share an isolated virtual network.</span></span> <span data-ttu-id="6fbf8-125">企業のセキュリティポリシーに従って、これらの懸念事項に安全に対応してください。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-125">Follow your corporate security policies to safely address these concerns.</span></span>

 

[<span data-ttu-id="6fbf8-126">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="6fbf8-126">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-beta-gb18030.md)

## <span data-ttu-id="6fbf8-127">App-v 5.0 クライアントの展開を計画する</span><span class="sxs-lookup"><span data-stu-id="6fbf8-127">Planning for App-V 5.0 client deployment</span></span>


<span data-ttu-id="6fbf8-128">ターゲットコンピューターで仮想化されたパッケージを実行するには、ターゲットコンピューターに App-v 5.0 クライアントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-128">To run virtualized packages on target computers, you must install the App-V 5.0 client on the target computers.</span></span> <span data-ttu-id="6fbf8-129">App-v 5.0 クライアントは、ターゲットコンピューターで仮想化されたアプリケーションを実行するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-129">The App-V 5.0 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="6fbf8-130">クライアントでは、ユーザーがアイコンや特定のファイルの種類を操作して、仮想化されたアプリケーションを開始できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-130">The client enables users to interact with icons and specific file types to start virtualized applications.</span></span> <span data-ttu-id="6fbf8-131">クライアントでは、管理サーバーからアプリケーションコンテンツを取得し、クライアントがアプリケーションを起動する前にコンテンツをキャッシュすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-131">The client also helps obtain application content from the management server and caches the content before the client starts the application.</span></span> <span data-ttu-id="6fbf8-132">2種類のクライアントがあります。リモートデスクトップサービスのクライアントであり、リモートデスクトップセッションホスト (RD セッションホスト) サーバーシステムと、他のすべてのコンピューターで使用される App-v 5.0 クライアントが使用されます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-132">There are two different client types: the client for Remote Desktop Services, which is used on Remote Desktop Session Host (RD Session Host) server systems and the App-V 5.0 client, which is used for all other computers.</span></span>

<span data-ttu-id="6fbf8-133">App-v 5.0 クライアントは、インストーラコマンドラインを使用するか、インストールが完了した後で PowerShell スクリプトを使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-133">The App-V 5.0 client should be configured by using either the installer command line or by using a PowerShell script after the installation has been completed.</span></span>

<span data-ttu-id="6fbf8-134">App-v 5.0 クライアントソフトウェアを展開するには、事前に設定を慎重に定義しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-134">The settings must be defined carefully in advance in order to expedite the deployment of the App-V 5.0 client software.</span></span> <span data-ttu-id="6fbf8-135">これは、さまざまな場所にあるコンピューターを使用していて、別の場所を使用するようにクライアントを構成する必要がある場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-135">This is especially important when you have computers in different offices where the clients must be configured to use different source locations.</span></span>

<span data-ttu-id="6fbf8-136">クライアントソフトウェアの展開方法も決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-136">You must also determine how you will deploy the client software.</span></span> <span data-ttu-id="6fbf8-137">各コンピューターにクライアントを手動で展開することもできますが、ほとんどの組織では、自動化されたプロセスを通じてクライアントを展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-137">Although it is possible to deploy the client manually on each computer, most organizations prefer to deploy the client through an automated process.</span></span> <span data-ttu-id="6fbf8-138">大規模な組織には、業務用の電子ソフトウェア配布 (ESD) システムがあります。これは、理想的なクライアント展開システムです。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-138">A larger organization might have an operational Electronic Software Distribution (ESD) system, which is an ideal client deployment system.</span></span> <span data-ttu-id="6fbf8-139">ESD システムが存在しない場合は、組織の標準的なソフトウェアインストール方法を使用できます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-139">If no ESD system exists, you can use your organization’s standard method of installing software.</span></span> <span data-ttu-id="6fbf8-140">可能な方法には、グループポリシーやさまざまなスクリプト手法があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-140">Possible methods include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="6fbf8-141">クライアントコンピューターの数と場所によっては、この展開プロセスが複雑になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-141">Depending on the quantity and disparate locations of your client computers, this deployment process can be complex.</span></span> <span data-ttu-id="6fbf8-142">すべてのコンピューターが正しい構成でクライアントをインストールできるように、構造化された手法を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-142">You must use a structured approach to ensure that all computers get the client installed with the correct configuration.</span></span>

<span data-ttu-id="6fbf8-143">クライアントの最小要件の一覧については、「 [app-v 5.0 の前提条件](app-v-50-prerequisites.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-143">For a list of the client minimum requirements see [App-V 5.0 Prerequisites](app-v-50-prerequisites.md).</span></span>

[<span data-ttu-id="6fbf8-144">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="6fbf8-144">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-gb18030.md)

## <a href="" id="bkmk-client-coexist"></a><span data-ttu-id="6fbf8-145">App-v クライアントの共存の計画</span><span class="sxs-lookup"><span data-stu-id="6fbf8-145">Planning for App-V client coexistence</span></span>


<span data-ttu-id="6fbf8-146">App-v 5.0 クライアントは、app-v 4.6 クライアントと並行して展開できます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-146">You can deploy the App-V 5.0 client side by side with the App-V 4.6 client.</span></span> <span data-ttu-id="6fbf8-147">クライアントの共存を使用するには、展開構成ファイルまたはユーザー構成ファイルを使用して、仮想化されたアプリケーションを追加または公開する必要があります。これらの構成ファイルには、アプリ-v 4.6 クライアントで動作するように構成する必要がある特定の設定が5.0 あります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-147">Client coexistence requires that you add or publish virtualized applications by using either a deployment configuration file or a user configuration file, because there are certain settings in these configuration files that must be configured in order for App-V 5.0 to function with App-V4.6 clients.</span></span> <span data-ttu-id="6fbf8-148">クライアントまたはサーバーのいずれかを使用してパッケージをアップグレードする場合、パッケージで構成ファイルを再送信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-148">When a package is upgraded by using either the client or the server, the package must resubmit the configuration file.</span></span> <span data-ttu-id="6fbf8-149">これは、対応する構成ファイルを持つすべてのパッケージに当てはまるため、クライアントの共存に固有ではありません。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-149">This is true for any package that has a corresponding configuration file, so it is not specific to client coexistence.</span></span> <span data-ttu-id="6fbf8-150">ただし、パッケージのアップグレード中に構成ファイルを送信しない場合、パッケージの状態は、共存シナリオでは予期したとおりに機能しません。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-150">However, if you do not submit the configuration file during the package upgrade, then the package state will not function as expected in coexistence scenarios.</span></span>

<span data-ttu-id="6fbf8-151">App-v 5.0 動的構成ファイル特定のユーザーに対してパッケージをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-151">App-V 5.0 dynamic configuration files customize a package for a specific user.</span></span> <span data-ttu-id="6fbf8-152">使用する前に、動的ユーザー構成 (.xml) ファイルまたは動的展開構成ファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-152">You must create the dynamic user configuration (.xml) file or the dynamic deployment configuration file before you can use them.</span></span> <span data-ttu-id="6fbf8-153">ファイルを作成するには、高度な手動操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-153">To create the file it requires an advanced manual operation.</span></span>

<span data-ttu-id="6fbf8-154">動的ユーザー構成ファイルを使用している場合、マニフェストファイルの拡張子について、App-v 5.0 情報は使用されません。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-154">When a dynamic user configuration file is used, none of the App-V 5.0 information for the extension in the manifest file is used.</span></span> <span data-ttu-id="6fbf8-155">つまり、動的ユーザー構成ファイルには、マニフェストファイルの App-v 5.0 に固有の拡張子と、削除や更新などの必要な変更を含める必要があることを意味します。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-155">This means that the dynamic user configuration file must include everything for the extension that is specific to App-V 5.0 in the manifest file, as well as the changes that you want to make, such as, deletions and updates.</span></span> <span data-ttu-id="6fbf8-156">カスタム構成ファイルの作成方法の詳細については、「 [app-v 5.0 管理コンソールを使用してカスタム構成ファイルを作成する方法](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-156">For more information about how to create a custom configuration file, see [How to Create a Custom Configuration File by Using the App-V 5.0 Management Console](how-to-create-a-custom-configuration-file-by-using-the-app-v-50-management-console.md).</span></span>

[<span data-ttu-id="6fbf8-157">同じコンピューター上に App-v 4.6 と App-v 5.0 クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6fbf8-157">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--50-client-on-the-same-computer.md)

## <a href="" id="bkmk-plan-for-scs"></a><span data-ttu-id="6fbf8-158">App-v 5.0 Shared Content Store (SCS) の計画</span><span class="sxs-lookup"><span data-stu-id="6fbf8-158">Planning for the App-V 5.0 Shared Content Store (SCS)</span></span>


<span data-ttu-id="6fbf8-159">App-v 5.0 shared content store モードでは、App-v 5.0 クライアントを実行しているコンピューターで仮想アプリケーションを実行できます。パッケージコンテンツは、App-v 5.0 クライアントを実行しているコンピューターに保存されません。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-159">The App-V 5.0 shared content store mode allows the computer running the App-V 5.0 client to run virtualized applications and none of the package contents is saved on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="6fbf8-160">仮想アプリケーションは、クライアントから要求された場合にのみ、ターゲットコンピューターにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-160">Virtual applications are streamed to target computers only when requested by the client.</span></span>

<span data-ttu-id="6fbf8-161">次の一覧は、App-v 5.0 shared content store を使用する場合のいくつかの利点を示しています。</span><span class="sxs-lookup"><span data-stu-id="6fbf8-161">The following list displays some of the benefits of using the App-V 5.0 shared content store:</span></span>

-   <span data-ttu-id="6fbf8-162">アプリ間およびマルチユーザーアプリケーションの競合を減らし、回帰テストの必要性を減らしました</span><span class="sxs-lookup"><span data-stu-id="6fbf8-162">Reduced app-to-app and multi-user application conflicts and hence a reduced need for regression testing</span></span>

-   <span data-ttu-id="6fbf8-163">展開リスクを軽減してアプリケーションの展開を迅速化する</span><span class="sxs-lookup"><span data-stu-id="6fbf8-163">Accelerated application deployment by reduction of deployment risk</span></span>

-   <span data-ttu-id="6fbf8-164">簡素化されたプロファイル管理</span><span class="sxs-lookup"><span data-stu-id="6fbf8-164">Simplified profile management</span></span>

[<span data-ttu-id="6fbf8-165">共有コンテンツ ストア モードの App-V 5.0 Client のインストール方法</span><span class="sxs-lookup"><span data-stu-id="6fbf8-165">How to Install the App-V 5.0 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)






## <a href="" id="other-resources-for-the-app-v-5-0-deployment-"></a><span data-ttu-id="6fbf8-166">App-v 5.0 の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="6fbf8-166">Other resources for the App-V 5.0 deployment</span></span>


[<span data-ttu-id="6fbf8-167">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="6fbf8-167">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





