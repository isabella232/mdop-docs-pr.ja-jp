---
title: MBAM 2.5 から MBAM 2.5 SP1 サービスリリース更新プログラムのアップグレード
author: dansimp
ms.author: ksharma
manager: miaposto
audience: ITPro
ms.topic: article
ms.prod: w10
ms.localizationpriority: Normal
ms.openlocfilehash: 372822e1ec049871c62af9f429290b88bbfac949
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812770"
---
# <span data-ttu-id="90287-102">MBAM 2.5 から MBAM 2.5 SP1 サービスリリース更新プログラムをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="90287-102">Upgrade from MBAM 2.5 to MBAM 2.5 SP1 Servicing Release Update</span></span>

<span data-ttu-id="90287-103">この記事では、Microsoft BitLocker の管理と監視 (MBAM) 2.5 から MBAM 2.5 Service Pack 1 (SP1) と、 [Microsoft デスクトップ最適化パック (MDOP)](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)を併用して、スタンドアロン構成での2019サービス更新を行う方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90287-103">This article provides step-by-step instructions to upgrade Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 to MBAM 2.5 Service Pack 1 (SP1) together with the [Microsoft Desktop Optimization Pack (MDOP) May 2019 servicing update](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack) in a standalone configuration.</span></span>

<span data-ttu-id="90287-104">このガイドでは、2サーバー構成を使用します。</span><span class="sxs-lookup"><span data-stu-id="90287-104">In this guide, we will use a two-server configuration.</span></span> <span data-ttu-id="90287-105">1つのサーバーは、Microsoft SQL Server 2016 を実行しているデータベースサーバーになります。</span><span class="sxs-lookup"><span data-stu-id="90287-105">One server will be a database server that's running Microsoft SQL Server 2016.</span></span> <span data-ttu-id="90287-106">このサーバーは、MBAM データベースとレポートをホストします。</span><span class="sxs-lookup"><span data-stu-id="90287-106">This server will host the MBAM databases and reports.</span></span> <span data-ttu-id="90287-107">他のサーバーは Windows Server 2012 R2 web サーバーになります。</span><span class="sxs-lookup"><span data-stu-id="90287-107">The other server will be a Windows Server 2012 R2 web server.</span></span> <span data-ttu-id="90287-108">このサーバーは、"管理と監視" と "セルフサービスポータル" をホストします。</span><span class="sxs-lookup"><span data-stu-id="90287-108">This server will host "Administration and Monitoring" and "Self-Service Portal."</span></span>

## <span data-ttu-id="90287-109">MBAM 2.5 SP1 のアップグレードの準備をする</span><span class="sxs-lookup"><span data-stu-id="90287-109">Prepare to upgrade MBAM 2.5 SP1</span></span>

### <span data-ttu-id="90287-110">環境内の MBAM サーバーを把握する</span><span class="sxs-lookup"><span data-stu-id="90287-110">Know the MBAM servers in your environment</span></span>

1. <span data-ttu-id="90287-111">SQL Server データベースエンジン: MBAM データベースをホストするサーバー。</span><span class="sxs-lookup"><span data-stu-id="90287-111">SQL Server Database Engine: Server that hosts the MBAM databases.</span></span>
2. <span data-ttu-id="90287-112">SQL Server Reporting Services: MBAM レポートをホストするサーバー。</span><span class="sxs-lookup"><span data-stu-id="90287-112">SQL Server Reporting Services: Server that hosts the MBAM reports.</span></span>
3. <span data-ttu-id="90287-113">インターネットインフォメーションサービス (IIS) web サーバー: MBAM Web アプリケーションと MBAM サービスをホストするサーバー。</span><span class="sxs-lookup"><span data-stu-id="90287-113">Internet Information Services (IIS) web servers: Server that hosts MBAM Web Applications and MBAM services.</span></span>
4. <span data-ttu-id="90287-114">省略Microsoft System Center Configuration Manager プライマリサイトサーバー: MBAM 構成アプリケーションは、このサーバー上で実行され、MBAM レポートを Configuration Manager に統合します。</span><span class="sxs-lookup"><span data-stu-id="90287-114">(Optional) Microsoft System Center Configuration Manager primary site server: The MBAM configuration application is run on this server to integrate MBAM reports with Configuration Manager.</span></span> <span data-ttu-id="90287-115">これらのレポートは、Configuration Manager SQL Server Reporting Services (SSRS) インスタンスの既存の Configuration Manager レポートにマージされます。</span><span class="sxs-lookup"><span data-stu-id="90287-115">These reports are then merged with existing Configuration Manager reports on the Configuration Manager SQL Server Reporting Services (SSRS) instance.</span></span>

### <span data-ttu-id="90287-116">サービスアカウント、グループ、サーバー名、およびレポート URL を特定する</span><span class="sxs-lookup"><span data-stu-id="90287-116">Identify service accounts, groups, server name, and reports URL</span></span>

