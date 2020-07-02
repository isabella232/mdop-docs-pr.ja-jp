---
title: Microsoft BitLocker Administration and Monitoring 2.5
description: Microsoft BitLocker Administration and Monitoring 2.5
author: dansimp
ms.assetid: fd81d7de-b166-47e8-b6c7-d984830762b6
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2e5243131853207f0ed3cbb6d0cd8fb8e3d56108
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795696"
---
# <span data-ttu-id="d948d-103">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="d948d-103">Microsoft BitLocker Administration and Monitoring 2.5</span></span>

<span data-ttu-id="d948d-104">Microsoft BitLocker の管理と監視 (MBAM) 2.5 は、BitLocker ドライブの暗号化を管理するために使用できる簡素化された管理インターフェイスを提供します。</span><span class="sxs-lookup"><span data-stu-id="d948d-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface that you can use to manage BitLocker Drive Encryption.</span></span> <span data-ttu-id="d948d-105">MBAM グループポリシーテンプレートを構成して、組織に適した BitLocker ドライブ暗号化ポリシーオプションを設定し、それらを使用して、それらのポリシーに対するクライアントのコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="d948d-105">You configure MBAM Group Policy Templates that enable you to set BitLocker Drive Encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="d948d-106">また、個々のコンピューターと企業全体の暗号化の状態について報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="d948d-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="d948d-107">さらに、ユーザーが PIN またはパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合に、回復キーの情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="d948d-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span> <span data-ttu-id="d948d-108">MBAM の詳しい説明については、「 [mbam 2.5 につい](about-mbam-25.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d948d-108">For a more detailed description of MBAM, see [About MBAM 2.5](about-mbam-25.md).</span></span>

