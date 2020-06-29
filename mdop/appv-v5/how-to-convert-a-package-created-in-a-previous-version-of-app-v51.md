---
title: 以前のバージョンの APP-V で作成されたパッケージを変換する方法
description: 以前のバージョンの APP-V で作成されたパッケージを変換する方法
author: dansimp
ms.assetid: 3366d399-2891-491d-8de1-f8cfdf39bbab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 402e64e3bdbc55eea1edb91d070bb7ebb11c912b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814355"
---
# <span data-ttu-id="6d049-103">以前のバージョンの APP-V で作成されたパッケージを変換する方法</span><span class="sxs-lookup"><span data-stu-id="6d049-103">How to Convert a Package Created in a Previous Version of App-V</span></span>


<span data-ttu-id="6d049-104">パッケージコンバーターユーティリティを使用して、以前のバージョンの App-v で作成された仮想アプリケーションパッケージをアップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="6d049-104">You can use the package converter utility to upgrade virtual application packages that have been created with previous versions of App-V.</span></span>

**<span data-ttu-id="6d049-105">注</span><span class="sxs-lookup"><span data-stu-id="6d049-105">Note</span></span>**  
<span data-ttu-id="6d049-106">64ビットアーキテクチャを搭載したコンピューターを実行している場合は、x86 バージョンの PowerShell を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d049-106">If you are running a computer with a 64-bit architecture, you must use the x86 version of PowerShell.</span></span>



<span data-ttu-id="6d049-107">パッケージコンバーターは、アプリ-V 4.5 sequencer またはそれ以降のバージョンを使って作成されたパッケージのみ、直接変換できます。</span><span class="sxs-lookup"><span data-stu-id="6d049-107">The package converter can only directly convert packages that were created by using the App-V 4.5 sequencer or a subsequent version.</span></span> <span data-ttu-id="6d049-108">App-v 4.5 より前のバージョンを使って作成されたパッケージは、変換する前に、App-v 4.5 または App-v 4.6 形式にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d049-108">Packages that were created using a version prior to App-V 4.5 must be upgraded to the App-V 4.5 or App-V 4.6 format before conversion.</span></span>

<span data-ttu-id="6d049-109">次の情報は、既存の仮想アプリケーションパッケージを変換する方向を示しています。</span><span class="sxs-lookup"><span data-stu-id="6d049-109">The following information provides direction for converting existing virtual application packages.</span></span>

**<span data-ttu-id="6d049-110">重要</span><span class="sxs-lookup"><span data-stu-id="6d049-110">Important</span></span>**  
<span data-ttu-id="6d049-111">パッケージの食ファイルをセキュリティで保護された場所とディレクトリに常に保存するようにパッケージコンバーターを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d049-111">You must configure the package converter to always save the package ingredients file to a secure location and directory.</span></span> <span data-ttu-id="6d049-112">セキュリティで保護された場所には、管理者のみがアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6d049-112">A secure location is accessible only by an administrator.</span></span> <span data-ttu-id="6d049-113">さらに、パッケージを展開するときは、安全な場所にパッケージを保存するか、変換処理中に他のユーザーがログインすることを許可されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d049-113">Additionally, when you deploy the package, you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion process.</span></span>



**<span data-ttu-id="6d049-114">App-v 4.6 のインストールフォルダーが仮想ファイルシステムルートにリダイレクトされます</span><span class="sxs-lookup"><span data-stu-id="6d049-114">App-V 4.6 installation folder is redirected to virtual file system root</span></span>**

<span data-ttu-id="6d049-115">パッケージを App-v 4.6 から5.1 に変換する場合、App-v 5.1 パッケージは、4.6 パッケージを作成するときに必要だったハードコードされたドライブにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="6d049-115">When you convert packages from App-V 4.6 to 5.1, the App-V 5.1 package can access the hardcoded drive that you were required to use when you created 4.6 packages.</span></span> <span data-ttu-id="6d049-116">ドライブ文字は、4.6 の優先順位のコンピューターでインストールドライブとして選択したドライブになります。</span><span class="sxs-lookup"><span data-stu-id="6d049-116">The drive letter will be the drive you selected as the installation drive on the 4.6 sequencing machine.</span></span> <span data-ttu-id="6d049-117">(既定のドライブ文字は Q:\\.)</span><span class="sxs-lookup"><span data-stu-id="6d049-117">(The default drive letter is Q:\\.)</span></span>

