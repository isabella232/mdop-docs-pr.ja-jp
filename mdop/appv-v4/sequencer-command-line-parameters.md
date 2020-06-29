---
title: Sequencer コマンド ライン パラメーター
description: Sequencer コマンド ライン パラメーター
author: dansimp
ms.assetid: 28fb875a-c302-4d95-b2e0-8dc0c5dbb0f8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ecfa269de04cf3dcba30cbb4a40f9176f03f6571
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815554"
---
# <span data-ttu-id="2c6f3-103">Sequencer コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c6f3-103">Sequencer Command-Line Parameters</span></span>


<span data-ttu-id="2c6f3-104">次の Application Virtualization (App-v) Sequencer パラメーターを使用して、アプリケーションの順序を管理したり、コマンドラインを使用して既存の仮想アプリケーションをアップグレードしたりすることができます。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-104">You can use the following Application Virtualization (App-V) Sequencer parameters to sequence an application and to upgrade an existing virtual application by using a command line.</span></span> <span data-ttu-id="2c6f3-105">コマンドラインを使用してアプリケーションをシーケンス処理する方法について詳しくは、[コマンドラインを使用して新しいアプリケーションを順序付ける方法](how-to-sequence-a-new-application-by-using-the-command-line.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-105">For more information about sequencing an application by using a command line, see [How to Sequence a New Application by Using the Command Line](how-to-sequence-a-new-application-by-using-the-command-line.md).</span></span>

## <span data-ttu-id="2c6f3-106">Sequencer コマンド ライン パラメーター</span><span class="sxs-lookup"><span data-stu-id="2c6f3-106">Sequencer Command-Line Parameters</span></span>


<a href="" id="-help-or---"></a>**<span data-ttu-id="2c6f3-107">/HELP または/?</span><span class="sxs-lookup"><span data-stu-id="2c6f3-107">/HELP or /?</span></span>**  
<span data-ttu-id="2c6f3-108">コマンドラインを使用してアプリケーションをシーケンス処理するときに使用できるパラメーターに関する情報を表示します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-108">Displays information about parameters that are available for using a command line to sequence applications.</span></span>

<a href="" id="-installpackage-or--i"></a>**<span data-ttu-id="2c6f3-109">/INSTALLPACKAGE または/I</span><span class="sxs-lookup"><span data-stu-id="2c6f3-109">/INSTALLPACKAGE or /I</span></span>**  
<span data-ttu-id="2c6f3-110">シーケンス可能なアプリケーションをインストールするために使用される Windows インストーラーまたはバッチファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-110">Specifies the Windows Installer or a batch file that will be used to install an application so that it can be sequenced.</span></span>

<a href="" id="-installpath-or--p"></a>**<span data-ttu-id="2c6f3-111">/INSTALLPATH または/P</span><span class="sxs-lookup"><span data-stu-id="2c6f3-111">/INSTALLPATH or /P</span></span>**  
<span data-ttu-id="2c6f3-112">アプリケーションのパッケージルートディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-112">Specifies the package root directory for an application.</span></span>

<a href="" id="-outputfile-or--o"></a>**<span data-ttu-id="2c6f3-113">/OUTPUTFILE または/O</span><span class="sxs-lookup"><span data-stu-id="2c6f3-113">/OUTPUTFILE or /O</span></span>**  
<span data-ttu-id="2c6f3-114">生成される SPRJ ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-114">Specifies the path and file name of the SPRJ file that will be generated.</span></span>

<a href="" id="-fullload-or--f"></a>**<span data-ttu-id="2c6f3-115">/Fullload または/F</span><span class="sxs-lookup"><span data-stu-id="2c6f3-115">/FULLLOAD or /F</span></span>**  
<span data-ttu-id="2c6f3-116">すべてのファイルをプライマリ機能ブロックに含めるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-116">Specifies whether all files will be contained in the primary feature block.</span></span> <span data-ttu-id="2c6f3-117">コマンドラインで **/fullload**パラメーターを指定した場合、関連付けられているすべてのアプリケーションデータが、プライマリ機能ブロックに追加されます。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-117">If the **/FULLLOAD** parameter is specified on the command line, all of the associated application data is added to primary feature block.</span></span> <span data-ttu-id="2c6f3-118">コマンドラインで **/fullload**パラメーターが指定されていない場合、関連付けられているアプリケーションデータは、プライマリ機能ブロックに追加されません。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-118">If the **/FULLLOAD** parameter is not specified on the command line, then none of the associated application data is added to the primary feature block.</span></span>

<a href="" id="-packagename-or--k"></a>**<span data-ttu-id="2c6f3-119">/PACKAGENAME または/K</span><span class="sxs-lookup"><span data-stu-id="2c6f3-119">/PACKAGENAME or /K</span></span>**  
<span data-ttu-id="2c6f3-120">シーケンス付けされたアプリケーションに割り当てるパッケージ名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-120">Specifies the package name that will be assigned to the sequenced application.</span></span>

<a href="" id="-blocksize"></a>**<span data-ttu-id="2c6f3-121">/BLOCKSIZE</span><span class="sxs-lookup"><span data-stu-id="2c6f3-121">/BLOCKSIZE</span></span>**  
<span data-ttu-id="2c6f3-122">パッケージをクライアントコンピューターにストリーミングするために使用される SFT ファイルブロックサイズを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-122">Specifies the SFT file block size that will be used to stream the package to client computers.</span></span> <span data-ttu-id="2c6f3-123">次のいずれかの値を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-123">You can select one of the following values:</span></span>

