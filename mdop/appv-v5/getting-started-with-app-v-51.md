---
title: App-V 5.1 をお使いになる前に
description: App-V 5.1 をお使いになる前に
author: dansimp
ms.assetid: 49a20e1f-0566-4e53-a417-1521393fc974
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff10f12bc672a24f2837f50bfb1f0033ede3e46f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814547"
---
# <span data-ttu-id="064e9-103">App-V 5.1 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="064e9-103">Getting Started with App-V 5.1</span></span>


<span data-ttu-id="064e9-104">Microsoft Application Virtualization (App-v) 5.1 を使用すると、管理者は、必要に応じてリアルタイムでサービスとしてアプリケーションを展開、更新、およびサポートできます。</span><span class="sxs-lookup"><span data-stu-id="064e9-104">Microsoft Application Virtualization (App-V) 5.1 enables administrators to deploy, update, and support applications as services in real time, on an as-needed basis.</span></span> <span data-ttu-id="064e9-105">個々のアプリケーションは、ローカルにインストールされた製品から一元的に管理されたサービスに変換され、コンピューターの事前構成やオペレーティングシステムの設定の変更を必要とせずに、どこでも利用できます。</span><span class="sxs-lookup"><span data-stu-id="064e9-105">Individual applications are transformed from locally installed products into centrally managed services and are available wherever you need, without the need to preconfigure computers or to change operating system settings.</span></span>

