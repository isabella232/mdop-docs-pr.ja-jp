---
title: 公開サーバーの結果ウィンドウの列
description: 公開サーバーの結果ウィンドウの列
author: dansimp
ms.assetid: ad875715-50b3-4881-a6b3-586238d12527
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: afc20f3c9fa1928b475638b191775b738e0a2446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815764"
---
# <span data-ttu-id="25dc2-103">公開サーバーの結果ウィンドウの列</span><span class="sxs-lookup"><span data-stu-id="25dc2-103">Publishing Servers Results Pane Columns</span></span>


<span data-ttu-id="25dc2-104">[**発行サーバーの結果**] ウィンドウには、さまざまな列を表示できます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-104">The **Publishing Servers Results** pane can display a variety of columns.</span></span> <span data-ttu-id="25dc2-105">既定では、**名前**、 **URL**、および**次の更新**が表示されます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-105">**Name**, **URL**, and **Next Refresh** are shown by default.</span></span>

<span data-ttu-id="25dc2-106">**注** 列を追加または削除するには、[**結果**] ウィンドウで右クリックし、[**表示**]、[**列の追加と削除**] の順に選択します。</span><span class="sxs-lookup"><span data-stu-id="25dc2-106">**Note** You can add or remove a column simply by right-clicking in the **Results** pane, selecting **View**, then selecting **Add/Remove Columns**.</span></span>

 

<span data-ttu-id="25dc2-107">リストは、任意の列によって並べ替えることができます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-107">The list can be sorted by any of the columns.</span></span> <span data-ttu-id="25dc2-108">日付と時刻を含む列は、昇順で並べ替えられます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-108">Columns that contain dates and times are sorted in chronological order, not alphabetical.</span></span> <span data-ttu-id="25dc2-109">日付と時刻、およびテキスト (**次の更新**など) が混在している列については、日付と時刻は、他のテキストよりも前にあると見なされます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-109">For columns that contain a mix of dates and times and text (for example, **Next Refresh**), dates and times are considered to come before any other text.</span></span>

<span data-ttu-id="25dc2-110">使用可能な列名には、次の要素が含まれています。</span><span class="sxs-lookup"><span data-stu-id="25dc2-110">The available column names contain the following elements.</span></span>

<a href="" id="name"></a>**<span data-ttu-id="25dc2-111">名前</span><span class="sxs-lookup"><span data-stu-id="25dc2-111">Name</span></span>**  
<span data-ttu-id="25dc2-112">サーバーの表示名。</span><span class="sxs-lookup"><span data-stu-id="25dc2-112">The display name for the server.</span></span>

<a href="" id="url"></a>**<span data-ttu-id="25dc2-113">URL</span><span class="sxs-lookup"><span data-stu-id="25dc2-113">URL</span></span>**  
<span data-ttu-id="25dc2-114">プロトコル、サーバー名、サーバーポート、および URL に結合されたパス。</span><span class="sxs-lookup"><span data-stu-id="25dc2-114">The protocol, server name, server port, and path combined into a URL.</span></span>

<a href="" id="next-user-refresh"></a>**<span data-ttu-id="25dc2-115">次回のユーザー更新</span><span class="sxs-lookup"><span data-stu-id="25dc2-115">Next User Refresh</span></span>**  
<span data-ttu-id="25dc2-116">次に、現在のユーザーに対して更新がスケジュールされたとき。</span><span class="sxs-lookup"><span data-stu-id="25dc2-116">The next time a refresh is scheduled for the current user.</span></span> <span data-ttu-id="25dc2-117">定期的な更新が設定されている時間を表示します。</span><span class="sxs-lookup"><span data-stu-id="25dc2-117">Displays the time if periodic refreshes are set up.</span></span> <span data-ttu-id="25dc2-118">サーバーがログイン時にのみ更新するよう設定されている場合は、**ログイン時に**表示されます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-118">Displays **On Login** if the server is set to refresh only on login.</span></span> <span data-ttu-id="25dc2-119">自動更新が有効になっていない場合は、**手動**で表示されます。</span><span class="sxs-lookup"><span data-stu-id="25dc2-119">Displays **Manual** if automatic refresh is not enabled.</span></span>

