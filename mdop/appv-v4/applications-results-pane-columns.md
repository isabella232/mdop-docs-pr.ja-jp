---
title: アプリケーションの結果ウィンドウの列
description: アプリケーションの結果ウィンドウの列
author: dansimp
ms.assetid: abae5ce2-40df-4f47-8062-f5eb6295c88c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c0138e40647a6a7d131a08aa03a9c9c1fcb071b3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819497"
---
# <span data-ttu-id="3f952-103">アプリケーションの結果ウィンドウの列</span><span class="sxs-lookup"><span data-stu-id="3f952-103">Applications Results Pane Columns</span></span>


<span data-ttu-id="3f952-104">Application Virtualization クライアント管理コンソールの [**アプリケーション**] ノードの**結果**ウィンドウには、さまざまな列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="3f952-104">The **Results** pane of the **Applications** node in the Application Virtualization Client Management Console can display a variety of columns.</span></span> <span data-ttu-id="3f952-105">**アプリケーション**、**実行中**、**ロック**済み、**パッケージの状態**が既定で表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f952-105">**Application**, **Running**, **Locked**, and **Package Status** are shown by default.</span></span>

<span data-ttu-id="3f952-106">**注** 列を追加または削除するには、[**結果**] ウィンドウで右クリックし、[**表示**] を選択して、[**列の追加と削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="3f952-106">**Note** You can add or remove columns by right-clicking in the **Results** pane, selecting **View**, and then selecting **Add/Remove Columns**.</span></span>

 

<span data-ttu-id="3f952-107">リストは、任意の列によって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="3f952-107">The list can be sorted by any column.</span></span> <span data-ttu-id="3f952-108">日付と時刻を含む列は、昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="3f952-108">Columns that contain dates and times are sorted in chronological order, not alphabetical.</span></span> <span data-ttu-id="3f952-109">日付と時刻が混在し、テキストが含まれている列の場合、日付と時刻は、他のテキストの前にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="3f952-109">For columns that contain a mix of dates and times and text, dates and times are considered to come before any other text.</span></span>

<span data-ttu-id="3f952-110">次の列を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3f952-110">The following columns are available.</span></span>

<a href="" id="application"></a>**<span data-ttu-id="3f952-111">Application</span><span class="sxs-lookup"><span data-stu-id="3f952-111">Application</span></span>**  
<span data-ttu-id="3f952-112">アプリケーション名とバージョンを、スペースで区切って指定します。</span><span class="sxs-lookup"><span data-stu-id="3f952-112">The application name and version, separated by a space.</span></span>

<a href="" id="application-in-use"></a>**<span data-ttu-id="3f952-113">使用中のアプリケーション</span><span class="sxs-lookup"><span data-stu-id="3f952-113">Application In Use</span></span>**  
<span data-ttu-id="3f952-114">いずれかのユーザーがアプリケーションを使用しているか (つまり、それを実行しているか読み込み中か) に応じて、 **[はい]** または [**いいえ**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="3f952-114">Displays **Yes** or **No** depending on whether any user is using the application (that is, running it or loading it).</span></span>

<a href="" id="app-virt-server"></a>**<span data-ttu-id="3f952-115">App Virt Server</span><span class="sxs-lookup"><span data-stu-id="3f952-115">App Virt Server</span></span>**  
<span data-ttu-id="3f952-116">パッケージがストリーミングされた Application Virtualization server。</span><span class="sxs-lookup"><span data-stu-id="3f952-116">The Application Virtualization server from which the package was streamed.</span></span>

<a href="" id="cached-icon-file"></a>**<span data-ttu-id="3f952-117">キャッシュアイコンファイル</span><span class="sxs-lookup"><span data-stu-id="3f952-117">Cached Icon File</span></span>**  
<span data-ttu-id="3f952-118">キャッシュ内のアイコンファイルの名前 (現在の実装の GUID)。</span><span class="sxs-lookup"><span data-stu-id="3f952-118">The name of the icon files in cache (a GUID in the current implementation).</span></span>

<a href="" id="cached-icon-path"></a>**<span data-ttu-id="3f952-119">キャッシュされたアイコンのパス</span><span class="sxs-lookup"><span data-stu-id="3f952-119">Cached Icon Path</span></span>**  
<span data-ttu-id="3f952-120">キャッシュ内のアイコンファイルの完全なパスです。</span><span class="sxs-lookup"><span data-stu-id="3f952-120">The full path to the icon files in cache.</span></span>

<a href="" id="cached-launch-percent"></a>**<span data-ttu-id="3f952-121">キャッシュされた起動の割合</span><span class="sxs-lookup"><span data-stu-id="3f952-121">Cached Launch Percent</span></span>**  
<span data-ttu-id="3f952-122">アプリケーションの起動データの現在のキャッシュ内の割合。</span><span class="sxs-lookup"><span data-stu-id="3f952-122">The percentage of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-launch-size--mb-"></a>**<span data-ttu-id="3f952-123">キャッシュされた起動サイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="3f952-123">Cached Launch Size (MB)</span></span>**  
<span data-ttu-id="3f952-124">アプリケーションの起動データ (現在キャッシュ内) の量。</span><span class="sxs-lookup"><span data-stu-id="3f952-124">The amount of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-osd-file"></a>**<span data-ttu-id="3f952-125">キャッシュされた OSD ファイル</span><span class="sxs-lookup"><span data-stu-id="3f952-125">Cached OSD File</span></span>**  
<span data-ttu-id="3f952-126">キャッシュ内の OSD ファイルの名前 (現在の実装の GUID)。</span><span class="sxs-lookup"><span data-stu-id="3f952-126">The name of the OSD file in the cache (which is a GUID in the current implementation).</span></span>

<a href="" id="cached-osd-path"></a>**<span data-ttu-id="3f952-127">キャッシュされた OSD パス</span><span class="sxs-lookup"><span data-stu-id="3f952-127">Cached OSD Path</span></span>**  
<span data-ttu-id="3f952-128">キャッシュ内の OSD ファイルへの完全パス。</span><span class="sxs-lookup"><span data-stu-id="3f952-128">The full path to the OSD file in the cache.</span></span>

<a href="" id="cached-package-percent"></a>**<span data-ttu-id="3f952-129">キャッシュされたパッケージの割合</span><span class="sxs-lookup"><span data-stu-id="3f952-129">Cached Package Percent</span></span>**  
<span data-ttu-id="3f952-130">現在キャッシュ内にあるパッケージの割合。</span><span class="sxs-lookup"><span data-stu-id="3f952-130">The percentage of the package currently in cache.</span></span>

<a href="" id="cached-package-size--mb-"></a>**<span data-ttu-id="3f952-131">キャッシュされたパッケージサイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="3f952-131">Cached Package Size (MB)</span></span>**  
<span data-ttu-id="3f952-132">現在キャッシュ内にあるパッケージの部分のサイズです。</span><span class="sxs-lookup"><span data-stu-id="3f952-132">The size of the portion of the package currently in cache.</span></span>

<a href="" id="icon-file"></a>**<span data-ttu-id="3f952-133">アイコンファイル</span><span class="sxs-lookup"><span data-stu-id="3f952-133">Icon File</span></span>**  
<span data-ttu-id="3f952-134">アイコンファイルの元の名前。</span><span class="sxs-lookup"><span data-stu-id="3f952-134">The original name of the icon file.</span></span>

<a href="" id="icon-path"></a>**<span data-ttu-id="3f952-135">アイコンのパス</span><span class="sxs-lookup"><span data-stu-id="3f952-135">Icon Path</span></span>**  
<span data-ttu-id="3f952-136">アイコンファイルの元のパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="3f952-136">The original path or URL for the icon file.</span></span>

<a href="" id="last-system-launch"></a>**<span data-ttu-id="3f952-137">最終システム起動</span><span class="sxs-lookup"><span data-stu-id="3f952-137">Last System Launch</span></span>**  
<span data-ttu-id="3f952-138">システムによって最後にアプリケーションが起動された時刻。</span><span class="sxs-lookup"><span data-stu-id="3f952-138">The last time the application was launched by the system.</span></span>

<a href="" id="last-user-launch"></a>**<span data-ttu-id="3f952-139">前回のユーザー起動</span><span class="sxs-lookup"><span data-stu-id="3f952-139">Last User Launch</span></span>**  
<span data-ttu-id="3f952-140">ユーザーが最後にアプリケーションを起動した時刻。</span><span class="sxs-lookup"><span data-stu-id="3f952-140">The last time the application was launched by the user.</span></span>

<a href="" id="launch-size--mb-"></a>**<span data-ttu-id="3f952-141">起動サイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="3f952-141">Launch Size (MB)</span></span>**  
<span data-ttu-id="3f952-142">アプリケーションを起動するために必要なパッケージデータの未圧縮サイズ。</span><span class="sxs-lookup"><span data-stu-id="3f952-142">The uncompressed size of the package data needed to launch the application.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="3f952-143">ロック</span><span class="sxs-lookup"><span data-stu-id="3f952-143">Locked</span></span>**  
<span data-ttu-id="3f952-144">アプリケーションのパッケージがキャッシュ内でロックされているかどうかに応じて、 **[はい]** または [**いいえ**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="3f952-144">Displays **Yes** or **No** depending on whether the application’s package is locked in the cache.</span></span>

<a href="" id="name"></a>**<span data-ttu-id="3f952-145">名前</span><span class="sxs-lookup"><span data-stu-id="3f952-145">Name</span></span>**  
<span data-ttu-id="3f952-146">アプリケーション名。</span><span class="sxs-lookup"><span data-stu-id="3f952-146">The application name.</span></span>

<a href="" id="osd-file"></a>**<span data-ttu-id="3f952-147">OSD ファイル</span><span class="sxs-lookup"><span data-stu-id="3f952-147">OSD File</span></span>**  
<span data-ttu-id="3f952-148">オープンソフトウェア記述子 (OSD) ファイルの元の名前。</span><span class="sxs-lookup"><span data-stu-id="3f952-148">The original name of the Open Software Descriptor (OSD) file.</span></span>

<a href="" id="osd-path"></a>**<span data-ttu-id="3f952-149">OSD パス</span><span class="sxs-lookup"><span data-stu-id="3f952-149">OSD Path</span></span>**  
<span data-ttu-id="3f952-150">OSD ファイルの完全な元のパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="3f952-150">The full original path or URL to the OSD file.</span></span>

<a href="" id="package-name"></a>**<span data-ttu-id="3f952-151">パッケージ名</span><span class="sxs-lookup"><span data-stu-id="3f952-151">Package Name</span></span>**  
<span data-ttu-id="3f952-152">パッケージの名前。</span><span class="sxs-lookup"><span data-stu-id="3f952-152">The name of the package.</span></span>

<a href="" id="package-guid"></a>**<span data-ttu-id="3f952-153">パッケージ GUID</span><span class="sxs-lookup"><span data-stu-id="3f952-153">Package GUID</span></span>**  
<span data-ttu-id="3f952-154">パッケージの GUID です。</span><span class="sxs-lookup"><span data-stu-id="3f952-154">The GUID for the package.</span></span>

<a href="" id="package-size--mb-"></a>**<span data-ttu-id="3f952-155">パッケージのサイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="3f952-155">Package Size (MB)</span></span>**  
<span data-ttu-id="3f952-156">パッケージ内の圧縮されていないデータの合計サイズ。</span><span class="sxs-lookup"><span data-stu-id="3f952-156">The total size of the uncompressed data in the package.</span></span>

<a href="" id="package-status"></a>**<span data-ttu-id="3f952-157">パッケージの状態</span><span class="sxs-lookup"><span data-stu-id="3f952-157">Package Status</span></span>**  
<span data-ttu-id="3f952-158">パッケージの現在の動作状態。</span><span class="sxs-lookup"><span data-stu-id="3f952-158">The current operational status of the package.</span></span>

<a href="" id="package-url"></a>**<span data-ttu-id="3f952-159">パッケージ URL</span><span class="sxs-lookup"><span data-stu-id="3f952-159">Package URL</span></span>**  
<span data-ttu-id="3f952-160">パッケージの URL です。</span><span class="sxs-lookup"><span data-stu-id="3f952-160">The URL for the package.</span></span>

<a href="" id="package-version"></a>**<span data-ttu-id="3f952-161">パッケージバージョン</span><span class="sxs-lookup"><span data-stu-id="3f952-161">Package Version</span></span>**  
<span data-ttu-id="3f952-162">パッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3f952-162">The version for the package.</span></span>

<a href="" id="package-version-guid"></a>**<span data-ttu-id="3f952-163">パッケージバージョン GUID</span><span class="sxs-lookup"><span data-stu-id="3f952-163">Package Version GUID</span></span>**  
<span data-ttu-id="3f952-164">パッケージバージョンの GUID です。</span><span class="sxs-lookup"><span data-stu-id="3f952-164">The GUID for the package version.</span></span>

<a href="" id="running"></a>**<span data-ttu-id="3f952-165">Running</span><span class="sxs-lookup"><span data-stu-id="3f952-165">Running</span></span>**  
<span data-ttu-id="3f952-166">現在のユーザーがアプリケーションを実行しているかどうかによって **[はい]** または [**いいえ**] と表示されます。</span><span class="sxs-lookup"><span data-stu-id="3f952-166">Displays **Yes** or **No** depending on whether the current user is running the application.</span></span>

<a href="" id="source"></a>**<span data-ttu-id="3f952-167">Source</span><span class="sxs-lookup"><span data-stu-id="3f952-167">Source</span></span>**  
<span data-ttu-id="3f952-168">アプリケーションが登場した場所: アプリケーション発行サーバーの名前か、OSD ファイルから直接追加されたアプリケーションの場合は "Local"。</span><span class="sxs-lookup"><span data-stu-id="3f952-168">Where the application came from—either the name of an application publishing server or "Local" for applications added from OSD files directly.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="3f952-169">バージョン</span><span class="sxs-lookup"><span data-stu-id="3f952-169">Version</span></span>**  
<span data-ttu-id="3f952-170">アプリケーションのバージョン。</span><span class="sxs-lookup"><span data-stu-id="3f952-170">The application version.</span></span>

## <span data-ttu-id="3f952-171">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3f952-171">Related topics</span></span>


[<span data-ttu-id="3f952-172">アプリケーション ノード</span><span class="sxs-lookup"><span data-stu-id="3f952-172">Applications Node</span></span>](applications-node.md)

[<span data-ttu-id="3f952-173">アプリケーションの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="3f952-173">Applications Results Pane</span></span>](applications-results-pane.md)

[<span data-ttu-id="3f952-174">Application Virtualization Client Management Console リファレンス</span><span class="sxs-lookup"><span data-stu-id="3f952-174">Application Virtualization Client Management Console Reference</span></span>](application-virtualization-client-management-console-reference.md)

 

 





