---
title: Application Virtualization サーバー ベースのシナリオ概要
description: Application Virtualization サーバー ベースのシナリオ概要
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822094"
---
# <span data-ttu-id="f2939-103">Application Virtualization サーバー ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="f2939-103">Application Virtualization Server-Based Scenario Overview</span></span>


<span data-ttu-id="f2939-104">Microsoft Application Virtualization 環境でサーバーベースの展開シナリオを使用する予定がある場合は、 *Application Virtualization Management server*と*Application virtualization ストリーミングサーバー*の違いについて理解しておくことが重要です。</span><span class="sxs-lookup"><span data-stu-id="f2939-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the differences between the *Application Virtualization Management Server* and the *Application Virtualization Streaming Server*.</span></span> <span data-ttu-id="f2939-105">このトピックでは、これらの違いについて説明します。パッケージ配信方法、伝送プロトコル、および展開を進めるために考慮する必要がある外部コンポーネントについても説明します。</span><span class="sxs-lookup"><span data-stu-id="f2939-105">This topic describes those differences and also provides information about package delivery methods, transmission protocols, and external components that you will need to consider as you proceed with your deployment.</span></span>

## <span data-ttu-id="f2939-106">Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="f2939-106">Application Virtualization Management Server</span></span>


<span data-ttu-id="f2939-107">Application Virtualization Management Server は、パブリッシング機能とストリーミング機能の両方を実行します。</span><span class="sxs-lookup"><span data-stu-id="f2939-107">The Application Virtualization Management Server performs both the publishing function and the streaming function.</span></span> <span data-ttu-id="f2939-108">サーバーは、承認されたユーザーのために、アプリケーションアイコン、ショートカット、ファイルの種類の関連付けを App-v クライアントに公開します。</span><span class="sxs-lookup"><span data-stu-id="f2939-108">The server publishes application icons, shortcuts, and file type associations to the App-V clients for authorized users.</span></span> <span data-ttu-id="f2939-109">ユーザー要求が受信された場合、ユーザーは、RTSP または RTSPS プロトコルを使用する認証済みユーザーにデータを必要とするサーバーストリームを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="f2939-109">When user requests for applications are received the server streams that data on-demand to authorized users using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="f2939-110">このサーバーを使用するほとんどの構成では、1つ以上の管理サーバーが、構成およびパッケージ情報用の共通データストアを共有しています。</span><span class="sxs-lookup"><span data-stu-id="f2939-110">In most configurations using this server, one or more Management Servers share a common data store for configuration and package information.</span></span>

<span data-ttu-id="f2939-111">Application Virtualization Management サーバーは Active Directory グループを使って、ユーザーの承認を管理します。</span><span class="sxs-lookup"><span data-stu-id="f2939-111">The Application Virtualization Management Servers use Active Directory groups to manage user authorization.</span></span> <span data-ttu-id="f2939-112">Active Directory ドメインサービスに加えて、これらのサーバーにはデータベースとデータストアを管理するための SQL Server がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="f2939-112">In addition to Active Directory Domain Services, these servers have SQL Server installed to manage the database and data store.</span></span> <span data-ttu-id="f2939-113">管理サーバーは、Microsoft 管理コンソールへのスナップインである Application Virtualization 管理コンソールを通じて制御されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-113">The Management Server is controlled through the Application Virtualization Management Console, a snap-in to the Microsoft Management Console.</span></span>

<span data-ttu-id="f2939-114">アプリケーションの仮想化管理サーバーでは、アプリケーションがエンドユーザーのオンデマンドでストリーミングされるため、これらのサーバーは、信頼性の高い高帯域幅の Lan を備えたシステム構成に最適です。</span><span class="sxs-lookup"><span data-stu-id="f2939-114">Because the Application Virtualization Management Servers stream applications to end-users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span>

## <span data-ttu-id="f2939-115">Application Virtualization ストリーミングサーバー</span><span class="sxs-lookup"><span data-stu-id="f2939-115">Application Virtualization Streaming Server</span></span>


