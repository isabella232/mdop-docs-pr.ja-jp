---
title: エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開
description: エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823627"
---
# <span data-ttu-id="82c78-103">エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開</span><span class="sxs-lookup"><span data-stu-id="82c78-103">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>


<span data-ttu-id="82c78-104">MED-V クライアントは、Microsoft System Center Configuration Manager などのエンタープライズソフトウェア配布システムを使用して配布できます。</span><span class="sxs-lookup"><span data-stu-id="82c78-104">MED-V client can be distributed using an enterprise software distribution system, such as Microsoft System Center Configuration Manager.</span></span>

<span data-ttu-id="82c78-105">**注** Microsoft System Center Configuration Manager を使用して MED-V をインストールする場合は、MED-V のパッケージを作成するときに、[実行] モードを [管理者権限] に設定します。</span><span class="sxs-lookup"><span data-stu-id="82c78-105">**Note** If MED-V is installed by using Microsoft System Center Configuration Manager, when creating a package for MED-V, set the run mode to administrative rights.</span></span>

 

<span data-ttu-id="82c78-106">エンタープライズソフトウェア配布システムを使用して MED-V を展開する前に、展開の準備が整った MED-V イメージを作成したことを確認します。</span><span class="sxs-lookup"><span data-stu-id="82c78-106">Before deploying MED-V using an enterprise software distribution system, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="82c78-107">MED-V イメージの作成について詳しくは、「 [Med-v イメージを作成](creating-a-med-v-image.md)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="82c78-107">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="82c78-108">MED-V イメージの準備が整ったら、環境にイメージを配布するための最適な方法を検討してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-108">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="82c78-109">画像は、次のいずれかの方法で配布できます。</span><span class="sxs-lookup"><span data-stu-id="82c78-109">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="82c78-110">Web にアップロードされ、Web ダウンロードによって配布されます。必要に応じて、Trim Transfer テクノロジを利用できます。</span><span class="sxs-lookup"><span data-stu-id="82c78-110">Uploaded to the Web and distributed via Web download, optionally utilizing Trim Transfer technology.</span></span>

-   <span data-ttu-id="82c78-111">プレステージイメージを使用して配布されます。</span><span class="sxs-lookup"><span data-stu-id="82c78-111">Distributed using image pre-staging.</span></span>

## <span data-ttu-id="82c78-112">Web 経由でのイメージの展開</span><span class="sxs-lookup"><span data-stu-id="82c78-112">Deploying the Image via the Web</span></span>


<span data-ttu-id="82c78-113">Web 経由で画像を展開する場合は、MED-V イメージを画像 Web 配布サーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="82c78-113">If you are deploying the image via the Web, upload the MED-V image to an image Web distribution server.</span></span> <span data-ttu-id="82c78-114">画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-114">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="82c78-115">画像をサーバーにアップロードする方法については、「 [Med-v イメージをサーバーにアップロードする方法](how-to-upload-a-med-v-image-to-the-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-115">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

## <span data-ttu-id="82c78-116">プレステージ経由でのイメージの展開</span><span class="sxs-lookup"><span data-stu-id="82c78-116">Deploying the Image via Pre-staging</span></span>


<span data-ttu-id="82c78-117">イメージのプレステージでイメージを展開する場合は、プレステージフォルダーを構成し、そのフォルダーに MED-V イメージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="82c78-117">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="82c78-118">イメージの事前ステージングの構成の詳細については、「[イメージの事前ステージングを構成する方法](how-to-configure-image-pre-staging.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-118">For more information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="82c78-119">**注** イメージの事前ステージングを使用している場合は、client.msi パッケージをプッシュする前に、イメージの事前ステージフォルダーを構成することが重要です。</span><span class="sxs-lookup"><span data-stu-id="82c78-119">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to pushing the client .msi package.</span></span> <span data-ttu-id="82c78-120">フォルダーパスは、client.msi パッケージに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="82c78-120">The folder path needs to be included in the client .msi package.</span></span>

 

<span data-ttu-id="82c78-121">最後に、エンタープライズソフトウェアの配布センターを使用して、client.msi パッケージをプッシュします。</span><span class="sxs-lookup"><span data-stu-id="82c78-121">Finally, push the client .msi package using your enterprise software distribution center.</span></span> <span data-ttu-id="82c78-122">その後、MED-V をインストールして、イメージを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="82c78-122">MED-V can then be installed and the image deployed.</span></span> <span data-ttu-id="82c78-123">MED-V クライアントのインストールの詳細については、「 [Med-v クライアントをインストールする方法](how-to-install-med-v-clientesds.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-123">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span> <span data-ttu-id="82c78-124">イメージの展開の詳細については、「[ワークスペースイメージを展開する方法](how-to-deploy-a-workspace-imageesds.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="82c78-124">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imageesds.md).</span></span>

 

 





