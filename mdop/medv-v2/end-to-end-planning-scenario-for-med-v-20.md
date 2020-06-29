---
title: MED-V 2.0 のエンド ツー エンドのプランニング シナリオ
description: MED-V 2.0 のエンド ツー エンドのプランニング シナリオ
author: dansimp
ms.assetid: e7833883-be93-4b42-9fa3-5c4d9a919058
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f34dcccade7987b8b01269caa667018a74d020c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827177"
---
# <span data-ttu-id="6110a-103">MED-V 2.0 のエンド ツー エンドのプランニング シナリオ</span><span class="sxs-lookup"><span data-stu-id="6110a-103">End-to-End Planning Scenario for MED-V 2.0</span></span>


<span data-ttu-id="6110a-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 のサンプルシナリオでは、複数のシナリオをエンドツーエンドで使用して、MED-V の展開を計画することの目標を達成するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6110a-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you achieve your goal of planning your MED-V deployment by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="6110a-105">このサンプルシナリオは、個々のシナリオと手順をコンテキストにまとめる際に役立つケーススタディと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="6110a-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="6110a-106">このセクションでは、企業内のエンドツーエンドのソリューションとして、MED-V の展開を計画するための基本的な情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="6110a-106">This section provides basic information and directions for planning you MED-V deployment as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="6110a-107">MED-V の計画ステップバイステップのシナリオ</span><span class="sxs-lookup"><span data-stu-id="6110a-107">MED-V Planning Step-by-Step Scenario</span></span>


<span data-ttu-id="6110a-108">このステップバイステップのシナリオのトピックには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="6110a-108">The topics in this step-by-step scenario include the following:</span></span>

-   <span data-ttu-id="6110a-109">[高レベルのアーキテクチャ](high-level-architecturemedv2.md)では、med-v 2.0 の上位レベルのシステムアーキテクチャとコンポーネント設計について説明します。</span><span class="sxs-lookup"><span data-stu-id="6110a-109">[High-Level Architecture](high-level-architecturemedv2.md) discusses the high-level system architecture and component design of MED-V 2.0.</span></span> <span data-ttu-id="6110a-110">MED-V は、1つのデバイスで2つのオペレーティングシステムを実行する、仮想イメージの配信、グループポリシーベースのプロビジョニング、一元管理を実行するために、Windows 仮想 PC を拡張します。</span><span class="sxs-lookup"><span data-stu-id="6110a-110">MED-V enhances Windows Virtual PC to run two operating systems on one device, adding virtual image delivery, Group Policy-based provisioning, and centralized management.</span></span> <span data-ttu-id="6110a-111">MED-V を使用することで、windows 7 Professional、Enterprise、または Windows 7 Ultimate を実行している Windows ベースのデスクトップで、企業の Windows 仮想 PC のイメージの構成、展開、管理を簡単に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="6110a-111">By using MED-V, you can easily configure, deploy, and manage corporate Windows Virtual PC images on any Windows-based desktop running Windows 7 Professional, Enterprise, or Windows 7 Ultimate.</span></span>

-   <span data-ttu-id="6110a-112">[Med-v の展開を定義して計画](define-and-plan-your-med-v-deployment.md)する med-v 2.0 の展開を計画する際の考慮事項について説明します。</span><span class="sxs-lookup"><span data-stu-id="6110a-112">[Define and Plan your MED-V Deployment](define-and-plan-your-med-v-deployment.md) discusses the considerations for planning your MED-V 2.0 deployment.</span></span> <span data-ttu-id="6110a-113">このトピックでは、エンタープライズで MED-V を受け取り、ディスク領域の要件を計算するシステムを特定する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="6110a-113">This topic provides direction about identifying the systems in your enterprise that receive MED-V and calculating disk space requirements.</span></span> <span data-ttu-id="6110a-114">このトピックでは、既存のインフラストラクチャを評価し、MED-V の展開にどのように使うかを決定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6110a-114">This topic also helps evaluate your existing infrastructure and determines how it can be used for MED-V deployment.</span></span>

-   <span data-ttu-id="6110a-115">[Med-v 2.0 のベストプラクティス](med-v-20-best-practices.md)では、環境の med-v 2.0 の計画、インストール、展開、および管理に推奨されるベストプラクティスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6110a-115">[MED-V 2.0 Best Practices](med-v-20-best-practices.md) discusses the recommended best practices for planning, installing, deploying, and managing MED-V 2.0 in your environment.</span></span> <span data-ttu-id="6110a-116">このベストプラクティスには、実行時間を短縮し、初めてセットアップして、パフォーマンスを向上させ、仮想マシンの管理を強化するための推奨事項が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6110a-116">These best practices include recommendations that produce faster run times, better operability during first time setup, increased performance, and better virtual machine management.</span></span>

## <span data-ttu-id="6110a-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6110a-117">Related topics</span></span>


[<span data-ttu-id="6110a-118">MED-V の計画</span><span class="sxs-lookup"><span data-stu-id="6110a-118">Planning for MED-V</span></span>](planning-for-med-v.md)

[<span data-ttu-id="6110a-119">MED-V 2.0 のエンド ツー エンドの展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="6110a-119">End-to-End Deployment Scenario for MED-V 2.0</span></span>](end-to-end-deployment-scenario-for-med-v-20.md)

[<span data-ttu-id="6110a-120">MED-V 2.0 のエンド ツー エンドの操作シナリオ</span><span class="sxs-lookup"><span data-stu-id="6110a-120">End-to-End Operations Scenario for MED-V 2.0</span></span>](end-to-end-operations-scenario-for-med-v-20.md)

 

 





