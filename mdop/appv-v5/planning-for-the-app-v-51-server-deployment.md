---
title: App-V 5.1 Server の展開計画
description: App-V 5.1 Server の展開計画
author: dansimp
ms.assetid: eedd97c9-bee0-4749-9d1e-ab9528fba398
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31e3a116eb511356b061e6ccb18c7e25c060a66e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813435"
---
# <span data-ttu-id="59324-103">App-V 5.1 Server の展開計画</span><span class="sxs-lookup"><span data-stu-id="59324-103">Planning for the App-V 5.1 Server Deployment</span></span>


<span data-ttu-id="59324-104">Microsoft Application Virtualization (App-v) 5.1 サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできる専門的な機能のセットで構成されています。</span><span class="sxs-lookup"><span data-stu-id="59324-104">The Microsoft Application Virtualization (App-V) 5.1 server infrastructure consists of a set of specialized features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span>

## <span data-ttu-id="59324-105">App-v 5.1 Server の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="59324-105">Planning for App-V 5.1 Server Deployment</span></span>


<span data-ttu-id="59324-106">App-v 5.1 サーバーは、次の機能で構成されています。</span><span class="sxs-lookup"><span data-stu-id="59324-106">The App-V 5.1 server consists of the following features:</span></span>

-   <span data-ttu-id="59324-107">管理サーバー– App-v 5.1 インフラストラクチャの全体的な管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="59324-107">Management Server – provides overall management functionality for the App-V 5.1 infrastructure.</span></span>

-   <span data-ttu-id="59324-108">管理データベース– App-v 5.1 管理のデータベース展開が容易になります。</span><span class="sxs-lookup"><span data-stu-id="59324-108">Management Database – facilitates database predeployments for App-V 5.1 management.</span></span>

-   <span data-ttu-id="59324-109">公開サーバー–仮想アプリケーションのホスティング機能とストリーミング機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="59324-109">Publishing Server – provides hosting and streaming functionality for virtual applications.</span></span>

-   <span data-ttu-id="59324-110">レポートサーバー– App-v 5.1 reporting services を提供します。</span><span class="sxs-lookup"><span data-stu-id="59324-110">Reporting Server – provides App-V 5.1 reporting services.</span></span>

-   <span data-ttu-id="59324-111">レポートデータベース– App-v 5.1 レポートのデータベース展開を容易にします。</span><span class="sxs-lookup"><span data-stu-id="59324-111">Reporting Database – facilitates database predeployments for App-V 5.1 reporting.</span></span>

<span data-ttu-id="59324-112">次の一覧は、App-v 5.1 サーバーインフラストラクチャをインストールするための推奨される方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="59324-112">The following list displays the recommended methods for installing the App-V 5.1 server infrastructure:</span></span>

