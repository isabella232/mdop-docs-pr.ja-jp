---
title: MBAM 1.0 に対応する環境の準備
description: MBAM 1.0 に対応する環境の準備
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823194"
---
# <span data-ttu-id="016bf-103">MBAM 1.0 に対応する環境の準備</span><span class="sxs-lookup"><span data-stu-id="016bf-103">Preparing your Environment for MBAM 1.0</span></span>


<span data-ttu-id="016bf-104">Microsoft BitLocker の管理と監視 (MBAM) セットアップを始める前に、製品をインストールするために必要な前提条件を満たしていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="016bf-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you have met the necessary prerequisites to install the product.</span></span> <span data-ttu-id="016bf-105">事前に前提条件がわかっている場合は、製品を効率的に展開し、その機能を有効にすることができます。これにより、組織のビジネス目標がより効率的にサポートされます。</span><span class="sxs-lookup"><span data-stu-id="016bf-105">If you know the prerequisites in advance, you can efficiently deploy the product and enable its features, which can support the business objectives of your organization more effectively.</span></span>

## <span data-ttu-id="016bf-106">MBAM 1.0 の展開の前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="016bf-106">Review MBAM 1.0 deployment prerequisites</span></span>


<span data-ttu-id="016bf-107">MBAM クライアントと MBAM サーバーの各機能には、適切にインストールする前に満たす必要がある特定の前提条件があります。</span><span class="sxs-lookup"><span data-stu-id="016bf-107">The MBAM Client and each of the MBAM Server features have specific prerequisites that must be met before they can be successfully installed.</span></span>

<span data-ttu-id="016bf-108">MBAM クライアントと MBAM サーバー機能を正常にインストールするには、MBAM Client または MBAM Server 機能のインストール用に指定されたコンピューターが MBAM セットアップ用に正しく準備されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="016bf-108">To ensure successful installation of MBAM Clients and MBAM Server features, you should plan to ensure that computers specified for MBAM Client or MBAM Server feature installation are properly prepared for MBAM Setup.</span></span>

<span data-ttu-id="016bf-109">**注** MBAM セットアップインストールを開始する前に、すべての前提条件が満たされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="016bf-109">**Note** MBAM Setup verifies if all prerequisites are met before installation starts.</span></span> <span data-ttu-id="016bf-110">満たされていない場合、セットアップは失敗します。</span><span class="sxs-lookup"><span data-stu-id="016bf-110">If they are not met, Setup will fail.</span></span>

 

[<span data-ttu-id="016bf-111">MBAM 1.0 展開の前提条件</span><span class="sxs-lookup"><span data-stu-id="016bf-111">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)

## <span data-ttu-id="016bf-112">MBAM 1.0 グループポリシー要件を計画する</span><span class="sxs-lookup"><span data-stu-id="016bf-112">Plan for MBAM 1.0 Group Policy requirements</span></span>


<span data-ttu-id="016bf-113">MBAM で企業のクライアントを管理するには、環境の暗号化要件のグループポリシーを定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="016bf-113">Before MBAM can manage clients in the enterprise, you must define the Group Policy for the encryption requirements of your environment.</span></span>

<span data-ttu-id="016bf-114">**重要** MBAM は、スタンドアロンの BitLocker ドライブ暗号化のポリシーでは動作しません。</span><span class="sxs-lookup"><span data-stu-id="016bf-114">**Important** MBAM will not work with policies for stand-alone BitLocker drive encryption.</span></span> <span data-ttu-id="016bf-115">MBAM にはグループポリシーを定義する必要があります。そうしないと、BitLocker の暗号化と強制は失敗します。</span><span class="sxs-lookup"><span data-stu-id="016bf-115">Group Policy must be defined for MBAM; otherwise, the BitLocker encryption and enforcement will fail.</span></span>

 

[<span data-ttu-id="016bf-116">MBAM 1.0 グループ ポリシー要件の計画</span><span class="sxs-lookup"><span data-stu-id="016bf-116">Planning for MBAM 1.0 Group Policy Requirements</span></span>](planning-for-mbam-10-group-policy-requirements.md)

## <span data-ttu-id="016bf-117">MBAM 1.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="016bf-117">Plan for MBAM 1.0 administrator roles</span></span>


<span data-ttu-id="016bf-118">MBAM 管理者ロールは、BitLocker の管理と監視のサーバー、コンプライアンスおよび監査レポート機能、コンプライアンスおよび監査ステータスデータベースをインストールするときに、MBAM セットアップによって作成されるローカルグループによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="016bf-118">MBAM administrator roles are managed by local groups that are created by MBAM Setup when you install the following: BitLocker Administration and Monitoring Server, the Compliance and Audit Reports feature, and the Compliance and Audit Status Database.</span></span>

<span data-ttu-id="016bf-119">MBAM ロールのメンバーシップは、より効率的に管理することができます。 ActiveDirectoryDomainServices でセキュリティグループを作成し、そのグループに適切な管理者アカウントを追加して、これらのセキュリティグループを MBAM ローカルグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="016bf-119">The membership of MBAM roles can be managed more effectively if you create security groups in ActiveDirectoryDomainServices, add the appropriate administrator accounts to those groups, and then add those security groups to the MBAM local groups.</span></span> <span data-ttu-id="016bf-120">詳細については、「 [MBAM 管理者ロールを管理する方法](how-to-manage-mbam-administrator-roles-mbam-1.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="016bf-120">For more information, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md).</span></span>

[<span data-ttu-id="016bf-121">MBAM 1.0 管理者ロールの計画</span><span class="sxs-lookup"><span data-stu-id="016bf-121">Planning for MBAM 1.0 Administrator Roles</span></span>](planning-for-mbam-10-administrator-roles.md)

## <span data-ttu-id="016bf-122">MBAM の計画に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="016bf-122">Other resources for MBAM planning</span></span>


[<span data-ttu-id="016bf-123">MBAM 1.0 の計画</span><span class="sxs-lookup"><span data-stu-id="016bf-123">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





