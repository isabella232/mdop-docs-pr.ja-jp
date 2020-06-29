---
title: MED-V 2.0 のエンド ツー エンドの展開シナリオ
description: MED-V 2.0 のエンド ツー エンドの展開シナリオ
author: dansimp
ms.assetid: 91bb5a9a-5fb1-4743-8494-9d4dee2ec222
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6d56e70ad359ebf2d76cf3f30f54f73cd9ca1c66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826174"
---
# <span data-ttu-id="35971-103">MED-V 2.0 のエンド ツー エンドの展開シナリオ</span><span class="sxs-lookup"><span data-stu-id="35971-103">End-to-End Deployment Scenario for MED-V 2.0</span></span>


<span data-ttu-id="35971-104">このサンプルシナリオ Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 では、複数のシナリオをエンドツーエンドで使用して、企業内の MED-V コンポーネントを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="35971-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy the MED-V components in your enterprise by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="35971-105">このサンプルシナリオは、個々のシナリオと手順をコンテキストにまとめる際に役立つケーススタディと考えることができます。</span><span class="sxs-lookup"><span data-stu-id="35971-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="35971-106">このセクションでは、企業内のエンドツーエンドのソリューションとして MED-V コンポーネントを展開するための基本的な情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-106">This section provides basic information and directions for deploying MED-V components as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="35971-107">MED-V の展開ステップバイステップのシナリオ</span><span class="sxs-lookup"><span data-stu-id="35971-107">MED-V Deployment Step-by-step Scenario</span></span>


<span data-ttu-id="35971-108">このステップバイステップのシナリオのトピックには、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="35971-108">The topics in this step-by-step scenario include the following:</span></span>

-   <span data-ttu-id="35971-109">[Med-v 2.0 でサポートされている構成](med-v-20-supported-configurations.md)では、環境に Microsoft Enterprise Desktop VIRTUALIZATION (med-v) 2.0 をインストールして実行するために必要な要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-109">[MED-V 2.0 Supported Configurations](med-v-20-supported-configurations.md) discusses the requirements that you must have to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0in your environment.</span></span> <span data-ttu-id="35971-110">このトピックでは、オペレーティングシステム要件、構成要件、および MED-V ワークスペースの要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-110">This topic specifies the operating system requirements, configuration requirements, and MED-V workspace requirements.</span></span> <span data-ttu-id="35971-111">このトピックには、MED-V 2.0 でサポートされている言語に関するローカライズ情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="35971-111">This topic also includes localization information about the languages that MED-V 2.0 supports.</span></span>

-   <span data-ttu-id="35971-112">[Med-v 2.0 展開の概要](med-v-20-deployment-overview.md)企業全体で med-v をインストールして展開するのに役立つ一般的な情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-112">[MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md) discusses general information and instructions to help you install and deploy MED-V throughout your enterprise.</span></span> <span data-ttu-id="35971-113">MED-V コンポーネントはクライアントベースであり、既存のエンタープライズインフラストラクチャとプロセスを使用して配信および管理されます。</span><span class="sxs-lookup"><span data-stu-id="35971-113">The MED-V components are client-based and are delivered and managed by using your existing enterprise infrastructure and processes.</span></span> <span data-ttu-id="35971-114">このトピックでは、med-v ソリューションの概要について説明します。 med-v ソリューションの概要について説明します。この記事では、展開する MED-V のインストールファイルと MED-V コンポーネントに関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="35971-114">This topic provides an overview of the MED-V solution that includes information about the MED-V installation files and the MED-V components that you deploy.</span></span> <span data-ttu-id="35971-115">このトピックでは、MED-V のインストールと展開プロセスの概要についても説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-115">This topic also provides a high-level overview of the MED-V installation and deployment process.</span></span>

