---
title: Application Virtualization システム コンポーネントの概要
description: Application Virtualization システム コンポーネントの概要
author: dansimp
ms.assetid: 75d88ef7-44d8-4fa7-b7f5-9153f37e570d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cab0065b9966094da687cce2f5e94069922189fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816054"
---
# <span data-ttu-id="29a27-103">Application Virtualization システム コンポーネントの概要</span><span class="sxs-lookup"><span data-stu-id="29a27-103">Overview of the Application Virtualization System Components</span></span>


<span data-ttu-id="29a27-104">次の表では、Microsoft Application Virtualization 管理システムの主要コンポーネントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="29a27-104">The following table describes the primary components of the Microsoft Application Virtualization Management System.</span></span> <span data-ttu-id="29a27-105">これらのシステムコンポーネントの展開の詳細については、「 [Application Virtualization Server ベースのシナリオ](application-virtualization-server-based-scenario.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="29a27-105">For more information about deploying these system components, see [Application Virtualization Server-Based Scenario](application-virtualization-server-based-scenario.md).</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="29a27-106">コンポーネント</span><span class="sxs-lookup"><span data-stu-id="29a27-106">Component</span></span></th>
<th align="left"><span data-ttu-id="29a27-107">機能</span><span class="sxs-lookup"><span data-stu-id="29a27-107">Function</span></span></th>
<th align="left"><span data-ttu-id="29a27-108">追加情報</span><span class="sxs-lookup"><span data-stu-id="29a27-108">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29a27-109">Microsoft Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="29a27-109">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-110">パッケージコンテンツのストリーミングと、アプリケーションの仮想化クライアントへのショートカットとファイルの種類の関連付けの発行を担当するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="29a27-110">The component responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization Client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-111">Application Virtualization Management Server では、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="29a27-111">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="29a27-112">コンテンツ </strong> フォルダー</span><span class="sxs-lookup"><span data-stu-id="29a27-112">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-113">ストリーミング用のアプリケーション仮想化パッケージの場所。</span><span class="sxs-lookup"><span data-stu-id="29a27-113">The location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-114">このフォルダーは、Application Virtualization Management Server の [共有] に配置できます。</span><span class="sxs-lookup"><span data-stu-id="29a27-114">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span> <span data-ttu-id="29a27-115">このフォルダーは、ストレージエリアネットワーク (SAN) 上に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="29a27-115">The folder can also be located on a Storage Area Network (SAN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29a27-116">Microsoft Application Virtualization 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="29a27-116">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-117">Microsoft Application Virtualization Server 管理用の MMC 3.0 スナップイン管理ユーティリティ。</span><span class="sxs-lookup"><span data-stu-id="29a27-117">An MMC 3.0 snap-in management utility for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-118">このコンポーネントは、Microsoft Application Virtualization サーバーにインストールすることも、MMC 3.0 との別のワークステーションにインストールすることもできます。NET 2.0 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="29a27-118">This component can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29a27-119">Microsoft Application Virtualization Management Web サービス</span><span class="sxs-lookup"><span data-stu-id="29a27-119">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-120">アプリケーションの仮想化データストアへの読み取り/書き込み要求の通信を担当するコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="29a27-120">The component responsible for communicating any read/write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-121">このコンポーネントは、Microsoft Application Virtualization サーバーまたは IIS がインストールされている別のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="29a27-121">This component can installed on the Microsoft Application Virtualization Server or on a separate computer with IIS installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29a27-122">Microsoft Application Virtualization データストア</span><span class="sxs-lookup"><span data-stu-id="29a27-122">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-123">SQL データベースに保存され、Application Virtualization インフラストラクチャに関連するすべての情報を保存する責任を負うコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="29a27-123">The component stored in the SQL database and responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-124">この情報には、アプリケーションのすべてのレコード、アプリケーションの割り当て、アプリケーションの仮想化環境の管理に必要なグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="29a27-124">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29a27-125">Microsoft Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="29a27-125">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-126">Application virtualization Management Server へのリンクが WAN と見なされる、ブランチオフィスのクライアントにストリーミングするためのアプリケーション仮想化パッケージをホストするコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="29a27-126">The component responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a WAN.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-127">このサーバーにはストリーミング機能のみが含まれており、Application Virtualization 管理コンソールでも、Application Virtualization 管理 Web サービスも提供されません。</span><span class="sxs-lookup"><span data-stu-id="29a27-127">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="29a27-128">Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="29a27-128">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-129">アプリケーションのインストールを監視して、仮想アプリケーションパッケージを作成するために使用されるコンポーネント。</span><span class="sxs-lookup"><span data-stu-id="29a27-129">The component used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-130">出力は、アプリケーションのアイコン、パッケージ定義情報を含む OSD ファイル、パッケージマニフェストファイル、およびアプリケーションプログラムのコンテンツファイルを含む SFT ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="29a27-130">Output consists of the application’s icons, an OSD file containing package definition information, a package manifest file, and the SFT file containing the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="29a27-131">Microsoft Application Virtualization クライアント</span><span class="sxs-lookup"><span data-stu-id="29a27-131">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-132">Application Virtualization デスクトップクライアントにインストールされたコンポーネント、またはリモートデスクトップサービス (以前のターミナルサービス) 用の Application Virtualization クライアントで、仮想化されたアプリケーションの仮想環境を提供します。</span><span class="sxs-lookup"><span data-stu-id="29a27-132">The component installed on the Application Virtualization Desktop Client or on the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services) and that provides the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="29a27-133">Microsoft Application Virtualization クライアントは、パッケージのストリーミングをキャッシュに管理し、公開の更新、トランスポート、およびすべてのアプリケーションの仮想化サーバーとの操作を管理します。</span><span class="sxs-lookup"><span data-stu-id="29a27-133">The Microsoft Application Virtualization Client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization Servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="29a27-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="29a27-134">Related topics</span></span>


[<span data-ttu-id="29a27-135">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="29a27-135">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="29a27-136">Application Virtualization サーバー ベースの実装におけるストリーミング ソリューションの計画</span><span class="sxs-lookup"><span data-stu-id="29a27-136">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

[<span data-ttu-id="29a27-137">Application Virtualization Management Server を使用した仮想アプリケーションの公開</span><span class="sxs-lookup"><span data-stu-id="29a27-137">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>](publishing-virtual-applications-using-application-virtualization-management-servers.md)

 

 





