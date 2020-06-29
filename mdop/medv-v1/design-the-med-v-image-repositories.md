---
title: MED-V イメージ リポジトリを設計する
description: MED-V イメージ リポジトリを設計する
author: dansimp
ms.assetid: e153154d-2751-4990-b94d-a2d76242c15f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0c59a0dd2d1b3a78bd211c6a6353a86c77d8fc2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823614"
---
# <span data-ttu-id="0fc34-103">MED-V イメージ リポジトリを設計する</span><span class="sxs-lookup"><span data-stu-id="0fc34-103">Design the MED-V Image Repositories</span></span>


<span data-ttu-id="0fc34-104">MED-V イメージを作成してパックした後は、任意の場所にあるファイルサーバーに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-104">After MED-V images are created and packed, they can be stored on a file server in any location.</span></span> <span data-ttu-id="0fc34-105">ファイルは、1つ以上の IIS サーバーによって HTTP または HTTPS 経由で送信される場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-105">The files may be sent over HTTP or HTTPS by one or more IIS servers.</span></span> <span data-ttu-id="0fc34-106">イメージリポジトリは、複数の MED-V インスタンスで共有できます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-106">The image repository can be shared by multiple MED-V instances.</span></span>

<span data-ttu-id="0fc34-107">イメージリポジトリを設計するには、まず、各クライアントに画像を展開する方法と、クライアントにローカルイメージリポジトリが必要かどうかを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-107">To design the image repositories, you must first decide how the images will be deployed to each client and then whether that client requires a local image repository.</span></span> <span data-ttu-id="0fc34-108">各リポジトリは、付随する IIS サーバーと共に設計および配置されます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-108">Each repository is then designed and placed, along with its accompanying IIS server.</span></span>

## <span data-ttu-id="0fc34-109">画像を配置する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="0fc34-109">Determine How Images Will Be Deployed</span></span>


<span data-ttu-id="0fc34-110">各 MED-V ワークスペースに対して、MED-V イメージをクライアントに展開する計画を決定します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-110">For each MED-V workspace, decide how you plan to deploy MED-V images to the client.</span></span> <span data-ttu-id="0fc34-111">これは、パックされた画像を保存するために必要なリポジトリの数と、それらのリポジトリが配置される場所を決定する際に重要となります。その後、リポジトリを設計します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-111">This is important in determining how many repositories are necessary to store the packed images, where those repositories will be placed, and then to design those repositories.</span></span>

<span data-ttu-id="0fc34-112">パックされた画像は、次の方法で展開できます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-112">Packed images can be deployed in the following ways:</span></span>

-   <span data-ttu-id="0fc34-113">ファイルサーバーと IIS サーバーで構成されるイメージ配布サーバーからネットワーク経由でダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-113">Downloaded over the network from an image distribution server, which comprises a file server and IIS server.</span></span>

-   <span data-ttu-id="0fc34-114">USB ドライブや DVD などのリムーバブルメディア。</span><span class="sxs-lookup"><span data-stu-id="0fc34-114">On removable media, such as a USB drive or DVD.</span></span>

-   <span data-ttu-id="0fc34-115">Enterprise software distribution center を使用して、クライアントコンピューター上のイメージストアディレクトリに事前にステージングされている。</span><span class="sxs-lookup"><span data-stu-id="0fc34-115">Pre-staged to an image store directory on the client computer using an enterprise software distribution center.</span></span>

<span data-ttu-id="0fc34-116">各クライアントに MED-V イメージを展開するために使用するメソッドと、その場所にイメージリポジトリが必要かどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-116">Decide which method, or methods, will be used to deploy MED-V images to each of the clients and whether the location will require an image repository.</span></span>

## <span data-ttu-id="0fc34-117">画像リポジトリの数を確認する</span><span class="sxs-lookup"><span data-stu-id="0fc34-117">Determine the Number of Image Repositories</span></span>


<span data-ttu-id="0fc34-118">必要なリポジトリの最小数を決定したので、次のいずれかの条件が当てはまる場合は、さらに多くの情報を追加します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-118">Now that you have determined the minimum number of repositories you need, add more if any of the following criteria apply:</span></span>

-   <span data-ttu-id="0fc34-119">MED-V の画像を分離する組織または規制上の理由: 一部の MED-V イメージは、同じリポジトリ内で共存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-119">Organizational or regulatory reasons to separate the MED-V images—some MED-V images may not be able to coexist in the same repository.</span></span> <span data-ttu-id="0fc34-120">たとえば、機密性の高い個人データの場合、データへのアクセスを必要とする従業員の限定されたユーザーのみが利用できるサーバー上のストレージが必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-120">For example, sensitive personal data may require storage on a server that is only available to a limited set of employees who need access to the data.</span></span>