<span data-ttu-id="064e9-106">App-v は、次の要素で構成されています。</span><span class="sxs-lookup"><span data-stu-id="064e9-106">App-V consists of the following elements:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="064e9-107">要素</span><span class="sxs-lookup"><span data-stu-id="064e9-107">Element</span></span></th>
<th align="left"><span data-ttu-id="064e9-108">説明</span><span class="sxs-lookup"><span data-stu-id="064e9-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="064e9-109">App-v Management Server</span><span class="sxs-lookup"><span data-stu-id="064e9-109">App-V Management Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="064e9-110">App-v インフラストラクチャを管理するための1つの場所を提供します。これにより、仮想アプリケーションは、App-v デスクトップクライアントとリモートデスクトップサービス (旧ターミナルサービス) クライアントの両方に配信されます。</span><span class="sxs-lookup"><span data-stu-id="064e9-110">Provides a central location for managing the App-V infrastructure, which delivers virtual applications to both the App-V Desktop Client and the Remote Desktop Services (formerly Terminal Services) Client.</span></span></p></li>
<li><p><span data-ttu-id="064e9-111">データストアには Microsoft SQL Server®を使います。ここでは、1つ以上の App-v 管理サーバーが1つの SQL Server データストアを共有できます。</span><span class="sxs-lookup"><span data-stu-id="064e9-111">Uses Microsoft SQL Server® for its data store, where one or more App-V Management servers can share a single SQL Server data store.</span></span></p></li>
<li><p><span data-ttu-id="064e9-112">要求を認証し、セキュリティ、メータリング、監視、データ収集を提供します。</span><span class="sxs-lookup"><span data-stu-id="064e9-112">Authenticates requests and provides security, metering, monitoring, and data gathering.</span></span> <span data-ttu-id="064e9-113">サーバーは Active Directory とサポートツールを使って、ユーザーとアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="064e9-113">The server uses Active Directory and supporting tools to manage users and applications.</span></span></p></li>
<li><p><span data-ttu-id="064e9-114">任意のコンピューターから App-v インフラストラクチャを構成できる管理サイトがあります。</span><span class="sxs-lookup"><span data-stu-id="064e9-114">Has a management site that lets you configure the App-V infrastructure from any computer.</span></span> <span data-ttu-id="064e9-115">アプリケーションの追加と削除、ショートカットの操作、ユーザーとグループへのアクセス許可の割り当て、接続グループの作成を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="064e9-115">You can add and remove applications, manipulate shortcuts, assign access permissions to users and groups, and create connection groups.</span></span></p></li>
<li><p><span data-ttu-id="064e9-116">App-v Web 管理コンソールと SQL Server データストアの間の通信を有効にします。</span><span class="sxs-lookup"><span data-stu-id="064e9-116">Enables communication between the App-V Web Management Console and the SQL Server data store.</span></span> <span data-ttu-id="064e9-117">これらのコンポーネントは、必要なシステムアーキテクチャに応じて、単一のサーバーコンピューターまたは1つ以上の別のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="064e9-117">These components can all be installed on a single server computer, or on one or more separate computers, depending on the required system architecture.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="064e9-118">App-v 発行サーバー</span><span class="sxs-lookup"><span data-stu-id="064e9-118">App-V Publishing Server</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="064e9-119">特定のユーザーに対応するアプリケーションを指定して、App-v クライアントを提供します。</span><span class="sxs-lookup"><span data-stu-id="064e9-119">Provides App-V Clients with entitled applications for the specific user</span></span></p></li>
<li><p><span data-ttu-id="064e9-120">ストリーミング用の仮想アプリケーションパッケージをホストします。</span><span class="sxs-lookup"><span data-stu-id="064e9-120">Hosts the virtual application package for streaming.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="064e9-121">App-v デスクトップクライアント</span><span class="sxs-lookup"><span data-stu-id="064e9-121">App-V Desktop Client</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="064e9-122">仮想アプリケーションを取得します</span><span class="sxs-lookup"><span data-stu-id="064e9-122">Retrieves virtual applications</span></span></p></li>
<li><p><span data-ttu-id="064e9-123">クライアントのアプリケーションを公開します</span><span class="sxs-lookup"><span data-stu-id="064e9-123">Publishes the applications on the clients</span></span></p></li>
<li><p><span data-ttu-id="064e9-124">Windows エンドポイントで実行時に仮想環境を自動的に設定および管理します。</span><span class="sxs-lookup"><span data-stu-id="064e9-124">Automatically sets up and manages virtual environments at runtime on Windows endpoints.</span></span></p></li>
<li><p><span data-ttu-id="064e9-125">ユーザー固有の仮想アプリケーション設定 (レジストリやファイルの変更など) を各ユーザー&#39;s プロファイルに保存します。</span><span class="sxs-lookup"><span data-stu-id="064e9-125">Stores user-specific virtual application settings, such as registry and file changes, in each user&#39;s profile.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="064e9-126">App-v リモートデスクトップサービス (RDS) クライアント</span><span class="sxs-lookup"><span data-stu-id="064e9-126">App-V Remote Desktop Services (RDS) Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="064e9-127">リモートデスクトップセッションホストサーバーで、共有デスクトップセッションのアプリ V デスクトップクライアントの機能を使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="064e9-127">Enables Remote Desktop Session Host servers to use the capabilities of the App-V Desktop Client for shared desktop sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="064e9-128">App-v Sequencer</span><span class="sxs-lookup"><span data-stu-id="064e9-128">App-V Sequencer</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="064e9-129">は、従来のアプリケーションを仮想アプリケーションに変換するために使用するウィザードベースのツールです。</span><span class="sxs-lookup"><span data-stu-id="064e9-129">Is a wizard-based tool that you use to transform traditional applications into virtual applications.</span></span></p></li>
<li><p><span data-ttu-id="064e9-130">"パッケージ" というアプリケーションを生成します。これは次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="064e9-130">Produces the application “package,” which consists of:</span></span></p>
<ol>
<li><p><span data-ttu-id="064e9-131">シーケンスアプリケーション (APPV) ファイル</span><span class="sxs-lookup"><span data-stu-id="064e9-131">a sequenced application (APPV) file</span></span></p></li>
<li><p><span data-ttu-id="064e9-132">スタンドアロン操作用に構成されたクライアントに展開できる Windows インストーラーファイル (MSI)</span><span class="sxs-lookup"><span data-stu-id="064e9-132">a Windows Installer file (MSI) that can be deployed to clients configured for stand-alone operation</span></span></p></li>
<li><p><span data-ttu-id="064e9-133">Report.XML、PackageName_DeploymentConfig.XML、PackageName_UserConfig.XML などのいくつかの XML ファイル。</span><span class="sxs-lookup"><span data-stu-id="064e9-133">Several XML files including Report.XML, PackageName_DeploymentConfig.XML, and PackageName_UserConfig.XML.</span></span> <span data-ttu-id="064e9-134">UserConfig と DeploymentConfig の XML ファイルを使って、パッケージの既定の動作に対するカスタムの変更を構成します。</span><span class="sxs-lookup"><span data-stu-id="064e9-134">The UserConfig and DeploymentConfig XML files are used to configure custom changes to the default behavior of the package.</span></span></p></li>
</ol></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="064e9-135">これらの要素の詳細については、「 [app-v 5.1 の高レベルアーキテクチャ](high-level-architecture-for-app-v-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="064e9-135">For more information about these elements, see [High Level Architecture for App-V 5.1](high-level-architecture-for-app-v-51.md).</span></span>

<span data-ttu-id="064e9-136">この製品を初めて使用する場合は、このドキュメントをよく読むことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="064e9-136">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="064e9-137">運用環境に展開する前に、テストネットワーク環境で展開計画を検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="064e9-137">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="064e9-138">関連するテクノロジのトレーニングの受講もご検討ください。</span><span class="sxs-lookup"><span data-stu-id="064e9-138">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="064e9-139">Microsoft のトレーニングの機会の詳細については、「Microsoft トレーニングの概要」を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="064e9-139">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="064e9-140">**注** この管理者ガイドのダウンロード可能なバージョンは利用できません。</span><span class="sxs-lookup"><span data-stu-id="064e9-140">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="064e9-141">ただし、TechNet ライブラリの特別モードでは、記事の選択、コレクションへのグループ化、またはのファイルへのエクスポートを行うことができ <https://go.microsoft.com/fwlink/?LinkId=272491> https://go.microsoft.com/fwlink/?LinkId=272491) ます。</span><span class="sxs-lookup"><span data-stu-id="064e9-141">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272491> (https://go.microsoft.com/fwlink/?LinkId=272491).</span></span>

 

<span data-ttu-id="064e9-142">このセクションでは、展開計画を開始する前に、製品についての基本的な理解を得るために5.1、app-v 5.1 に関する詳細情報を提供しています。</span><span class="sxs-lookup"><span data-stu-id="064e9-142">This section of the App-V 5.1 Administrator’s Guide includes high-level information about App-V 5.1 to provide you with a basic understanding of the product before you begin the deployment planning.</span></span>

## <span data-ttu-id="064e9-143">App-v 5.1 の概要</span><span class="sxs-lookup"><span data-stu-id="064e9-143">Getting started with App-V 5.1</span></span>


-   [<span data-ttu-id="064e9-144">App-V 5.1 について</span><span class="sxs-lookup"><span data-stu-id="064e9-144">About App-V 5.1</span></span>](about-app-v-51.md)

    <span data-ttu-id="064e9-145">App-v 5.1 の概要と、組織での使用方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="064e9-145">Provides a high-level overview of App-V 5.1 and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="064e9-146">App-V 5.1 の評価</span><span class="sxs-lookup"><span data-stu-id="064e9-146">Evaluating App-V 5.1</span></span>](evaluating-app-v-51.md)

    <span data-ttu-id="064e9-147">組織で使用するために、どのように App-v 5.1 を最適に評価できるかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="064e9-147">Provides information about how you can best evaluate App-V 5.1 for use in your organization.</span></span>

