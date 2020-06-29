---
title: MED-V インスタンスの数を特定する
description: MED-V インスタンスの数を特定する
author: dansimp
ms.assetid: edea9bdf-a28c-4d24-9298-7bd6536c3a94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22f7d54318d2dc489461474e5531c5162d8c087d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824257"
---
# <span data-ttu-id="83ea5-103">MED-V インスタンスの数を特定する</span><span class="sxs-lookup"><span data-stu-id="83ea5-103">Identify the Number of MED-V Instances</span></span>


<span data-ttu-id="83ea5-104">サーバーインフラストラクチャを設計するには、MED-V インスタンスの数を決定し、各インスタンスのスコープを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-104">You need to determine the number of MED-V instances, as well as define the scope for each instance so that you can design the server infrastructure.</span></span> <span data-ttu-id="83ea5-105">MED インスタンスには、次の内容が含まれます。</span><span class="sxs-lookup"><span data-stu-id="83ea5-105">A MED-V instance includes the following:</span></span>

-   <span data-ttu-id="83ea5-106">Active Directory のアクセス許可など、サーバーに保存されている MED-V サーバーと MED-V ワークスペース。</span><span class="sxs-lookup"><span data-stu-id="83ea5-106">The MED-V server and the MED-V workspaces stored on the server, including Active Directory permissions.</span></span>

-   <span data-ttu-id="83ea5-107">クライアントイベントを格納する SQL Server データベース。</span><span class="sxs-lookup"><span data-stu-id="83ea5-107">A SQL Server database that stores client events.</span></span> <span data-ttu-id="83ea5-108">データベースが複数の MED-V インスタンスで共有されている可能性があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-108">The database may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="83ea5-109">パックされた MED イメージのイメージリポジトリ。</span><span class="sxs-lookup"><span data-stu-id="83ea5-109">The image repository for the packed MED-V images.</span></span> <span data-ttu-id="83ea5-110">リポジトリは、複数の MED-V インスタンスで共有される場合があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-110">The repository may be shared by multiple MED-V instances.</span></span>

-   <span data-ttu-id="83ea5-111">画像の作成とパック、および MED-V ワークスペースの作成に使われる管理コンソール。</span><span class="sxs-lookup"><span data-stu-id="83ea5-111">The management console used to create and pack images and to create MED-V workspaces.</span></span> <span data-ttu-id="83ea5-112">コンソールは、複数の MED-V インスタンスで同時に使うことはできませんが、1つの MED-V サーバーから切断してから、別の MED-V サーバーに接続することができます。</span><span class="sxs-lookup"><span data-stu-id="83ea5-112">The console cannot be used simultaneously by multiple MED-V instances, but it can be disconnected from one MED-V server and then connected to a different MED-V server.</span></span>

-   <span data-ttu-id="83ea5-113">MED-V ワークスペースを受け取る MED-V クライアントと、それらを使用するための承認をサーバーから取得します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-113">MED-V clients that receive MED-V workspaces, and authorization to use them, from the server.</span></span>

<span data-ttu-id="83ea5-114">別の MED インスタンスは、MED-V ワークスペースの統合や共有を行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="83ea5-114">Separate MED-V instances cannot be integrated or share MED-V workspaces.</span></span> <span data-ttu-id="83ea5-115">そのため、各追加のインスタンスは仮想化管理を decentralizes します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-115">Therefore, each additional instance decentralizes the virtualization management.</span></span>

## <span data-ttu-id="83ea5-116">必要な MED-V インスタンスの数を決定する</span><span class="sxs-lookup"><span data-stu-id="83ea5-116">Determine the Number of MED-V Instances Required</span></span>


<span data-ttu-id="83ea5-117">まず、MED-V インスタンスを1つ使用していることを前提とします。</span><span class="sxs-lookup"><span data-stu-id="83ea5-117">Start by assuming you are using one MED-V instance.</span></span> <span data-ttu-id="83ea5-118">次に、以下の条件を考慮して、インフラストラクチャに適用される各条件についてその他のインスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-118">Then, consider the following conditions, and add additional instances for each condition that applies to your infrastructure.</span></span>