-   <span data-ttu-id="2c6f3-124">4 KB</span><span class="sxs-lookup"><span data-stu-id="2c6f3-124">4 KB</span></span>

-   <span data-ttu-id="2c6f3-125">16 KB</span><span class="sxs-lookup"><span data-stu-id="2c6f3-125">16 KB</span></span>

-   <span data-ttu-id="2c6f3-126">32 KB</span><span class="sxs-lookup"><span data-stu-id="2c6f3-126">32 KB</span></span>

-   <span data-ttu-id="2c6f3-127">64 KB</span><span class="sxs-lookup"><span data-stu-id="2c6f3-127">64 KB</span></span>

<span data-ttu-id="2c6f3-128">ブロックサイズを指定するときは、SFT ファイルのサイズを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-128">You should consider the size of the SFT file when you specify the block size.</span></span> <span data-ttu-id="2c6f3-129">ブロックサイズが小さいファイルは、ネットワーク上でのストリーミングには時間がかかりますが、帯域幅の消費が少なくなります。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-129">A file with a smaller block size takes longer to stream over the network but is less bandwidth-intensive.</span></span> <span data-ttu-id="2c6f3-130">ブロックサイズが大きいファイルでは、より多くのネットワーク帯域幅が使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-130">Files with larger block sizes use more network bandwidth.</span></span>

<a href="" id="-compression"></a>**<span data-ttu-id="2c6f3-131">/圧縮</span><span class="sxs-lookup"><span data-stu-id="2c6f3-131">/COMPRESSION</span></span>**  
<span data-ttu-id="2c6f3-132">クライアントにストリーミングされる SFT ファイルを圧縮するためのメソッドを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-132">Specifies the method for compressing the SFT file that will be streamed to the client.</span></span>

<a href="" id="-msi-or--m"></a>**<span data-ttu-id="2c6f3-133">/MSI または/M</span><span class="sxs-lookup"><span data-stu-id="2c6f3-133">/MSI or /M</span></span>**  
<span data-ttu-id="2c6f3-134">シーケンス付きアプリケーションの Windows インストーラーを作成するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-134">Specifies whether a Windows Installer for the sequenced application should be created.</span></span>

<a href="" id="-default"></a>**<span data-ttu-id="2c6f3-135">/DEFAULT</span><span class="sxs-lookup"><span data-stu-id="2c6f3-135">/DEFAULT</span></span>**  
<span data-ttu-id="2c6f3-136">仮想アプリケーションパッケージの作成時に使用される既定の SPRJ ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-136">Specifies the default SPRJ file that will be used when creating a virtual application package.</span></span> <span data-ttu-id="2c6f3-137">このファイルは、アプリケーションを初めてシーケンスするときに、sprj テンプレートとして使用されます。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-137">This file is used as the .sprj template when the application is sequenced for the first time.</span></span>

<a href="" id="-upgrade"></a>**<span data-ttu-id="2c6f3-138">/UPGRADE</span><span class="sxs-lookup"><span data-stu-id="2c6f3-138">/UPGRADE</span></span>**  
<span data-ttu-id="2c6f3-139">アップグレードされる SPRJ ファイルのパスとファイル名を指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-139">Specifies the path and file name of the SPRJ file that will be upgraded.</span></span>

<a href="" id="-decodepath"></a>**<span data-ttu-id="2c6f3-140">/DECODEPATH</span><span class="sxs-lookup"><span data-stu-id="2c6f3-140">/DECODEPATH</span></span>**  
<span data-ttu-id="2c6f3-141">シーケンス処理対象のアプリケーションパッケージに関連付けられたファイルがインストールされている、シーケンスコンピューター上のディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-141">Specifies the directory on the sequencing computer where the files associated with the sequenced application package are installed.</span></span> <span data-ttu-id="2c6f3-142">ディレクトリを指定するときは、次のいずれかの形式を使用します。</span><span class="sxs-lookup"><span data-stu-id="2c6f3-142">Use one of the following formats when specifying the directory:</span></span>

-   <span data-ttu-id="2c6f3-143">/decodepath: Q:</span><span class="sxs-lookup"><span data-stu-id="2c6f3-143">/decodepath:Q:</span></span>

-   <span data-ttu-id="2c6f3-144">/decodepath: Q:.</span><span class="sxs-lookup"><span data-stu-id="2c6f3-144">/decodepath:Q:.</span></span>

-   <span data-ttu-id="2c6f3-145">/decodepath: "Q:."</span><span class="sxs-lookup"><span data-stu-id="2c6f3-145">/decodepath:”Q:.”</span></span>

-   <span data-ttu-id="2c6f3-146">/decodepath: "Q:"</span><span class="sxs-lookup"><span data-stu-id="2c6f3-146">/decodepath:”Q:”</span></span>

## <span data-ttu-id="2c6f3-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c6f3-147">Related topics</span></span>


[<span data-ttu-id="2c6f3-148">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2c6f3-148">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="2c6f3-149">Sequencer コマンド ライン エラー コード</span><span class="sxs-lookup"><span data-stu-id="2c6f3-149">Sequencer Command-Line Error Codes</span></span>](sequencer-command-line-error-codes.md)

 

 





