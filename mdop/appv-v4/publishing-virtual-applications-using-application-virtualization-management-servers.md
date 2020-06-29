---
title: Application Virtualization Management Server を使用した仮想アプリケーションの公開
description: Application Virtualization Management Server を使用した仮想アプリケーションの公開
author: dansimp
ms.assetid: f3d79284-3f82-4ca3-b741-1a80b61490da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01b85d73ed0a6a8bf723be381e947fbbc003bf6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815767"
---
# <span data-ttu-id="18de8-103">Application Virtualization Management Server を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="18de8-103">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>


<span data-ttu-id="18de8-104">Application Virtualization Server ベースの展開では、配置済みの仮想アプリケーションパッケージの順序付け、テスト、展開が行われ、アプリケーションの仮想化管理サーバーで使用されるメインコンテンツ共有にコピーされます。</span><span class="sxs-lookup"><span data-stu-id="18de8-104">In an Application Virtualization Server-based deployment, virtual application packages that have been sequenced, tested, and found deployable are copied to the main CONTENT share to be used by the Application Virtualization Management Server.</span></span> <span data-ttu-id="18de8-105">アプリケーションの仮想化管理サーバーにパッケージをインポートした後は、それらをエンドユーザーに公開することができます。</span><span class="sxs-lookup"><span data-stu-id="18de8-105">After the packages are imported on the Application Virtualization Management Server, they can be published to the end users.</span></span>

<span data-ttu-id="18de8-106">**注** コンテンツ共有は、サーバーの接続されているディスクストレージに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="18de8-106">**Note** The CONTENT share should be located on the server’s attached disk storage.</span></span> <span data-ttu-id="18de8-107">ネットワークへの影響があるため、SAN や DFS 共有などのネットワークストレージデバイスを使用することは慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="18de8-107">Using a network storage device such as a SAN or a DFS share should be considered carefully because of the network impact.</span></span>

 

<span data-ttu-id="18de8-108">アプリケーションは Active Directory グループにプロビジョニングされます。</span><span class="sxs-lookup"><span data-stu-id="18de8-108">Applications are provisioned to Active Directory groups.</span></span> <span data-ttu-id="18de8-109">通常、Application Virtualization 管理者は、公開する各仮想アプリケーションの Active Directory グループを作成し、そのグループに適切なユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="18de8-109">Typically, the Application Virtualization administrator will create Active Directory groups for each virtual application to be published and then add the appropriate users to those groups.</span></span> <span data-ttu-id="18de8-110">ユーザーがワークステーションにログオンすると、アプリケーションの仮想化クライアントは既定で、ログオンしているユーザーの資格情報を使用して発行の更新を実行します。</span><span class="sxs-lookup"><span data-stu-id="18de8-110">When the users log on to their workstations, the Application Virtualization Client, by default, performs a publishing refresh using the credentials of the logged on user.</span></span> <span data-ttu-id="18de8-111">ユーザーは、ショートカットが配置されている場所からアプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="18de8-111">The user can then start applications from wherever the shortcuts have been placed.</span></span> <span data-ttu-id="18de8-112">アプリケーションの仮想化管理者は、アプリケーションのシーケンス中にクライアントシステム上のショートカットの場所と数を決定します。</span><span class="sxs-lookup"><span data-stu-id="18de8-112">The Application Virtualization administrator determines where and how many shortcuts are located on the client system during the sequencing of the application.</span></span>

<span data-ttu-id="18de8-113">**注** *公開更新*は、アプリケーションの仮想化クライアントで定義されている Application virtualization Server への呼び出しで、エンドユーザーが使用するためにどの仮想アプリケーションのショートカットがクライアントに送信されるかを決定します。</span><span class="sxs-lookup"><span data-stu-id="18de8-113">**Note** A *publishing refresh* is a call to the Application Virtualization Server that is defined on the Application Virtualization Client, to determine which virtual application shortcuts are sent to the client for use by the end user.</span></span>

 

## <span data-ttu-id="18de8-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="18de8-114">Related topics</span></span>


[<span data-ttu-id="18de8-115">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="18de8-115">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="18de8-116">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="18de8-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="18de8-117">Application Virtualization システム コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="18de8-117">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="18de8-118">Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="18de8-118">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





