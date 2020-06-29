---
title: Application Virtualization Management Server を構成する方法
description: Application Virtualization Management Server を構成する方法
author: dansimp
ms.assetid: a9f96148-bf2d-486f-98c2-23409bfb0935
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6d54dd213efb8d5cbff5d0e730e6dc08c8d19b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817844"
---
# <span data-ttu-id="413a7-103">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="413a7-103">How to Configure the Application Virtualization Management Servers</span></span>


<span data-ttu-id="413a7-104">仮想化されたアプリケーションをアプリケーションの仮想化デスクトップクライアントまたはリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングできるようにするには、Application Virtualization Management Server が構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="413a7-104">Before virtualized applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Management Server must be configured.</span></span> <span data-ttu-id="413a7-105">サーバーを構成するときは、SFT ファイルが読み込まれて保存される*コンテンツディレクトリ*を設定することになります。</span><span class="sxs-lookup"><span data-stu-id="413a7-105">When you configure the server, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="413a7-106">SFT ファイルには、仮想化されたアプリケーション (またはアプリケーション) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="413a7-106">The SFT files contain the virtualized application (or applications).</span></span>

<span data-ttu-id="413a7-107">**重要** Application Virtualization サーバーは、RTSP または RTSPS プロトコルのみを使って、SFT ファイルをデスクトップクライアントとリモートデスクトップサービスのクライアントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="413a7-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="413a7-108">ICO (icon) ファイルと OSD (open software descriptor) ファイルを、別のファイルまたは HTTP サーバーからストリーミングするように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="413a7-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="413a7-109">Application Virtualization Management Server を構成するには</span><span class="sxs-lookup"><span data-stu-id="413a7-109">To configure the Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="413a7-110">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="413a7-110">Complete the following procedure:</span></span>

    [<span data-ttu-id="413a7-111">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="413a7-111">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="413a7-112">**注** インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="413a7-112">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="413a7-113">\\ コンテンツディレクトリに指定した場所に移動し、必要に応じてディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="413a7-113">Navigate to the location that you specified for the \\Content directory, and if necessary, create the directory.</span></span>

3.  <span data-ttu-id="413a7-114">コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。</span><span class="sxs-lookup"><span data-stu-id="413a7-114">When the content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="413a7-115">関連トピック</span><span class="sxs-lookup"><span data-stu-id="413a7-115">Related topics</span></span>


[<span data-ttu-id="413a7-116">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="413a7-116">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="413a7-117">Application Virtualization のシステム要件</span><span class="sxs-lookup"><span data-stu-id="413a7-117">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="413a7-118">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="413a7-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="413a7-119">サーバー ベースの展開用にサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="413a7-119">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

 

 





