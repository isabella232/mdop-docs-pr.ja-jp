---
title: '[除外項目] タブ'
description: '[除外項目] タブ'
author: dansimp
ms.assetid: 864e46dd-3d6e-4a1b-acf4-9dc00548117e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0f472fb61c121a1977c3c4ff927bd1ba6f680d86
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821577"
---
# <span data-ttu-id="750f7-103">[除外項目] タブ</span><span class="sxs-lookup"><span data-stu-id="750f7-103">Exclusion Items Tab</span></span>


<span data-ttu-id="750f7-104">[**除外項目**] タブには、Application Virtualization Sequencer が仮想ファイルシステムまたは仮想レジストリから除外した式が表示されます。</span><span class="sxs-lookup"><span data-stu-id="750f7-104">The **Exclusion Items** tab displays the expressions that the Application Virtualization Sequencer excludes from the virtual file system or virtual registry.</span></span> <span data-ttu-id="750f7-105">これらの式は、シーケンス付きのアプリケーションパッケージをアプリケーションの仮想化デスクトップクライアントで実行できるようにするために除外されます。</span><span class="sxs-lookup"><span data-stu-id="750f7-105">These expressions are excluded to ensure that the sequenced application package can run on Application Virtualization Desktop Clients.</span></span> <span data-ttu-id="750f7-106">また、シーケンスで望ましくない可能性のある、標準以外のインストールディレクトリを除外することもできます。</span><span class="sxs-lookup"><span data-stu-id="750f7-106">You can also exclude non-standard installation directories that might be unwanted in the sequencing.</span></span>

<span data-ttu-id="750f7-107">このタブには、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="750f7-107">This tab contains the following elements.</span></span>

<a href="" id="exclude-path"></a>**<span data-ttu-id="750f7-108">除外パス</span><span class="sxs-lookup"><span data-stu-id="750f7-108">Exclude Path</span></span>**  
<span data-ttu-id="750f7-109">仮想ファイルシステム項目または仮想レジストリ項目の解析中に検出された場合に、Sequencer が除外する変数名を表示します。</span><span class="sxs-lookup"><span data-stu-id="750f7-109">Displays variable names that the Sequencer excludes if encountered while parsing virtual file system items or virtual registry items.</span></span>

<a href="" id="resolves-to"></a>**<span data-ttu-id="750f7-110">に解決されます</span><span class="sxs-lookup"><span data-stu-id="750f7-110">Resolves To</span></span>**  
<span data-ttu-id="750f7-111">Sequencer 変数に対応する実際のパスを表示します。</span><span class="sxs-lookup"><span data-stu-id="750f7-111">Displays the actual paths that correspond to the Sequencer variables.</span></span>

<a href="" id="map-type"></a>**<span data-ttu-id="750f7-112">マップの種類</span><span class="sxs-lookup"><span data-stu-id="750f7-112">Map Type</span></span>**  
<span data-ttu-id="750f7-113">仮想ファイルシステムまたは仮想レジストリ内の項目を解析するために Sequencer が適用するマッピング規則を表示します。</span><span class="sxs-lookup"><span data-stu-id="750f7-113">Displays mapping rules that the Sequencer applies to parse items in the virtual file system or virtual registry.</span></span> <span data-ttu-id="750f7-114">次のいずれかの値が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="750f7-114">One of the following values can occur:</span></span>

<a href="" id="new"></a>**<span data-ttu-id="750f7-115">新規</span><span class="sxs-lookup"><span data-stu-id="750f7-115">New</span></span>**  
<span data-ttu-id="750f7-116">新しい除外項目を入力するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-116">Click to enter a new exclusion item.</span></span>

<a href="" id="edit"></a>**<span data-ttu-id="750f7-117">Edit</span><span class="sxs-lookup"><span data-stu-id="750f7-117">Edit</span></span>**  
<span data-ttu-id="750f7-118">選択した除外を編集するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-118">Click to edit a selected exclusion.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="750f7-119">Delete</span><span class="sxs-lookup"><span data-stu-id="750f7-119">Delete</span></span>**  
<span data-ttu-id="750f7-120">選択した除外を削除するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-120">Click to remove a selected exclusion.</span></span>

<a href="" id="save-as-default"></a>**<span data-ttu-id="750f7-121">既定値として保存</span><span class="sxs-lookup"><span data-stu-id="750f7-121">Save As Default</span></span>**  
<span data-ttu-id="750f7-122">現在の除外項目を既定値として保存するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-122">Click to save the current exclusion items as your default.</span></span>

<a href="" id="restore-defaults"></a>**<span data-ttu-id="750f7-123">既定値に戻す</span><span class="sxs-lookup"><span data-stu-id="750f7-123">Restore Defaults</span></span>**  
<span data-ttu-id="750f7-124">既定の割り当て済みの除外アイテムを復元し、追加したアイテムを削除するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-124">Click to restore default-assigned exclusion items and remove any items you added.</span></span>

<a href="" id="ok"></a>**<span data-ttu-id="750f7-125">OK</span><span class="sxs-lookup"><span data-stu-id="750f7-125">OK</span></span>**  
<span data-ttu-id="750f7-126">これをクリックして、表示される例外を受け入れます。</span><span class="sxs-lookup"><span data-stu-id="750f7-126">Click to accept the displayed exceptions.</span></span>

<a href="" id="cancel"></a>**<span data-ttu-id="750f7-127">Cancel</span><span class="sxs-lookup"><span data-stu-id="750f7-127">Cancel</span></span>**  
<span data-ttu-id="750f7-128">変更を取り消すには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="750f7-128">Click to cancel any changes you have made.</span></span>

## <span data-ttu-id="750f7-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="750f7-129">Related topics</span></span>


[<span data-ttu-id="750f7-130">Application Virtualization Sequencer [オプション] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="750f7-130">Application Virtualization Sequencer Options Dialog Box</span></span>](application-virtualization-sequencer-options-dialog-box.md)

[<span data-ttu-id="750f7-131">[除外項目] ダイアログ ボックス</span><span class="sxs-lookup"><span data-stu-id="750f7-131">Exclusion Item Dialog Box</span></span>](exclusion-item-dialog-box.md)

 

 





