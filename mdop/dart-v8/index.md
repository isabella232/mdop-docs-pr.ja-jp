---
title: 診断/回復ツールセット8管理者ガイド
description: 診断/回復ツールセット8管理者ガイド
author: dansimp
ms.assetid: 33685dd7-844f-4864-b504-3ef384ef01de
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 10/03/2017
ms.openlocfilehash: c4f4e7cb49b89759acc4c3c738ff74a4a197b120
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795739"
---
# <span data-ttu-id="2c2aa-103">診断/回復ツールセット8管理者ガイド</span><span class="sxs-lookup"><span data-stu-id="2c2aa-103">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>


<span data-ttu-id="2c2aa-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 では、起動できない、または予期したとおりに問題が発生したコンピューターを診断および修復できます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 lets you diagnose and repair a computer that cannot be started or that has problems starting as expected.</span></span> <span data-ttu-id="2c2aa-105">DaRT 8.0 を使用すると、使用できなくなったエンドユーザーのコンピューターを回復したり、問題の考えられる原因を診断したり、起動できない、またはロックアウトされたコンピューターをすばやく修復したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-105">By using DaRT 8.0, you can recover end-user computers that have become unusable, diagnose probable causes of issues, and quickly repair unbootable or locked-out computers.</span></span> <span data-ttu-id="2c2aa-106">必要な場合は、コンピューターがオンラインでない場合でも、重要な消失したファイルをすばやく復元し、マルウェアを検出して削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-106">When it is necessary, you can also quickly restore important lost files and detect and remove malware, even when the computer is not online.</span></span>

<span data-ttu-id="2c2aa-107">DaRT 8.0 を使用すると、国際標準化機構 (ISO) および Windows Imaging (WIM) ファイル形式で DaRT の回復画像を作成して、CD、DVD、または USB にイメージを書き込むことができます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-107">DaRT 8.0 lets you create a DaRT recovery image in International Organization for Standardization (ISO) and Windows Imaging (WIM) file formats and burn the image to a CD, DVD, or USB.</span></span> <span data-ttu-id="2c2aa-108">次に、回復イメージファイルを使用して、ローカルまたはリモートパーティションまたは回復パーティションに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-108">You can then use the recovery image files and deploy them locally or to a remote partition or a recovery partition.</span></span>

<span data-ttu-id="2c2aa-109">DaRT 8.0 は、Microsoft デスクトップ最適化パック (MDOP) の重要な部分であり、ソフトウェアアシュアランスのお客様が利用できる動的ソリューションであり、ソフトウェアのインストールコストの削減、サービスとしてのアプリケーションの配信、エンタープライズデスクトップ環境の管理や管理に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-109">DaRT 8.0 is an important part of the Microsoft Desktop Optimization Pack (MDOP), a dynamic solution available to Software Assurance customers that helps reduce software installation costs, enables delivery of applications as services, and helps manage and control enterprise desktop environments.</span></span>

<a href="" id="getting-started-with-dart-8-0"></a>[<span data-ttu-id="2c2aa-110">DaRT 8.0 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="2c2aa-110">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)  

