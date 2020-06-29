---
title: Application Virtualization Sequencer について
description: Application Virtualization Sequencer について
author: dansimp
ms.assetid: bee193ca-58bd-40c9-b41a-310435633895
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 83709bcceabe3312fba34512b47d28a24b4dc52c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819997"
---
# <span data-ttu-id="a67b3-103">Application Virtualization Sequencer について</span><span class="sxs-lookup"><span data-stu-id="a67b3-103">About the Application Virtualization Sequencer</span></span>


<span data-ttu-id="a67b3-104">Microsoft Application Virtualization (App-v) Sequencer は、アプリケーションのすべてのインストールとセットアップのプロセスを監視および記録し、次のファイルを作成します。 **.ico**、 **OSD**、 **SFT**、 **SPRJ**。</span><span class="sxs-lookup"><span data-stu-id="a67b3-104">The Microsoft Application Virtualization (App-V) Sequencer monitors and records all installation and setup processes for an application and creates the following files: **ICO**, **OSD**, **SFT**, and **SPRJ**.</span></span> <span data-ttu-id="a67b3-105">これらのファイルには、アプリケーションに関する必要な情報がすべて含まれているため、アプリケーションはターゲットコンピューター上の仮想環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-105">These files contain all the necessary information about an application so the application can run in a virtual environment on target computers.</span></span> <span data-ttu-id="a67b3-106">Microsoft Application Virtualization (App-v) Sequencer を使用して、仮想アプリケーションを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-106">You can use the Microsoft Application Virtualization (App-V) Sequencer to create virtual applications.</span></span> <span data-ttu-id="a67b3-107">アプリケーションをシーケンスした後、ターゲットコンピューターにストリーミングするか、仮想アプリケーションパッケージのコンテンツをダウンロードしてローカルでアプリケーションを実行することによって、ターゲットコンピューターで仮想アプリケーションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-107">After you sequence an application, it can be streamed to target computers, or target computers can run the virtual application by downloading the contents of the virtual application package and running the application locally.</span></span>

<span data-ttu-id="a67b3-108">**重要** 仮想アプリケーションパッケージを実行するには、対象のコンピューターで適切なバージョンの App-v クライアントが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b3-108">**Important** To run a virtual application package the target computer must be running the appropriate version of the App-V client.</span></span>

 

<span data-ttu-id="a67b3-109">各アプリケーションは仮想環境で実行され、ターゲットコンピューターでインストールまたは実行されている他のアプリケーションから分離されているため、ターゲットコンピューターでは、仮想アプリケーションパッケージはターゲットコンピューター上で動作しません。</span><span class="sxs-lookup"><span data-stu-id="a67b3-109">Virtual application packages run on target computers without interacting with the underlying operating system on the target computer because each application runs in a virtual environment and is isolated from other applications that are installed or running on the target computer.</span></span> <span data-ttu-id="a67b3-110">この分離によってアプリケーションの競合が軽減され、アプリケーションの展開前に必要なテストの量を減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-110">This isolation can reduce application conflicts and can help decrease the required amount of application pre-deployment testing.</span></span>

## <span data-ttu-id="a67b3-111">Sequencer 用語</span><span class="sxs-lookup"><span data-stu-id="a67b3-111">Sequencer Terminology</span></span>


<a href="" id="application-virtualization-drive"></a><span data-ttu-id="a67b3-112">Application Virtualization ドライブ</span><span class="sxs-lookup"><span data-stu-id="a67b3-112">Application Virtualization drive</span></span>  
<span data-ttu-id="a67b3-113">アプリケーションの仮想化ドライブは、シーケンスされたアプリケーションを実行するターゲットコンピューター上の既定のドライブ (q: \) です。</span><span class="sxs-lookup"><span data-stu-id="a67b3-113">The application virtualization drive is the default drive (Q:\) on the target computer from which sequenced applications are run.</span></span>