<span data-ttu-id="f2939-116">Application Virtualization Streaming Server では、管理サーバーによって提供されるのと同じストリーミングとパッケージのアップグレード機能が提供されますが、Active Directory または SQL Server の要件はありません。</span><span class="sxs-lookup"><span data-stu-id="f2939-116">The Application Virtualization Streaming Server delivers the same streaming and package upgrade capabilities provided by the Management Server, but without its Active Directory or SQL Server requirements.</span></span> <span data-ttu-id="f2939-117">ただし、ストリーミングサーバーには公開サービスがなく、ライセンス機能もメータリング機能もありません。</span><span class="sxs-lookup"><span data-stu-id="f2939-117">However, the Streaming Server does not have a publishing service, nor does it have licensing or metering capabilities.</span></span> <span data-ttu-id="f2939-118">別個の App-v 管理サーバーの発行サービスは、app-v ストリーミングサーバーと組み合わせて使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-118">The publishing service of a separate App-V Management Server is used in conjunction with the App-V Streaming Server.</span></span> <span data-ttu-id="f2939-119">App-v ストリーミングサーバーは、従来のサーバー構成のストリーミング機能を使用して、複数の場所でアプリケーションの仮想化を使う必要がある企業のニーズに対応していますが、すべての場所で App-v 管理サーバーをサポートするインフラストラクチャが含まれていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2939-119">The App-V Streaming Server addresses the needs of businesses that want to use Application Virtualization in multiple locations with the streaming capabilities of the classic server configuration but might not have the infrastructure to support App-V Management Servers in every location.</span></span>

<span data-ttu-id="f2939-120">Application Virtualization Streaming Server は、既存の電子ソフトウェア配布システム (ESD) がある環境でも使うことができます。</span><span class="sxs-lookup"><span data-stu-id="f2939-120">The Application Virtualization Streaming Server can also be used in environments with an existing electronic software distribution system (ESD).</span></span> <span data-ttu-id="f2939-121">ESD を使ってストリーミングアプリケーションを管理します。</span><span class="sxs-lookup"><span data-stu-id="f2939-121">You use the ESD to manage streaming applications.</span></span> <span data-ttu-id="f2939-122">Application Virtualization Management Server とは異なり、ストリーミングサーバーでは、SQL や管理コンソールは使用されません。</span><span class="sxs-lookup"><span data-stu-id="f2939-122">Unlike the Application Virtualization Management Server, the Streaming Server does not use SQL or a management console.</span></span> <span data-ttu-id="f2939-123">これらのサーバーは、アクセス制御リスト (Acl) を使用してユーザーの承認を付与します。</span><span class="sxs-lookup"><span data-stu-id="f2939-123">These servers use access control lists (ACLs) to grant user authorization.</span></span>

## <span data-ttu-id="f2939-124">パッケージ配信方法</span><span class="sxs-lookup"><span data-stu-id="f2939-124">Package Delivery Methods</span></span>


<span data-ttu-id="f2939-125">Application Virtualization サーバーを発行配信方法として使用する予定がある場合は、次のパッケージ配信方法がシナリオで採用されているかどうかを判断する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2939-125">If you plan to use an Application Virtualization Server as the publishing delivery method, you need to determine which of the following package delivery methods your scenario employs:</span></span>

-   *<span data-ttu-id="f2939-126">動的なパッケージの配信</span><span class="sxs-lookup"><span data-stu-id="f2939-126">Dynamic package delivery</span></span>*

-   *<span data-ttu-id="f2939-127">ファイルパッケージ配信からのロード</span><span class="sxs-lookup"><span data-stu-id="f2939-127">Load from file package delivery</span></span>*

### <span data-ttu-id="f2939-128">動的なパッケージの配信</span><span class="sxs-lookup"><span data-stu-id="f2939-128">Dynamic Package Delivery</span></span>

