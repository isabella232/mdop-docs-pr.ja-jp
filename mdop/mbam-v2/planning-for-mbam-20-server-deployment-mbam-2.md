---
title: MBAM 2.0 サーバーの展開計画
description: MBAM 2.0 サーバーの展開計画
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812611"
---
# <span data-ttu-id="bf813-103">MBAM 2.0 サーバーの展開計画</span><span class="sxs-lookup"><span data-stu-id="bf813-103">Planning for MBAM 2.0 Server Deployment</span></span>


<span data-ttu-id="bf813-104">Microsoft BitLocker の管理と監視 (MBAM) サーバーインフラストラクチャは、企業の要件に基づいて1つまたは複数のサーバーコンピューターにインストールできるサーバー機能のセットによって異なります。</span><span class="sxs-lookup"><span data-stu-id="bf813-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="bf813-105">Configuration Manager トポロジを使用して Microsoft BitLocker の管理と監視をインストールする場合は、「 [Configuration manager を使用して MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf813-105">If you are installing Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="bf813-106">**注** 1台のサーバーでの Microsoft BitLocker 管理と監視のインストールは、テスト環境でのみお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf813-106">**Note** Installations of Microsoft BitLocker Administration and Monitoring on a single server are recommended only for test environments.</span></span>

 

## <span data-ttu-id="bf813-107">MBAM サーバー展開の計画</span><span class="sxs-lookup"><span data-stu-id="bf813-107">Planning for MBAM Server Deployment</span></span>


<span data-ttu-id="bf813-108">MBAM サーバー展開用のインフラストラクチャには、次の機能が含まれます。</span><span class="sxs-lookup"><span data-stu-id="bf813-108">The infrastructure for an MBAM Server deployment includes the following features:</span></span>

-   <span data-ttu-id="bf813-109">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="bf813-109">Recovery Database</span></span>

-   <span data-ttu-id="bf813-110">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="bf813-110">Compliance and Audit Database</span></span>

-   <span data-ttu-id="bf813-111">コンプライアンスと監査レポート</span><span class="sxs-lookup"><span data-stu-id="bf813-111">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="bf813-112">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="bf813-112">Self-Service Portal</span></span>

-   <span data-ttu-id="bf813-113">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="bf813-113">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="bf813-114">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="bf813-114">MBAM Group Policy Template</span></span>

<span data-ttu-id="bf813-115">MBAM Server データベースと機能は、スケーラビリティ要件に応じて、さまざまな構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bf813-115">MBAM Server databases and features can be installed in different configurations, depending on your scalability requirements.</span></span> <span data-ttu-id="bf813-116">すべての MBAM Server 機能は1台のサーバーにインストールすることも、複数のサーバーに分散することもできます。</span><span class="sxs-lookup"><span data-stu-id="bf813-116">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="bf813-117">2 ~ 4 台のサーバーの構成をコンピューターの要件に応じて使うこともできますが、運用環境には 2 server 構成を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bf813-117">We recommend that you use a two-server configuration for production environments, although configurations of two to four servers can also be used, depending on your computing requirements.</span></span>

<span data-ttu-id="bf813-118">各 MBAM 機能には、特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="bf813-118">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="bf813-119">サーバー機能の前提条件とハードウェアとソフトウェアの要件の一覧については、「 [mbam 2.0 の展開に関する前提条件](mbam-20-deployment-prerequisites-mbam-2.md)と[Mbam 2.0 でサポートされている構成](mbam-20-supported-configurations-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf813-119">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>

<span data-ttu-id="bf813-120">サーバー関連の MBAM 機能に加えて、サーバーセットアップアプリケーションには MBAM グループポリシーテンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf813-120">In addition to the server-related MBAM features, the Server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="bf813-121">このテンプレートには、エンタープライズでの BitLocker ドライブ暗号化を管理するように構成したグループポリシーオブジェクト (GPO) の設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="bf813-121">The template contains Group Policy Object (GPO) settings that you configure to manage BitLocker Drive Encryption in the enterprise.</span></span> <span data-ttu-id="bf813-122">このテンプレートは、グループポリシー管理コンソール (GPMC) または高度なグループポリシー管理 (AGPM) を実行できる任意のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bf813-122">You can install this template on any computer that can run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="bf813-123">MBAM サーバーの展開を計画するときには、MBAM の BitLocker 回復キーは1回だけ使用することをお勧めします。その後、回復キーの有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="bf813-123">As you plan the MBAM Server deployment, consider that BitLocker recovery keys in MBAM are intended for single use only, after which recovery keys expire.</span></span> <span data-ttu-id="bf813-124">使用後にキーの有効期限が切れるようにするには、ヘルプデスクポータルまたはセルフサービスポータルを使用してキーを取得する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf813-124">In order for the keys to expire after use, they must be retrieved through the Help Desk Portal or the Self-Service Portal.</span></span>

## <span data-ttu-id="bf813-125">MBAM Server 機能の展開の順序</span><span class="sxs-lookup"><span data-stu-id="bf813-125">Order of Deployment of MBAM Server Features</span></span>


<span data-ttu-id="bf813-126">複数のサーバーに MBAM 機能を導入するには、次の順序で機能をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf813-126">To deploy MBAM features on multiple servers, you have to install the features in the following order:</span></span>

1.  <span data-ttu-id="bf813-127">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="bf813-127">Recovery Database</span></span>

2.  <span data-ttu-id="bf813-128">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="bf813-128">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="bf813-129">コンプライアンス監査とレポート</span><span class="sxs-lookup"><span data-stu-id="bf813-129">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="bf813-130">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="bf813-130">Self-Service Portal</span></span>

5.  <span data-ttu-id="bf813-131">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="bf813-131">Administration and Monitoring Server</span></span>

6.  <span data-ttu-id="bf813-132">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="bf813-132">MBAM Group Policy Template</span></span>

<span data-ttu-id="bf813-133">**注** 各機能をインストールするコンピューターの名前を把握しておきます。</span><span class="sxs-lookup"><span data-stu-id="bf813-133">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="bf813-134">この情報は、インストールプロセス全体で使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bf813-134">You have to use this information throughout the installation process.</span></span> <span data-ttu-id="bf813-135">この作業に役立てるために、展開チェックリストを印刷して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="bf813-135">You can print and use a deployment checklist to assist in this effort.</span></span> <span data-ttu-id="bf813-136">MBAM 展開チェックリストの詳細については、「 [mbam 2.0 の展開チェックリスト](mbam-20-deployment-checklist-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bf813-136">For more information about the MBAM Deployment Checklist, see [MBAM 2.0 Deployment Checklist](mbam-20-deployment-checklist-mbam-2.md).</span></span>

 

## <span data-ttu-id="bf813-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bf813-137">Related topics</span></span>


[<span data-ttu-id="bf813-138">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="bf813-138">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="bf813-139">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="bf813-139">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





