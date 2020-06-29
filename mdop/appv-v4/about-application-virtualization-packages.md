---
title: Application Virtualization パッケージについて
description: Application Virtualization パッケージについて
author: dansimp
ms.assetid: 69bd35c1-7af3-43db-931b-3074780aa926
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cfe6df90881ea4179fa8cd224609ca6d28ff5f61
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10820084"
---
# <span data-ttu-id="4dd7a-103">Application Virtualization パッケージについて</span><span class="sxs-lookup"><span data-stu-id="4dd7a-103">About Application Virtualization Packages</span></span>


<span data-ttu-id="4dd7a-104">アプリケーションの仮想化では、*パッケージ*はシーケンス処理の出力です。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-104">In Application Virtualization, a *package* is the output of the sequencing process.</span></span> <span data-ttu-id="4dd7a-105">初めてサーバーにアプリケーションを展開するとき、および新しいバージョンでアプリケーションをアップグレードするときは、パッケージを使用します。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-105">You use packages when you first deploy applications on your servers and when you upgrade applications with a new version.</span></span> <span data-ttu-id="4dd7a-106">パッケージを使用すると、アプリケーションの仮想化管理サーバーで仮想アプリケーションのバージョンを制御できます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-106">Packages enable you to control virtual application versions on your Application Virtualization Management Servers.</span></span> <span data-ttu-id="4dd7a-107">1つのパッケージには、1つまたは複数のアプリケーションを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-107">A single package can contain one or more applications.</span></span> <span data-ttu-id="4dd7a-108">各アプリケーションパッケージには、自己完結型の単位として一連のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-108">Each application package contains a set of files as a self-contained unit.</span></span>

## <span data-ttu-id="4dd7a-109">パッケージの管理</span><span class="sxs-lookup"><span data-stu-id="4dd7a-109">Managing Packages</span></span>


<span data-ttu-id="4dd7a-110">Sequencer がプロセスの一部として1つ以上のアプリケーションのパッケージを作成した後は、Sequencer で生成されたファイルをアプリケーションの仮想化管理サーバーにコピーして、ストリーミングで利用できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-110">After the Sequencer creates a package of one or more applications as part of its process, you can copy the Sequencer-generated files to a Application Virtualization Management Server and make them available for streaming.</span></span>

<span data-ttu-id="4dd7a-111">利用可能なパッケージは、Application Virtualization 管理コンソールの左側のウィンドウにある [**パッケージ**] コンテナーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-111">Available packages appear under the **Packages** container in the left pane of the Application Virtualization Management Console.</span></span> <span data-ttu-id="4dd7a-112">Sequencer プロジェクト (SPRJ) ファイルまたはオープンソフトウェア記述子 (OSD) ファイルを使用してアプリケーションをインポートすると、関連エントリが [**パッケージ**] コンテナーに表示されます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-112">When you import an application with a Sequencer Project (SPRJ) file or an Open Software Descriptor (OSD) file, a related entry appears in the **Packages** container.</span></span> <span data-ttu-id="4dd7a-113">Application Virtualization Server 管理コンソールから、パッケージとバージョンを展開、アップグレード、または削除することができます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-113">From the Application Virtualization Server Management Console, you can then deploy, upgrade, or delete packages and versions of them.</span></span>

<span data-ttu-id="4dd7a-114">各仮想アプリケーションには、関連付けられたパッケージがあります。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-114">Each virtual application has an associated package.</span></span> <span data-ttu-id="4dd7a-115">このパッケージには、次のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-115">This package includes the following files:</span></span>

-   <span data-ttu-id="4dd7a-116">SFT —アプリケーションをクライアントにストリーム転送するファイル。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-116">SFT—The file that streams the application to clients.</span></span>

-   <span data-ttu-id="4dd7a-117">OSD — Open Software Descriptor ファイルには、アプリケーションを見つけて起動するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-117">OSD—The Open Software Descriptor file contains the information needed to find and launch the application.</span></span>

-   <span data-ttu-id="4dd7a-118">ICO —ユーザーインターフェイスやショートカットでアプリケーションを視覚的に表すアイコンファイル。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-118">ICO—The icon file that visually represents the application in user interfaces and shortcuts.</span></span>

-   <span data-ttu-id="4dd7a-119">SPRJ — Sequencer プロジェクトファイル。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-119">SPRJ—The Sequencer Project file.</span></span>