<span data-ttu-id="f2939-129">動的なパッケージ配信中に、サーバー (Application Virtualization Management Server、Application Virtualization ストリーミングサーバー、または IIS サーバー) は、オンデマンド展開によって、仮想化されたアプリケーションをエンドユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="f2939-129">During dynamic package delivery, the server (Application Virtualization Management Server, Application Virtualization Streaming Server, or IIS server) delivers the virtualized applications to the end users through on-demand deployment.</span></span> <span data-ttu-id="f2939-130">サーバーは、ユーザーが最初にアプリケーションを起動しようとすると (オンデマンドで)、仮想化されたアプリケーションとパッケージをクライアントコンピューターに配信します。</span><span class="sxs-lookup"><span data-stu-id="f2939-130">The server delivers the virtualized applications and packages to a client computer only when a user first attempts to launch an application (on demand).</span></span> <span data-ttu-id="f2939-131">サーバーは、アプリケーションを起動するために必要なブロックのみをストリームします (プライマリ機能ブロック)。</span><span class="sxs-lookup"><span data-stu-id="f2939-131">The server streams only the blocks needed to start the application (primary feature block).</span></span> <span data-ttu-id="f2939-132">プライマリ機能ブロックがクライアントに配信されると、アプリケーションが実行されます。クライアントは、プライマリ機能ブロックに含まれていないアプリケーションの一部にアクセスする必要がない限り、完全なアプリケーション (段階的な展開) を受け取ることはありません。</span><span class="sxs-lookup"><span data-stu-id="f2939-132">After the primary feature block is delivered to the client, the application runs; the client does not receive the complete application (incremental deployment) unless the client needs access to a part of the application that is not included in the primary feature block.</span></span> <span data-ttu-id="f2939-133">この場合、クライアントは、シーケンス外の要求を実行し、セカンダリ機能ブロックはクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="f2939-133">When this occurs, the client performs an out-of-sequence request and the secondary feature block is streamed to the client.</span></span> <span data-ttu-id="f2939-134">動的なパッケージ配信により、アプリケーションを迅速に起動できます。</span><span class="sxs-lookup"><span data-stu-id="f2939-134">Dynamic package delivery allows for rapid application launch.</span></span>

### <span data-ttu-id="f2939-135">ファイルパッケージ配信からのロード</span><span class="sxs-lookup"><span data-stu-id="f2939-135">Load from File Package Delivery</span></span>

<span data-ttu-id="f2939-136">ファイルパッケージ配信からロードするために、サーバーは、ユーザーがアプリケーションを起動する前に、仮想化されたアプリケーションパッケージ全体をクライアントコンピューターに配信します。</span><span class="sxs-lookup"><span data-stu-id="f2939-136">For load from file package delivery, the server delivers the entire virtualized application package to a client computer before the user launches the application.</span></span> <span data-ttu-id="f2939-137">このシナリオでは、仮想化されたアプリケーションは、動的配信モデルによって使用される動的な段階的な方法ではなく、完全なパッケージとして提供されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-137">In this scenario, virtualized applications are delivered as a full package, rather than through the dynamic, incremental method used by the dynamic delivery model.</span></span>

<span data-ttu-id="f2939-138">**注** 各配信方法では、仮想アプリケーションの最初の配信プロセスと仮想アプリケーションの更新プロセスは同じです。更新された仮想アプリケーションパッケージは、元のアプリケーションパッケージと置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f2939-138">**Note** For each delivery method, the initial virtual application delivery process and the virtual application update process are the same; the updated virtual application package replaces the original application package.</span></span>

 

