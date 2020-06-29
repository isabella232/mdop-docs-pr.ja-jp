---
title: 電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画
description: 電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画
author: dansimp
ms.assetid: bc18772a-f169-486f-adb1-7af1a31845aa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c49d6fc0b5f8f5dee347ead3bb899ce9b0387024
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815857"
---
# <span data-ttu-id="58d81-103">電子ソフトウェア配布の実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="58d81-103">Planning Your Streaming Solution in an Electronic Software Distribution Implementation</span></span>


<span data-ttu-id="58d81-104">ESD システムと連携してストリーミングサーバーを使用して、アプリケーションコンテンツをエンドユーザーのコンピューターで利用できるようにする場合は、いくつかの方法を選ぶことができます。これには、既に配置されているインフラストラクチャを利用できます。</span><span class="sxs-lookup"><span data-stu-id="58d81-104">If you decide to use streaming servers in conjunction with your ESD system to make application content available to your end user computers, you can choose from several alternatives, taking advantage of whatever infrastructure is already in place.</span></span> <span data-ttu-id="58d81-105">たとえば、お客様の ESD システムが、現場支店のサーバーでソフトウェア配布共有を使用している場合は、そのようなサーバー上でアプリケーションの仮想化 \ コンテンツ共有を配置し、そのコンテンツ共有をアプリケーションコンテンツソースとして使用するようにクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="58d81-105">For example, if your ESD system has software distribution shares on servers in your field branch offices, you can place the Application Virtualization \\CONTENT share on those servers and then configure the clients to use that content share as their application content source.</span></span> <span data-ttu-id="58d81-106">サポートされているオプションには、ファイルサーバーまたは IIS サーバーの使用があります。</span><span class="sxs-lookup"><span data-stu-id="58d81-106">The supported options include using a file server or an IIS server.</span></span> <span data-ttu-id="58d81-107">また、既存のファイルサーバーまたは IIS サーバーに Application Virtualization Streaming Server をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="58d81-107">You could also install the Application Virtualization Streaming Server on an existing file server or IIS server.</span></span>

<span data-ttu-id="58d81-108">Application Virtualization Streaming Server は、Application Virtualization のアクティブなアップグレード機能をサポートします。</span><span class="sxs-lookup"><span data-stu-id="58d81-108">The Application Virtualization Streaming Server provides support for the active upgrade feature in Application Virtualization.</span></span> <span data-ttu-id="58d81-109">アクティブなアップグレード機能を使用すると、アプリケーションを現在実行しているユーザーに影響を与えずに、新しいバージョンのアプリケーションを App-v Management Server または Streaming Server に追加することができます。</span><span class="sxs-lookup"><span data-stu-id="58d81-109">The active upgrade feature enables a new version of an application to be added to an App-V Management Server or Streaming Server without affecting users currently running the application.</span></span> <span data-ttu-id="58d81-110">次にユーザーがアプリケーションを起動したときに、app-v 管理サーバーまたはストリーミングサーバーからアプリケーションの最新バージョンが自動的に取得されます。</span><span class="sxs-lookup"><span data-stu-id="58d81-110">The App-V clients will automatically receive the latest version of the application from the App-V Management Server or Streaming Server the next time the user starts the application.</span></span> <span data-ttu-id="58d81-111">この機能を利用するには、RTSP (S) プロトコルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58d81-111">Use of the RTSP(S) protocol is required for this feature.</span></span> <span data-ttu-id="58d81-112">Application Virtualization Streaming Server を使用しない場合は、ESD システムを使用して、アプリケーションパッケージのアップグレードを明示的に管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58d81-112">If you choose not to use the Application Virtualization Streaming Server, you will need to explicitly manage application package upgrades by using the ESD system.</span></span>

<span data-ttu-id="58d81-113">**注** アプリケーションへのアクセスは Active Directory ドメインサービスのセキュリティグループによって制御されるため、各仮想アプリケーションのセキュリティグループを設定し、各グループに追加されるユーザーを管理するためのプロセスを計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="58d81-113">**Note** Access to the applications is controlled by means of Security Groups in Active Directory Domain Services, so you will need to plan a process for setting up a security group for each virtual application and for managing which users are added to each group.</span></span> <span data-ttu-id="58d81-114">Application Virtualization システム管理者は、コンテンツ共有の下にあるアプリケーションディレクトリに Acl を適用することによって、これらの Active Directory グループを使用するように各ストリーミングサーバーを構成します。 Active Directory グループメンバーシップに基づくパッケージへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="58d81-114">The Application Virtualization system administrator configures each streaming server to use these Active Directory groups by applying ACLs to the application directories under the CONTENT share, which controls access to the packages based on Active Directory group membership.</span></span>

 