<span data-ttu-id="2c2aa-111">[DaRT 8.0](about-dart-80-dart-8.md) **|** について[DaRT 8.0](release-notes-for-dart-80--dart-8.md) **|** のリリースノート[DaRT 8.0 SP1](about-dart-80-sp1.md) **|** について[DaRT 8.0 SP1](release-notes-for-dart-80-sp1.md) **|** のリリースノート[DaRT 8.1](about-dart-81.md) **|** について[DaRT 8.1](release-notes-for-dart-81.md) **|** のリリースノート[DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md) **|** でのツールの概要[DaRT 8.0 のアクセシビリティ](accessibility-for-dart-80-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="2c2aa-111">[About DaRT 8.0](about-dart-80-dart-8.md)**|**[Release Notes for DaRT 8.0](release-notes-for-dart-80--dart-8.md)**|**[About DaRT 8.0 SP1](about-dart-80-sp1.md)**|**[Release Notes for DaRT 8.0 SP1](release-notes-for-dart-80-sp1.md)**|**[About DaRT 8.1](about-dart-81.md)**|**[Release Notes for DaRT 8.1](release-notes-for-dart-81.md)**|**[Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md)**|**[Accessibility for DaRT 8.0](accessibility-for-dart-80-dart-8.md)</span></span>

<a href="" id="planning-for-dart-8-0"></a>[<span data-ttu-id="2c2aa-112">DaRT 8.0 の計画</span><span class="sxs-lookup"><span data-stu-id="2c2aa-112">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)  

<span data-ttu-id="2c2aa-113">[DaRT 8.0](planning-to-deploy-dart-80-dart-8.md) **|** の展開を計画する[DaRT 8.0 サポートされている構成](dart-80-supported-configurations-dart-8.md) **|**[DaRT 8.0 リカバリイメージ](planning-to-create-the-dart-80-recovery-image-dart-8.md) **|** の作成の計画[DaRT 8.0 リカバリイメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md) **|**[DaRT 8.0 の計画チェックリスト](dart-80-planning-checklist-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="2c2aa-113">[Planning to Deploy DaRT 8.0](planning-to-deploy-dart-80-dart-8.md)**|**[DaRT 8.0 Supported Configurations](dart-80-supported-configurations-dart-8.md)**|**[Planning to Create the DaRT 8.0 Recovery Image](planning-to-create-the-dart-80-recovery-image-dart-8.md)**|**[Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)**|**[DaRT 8.0 Planning Checklist](dart-80-planning-checklist-dart-8.md)</span></span>

<a href="" id="deploying-dart-8-0"></a>[<span data-ttu-id="2c2aa-114">DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="2c2aa-114">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)  

<span data-ttu-id="2c2aa-115">[管理者のコンピューターへの DaRT 8.0 の展開](deploying-dart-80-to-administrator-computers-dart-8.md) **|**[DaRT 8.0 リカバリイメージ](creating-the-dart-80-recovery-image-dart-8.md) **|** の作成[DaRT リカバリイメージ](deploying-the-dart-recovery-image-dart-8.md) **|** の展開[DaRT 8.0 展開のチェックリスト](dart-80-deployment-checklist-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="2c2aa-115">[Deploying DaRT 8.0 to Administrator Computers](deploying-dart-80-to-administrator-computers-dart-8.md)**|**[Creating the DaRT 8.0 Recovery Image](creating-the-dart-80-recovery-image-dart-8.md)**|**[Deploying the DaRT Recovery Image](deploying-the-dart-recovery-image-dart-8.md)**|**[DaRT 8.0 Deployment Checklist](dart-80-deployment-checklist-dart-8.md)</span></span>

<a href="" id="operations-for-dart-8-0"></a>[<span data-ttu-id="2c2aa-116">DaRT 8.0 の操作</span><span class="sxs-lookup"><span data-stu-id="2c2aa-116">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)  

<span data-ttu-id="2c2aa-117">[DaRT 8.0 を使用してコンピューターを回復する](recovering-computers-using-dart-80-dart-8.md) **|**[クラッシュアナライザー](diagnosing-system-failures-with-crash-analyzer--dart-8.md) **|** によるシステム障害の診断[DaRT 8.0](security-and-privacy-for-dart-80-dart-8.md) **|** のセキュリティとプライバシー[PowerShell を使用した DaRT 8.0 の管理](administering-dart-80-using-powershell-dart-8.md)</span><span class="sxs-lookup"><span data-stu-id="2c2aa-117">[Recovering Computers Using DaRT 8.0](recovering-computers-using-dart-80-dart-8.md)**|**[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md)**|**[Security and Privacy for DaRT 8.0](security-and-privacy-for-dart-80-dart-8.md)**|**[Administering DaRT 8.0 Using PowerShell](administering-dart-80-using-powershell-dart-8.md)</span></span>

<a href="" id="technical-reference-for-dart-8-0"></a>[<span data-ttu-id="2c2aa-118">DaRT 8.0 テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="2c2aa-118">Technical Reference for DaRT 8.0</span></span>](technical-reference-for-dart-80-new-ia.md)  

[<span data-ttu-id="2c2aa-119">Microsoft 診断/回復ツールセット (DaRT) ユーザーは、マルウェア検出に Microsoft Defender オフライン (WDO) を使用する必要があります。--></span><span class="sxs-lookup"><span data-stu-id="2c2aa-119">Microsoft Diagnostics and Recovery Toolset (DaRT) users should use Microsoft Defender Offline (WDO) for malware detection--></span></span>](use-windows-defender-offline-wdo-for-malware-protection-not-dart.md)

<a href="" id="troubleshooting-dart-8-0"></a>[<span data-ttu-id="2c2aa-120">DaRT 8.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="2c2aa-120">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)  

### <span data-ttu-id="2c2aa-121">詳細情報</span><span class="sxs-lookup"><span data-stu-id="2c2aa-121">More Information</span></span>

<a href="" id="how-do-i-get-mdop"></a>[<span data-ttu-id="2c2aa-122">MDOP を取得するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="2c2aa-122">How Do I Get MDOP</span></span>](https://go.microsoft.com/fwlink/?LinkId=322049)  
<span data-ttu-id="2c2aa-123">DaRT のダウンロード方法については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-123">Get information about how to download DaRT.</span></span>

<a href="" id="release-notes-for-dart-8-0"></a>[<span data-ttu-id="2c2aa-124">DaRT 8.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="2c2aa-124">Release Notes for DaRT 8.0</span></span>](release-notes-for-dart-80--dart-8.md)  
<span data-ttu-id="2c2aa-125">DaRT 8.0 の更新された製品情報と既知の問題を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-125">View updated product information and known issues for DaRT 8.0.</span></span>

<a href="" id="mdop-techcenter-page"></a>[<span data-ttu-id="2c2aa-126">MDOP TechCenter ページ</span><span class="sxs-lookup"><span data-stu-id="2c2aa-126">MDOP TechCenter Page</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=225286)  
<span data-ttu-id="2c2aa-127">最新の MDOP 情報とリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-127">Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a>[<span data-ttu-id="2c2aa-128">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="2c2aa-128">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
<span data-ttu-id="2c2aa-129">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-129">Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="2c2aa-130">また、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)で、お客[様のフィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、更新について確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="2c2aa-130">You can also [send us feedback](mailto:MDOPDocs@microsoft.com), or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

 

 





