---
title: ストリーミング方法の選択
description: ストリーミング方法の選択
author: dansimp
ms.assetid: 50d5e0ec-7f48-4cea-8711-5882bd89153b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0acfd345ac55f11476cffe94b3a95b13c5d8f303
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821667"
---
# <span data-ttu-id="7bcd4-103">ストリーミング方法の選択</span><span class="sxs-lookup"><span data-stu-id="7bcd4-103">Determine Your Streaming Method</span></span>


<span data-ttu-id="7bcd4-104">ユーザーが公開プロセスによってコンピューター上に配置されたアイコンをダブルクリックすると、アプリケーションの仮想化クライアントはストリーミングソースの場所から仮想アプリケーションパッケージコンテンツを取得します。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-104">The first time that a user double-clicks the icon that has been placed on a computer through the publishing process, the Application Virtualization client will obtain the virtual application package content from a streaming source location.</span></span>

<span data-ttu-id="7bcd4-105">**注** 
*ストリーミング*は、主要な機能ブロックから始まり、必要に応じて追加のブロックを取得して、シーケンス処理されたアプリケーションパッケージからコンテンツを取得するプロセスを記述するために使われる用語です。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-105">**Note**
*Streaming* is the term used to describe the process of obtaining content from a sequenced application package, starting with the primary feature block and then obtaining additional blocks as needed.</span></span>

 

<span data-ttu-id="7bcd4-106">ストリーミングソースの場所は、通常、ユーザーのコンピューターによってアクセスできるサーバーです。ただし、Microsoft Endpoint Configuration Manager などの一部の電子配布システムでは、ユーザーのコンピューターに SFT ファイルを配布し、そのコンピューターのキャッシュからローカルで仮想アプリケーションパッケージをストリーミングすることができます。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-106">The streaming source location is usually a server that is accessible by the user’s computer; however, some electronic distribution systems, such as Microsoft Endpoint Configuration Manager, can distribute the SFT file to the user’s computer and then stream the virtual application package locally from that computer’s cache.</span></span>

<span data-ttu-id="7bcd4-107">**注** 仮想パッケージのストリーミングソースの場所は、サーバーではないコンピューターで設定することができます。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-107">**Note** A streaming source location for virtual packages can be set up on a computer that is not a server.</span></span> <span data-ttu-id="7bcd4-108">これは、サーバーがない小規模の支店で特に便利です。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-108">This is especially useful in a small branch office that has no server.</span></span>

 

<span data-ttu-id="7bcd4-109">順序付けされたアプリケーションの保存に使用できるストリーミングソースについては、次の表を参照してください。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-109">The streaming sources that can be used to store sequenced applications are described in the following table.</span></span>

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
<th align="left"><span data-ttu-id="7bcd4-110">サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="7bcd4-110">Server Type</span></span></th>
<th align="left"><span data-ttu-id="7bcd4-111">プロトコル</span><span class="sxs-lookup"><span data-stu-id="7bcd4-111">Protocol</span></span></th>
<th align="left"><span data-ttu-id="7bcd4-112">長所</span><span class="sxs-lookup"><span data-stu-id="7bcd4-112">Advantages</span></span></th>
<th align="left"><span data-ttu-id="7bcd4-113">短所</span><span class="sxs-lookup"><span data-stu-id="7bcd4-113">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="7bcd4-114">Links</span><span class="sxs-lookup"><span data-stu-id="7bcd4-114">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7bcd4-115">ファイル サーバー</span><span class="sxs-lookup"><span data-stu-id="7bcd4-115">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="7bcd4-116">ファイル</span><span class="sxs-lookup"><span data-stu-id="7bcd4-116">File</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-117">\ コンテンツ共有を使用して既存のファイルサーバーを構成するシンプルで低コストのソリューション</span><span class="sxs-lookup"><span data-stu-id="7bcd4-117">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-118">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="7bcd4-118">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="7bcd4-119">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7bcd4-119">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7bcd4-120">IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="7bcd4-120">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="7bcd4-121">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="7bcd4-121">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-122">HTTPS プロトコルを使用した強化されたセキュリティをサポートします。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-122">Supports enhanced security using HTTPS protocol.</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-123">インターネット経由のリモートコンピューターへのストリーミングをサポートしています</span><span class="sxs-lookup"><span data-stu-id="7bcd4-123">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-124">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="7bcd4-124">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-125">高いスケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="7bcd4-125">Highly scalable</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-126">使い慣れたプロトコル</span><span class="sxs-lookup"><span data-stu-id="7bcd4-126">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-127">IIS を管理する必要がある</span><span class="sxs-lookup"><span data-stu-id="7bcd4-127">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-128">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="7bcd4-128">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="7bcd4-129">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="7bcd4-129">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7bcd4-130">Application Virtualization ストリーミングサーバー</span><span class="sxs-lookup"><span data-stu-id="7bcd4-130">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="7bcd4-131">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="7bcd4-131">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-132">アクティブなアップグレード</span><span class="sxs-lookup"><span data-stu-id="7bcd4-132">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-133">RTSPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="7bcd4-133">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-134">ファイアウォール内の1つのポートのみ開く (RTSPS のみ)</span><span class="sxs-lookup"><span data-stu-id="7bcd4-134">Only one port in firewall to open (RTSPS only)</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7bcd4-135">デュアルインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="7bcd4-135">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="7bcd4-136">サーバー管理の要件</span><span class="sxs-lookup"><span data-stu-id="7bcd4-136">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="7bcd4-137">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="7bcd4-137">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="7bcd4-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="7bcd4-138">Related topics</span></span>


[<span data-ttu-id="7bcd4-139">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="7bcd4-139">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="7bcd4-140">電子ソフトウェア配布ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="7bcd4-140">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)

[<span data-ttu-id="7bcd4-141">公開方法の選択</span><span class="sxs-lookup"><span data-stu-id="7bcd4-141">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

 

 





