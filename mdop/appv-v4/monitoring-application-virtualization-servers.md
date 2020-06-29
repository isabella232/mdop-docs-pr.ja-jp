---
title: Application Virtualization サーバーの監視
description: Application Virtualization サーバーの監視
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816144"
---
# <span data-ttu-id="bcd32-103">Application Virtualization サーバーの監視</span><span class="sxs-lookup"><span data-stu-id="bcd32-103">Monitoring Application Virtualization Servers</span></span>


<span data-ttu-id="bcd32-104">Application Virtualization (App-v) サーバーの管理を簡素化するために、System Center Operations Manager2007 Management Pack を使用できます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-104">To simplify Application Virtualization (App-V) Server management, you can use the System Center Operations Manager2007 Management Pack.</span></span> <span data-ttu-id="bcd32-105">この管理パックは、Application Virtualization (App-v) 4.5 サーバーのみをサポートします。以前のサーバーバージョンはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="bcd32-105">This Management Pack supports only Application Virtualization (App-V) 4.5 servers; it does not support previous server versions.</span></span> <span data-ttu-id="bcd32-106">管理パックは、app-v クライアント要求を処理するための App-v Server の可用性を最大化します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-106">The Management Pack maximizes App-V Server availability for handling App-V Client requests.</span></span>

## <span data-ttu-id="bcd32-107">ステータスインジケーター</span><span class="sxs-lookup"><span data-stu-id="bcd32-107">Status Indicators</span></span>


<span data-ttu-id="bcd32-108">App-v サーバーの正常性ステータスインジケーターは、色分けされています。</span><span class="sxs-lookup"><span data-stu-id="bcd32-108">The App-V Server health status indicators are color-coded.</span></span> <span data-ttu-id="bcd32-109">色は、次の状態の値を表します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-109">The colors represent the following status values:</span></span>

-   <span data-ttu-id="bcd32-110">[色なしの場合、サーバーが回復不可能なエラーなしで実行されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-110">No color indicates that the server is running without non-recoverable errors.</span></span>

-   <span data-ttu-id="bcd32-111">黄色は、コンポーネントのいずれかが正常に機能していないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-111">Yellow indicates that one of the components is not functioning correctly.</span></span> <span data-ttu-id="bcd32-112">サーバーの全体的な機能は低下していますが、サーバーは引き続き利用できます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-112">The overall functionality of the server is degraded, but the server is still available.</span></span>

-   <span data-ttu-id="bcd32-113">赤は、サーバーが使用できないことと、キーサービスを提供できないこと、または外部サービスの依存関係と通信できないことを示します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-113">Red indicates that the server is not available and that it cannot provide key services or communicate with external service dependencies.</span></span>

## <span data-ttu-id="bcd32-114">モニタリングの条件</span><span class="sxs-lookup"><span data-stu-id="bcd32-114">Monitoring Criteria</span></span>


<span data-ttu-id="bcd32-115">管理パックは、サーバーの正常性の次の側面を監視します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-115">The Management Pack monitors the following aspects of server health:</span></span>

-   <span data-ttu-id="bcd32-116">サーバーの状態: サーバーイベントを監視し、サーバーが予期されたサービスを提供していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-116">Server Status—monitors server events to validate that the server is providing its expected services.</span></span>

-   <span data-ttu-id="bcd32-117">データストアアクセス—1つ以上の App-v 管理サーバーが、App-v データストアにアクセスして通信できるかどうかを追跡します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-117">Data Store Access—tracks the ability of one or more of the App-V Management Servers to access and communicate with the App-V data store.</span></span>

-   <span data-ttu-id="bcd32-118">コンテンツデータへのアクセス—ローカルディレクトリまたはネットワーク共有である \\ コンテンツディレクトリへのアクセスを監視し、要求されたファイルを読み取ることができます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-118">Content Data Access—monitors access to the \\Content directory, which might be a local directory or a network share, and the ability to read the requested files.</span></span>

-   <span data-ttu-id="bcd32-119">セキュリティ— App-v Server の証明書とセキュリティで保護された通信に関するエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-119">Security—reports errors with the App-V Server’s certificate and secure communications.</span></span>

-   <span data-ttu-id="bcd32-120">クライアント要求の処理: クライアント要求を処理して適切に応答する1つ以上の App-v サーバーの機能を監視します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-120">Client Request Handling—monitors the ability of one or more of the App-V Servers to handle and correctly respond to client requests.</span></span> <span data-ttu-id="bcd32-121">これらの要求には、構成要求、パッケージ読み込み要求、一連の要求などとしてのアイテムの公開が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-121">These requests include publishing such items as configuration requests, package load requests, and out of sequence requests.</span></span>

-   <span data-ttu-id="bcd32-122">[サーバー構成] — App-v Server の構成設定を確認します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-122">Server Configuration—checks the configuration settings of the App-V Server.</span></span> <span data-ttu-id="bcd32-123">これらの構成設定には、レジストリと App-v データストアの設定が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-123">These configuration settings include the settings in the registry and in the App-V data store.</span></span>

## <span data-ttu-id="bcd32-124">サーバーの相違点</span><span class="sxs-lookup"><span data-stu-id="bcd32-124">Server Differences</span></span>


<span data-ttu-id="bcd32-125">App-v 管理サーバーと App-v ストリーミングサーバーの主な違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bcd32-125">The main differences between the App-V Management Server and the App-V Streaming Server are as follows:</span></span>

-   <span data-ttu-id="bcd32-126">App-v 管理サーバーは、パブリッシング、ストリーミング、管理、レポートサービスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-126">App-V Management Servers can provide publishing, streaming, management, and reporting services.</span></span> <span data-ttu-id="bcd32-127">そのため、管理パックは、アプリを管理することができるのではなく、app-v の管理サーバーのさまざまな側面を管理することができます。これには、パッケージストリーミングのみが用意されています。</span><span class="sxs-lookup"><span data-stu-id="bcd32-127">Therefore, the Management Pack can manage more aspects of the App-V Management Server than it can manage on the App-V Streaming Server, which provides only package streaming.</span></span>

-   <span data-ttu-id="bcd32-128">App-v ストリーミングサーバーには、app-v データストアがないため、データストアへのアクセスは監視されません。</span><span class="sxs-lookup"><span data-stu-id="bcd32-128">The App-V Streaming Server does not have an App-V data store, so data store access is not monitored.</span></span> <span data-ttu-id="bcd32-129">App-v ストリーミングサーバーの構成情報は、レジストリで管理されます。</span><span class="sxs-lookup"><span data-stu-id="bcd32-129">The configuration information for the App-V Streaming Server is managed in the registry.</span></span>

-   <span data-ttu-id="bcd32-130">App-v ストリーミングサーバーでは、App-v Server 管理コンソールインターフェイスは使用されません。その他のツールを使用して、構成を管理します。</span><span class="sxs-lookup"><span data-stu-id="bcd32-130">The App-V Streaming Server does not use the App-V Server Management Console interface; use other tools to manage the configuration.</span></span>

## <span data-ttu-id="bcd32-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bcd32-131">Related topics</span></span>


[<span data-ttu-id="bcd32-132">Application Virtualization サーバー</span><span class="sxs-lookup"><span data-stu-id="bcd32-132">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





