---
title: MBAM 2.0 のアーキテクチャの概要
description: MBAM 2.0 のアーキテクチャの概要
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824704"
---
# <span data-ttu-id="67b9b-103">MBAM 2.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="67b9b-103">High-Level Architecture for MBAM 2.0</span></span>


<span data-ttu-id="67b9b-104">Microsoft BitLocker の管理と監視 (MBAM) は、BitLocker のプロビジョニングと展開を簡素化し、BitLocker に関するコンプライアンスとレポートを向上させ、サポートのコストを削減するために使用できるクライアント/サーバーソリューションです。</span><span class="sxs-lookup"><span data-stu-id="67b9b-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server solution that can help you simplify BitLocker provisioning and deployment, improve compliance and reporting on BitLocker, and reduce support costs.</span></span> <span data-ttu-id="67b9b-105">Microsoft BitLocker の管理と監視には、このトピックで説明する機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-105">Microsoft BitLocker Administration and Monitoring includes the features that are described in this topic.</span></span>

<span data-ttu-id="67b9b-106">Microsoft BitLocker の管理と監視は、スタンドアロントポロジまたは Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager と統合されたトポロジに展開できます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-106">Microsoft BitLocker Administration and Monitoring can be deployed in the Stand-alone topology, or in a topology that is integrated with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="67b9b-107">このトピックでは、スタンドアロントポロジのアーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="67b9b-107">This topic describes the architecture for the Stand-alone topology.</span></span> <span data-ttu-id="67b9b-108">統合構成マネージャートポロジでの展開について詳しくは、「 [MBAM と構成マネージャーを使用する](using-mbam-with-configuration-manager.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="67b9b-108">For information about deploying in the integrated Configuration Manager topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

<span data-ttu-id="67b9b-109">次の図は、2つのサーバーと管理ワークステーションで構成される運用環境の MBAM 推奨アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-109">The following diagram shows the MBAM recommended architecture for a production environment, which consists of two servers and a management workstation.</span></span> <span data-ttu-id="67b9b-110">このアーキテクチャでは、最大 20万 MBAM クライアントがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-110">This architecture supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="67b9b-111">アーキテクチャイメージのサーバー機能とデータベースについては、次のセクションで説明しています。また、これらの機能をインストールすることをお勧めするコンピューターまたはサーバーの下に表示されています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-111">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

<span data-ttu-id="67b9b-112">**注** 単一サーバーアーキテクチャは、テスト環境でのみ使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67b9b-112">**Note** A single-server architecture should be used only in test environments.</span></span>

 

![mbam 2 2-サーバー展開トポロジ](images/mbam2-3-servers.gif)

## <span data-ttu-id="67b9b-114">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="67b9b-114">Administration and Monitoring Server</span></span>


<span data-ttu-id="67b9b-115">このサーバーには、次の機能がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-115">The following features are installed on this server:</span></span>

-   <span data-ttu-id="67b9b-116">**管理と監視サーバー**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-116">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="67b9b-117">管理と監視のサーバー機能は Windows サーバーにインストールされ、管理と監視の web サイトで構成されます。これには、レポート、ヘルプデスクポータル、および監視 web サービスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-117">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Administration and Monitoring website, which includes the reports and the Help Desk Portal, and the monitoring web services.</span></span>

-   <span data-ttu-id="67b9b-118">**セルフサービスポータル**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-118">**Self-Service Portal**.</span></span> <span data-ttu-id="67b9b-119">セルフサービスポータルは Windows サーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-119">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="67b9b-120">セルフサービスポータルを使用すると、クライアントコンピューターのエンドユーザーが、ロックされた BitLocker ボリュームを回復するための回復キーを取得できる web サイトに個別にログオンできます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-120">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="67b9b-121">データベースサーバー</span><span class="sxs-lookup"><span data-stu-id="67b9b-121">Database Server</span></span>


<span data-ttu-id="67b9b-122">このサーバーには、次の機能がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-122">The following features are installed on this server:</span></span>

-   <span data-ttu-id="67b9b-123">**回復データベース**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-123">**Recovery Database**.</span></span> <span data-ttu-id="67b9b-124">回復データベースは、Windows server とサポートされている Microsoft SQLServer のインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-124">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="67b9b-125">このデータベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-125">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="67b9b-126">**コンプライアンスと監査データベース**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-126">**Compliance and Audit Database**.</span></span> <span data-ttu-id="67b9b-127">コンプライアンスと監査データベースは、Windows server とサポートされている SQLServer のインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-127">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="67b9b-128">このデータベースには、MBAM クライアントコンピューターのコンプライアンスデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-128">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="67b9b-129">このデータは、主に SQL Server Reporting Services (SSRS) ホストであるレポートに使用されます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-129">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="67b9b-130">**コンプライアンスおよび監査レポート**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-130">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="67b9b-131">コンプライアンスと監査レポートは、Windows server と、SQL Server Reporting Services (SSRS) 機能がインストールされている SQLServer のサポートされているインスタンスにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-131">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="67b9b-132">これらのレポートには、管理と監視の web サイトから、または SSRS サーバーから直接アクセスできる MBAM レポートが用意されています。</span><span class="sxs-lookup"><span data-stu-id="67b9b-132">These reports provide MBAM reports that you can access from the Administration and Monitoring website or directly from the SSRS server.</span></span>

## <span data-ttu-id="67b9b-133">管理ワークステーション</span><span class="sxs-lookup"><span data-stu-id="67b9b-133">Management Workstation</span></span>


<span data-ttu-id="67b9b-134">以下の機能は管理ワークステーションにインストールされます。これは、Windows server またはクライアントコンピューターとして使用できます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-134">The following feature is installed on the Management workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="67b9b-135">**ポリシーテンプレート**。</span><span class="sxs-lookup"><span data-stu-id="67b9b-135">**Policy Template**.</span></span> <span data-ttu-id="67b9b-136">ポリシーテンプレートは、BitLocker ドライブ暗号化の MBAM 実装設定を定義するグループポリシー設定で構成されます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-136">The Policy Template consists of Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="67b9b-137">ポリシーテンプレートは、任意のサーバーまたはワークステーションにインストールできますが、一般的には、サポートされている Windows サーバーまたはクライアントコンピューターである管理ワークステーションにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="67b9b-137">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="67b9b-138">ワークステーションは専用のコンピュータである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67b9b-138">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="67b9b-139">MBAM クライアント</span><span class="sxs-lookup"><span data-stu-id="67b9b-139">MBAM Client</span></span>


<span data-ttu-id="67b9b-140">MBAM クライアントは Windows コンピューターにインストールされ、次のような特徴があります。</span><span class="sxs-lookup"><span data-stu-id="67b9b-140">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="67b9b-141">グループポリシーを使用して、企業内のクライアントコンピューターの BitLocker ドライブ暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="67b9b-141">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="67b9b-142">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="67b9b-142">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="67b9b-143">コンピューターのコンプライアンスデータを収集し、データをレポートシステムに渡します。</span><span class="sxs-lookup"><span data-stu-id="67b9b-143">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="67b9b-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="67b9b-144">Related topics</span></span>


[<span data-ttu-id="67b9b-145">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="67b9b-145">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





