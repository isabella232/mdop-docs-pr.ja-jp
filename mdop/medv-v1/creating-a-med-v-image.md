---
title: MED-V イメージの作成
description: MED-V イメージの作成
author: dansimp
ms.assetid: 7cbbcd22-83f5-4b60-825f-781b4c6a2d36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de1c2cd87d85bbe2fc40b9007eba8f86d2ed6f60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812499"
---
# <span data-ttu-id="c9814-103">MED-V イメージの作成</span><span class="sxs-lookup"><span data-stu-id="c9814-103">Creating a MED-V Image</span></span>


## <span data-ttu-id="c9814-104">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="c9814-104">In This Section</span></span>


<span data-ttu-id="c9814-105">このセクションでは、MED-V クライアントと MED-V の管理アプリケーションがインストールされているコンピューターで MED-V イメージを構成する方法について説明し、次の内容について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-105">This section describes how to configure a MED-V image on a computer on which the MED-V client and MED-V management application are installed, and explains the following:</span></span>

<a href="" id="how-to-create-and-test-a-med-v-image"></a>[<span data-ttu-id="c9814-106">MED-V イメージを作成してテストする方法</span><span class="sxs-lookup"><span data-stu-id="c9814-106">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)  
<span data-ttu-id="c9814-107">MED-V イメージの作成方法と、ローカルでのイメージのテスト方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-107">Describes how to create a MED-V image, and then test the image locally.</span></span>

<a href="" id="how-to-pack-a-med-v-image"></a>[<span data-ttu-id="c9814-108">MED-V イメージをパックする方法</span><span class="sxs-lookup"><span data-stu-id="c9814-108">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)  
<span data-ttu-id="c9814-109">展開パッケージに追加したりサーバーにアップロードしたりできるように、MED-V イメージをパックする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-109">Describes how to pack a MED-V image so that it can be added to a deployment package or uploaded to the server.</span></span>

<a href="" id="how-to-upload-a-med-v-image-to-the-server"></a>[<span data-ttu-id="c9814-110">MED-V イメージをサーバーにアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="c9814-110">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)  
<span data-ttu-id="c9814-111">サーバーに MED-V イメージをアップロードする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-111">Describes how to upload a MED-V image to the server.</span></span>

<a href="" id="how-to-localize-a-med-v-image"></a>[<span data-ttu-id="c9814-112">MED-V イメージをローカライズする方法</span><span class="sxs-lookup"><span data-stu-id="c9814-112">How to Localize a MED-V Image</span></span>](how-to-localize-a-med-v-image.md)  
<span data-ttu-id="c9814-113">イメージの抽出またはダウンロードを行って、MED-V イメージをローカライズする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-113">Describes how to localize a MED-V image either through extracting or downloading the image.</span></span>

<a href="" id="how-to-update-a-med-v-image"></a>[<span data-ttu-id="c9814-114">MED-V イメージを更新する方法</span><span class="sxs-lookup"><span data-stu-id="c9814-114">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)  
<span data-ttu-id="c9814-115">MED-V イメージを更新して、新しいバージョンのイメージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-115">Describes how to update a MED-V image to create a new version of the image.</span></span>

<a href="" id="how-to-delete-a-med-v-image"></a>[<span data-ttu-id="c9814-116">MED-V イメージを削除する方法</span><span class="sxs-lookup"><span data-stu-id="c9814-116">How to Delete a MED-V Image</span></span>](how-to-delete-a-med-v-image.md)  
<span data-ttu-id="c9814-117">MED-V イメージを削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="c9814-117">Describes how to delete a MED-V image.</span></span>

<span data-ttu-id="c9814-118">**注** MED-V イメージが構成された後は、MED-V ワークスペースのセットアップの一部として、展開後にクライアントで参加するドメインの手順を実行する必要があるため、コンピューターはドメインに参加してはなりません。</span><span class="sxs-lookup"><span data-stu-id="c9814-118">**Note** After the MED-V image is configured, the computer should not be part of a domain because the join domain procedure should be performed on the client after the deployment, as part of the MED-V workspace setup.</span></span>

 

 

 