<a href="" id="ico-file"></a><span data-ttu-id="a67b3-114">ICO ファイル</span><span class="sxs-lookup"><span data-stu-id="a67b3-114">ICO file</span></span>  
<span data-ttu-id="a67b3-115">順序指定されたアプリケーションを起動するために使われる、クライアントデスクトップ上のアイコンファイル。</span><span class="sxs-lookup"><span data-stu-id="a67b3-115">The icon file on the client desktop which is used to launch a sequenced application.</span></span>

<a href="" id="installation-directory"></a><span data-ttu-id="a67b3-116">インストールディレクトリ</span><span class="sxs-lookup"><span data-stu-id="a67b3-116">Installation directory</span></span>  
<span data-ttu-id="a67b3-117">セットアップ時にインストールファイルを配置するために sequencer によって使用されるディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a67b3-117">The directory used by the sequencer to place installation files during setup.</span></span>

<a href="" id="open-software-descriptor--osd--file"></a><span data-ttu-id="a67b3-118">オープンソフトウェア記述子 (OSD) ファイル</span><span class="sxs-lookup"><span data-stu-id="a67b3-118">Open Software Descriptor (OSD) file</span></span>  
<span data-ttu-id="a67b3-119">App-v クライアントに対して、アプリ V ストリーミングサーバーからシーケンスされたアプリケーションを取得する方法と、仮想環境でシーケンス形式のアプリケーションを実行する方法について指示する XML ベースのファイル。</span><span class="sxs-lookup"><span data-stu-id="a67b3-119">An XML-based file that instructs the App-V client how to retrieve the sequenced application from the App-V streaming server and how to run the sequenced application in the virtual environment.</span></span>

<a href="" id="package-root-directory"></a><span data-ttu-id="a67b3-120">パッケージルートディレクトリ</span><span class="sxs-lookup"><span data-stu-id="a67b3-120">Package root directory</span></span>  
<span data-ttu-id="a67b3-121">シーケンス処理を行うアプリケーションパッケージのファイルがインストールされている、シーケンスコンピューター上のディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="a67b3-121">The directory on the sequencing computer on which files for the sequenced application package are installed.</span></span> <span data-ttu-id="a67b3-122">このディレクトリは、シーケンスされたアプリケーションをストリーミングするコンピューター上でも実質的に存在します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-122">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span>

<a href="" id="sequenced-application"></a><span data-ttu-id="a67b3-123">シーケンスアプリケーション</span><span class="sxs-lookup"><span data-stu-id="a67b3-123">Sequenced application</span></span>  
<span data-ttu-id="a67b3-124">Sequencer で監視されているアプリケーション。プライマリ機能ブロックとセカンダリ機能ブロックに分割され、App-v client t を実行するターゲットコンピューターにストリーミングされ、仮想環境が実行されます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-124">An application that has been monitored by the sequencer, broken up into primary and secondary feature blocks, streamed to a target computer running the App-V client t, and runs a virtual environment.</span></span>

<a href="" id="sequenced-application-package"></a><span data-ttu-id="a67b3-125">シーケンスアプリケーションパッケージ</span><span class="sxs-lookup"><span data-stu-id="a67b3-125">Sequenced application package</span></span>  
<span data-ttu-id="a67b3-126">仮想アプリケーションを構成するファイルで、仮想アプリケーションの実行を許可します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-126">The files that comprise a virtual application and allow a virtual application to run.</span></span> <span data-ttu-id="a67b3-127">これらのファイルは、シーケンスの後に作成され、個別に **.osd**、 **sft**、 **sprj**、 **.ico**のファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-127">These files are created after sequencing and specifically include **.osd**, **.sft**, **.sprj**, and **.ico** files.</span></span>

<a href="" id="sequencing"></a><span data-ttu-id="a67b3-128">付け</span><span class="sxs-lookup"><span data-stu-id="a67b3-128">Sequencing</span></span>  
<span data-ttu-id="a67b3-129">App-v Sequencer を使ってアプリケーションパッケージを作成するプロセス。</span><span class="sxs-lookup"><span data-stu-id="a67b3-129">The process of creating an application package using the App-V Sequencer.</span></span> <span data-ttu-id="a67b3-130">このプロセスでは、アプリケーションが監視され、そのショートカットが構成され、シーケンス処理されたアプリケーションパッケージが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-130">In this process, an application is monitored, its shortcuts are configured, and a sequenced application package is created.</span></span>

