---
title: クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法
description: クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法
author: dansimp
ms.assetid: 150a2f88-68a5-40eb-8471-e5008488ab6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db56bb21ad885d1e3aa73bcbd922a7e8bde77080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822804"
---
# <span data-ttu-id="333f5-103">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="333f5-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="333f5-104">通常、デバッグ情報は、実行可能ファイルとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="333f5-104">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="333f5-105">応答を停止したアプリケーションをデバッグするとき (たとえば、クラッシュした場合)、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="333f5-105">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="333f5-106">Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 の Crash Analyzer を実行すると、シンボルファイルが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="333f5-106">Symbol files are automatically downloaded when you run the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer.</span></span> <span data-ttu-id="333f5-107">コンピューターがインターネットに接続されていない場合、またはネットワークでコンピューターが HTTP プロキシサーバーにアクセスする必要がある場合、シンボルファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="333f5-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

## <span data-ttu-id="333f5-108">シンボルファイルへのアクセスを確保する</span><span class="sxs-lookup"><span data-stu-id="333f5-108">Ensure access to symbol files</span></span>


<span data-ttu-id="333f5-109">通常、デバッグ情報は、実行可能ファイルとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="333f5-109">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="333f5-110">応答を停止したアプリケーションをデバッグするとき (たとえば、クラッシュした場合)、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="333f5-110">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="333f5-111">**クラッシュアナライザー**を実行すると、シンボルファイルが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="333f5-111">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="333f5-112">コンピューターがインターネットに接続されていない場合、またはネットワークでコンピューターが HTTP プロキシサーバーにアクセスする必要がある場合、シンボルファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="333f5-112">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

<span data-ttu-id="333f5-113">シンボルファイルへのアクセスを保証するために使用できるオプションの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="333f5-113">The following is a list of options that are available for guaranteeing access to symbol files:</span></span>

-   **<span data-ttu-id="333f5-114">ダンプファイルを別のコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="333f5-114">Copy the dump file to another computer.</span></span>** <span data-ttu-id="333f5-115">インターネットに接続していないためにシンボルをダウンロードできない場合は、インターネットに接続されているコンピューターにクラッシュダンプファイルをコピーし、そのコンピューターでスタンドアロンの**Crash Analyzer ウィザード**を実行します。</span><span class="sxs-lookup"><span data-stu-id="333f5-115">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the crash dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

-   **<span data-ttu-id="333f5-116">別のコンピューターからシンボルファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="333f5-116">Access the symbol files from another computer.</span></span>** <span data-ttu-id="333f5-117">インターネットに接続していないためにシンボルをダウンロードできない場合は、インターネット接続されているコンピューターからシンボルをダウンロードして、インターネットに接続していないコンピューターにファイルをコピーするか、ネットワークドライブをローカルネットワーク上のシンボルが使用可能な場所にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="333f5-117">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="333f5-118">Windows 回復環境 (WindowsRE) で**クラッシュアナライザー**を実行する場合は、DaRT 回復イメージにシンボルファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="333f5-118">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the DaRT recovery image.</span></span> <span data-ttu-id="333f5-119">回復イメージの作成方法の詳細については、「 [DaRT 7.0 の回復イメージを作成](creating-the-dart-70-recovery-image-dart-7.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="333f5-119">For more information about how to create a recovery image, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

-   **<span data-ttu-id="333f5-120">HTTP プロキシサーバー経由でのシンボルファイルへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="333f5-120">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="333f5-121">HTTP プロキシサーバーにアクセスする必要があるため、シンボルをダウンロードできない場合は、次の手順を使用して HTTP プロキシサーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="333f5-121">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="333f5-122">DaRT7 では、 **Crash Analyzer ウィザード**の [**シンボルファイルの場所の指定**] ダイアログページで、ラベルプロキシサーバーでマークされた設定を使用できます **("server: port" の形式を使用します)**。</span><span class="sxs-lookup"><span data-stu-id="333f5-122">In DaRT7, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="333f5-123">このテキストボックスを使用して、プロキシサーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="333f5-123">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="333f5-124">" \*\* &lt; Hostname &gt; : &lt; port &gt; \*\*" という形式のプロキシアドレスを入力します。これは、 &lt; **ホスト**名 &gt; が DNS 名または IP アドレスであり、 &lt; **ポート** &gt; が TCP ポート番号 (通常は 80) です。</span><span class="sxs-lookup"><span data-stu-id="333f5-124">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number, usually 80.</span></span> <span data-ttu-id="333f5-125">**クラッシュアナライザー**を実行するには、2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="333f5-125">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="333f5-126">次に、これらの各モードでプロキシ設定を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="333f5-126">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="333f5-127">**オンラインモード:** このモードでは、[プロキシサーバー] フィールドが空白になっている場合、ウィザードでは、コントロールパネルの [インターネットオプション] のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="333f5-127">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="333f5-128">提供されているテキストボックスにプロキシアドレスを入力すると、そのアドレスが使用され、[インターネットオプション] の設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="333f5-128">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="333f5-129">**Windows 回復環境 (WindowsRE):**[**診断と回復] のツールセット**ウィンドウから**クラッシュアナライザー**を実行すると、既定のプロキシアドレスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="333f5-129">**Windows Recovery Environment (WindowsRE):** When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="333f5-130">コンピューターがインターネットに直接接続されている場合は、プロキシアドレスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="333f5-130">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="333f5-131">このため、ウィザードの設定でこのフィールドを空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="333f5-131">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="333f5-132">コンピューターがインターネットに直接接続されておらず、プロキシサーバーがあるネットワーク環境内にある場合は、ウィザードのプロキシフィールドを設定して、シンボルストアにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="333f5-132">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="333f5-133">プロキシアドレスは、ネットワーク管理者から取得できます。</span><span class="sxs-lookup"><span data-stu-id="333f5-133">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="333f5-134">プロキシサーバーを設定することが重要なのは、パブリックシンボルストアがインターネットに接続されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="333f5-134">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="333f5-135">シンボルがすでに DaRT リカバリ画像に登録されている場合、またはローカルで利用可能な場合は、プロキシサーバーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="333f5-135">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="333f5-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="333f5-136">Related topics</span></span>


[<span data-ttu-id="333f5-137">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="333f5-137">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





