---
title: 分散環境への App-V 管理の構成
description: 分散環境への App-V 管理の構成
author: dansimp
ms.assetid: 53971fa9-8319-435c-be74-c37feb9af1da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c1a638d6afde9270859c8aa98fc9f421c39cfc72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821914"
---
# <span data-ttu-id="06eb8-103">分散環境への App-V 管理の構成</span><span class="sxs-lookup"><span data-stu-id="06eb8-103">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="06eb8-104">特定の組織のインフラストラクチャを設計する場合は、app-v management Server をインストールするコンピューター以外のコンピューターに、App-v 管理 Web サービスをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="06eb8-104">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="06eb8-105">これらの App-v コンポーネントを分離する一般的な理由には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="06eb8-105">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="06eb8-106">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="06eb8-106">Performance</span></span>

-   <span data-ttu-id="06eb8-107">信頼性</span><span class="sxs-lookup"><span data-stu-id="06eb8-107">Reliability</span></span>

-   <span data-ttu-id="06eb8-108">対象</span><span class="sxs-lookup"><span data-stu-id="06eb8-108">Availability</span></span>

-   <span data-ttu-id="06eb8-109">スケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="06eb8-109">Scalability</span></span>

<span data-ttu-id="06eb8-110">管理サーバーと管理 Web サービスを分離するには、インフラストラクチャが正常に動作するために追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="06eb8-110">Separating the Management Server and Management Web Service requires additional configuration for the infrastructure to operate correctly.</span></span> <span data-ttu-id="06eb8-111">これらの2つの機能を分離しても、このトピックで説明する手順を実行しない場合、管理コンソールは管理 Web サービスに接続しますが、データストアで適切に認証することはできません。</span><span class="sxs-lookup"><span data-stu-id="06eb8-111">When you separate these two features but do not complete the procedures described in this topic, the Management Console will connect to the Management Web Service but will not be able to properly authenticate with the data store.</span></span> <span data-ttu-id="06eb8-112">管理コンソールが正しく読み込まれず、管理者が管理タスクをすべて実行できなくなります。</span><span class="sxs-lookup"><span data-stu-id="06eb8-112">The Management Console will not load properly, and the administrator will not be able to complete any administrative tasks.</span></span>

<span data-ttu-id="06eb8-113">この動作が発生するのは、管理 Web サービスが管理コンソールから渡された資格情報を使用してデータストアにアクセスできないためです。</span><span class="sxs-lookup"><span data-stu-id="06eb8-113">This behavior occurs because the Management Web Service cannot use the credentials, passed to it from the Management Console, to access the data store.</span></span> <span data-ttu-id="06eb8-114">この解決策は、管理 Web サービスサーバーが委任に対して信頼されるように構成することです。</span><span class="sxs-lookup"><span data-stu-id="06eb8-114">The solution is to configure the Management Web Service server to be “Trusted for delegation.”</span></span>

## <span data-ttu-id="06eb8-115">Active Directory ドメインサービスの構成</span><span class="sxs-lookup"><span data-stu-id="06eb8-115">Configuring Active Directory Domain Services</span></span>


<span data-ttu-id="06eb8-116">また、分散環境で動作するように Active Directory ドメインサービスを適切に構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06eb8-116">It is also necessary to configure Active Directory Domain Services properly to work in a distributed environment.</span></span> <span data-ttu-id="06eb8-117">このセクションには、Active Directory ドメインサービスを構成する必要がある情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="06eb8-117">This section includes the information you need configure Active Directory Domain Services.</span></span>

### <span data-ttu-id="06eb8-118">SQL サービスがローカルシステムアカウントを使用している場合</span><span class="sxs-lookup"><span data-stu-id="06eb8-118">When SQL Service Uses Local System account</span></span>

<span data-ttu-id="06eb8-119">SQL サービスがローカルシステムアカウントを使用している環境をセットアップするには、委任に対して信頼されるように、管理 Web サービスのコンピューターアカウントのプロパティを変更します。</span><span class="sxs-lookup"><span data-stu-id="06eb8-119">To set up the environment where the SQL Service uses the local system account, change the properties of the machine account of the Management Web Service to be trusted for delegation.</span></span> <span data-ttu-id="06eb8-120">この方法の詳細な手順については、「[委任に対して信頼されるようにサーバーを構成する方法](how-to-configure-the-server-to-be-trusted-for-delegation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="06eb8-120">For detailed procedures about how to do this, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md)</span></span>

### <span data-ttu-id="06eb8-121">SQL サービスでドメインベースのアカウントを使用している場合</span><span class="sxs-lookup"><span data-stu-id="06eb8-121">When SQL Service Uses Domain-Based Account</span></span>

<span data-ttu-id="06eb8-122">SQL Server がドメインベースのサービスアカウントを使用する環境をセットアップするには、次のようなさまざまな要因が適用されるかどうかを検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06eb8-122">To set up the environment where SQL Servers use domain-based service accounts, you need to consider whether or not a variety of factors apply, including the following:</span></span>

-   <span data-ttu-id="06eb8-123">SQL Server のクラスタリング</span><span class="sxs-lookup"><span data-stu-id="06eb8-123">Clustering of SQL Server</span></span>

-   <span data-ttu-id="06eb8-124">レプリケーション</span><span class="sxs-lookup"><span data-stu-id="06eb8-124">Replication</span></span>

-   <span data-ttu-id="06eb8-125">自動化されたタスク</span><span class="sxs-lookup"><span data-stu-id="06eb8-125">Automated tasks</span></span>

-   <span data-ttu-id="06eb8-126">リンクサーバー</span><span class="sxs-lookup"><span data-stu-id="06eb8-126">Linked servers</span></span>

<span data-ttu-id="06eb8-127">SQL サービスがドメインベースのアカウントを使用している場合の Active Directory ドメインサービスの構成の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151968> 。</span><span class="sxs-lookup"><span data-stu-id="06eb8-127">For information about configuring Active Directory Domain Services when the SQL service uses a domain-based account, see <https://go.microsoft.com/fwlink/?LinkId=151968>.</span></span>

 

 





