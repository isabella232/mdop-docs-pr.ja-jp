---
title: Application Virtualization Streaming Server を構成する方法
description: Application Virtualization Streaming Server を構成する方法
author: dansimp
ms.assetid: 3e2dde35-9d72-40ba-9fdf-d0338bd4d561
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0ec5497b010d18bcba60e81e96cbe6334c27fb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817824"
---
# <span data-ttu-id="75ef2-103">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="75ef2-103">How to Configure the Application Virtualization Streaming Servers</span></span>


<span data-ttu-id="75ef2-104">仮想アプリケーションをアプリケーションの仮想化デスクトップクライアントまたはリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングできるようにするには、Application Virtualization ストリーミングサーバーが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ef2-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client or the Client for Remote Desktop Services (formerly Terminal Services), the Application Virtualization Streaming Servers must be configured.</span></span> <span data-ttu-id="75ef2-105">サーバーを構成するときは、SFT ファイルが読み込まれて保存される*コンテンツディレクトリ*を設定することになります。</span><span class="sxs-lookup"><span data-stu-id="75ef2-105">When you configure the servers, you are setting up the *content directory* where the SFT files are loaded and stored.</span></span> <span data-ttu-id="75ef2-106">SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="75ef2-106">The SFT files contain the virtual application (or applications).</span></span>

<span data-ttu-id="75ef2-107">**重要** Application Virtualization サーバーは、RTSP または RTSPS プロトコルのみを使って、SFT ファイルをデスクトップクライアントとリモートデスクトップサービスのクライアントにストリーミングします。</span><span class="sxs-lookup"><span data-stu-id="75ef2-107">**Important** Application Virtualization Servers stream SFT files to the Desktop Client and the Client for Remote Desktop Services using only RTSP or RTSPS protocols.</span></span> <span data-ttu-id="75ef2-108">ICO (icon) ファイルと OSD (open software descriptor) ファイルを、別のファイルまたは HTTP サーバーからストリーミングするように構成することができます。</span><span class="sxs-lookup"><span data-stu-id="75ef2-108">The ICO (icon) file and the OSD (open software descriptor) file can be configured to stream from a different file or HTTP server.</span></span>

 

**<span data-ttu-id="75ef2-109">Application Virtualization ストリーミングサーバーを構成するには</span><span class="sxs-lookup"><span data-stu-id="75ef2-109">To configure the Application Virtualization Streaming Servers</span></span>**

1.  <span data-ttu-id="75ef2-110">Application Virtualization ストリーミングサーバーのインストール手順を完了します。</span><span class="sxs-lookup"><span data-stu-id="75ef2-110">Complete the installation procedure for the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="75ef2-111">インストール手順では、[**コンテンツパス**] 画面で \\ コンテンツディレクトリの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="75ef2-111">During the installation procedure, you specify the location of the \\Content directory on the **Content Path** screen.</span></span>

2.  <span data-ttu-id="75ef2-112">\\ コンテンツディレクトリで指定した場所に移動し、必要に応じてディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="75ef2-112">Navigate to the location that you specified for the \\Content directory, and if you have to, create the directory.</span></span>

3.  <span data-ttu-id="75ef2-113">コンテンツディレクトリが作成されたら、このディレクトリを標準ファイル共有として構成します。</span><span class="sxs-lookup"><span data-stu-id="75ef2-113">When the Content directory is created, configure this directory as a standard file share.</span></span>

4.  <span data-ttu-id="75ef2-114">コンテンツディレクトリと、コンテンツディレクトリの下にあるパッケージフォルダーへの NTFS ファイルシステムの権限を構成します。</span><span class="sxs-lookup"><span data-stu-id="75ef2-114">Configure the NTFS file system permissions to the Content directory and the package folders under the Content directory.</span></span> <span data-ttu-id="75ef2-115">各アプリケーションにどのユーザーがアクセスできるかを定義する Active Directory ドメインサービスのセキュリティグループを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="75ef2-115">You should use Security Groups in Active Directory Domain Services that define which users can access each application.</span></span>

## <span data-ttu-id="75ef2-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="75ef2-116">Related topics</span></span>


[<span data-ttu-id="75ef2-117">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="75ef2-117">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="75ef2-118">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="75ef2-118">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="75ef2-119">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="75ef2-119">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="75ef2-120">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="75ef2-120">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

[<span data-ttu-id="75ef2-121">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="75ef2-121">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)

 

 