<span data-ttu-id="6d049-118">App-v 5.1 より前のバージョンでは、4.6 のルートフォルダーは認識されず、App-v 5.0 パッケージでアクセスできませんでした。</span><span class="sxs-lookup"><span data-stu-id="6d049-118">Prior to App-V 5.1, the 4.6 root folder was not recognized and could not be accessed by App-V 5.0 packages.</span></span> <span data-ttu-id="6d049-119">この時点で、アプリ5.1 からの完全なパスを使用して、ハードコーディングされたファイルにアクセスしたり、プログラムによってプログラムによって4.6 ファイルをプログラムで列挙したりできます。</span><span class="sxs-lookup"><span data-stu-id="6d049-119">Now, App-V 5.1 packages can access hardcoded files by their full path or can programmatically enumerate files under the App-V 4.6 installation root.</span></span>

<span data-ttu-id="6d049-120">**技術的な詳細:** App-v 5.1 パッケージコンバーターによって、Filesystem 要素の FilesystemMetadata.xml ファイルに、App-v 4.6 インストールルートフォルダーと短いフォルダー名が保存されます。</span><span class="sxs-lookup"><span data-stu-id="6d049-120">**Technical Details:** The App-V 5.1 package converter will save the App-V 4.6 installation root folder and short folder names in the FilesystemMetadata.xml file in the Filesystem element.</span></span> <span data-ttu-id="6d049-121">App-v 5.1 クライアントで仮想プロセスが作成されると、アプリ-V 4.6 インストールルートから仮想ファイルシステムのルートへの要求がマップされます。</span><span class="sxs-lookup"><span data-stu-id="6d049-121">When the App-V 5.1 client creates the virtual process, it will map requests from the App-V 4.6 installation root to the virtual file system root.</span></span>

**<span data-ttu-id="6d049-122">開始するには</span><span class="sxs-lookup"><span data-stu-id="6d049-122">Getting started</span></span>**

1.  <span data-ttu-id="6d049-123">環境内のコンピューターに app-v Sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6d049-123">Install the App-V Sequencer on a computer in your environment.</span></span> <span data-ttu-id="6d049-124">Sequencer のインストール方法については、「 [sequencer をインストールする方法](how-to-install-the-sequencer-51beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d049-124">For information about how to install the Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