-   <span data-ttu-id="59324-113">App-v 5.1 サーバーをインストールします。</span><span class="sxs-lookup"><span data-stu-id="59324-113">Install the App-V 5.1 server.</span></span> <span data-ttu-id="59324-114">詳細については、「 [app-v 5.1 サーバーを展開する方法](how-to-deploy-the-app-v-51-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59324-114">For more information, see [How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md).</span></span>

-   <span data-ttu-id="59324-115">データベース、レポート、管理の各機能を別々のコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="59324-115">Install the database, reporting, and management features on separate computers.</span></span> <span data-ttu-id="59324-116">詳細については、「[管理データベースとレポートデータベースを管理サービスおよびレポートサービスから別のコンピューターにインストールする方法](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59324-116">For more information, see [How to Install the Management and Reporting Databases on Separate Computers from the Management and Reporting Services](how-to-install-the-management-and-reporting-databases-on-separate-computers-from-the-management-and-reporting-services51.md).</span></span>

-   <span data-ttu-id="59324-117">電子ソフトウェア配布 (ESD) を使用します。</span><span class="sxs-lookup"><span data-stu-id="59324-117">Use Electronic Software Distribution (ESD).</span></span> <span data-ttu-id="59324-118">詳細については、「[電子ソフトウェアの配布を使用して app-v 5.1 パッケージを展開する方法](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="59324-118">For more information, see [How to deploy App-V 5.1 Packages Using Electronic Software Distribution](how-to-deploy-app-v-51-packages-using-electronic-software-distribution.md).</span></span>

-   <span data-ttu-id="59324-119">すべてのサーバー機能を1台のコンピューターにインストールします。</span><span class="sxs-lookup"><span data-stu-id="59324-119">Install all server features on a single computer.</span></span>

## <a href="" id="---------app-v-5-1-server-interaction"></a> <span data-ttu-id="59324-120">App-v 5.1 Server の対話式操作</span><span class="sxs-lookup"><span data-stu-id="59324-120">App-V 5.1 Server Interaction</span></span>


<span data-ttu-id="59324-121">このセクションでは、さまざまな App-v 5.1 サーバーの役割が互いにどのように連携するかについて説明します。</span><span class="sxs-lookup"><span data-stu-id="59324-121">This section contains information about how the various App-V 5.1 server roles interact with each other.</span></span>

<span data-ttu-id="59324-122">App-v 5.1 Management Server には、パッケージのリポジトリと割り当てられた構成が含まれています。</span><span class="sxs-lookup"><span data-stu-id="59324-122">The App-V 5.1 Management Server contains the repository of packages and their assigned configurations.</span></span> <span data-ttu-id="59324-123">管理サーバーに登録されている発行サーバーの場合、関連付けられたメタデータは、App-v 5.1 クライアントを実行しているコンピューターから発行された更新要求を受信するときに使用する発行サーバーに提供されます。</span><span class="sxs-lookup"><span data-stu-id="59324-123">For Publishing Servers that are registered with the Management Server, the associated metadata is provided to the Publishing servers for use when publishing refresh requests are received from computers running the App-V 5.1 Client.</span></span> <span data-ttu-id="59324-124">1つの管理サーバーによって管理される app-v 5.1 発行サーバーは、さまざまなクライアントでサービスを提供でき、異なる web サイト名とポートバインドを持つことができます。</span><span class="sxs-lookup"><span data-stu-id="59324-124">App-V 5.1 publishing servers managed by a single management server can be serving different clients and can have different website names and port bindings.</span></span> <span data-ttu-id="59324-125">さらに、同じ管理サーバーによって管理されるすべての発行サーバーは、互いに複製されます。</span><span class="sxs-lookup"><span data-stu-id="59324-125">Additionally, all Publishing Servers managed by the same Management Server are replicas of each other.</span></span>

<span data-ttu-id="59324-126">**注** Management サーバーでは、ロードバランシングは実行されません。</span><span class="sxs-lookup"><span data-stu-id="59324-126">**Note** The Management Server does not perform any load balancing.</span></span> <span data-ttu-id="59324-127">関連付けられているメタデータは、クライアント要求の処理時に使用するために発行サーバーに渡されます。</span><span class="sxs-lookup"><span data-stu-id="59324-127">The associated metadata is simply passed to the publishing server for use when processing client requests.</span></span>

 

## <span data-ttu-id="59324-128">サーバー関連のプロトコルと外部機能</span><span class="sxs-lookup"><span data-stu-id="59324-128">Server-Related Protocols and External Features</span></span>


<span data-ttu-id="59324-129">次の例は、App-v 5.1 サーバーで使用されるサーバー関連のプロトコルに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="59324-129">The following displays information about server-related protocols used by the App-V 5.1 servers.</span></span> <span data-ttu-id="59324-130">この表には、各サーバーの種類のレポートメカニズムも含まれています。</span><span class="sxs-lookup"><span data-stu-id="59324-130">The table also includes the reporting mechanism for each server type.</span></span>

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
<th align="left"><span data-ttu-id="59324-131">サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="59324-131">Server Type</span></span></th>
<th align="left"><span data-ttu-id="59324-132">プロトコル</span><span class="sxs-lookup"><span data-stu-id="59324-132">Protocols</span></span></th>
<th align="left"><span data-ttu-id="59324-133">必要な外部機能</span><span class="sxs-lookup"><span data-stu-id="59324-133">External Features Needed</span></span></th>
<th align="left"><span data-ttu-id="59324-134">レポート</span><span class="sxs-lookup"><span data-stu-id="59324-134">Reporting</span></span></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="59324-135">IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="59324-135">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-136">HTTP</span><span class="sxs-lookup"><span data-stu-id="59324-136">HTTP</span></span></p>
<p><span data-ttu-id="59324-137">HTTPS</span><span class="sxs-lookup"><span data-stu-id="59324-137">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-138">このサーバープロトコルの組み合わせでは、管理サーバーとストリーミングサーバー間でコンテンツを同期するメカニズムが必要になります。</span><span class="sxs-lookup"><span data-stu-id="59324-138">This server-protocol combination requires a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="59324-139">HTTP または HTTPS を使用する場合は、IIS サーバーとファイアウォールを使用して、サーバーが公開されないようにインターネットを保護します。</span><span class="sxs-lookup"><span data-stu-id="59324-139">When using HTTP or HTTPS, use an IIS server and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-140">内部</span><span class="sxs-lookup"><span data-stu-id="59324-140">Internal</span></span></p></td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="59324-141">ファイル</span><span class="sxs-lookup"><span data-stu-id="59324-141">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-142">SMB</span><span class="sxs-lookup"><span data-stu-id="59324-142">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-143">このサーバープロトコルの組み合わせでは、管理サーバーとストリーミングサーバーの間でコンテンツを同期することがサポートされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="59324-143">This server-protocol combination requires support to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="59324-144">クライアントコンピューターでファイル共有またはストリーミング機能を使用します。</span><span class="sxs-lookup"><span data-stu-id="59324-144">Use a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="59324-145">内部</span><span class="sxs-lookup"><span data-stu-id="59324-145">Internal</span></span></p></td>
<td align="left"></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="59324-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="59324-146">Related topics</span></span>


[<span data-ttu-id="59324-147">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="59324-147">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

[<span data-ttu-id="59324-148">App-V 5.1 Server の展開</span><span class="sxs-lookup"><span data-stu-id="59324-148">Deploying the App-V 5.1 Server</span></span>](deploying-the-app-v-51-server.md)

 

 