<a href="" id="default-refresh-policy"></a>**<span data-ttu-id="25dc2-120">既定の更新ポリシー</span><span class="sxs-lookup"><span data-stu-id="25dc2-120">Default Refresh Policy</span></span>**  
<span data-ttu-id="25dc2-121">**ログイン時**、または**定期的\*\*\*\*に、サーバー**がどのように構成されているかを示します。</span><span class="sxs-lookup"><span data-stu-id="25dc2-121">Displays **Manual**, **On Login**, or **Periodic** to describe how the server is configured.</span></span>

<a href="" id="host"></a>**<span data-ttu-id="25dc2-122">Host</span><span class="sxs-lookup"><span data-stu-id="25dc2-122">Host</span></span>**  
<span data-ttu-id="25dc2-123">サーバーの名前または IP アドレス。</span><span class="sxs-lookup"><span data-stu-id="25dc2-123">The name or IP address for the server.</span></span>

<a href="" id="type"></a>**<span data-ttu-id="25dc2-124">型</span><span class="sxs-lookup"><span data-stu-id="25dc2-124">Type</span></span>**  
<span data-ttu-id="25dc2-125">サーバーの種類を示す**HTTP**または**仮想アプリケーション**を表示します。</span><span class="sxs-lookup"><span data-stu-id="25dc2-125">Displays **HTTP** or **Virtual Application** to indicate the server type.</span></span>

<a href="" id="port"></a>**<span data-ttu-id="25dc2-126">Port</span><span class="sxs-lookup"><span data-stu-id="25dc2-126">Port</span></span>**  
<span data-ttu-id="25dc2-127">使用するサーバー上のポート。</span><span class="sxs-lookup"><span data-stu-id="25dc2-127">The port on the server to be used.</span></span>

<a href="" id="path"></a>**<span data-ttu-id="25dc2-128">パス</span><span class="sxs-lookup"><span data-stu-id="25dc2-128">Path</span></span>**  
<span data-ttu-id="25dc2-129">サーバー上のパス (通常は、Application Virtualization サーバーの場合は "/" のみ)。</span><span class="sxs-lookup"><span data-stu-id="25dc2-129">The path on the server (generally just "/" for Application Virtualization Servers).</span></span>

<a href="" id="last-user-refresh"></a>**<span data-ttu-id="25dc2-130">最終ユーザー更新</span><span class="sxs-lookup"><span data-stu-id="25dc2-130">Last User Refresh</span></span>**  
<span data-ttu-id="25dc2-131">現在のユーザーが最後に更新した時刻。</span><span class="sxs-lookup"><span data-stu-id="25dc2-131">The time the last refresh occurred for the current user.</span></span>

<a href="" id="last-system-refresh"></a>**<span data-ttu-id="25dc2-132">最終システム更新</span><span class="sxs-lookup"><span data-stu-id="25dc2-132">Last System Refresh</span></span>**  
<span data-ttu-id="25dc2-133">いずれかのユーザーに対してこのサーバーから更新が行われた最後の時刻。</span><span class="sxs-lookup"><span data-stu-id="25dc2-133">The last time a refresh happened from this server for any user.</span></span>

## <span data-ttu-id="25dc2-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="25dc2-134">Related topics</span></span>


[<span data-ttu-id="25dc2-135">公開サーバー ノード</span><span class="sxs-lookup"><span data-stu-id="25dc2-135">Publishing Servers Node</span></span>](publishing-servers-node.md)

[<span data-ttu-id="25dc2-136">公開サーバーの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="25dc2-136">Publishing Servers Results Pane</span></span>](publishing-servers-results-pane.md)

 

 





