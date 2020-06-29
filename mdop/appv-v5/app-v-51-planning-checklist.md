---
title: APP-V 5.1 の計画チェックリスト
description: APP-V 5.1 の計画チェックリスト
author: dansimp
ms.assetid: 1e26a861-0612-43a6-972f-375a40a8dcbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f113f9c343436695de40ccafb268f8952aea744
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814754"
---
# <span data-ttu-id="57eb9-103">APP-V 5.1 の計画チェックリスト</span><span class="sxs-lookup"><span data-stu-id="57eb9-103">App-V 5.1 Planning Checklist</span></span>

<span data-ttu-id="57eb9-104">このチェックリストを使用して、Microsoft Application Virtualization (App-v) 5.1 展開用のコンピューティング環境の準備を計画することができます。</span><span class="sxs-lookup"><span data-stu-id="57eb9-104">This checklist can be used to help you plan for preparing your computing environment for Microsoft Application Virtualization (App-V) 5.1 deployment.</span></span>

> [!NOTE]
> <span data-ttu-id="57eb9-105">このチェックリストは、推奨される手順と、App-v 5.1 の展開を計画する際に考慮する必要のある項目の概要を示しています。</span><span class="sxs-lookup"><span data-stu-id="57eb9-105">This checklist outlines the recommended steps and a high-level list of items to consider when planning for an App-V 5.1 deployment.</span></span> <span data-ttu-id="57eb9-106">このチェックリストをスプレッドシートプログラムにコピーして、用途に合わせてカスタマイズすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57eb9-106">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

| |<span data-ttu-id="57eb9-107">タスク</span><span class="sxs-lookup"><span data-stu-id="57eb9-107">Task</span></span> |<span data-ttu-id="57eb9-108">参照先</span><span class="sxs-lookup"><span data-stu-id="57eb9-108">References</span></span> |
|-|-|-|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-110">展開計画を開始する前に、製品についての基本的な理解を得るために、App-v 5.1 に関する概要情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="57eb9-110">Review the getting started information about App-V 5.1 to gain a basic understanding of the product before beginning deployment planning.</span></span>|[<span data-ttu-id="57eb9-111">App-V 5.1 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="57eb9-111">Getting Started with App-V 5.1</span></span>](getting-started-with-app-v-51.md)|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-113">アプリ-V 5.1 1.0 展開の前提条件を計画し、コンピューティング環境を準備します。</span><span class="sxs-lookup"><span data-stu-id="57eb9-113">Plan for App-V 5.1 1.0 Deployment Prerequisites and prepare your computing environment.</span></span>|[<span data-ttu-id="57eb9-114">App-V 5.1 の前提条件</span><span class="sxs-lookup"><span data-stu-id="57eb9-114">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-116">App-v 5.1 management server を使用する予定がある場合は、必要な役割を計画します。</span><span class="sxs-lookup"><span data-stu-id="57eb9-116">If you plan to use the App-V 5.1 management server, plan for the required roles.</span></span>|[<span data-ttu-id="57eb9-117">App-V 5.1 Server の展開計画</span><span class="sxs-lookup"><span data-stu-id="57eb9-117">Planning for the App-V 5.1 Server Deployment</span></span>](planning-for-the-app-v-51-server-deployment.md)|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-119">仮想化されたアプリケーションを作成して実行できるように、App-v 5.1 sequencer とクライアントを計画します。</span><span class="sxs-lookup"><span data-stu-id="57eb9-119">Plan for the App-V 5.1 sequencer and client so you to create and run virtualized applications.</span></span>|[<span data-ttu-id="57eb9-120">App-V 5.1 Sequencer および Client の展開計画</span><span class="sxs-lookup"><span data-stu-id="57eb9-120">Planning for the App-V 5.1 Sequencer and Client Deployment</span></span>](planning-for-the-app-v-51-sequencer-and-client-deployment.md)|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-122">該当する場合は、以前のバージョンの App-v から移行するためのオプションと手順を確認します。</span><span class="sxs-lookup"><span data-stu-id="57eb9-122">If applicable, review the options and steps for migrating from a previous version of App-V.</span></span>|[<span data-ttu-id="57eb9-123">APP-V の以前のバージョンからの移行計画</span><span class="sxs-lookup"><span data-stu-id="57eb9-123">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v51.md)|
|![チェックリストボックス](images/checklistbox.gif) |<span data-ttu-id="57eb9-125">共有コンテンツストアモードで使用している App-v 5.1 クライアントの実行を計画します。</span><span class="sxs-lookup"><span data-stu-id="57eb9-125">Plan for running App-V 5.1 clients using in shared content store mode.</span></span>|[<span data-ttu-id="57eb9-126">共有コンテンツ ストア モードの App-V 5.1 Client のインストール方法</span><span class="sxs-lookup"><span data-stu-id="57eb9-126">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)|
|![チェックリストボックス](images/checklistbox.gif) |         |         |

## <span data-ttu-id="57eb9-128">関連トピック</span><span class="sxs-lookup"><span data-stu-id="57eb9-128">Related topics</span></span>

[<span data-ttu-id="57eb9-129">App-V 5.1 の計画</span><span class="sxs-lookup"><span data-stu-id="57eb9-129">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)