<a href="" id="sequencing-computer"></a><span data-ttu-id="a67b3-131">優先順位のコンピューター</span><span class="sxs-lookup"><span data-stu-id="a67b3-131">Sequencing computer</span></span>  
<span data-ttu-id="a67b3-132">アプリケーションのシーケンスに使用されているコンピューター。</span><span class="sxs-lookup"><span data-stu-id="a67b3-132">The computer used to sequence an application.</span></span>

<a href="" id="virtual-application"></a><span data-ttu-id="a67b3-133">仮想アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a67b3-133">Virtual application</span></span>  
<span data-ttu-id="a67b3-134">Sequencer によってパッケージ化されたアプリケーションは、自己完結型の仮想環境で実行できます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-134">An application packaged by the Sequencer to run in a self-contained, virtual environment.</span></span> <span data-ttu-id="a67b3-135">仮想環境には、アプリケーションをローカルにインストールせずにアプリケーションをクライアントで実行するために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="a67b3-135">The virtual environment contains the information necessary to run the application on the client without installing the application locally.</span></span>

<a href="" id="primary-feature-block"></a><span data-ttu-id="a67b3-136">プライマリ機能ブロック</span><span class="sxs-lookup"><span data-stu-id="a67b3-136">Primary feature block</span></span>  
<span data-ttu-id="a67b3-137">ターゲットコンピューターでアプリケーションを実行するために必要な仮想アプリケーションパッケージの最小コンテンツ。</span><span class="sxs-lookup"><span data-stu-id="a67b3-137">The minimum content in a virtual application package that is necessary for an application to run on a target computer.</span></span> <span data-ttu-id="a67b3-138">プライマリ機能ブロック内のコンテンツは、シーケンスのアプリケーションフェーズで識別され、通常、最も使用されているアプリケーション機能のコンテンツで構成されます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-138">The content in the primary feature block is identified during the application phase of sequencing and typically consists of the content for the most used application features.</span></span>

## <a href="" id="sequencing-applications-"></a><span data-ttu-id="a67b3-139">シーケンス処理アプリケーション</span><span class="sxs-lookup"><span data-stu-id="a67b3-139">Sequencing Applications</span></span>


<span data-ttu-id="a67b3-140">環境で仮想アプリケーションパッケージを作成および変更するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="a67b3-140">There are two methods to create and modify virtual application packages in your environment.</span></span> <span data-ttu-id="a67b3-141">最初の方法は、**シーケンス**ウィザードを使用することです。</span><span class="sxs-lookup"><span data-stu-id="a67b3-141">The first method is by using the **Sequencing** wizard.</span></span> <span data-ttu-id="a67b3-142">**シーケンス**ウィザードでは、新規作成、または既存の仮想アプリケーションパッケージの変更を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-142">The **Sequencing** wizard allows you to create new, or modify existing virtual application packages.</span></span> <span data-ttu-id="a67b3-143">**シーケンス**ウィザードの使い方について詳しくは、「[新しいアプリケーションを順序付ける方法](how-to-sequence-a-new-application.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a67b3-143">For more information about using the **Sequencing** wizard see, [How to Sequence a New Application](how-to-sequence-a-new-application.md).</span></span> <span data-ttu-id="a67b3-144">2番目の方法では、コマンドラインを使用します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-144">The second method is by using the command-line.</span></span> <span data-ttu-id="a67b3-145">コマンドラインでは、コマンドプロンプトを使用して、新しい仮想アプリケーションパッケージを作成したり、既存の仮想アプリケーションパッケージを変更したりできます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-145">The command-line allows you to create new, or modify existing virtual application packages using the command prompt.</span></span> <span data-ttu-id="a67b3-146">コマンドラインの使い方について詳しくは、[コマンドラインを使用して仮想アプリケーションを管理する方法](how-to-manage-virtual-applications-using-the-command-line.md)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a67b3-146">For more information about using the command line see, [How to Manage Virtual Applications Using the Command Line](how-to-manage-virtual-applications-using-the-command-line.md).</span></span>

