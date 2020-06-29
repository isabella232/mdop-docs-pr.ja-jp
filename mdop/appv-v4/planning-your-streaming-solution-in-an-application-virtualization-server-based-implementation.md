---
title: Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画
description: Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画
author: dansimp
ms.assetid: 3a57306e-5c54-4fde-8593-fe3b788f18d3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d315f554eb99fc5c05c231630eaa41d4f505535
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815867"
---
# <span data-ttu-id="31a0b-103">Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="31a0b-103">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>


<span data-ttu-id="31a0b-104">Application virtualization Management Server ベースの実装と組み合わせてアプリケーション仮想化ストリーミングサーバーを使用する場合は、いくつかの方法から選ぶことができます。これには、さまざまなインフラストラクチャが用意されています。</span><span class="sxs-lookup"><span data-stu-id="31a0b-104">If you want to use Application Virtualization Streaming Servers in conjunction with your Application Virtualization Management Server-based implementation, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="31a0b-105">たとえば、フィールドブランチオフィスに既にサーバーがある場合は、それらのサーバー上でアプリケーションの仮想化 \ コンテンツ共有を配置し、そのコンテンツ共有をアプリケーションコンテンツソースとして使用するようにクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-105">For example, if you already have servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="31a0b-106">アプリケーションの仮想化管理サーバーのみを使用する場合 (たとえば、1つの office しか持っていない場合)、クライアントはそのサーバーからコンテンツをストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-106">If you choose to use only Application Virtualization Management Servers—for example, because you have only a single office—the clients can stream content from that server.</span></span>

<span data-ttu-id="31a0b-107">サポートされているオプションには、ファイルサーバー、IIS サーバー、または Application Virtualization ストリーミングサーバーの使用があります。</span><span class="sxs-lookup"><span data-stu-id="31a0b-107">The supported options include using a file server, an IIS server, or an Application Virtualization Streaming Server.</span></span> <span data-ttu-id="31a0b-108">また、既存のファイルサーバーまたは IIS サーバーに Application Virtualization Streaming Server をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-108">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span> <span data-ttu-id="31a0b-109">これらのさまざまなオプションの特性を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-109">The characteristics of these different options are summarized in the following table.</span></span>

<span data-ttu-id="31a0b-110">**注** アクティブなアップグレード機能を使用すると、アプリケーションを現在実行しているユーザーに影響を与えずに、新しいバージョンのアプリケーションを App-v Management Server または Streaming Server に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-110">**Note** The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="31a0b-111">次にユーザーがアプリケーションを起動したときに、app-v 管理サーバーまたはストリーミングサーバーからアプリケーションの最新バージョンが自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="31a0b-111">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="31a0b-112">この機能を利用するには、RTSP (S) プロトコルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31a0b-112">Use of the RTSP(S) protocol is required for this feature.</span></span>

 

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
<th align="left"><span data-ttu-id="31a0b-113">サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="31a0b-113">Server Type</span></span></th>
<th align="left"><span data-ttu-id="31a0b-114">プロトコル</span><span class="sxs-lookup"><span data-stu-id="31a0b-114">Protocol</span></span></th>
<th align="left"><span data-ttu-id="31a0b-115">長所</span><span class="sxs-lookup"><span data-stu-id="31a0b-115">Advantages</span></span></th>
<th align="left"><span data-ttu-id="31a0b-116">短所</span><span class="sxs-lookup"><span data-stu-id="31a0b-116">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="31a0b-117">Links</span><span class="sxs-lookup"><span data-stu-id="31a0b-117">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31a0b-118">ファイル サーバー</span><span class="sxs-lookup"><span data-stu-id="31a0b-118">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31a0b-119">SMB</span><span class="sxs-lookup"><span data-stu-id="31a0b-119">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-120">\ コンテンツ共有を使用して既存のファイルサーバーを構成するシンプルで低コストのソリューション</span><span class="sxs-lookup"><span data-stu-id="31a0b-120">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-121">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="31a0b-121">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="31a0b-122">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="31a0b-122">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31a0b-123">IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="31a0b-123">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31a0b-124">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="31a0b-124">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-125">HTTPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="31a0b-125">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="31a0b-126">インターネット経由のリモートコンピューターへのストリーミングをサポートしています</span><span class="sxs-lookup"><span data-stu-id="31a0b-126">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="31a0b-127">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="31a0b-127">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="31a0b-128">対応</span><span class="sxs-lookup"><span data-stu-id="31a0b-128">Scalable</span></span></p></li>
<li><p><span data-ttu-id="31a0b-129">使い慣れたプロトコル</span><span class="sxs-lookup"><span data-stu-id="31a0b-129">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-130">IIS を管理する必要がある</span><span class="sxs-lookup"><span data-stu-id="31a0b-130">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="31a0b-131">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="31a0b-131">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="31a0b-132">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="31a0b-132">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31a0b-133">Application Virtualization ストリーミングサーバー</span><span class="sxs-lookup"><span data-stu-id="31a0b-133">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31a0b-134">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="31a0b-134">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-135">アクティブなアップグレード</span><span class="sxs-lookup"><span data-stu-id="31a0b-135">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="31a0b-136">RTSPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="31a0b-136">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="31a0b-137">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="31a0b-137">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-138">デュアルインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="31a0b-138">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="31a0b-139">サーバー管理の要件</span><span class="sxs-lookup"><span data-stu-id="31a0b-139">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-streaming-servers.md" data-raw-source="[How to Configure the Application Virtualization Streaming Servers](how-to-configure-the-application-virtualization-streaming-servers.md)"><span data-ttu-id="31a0b-140">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="31a0b-140">How to Configure the Application Virtualization Streaming Servers</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31a0b-141">Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="31a0b-141">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="31a0b-142">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="31a0b-142">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-143">アクティブなアップグレード</span><span class="sxs-lookup"><span data-stu-id="31a0b-143">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="31a0b-144">RTSPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="31a0b-144">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="31a0b-145">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="31a0b-145">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="31a0b-146">デュアルインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="31a0b-146">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="31a0b-147">サーバー管理の要件</span><span class="sxs-lookup"><span data-stu-id="31a0b-147">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="31a0b-148">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="31a0b-148">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="31a0b-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="31a0b-149">Related topics</span></span>


[<span data-ttu-id="31a0b-150">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="31a0b-150">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="31a0b-151">Application Virtualization システム コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="31a0b-151">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="31a0b-152">Application Virtualization Management Server を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="31a0b-152">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





