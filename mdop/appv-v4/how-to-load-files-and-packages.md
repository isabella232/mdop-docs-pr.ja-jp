---
title: ファイルとパッケージを読み込む方法
description: ファイルとパッケージを読み込む方法
author: dansimp
ms.assetid: f86f5bf1-99a4-44d7-ae2f-e6049c482f68
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9427fd8089ec9c22d7d379b15ae94bf421ca2d44
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817237"
---
# <span data-ttu-id="1189c-103">ファイルとパッケージを読み込む方法</span><span class="sxs-lookup"><span data-stu-id="1189c-103">How to Load Files and Packages</span></span>


<span data-ttu-id="1189c-104">次の手順を使用して、Application Virtualization サーバーにファイルやパッケージを読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1189c-104">You can use the following procedure to load files and packages on Application Virtualization Servers.</span></span>

<span data-ttu-id="1189c-105">**注** インストールプロセス中に、**コンテンツパス**ページ上の \\ コンテンツディレクトリの場所を指定しました。</span><span class="sxs-lookup"><span data-stu-id="1189c-105">**Note** During the installation process, you specified the location of the \\Content directory on the **Content Path** page.</span></span> <span data-ttu-id="1189c-106">このディレクトリは、その場所をポイントする前に、標準のファイル共有として作成して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="1189c-106">This directory should be created and configured as a standard file share before you point to its location.</span></span>

 

**<span data-ttu-id="1189c-107">ファイルとパッケージを読み込むには</span><span class="sxs-lookup"><span data-stu-id="1189c-107">To load files and packages</span></span>**

1.  <span data-ttu-id="1189c-108">アプリケーションをストリーミングするコンピューターで、\\ コンテンツディレクトリに指定した場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="1189c-108">On the computer from which you will stream applications, navigate to the location that you specified for the \\Content directory.</span></span> <span data-ttu-id="1189c-109">必要に応じて、ディレクトリを作成し、標準のファイル共有として構成します。</span><span class="sxs-lookup"><span data-stu-id="1189c-109">If necessary, create the directory and configure it as a standard file share.</span></span>

2.  <span data-ttu-id="1189c-110">仮想アプリケーションとパッケージの SFT ファイルを、\\ コンテンツディレクトリに移動します。</span><span class="sxs-lookup"><span data-stu-id="1189c-110">Move the SFT files for the virtual applications and packages to the \\Content directory.</span></span> <span data-ttu-id="1189c-111">お使いの SFT ファイルを整理して、混乱を避けるために、アプリケーションとパッケージを専用のサブフォルダーに配置します。</span><span class="sxs-lookup"><span data-stu-id="1189c-111">To keep the SFT files organized and to avoid confusion, put applications and packages in dedicated subfolders.</span></span>

3.  <span data-ttu-id="1189c-112">次の条件を考慮して、シナリオと構成の要件に従って、アプリケーションとパッケージを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1189c-112">Load the applications and packages according to the requirements of your scenario and configuration, considering the following conditions:</span></span>

    -   <span data-ttu-id="1189c-113">アプリケーションやパッケージが Application Virtualization (App-v) Management サーバーに保存されている場合は、管理コンソールから読み込みます。</span><span class="sxs-lookup"><span data-stu-id="1189c-113">If your applications and packages are stored on an Application Virtualization (App-V) Management Server, load them through the Management Console.</span></span> <span data-ttu-id="1189c-114">詳細については、「[アプリケーションを読み込みまたはアンロードする方法](how-to-load-or-unload-an-application.md)」または「[デスクトップ通知領域から仮想アプリケーションを読み込む](how-to-load-virtual-applications-from-the-desktop-notification-area.md)方法」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1189c-114">For more information, see [How to Load or Unload an Application](how-to-load-or-unload-an-application.md) or [How to Load Virtual Applications from the Desktop Notification Area](how-to-load-virtual-applications-from-the-desktop-notification-area.md).</span></span>

    -   <span data-ttu-id="1189c-115">アプリケーションが、app-v Streaming Server、Web サーバー、またはファイルサーバーとして構成されたコンピューターに保存されている場合は、アプリケーションを自動的に読み込むことができます。</span><span class="sxs-lookup"><span data-stu-id="1189c-115">If your applications are stored on an App-V Streaming Server, a Web server, or a computer configured as a file server, the applications can be automatically loaded.</span></span>

        <span data-ttu-id="1189c-116">**注** App-v ストリーミングサーバーは、アプリケーションやパッケージ用の \\ コンテンツディレクトリを自動的にポーリングし、この情報を RAM に入れてアプリケーション要求を処理します。</span><span class="sxs-lookup"><span data-stu-id="1189c-116">**Note** The App-V Streaming Server automatically polls the \\Content directory for applications and packages and puts this information in RAM to service application requests.</span></span>

        <span data-ttu-id="1189c-117">アプリケーションとパッケージを Web サーバーとファイルサーバーから取得するように、App-v クライアントが適切に構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1189c-117">The App-V Clients must be properly configured to retrieve applications and packages from Web servers and file servers.</span></span> <span data-ttu-id="1189c-118">詳細については、「[アプリケーションパッケージの取得用にクライアントを構成する方法](how-to-configure-the-client-for-application-package-retrieval.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1189c-118">For more information, see [How to Configure the Client for Application Package Retrieval](how-to-configure-the-client-for-application-package-retrieval.md).</span></span>

         

## <span data-ttu-id="1189c-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1189c-119">Related topics</span></span>


[<span data-ttu-id="1189c-120">Application Virtualization サーバー</span><span class="sxs-lookup"><span data-stu-id="1189c-120">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