-   <span data-ttu-id="0fc34-121">分離ネットワークのクライアント—ネットワーク経由でイメージを展開する場合は、分離されたネットワークがあるかどうかを確認し、別のリポジトリが必要かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-121">Clients in isolated networks—if images will be deployed over the network, determine whether any networks are isolated and require a separate repository.</span></span> <span data-ttu-id="0fc34-122">たとえば、多くの場合、組織は運用ネットワークからラボネットワークを分離します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-122">For example, organizations often isolate lab networks from production networks.</span></span>

-   <span data-ttu-id="0fc34-123">リモートネットワークのクライアント: 画像がネットワーク経由で展開される場合、クライアントが MED-V ワークスペースを読み込むときに適切なエクスペリエンスを提供するために十分な帯域幅のないネットワークリンクによって、一部のクライアントコンピューターがリポジトリから分離されることがあります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-123">Clients in remote networks—if images will be deployed over the network, some client machines may be separated from the repository by network links that have insufficient bandwidth to provide an adequate experience when a client loads a MED-V workspace.</span></span> <span data-ttu-id="0fc34-124">必要に応じて、このニーズに対処するために追加の MED-V インスタンスを設計します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-124">If necessary, design additional MED-V instances to address this need.</span></span>

<span data-ttu-id="0fc34-125">これらのリポジトリをデザインに追加します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-125">Add these repositories to the design.</span></span> <span data-ttu-id="0fc34-126">各リポジトリの名前と設計の理由を決定します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-126">Decide on a name for each repository and the reason for designing it.</span></span> <span data-ttu-id="0fc34-127">リポジトリに格納する MED-V イメージと、リポジトリからの画像を含む med-v のクライアントのどちらを読み込むかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-127">Decide which MED-V images the repositories will hold and which MED-V clients will load MED-V workspaces with images from the repository.</span></span>

## <span data-ttu-id="0fc34-128">イメージリポジトリを設計して配置する</span><span class="sxs-lookup"><span data-stu-id="0fc34-128">Design and Place the Image Repositories</span></span>


<span data-ttu-id="0fc34-129">クライアントが新しい画像を利用できるようになると、クライアントはイメージのダウンロードを開始します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-129">When a new image is available to clients, clients begin downloading the image, possibly simultaneously.</span></span> <span data-ttu-id="0fc34-130">これにより、リポジトリで需要が高くなり、イメージリポジトリの設計時に考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-130">This creates a high demand on the repository and must be taken into account when designing the image repository.</span></span>

<span data-ttu-id="0fc34-131">各リポジトリについて、保存するデータの量を決定します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-131">For each repository, determine the amount of data it will store.</span></span> <span data-ttu-id="0fc34-132">リポジトリに格納される画像のサイズを合計します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-132">Sum the sizes of images that will be stored in the repository.</span></span> <span data-ttu-id="0fc34-133">これは、ファイルサーバー上で必要なディスク領域の値です。</span><span class="sxs-lookup"><span data-stu-id="0fc34-133">This is the value of the disk space required on the file server.</span></span>

<span data-ttu-id="0fc34-134">次に、リポジトリから MED-V イメージをダウンロードする可能性のあるクライアントの数を追加します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-134">Next, add up the number of clients that may download MED-V images from the repository.</span></span> <span data-ttu-id="0fc34-135">これは、新しい MED-V イメージがリポジトリに読み込まれたときに発生する可能性がある同時ダウンロードの最大数です。</span><span class="sxs-lookup"><span data-stu-id="0fc34-135">This is the maximum number of concurrent downloads that can occur when a new MED-V image is loaded into the repository.</span></span> <span data-ttu-id="0fc34-136">このファイルサーバーは、作成する IO 要求を満たすことができるディスクサブシステムで設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-136">The file server must be designed with a disk subsystem that can meet the IO demands this will create.</span></span>

<span data-ttu-id="0fc34-137">イメージリポジトリは、MED-V サーバーと、SQL Server を実行しているサーバー、またはリモートファイル共有の同じシステム上に存在することができます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-137">The image repository can reside on the same system as the MED-V server and the server running SQL Server, or on a remote file share.</span></span> <span data-ttu-id="0fc34-138">また、Windows Server2008 Hyper-v VM で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-138">You can also run it in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="0fc34-139">イメージリポジトリがサービスを実行しているクライアントのネットワーク上の場所を確認し、それらのクライアントのサービスレベルの期待値を満たす十分な帯域幅があるネットワーク上の場所にリポジトリを配置します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-139">Check the network location of the clients that the image repository will service, and place the repository in a network location where it will have sufficient bandwidth to meet the service level expectations of those clients.</span></span>

### <span data-ttu-id="0fc34-140">フォールトトレランス</span><span class="sxs-lookup"><span data-stu-id="0fc34-140">Fault Tolerance</span></span>

