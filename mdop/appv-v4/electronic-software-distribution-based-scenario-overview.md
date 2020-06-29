---
title: 電子ソフトウェア配布ベースのシナリオ概要
description: 電子ソフトウェア配布ベースのシナリオ概要
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821597"
---
# <span data-ttu-id="62040-103">電子ソフトウェア配布ベースのシナリオ概要</span><span class="sxs-lookup"><span data-stu-id="62040-103">Electronic Software Distribution-Based Scenario Overview</span></span>


<span data-ttu-id="62040-104">仮想アプリケーションを展開するために電子ソフトウェア配布 (ESD) ソリューションを使用する予定がある場合は、その判断によって影響を受ける要因を理解することが重要です。</span><span class="sxs-lookup"><span data-stu-id="62040-104">If you plan to use an electronic software distribution (ESD) solution to deploy virtual applications, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="62040-105">このトピックでは、ESD ベースのシナリオを使用する利点について説明し、展開を進めるときに考慮する必要がある発行およびパッケージのストリーミング方法に関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="62040-105">This topic describes the benefits of using an ESD-based scenario and provides information about the publishing and package streaming methods that you will need to consider as you proceed with your deployment.</span></span>

<span data-ttu-id="62040-106">**重要** どちらの ESD ソリューションを使っていても、特定の解決策の要件について理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="62040-106">**Important** Whichever ESD solution you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="62040-107">Microsoft Endpoint Configuration Manager を使用している場合は、の Configuration Manager のドキュメントを参照してください <https://go.microsoft.com/fwlink/?LinkId=66999> 。</span><span class="sxs-lookup"><span data-stu-id="62040-107">If you are using Microsoft Endpoint Configuration Manager, see the Configuration Manager documentation at <https://go.microsoft.com/fwlink/?LinkId=66999>.</span></span>

 

<span data-ttu-id="62040-108">既存の ESD システムを使用すると、次のようなメリットが得られます。</span><span class="sxs-lookup"><span data-stu-id="62040-108">Using an existing ESD system provides you with the following benefits:</span></span>

-   <span data-ttu-id="62040-109">デュアル管理インフラストラクチャの排除</span><span class="sxs-lookup"><span data-stu-id="62040-109">Eliminates dual management infrastructures</span></span>

-   <span data-ttu-id="62040-110">追加ハードウェアのコストを削減する</span><span class="sxs-lookup"><span data-stu-id="62040-110">Reduces the cost of additional hardware</span></span>

-   <span data-ttu-id="62040-111">追加のオペレーティングシステムとデータベースライセンスのコストを削減する</span><span class="sxs-lookup"><span data-stu-id="62040-111">Reduces the cost of additional operating system and database licenses</span></span>

## <span data-ttu-id="62040-112">発行方法</span><span class="sxs-lookup"><span data-stu-id="62040-112">Publishing Methods</span></span>


<span data-ttu-id="62040-113">ESD ベースのシナリオを使用する場合、アプリケーションをクライアントに公開するための次の選択肢があります。</span><span class="sxs-lookup"><span data-stu-id="62040-113">When using an ESD-based scenario, you have the following choices for publishing the application to the clients:</span></span>

-   **<span data-ttu-id="62040-114">スタンドアロンの Windows インストーラー。</span><span class="sxs-lookup"><span data-stu-id="62040-114">Stand-alone Windows Installer.</span></span>** <span data-ttu-id="62040-115">Windows Installer ファイルには、マニフェストと、クライアントがパッケージを構成するために使用する OSD ファイルと ICO ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62040-115">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="62040-116">このシナリオではサーバーを使用しないため、Windows Installer ファイルでも、SFT ファイルがクライアントにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="62040-116">The Windows Installer file also copies the SFT file to the client because this scenario does not use a server.</span></span>

