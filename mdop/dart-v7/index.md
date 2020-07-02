---
title: 診断/回復ツールセット7管理者ガイド
description: 診断/回復ツールセット7管理者ガイド
author: dansimp
ms.assetid: bf89eccd-fc03-48ff-9019-a8640e11dd99
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 92cba6f364fc04e0113232c4682bcee8fe2bd73f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795595"
---
# <span data-ttu-id="e48b1-103">診断/回復ツールセット7管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="e48b1-103">Diagnostics and Recovery Toolset 7 Administrator's Guide</span></span>


<span data-ttu-id="e48b1-104">Microsoft 診断/回復ツールセット (DaRT) 7 を使用すると、起動できない、または予期したときに問題が発生したコンピューターを診断および修復できます。</span><span class="sxs-lookup"><span data-stu-id="e48b1-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 lets you diagnose and repair a computer that cannot be started or that has problems starting as expected.</span></span> <span data-ttu-id="e48b1-105">DaRT を使用することで、使用できなくなったエンドユーザーのコンピューターを回復したり、問題の考えられる原因を診断したり、起動できない、またはロックアウトされたコンピューターをすばやく修復したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e48b1-105">By using DaRT, you can recover end-user computers that have become unusable, diagnose probable causes of issues, and quickly repair unbootable or locked-out computers.</span></span> <span data-ttu-id="e48b1-106">必要な場合は、コンピューターがオンラインでない場合でも、重要な消失したファイルをすばやく復元し、マルウェアを検出して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e48b1-106">When it is necessary, you can also quickly restore important lost files and detect and remove malware, even when the computer is not online.</span></span>

<span data-ttu-id="e48b1-107">DaRT は、Microsoft デスクトップ最適化パック (MDOP) の重要な部分であり、ソフトウェアアシュアランスのお客様が利用できる動的ソリューションであり、ソフトウェアのインストールコストの削減、サービスとしてのアプリケーションの配信、エンタープライズデスクトップ環境の管理や管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="e48b1-107">DaRT is an important part of the Microsoft Desktop Optimization Pack (MDOP), a dynamic solution available to Software Assurance customers that helps reduce software installation costs, enables delivery of applications as services, and helps manage and control enterprise desktop environments.</span></span>

<a href="" id="getting-started-with-dart-7-0"></a>[<span data-ttu-id="e48b1-108">DaRT 7.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="e48b1-108">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)  

<span data-ttu-id="e48b1-109">[DaRT 7.0](about-dart-70-new-ia.md) **|** について[DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md) **|** でのツールの概要[DaRT 7.0 のアクセシビリティ](accessibility-for-dart-70.md)</span><span class="sxs-lookup"><span data-stu-id="e48b1-109">[About DaRT 7.0](about-dart-70-new-ia.md)**|**[Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md)**|**[Accessibility for DaRT 7.0](accessibility-for-dart-70.md)</span></span>

<a href="" id="planning-for-dart-7-0"></a>[<span data-ttu-id="e48b1-110">DaRT 7.0 の計画</span><span class="sxs-lookup"><span data-stu-id="e48b1-110">Planning for DaRT 7.0</span></span>](planning-for-dart-70-new-ia.md)  