<span data-ttu-id="0fc34-141">イメージリポジトリが利用できない場合、クライアントは、新しいまたは更新された MED-V イメージをダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="0fc34-141">If the image repository is unavailable, clients will not be able to download new or updated MED-V images.</span></span> <span data-ttu-id="0fc34-142">ファイルサーバーとフォールトトレラントディスクのフォールトトレランスオプションを設計するには、「 [MICROSOFT SQL server 2008 ガイドのインフラストラクチャ計画と設計](https://go.microsoft.com/fwlink/?LinkId=163302)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fc34-142">To design fault-tolerance options for the file server and fault-tolerant disks, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide.</span></span>

## <span data-ttu-id="0fc34-143">IIS サーバーを設計して配置する</span><span class="sxs-lookup"><span data-stu-id="0fc34-143">Design and Place the IIS Servers</span></span>


<span data-ttu-id="0fc34-144">このセクションは、クライアントが HTTP または HTTPS を使ってネットワーク経由で画像ファイルをダウンロードする場合にのみ関連します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-144">This section is only relevant if clients will download image files over the network using HTTP or HTTPS.</span></span>

<span data-ttu-id="0fc34-145">IIS サーバーは、MED-V サーバーと SQL Server を実行しているサーバーと同じシステム上で共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-145">The IIS server can coexist on the same system as the MED-V server and the server running SQL Server.</span></span> <span data-ttu-id="0fc34-146">また、Windows Server2008 Hyper-v VM で実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-146">It can also run in a Windows Server2008 Hyper-V VM.</span></span> <span data-ttu-id="0fc34-147">IIS サーバーインフラストラクチャには、組織のサービスレベルの期待値内でクライアントに画像を配信するための十分なスループットが必要です。</span><span class="sxs-lookup"><span data-stu-id="0fc34-147">The IIS server infrastructure must have sufficient throughput to deliver images to clients within the service level expectations of the organization.</span></span> <span data-ttu-id="0fc34-148">これによって作成される IO 要求を満たすことができるディスクサブシステムで設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0fc34-148">It must be designed with a disk subsystem that can meet the IO demands this creates.</span></span>

<span data-ttu-id="0fc34-149">各イメージリポジトリについて、IIS を使用して、MED-V イメージをダウンロードできるクライアントの数を合計します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-149">For each image repository, sum the number of clients that may download MED-V images using IIS.</span></span> <span data-ttu-id="0fc34-150">これは、画像がリポジトリに読み込まれたときに発生する可能性がある同時ダウンロードの最大数です。</span><span class="sxs-lookup"><span data-stu-id="0fc34-150">This is the maximum number of concurrent downloads that can occur when an image is loaded into the repository.</span></span> <span data-ttu-id="0fc34-151">「[プロジェクトのスコープを定義](define-the-project-scope.md)して、IIS サーバーインフラストラクチャの設計を計画し、リポジトリに割り当てる適切な帯域幅を決定する」で決定されたスループットの合計とサービスレベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="0fc34-151">Use the throughput sum and the service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to plan the design of the IIS server infrastructure and to determine the appropriate amount of bandwidth to allocate for the repository.</span></span>

<span data-ttu-id="0fc34-152">IIS インフラストラクチャを設計するには、『 [Microsoft インターネットインフォメーションサービス](https://go.microsoft.com/fwlink/?LinkId=160826)ガイド』を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fc34-152">To design the IIS infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

### <span data-ttu-id="0fc34-153">フォールトトレランス</span><span class="sxs-lookup"><span data-stu-id="0fc34-153">Fault Tolerance</span></span>

<span data-ttu-id="0fc34-154">IIS サーバーインフラストラクチャを利用できない場合、クライアントは、新しいイメージや更新された画像をダウンロードできません。</span><span class="sxs-lookup"><span data-stu-id="0fc34-154">If the IIS server infrastructure is unavailable, clients will not be able to download new or updated images.</span></span> <span data-ttu-id="0fc34-155">フォールトトレランスを構成するために、Windows Server2008 ベースの IIS サーバーをフェールオーバークラスターに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="0fc34-155">To configure fault tolerance, the Windows Server2008-based IIS server can be placed in a failover cluster.</span></span> <span data-ttu-id="0fc34-156">IIS サーバーインフラストラクチャのフォールトトレランスを設計するには、『 [Microsoft インターネットインフォメーションサービス](https://go.microsoft.com/fwlink/?LinkId=160826)ガイド』を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0fc34-156">To design the fault tolerance for the IIS server infrastructure, see the [Infrastructure Planning and Design Microsoft Internet Information Services](https://go.microsoft.com/fwlink/?LinkId=160826) guide.</span></span>

## <span data-ttu-id="0fc34-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0fc34-157">Related topics</span></span>


[<span data-ttu-id="0fc34-158">エンタープライズ ソフトウェア配布システムを使用した MED-V ワークスペースの展開</span><span class="sxs-lookup"><span data-stu-id="0fc34-158">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)

[<span data-ttu-id="0fc34-159">展開パッケージを使用した MED-V ワークスペースの展開</span><span class="sxs-lookup"><span data-stu-id="0fc34-159">Deploying a MED-V Workspace Using a Deployment Package</span></span>](deploying-a-med-v-workspace-using-a-deployment-package.md)

 

 