1. <span data-ttu-id="90287-117">IIS web サーバーで MBAM データベースへのデータの読み取りと書き込みのために使用される MBAM アプリケーションプールサービスアカウントを特定します。</span><span class="sxs-lookup"><span data-stu-id="90287-117">Identify the MBAM application pool service account that's used by IIS web servers to read and write data to MBAM databases.</span></span>
2. <span data-ttu-id="90287-118">MBAM web 機能の構成およびレポート web サービスの URL で使用されるグループを特定します。</span><span class="sxs-lookup"><span data-stu-id="90287-118">Identify the groups that are used during the MBAM web features configuration and the reports web service URL.</span></span>
3. <span data-ttu-id="90287-119">SQL Server 名とインスタンス名を確認します。</span><span class="sxs-lookup"><span data-stu-id="90287-119">Identify the SQL Server name and instance name.</span></span> <span data-ttu-id="90287-120">詳細については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90287-120">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ANP1]

4. <span data-ttu-id="90287-121">コンプライアンスデータおよび監査データベースからコンプライアンスデータを読み取るために使用される SQL Server Reporting Services アカウントを特定します。</span><span class="sxs-lookup"><span data-stu-id="90287-121">Identify the SQL Server Reporting Services Account that's used for reading compliance data from the Compliance and Audit database.</span></span> <span data-ttu-id="90287-122">詳細については、このビデオをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="90287-122">Watch this video to learn more.</span></span>

    > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALdZ]

## <span data-ttu-id="90287-123">MBAM インフラストラクチャを最新バージョンにアップグレードする</span><span class="sxs-lookup"><span data-stu-id="90287-123">Upgrade the MBAM infrastructure to the latest version available</span></span>

<span data-ttu-id="90287-124">MBAM サーバーインフラストラクチャのインストールまたはアップグレードは、以下に示す順番で実行されます。</span><span class="sxs-lookup"><span data-stu-id="90287-124">MBAM Server infrastructure installation or upgrade is always performed in the order listed below:</span></span>

- <span data-ttu-id="90287-125">SQL Server データベースエンジン: データベース</span><span class="sxs-lookup"><span data-stu-id="90287-125">SQL Server Database Engine: Databases</span></span>
- <span data-ttu-id="90287-126">SQL Server Reporting Services: レポート</span><span class="sxs-lookup"><span data-stu-id="90287-126">SQL Server Reporting Services: Reports</span></span>
- <span data-ttu-id="90287-127">Web サーバー: Web アプリケーション</span><span class="sxs-lookup"><span data-stu-id="90287-127">Web Server: Web Applications</span></span>
- <span data-ttu-id="90287-128">SCCM サーバー: SCCM 統合レポート (該当する場合)</span><span class="sxs-lookup"><span data-stu-id="90287-128">SCCM Server: SCCM Integrated Reports if applicable</span></span>
- <span data-ttu-id="90287-129">クライアント: MBAM エージェントまたはクライアント更新プログラム</span><span class="sxs-lookup"><span data-stu-id="90287-129">Clients: MBAM Agent or Client Update</span></span>
- <span data-ttu-id="90287-130">グループポリシーテンプレート: 新しいテンプレートを使用して既存のグループポリシーを更新し、既存の MBAM グループポリシーの新しい設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="90287-130">Group Policy Templates: Update the existing Group Policy with new templates and enable new settings on existing MBAM Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="90287-131">アップグレードを実行する前に、MBAM データベースのデータベース全体のバックアップを作成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="90287-131">We recommend that you create a full database backup of the MBAM databases before you run the upgrades.</span></span>

### <span data-ttu-id="90287-132">MBAM SQL Server をアップグレードする</span><span class="sxs-lookup"><span data-stu-id="90287-132">Upgrade the MBAM SQL Server</span></span>

<span data-ttu-id="90287-133">このビデオでは、MBAM SQL Server をアップグレードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="90287-133">Watch this video to learn how to upgrade the MBAM SQL Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALew]

### <span data-ttu-id="90287-134">MBAM Web サーバーをアップグレードする</span><span class="sxs-lookup"><span data-stu-id="90287-134">Upgrade the MBAM Web Server</span></span>

<span data-ttu-id="90287-135">このビデオを見て、MBAM Web サーバーをアップグレードする方法を学習してください。</span><span class="sxs-lookup"><span data-stu-id="90287-135">Watch this video to learn how to upgrade the MBAM Web Server:</span></span>

   > [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE3ALex]

## <span data-ttu-id="90287-136">詳細情報</span><span class="sxs-lookup"><span data-stu-id="90287-136">More information</span></span>

<span data-ttu-id="90287-137">MBAM 2.5 SP1 の既知の問題の詳細については、「 [mbam 2.5 sp1 のリリースノート](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="90287-137">For more information about known issues in MBAM 2.5 SP1, see [Release Notes for MBAM 2.5 SP1](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/release-notes-for-mbam-25-sp1).</span></span>
