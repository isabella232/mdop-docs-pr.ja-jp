---
title: 公開サーバー ノード
description: 公開サーバー ノード
author: dansimp
ms.assetid: b5823c6c-15bc-4e8d-aeeb-acc366ffedd1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c001e246c63919773d29a2317d5a43937c0813f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815797"
---
# <span data-ttu-id="71428-103">公開サーバー ノード</span><span class="sxs-lookup"><span data-stu-id="71428-103">Publishing Servers Node</span></span>


<span data-ttu-id="71428-104">[**発行サーバー** ] ノードは、Application Virtualization クライアント管理コンソールの**スコープ**ウィンドウの [ **application virtualization** ] ノードの1つ下のレベルにあります。</span><span class="sxs-lookup"><span data-stu-id="71428-104">The **Publishing Servers** node is one level below the **Application Virtualization** node in the **Scope** pane of the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="71428-105">このノードを選択すると、[**結果**] ウィンドウに発行サーバーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="71428-105">When you select this node, the **Results** pane displays a list of publishing servers.</span></span>

<span data-ttu-id="71428-106">[**発行サーバー** ] ノードを右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="71428-106">Right-click the **Publishing Servers** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-server"></a>**<span data-ttu-id="71428-107">新しいサーバー</span><span class="sxs-lookup"><span data-stu-id="71428-107">New Server</span></span>**  
<span data-ttu-id="71428-108">このメニュー項目によって、新しいサーバーウィザードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="71428-108">This menu item displays the New Server Wizard.</span></span> <span data-ttu-id="71428-109">このウィザードは、次の2つのページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="71428-109">This wizard consists of two pages:</span></span>

1.  <span data-ttu-id="71428-110">サーバーの表示名とサーバーの種類を入力します。</span><span class="sxs-lookup"><span data-stu-id="71428-110">Enter a server display name and server type:</span></span>

    -   <span data-ttu-id="71428-111">[**表示名**: サーバーに対して表示する名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="71428-111">**Display Name**—Enter a name that you want displayed for the server.</span></span> <span data-ttu-id="71428-112">既定では、このフィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="71428-112">This field is blank by default.</span></span>

    -   <span data-ttu-id="71428-113">[ **Type**]: サーバーの種類のドロップダウンリストからサーバーの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="71428-113">**Type**—Choose the server type from the drop-down list of server types.</span></span>

2.  <span data-ttu-id="71428-114">サーバーの接続設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="71428-114">Specify the connection settings for the server:</span></span>

    -   <span data-ttu-id="71428-115">[ **Host name (ホスト名) 名**: サーバーの名前または IP アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="71428-115">**Host Name**—Enter the name or IP address for the server.</span></span>

    -   <span data-ttu-id="71428-116">[ **Port (ポート**) 数-ポート番号に対応する数値を入力します。</span><span class="sxs-lookup"><span data-stu-id="71428-116">**Port**—Enter a numeric value that corresponds to the port number.</span></span> <span data-ttu-id="71428-117">サーバーの種類が "Application Virtualization Server" である場合、既定値は554、サーバーの種類が "標準 HTTP サーバー" の場合は80です。</span><span class="sxs-lookup"><span data-stu-id="71428-117">The default value is 554 if the server type is "Application Virtualization Server" and 80 if the server type is "Standard HTTP Server."</span></span>

    -   <span data-ttu-id="71428-118">**Path**: サーバーの種類が "Application virtualization server" または "Enhanced Security Application virtualization server" である場合、このフィールドは既定で "/" に設定され、読み取り専用です。</span><span class="sxs-lookup"><span data-stu-id="71428-118">**Path**—This field defaults to "/" and is read-only when the server type is "Application Virtualization Server" or “Enhanced Security Application Virtualization Server”.</span></span> <span data-ttu-id="71428-119">サーバーの種類が "標準 HTTP サーバー" または "強化されたセキュリティ HTTP サーバー" の場合、[ **Path** ] フィールドも編集できます。</span><span class="sxs-lookup"><span data-stu-id="71428-119">When the server type is “Standard HTTP Server” or “Enhanced Security HTTP Server”, the **Path** field is also editable.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="71428-120">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="71428-120">New Window from Here</span></span>**  
<span data-ttu-id="71428-121">このメニュー項目を選択すると、選択したノードがルートノードとして新しい管理コンソールが開きます。</span><span class="sxs-lookup"><span data-stu-id="71428-121">Select this menu item to open a new management console with the selected node as the root node.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="71428-122">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="71428-122">Export List</span></span>**  
<span data-ttu-id="71428-123">このメニュー項目を使用して、**結果**ウィンドウの内容を含むタブ区切りのテキストファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="71428-123">You can use this menu item to create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="71428-124">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="71428-124">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="71428-125">View</span><span class="sxs-lookup"><span data-stu-id="71428-125">View</span></span>**  
<span data-ttu-id="71428-126">メニュー項目のこのポップアップリストでは、[**結果**] ウィンドウの外観と内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="71428-126">This pop-up list of menu items enables you to change the appearance and content of the **Results** pane.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="71428-127">Refresh</span><span class="sxs-lookup"><span data-stu-id="71428-127">Refresh</span></span>**  
<span data-ttu-id="71428-128">この項目を選択すると、管理コンソールが更新されます。</span><span class="sxs-lookup"><span data-stu-id="71428-128">Select this item to refresh the management console.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="71428-129">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="71428-129">Help</span></span>**  
<span data-ttu-id="71428-130">この項目は、管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="71428-130">This item displays the help system for the management console.</span></span>

## <span data-ttu-id="71428-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="71428-131">Related topics</span></span>


[<span data-ttu-id="71428-132">公開サーバーの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="71428-132">Publishing Servers Results Pane</span></span>](publishing-servers-results-pane.md)

[<span data-ttu-id="71428-133">公開サーバーの結果ウィンドウの列</span><span class="sxs-lookup"><span data-stu-id="71428-133">Publishing Servers Results Pane Columns</span></span>](publishing-servers-results-pane-columns.md)

 

 





