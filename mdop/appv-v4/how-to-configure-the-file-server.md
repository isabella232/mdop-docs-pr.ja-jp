---
title: ファイル サーバーを構成する方法
description: ファイル サーバーを構成する方法
author: dansimp
ms.assetid: 0977554c-1741-411b-85e7-7e1cd017542f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8a8971ad5c9f83dec4d0c77a16f1093ef7026b5c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817784"
---
# <span data-ttu-id="3d0de-103">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3d0de-103">How to Configure the File Server</span></span>


<span data-ttu-id="3d0de-104">次の手順を使用して、ファイル共有として使用されるローカルコンピューターを構成し、Application Virtualization デスクトップクライアントとリモートデスクトップサービス (旧ターミナルサービス) のクライアントにストリームアプリケーションを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="3d0de-104">You can use the following procedure to configure a local computer that is used as a file share and streams applications to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="3d0de-105">このシナリオは、既存のハードウェア環境にサーバーインフラストラクチャを追加したくない場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="3d0de-105">This scenario is used when you do not want to add an additional server infrastructure to your existing hardware environment.</span></span>

<span data-ttu-id="3d0de-106">ローカルオフィスにインストールされているファイル共有への配布ポイントとして Application Virtualization Management Server を使用している場合、仮想アプリケーションをファイル共有として使用するコンピューターにストリーミングできるようにするには、このサーバーを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3d0de-106">If you are using an Application Virtualization Management Server as a distribution point to the file share installed in local offices, you must configure this server before virtual applications can be streamed to the computers that are used as file shares.</span></span> <span data-ttu-id="3d0de-107">サーバーとファイル共有を構成すると、SFT ファイルが読み込まれ、保存されるコンテンツディレクトリを設定することになります。</span><span class="sxs-lookup"><span data-stu-id="3d0de-107">When you configure the servers and the file shares, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="3d0de-108">SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3d0de-108">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="3d0de-109">**重要** アプリケーションの仮想化デスクトップクライアントとリモートデスクトップサービスのクライアントに適切にストリーミングするアプリケーションの場合、SFT ファイルは、仮想アプリケーションを保存しているサーバー上のコンテンツディレクトリからストリーミングします。ICO (icon) ファイルと OSD (open software descriptor) ファイルは、別のサーバーからストリーミングするように構成できます。</span><span class="sxs-lookup"><span data-stu-id="3d0de-109">**Important** For applications to stream properly to the Application Virtualization Desktop Client and the Client for Remote Desktop Services, the SFT file streams from the content directory on the server where you store the virtual application; the ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different server.</span></span>

 

**<span data-ttu-id="3d0de-110">Application Virtualization ファイルサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="3d0de-110">To configure the Application Virtualization file server</span></span>**

1.  <span data-ttu-id="3d0de-111">配布ポイントとして使用されるサーバーを構成するには、次のインストール手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="3d0de-111">Complete the following installation procedure to configure the server that is used as the distribution point:</span></span>

    [<span data-ttu-id="3d0de-112">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="3d0de-112">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

    <span data-ttu-id="3d0de-113">**注** インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="3d0de-113">**Note** During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

     

2.  <span data-ttu-id="3d0de-114">ファイル共有として使用している各コンピューターにサーバーをインストールしたときに指定したディレクトリに対応する、\\ コンテンツディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="3d0de-114">Create a \\Content directory, which corresponds to the directory you specified when you installed the server, on each computer that you are using as a file share.</span></span>

    <span data-ttu-id="3d0de-115">**重要** アプリケーションの仮想化デスクトップクライアントを構成して、アプリケーションの仮想化サーバーまたは IIS サーバーからではなく、ファイル共有として使用しているコンピューターからアプリケーションをストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="3d0de-115">**Important** Configure the Application Virtualization Desktop Clients to stream applications from the computer you are using as a file share rather than from an Application Virtualization Server or IIS server.</span></span>

     

3.  <span data-ttu-id="3d0de-116">\\ コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。</span><span class="sxs-lookup"><span data-stu-id="3d0de-116">When the \\Content directory is created, configure this directory as a standard file share.</span></span>

## <span data-ttu-id="3d0de-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3d0de-117">Related topics</span></span>


[<span data-ttu-id="3d0de-118">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="3d0de-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="3d0de-119">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="3d0de-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="3d0de-120">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3d0de-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="3d0de-121">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="3d0de-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="3d0de-122">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3d0de-122">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