-   <span data-ttu-id="83ea5-119">サポートされているユーザーの数。各 MED-V インスタンスは、最大5000の同時アクティブクライアントをサポートできます。</span><span class="sxs-lookup"><span data-stu-id="83ea5-119">Number of supported users—Each MED-V instance can support up to 5,000 concurrently active clients.</span></span> <span data-ttu-id="83ea5-120">同時アクティブとは、クライアントが、MED-V サーバーを使用してオンラインになっていて、ポリシーおよびイメージの更新、およびイベントに対して投票をサーバーに送信することを意味します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-120">Concurrently active means the client is online with the MED-V server and sending polls to the server for policy and image updates, as well as events.</span></span> <span data-ttu-id="83ea5-121">インフラストラクチャに5000を超えるアクティブユーザーが含まれている場合は、5000ユーザーごとに1つのインスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-121">If your infrastructure will include more than 5,000 active users, add one instance for every 5,000 users.</span></span>

-   <span data-ttu-id="83ea5-122">信頼されていないドメインのユーザー: MED-V サーバーは、Active Directory ユーザーやグループに対して、MED-V ワークスペースのアクセス許可を関連付けます。</span><span class="sxs-lookup"><span data-stu-id="83ea5-122">Users in untrusted domains—The MED-V server associates MED-V workspace permissions with Active Directory users and/or groups.</span></span> <span data-ttu-id="83ea5-123">これを行うには、med-v サーバーの信頼境界内に MED-V ユーザーが存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-123">This requires MED-V users to exist within the trust boundary of the MED-V server.</span></span> <span data-ttu-id="83ea5-124">独立した信頼されていないドメイン内の MED-V ユーザーのグループごとに、1つの MED-V インスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-124">Add one MED-V instance for each group of MED-V users that is in a separate, untrusted domain.</span></span>

-   <span data-ttu-id="83ea5-125">分離ネットワークのクライアント: 分離されたネットワーク内にクライアントが存在するかどうかを確認します。そのため、別の MED-V インスタンスが必要です。</span><span class="sxs-lookup"><span data-stu-id="83ea5-125">Clients in isolated networks—Determine whether any clients reside in networks that are isolated and therefore require a separate MED-V instance.</span></span> <span data-ttu-id="83ea5-126">たとえば、多くの場合、組織は運用ネットワークからラボネットワークを分離します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-126">For example, organizations often isolate lab networks from production networks.</span></span> <span data-ttu-id="83ea5-127">MED-V クライアントを含む、分離された各ネットワークの MED-V インスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-127">Add a MED-V instance for each isolated network that will contain MED-V clients.</span></span>

-   <span data-ttu-id="83ea5-128">組織の要件: 組織では、機密性の高いアプリケーションを、ドメイン内の制限されたユーザーのセットのみに配信する場合など、セキュリティ上の理由により、個別の MED インスタンスで管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-128">Organizational requirements—The organization may require that a group of clients be managed by a separate MED-V instance for security reasons, such as when sensitive applications are delivered only to a restricted set of users within a domain.</span></span> <span data-ttu-id="83ea5-129">たとえば、payroll 部門は、他の部門のユーザーに対して、給与処理のポリシーが保存されている MED-V インスタンスへのアクセスを拒否する場合があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-129">For example, the payroll department may deny users from other departments access to the MED-V instance that stores policy for payroll processing.</span></span> <span data-ttu-id="83ea5-130">さらに、組織で分散管理モデルを使用している場合、専用の仮想環境を管理するために、MED-V クライアントを持つ各ビジネスグループに個別の MED-V インスタンスが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-130">Additionally, if the organization uses a distributed management model, a separate MED-V instance may be required for each business group having MED-V clients in order to enable the group to manage its own virtualized environment.</span></span> <span data-ttu-id="83ea5-131">各組織の要件に対して、1つの MED-V インスタンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-131">Add one MED-V instance for each separate organizational requirement.</span></span>

-   <span data-ttu-id="83ea5-132">法律上の考慮事項: 米国のセキュリティやプライバシーの問題、および fiduciary 法では、特定のデータを分離する必要がある場合や、その他のデータが国境を越えている場合があります。</span><span class="sxs-lookup"><span data-stu-id="83ea5-132">Legal considerations—National security or privacy issues and fiduciary laws could require the separation of certain data or prevent other data from crossing national borders.</span></span> <span data-ttu-id="83ea5-133">必要に応じて、追加の MED-V インスタンスを追加して、このニーズに対処します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-133">If necessary, add additional MED-V instances to address this need.</span></span>

<span data-ttu-id="83ea5-134">インフラストラクチャに必要な MED-V インスタンスの数と、それぞれの理由を決定したら、各インスタンスの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="83ea5-134">After you determine the number of MED-V instances required for your infrastructure, as well as the reasoning for each one, provide a name for each instance.</span></span>

 

 