-   **<span data-ttu-id="62040-117">パッケージマニフェストを含む Windows インストーラー。</span><span class="sxs-lookup"><span data-stu-id="62040-117">Windows Installer with the package manifest.</span></span>** <span data-ttu-id="62040-118">Windows Installer ファイルには、マニフェストと、クライアントがパッケージを構成するために使用する OSD ファイルと ICO ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="62040-118">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="62040-119">SFT ファイルがサーバーに保存されています。</span><span class="sxs-lookup"><span data-stu-id="62040-119">The SFT file is stored on a server.</span></span> <span data-ttu-id="62040-120">コマンドラインパラメーターは、クライアントが SFT ファイルの場所を指定するように指示します。</span><span class="sxs-lookup"><span data-stu-id="62040-120">A command-line parameter directs the client to the location of the SFT file.</span></span>

-   **<span data-ttu-id="62040-121">SFTMIME コマンド。</span><span class="sxs-lookup"><span data-stu-id="62040-121">SFTMIME commands.</span></span>** <span data-ttu-id="62040-122">SFTMIME コマンドは、マニフェスト、OSD、ICO、および SFT の各ファイルと共に使用され、クライアントにパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="62040-122">SFTMIME commands are used with the manifest, OSD, ICO, and SFT files to add packages to the client.</span></span> <span data-ttu-id="62040-123">マニフェストファイルは、クライアントコンピューター上に存在するか、UNC パスを介してアクセスできる必要があります。</span><span class="sxs-lookup"><span data-stu-id="62040-123">The manifest file must be on the client computer, or it must be accessible through a UNC path.</span></span> <span data-ttu-id="62040-124">クライアントの構成とコマンドラインオプションに応じて、OSD、ICO、および SFT の各ファイルは、クライアントコンピューターまたはサーバー上に存在することができます。</span><span class="sxs-lookup"><span data-stu-id="62040-124">Depending on the client configuration and the command-line options, the OSD, ICO, and SFT files can be on the client computer or on a server.</span></span>

