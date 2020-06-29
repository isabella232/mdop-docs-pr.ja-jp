---
title: App-V 5.1 Sequencer および Client の展開
description: App-V 5.1 Sequencer および Client の展開
author: dansimp
ms.assetid: 74f32794-4c76-436f-a542-f9e95d89063d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3b78059e5005f563bb99d7e6f4b5fe0af2eae8d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814570"
---
# <span data-ttu-id="bde02-103">App-V 5.1 Sequencer および Client の展開</span><span class="sxs-lookup"><span data-stu-id="bde02-103">Deploying the App-V 5.1 Sequencer and Client</span></span>


<span data-ttu-id="bde02-104">Microsoft Application Virtualization (App-v) 5.1 Sequencer およびクライアントを使用すると、管理者は仮想化されたアプリケーションを仮想化して実行できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-104">The Microsoft Application Virtualization (App-V) 5.1 Sequencer and client enable administrators to virtualize and run virtualized applications.</span></span>

## <span data-ttu-id="bde02-105">クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="bde02-105">Deploy the client</span></span>


<span data-ttu-id="bde02-106">App-v 5.1 クライアントは、ターゲットコンピューターで仮想化されたアプリケーションを実行するコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="bde02-106">The App-V 5.1 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="bde02-107">クライアントを使うと、ユーザーはアイコンを操作したり、ファイルの種類をダブルクリックして、仮想化されたアプリケーションを開始したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-107">The client enables users to interact with icons and to double-click file types, so that they can start a virtualized application.</span></span> <span data-ttu-id="bde02-108">クライアントは、管理サーバーから仮想アプリケーションコンテンツを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="bde02-108">The client can also obtain the virtual application content from the management server.</span></span>

[<span data-ttu-id="bde02-109">APP-V Client を展開する方法</span><span class="sxs-lookup"><span data-stu-id="bde02-109">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-51gb18030.md)

