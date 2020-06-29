---
title: ワークスペースのイメージを展開する方法
description: ワークスペースのイメージを展開する方法
author: dansimp
ms.assetid: ccc8e89b-1625-4b58-837e-4c6d93d46070
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4cb16b0a4c278d135fdc9b737aa7a6e9b46115e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827004"
---
# <span data-ttu-id="c70b7-103">ワークスペースのイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c70b7-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="c70b7-104">エンタープライズソフトウェア配布システムを使用している場合、次のいずれかの方法で、クライアントコンピューターに新しい画像を展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c70b7-104">When using an enterprise software distribution system, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="c70b7-105">Web ダウンロード</span><span class="sxs-lookup"><span data-stu-id="c70b7-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="c70b7-106">プレステージイメージ</span><span class="sxs-lookup"><span data-stu-id="c70b7-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="c70b7-107">Web 経由でワークスペースイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c70b7-107">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="c70b7-108">Web 経由でワークスペースイメージを展開するには</span><span class="sxs-lookup"><span data-stu-id="c70b7-108">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="c70b7-109">MED-V イメージをサーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="c70b7-109">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="c70b7-110">画像をアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c70b7-110">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="c70b7-111">エンタープライズソフトウェア配布システムを使用して、ユーザーのコンピューターに MED-V クライアントの .msi パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c70b7-111">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="c70b7-112">MED-V の client.msi パッケージをインストールする方法については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c70b7-112">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="c70b7-113">MED-V クライアントは、初めてインストールされて開始されます。</span><span class="sxs-lookup"><span data-stu-id="c70b7-113">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="c70b7-114">初回起動時に、クライアントは、クライアントのインストールで指定されたサーバーアドレスから画像をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="c70b7-114">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="c70b7-115">イメージの事前ステージングを使用してワークスペースイメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c70b7-115">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="c70b7-116">イメージの事前ステージングを使用してワークスペースイメージを展開するには</span><span class="sxs-lookup"><span data-stu-id="c70b7-116">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="c70b7-117">イメージの事前ステージフォルダーを作成し、そのフォルダーにイメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="c70b7-117">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="c70b7-118">イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c70b7-118">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="c70b7-119">エンタープライズソフトウェア配布システムを使用して、ユーザーのコンピューターに MED-V クライアントの .msi パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c70b7-119">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="c70b7-120">MED-V の client.msi パッケージをインストールする方法については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c70b7-120">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="c70b7-121">MED-V クライアントは、初めてインストールされて開始されます。</span><span class="sxs-lookup"><span data-stu-id="c70b7-121">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="c70b7-122">初めて起動するときに、クライアントは、クライアントのインストールで指定された事前ステージフォルダーから画像を取得します。</span><span class="sxs-lookup"><span data-stu-id="c70b7-122">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <span data-ttu-id="c70b7-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c70b7-123">Related topics</span></span>


[<span data-ttu-id="c70b7-124">イメージ Web 配布サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c70b7-124">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





