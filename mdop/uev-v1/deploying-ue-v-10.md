---
title: UE-V 1.0 の展開
description: UE-V 1.0 の展開
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827147"
---
# <span data-ttu-id="eb266-103">UE-V 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="eb266-103">Deploying UE-V 1.0</span></span>


<span data-ttu-id="eb266-104">Microsoft User Experience Virtualization (UE-V) でサポートされている展開構成は多数あります。</span><span class="sxs-lookup"><span data-stu-id="eb266-104">There are a number of different deployment configurations that Microsoft User Experience Virtualization (UE-V) supports.</span></span> <span data-ttu-id="eb266-105">このセクションでは、展開のさまざまな段階で完了する必要があるタスクを正常に実行するための一般的な情報と段階的な手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb266-105">This section includes general information and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="eb266-106">UE-V の展開情報</span><span class="sxs-lookup"><span data-stu-id="eb266-106">Deployment information for UE-V</span></span>


<span data-ttu-id="eb266-107">UE-V の展開では、ネットワーク共有上の設定の保存場所と、設定を同期するすべてのコンピューターに UE-V エージェントがインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb266-107">A UE-V deployment requires a settings storage location on a network share and a UE-V agent installed on every computer that synchronizes settings.</span></span> <span data-ttu-id="eb266-108">UE-V のグループポリシーテンプレートを使用して、UE-V の設定を管理できます。</span><span class="sxs-lookup"><span data-stu-id="eb266-108">The UE-V Group Policy templates can be used to manage UE-V settings.</span></span> <span data-ttu-id="eb266-109">次のトピックでは、これらの機能を展開する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="eb266-109">The following topics describe how to deploy these features.</span></span>

[<span data-ttu-id="eb266-110">UE-V 1.0 の設定の保存場所の展開</span><span class="sxs-lookup"><span data-stu-id="eb266-110">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

<span data-ttu-id="eb266-111">すべての UE-V 展開では、同期された設定値を含む設定パッケージが配置されている設定の保存場所が必要です。</span><span class="sxs-lookup"><span data-stu-id="eb266-111">All UE-V deployments require a settings storage location where the settings packages that contain the synchronized setting values are located.</span></span>

[<span data-ttu-id="eb266-112">UE-V エージェントの展開</span><span class="sxs-lookup"><span data-stu-id="eb266-112">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

<span data-ttu-id="eb266-113">UE-V を使用して設定を同期するには、コンピューターで UE-V エージェントをインストールして実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb266-113">To synchronize settings by using UE-V, a computer must have the UE-V Agent installed and running.</span></span>

[<span data-ttu-id="eb266-114">UE-V グループ ポリシー ADMX テンプレートのインストール</span><span class="sxs-lookup"><span data-stu-id="eb266-114">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="eb266-115">UE-V の構成および標準の UE-V 構成を展開する前に、グループポリシーを使って UE-V の設定を事前に構成することができます。</span><span class="sxs-lookup"><span data-stu-id="eb266-115">You can use Group Policy to preconfigure UE-V settings before you deploy the UE-V Agent as well as standard UE-V configuration.</span></span>

## <span data-ttu-id="eb266-116">カスタムテンプレートの展開に関する展開情報</span><span class="sxs-lookup"><span data-stu-id="eb266-116">Deployment information for custom template deployment</span></span>


<span data-ttu-id="eb266-117">基幹業務アプリケーションなど、UE-V に含まれている Microsoft アプリケーション以外のアプリケーションのカスタム設定場所テンプレートの作成を計画している場合は、設定テンプレートカタログを展開することができます。これらのテンプレートを作成するには、UE-V Generator をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb266-117">If you plan to create custom settings location templates for applications other than the Microsoft applications that are included in UE-V, such as line-of-business applications, then you can deploy a settings template catalog and you must install the UE-V Generator to create those templates.</span></span> <span data-ttu-id="eb266-118">詳細については、「 [ue-v 1.0 向けのカスタムテンプレートの展開を計画](planning-for-custom-template-deployment-for-ue-v-10.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb266-118">For more information, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

[<span data-ttu-id="eb266-119">UE-V Generator のインストール</span><span class="sxs-lookup"><span data-stu-id="eb266-119">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="eb266-120">UE-V Generator を使って、既定のアプリケーション以外のアプリケーションの設定を同期できるように、カスタム設定の場所テンプレートを作成、編集、検証します。</span><span class="sxs-lookup"><span data-stu-id="eb266-120">Use the UE-V Generator to create, edit, and validate custom settings location templates that help synchronize settings of applications other than the default applications.</span></span>

[<span data-ttu-id="eb266-121">UE-V 1.0 の設定テンプレート カタログの展開</span><span class="sxs-lookup"><span data-stu-id="eb266-121">Deploying the Settings Template Catalog for UE-V 1.0</span></span>](deploying-the-settings-template-catalog-for-ue-v-10.md)

<span data-ttu-id="eb266-122">UE-V Agent の既定のアプリケーション以外のアプリケーションをサポートするためにカスタム設定の場所テンプレートを展開する必要がある場合は、設定テンプレートカタログを構成して保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb266-122">If you need to deploy custom settings location templates to support applications other than the default applications in the UE-V Agent, you must configure a settings template catalog to store them.</span></span>

[<span data-ttu-id="eb266-123">UE-V 1.0 の UE-V 設定場所テンプレートの展開</span><span class="sxs-lookup"><span data-stu-id="eb266-123">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

<span data-ttu-id="eb266-124">UE-V Agent で既定のアプリケーション以外のアプリケーションを同期する必要がある場合は、UE-V Generator を使用して作成されたカスタム設定の場所テンプレートを、UE-V 設定テンプレートカタログに配布できます。</span><span class="sxs-lookup"><span data-stu-id="eb266-124">If you need to synchronize applications other than the default applications in the UE-V Agent, the custom setting location templates that are created with UE-V Generator can be distributed to the UE-V settings template catalog.</span></span>

<span data-ttu-id="eb266-125">**注** カスタムテンプレートを展開するには、設定テンプレートカタログが必要です。</span><span class="sxs-lookup"><span data-stu-id="eb266-125">**Note** Deploying custom templates requires a settings template catalog.</span></span> <span data-ttu-id="eb266-126">既定の Microsoft アプリケーションテンプレートは、UE-V エージェントと共に展開されます。</span><span class="sxs-lookup"><span data-stu-id="eb266-126">The default Microsoft application templates are deployed with the UE-V Agent.</span></span>

 

## <span data-ttu-id="eb266-127">この製品のトピック</span><span class="sxs-lookup"><span data-stu-id="eb266-127">Topics for this product</span></span>


[<span data-ttu-id="eb266-128">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="eb266-128">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="eb266-129">User Experience Virtualization 1.0 の概要</span><span class="sxs-lookup"><span data-stu-id="eb266-129">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="eb266-130">UE-V 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="eb266-130">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="eb266-131">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="eb266-131">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="eb266-132">UE-V 1.0 のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="eb266-132">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





