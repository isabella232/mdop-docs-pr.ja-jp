---
title: OSD ファイルを編集する方法
description: OSD ファイルを編集する方法
author: dansimp
ms.assetid: 0d126ba7-72fb-42ce-982e-90ed01a852c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4a0ff4a8efe1fa177f6847c344add94bca3648cb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817437"
---
# <span data-ttu-id="4f341-103">OSD ファイルを編集する方法</span><span class="sxs-lookup"><span data-stu-id="4f341-103">How to Edit an OSD File</span></span>


<span data-ttu-id="4f341-104">要素または属性を追加または削除して、シーケンス処理されたアプリケーションパッケージのオープンソフトウェア記述子 (OSD) ファイルを変更するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="4f341-104">Use the following procedures to modify a sequenced application package's Open Software Descriptor (OSD) file by adding or deleting an element or an attribute.</span></span>

<span data-ttu-id="4f341-105">**注** 属性を持たない要素もあります。そのため、すべての要素に属性を追加することはできません。</span><span class="sxs-lookup"><span data-stu-id="4f341-105">**Note** Some elements do not have an attribute, so it is not possible to add an attribute to every element.</span></span>

 

<span data-ttu-id="4f341-106">**重要** OSD エディターを使って、.OSD ファイルの名前を変更する場合は、[名前を**付けて保存**] を使用して、変更をプロジェクトファイルに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="4f341-106">**Important** If you use the OSD editor to change the .sft file name, the HREF attribute of the CODEBASE element in the OSD file, you must use the **Save As** command to save the change to the project files.</span></span>

 

**<span data-ttu-id="4f341-107">要素を追加するには</span><span class="sxs-lookup"><span data-stu-id="4f341-107">To add an element</span></span>**

1.  <span data-ttu-id="4f341-108">[ **OSD ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-108">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="4f341-109">ナビゲーションウィンドウで、変更するシーケンス形式のアプリケーションパッケージの OSD ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f341-109">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="4f341-110">ナビゲーションウィンドウで、変更する要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-110">In the navigation pane, right-click the element that you want to modify.</span></span> <span data-ttu-id="4f341-111">メニューで [**要素**] を選択し、[**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-111">On the menu, select **Element** and select **Add**.</span></span>

4.  <span data-ttu-id="4f341-112">メニューから、追加する要素 ( **Codebase**など) を選びます。</span><span class="sxs-lookup"><span data-stu-id="4f341-112">From the menu, select the element you want to add—for example, **Codebase**.</span></span>

5.  <span data-ttu-id="4f341-113">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-113">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="4f341-114">要素を削除するには</span><span class="sxs-lookup"><span data-stu-id="4f341-114">To delete an element</span></span>**

1.  <span data-ttu-id="4f341-115">[ **OSD ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-115">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="4f341-116">ナビゲーションウィンドウで、変更するシーケンス形式のアプリケーションパッケージの OSD ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f341-116">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="4f341-117">ナビゲーションウィンドウで、削除する要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-117">In the navigation pane, right-click the element that you want to delete.</span></span> <span data-ttu-id="4f341-118">メニューの [**要素**] を選択し、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-118">On the menu, select **Element** and select **Delete**.</span></span>

4.  <span data-ttu-id="4f341-119">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-119">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="4f341-120">属性を追加するには</span><span class="sxs-lookup"><span data-stu-id="4f341-120">To add an attribute</span></span>**

1.  <span data-ttu-id="4f341-121">[ **OSD ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-121">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="4f341-122">ナビゲーションウィンドウで、変更するシーケンス形式のアプリケーションパッケージの OSD ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f341-122">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="4f341-123">左側のウィンドウで、属性を追加する要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-123">In the left pane, right-click the element to which you want to add an attribute.</span></span> <span data-ttu-id="4f341-124">メニューで、[**属性**] を選択し、表示されている属性から選択して [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-124">On the menu, select **Attribute** and select **Add**, choosing from the listed available attributes.</span></span>

4.  <span data-ttu-id="4f341-125">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-125">From the **File** menu, select **Save**.</span></span>

**<span data-ttu-id="4f341-126">属性を削除するには</span><span class="sxs-lookup"><span data-stu-id="4f341-126">To delete an attribute</span></span>**

1.  <span data-ttu-id="4f341-127">[ **OSD ファイル**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-127">Click the **OSD File** tab.</span></span>

2.  <span data-ttu-id="4f341-128">ナビゲーションウィンドウで、変更するシーケンス形式のアプリケーションパッケージの OSD ファイルを選びます。</span><span class="sxs-lookup"><span data-stu-id="4f341-128">In the navigation pane, select the sequenced application package's OSD file you want to modify.</span></span>

3.  <span data-ttu-id="4f341-129">ナビゲーションウィンドウで、属性を削除する要素を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="4f341-129">In the navigation pane, right-click the element from which you want to delete an attribute.</span></span> <span data-ttu-id="4f341-130">メニューで、[**属性**] を選択し、[**削除**] を選択して、削除する属性を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-130">On the menu, select **Attribute** and then select **Delete**, choosing the attribute you wish to delete.</span></span>

4.  <span data-ttu-id="4f341-131">[**ファイル**] メニューで、[**保存**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="4f341-131">From the **File** menu, select **Save**.</span></span>

## <span data-ttu-id="4f341-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="4f341-132">Related topics</span></span>


[<span data-ttu-id="4f341-133">[OSD] タブについて</span><span class="sxs-lookup"><span data-stu-id="4f341-133">About the OSD Tab</span></span>](about-the-osd-tab.md)

[<span data-ttu-id="4f341-134">テキスト エディターを使用して OSD ファイルを編集する方法</span><span class="sxs-lookup"><span data-stu-id="4f341-134">How to Edit an OSD File Using a Text Editor</span></span>](how-to-edit-an-osd-file-using-a-text-editor.md)

[<span data-ttu-id="4f341-135">OSD ファイルの要素</span><span class="sxs-lookup"><span data-stu-id="4f341-135">OSD File Elements</span></span>](osd-file-elements.md)

[<span data-ttu-id="4f341-136">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="4f341-136">Sequencer Console</span></span>](sequencer-console.md)

 

 





