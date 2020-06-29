---
title: ワークスペースのイメージを展開する方法
description: ワークスペースのイメージを展開する方法
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827014"
---
# <span data-ttu-id="8b322-103">ワークスペースのイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="8b322-104">展開パッケージを使用する場合、次のいずれかの方法で、クライアントコンピューターに新しい画像を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="8b322-104">When using a deployment package, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="8b322-105">Web ダウンロード</span><span class="sxs-lookup"><span data-stu-id="8b322-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="8b322-106">プレステージイメージ</span><span class="sxs-lookup"><span data-stu-id="8b322-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [<span data-ttu-id="8b322-107">展開パッケージ内に画像を展開する</span><span class="sxs-lookup"><span data-stu-id="8b322-107">Deploying the image inside the deployment package</span></span>](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="8b322-108">Web 経由でワークスペースイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-108">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="8b322-109">Web 経由でワークスペースイメージを展開するには</span><span class="sxs-lookup"><span data-stu-id="8b322-109">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="8b322-110">MED-V イメージをサーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8b322-110">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="8b322-111">画像をアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-111">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="8b322-112">展開パッケージを作成し、イメージの場所へのサーバーパスを含めます。</span><span class="sxs-lookup"><span data-stu-id="8b322-112">Create a deployment package, and include the server path to the location of the image.</span></span>

    <span data-ttu-id="8b322-113">展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-113">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="8b322-114">パッケージをエンドユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="8b322-114">Deploy the package to end users.</span></span>

    <span data-ttu-id="8b322-115">パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-115">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="8b322-116">MED-V クライアントは、初めてインストールされて開始されます。</span><span class="sxs-lookup"><span data-stu-id="8b322-116">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="8b322-117">初回起動時に、クライアントは、クライアントのインストールで指定されたサーバーアドレスから画像をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="8b322-117">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="8b322-118">イメージの事前ステージングを使用してワークスペースイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-118">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="8b322-119">イメージの事前ステージングを使用してワークスペースイメージを展開するには</span><span class="sxs-lookup"><span data-stu-id="8b322-119">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="8b322-120">イメージの事前ステージフォルダーを作成し、そのフォルダーにイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="8b322-120">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="8b322-121">イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-121">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="8b322-122">展開パッケージを作成し、イメージの事前ステージフォルダーへのパスを含めます。</span><span class="sxs-lookup"><span data-stu-id="8b322-122">Create a deployment package, and include the path to the image pre-stage folder.</span></span>

    <span data-ttu-id="8b322-123">展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-123">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="8b322-124">パッケージをエンドユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="8b322-124">Deploy the package to end users.</span></span>

    <span data-ttu-id="8b322-125">パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-125">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="8b322-126">MED-V クライアントは、初めてインストールされて開始されます。</span><span class="sxs-lookup"><span data-stu-id="8b322-126">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="8b322-127">初めて起動するときに、クライアントは、クライアントのインストールで指定された事前ステージフォルダーから画像を取得します。</span><span class="sxs-lookup"><span data-stu-id="8b322-127">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a><span data-ttu-id="8b322-128">展開パッケージを使用してワークスペースイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-128">How to Deploy a Workspace Image Using a Deployment Package</span></span>


**<span data-ttu-id="8b322-129">展開パッケージを使用してワークスペースイメージを展開するには</span><span class="sxs-lookup"><span data-stu-id="8b322-129">To deploy a workspace image using a deployment package</span></span>**

1.  <span data-ttu-id="8b322-130">展開パッケージを作成し、その画像をパッケージに含めます。</span><span class="sxs-lookup"><span data-stu-id="8b322-130">Create a deployment package, and include the image in the package.</span></span>

    <span data-ttu-id="8b322-131">展開パッケージを作成する方法については、「[展開パッケージを構成する方法](how-to-configure-a-deployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-131">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

2.  <span data-ttu-id="8b322-132">パッケージをエンドユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="8b322-132">Deploy the package to end users.</span></span>

    <span data-ttu-id="8b322-133">パッケージの展開の詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientdeployment-package.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8b322-133">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="8b322-134">パッケージのインストールの一部として、この画像がホストにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="8b322-134">The image is imported to the host as part of the package installation.</span></span>

## <span data-ttu-id="8b322-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8b322-135">Related topics</span></span>


[<span data-ttu-id="8b322-136">イメージ Web 配布サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-136">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

[<span data-ttu-id="8b322-137">展開パッケージを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8b322-137">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

 

 





