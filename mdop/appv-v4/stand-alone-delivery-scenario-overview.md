---
title: スタンドアロン配信シナリオの概要
description: スタンドアロン配信シナリオの概要
author: dansimp
ms.assetid: b109f309-f3c1-43af-996f-2a9b138dd171
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f29b1c8d1c9ae97f7a21498369647f31f552839
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815307"
---
# <span data-ttu-id="c2b49-103">スタンドアロン配信シナリオの概要</span><span class="sxs-lookup"><span data-stu-id="c2b49-103">Stand-Alone Delivery Scenario Overview</span></span>


<span data-ttu-id="c2b49-104">スタンドアロン配信シナリオは、低帯域幅接続または接続なしのいずれかの環境に適したアプリケーション仮想化ソリューションであり、一元管理されたサーバーからアプリケーションをストリーミングするアプリケーションの仮想化デスクトップクライアントの機能を制限します。</span><span class="sxs-lookup"><span data-stu-id="c2b49-104">The stand-alone delivery scenario is an ideal application virtualization solution for environments where either low bandwidth connectivity or no connectivity limits the ability of the Application Virtualization Desktop Client to stream applications from centralized servers.</span></span> <span data-ttu-id="c2b49-105">このような環境では、ユーザーがリモートで作業することが多くあり、デバイス所有者が Windows Installer ファイルを使用してアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="c2b49-105">In these environments, users often work remotely and device owners install applications by using Windows Installer files.</span></span>

<span data-ttu-id="c2b49-106">Application Virtualization Sequencer を使用して、Windows インストーラファイルを含むシーケンス付きのアプリケーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="c2b49-106">You can use the Application Virtualization Sequencer to create sequenced applications that include Windows Installer files.</span></span> <span data-ttu-id="c2b49-107">これらのパッケージには、仮想化されたアプリケーション、公開情報、クライアントシステムにパッケージをインストールするために必要なインストーラールーチンが含まれています。</span><span class="sxs-lookup"><span data-stu-id="c2b49-107">These packages include the virtualized applications, publication information, and the necessary installer routines for installing the packages on the client systems.</span></span> <span data-ttu-id="c2b49-108">インストーラーは、仮想アプリケーションパッケージを Microsoft Application Virtualization デスクトップクライアントに追加します。</span><span class="sxs-lookup"><span data-stu-id="c2b49-108">The installer adds the virtual application package to the Microsoft Application Virtualization Desktop Client.</span></span> <span data-ttu-id="c2b49-109">文書情報は、WAN を介してアプリケーションをストリーミングするのではなく、ローカルの場所から読み込むように構成されています。</span><span class="sxs-lookup"><span data-stu-id="c2b49-109">The publication information is configured to load applications from a local location rather than stream them across a WAN.</span></span> <span data-ttu-id="c2b49-110">ユーザーは、一時的にネットワークに接続して、Windows インストーラファイルを取得したり、DVD から実行したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="c2b49-110">Users can temporarily connect to a network to retrieve the Windows Installer files or can run them from a DVD.</span></span>

<span data-ttu-id="c2b49-111">単体配信シナリオでは、ユーザーに次のような利点があります。</span><span class="sxs-lookup"><span data-stu-id="c2b49-111">The stand-alone delivery scenario provides users the following benefits:</span></span>

-   <span data-ttu-id="c2b49-112">簡単な展開操作。</span><span class="sxs-lookup"><span data-stu-id="c2b49-112">Simple deployment operation.</span></span>

-   <span data-ttu-id="c2b49-113">ネットワークとサーバーは、実行時には必要ありません。</span><span class="sxs-lookup"><span data-stu-id="c2b49-113">Network and servers not needed at runtime.</span></span>

-   <span data-ttu-id="c2b49-114">アプリケーションはプレキャッシュされていて、すべてのユーザーが使用できます。</span><span class="sxs-lookup"><span data-stu-id="c2b49-114">Applications pre-cached and available to all users.</span></span>

<span data-ttu-id="c2b49-115">単体配信シナリオには、次のような制限があります。</span><span class="sxs-lookup"><span data-stu-id="c2b49-115">The stand-alone delivery scenario has the following limitations:</span></span>

-   <span data-ttu-id="c2b49-116">組み込みの自動レポート機能は利用できません。レポートは、外部レポートツールを使用して生成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2b49-116">Built-in, automated reporting is unavailable; reports must be generated with external reporting tools.</span></span>

-   <span data-ttu-id="c2b49-117">アプリケーションは、元の Windows インストーラーファイルと同じように、手動でクライアントに配信する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c2b49-117">Applications must be delivered to the client manually like the original Windows Installer files.</span></span>

## <span data-ttu-id="c2b49-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c2b49-118">Related topics</span></span>


[<span data-ttu-id="c2b49-119">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="c2b49-119">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="c2b49-120">クライアントで仮想アプリケーションを公開する方法</span><span class="sxs-lookup"><span data-stu-id="c2b49-120">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

 

 