2.  

    <span data-ttu-id="6d049-125">次のコマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6d049-125">The following cmdlets are available:</span></span>

    -   <span data-ttu-id="6d049-126">AppvLegacyPackage –このコマンドレットは、パッケージを確認するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="6d049-126">Test-AppvLegacyPackage – This cmdlet is designed to check packages.</span></span> <span data-ttu-id="6d049-127">このアプリは **、見つからない**ファイル、無効なソース、 **.osd**ファイルエラー、または無効なパッケージバージョンなど、パッケージに関連するすべてのエラーに関する情報を返します。</span><span class="sxs-lookup"><span data-stu-id="6d049-127">It will return information about any failures with the package such as missing **.sft** files, an invalid source, **.osd** file errors, or invalid package version.</span></span> <span data-ttu-id="6d049-128">このコマンドレットは、 **sft**ファイルを解析したり、詳細な検証を実行したりしません。</span><span class="sxs-lookup"><span data-stu-id="6d049-128">This cmdlet will not parse the **.sft** file or do any in depth validation.</span></span> <span data-ttu-id="6d049-129">このコマンドレットのオプションと基本的な機能の詳細については、PowerShell cmdline を使用して「」と入力 `Test-AppvLegacyPackage -?` します。</span><span class="sxs-lookup"><span data-stu-id="6d049-129">For information about options and basic functionality for this cmdlet, using the PowerShell cmdline, type `Test-AppvLegacyPackage -?`.</span></span>

    -   <span data-ttu-id="6d049-130">ConvertFrom-AppvLegacyPackage –既存のパッケージを変換するには、を入力 `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages` します。</span><span class="sxs-lookup"><span data-stu-id="6d049-130">ConvertFrom-AppvLegacyPackage – To convert an existing package, type `ConvertFrom-AppvLegacyPackage c:\contentStore c:\convertedPackages`.</span></span> <span data-ttu-id="6d049-131">このコマンドは、 `c:\contentStore` 既存のパッケージの場所を表します。これは、生成された `c:\convertedPackages` app-v 5.1 仮想アプリケーションパッケージファイルが保存される出力ディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="6d049-131">In this command, `c:\contentStore` represents the location of the existing package and `c:\convertedPackages` is the output directory to which the resulting App-V 5.1 virtual application package file will be saved.</span></span> <span data-ttu-id="6d049-132">既定では、新しい名前を指定しない場合は、古いパッケージ名が App-v 5.1 ファイル名として使われます。</span><span class="sxs-lookup"><span data-stu-id="6d049-132">By default, if you do not specify a new name, the old package name will be used for the App-V 5.1 filename.</span></span>

        <span data-ttu-id="6d049-133">さらに、パッケージコンバーターは、パッケージをストリームフォールトに設定することによって、app-v 5.1 でパッケージのパフォーマンスを最適化します。</span><span class="sxs-lookup"><span data-stu-id="6d049-133">Additionally, the package converter optimizes performance of packages in App-V 5.1 by setting the package to stream fault the App-V package.</span></span>  <span data-ttu-id="6d049-134">これはプライマリ機能ブロックよりもパフォーマンスが高く、パッケージを完全にダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="6d049-134">This is more performant than the primary feature block and fully downloading the package.</span></span> <span data-ttu-id="6d049-135">フラグ**Downloadfullpackageonfirstlaunch**を使用すると、パッケージを変換して、既定でパッケージが完全にダウンロードされるように設定することができます。</span><span class="sxs-lookup"><span data-stu-id="6d049-135">The flag **DownloadFullPackageOnFirstLaunch** allows you to convert the package and set the package to be fully downloaded by default.</span></span>

        **<span data-ttu-id="6d049-136">注</span><span class="sxs-lookup"><span data-stu-id="6d049-136">Note</span></span>**  
        <span data-ttu-id="6d049-137">出力ディレクトリを指定する前に、出力ディレクトリを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d049-137">Before you specify the output directory, you must create the output directory.</span></span>



~~~
**Advanced Conversion Tips**

-   Piping - PowerShell supports piping. Piping allows you to call `dir c:\contentStore\myPackage | Test-AppvLegacyPackage`. In this example, the directory object that represents `myPackage` will be given as input to the `Test-AppvLegacyPackage` command and bound to the `-Source` parameter. Piping like this is especially useful when you want to batch commands together; for example, `dir .\ | Test-AppvLegacyPackage | ConvertFrom-AppvLegacyAppvPackage -Target .\ConvertedPackages`. This piped command would test the packages and then pass those objects on to actually be converted. You can also apply a filter on packages without errors or only specify a directory which contains an **.sprj** file or pipe them to another cmdlet that adds the filtered package to the server or publishes them to the App-V 5.1 client.

-   Batching - The PowerShell command enables batching. More specifically, the cmdlets support taking a string\[\] object for the `-Source` parameter which represents a list of directory paths. This allows you to enter `$packages = dir c:\contentStore` and then call `ConvertFrom-AppvLegacyAppvPackage-Source $packages -Target c:\ConvertedPackages` or to use piping and call `dir c:\ContentStore | ConvertFrom-AppvLegacyAppvPackage -Target C:\ConvertedPackages`.

-   Other functionality - PowerShell has other built-in functionality for features such as aliases, piping, lazy-binding, .NET object, and many others. All of these are usable in PowerShell and can help you create advanced scenarios for the Package Converter.

**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="6d049-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d049-138">Related topics</span></span>


[<span data-ttu-id="6d049-139">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="6d049-139">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









