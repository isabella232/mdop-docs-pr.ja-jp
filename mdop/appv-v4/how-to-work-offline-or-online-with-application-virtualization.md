---
title: Application Virtualization をオフラインまたはオンラインで作業する方法
description: Application Virtualization をオフラインまたはオンラインで作業する方法
author: dansimp
ms.assetid: aa532b37-8a00-4db4-9b51-e1e8354b2495
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0dfdd315fe607156135247c4a34d0248ef8fbdd9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816377"
---
# <span data-ttu-id="883c3-103">Application Virtualization をオフラインまたはオンラインで作業する方法</span><span class="sxs-lookup"><span data-stu-id="883c3-103">How to Work Offline or Online with Application Virtualization</span></span>


<span data-ttu-id="883c3-104">長時間ネットワークから切断する予定の場合は、オフラインモードで作業することで、アプリケーションの仮想化クライアントがサーバーと通信しようとしたときに発生する可能性のある遅延を排除することができます。</span><span class="sxs-lookup"><span data-stu-id="883c3-104">If you plan to be disconnected from the network for an extended period of time, you can work in offline mode to eliminate possible delays when the Application Virtualization client attempts to communicate with the server.</span></span> <span data-ttu-id="883c3-105">オフラインモードでは、Application Virtualization クライアントは発行サーバーとの通信を試みないため、オフラインモードを有効にする前にアプリケーションが完全にキャッシュされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="883c3-105">In offline mode, the Application Virtualization client will not attempt to communicate with the publishing server, so applications must be fully cached before enabling offline mode.</span></span> <span data-ttu-id="883c3-106">アプリケーションは、コンピューターのローカルディスク上にある場合でも、コンテンツ共有から取得されることはありません。</span><span class="sxs-lookup"><span data-stu-id="883c3-106">Applications will not be retrieved from the content share even if they are on the local disk on the computer.</span></span> <span data-ttu-id="883c3-107">次の Application Virtualization クライアントの手順を使用して、オフラインとオンラインの作業を切り替えることができます。</span><span class="sxs-lookup"><span data-stu-id="883c3-107">You can use the following Application Virtualization Client procedure to toggle between working offline and online.</span></span>

<span data-ttu-id="883c3-108">**注** 既定では、リモートデスクトップサービス (旧ターミナルサービス) のクライアントでは [**オフライン作業**] が無効になっています。</span><span class="sxs-lookup"><span data-stu-id="883c3-108">**Note** By default, **Work Offline** is disabled for the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="883c3-109">システム管理者は、リモートデスクトップサービスのクライアントでこの設定を使用できるように、ユーザーの権限を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="883c3-109">Your system administrator must change your user permissions to allow you to use this setting on a Client for Remote Desktop Services.</span></span>

 

**<span data-ttu-id="883c3-110">オフラインで作業するには</span><span class="sxs-lookup"><span data-stu-id="883c3-110">To work offline</span></span>**

-   <span data-ttu-id="883c3-111">通知領域の [Application Virtualization システム] アイコンを右クリックし、ポップアップメニューから [**オフライン作業**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="883c3-111">Right-click the Application Virtualization System icon in the notification area, and select **Work Offline** from the pop-up menu.</span></span>

**<span data-ttu-id="883c3-112">オンラインで作業するには</span><span class="sxs-lookup"><span data-stu-id="883c3-112">To work online</span></span>**

-   <span data-ttu-id="883c3-113">通知領域の [Application Virtualization システム] アイコンを右クリックし、ポップアップメニューから [**オンライン作業**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="883c3-113">Right-click the Application Virtualization System icon in the notification area, and select **Work Online** from the pop-up menu.</span></span>

## <span data-ttu-id="883c3-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="883c3-114">Related topics</span></span>


[<span data-ttu-id="883c3-115">Application Virtualization Client Management の デスクトップ通知領域を使用する方法</span><span class="sxs-lookup"><span data-stu-id="883c3-115">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