-   <span data-ttu-id="35971-116">[Med-v の展開環境を準備する-](prepare-the-deployment-environment-for-med-v.md) hyper-v 2.0 展開用に環境を準備する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-116">[Prepare the Deployment Environment for MED-V](prepare-the-deployment-environment-for-med-v.md) discusses how to prepare your environment for a MED-V 2.0 deployment.</span></span> <span data-ttu-id="35971-117">このセクションでは、Microsoft Windows 7 や Active Directory インフラストラクチャなどの MED-V 環境で必要とされる前提条件について説明します。グループポリシーを使用して、オペレーティングシステム、アプリケーション、ユーザーの設定の一元管理と構成を提供します。</span><span class="sxs-lookup"><span data-stu-id="35971-117">This section describes the prerequisites that are required for the MED-V environment, such as Microsoft Windows 7 and an Active Directory infrastructure in which you use Group Policy to provide centralized management and configuration of operating systems, applications, and users' settings.</span></span> <span data-ttu-id="35971-118">このセクションでは、Windows 仮想 PC や必要な Windows 仮想 PC の更新など、企業全体で MED-V 2.0 をインストールして展開するために必要な前提条件についても説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-118">This section also describes the prerequisites that you must have for installing and deploying MED-V 2.0 throughout your enterprise, such as Windows Virtual PC and the required Windows Virtual PC update.</span></span>

-   <span data-ttu-id="35971-119">[Med-v コンポーネントを展開](deploy-the-med-v-components.md)すると、すべての必要なインストールファイルと med-v コンポーネントをエンタープライズ全体にインストールするさまざまな方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="35971-119">[Deploy the MED-V Components](deploy-the-med-v-components.md) discusses the different ways you can install all of the necessary installation files and MED-V components throughout your enterprise.</span></span> <span data-ttu-id="35971-120">MED-V をインストールして展開するには、通常、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="35971-120">To install and deploy MED-V, you typically follow these steps:</span></span>

    1.  <span data-ttu-id="35971-121">Med-v ワークスペースパッケージを作成するために使用する管理コンピューターに、 **Med-v Workspace パッケージャー**をインストールします。</span><span class="sxs-lookup"><span data-stu-id="35971-121">Install the **MED-V Workspace Packager** on the administrator computer that you will use to build the MED-V workspace packages.</span></span> <span data-ttu-id="35971-122">詳細については、「 [Med-v ワークスペースパッケージャーをインストールする方法](how-to-install-the-med-v-workspace-packager.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35971-122">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

    2.  <span data-ttu-id="35971-123">MED-V ワークスペースパッケージを作成してテストします。</span><span class="sxs-lookup"><span data-stu-id="35971-123">Create and test your MED-V workspace packages.</span></span> <span data-ttu-id="35971-124">詳細については、「 [Med-v ワークスペースパッケージを作成する](create-a-med-v-workspace-package.md)」および「 [Med-v ワークスペースパッケージのテスト](testing-the-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35971-124">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) and [Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md).</span></span>

    3.  <span data-ttu-id="35971-125">会社の既存のアプリケーション展開方法を使用して、エンタープライズ全体で MED-V を展開します。</span><span class="sxs-lookup"><span data-stu-id="35971-125">Deploy MED-V throughout your enterprise by using your company’s existing method for deploying applications.</span></span> <span data-ttu-id="35971-126">詳細については、「 [Med-v ワークスペースパッケージの展開](deploying-the-med-v-workspace-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="35971-126">For more information, see [Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md).</span></span>

## <span data-ttu-id="35971-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="35971-127">Related topics</span></span>


[<span data-ttu-id="35971-128">MED-V の展開</span><span class="sxs-lookup"><span data-stu-id="35971-128">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="35971-129">MED-V 2.0 のエンド ツー エンドのプランニング シナリオ</span><span class="sxs-lookup"><span data-stu-id="35971-129">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="35971-130">MED-V 2.0 のエンド ツー エンドの操作シナリオ</span><span class="sxs-lookup"><span data-stu-id="35971-130">End-to-End Operations Scenario for MED-V 2.0</span></span>](end-to-end-operations-scenario-for-med-v-20.md)

 

 





