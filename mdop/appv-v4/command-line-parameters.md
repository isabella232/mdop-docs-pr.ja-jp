---
title: コマンド ライン パラメーター
description: コマンド ライン パラメーター
author: dansimp
ms.assetid: d90a0591-f1ce-4cb8-b244-85cc70461922
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 31d6ca1215648e2519e9818817ab5cc779a746d0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819404"
---
# <span data-ttu-id="0c3ff-103">コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c3ff-103">Command-Line Parameters</span></span>


<span data-ttu-id="0c3ff-104">次の Application Virtualization Sequencer パラメーターを使用して、アプリケーションのシーケンスを実行し、コマンドプロンプトでシーケンス処理されたアプリケーションパッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-104">Use the following Application Virtualization Sequencer parameters to sequence an application and to upgrade a sequenced application package at the command prompt.</span></span> <span data-ttu-id="0c3ff-105">Microsoft Application Virtualization Sequencer ディレクトリで、「 **Sftsequencer**」と入力し、その後に適切なパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-105">In the Microsoft Application Virtualization Sequencer directory, you would enter **SFTSequencer**, followed by the appropriate parameter.</span></span>

<a href="" id="-help-or---"></a><span data-ttu-id="0c3ff-106">*/Help*または */?*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-106">*/HELP* or */?*</span></span>  
<span data-ttu-id="0c3ff-107">コマンドラインの順序付けに使用できるパラメーターの一覧を表示するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-107">Use to display the list of parameters available for command-line sequencing.</span></span>

<a href="" id="-installpackage-or--i"></a><span data-ttu-id="0c3ff-108">*/INSTALLPACKAGE*または */i*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-108">*/INSTALLPACKAGE* or */I*</span></span>  
<span data-ttu-id="0c3ff-109">アプリケーションを順序付けするインストーラーまたはバッチファイルを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-109">Use to specify the installer or a batch file for the application to be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a><span data-ttu-id="0c3ff-110">*/INSTALLPATH*または */p*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-110">*/INSTALLPATH* or */P*</span></span>  
<span data-ttu-id="0c3ff-111">パッケージルートディレクトリを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-111">Use to specify the package root directory.</span></span>

<a href="" id="-outputfile-or--o"></a><span data-ttu-id="0c3ff-112">*/OUTPUTFILE*または */o*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-112">*/OUTPUTFILE* or */O*</span></span>  
<span data-ttu-id="0c3ff-113">生成される SPRJ ファイルのパスとファイル名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-113">Use to specify the path and file name of the SPRJ file that will be generated.</span></span>

<span data-ttu-id="0c3ff-114">**重要** */OUTPUTFILE*パラメーターは、アップグレードを意図していないパッケージを開くときには使用できません。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-114">**Important** The */OUTPUTFILE* parameter is not available when opening a package that you do not intend to upgrade.</span></span>

 

<a href="" id="-fullload-or--f"></a><span data-ttu-id="0c3ff-115">*/Fullload*または */f*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-115">*/FULLLOAD* or */F*</span></span>  
<span data-ttu-id="0c3ff-116">すべてをプライマリ機能ブロックに含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-116">Use to specify whether to put everything in the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a><span data-ttu-id="0c3ff-117">*/PACKAGENAME*または */k*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-117">*/PACKAGENAME* or */K*</span></span>  
<span data-ttu-id="0c3ff-118">シーケンスアプリケーションのパッケージ名を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-118">Use to specify the package name of the sequenced application.</span></span>

<a href="" id="-blocksize"></a>*<span data-ttu-id="0c3ff-119">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="0c3ff-119">/BLOCKSIZE</span></span>*  
<span data-ttu-id="0c3ff-120">パッケージをクライアントコンピューターにストリーミングするために使用される SFT ファイルブロックサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-120">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="0c3ff-121">次のいずれかの値を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-121">You can select one of the following values:</span></span>

-   <span data-ttu-id="0c3ff-122">4 KB</span><span class="sxs-lookup"><span data-stu-id="0c3ff-122">4 KB</span></span>

-   <span data-ttu-id="0c3ff-123">16 KB</span><span class="sxs-lookup"><span data-stu-id="0c3ff-123">16 KB</span></span>

