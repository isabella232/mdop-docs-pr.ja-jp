---
title: MBAM 2.0 の展開
description: MBAM 2.0 の展開
author: dansimp
ms.assetid: 4b0eaf10-81b4-427e-9d43-eb833de935a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba4423de5306e1ca204ef3b9fd31424bb8f2630f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823474"
---
# <span data-ttu-id="4e11d-103">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="4e11d-103">Deploying MBAM 2.0</span></span>


<span data-ttu-id="4e11d-104">Microsoft BitLocker の管理と監視 (MBAM) では、さまざまな展開構成がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="4e11d-104">Microsoft BitLocker Administration and Monitoring (MBAM) supports a number of different deployment configurations.</span></span> <span data-ttu-id="4e11d-105">このセクションには、展開のさまざまな段階で完了する必要があるタスクを正常に実行するために、MBAM と段階的な手順の展開について考慮する必要がある情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4e11d-105">This section includes information that you should consider about the deployment of MBAM and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

<span data-ttu-id="4e11d-106">MBAM は、スタンドアロントポロジか、または MBAM を Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager と統合したトポロジで展開できます。</span><span class="sxs-lookup"><span data-stu-id="4e11d-106">You can deploy MBAM either in a Stand-alone topology, or with a topology that integrates MBAM with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="4e11d-107">Configuration Manager の統合トポロジでの MBAM のインストールの詳細については、「 [MBAM を構成マネージャーと共に使用する](using-mbam-with-configuration-manager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="4e11d-107">For information about installing MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

## <span data-ttu-id="4e11d-108">展開情報</span><span class="sxs-lookup"><span data-stu-id="4e11d-108">Deployment Information</span></span>


-   [<span data-ttu-id="4e11d-109">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="4e11d-109">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

    <span data-ttu-id="4e11d-110">このセクションでは、さまざまな MBAM 展開トポロジオプションと、mbam セットアップを使用して MBAM Server 機能を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e11d-110">This section describes the different MBAM deployment topology options and how to use MBAM Setup to deploy MBAM Server features.</span></span>

-   [<span data-ttu-id="4e11d-111">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="4e11d-111">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

    <span data-ttu-id="4e11d-112">このセクションでは、MBAM クライアントを管理するために必要な MBAM グループポリシーオブジェクトを作成して、企業全体で BitLocker 暗号化ポリシーを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e11d-112">This section describes how to create and deploy MBAM Group Policy Objects that are required for managing MBAM Clients and BitLocker encryption policies throughout the enterprise.</span></span>

-   [<span data-ttu-id="4e11d-113">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="4e11d-113">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

    <span data-ttu-id="4e11d-114">このセクションでは、MBAM クライアントインストーラーファイルを使用して MBAM クライアントソフトウェアを展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e11d-114">This section describes how to use the MBAM Client Installer files to deploy the MBAM Client software.</span></span>

-   [<span data-ttu-id="4e11d-115">MBAM 2.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="4e11d-115">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)

    <span data-ttu-id="4e11d-116">このセクションには、MBAM Server 機能と MBAM クライアント展開のサポートに使用できる展開チェックリストが用意されています。</span><span class="sxs-lookup"><span data-stu-id="4e11d-116">This section provides a deployment checklist that can be used to assist in MBAM Server feature and MBAM Client deployment.</span></span>

-   [<span data-ttu-id="4e11d-117">旧バージョンの MBAM からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="4e11d-117">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)

    <span data-ttu-id="4e11d-118">このセクションでは、以前のバージョンから MBAM をアップグレードする手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="4e11d-118">This section provides instructions for upgrading MBAM from previous versions.</span></span>

## <span data-ttu-id="4e11d-119">MBAM の展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="4e11d-119">Other Resources for Deploying MBAM</span></span>


[<span data-ttu-id="4e11d-120">Microsoft BitLocker の管理と監視2管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="4e11d-120">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="4e11d-121">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="4e11d-121">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

[<span data-ttu-id="4e11d-122">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="4e11d-122">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="4e11d-123">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="4e11d-123">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="4e11d-124">MBAM 2.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="4e11d-124">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