<span data-ttu-id="f2939-139">次の表では、各パッケージ配信方法の長所と短所を比較しています。</span><span class="sxs-lookup"><span data-stu-id="f2939-139">The following table compares the advantages and disadvantages of each package delivery method.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f2939-140">メソッド</span><span class="sxs-lookup"><span data-stu-id="f2939-140">Method</span></span></th>
<th align="left"><span data-ttu-id="f2939-141">長所</span><span class="sxs-lookup"><span data-stu-id="f2939-141">Advantages</span></span></th>
<th align="left"><span data-ttu-id="f2939-142">短所</span><span class="sxs-lookup"><span data-stu-id="f2939-142">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="f2939-143">コメント</span><span class="sxs-lookup"><span data-stu-id="f2939-143">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f2939-144">動的なパッケージの配信</span><span class="sxs-lookup"><span data-stu-id="f2939-144">Dynamic package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-145">アプリケーションはオンデマンドで配信され、更新されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-145">Applications are delivered and updated on demand.</span></span></p>
<p><span data-ttu-id="f2939-146">アプリは、起動時間を最適化するために段階的に配信および更新されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-146">Applications are delivered and updated incrementally to optimize launch time.</span></span></p>
<p><span data-ttu-id="f2939-147">更新プログラムは、クライアントデスクトップに自動的に配信されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-147">Updates are delivered automatically to the client desktop.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-148">サーバーの要件により、エンタープライズトポロジのフットプリントが大きくなります。</span><span class="sxs-lookup"><span data-stu-id="f2939-148">Larger footprint in enterprise topology because of server requirements.</span></span></p>
<p><span data-ttu-id="f2939-149">アプリケーションのストリーミングは LAN 経由で行う必要があります。WAN 経由の展開シナリオ、またはサーバーとクライアント間の信頼性の低いまたは断続的な接続を使用している場合は、使用できない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="f2939-149">Application streaming should be over a LAN; deployment scenarios over a WAN or that use an unreliable or intermittent connection between the server and client might be unusable.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-150">ストリーミングインフラストラクチャが必要です。</span><span class="sxs-lookup"><span data-stu-id="f2939-150">Requires a streaming infrastructure.</span></span></p>
<p><span data-ttu-id="f2939-151">Windows インストーラーは、アプリケーションの仮想化デスクトップクライアントソフトウェアをエンドユーザーのコンピューターに展開するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f2939-151">Windows Installer used to deploy Application Virtualization Desktop Client software to end-user computers.</span></span></p>
<p><span data-ttu-id="f2939-152">大企業は、アプリケーションの仮想化ストリーミングサーバーを配布ポイントとして使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2939-152">Large enterprises should use Application Virtualization Streaming Servers as distribution points.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f2939-153">ファイルパッケージ配信からのロード</span><span class="sxs-lookup"><span data-stu-id="f2939-153">Load from file package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-154">一般的なエンタープライズ管理プラクティスとの一貫性。</span><span class="sxs-lookup"><span data-stu-id="f2939-154">Consistent with typical enterprise management practices.</span></span></p>
<p><span data-ttu-id="f2939-155">単体構成のシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="f2939-155">Supports stand-alone configuration scenario.</span></span></p>
<p><span data-ttu-id="f2939-156">マイクロブランチオフィスの問題に対する解決策を提供します。</span><span class="sxs-lookup"><span data-stu-id="f2939-156">Provides solution to micro–branch office problem.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-157">アプリケーションの配信と更新はオンデマンドではできません。</span><span class="sxs-lookup"><span data-stu-id="f2939-157">Application delivery and update is not possible on-demand.</span></span></p>
<p><span data-ttu-id="f2939-158">アプリケーションの配信と更新は段階的に行われません。動的配信と相対的にリソース使用量が増加します。</span><span class="sxs-lookup"><span data-stu-id="f2939-158">Application delivery and update is not incremental; it increases resource consumption relative to dynamic delivery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-159">IT 組織は、多くの場合、アプリケーションライセンス、ユーザー認証、認証を管理する責任を負います。</span><span class="sxs-lookup"><span data-stu-id="f2939-159">The IT organization is often responsible for managing application licenses, user authorization, and authentication.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f2939-160">サーバー関連のプロトコルと外部コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f2939-160">Server-Related Protocols and External Components</span></span>


