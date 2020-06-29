---
title: App-V 5.1 のアーキテクチャの概要
description: App-V 5.1 のアーキテクチャの概要
author: dansimp
ms.assetid: 90406361-55b8-40b7-85c0-449436789d4c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8044c6ae9af4673ec12b47cf3b8fa73a134d9cca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814522"
---
# <span data-ttu-id="5d41c-103">App-V 5.1 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="5d41c-103">High Level Architecture for App-V 5.1</span></span>


<span data-ttu-id="5d41c-104">Microsoft Application Virtualization (App-v) 5.1 の展開を簡素化するには、次の情報を参考にしてください。</span><span class="sxs-lookup"><span data-stu-id="5d41c-104">Use the following information to help you simplify you Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

## <span data-ttu-id="5d41c-105">アーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="5d41c-105">Architecture Overview</span></span>


<span data-ttu-id="5d41c-106">一般的なアプリ-V 5.1 の実装は、次の要素で構成されます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-106">A typical App-V 5.1 implementation consists of the following elements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5d41c-107">要素</span><span class="sxs-lookup"><span data-stu-id="5d41c-107">Element</span></span></th>
<th align="left"><span data-ttu-id="5d41c-108">詳細情報</span><span class="sxs-lookup"><span data-stu-id="5d41c-108">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d41c-109">App-v 5.1 Management Server</span><span class="sxs-lookup"><span data-stu-id="5d41c-109">App-V 5.1 Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d41c-110">App-v 5.1 Management サーバーには、app-v 5.1 インフラストラクチャの全体的な管理機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5d41c-110">The App-V 5.1 Management server provides overall management functionality for the App-V 5.1 infrastructure.</span></span> <span data-ttu-id="5d41c-111">さらに、環境に管理サーバーの複数のインスタンスをインストールすることもできます。これには次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="5d41c-111">Additionally, you can install more than one instance of the management server in your environment which provides the following benefits:</span></span></p>
<ul>
<li><p><span data-ttu-id="5d41c-112">フォールトトレランスと高可用性–2つの別々のコンピューターに、5.1 アプリをインストールして構成することは、サーバーの1つが利用できない場合やオフラインの場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-112">Fault Tolerance and High Availability – Installing and configuring the App-V 5.1 Management server on two separate computers can help in situations when one of the servers is unavailable or offline.</span></span></p>
<p><span data-ttu-id="5d41c-113">また、複数のコンピューターに管理サーバーをインストールすることで、App-v 5.1 の可用性を高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-113">You can also help increase App-V 5.1 availability by installing the Management server on multiple computers.</span></span> <span data-ttu-id="5d41c-114">このシナリオでは、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d41c-114">In this scenario, a network load balancer should also be considered so that server requests are balanced.</span></span></p></li>
<li><p><span data-ttu-id="5d41c-115">スケーラビリティ–高負荷をサポートするために必要に応じて、他の管理サーバーを追加することができます。たとえば、ロードバランサーの背後に複数のサーバーをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-115">Scalability – You can add additional management servers as necessary to support a high load, for example you can install multiple servers behind a load balancer.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d41c-116">App-v 5.1 公開サーバー</span><span class="sxs-lookup"><span data-stu-id="5d41c-116">App-V 5.1 Publishing Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d41c-117">App-v 5.1 公開サーバーには、仮想アプリケーションのホスティングとストリーミングの機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5d41c-117">The App-V 5.1 publishing server provides functionality for virtual application hosting and streaming.</span></span> <span data-ttu-id="5d41c-118">発行サーバーでは、データベース接続は必要ありません。次のプロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="5d41c-118">The publishing server does not require a database connection and supports the following protocols:</span></span></p>
<ul>
<li><p><span data-ttu-id="5d41c-119">HTTP と HTTPS</span><span class="sxs-lookup"><span data-stu-id="5d41c-119">HTTP, and HTTPS</span></span></p></li>
</ul>
<p><span data-ttu-id="5d41c-120">また、複数のコンピューターに発行サーバーをインストールすることで、App-v 5.1 の可用性を向上させることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-120">You can also help increase App-V 5.1 availability by installing the Publishing server on multiple computers.</span></span> <span data-ttu-id="5d41c-121">また、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d41c-121">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5d41c-122">App-v 5.1 レポートサーバー</span><span class="sxs-lookup"><span data-stu-id="5d41c-122">App-V 5.1 Reporting Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d41c-123">App-v 5.1 レポートサーバーを使用すると、承認されたユーザーは、app-v 5.1 インフラストラクチャを管理するのに役立つ、既存の App-v 5.1 レポートとアドホックレポートを実行して表示することができます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-123">The App-V 5.1 Reporting server enables authorized users to run and view existing App-V 5.1 reports and ad hoc reports that can help them manage the App-V 5.1 infrastructure.</span></span> <span data-ttu-id="5d41c-124">レポートサーバーには、App-v 5.1 レポートデータベースへの接続が必要です。</span><span class="sxs-lookup"><span data-stu-id="5d41c-124">The Reporting server requires a connection to the App-V 5.1 reporting database.</span></span> <span data-ttu-id="5d41c-125">また、複数のコンピューターにレポートサーバーをインストールすることで、App-v 5.1 の可用性を高めることもできます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-125">You can also help increase App-V 5.1 availability by installing the Reporting server on multiple computers.</span></span> <span data-ttu-id="5d41c-126">また、サーバー要求が分散されるように、ネットワークロードバランサーも考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5d41c-126">A network load balancer should also be considered so that server requests are balanced.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5d41c-127">App-v 5.1 クライアント</span><span class="sxs-lookup"><span data-stu-id="5d41c-127">App-V 5.1 Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="5d41c-128">App-v 5.1 を使用して作成されたパッケージを、ターゲットコンピューターで実行するには、App-v 5.1 クライアントを使用します。</span><span class="sxs-lookup"><span data-stu-id="5d41c-128">The App-V 5.1 client enables packages created using App-V 5.1 to run on target computers.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5d41c-129">**注** 電子ソフトウェアの配布 (ESD) で App-v 5.1 を使用している場合、app-v 5.1 Management server を使用する必要はありませんが、App-v 5.1 のレポート機能とストリーミング機能を利用することはできます。</span><span class="sxs-lookup"><span data-stu-id="5d41c-129">**Note** If you are using App-V 5.1 with Electronic Software Distribution (ESD) you are not required to use the App-V 5.1 Management server, however you can still utilize the reporting and streaming functionality of App-V 5.1.</span></span>

 






## <span data-ttu-id="5d41c-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5d41c-130">Related topics</span></span>


[<span data-ttu-id="5d41c-131">App-V 5.1 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="5d41c-131">Getting Started with App-V 5.1</span></span>](getting-started-with-app-v-51.md)

 

 




