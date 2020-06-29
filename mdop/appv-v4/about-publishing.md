---
title: 公開について
description: 公開について
author: dansimp
ms.assetid: 295074d7-123f-4740-b938-e4a371ee72fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 329f3ecf2d8a906c21944baa01db0c64e653341c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820007"
---
# <span data-ttu-id="1513e-103">公開について</span><span class="sxs-lookup"><span data-stu-id="1513e-103">About Publishing</span></span>


<span data-ttu-id="1513e-104">Application Virtualization Server 管理コンソールからアプリケーションの仮想化クライアントに対して、公開アプリケーションを一元管理できます。</span><span class="sxs-lookup"><span data-stu-id="1513e-104">You can centrally manage publishing applications to the Application Virtualization Client from the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="1513e-105">たとえば、アプリケーションへのアクセスを割り当てることができます。また、リモートデスクトップサービス (以前のターミナルサービス) の Application Virtualization デスクトップクライアントとクライアントがその情報を更新する必要があるタイミングと頻度を定義することができます。</span><span class="sxs-lookup"><span data-stu-id="1513e-105">For example, you can assign access to applications and define when and how often the Application Virtualization Desktop Client and Client for Remote Desktop Services (formerly Terminal Services) need to refresh that information.</span></span> <span data-ttu-id="1513e-106">設定されたスケジュールに基づいて、またはユーザーがクライアントにログインするたびにこの情報を更新するようにクライアントを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="1513e-106">You can set the clients to refresh this information on a set schedule or every time the user logs in to the client.</span></span> <span data-ttu-id="1513e-107">また、コンソールのアプリケーション発行機能を使って、クライアントに公開されている (または利用可能な) アプリケーションをユーザーが確認できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1513e-107">Also, you can use the console's application publishing functionality to enable users to see which applications are published (or available) to the client.</span></span>

<span data-ttu-id="1513e-108">**注** クライアントが公開情報を更新する前に、クライアントは Application Virtualization Management Server について知っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="1513e-108">**Note** Before the client can refresh the publishing information, the client must know about the Application Virtualization Management Server.</span></span> <span data-ttu-id="1513e-109">クライアントをインストールするときに、サーバーに関する必要な情報をクライアントで構成します。</span><span class="sxs-lookup"><span data-stu-id="1513e-109">You configure the client with the necessary information about the server when you install the client.</span></span>

 

<span data-ttu-id="1513e-110">クライアントがアプリケーションの公開情報のためにサーバーに接続すると、サーバーは、ユーザーがアクセス許可を持っているアプリケーションの一覧と、対応するオープンソフトウェア記述子 (OSD) ファイルの場所をクライアントに提供します。</span><span class="sxs-lookup"><span data-stu-id="1513e-110">When a client contacts the server for application publishing information, the server provides the client with the list of applications that the user has permission to access and the location of the corresponding Open Software Descriptor (OSD) files.</span></span> <span data-ttu-id="1513e-111">サーバーは、アイコン、ファイルの種類の関連付け、およびショートカットに関する関連情報も提供します。</span><span class="sxs-lookup"><span data-stu-id="1513e-111">The server also provides the relevant information about icons, file type associations, and shortcuts.</span></span>

## <span data-ttu-id="1513e-112">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1513e-112">Related topics</span></span>


[<span data-ttu-id="1513e-113">アプリケーション ライセンスについて</span><span class="sxs-lookup"><span data-stu-id="1513e-113">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="1513e-114">Application Virtualization アプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="1513e-114">About Application Virtualization Applications</span></span>](about-application-virtualization-applications.md)

 

 