<span data-ttu-id="f2939-161">次の表に、Application Virtualization Server ベースのシナリオで使用できるサーバーの種類と、それに対応する伝送プロトコルと、特定のサーバー構成をサポートするために必要な外部コンポーネントを示します。</span><span class="sxs-lookup"><span data-stu-id="f2939-161">The following table lists the server types that can be used in an Application Virtualization Server-based scenarios, along with their corresponding transmission protocols and the external components needed to support the specific server configuration.</span></span> <span data-ttu-id="f2939-162">また、この表には、各サーバーの種類のレポートメカニズムとアクティブなアップグレードメカニズムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="f2939-162">The table also includes the reporting mechanism and the active upgrade mechanism for each server type.</span></span> <span data-ttu-id="f2939-163">これらのシナリオではすべて Application Virtualization Management Server が使用されるため、システムに組み込まれている内部レポート機能を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="f2939-163">Because these scenarios all use the Application Virtualization Management Server, you can use the internal reporting functionality that is built into the system.</span></span> <span data-ttu-id="f2939-164">アプリケーションの仮想化管理または Application Virtualization Streaming Server を使って、パッケージをクライアントに配信する場合、ユーザーがクライアントにログインすると、サーバー上のパッケージが自動的にアップグレードされます。IIS サーバーまたはファイルを使用してパッケージをクライアントに配信する場合、クライアント上のパッケージを手動でアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="f2939-164">If you use an Application Virtualization Management or an Application Virtualization Streaming Server to deliver packages to the client, packages on the server are automatically upgraded when a user logs into the client; if you use IIS servers or a file to deliver the packages to the client, the packages on the client must be upgraded manually.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f2939-165">サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="f2939-165">Server Type</span></span></th>
<th align="left"><span data-ttu-id="f2939-166">プロトコル</span><span class="sxs-lookup"><span data-stu-id="f2939-166">Protocols</span></span></th>
<th align="left"><span data-ttu-id="f2939-167">必要な外部コンポーネント</span><span class="sxs-lookup"><span data-stu-id="f2939-167">External Components Needed</span></span></th>
<th align="left"><span data-ttu-id="f2939-168">レポート</span><span class="sxs-lookup"><span data-stu-id="f2939-168">Reporting</span></span></th>
<th align="left"><span data-ttu-id="f2939-169">アクティブなアップグレード</span><span class="sxs-lookup"><span data-stu-id="f2939-169">Active Upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f2939-170">Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="f2939-170">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-171">RTSP</span><span class="sxs-lookup"><span data-stu-id="f2939-171">RTSP</span></span></p>
<p><span data-ttu-id="f2939-172">RTSPS</span><span class="sxs-lookup"><span data-stu-id="f2939-172">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-173">HTTPS を使用する場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイル、ファイアウォールをダウンロードして、サーバーをインターネットに公開することを防止します。</span><span class="sxs-lookup"><span data-stu-id="f2939-173">When using HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-174">内部</span><span class="sxs-lookup"><span data-stu-id="f2939-174">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-175">サポートされています</span><span class="sxs-lookup"><span data-stu-id="f2939-175">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f2939-176">Application Virtualization ストリーミングサーバー</span><span class="sxs-lookup"><span data-stu-id="f2939-176">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-177">RTSP</span><span class="sxs-lookup"><span data-stu-id="f2939-177">RTSP</span></span></p>
<p><span data-ttu-id="f2939-178">RTSPS</span><span class="sxs-lookup"><span data-stu-id="f2939-178">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-179">メカニズムを使用して、管理サーバーとストリーミングサーバーの間でコンテンツを同期します。</span><span class="sxs-lookup"><span data-stu-id="f2939-179">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="f2939-180">HTTPS を使用する場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイルをダウンロードし、ファイアウォールを使用してサーバーをインターネットに公開されないように保護します。</span><span class="sxs-lookup"><span data-stu-id="f2939-180">When using HTTPS, use an IIS server to download ICO and OSD files and use a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-181">内部</span><span class="sxs-lookup"><span data-stu-id="f2939-181">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-182">サポートされています</span><span class="sxs-lookup"><span data-stu-id="f2939-182">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f2939-183">IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="f2939-183">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-184">HTTP</span><span class="sxs-lookup"><span data-stu-id="f2939-184">HTTP</span></span></p>
<p><span data-ttu-id="f2939-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="f2939-185">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-186">メカニズムを使用して、管理サーバーとストリーミングサーバーの間でコンテンツを同期します。</span><span class="sxs-lookup"><span data-stu-id="f2939-186">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="f2939-187">HTTP または HTTPS を使用している場合は、IIS サーバーを使用して、ICO ファイルと OSD ファイル、ファイアウォールをダウンロードして、サーバーをインターネットに公開することを防止します。</span><span class="sxs-lookup"><span data-stu-id="f2939-187">When using HTTP or HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-188">内部</span><span class="sxs-lookup"><span data-stu-id="f2939-188">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-189">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f2939-189">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f2939-190">ファイル</span><span class="sxs-lookup"><span data-stu-id="f2939-190">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-191">SMB</span><span class="sxs-lookup"><span data-stu-id="f2939-191">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-192">管理サーバーとストリーミングサーバー間でコンテンツを同期する方法が必要です。</span><span class="sxs-lookup"><span data-stu-id="f2939-192">You need a way to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="f2939-193">ファイル共有またはストリーミング機能を使用しているクライアントコンピューターが必要です。</span><span class="sxs-lookup"><span data-stu-id="f2939-193">You need a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-194">内部</span><span class="sxs-lookup"><span data-stu-id="f2939-194">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2939-195">サポートされていません</span><span class="sxs-lookup"><span data-stu-id="f2939-195">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f2939-196">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f2939-196">Related topics</span></span>


[<span data-ttu-id="f2939-197">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="f2939-197">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="f2939-198">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="f2939-198">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="f2939-199">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="f2939-199">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





