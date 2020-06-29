---
title: プロバイダー ポリシー ノード
description: プロバイダー ポリシー ノード
author: dansimp
ms.assetid: 89b47076-7732-4128-93cc-8e6d5b671c8e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221171b22471a4a8614b13023b24dd21fd571dd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815834"
---
# <span data-ttu-id="17d50-103">プロバイダー ポリシー ノード</span><span class="sxs-lookup"><span data-stu-id="17d50-103">Provider Policies Node</span></span>


<span data-ttu-id="17d50-104">[**プロバイダーポリシー** ] ノードは、Application Virtualization Server 管理コンソールの**スコープ**ウィンドウの [application virtualization System] ノードの1つ下のレベルにあります。</span><span class="sxs-lookup"><span data-stu-id="17d50-104">The **Provider Policies** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="17d50-105">このノードを選択すると、[**結果**] ウィンドウにプロバイダーポリシーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="17d50-105">When you select this node, the **Results** pane displays a list of provider policies.</span></span> <span data-ttu-id="17d50-106">[**プロバイダーポリシー** ] ノードを右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="17d50-106">Right-click the **Provider Policies** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-provider-policy"></a>**<span data-ttu-id="17d50-107">新しいプロバイダーポリシー</span><span class="sxs-lookup"><span data-stu-id="17d50-107">New Provider Policy</span></span>**  
<span data-ttu-id="17d50-108">新しいプロバイダーポリシーウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="17d50-108">Displays the New Provider Policy Wizard.</span></span> <span data-ttu-id="17d50-109">このウィザードは、次のページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="17d50-109">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="17d50-110">[**プロバイダーポリシー名**] フィールドに名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="17d50-110">Enter a name in the **Provider Policy Name** field.</span></span> <span data-ttu-id="17d50-111">この機能が必要な場合は、[**管理コンソールを使用してクライアントデスクトップを管理**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17d50-111">Select the **Manage client desktop using the Management Console** check box if you want that capability.</span></span> <span data-ttu-id="17d50-112">関連する機能が必要な場合は、次のいずれかまたは両方のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17d50-112">Select one or both of the following check boxes if you want the associated functionality:</span></span>

    -   **<span data-ttu-id="17d50-113">ユーザーがログインしたときに発行構成を更新する</span><span class="sxs-lookup"><span data-stu-id="17d50-113">Refresh publishing configuration when a user logs in</span></span>**

    -   <span data-ttu-id="17d50-114">**構成を毎回更新**する。</span><span class="sxs-lookup"><span data-stu-id="17d50-114">**Refresh configuration every**.</span></span> <span data-ttu-id="17d50-115">このオプションを選択した後で、番号を入力し、ドロップダウンメニューから単位を選択します。</span><span class="sxs-lookup"><span data-stu-id="17d50-115">After selecting this option, enter a number and select the unit from the drop-down menu.</span></span> <span data-ttu-id="17d50-116">有効なエントリの範囲は、最低**30 分**から**999 日**までです。</span><span class="sxs-lookup"><span data-stu-id="17d50-116">Valid entries range from a minimum of **30 minutes** to a maximum of **999 days**.</span></span>

2.  <span data-ttu-id="17d50-117">[**追加**] または [**削除**] をクリックして、グループの割り当てを追加または削除します。</span><span class="sxs-lookup"><span data-stu-id="17d50-117">Click **Add** or **Remove** to add or remove a group assignment.</span></span> <span data-ttu-id="17d50-118">Windows の標準の [**参照**] ダイアログボックスを使って、ユーザーグループを見つけます。</span><span class="sxs-lookup"><span data-stu-id="17d50-118">Use the standard **Windows Browse** dialog box to find a user group.</span></span>

3.  <span data-ttu-id="17d50-119">関連付けられている機能を有効にするには、[**プロバイダーパイプライン構成**] ダイアログボックスで次のいずれかのチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="17d50-119">Select one of the following check boxes on the **Provider Pipeline Configuration** dialog box to enable the associated feature:</span></span>

    -   <span data-ttu-id="17d50-120">[ **Authentication**]: ドロップダウンリストから認証の種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="17d50-120">**Authentication**—Select the type of authentication from the drop-down list.</span></span>

    -   **<span data-ttu-id="17d50-121">アクセス許可の設定を適用する</span><span class="sxs-lookup"><span data-stu-id="17d50-121">Enforce Access Permission Settings</span></span>**

    -   **<span data-ttu-id="17d50-122">使用状況情報の記録</span><span class="sxs-lookup"><span data-stu-id="17d50-122">Log Usage Information</span></span>**

    -   <span data-ttu-id="17d50-123">[**ライセンス**] —ドロップダウンリストから適用スキームを選択します。</span><span class="sxs-lookup"><span data-stu-id="17d50-123">**Licensing**—Select an enforcement scheme from the drop-down list.</span></span>

4.  <span data-ttu-id="17d50-124">[**完了**] をクリックして、新しいプロバイダーポリシーを追加します。</span><span class="sxs-lookup"><span data-stu-id="17d50-124">Click **Finish** to add the new provider policy.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="17d50-125">View</span><span class="sxs-lookup"><span data-stu-id="17d50-125">View</span></span>**  
<span data-ttu-id="17d50-126">[**結果**] ウィンドウの外観と内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="17d50-126">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="17d50-127">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="17d50-127">New Window from Here</span></span>**  
<span data-ttu-id="17d50-128">選択したノードがルートノードとして新しい管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="17d50-128">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="17d50-129">Refresh</span><span class="sxs-lookup"><span data-stu-id="17d50-129">Refresh</span></span>**  
<span data-ttu-id="17d50-130">サーバーの表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="17d50-130">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="17d50-131">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="17d50-131">Export List</span></span>**  
<span data-ttu-id="17d50-132">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="17d50-132">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="17d50-133">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="17d50-133">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="17d50-134">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="17d50-134">Help</span></span>**  
<span data-ttu-id="17d50-135">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="17d50-135">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="17d50-136">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17d50-136">Related topics</span></span>


[<span data-ttu-id="17d50-137">サーバー管理コンソール: プロバイダー ポリシー ノード</span><span class="sxs-lookup"><span data-stu-id="17d50-137">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





