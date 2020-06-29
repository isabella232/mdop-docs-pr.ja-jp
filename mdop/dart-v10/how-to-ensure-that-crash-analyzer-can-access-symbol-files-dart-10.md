---
title: クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法
description: クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法
author: dansimp
ms.assetid: 39e307bd-5d21-4e44-bed6-bf532f580775
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e0ba2fa777039e1c6ffb91dd997438d8ea50616
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822607"
---
# <span data-ttu-id="b6db6-103">クラッシュ アナライザーがシンボル ファイルにアクセスできるようにする方法</span><span class="sxs-lookup"><span data-stu-id="b6db6-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="b6db6-104">通常、デバッグ情報は、プログラムとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-104">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="b6db6-105">応答を停止したアプリケーションをデバッグするときに、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6db6-105">You must have access to the symbol information when you debug an application that has stopped responding.</span></span>

<span data-ttu-id="b6db6-106">**クラッシュアナライザー**を実行すると、シンボルファイルが自動的にダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-106">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="b6db6-107">コンピューターがインターネットに接続されていない場合、またはネットワークでコンピューターが HTTP プロキシサーバーにアクセスする必要がある場合、シンボルファイルをダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="b6db6-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

**<span data-ttu-id="b6db6-108">クラッシュアナライザーがシンボルファイルにアクセスできることを確認するには</span><span class="sxs-lookup"><span data-stu-id="b6db6-108">To ensure that Crash Analyzer can access symbol files</span></span>**

1.  **<span data-ttu-id="b6db6-109">ダンプファイルを別のコンピューターにコピーします。</span><span class="sxs-lookup"><span data-stu-id="b6db6-109">Copy the dump file to another computer.</span></span>** <span data-ttu-id="b6db6-110">インターネットに接続していないためにシンボルをダウンロードできない場合は、インターネットに接続されているコンピューターにメモリダンプファイルをコピーし、そのコンピューターでスタンドアロンの**Crash Analyzer ウィザード**を実行します。</span><span class="sxs-lookup"><span data-stu-id="b6db6-110">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the memory dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

2.  **<span data-ttu-id="b6db6-111">別のコンピューターからシンボルファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b6db6-111">Access the symbol files from another computer.</span></span>** <span data-ttu-id="b6db6-112">インターネットに接続していないためにシンボルをダウンロードできない場合は、インターネット接続されているコンピューターからシンボルをダウンロードして、インターネットに接続していないコンピューターにファイルをコピーするか、ネットワークドライブをローカルネットワーク上のシンボルが使用可能な場所にマップすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-112">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="b6db6-113">Windows 回復環境 (WindowsRE) で**クラッシュアナライザー**を実行した場合、Microsoft Diagnostics And Recovery ツールセット (DaRT) 10 の回復イメージにシンボルファイルを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-113">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

3.  **<span data-ttu-id="b6db6-114">HTTP プロキシサーバー経由でのシンボルファイルへのアクセス。</span><span class="sxs-lookup"><span data-stu-id="b6db6-114">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="b6db6-115">HTTP プロキシサーバーにアクセスする必要があるため、シンボルをダウンロードできない場合は、次の手順を使用して HTTP プロキシサーバーにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="b6db6-115">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="b6db6-116">DaRT 10 では、[ **Crash Analyzer] ウィザード**では、ラベルプロキシサーバーでマークされた [**シンボルファイルの場所の指定**] ダイアログページで設定を行うことができます **("server: port" の形式を使用します)**。</span><span class="sxs-lookup"><span data-stu-id="b6db6-116">In DaRT 10, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="b6db6-117">このテキストボックスを使用して、プロキシサーバーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-117">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="b6db6-118">[ \*\* &lt; Hostname &gt; : &lt; port &gt; \*\*] の形式でプロキシアドレスを入力します。ここで、 &lt; **hostname** &gt; は DNS 名または IP アドレスで、 &lt; **ポート** &gt; は TCP ポート番号です。</span><span class="sxs-lookup"><span data-stu-id="b6db6-118">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number.</span></span> <span data-ttu-id="b6db6-119">**クラッシュアナライザー**を実行するには、2つのモードがあります。</span><span class="sxs-lookup"><span data-stu-id="b6db6-119">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="b6db6-120">次に、これらの各モードでプロキシ設定を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="b6db6-120">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="b6db6-121">**オンラインモード:** このモードでは、[プロキシサーバー] フィールドが空白になっている場合、ウィザードでは、コントロールパネルの [インターネットオプション] のプロキシ設定が使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-121">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="b6db6-122">提供されているテキストボックスにプロキシアドレスを入力すると、そのアドレスが使用され、[インターネットオプション] の設定が上書きされます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-122">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="b6db6-123">Windows 回復環境 (WindowsRE): [**診断/回復ツールセット**] ウィンドウから**クラッシュアナライザー**を実行すると、既定のプロキシアドレスは表示されません。</span><span class="sxs-lookup"><span data-stu-id="b6db6-123">Windows Recovery Environment (WindowsRE): When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="b6db6-124">コンピューターがインターネットに直接接続されている場合は、プロキシアドレスは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b6db6-124">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="b6db6-125">このため、ウィザードの設定でこのフィールドを空白のままにすることができます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-125">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="b6db6-126">コンピューターがインターネットに直接接続されておらず、プロキシサーバーがあるネットワーク環境内にある場合は、ウィザードのプロキシフィールドを設定して、シンボルストアにアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6db6-126">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="b6db6-127">プロキシアドレスは、ネットワーク管理者から取得できます。</span><span class="sxs-lookup"><span data-stu-id="b6db6-127">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="b6db6-128">プロキシサーバーを設定することが重要なのは、パブリックシンボルストアがインターネットに接続されている場合のみです。</span><span class="sxs-lookup"><span data-stu-id="b6db6-128">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="b6db6-129">シンボルがすでに DaRT リカバリ画像に登録されている場合、またはローカルで利用可能な場合は、プロキシサーバーを設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="b6db6-129">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="b6db6-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b6db6-130">Related topics</span></span>


[<span data-ttu-id="b6db6-131">クラッシュ アナライザーを使用したシステム障害の診断</span><span class="sxs-lookup"><span data-stu-id="b6db6-131">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="b6db6-132">DaRT 10 の操作</span><span class="sxs-lookup"><span data-stu-id="b6db6-132">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 