<span data-ttu-id="58d81-115">利用可能なストリーミングオプションの特性を次の表にまとめます。</span><span class="sxs-lookup"><span data-stu-id="58d81-115">The characteristics of the available streaming options are summarized in the following table.</span></span>

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
<th align="left"><span data-ttu-id="58d81-116">サーバーの種類</span><span class="sxs-lookup"><span data-stu-id="58d81-116">Server Type</span></span></th>
<th align="left"><span data-ttu-id="58d81-117">プロトコル</span><span class="sxs-lookup"><span data-stu-id="58d81-117">Protocol</span></span></th>
<th align="left"><span data-ttu-id="58d81-118">長所</span><span class="sxs-lookup"><span data-stu-id="58d81-118">Advantages</span></span></th>
<th align="left"><span data-ttu-id="58d81-119">短所</span><span class="sxs-lookup"><span data-stu-id="58d81-119">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="58d81-120">Links</span><span class="sxs-lookup"><span data-stu-id="58d81-120">Links</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58d81-121">ファイル サーバー</span><span class="sxs-lookup"><span data-stu-id="58d81-121">File server</span></span></p></td>
<td align="left"><p><span data-ttu-id="58d81-122">SMB</span><span class="sxs-lookup"><span data-stu-id="58d81-122">SMB</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-123">\ コンテンツ共有を使用して既存のファイルサーバーを構成するシンプルで低コストのソリューション</span><span class="sxs-lookup"><span data-stu-id="58d81-123">Simple low-cost solution to configure existing file server with \CONTENT share</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-124">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="58d81-124">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-file-server.md" data-raw-source="[How to Configure the File Server](how-to-configure-the-file-server.md)"><span data-ttu-id="58d81-125">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="58d81-125">How to Configure the File Server</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="58d81-126">IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="58d81-126">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="58d81-127">HTTP/HTTPS</span><span class="sxs-lookup"><span data-stu-id="58d81-127">HTTP/ HTTPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-128">HTTPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="58d81-128">Supports enhanced security using HTTPS protocol</span></span></p></li>
<li><p><span data-ttu-id="58d81-129">インターネット経由のリモートコンピューターへのストリーミングをサポートしています</span><span class="sxs-lookup"><span data-stu-id="58d81-129">Supports streaming to remote computers across the Internet</span></span></p></li>
<li><p><span data-ttu-id="58d81-130">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="58d81-130">Only one port in firewall to open</span></span></p></li>
<li><p><span data-ttu-id="58d81-131">対応</span><span class="sxs-lookup"><span data-stu-id="58d81-131">Scalable</span></span></p></li>
<li><p><span data-ttu-id="58d81-132">使い慣れたプロトコル</span><span class="sxs-lookup"><span data-stu-id="58d81-132">Familiar protocol</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-133">IIS を管理する必要がある</span><span class="sxs-lookup"><span data-stu-id="58d81-133">Need to manage IIS</span></span></p></li>
<li><p><span data-ttu-id="58d81-134">アクティブなアップグレードなし</span><span class="sxs-lookup"><span data-stu-id="58d81-134">No active upgrade</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-server-for-iis.md" data-raw-source="[How to Configure the Server for IIS](how-to-configure-the-server-for-iis.md)"><span data-ttu-id="58d81-135">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="58d81-135">How to Configure the Server for IIS</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="58d81-136">Application Virtualization ストリーミングサーバー</span><span class="sxs-lookup"><span data-stu-id="58d81-136">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="58d81-137">RTSP/RTSPS</span><span class="sxs-lookup"><span data-stu-id="58d81-137">RTSP/ RTSPS</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-138">アクティブなアップグレード</span><span class="sxs-lookup"><span data-stu-id="58d81-138">Active upgrade</span></span></p></li>
<li><p><span data-ttu-id="58d81-139">RTSPS プロトコルを使用した強化されたセキュリティのサポート</span><span class="sxs-lookup"><span data-stu-id="58d81-139">Supports enhanced security using RTSPS protocol</span></span></p></li>
<li><p><span data-ttu-id="58d81-140">開くことができるのはファイアウォール内の1つのポートのみです。</span><span class="sxs-lookup"><span data-stu-id="58d81-140">Only one port in firewall to open</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="58d81-141">デュアルインフラストラクチャ</span><span class="sxs-lookup"><span data-stu-id="58d81-141">Dual infrastructure</span></span></p></li>
<li><p><span data-ttu-id="58d81-142">サーバー管理の要件</span><span class="sxs-lookup"><span data-stu-id="58d81-142">Server administration requirement</span></span></p></li>
</ul></td>
<td align="left"><p><a href="how-to-configure-the-application-virtualization-management-servers.md" data-raw-source="[How to Configure the Application Virtualization Management Servers](how-to-configure-the-application-virtualization-management-servers.md)"><span data-ttu-id="58d81-143">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="58d81-143">How to Configure the Application Virtualization Management Servers</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="58d81-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="58d81-144">Related topics</span></span>


[<span data-ttu-id="58d81-145">ESD ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="58d81-145">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)

[<span data-ttu-id="58d81-146">セキュリティと保護の概要</span><span class="sxs-lookup"><span data-stu-id="58d81-146">Security and Protection Overview</span></span>](security-and-protection-overview.md)

[<span data-ttu-id="58d81-147">電子ソフトウェア配布を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="58d81-147">Publishing Virtual Applications Using Electronic Software Distribution</span></span>](publishing-virtual-applications-using-electronic-software-distribution.md)

 

 





