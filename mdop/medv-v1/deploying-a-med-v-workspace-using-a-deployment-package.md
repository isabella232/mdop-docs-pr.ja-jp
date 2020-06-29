---
title: 展開パッケージを使用した MED-V ワークスペースの展開
description: 展開パッケージを使用した MED-V ワークスペースの展開
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823634"
---
# <span data-ttu-id="a56e7-103">展開パッケージを使用した MED-V ワークスペースの展開</span><span class="sxs-lookup"><span data-stu-id="a56e7-103">Deploying a MED-V Workspace Using a Deployment Package</span></span>


<span data-ttu-id="a56e7-104">展開パッケージのインストールでは、必要なすべての前提条件と、管理者によって定義されたすべての設定と共に、MED-V クライアントをインストールする方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-104">The deployment package installation provides a method of installing MED-V client together with all its required prerequisites as well as any settings predefined by the administrator.</span></span>

<span data-ttu-id="a56e7-105">展開パッケージを使用する場合、パッケージは共有ネットワークまたはリムーバブルメディア経由で配布されます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-105">When using a deployment package, the package is distributed via a shared network or removable media.</span></span> <span data-ttu-id="a56e7-106">画像はパッケージに含めることも、個別に配布することもできます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-106">The image can be included in the package or can be distributed separately.</span></span>

<span data-ttu-id="a56e7-107">展開パッケージを作成する前に、展開の準備が整った MED-V イメージを作成していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a56e7-107">Before creating a deployment package, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="a56e7-108">MED-V イメージの作成について詳しくは、「 [Med-v イメージを作成](creating-a-med-v-image.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-108">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="a56e7-109">MED-V イメージの準備が整ったら、環境にイメージを配布するための最適な方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-109">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="a56e7-110">画像は、次のいずれかの方法で配布できます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-110">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="a56e7-111">Web にアップロードされ、Web ダウンロードによって配布されます。必要に応じて、Trim Transfer テクノロジを使用します。</span><span class="sxs-lookup"><span data-stu-id="a56e7-111">Uploaded to the Web and distributed via Web download, optionally using Trim Transfer technology.</span></span>

-   <span data-ttu-id="a56e7-112">プレステージイメージを使用して配布されます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-112">Distributed using image pre-staging.</span></span>

-   <span data-ttu-id="a56e7-113">展開パッケージに含まれており、他のすべての MED-V コンポーネントと共に配布されます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-113">Included in the deployment package and distributed together with all the other MED-V components.</span></span>

<span data-ttu-id="a56e7-114">画像がパッケージに含まれている場合、その画像に必要なその他の構成はありません。</span><span class="sxs-lookup"><span data-stu-id="a56e7-114">If the image will be included in the package, no other configurations are necessary for the image.</span></span> <span data-ttu-id="a56e7-115">画像が展開パッケージに含まれない場合は、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="a56e7-115">If the image will not be included in the deployment package, do one of the following:</span></span>

-   <span data-ttu-id="a56e7-116">Web 経由でイメージを展開する場合は、イメージ Web 配布サーバーに MED-V イメージをアップロードします。</span><span class="sxs-lookup"><span data-stu-id="a56e7-116">If you are deploying the image via the Web, upload the MED-V image to the image Web distribution server.</span></span> <span data-ttu-id="a56e7-117">画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-117">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="a56e7-118">画像をサーバーにアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-118">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

-   <span data-ttu-id="a56e7-119">イメージのプレステージでイメージを展開する場合は、プレステージフォルダーを構成し、そのフォルダーに MED-V イメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="a56e7-119">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="a56e7-120">イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-120">For more information on configuring the image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="a56e7-121">**注** イメージの事前ステージングを使用している場合は、展開パッケージを作成する前に、イメージの事前ステージフォルダーを構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a56e7-121">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to creating the deployment package.</span></span> <span data-ttu-id="a56e7-122">フォルダーパスは展開パッケージに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a56e7-122">The folder path needs to be included in the deployment package.</span></span>

 

<span data-ttu-id="a56e7-123">最後に、展開パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="a56e7-123">Finally, create the deployment package.</span></span> <span data-ttu-id="a56e7-124">展開パッケージの作成の詳細については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-124">For more information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span> <span data-ttu-id="a56e7-125">パッケージが完了したら、パッケージを展開用に配布します。</span><span class="sxs-lookup"><span data-stu-id="a56e7-125">After the package is complete, distribute it for deployment.</span></span>

<span data-ttu-id="a56e7-126">展開パッケージが配布された後、MED-V クライアントをインストールして、イメージを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="a56e7-126">After the deployment package is distributed, MED-V client can be installed and the image deployed.</span></span> <span data-ttu-id="a56e7-127">MED-V クライアントのインストールの詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-127">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span> <span data-ttu-id="a56e7-128">イメージの展開の詳細については、「[ワークスペースイメージを展開する方法](how-to-deploy-a-workspace-imagedeployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a56e7-128">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imagedeployment-package.md).</span></span>

 

 