<span data-ttu-id="4dd7a-120">SPRJ ファイルをインポートすると、既定では、すべてのシーケンスされたアプリケーションを展開に使用できますが、アプリケーションはストリーミングに対して有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-120">When you import the SPRJ file, all sequenced applications are available for deployment, by default, but the applications are not enabled for streaming.</span></span> <span data-ttu-id="4dd7a-121">パッケージ内のアプリケーションのすべてまたは一部をストリーミングすることを選択できます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-121">You can choose to stream all or some of the applications in the package.</span></span> <span data-ttu-id="4dd7a-122">たとえば、Microsoft Office をシーケンスしてインポートした場合、[設定の保存] ウィザードなどのアプリケーションを展開しないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-122">For example, if you sequenced and imported Microsoft Office, you can choose not to deploy some applications, such as the Save My Settings Wizard.</span></span> <span data-ttu-id="4dd7a-123">この場合、展開する各アプリケーションを右クリックして、[**プロパティ**] を選択し、[**有効**] ボックスがオフになっていることを確認します (空白)。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-123">In this case, right-click each application you want to deploy, choose **Properties**, and make sure that the **Enabled** box is cleared (blank).</span></span> <span data-ttu-id="4dd7a-124">[**有効**] ボックスが選択されているアプリケーションのみが、クライアントコンピューターにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-124">Only the applications with the **Enabled** box selected will stream to client computers.</span></span>

<span data-ttu-id="4dd7a-125">パッケージを再シーケンスし、ストリーミング用の新しい SFT ファイルを生成したら、Application Virtualization Server 管理コンソールを使用して、古いパッケージをすばやく簡単にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-125">After you resequence a package and produce a new SFT file for streaming, you can upgrade the old package quickly and easily through the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="4dd7a-126">**パッケージノードを**使用する必要がある操作シナリオは、パッケージの新しいバージョン (SFT ファイル) を導入する場合に限られます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-126">The only operational scenario that requires you to use the **Packages** node is when you introduce a new version (SFT file) for the package.</span></span> <span data-ttu-id="4dd7a-127">アプリケーションをインポートするたびに、access とライセンスをアプリケーションに割り当てると、Application Virtualization システムはこの情報をパッケージレベルで追跡します。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-127">Whenever you import applications, assign access and licenses to applications, and so on, the Application Virtualization System tracks this information at the package level.</span></span> <span data-ttu-id="4dd7a-128">つまり、アプリケーションを使用するようにユーザーを承認すると、同じパッケージ内のアプリケーションを実行するためのアクセス許可をユーザーに与えることになります。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-128">This means that when you authorize a user to use an application, you are giving the user permission to run any application in the same package.</span></span>

### <span data-ttu-id="4dd7a-129">パッケージバージョン</span><span class="sxs-lookup"><span data-stu-id="4dd7a-129">Package Version</span></span>

<span data-ttu-id="4dd7a-130">パッケージバージョンは、特定の SFT ファイルで表されます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-130">A package version is represented by a specific SFT file.</span></span> <span data-ttu-id="4dd7a-131">パッケージをアップグレードする (アプリケーションの更新を適用する、またはアプリケーションをパッケージに追加する) と、新しい SFT ファイルが生成されます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-131">When you upgrade a package (apply an update to an application or add an application to a package), you generate a new SFT file.</span></span> <span data-ttu-id="4dd7a-132">新しい SFT ファイルを作成するたびに、新しいパッケージバージョンを作成することになります。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-132">Each time you create a new SFT file, you are creating a new package version.</span></span>

<span data-ttu-id="4dd7a-133">Application Virtualization Server 管理コンソールを使用してアプリケーションをインポートすると、パッケージとパッケージバージョンがまだ存在しない場合は、ソフトウェアによって自動的に作成されます。</span><span class="sxs-lookup"><span data-stu-id="4dd7a-133">When you import applications through the Application Virtualization Server Management Console, the software automatically creates a package and a package version if they do not already exist.</span></span>

## <span data-ttu-id="4dd7a-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4dd7a-134">Related topics</span></span>


[<span data-ttu-id="4dd7a-135">Application Virtualization アプリケーションについて</span><span class="sxs-lookup"><span data-stu-id="4dd7a-135">About Application Virtualization Applications</span></span>](about-application-virtualization-applications.md)

[<span data-ttu-id="4dd7a-136">Application Virtualization サーバー管理コンソールについて</span><span class="sxs-lookup"><span data-stu-id="4dd7a-136">About the Application Virtualization Server Management Console</span></span>](about-the-application-virtualization-server-management-console.md)

[<span data-ttu-id="4dd7a-137">サーバー管理コンソールでパッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="4dd7a-137">How to Manage Packages in the Server Management Console</span></span>](how-to-manage-packages-in-the-server-management-console.md)

 

 





