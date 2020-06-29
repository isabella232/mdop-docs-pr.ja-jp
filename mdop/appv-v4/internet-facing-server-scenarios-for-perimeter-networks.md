---
title: 境界ネットワークのインターネットに接続されたサーバーのシナリオ
description: 境界ネットワークのインターネットに接続されたサーバーのシナリオ
author: dansimp
ms.assetid: 8a4da6e6-82c7-49e5-b9b1-1666cba02f65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fcb04e651341fa107c358eaabbd7992d7ea155ec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816284"
---
# <span data-ttu-id="44b48-103">境界ネットワークのインターネットに接続されたサーバーのシナリオ</span><span class="sxs-lookup"><span data-stu-id="44b48-103">Internet-Facing Server Scenarios for Perimeter Networks</span></span>


<span data-ttu-id="44b48-104">App-v 4.5 は、ネットワークに接続されていない、またはネットワークから切断されたユーザーが引き続きアプリを使用できるようにする、インターネットに接続しているサーバーのシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="44b48-104">App-V4.5 supports Internet-facing server scenarios, in which users who are not connected to the corporate network or who disconnect from the network can still use App-V.</span></span> <span data-ttu-id="44b48-105">次の図に示すように、インターネット (RTSPS および HTTPS) でのセキュリティで保護されたプロトコルの使用のみがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="44b48-105">As shown in the following illustration, only the use of secure protocols on the Internet (RTSPS and HTTPS) is supported.</span></span>

![app-v ファイアウォールの配置図](images/appvfirewalls.gif)

<span data-ttu-id="44b48-107">ISA Server を使用して、次の方法で App-v インフラストラクチャが内部ネットワーク上にある ISA Server を使用して、インターネット向けソリューションをセットアップできます。</span><span class="sxs-lookup"><span data-stu-id="44b48-107">You can set up an Internet-facing solution, using an ISA Server, where the App-V infrastructure is on the internal network in the following ways:</span></span>

-   <span data-ttu-id="44b48-108">ICO ファイルと OSD ファイルをホストしている IIS サーバー用の Web 公開ルールを作成します。また、必要に応じて、ストリーミング用のパッケージを内部ネットワーク上に配置します。</span><span class="sxs-lookup"><span data-stu-id="44b48-108">Create a Web Publishing rule for the IIS server that is hosting the ICO and OSD files—and optionally, the packages for streaming—located on the internal network.</span></span> <span data-ttu-id="44b48-109">詳細な手順については <https://go.microsoft.com/fwlink/?LinkId=151982> 、をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44b48-109">Detailed steps are provided at <https://go.microsoft.com/fwlink/?LinkId=151982>.</span></span>

