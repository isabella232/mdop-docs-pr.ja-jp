---
title: MBAM 2.0 に対応する環境の準備
description: MBAM 2.0 に対応する環境の準備
author: dansimp
ms.assetid: 5fb01da9-620e-4992-9e54-2ed3fb69e6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1be989112d456064db302952d50159d00b5597a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825607"
---
# <span data-ttu-id="82583-103">MBAM 2.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="82583-103">Preparing your Environment for MBAM 2.0</span></span>


<span data-ttu-id="82583-104">Microsoft BitLocker の管理と監視 (MBAM) のセットアップを開始する前に、製品をインストールするための前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="82583-104">Before beginning Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should make sure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="82583-105">前提条件が事前に判明していることがわかっている場合は、組織のビジネス目標を効率的にサポートするために、製品を効率的に展開し、その機能を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="82583-105">When you know what the prerequisites are ahead of time, you can efficiently deploy the product and enable its features so that it most effectively supports your organization’s business objectives.</span></span>

<span data-ttu-id="82583-106">Microsoft System Center Configuration Manager 2007 または MicrosoftSystemCenter2012 ConfigurationManager を使用して Microsoft BitLocker の管理と監視を展開している場合は、「 [Configuration manager で MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82583-106">If you are deploying Microsoft BitLocker Administration and Monitoring with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

## <span data-ttu-id="82583-107">MBAM 2.0 の展開の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="82583-107">Review MBAM 2.0 Deployment Prerequisites</span></span>


<span data-ttu-id="82583-108">MBAM クライアントと MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="82583-108">The MBAM Client and each of the MBAM Server features have specific prerequisites that must be met before they can be successfully installed.</span></span>

<span data-ttu-id="82583-109">MBAM クライアントと MBAM サーバー機能を正常にインストールするには、MBAM Client または MBAM Server 機能のインストール用に指定されたコンピューターが、MBAM セットアップ用に適切に準備されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82583-109">To ensure successful installation of MBAM Clients and MBAM Server features, ensure that computers specified for MBAM Client or MBAM Server feature installation are properly prepared for MBAM Setup.</span></span>

<span data-ttu-id="82583-110">**注** MBAM セットアップインストールを開始する前に、すべての前提条件が満たされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="82583-110">**Note** MBAM Setup checks that all prerequisites are met before installation starts.</span></span> <span data-ttu-id="82583-111">すべての前提条件が満たされていない場合、セットアップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="82583-111">If all prerequisites are not met, Setup will fail.</span></span>

 

[<span data-ttu-id="82583-112">MBAM 2.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="82583-112">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)

## <span data-ttu-id="82583-113">MBAM 2.0 グループポリシー要件を計画する</span><span class="sxs-lookup"><span data-stu-id="82583-113">Plan for MBAM 2.0 Group Policy Requirements</span></span>


<span data-ttu-id="82583-114">MBAM で企業のクライアントを管理するには、環境の暗号化要件のグループポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="82583-114">Before MBAM can manage clients in the enterprise, you must define Group Policy for the encryption requirements of your environment.</span></span>

<span data-ttu-id="82583-115">**重要** MBAM は、スタンドアロンの BitLocker ドライブ暗号化のポリシーでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="82583-115">**Important** MBAM will not work with policies for stand-alone BitLocker drive encryption.</span></span> <span data-ttu-id="82583-116">MBAM には、グループポリシー設定を定義する必要があります。または、BitLocker 暗号化と強制適用は失敗します。</span><span class="sxs-lookup"><span data-stu-id="82583-116">Group Policy settings must be defined for MBAM, or BitLocker encryption and enforcement will fail.</span></span>

 

[<span data-ttu-id="82583-117">MBAM 2.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="82583-117">Planning for MBAM 2.0 Group Policy Requirements</span></span>](planning-for-mbam-20-group-policy-requirements-mbam-2.md)

## <span data-ttu-id="82583-118">MBAM 2.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="82583-118">Plan for MBAM 2.0 Administrator Roles</span></span>


<span data-ttu-id="82583-119">MBAM 管理者ロールは、BitLocker の管理および監視サーバー、コンプライアンスおよび監査レポート機能、コンプライアンスおよび監査ステータスデータベースをインストールするときに、MBAM セットアップによって作成されるローカルグループによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="82583-119">MBAM administrator roles are managed by local groups that are created by MBAM Setup when you install the BitLocker Administration and Monitoring Server, the Compliance and Audit Reports feature, and the Compliance and Audit Status Database.</span></span>

<span data-ttu-id="82583-120">Microsoft BitLocker の管理と監視の役割のメンバーシップは、ActiveDirectoryDomainServices でセキュリティグループを作成し、適切な管理者アカウントをこれらのグループに追加して、これらのセキュリティグループを BitLocker 管理とローカルグループの監視に追加することによって、最適な管理を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="82583-120">The membership of Microsoft BitLocker Administration and Monitoring roles can best be managed by creating security groups in ActiveDirectoryDomainServices, adding the appropriate administrator accounts to those groups, and then adding those security groups to the BitLocker Administration and Monitoring local groups.</span></span> <span data-ttu-id="82583-121">詳細については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82583-121">For more information, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md).</span></span>

## <span data-ttu-id="82583-122">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="82583-122">Other Resources for MBAM Planning</span></span>


[<span data-ttu-id="82583-123">MBAM 2.0 の計画</span><span class="sxs-lookup"><span data-stu-id="82583-123">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="82583-124">MBAM 2.0 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="82583-124">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)

 

 