<span data-ttu-id="d948d-109">MBAM の入手方法については、「 [MDOP の入手方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d948d-109">To obtain MBAM, see [How Do I Get MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop).</span></span>

## <span data-ttu-id="d948d-110">概要</span><span class="sxs-lookup"><span data-stu-id="d948d-110">Outline</span></span>

- <a href="" id="getting-started-with-mbam-2-5"></a>[<span data-ttu-id="d948d-111">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="d948d-111">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)
  - [<span data-ttu-id="d948d-112">MBAM 2.5 の概要</span><span class="sxs-lookup"><span data-stu-id="d948d-112">About MBAM 2.5</span></span>](about-mbam-25.md)
  - [<span data-ttu-id="d948d-113">MBAM 2.5 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="d948d-113">Release Notes for MBAM 2.5</span></span>](release-notes-for-mbam-25.md)
  - [<span data-ttu-id="d948d-114">MBAM 2.5 SP1 の概要</span><span class="sxs-lookup"><span data-stu-id="d948d-114">About MBAM 2.5 SP1</span></span>](about-mbam-25-sp1.md)
  - [<span data-ttu-id="d948d-115">MBAM 2.5 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="d948d-115">Release Notes for MBAM 2.5 SP1</span></span>](release-notes-for-mbam-25-sp1.md)
  - [<span data-ttu-id="d948d-116">テスト環境での MBAM 2.5 の評価</span><span class="sxs-lookup"><span data-stu-id="d948d-116">Evaluating MBAM 2.5 in a Test Environment</span></span>](evaluating-mbam-25-in-a-test-environment.md)
  - [<span data-ttu-id="d948d-117">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="d948d-117">High-Level Architecture for MBAM 2.5</span></span>](high-level-architecture-for-mbam-25.md)
  - [<span data-ttu-id="d948d-118">MBAM 2.5 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="d948d-118">Accessibility for MBAM 2.5</span></span>](accessibility-for-mbam-25.md)
- <a href="" id="planning-for-mbam-2-5"></a>[<span data-ttu-id="d948d-119">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="d948d-119">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)
  - [<span data-ttu-id="d948d-120">MBAM 2.5 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="d948d-120">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)
  - [<span data-ttu-id="d948d-121">MBAM 2.5 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="d948d-121">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)
  - [<span data-ttu-id="d948d-122">MBAM 2.5 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="d948d-122">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)
  - [<span data-ttu-id="d948d-123">MBAM 2.5 グループとアカウントの計画</span><span class="sxs-lookup"><span data-stu-id="d948d-123">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)
  - [<span data-ttu-id="d948d-124">MBAM Web サイトをセキュリティで保護する方法の計画</span><span class="sxs-lookup"><span data-stu-id="d948d-124">Planning How to Secure the MBAM Websites</span></span>](planning-how-to-secure-the-mbam-websites.md)
  - [<span data-ttu-id="d948d-125">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="d948d-125">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)
  - [<span data-ttu-id="d948d-126">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="d948d-126">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)
  - [<span data-ttu-id="d948d-127">MBAM 2.5 の高可用性のための計画</span><span class="sxs-lookup"><span data-stu-id="d948d-127">Planning for MBAM 2.5 High Availability</span></span>](planning-for-mbam-25-high-availability.md)
  - [<span data-ttu-id="d948d-128">MBAM 2.5 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="d948d-128">MBAM 2.5 Security Considerations</span></span>](mbam-25-security-considerations.md)
  - [<span data-ttu-id="d948d-129">MBAM 2.5 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d948d-129">MBAM 2.5 Planning Checklist</span></span>](mbam-25-planning-checklist.md)
- <a href="" id="deploying-mbam-2-5"></a>[<span data-ttu-id="d948d-130">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="d948d-130">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)
  - [<span data-ttu-id="d948d-131">MBAM 2.5 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="d948d-131">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)
  - [<span data-ttu-id="d948d-132">MBAM 2.5 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="d948d-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)
  - [<span data-ttu-id="d948d-133">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="d948d-133">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)
  - [<span data-ttu-id="d948d-134">MBAM 2.5 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="d948d-134">MBAM 2.5 Deployment Checklist</span></span>](mbam-25-deployment-checklist.md)
  - [<span data-ttu-id="d948d-135">以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="d948d-135">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)
  - [<span data-ttu-id="d948d-136">MBAM サーバーの機能またはソフトウェアの削除</span><span class="sxs-lookup"><span data-stu-id="d948d-136">Removing MBAM Server Features or Software</span></span>](removing-mbam-server-features-or-software.md)
- <a href="" id="operations-for-mbam-2-5"></a>[<span data-ttu-id="d948d-137">MBAM 2.5 の操作</span><span class="sxs-lookup"><span data-stu-id="d948d-137">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)
  - [<span data-ttu-id="d948d-138">MBAM 2.5 機能の管理</span><span class="sxs-lookup"><span data-stu-id="d948d-138">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)
  - [<span data-ttu-id="d948d-139">MBAM 2.5 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="d948d-139">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)
  - [<span data-ttu-id="d948d-140">MBAM 2.5 での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="d948d-140">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)
  - [<span data-ttu-id="d948d-141">MBAM 2.5 の保守</span><span class="sxs-lookup"><span data-stu-id="d948d-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)
  - [<span data-ttu-id="d948d-142">Windows PowerShell を使用した MBAM 2.5 の管理</span><span class="sxs-lookup"><span data-stu-id="d948d-142">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)
- <a href="" id="troubleshooting-mbam-2-5"></a>[<span data-ttu-id="d948d-143">MBAM 2.5 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d948d-143">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)
- <a href="" id="technical-reference-for-mbam-2-5"></a>[<span data-ttu-id="d948d-144">MBAM 2.5 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="d948d-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)
  - [<span data-ttu-id="d948d-145">クライアントのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="d948d-145">Client Event Logs</span></span>](client-event-logs.md)
  - [<span data-ttu-id="d948d-146">サーバーのイベント ログ</span><span class="sxs-lookup"><span data-stu-id="d948d-146">Server Event Logs</span></span>](server-event-logs.md)

## <span data-ttu-id="d948d-147">詳細情報</span><span class="sxs-lookup"><span data-stu-id="d948d-147">More Information</span></span>

- [<span data-ttu-id="d948d-148">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="d948d-148">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="d948d-149">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d948d-149">Find documentation, videos, and other resources for MDOP technologies.</span></span>

- [<span data-ttu-id="d948d-150">MBAM 展開ガイド</span><span class="sxs-lookup"><span data-stu-id="d948d-150">MBAM Deployment Guide</span></span>](https://www.microsoft.com/download/details.aspx?id=38398)

  <span data-ttu-id="d948d-151">各方法のステップバイステップの手順など、MBAM の展開方法を選択する方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d948d-151">Get help in choosing a deployment method for MBAM, including step-by-step instructions for each method.</span></span>
    
- [<span data-ttu-id="d948d-152">MBAM 2.5 SP1 サーバーに修正プログラムを適用する</span><span class="sxs-lookup"><span data-stu-id="d948d-152">Apply Hotfixes on MBAM 2.5 SP1 Server</span></span>](apply-hotfix-for-mbam-25-sp1.md)

  <span data-ttu-id="d948d-153">MBAM 2.5 SP1 サーバーホットフィックスの適用方法のガイド</span><span class="sxs-lookup"><span data-stu-id="d948d-153">Guide of how to apply MBAM 2.5 SP1 Server hotfixes</span></span>
