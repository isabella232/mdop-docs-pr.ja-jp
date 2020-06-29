---
title: アプリケーションの公開とクライアントとのやり取り
description: アプリケーションの公開とクライアントとのやり取り
author: dansimp
ms.assetid: 36a4bf6f-a917-41a6-9856-6248686df352
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 69fcf119faaf35e53ae36f386bcb3480e2ee3b0e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814731"
---
# <span data-ttu-id="09441-103">アプリケーションの公開とクライアントとのやり取り</span><span class="sxs-lookup"><span data-stu-id="09441-103">Application Publishing and Client Interaction</span></span>


<span data-ttu-id="09441-104">この記事では、一般的な App-v クライアント操作とローカルオペレーティングシステムとの統合に関する技術情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-104">This article provides technical information about common App-V client operations and their integration with the local operating system.</span></span>

-   [<span data-ttu-id="09441-105">Sequencer によって作成された app-v パッケージファイル</span><span class="sxs-lookup"><span data-stu-id="09441-105">App-V package files created by the Sequencer</span></span>](#bkmk-appv-pkg-files-list)

-   [<span data-ttu-id="09441-106">Appv ファイルには何がありますか?</span><span class="sxs-lookup"><span data-stu-id="09441-106">What’s in the appv file?</span></span>](#bkmk-appv-file-contents)

-   [<span data-ttu-id="09441-107">App-v クライアントデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="09441-107">App-V client data storage locations</span></span>](#bkmk-files-data-storage)

-   [<span data-ttu-id="09441-108">パッケージレジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-108">Package registry</span></span>](#bkmk-pkg-registry)

-   [<span data-ttu-id="09441-109">App-v パッケージストアの動作</span><span class="sxs-lookup"><span data-stu-id="09441-109">App-V package store behavior</span></span>](#bkmk-pkg-store-behavior)

-   [<span data-ttu-id="09441-110">ローミングのレジストリとデータ</span><span class="sxs-lookup"><span data-stu-id="09441-110">Roaming registry and data</span></span>](#bkmk-roaming-reg-data)

-   [<span data-ttu-id="09441-111">App-v クライアントアプリケーションのライフサイクル管理</span><span class="sxs-lookup"><span data-stu-id="09441-111">App-V client application lifecycle management</span></span>](#bkmk-clt-app-lifecycle)

-   [<span data-ttu-id="09441-112">App-v パッケージの統合</span><span class="sxs-lookup"><span data-stu-id="09441-112">Integration of App-V packages</span></span>](#bkmk-integr-appv-pkgs)

-   [<span data-ttu-id="09441-113">動的構成処理</span><span class="sxs-lookup"><span data-stu-id="09441-113">Dynamic configuration processing</span></span>](#bkmk-dynamic-config)

-   [<span data-ttu-id="09441-114">Side-by-side アセンブリ</span><span class="sxs-lookup"><span data-stu-id="09441-114">Side-by-side assemblies</span></span>](#bkmk-sidebyside-assemblies)

-   [<span data-ttu-id="09441-115">クライアントログ</span><span class="sxs-lookup"><span data-stu-id="09441-115">Client logging</span></span>](#bkmk-client-logging)

<span data-ttu-id="09441-116">その他の参照情報については、 [Microsoft Application Virtualization (app-v) のドキュメントリソースのダウンロードページ](https://www.microsoft.com/download/details.aspx?id=27760)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-116">For additional reference information, see [Microsoft Application Virtualization (App-V) Documentation Resources Download Page](https://www.microsoft.com/download/details.aspx?id=27760).</span></span>

## <a href="" id="bkmk-appv-pkg-files-list"></a><span data-ttu-id="09441-117">Sequencer によって作成された app-v パッケージファイル</span><span class="sxs-lookup"><span data-stu-id="09441-117">App-V package files created by the Sequencer</span></span>


<span data-ttu-id="09441-118">Sequencer は App-v パッケージを作成し、仮想化されたアプリケーションを生成します。</span><span class="sxs-lookup"><span data-stu-id="09441-118">The Sequencer creates App-V packages and produces a virtualized application.</span></span> <span data-ttu-id="09441-119">シーケンス処理では、次のファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-119">The sequencing process creates the following files:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-120">ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-120">File</span></span></th>
<th align="left"><span data-ttu-id="09441-121">説明</span><span class="sxs-lookup"><span data-stu-id="09441-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-122">appv</span><span class="sxs-lookup"><span data-stu-id="09441-122">.appv</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-123">シーケンス処理からキャプチャされたアセットと状態情報を含むプライマリパッケージファイル。</span><span class="sxs-lookup"><span data-stu-id="09441-123">The primary package file, which contains the captured assets and state information from the sequencing process.</span></span></p></li>
<li><p><span data-ttu-id="09441-124">パッケージファイル、公開情報、およびトークン化された形式での、配布時にコンピューターと特定のユーザーに再適用可能なレジストリのアーキテクチャ。</span><span class="sxs-lookup"><span data-stu-id="09441-124">Architecture of the package file, publishing information, and registry in a tokenized form that can be reapplied to a machine and to a specific user upon delivery.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-125">.MSI</span><span class="sxs-lookup"><span data-stu-id="09441-125">.MSI</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-126">手動で、またはサードパーティの展開プラットフォームを使用して、app-v ファイルを展開するために使用できる実行可能な展開ラッパー。</span><span class="sxs-lookup"><span data-stu-id="09441-126">Executable deployment wrapper that you can use to deploy .appv files manually or by using a third-party deployment platform.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-127">_DeploymentConfig.XML</span><span class="sxs-lookup"><span data-stu-id="09441-127">_DeploymentConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-128">App-v クライアントを実行しているコンピューター上のすべてのユーザーにグローバルに展開されるパッケージ内のすべてのアプリケーションの既定の発行パラメーターをカスタマイズするために使用されるファイル。</span><span class="sxs-lookup"><span data-stu-id="09441-128">File used to customize the default publishing parameters for all applications in a package that is deployed globally to all users on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-129">_UserConfig.XML</span><span class="sxs-lookup"><span data-stu-id="09441-129">_UserConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-130">App-v クライアントを実行しているコンピューター上の特定のユーザーに展開されているパッケージ内のすべてのアプリケーションの発行パラメーターをカスタマイズするために使用されるファイルです。</span><span class="sxs-lookup"><span data-stu-id="09441-130">File used to customize the publishing parameters for all applications in a package that is a deployed to a specific user on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-131">Report.xml</span><span class="sxs-lookup"><span data-stu-id="09441-131">Report.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-132">ドライバーの除外、ファイル、レジストリの場所など、シーケンス処理の結果として発生するメッセージの概要。</span><span class="sxs-lookup"><span data-stu-id="09441-132">Summary of messages resulting from the sequencing process, including omitted drivers, files, and registry locations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-133">.CAB</span><span class="sxs-lookup"><span data-stu-id="09441-133">.CAB</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="09441-134">オプション: </em> 以前にシーケンスされた仮想アプリケーションパッケージを自動的に再構築するために使用されるパッケージアクセラレータファイル。</span><span class="sxs-lookup"><span data-stu-id="09441-134">Optional:</em> Package accelerator file used to automatically rebuild a previously sequenced virtual application package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-135">appvt</span><span class="sxs-lookup"><span data-stu-id="09441-135">.appvt</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="09441-136">オプション: </em> 一般的に再利用される sequencer 設定を保持するために使用される sequencer テンプレートファイル。</span><span class="sxs-lookup"><span data-stu-id="09441-136">Optional:</em> Sequencer template file used to retain commonly reused Sequencer settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-137">シーケンスの詳細については、「 [Application Virtualization シーケンスのガイド](https://go.microsoft.com/fwlink/?LinkID=269810)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-137">For information about sequencing, see [Application Virtualization Sequencing Guide](https://go.microsoft.com/fwlink/?LinkID=269810).</span></span>

## <a href="" id="bkmk-appv-file-contents"></a><span data-ttu-id="09441-138">Appv ファイルには何がありますか?</span><span class="sxs-lookup"><span data-stu-id="09441-138">What’s in the appv file?</span></span>


<span data-ttu-id="09441-139">Appv ファイルは、XML ファイルと XML 以外のファイルを1つのエンティティに保存するコンテナーです。</span><span class="sxs-lookup"><span data-stu-id="09441-139">The appv file is a container that stores XML and non-XML files together in a single entity.</span></span> <span data-ttu-id="09441-140">このファイルは、オープンパッケージ規則 (OPC) 標準に基づいた AppX 形式で作成されています。</span><span class="sxs-lookup"><span data-stu-id="09441-140">This file is built from the AppX format, which is based on the Open Packaging Conventions (OPC) standard.</span></span>

<span data-ttu-id="09441-141">Appv ファイルの内容を表示するには、パッケージのコピーを作成し、コピーしたファイルの名前を ZIP 拡張子に変更します。</span><span class="sxs-lookup"><span data-stu-id="09441-141">To view the appv file contents, make a copy of the package, and then rename the copied file to a ZIP extension.</span></span>

<span data-ttu-id="09441-142">Appv ファイルには、仮想アプリケーションを作成して発行するときに使用する、次のフォルダーとファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-142">The appv file contains the following folder and files, which are used when creating and publishing a virtual application:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-143">名前</span><span class="sxs-lookup"><span data-stu-id="09441-143">Name</span></span></th>
<th align="left"><span data-ttu-id="09441-144">型</span><span class="sxs-lookup"><span data-stu-id="09441-144">Type</span></span></th>
<th align="left"><span data-ttu-id="09441-145">説明</span><span class="sxs-lookup"><span data-stu-id="09441-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-146">ルート</span><span class="sxs-lookup"><span data-stu-id="09441-146">Root</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-147">ファイル フォルダー</span><span class="sxs-lookup"><span data-stu-id="09441-147">File folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-148">シーケンス中にキャプチャされる、仮想化されたアプリケーションのファイルシステムを含むディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="09441-148">Directory that contains the file system for the virtualized application that is captured during sequencing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-149">[Content_Types] .xml</span><span class="sxs-lookup"><span data-stu-id="09441-149">[Content_Types].xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-150">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-150">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-151">Appv ファイル (DLL、EXE、BIN など) の主要なコンテンツタイプの一覧です。</span><span class="sxs-lookup"><span data-stu-id="09441-151">List of the core content types in the appv file (e.g. DLL, EXE, BIN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-152">AppxBlockMap.xml</span><span class="sxs-lookup"><span data-stu-id="09441-152">AppxBlockMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-153">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-153">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-154">Appv ファイルのレイアウト。ファイル、ブロック、およびブロックマップ要素を使用します。これにより、App-v パッケージ内のファイルの場所と検証が有効になります。</span><span class="sxs-lookup"><span data-stu-id="09441-154">Layout of the appv file, which uses File, Block, and BlockMap elements that enable location and validation of files in the App-V package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-155">AppxManifest.xml</span><span class="sxs-lookup"><span data-stu-id="09441-155">AppxManifest.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-156">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-156">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-157">パッケージの追加、発行、起動に必要な情報が含まれているパッケージのメタデータ。</span><span class="sxs-lookup"><span data-stu-id="09441-157">Metadata for the package that contains the required information for adding, publishing, and launching the package.</span></span> <span data-ttu-id="09441-158">パッケージに関連付けられている拡張ポイント (ファイルの種類の関連付けとショートカット) と、名前と Guid が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-158">Includes extension points (file type associations and shortcuts) and the names and GUIDs associated with the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-159">FilesystemMetadata.xml</span><span class="sxs-lookup"><span data-stu-id="09441-159">FilesystemMetadata.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-160">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-160">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-161">シーケンス中にキャプチャされたファイルの一覧。属性 (例: ディレクトリ、ファイル、非透過ディレクトリ、空のディレクトリ、および長い名前と短い名前) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-161">List of the files captured during sequencing, including attributes (e.g., directories, files, opaque directories, empty directories,and long and short names).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-162">PackageHistory.xml</span><span class="sxs-lookup"><span data-stu-id="09441-162">PackageHistory.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-163">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-163">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-164">シーケンスコンピューターについての情報 (オペレーティングシステムのバージョン、Internet Explorer のバージョン、.Net Framework のバージョン) とプロセス (アップグレード、パッケージバージョン) について説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-164">Information about the sequencing computer (operating system version, Internet Explorer version, .Net Framework version) and process (upgrade, package version).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-165">.Dat</span><span class="sxs-lookup"><span data-stu-id="09441-165">Registry.dat</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-166">DAT ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-166">DAT File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-167">パッケージのシーケンス処理中にキャプチャされたレジストリキーと値。</span><span class="sxs-lookup"><span data-stu-id="09441-167">Registry keys and values captured during the sequencing process for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-168">StreamMap.xml</span><span class="sxs-lookup"><span data-stu-id="09441-168">StreamMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-169">XML ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-169">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-170">プライマリおよび発行機能ブロックのファイルのリスト。</span><span class="sxs-lookup"><span data-stu-id="09441-170">List of files for the primary and publishing feature block.</span></span> <span data-ttu-id="09441-171">発行機能ブロックには、パッケージを発行するためのファイル (EXE と DLL) の ICO ファイルと必要な部分が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-171">The publishing feature block contains the ICO files and required portions of files (EXE and DLL) for publishing the package.</span></span> <span data-ttu-id="09441-172">存在する場合、プライマリ機能ブロックには、シーケンス処理中にストリーミング用に最適化されたファイルが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-172">When present, the primary feature block includes files that have been optimized for streaming during the sequencing process.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a><span data-ttu-id="09441-173">App-v クライアントデータの保存場所</span><span class="sxs-lookup"><span data-stu-id="09441-173">App-V client data storage locations</span></span>


<span data-ttu-id="09441-174">App-v クライアントは、仮想アプリケーションが適切に動作し、ローカルにインストールされたアプリケーションと同じように動作するように、タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-174">The App-V client performs tasks to ensure that virtual applications run properly and work like locally installed applications.</span></span> <span data-ttu-id="09441-175">仮想アプリケーションを開いて実行するプロセスには、仮想ファイルシステムとレジストリからのマッピングが必要です。これにより、ユーザーが予期している従来のアプリケーションの必要なコンポーネントをアプリケーションに確実に持たせることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-175">The process of opening and running virtual applications requires mapping from the virtual file system and registry to ensure the application has the required components of a traditional application expected by users.</span></span> <span data-ttu-id="09441-176">このセクションでは、仮想アプリケーションを実行するために必要なアセットと、App-v にアセットが保存されている場所を一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="09441-176">This section describes the assets that are required to run virtual applications and lists the location where App-V stores the assets.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-177">名前</span><span class="sxs-lookup"><span data-stu-id="09441-177">Name</span></span></th>
<th align="left"><span data-ttu-id="09441-178">場所</span><span class="sxs-lookup"><span data-stu-id="09441-178">Location</span></span></th>
<th align="left"><span data-ttu-id="09441-179">説明</span><span class="sxs-lookup"><span data-stu-id="09441-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-180">パッケージストア</span><span class="sxs-lookup"><span data-stu-id="09441-180">Package Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-181">%ProgramData%\App-V</span><span class="sxs-lookup"><span data-stu-id="09441-181">%ProgramData%\App-V</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-182">読み取り専用パッケージファイルの既定の場所</span><span class="sxs-lookup"><span data-stu-id="09441-182">Default location for read only package files</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-183">マシンカタログ</span><span class="sxs-lookup"><span data-stu-id="09441-183">Machine Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="09441-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-185">コンピューターごとの構成ドキュメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="09441-185">Contains per-machine configuration documents</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-186">ユーザーカタログ</span><span class="sxs-lookup"><span data-stu-id="09441-186">User Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-187">%AppData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="09441-187">%AppData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-188">ユーザーごとの構成ドキュメントが含まれています</span><span class="sxs-lookup"><span data-stu-id="09441-188">Contains per-user configuration documents</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-189">ショートカットバックアップ</span><span class="sxs-lookup"><span data-stu-id="09441-189">Shortcut Backups</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span><span class="sxs-lookup"><span data-stu-id="09441-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-191">パッケージの未公開の復元を可能にする、以前の統合ポイントが保存されます</span><span class="sxs-lookup"><span data-stu-id="09441-191">Stores previous integration points that enable restore on package unpublish</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-192">書き込み時 (COW) ローミング</span><span class="sxs-lookup"><span data-stu-id="09441-192">Copy on Write (COW) Roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-193">%AppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="09441-193">%AppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-194">パッケージを変更するための書き込み可能なローミングの場所</span><span class="sxs-lookup"><span data-stu-id="09441-194">Writeable roaming location for package modification</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-195">書き込み時 (COW) のローカルコピー</span><span class="sxs-lookup"><span data-stu-id="09441-195">Copy on Write (COW) Local</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="09441-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-197">パッケージを変更するための書き込み可能なローミングしない場所</span><span class="sxs-lookup"><span data-stu-id="09441-197">Writeable non-roaming location for package modification</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-198">コンピューターのレジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-198">Machine Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-199">HKLM\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="09441-199">HKLM\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-200">VReg for machine またはグローバルに公開されたパッケージ (コンピューターハイブ) などのパッケージの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-200">Contains package state information, including VReg for machine or globally published packages (Machine hive)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-201">ユーザーレジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-201">User Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-202">HKCU\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="09441-202">HKCU\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-203">VReg などのユーザーパッケージの状態情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-203">Contains user package state information including VReg</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-204">ユーザーレジストリクラス</span><span class="sxs-lookup"><span data-stu-id="09441-204">User Registry Classes</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-205">Hkcu\ ソフトウェア \ クラス \ AppV</span><span class="sxs-lookup"><span data-stu-id="09441-205">HKCU\Software\Classes\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-206">追加のユーザーパッケージの状態情報が含まれています</span><span class="sxs-lookup"><span data-stu-id="09441-206">Contains additional user package state information</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-207">表の詳細については、次のセクションとドキュメント全体で説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-207">Additional details for the table are provided in the section below and throughout the document.</span></span>

### <span data-ttu-id="09441-208">パッケージストア</span><span class="sxs-lookup"><span data-stu-id="09441-208">Package store</span></span>

<span data-ttu-id="09441-209">App-v クライアントは、パッケージストアにマウントされているアプリケーションアセットを管理します。</span><span class="sxs-lookup"><span data-stu-id="09441-209">The App-V Client manages the applications assets mounted in the package store.</span></span> <span data-ttu-id="09441-210">この既定の保存場所はですが `%ProgramData%\App-V` 、セットアップ中またはセットアップ後に構成するには、 `Set-AppVClientConfiguration` ローカルレジストリ ( `PackageInstallationRoot` キーの下の値) を変更する PowerShell コマンドを使用し `HKLM\Software\Microsoft\AppV\Client\Streaming` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-210">This default storage location is `%ProgramData%\App-V`, but you can configure it during or after setup by using the `Set-AppVClientConfiguration` PowerShell command, which modifies the local registry (`PackageInstallationRoot` value under the `HKLM\Software\Microsoft\AppV\Client\Streaming` key).</span></span> <span data-ttu-id="09441-211">パッケージストアは、クライアントオペレーティングシステムのローカルパスに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-211">The package store must be located at a local path on the client operating system.</span></span> <span data-ttu-id="09441-212">個々のパッケージは、パッケージ GUID とバージョン GUID という名前のサブディレクトリのパッケージストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-212">The individual packages are stored in the package store in subdirectories named for the Package GUID and Version GUID.</span></span>

<span data-ttu-id="09441-213">特定のアプリケーションへのパスの例:</span><span class="sxs-lookup"><span data-stu-id="09441-213">Example of a path to a specific application:</span></span>

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

<span data-ttu-id="09441-214">セットアップ時にパッケージストアの既定の場所を変更する方法については、「 [App-v クライアントを展開する方法](how-to-deploy-the-app-v-client-51gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-214">To change the default location of the package store during setup, see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md).</span></span>

### <span data-ttu-id="09441-215">共有コンテンツストア</span><span class="sxs-lookup"><span data-stu-id="09441-215">Shared Content Store</span></span>

<span data-ttu-id="09441-216">App-v クライアントが共有コンテンツストアモードで構成されている場合、ストリームフォールトが発生したときに、データはディスクに書き込まれません。つまり、パッケージでは、最小限のローカルディスク領域 (パブリッシュデータ) が必要です。</span><span class="sxs-lookup"><span data-stu-id="09441-216">If the App-V Client is configured in Shared Content Store mode, no data is written to disk when a stream fault occurs, which means that the packages require minimal local disk space (publishing data).</span></span> <span data-ttu-id="09441-217">ディスク領域を節約するには、ローカルストレージを制限できるため、高パフォーマンスのネットワーク上の場所 (SAN など) からアプリケーションをストリーミングすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="09441-217">The use of less disk space is highly desirable in VDI environments, where local storage can be limited, and streaming the applications from a high performance network location (such as a SAN) is preferable.</span></span> <span data-ttu-id="09441-218">共有コンテンツストアモードの詳細については、を参照してください <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。</span><span class="sxs-lookup"><span data-stu-id="09441-218">For more information on shared content store mode, see <https://go.microsoft.com/fwlink/p/?LinkId=392750>.</span></span>

<span data-ttu-id="09441-219">**注** App-v クライアントで共有コンテンツストアの構成を使用している場合でも、コンピューターとパッケージストアはローカルドライブに配置されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-219">**Note** The machine and package store must be located on a local drive, even when you’re using Shared Content Store configurations for the App-V Client.</span></span>

 

### <span data-ttu-id="09441-220">パッケージカタログ</span><span class="sxs-lookup"><span data-stu-id="09441-220">Package catalogs</span></span>

<span data-ttu-id="09441-221">App-v クライアントは、次の2つのファイルベースの場所を管理します。</span><span class="sxs-lookup"><span data-stu-id="09441-221">The App-V Client manages the following two file-based locations:</span></span>

-   **<span data-ttu-id="09441-222">カタログ (ユーザーとコンピューター)</span><span class="sxs-lookup"><span data-stu-id="09441-222">Catalogs (user and machine).</span></span>**

-   <span data-ttu-id="09441-223">**レジストリの場所**: パッケージの発行方法によって異なります。</span><span class="sxs-lookup"><span data-stu-id="09441-223">**Registry locations** - depends on how the package is targeted for publishing.</span></span> <span data-ttu-id="09441-224">コンピューターのカタログ (データストア) と個々のユーザーのカタログがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-224">There is a Catalog (data store) for the computer, and a catalog for each individual user.</span></span> <span data-ttu-id="09441-225">コンピューターカタログには、すべてのユーザーまたは任意のユーザーに適用されるグローバル情報が保存され、ユーザーカタログには特定のユーザーに適用される情報が格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-225">The Machine Catalog stores global information applicable to all users or any user, and the User Catalog stores information applicable to a specific user.</span></span> <span data-ttu-id="09441-226">カタログは、動的構成とマニフェストファイルのコレクションです。パッケージバージョンごとの file と registry のどちらにも個別のデータがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-226">The Catalog is a collection of Dynamic Configurations and manifest files; there is discrete data for both file and registry per package version.</span></span> 

### <span data-ttu-id="09441-227">マシンカタログ</span><span class="sxs-lookup"><span data-stu-id="09441-227">Machine catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-228">説明</span><span class="sxs-lookup"><span data-stu-id="09441-228">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-229">パッケージが追加されて発行されるときに、コンピューター上のユーザーが利用できるパッケージドキュメントを保存します。</span><span class="sxs-lookup"><span data-stu-id="09441-229">Stores package documents that are available to users on the machine, when packages are added and published.</span></span> <span data-ttu-id="09441-230">ただし、公開時にパッケージが "グローバル" の場合、すべてのユーザーが統合を利用できます。</span><span class="sxs-lookup"><span data-stu-id="09441-230">However, if a package is “global” at publishing time, the integrations are available to all users.</span></span></p>
<p><span data-ttu-id="09441-231">パッケージがグローバルでない場合は、特定のユーザーに対してのみ統合が公開されますが、グローバルリソースは、クライアントコンピューター上のすべてのユーザーに対して変更されて表示されます (たとえば、パッケージディレクトリは共有ディスクの場所にあります)。</span><span class="sxs-lookup"><span data-stu-id="09441-231">If a package is non-global, the integrations are published only for specific users, but there are still global resources that are modified and visible to anyone on the client computer (e.g., the package directory is in a shared disk location).</span></span></p>
<p><span data-ttu-id="09441-232">パッケージがコンピューター上のユーザー (グローバルまたは非グローバル) で利用できる場合、マニフェストはコンピューターカタログに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-232">If a package is available to a user on the computer (global or non-global), the manifest is stored in the Machine Catalog.</span></span> <span data-ttu-id="09441-233">パッケージがグローバルに公開されている場合、コンピューターカタログに保存されている動的構成ファイルがあります。したがって、パッケージがグローバルであるかどうかは、コンピューターカタログのポリシーファイル (UserDeploymentConfiguration ファイル) があるかどうかによって定義されます。</span><span class="sxs-lookup"><span data-stu-id="09441-233">When a package is published globally, there is a Dynamic Configuration file, stored in the Machine Catalog; therefore, the determination of whether a package is global is defined according to whether there is a policy file (UserDeploymentConfiguration file) in the Machine Catalog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-234">既定の保存場所</span><span class="sxs-lookup"><span data-stu-id="09441-234">Default storage location</span></span></p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p><span data-ttu-id="09441-235">この場所は、パッケージストアの場所とは異なります。</span><span class="sxs-lookup"><span data-stu-id="09441-235">This location is not the same as the Package Store location.</span></span> <span data-ttu-id="09441-236">パッケージストアは、パッケージファイルのゴールデンまたは pristine のコピーです。</span><span class="sxs-lookup"><span data-stu-id="09441-236">The Package Store is the golden or pristine copy of the package files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-237">Machine カタログ内のファイル</span><span class="sxs-lookup"><span data-stu-id="09441-237">Files in the machine catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-238">Manifest.xml</span><span class="sxs-lookup"><span data-stu-id="09441-238">Manifest.xml</span></span></p></li>
<li><p><span data-ttu-id="09441-239">DeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="09441-239">DeploymentConfiguration.xml</span></span></p></li>
<li><p><span data-ttu-id="09441-240">UserManifest.xml (グローバルに公開されるパッケージ)</span><span class="sxs-lookup"><span data-stu-id="09441-240">UserManifest.xml (Globally Published Package)</span></span></p></li>
<li><p><span data-ttu-id="09441-241">UserDeploymentConfiguration.xml (グローバルに公開されるパッケージ)</span><span class="sxs-lookup"><span data-stu-id="09441-241">UserDeploymentConfiguration.xml (Globally Published Package)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-242">パッケージが接続グループの一部であるときに使用される、追加のコンピューターカタログの場所</span><span class="sxs-lookup"><span data-stu-id="09441-242">Additional machine catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-243">次の場所は、上で説明した特定のパッケージの場所に加えています。</span><span class="sxs-lookup"><span data-stu-id="09441-243">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-244">パッケージが接続グループの一部である場合の、コンピューターカタログ内の追加ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-244">Additional files in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-245">PackageGroupDescriptor.xml</span><span class="sxs-lookup"><span data-stu-id="09441-245">PackageGroupDescriptor.xml</span></span></p></li>
<li><p><span data-ttu-id="09441-246">UserPackageGroupDescriptor.xml (グローバルに公開された接続グループ)</span><span class="sxs-lookup"><span data-stu-id="09441-246">UserPackageGroupDescriptor.xml (globally published Connection Group)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="09441-247">ユーザーカタログ</span><span class="sxs-lookup"><span data-stu-id="09441-247">User catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-248">説明</span><span class="sxs-lookup"><span data-stu-id="09441-248">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-249">発行プロセス中に作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-249">Created during the publishing process.</span></span> <span data-ttu-id="09441-250">パッケージの公開に使用される情報が含まれています。また、起動時に、特定のユーザーにパッケージがプロビジョニングされていることを確認するためにも使われます。</span><span class="sxs-lookup"><span data-stu-id="09441-250">Contains information used for publishing the package, and also used at launch to ensure that a package is provisioned to a specific user.</span></span> <span data-ttu-id="09441-251">ローミングの場所に作成され、ユーザー固有の公開情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-251">Created in a roaming location and includes user-specific publishing information.</span></span></p>
<p><span data-ttu-id="09441-252">ユーザーに対してパッケージが公開されると、ポリシーファイルがユーザーカタログに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-252">When a package is published for a user, the policy file is stored in the User Catalog.</span></span> <span data-ttu-id="09441-253">同時に、マニフェストのコピーもユーザーカタログに保存されます。</span><span class="sxs-lookup"><span data-stu-id="09441-253">At the same time, a copy of the manifest is also stored in the User Catalog.</span></span> <span data-ttu-id="09441-254">ユーザーに対してパッケージの利用資格が削除されると、関連するパッケージファイルがユーザーカタログから削除されます。</span><span class="sxs-lookup"><span data-stu-id="09441-254">When a package entitlement is removed for a user, the relevant package files are removed from the User Catalog.</span></span> <span data-ttu-id="09441-255">ユーザーカタログを見ると、管理者は動的な構成ファイルの存在を見ることができます。これは、パッケージがそのユーザーの権利を持つことを示します。</span><span class="sxs-lookup"><span data-stu-id="09441-255">Looking at the user catalog, an administrator can view the presence of a Dynamic Configuration file, which indicates that the package is entitled for that user.</span></span></p>
<p><span data-ttu-id="09441-256">ローミングユーザーの場合は、ユーザーカタログをローミングまたは共有の場所に置いて、既定でターゲットユーザーを指定するようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-256">For roaming users, the User Catalog needs to be in a roaming or shared location to preserve the legacy App-V behavior of targeting users by default.</span></span> <span data-ttu-id="09441-257">利用資格とポリシーは、コンピューターではなくユーザーに関連付けられているため、プロビジョニングされたユーザーと一緒に移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-257">Entitlement and policy are tied to a user, not a computer, so they should roam with the user once they are provisioned.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-258">既定の保存場所</span><span class="sxs-lookup"><span data-stu-id="09441-258">Default storage location</span></span></p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-259">ユーザーカタログ内のファイル</span><span class="sxs-lookup"><span data-stu-id="09441-259">Files in the user catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-260">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="09441-260">UserManifest.xml</span></span></p></li>
<li><p><span data-ttu-id="09441-261">DynamicConfiguration.xml または UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="09441-261">DynamicConfiguration.xml or UserDeploymentConfiguration.xml</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-262">パッケージが接続グループの一部であるときに使用される追加のユーザーカタログの場所</span><span class="sxs-lookup"><span data-stu-id="09441-262">Additional user catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-263">次の場所は、上で説明した特定のパッケージの場所に加えています。</span><span class="sxs-lookup"><span data-stu-id="09441-263">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-264">パッケージが接続グループの一部である場合の、コンピューターカタログ内の追加ファイル</span><span class="sxs-lookup"><span data-stu-id="09441-264">Additional file in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="09441-265">ショートカットバックアップ</span><span class="sxs-lookup"><span data-stu-id="09441-265">Shortcut backups</span></span>

<span data-ttu-id="09441-266">公開プロセス中に、App-v クライアントは、ショートカットと統合ポイントをこのバックアップにバックアップし `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` ます。これにより、パッケージが未公開の場合、これらの統合ポイントを以前のバージョンに復元することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-266">During the publishing process, the App-V Client backs up any shortcuts and integration points to `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` This backup enables the restoration of these integration points to the previous versions when the package is unpublished.</span></span>

### <span data-ttu-id="09441-267">書き込み時にファイルをコピーする</span><span class="sxs-lookup"><span data-stu-id="09441-267">Copy on Write files</span></span>

<span data-ttu-id="09441-268">パッケージストアには、発行サーバーからストリーミングされたパッケージファイルの pristine コピーが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-268">The Package Store contains a pristine copy of the package files that have been streamed from the publishing server.</span></span> <span data-ttu-id="09441-269">App-v アプリケーションの通常の操作では、ユーザーまたはサービスはファイルの変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-269">During normal operation of an App-V application, the user or service may require changes to the files.</span></span> <span data-ttu-id="09441-270">アプリを修復する機能を維持するために、これらの変更はパッケージストアでは行われません。そのため、これらの変更は削除されます。</span><span class="sxs-lookup"><span data-stu-id="09441-270">These changes are not made in the package store in order to preserve your ability to repair the application, which removes these changes.</span></span> <span data-ttu-id="09441-271">これらの場所は、書き込み時にコピー (COW) と呼ばれ、ローミングとローミング以外の場所の両方をサポートします。</span><span class="sxs-lookup"><span data-stu-id="09441-271">These locations, called Copy on Write (COW), support both roaming and non-roaming locations.</span></span> <span data-ttu-id="09441-272">変更が保存される場所は、ネイティブエクスペリエンスに変更を書き込むためにプログラムがプログラミングされている場所によって異なります。</span><span class="sxs-lookup"><span data-stu-id="09441-272">The location where the modifications are stored depends where the application has been programmed to write changes to in a native experience.</span></span>

### <span data-ttu-id="09441-273">COW ローミング</span><span class="sxs-lookup"><span data-stu-id="09441-273">COW roaming</span></span>

<span data-ttu-id="09441-274">上で説明した COW ローミングの場所には、一般的な% AppData% の場所または \\Users\\{username}\\AppData\\Roaming の場所を対象とするファイルとディレクトリへの変更が保存されています。</span><span class="sxs-lookup"><span data-stu-id="09441-274">The COW Roaming location described above stores changes to files and directories that are targeted to the typical %AppData% location or \\Users\\{username}\\AppData\\Roaming location.</span></span> <span data-ttu-id="09441-275">これらのディレクトリとファイルは、オペレーティングシステムの設定に基づいてローミングされます。</span><span class="sxs-lookup"><span data-stu-id="09441-275">These directories and files are then roamed based on the operating system settings.</span></span>

### <span data-ttu-id="09441-276">COW ローカル</span><span class="sxs-lookup"><span data-stu-id="09441-276">COW local</span></span>

<span data-ttu-id="09441-277">COW ローカルの場所はローミングの場所と似ていますが、ローミングサポートが構成されている場合でも、ディレクトリとファイルは他のコンピューターにはローミングされません。</span><span class="sxs-lookup"><span data-stu-id="09441-277">The COW Local location is similar to the roaming location, but the directories and files are not roamed to other computers, even if roaming support has been configured.</span></span> <span data-ttu-id="09441-278">上で説明した COW ローカル上の場所は、一般的な windows に適用されますが、% AppData% の場所は変更できません。</span><span class="sxs-lookup"><span data-stu-id="09441-278">The COW Local location described above stores changes applicable to typical windows and not the %AppData% location.</span></span> <span data-ttu-id="09441-279">一覧に表示されるディレクトリは異なりますが、Windows の標準的な場所 (一般的な AppData や一般的な AppDataS など) には2つの場所があります。</span><span class="sxs-lookup"><span data-stu-id="09441-279">The directories listed will vary but there will be two locations for any typical Windows locations (e.g. Common AppData and Common AppDataS).</span></span> <span data-ttu-id="09441-280">**S**は、仮想サービスが、ログオンしているユーザーとは別の管理者として変更を要求した場合に、制限された場所を示します。</span><span class="sxs-lookup"><span data-stu-id="09441-280">The **S** signifies the restricted location when the virtual service requests the change as a different elevated user from the logged on users.</span></span> <span data-ttu-id="09441-281">非**S**位置には、ユーザーベースの変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="09441-281">The non-**S** location stores user based changes.</span></span>

## <a href="" id="bkmk-pkg-registry"></a><span data-ttu-id="09441-282">パッケージレジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-282">Package registry</span></span>


<span data-ttu-id="09441-283">アプリケーションがパッケージのレジストリデータにアクセスできるようにするには、その前に、App-v クライアントでパッケージのレジストリデータをアプリケーションで使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-283">Before an application can access the package registry data, the App-V Client must make the package registry data available to the applications.</span></span> <span data-ttu-id="09441-284">App-v クライアントは、実際のレジストリをすべてのレジストリデータのバッキングストアとして使用します。</span><span class="sxs-lookup"><span data-stu-id="09441-284">The App-V Client uses the real registry as a backing store for all registry data.</span></span>

<span data-ttu-id="09441-285">新しいパッケージを App-v クライアントに追加すると、レジストリのコピーが作成されます。パッケージからの DAT ファイルは、で作成され `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-285">When a new package is added to the App-V Client, a copy of the REGISTRY.DAT file from the package is created at `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat`.</span></span> <span data-ttu-id="09441-286">ファイルの名前は、のバージョン GUID です。DAT 拡張機能。</span><span class="sxs-lookup"><span data-stu-id="09441-286">The name of the file is the version GUID with the .DAT extension.</span></span> <span data-ttu-id="09441-287">このコピーが行われる理由は、パッケージの実際のハイブファイルが使用されていないことを確認することです。これにより、後でパッケージを削除できなくなります。</span><span class="sxs-lookup"><span data-stu-id="09441-287">The reason this copy is made is to ensure that the actual hive file in the package is never in use, which would prevent the removal of the package at a later time.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="09441-288">パッケージストアからのレジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-288">Registry.dat from Package Store</span></span></strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong><span data-ttu-id="09441-289">%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</span><span class="sxs-lookup"><span data-stu-id="09441-289">%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-290">クライアントでパッケージの最初のアプリケーションが起動されると、クライアントはハイブファイルの内容をステージまたはコピーし、別の場所でパッケージレジストリデータを再作成し `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-290">When the first application from the package is launched on the client, the client stages or copies the contents out of the hive file, re-creating the package registry data in an alternate location `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY`.</span></span> <span data-ttu-id="09441-291">ステージされたレジストリデータには、2つの異なる種類のコンピューターデータとユーザーデータがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-291">The staged registry data has two distinct types of machine data and user data.</span></span> <span data-ttu-id="09441-292">マシンデータは、マシン上のすべてのユーザーに対して共有されます。</span><span class="sxs-lookup"><span data-stu-id="09441-292">Machine data is shared across all users on the machine.</span></span> <span data-ttu-id="09441-293">ユーザーデータは、ユーザーごとにユーザー固有の場所にステージングされ `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-293">User data is staged for each user to a userspecific location `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User`.</span></span> <span data-ttu-id="09441-294">マシンデータは、パッケージの削除時に最終的に削除され、ユーザーのデータが削除された場合にユーザーデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="09441-294">The machine data is ultimately removed at package removal time, and the user data is removed on a user unpublish operation.</span></span>

### <span data-ttu-id="09441-295">パッケージレジストリステージングと接続グループレジストリステージング</span><span class="sxs-lookup"><span data-stu-id="09441-295">Package registry staging vs. connection group registry staging</span></span>

<span data-ttu-id="09441-296">接続グループが存在する場合、以前のレジストリのステージングプロセスは true を保持しますが、1つの hive ファイルを処理する代わりに、複数のハイブファイルがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-296">When connection groups are present, the previous process of staging the registry holds true, but instead of having one hive file to process, there are more than one.</span></span> <span data-ttu-id="09441-297">ファイルは、接続グループ XML に表示されている順序で処理され、最初のライターが競合に勝利します。</span><span class="sxs-lookup"><span data-stu-id="09441-297">The files are processed in the order in which they appear in the connection group XML, with the first writer winning any conflicts.</span></span>

<span data-ttu-id="09441-298">ステージされたレジストリは、1つのパッケージケースと同じように維持されます。</span><span class="sxs-lookup"><span data-stu-id="09441-298">The staged registry persists the same way as in the single package case.</span></span> <span data-ttu-id="09441-299">ステージングされたユーザーのレジストリデータは、無効になるまで接続グループに残ります。接続グループの削除時にステージマシンのレジストリデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="09441-299">Staged user registry data remains for the connection group until it is disabled; staged machine registry data is removed on connection group removal.</span></span>

### <span data-ttu-id="09441-300">仮想レジストリ</span><span class="sxs-lookup"><span data-stu-id="09441-300">Virtual registry</span></span>

<span data-ttu-id="09441-301">仮想レジストリ (VREG) の目的は、パッケージレジストリとネイティブレジストリの1つのマージされたビューをアプリケーションに提供することです。</span><span class="sxs-lookup"><span data-stu-id="09441-301">The purpose of the virtual registry (VREG) is to provide a single merged view of the package registry and the native registry to applications.</span></span> <span data-ttu-id="09441-302">また、書き込み時書き込み (COW) 機能も提供します。これは、仮想プロセスのコンテキストからレジストリに加えられたすべての変更を、個別の COW 位置に作成することです。</span><span class="sxs-lookup"><span data-stu-id="09441-302">It also provides copy-on-write (COW) functionality – that is any changes made to the registry from the context of a virtual process are made to a separate COW location.</span></span> <span data-ttu-id="09441-303">つまり、VREG は、レジストリの COW-ネイティブで設定されている場所に基づいて、最大3つの個別のレジストリ位置を1つのビューに結合する必要があることを意味し &gt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="09441-303">This means that the VREG must combine up to three separate registry locations into a single view based on the populated locations in the registry COW -&gt; package -&gt; native.</span></span> <span data-ttu-id="09441-304">レジストリデータに対する要求が行われると、要求されたデータが検出されるまで順番に検索されます。</span><span class="sxs-lookup"><span data-stu-id="09441-304">When a request is made for a registry data it will locate in order until it finds the data it was requesting.</span></span> <span data-ttu-id="09441-305">つまり、COW の場所に格納されている値がある場合は、他の場所に移動しません。ただし、COW の場所にデータが存在しない場合は、パッケージに進み、適切なデータが見つかるまで、ネイティブの場所に格納します。</span><span class="sxs-lookup"><span data-stu-id="09441-305">Meaning if there is a value stored in a COW location it will not proceed to other locations, however, if there is no data in the COW location it will proceed to the Package and then Native location until it finds the appropriate data.</span></span>

### <span data-ttu-id="09441-306">レジストリの場所</span><span class="sxs-lookup"><span data-stu-id="09441-306">Registry locations</span></span>

<span data-ttu-id="09441-307">パッケージが個別に公開されるか、または接続グループの一部として公開されるかに応じて、2つのパッケージレジストリの場所と2つの接続グループの場所があります。</span><span class="sxs-lookup"><span data-stu-id="09441-307">There are two package registry locations and two connection group locations where the App-V Client stores registry information, depending on whether the Package is published individually or as part of a connection group.</span></span> <span data-ttu-id="09441-308">パッケージ用の COW 場所は3つあり、接続グループには3つあり、VREG によって作成および管理されます。</span><span class="sxs-lookup"><span data-stu-id="09441-308">There are three COW locations for packages and three for connection groups, which are created and managed by the VREG.</span></span> <span data-ttu-id="09441-309">パッケージと接続グループの設定は共有されません。</span><span class="sxs-lookup"><span data-stu-id="09441-309">Settings for packages and connection groups are not shared:</span></span>

**<span data-ttu-id="09441-310">シングルパッケージ VReg:</span><span class="sxs-lookup"><span data-stu-id="09441-310">Single Package VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="09441-311">場所</span><span class="sxs-lookup"><span data-stu-id="09441-311">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="09441-312">説明</span><span class="sxs-lookup"><span data-stu-id="09441-312">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="09441-313">手法</span><span class="sxs-lookup"><span data-stu-id="09441-313">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-314">コンピューター Registry\Client\Packages\PkgGUID\REGISTRY (書き込みできるのは昇格プロセスのみ)</span><span class="sxs-lookup"><span data-stu-id="09441-314">Machine Registry\Client\Packages\PkgGUID\REGISTRY (Only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="09441-315">ユーザー Registry\Client\Packages\PkgGUID\REGISTRY (ユーザーローミング (ソフトウェア \ クラス以外の HKCU の下に記載されているもの)</span><span class="sxs-lookup"><span data-stu-id="09441-315">User Registry\Client\Packages\PkgGUID\REGISTRY (User Roaming anything written under HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="09441-316">User Registry Classes\Client\Packages\PkgGUID\REGISTRY (hkcu¥ソフトウェア \ クラスの書き込みと、昇格していないプロセスの HKLM)</span><span class="sxs-lookup"><span data-stu-id="09441-316">User Registry Classes\Client\Packages\PkgGUID\REGISTRY (HKCU\Software\Classes writes and HKLM for non elevated process)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="09441-317">Package</span><span class="sxs-lookup"><span data-stu-id="09441-317">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-318">コンピューター Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span><span class="sxs-lookup"><span data-stu-id="09441-318">Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span></span></p></li>
<li><p><span data-ttu-id="09441-319">User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span><span class="sxs-lookup"><span data-stu-id="09441-319">User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="09441-320">先住民</span><span class="sxs-lookup"><span data-stu-id="09441-320">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-321">ネイティブアプリケーションのレジストリの場所</span><span class="sxs-lookup"><span data-stu-id="09441-321">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**<span data-ttu-id="09441-322">接続グループの VReg:</span><span class="sxs-lookup"><span data-stu-id="09441-322">Connection Group VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="09441-323">場所</span><span class="sxs-lookup"><span data-stu-id="09441-323">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="09441-324">説明</span><span class="sxs-lookup"><span data-stu-id="09441-324">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="09441-325">手法</span><span class="sxs-lookup"><span data-stu-id="09441-325">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-326">コンピューター Registry\Client\PackageGroups\GrpGUID\REGISTRY (書き込みできるのは昇格プロセスのみ)</span><span class="sxs-lookup"><span data-stu-id="09441-326">Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="09441-327">ユーザー Registry\Client\PackageGroups\GrpGUID\REGISTRY (ソフトウェア \ クラス以外の HKCU に書き込まれているもの)</span><span class="sxs-lookup"><span data-stu-id="09441-327">User Registry\Client\PackageGroups\GrpGUID\REGISTRY (Anything written to HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="09441-328">User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="09441-328">User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="09441-329">Package</span><span class="sxs-lookup"><span data-stu-id="09441-329">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-330">コンピューター Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="09441-330">Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
<li><p><span data-ttu-id="09441-331">User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="09441-331">User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="09441-332">先住民</span><span class="sxs-lookup"><span data-stu-id="09441-332">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="09441-333">ネイティブアプリケーションのレジストリの場所</span><span class="sxs-lookup"><span data-stu-id="09441-333">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="09441-334">HKLM には2つの COW の場所があります。昇格した管理者以外のプロセス</span><span class="sxs-lookup"><span data-stu-id="09441-334">There are two COW locations for HKLM; elevated and non-elevated processes.</span></span> <span data-ttu-id="09441-335">昇格されたプロセスは、HKLM の下のセキュリティ保護された COW に HKLM の変更を常に書き込みます。</span><span class="sxs-lookup"><span data-stu-id="09441-335">Elevated processes always write HKLM changes to the secure COW under HKLM.</span></span> <span data-ttu-id="09441-336">昇格されていないプロセスは、常に、セキュリティで保護されていない COW に HKLM の変更を記録します。</span><span class="sxs-lookup"><span data-stu-id="09441-336">Non-elevated processes always write HKLM changes to the non-secure COW under HKCU\\Software\\Classes.</span></span> <span data-ttu-id="09441-337">アプリケーションが HKLM から変更を読み取ると、昇格したプロセスは HKLM のセキュリティ保護された COW からの変更を読み取ります。</span><span class="sxs-lookup"><span data-stu-id="09441-337">When an application reads changes from HKLM, elevated processes will read changes from the secure COW under HKLM.</span></span> <span data-ttu-id="09441-338">どちらからも昇格していない読み取りは、安全でない COW の最初に行われた変更を favoring します。</span><span class="sxs-lookup"><span data-stu-id="09441-338">Non-elevated reads from both, favoring the changes made in the unsecure COW first.</span></span>

### <span data-ttu-id="09441-339">パススルーキー</span><span class="sxs-lookup"><span data-stu-id="09441-339">Pass-through keys</span></span>

<span data-ttu-id="09441-340">パススルーキーを使用すると、管理者は、パッケージと COW の場所をバイパスしてネイティブレジストリからのみ読み取り可能になるように、特定のキーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="09441-340">Pass-through keys enable an administrator to configure certain keys so they can only be read from the native registry, bypassing the Package and COW locations.</span></span> <span data-ttu-id="09441-341">パススルー場所は、(パッケージ固有ではなく) マシンに対してグローバルであり、キーへのパスを追加することで構成できます。これは、キーのパスを渡すことによって、キーのパスを、キーのパス**と呼ばれる** **REG \ _MULTI \ _SZ**値に渡すことができ `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-341">Pass-through locations are global to the machine (not package specific) and can be configured by adding the path to the key, which should be treated as pass-through to the **REG\_MULTI\_SZ** value called **PassThroughPaths** of the key `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry`.</span></span> <span data-ttu-id="09441-342">この複数文字列値 (およびその子) の下に表示されるすべてのキーは、パススルーとして扱われます。</span><span class="sxs-lookup"><span data-stu-id="09441-342">Any key that appears under this multi-string value (and their children) will be treated as pass-through.</span></span>

<span data-ttu-id="09441-343">既定では、次の場所がパススルー場所として構成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-343">The following locations are configured as pass-through locations by default:</span></span>

-   <span data-ttu-id="09441-344">HKEY \ _CURRENT \ _USER \ ソフトウェア \ クラス \\ ローカル Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="09441-344">HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="09441-345">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \ クラス \\ ローカル Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="09441-345">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="09441-346">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span><span class="sxs-lookup"><span data-stu-id="09441-346">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span></span>

-   <span data-ttu-id="09441-347">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span><span class="sxs-lookup"><span data-stu-id="09441-347">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span></span>

-   <span data-ttu-id="09441-348">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span><span class="sxs-lookup"><span data-stu-id="09441-348">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span></span>

-   <span data-ttu-id="09441-349">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet の設定</span><span class="sxs-lookup"><span data-stu-id="09441-349">HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>

-   <span data-ttu-id="09441-350">HKEY \ _LOCAL \ _MACHINE \ ソフトウェア \\ Windows nt¥のバージョン \\ Perflib</span><span class="sxs-lookup"><span data-stu-id="09441-350">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib</span></span>

-   <span data-ttu-id="09441-351">HKEY \ _LOCAL \ _MACHINE \\ ソフトウェア \\ ポリシー</span><span class="sxs-lookup"><span data-stu-id="09441-351">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies</span></span>

-   <span data-ttu-id="09441-352">HKEY \ _CURRENT \ _USER \\ ソフトウェア \\ ポリシー</span><span class="sxs-lookup"><span data-stu-id="09441-352">HKEY\_CURRENT\_USER\\SOFTWARE\\Policies</span></span>

<span data-ttu-id="09441-353">パススルーキーの目的は、仮想アプリケーションが VReg で、操作や統合を成功させるために非仮想アプリケーションに必要なレジストリデータを書き込むことがないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="09441-353">The purpose of Pass-through keys is to ensure that a virtual application does not write registry data in the VReg that is required for non-virtual applications for successful operation or integration.</span></span> <span data-ttu-id="09441-354">[ポリシー] キーを使うと、管理者によって設定されたグループポリシーベースの設定が使用されるようになり、パッケージ設定ごとには使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="09441-354">The Policies key ensures that Group Policy based settings set by the administrator are utilized and not per package settings.</span></span> <span data-ttu-id="09441-355">AppModel キーは、Windows モダン UI ベースのアプリケーションと統合するために必要です。</span><span class="sxs-lookup"><span data-stu-id="09441-355">The AppModel key is required for integration with Windows Modern UI based applications.</span></span> <span data-ttu-id="09441-356">既定のパススルーキーを変更しないことをお勧めしますが、場合によっては、アプリケーションの動作に基づいて追加のパススルーキーを追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-356">It is recommend that administers do not modify any of the default pass-through keys, but in some instances, based on application behavior may require adding additional pass-through keys.</span></span>

## <a href="" id="bkmk-pkg-store-behavior"></a><span data-ttu-id="09441-357">App-v パッケージストアの動作</span><span class="sxs-lookup"><span data-stu-id="09441-357">App-V package store behavior</span></span>


<span data-ttu-id="09441-358">App-v 5 は、パッケージストアを管理します。これは、appv ファイルから展開されたアセットファイルが保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="09441-358">App-V 5 manages the Package Store, which is the location where the expanded asset files from the appv file are stored.</span></span> <span data-ttu-id="09441-359">既定では、この場所は、\ programdata% ¥¥ V に保存され、記憶域の制限は空きディスク領域に限定されます。</span><span class="sxs-lookup"><span data-stu-id="09441-359">By default, this location is stored at %ProgramData%\\App-V, and is limited in terms of storage capabilities only by free disk space.</span></span> <span data-ttu-id="09441-360">パッケージストアは、前のセクションで説明したパッケージとバージョンの Guid によって整理されます。</span><span class="sxs-lookup"><span data-stu-id="09441-360">The package store is organized by the GUIDs for the package and version as mentioned in the previous section.</span></span>

### <span data-ttu-id="09441-361">パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="09441-361">Add packages</span></span>

<span data-ttu-id="09441-362">App-v パッケージは、App-v クライアントのコンピューターに加えて、ステージングされます。</span><span class="sxs-lookup"><span data-stu-id="09441-362">App-V Packages are staged upon addition to the computer with the App-V Client.</span></span> <span data-ttu-id="09441-363">App-v クライアントでは、オンデマンドステージングが提供されます。</span><span class="sxs-lookup"><span data-stu-id="09441-363">The App-V Client provides on-demand staging.</span></span> <span data-ttu-id="09441-364">公開または手動による AppVClientPackage の場合、データ構造はパッケージストア (c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}) に組み込まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-364">During publishing or a manual Add-AppVClientPackage, the data structure is built in the package store (c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}).</span></span> <span data-ttu-id="09441-365">StreamMap.xml で定義されている発行ブロックで識別されたパッケージファイルがシステムに追加され、最上位のフォルダーと子ファイルがステージングされて、起動時に適切なアプリケーションアセットが存在することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="09441-365">The package files identified in the publishing block defined in the StreamMap.xml are added to the system and the top level folders and child files staged to ensure proper application assets exist at launch.</span></span>

### <span data-ttu-id="09441-366">パッケージのマウント</span><span class="sxs-lookup"><span data-stu-id="09441-366">Mounting packages</span></span>

<span data-ttu-id="09441-367">パッケージは、PowerShell を使って明示的に読み込むことも、 `Mount-AppVClientPackage` または**APP-V クライアント UI**を使ってパッケージをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="09441-367">Packages can be explicitly loaded using the PowerShell `Mount-AppVClientPackage` or by using the **App-V Client UI** to download a package.</span></span> <span data-ttu-id="09441-368">この操作では、パッケージ全体がパッケージストアに完全に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-368">This operation completely loads the entire package into the package store.</span></span>

### <span data-ttu-id="09441-369">ストリーミングパッケージ</span><span class="sxs-lookup"><span data-stu-id="09441-369">Streaming packages</span></span>

<span data-ttu-id="09441-370">App-v クライアントを構成して、ストリーミングの既定の動作を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-370">The App-V Client can be configured to change the default behavior of streaming.</span></span> <span data-ttu-id="09441-371">すべてのストリーミングポリシーは、次のレジストリキーに保存され `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-371">All streaming policies are stored under the following registry key: `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming`.</span></span> <span data-ttu-id="09441-372">ポリシーは、PowerShell コマンドレットを使って設定し `Set-AppvClientConfiguration` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-372">Policies are set using the PowerShell cmdlet `Set-AppvClientConfiguration`.</span></span> <span data-ttu-id="09441-373">ストリーミングには、次のポリシーが適用されます。</span><span class="sxs-lookup"><span data-stu-id="09441-373">The following policies apply to Streaming:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-374">ポリシー</span><span class="sxs-lookup"><span data-stu-id="09441-374">Policy</span></span></th>
<th align="left"><span data-ttu-id="09441-375">説明</span><span class="sxs-lookup"><span data-stu-id="09441-375">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-376">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="09441-376">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-377">Windows 8 以降では、3G および携帯電話ネットワーク上でのストリーミングが可能になります。</span><span class="sxs-lookup"><span data-stu-id="09441-377">On Windows 8 and later, it allows streaming over 3G and cellular networks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-378">ロード</span><span class="sxs-lookup"><span data-stu-id="09441-378">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-379">バックグラウンド読み込み設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="09441-379">Specifies the Background Load setting:</span></span></p>
<p><strong><span data-ttu-id="09441-380">0 </strong> - 無効</span><span class="sxs-lookup"><span data-stu-id="09441-380">0</strong> - Disabled</span></span></p>
<p><strong><span data-ttu-id="09441-381">1 </strong> -以前に使用したパッケージのみ</span><span class="sxs-lookup"><span data-stu-id="09441-381">1</strong> – Previously Used Packages only</span></span></p>
<p><strong><span data-ttu-id="09441-382">2 </strong> –すべてのパッケージ</span><span class="sxs-lookup"><span data-stu-id="09441-382">2</strong> – All Packages</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-383">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="09441-383">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-384">ローカルコンピューターのパッケージストアのルートフォルダー</span><span class="sxs-lookup"><span data-stu-id="09441-384">The root folder for the package store in the local machine</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-385">パッケージパッケージ</span><span class="sxs-lookup"><span data-stu-id="09441-385">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-386">パッケージをストリーミングする必要があるルートの上書き</span><span class="sxs-lookup"><span data-stu-id="09441-386">The root override where packages should be streamed from</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-387">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="09441-387">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-388">VDI シナリオで共有コンテンツストアを使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="09441-388">Enables the use of Shared Content Store for VDI scenarios</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="09441-389">これらの設定は、クライアントに対する App-v パッケージアセットの動作に影響します。</span><span class="sxs-lookup"><span data-stu-id="09441-389">These settings affect the behavior of streaming App-V package assets to the client.</span></span> <span data-ttu-id="09441-390">既定では、最初の発行とプライマリ機能ブロックをダウンロードした後に必要なアセットのみがアプリによってダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-390">By default, App-V only downloads the assets required after downloading the initial publishing and primary feature blocks.</span></span> <span data-ttu-id="09441-391">ストリーミングパッケージについては、次の3つの具体的な動作について説明する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-391">There are three specific behaviors around streaming packages that must be explained:</span></span>

-   <span data-ttu-id="09441-392">バックグラウンドストリーミング</span><span class="sxs-lookup"><span data-stu-id="09441-392">Background Streaming</span></span>

-   <span data-ttu-id="09441-393">最適化されたストリーミング</span><span class="sxs-lookup"><span data-stu-id="09441-393">Optimized Streaming</span></span>

-   <span data-ttu-id="09441-394">ストリームフォールト</span><span class="sxs-lookup"><span data-stu-id="09441-394">Stream Faults</span></span>

### <span data-ttu-id="09441-395">バックグラウンドストリーミング</span><span class="sxs-lookup"><span data-stu-id="09441-395">Background streaming</span></span>

<span data-ttu-id="09441-396">PowerShell コマンドレットを使用して、 `Get-AppvClientConfiguration` バックグラウンドストリーミングの現在のモードを確認できます。これには、AppvClientConfiguration または registry (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming key) を使って、自動読み込み設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="09441-396">The PowerShell cmdlet `Get-AppvClientConfiguration` can be used to determine the current mode for background streaming with the AutoLoad setting and modified with the cmdlet Set-AppvClientConfiguration or from the registry (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming key).</span></span> <span data-ttu-id="09441-397">バックグラウンドストリーミングは既定の設定で、以前に使用したパッケージをダウンロードするための自動ロード設定が設定されています。</span><span class="sxs-lookup"><span data-stu-id="09441-397">Background streaming is a default setting where the Autoload setting is set to download previously used packages.</span></span> <span data-ttu-id="09441-398">既定の設定 (値 = 1) に基づく動作は、アプリケーションが起動された後にバックグラウンドで App-v データブロックをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="09441-398">The behavior based on default setting (value=1) downloads App-V data blocks in the background after the application has been launched.</span></span> <span data-ttu-id="09441-399">この設定は、起動されているかどうかにかかわらず、すべてのパッケージ (値 = 0) またはすべてのパッケージ (value = 2) で無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-399">This setting can be disabled all together (value=0) or enabled for all packages (value=2), whether they have been launched.</span></span>

### <span data-ttu-id="09441-400">最適化されたストリーミング</span><span class="sxs-lookup"><span data-stu-id="09441-400">Optimized streaming</span></span>

<span data-ttu-id="09441-401">アプリ-V パッケージは、シーケンス中にプライマリ機能ブロックを使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="09441-401">App-V packages can be configured with a primary feature block during sequencing.</span></span> <span data-ttu-id="09441-402">この設定により、シーケンスエンジニアは、特定のアプリケーションやアプリケーションの起動ファイルを監視し、パッケージ内のアプリケーションの最初の起動時にストリーミングのために、ストリーミング用にデータのブロックをマークすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-402">This setting allows the sequencing engineer to monitor launch files for a specific application, or applications, and mark the blocks of data in the App-V package for streaming at first launch of any application in the package.</span></span>

### <span data-ttu-id="09441-403">ストリームフォールト</span><span class="sxs-lookup"><span data-stu-id="09441-403">Stream faults</span></span>

<span data-ttu-id="09441-404">発行データとプライマリ機能ブロックの最初のストリームの後に、追加のファイルの要求によってストリームフォールトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-404">After the initial stream of any publishing data and the primary feature block, requests for additional files perform stream faults.</span></span> <span data-ttu-id="09441-405">これらのデータのブロックは、必要に応じてパッケージストアにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-405">These blocks of data are downloaded to the package store on an as-needed basis.</span></span> <span data-ttu-id="09441-406">これにより、ユーザーはパッケージのわずかな部分のみをダウンロードできます。通常は、パッケージを起動して通常のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-406">This allows a user to download only a small part of the package, typically enough to launch the package and run normal tasks.</span></span> <span data-ttu-id="09441-407">他のすべてのブロックは、ユーザーが現在パッケージストアに含まれていないデータを必要とする操作を開始したときにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-407">All other blocks are downloaded when a user initiates an operation that requires data not currently in the package store.</span></span>

<span data-ttu-id="09441-408">App-v パッケージのストリーミングアクセスの詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=392770> 。</span><span class="sxs-lookup"><span data-stu-id="09441-408">For more information on App-V Package streaming visit: <https://go.microsoft.com/fwlink/?LinkId=392770>.</span></span>

<span data-ttu-id="09441-409">ストリーミング最適化のシーケンスは、次のページで参照でき <https://go.microsoft.com/fwlink/?LinkId=392771> ます。</span><span class="sxs-lookup"><span data-stu-id="09441-409">Sequencing for streaming optimization is available at: <https://go.microsoft.com/fwlink/?LinkId=392771>.</span></span>

### <span data-ttu-id="09441-410">パッケージのアップグレード</span><span class="sxs-lookup"><span data-stu-id="09441-410">Package upgrades</span></span>

<span data-ttu-id="09441-411">App-v パッケージを適用するには、アプリケーションのライフサイクル全体を通じて更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-411">App-V Packages require updating throughout the lifecycle of the application.</span></span> <span data-ttu-id="09441-412">App-v パッケージのアップグレードは、パッケージの公開操作と似ていますが、各バージョンは独自の "パッケージ" という場所で作成され `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` ます。</span><span class="sxs-lookup"><span data-stu-id="09441-412">App-V Package upgrades are similar to the package publish operation, as each version will be created in its own PackageRoot location: `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}`.</span></span> <span data-ttu-id="09441-413">アップグレード操作は、同じパッケージの他のバージョンから、同一およびストリーム形式のファイルへのハードリンクを作成することによって最適化されています。</span><span class="sxs-lookup"><span data-stu-id="09441-413">The upgrade operation is optimized by creating hard links to identical- and streamed-files from other versions of the same package.</span></span>

### <span data-ttu-id="09441-414">パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="09441-414">Package removal</span></span>

<span data-ttu-id="09441-415">パッケージが削除されるときの App-v クライアントの動作は、削除に使用されるメソッドによって異なります。</span><span class="sxs-lookup"><span data-stu-id="09441-415">The behavior of the App-V Client when packages are removed depends on the method used for removal.</span></span> <span data-ttu-id="09441-416">アプリケーションの発行を取り下げるために、App-v の完全なインフラストラクチャを使うと、ユーザーカタログファイル (グローバルに公開されたアプリケーションのコンピューターカタログ) は削除されますが、パッケージストアの場所と COW の場所は保持されます。</span><span class="sxs-lookup"><span data-stu-id="09441-416">Using an App-V full infrastructure to unpublish the application, the user catalog files (machine catalog for globally published applications) are removed, but retains the package store location and COW locations.</span></span> <span data-ttu-id="09441-417">PowerShell コマンドレットを `Remove-AppVClientPackge` 使用して App-v パッケージを削除すると、パッケージストアの場所がクリーンアップされます。</span><span class="sxs-lookup"><span data-stu-id="09441-417">When the PowerShell cmdlet `Remove-AppVClientPackge` is used to remove an App-V Package, the package store location is cleaned.</span></span> <span data-ttu-id="09441-418">管理サーバーからの App-v パッケージの未発行は、削除操作を実行しないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="09441-418">Remember that unpublishing an App-V Package from the Management Server does not perform a Remove operation.</span></span> <span data-ttu-id="09441-419">どちらの操作でも、パッケージストアパッケージファイルは削除されません。</span><span class="sxs-lookup"><span data-stu-id="09441-419">Neither operation will remove the Package Store package files.</span></span>

## <a href="" id="bkmk-roaming-reg-data"></a><span data-ttu-id="09441-420">ローミングのレジストリとデータ</span><span class="sxs-lookup"><span data-stu-id="09441-420">Roaming registry and data</span></span>


<span data-ttu-id="09441-421">アプリ-V 5 は、使用されているアプリケーションの書き込み方法に応じて、ローミング時にほぼネイティブなエクスペリエンスを提供できます。</span><span class="sxs-lookup"><span data-stu-id="09441-421">App-V 5 is able to provide a near-native experience when roaming, depending on how the application being used is written.</span></span> <span data-ttu-id="09441-422">既定では、オペレーティングシステムのローミング構成に基づいて、ローミングの場所に格納されている App-v ローミングの AppData が指定されています。</span><span class="sxs-lookup"><span data-stu-id="09441-422">By default, App-V roams AppData that is stored in the roaming location, based on the roaming configuration of the operating system.</span></span> <span data-ttu-id="09441-423">ファイルベースのデータを格納するための他の場所は、ローミングされていない場所にあるため、コンピューター間ではローミングされません。</span><span class="sxs-lookup"><span data-stu-id="09441-423">Other locations for storage of file-based data do not roam from computer to computer, since they are in locations that are not roamed.</span></span>

### <a href="" id="bkmk-clt-inter-roam-reqs"></a><span data-ttu-id="09441-424">ローミング要件とユーザーカタログデータストレージ</span><span class="sxs-lookup"><span data-stu-id="09441-424">Roaming requirements and user catalog data storage</span></span>

<span data-ttu-id="09441-425">App-v は、次の形式のデータを保存します。これは、ユーザーのカタログの状態を表します。</span><span class="sxs-lookup"><span data-stu-id="09441-425">App-V stores data, which represents the state of the user’s catalog, in the form of:</span></span>

-   <span data-ttu-id="09441-426">%Appdata%\\Microsoft\\AppV\\Client\\Catalog のファイル</span><span class="sxs-lookup"><span data-stu-id="09441-426">Files under %appdata%\\Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="09441-427">レジストリ設定</span><span class="sxs-lookup"><span data-stu-id="09441-427">Registry settings under</span></span> `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

<span data-ttu-id="09441-428">これらのファイルとレジストリ設定は、ユーザーのカタログを表しているため、どちらもローミングするか、または特定のユーザーに対してローミングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-428">Together, these files and registry settings represent the user’s catalog, so either both must be roamed, or neither must be roamed for a given user.</span></span> <span data-ttu-id="09441-429">App-v はローミング% AppData% をサポートしていませんが、ユーザーのプロファイル (レジストリ) をローミングすることはできません。またその逆もできません。</span><span class="sxs-lookup"><span data-stu-id="09441-429">App-V does not support roaming %AppData%, but not roaming the user’s profile (registry), or vice versa.</span></span>

<span data-ttu-id="09441-430">**注** **AppvClientPackage**コマンドレットでは、ユーザーのアプリの状態が [不足] または [ `HKEY_CURRENT_USER` % appdata%] のデータと一致しない場合、パッケージの発行状態は修復されません。</span><span class="sxs-lookup"><span data-stu-id="09441-430">**Note** The **Repair-AppvClientPackage** cmdlet does not repair the publishing state of packages, where the user’s App-V state under `HKEY_CURRENT_USER` is missing or mismatched with the data in %appdata%.</span></span>

 

### <span data-ttu-id="09441-431">レジストリベースのデータ</span><span class="sxs-lookup"><span data-stu-id="09441-431">Registry-based data</span></span>

<span data-ttu-id="09441-432">App-v registry ローミングは、次の表のように2つのシナリオに分類されます。</span><span class="sxs-lookup"><span data-stu-id="09441-432">App-V registry roaming falls into two scenarios, as shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-433">シナリオ</span><span class="sxs-lookup"><span data-stu-id="09441-433">Scenario</span></span></th>
<th align="left"><span data-ttu-id="09441-434">説明</span><span class="sxs-lookup"><span data-stu-id="09441-434">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-435">標準ユーザーとして実行されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="09441-435">Applications that are run as standard users</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-436">標準ユーザーが App-v アプリケーションを起動すると、アプリケーションの HKLM と HKCU の両方が、コンピューター上の HKCU ハイブに保存されます。</span><span class="sxs-lookup"><span data-stu-id="09441-436">When a standard user launches an App-V application, both HKLM and HKCU for App-V applications are stored in the HKCU hive on the machine.</span></span> <span data-ttu-id="09441-437">これは、2つの異なるパスとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="09441-437">This presents as two distinct paths:</span></span></p>
<ul>
<li><p><span data-ttu-id="09441-438">HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="09441-438">HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="09441-439">HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="09441-439">HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</span></span></p></li>
</ul>
<p><span data-ttu-id="09441-440">この場所は、オペレーティングシステムの設定に基づいてローミングが有効になっています。</span><span class="sxs-lookup"><span data-stu-id="09441-440">The locations are enabled for roaming based on the operating system settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-441">昇格を使用して実行されるアプリケーション</span><span class="sxs-lookup"><span data-stu-id="09441-441">Applications that are run with elevation</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-442">昇格を使ってアプリケーションを起動すると、次のようになります。</span><span class="sxs-lookup"><span data-stu-id="09441-442">When an application is launched with elevation:</span></span></p>
<ul>
<li><p><span data-ttu-id="09441-443">HKLM データはローカルコンピューターの HKLM ハイブに保存されている</span><span class="sxs-lookup"><span data-stu-id="09441-443">HKLM data is stored in the HKLM hive on the local computer</span></span></p></li>
<li><p><span data-ttu-id="09441-444">HKCU データは、ユーザーのレジストリの場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-444">HKCU data is stored in the User Registry location</span></span></p></li>
</ul>
<p><span data-ttu-id="09441-445">このシナリオでは、これらの設定は通常のオペレーティングシステムローミング構成ではローミングされず、作成したレジストリキーと値は次の場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-445">In this scenario, these settings are not roamed with normal operating system roaming configurations, and the resulting registry keys and values are stored in the following location:</span></span></p>
<ul>
<li><p><span data-ttu-id="09441-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} {UserSID} \ REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="09441-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="09441-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="09441-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="09441-448">App-v とフォルダーのリダイレクト</span><span class="sxs-lookup"><span data-stu-id="09441-448">App-V and folder redirection</span></span>

<span data-ttu-id="09441-449">App-v 5.1 は、ローミング AppData フォルダーのフォルダーリダイレクション (% AppData%) をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="09441-449">App-V 5.1 supports folder redirection of the roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="09441-450">仮想環境が開始されると、ユーザーのローミングの AppData ディレクトリからローミングの AppData の状態がローカルキャッシュにコピーされます。</span><span class="sxs-lookup"><span data-stu-id="09441-450">When the virtual environment is started, the roaming AppData state from the user’s roaming AppData directory is copied to the local cache.</span></span> <span data-ttu-id="09441-451">逆に、仮想環境がシャットダウンされると、特定のユーザーのローミング AppData に関連付けられているローカルキャッシュは、そのユーザーのローミング用の AppData ディレクトリの実際の場所に転送されます。</span><span class="sxs-lookup"><span data-stu-id="09441-451">Conversely, when the virtual environment is shut down, the local cache that is associated with a specific user’s roaming AppData is transferred to the actual location of that user’s roaming AppData directory.</span></span>

<span data-ttu-id="09441-452">一般的なパッケージには、appdata¥ Local と AppData\\Roaming. の両方の設定のために、ユーザーのバッキングストアでマップされた複数の場所があります。</span><span class="sxs-lookup"><span data-stu-id="09441-452">A typical package has several locations mapped in the user’s backing store for settings in both AppData\\Local and AppData\\Roaming.</span></span> <span data-ttu-id="09441-453">これらの場所は、ユーザーのプロファイル内のユーザーごとに保存され、パッケージの VFS ディレクトリに加えられた変更を保存し、既定のパッケージの VFS を保護するために使用される、書き込み場所のコピーです。</span><span class="sxs-lookup"><span data-stu-id="09441-453">These locations are the Copy on Write locations that are stored per user in the user’s profile, and that are used to store changes made to the package VFS directories and to protect the default package VFS.</span></span>

<span data-ttu-id="09441-454">次の表は、フォルダリダイレクションが実装されていない場合のローカルとローミングの場所を示しています。</span><span class="sxs-lookup"><span data-stu-id="09441-454">The following table shows local and roaming locations, when folder redirection has not been implemented.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-455">パッケージ内の VFS ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="09441-455">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="09441-456">バッキングストアのマップされた場所</span><span class="sxs-lookup"><span data-stu-id="09441-456">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-457">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="09441-457">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-458">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ programfilesx86</span><span class="sxs-lookup"><span data-stu-id="09441-458">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-459">SystemX86</span><span class="sxs-lookup"><span data-stu-id="09441-459">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-460">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ systemx86</span><span class="sxs-lookup"><span data-stu-id="09441-460">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-461">Windows</span><span class="sxs-lookup"><span data-stu-id="09441-461">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-462">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="09441-462">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-463">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="09441-463">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-464">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="09441-464">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-465">AppData</span><span class="sxs-lookup"><span data-stu-id="09441-465">AppData</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-466">C:\users\jsmith\AppData の &lt; 強い &gt; ローミング </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ AppData</span><span class="sxs-lookup"><span data-stu-id="09441-466">C:\users\jsmith\AppData&lt;strong&gt;Roaming</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="09441-467">次の表では、フォルダリダイレクションが% AppData% に実装されていて、場所がリダイレクトされている場合 (通常はネットワーク上の場所) を示しています。</span><span class="sxs-lookup"><span data-stu-id="09441-467">The following table shows local and roaming locations, when folder redirection has been implemented for %AppData%, and the location has been redirected (typically to a network location).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-468">パッケージ内の VFS ディレクトリ</span><span class="sxs-lookup"><span data-stu-id="09441-468">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="09441-469">バッキングストアのマップされた場所</span><span class="sxs-lookup"><span data-stu-id="09441-469">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-470">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="09441-470">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-471">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ programfilesx86</span><span class="sxs-lookup"><span data-stu-id="09441-471">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-472">SystemX86</span><span class="sxs-lookup"><span data-stu-id="09441-472">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-473">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ systemx86</span><span class="sxs-lookup"><span data-stu-id="09441-473">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-474">Windows</span><span class="sxs-lookup"><span data-stu-id="09441-474">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-475">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="09441-475">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-476">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="09441-476">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-477">C:\users\jsmith\AppData の &lt; 強い &gt; 地元 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="09441-477">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-478">AppData</span><span class="sxs-lookup"><span data-stu-id="09441-478">AppData</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="09441-479">\ サーバ </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ AppData</span><span class="sxs-lookup"><span data-stu-id="09441-479">\Fileserver</strong>\users\jsmith\roaming\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="09441-480">現在の App-v クライアントの VFS ドライバーは、ネットワーク上の場所に書き込むことができないため、App-v クライアントは、フォルダーリダイレクションの存在を検出し、発行時と仮想環境の開始時にローカルドライブ上のデータをコピーします。</span><span class="sxs-lookup"><span data-stu-id="09441-480">The current App-V Client VFS driver cannot write to network locations, so the App-V Client detects the presence of folder redirection and copies the data on the local drive during publishing and when the virtual environment starts.</span></span> <span data-ttu-id="09441-481">ユーザーが app-v アプリケーションを閉じた後、App-v クライアントが仮想環境を閉じると、VFS AppData のローカルストレージがネットワークにコピーされて、他のコンピューターへのローミングが有効になり、プロセスが繰り返されます。</span><span class="sxs-lookup"><span data-stu-id="09441-481">After the user closes the App-V application and the App-V Client closes the virtual environment, the local storage of the VFS AppData is copied back to the network, enabling roaming to additional machines, where the process will be repeated.</span></span> <span data-ttu-id="09441-482">プロセスの詳細な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09441-482">The detailed steps of the processes are:</span></span>

1.  <span data-ttu-id="09441-483">パブリッシングまたは仮想環境の起動時に、App-v クライアントによって AppData ディレクトリの場所が検出されます。</span><span class="sxs-lookup"><span data-stu-id="09441-483">During publishing or virtual environment startup, the App-V Client detects the location of the AppData directory.</span></span>

2.  <span data-ttu-id="09441-484">ローミングの AppData パスが local または ino appdata¥ローミングの場所がマッピングされている場合は、何も起こりません。</span><span class="sxs-lookup"><span data-stu-id="09441-484">If the roaming AppData path is local or ino AppData\\Roaming location is mapped, nothing happens.</span></span>

3.  <span data-ttu-id="09441-485">ローミングの AppData パスがローカルではない場合、VFS AppData ディレクトリはローカルの AppData ディレクトリにマップされます。</span><span class="sxs-lookup"><span data-stu-id="09441-485">If the roaming AppData path is not local, the VFS AppData directory is mapped to the local AppData directory.</span></span>

<span data-ttu-id="09441-486">このプロセスによって、App-v クライアントの VFS ドライバーでサポートされていないローカル以外の% AppData% の問題が解決されます。</span><span class="sxs-lookup"><span data-stu-id="09441-486">This process solves the problem of a non-local %AppData% that is not supported by the App-V Client VFS driver.</span></span> <span data-ttu-id="09441-487">ただし、この新しい場所に保存されているデータは、フォルダーリダイレクションではローミングされません。</span><span class="sxs-lookup"><span data-stu-id="09441-487">However, the data stored in this new location is not roamed with folder redirection.</span></span> <span data-ttu-id="09441-488">アプリケーションの実行中のすべての変更は、local AppData の位置情報に対して行われ、リダイレクトされた場所にコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-488">All changes during the running of the application happen to the local AppData location and must be copied to the redirected location.</span></span> <span data-ttu-id="09441-489">このプロセスの詳細な手順は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09441-489">The detailed steps of this process are:</span></span>

1.  <span data-ttu-id="09441-490">App-v アプリケーションがシャットダウンされ、仮想環境がシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="09441-490">App-V application is shut down, which shuts down the virtual environment.</span></span>

2.  <span data-ttu-id="09441-491">ローミング用の AppData の場所のローカルキャッシュは圧縮され、ZIP ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="09441-491">The local cache of the roaming AppData location is compressed and stored in a ZIP file.</span></span>

3.  <span data-ttu-id="09441-492">ZIP パッケージ処理の最後のタイムスタンプを使って、ファイルに名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="09441-492">A timestamp at the end of the ZIP packaging process is used to name the file.</span></span>

4.  <span data-ttu-id="09441-493">タイムスタンプは、 &lt; &gt; 最後の既知の AppData のタイムスタンプとして、HKEY \ _CURRENT \ _USER \\Software\\microsoft\\appv\\client\\packages\\ GUID \\AppDataTime のレジストリに記録されます。</span><span class="sxs-lookup"><span data-stu-id="09441-493">The timestamp is recorded in the registry: HKEY\_CURRENT\_USER\\Software\\Microsoft\\AppV\\Client\\Packages\\&lt;GUID&gt;\\AppDataTime as the last known AppData timestamp.</span></span>

5.  <span data-ttu-id="09441-494">フォルダリダイレクションプロセスが呼び出されて、ローミングの AppData ディレクトリにアップロードされた ZIP ファイルが評価され、開始されます。</span><span class="sxs-lookup"><span data-stu-id="09441-494">The folder redirection process is called to evaluate and initiate the ZIP file uploaded to the roaming AppData directory.</span></span>

<span data-ttu-id="09441-495">このタイムスタンプは、競合が発生した場合に "最後のライター wins" シナリオを決定するために使用され、アプリが公開されたとき、または仮想環境が開始されたときにデータのダウンロードを最適化するために使われます。</span><span class="sxs-lookup"><span data-stu-id="09441-495">The timestamp is used to determine a “last writer wins” scenario if there is a conflict and is used to optimize the download of the data when the App-V application is published or the virtual environment is started.</span></span> <span data-ttu-id="09441-496">フォルダーリダイレクションは、サポートポリシーによってカバーされている他のクライアントからデータを利用できるようにします。また、appdata¥ローミングデータをクライアント上の local AppData の場所に保存するプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="09441-496">Folder redirection will make the data available from any other clients covered by the supporting policy and will initiate the process of storing the AppData\\Roaming data to the local AppData location on the client.</span></span> <span data-ttu-id="09441-497">詳細なプロセスは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09441-497">The detailed processes are:</span></span>

1.  <span data-ttu-id="09441-498">ユーザーは、アプリケーションを起動して仮想環境を開始します。</span><span class="sxs-lookup"><span data-stu-id="09441-498">The user starts the virtual environment by starting an application.</span></span>

2.  <span data-ttu-id="09441-499">アプリケーションの仮想環境では、最新のタイムスタンプ付き ZIP ファイルが存在する場合は、そのファイルがチェックされます。</span><span class="sxs-lookup"><span data-stu-id="09441-499">The application’s virtual environment checks for the most recent time stamped ZIP file, if present.</span></span>

3.  <span data-ttu-id="09441-500">レジストリのチェックボックスがオンになっている場合は、最後にアップロードされた既知のタイムスタンプを確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-500">The registry is checked for the last known uploaded timestamp, if present.</span></span>

4.  <span data-ttu-id="09441-501">ローカルの最後のアップロードのタイムスタンプが ZIP ファイルのタイムスタンプ以上でなければ、最新の ZIP ファイルがダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-501">The most recent ZIP file is downloaded unless the local last known upload timestamp is greater than or equal to the timestamp from the ZIP file.</span></span>

5.  <span data-ttu-id="09441-502">ローカルの最終既知のアップロードのタイムスタンプが、ローミングの AppData の最新の ZIP ファイルよりも前にある場合は、ZIP ファイルはユーザーのプロファイルのローカルの temp ディレクトリに抽出されます。</span><span class="sxs-lookup"><span data-stu-id="09441-502">If the local last known upload timestamp is earlier than that of the most recent ZIP file in the roaming AppData location, the ZIP file is extracted to the local temp directory in the user’s profile.</span></span>

6.  <span data-ttu-id="09441-503">ZIP ファイルが正常に抽出されると、ローミングの AppData ディレクトリのローカルキャッシュが名前が変更され、新しいデータが所定の位置に移動されます。</span><span class="sxs-lookup"><span data-stu-id="09441-503">After the ZIP file is successfully extracted, the local cache of the roaming AppData directory is renamed and the new data is moved into place.</span></span>

7.  <span data-ttu-id="09441-504">名前を変更したディレクトリが削除され、最近保存されたローミングの AppData データでアプリケーションが開きます。</span><span class="sxs-lookup"><span data-stu-id="09441-504">The renamed directory is deleted and the application opens with the most recently saved roaming AppData data.</span></span>

<span data-ttu-id="09441-505">これにより、appdata¥ローミング場所に存在するアプリケーション設定の移動が正常に完了します。</span><span class="sxs-lookup"><span data-stu-id="09441-505">This completes the successful roaming of application settings that are present in AppData\\Roaming locations.</span></span> <span data-ttu-id="09441-506">対処する必要があるその他の条件は、パッケージの修復操作だけです。</span><span class="sxs-lookup"><span data-stu-id="09441-506">The only other condition that must be addressed is a package repair operation.</span></span> <span data-ttu-id="09441-507">プロセスの詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09441-507">The details of the process are:</span></span>

1.  <span data-ttu-id="09441-508">修復中に、ユーザーのローミング用の AppData ディレクトリへのパスがローカルでないかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="09441-508">During repair, detect if the path to the user’s roaming AppData directory is not local.</span></span>

2.  <span data-ttu-id="09441-509">ローカル以外のローミングパスのターゲットをマップすると、期待されるローミングとローカル AppData の場所が再作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-509">Map the non-local roaming AppData path targets are recreated the expected roaming and local AppData locations.</span></span>

3.  <span data-ttu-id="09441-510">レジストリに保存されているタイムスタンプを削除します (存在する場合)。</span><span class="sxs-lookup"><span data-stu-id="09441-510">Delete the timestamp stored in the registry, if present.</span></span>

<span data-ttu-id="09441-511">このプロセスでは、AppData のローカルとネットワークの場所の両方を再作成し、タイムスタンプのレジストリレコードを削除します。</span><span class="sxs-lookup"><span data-stu-id="09441-511">This process will re-create both the local and network locations for AppData and remove the registry record of the timestamp.</span></span>

## <a href="" id="bkmk-clt-app-lifecycle"></a><span data-ttu-id="09441-512">App-v クライアントアプリケーションのライフサイクル管理</span><span class="sxs-lookup"><span data-stu-id="09441-512">App-V client application lifecycle management</span></span>


<span data-ttu-id="09441-513">アプリが順番に実行された場合、アプリは、アプリの順序が付けられた後、アプリの管理と発行サーバーを介して、ユーザーまたはコンピューターに管理され、公開されます。</span><span class="sxs-lookup"><span data-stu-id="09441-513">In an App-V Full Infrastructure, after applications are sequenced they are managed and published to users or computers via the App-V Management and Publishing servers.</span></span> <span data-ttu-id="09441-514">このセクションでは、共通の App-v アプリケーションのライフサイクル操作 (追加、公開、起動、アップグレード、および削除) の際に発生する操作と、App-v クライアントの視点から変更および変更されたファイルとレジストリの場所について詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-514">This section details the operations that occur during the common App-V application lifecycle operations (Add, publishing, launch, upgrade, and removal) and the file and registry locations that are changed and modified from the App-V Client perspective.</span></span> <span data-ttu-id="09441-515">App-v クライアント操作は、App-v クライアントを実行しているコンピューターで開始される一連の PowerShell コマンドとして実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-515">The App-V Client operations are performed as a series of PowerShell commands initiated on the computer running the App-V Client.</span></span>

<span data-ttu-id="09441-516">このドキュメントでは、App-v の完全なインフラストラクチャソリューションに焦点を当てています。</span><span class="sxs-lookup"><span data-stu-id="09441-516">This document focuses on App-V Full Infrastructure solutions.</span></span> <span data-ttu-id="09441-517">Configuration Manager 2012 との App-v との統合の詳細については、「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=392773> 。</span><span class="sxs-lookup"><span data-stu-id="09441-517">For specific information on App-V Integration with Configuration Manager 2012 visit: <https://go.microsoft.com/fwlink/?LinkId=392773>.</span></span>

<span data-ttu-id="09441-518">App-v アプリケーションのライフサイクルタスクは、ユーザーのログイン (既定)、コンピューターの起動時、またはバックグラウンドの時間指定操作でトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="09441-518">The App-V application lifecycle tasks are triggered at user login (default), machine startup, or as background timed operations.</span></span> <span data-ttu-id="09441-519">公開サーバー、更新間隔、パッケージスクリプトの有効化などの、App-v クライアント操作の設定は、クライアントのセットアップまたは PowerShell コマンドを使ってセットアップするときに構成します。</span><span class="sxs-lookup"><span data-stu-id="09441-519">The settings for the App-V Client operations, including Publishing Servers, refresh intervals, package script enablement, and others, are configured during setup of the client or post-setup with PowerShell commands.</span></span> <span data-ttu-id="09441-520">TechNet の「クライアントを展開する方法」を参照してください。 [App-v クライアントを展開する方法](how-to-deploy-the-app-v-client-51gb18030.md)、または PowerShell を使用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-520">See the How to Deploy the Client section on TechNet at: [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md) or utilize the PowerShell:</span></span>

```powershell
get-command *appv*
```

### <span data-ttu-id="09441-521">公開の更新</span><span class="sxs-lookup"><span data-stu-id="09441-521">Publishing refresh</span></span>

<span data-ttu-id="09441-522">発行の更新処理は、App-v クライアントで実行されるいくつかの小さな操作で構成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-522">The publishing refresh process is comprised of several smaller operations that are performed on the App-V Client.</span></span> <span data-ttu-id="09441-523">App-v はアプリケーションの仮想化テクノロジであり、タスクスケジュール技術ではないため、Windows タスクスケジューラを使用して、ユーザーのログオン、コンピューターの起動時、およびスケジュールされた間隔でプロセスを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-523">Since App-V is an application virtualization technology and not a task scheduling technology, the Windows Task Scheduler is utilized to enable the process at user logon, machine startup, and at scheduled intervals.</span></span> <span data-ttu-id="09441-524">上記のセットアップ中のクライアントの構成は、適切な設定でクライアントを大規模なコンピューターグループに配布する場合に推奨される方法です。</span><span class="sxs-lookup"><span data-stu-id="09441-524">The configuration of the client during setup listed above is the preferred method when distributing the client to a large group of computers with the correct settings.</span></span> <span data-ttu-id="09441-525">これらのクライアント設定は、次の PowerShell コマンドレットを使用して構成できます。</span><span class="sxs-lookup"><span data-stu-id="09441-525">These client settings can be configured with the following PowerShell cmdlets:</span></span>

-   <span data-ttu-id="09441-526">**Add-AppVPublishingServer:** App-v パッケージを提供する App-v パブリッシングサーバーでクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="09441-526">**Add-AppVPublishingServer:** Configures the client with an App-V Publishing Server that provides App-V packages.</span></span>

-   <span data-ttu-id="09441-527">**Set-AppVPublishingServer:** App-v 発行サーバーの現在の設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="09441-527">**Set-AppVPublishingServer:** Modifies the current settings for the App-V Publishing Server.</span></span>

-   <span data-ttu-id="09441-528">**Set-AppVClientConfiguration:** App-v クライアントの currents 設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="09441-528">**Set-AppVClientConfiguration:** Modifies the currents settings for the App-V Client.</span></span>

-   <span data-ttu-id="09441-529">**同期-AppVPublishingServer:** App-v の公開更新プロセスを手動で開始します。</span><span class="sxs-lookup"><span data-stu-id="09441-529">**Sync-AppVPublishingServer:** Initiates an App-V Publishing Refresh process manually.</span></span> <span data-ttu-id="09441-530">これは、発行サーバーの構成中に作成されたスケジュールされたタスクでも使用されます。</span><span class="sxs-lookup"><span data-stu-id="09441-530">This is also utilized in the scheduled tasks created during configuration of the publishing server.</span></span>

<span data-ttu-id="09441-531">以下のセクションでは、App-v の公開更新のさまざまなフェーズで発生する操作の詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-531">The focus of the following sections is to detail the operations that occur during different phases of an App-V Publishing Refresh.</span></span> <span data-ttu-id="09441-532">次のトピックが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-532">The topics include:</span></span>

-   <span data-ttu-id="09441-533">App-v パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="09441-533">Adding an App-V Package</span></span>

-   <span data-ttu-id="09441-534">App-v パッケージの発行</span><span class="sxs-lookup"><span data-stu-id="09441-534">Publishing an App-V Package</span></span>

### <span data-ttu-id="09441-535">App-v パッケージを追加する</span><span class="sxs-lookup"><span data-stu-id="09441-535">Adding an App-V package</span></span>

<span data-ttu-id="09441-536">クライアントへの App-v パッケージの追加は、公開の更新プロセスの最初の手順です。</span><span class="sxs-lookup"><span data-stu-id="09441-536">Adding an App-V package to the client is the first step of the publishing refresh process.</span></span> <span data-ttu-id="09441-537">最終的な結果は `Add-AppVClientPackage` PowerShell のコマンドレットと同じですが、[発行更新の追加] プロセスの場合を除いて、構成済みの発行サーバーは接続され、1つのパッケージ追加操作ではなく、より詳細な情報を取得するために、クライアントに上位レベルのアプリケーションの一覧を渡します。</span><span class="sxs-lookup"><span data-stu-id="09441-537">The end result is the same as the `Add-AppVClientPackage` cmdlet in PowerShell, except during the publishing refresh add process, the configured publishing server is contacted and passes a high-level list of applications back to the client to pull more detailed information and not a single package add operation.</span></span> <span data-ttu-id="09441-538">このプロセスは、パッケージまたは接続グループの追加または更新のためにクライアントを構成して続行し、appv ファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="09441-538">The process continues by configuring the client for package or connection group additions or updates, then accesses the appv file.</span></span> <span data-ttu-id="09441-539">次に、appv ファイルの内容が展開され、ローカルオペレーティングシステムの適切な場所に配置されます。</span><span class="sxs-lookup"><span data-stu-id="09441-539">Next, the contents of the appv file are expanded and placed on the local operating system in the appropriate locations.</span></span> <span data-ttu-id="09441-540">次に、パッケージがフォールトストリーミング用に構成されていることを前提とした、プロセスの詳細なワークフローを示します。</span><span class="sxs-lookup"><span data-stu-id="09441-540">The following is a detailed workflow of the process, assuming the package is configured for Fault Streaming.</span></span>

**<span data-ttu-id="09441-541">App-v パッケージを追加する方法</span><span class="sxs-lookup"><span data-stu-id="09441-541">How to add an App-V package</span></span>**

1.  <span data-ttu-id="09441-542">PowerShell 経由の手動開始、または発行更新プロセスのタスクシーケンスの開始。</span><span class="sxs-lookup"><span data-stu-id="09441-542">Manual initiation via PowerShell or Task Sequence initiation of the Publishing Refresh process.</span></span>

    1.  <span data-ttu-id="09441-543">App-v クライアントは、HTTP 接続を行って、ターゲットに基づいてアプリケーションの一覧を要求します。</span><span class="sxs-lookup"><span data-stu-id="09441-543">The App-V Client makes an HTTP connection and requests a list of applications based on the target.</span></span> <span data-ttu-id="09441-544">発行の更新プロセスでは、ターゲットコンピューターまたはユーザーがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="09441-544">The Publishing refresh process supports targeting machines or users.</span></span>

    2.  <span data-ttu-id="09441-545">App-v 発行サーバーは、開始するターゲット、ユーザー、またはコンピューターの id を使用し、データベースにアプリケーションの一覧を照会します。</span><span class="sxs-lookup"><span data-stu-id="09441-545">The App-V Publishing Server uses the identity of the initiating target, user or machine, and queries the database for a list of entitled applications.</span></span> <span data-ttu-id="09441-546">アプリケーションの一覧は XML 応答として提供されます。クライアントは、パッケージごとに追加の要求をサーバーに送信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="09441-546">The list of applications is provided as an XML response, which the client uses to send additional requests to the server for more information on a per package basis.</span></span>

2.  <span data-ttu-id="09441-547">App-v クライアントの発行エージェントは、次のすべての操作をシリアル化して実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-547">The Publishing Agent on the App-V Client performs all actions below serialized.</span></span>

    <span data-ttu-id="09441-548">接続グループの一部であるパッケージバージョンの更新を処理できないため、未発行または無効なすべての接続グループを評価します。</span><span class="sxs-lookup"><span data-stu-id="09441-548">Evaluate any connection groups that are unpublished or disabled, since package version updates that are part of the connection group cannot be processed.</span></span>

3.  <span data-ttu-id="09441-549">追加操作または更新操作を識別して、パッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="09441-549">Configure the packages by identifying an Add or Update operations.</span></span>

    1.  <span data-ttu-id="09441-550">App-v クライアントでは、Windows の AppX API を利用し、発行サーバーから appv ファイルにアクセスします。</span><span class="sxs-lookup"><span data-stu-id="09441-550">The App-V Client utilizes the AppX API from Windows and accesses the appv file from the publishing server.</span></span>

    2.  <span data-ttu-id="09441-551">パッケージファイルが開かれ、AppXManifest.xml と StreamMap.xml がパッケージストアにダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-551">The package file is opened and the AppXManifest.xml and StreamMap.xml are downloaded to the Package Store.</span></span>

    3.  <span data-ttu-id="09441-552">StreamMap.xml で定義された完全な公開ブロックデータ。</span><span class="sxs-lookup"><span data-stu-id="09441-552">Completely stream publishing block data defined in the StreamMap.xml.</span></span> <span data-ttu-id="09441-553">パッケージストア¥ pkgguid¥ verguid¥の公開ブロックデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="09441-553">Stores the publishing block data in the Package Store\\PkgGUID\\VerGUID\\Root.</span></span>

        -   <span data-ttu-id="09441-554">アイコン: 拡張ポイントのターゲット。</span><span class="sxs-lookup"><span data-stu-id="09441-554">Icons: Targets of extension points.</span></span>

        -   <span data-ttu-id="09441-555">移植可能な実行可能ヘッダー (PE ヘッダー): イメージに関する基本情報が含まれる拡張ポイントのターゲット。ディスク上に直接アクセスしているか、ファイルの種類を介して直接アクセスします。</span><span class="sxs-lookup"><span data-stu-id="09441-555">Portable Executable Headers (PE Headers): Targets of extension points that contain the base information about the image need on disk, directly accessed or via file types.</span></span>

        -   <span data-ttu-id="09441-556">スクリプト: 発行プロセス全体で使用するために、スクリプトディレクトリをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="09441-556">Scripts: Download scripts directory for use throughout the publishing process.</span></span>

    4.  <span data-ttu-id="09441-557">パッケージストアにデータを設定します。</span><span class="sxs-lookup"><span data-stu-id="09441-557">Populate the Package store:</span></span>

        1.  <span data-ttu-id="09441-558">一覧表示されているすべてのディレクトリについて抽出されたパッケージを表す、ディスク上にスパースファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="09441-558">Create sparse files on disk that represent the extracted package for any directories listed.</span></span>

        2.  <span data-ttu-id="09441-559">ルートの下にある上位レベルのファイルとディレクトリをステージ化します。</span><span class="sxs-lookup"><span data-stu-id="09441-559">Stage top level files and directories under root.</span></span>

        3.  <span data-ttu-id="09441-560">その他のすべてのファイルは、ディレクトリがディスクのスパースとして表示され、オンデマンドでストリーミングされたときに作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-560">All other files are created when the directory is listed as sparse on disk and streamed on demand.</span></span>

    5.  <span data-ttu-id="09441-561">マシンカタログエントリを作成します。</span><span class="sxs-lookup"><span data-stu-id="09441-561">Create the machine catalog entries.</span></span> <span data-ttu-id="09441-562">パッケージファイルから Manifest.xml と DeploymentConfiguration.xml を作成します (パッケージ内の DeploymentConfiguration.xml ファイルがプレースホルダーに作成されていない場合)。</span><span class="sxs-lookup"><span data-stu-id="09441-562">Create the Manifest.xml and DeploymentConfiguration.xml from the package files (if no DeploymentConfiguration.xml file in the package a placeholder is created).</span></span>

    6.  <span data-ttu-id="09441-563">レジストリ HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog でパッケージストアの場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="09441-563">Create location of the package store in the registry HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog</span></span>

    7.  <span data-ttu-id="09441-564">パッケージストアから%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat に、レジストリファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="09441-564">Create the Registry.dat file from the package store to %ProgramData%\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat</span></span>

    8.  <span data-ttu-id="09441-565">App-v カーネルモードドライバー HKLM\\Microsoft\\Software\\AppV\\MAV でパッケージを登録します。</span><span class="sxs-lookup"><span data-stu-id="09441-565">Register the package with the App-V Kernel Mode Driver HKLM\\Microsoft\\Software\\AppV\\MAV</span></span>

    9.  <span data-ttu-id="09441-566">パッケージの AppxManifest.xml または DeploymentConfig.xml ファイルからスクリプトを呼び出して、タイミングを追加します。</span><span class="sxs-lookup"><span data-stu-id="09441-566">Invoke scripting from the AppxManifest.xml or DeploymentConfig.xml file for Package Add timing.</span></span>

4.  <span data-ttu-id="09441-567">追加と有効化または無効化によって接続グループを構成します。</span><span class="sxs-lookup"><span data-stu-id="09441-567">Configure Connection Groups by adding and enabling or disabling.</span></span>

5.  <span data-ttu-id="09441-568">ターゲット (ユーザーまたはコンピューター) に発行されていないオブジェクトを削除します。</span><span class="sxs-lookup"><span data-stu-id="09441-568">Remove objects that are not published to the target (user or machine).</span></span>

    <span data-ttu-id="09441-569">**注** この操作では、パッケージ削除は実行されませんが、特定のターゲット (ユーザーまたはコンピューター) の統合ポイントが削除され、ユーザーカタログファイル (グローバルに公開されているコンピューターカタログファイル) が削除されます。</span><span class="sxs-lookup"><span data-stu-id="09441-569">**Note** This will not perform a package deletion but rather remove integration points for the specific target (user or machine) and remove user catalog files (machine catalog files for globally published).</span></span>

     

6.  <span data-ttu-id="09441-570">クライアント構成に基づいて、バックグラウンドでの読み込みマウントを呼び出します。</span><span class="sxs-lookup"><span data-stu-id="09441-570">Invoke background load mounting based on client configuration.</span></span>

7.  <span data-ttu-id="09441-571">マシンまたはユーザーについて既に公開情報を持っているパッケージは、直ちに復元されます。</span><span class="sxs-lookup"><span data-stu-id="09441-571">Packages that already have publishing information for the machine or user are immediately restored.</span></span>

    <span data-ttu-id="09441-572">**注** この状態は、パッケージをバックグラウンドで追加することなく、削除しなくても削除の製品として発生します。</span><span class="sxs-lookup"><span data-stu-id="09441-572">**Note** This condition occurs as a product of removal without unpublishing with background addition of the package.</span></span>

     

<span data-ttu-id="09441-573">これにより、App-v パッケージの発行更新プロセスが完了します。</span><span class="sxs-lookup"><span data-stu-id="09441-573">This completes an App-V package add of the publishing refresh process.</span></span> <span data-ttu-id="09441-574">次の手順では、パッケージを特定のターゲット (コンピューターまたはユーザー) に公開します。</span><span class="sxs-lookup"><span data-stu-id="09441-574">The next step is publishing the package to the specific target (machine or user).</span></span>

![パッケージファイルとレジストリデータを追加する](images/packageaddfileandregistrydata.png)

### <span data-ttu-id="09441-576">App-v パッケージの発行</span><span class="sxs-lookup"><span data-stu-id="09441-576">Publishing an App-V package</span></span>

<span data-ttu-id="09441-577">公開の更新操作では、特定の発行操作 (AppVClientPackage) によって、ユーザーカタログにエントリが追加され、ユーザーに資格が割り当てられ、ローカルストアが識別され、統合手順が完了して終了します。</span><span class="sxs-lookup"><span data-stu-id="09441-577">During the Publishing Refresh operation, the specific publishing operation (Publish-AppVClientPackage) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span> <span data-ttu-id="09441-578">次に、詳細な手順を示します。</span><span class="sxs-lookup"><span data-stu-id="09441-578">The following are the detailed steps.</span></span>

**<span data-ttu-id="09441-579">公開と App-v パッケージの発行方法</span><span class="sxs-lookup"><span data-stu-id="09441-579">How to publish and App-V package</span></span>**

1.  <span data-ttu-id="09441-580">パッケージエントリがユーザーカタログに追加される</span><span class="sxs-lookup"><span data-stu-id="09441-580">Package entries are added to the user catalog</span></span>

    1.  <span data-ttu-id="09441-581">ユーザーを対象にしたパッケージ: ユーザーカタログのコンピューターに UserDeploymentConfiguration.xml と UserManifest.xml が配置されます。</span><span class="sxs-lookup"><span data-stu-id="09441-581">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the User Catalog</span></span>

    2.  <span data-ttu-id="09441-582">マシンの対象指定 (グローバル) パッケージ: UserDeploymentConfiguration.xml がコンピューターカタログに配置される</span><span class="sxs-lookup"><span data-stu-id="09441-582">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the Machine Catalog</span></span>

2.  <span data-ttu-id="09441-583">HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのためにカーネルモードドライバーでパッケージを登録します。</span><span class="sxs-lookup"><span data-stu-id="09441-583">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

3.  <span data-ttu-id="09441-584">統合タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-584">Perform integration tasks.</span></span>

    1.  <span data-ttu-id="09441-585">延長点を作成します。</span><span class="sxs-lookup"><span data-stu-id="09441-585">Create extension points.</span></span>

    2.  <span data-ttu-id="09441-586">ユーザーのレジストリとローミングプロファイル (ショートカットバックアップ) にバックアップ情報を保存します。</span><span class="sxs-lookup"><span data-stu-id="09441-586">Store backup information in the user’s registry and roaming profile (Shortcut Backups).</span></span>

        <span data-ttu-id="09441-587">**注** これにより、パッケージが未公開の場合は、拡張ポイントを復元できるようになります。</span><span class="sxs-lookup"><span data-stu-id="09441-587">**Note** This enables restore extension points if the package is unpublished.</span></span>

         

    3.  <span data-ttu-id="09441-588">公開タイミングのターゲットとなるスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-588">Run scripts targeted for publishing timing.</span></span>

<span data-ttu-id="09441-589">接続グループの一部である App-v パッケージの公開は、上記のプロセスと非常に似ています。</span><span class="sxs-lookup"><span data-stu-id="09441-589">Publishing an App-V Package that is part of a Connection Group is very similar to the above process.</span></span> <span data-ttu-id="09441-590">接続グループの場合、特定のカタログ情報を格納するパスには、カタログディレクトリの子として PackageGroups が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-590">For connection groups, the path that stores the specific catalog information includes PackageGroups as a child of the Catalog Directory.</span></span> <span data-ttu-id="09441-591">詳細については、上記のコンピューターとユーザーのカタログ情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="09441-591">Review the machine and users catalog information above for details.</span></span>

![パッケージファイルとレジストリデータの追加-グローバル](images/packageaddfileandregistrydata-global.png)

### <span data-ttu-id="09441-593">アプリケーションの起動</span><span class="sxs-lookup"><span data-stu-id="09441-593">Application launch</span></span>

<span data-ttu-id="09441-594">公開の更新プロセスが完了すると、ユーザーはアプリを起動し、その後で App-v アプリケーションを再起動します。</span><span class="sxs-lookup"><span data-stu-id="09441-594">After the Publishing Refresh process, the user launches and subsequently re-launches an App-V application.</span></span> <span data-ttu-id="09441-595">このプロセスは非常にシンプルで、最小限のネットワークトラフィックですばやく起動するように最適化されています。</span><span class="sxs-lookup"><span data-stu-id="09441-595">The process is very simple and optimized to launch quickly with a minimum of network traffic.</span></span> <span data-ttu-id="09441-596">App-v クライアントは、発行中に作成されたファイルについて、ユーザーカタログへのパスを確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-596">The App-V Client checks the path to the user catalog for files created during publishing.</span></span> <span data-ttu-id="09441-597">パッケージを起動する権利が確立されると、App-v クライアントは仮想環境を作成し、必要なデータのストリーミングを開始し、仮想環境の作成時に適切なマニフェストと展開構成ファイルを適用します。</span><span class="sxs-lookup"><span data-stu-id="09441-597">After rights to launch the package are established, the App-V Client creates a virtual environment, begins streaming any necessary data, and applies the appropriate manifest and deployment configuration files during virtual environment creation.</span></span> <span data-ttu-id="09441-598">仮想環境が作成され、特定のパッケージとアプリケーション用に構成されると、アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="09441-598">With the virtual environment created and configured for the specific package and application, the application starts.</span></span>

**<span data-ttu-id="09441-599">App-v アプリケーションを起動する方法</span><span class="sxs-lookup"><span data-stu-id="09441-599">How to launch App-V applications</span></span>**

1.  <span data-ttu-id="09441-600">ユーザーは、ショートカットまたはファイルの種類の呼び出しをクリックしてアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="09441-600">User launches the application by clicking on a shortcut or file type invocation.</span></span>

2.  <span data-ttu-id="09441-601">App-v クライアントが、次のファイルに対するユーザーカタログの存在を確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-601">The App-V Client verifies existence in the User Catalog for the following files</span></span>

    -   <span data-ttu-id="09441-602">UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="09441-602">UserDeploymentConfiguration.xml</span></span>

    -   <span data-ttu-id="09441-603">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="09441-603">UserManifest.xml</span></span>

3.  <span data-ttu-id="09441-604">ファイルが存在する場合、アプリケーションはその特定のユーザーの資格を持ち、アプリケーションは起動のプロセスを開始します。</span><span class="sxs-lookup"><span data-stu-id="09441-604">If the files are present, the application is entitled for that specific user and the application will start the process for launch.</span></span> <span data-ttu-id="09441-605">この時点では、ネットワークトラフィックはありません。</span><span class="sxs-lookup"><span data-stu-id="09441-605">There is no network traffic at this point.</span></span>

4.  <span data-ttu-id="09441-606">次に、app-v クライアントは、App-v Client サービスに登録されているパッケージのパスがレジストリで検出されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-606">Next, the App-V Client checks that the path for the package registered for the App-V Client service is found in the registry.</span></span>

5.  <span data-ttu-id="09441-607">パッケージストアへのパスを見つけると、仮想環境が作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-607">Upon finding the path to the package store, the virtual environment is created.</span></span> <span data-ttu-id="09441-608">初めての起動の場合は、プライマリ機能ブロックがある場合はダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="09441-608">If this is the first launch, the Primary Feature Block downloads if present.</span></span>

6.  <span data-ttu-id="09441-609">ダウンロードした後、App-v クライアントサービスはマニフェストと展開構成ファイルを使用して、仮想環境とすべての App-v サブシステムの読み込みを構成します。</span><span class="sxs-lookup"><span data-stu-id="09441-609">After downloading, the App-V Client service consumes the manifest and deployment configuration files to configure the virtual environment and all App-V subsystems are loaded.</span></span>

7.  <span data-ttu-id="09441-610">アプリケーションが起動します。</span><span class="sxs-lookup"><span data-stu-id="09441-610">The Application launches.</span></span> <span data-ttu-id="09441-611">パッケージストア (スパースファイル) に不足しているファイルがある場合は、必要に応じて、ファイルが stream によってエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="09441-611">For any missing files in the package store (sparse files), App-V will stream fault the files on an as needed basis.</span></span>

    ![パッケージファイルとレジストリデータストリームの追加](images/packageaddfileandregistrydata-stream.png)

### <span data-ttu-id="09441-613">App-v パッケージのアップグレード</span><span class="sxs-lookup"><span data-stu-id="09441-613">Upgrading an App-V package</span></span>

<span data-ttu-id="09441-614">App-v 5 パッケージのアップグレードプロセスは、以前のバージョンの App-v とは異なります。</span><span class="sxs-lookup"><span data-stu-id="09441-614">The App-V 5 package upgrade process differs from the older versions of App-V.</span></span> <span data-ttu-id="09441-615">App-v では、異なるユーザーに対してコンピューター上の同じパッケージの複数のバージョンがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="09441-615">App-V supports multiple versions of the same package on a machine entitled to different users.</span></span> <span data-ttu-id="09441-616">パッケージバージョンは、パッケージストアとしていつでも追加できます。また、新しいリソースでカタログが更新されます。</span><span class="sxs-lookup"><span data-stu-id="09441-616">Package versions can be added at any time as the package store and catalogs are updated with the new resources.</span></span> <span data-ttu-id="09441-617">新しいバージョンリソースの追加に固有のプロセスは、記憶域の最適化です。</span><span class="sxs-lookup"><span data-stu-id="09441-617">The only process specific to the addition of new version resources is storage optimization.</span></span> <span data-ttu-id="09441-618">アップグレード中は、新しいバージョンのストアの場所に新しいファイルのみが追加され、変更されていないファイルに対してハードリンクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-618">During an upgrade, only the new files are added to the new version store location and hard links are created for unchanged files.</span></span> <span data-ttu-id="09441-619">これにより、ディスク上の1つの場所でファイルを表示して、ディスク上のファイルの場所エントリを持つすべてのフォルダーに投影するだけで、全体的な記憶域が削減されます。</span><span class="sxs-lookup"><span data-stu-id="09441-619">This reduces the overall storage by only presenting the file on one disk location and then projecting it into all folders with a file location entry on the disk.</span></span> <span data-ttu-id="09441-620">App-v パッケージのアップグレードの具体的な詳細は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="09441-620">The specific details of upgrading an App-V Package are as follows:</span></span>

**<span data-ttu-id="09441-621">App-v パッケージのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="09441-621">How to upgrade an App-V package</span></span>**

1.  <span data-ttu-id="09441-622">App-v クライアントは、公開の更新を実行し、新しいバージョンの App-v パッケージを検出します。</span><span class="sxs-lookup"><span data-stu-id="09441-622">The App-V Client performs a Publishing Refresh and discovers a newer version of an App-V Package.</span></span>

2.  <span data-ttu-id="09441-623">パッケージエントリは、新しいバージョンの適切なカタログに追加されます。</span><span class="sxs-lookup"><span data-stu-id="09441-623">Package entries are added to the appropriate catalog for the new version</span></span>

    1.  <span data-ttu-id="09441-624">ユーザーを対象にしたパッケージ: appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID でユーザーカタログのコンピューターに配置される UserDeploymentConfiguration.xml と UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="09441-624">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the user catalog at appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

    2.  <span data-ttu-id="09441-625">コンピューターの対象指定 (グローバル) パッケージ: UserDeploymentConfiguration.xml は、%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID のコンピューターカタログに配置されます。</span><span class="sxs-lookup"><span data-stu-id="09441-625">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the machine catalog at %programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

3.  <span data-ttu-id="09441-626">HKLM\\Software\\Microsoft\\AppV\\MAV でユーザーのためにカーネルモードドライバーでパッケージを登録します。</span><span class="sxs-lookup"><span data-stu-id="09441-626">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

4.  <span data-ttu-id="09441-627">統合タスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-627">Perform integration tasks.</span></span>

    -   <span data-ttu-id="09441-628">マニフェストおよび動的構成ファイルから拡張機能 (EP) を統合します。</span><span class="sxs-lookup"><span data-stu-id="09441-628">Integrate extensions points (EP) from the Manifest and Dynamic Configuration files.</span></span>

    1.  <span data-ttu-id="09441-629">ファイルベースの EP データは、パッケージストアからの接合ポイントを利用する AppData フォルダーに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-629">File based EP data is stored in the AppData folder utilizing Junction Points from the package store.</span></span>

    2.  <span data-ttu-id="09441-630">新しいバージョンが使用可能になったときに、バージョン1の EPs は既に存在します。</span><span class="sxs-lookup"><span data-stu-id="09441-630">Version 1 EPs already exist when a new version becomes available.</span></span>

    3.  <span data-ttu-id="09441-631">拡張ポイントは、新しいまたは更新された拡張ポイントについて、マシンまたはユーザーのカタログ内のバージョン2の場所に切り替えられます。</span><span class="sxs-lookup"><span data-stu-id="09441-631">The extension points are switched to the Version 2 location in machine or user catalogs for any newer or updated extension points.</span></span>

5.  <span data-ttu-id="09441-632">公開タイミングのターゲットとなるスクリプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-632">Run scripts targeted for publishing timing.</span></span>

6.  <span data-ttu-id="09441-633">必要に応じて、side-by-side アセンブリをインストールします。</span><span class="sxs-lookup"><span data-stu-id="09441-633">Install Side by Side assemblies as required.</span></span>

### <span data-ttu-id="09441-634">使用中の App-v パッケージのアップグレード</span><span class="sxs-lookup"><span data-stu-id="09441-634">Upgrading an in-use App-V package</span></span>

<span data-ttu-id="09441-635">**App-v 5 SP2 以降**: エンドユーザーが使用しているパッケージをアップグレードしようとすると、アップグレードタスクは保留状態になります。</span><span class="sxs-lookup"><span data-stu-id="09441-635">**Starting in App-V 5 SP2**: If you try to upgrade a package that is in use by an end user, the upgrade task is placed in a pending state.</span></span> <span data-ttu-id="09441-636">アップグレードは、次のルールに従って後で実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-636">The upgrade will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-637">タスクの種類</span><span class="sxs-lookup"><span data-stu-id="09441-637">Task type</span></span></th>
<th align="left"><span data-ttu-id="09441-638">該当するルール</span><span class="sxs-lookup"><span data-stu-id="09441-638">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-639">ユーザーベースのタスク (パッケージをユーザーに公開するなど)</span><span class="sxs-lookup"><span data-stu-id="09441-639">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-640">保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-640">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-641">グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</span><span class="sxs-lookup"><span data-stu-id="09441-641">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-642">保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-642">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-643">タスクが保留状態になっている場合、App-v クライアントは、次のように、保留中のタスクのレジストリキーも生成します。</span><span class="sxs-lookup"><span data-stu-id="09441-643">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-644">ユーザーベースまたはグローバルベースのタスク</span><span class="sxs-lookup"><span data-stu-id="09441-644">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="09441-645">レジストリキーが生成される場所</span><span class="sxs-lookup"><span data-stu-id="09441-645">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-646">ユーザーベースのタスク</span><span class="sxs-lookup"><span data-stu-id="09441-646">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-647">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="09441-647">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-648">グローバルに基づくタスク</span><span class="sxs-lookup"><span data-stu-id="09441-648">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-649">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="09441-649">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-650">ユーザーが新しいバージョンのパッケージを使用できるようにするには、次の操作を完了する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-650">The following operations must be completed before users can use the newer version of the package:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-651">タスク</span><span class="sxs-lookup"><span data-stu-id="09441-651">Task</span></span></th>
<th align="left"><span data-ttu-id="09441-652">詳細</span><span class="sxs-lookup"><span data-stu-id="09441-652">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-653">パッケージをコンピューターに追加する</span><span class="sxs-lookup"><span data-stu-id="09441-653">Add the package to the computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-654">このタスクはコンピューターに固有のものであり、上記のパッケージ追加のセクションの手順に従って、いつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="09441-654">This task is computer specific and you can perform it at any time by completing the steps in the Package Add section above.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-655">パッケージを公開する</span><span class="sxs-lookup"><span data-stu-id="09441-655">Publish the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-656">手順については、上記のパッケージ発行に関するセクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-656">See the Package Publishing section above for steps.</span></span> <span data-ttu-id="09441-657">このプロセスでは、システムの拡張ポイントを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-657">This process requires that you update extension points on the system.</span></span> <span data-ttu-id="09441-658">このタスクを完了するときにエンドユーザーがアプリケーションを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="09441-658">End users cannot be using the application when you complete this task.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="09441-659">パッケージを更新するためのガイドとして、次のシナリオの例を使用します。</span><span class="sxs-lookup"><span data-stu-id="09441-659">Use the following example scenarios as a guide for updating packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-660">シナリオ</span><span class="sxs-lookup"><span data-stu-id="09441-660">Scenario</span></span></th>
<th align="left"><span data-ttu-id="09441-661">要件</span><span class="sxs-lookup"><span data-stu-id="09441-661">Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-662">アップグレードしようとしたときに、app-v パッケージが使用されない</span><span class="sxs-lookup"><span data-stu-id="09441-662">App-V package is not in use when you try to upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-663">仮想アプリケーション、COM サーバー、またはシェルの拡張機能を使って、パッケージの次のコンポーネントを使用することはできません。</span><span class="sxs-lookup"><span data-stu-id="09441-663">None of the following components of the package can be in use: virtual application, COM server, or shell extensions.</span></span></p>
<p><span data-ttu-id="09441-664">管理者が新しいバージョンのパッケージを公開し、次回パッケージ内のコンポーネントまたはアプリケーションが起動したときにアップグレードが動作します。</span><span class="sxs-lookup"><span data-stu-id="09441-664">The administrator publishes a newer version of the package and the upgrade works the next time a component or application inside the package is launched.</span></span> <span data-ttu-id="09441-665">パッケージの新しいバージョンがストリーミングされ、実行されます。</span><span class="sxs-lookup"><span data-stu-id="09441-665">The new version of the package is streamed and run.</span></span> <span data-ttu-id="09441-666">このシナリオでは、アプリ-v 5 の以前のリリースからの app-v 5 SP2 では何も変更されていません。</span><span class="sxs-lookup"><span data-stu-id="09441-666">Nothing has changed in this scenario in App-V 5 SP2 from previous releases of App-V 5.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-667">管理者がパッケージの新しいバージョンを発行するときに、app-v パッケージが使用されている</span><span class="sxs-lookup"><span data-stu-id="09441-667">App-V package is in use when the administrator publishes a newer version of the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-668">アップグレード操作は、App-v クライアントによって保留状態に設定されます。つまり、パッケージが使用されていないときに、キューに登録され、後で実行されることを意味します。</span><span class="sxs-lookup"><span data-stu-id="09441-668">The upgrade operation is set to pending by the App-V Client, which means that it is queued and carried out later when the package is not in use.</span></span></p>
<p><span data-ttu-id="09441-669">パッケージアプリケーションを使用している場合、ユーザーは仮想アプリケーションをシャットダウンした後、アップグレードが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09441-669">If the package application is in use, the user shuts down the virtual application, after which the upgrade can occur.</span></span></p>
<p><span data-ttu-id="09441-670">パッケージにシェル拡張機能 (Office 2013) が含まれている場合、Windows エクスプローラーによって完全に読み込まれるため、ユーザーはログインできません。</span><span class="sxs-lookup"><span data-stu-id="09441-670">If the package has shell extensions (Office 2013), which are permanently loaded by Windows Explorer, the user cannot be logged in.</span></span> <span data-ttu-id="09441-671">ユーザーはログオフし、もう一度ログインして、App-v パッケージのアップグレードを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-671">Users must log off and the log back in to initiate the App-V package upgrade.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="09441-672">グローバル vs ユーザー発行</span><span class="sxs-lookup"><span data-stu-id="09441-672">Global vs user publishing</span></span>

<span data-ttu-id="09441-673">App-v パッケージは、次の2つの方法のいずれかで公開できます。特定のユーザーまたはユーザーのグループに対してアプリ V パッケージを適用し、コンピューターのすべてのユーザーに対して、アプリ全体に対して app-v パッケージを適用するユーザー。</span><span class="sxs-lookup"><span data-stu-id="09441-673">App-V Packages can be published in one of two ways; User which entitles an App-V package to a specific user or group of users and Global which entitles the App-V package to the entire machine for all users of the machine.</span></span> <span data-ttu-id="09441-674">パッケージのアップグレードが保留になっていて、App-v パッケージが使用されていない場合は、次の2種類の発行を検討してください。</span><span class="sxs-lookup"><span data-stu-id="09441-674">Once a package upgrade has been pended and the App-V package is not in use, consider the two types of publishing:</span></span>

-   <span data-ttu-id="09441-675">**グローバルに公開済み**: アプリケーションはコンピューターに公開されます。そのコンピューター上のすべてのユーザーがそれを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="09441-675">**Globally published**: the application is published to a machine; all users on that machine can use it.</span></span> <span data-ttu-id="09441-676">アップグレードは、App-v Client サービスが開始されたときに発生します。これは、実質的にコンピューターの再起動を意味します。</span><span class="sxs-lookup"><span data-stu-id="09441-676">The upgrade will happen when the App-V Client Service starts, which effectively means a machine restart.</span></span>

-   <span data-ttu-id="09441-677">**ユーザーが公開**されました: アプリケーションはユーザーに公開されます。</span><span class="sxs-lookup"><span data-stu-id="09441-677">**User published**: the application is published to a user.</span></span> <span data-ttu-id="09441-678">コンピューターに複数のユーザーがいる場合、そのアプリケーションはユーザーのサブセットに公開できます。</span><span class="sxs-lookup"><span data-stu-id="09441-678">If there are multiple users on the machine, the application can be published to a subset of the users.</span></span> <span data-ttu-id="09441-679">アップグレードは、ユーザーがログインしたとき、または再び公開されたとき (定期的に、ConfigMgr ポリシーの更新と評価、または PowerShell コマンドを使って明示的に実行した場合) に行われます。</span><span class="sxs-lookup"><span data-stu-id="09441-679">The upgrade will happen when the user logs in or when it is published again (periodically, ConfigMgr Policy refresh and evaluation, or an App-V periodic publishing/refresh, or explicitly via PowerShell commands).</span></span>

### <span data-ttu-id="09441-680">App-v パッケージの削除</span><span class="sxs-lookup"><span data-stu-id="09441-680">Removing an App-V package</span></span>

<span data-ttu-id="09441-681">完全なインフラストラクチャでの App-v アプリケーションの削除は、未発行操作であり、パッケージの削除は実行されません。</span><span class="sxs-lookup"><span data-stu-id="09441-681">Removing App-V applications in a Full Infrastructure is an unpublish operation, and does not perform a package removal.</span></span> <span data-ttu-id="09441-682">このプロセスは、上の発行プロセスと同じですが、削除プロセスを追加する代わりに、App-v パッケージに加えられた変更を元に戻します。</span><span class="sxs-lookup"><span data-stu-id="09441-682">The process is the same as the publish process above, but instead of adding the removal process reverses the changes that have been made for App-V Packages.</span></span>

### <span data-ttu-id="09441-683">App-v パッケージを修復する</span><span class="sxs-lookup"><span data-stu-id="09441-683">Repairing an App-V package</span></span>

<span data-ttu-id="09441-684">修復操作は非常に簡単ですが、コンピューター上の多くの場所に影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="09441-684">The repair operation is very simple but may affect many locations on the machine.</span></span> <span data-ttu-id="09441-685">前に説明した Copy on Write (COW) の場所は削除され、拡張ポイントは統合されていない状態になり、再び統合されます。</span><span class="sxs-lookup"><span data-stu-id="09441-685">The previously mentioned Copy on Write (COW) locations are removed, and extension points are de-integrated and then re-integrated.</span></span> <span data-ttu-id="09441-686">COW データの配置場所を確認するには、レジストリに登録されている場所を確認してください。</span><span class="sxs-lookup"><span data-stu-id="09441-686">Please review the COW data placement locations by reviewing where they are registered in the registry.</span></span> <span data-ttu-id="09441-687">この操作は自動的に実行され、アプリ-V クライアント本体または PowerShell 経由 (AppVClientPackage) から修復操作を開始する場合以外に、管理者が制御することはできません。</span><span class="sxs-lookup"><span data-stu-id="09441-687">This operation is done automatically and there is no administrative control other than initiating a Repair operation from the App-V Client Console or via PowerShell (Repair-AppVClientPackage).</span></span>

## <a href="" id="bkmk-integr-appv-pkgs"></a><span data-ttu-id="09441-688">App-v パッケージの統合</span><span class="sxs-lookup"><span data-stu-id="09441-688">Integration of App-V packages</span></span>


<span data-ttu-id="09441-689">App-v クライアントとパッケージアーキテクチャは、パッケージの追加と発行中にローカルのオペレーティングシステムとの固有の統合を実現します。</span><span class="sxs-lookup"><span data-stu-id="09441-689">The App-V Client and package architecture provides specific integration with the local operating system during the addition and publishing of packages.</span></span> <span data-ttu-id="09441-690">3つのファイルは、App-v パッケージの統合または拡張ポイントを定義します。</span><span class="sxs-lookup"><span data-stu-id="09441-690">Three files define the integration or extension points for an App-V Package:</span></span>

-   <span data-ttu-id="09441-691">AppXManifest.xml: パッケージの内部に保存され、パッケージストアとユーザープロファイルに保存されているフォールバックコピーが含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-691">AppXManifest.xml: Stored inside of the package with fallback copies stored in the package store and the user profile.</span></span> <span data-ttu-id="09441-692">シーケンス処理中に作成されたオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="09441-692">Contains the options created during the sequencing process.</span></span>

-   <span data-ttu-id="09441-693">DeploymentConfig.xml: コンピューターとユーザーによる統合の拡張ポイントの構成情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="09441-693">DeploymentConfig.xml: Provides configuration information of computer and user based integration extension points.</span></span>

-   <span data-ttu-id="09441-694">UserConfig.xml: ユーザーベースの構成のみを提供し、ユーザーベースの拡張ポイントのみをターゲットとする Deploymentconfig.xml のサブセット。</span><span class="sxs-lookup"><span data-stu-id="09441-694">UserConfig.xml: A subset of the Deploymentconfig.xml that only provides user- based configurations and only targets user-based extension points.</span></span>

### <span data-ttu-id="09441-695">統合のルール</span><span class="sxs-lookup"><span data-stu-id="09441-695">Rules of integration</span></span>

<span data-ttu-id="09441-696">App-v アプリケーションが app-v クライアントを備えたコンピューターに公開されると、次の一覧に示すように特定の操作が行われます。</span><span class="sxs-lookup"><span data-stu-id="09441-696">When App-V applications are published to a computer with the App-V Client, some specific actions take place as described in the list below:</span></span>

-   <span data-ttu-id="09441-697">グローバル公開: ショートカットは、[すべてのユーザー] プロファイルの場所と他の拡張ポイントに保存され、HKLM ハイブのレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-697">Global Publishing: Shortcuts are stored in the All Users profile location and other extension points are stored in the registry in the HKLM hive.</span></span>

-   <span data-ttu-id="09441-698">ユーザー公開: ショートカットは、現在のユーザーアカウントプロファイルに保存され、その他の拡張ポイントは、HKCU ハイブのレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-698">User Publishing: Shortcuts are stored in the current user account profile and other extension points are stored in the registry in the HKCU hive.</span></span>

-   <span data-ttu-id="09441-699">バックアップと復元: 既存のネイティブアプリケーションデータとレジストリ (FTA 登録など) は、発行時にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="09441-699">Backup and Restore: Existing native application data and registry (such as FTA registrations) are backed up during publishing.</span></span>

    1.  <span data-ttu-id="09441-700">App-v パッケージには、所有権が最新の公開された App-v アプリケーションに渡される、最後の統合パッケージに基づいて所有権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="09441-700">App-V packages are given ownership based on the last integrated package where the ownership is passed to the newest published App-V application.</span></span>

    2.  <span data-ttu-id="09441-701">所有している App-v パッケージが公開されていない場合は、1つのアプリから別のアプリに所有権が転送されます。</span><span class="sxs-lookup"><span data-stu-id="09441-701">Ownership transfers from one App-V package to another when the owning App-V package is unpublished.</span></span> <span data-ttu-id="09441-702">これにより、データまたはレジストリの復元が開始されることはありません。</span><span class="sxs-lookup"><span data-stu-id="09441-702">This will not initiate a restore of the data or registry.</span></span>

    3.  <span data-ttu-id="09441-703">拡張ポイントごとに、最後のパッケージが未公開または削除されたときに、バックアップしたデータを復元します。</span><span class="sxs-lookup"><span data-stu-id="09441-703">Restore the backed up data when the last package is unpublished or removed on a per extension point basis.</span></span>

### <span data-ttu-id="09441-704">拡張点</span><span class="sxs-lookup"><span data-stu-id="09441-704">Extension points</span></span>

<span data-ttu-id="09441-705">App-v の公開ファイル (マニフェストと動的構成) には、アプリケーションをローカルオペレーティングシステムと統合できるようにするいくつかの拡張ポイントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="09441-705">The App-V publishing files (manifest and dynamic configuration) provide several extension points that enable the application to integrate with the local operating system.</span></span> <span data-ttu-id="09441-706">これらの拡張機能は、ショートカットの配置、ファイルの種類の関連付けの作成、コンポーネントの登録など、一般的なアプリケーションのインストールタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="09441-706">These extension points perform typical application installation tasks, such as placing shortcuts, creating file type associations, and registering components.</span></span> <span data-ttu-id="09441-707">従来のアプリケーションと同じ方法でインストールされない仮想アプリケーションは、いくつかの違いがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-707">As these are virtualized applications that are not installed in the same manner a traditional application, there are some differences.</span></span> <span data-ttu-id="09441-708">このセクションで取り上げている拡張ポイントの一覧を次に示します。</span><span class="sxs-lookup"><span data-stu-id="09441-708">The following is a list of extension points covered in this section:</span></span>

-   <span data-ttu-id="09441-709">ショートカット</span><span class="sxs-lookup"><span data-stu-id="09441-709">Shortcuts</span></span>

-   <span data-ttu-id="09441-710">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="09441-710">File Type Associations</span></span>

-   <span data-ttu-id="09441-711">シェルの拡張機能</span><span class="sxs-lookup"><span data-stu-id="09441-711">Shell Extensions</span></span>

-   <span data-ttu-id="09441-712">COM</span><span class="sxs-lookup"><span data-stu-id="09441-712">COM</span></span>

-   <span data-ttu-id="09441-713">ソフトウェアクライアント</span><span class="sxs-lookup"><span data-stu-id="09441-713">Software Clients</span></span>

-   <span data-ttu-id="09441-714">アプリケーションの機能</span><span class="sxs-lookup"><span data-stu-id="09441-714">Application capabilities</span></span>

-   <span data-ttu-id="09441-715">URL プロトコルハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-715">URL Protocol Handler</span></span>

-   <span data-ttu-id="09441-716">AppPath</span><span class="sxs-lookup"><span data-stu-id="09441-716">AppPath</span></span>

-   <span data-ttu-id="09441-717">仮想アプリケーション</span><span class="sxs-lookup"><span data-stu-id="09441-717">Virtual Application</span></span>

### <span data-ttu-id="09441-718">ショートカット</span><span class="sxs-lookup"><span data-stu-id="09441-718">Shortcuts</span></span>

<span data-ttu-id="09441-719">短い切り取りは、OS との統合の基本的な要素の1つであり、App-v アプリケーションを直接ユーザーが起動するためのインターフェイスです。</span><span class="sxs-lookup"><span data-stu-id="09441-719">The short cut is one of the basic elements of integration with the OS and is the interface for direct user launch of an App-V application.</span></span> <span data-ttu-id="09441-720">App-v アプリケーションの発行と発行取り消し中。</span><span class="sxs-lookup"><span data-stu-id="09441-720">During the publishing and unpublishing of App-V applications.</span></span>

<span data-ttu-id="09441-721">パッケージマニフェストと動的構成 XML ファイルから、特定のアプリケーションの実行可能ファイルへのパスは、次のようなセクションにあります。</span><span class="sxs-lookup"><span data-stu-id="09441-721">From the package manifest and dynamic configuration XML files, the path to a specific application executable can be found in a section similar to the following:</span></span>

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

<span data-ttu-id="09441-722">前に説明したように、App-v のショートカットは、更新操作に基づいて既定でユーザーのプロファイルに配置されます。</span><span class="sxs-lookup"><span data-stu-id="09441-722">As mentioned previously, the App-V shortcuts are placed by default in the user’s profile based on the refresh operation.</span></span> <span data-ttu-id="09441-723">グローバル更新場所 [すべてのユーザー] プロファイルとユーザー更新のショートカットは、特定のユーザーのプロファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-723">Global refresh places shortcuts in the All Users profile and user refresh stores them in the specific user’s profile.</span></span> <span data-ttu-id="09441-724">実際の実行可能ファイルは、パッケージストアに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-724">The actual executable is stored in the Package Store.</span></span> <span data-ttu-id="09441-725">ICO ファイルの場所は、App-v パッケージ内のトークン化された場所です。</span><span class="sxs-lookup"><span data-stu-id="09441-725">The location of the ICO file is a tokenized location in the App-V package.</span></span>

### <span data-ttu-id="09441-726">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="09441-726">File type associations</span></span>

<span data-ttu-id="09441-727">App-v クライアントは、発行中にローカルのオペレーティングシステムのファイルの種類の関連付けを管理します。これにより、ユーザーはファイルの種類の呼び出しを使用したり、明示的に登録された拡張子 (.docx) を使ってファイルを開いたりして、App-v アプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-727">The App-V Client manages the local operating system File Type Associations during publishing, which enables users to use file type invocations or to open a file with a specifically registered extension (.docx) to start an App-V application.</span></span> <span data-ttu-id="09441-728">ファイルの種類の関連付けは、次の例で示すようにマニフェストと動的構成ファイルに存在します。</span><span class="sxs-lookup"><span data-stu-id="09441-728">File type associations are present in the manifest and dynamic configuration files as represented in the example below:</span></span>

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

<span data-ttu-id="09441-729">**注** この例では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="09441-729">**Note** In this example:</span></span>

-   `<Name>.xdp</Name>` <span data-ttu-id="09441-730">は拡張機能です</span><span class="sxs-lookup"><span data-stu-id="09441-730">is the extension</span></span>

-   `<Name>AcroExch.XDPDoc</Name>` <span data-ttu-id="09441-731">は ProgId 値 (付加された ProgId を指します)</span><span class="sxs-lookup"><span data-stu-id="09441-731">is the ProgId value (which points to the adjoining ProgId)</span></span>

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` <span data-ttu-id="09441-732">はコマンドラインで、アプリケーションの実行可能ファイルを指します。</span><span class="sxs-lookup"><span data-stu-id="09441-732">is the command line, which points to the application executable</span></span>

 

### <span data-ttu-id="09441-733">シェル拡張</span><span class="sxs-lookup"><span data-stu-id="09441-733">Shell extensions</span></span>

<span data-ttu-id="09441-734">シェルの拡張機能は、シーケンス処理中にパッケージに自動的に埋め込まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-734">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="09441-735">パッケージがグローバルに公開されると、シェル拡張によって、アプリケーションがローカルにインストールされている場合と同じ機能をユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="09441-735">When the package is published globally, the shell extension gives users the same functionality as if the application were locally installed.</span></span> <span data-ttu-id="09441-736">アプリケーションでは、シェルの拡張機能を有効にするために、クライアントで追加のセットアップや構成を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09441-736">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

**<span data-ttu-id="09441-737">シェルの拡張機能を使用するための要件:</span><span class="sxs-lookup"><span data-stu-id="09441-737">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="09441-738">埋め込まれたシェルの拡張機能を含むパッケージは、グローバルに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="09441-738">Packages that contain embedded shell extensions must be published globally.</span></span>

-   <span data-ttu-id="09441-739">アプリケーション、Sequencer、および App-v クライアントの "ビット" は一致する必要があります。また、シェルの拡張機能は使用できません。</span><span class="sxs-lookup"><span data-stu-id="09441-739">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="09441-740">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="09441-740">For example:</span></span>

    -   <span data-ttu-id="09441-741">このアプリケーションのバージョンは64ビットです。</span><span class="sxs-lookup"><span data-stu-id="09441-741">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="09441-742">Sequencer は64ビットコンピューターで実行されています。</span><span class="sxs-lookup"><span data-stu-id="09441-742">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="09441-743">パッケージは、64ビットの App-v クライアントコンピューターに配信されます。</span><span class="sxs-lookup"><span data-stu-id="09441-743">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="09441-744">次の表は、サポートされているシェルの拡張機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="09441-744">The following table displays the supported shell extensions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-745">ハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-745">Handler</span></span></th>
<th align="left"><span data-ttu-id="09441-746">説明</span><span class="sxs-lookup"><span data-stu-id="09441-746">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-747">コンテキストメニューハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-747">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-748">コンテキストメニューにメニュー項目を追加します。</span><span class="sxs-lookup"><span data-stu-id="09441-748">Adds menu items to the context menu.</span></span> <span data-ttu-id="09441-749">コンテキストメニューが表示される前に呼び出されます。</span><span class="sxs-lookup"><span data-stu-id="09441-749">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-750">ドラッグアンドドロップハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-750">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-751">ドラッグアンドドロップを右クリックし、表示されるコンテキストメニューを変更して、アクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="09441-751">Controls the action upon right-click drag-and-drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-752">ドロップターゲットハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-752">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-753">データオブジェクトがドラッグアンドドロップされた後、ファイルなどのドロップターゲットを介して、アクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="09441-753">Controls the action after a data object is dragged-and-dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-754">データオブジェクトハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-754">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-755">ファイルがクリップボードにコピーされた後、またはドロップターゲットをドラッグアンドドロップした後にアクションを制御します。</span><span class="sxs-lookup"><span data-stu-id="09441-755">Controls the action after a file is copied to the clipboard or dragged-and-dropped over a drop target.</span></span> <span data-ttu-id="09441-756">ドロップターゲットには、追加のクリップボード形式を指定できます。</span><span class="sxs-lookup"><span data-stu-id="09441-756">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-757">プロパティシートハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-757">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-758">ページをオブジェクトの [プロパティシート] ダイアログボックスに置換または追加します。</span><span class="sxs-lookup"><span data-stu-id="09441-758">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-759">ヒントハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-759">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-760">マウスをポイントしたときに、項目のフラグとヒントの情報を取得し、ポップアップヒントの中に表示することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-760">Allows retrieving flags and infotip information for an item and displaying it inside a popup tooltip upon mouse- hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-761">列ハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-761">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-762">Windows エクスプローラーの [詳細] ビューでカスタム列の作成と表示を行うことができ <em> </em> ます。</span><span class="sxs-lookup"><span data-stu-id="09441-762">Allows creating and displaying custom columns in Windows Explorer <em>Details view</em>.</span></span> <span data-ttu-id="09441-763">並べ替えとグループ化を拡張するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="09441-763">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-764">プレビューハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-764">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-765">エクスプローラーのプレビューウィンドウにファイルのプレビューが表示されるようにします。</span><span class="sxs-lookup"><span data-stu-id="09441-765">Enables a preview of a file to be displayed in the Windows Explorer Preview Pane.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="09441-766">COM</span><span class="sxs-lookup"><span data-stu-id="09441-766">COM</span></span>

<span data-ttu-id="09441-767">App-v クライアントでは、COM 統合と仮想化のサポートによってアプリケーションの公開がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="09441-767">The App-V Client supports publishing applications with support for COM integration and virtualization.</span></span> <span data-ttu-id="09441-768">COM の統合により、App-v クライアントは、ローカルのオペレーティングシステムとオブジェクトの仮想化に COM オブジェクトを登録することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-768">COM integration allows the App-V Client to register COM objects on the local operating system and virtualization of the objects.</span></span> <span data-ttu-id="09441-769">このドキュメントでは、COM オブジェクトの統合について追加の詳細情報が必要です。</span><span class="sxs-lookup"><span data-stu-id="09441-769">For the purposes of this document, the integration of COM objects requires additional detail.</span></span>

<span data-ttu-id="09441-770">App-v では、プロセス外とインプロセスの2種類のプロセスを使用して、パッケージからローカルオペレーティングシステムへの COM オブジェクトの登録をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="09441-770">App-V supports registering COM objects from the package to the local operating system with two process types: Out-of-process and in-process.</span></span> <span data-ttu-id="09441-771">COM オブジェクトの登録は、オフ、分離、統合された特定のアプリ-V パッケージの複数の操作モードの組み合わせで行われます。</span><span class="sxs-lookup"><span data-stu-id="09441-771">Registering COM objects is accomplished with one or a combination of multiple modes of operation for a specific App-V package that includes off, Isolated, and Integrated.</span></span> <span data-ttu-id="09441-772">統合モードは、アウトプロセスまたはインプロセスのいずれかの種類に対して構成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-772">The integrated mode is configured for either the out-of-process or in-process type.</span></span> <span data-ttu-id="09441-773">COM のモードと型の構成は、動的構成ファイル (deploymentconfig.xml または userconfig.xml) を使用して実現されます。</span><span class="sxs-lookup"><span data-stu-id="09441-773">Configuration of COM modes and types is accomplished with dynamic configuration files (deploymentconfig.xml or userconfig.xml).</span></span>

<span data-ttu-id="09441-774">App-v との統合について詳しくは、次のページをご覧 <https://go.microsoft.com/fwlink/?LinkId=392834> ください。</span><span class="sxs-lookup"><span data-stu-id="09441-774">Details on App-V integration are available at: <https://go.microsoft.com/fwlink/?LinkId=392834>.</span></span>

### <span data-ttu-id="09441-775">ソフトウェアクライアントとアプリケーション機能</span><span class="sxs-lookup"><span data-stu-id="09441-775">Software clients and application capabilities</span></span>

<span data-ttu-id="09441-776">App-v は、仮想化されたアプリケーションをオペレーティングシステムのソフトウェアクライアントに登録するために、特定のソフトウェアクライアントとアプリケーション機能の拡張ポイントをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09441-776">App-V supports specific software clients and application capabilities extension points that enable virtualized applications to be registered with the software client of the operating system.</span></span> <span data-ttu-id="09441-777">これにより、ユーザーは、メール、インスタントメッセージ、メディアプレーヤーなどの操作のための既定のプログラムを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="09441-777">This enables users to select default programs for operations like email, instant messaging, and media player.</span></span> <span data-ttu-id="09441-778">この操作は、コントロールパネルで、[プログラムのアクセスとコンピューターの既定の設定] を使用して実行され、マニフェストまたは動的構成ファイルのシーケンス中に構成されます。</span><span class="sxs-lookup"><span data-stu-id="09441-778">This operation is performed in the control panel with the Set Program Access and Computer Defaults, and configured during sequencing in the manifest or dynamic configuration files.</span></span> <span data-ttu-id="09441-779">アプリケーション機能は、App-v アプリケーションがグローバルに公開されている場合にのみサポートされます。</span><span class="sxs-lookup"><span data-stu-id="09441-779">Application capabilities are only supported when the App-V applications are published globally.</span></span>

<span data-ttu-id="09441-780">App-v ベースのメールクライアントのソフトウェアクライアント登録の例。</span><span class="sxs-lookup"><span data-stu-id="09441-780">Example of software client registration of an App-V based mail client.</span></span>

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

<span data-ttu-id="09441-781">**注** この例では、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="09441-781">**Note** In this example:</span></span>

-   `<ClientConfiguration EmailEnabled="true" />` <span data-ttu-id="09441-782">ソフトウェアクライアント全体がメールクライアントを統合するように設定されている</span><span class="sxs-lookup"><span data-stu-id="09441-782">is the overall Software Clients setting to integrate Email clients</span></span>

-   `<EMail MakeDefault="true">` <span data-ttu-id="09441-783">既定のメールクライアントとして特定のメールクライアントを設定するためのフラグ</span><span class="sxs-lookup"><span data-stu-id="09441-783">is the flag to set a particular Email client as the default Email client</span></span>

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` <span data-ttu-id="09441-784">は MAPI dll の登録です</span><span class="sxs-lookup"><span data-stu-id="09441-784">is the MAPI dll registration</span></span>

 

### <span data-ttu-id="09441-785">URL プロトコルハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-785">URL Protocol handler</span></span>

<span data-ttu-id="09441-786">アプリケーションは、ファイルの種類の呼び出しを利用する、常に仮想化されたアプリケーションとは限りません。</span><span class="sxs-lookup"><span data-stu-id="09441-786">Applications do not always specifically called virtualized applications utilizing file type invocation.</span></span> <span data-ttu-id="09441-787">たとえば、ドキュメントまたは web ページ内の mailto: リンクの埋め込みをサポートしているアプリケーションの場合、ユーザーは mailto: リンクをクリックして、登録されているメールクライアントを取得することを想定しています。</span><span class="sxs-lookup"><span data-stu-id="09441-787">For, example, in an application that supports embedding a mailto: link inside a document or web page, the user clicks on a mailto: link and expects to get their registered mail client.</span></span> <span data-ttu-id="09441-788">App-v では、ローカルオペレーティングシステムでパッケージ単位で登録できる URL プロトコルハンドラーがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="09441-788">App-V supports URL Protocol handlers that can be registered on a per-package basis with the local operating system.</span></span> <span data-ttu-id="09441-789">シーケンス中に、URL プロトコルハンドラーがパッケージに自動的に追加されます。</span><span class="sxs-lookup"><span data-stu-id="09441-789">During sequencing, the URL protocol handlers are automatically added to the package.</span></span>

<span data-ttu-id="09441-790">特定の URL プロトコルハンドラーを登録できるアプリケーションが複数ある場合は、動的な構成ファイルを使用して動作を変更し、プライマリアプリケーションとして起動しないアプリケーションに対してこの機能を抑制または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-790">For situations where there is more than one application that could register the specific URL Protocol handler, the dynamic configuration files can be utilized to modify the behavior and suppress or disable this feature for an application that should not be the primary application launched.</span></span>

### <span data-ttu-id="09441-791">AppPath</span><span class="sxs-lookup"><span data-stu-id="09441-791">AppPath</span></span>

<span data-ttu-id="09441-792">AppPath extension ポイントでは、オペレーティングシステムから直接、App-v アプリケーションの呼び出しをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09441-792">The AppPath extension point supports calling App-V applications directly from the operating system.</span></span> <span data-ttu-id="09441-793">通常、この操作は、オペレーティングシステムによっては、実行可能ファイルへの特定のパスを呼び出すことなく、管理者がオペレーティングシステムのコマンドまたはスクリプトから App-v アプリケーションへのアクセスを提供できるようにするために行われます。</span><span class="sxs-lookup"><span data-stu-id="09441-793">This is typically accomplished from the Run or Start Screen, depending on the operating system, which enables administrators to provide access to App-V applications from operating system commands or scripts without calling the specific path to the executable.</span></span> <span data-ttu-id="09441-794">そのため、公開時に実行されるため、すべてのシステムでシステムパス環境変数を変更する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="09441-794">It therefore avoids modifying the system path environment variable on all systems, as it is accomplished during publishing.</span></span>

<span data-ttu-id="09441-795">AppPath extension point は、マニフェストまたは動的構成ファイルのいずれかで構成され、ユーザーの発行時にローカルコンピューター上のレジストリに格納されます。</span><span class="sxs-lookup"><span data-stu-id="09441-795">The AppPath extension point is configured either in the manifest or in the dynamic configuration files and is stored in the registry on the local machine during publishing for the user.</span></span> <span data-ttu-id="09441-796">AppPath review の詳細については、次の情報を参照 <https://go.microsoft.com/fwlink/?LinkId=392835> してください。</span><span class="sxs-lookup"><span data-stu-id="09441-796">For additional information on AppPath review: <https://go.microsoft.com/fwlink/?LinkId=392835>.</span></span>

### <span data-ttu-id="09441-797">仮想アプリケーション</span><span class="sxs-lookup"><span data-stu-id="09441-797">Virtual application</span></span>

<span data-ttu-id="09441-798">このサブシステムは、シーケンス中にキャプチャされたアプリケーションのリストを提供します。これは通常、他の App-v コンポーネントによって消費されます。</span><span class="sxs-lookup"><span data-stu-id="09441-798">This subsystem provides a list of applications captured during sequencing which is usually consumed by other App-V components.</span></span> <span data-ttu-id="09441-799">動的構成ファイルを使用すると、特定のアプリケーションに属する拡張点の統合を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-799">Integration of extension points belonging to a particular application can be disabled using dynamic configuration files.</span></span> <span data-ttu-id="09441-800">たとえば、2つのアプリケーションがパッケージに含まれている場合は、他のアプリケーションの拡張ポイントとの統合のみを許可するために、1つのアプリケーションに属するすべての拡張機能を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-800">For example, if a package contains two applications, it is possible to disable all extension points belonging to one application, in order to allow only integration of extension points of other application.</span></span>

### <span data-ttu-id="09441-801">拡張ポイントルール</span><span class="sxs-lookup"><span data-stu-id="09441-801">Extension point rules</span></span>

<span data-ttu-id="09441-802">上記で説明した拡張ポイントは、パッケージの公開方法に基づいてオペレーティングシステムに統合されています。</span><span class="sxs-lookup"><span data-stu-id="09441-802">The extension points described above are integrated into the operating system based on how the packages has been published.</span></span> <span data-ttu-id="09441-803">[グローバル発行] では、[公共のコンピューター上の場所] に拡張ポイントが配置されます。ここでは、ユーザーの発行によって、ユーザーの場所に拡張</span><span class="sxs-lookup"><span data-stu-id="09441-803">Global publishing places extension points in public machine locations, where user publishing places extension points in user locations.</span></span> <span data-ttu-id="09441-804">たとえば、デスクトップ上に作成され、グローバルに公開されたショートカットは、ショートカットのファイルデータ (% public% ¥ desktop) とレジストリデータ (HKLM\\Software\\Classes) になります。</span><span class="sxs-lookup"><span data-stu-id="09441-804">For example a shortcut that is created on the desktop and published globally will result in the file data for the shortcut (%Public%\\Desktop) and the registry data (HKLM\\Software\\Classes).</span></span> <span data-ttu-id="09441-805">同じショートカットには、ファイルデータ (%UserProfile%\\Desktop) とレジストリデータ (hkcu¥¥ $ Classes) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="09441-805">The same shortcut would have file data (%UserProfile%\\Desktop) and registry data (HKCU\\Software\\Classes).</span></span>

<span data-ttu-id="09441-806">拡張ポイントは、すべて同じ方法で公開されるわけではありません。一部の拡張ポイントには、グローバル発行が必要であり、他の場合は、特定のオペレーティングシステムやアーキテクチャでの順序付けが必要になります。</span><span class="sxs-lookup"><span data-stu-id="09441-806">Extension points are not all published the same way, where some extension points will require global publishing and others require sequencing on the specific operating system and architecture where they are delivered.</span></span> <span data-ttu-id="09441-807">以下に、これら2つの主要なルールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-807">Below is a table that describes these two key rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="09441-808">仮想拡張機能</span><span class="sxs-lookup"><span data-stu-id="09441-808">Virtual Extension</span></span></th>
<th align="left"><span data-ttu-id="09441-809">ターゲット OS のシーケンスが必要</span><span class="sxs-lookup"><span data-stu-id="09441-809">Requires target OS Sequencing</span></span></th>
<th align="left"><span data-ttu-id="09441-810">グローバル発行が必要</span><span class="sxs-lookup"><span data-stu-id="09441-810">Requires Global Publishing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-811">キー</span><span class="sxs-lookup"><span data-stu-id="09441-811">Shortcut</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-812">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="09441-812">File Type Association</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-813">URL プロトコル</span><span class="sxs-lookup"><span data-stu-id="09441-813">URL Protocols</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-814">○</span><span class="sxs-lookup"><span data-stu-id="09441-814">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-815">AppPaths</span><span class="sxs-lookup"><span data-stu-id="09441-815">AppPaths</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-816">○</span><span class="sxs-lookup"><span data-stu-id="09441-816">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-817">COM モード</span><span class="sxs-lookup"><span data-stu-id="09441-817">COM Mode</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-818">ソフトウェアクライアント</span><span class="sxs-lookup"><span data-stu-id="09441-818">Software Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-819">○</span><span class="sxs-lookup"><span data-stu-id="09441-819">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-820">アプリケーションの機能</span><span class="sxs-lookup"><span data-stu-id="09441-820">Application Capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-821">○</span><span class="sxs-lookup"><span data-stu-id="09441-821">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-822">○</span><span class="sxs-lookup"><span data-stu-id="09441-822">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-823">コンテキストメニューハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-823">Context Menu Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-824">○</span><span class="sxs-lookup"><span data-stu-id="09441-824">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-825">○</span><span class="sxs-lookup"><span data-stu-id="09441-825">X</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-826">ドラッグアンドドロップハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-826">Drag-and-drop Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-827">○</span><span class="sxs-lookup"><span data-stu-id="09441-827">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-828">データオブジェクトハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-828">Data Object Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-829">○</span><span class="sxs-lookup"><span data-stu-id="09441-829">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-830">プロパティシートハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-830">Property Sheet Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-831">○</span><span class="sxs-lookup"><span data-stu-id="09441-831">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-832">ヒントハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-832">Infotip Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-833">○</span><span class="sxs-lookup"><span data-stu-id="09441-833">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-834">列ハンドラー</span><span class="sxs-lookup"><span data-stu-id="09441-834">Column Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-835">○</span><span class="sxs-lookup"><span data-stu-id="09441-835">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-836">シェルの拡張機能</span><span class="sxs-lookup"><span data-stu-id="09441-836">Shell Extensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-837">○</span><span class="sxs-lookup"><span data-stu-id="09441-837">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="09441-838">Browser Helper オブジェクト</span><span class="sxs-lookup"><span data-stu-id="09441-838">Browser Helper Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-839">○</span><span class="sxs-lookup"><span data-stu-id="09441-839">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-840">○</span><span class="sxs-lookup"><span data-stu-id="09441-840">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="09441-841">Active X オブジェクト</span><span class="sxs-lookup"><span data-stu-id="09441-841">Active X Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-842">○</span><span class="sxs-lookup"><span data-stu-id="09441-842">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="09441-843">○</span><span class="sxs-lookup"><span data-stu-id="09441-843">X</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-dynamic-config"></a><span data-ttu-id="09441-844">動的構成処理</span><span class="sxs-lookup"><span data-stu-id="09441-844">Dynamic configuration processing</span></span>


<span data-ttu-id="09441-845">App-v パッケージを1台のコンピューターまたはユーザーに展開するのは非常に簡単です。</span><span class="sxs-lookup"><span data-stu-id="09441-845">Deploying App-V packages to one machine or user is very simple.</span></span> <span data-ttu-id="09441-846">ただし、組織が大量のビジネスラインと地理的および政治的な境界を越えて AppV アプリケーションを展開すると、1つの設定でアプリケーションを1つの方法でシーケンスすることができなくなります。</span><span class="sxs-lookup"><span data-stu-id="09441-846">However, as organizations deploy AppV applications across business lines and geographic and political boundaries, the ability to sequence an application one time with one set of settings becomes impossible.</span></span> <span data-ttu-id="09441-847">App-v は、マニフェストファイルでシーケンス処理中に特定の設定と構成をキャプチャすることに加えて、動的構成ファイルでの変更もサポートするため、このシナリオ向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="09441-847">App-V was designed for this scenario, as it captures specific settings and configurations during sequencing in the Manifest file, but also supports modification with Dynamic Configuration files.</span></span>

<span data-ttu-id="09441-848">App-v の動的構成では、マシンレベルまたはユーザーレベルでパッケージのポリシーを指定することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-848">App-V dynamic configuration allows for specifying a policy for a package either at the machine level or at the user level.</span></span> <span data-ttu-id="09441-849">動的構成ファイルを使用すると、シーケンスエンジニアは、ユーザーまたはコンピューターの個々のグループのニーズに対応するために、パッケージの構成を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="09441-849">The Dynamic Configuration files enable sequencing engineers to modify the configuration of a package, post-sequencing, to address the needs of individual groups of users or machines.</span></span> <span data-ttu-id="09441-850">場合によっては、App-v 環境内で適切な機能を提供するために、アプリケーションの変更が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-850">In some instances it may be necessary to make modifications to the application to provide proper functionality within the App-V environment.</span></span> <span data-ttu-id="09441-851">たとえば、アプリケーションの実行中に特定の操作を実行できるようにするには、\ _ \ \* config.xml ファイルに変更を加える必要がある場合があります。これは、仮想化されたアプリケーションが別のアプリケーションからその拡張機能を上書きしないように mailto 拡張機能を無効にするなどの場合です。</span><span class="sxs-lookup"><span data-stu-id="09441-851">For example, it may be necessary to make modifications to the \_\*config.xml files to allow certain actions to be performed at a specified time during the execution of the application, like disabling a mailto extension to prevent a virtualized application from overwriting that extension from another application.</span></span>

<span data-ttu-id="09441-852">App-v パッケージには、(シーケンス操作の代表者である) appv パッケージファイル内のマニフェストファイルが含まれています。また、動的構成ファイルが特定のパッケージに割り当てられている場合を除き、これらのポリシーが選択されます。</span><span class="sxs-lookup"><span data-stu-id="09441-852">App-V Packages contain the Manifest file inside of the appv package file, which is representative of sequencing operations and is the policy of choice unless Dynamic Configuration files are assigned to a specific package.</span></span> <span data-ttu-id="09441-853">事後処理のために、動的構成ファイルを変更して、さまざまな内線番号を持つ別のデスクトップまたはユーザーにアプリケーションを発行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-853">Post-sequencing, the Dynamic Configuration files can be modified to allow the publishing of an application to different desktops or users with different extension points.</span></span> <span data-ttu-id="09441-854">2つの動的構成ファイルは、動的展開構成 (DDC) と動的ユーザー構成 (DUC) ファイルです。</span><span class="sxs-lookup"><span data-stu-id="09441-854">The two Dynamic Configuration Files are the Dynamic Deployment Configuration (DDC) and Dynamic User Configuration (DUC) files.</span></span> <span data-ttu-id="09441-855">このセクションでは、マニフェストと動的構成ファイルの組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-855">This section focuses on the combination of the manifest and dynamic configuration files.</span></span>

### <span data-ttu-id="09441-856">動的構成ファイルの例</span><span class="sxs-lookup"><span data-stu-id="09441-856">Example for dynamic configuration files</span></span>

<span data-ttu-id="09441-857">次の例では、発行後のマニフェスト、展開構成、ユーザー構成ファイルの組み合わせについて説明します。</span><span class="sxs-lookup"><span data-stu-id="09441-857">The example below shows the combination of the Manifest, Deployment Configuration and User Configuration files after publishing and during normal operation.</span></span> <span data-ttu-id="09441-858">次の例では、各ファイルの簡単な例を示します。</span><span class="sxs-lookup"><span data-stu-id="09441-858">These examples are abbreviated examples of each of the files.</span></span> <span data-ttu-id="09441-859">目的として、ファイルの組み合わせのみが表示され、各ファイルで利用可能な特定のカテゴリについての完全な説明はありません。</span><span class="sxs-lookup"><span data-stu-id="09441-859">The purpose is show the combination of the files only and not to be a complete description of the specific categories available in each of the files.</span></span> <span data-ttu-id="09441-860">詳細については、次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-860">For more information review the App-V 5 Sequencing Guide at:</span></span> <https://go.microsoft.com/fwlink/?LinkID=269810>

**<span data-ttu-id="09441-861">ノート</span><span class="sxs-lookup"><span data-stu-id="09441-861">Manifest</span></span>**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**<span data-ttu-id="09441-862">展開構成</span><span class="sxs-lookup"><span data-stu-id="09441-862">Deployment Configuration</span></span>**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**<span data-ttu-id="09441-863">ユーザー構成</span><span class="sxs-lookup"><span data-stu-id="09441-863">User Configuration</span></span>**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a href="" id="bkmk-sidebyside-assemblies"></a><span data-ttu-id="09441-864">Side-by-side アセンブリ</span><span class="sxs-lookup"><span data-stu-id="09441-864">Side-by-side assemblies</span></span>


<span data-ttu-id="09441-865">App-v は、仮想アプリケーションの発行中にクライアントに対してシーケンス処理と展開を行うときに、side-by-side (SxS) アセンブリの自動パッケージ化をサポートします。</span><span class="sxs-lookup"><span data-stu-id="09441-865">App-V supports the automatic packaging of side-by-side (SxS) assemblies during sequencing and deployment on the client during virtual application publishing.</span></span> <span data-ttu-id="09441-866">App-v 5 SP2 では、シーケンスコンピューターにアセンブリが存在しない場合のシーケンス中の SxS アセンブリのキャプチャがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="09441-866">App-V 5 SP2 supports capturing SxS assemblies during sequencing for assemblies not present on the sequencing machine.</span></span> <span data-ttu-id="09441-867">さらに、Visual C++ (バージョン8以降) と MSXML ランタイムで構成されているアセンブリの場合、Sequencer は、監視中にインストールされていない場合でも、これらの依存関係を自動的に検出してキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="09441-867">And for assemblies consisting of Visual C++ (Version 8 and newer) and/or MSXML run-time, the Sequencer will automatically detect and capture these dependencies even if they were not installed during monitoring.</span></span> <span data-ttu-id="09441-868">Side-by-side アセンブリ機能を使用すると、アプリ-V の以前のバージョンの制限を削除します。これは、シーケンスワークステーションに既に存在するアセンブリをアプリによってキャプチャすることはできません。また、パッケージごとに1つのビットバージョンに制限されているアセンブリを公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="09441-868">The Side by Side assemblies feature removes the limitations of previous versions of App-V, where the App-V Sequencer did not capture assemblies already present on the sequencing workstation, and privatizing the assemblies which limited to one bit version per package.</span></span> <span data-ttu-id="09441-869">この動作では、展開された App-v アプリケーションで、必要な SxS アセンブリが見つからないため、アプリケーションの起動エラーが発生していました。</span><span class="sxs-lookup"><span data-stu-id="09441-869">This behavior resulted in deployed App-V applications to clients missing the required SxS assemblies, causing application launch failures.</span></span> <span data-ttu-id="09441-870">これにより、パッケージ化プロセスを文書化した後、仮想アプリケーションのサポートを確実にするために、パッケージに必要なすべてのアセンブリが、ユーザーのクライアントオペレーティングシステムにローカルにインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-870">This forced the packaging process to document and then ensure that all assemblies required for packages were locally installed on the user’s client operating system to ensure support for the virtual applications.</span></span> <span data-ttu-id="09441-871">このタスクは、アセンブリの数と、必要な依存関係に関するアプリケーションドキュメントがないことに基づいて、管理と実装の両方の課題となっていました。</span><span class="sxs-lookup"><span data-stu-id="09441-871">Based on the number of assemblies and the lack of application documentation for the required dependencies, this task was both a management and implementation challenge.</span></span>

<span data-ttu-id="09441-872">App-v の side by Side Assembly のサポートには、次の機能があります。</span><span class="sxs-lookup"><span data-stu-id="09441-872">Side by Side Assembly support in App-V has the following features.</span></span>

-   <span data-ttu-id="09441-873">アセンブリがシーケンスワークステーションに既にインストールされているかどうかに関係なく、シーケンス中の SxS アセンブリの自動キャプチャ。</span><span class="sxs-lookup"><span data-stu-id="09441-873">Automatic captures of SxS assembly during Sequencing, regardless of whether the assembly was already installed on the sequencing workstation.</span></span>

-   <span data-ttu-id="09441-874">アプリが存在しない場合、App-v クライアントは、要求された SxS アセンブリを発行時にクライアントコンピューターに自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="09441-874">The App-V Client automatically installs required SxS assemblies to the client computer at publishing time when they are not present.</span></span>

-   <span data-ttu-id="09441-875">Sequencer は、Sequencer のレポートメカニズムで VC ランタイム依存関係を報告します。</span><span class="sxs-lookup"><span data-stu-id="09441-875">The Sequencer reports the VC run-time dependency in Sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="09441-876">Sequencer では、Sequencer に既にインストールされているアセンブリを選ぶことはできません。これらのアセンブリがターゲットコンピューターに既にインストールされているシナリオをサポートします。</span><span class="sxs-lookup"><span data-stu-id="09441-876">The Sequencer allows opting to not package the assemblies that are already installed on the Sequencer, supporting scenarios where the assemblies have previously been installed on the target computers.</span></span>

### <span data-ttu-id="09441-877">SxS アセンブリの自動発行</span><span class="sxs-lookup"><span data-stu-id="09441-877">Automatic publishing of SxS assemblies</span></span>

<span data-ttu-id="09441-878">SxS アセンブリを使用して app-v パッケージを発行するときに、App-v クライアントはコンピューター上にアセンブリが存在するかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="09441-878">During publishing of an App-V package with SxS assemblies the App-V Client will check for the presence of the assembly on the machine.</span></span> <span data-ttu-id="09441-879">アセンブリが存在しない場合、クライアントはアセンブリをコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="09441-879">If the assembly does not exist, the client will deploy the assembly to the machine.</span></span> <span data-ttu-id="09441-880">接続グループの一部であるパッケージは、アセンブリインストールに関する情報が接続グループに含まれていないため、基本パッケージの一部である Side-by-side アセンブリインストールに依存します。</span><span class="sxs-lookup"><span data-stu-id="09441-880">Packages that are part of connection groups will rely on the Side by Side assembly installations that are part of the base packages, as the connection group does not contain any information about assembly installation.</span></span>

<span data-ttu-id="09441-881">**注** アセンブリをパッケージ化または削除しても、そのパッケージのアセンブリは削除されません。</span><span class="sxs-lookup"><span data-stu-id="09441-881">**Note** UnPublishing or removing a package with an assembly does not remove the assemblies for that package.</span></span>

 

## <a href="" id="bkmk-client-logging"></a><span data-ttu-id="09441-882">クライアントログ</span><span class="sxs-lookup"><span data-stu-id="09441-882">Client logging</span></span>


<span data-ttu-id="09441-883">App-v クライアントは、標準の ETW 形式で Windows イベントログに情報を記録します。</span><span class="sxs-lookup"><span data-stu-id="09441-883">The App-V client logs information to the Windows Event log in standard ETW format.</span></span> <span data-ttu-id="09441-884">特定の App-v イベントは、[アプリケーションとサービスの Logs\\Microsoft\\AppV\\Client.] の下にあるイベントビューアーで見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="09441-884">The specific App-V events can be found in the event viewer, under Applications and Services Logs\\Microsoft\\AppV\\Client.</span></span>

<span data-ttu-id="09441-885">**注** App-v 5.0 SP3 では、一部のログが統合され、次の場所に移動されました。</span><span class="sxs-lookup"><span data-stu-id="09441-885">**Note** In App-V 5.0 SP3, some logs were consolidated and moved to the following location:</span></span>

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

<span data-ttu-id="09441-886">移動したログの一覧については、「 [app-v 5.0 SP3 につい](about-app-v-50-sp3.md#bkmk-event-logs-moved)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="09441-886">For a list of the moved logs, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

 

<span data-ttu-id="09441-887">以下に記載されている、3つの特定のイベントカテゴリがあります。</span><span class="sxs-lookup"><span data-stu-id="09441-887">There are three specific categories of events recorded described below.</span></span>

<span data-ttu-id="09441-888">[**管理者**]: アプリ-V クライアントに適用される構成のイベントをログに記録し、プライマリ警告とエラーを格納します。</span><span class="sxs-lookup"><span data-stu-id="09441-888">**Admin**: Logs events for configurations being applied to the App-V Client, and contains the primary warnings and errors.</span></span>

<span data-ttu-id="09441-889">**オペレーショナル**: app-v クライアントで完了した app-v 操作の監査ログを作成する、各コンポーネントの一般的なアプリの実行と使用のログを記録します。</span><span class="sxs-lookup"><span data-stu-id="09441-889">**Operational**: Logs the general App-V execution and usage of individual components creating an audit log of the App-V operations that have been completed on the App-V Client.</span></span>

<span data-ttu-id="09441-890">**仮想アプリケーション**: 仮想アプリケーションは、仮想化サブシステムの起動と使用をログに記録します。</span><span class="sxs-lookup"><span data-stu-id="09441-890">**Virtual Application**: Logs virtual application launches and use of virtualization subsystems.</span></span>






 

 





