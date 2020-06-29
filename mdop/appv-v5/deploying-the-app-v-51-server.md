---
title: App-V 5.1 Server の展開
description: App-V 5.1 Server の展開
author: dansimp
ms.assetid: 987b61dc-00d6-49ba-8f1b-92d7b948e702
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2bcff2a3211ea3e2f666aff1d6f2ad919509aa3a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814563"
---
# <span data-ttu-id="667b5-103">App-V 5.1 Server の展開</span><span class="sxs-lookup"><span data-stu-id="667b5-103">Deploying the App-V 5.1 Server</span></span>

<span data-ttu-id="667b5-104">このトピックで説明するさまざまな展開構成を使用して、Microsoft Application Virtualization (App-v) 5.1 サーバー機能をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="667b5-104">You can install the Microsoft Application Virtualization (App-V) 5.1 server features by using different deployment configurations, which described in this topic.</span></span> <span data-ttu-id="667b5-105">サーバー機能をインストールする前に、「 [app-v 5.1 のセキュリティに関する考慮事項](app-v-51-security-considerations.md)」のサーバーセクションを確認してください。</span><span class="sxs-lookup"><span data-stu-id="667b5-105">Before you install the server features, review the server section of [App-V 5.1 Security Considerations](app-v-51-security-considerations.md).</span></span>

