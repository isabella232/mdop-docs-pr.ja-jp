---
title: MED-V ワークスペース イメージの更新
description: MED-V ワークスペース イメージの更新
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825854"
---
# <span data-ttu-id="36e9a-103">MED-V ワークスペース イメージの更新</span><span class="sxs-lookup"><span data-stu-id="36e9a-103">Updating a MED-V Workspace Image</span></span>


<span data-ttu-id="36e9a-104">画像は、次のいずれかの方法で更新できます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-104">An image can be updated in one of the following ways:</span></span>

-   <span data-ttu-id="36e9a-105">エンタープライズソフトウェア配布システムを使用して、更新プログラムをゲストオペレーティングシステムにプッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-105">The update can be pushed to the guest operating system using your enterprise software distribution system.</span></span>

-   <span data-ttu-id="36e9a-106">更新プログラムはイメージ Web 配布サーバーにアップロードでき、クライアントによってダウンロードされ、MED-V イメージに適用されます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-106">The update can be uploaded to the image Web distribution server, and then downloaded by the client and applied to the MED-V image.</span></span>

-   <span data-ttu-id="36e9a-107">MED-V の基本イメージを更新して再展開することができます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-107">The MED-V base image can be updated and redeployed.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a><span data-ttu-id="36e9a-108">エンタープライズソフトウェア配布システムを使用して MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="36e9a-108">How to Update a MED-V Image Using an Enterprise Software Distribution System</span></span>


**<span data-ttu-id="36e9a-109">エンタープライズソフトウェア配布システムを使用して MED-V イメージを更新するには</span><span class="sxs-lookup"><span data-stu-id="36e9a-109">To update a MED-V image using an enterprise software distribution system</span></span>**

-   <span data-ttu-id="36e9a-110">使用しているシステムのマニュアルを参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e9a-110">Refer to the documentation of the system you are using.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a><span data-ttu-id="36e9a-111">Web ダウンロードを使用して MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="36e9a-111">How to Update a MED-V Image Using Web Download</span></span>


**<span data-ttu-id="36e9a-112">Web ダウンロードを使用して MED-V イメージを更新するには</span><span class="sxs-lookup"><span data-stu-id="36e9a-112">To update a MED-V image using Web download</span></span>**

1.  <span data-ttu-id="36e9a-113">[**仮想マシン**] タブで、更新される med-v イメージに関連付けられている med-v ワークスペースポリシーに、次の設定が適用されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="36e9a-113">In MED-V management, on the **Virtual Machine** tab, ensure that the following settings are applied to the MED-V workspace policies that are associated with the MED-V image being updated:</span></span>

    -   <span data-ttu-id="36e9a-114">[**新しいバージョンが利用可能になったときに更新を提案**する] チェックボックスがオンになっている。</span><span class="sxs-lookup"><span data-stu-id="36e9a-114">The **Suggest update when a new version is available** check box is selected.</span></span>

    -   <span data-ttu-id="36e9a-115">必要に応じて、[**このワークスペースのイメージをダウンロードするときにトリム転送を使用**する] チェックボックスがオンになっている必要があります。</span><span class="sxs-lookup"><span data-stu-id="36e9a-115">Optionally, the **Clients should use Trim Transfer when downloading images for this Workspace** check box is selected.</span></span>

    <span data-ttu-id="36e9a-116">詳細については、「[仮想マシンの設定を Med-v ワークスペースに適用する方法](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="36e9a-116">For more information, see [How to Apply Virtual Machine Settings to a MED-V Workspace](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md).</span></span>

2.  <span data-ttu-id="36e9a-117">イメージの Web 配布サーバーにイメージの更新をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="36e9a-117">Upload the image update to the image Web distribution server.</span></span>

    <span data-ttu-id="36e9a-118">更新する必要がある画像を含むすべてのクライアントは、更新プログラムを自動的にダウンロードして画像に適用します。</span><span class="sxs-lookup"><span data-stu-id="36e9a-118">All clients with images that need to be updated automatically download the update and apply it to the image.</span></span>

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a><span data-ttu-id="36e9a-119">MED-V ベースイメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="36e9a-119">How to Update a MED-V Base Image</span></span>


**<span data-ttu-id="36e9a-120">MED-V ベースイメージを更新するには</span><span class="sxs-lookup"><span data-stu-id="36e9a-120">To update a MED-V base image</span></span>**

1.  <span data-ttu-id="36e9a-121">仮想 PC2007 で既存の画像を開きます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-121">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="36e9a-122">イメージに必要な変更を加え、イメージを更新します (新しいソフトウェアをインストールするなど)。</span><span class="sxs-lookup"><span data-stu-id="36e9a-122">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="36e9a-123">Virtual PC2007 を閉じます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-123">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="36e9a-124">画像をテストします。</span><span class="sxs-lookup"><span data-stu-id="36e9a-124">Test the image.</span></span>

5.  <span data-ttu-id="36e9a-125">画像のテストが完了したら、既存の画像と同じ名前を使って、その画像をローカルリポジトリにパックします。</span><span class="sxs-lookup"><span data-stu-id="36e9a-125">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="36e9a-126">**注** 画像に既存のバージョンとは異なる名前を指定した場合は、既存の画像の新しいバージョンではなく、新しい画像が作成されます。</span><span class="sxs-lookup"><span data-stu-id="36e9a-126">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="36e9a-127">新しいバージョンをサーバーにアップロードし、イメージの事前ステージフォルダーにプッシュするか、展開パッケージで配布します。</span><span class="sxs-lookup"><span data-stu-id="36e9a-127">Upload the new version to the server, push it to the image pre-stage folder, or distribute it via a deployment package.</span></span>

## <span data-ttu-id="36e9a-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="36e9a-128">Related topics</span></span>


[<span data-ttu-id="36e9a-129">MED-V イメージの作成</span><span class="sxs-lookup"><span data-stu-id="36e9a-129">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="36e9a-130">MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="36e9a-130">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)

[<span data-ttu-id="36e9a-131">MED-V ワークスペース ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="36e9a-131">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="36e9a-132">イメージ Web 配布サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="36e9a-132">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