-   <span data-ttu-id="0c3ff-124">32 KB</span><span class="sxs-lookup"><span data-stu-id="0c3ff-124">32 KB</span></span>

-   <span data-ttu-id="0c3ff-125">64 KB</span><span class="sxs-lookup"><span data-stu-id="0c3ff-125">64 KB</span></span>

<span data-ttu-id="0c3ff-126">ブロックサイズを指定するときは、SFT ファイルのサイズを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-126">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="0c3ff-127">ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-127">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="0c3ff-128">ブロックサイズが大きいファイルでは、より多くのネットワーク帯域幅が使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-128">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>*<span data-ttu-id="0c3ff-129">/圧縮</span><span class="sxs-lookup"><span data-stu-id="0c3ff-129">/COMPRESSION</span></span>*  
<span data-ttu-id="0c3ff-130">クライアントにストリーミングされるときに、SFT ファイルを圧縮するためのメソッドを指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-130">Use to specify the method for compressing the SFT file as it is streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a><span data-ttu-id="0c3ff-131">*/MSI*または */m*</span><span class="sxs-lookup"><span data-stu-id="0c3ff-131">*/MSI* or */M*</span></span>  
<span data-ttu-id="0c3ff-132">シーケンスアプリケーションの Microsoft Windows インストーラーパッケージの生成を指定するために使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-132">Use to specify generating a Microsoft Windows Installer package for the sequenced application.</span></span>

<a href="" id="-default"></a>*<span data-ttu-id="0c3ff-133">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="0c3ff-133">/DEFAULT</span></span>*  
<span data-ttu-id="0c3ff-134">仮想アプリケーションパッケージの作成時に使用される既定の SPRJ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-134">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="0c3ff-135">このファイルは、アプリケーションを初めてシーケンスするときに、sprj テンプレートとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-135">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>*<span data-ttu-id="0c3ff-136">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="0c3ff-136">/UPGRADE</span></span>*  
<span data-ttu-id="0c3ff-137">アップグレードされる SPRJ ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-137">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>*<span data-ttu-id="0c3ff-138">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="0c3ff-138">/DECODEPATH</span></span>*  
<span data-ttu-id="0c3ff-139">シーケンス処理対象のアプリケーションパッケージに関連付けられたファイルがインストールされている、シーケンスコンピューター上のディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-139">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="0c3ff-140">ディレクトリを指定するときは、次のいずれかの形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c3ff-140">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="0c3ff-141">/decodepath: Q:</span><span class="sxs-lookup"><span data-stu-id="0c3ff-141">/decodepath:Q:</span></span>

-   <span data-ttu-id="0c3ff-142">/decodepath: Q:.</span><span class="sxs-lookup"><span data-stu-id="0c3ff-142">/decodepath:Q:.</span></span>

-   <span data-ttu-id="0c3ff-143">/decodepath: "Q:."</span><span class="sxs-lookup"><span data-stu-id="0c3ff-143">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="0c3ff-144">/decodepath: "Q:"</span><span class="sxs-lookup"><span data-stu-id="0c3ff-144">/decodepath:”Q:”</span></span>

## <span data-ttu-id="0c3ff-145">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0c3ff-145">Related topics</span></span>


[<span data-ttu-id="0c3ff-146">Sequencer コマンド ラインの使用について</span><span class="sxs-lookup"><span data-stu-id="0c3ff-146">About Using the Sequencer Command Line</span></span>](about-using-the-sequencer-command-line.md)

[<span data-ttu-id="0c3ff-147">コマンド ラインを使用してシーケンス処理されたアプリケーションを開く方法</span><span class="sxs-lookup"><span data-stu-id="0c3ff-147">How to Open a Sequenced Application Using the Command Line</span></span>](how-to-open-a-sequenced-application-using-the-command-line.md)

[<span data-ttu-id="0c3ff-148">パッケージを開くコマンドを使用してパッケージをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="0c3ff-148">How to Upgrade a Package Using the Open Package Command</span></span>](how-to-upgrade-a-package-using-the-open-package-command.md)

 

 





