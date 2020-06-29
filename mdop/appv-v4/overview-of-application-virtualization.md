---
title: Application Virtualization の概要
description: Application Virtualization の概要
author: dansimp
ms.assetid: 80545ef4-cf4c-420c-88d6-48e9f226051f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f3719a817137edfd76b1b972e966c685581c58e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816064"
---
# <span data-ttu-id="bfc7b-103">Application Virtualization の概要</span><span class="sxs-lookup"><span data-stu-id="bfc7b-103">Overview of Application Virtualization</span></span>


<span data-ttu-id="bfc7b-104">Microsoft Application Virtualization (App-v) を使うと、アプリケーションをコンピューターに直接インストールすることなく、エンドユーザーのコンピューターでアプリケーションを使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-104">Microsoft Application Virtualization (App-V) can make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="bfc7b-105">これは、*アプリケーションの順序*付けと呼ばれるプロセスによって可能になります。これにより、各アプリケーションは、クライアントコンピューター上の独立した仮想環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="bfc7b-106">順序付けされたアプリケーションは、互いに分離されます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-106">The sequenced applications are isolated from each other.</span></span> <span data-ttu-id="bfc7b-107">これによりアプリケーションの競合がなくなりますが、アプリケーションはクライアントコンピューターと引き続き操作できます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-107">This eliminates application conflicts, but the applications can still interact with the client computer.</span></span>

<span data-ttu-id="bfc7b-108">App-v クライアントは、エンドユーザーがコンピューターに公開された後にアプリケーションを操作できるようにするための機能です。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-108">The App-V client is the feature that lets the end user interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="bfc7b-109">クライアントは、仮想化されたアプリケーションが各コンピューターで実行される仮想環境を管理します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-109">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="bfc7b-110">クライアントがコンピューターにインストールされた後、アプリケーションは*発行*と呼ばれるプロセスによってコンピューターから利用できるようにする必要があります。これにより、エンドユーザーは仮想アプリケーションを実行できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-110">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="bfc7b-111">公開プロセスでは、仮想アプリケーションのアイコンとショートカットをコンピューターにコピーします (通常は Windows デスクトップまたは [**スタート**] メニュー)。また、パッケージ定義とファイルの種類の関連付け情報もコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-111">The publishing process copies the virtual application icons and shortcuts to the computer—typically on the Windows desktop or on the **Start** menu—and also copies the package definition and file type association information to the computer.</span></span> <span data-ttu-id="bfc7b-112">公開すると、エンドユーザーのコンピューターでもアプリケーションパッケージのコンテンツを利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-112">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="bfc7b-113">仮想アプリケーションパッケージのコンテンツは、1つまたは複数のアプリケーション仮想化サーバーにコピーできます。これにより、オンデマンドでクライアントにストリーミングしてローカルにキャッシュすることができます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-113">The virtual application package content can be copied onto one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="bfc7b-114">ファイルサーバーと Web サーバーをストリーミングサーバーとして使用することも、Microsoft Endpoint Configuration Manager などの電子ソフトウェア配布システムを使用している場合など、エンドユーザーのコンピューターに直接コピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-114">File servers and Web servers can also be used as streaming servers, or the content can be copied directly to the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="bfc7b-115">複数サーバーの実装では、すべてのストリーミングサーバーでパッケージコンテンツを保持し、最新の状態に維持するには、包括的なパッケージ管理ソリューションが必要です。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-115">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="bfc7b-116">組織の規模によっては、世界中のエンドユーザーに対して多数の仮想アプリケーションを利用できるようにすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-116">Depending on the size of your organization, you might need to have many virtual applications available to end users located all over the world.</span></span> <span data-ttu-id="bfc7b-117">このパッケージを管理して、すべてのユーザーが適切なアプリケーションを使用できるようにするため、およびそれらにアクセスする必要がある場合は、重要な要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-117">Managing the packages to ensure that the appropriate applications are available to all users where and when they need access to them is therefore an important requirement.</span></span>

## <span data-ttu-id="bfc7b-118">Microsoft Application Virtualization システムの機能</span><span class="sxs-lookup"><span data-stu-id="bfc7b-118">Microsoft Application Virtualization System Features</span></span>


