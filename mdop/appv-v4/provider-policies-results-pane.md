---
title: プロバイダー ポリシーの結果ウィンドウ
description: プロバイダー ポリシーの結果ウィンドウ
author: dansimp
ms.assetid: 17ea0836-bfb5-4966-8778-155444d81e64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97e7497617d19c09291104fce237b030a149e743
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815824"
---
# <span data-ttu-id="45f21-103">プロバイダー ポリシーの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="45f21-103">Provider Policies Results Pane</span></span>


<span data-ttu-id="45f21-104">Application Virtualization Server 管理コンソールの [**プロバイダーポリシーの結果**] ウィンドウに、利用可能なプロバイダーポリシーの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="45f21-104">The **Provider Policies Results** pane in the Application Virtualization Server Management Console displays a list of the available provider policies.</span></span>

<span data-ttu-id="45f21-105">任意のプロバイダーポリシーを右クリックして、次の要素を表示します。</span><span class="sxs-lookup"><span data-stu-id="45f21-105">Right-click any provider policy to display the following elements.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="45f21-106">Delete</span><span class="sxs-lookup"><span data-stu-id="45f21-106">Delete</span></span>**  
<span data-ttu-id="45f21-107">このメニュー項目を使用すると、[**結果**] ウィンドウからプロバイダーポリシーを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="45f21-107">This menu item enables you to delete a provider policy from the **Results** pane.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="45f21-108">Rename</span><span class="sxs-lookup"><span data-stu-id="45f21-108">Rename</span></span>**  
<span data-ttu-id="45f21-109">このメニュー項目を使用すると、[**結果**] ウィンドウでプロバイダーポリシーの名前を変更できます。</span><span class="sxs-lookup"><span data-stu-id="45f21-109">This menu item enables you to change the name of a provider policy in the **Results** pane.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="45f21-110">プロパティ</span><span class="sxs-lookup"><span data-stu-id="45f21-110">Properties</span></span>**  
<span data-ttu-id="45f21-111">このメニュー項目では、選択したプロバイダーポリシーの [**プロパティ**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="45f21-111">This menu item displays the **Properties** dialog box for the selected provider policy.</span></span> <span data-ttu-id="45f21-112">[**プロパティ**] ダイアログボックスには、次のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="45f21-112">The **Properties** dialog box has the following tabs:</span></span>

-   <span data-ttu-id="45f21-113">**[全般**] — Application Virtualization Server 管理コンソールからクライアントデスクトップのショートカットを一元管理する場合は、[**管理コンソール\*\*\*\*を使用してクライアントデスクトップを管理**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="45f21-113">**General**—Enables you to select the **Manage client desktop using the** **Management Console** check box if you want to centrally manage shortcuts on the client desktops from the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="45f21-114">コンソールからショートカットを管理する場合は、チェックボックスをオンにして、ユーザーがログインするたびに、または指定した間隔でデスクトップを更新することができます。</span><span class="sxs-lookup"><span data-stu-id="45f21-114">If you choose to manage shortcuts from the console, you can select check boxes to refresh the desktop every time a user logs in and at intervals you specify.</span></span>

-   <span data-ttu-id="45f21-115">[**グループの割り当て]**—プロバイダーポリシーに割り当てられているユーザーグループの追加と削除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="45f21-115">**Group Assignment**—Enables you to add and remove user groups assigned to the provider policy.</span></span>

-   <span data-ttu-id="45f21-116">**プロバイダーパイプライン**: 必要な認証を指定できます。</span><span class="sxs-lookup"><span data-stu-id="45f21-116">**Provider Pipeline**—Enables you to specify the authentication required.</span></span>

    -   <span data-ttu-id="45f21-117">[**アクセス許可の設定を適用**する]、[**使用状況情報の記録**]、[**ライセンス**] のチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="45f21-117">Select the desired check boxes for **Enforce Access Permission Settings**, **Log Usage Information**, and **Licensing**.</span></span> <span data-ttu-id="45f21-118">[**ライセンス**] チェックボックスをオンにした場合は、ドロップダウンリストから [**ライセンスの使用を監査**する] または [**ライセンスポリシーを適用**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="45f21-118">If you select the **Licensing** check box, select **Audit License Usage Only** or **Enforce License Policies** from the drop-down list.</span></span> <span data-ttu-id="45f21-119">最初のオプションでは、ライセンスの使用状況が監視されますが、2番目のオプションではライセンスポリシーが厳密に適用されます。</span><span class="sxs-lookup"><span data-stu-id="45f21-119">The first option monitors license usage, while the second option strictly enforces your licensing policy.</span></span> <span data-ttu-id="45f21-120">[**完了**] をクリックし、メッセージを読み、[ **OK** ] をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="45f21-120">Click **Finish**, and then read the prompt and click **OK** to continue.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="45f21-121">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="45f21-121">Help</span></span>**  
<span data-ttu-id="45f21-122">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="45f21-122">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="45f21-123">[**結果**] ウィンドウ内の任意の場所 (プロバイダーポリシーを除く) を右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="45f21-123">Right-click anywhere in the **Results** pane, except on a provider policy, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="45f21-124">Refresh</span><span class="sxs-lookup"><span data-stu-id="45f21-124">Refresh</span></span>**  
<span data-ttu-id="45f21-125">このメニュー項目を選択すると、プロバイダーポリシーの表示が更新されます。</span><span class="sxs-lookup"><span data-stu-id="45f21-125">Select this menu item to refresh the view of the provider policies.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="45f21-126">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="45f21-126">Export List</span></span>**  
<span data-ttu-id="45f21-127">このメニュー項目を使うと、**結果**ウィンドウの内容を含むタブ区切りのテキストファイルを作成できます。</span><span class="sxs-lookup"><span data-stu-id="45f21-127">With this menu item, you can create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="45f21-128">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="45f21-128">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="45f21-129">View</span><span class="sxs-lookup"><span data-stu-id="45f21-129">View</span></span>**  
<span data-ttu-id="45f21-130">このメニュー項目では、[**結果**] ウィンドウの外観と内容を変更することができます。</span><span class="sxs-lookup"><span data-stu-id="45f21-130">This menu item lets you change the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="45f21-131">整列/行アップアイコン</span><span class="sxs-lookup"><span data-stu-id="45f21-131">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="45f21-132">これらのメニュー項目は、[**結果**] ウィンドウでのアイコンの表示方法を変更するために使うことができます。</span><span class="sxs-lookup"><span data-stu-id="45f21-132">These menu items can be used to change how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="45f21-133">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="45f21-133">Help</span></span>**  
<span data-ttu-id="45f21-134">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="45f21-134">Displays the help system of the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="45f21-135">関連トピック</span><span class="sxs-lookup"><span data-stu-id="45f21-135">Related topics</span></span>


[<span data-ttu-id="45f21-136">サーバー管理コンソール: プロバイダー ポリシー ノード</span><span class="sxs-lookup"><span data-stu-id="45f21-136">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





