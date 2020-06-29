---
title: ファイルの種類の関連付けの結果ウィンドウに表示される列
description: ファイルの種類の関連付けの結果ウィンドウに表示される列
author: dansimp
ms.assetid: eab48e20-9c92-459d-a06b-8e20202d73f6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 244c0cbcec7e4601dfbcface34ac28c23433a1bd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821584"
---
# <span data-ttu-id="6d148-103">ファイルの種類の関連付けの結果ウィンドウに表示される列</span><span class="sxs-lookup"><span data-stu-id="6d148-103">File Type Association Results Pane Columns</span></span>


<span data-ttu-id="6d148-104">Application Virtualization クライアント管理コンソールでは、[**ファイルの関連付け**] ノードの**結果**ウィンドウにさまざまな列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="6d148-104">In the Application Virtualization Client Management Console, the **Results** pane of the **File Associations** node can display a variety of columns.</span></span> <span data-ttu-id="6d148-105">既定では、**拡張機能**、**説明**、**アプリケーション**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d148-105">**Extension**, **Description**, and **Application** are shown by default.</span></span>

<span data-ttu-id="6d148-106">**注** 列を追加または削除するには、[**結果**] ウィンドウで右クリックし、[**表示**]、[**列の追加と削除**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="6d148-106">**Note** You can add or remove a column simply by right-clicking in the **Results** pane, selecting **View**, then selecting **Add/Remove Columns**.</span></span>

 

<span data-ttu-id="6d148-107">リストは、任意の列によって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="6d148-107">The list can be sorted by any of the columns.</span></span> <span data-ttu-id="6d148-108">日付と時刻を含む列は、昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="6d148-108">Columns that contain dates and times are sorted in chronological order, not alphabetical.</span></span> <span data-ttu-id="6d148-109">日付と時刻が混在し、テキストが含まれている列の場合、日付と時刻は、他のテキストの前にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="6d148-109">For columns that contain a mix of dates and times and text, dates and times are considered to come before any other text.</span></span>

<span data-ttu-id="6d148-110">使用可能な列名には、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d148-110">The available column names contain the following elements.</span></span>

<a href="" id="extension"></a>**<span data-ttu-id="6d148-111">拡張機能</span><span class="sxs-lookup"><span data-stu-id="6d148-111">Extension</span></span>**  
<span data-ttu-id="6d148-112">ドキュメントや HTML などの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="6d148-112">The extension, such as DOC or HTML.</span></span> <span data-ttu-id="6d148-113">これは、リストを整理するためのフィールドであるため、各拡張子はリストに1回表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d148-113">This is the field by which the list is organized, so each extension is displayed once on the list.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="6d148-114">説明</span><span class="sxs-lookup"><span data-stu-id="6d148-114">Description</span></span>**  
<span data-ttu-id="6d148-115">説明またはユーザーフレンドリ名。</span><span class="sxs-lookup"><span data-stu-id="6d148-115">The description or user-friendly name.</span></span>

<a href="" id="application"></a>**<span data-ttu-id="6d148-116">Application</span><span class="sxs-lookup"><span data-stu-id="6d148-116">Application</span></span>**  
<span data-ttu-id="6d148-117">このファイルの種類の既定のアクションに関連付けられているアプリケーションの名前とバージョン。</span><span class="sxs-lookup"><span data-stu-id="6d148-117">The name and version of the application associated with the default action of this file type.</span></span>

<a href="" id="parameters"></a>**<span data-ttu-id="6d148-118">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6d148-118">Parameters</span></span>**  
<span data-ttu-id="6d148-119">既定のアクションのパラメーター。</span><span class="sxs-lookup"><span data-stu-id="6d148-119">The parameters for the default action.</span></span>

<a href="" id="default-action"></a>**<span data-ttu-id="6d148-120">既定のアクション</span><span class="sxs-lookup"><span data-stu-id="6d148-120">Default Action</span></span>**  
<span data-ttu-id="6d148-121">既定のアクションの名前。</span><span class="sxs-lookup"><span data-stu-id="6d148-121">The name of the default action.</span></span>

<a href="" id="dde"></a>**<span data-ttu-id="6d148-122">DDE</span><span class="sxs-lookup"><span data-stu-id="6d148-122">DDE</span></span>**  
<span data-ttu-id="6d148-123">既定のアクションに対して動的データ交換 (DDE) が有効になっているかどうかに応じて、[**有効**] または [**無効**] が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6d148-123">Displays **Enabled** or **Disabled** depending on whether Dynamic Data Exchange (DDE) is enabled for the default action.</span></span>

<a href="" id="linked-extensions"></a>**<span data-ttu-id="6d148-124">リンクされた拡張機能</span><span class="sxs-lookup"><span data-stu-id="6d148-124">Linked Extensions</span></span>**  
<span data-ttu-id="6d148-125">同じ型に関連付けられている他の拡張子のコンマ区切りのリスト。</span><span class="sxs-lookup"><span data-stu-id="6d148-125">A comma-separated list of other extensions that are associated with the same type.</span></span>

<a href="" id="confirm-open"></a>**<span data-ttu-id="6d148-126">開いていることを確認する</span><span class="sxs-lookup"><span data-stu-id="6d148-126">Confirm Open</span></span>**  
<span data-ttu-id="6d148-127">[**ダウンロード後にファイルを開く**] が選択されているかどうかに応じて、"はい" または "**いいえ** **"**</span><span class="sxs-lookup"><span data-stu-id="6d148-127">Displays **Yes** or **No** depending on whether **Confirm open after download** is selected.</span></span>

<a href="" id="always-show"></a>**<span data-ttu-id="6d148-128">常に表示</span><span class="sxs-lookup"><span data-stu-id="6d148-128">Always Show</span></span>**  
<span data-ttu-id="6d148-129">[**常に表示する**] が選択されているかどうかによって [**はい]** または [**いいえ**] と表示</span><span class="sxs-lookup"><span data-stu-id="6d148-129">Displays **Yes** or **No** depending on whether **Always show extension** is selected.</span></span>

<a href="" id="shell-new"></a>**<span data-ttu-id="6d148-130">シェルの新規作成</span><span class="sxs-lookup"><span data-stu-id="6d148-130">Shell New</span></span>**  
<span data-ttu-id="6d148-131">シェルの [**新規**] メニューに拡張機能を追加するかどうかに応じて、 **[はい]** または [**いいえ**] を表示します。</span><span class="sxs-lookup"><span data-stu-id="6d148-131">Displays **Yes** or **No** depending on whether the extension is added to the shell’s **New** menu.</span></span>

<a href="" id="applies-to"></a>**<span data-ttu-id="6d148-132">適用対象</span><span class="sxs-lookup"><span data-stu-id="6d148-132">Applies To</span></span>**  
<span data-ttu-id="6d148-133">ユーザーまたはコンピューター全体の関連付けのどちらであるかに応じて、**ユーザー**または**コンピューター**を表示します。</span><span class="sxs-lookup"><span data-stu-id="6d148-133">Displays **User** or **Computer** depending on whether this is a user-specific or computer-wide association.</span></span>

<a href="" id="icon-file"></a>**<span data-ttu-id="6d148-134">アイコンファイル</span><span class="sxs-lookup"><span data-stu-id="6d148-134">Icon File</span></span>**  
<span data-ttu-id="6d148-135">アイコンファイルの元の名前。</span><span class="sxs-lookup"><span data-stu-id="6d148-135">The original name of the icon file.</span></span>

<a href="" id="icon-path"></a>**<span data-ttu-id="6d148-136">アイコンのパス</span><span class="sxs-lookup"><span data-stu-id="6d148-136">Icon Path</span></span>**  
<span data-ttu-id="6d148-137">アイコンファイルの元のパスまたは URL。</span><span class="sxs-lookup"><span data-stu-id="6d148-137">The original path or URL for the icon file.</span></span>

<a href="" id="cached-icon-file"></a>**<span data-ttu-id="6d148-138">キャッシュアイコンファイル</span><span class="sxs-lookup"><span data-stu-id="6d148-138">Cached Icon File</span></span>**  
<span data-ttu-id="6d148-139">キャッシュ内のアイコンファイルの名前 (現在の実装の GUID)。</span><span class="sxs-lookup"><span data-stu-id="6d148-139">The name of the icon files in cache (which is a GUID in the current implementation).</span></span>

<a href="" id="cached-icon-path"></a>**<span data-ttu-id="6d148-140">キャッシュされたアイコンのパス</span><span class="sxs-lookup"><span data-stu-id="6d148-140">Cached Icon Path</span></span>**  
<span data-ttu-id="6d148-141">キャッシュ内のアイコンファイルの完全なパスです。</span><span class="sxs-lookup"><span data-stu-id="6d148-141">The full path to the icon files in cache.</span></span>

<a href="" id="content-type"></a>**<span data-ttu-id="6d148-142">コンテンツの種類</span><span class="sxs-lookup"><span data-stu-id="6d148-142">Content Type</span></span>**  
<span data-ttu-id="6d148-143">コンテンツタイプ。</span><span class="sxs-lookup"><span data-stu-id="6d148-143">The content type.</span></span>

<a href="" id="perceived-type"></a>**<span data-ttu-id="6d148-144">認識型</span><span class="sxs-lookup"><span data-stu-id="6d148-144">Perceived Type</span></span>**  
<span data-ttu-id="6d148-145">認識された型または空白。</span><span class="sxs-lookup"><span data-stu-id="6d148-145">The perceived type or blank.</span></span>

## <span data-ttu-id="6d148-146">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6d148-146">Related topics</span></span>


[<span data-ttu-id="6d148-147">ファイルの種類の関連付けノード</span><span class="sxs-lookup"><span data-stu-id="6d148-147">File Type Associations Node</span></span>](file-type-associations-node-client.md)

[<span data-ttu-id="6d148-148">ファイルの種類の関連付けの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="6d148-148">File Type Association Results Pane</span></span>](file-type-association-results-pane.md)

 

 