[<span data-ttu-id="bde02-110">App-V 5.1 Client をアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bde02-110">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)

[<span data-ttu-id="bde02-111">同じコンピューター上に App-v 4.6 と App-v 5.1 クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="bde02-111">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

## <span data-ttu-id="bde02-112">クライアント構成の設定</span><span class="sxs-lookup"><span data-stu-id="bde02-112">Client Configuration Settings</span></span>


<span data-ttu-id="bde02-113">App-v 5.1 クライアントの構成は、レジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="bde02-113">The App-V 5.1 client stores its configuration in the registry.</span></span> <span data-ttu-id="bde02-114">レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-114">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="bde02-115">また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bde02-115">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="bde02-116">Client の構成設定について</span><span class="sxs-lookup"><span data-stu-id="bde02-116">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

## <span data-ttu-id="bde02-117">ADMX テンプレートとグループポリシーを使用してクライアントを構成する</span><span class="sxs-lookup"><span data-stu-id="bde02-117">Configure the client by using the ADMX template and Group Policy</span></span>


<span data-ttu-id="bde02-118">Microsoft ADMX テンプレートを使用して、App-v 5.1 クライアントとリモートデスクトップサービスクライアントのクライアント設定を構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-118">You can use the Microsoft ADMX template to configure the client settings for the App-V 5.1 client and the Remote Desktop Services client.</span></span> <span data-ttu-id="bde02-119">ADMX テンプレートは、既存のグループポリシーインフラストラクチャを使用して、一般的なクライアントの構成を管理します。また、このテンプレートには、App-v 5.1 クライアント構成の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bde02-119">The ADMX template manages common client configurations by using an existing Group Policy infrastructure and it includes settings for the App-V 5.1 client configuration.</span></span>

<span data-ttu-id="bde02-120">**重要** Microsoft ダウンロードセンターから App V 5.1 ADMX テンプレートを入手できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-120">**Important** You can obtain the App-V 5.1 ADMX template from the Microsoft Download Center.</span></span>

 

<span data-ttu-id="bde02-121">ADMX テンプレートをダウンロードしてインストールした後、グループポリシーの管理に使用するコンピューターで次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="bde02-121">After you download and install the ADMX template, perform the following steps on the computer that you will use to manage Group Policy.</span></span> <span data-ttu-id="bde02-122">これは通常、ドメインコントローラーです。</span><span class="sxs-lookup"><span data-stu-id="bde02-122">This is typically the Domain Controller.</span></span>

1.  <span data-ttu-id="bde02-123">次のディレクトリに、 **admx**ファイルを保存します。 **Windows \\ ポリシーの定義**</span><span class="sxs-lookup"><span data-stu-id="bde02-123">Save the **.admx** file to the following directory: **Windows \\ PolicyDefinitions**</span></span>

2.  <span data-ttu-id="bde02-124">**Adml**ファイルを次のディレクトリに保存します。 \*\*Windows \\ ポリシー定義 \ \ &lt; 言語ディレクトリ &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="bde02-124">Save the **.adml** file to the following directory: **Windows \\ PolicyDefinitions \\ &lt;Language Directory&gt;**</span></span>

<span data-ttu-id="bde02-125">上記の手順を完了したら、**グループポリシー管理**コンソールを使用して、app-v 5.1 クライアント構成設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-125">After you have completed the preceding steps, you can manage the App-V 5.1 client configuration settings with the **Group Policy Management** console.</span></span>

<span data-ttu-id="bde02-126">また、App-v 5.1 クライアントは、その構成をレジストリに保存します。</span><span class="sxs-lookup"><span data-stu-id="bde02-126">The App-V 5.1 client also stores its configuration in the registry.</span></span> <span data-ttu-id="bde02-127">レジストリ内のデータの形式を理解している場合は、クライアントに関する有用な情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-127">You can gather some useful information about the client if you understand the format of the data in the registry.</span></span> <span data-ttu-id="bde02-128">また、レジストリエントリを変更して、多くのクライアント操作を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="bde02-128">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="bde02-129">ADMX テンプレートとグループ ポリシーを使用して App-V 5.1 Client 構成を変更する方法</span><span class="sxs-lookup"><span data-stu-id="bde02-129">How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

## <span data-ttu-id="bde02-130">共有コンテンツストアモードを使用してクライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="bde02-130">Deploy the client by using the Shared Content Store mode</span></span>


<span data-ttu-id="bde02-131">アプリ-V 5.1 共有コンテンツストア (SCS) モードでは、関連付けられたパッケージデータをローカルに保存することなく、SCS アプリ5.1 で仮想化されたアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-131">The App-V 5.1 Shared Content Store (SCS) mode enables the SCS App-V 5.1 clients to run virtualized applications without saving any of the associated package data locally.</span></span> <span data-ttu-id="bde02-132">必要なすべての仮想化パッケージデータがネットワーク経由で送信されます。そのため、接続速度が速い環境でのみ、SCS モードを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bde02-132">All required virtualized package data is transmitted across the network; therefore, you should only use the SCS mode in environments with a fast connection.</span></span> <span data-ttu-id="bde02-133">App-v 5.1 クライアントのリモートデスクトップサービス (RDS) と標準バージョンの両方が、SCS モードでサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bde02-133">Both the Remote Desktop Services (RDS) and the standard version of the App-V 5.1 client are supported with SCS mode.</span></span>

<span data-ttu-id="bde02-134">**重要** App-v 5.1 クライアントが SCS モードで実行されるように構成されている場合、app-v 5.1 パッケージのストリーミング元の場所は利用可能である必要があります。それ以外の場合は、仮想化されたパッケージは失敗します。</span><span class="sxs-lookup"><span data-stu-id="bde02-134">**Important** If the App-V 5.1 client is configured to run in the SCS mode, the location where the App-V 5.1 packages are streamed from must be available, otherwise, the virtualized package will fail.</span></span> <span data-ttu-id="bde02-135">さらに、インターネット上の SCS モードで App-v 5.1 クライアントを実行しているコンピューターには、仮想化されたアプリケーションの展開をお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="bde02-135">Additionally, we do not recommend deployment of virtualized applications to computers that run the App-V 5.1 client in the SCS mode across the internet.</span></span>

 

<span data-ttu-id="bde02-136">さらに、SCS は、仮想化されたパッケージを含む物理的な場所ではありません。</span><span class="sxs-lookup"><span data-stu-id="bde02-136">Additionally, the SCS is not a physical location that contains virtualized packages.</span></span> <span data-ttu-id="bde02-137">これは、App-v 5.1 クライアントがネットワーク経由で必要な仮想化パッケージデータをストリーミングできるモードです。</span><span class="sxs-lookup"><span data-stu-id="bde02-137">It is a mode that allows the App-V 5.1 client to stream the required virtualized package data across the network.</span></span>

<span data-ttu-id="bde02-138">SCS モードは、次のシナリオで役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bde02-138">The SCS mode is helpful in the following scenarios:</span></span>

-   <span data-ttu-id="bde02-139">仮想デスクトップインフラストラクチャ (VDI) の展開</span><span class="sxs-lookup"><span data-stu-id="bde02-139">Virtual desktop infrastructure (VDI) deployments</span></span>

-   <span data-ttu-id="bde02-140">リモートデスクトップサービス (RDS) の展開</span><span class="sxs-lookup"><span data-stu-id="bde02-140">Remote desktop services (RDS) deployments</span></span>

<span data-ttu-id="bde02-141">環境で SCS を使うには、SCS モードで App-v 5.1 クライアントを実行できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bde02-141">To use SCS in your environment, you must enable the App-V 5.1 client to run in SCS mode.</span></span> <span data-ttu-id="bde02-142">この設定はインストール時に指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bde02-142">This setting should be specified during installation.</span></span> <span data-ttu-id="bde02-143">既定では、クライアントは SCS モードを使うように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="bde02-143">By default, the client is not configured to use SCS mode.</span></span> <span data-ttu-id="bde02-144">SCS の使用を計画している場合は、推奨される手順を使用してクライアントをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bde02-144">You should install the client by using the suggested procedure if you plan to use SCS.</span></span> <span data-ttu-id="bde02-145">ただし、既存の App-v 5.1 クライアントを SCS モードで実行するように構成するには、App-v 5.1 クライアントを実行しているコンピューターに次の PowerShell コマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="bde02-145">However, you can configure an existing App-V 5.1 client to run in SCS mode by entering the following PowerShell command on the computer that runs the App-V 5.1 client:</span></span>

**<span data-ttu-id="bde02-146">set-AppvClientConfiguration-SharedContentStoreMode 1</span><span class="sxs-lookup"><span data-stu-id="bde02-146">set-AppvClientConfiguration -SharedContentStoreMode 1</span></span>**

<span data-ttu-id="bde02-147">管理者が、SCS モードで App-v 5.1 クライアントを実行しているコンピューターで仮想アプリケーションを事前に読み込む場合があります。</span><span class="sxs-lookup"><span data-stu-id="bde02-147">There might be cases when the administrator pre-loads some virtual applications on the computer that runs the App-V 5.1 client in SCS mode.</span></span> <span data-ttu-id="bde02-148">これは、パッケージの追加、公開、マウントを行う PowerShell コマンドで実現できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-148">This can be accomplished with PowerShell commands to add, publish, and mount the package.</span></span> <span data-ttu-id="bde02-149">たとえば、すべてのコンピューターにパッケージが事前に読み込まれている場合、管理者は PowerShell コマンドを使用してパッケージを追加、発行、マウントすることができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-149">For example, if a package is pre-loaded on all computers, the administrator could add, publish, and mount the package by using PowerShell commands.</span></span> <span data-ttu-id="bde02-150">パッケージは、ローカルに保存されているため、ネットワーク経由でストリーミングされません。</span><span class="sxs-lookup"><span data-stu-id="bde02-150">The package would not stream across the network because it would be locally stored.</span></span>

[<span data-ttu-id="bde02-151">共有コンテンツ ストア モードの App-V 5.1 Client のインストール方法</span><span class="sxs-lookup"><span data-stu-id="bde02-151">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

## <span data-ttu-id="bde02-152">Sequencer の展開</span><span class="sxs-lookup"><span data-stu-id="bde02-152">Deploy the Sequencer</span></span>


<span data-ttu-id="bde02-153">Sequencer は、標準のアプリケーションを仮想パッケージに変換して、App-v 5.1 クライアントを実行するコンピューターに展開するために使うツールです。</span><span class="sxs-lookup"><span data-stu-id="bde02-153">The Sequencer is a tool that is used to convert standard applications into virtual packages for deployment to computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="bde02-154">Sequencer は、前の優先順位のワークフローに対する変更を最小限に抑えて、単純で予測可能な変換プロセスを実現するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="bde02-154">The Sequencer helps provide a simple and predictable conversion process with minimal changes to prior sequencing workflows.</span></span> <span data-ttu-id="bde02-155">さらに、Sequencer では、仮想化されたアプリケーションの接続を可能にするアプリケーションをより簡単に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-155">In addition, the Sequencer allows users to more easily configure applications to enable connections of virtualized applications.</span></span>

<span data-ttu-id="bde02-156">App-v 5.1 Sequencer の変更の一覧については、「[アプリ-v 5.1 につい](about-app-v-51.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bde02-156">For a list of changes in the App-V 5.1 Sequencer, see [About App-V 5.1](about-app-v-51.md).</span></span>

[<span data-ttu-id="bde02-157">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="bde02-157">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-51beta-gb18030.md)

## <a href="" id="---------app-v-5-1-client-and-sequencer-logs"></a> <span data-ttu-id="bde02-158">App-v 5.1 クライアントと Sequencer ログ</span><span class="sxs-lookup"><span data-stu-id="bde02-158">App-V 5.1 Client and Sequencer logs</span></span>


<span data-ttu-id="bde02-159">App-v 5.1 を使用しているときに、Sequencer のインストールと操作イベントのトラブルシューティングに役立つように、App-v 5.1 Sequencer ログ情報を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="bde02-159">You can use the App-V 5.1 Sequencer log information to help troubleshoot the Sequencer installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="bde02-160">Sequencer 関連のログ情報は、**イベントビューアー**で確認できます。</span><span class="sxs-lookup"><span data-stu-id="bde02-160">The Sequencer-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="bde02-161">次の行は、Sequencer に関連するイベントの特定のパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="bde02-161">The following line displays the specific path for Sequencer-related events:</span></span>

<span data-ttu-id="bde02-162">**イベントビューアー \ \ アプリケーションとサービスログ \\ Microsoft \ \ \ \ \ \ \ \ \ \ \ \ \ \ \ App V**。Sequencer 関連のイベントは、 **AppV \ _Sequencer**と共に付加されます。</span><span class="sxs-lookup"><span data-stu-id="bde02-162">**Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V**. Sequencer-related events are prepended with **AppV\_Sequencer**.</span></span> <span data-ttu-id="bde02-163">クライアント関連のイベントは、 **AppV \ _Client**と共に付加されます。</span><span class="sxs-lookup"><span data-stu-id="bde02-163">Client-related events are prepended with **AppV\_Client**.</span></span>

## <span data-ttu-id="bde02-164">Sequencer とクライアントを展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="bde02-164">Other resources for deploying the Sequencer and client</span></span>


[<span data-ttu-id="bde02-165">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="bde02-165">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="bde02-166">App-V 5.1 の計画</span><span class="sxs-lookup"><span data-stu-id="bde02-166">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)






 

 





