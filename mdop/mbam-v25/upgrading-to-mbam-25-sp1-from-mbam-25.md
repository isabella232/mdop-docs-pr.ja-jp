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
ms.openlocfilehash: 19da3df0976b51700e0d10c302a31421a88d17e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812746"
---
# <span data-ttu-id="92a66-103">MBAM 2.5 から MBAM 2.5 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="92a66-103">Upgrading to MBAM 2.5 SP1 from MBAM 2.5</span></span>
<span data-ttu-id="92a66-104">このトピックでは、Microsoft BitLocker 管理および監視 (MBAM) サーバー2.5 と MBAM クライアントを2.5 から MBAM 2.5 SP1 にアップグレードするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92a66-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server 2.5 and the MBAM Client from 2.5 to MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="92a66-105">始める前に</span><span class="sxs-lookup"><span data-stu-id="92a66-105">Before you begin</span></span>
#### <span data-ttu-id="92a66-106">2019年5月のサービスリリースをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="92a66-106">Download the May 2019 servicing release</span></span>
[<span data-ttu-id="92a66-107">デスクトップ最適化パック</span><span class="sxs-lookup"><span data-stu-id="92a66-107">Desktop Optimization Pack</span></span>](https://www.microsoft.com/download/details.aspx?id=58345)

#### <span data-ttu-id="92a66-108">インストールドキュメントを確認する</span><span class="sxs-lookup"><span data-stu-id="92a66-108">Verify the installation documentaion</span></span>
<span data-ttu-id="92a66-109">すべてのサーバー名、データベース名、サービスアカウント、パスワードなど、MBAM 環境の最新ドキュメントがあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="92a66-109">Verify you have a current documentation of your MBAM environment, including all server names, database names, service accounts and their passwords.</span></span>

### <span data-ttu-id="92a66-110">アップグレード手順</span><span class="sxs-lookup"><span data-stu-id="92a66-110">Upgrade steps</span></span>
#### <span data-ttu-id="92a66-111">MBAM データベースのアップグレード手順 (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="92a66-111">Steps to upgrade the MBAM Database (SQL Server)</span></span>
1. <span data-ttu-id="92a66-112">MBAM コンフィギュレーターの使用SQL server または SSRS データベースがホストされている場所からレポートロールを削除します。</span><span class="sxs-lookup"><span data-stu-id="92a66-112">Using the MBAM Configurator; remove the Reports role from the SQL server, or wherever the SSRS database is hosted.</span></span> <span data-ttu-id="92a66-113">使用している環境に応じて、同じサーバーまたは別のサーバーにすることができます。</span><span class="sxs-lookup"><span data-stu-id="92a66-113">Depending on your environment, this can be the same server or a separate one.</span></span>
  > [!NOTE]
  > <span data-ttu-id="92a66-114">データベースを削除するオプションは表示されません。これは想定されています。</span><span class="sxs-lookup"><span data-stu-id="92a66-114">You will not see an option to remove the Databases; this is expected.</span></span>  
2. <span data-ttu-id="92a66-115">2.5 SP1 をインストールします (次に、ボリュームライセンスサービスセンターサイトから、MDOP-Microsoft デスクトップ最適化パック2015にあります)。</span><span class="sxs-lookup"><span data-stu-id="92a66-115">Install 2.5 SP1(Located with MDOP - Microsoft Desktop Optimization Pack 2015 from the Volume Licensing Service Center site:</span></span>  <https://www.microsoft.com/Licensing/servicecenter/default.aspx>
3. <span data-ttu-id="92a66-116">この時点で構成しない</span><span class="sxs-lookup"><span data-stu-id="92a66-116">Do not configure it at this time</span></span> 
4. <span data-ttu-id="92a66-117">MBAM コンフィギュレーターの使用レポートロールをもう一度追加する</span><span class="sxs-lookup"><span data-stu-id="92a66-117">Using the MBAM Configurator; re-add the Reports role</span></span>
5. <span data-ttu-id="92a66-118">MBAM コンフィギュレーターの使用sql Server の sql データベースロールを再追加する</span><span class="sxs-lookup"><span data-stu-id="92a66-118">Using the MBAM Configurator; re-add the SQL Database role on the SQL Server</span></span>
6. <span data-ttu-id="92a66-119">最後に、Db は既に存在し、作成されていないという警告が表示されますが、これは予期されています。</span><span class="sxs-lookup"><span data-stu-id="92a66-119">At the end, you will be warned that the DBs already exist and  weren’t created, but this is expected</span></span>
7. <span data-ttu-id="92a66-120">このプロセスにより、既存のデータベースがインストールされている現在のバージョンに更新されます。</span><span class="sxs-lookup"><span data-stu-id="92a66-120">This process updates the existing databases to the current version being installed.</span></span>              

#### <span data-ttu-id="92a66-121">MBAM サーバーをアップグレードする手順 (MBAM と IIS を実行している場合)</span><span class="sxs-lookup"><span data-stu-id="92a66-121">Steps to upgrade the MBAM Server (Running MBAM and IIS)</span></span>
1. <span data-ttu-id="92a66-122">MBAM コンフィギュレーターの使用IIS サーバーから管理者とセルフサービスポータルを削除する</span><span class="sxs-lookup"><span data-stu-id="92a66-122">Using the MBAM Configurator; remove the Admin and Self Service Portals from  the IIS server</span></span>
2. <span data-ttu-id="92a66-123">MBAM 2.5 SP1 をインストールする</span><span class="sxs-lookup"><span data-stu-id="92a66-123">Install MBAM 2.5 SP1</span></span>
3. <span data-ttu-id="92a66-124">この時点で構成しない</span><span class="sxs-lookup"><span data-stu-id="92a66-124">Do not configure it at this time</span></span>  
4. <span data-ttu-id="92a66-125">MBAM コンフィギュレーターの使用管理者とセルフサービスポータルを IIS サーバーに再追加する</span><span class="sxs-lookup"><span data-stu-id="92a66-125">Using the MBAM Configurator; re-add the Admin and Self Service Portals to the IIS server</span></span> 
5. <span data-ttu-id="92a66-126">管理者特権でコマンドプロンプトを開き、「 **IISRESET**」と入力して、Enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="92a66-126">Open an elevated command prompt, type **IISRESET**, and hit Enter.</span></span>
 
#### <span data-ttu-id="92a66-127">MBAM クライアント/エンドポイントのアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="92a66-127">Steps to upgrade the MBAM Clients/Endpoints</span></span>
1. <span data-ttu-id="92a66-128">クライアントエンドポイントから2.5 エージェントをアンインストールする</span><span class="sxs-lookup"><span data-stu-id="92a66-128">Uninstall the 2.5 Agent from client endpoints</span></span>
2. <span data-ttu-id="92a66-129">クライアントエンドポイントに 2.5 SP1 エージェントをインストールする</span><span class="sxs-lookup"><span data-stu-id="92a66-129">Install the 2.5 SP1 Agent on the client endpoints</span></span>
3. <span data-ttu-id="92a66-130">2.5 SP1 エージェントを実行しているクライアントに2019年5月のロールアップクライアント更新プログラムをプッシュする</span><span class="sxs-lookup"><span data-stu-id="92a66-130">Push out the May 2019 Rollup Client update to clients running the 2.5 SP1 Agent</span></span> 
4. <span data-ttu-id="92a66-131">2019年5月のロールアップをインストールする前に、既存のクライアントをアンインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="92a66-131">There is no need to uninstall the existing client prior to installing the May 2019 Rollup.</span></span>  
