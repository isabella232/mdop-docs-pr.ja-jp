---
title: IIS のサーバーを構成する方法
description: IIS のサーバーを構成する方法
author: dansimp
ms.assetid: 1fcfc583-322f-4a38-90d0-e64bfa9ee3d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9fe3367698b6f387d4467afdad1b3e17211134d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817744"
---
# <span data-ttu-id="c93a2-103">IIS のサーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c93a2-103">How to Configure the Server for IIS</span></span>


<span data-ttu-id="c93a2-104">仮想アプリケーションをアプリケーションの仮想化デスクトップクライアントとリモートデスクトップサービス (以前のターミナルサービス) のクライアントにストリーミングするには、IIS サーバーが構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="c93a2-104">Before virtual applications can be streamed to the Application Virtualization Desktop Client and the Client for Remote Desktop Services (formerly Terminal Services), the IIS servers must be configured.</span></span> <span data-ttu-id="c93a2-105">サーバーを構成するときは、SFT ファイルが読み込まれて保存されるコンテンツディレクトリを設定することになります。</span><span class="sxs-lookup"><span data-stu-id="c93a2-105">When you configure the servers, you are setting up the content directory where the SFT files are loaded and stored.</span></span> <span data-ttu-id="c93a2-106">SFT ファイルには、仮想アプリケーション (またはアプリケーション) が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c93a2-106">The SFT files contain the virtual application (or applications).</span></span>

**<span data-ttu-id="c93a2-107">IIS サーバーでコンテンツディレクトリを構成するには</span><span class="sxs-lookup"><span data-stu-id="c93a2-107">To configure the content directory on the IIS server</span></span>**

1.  <span data-ttu-id="c93a2-108">IIS を実行しているサーバーで、コンテンツディレクトリとして使用するディレクトリを見つけるか、ディレクトリが存在しない場合は作成します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-108">On the server that is running IIS, locate the directory that you want to use as the content directory, or create the directory if it does not exist.</span></span> <span data-ttu-id="c93a2-109">このディレクトリを標準のファイル共有として構成します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-109">Configure this directory as a standard file share.</span></span>

2.  <span data-ttu-id="c93a2-110">IIS を実行しているサーバーで、 **Iis Manager**を開き、[既定の web サイト] で、サーバー上で作成したコンテンツディレクトリに対応する仮想ディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-110">On the server that is running IIS, open **IIS Manager**, and under the default website, create a virtual directory that corresponds to the content directory that you created on the server.</span></span> <span data-ttu-id="c93a2-111">**「既読**」がオンになっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-111">Make sure that **Read** is checked.</span></span>

3.  <span data-ttu-id="c93a2-112">新しく作成された仮想ディレクトリにエイリアスの**内容**を指定します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-112">Give the newly created virtual directory the alias **Content**.</span></span>

4.  <span data-ttu-id="c93a2-113">この仮想ディレクトリのその他のすべての既定の設定をそのまま使用します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-113">Accept all other default settings for this virtual directory.</span></span>

5.  <span data-ttu-id="c93a2-114">以前に定義した Active Directory ドメインサービスのセキュリティグループを使用して、コンテンツディレクトリとコンテンツディレクトリの下に、NTFS ファイルシステムの権限を構成します。</span><span class="sxs-lookup"><span data-stu-id="c93a2-114">Configure the NTFS file system permissions to the content directory and the package folders under the content directory by using the Security Groups in Active Directory Domain Services that you defined earlier.</span></span>

<span data-ttu-id="c93a2-115">**注** IIS を使って ICO ファイルと OSD ファイルを公開する場合は、OSD = TXT の MIME タイプを構成する必要があります。そうしないと、IIS は、ICO ファイルと OSD ファイルをクライアントに提供しません。</span><span class="sxs-lookup"><span data-stu-id="c93a2-115">**Note** If you are using IIS to publish the ICO and OSD files, you must configure a MIME type for OSD=TXT; otherwise, IIS will not serve the ICO and OSD files to clients.</span></span> <span data-ttu-id="c93a2-116">IIS を使ってパッケージ (SFT files) を公開している場合は、SFT = Binary の MIME タイプを構成する必要があります。そうしないと、IIS は SFT ファイルをクライアントに提供しません。</span><span class="sxs-lookup"><span data-stu-id="c93a2-116">If you are using IIS to publish packages (SFT files), you must configure a MIME type for SFT=Binary; otherwise, IIS will not serve the SFT files to clients.</span></span>

 

## <span data-ttu-id="c93a2-117">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c93a2-117">Related topics</span></span>


[<span data-ttu-id="c93a2-118">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c93a2-118">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="c93a2-119">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="c93a2-119">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="c93a2-120">Application Virtualization Management Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c93a2-120">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)

[<span data-ttu-id="c93a2-121">Application Virtualization Streaming Server を構成する方法</span><span class="sxs-lookup"><span data-stu-id="c93a2-121">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)

[<span data-ttu-id="c93a2-122">ファイル サーバーを構成する方法</span><span class="sxs-lookup"><span data-stu-id="c93a2-122">How to Configure the File Server</span></span>](how-to-configure-the-file-server.md)

 

 





