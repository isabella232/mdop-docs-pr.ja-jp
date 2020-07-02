---
title: Microsoft User Experience Virtualization (UE-V) 1.0
description: Microsoft User Experience Virtualization (UE-V) 1.0
author: dansimp
ms.assetid: 7c2b59f6-bbe9-4373-8b08-c1738665a37b
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2bafda641242ca0fb3a3fae3ea7aaea24eeb77b2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795683"
---
# <span data-ttu-id="18178-103">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="18178-103">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>

>[!NOTE]
><span data-ttu-id="18178-104">このドキュメントは、Microsoft デスクトップ最適化パック (MDOP) に含まれている UE-V のバージョンを示しています。</span><span class="sxs-lookup"><span data-stu-id="18178-104">This documentation is a for version of UE-V that was included in the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="18178-105">Windows 10 Enterprise に含まれている最新バージョンの UE-V の詳細については、「 [ue-v の使用を開始](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="18178-105">For information about the latest version of UE-V which is included in Windows 10 Enterprise, see [Get Started with UE-V](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started).</span></span>


<span data-ttu-id="18178-106">Microsoft User Experience Virtualization (UE-V) では、ユーザーのアプリケーション設定と Windows オペレーティングシステムの設定がキャプチャされ、集中化されます。</span><span class="sxs-lookup"><span data-stu-id="18178-106">Microsoft User Experience Virtualization (UE-V) captures and centralizes application settings and Windows operating system settings for the user.</span></span> <span data-ttu-id="18178-107">これらの設定は、デスクトップコンピューター、ノート pc、仮想デスクトップインフラストラクチャ (VDI) セッションなど、ユーザーによってアクセスされるさまざまなコンピューターに適用されます。</span><span class="sxs-lookup"><span data-stu-id="18178-107">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<a href="" id="getting-started-with-user-experience-virtualization-1-0"></a>[<span data-ttu-id="18178-108">User Experience Virtualization 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="18178-108">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)  

<span data-ttu-id="18178-109">[User Experience Virtualization 1.0 SP1](about-user-experience-virtualization-10-sp1.md) **|** について[Microsoft User Experience Virtualization (ue-v) 1.0 SP1 のリリースノート](microsoft-user-experience-virtualization--ue-v--10-sp1-release-notes.md) **|**[User Experience Virtualization 1.0](about-user-experience-virtualization-10.md) **|** について[Microsoft User Experience Virtualization (ue-v) 1.0 リリースノート](microsoft-user-experience-virtualization--ue-v--10-release-notes.md) **|**[Ue-v 1.0](high-level-architecture-for-ue-v-10.md) **|** の高レベルアーキテクチャ[Ue-v のアクセシビリティ](accessibility-for-ue-v.md)</span><span class="sxs-lookup"><span data-stu-id="18178-109">[About User Experience Virtualization 1.0 SP1](about-user-experience-virtualization-10-sp1.md)**|**[Microsoft User Experience Virtualization (UE-V) 1.0 SP1 Release Notes](microsoft-user-experience-virtualization--ue-v--10-sp1-release-notes.md)**|**[About User Experience Virtualization 1.0](about-user-experience-virtualization-10.md)**|**[Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)**|**[High-Level Architecture for UE-V 1.0](high-level-architecture-for-ue-v-10.md)**|**[Accessibility for UE-V](accessibility-for-ue-v.md)</span></span>

<a href="" id="planning-for-ue-v-1-0"></a>[<span data-ttu-id="18178-110">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="18178-110">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)  

<span data-ttu-id="18178-111">UE-V の環境の[準備](preparing-your-environment-for-ue-v.md) **|**[Ue-v 1.0](supported-configurations-for-ue-v-10.md) **|** でサポートされている構成[Ue-v 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md) **|** と同期するアプリケーションを計画する[Ue-v 構成メソッド](planning-for-ue-v-configuration-methods.md) **|** の計画[Ue-v のチェックリスト](ue-v-checklist.md)</span><span class="sxs-lookup"><span data-stu-id="18178-111">[Preparing Your Environment for UE-V](preparing-your-environment-for-ue-v.md)**|**[Supported Configurations for UE-V 1.0](supported-configurations-for-ue-v-10.md)**|**[Planning Which Applications to Synchronize with UE-V 1.0](planning-which-applications-to-synchronize-with-ue-v-10.md)**|**[Planning for UE-V Configuration Methods](planning-for-ue-v-configuration-methods.md)**|**[UE-V Checklist](ue-v-checklist.md)</span></span>

<a href="" id="deploying-ue-v-1-0"></a>[<span data-ttu-id="18178-112">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="18178-112">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)  

<span data-ttu-id="18178-113">[Ue-v 1.0](deploying-the-settings-storage-location-for-ue-v-10.md) **|** の設定の保存場所の配置[グループポリシーオブジェクト](configuring-ue-v-with-group-policy-objects.md) **|** を使用して Ue-v を設定する[Ue-v 1.0](deploying-the-settings-template-catalog-for-ue-v-10.md) **|** 用の設定テンプレートカタログの展開[Ue-v 1.0 用の Ue-v 設定の場所テンプレートの展開](deploying-ue-v-settings-location-templates-for-ue-v-10.md) **|**[Ue-v agent](deploying-the-ue-v-agent.md) **|** の展開[Ue-v Generator のインストール](installing-the-ue-v-generator.md)</span><span class="sxs-lookup"><span data-stu-id="18178-113">[Deploying the Settings Storage Location for UE-V 1.0](deploying-the-settings-storage-location-for-ue-v-10.md)**|**[Configuring UE-V with Group Policy Objects](configuring-ue-v-with-group-policy-objects.md)**|**[Deploying the Settings Template Catalog for UE-V 1.0](deploying-the-settings-template-catalog-for-ue-v-10.md)**|**[Deploying UE-V Settings Location Templates for UE-V 1.0](deploying-ue-v-settings-location-templates-for-ue-v-10.md)**|**[Deploying the UE-V Agent](deploying-the-ue-v-agent.md)**|**[Installing the UE-V Generator](installing-the-ue-v-generator.md)</span></span>

<a href="" id="operations-for-ue-v-1-0"></a>[<span data-ttu-id="18178-114">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="18178-114">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)  

<span data-ttu-id="18178-115">[Ue-v 1.0](administering-ue-v-10.md) **|** の管理[カスタム Ue-v テンプレートと Ue-v ジェネレーター](working-with-custom-ue-v-templates-and-the-ue-v-generator.md) **|** を使用する[PowerShell と WMI](administering-ue-v-with-powershell-and-wmi.md)  | を使った ue-v の管理[Ue-v 1.0 のセキュリティとプライバシー](security-and-privacy-for-ue-v-10.md)</span><span class="sxs-lookup"><span data-stu-id="18178-115">[Administering UE-V 1.0](administering-ue-v-10.md)**|**[Working with Custom UE-V Templates and the UE-V Generator](working-with-custom-ue-v-templates-and-the-ue-v-generator.md)**|**[Administering UE-V with PowerShell and WMI](administering-ue-v-with-powershell-and-wmi.md)|[Security and Privacy for UE-V 1.0](security-and-privacy-for-ue-v-10.md)</span></span>

<a href="" id="troubleshooting-ue-v-1-0"></a>[<span data-ttu-id="18178-116">UE-V 1.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="18178-116">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)  

### <span data-ttu-id="18178-117">詳細情報</span><span class="sxs-lookup"><span data-stu-id="18178-117">More information</span></span>

<a href="" id="microsoft-user-experience-virtualization--ue-v--1-0-release-notes"></a>[<span data-ttu-id="18178-118">Microsoft User Experience Virtualization (UE-V) 1.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="18178-118">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--10-release-notes.md)  
<span data-ttu-id="18178-119">UE-V 1.0 の更新された製品情報と既知の問題を確認します。</span><span class="sxs-lookup"><span data-stu-id="18178-119">View updated product information and known issues for UE-V 1.0.</span></span>

<a href="" id="mdop-techcenter-page"></a>[<span data-ttu-id="18178-120">MDOP TechCenter ページ</span><span class="sxs-lookup"><span data-stu-id="18178-120">MDOP TechCenter Page</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=225286)  
<span data-ttu-id="18178-121">最新の MDOP 情報とリソースについて説明します。</span><span class="sxs-lookup"><span data-stu-id="18178-121">Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a>[<span data-ttu-id="18178-122">MDOP 情報の操作</span><span class="sxs-lookup"><span data-stu-id="18178-122">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
<span data-ttu-id="18178-123">MDOP テクノロジについては、ドキュメント、ビデオ、およびその他のリソースを参照してください。</span><span class="sxs-lookup"><span data-stu-id="18178-123">Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="18178-124">また、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をフォローして、[フィードバックを送信](mailto:MDOPDocs@microsoft.com)したり、更新プログラムに関する情報を確認したりすることもできます。</span><span class="sxs-lookup"><span data-stu-id="18178-124">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

 

 





