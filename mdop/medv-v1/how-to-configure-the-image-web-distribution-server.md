---
title: イメージ Web 配布サーバーを構成する方法
description: イメージ Web 配布サーバーを構成する方法
author: dansimp
ms.assetid: 2d32ae79-dff5-4c05-a412-dd15452b6007
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8a21b14fbaca6bbc09d4c35b4d8fb86365c42e3b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825157"
---
# <span data-ttu-id="2d2a8-103">イメージ Web 配布サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="2d2a8-103">How to Configure the Image Web Distribution Server</span></span>


<span data-ttu-id="2d2a8-104">イメージリポジトリは、イメージの配布に使用されるオプションのサーバーです (管理者は、新しいイメージをアップロードし、クライアントコンピューターは、新しいイメージをアップロードし、クライアントコンピューターは、サーバーを15分ごとに確認して、新しい画像が利用可能な場合は、そのイメージを更新します)。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-104">An image repository is an optional server that is used for image distribution (where administrators upload new images and client computers check the server every 15 minutes and update their image if a new one is available).</span></span>

## <a href="" id="bkmk-configuringanimagereporitoryusingiis"></a>


<span data-ttu-id="2d2a8-105">画像配布サーバーには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-105">An image distribution server requires the following:</span></span>

-   <span data-ttu-id="2d2a8-106">インターネットインフォメーションサービス (IIS) —詳細については、「[インターネットインフォメーションサービス](https://go.microsoft.com/fwlink/?LinkId=142995)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-106">Internet Information Services (IIS)—For information, see [Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=142995).</span></span>

    <span data-ttu-id="2d2a8-107">IIS のインストール中に、役割サービスを追加するときに、次のサポートされている認証方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-107">During the IIS installation, when adding role services, select the following supported authentication methods:</span></span>

    -   **<span data-ttu-id="2d2a8-108">基本認証</span><span class="sxs-lookup"><span data-stu-id="2d2a8-108">Basic Authentication</span></span>**

    -   **<span data-ttu-id="2d2a8-109">Windows 認証</span><span class="sxs-lookup"><span data-stu-id="2d2a8-109">Windows Authentication</span></span>**

    -   **<span data-ttu-id="2d2a8-110">クライアント証明書のマッピング認証</span><span class="sxs-lookup"><span data-stu-id="2d2a8-110">Client Certificate Mapping Authentication</span></span>**

    <span data-ttu-id="2d2a8-111">IIS を構成する場合は、次の情報を含めます。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-111">When configuring IIS, include the following:</span></span>

    -   <span data-ttu-id="2d2a8-112">**MEDVImages**という名前のエイリアスを使用して仮想ディレクトリを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-112">Add a virtual directory, with the alias named **MEDVImages**.</span></span> <span data-ttu-id="2d2a8-113">物理パスは、画像の場所をポイントする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-113">The physical path should point to the location of the images.</span></span>

    -   <span data-ttu-id="2d2a8-114">BITS を有効にします。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-114">Enable BITS.</span></span>

    -   <span data-ttu-id="2d2a8-115">次の MIME の種類を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-115">Add the following MIME types:</span></span>

        -   **<span data-ttu-id="2d2a8-116">ckm (アプリケーション/オクテット-ストリーム)</span><span class="sxs-lookup"><span data-stu-id="2d2a8-116">.ckm (application/octet-stream)</span></span>**

        -   <span data-ttu-id="2d2a8-117">**. index (アプリケーション/オクテット-ストリーム**)</span><span class="sxs-lookup"><span data-stu-id="2d2a8-117">**.index (application/octet-stream**)</span></span>

    -   <span data-ttu-id="2d2a8-118">MED-V サイトで、**すべてのユーザー**に読み取りアクセス許可を追加します。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-118">On the MED-V site, add read permissions to **Everyone**.</span></span>

    -   <span data-ttu-id="2d2a8-119">IIS を再起動します。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-119">Restart IIS.</span></span>

-   <span data-ttu-id="2d2a8-120">IIS 用 BITS サーバー拡張機能: 詳細については、「 [Bits サーバー拡張機能をインストール](https://go.microsoft.com/fwlink/?LinkId=142996)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2d2a8-120">BITS Server Extensions for IIS—For information, see [Install BITS Server Extensions](https://go.microsoft.com/fwlink/?LinkId=142996).</span></span>

## <span data-ttu-id="2d2a8-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2d2a8-121">Related topics</span></span>


[<span data-ttu-id="2d2a8-122">サポートされる構成</span><span class="sxs-lookup"><span data-stu-id="2d2a8-122">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="2d2a8-123">MED-V イメージ リポジトリを設計する</span><span class="sxs-lookup"><span data-stu-id="2d2a8-123">Design the MED-V Image Repositories</span></span>](design-the-med-v-image-repositories.md)

 

 