-   <span data-ttu-id="44b48-110">App-v Web Management Server (RTSPS) のサーバー公開ルールを作成します。</span><span class="sxs-lookup"><span data-stu-id="44b48-110">Create a Server Publishing rule for the App-V Web Management Server (RTSPS).</span></span> <span data-ttu-id="44b48-111">詳細な手順については [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983) 、をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="44b48-111">Detailed steps are provided at [https://go.microsoft.com/fwlink/?LinkId=151983&](https://go.microsoft.com/fwlink/?LinkId=151983).</span></span>

<span data-ttu-id="44b48-112">次の図に示すように、クライアントと ISA Server の間、または ISA Server と内部ネットワークの間で、インフラストラクチャが他のファイアウォールを実装している場合は、RTSPS (TCP 322) と HTTPS (TCP 443) の両方のファイアウォールルールを作成して、トラフィックフローをサポートする必要があります。</span><span class="sxs-lookup"><span data-stu-id="44b48-112">As shown in the following illustration, if the infrastructure has implemented other firewalls between the client and the ISA Server or between the ISA Server and the internal network, both RTSPS (TCP 322) and HTTPS (TCP 443) firewall rules must be created to support the flow of traffic.</span></span> <span data-ttu-id="44b48-113">また、ISA Server と内部ネットワークの間にファイアウォールが実装されている場合は、ドメインメンバーに必要な既定のトラフィックをファイアウォール (DNS、LDAP、Kerberos、SMB/CIFS) でトンネリングすることを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="44b48-113">Also, if firewalls have been implemented between the ISA Server and the internal network, the default traffic required for domain members must be permitted to tunnel through the firewall (DNS, LDAP, Kerberos, SMB/CIFS).</span></span>

![app v 境界ネットワークファイアウォールの図](images/appvperimeternetworkfirewall.gif)

<span data-ttu-id="44b48-115">ファイアウォールの解決策は環境によって異なるため、このトピックで示されているガイダンスでは、インターネットに接続された App-v 環境を境界ネットワークで構成するために必要なトラフィックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="44b48-115">Because the firewall solutions vary from environment to environment, the guidance provided in this topic describes the traffic that would be required to configure an Internet-facing App-V environment in the perimeter network.</span></span> <span data-ttu-id="44b48-116">この情報には、推奨される内部ネットワークサーバーも含まれます。</span><span class="sxs-lookup"><span data-stu-id="44b48-116">This information also includes the recommended internal network servers.</span></span>

<span data-ttu-id="44b48-117">境界ネットワークに次のサーバーを配置します。</span><span class="sxs-lookup"><span data-stu-id="44b48-117">Place the following servers in the perimeter network:</span></span>

-   <span data-ttu-id="44b48-118">App-v Management Server</span><span class="sxs-lookup"><span data-stu-id="44b48-118">App-V Management Server</span></span>

-   <span data-ttu-id="44b48-119">公開とストリーミング用の IIS サーバー</span><span class="sxs-lookup"><span data-stu-id="44b48-119">IIS server for publishing and streaming</span></span>

<span data-ttu-id="44b48-120">**注** 管理サーバーと IIS サーバーを別々のコンピューターに配置することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="44b48-120">**Note** It is a best practice to place the Management Server and IIS server on separate computers.</span></span>

 

<span data-ttu-id="44b48-121">次のサーバーを内部ネットワークに配置します。</span><span class="sxs-lookup"><span data-stu-id="44b48-121">Place the following servers in the internal network:</span></span>

-   <span data-ttu-id="44b48-122">Content server</span><span class="sxs-lookup"><span data-stu-id="44b48-122">Content server</span></span>

-   <span data-ttu-id="44b48-123">データストア (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="44b48-123">Data store (SQL Server)</span></span>

-   <span data-ttu-id="44b48-124">Active Directory ドメインコントローラー</span><span class="sxs-lookup"><span data-stu-id="44b48-124">Active Directory Domain Controller</span></span>

## <span data-ttu-id="44b48-125">トラフィック要件</span><span class="sxs-lookup"><span data-stu-id="44b48-125">Traffic Requirements</span></span>


<span data-ttu-id="44b48-126">次の表に、インターネットおよび境界ネットワークと、境界ネットワークから内部ネットワークへの通信のトラフィック要件を示します。</span><span class="sxs-lookup"><span data-stu-id="44b48-126">The following tables list the traffic requirements for communication from the Internet and the perimeter network and from the perimeter network to the internal network.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44b48-127">インターネットから境界ネットワークへのトラフィック要件</span><span class="sxs-lookup"><span data-stu-id="44b48-127">Traffic Requirements from Internet to Perimeter Network</span></span></th>
<th align="left"><span data-ttu-id="44b48-128">詳細</span><span class="sxs-lookup"><span data-stu-id="44b48-128">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b48-129">RTSPS (公開の更新およびストリーミングパッケージ)</span><span class="sxs-lookup"><span data-stu-id="44b48-129">RTSPS (publishing refresh and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-130">既定では TCP 322これは、App-v Management Server で変更できます。</span><span class="sxs-lookup"><span data-stu-id="44b48-130">TCP 322 by default; this can be changed in App-V Management Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44b48-131">HTTPS (ICO ファイルと OSD ファイル、ストリーミングパッケージ)</span><span class="sxs-lookup"><span data-stu-id="44b48-131">HTTPS (publishing ICO and OSD files and streaming packages)</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-132">既定では TCP 443これは、IIS 構成で変更できます。</span><span class="sxs-lookup"><span data-stu-id="44b48-132">TCP 443 by default; this can be changed in the IIS configuration.</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="44b48-133">境界ネットワークから内部ネットワークへのトラフィック要件</span><span class="sxs-lookup"><span data-stu-id="44b48-133">Traffic Requirements from Perimeter Network to Internal Network</span></span></th>
<th align="left"><span data-ttu-id="44b48-134">詳細</span><span class="sxs-lookup"><span data-stu-id="44b48-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b48-135">SQL Server</span><span class="sxs-lookup"><span data-stu-id="44b48-135">SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-136">TCP 1433 は既定のままですが、SQL Server で構成できます。</span><span class="sxs-lookup"><span data-stu-id="44b48-136">TCP 1433 is the default but can be configured in SQL Server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44b48-137">SMB/CIFS</span><span class="sxs-lookup"><span data-stu-id="44b48-137">SMB/CIFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-138">コンテンツディレクトリが管理サーバーまたは IIS サーバーからリモートで配置されている場合 (推奨)</span><span class="sxs-lookup"><span data-stu-id="44b48-138">If the content directory is located remotely from the Management Server(s) or IIS server (recommended).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b48-139">Kerberos</span><span class="sxs-lookup"><span data-stu-id="44b48-139">Kerberos</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-140">TCP および UDP 88</span><span class="sxs-lookup"><span data-stu-id="44b48-140">TCP and UDP 88</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="44b48-141">LDAP</span><span class="sxs-lookup"><span data-stu-id="44b48-141">LDAP</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-142">TCP および UDP 389</span><span class="sxs-lookup"><span data-stu-id="44b48-142">TCP and UDP 389</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="44b48-143">DNS</span><span class="sxs-lookup"><span data-stu-id="44b48-143">DNS</span></span></p></td>
<td align="left"><p><span data-ttu-id="44b48-144">内部リソースの名前解決 (境界ネットワークサーバー上のホストのファイルを使用して除去可能)</span><span class="sxs-lookup"><span data-stu-id="44b48-144">For name resolution of internal resources (can be eliminated with the use of host’s file on perimeter network servers)</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