<span data-ttu-id="667b5-106">App-v Server の展開について詳しくは、「 [app-v 5.1 につい](about-app-v-51.md#bkmk-migrate-to-51)て」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="667b5-106">For information about deploying the App-V Server, see [About App-V 5.1](about-app-v-51.md#bkmk-migrate-to-51).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="667b5-107">App-v 5.1 サーバーをインストールして構成する前に、各コンポーネントをホストするポートを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="667b5-107">Before you install and configure the App-V 5.1 servers, you must specify a port where each component will be hosted.</span></span> <span data-ttu-id="667b5-108">また、関連するファイアウォール規則を追加して、着信要求に対して指定されたポートへのアクセスを許可する必要もあります。</span><span class="sxs-lookup"><span data-stu-id="667b5-108">You must also add the associated firewall rules to allow incoming requests to access the specified ports.</span></span> <span data-ttu-id="667b5-109">インストーラーは、ファイアウォールの設定を変更しません。</span><span class="sxs-lookup"><span data-stu-id="667b5-109">The installer does not modify firewall settings.</span></span>

## <a href="" id="---------app-v-5-1-server-overview"></a> <span data-ttu-id="667b5-110">App-v 5.1 サーバーの概要</span><span class="sxs-lookup"><span data-stu-id="667b5-110">App-V 5.1 Server overview</span></span>

<span data-ttu-id="667b5-111">App-v 5.1 サーバーは、5つのコンポーネントで構成されています。</span><span class="sxs-lookup"><span data-stu-id="667b5-111">The App-V 5.1 Server is made up of five components.</span></span> <span data-ttu-id="667b5-112">各コンポーネントは、App-v 5.1 環境内で異なる目的を果たします。</span><span class="sxs-lookup"><span data-stu-id="667b5-112">Each component serves a different purpose within the App-V 5.1 environment.</span></span> <span data-ttu-id="667b5-113">ここでは、5つの各コンポーネントについて簡単に説明します。</span><span class="sxs-lookup"><span data-stu-id="667b5-113">Each of the five components is briefly described here:</span></span>

- <span data-ttu-id="667b5-114">管理サーバー– App-v 5.1 インフラストラクチャの全体的な管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="667b5-114">Management Server – provides overall management functionality for the App-V 5.1 infrastructure.</span></span>
- <span data-ttu-id="667b5-115">管理データベース– App-v 5.1 管理のデータベース展開が容易になります。</span><span class="sxs-lookup"><span data-stu-id="667b5-115">Management Database – facilitates database predeployments for App-V 5.1 management.</span></span>
- <span data-ttu-id="667b5-116">公開サーバー–仮想アプリケーションのホスティング機能とストリーミング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="667b5-116">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>
- <span data-ttu-id="667b5-117">レポートサーバー– App-v 5.1 reporting services を提供します。</span><span class="sxs-lookup"><span data-stu-id="667b5-117">Reporting Server – provides App-V 5.1 reporting services.</span></span>
- <span data-ttu-id="667b5-118">レポートデータベース– App-v 5.1 レポートのデータベース展開を容易にします。</span><span class="sxs-lookup"><span data-stu-id="667b5-118">Reporting Database – facilitates database predeployments for App-V 5.1 reporting.</span></span>

## <a href="" id="---------app-v-5-1-stand-alone-deployment"></a> <span data-ttu-id="667b5-119">App-v 5.1 単体展開</span><span class="sxs-lookup"><span data-stu-id="667b5-119">App-V 5.1 stand-alone deployment</span></span>

<span data-ttu-id="667b5-120">アプリ-V 5.1 単体展開では、小規模の展開またはテスト環境に適したトポロジが提供されます。</span><span class="sxs-lookup"><span data-stu-id="667b5-120">The App-V 5.1 standalone deployment provides a good topology for a small deployment or a test environment.</span></span> <span data-ttu-id="667b5-121">この種類の実装を使うと、すべてのサーバーコンポーネントが1台のコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="667b5-121">When you use this type of implementation, all server components are deployed to a single computer.</span></span> <span data-ttu-id="667b5-122">サービスと関連データベースは、app-v 5.1 コンポーネントを実行しているコンピューター上のリソースに対して競合します。</span><span class="sxs-lookup"><span data-stu-id="667b5-122">The services and associated databases will compete for the resources on the computer that runs the App-V 5.1 components.</span></span> <span data-ttu-id="667b5-123">そのため、このトポロジは大規模な展開には使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="667b5-123">Therefore, you should not use this topology for larger deployments.</span></span>

[<span data-ttu-id="667b5-124">App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="667b5-124">How to Deploy the App-V 5.1 Server</span></span>](how-to-deploy-the-app-v-51-server.md)

[<span data-ttu-id="667b5-125">スクリプトを使用して App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="667b5-125">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

## <a href="" id="---------app-v-5-1-server-distributed-deployment"></a> <span data-ttu-id="667b5-126">App-v 5.1 Server 分散展開</span><span class="sxs-lookup"><span data-stu-id="667b5-126">App-V 5.1 Server distributed deployment</span></span>

<span data-ttu-id="667b5-127">分散展開トポロジは、大規模な App-v 5.1 クライアントベースをサポートし、環境をより簡単に管理およびスケーリングできるようにします。</span><span class="sxs-lookup"><span data-stu-id="667b5-127">The distributed deployment topology can support a large App-V 5.1 client base and it allows you to more easily manage and scale your environment.</span></span> <span data-ttu-id="667b5-128">この種類の展開を使用する場合、組織の構造と要件に基づいて、App-v 5.1 サーバーコンポーネントが複数のコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="667b5-128">When you use this type of deployment, the App-V 5.1 Server components are deployed across multiple computers, based on the structure and requirements of the organization.</span></span>

[<span data-ttu-id="667b5-129">管理とレポート サービスとは別のコンピューターに管理とレポートのデータベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="667b5-129">How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services</span></span>](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)

[<span data-ttu-id="667b5-130">スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="667b5-130">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

[<span data-ttu-id="667b5-131">スクリプトを使用して App-V 5.1 Server を展開する方法</span><span class="sxs-lookup"><span data-stu-id="667b5-131">How to Deploy the App-V 5.1 Server Using a Script</span></span>](how-to-deploy-the-app-v-51-server-using-a-script.md)

[<span data-ttu-id="667b5-132">リモート コンピューターに公開サーバーをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="667b5-132">How to Install the Publishing Server on a Remote Computer</span></span>](how-to-install-the-publishing-server-on-a-remote-computer51.md)

[<span data-ttu-id="667b5-133">スタンドアロン コンピューターに管理サーバーをインストールしてデータベースに接続する方法</span><span class="sxs-lookup"><span data-stu-id="667b5-133">How to install the Management Server on a Standalone Computer and Connect it to the Database</span></span>](how-to-install-the-management-server-on-a-standalone-computer-and-connect-it-to-the-database51.md)

## <span data-ttu-id="667b5-134">エンタープライズソフトウェア配布 (ESD) ソリューションと App-v 5.1 を使用する</span><span class="sxs-lookup"><span data-stu-id="667b5-134">Using an Enterprise Software Distribution (ESD) solution and App-V 5.1</span></span>

<span data-ttu-id="667b5-135">また、アプリ-V 5.1 を展開せずに ESD を使って、App-v 5.1 のクライアントとパッケージを展開することもできます。</span><span class="sxs-lookup"><span data-stu-id="667b5-135">You can also deploy the App-V 5.1 clients and packages by using an ESD without having to deploy App-V 5.1.</span></span> <span data-ttu-id="667b5-136">統合のためのすべての機能は、使用する ESD によって異なります。</span><span class="sxs-lookup"><span data-stu-id="667b5-136">The full capabilities for integration will vary depending on the ESD that you use.</span></span>

> [!NOTE]
> <span data-ttu-id="667b5-137">アプリ-V 5.1 レポートサーバーおよびレポートデータベースは、ESD と共に展開して、App-v 5.1 クライアントからレポートデータを収集することができます。</span><span class="sxs-lookup"><span data-stu-id="667b5-137">The App-V 5.1 reporting server and reporting database can still be deployed alongside the ESD to collect the reporting data from the App-V 5.1 clients.</span></span> <span data-ttu-id="667b5-138">ただし、他の3つのサーバーコンポーネントは、ESD 機能と競合するため、展開しないでください。</span><span class="sxs-lookup"><span data-stu-id="667b5-138">However, the other three server components should not be deployed, because they will conflict with the ESD functionality.</span></span>

[<span data-ttu-id="667b5-139">電子ソフトウェア配布 (ESD) を使用した APP-V 5.1 パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="667b5-139">Deploying App-V 5.1 Packages by Using Electronic Software Distribution (ESD)</span></span>](deploying-app-v-51-packages-by-using-electronic-software-distribution--esd-.md)

## <a href="" id="---------app-v-5-1-server-logs"></a> <span data-ttu-id="667b5-140">App-v 5.1 サーバーログ</span><span class="sxs-lookup"><span data-stu-id="667b5-140">App-V 5.1 Server logs</span></span>

<span data-ttu-id="667b5-141">App-v 5.1 サーバーログ情報を使用して、App-v 5.1 を使用しているときにサーバーのインストールと操作イベントのトラブルシューティングを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="667b5-141">You can use App-V 5.1 server log information to help troubleshoot the server installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="667b5-142">サーバー関連のログ情報は、**イベントビューアー**で確認できます。</span><span class="sxs-lookup"><span data-stu-id="667b5-142">The server-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="667b5-143">次の行は、サーバーに関連するイベントの特定のパスを示しています。</span><span class="sxs-lookup"><span data-stu-id="667b5-143">The following line displays the specific path for Server-related events:</span></span>

**<span data-ttu-id="667b5-144">イベントビューアー \ \ アプリケーションとサービスログ \\ Microsoft \ \ App V</span><span class="sxs-lookup"><span data-stu-id="667b5-144">Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V</span></span>**

<span data-ttu-id="667b5-145">関連する設定ログは、次のディレクトリに保存されます。</span><span class="sxs-lookup"><span data-stu-id="667b5-145">Associated setup logs are saved in the following directory:</span></span>

**<span data-ttu-id="667b5-146">テンポラリ</span><span class="sxs-lookup"><span data-stu-id="667b5-146">%temp%</span></span>**

<span data-ttu-id="667b5-147">App-v 5.0 SP3 では、一部のログは統合されて移動されました。</span><span class="sxs-lookup"><span data-stu-id="667b5-147">In App-V 5.0 SP3, some logs were consolidated and moved.</span></span> <span data-ttu-id="667b5-148">「 [App-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-event-logs-moved)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="667b5-148">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

## <a href="" id="---------app-v-5-1-reporting"></a> <span data-ttu-id="667b5-149">App-v 5.1 レポート</span><span class="sxs-lookup"><span data-stu-id="667b5-149">App-V 5.1 reporting</span></span>

<span data-ttu-id="667b5-150">App-v 5.1 レポートを使用すると、App-v 5.1 クライアントはデータを収集し、そのデータを中央リポジトリに保存するように返信することができます。</span><span class="sxs-lookup"><span data-stu-id="667b5-150">App-V 5.1 reporting allows App-V 5.1 clients to collect data and then send it back to be stored in a central repository.</span></span> <span data-ttu-id="667b5-151">この情報を使用して、組織内の仮想アプリケーションの使用状況をより適切に表示できます。</span><span class="sxs-lookup"><span data-stu-id="667b5-151">You can use this information to get a better view of the virtual application usage within your organization.</span></span> <span data-ttu-id="667b5-152">次の一覧は、App-v 5.1 クライアントで収集されるいくつかの種類の情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="667b5-152">The following list displays some of the types of information the App-V 5.1 client collects:</span></span>

- <span data-ttu-id="667b5-153">App-v 5.1 クライアントを実行しているコンピューターに関する情報。</span><span class="sxs-lookup"><span data-stu-id="667b5-153">Information about the computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="667b5-154">App-v 5.1 クライアントを実行する特定のコンピューター上の仮想化されたパッケージに関する情報。</span><span class="sxs-lookup"><span data-stu-id="667b5-154">Information about virtualized packages on a specific computer that runs the App-V 5.1 client.</span></span>
- <span data-ttu-id="667b5-155">特定のユーザーに対して開いているパッケージとシャットダウンする情報</span><span class="sxs-lookup"><span data-stu-id="667b5-155">Information about package open and shutdown for a specific user.</span></span>

<span data-ttu-id="667b5-156">レポートの情報は、レポートサーバーデータベースに正常に送信されるまで保持されます。</span><span class="sxs-lookup"><span data-stu-id="667b5-156">The reporting information will be maintained until it is successfully sent to the reporting server database.</span></span> <span data-ttu-id="667b5-157">データがデータベースに含まれたら、Microsoft SQL Server Reporting Services を使用して、必要なレポートを生成することができます。</span><span class="sxs-lookup"><span data-stu-id="667b5-157">After the data is in the database, you can use Microsoft SQL Server Reporting Services to generate any necessary reports.</span></span>

<span data-ttu-id="667b5-158">レポート情報を取得する場合は、Microsoft SQL Server Reporting Services (SSRS) を使用する必要があります。これは Microsoft SQL で利用できます。</span><span class="sxs-lookup"><span data-stu-id="667b5-158">If you want to retrieve report information, you must use Microsoft SQL Server Reporting Services (SSRS) which is available with Microsoft SQL.</span></span> <span data-ttu-id="667b5-159">SSRS は、App-v 5.1 レポートサーバーをインストールするときにはインストールされず、関連付けられたレポートを生成するために個別に展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="667b5-159">SSRS is not installed when you install the App-V 5.1 reporting server and it must be deployed separately to generate the associated reports.</span></span>

<span data-ttu-id="667b5-160">[App-v 5.1 レポート](about-app-v-51-reporting.md)の詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="667b5-160">Use the following link for more information [About App-V 5.1 Reporting](about-app-v-51-reporting.md).</span></span>

[<span data-ttu-id="667b5-161">PowerShell を使用して App-V 5.1 Client のレポート機能を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="667b5-161">How to Enable Reporting on the App-V 5.1 Client by Using PowerShell</span></span>](how-to-enable-reporting-on-the-app-v-51-client-by-using-powershell.md)

## <span data-ttu-id="667b5-162">App-v server のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="667b5-162">Other resources for the App-V server</span></span>

[<span data-ttu-id="667b5-163">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="667b5-163">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)
