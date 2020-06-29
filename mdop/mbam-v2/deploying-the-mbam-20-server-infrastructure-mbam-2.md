---
title: MBAM 2.0 サーバー インフラストラクチャの展開
description: MBAM 2.0 サーバー インフラストラクチャの展開
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22a69fe8f6853c02a818bb026b36771cd09632f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824757"
---
# <span data-ttu-id="76aee-103">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="76aee-103">Deploying the MBAM 2.0 Server Infrastructure</span></span>


<span data-ttu-id="76aee-104">スタンドアロントポロジ用の Microsoft BitLocker 管理と監視 (MBAM) サーバー機能は、実稼働環境の2台以上のサーバー上のさまざまな構成でインストールできます。</span><span class="sxs-lookup"><span data-stu-id="76aee-104">Microsoft BitLocker Administration and Monitoring (MBAM) Server features for the Stand-alone topology can be installed in different configurations on two or more servers in a production environment.</span></span> <span data-ttu-id="76aee-105">推奨される構成は、スケーラビリティ要件に応じて、運用環境の2つのサーバーです。</span><span class="sxs-lookup"><span data-stu-id="76aee-105">The recommended configuration is two servers for a production environment, depending on your scalability requirements.</span></span> <span data-ttu-id="76aee-106">MBAM インストールでは、テスト環境でのみ単一のサーバーを使用します。</span><span class="sxs-lookup"><span data-stu-id="76aee-106">Use a single server for an MBAM installation only in test environments.</span></span> <span data-ttu-id="76aee-107">MBAM Server 機能の展開の計画について詳しくは、「 [mbam 2.0 サーバー展開の計画](planning-for-mbam-20-server-deployment-mbam-2.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="76aee-107">For more information about planning for the MBAM Server feature deployment, see [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md).</span></span>

<span data-ttu-id="76aee-108">次の図は、推奨される 2 server MBAM 展開を構成する方法の例を示しています。</span><span class="sxs-lookup"><span data-stu-id="76aee-108">The following diagram shows an example of how you can configure the recommended two-server MBAM deployment.</span></span> <span data-ttu-id="76aee-109">この構成では、運用環境で最大 20万 MBAM クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="76aee-109">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span> <span data-ttu-id="76aee-110">アーキテクチャイメージのサーバー機能とデータベースについては、次のセクションで説明しています。また、これらの機能をインストールすることをお勧めするコンピューターまたはサーバーの下に表示されています。</span><span class="sxs-lookup"><span data-stu-id="76aee-110">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

![mbam 2 2-サーバー展開トポロジ](images/mbam2-3-servers.gif)

## <span data-ttu-id="76aee-112">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="76aee-112">Administration and Monitoring Server</span></span>


<span data-ttu-id="76aee-113">このサーバーには、次の機能がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="76aee-113">The following features are installed on this server:</span></span>

-   <span data-ttu-id="76aee-114">**管理と監視サーバー**。</span><span class="sxs-lookup"><span data-stu-id="76aee-114">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="76aee-115">管理と監視のサーバー機能は Windows サーバーにインストールされ、ヘルプデスクの web サイトと監視 web サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="76aee-115">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Help Desk website and the monitoring web services.</span></span>

-   <span data-ttu-id="76aee-116">**セルフサービスポータル**。</span><span class="sxs-lookup"><span data-stu-id="76aee-116">**Self-Service Portal**.</span></span> <span data-ttu-id="76aee-117">セルフサービスポータルは Windows サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="76aee-117">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="76aee-118">セルフサービスポータルを使用すると、クライアントコンピューターのエンドユーザーが、ロックされた BitLocker ボリュームを回復するための回復キーを取得できる web サイトに個別にログオンできます。</span><span class="sxs-lookup"><span data-stu-id="76aee-118">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="76aee-119">データベースサーバー</span><span class="sxs-lookup"><span data-stu-id="76aee-119">Database Server</span></span>


<span data-ttu-id="76aee-120">このサーバーには、次の機能がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="76aee-120">The following features are installed on this server:</span></span>

-   <span data-ttu-id="76aee-121">**回復データベース**。</span><span class="sxs-lookup"><span data-stu-id="76aee-121">**Recovery Database**.</span></span> <span data-ttu-id="76aee-122">回復データベースは、Windows server とサポートされている Microsoft SQLServer のインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="76aee-122">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="76aee-123">このデータベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="76aee-123">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="76aee-124">**コンプライアンスと監査データベース**。</span><span class="sxs-lookup"><span data-stu-id="76aee-124">**Compliance and Audit Database**.</span></span> <span data-ttu-id="76aee-125">コンプライアンスと監査データベースは、Windows server とサポートされている SQLServer のインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="76aee-125">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="76aee-126">このデータベースには、MBAM クライアントコンピューターのコンプライアンスデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="76aee-126">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="76aee-127">このデータは、主に SQL Server Reporting Services (SSRS) ホストであるレポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="76aee-127">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="76aee-128">**コンプライアンスおよび監査レポート**。</span><span class="sxs-lookup"><span data-stu-id="76aee-128">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="76aee-129">コンプライアンスと監査レポートは、Windows server と、SQL Server Reporting Services (SSRS) 機能がインストールされている SQLServer のサポートされているインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="76aee-129">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="76aee-130">これらのレポートには、ヘルプデスクの web サイトから、または SSRS サーバーから直接アクセスできる MBAM レポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="76aee-130">These reports provide MBAM reports that you can access from the Help Desk website or directly from the SSRS server.</span></span>

## <span data-ttu-id="76aee-131">管理ワークステーション</span><span class="sxs-lookup"><span data-stu-id="76aee-131">Management Workstation</span></span>


<span data-ttu-id="76aee-132">以下の機能は管理ワークステーションにインストールされます。これは、Windows server またはクライアントコンピューターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="76aee-132">The following feature is installed on the Management Workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="76aee-133">**ポリシーテンプレート**。</span><span class="sxs-lookup"><span data-stu-id="76aee-133">**Policy Template**.</span></span> <span data-ttu-id="76aee-134">ポリシーテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループポリシーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="76aee-134">The Policy Template consists of Group Policies that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="76aee-135">ポリシーテンプレートは、任意のサーバーまたはワークステーションにインストールできますが、一般的には、サポートされている Windows サーバーまたはクライアントコンピューターである管理ワークステーションにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="76aee-135">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="76aee-136">ワークステーションは専用のコンピュータである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="76aee-136">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="76aee-137">MBAM クライアント</span><span class="sxs-lookup"><span data-stu-id="76aee-137">MBAM Client</span></span>


<span data-ttu-id="76aee-138">MBAM クライアントは Windows コンピューターにインストールされ、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="76aee-138">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="76aee-139">グループポリシーを使用して、企業内のクライアントコンピューターの BitLocker ドライブ暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="76aee-139">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="76aee-140">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="76aee-140">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="76aee-141">コンピューターのコンプライアンスデータを収集し、データをレポートシステムに渡します。</span><span class="sxs-lookup"><span data-stu-id="76aee-141">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="76aee-142">MBAM 2.0 サーバー機能の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="76aee-142">Other Resources for Deploying MBAM 2.0 Server Features</span></span>


[<span data-ttu-id="76aee-143">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="76aee-143">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





