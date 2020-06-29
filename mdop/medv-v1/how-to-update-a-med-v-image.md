---
title: MED-V イメージを更新する方法
description: MED-V イメージを更新する方法
author: dansimp
ms.assetid: 61eacf50-3a00-4bb8-b2f3-7350a6467fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f62cbd54d8593646460700a86ea48b5df4ce437
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812498"
---
# <span data-ttu-id="1b666-103">MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="1b666-103">How to Update a MED-V Image</span></span>


## <span data-ttu-id="1b666-104">MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="1b666-104">How to Update a MED-V Image</span></span>


<span data-ttu-id="1b666-105">既存の MED-V イメージを更新して、新しいバージョンのイメージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="1b666-105">An existing MED-V image can be updated, thereby creating a new version of the image.</span></span> <span data-ttu-id="1b666-106">これで、新しいバージョンがクライアントコンピューターに展開され、既存の画像が置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="1b666-106">The new version can then be deployed on client computers, replacing the existing image.</span></span>

<span data-ttu-id="1b666-107">**注** 新しいバージョンがクライアントに展開されると、既存のイメージが上書きされます。</span><span class="sxs-lookup"><span data-stu-id="1b666-107">**Note** When a new version is deployed on the client, it overwrites the existing image.</span></span> <span data-ttu-id="1b666-108">画像を更新するときに、クライアント上のデータを保存する必要がないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="1b666-108">When updating an image, ensure that no data on the client needs to be saved.</span></span>

 

**<span data-ttu-id="1b666-109">MED-V イメージを更新するには</span><span class="sxs-lookup"><span data-stu-id="1b666-109">To update a MED-V image</span></span>**

1.  <span data-ttu-id="1b666-110">仮想 PC2007 で既存の画像を開きます。</span><span class="sxs-lookup"><span data-stu-id="1b666-110">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="1b666-111">イメージに必要な変更を加え、イメージを更新します (新しいソフトウェアをインストールするなど)。</span><span class="sxs-lookup"><span data-stu-id="1b666-111">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="1b666-112">Virtual PC2007 を閉じます。</span><span class="sxs-lookup"><span data-stu-id="1b666-112">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="1b666-113">画像をテストします。</span><span class="sxs-lookup"><span data-stu-id="1b666-113">Test the image.</span></span>

5.  <span data-ttu-id="1b666-114">画像のテストが完了したら、既存の画像と同じ名前を使って、その画像をローカルリポジトリにパックします。</span><span class="sxs-lookup"><span data-stu-id="1b666-114">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="1b666-115">**注** 画像に既存のバージョンとは異なる名前を指定した場合は、既存の画像の新しいバージョンではなく、新しい画像が作成されます。</span><span class="sxs-lookup"><span data-stu-id="1b666-115">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="1b666-116">サーバーに新しいバージョンをアップロードするか、展開パッケージを使用して配布します。</span><span class="sxs-lookup"><span data-stu-id="1b666-116">Upload the new version to the server or distribute it via a deployment package.</span></span>

## <span data-ttu-id="1b666-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1b666-117">Related topics</span></span>


[<span data-ttu-id="1b666-118">MED-V の仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="1b666-118">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="1b666-119">MED-V イメージを作成してテストする方法</span><span class="sxs-lookup"><span data-stu-id="1b666-119">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)

[<span data-ttu-id="1b666-120">MED-V イメージをパックする方法</span><span class="sxs-lookup"><span data-stu-id="1b666-120">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)

[<span data-ttu-id="1b666-121">MED-V イメージをサーバーにアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="1b666-121">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="1b666-122">MED-V ワークスペース イメージの更新</span><span class="sxs-lookup"><span data-stu-id="1b666-122">Updating a MED-V Workspace Image</span></span>](updating-a-med-v-workspace-image.md)

 

 