<span data-ttu-id="bfc7b-119">次の表では、Microsoft Application Virtualization 管理システムの主な機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-119">The following table describes the primary features of the Microsoft Application Virtualization Management System.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfc7b-120">機能</span><span class="sxs-lookup"><span data-stu-id="bfc7b-120">Feature</span></span></th>
<th align="left"><span data-ttu-id="bfc7b-121">機能</span><span class="sxs-lookup"><span data-stu-id="bfc7b-121">Function</span></span></th>
<th align="left"><span data-ttu-id="bfc7b-122">追加情報</span><span class="sxs-lookup"><span data-stu-id="bfc7b-122">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfc7b-123">Microsoft Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="bfc7b-123">Microsoft Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-124">パッケージコンテンツのストリーミングと、アプリケーション仮想化クライアントへのショートカットとファイルの種類の関連付けの公開を担当します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-124">Responsible for streaming the package content and publishing the shortcuts and file type associations to the Application Virtualization client.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-125">Application Virtualization Management Server では、アクティブなアップグレード、ライセンス管理、およびレポートに使用できるデータベースがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-125">The Application Virtualization Management Server supports active upgrade, License Management, and a database that can be used for reporting.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="bfc7b-126">コンテンツ </strong> フォルダー</span><span class="sxs-lookup"><span data-stu-id="bfc7b-126">Content</strong> folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-127">ストリーミング用のアプリケーションの仮想化パッケージの場所を示します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-127">Indicates the location of the Application Virtualization packages for streaming.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-128">このフォルダーは、Application Virtualization Management Server の [共有] に配置できます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-128">This folder can be located on a share on or off the Application Virtualization Management Server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfc7b-129">Microsoft Application Virtualization 管理コンソール</span><span class="sxs-lookup"><span data-stu-id="bfc7b-129">Microsoft Application Virtualization Management Console</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-130">この本体は、Microsoft Application Virtualization Server の管理に使用される MMC 3.0 スナップイン管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-130">This console is an MMC 3.0 snap-in management tool used for Microsoft Application Virtualization Server administration.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-131">このツールは、Microsoft Application Virtualization server にインストールすることも、Microsoft 管理コンソール (MMC) 3.0 と Microsoft を含む別のワークステーションにインストールすることもできます。NETFramework 2.0 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-131">This tool can be installed on the Microsoft Application Virtualization server or located on a separate workstation that has Microsoft Management Console (MMC)3.0 and Microsoft .NETFramework 2.0 installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfc7b-132">Microsoft Application Virtualization Management Web サービス</span><span class="sxs-lookup"><span data-stu-id="bfc7b-132">Microsoft Application Virtualization Management Web Service</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-133">読み取りおよび書き込み要求をアプリケーションの仮想化データストアに伝える責任を負います。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-133">Responsible for communicating any read and write requests to the Application Virtualization data store.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-134">管理 Web サービスは、Microsoft Application Virtualization Management server または Microsoft インターネットインフォメーションサービス (IIS) がインストールされている別のコンピューターにインストールできます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-134">The Management Web Service can be installed on the Microsoft Application Virtualization Management server or on a separate computer that has Microsoft Internet Information Services (IIS) installed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfc7b-135">Microsoft Application Virtualization データストア</span><span class="sxs-lookup"><span data-stu-id="bfc7b-135">Microsoft Application Virtualization Data Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-136">Application Virtualization インフラストラクチャに関連するすべての情報を保存することを担当する App-v SQL Server データベース。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-136">The App-V SQL Server database responsible for storing all information related to the Application Virtualization infrastructure.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-137">この情報には、アプリケーションのすべてのレコード、アプリケーションの割り当て、アプリケーションの仮想化環境の管理に必要なグループが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-137">This information includes all application records, application assignments, and which groups have responsibility for managing the Application Virtualization environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfc7b-138">Microsoft Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="bfc7b-138">Microsoft Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-139">Application virtualization Management Server へのリンクがワイドエリアネットワーク (WAN) 接続と見なされる、ブランチオフィスのクライアントにストリーミングするためのアプリケーション仮想化パッケージをホストする責任を負います。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-139">Responsible for hosting the Application Virtualization packages for streaming to clients in a branch office, where the link back to the Application Virtualization Management Server is considered a wide area networks (WAN) connection.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-140">このサーバーにはストリーミング機能のみが含まれており、Application Virtualization 管理コンソールでも、Application Virtualization 管理 Web サービスも提供されません。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-140">This server contains streaming functionality only and provides neither the Application Virtualization Management Console nor the Application Virtualization Management Web Service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfc7b-141">Microsoft Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="bfc7b-141">Microsoft Application Virtualization Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-142">Sequencer は、仮想アプリケーションパッケージを作成するためにアプリケーションのインストールを監視およびキャプチャするために使われます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-142">The sequencer is used to monitor and capture the installation of applications to create virtual application packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-143">出力は、アプリケーションのアイコン、パッケージ定義情報が格納されている .osd ファイル、パッケージマニフェストファイル、およびアプリケーションプログラムのコンテンツファイルを含む sft ファイルで構成されます。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-143">The output consists of the application’s icons, an .osd file that contains package definition information, a package manifest file, and the .sft file that contains the application program’s content files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfc7b-144">Microsoft Application Virtualization クライアント</span><span class="sxs-lookup"><span data-stu-id="bfc7b-144">Microsoft Application Virtualization Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-145">Application Virtualization デスクトップクライアントと、リモートデスクトップサービス用の Application Virtualization クライアントは、仮想化されたアプリケーションの仮想環境を提供し、管理します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-145">The Application Virtualization Desktop Client and the Application Virtualization Client for Remote Desktop Services provide and manage the virtual environment for the virtualized applications.</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfc7b-146">Microsoft Application Virtualization クライアントは、パッケージのストリーミングをキャッシュに管理し、公開の更新、トランスポート、およびすべてのアプリケーションの仮想化サーバーとの操作を管理します。</span><span class="sxs-lookup"><span data-stu-id="bfc7b-146">The Microsoft Application Virtualization client manages the package streaming into cache, publishing refresh, transport, and all interaction with the Application Virtualization servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

 

 





