---
title: Microsoft BitLocker の管理と監視2管理者ガイド
description: Microsoft BitLocker の管理と監視2管理者ガイド
author: dansimp
ms.assetid: fdb43f62-960a-4811-8802-50efdf04b4af
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: dd6deb6fb91c64ac8609b54114e0dd417497034a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795752"
---
# <span data-ttu-id="63284-103">Microsoft BitLocker の管理と監視2管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="63284-103">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>

<span data-ttu-id="63284-104">Microsoft BitLockerAdministration/Monitoring (MBAM) 2.0 は、BitLocker ドライブの暗号化を管理するために使用できる簡素化された管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="63284-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="63284-105">BitLockerAdministration と Monitoring 2.0 では、エンタープライズに適した BitLocker ドライブ暗号化ポリシーオプションを選択し、それらを使ってそれらのポリシーに対するクライアントのコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="63284-105">In BitLockerAdministration and Monitoring2.0, you can select BitLocker drive encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="63284-106">また、個々のコンピューターと企業全体の暗号化の状態について報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="63284-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="63284-107">さらに、ユーザーが PIN またはパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合に、回復キーの情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="63284-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span>

## <span data-ttu-id="63284-108">概要</span><span class="sxs-lookup"><span data-stu-id="63284-108">Outline</span></span>

- [<span data-ttu-id="63284-109">MBAM 2.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="63284-109">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-110">MBAM 2.0 の概要</span><span class="sxs-lookup"><span data-stu-id="63284-110">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-111">MBAM 2.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="63284-111">Release Notes for MBAM 2.0</span></span>](release-notes-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-112">MBAM 2.0 SP1 の概要</span><span class="sxs-lookup"><span data-stu-id="63284-112">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)
  - [<span data-ttu-id="63284-113">MBAM 2.0 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="63284-113">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)
  - [<span data-ttu-id="63284-114">MBAM 2.0 の評価</span><span class="sxs-lookup"><span data-stu-id="63284-114">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-115">MBAM 2.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="63284-115">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-116">MBAM 2.0 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="63284-116">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)
- [<span data-ttu-id="63284-117">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="63284-117">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-118">MBAM 2.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="63284-118">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-119">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="63284-119">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)
  - [<span data-ttu-id="63284-120">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="63284-120">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-121">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="63284-121">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)
  - [<span data-ttu-id="63284-122">MBAM 2.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="63284-122">MBAM 2.0 Planning Checklist</span></span>](mbam-20-planning-checklist-mbam-2.md)
- [<span data-ttu-id="63284-123">MBAM 2.0 の展開</span><span class="sxs-lookup"><span data-stu-id="63284-123">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-124">MBAM 2.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="63284-124">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)
  - [<span data-ttu-id="63284-125">MBAM 2.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="63284-125">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)
  - [<span data-ttu-id="63284-126">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="63284-126">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)
  - [<span data-ttu-id="63284-127">MBAM 2.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="63284-127">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)
  - [<span data-ttu-id="63284-128">旧バージョンの MBAM からのアップグレード</span><span class="sxs-lookup"><span data-stu-id="63284-128">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)
- [<span data-ttu-id="63284-129">MBAM 2.0 の操作</span><span class="sxs-lookup"><span data-stu-id="63284-129">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-130">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="63284-130">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)
  - [<span data-ttu-id="63284-131">MBAM 2.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="63284-131">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)
  - [<span data-ttu-id="63284-132">MBAM 2.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="63284-132">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-133">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="63284-133">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)
  - [<span data-ttu-id="63284-134">MBAM 2.0 の保守</span><span class="sxs-lookup"><span data-stu-id="63284-134">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-135">MBAM 2.0 のセキュリティとプライバシー</span><span class="sxs-lookup"><span data-stu-id="63284-135">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="63284-136">PowerShell を使用した MBAM 2.0 の管理</span><span class="sxs-lookup"><span data-stu-id="63284-136">Administering MBAM 2.0 Using PowerShell</span></span>](administering-mbam-20-using-powershell-mbam-2.md)
- [<span data-ttu-id="63284-137">MBAM 2.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="63284-137">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

## <span data-ttu-id="63284-138">詳細情報</span><span class="sxs-lookup"><span data-stu-id="63284-138">More Information</span></span>

- [<span data-ttu-id="63284-139">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="63284-139">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="63284-140">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="63284-140">Find documentation, videos, and other resources for MDOP technologies.</span></span>

 

 