<span data-ttu-id="e48b1-111">[DaRT 7.0](planning-to-deploy-dart-70.md) **|** の展開を計画する[DaRT 7.0 サポートされている構成](dart-70-supported-configurations-dart-7.md) **|**[DaRT 7.0 リカバリイメージ](planning-to-create-the-dart-70-recovery-image.md) **|** の作成の計画[DaRT 7.0 リカバリイメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md) **|**[DaRT 7.0 の計画チェックリスト](dart-70-planning-checklist-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="e48b1-111">[Planning to Deploy DaRT 7.0](planning-to-deploy-dart-70.md)**|**[DaRT 7.0 Supported Configurations](dart-70-supported-configurations-dart-7.md)**|**[Planning to Create the DaRT 7.0 Recovery Image](planning-to-create-the-dart-70-recovery-image.md)**|**[Planning How to Save and Deploy the DaRT 7.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)**|**[DaRT 7.0 Planning Checklist](dart-70-planning-checklist-dart-7.md)</span></span>

<a href="" id="deploying-dart-7-0"></a>[<span data-ttu-id="e48b1-112">DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="e48b1-112">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)  

<span data-ttu-id="e48b1-113">[管理者のコンピューターへの DaRT 7.0 の展開](deploying-dart-70-to-administrator-computers-dart-7.md) **|**[DaRT 7.0 リカバリイメージ](creating-the-dart-70-recovery-image-dart-7.md) **|** の作成[DaRT 7.0 リカバリイメージ](deploying-the-dart-70-recovery-image-dart-7.md) **|** の展開[DaRT 7.0 展開のチェックリスト](dart-70-deployment-checklist-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="e48b1-113">[Deploying DaRT 7.0 to Administrator Computers](deploying-dart-70-to-administrator-computers-dart-7.md)**|**[Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md)**|**[Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md)**|**[DaRT 7.0 Deployment Checklist](dart-70-deployment-checklist-dart-7.md)</span></span>

<a href="" id="operations-for-dart-7-0"></a>[<span data-ttu-id="e48b1-114">DaRT 7.0 の操作</span><span class="sxs-lookup"><span data-stu-id="e48b1-114">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)  

<span data-ttu-id="e48b1-115">[DaRT 7.0 を使用してコンピューターを回復する](recovering-computers-using-dart-70-dart-7.md) **|**[クラッシュアナライザー](diagnosing-system-failures-with-crash-analyzer--dart-7.md) **|** によるシステム障害の診断[DaRT 7.0 のセキュリティに関する考慮事項](security-considerations-for-dart-70-dart-7.md)</span><span class="sxs-lookup"><span data-stu-id="e48b1-115">[Recovering Computers Using DaRT 7.0](recovering-computers-using-dart-70-dart-7.md)**|**[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md)**|**[Security Considerations for DaRT 7.0](security-considerations-for-dart-70-dart-7.md)</span></span>

<a href="" id="troubleshooting-dart-7-0"></a>[<span data-ttu-id="e48b1-116">DaRT 7.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="e48b1-116">Troubleshooting DaRT 7.0</span></span>](troubleshooting-dart-70-new-ia.md)  

<a href="" id="technical-reference-for-dart-7-0"></a>[<span data-ttu-id="e48b1-117">DaRT 7.0 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="e48b1-117">Technical Reference for DaRT 7.0</span></span>](technical-reference-for-dart-70-new-ia.md)  

### <span data-ttu-id="e48b1-118">詳細情報</span><span class="sxs-lookup"><span data-stu-id="e48b1-118">More Information</span></span>

<a href="" id="release-notes-for-dart-7-0"></a>[<span data-ttu-id="e48b1-119">DaRT 7.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="e48b1-119">Release Notes for DaRT 7.0</span></span>](release-notes-for-dart-70-new-ia.md)  
<span data-ttu-id="e48b1-120">DaRT 7 の更新された製品情報と既知の問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="e48b1-120">View updated product information and known issues for DaRT 7.</span></span>

<a href="" id="mdop-techcenter-page"></a>[<span data-ttu-id="e48b1-121">MDOP TechCenter ページ</span><span class="sxs-lookup"><span data-stu-id="e48b1-121">MDOP TechCenter Page</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=225286)  
<span data-ttu-id="e48b1-122">最新の MDOP 情報とリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e48b1-122">Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a>[<span data-ttu-id="e48b1-123">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="e48b1-123">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
<span data-ttu-id="e48b1-124">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="e48b1-124">Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="e48b1-125">また、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をフォローして、[フィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、更新プログラムに関する情報を確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="e48b1-125">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

 

 





