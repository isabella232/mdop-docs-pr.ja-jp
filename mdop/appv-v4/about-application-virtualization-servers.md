---
title: Application Virtualization サーバーについて
description: Application Virtualization サーバーについて
author: dansimp
ms.assetid: 60a45509-2112-44ca-8e28-c73b0c2ff85e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: da26d982c36f25f6fc2d7bc4a7e8684808854992
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820044"
---
# <span data-ttu-id="fa199-103">Application Virtualization サーバーについて</span><span class="sxs-lookup"><span data-stu-id="fa199-103">About Application Virtualization Servers</span></span>


<span data-ttu-id="fa199-104">アプリケーション*発行サーバー*とも呼ばれる Application Virtualization 管理サーバーは、仮想環境で実行するために処理されるアプリケーションへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="fa199-104">Application Virtualization Management Servers, also called *application publishing servers*, control access to the applications that are processed to run in a virtual environment.</span></span> <span data-ttu-id="fa199-105">仮想アプリケーションは、Application Virtualization Management Server に保存されています。</span><span class="sxs-lookup"><span data-stu-id="fa199-105">Virtual applications are stored on the Application Virtualization Management Servers.</span></span> <span data-ttu-id="fa199-106">クライアントによって仮想アプリケーションが呼び出されると、アプリケーションパッケージはアプリケーションの仮想化管理サーバーからクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="fa199-106">When a virtual application is called for by the client, the application package is streamed to the client from the Application Virtualization Management Servers.</span></span>

<span data-ttu-id="fa199-107">**注** アプリケーションの仮想化ストリーミングサーバーからクライアントにアプリケーションをストリーミングすることもできます。</span><span class="sxs-lookup"><span data-stu-id="fa199-107">**Note** You can also stream applications to clients from Application Virtualization Streaming Servers.</span></span> <span data-ttu-id="fa199-108">ストリーミングサーバーでは、公開、管理、レポートなど、管理サーバーから利用できるサービスの一部は提供されません。</span><span class="sxs-lookup"><span data-stu-id="fa199-108">Streaming Servers do not offer some of the services that are available from the Management Servers, such as publishing, management, and reporting.</span></span>

<span data-ttu-id="fa199-109">アプリケーションは、ファイルまたはディスクから直接クライアントにストリーミングできます。</span><span class="sxs-lookup"><span data-stu-id="fa199-109">You can stream applications to the client directly from a file or disk.</span></span> <span data-ttu-id="fa199-110">低または信頼性の低い接続または帯域幅が制限されている場合には、ファイルまたはディスクからのストリーミングに最適なアプリケーション仮想化の展開シナリオもあります。</span><span class="sxs-lookup"><span data-stu-id="fa199-110">Some application virtualization deployment scenarios, which are characterized by low or unreliable connectivity or where bandwidth is limited, are ideally suited for streaming from file or disk.</span></span>

 

<span data-ttu-id="fa199-111">1つのデータストアを共有する1つ以上の Application Virtualization 管理サーバーが、 *Application virtualization システム*を構築します。</span><span class="sxs-lookup"><span data-stu-id="fa199-111">One or more Application Virtualization Management Servers that share a single data store make up an *Application Virtualization system*.</span></span>

## <span data-ttu-id="fa199-112">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fa199-112">Related topics</span></span>


[<span data-ttu-id="fa199-113">Application Virtualization Client Management Console の概要</span><span class="sxs-lookup"><span data-stu-id="fa199-113">Application Virtualization Client Management Console Overview</span></span>](application-virtualization-client-management-console-overview.md)

[<span data-ttu-id="fa199-114">デスクトップ通知領域から仮想アプリケーションを更新する方法</span><span class="sxs-lookup"><span data-stu-id="fa199-114">How to Refresh Virtual Applications from the Desktop Notification Area</span></span>](how-to-refresh-virtual-applications-from-the-desktop-notification-area.md)

[<span data-ttu-id="fa199-115">公開サーバーをセットアップする方法</span><span class="sxs-lookup"><span data-stu-id="fa199-115">How to Set Up Publishing Servers</span></span>](how-to-set-up-publishing-servers.md)

 

 