<span data-ttu-id="62040-125">上記の発行方法の詳細については、「[発行方法を決定](determine-your-publishing-method.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62040-125">For more detailed information about the preceding publishing methods, see [Determine Your Publishing Method](determine-your-publishing-method.md).</span></span>

## <span data-ttu-id="62040-126">パッケージストリーミングの方法</span><span class="sxs-lookup"><span data-stu-id="62040-126">Package Streaming Methods</span></span>


<span data-ttu-id="62040-127">仮想アプリケーションパッケージ (または SFT ファイル) をサーバーからクライアントにストリーミングするためにアプリケーションの仮想化システムが使用するメソッドを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="62040-127">You will need to determine the method your Application Virtualization System will use to stream the virtual application packages, or SFT files, from the server to the clients.</span></span> <span data-ttu-id="62040-128">次のストリーミングオプションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="62040-128">The following streaming options are available:</span></span>

-   **<span data-ttu-id="62040-129">Application Virtualization ストリーミングサーバー。</span><span class="sxs-lookup"><span data-stu-id="62040-129">Application Virtualization Streaming Server.</span></span>** <span data-ttu-id="62040-130">構成で Application Virtualization Streaming Server を使用している場合、SFT ファイルは、RTSP または RTSPS プロトコルを使ってそのサーバーのクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="62040-130">If you use an Application Virtualization Streaming Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="62040-131">コンピューターにサーバーソフトウェアをインストールする必要があります。これは、レジストリを使って構成する必要がありますが、この構成は、SQL や Active Directory ドメインサービスなどのサービスに依存しません。</span><span class="sxs-lookup"><span data-stu-id="62040-131">You must install the server software on a computer and you must configure it through the registry, but this configuration does not depend on services such as SQL or Active Directory Domain Services.</span></span> <span data-ttu-id="62040-132">SFT ファイルは、クライアントからアクセスできる場所にサーバー上に格納されます。</span><span class="sxs-lookup"><span data-stu-id="62040-132">The SFT files are stored on the server at a location accessible by the clients.</span></span> <span data-ttu-id="62040-133">公開情報は、任意の配布メカニズムを通じてクライアントに配布できます。</span><span class="sxs-lookup"><span data-stu-id="62040-133">Publishing information can be distributed to the clients through any distribution mechanism.</span></span> <span data-ttu-id="62040-134">ただし、構成すると、クライアントはパッケージのアップグレードを自動的に受け取り、アクティブなアップグレードがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="62040-134">However, when configured, the client receives package upgrades automatically and active upgrade is supported.</span></span>

-   **<span data-ttu-id="62040-135">Application Virtualization Management Server。</span><span class="sxs-lookup"><span data-stu-id="62040-135">Application Virtualization Management Server.</span></span>** <span data-ttu-id="62040-136">構成で Application Virtualization Management Server を使用している場合、SFT ファイルは、RTSP または RTSPS プロトコルを使ってそのサーバーのクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="62040-136">If you use an Application Virtualization Management Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="62040-137">このサーバーは、Application Virtualization 管理コンソールを使って管理します。</span><span class="sxs-lookup"><span data-stu-id="62040-137">You manage this server through the Application Virtualization Management Console.</span></span> <span data-ttu-id="62040-138">この構成では、SQL データベースと Active Directory services を使用します。</span><span class="sxs-lookup"><span data-stu-id="62040-138">This configuration uses a SQL database and Active Directory services.</span></span> <span data-ttu-id="62040-139">サーバーは発行情報をクライアントに配布できます。そのため、追加の公開メカニズムは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="62040-139">The server can distribute publishing information to the clients, so additional publishing mechanisms are not needed.</span></span>

-   **<span data-ttu-id="62040-140">ファイルサーバー。</span><span class="sxs-lookup"><span data-stu-id="62040-140">File server.</span></span>** <span data-ttu-id="62040-141">構成でファイルサーバーを使用している場合、SFT ファイルは、SMB プロトコルを使用して他のクライアントコンピューターにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="62040-141">If you use a file server in your configuration, the SFT files are streamed to the other client computers by using SMB protocols.</span></span> <span data-ttu-id="62040-142">この構成で使用されるファイルサーバーは、ファイル共有と SFT ファイルにアクセス制御リスト (Acl) を作成することによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="62040-142">File servers used in this configuration are managed by creating access control lists (ACLs) on the file shares and SFT files.</span></span> <span data-ttu-id="62040-143">クライアントがファイルサーバー上の適切なファイルにアクセスするには、注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62040-143">Care must be taken to direct the clients to the correct files on the file server.</span></span>

-   **<span data-ttu-id="62040-144">IIS サーバー。</span><span class="sxs-lookup"><span data-stu-id="62040-144">IIS server.</span></span>** <span data-ttu-id="62040-145">構成で IIS サーバーを使用している場合、SFT ファイルは、HTTP または HTTPS プロトコルを使用してそのサーバーからクライアントにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="62040-145">If you use an IIS server in your configuration, the SFT files are streamed to the clients from that server using HTTP or HTTPS protocols.</span></span> <span data-ttu-id="62040-146">IIS サーバーの構成と管理は簡単です。</span><span class="sxs-lookup"><span data-stu-id="62040-146">The IIS server is easy to configure and manage.</span></span> <span data-ttu-id="62040-147">クライアントを IIS サーバー上の適切なファイルに接続するには、注意を払う必要があります。</span><span class="sxs-lookup"><span data-stu-id="62040-147">Care must be taken to direct the clients to the correct files on the IIS server.</span></span>

<span data-ttu-id="62040-148">上記のストリーミングメソッドの詳細については、「[ストリーミングメソッドを決定](determine-your-streaming-method.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="62040-148">For more detailed information about the preceding streaming methods, see [Determine Your Streaming Method](determine-your-streaming-method.md).</span></span>

## <span data-ttu-id="62040-149">関連トピック</span><span class="sxs-lookup"><span data-stu-id="62040-149">Related topics</span></span>


[<span data-ttu-id="62040-150">Application Virtualization Client インストーラーのコマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="62040-150">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="62040-151">Application Virtualization サーバー ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="62040-151">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="62040-152">公開方法の選択</span><span class="sxs-lookup"><span data-stu-id="62040-152">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="62040-153">ストリーミング方法の選択</span><span class="sxs-lookup"><span data-stu-id="62040-153">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="62040-154">電子ソフトウェア配布ベースのシナリオ</span><span class="sxs-lookup"><span data-stu-id="62040-154">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="62040-155">SFTMIME コマンドリファレンス</span><span class="sxs-lookup"><span data-stu-id="62040-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





