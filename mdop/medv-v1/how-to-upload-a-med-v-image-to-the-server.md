---
title: MED-V イメージをサーバーにアップロードする方法
description: MED-V イメージをサーバーにアップロードする方法
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825704"
---
# <span data-ttu-id="74b39-103">MED-V イメージをサーバーにアップロードする方法</span><span class="sxs-lookup"><span data-stu-id="74b39-103">How to Upload a MED-V Image to the Server</span></span>


<span data-ttu-id="74b39-104">MED-V イメージのテストが完了したら、それをパックしてからサーバーにアップロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="74b39-104">After a MED-V image has been tested, it can be packed and then uploaded to the server.</span></span> <span data-ttu-id="74b39-105">画像 Web 配布サーバーの構成の詳細については、「[イメージ Web 配布サーバーを構成する方法](how-to-configure-the-image-web-distribution-server.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b39-105">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span>

<span data-ttu-id="74b39-106">MED-V イメージがパックされてサーバーにアップロードされると、エンタープライズソフトウェア配布センターを使用してユーザーに配布するか、展開パッケージを使用してユーザーがダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="74b39-106">Once a MED-V image is packed and uploaded to the server, it can be distributed to users by using an enterprise software distribution center, or it can be downloaded by users using a deployment package.</span></span> <span data-ttu-id="74b39-107">エンタープライズソフトウェアの配布センターを使用した展開については、「[エンタープライズソフトウェアの配布システムを使用した Med-v ワークスペースの展開](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="74b39-107">For information on deployment using an enterprise software distribution center, see [Deploying a MED-V Workspace Using an Enterprise Software Distribution System](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md).</span></span> <span data-ttu-id="74b39-108">パッケージを使用した展開について詳しくは、「[展開パッケージを使用した Med-v ワークスペースの展開](deploying-a-med-v-workspace-using-a-deployment-package.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="74b39-108">For information on deployment using a package, see [Deploying a MED-V Workspace Using a Deployment Package](deploying-a-med-v-workspace-using-a-deployment-package.md).</span></span>

**<span data-ttu-id="74b39-109">注</span><span class="sxs-lookup"><span data-stu-id="74b39-109">Note</span></span>**  
<span data-ttu-id="74b39-110">画像をアップロードする前に、Web プロキシがブラウザーの設定で定義されていないこと、および Windows Update が現在実行されていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="74b39-110">Before uploading an image, verify that a Web proxy is not defined in your browser settings and that Windows Update is not currently running.</span></span>



**<span data-ttu-id="74b39-111">サーバーに MED-V イメージをアップロードするには</span><span class="sxs-lookup"><span data-stu-id="74b39-111">To upload a MED-V image to the server</span></span>**

1.  <span data-ttu-id="74b39-112">[**ローカルパック**されたイメージ] ウィンドウで、作成した画像を選択します。</span><span class="sxs-lookup"><span data-stu-id="74b39-112">In the **Local Packed Images** pane, select the image you created.</span></span>

2.  <span data-ttu-id="74b39-113">[**アップロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="74b39-113">Click **Upload**.</span></span>

    <span data-ttu-id="74b39-114">画像がサーバーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="74b39-114">The image is uploaded to the server.</span></span> <span data-ttu-id="74b39-115">これには時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="74b39-115">This might take a considerable amount of time.</span></span>

    <span data-ttu-id="74b39-116">サーバー上の画像は、次の表に示すプロパティで定義されています。</span><span class="sxs-lookup"><span data-stu-id="74b39-116">Images on the server are defined with the properties listed in the following table.</span></span>

**<span data-ttu-id="74b39-117">サーバープロパティでのパックされた画像</span><span class="sxs-lookup"><span data-stu-id="74b39-117">Packed Images on Server Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="74b39-118">プロパティ</span><span class="sxs-lookup"><span data-stu-id="74b39-118">Property</span></span></th>
<th align="left"><span data-ttu-id="74b39-119">説明</span><span class="sxs-lookup"><span data-stu-id="74b39-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="74b39-120">画像名</span><span class="sxs-lookup"><span data-stu-id="74b39-120">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b39-121">管理者がイメージを作成したときに定義されたパックされたイメージの名前です。</span><span class="sxs-lookup"><span data-stu-id="74b39-121">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="74b39-122">バージョン</span><span class="sxs-lookup"><span data-stu-id="74b39-122">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b39-123">表示される画像のバージョン。</span><span class="sxs-lookup"><span data-stu-id="74b39-123">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="74b39-124">注</span><span class="sxs-lookup"><span data-stu-id="74b39-124">Note</span></span></strong><br/><p><span data-ttu-id="74b39-125">削除しない限り、以前のすべてのバージョンは保持されます。</span><span class="sxs-lookup"><span data-stu-id="74b39-125">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="74b39-126">ファイルサイズ (圧縮済み)</span><span class="sxs-lookup"><span data-stu-id="74b39-126">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b39-127">画像の物理圧縮サイズ。</span><span class="sxs-lookup"><span data-stu-id="74b39-127">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="74b39-128">画像サイズ (非圧縮)</span><span class="sxs-lookup"><span data-stu-id="74b39-128">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b39-129">画像の圧縮されていない物理サイズ。</span><span class="sxs-lookup"><span data-stu-id="74b39-129">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="74b39-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="74b39-130">Related topics</span></span>


[<span data-ttu-id="74b39-131">MED-V クライアントと MED-V 管理コンソールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="74b39-131">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="74b39-132">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="74b39-132">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="74b39-133">MED-V の仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="74b39-133">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="74b39-134">MED-V イメージをパックする方法</span><span class="sxs-lookup"><span data-stu-id="74b39-134">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)









