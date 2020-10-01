---
title: MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード
description: MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード
author: dansimp
ms.assetid: ''
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 2/16/2018
ms.openlocfilehash: 330ded822dd9da96a1c33eabcb31d744044dc28e
ms.sourcegitcommit: ae34c5cb5e7979b472b257a4691142e493d5d6fe
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/30/2020
ms.locfileid: "11091622"
---
# <span data-ttu-id="5cdee-103">MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="5cdee-103">Upgrading to MBAM 2.5 SP1 from MBAM 2.5</span></span>
<span data-ttu-id="5cdee-104">このトピックでは、Microsoft BitLocker 管理および監視 (MBAM) サーバー2.5 と MBAM クライアントを2.5 から MBAM 2.5 SP1 にアップグレードするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="5cdee-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 and the MBAM Client from 2.5 to MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="5cdee-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="5cdee-105">Before you begin</span></span>
#### <span data-ttu-id="5cdee-106">2019年5月のサービスリリースをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="5cdee-106">Download the May 2019 servicing release</span></span>
[<span data-ttu-id="5cdee-107">デスクトップ最適化パック</span><span class="sxs-lookup"><span data-stu-id="5cdee-107">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=58345)

#### <span data-ttu-id="5cdee-108">2018年7月のサービスリリースをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="5cdee-108">Download the July 2018 servicing release</span></span>
[<span data-ttu-id="5cdee-109">デスクトップ最適化パック</span><span class="sxs-lookup"><span data-stu-id="5cdee-109">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=57157)


#### <span data-ttu-id="5cdee-110">インストールドキュメントを確認する</span><span class="sxs-lookup"><span data-stu-id="5cdee-110">Verify the installation documentaion</span></span>
<span data-ttu-id="5cdee-111">すべてのサーバー名、データベース名、サービスアカウント、パスワードなど、MBAM 環境の最新ドキュメントがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5cdee-111">Verify you have a current documentation of your MBAM environment, including all server names, database names, service accounts and their passwords.</span></span>

### <span data-ttu-id="5cdee-112">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="5cdee-112">Upgrade steps</span></span>
#### <span data-ttu-id="5cdee-113">MBAM データベースのアップグレード手順 (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="5cdee-113">Steps to upgrade the MBAM Database (SQL Server)</span></span>
1. <span data-ttu-id="5cdee-114">MBAM コンフィギュレーターの使用SQL server または SSRS データベースがホストされている場所からレポートロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="5cdee-114">Using the MBAM Configurator; remove the Reports role from the SQL server, or wherever the SSRS database is hosted.</span></span> <span data-ttu-id="5cdee-115">使用している環境に応じて、同じサーバーまたは別のサーバーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="5cdee-115">Depending on your environment, this can be the same server or a separate one.</span></span>
  > [!NOTE]
  > <span data-ttu-id="5cdee-116">データベースを削除するオプションは表示されません。これは想定されています。</span><span class="sxs-lookup"><span data-stu-id="5cdee-116">You will not see an option to remove the Databases; this is expected.</span></span>  
2. <span data-ttu-id="5cdee-117">2.5 SP1 をインストールします (次に、ボリュームライセンスサービスセンターサイトから、MDOP-Microsoft デスクトップ最適化パック2015にあります)。</span><span class="sxs-lookup"><span data-stu-id="5cdee-117">Install 2.5 SP1(Located with MDOP - Microsoft Desktop Optimization Pack 2015 from the Volume Licensing Service Center site:</span></span>  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. <span data-ttu-id="5cdee-118">この時点で構成しない</span><span class="sxs-lookup"><span data-stu-id="5cdee-118">Do not configure it at this time</span></span> 
4. <span data-ttu-id="5cdee-119">MBAM コンフィギュレーターの使用レポートロールをもう一度追加する</span><span class="sxs-lookup"><span data-stu-id="5cdee-119">Using the MBAM Configurator; re-add the Reports role</span></span>
5. <span data-ttu-id="5cdee-120">MBAM コンフィギュレーターの使用sql Server の sql データベースロールを再追加する</span><span class="sxs-lookup"><span data-stu-id="5cdee-120">Using the MBAM Configurator; re-add the SQL Database role on the SQL Server</span></span>
6. <span data-ttu-id="5cdee-121">最後に、Db は既に存在し、作成されていないという警告が表示されますが、これは予期されています。</span><span class="sxs-lookup"><span data-stu-id="5cdee-121">At the end, you will be warned that the DBs already exist and  weren’t created, but this is expected</span></span>
7. <span data-ttu-id="5cdee-122">このプロセスにより、既存のデータベースがインストールされている現在のバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="5cdee-122">This process updates the existing databases to the current version being installed.</span></span>              

#### <span data-ttu-id="5cdee-123">MBAM サーバーをアップグレードする手順 (MBAM と IIS を実行している場合)</span><span class="sxs-lookup"><span data-stu-id="5cdee-123">Steps to upgrade the MBAM Server (Running MBAM and IIS)</span></span>
1. <span data-ttu-id="5cdee-124">MBAM コンフィギュレーターの使用IIS サーバーから管理者とセルフサービスポータルを削除する</span><span class="sxs-lookup"><span data-stu-id="5cdee-124">Using the MBAM Configurator; remove the Admin and Self Service Portals from  the IIS server</span></span>
2. <span data-ttu-id="5cdee-125">MBAM 2.5 SP1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="5cdee-125">Install MBAM 2.5 SP1</span></span>
3. <span data-ttu-id="5cdee-126">この時点で構成しない</span><span class="sxs-lookup"><span data-stu-id="5cdee-126">Do not configure it at this time</span></span>  
4. <span data-ttu-id="5cdee-127">MBAM コンフィギュレーターの使用管理者とセルフサービスポータルを IIS サーバーに再追加する</span><span class="sxs-lookup"><span data-stu-id="5cdee-127">Using the MBAM Configurator; re-add the Admin and Self Service Portals to the IIS server</span></span> 
5. <span data-ttu-id="5cdee-128">管理者特権でコマンドプロンプトを開き、「 **IISRESET**」と入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5cdee-128">Open an elevated command prompt, type **IISRESET**, and hit Enter.</span></span>
 
#### <span data-ttu-id="5cdee-129">MBAM クライアント/エンドポイントのアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="5cdee-129">Steps to upgrade the MBAM Clients/Endpoints</span></span>
1. <span data-ttu-id="5cdee-130">クライアントエンドポイントから2.5 エージェントをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="5cdee-130">Uninstall the 2.5 Agent from client endpoints</span></span>
2. <span data-ttu-id="5cdee-131">クライアントエンドポイントに 2.5 SP1 エージェントをインストールする</span><span class="sxs-lookup"><span data-stu-id="5cdee-131">Install the 2.5 SP1 Agent on the client endpoints</span></span>
3. <span data-ttu-id="5cdee-132">2.5 SP1 エージェントを実行しているクライアントに2019年5月のロールアップクライアント更新プログラムをプッシュする</span><span class="sxs-lookup"><span data-stu-id="5cdee-132">Push out the May 2019 Rollup Client update to clients running the 2.5 SP1 Agent</span></span> 
4. <span data-ttu-id="5cdee-133">2019年5月のロールアップをインストールする前に、既存のクライアントをアンインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="5cdee-133">There is no need to uninstall the existing client prior to installing the May 2019 Rollup.</span></span>  