-   [<span data-ttu-id="064e9-148">App-V 5.1 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="064e9-148">High Level Architecture for App-V 5.1</span></span>](high-level-architecture-for-app-v-51.md)

    <span data-ttu-id="064e9-149">App-v 5.1 の機能と連携のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="064e9-149">Provides a description of the App-V 5.1 features and how they work together.</span></span>

-   [<span data-ttu-id="064e9-150">App-V 5.1 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="064e9-150">Accessibility for App-V 5.1</span></span>](accessibility-for-app-v-51.md)

    <span data-ttu-id="064e9-151">障碍のある方がこの製品とそれに対応するドキュメントのアクセシビリティを高めるための機能とサービスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="064e9-151">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="064e9-152">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="064e9-152">Other resources for this product</span></span>


-   [<span data-ttu-id="064e9-153">Microsoft Application Virtualization 5.1 管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="064e9-153">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="064e9-154">App-V 5.1 の計画</span><span class="sxs-lookup"><span data-stu-id="064e9-154">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)

-   [<span data-ttu-id="064e9-155">APP-V 5.1 の展開</span><span class="sxs-lookup"><span data-stu-id="064e9-155">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

-   [<span data-ttu-id="064e9-156">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="064e9-156">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

-   [<span data-ttu-id="064e9-157">App-V 5.1 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="064e9-157">Troubleshooting App-V 5.1</span></span>](troubleshooting-app-v-51.md)

-   [<span data-ttu-id="064e9-158">App-V 5.1 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="064e9-158">Technical Reference for App-V 5.1</span></span>](technical-reference-for-app-v-51.md)






 

 