<span data-ttu-id="a67b3-147">**シーケンス**ウィザードでは、仮想アプリケーションパッケージを作成するための次の機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-147">The **Sequencing** wizard provides the following functions for creating virtual application packages:</span></span>

1.  <span data-ttu-id="a67b3-148">**パッケージの構成**:**シーケンス**ウィザードでは、オープンソフトウェア記述子 (OSD) ファイルを作成するために必要なパッケージ構成情報を入力するように求められます。これは、シーケンス処理されたアプリケーションパッケージを開始するために必要なファイルです。</span><span class="sxs-lookup"><span data-stu-id="a67b3-148">**Package Configuration**: The **Sequencing** Wizard prompts for package configuration information necessary to complete the Open Software Descriptor (OSD) file, which is a required file for starting a sequenced application package.</span></span>

2.  <span data-ttu-id="a67b3-149">**アプリケーションのインストール**:**シーケンス**ウィザードは、アプリケーションのインストールとスタートアップの構成に関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-149">**Application Installation**: The **Sequencing** Wizard gathers information about an application’s installation and startup configurations.</span></span> <span data-ttu-id="a67b3-150">アプリケーションに関連付けられたインストールとスタートアップの情報を監視および記録して、仮想アプリケーションパッケージに必要なファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-150">It monitors and records the installation and startup information associated with the application to create the files necessary for a virtual application package.</span></span>

3.  <span data-ttu-id="a67b3-151">**アプリケーションの起動**:**シーケンス**ウィザードでは、ターゲットコンピューターでシーケンス処理されたアプリケーションパッケージの最初の起動を実行するために必要なコードブロックのコンパイルと順序付けを行うための情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="a67b3-151">**Application Startup**: The **Sequencing** Wizard gathers information for compiling and ordering the blocks of code necessary to perform the initial startup of the sequenced application package on the target computer.</span></span> <span data-ttu-id="a67b3-152">コードブロックのコンパイルは、プライマリ機能ブロックと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="a67b3-152">The compilation of the code block is referred to as the primary feature block.</span></span>

## <span data-ttu-id="a67b3-153">Application Virtualization Sequencer のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a67b3-153">Application Virtualization Sequencer Security Considerations</span></span>


<span data-ttu-id="a67b3-154">App-v Sequencer は、ローカルシステムアカウントを使ってシーケンス処理中に検出されたすべてのサービスを実行し、サービス制御要求ではセキュリティ記述子を適用しません。</span><span class="sxs-lookup"><span data-stu-id="a67b3-154">The App-V Sequencer runs all services detected at sequencing time using the Local System account and does not enforce security descriptors on service control requests.</span></span> <span data-ttu-id="a67b3-155">サービスが別のユーザーアカウントを使用してインストールされている場合、またはセキュリティ記述子が別のユーザーグループ固有のサービスのアクセス許可を付与することを意図している場合は、サービスを仮想化する必要があるかどうか慎重に検討してください。</span><span class="sxs-lookup"><span data-stu-id="a67b3-155">If the service was installed using a different user account or if the security descriptors are intended to grant different user groups specific service permissions, consider carefully whether the service should be virtualized.</span></span> <span data-ttu-id="a67b3-156">場合によっては、対象のサービスセキュリティが維持されるように、サービスをローカルにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b3-156">In some cases, you should install the service locally to ensure that the intended service security is preserved.</span></span>

<span data-ttu-id="a67b3-157">**重要** 仮想アプリケーションパッケージは、常に安全な場所に保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a67b3-157">**Important** You should always save virtual application packages in a secure location.</span></span>

 

## <span data-ttu-id="a67b3-158">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a67b3-158">Related topics</span></span>


[<span data-ttu-id="a67b3-159">Application Virtualization Sequencer の概要</span><span class="sxs-lookup"><span data-stu-id="a67b3-159">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





