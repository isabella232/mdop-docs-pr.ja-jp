---
title: Microsoft BitLocker の管理と監視1管理者ガイド
description: Microsoft BitLocker の管理と監視1管理者ガイド
author: dansimp
ms.assetid: 4086e721-db24-4439-bdcd-ac5ef901811f
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 5336108e12738a21441df8062fbcd8bd98933945
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795760"
---
# <span data-ttu-id="55d5d-103">Microsoft BitLocker の管理と監視1管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="55d5d-103">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>

<span data-ttu-id="55d5d-104">Microsoft BitLocker の管理と監視 (MBAM) には、BitLocker ドライブの暗号化を管理するために使用できる簡素化された管理インターフェイスが用意されています。</span><span class="sxs-lookup"><span data-stu-id="55d5d-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="55d5d-105">MBAM では、組織に適した BitLocker 暗号化ポリシーオプションを選択し、それらを使用してそれらのポリシーに対するクライアントのコンプライアンスを監視することができます。</span><span class="sxs-lookup"><span data-stu-id="55d5d-105">With MBAM, you can select BitLocker encryption policy options that are appropriate to your enterprise and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="55d5d-106">また、個々のコンピューターとエンタープライズ全体の暗号化の状態について報告することもできます。</span><span class="sxs-lookup"><span data-stu-id="55d5d-106">You can also report on the encryption status of an individual computer and on the entire enterprise.</span></span> <span data-ttu-id="55d5d-107">さらに、ユーザーが PIN またはパスワードを忘れた場合や、BIOS またはブートレコードが変更された場合に、回復キーの情報にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="55d5d-107">In addition, you can access recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

- [<span data-ttu-id="55d5d-108">MBAM 1.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="55d5d-108">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)  
  - [<span data-ttu-id="55d5d-109">MBAM 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="55d5d-109">About MBAM 1.0</span></span>](about-mbam-10.md)
  - [<span data-ttu-id="55d5d-110">MBAM 1.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="55d5d-110">Release Notes for MBAM 1.0</span></span>](release-notes-for-mbam-10.md)
  - [<span data-ttu-id="55d5d-111">MBAM 1.0 の評価</span><span class="sxs-lookup"><span data-stu-id="55d5d-111">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)
  - [<span data-ttu-id="55d5d-112">MBAM 1.0 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="55d5d-112">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)
  - [<span data-ttu-id="55d5d-113">MBAM 1.0 のアクセシビリティ</span><span class="sxs-lookup"><span data-stu-id="55d5d-113">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)
  - [<span data-ttu-id="55d5d-114">MBAM 1.0 のプライバシーに関する声明</span><span class="sxs-lookup"><span data-stu-id="55d5d-114">Privacy Statement for MBAM 1.0</span></span>](privacy-statement-for-mbam-10.md)
- [<span data-ttu-id="55d5d-115">MBAM 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="55d5d-115">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)  
  - [<span data-ttu-id="55d5d-116">MBAM 1.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="55d5d-116">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)
  - [<span data-ttu-id="55d5d-117">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="55d5d-117">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)
  - [<span data-ttu-id="55d5d-118">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="55d5d-118">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)
  - [<span data-ttu-id="55d5d-119">MBAM 1.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="55d5d-119">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)
  - [<span data-ttu-id="55d5d-120">MBAM 1.0 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="55d5d-120">MBAM 1.0 Planning Checklist</span></span>](mbam-10-planning-checklist.md)
- [<span data-ttu-id="55d5d-121">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="55d5d-121">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)  
  - [<span data-ttu-id="55d5d-122">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="55d5d-122">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)
  - [<span data-ttu-id="55d5d-123">MBAM 1.0 グループ ポリシー オブジェクトの展開</span><span class="sxs-lookup"><span data-stu-id="55d5d-123">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)
  - [<span data-ttu-id="55d5d-124">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="55d5d-124">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)
  - [<span data-ttu-id="55d5d-125">MBAM 1.0 Language Release 更新プログラムの展開</span><span class="sxs-lookup"><span data-stu-id="55d5d-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)
  - [<span data-ttu-id="55d5d-126">MBAM 1.0 の展開チェックリスト</span><span class="sxs-lookup"><span data-stu-id="55d5d-126">MBAM 1.0 Deployment Checklist</span></span>](mbam-10-deployment-checklist.md)
- [<span data-ttu-id="55d5d-127">MBAM 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="55d5d-127">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)  
  - [<span data-ttu-id="55d5d-128">MBAM 1.0 機能の管理</span><span class="sxs-lookup"><span data-stu-id="55d5d-128">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)
  - [<span data-ttu-id="55d5d-129">MBAM 1.0 での BitLocker 準拠の監視とレポート</span><span class="sxs-lookup"><span data-stu-id="55d5d-129">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)
  - [<span data-ttu-id="55d5d-130">MBAM での BitLocker 管理の実行</span><span class="sxs-lookup"><span data-stu-id="55d5d-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)
  - [<span data-ttu-id="55d5d-131">PowerShell を使用した MBAM 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="55d5d-131">Administering MBAM 1.0 by Using PowerShell</span></span>](administering-mbam-10-by-using-powershell.md)
- [<span data-ttu-id="55d5d-132">MBAM 1.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="55d5d-132">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)  

## <span data-ttu-id="55d5d-133">詳細情報</span><span class="sxs-lookup"><span data-stu-id="55d5d-133">More Information</span></span>
- [<span data-ttu-id="55d5d-134">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="55d5d-134">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
  <span data-ttu-id="55d5d-135">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="55d5d-135">Find documentation, videos, and other resources for MDOP technologies.</span></span>
