---
title: アプリケーション ライセンス ノード
description: アプリケーション ライセンス ノード
author: dansimp
ms.assetid: 2b8752ff-aa56-483e-b844-966941af2d94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 720de1860e72ae2c71298f93e9b346afd66da569
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819514"
---
# <span data-ttu-id="cf843-103">アプリケーション ライセンス ノード</span><span class="sxs-lookup"><span data-stu-id="cf843-103">Applications Licenses Node</span></span>


<span data-ttu-id="cf843-104">[**アプリケーションライセンス**] ノードは、Application Virtualization Server 管理コンソールの**スコープ**ウィンドウで、application virtualization システムノードの1つ下のレベルにあります。</span><span class="sxs-lookup"><span data-stu-id="cf843-104">The **Applications Licenses** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="cf843-105">このノードを選択すると、[**結果**] ウィンドウにライセンスとライセンスグループの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf843-105">When you select this node, the **Results** pane displays a list of licenses and license groups.</span></span> <span data-ttu-id="cf843-106">次のライセンスの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="cf843-106">The following license types are available:</span></span>

-   <span data-ttu-id="cf843-107">実質**無制限のライセンス**: 同時に複数のユーザーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-107">**Unlimited License**—Provides access for any number of simultaneous users.</span></span> <span data-ttu-id="cf843-108">このライセンスの方法は、企業全体のライセンスをアプリケーションに関連付ける場合に適しています。</span><span class="sxs-lookup"><span data-stu-id="cf843-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="cf843-109">**同時ライセンス**: アプリケーションの使用を許可する同時ユーザーの最大数を定義できます。</span><span class="sxs-lookup"><span data-stu-id="cf843-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="cf843-110">**"名前付きライセンス"**: 個々のユーザーにライセンスを割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="cf843-111">名前付きライセンスを使用して、特定のユーザーが常にアプリケーションを実行できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="cf843-112">**注** 同じアプリケーションの同時ライセンスと名前付きライセンスを組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-112">**Note** You can combine concurrent and named licenses for the same application.</span></span>

 

<span data-ttu-id="cf843-113">[**アプリケーションライセンス**] ノードを右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-113">Right-click the **Applications Licenses** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="cf843-114">新規実質無制限のライセンス</span><span class="sxs-lookup"><span data-stu-id="cf843-114">New Unlimited License</span></span>**  
<span data-ttu-id="cf843-115">新しい無制限のライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-115">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="cf843-116">このウィザードは、次のページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="cf843-116">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="cf843-117">[**アプリケーションライセンスグループ名**] フィールドにライセンスグループの名前を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf843-117">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="cf843-118">(0 ~ 100 の任意の値を入力できます。)また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-118">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="cf843-119">[**ライセンスの説明**] フィールドに簡単な説明テキストを入力し、[**有効**] チェックボックスをオンにしてライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cf843-119">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="cf843-120">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-120">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="cf843-121">表示される有効期限の日付を使用する場合は、チェックボックスをオンにしてください。または、予定表ユーティリティを使用して、目的の有効期限の日付を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-121">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="cf843-122">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf843-122">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="cf843-123">新しい同時ライセンス</span><span class="sxs-lookup"><span data-stu-id="cf843-123">New Concurrent License</span></span>**  
<span data-ttu-id="cf843-124">新しい同時ライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-124">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="cf843-125">このウィザードは、次の3つのページで構成されており、実質無制限のライセンスウィザードとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="cf843-125">This wizard consists of the following three pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="cf843-126">[**アプリケーションライセンスグループ名**] フィールドにライセンスグループの名前を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf843-126">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="cf843-127">(0 ~ 100 の任意の値を入力できます。)また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-127">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="cf843-128">[**ライセンスの説明**] フィールドに簡単な説明テキストを入力し、[**同時ライセンス数**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf843-128">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span>

    <span data-ttu-id="cf843-129">また、上下の矢印を使用して、同時ライセンス数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-129">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="cf843-130">ライセンスを有効にするには、[**有効**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="cf843-130">Select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="cf843-131">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-131">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="cf843-132">表示される有効期限の日付を使用する場合は、チェックボックスをオンにしてください。または、予定表ユーティリティを使用して、目的の有効期限の日付を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-132">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="cf843-133">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf843-133">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="cf843-134">新しい名前付きライセンス</span><span class="sxs-lookup"><span data-stu-id="cf843-134">New Named License</span></span>**  
<span data-ttu-id="cf843-135">新しい名前付きライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-135">Displays the New Named License Wizard.</span></span> <span data-ttu-id="cf843-136">このウィザードは、次の4つのページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="cf843-136">This wizard consists of the following four pages:</span></span>

1.  <span data-ttu-id="cf843-137">[**アプリケーションライセンスグループ名**] フィールドにライセンスグループの名前を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="cf843-137">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="cf843-138">(0 ~ 100 の任意の値を入力できます)。</span><span class="sxs-lookup"><span data-stu-id="cf843-138">(You can enter any value from 0 through 100).</span></span> <span data-ttu-id="cf843-139">また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-139">You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="cf843-140">[**ライセンスの説明**] フィールドに簡単な説明テキストを入力し、[**有効**] チェックボックスをオンにしてライセンスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="cf843-140">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="cf843-141">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="cf843-141">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="cf843-142">表示される有効期限の日付を使用する場合は、チェックボックスをオンにしてください。または、予定表ユーティリティを使用して、目的の有効期限の日付を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="cf843-142">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="cf843-143">[指定したユーザーの**追加**、**編集**、**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="cf843-143">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="cf843-144">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="cf843-144">Click **Finish** to add the new license.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="cf843-145">View</span><span class="sxs-lookup"><span data-stu-id="cf843-145">View</span></span>**  
<span data-ttu-id="cf843-146">[**結果**] ウィンドウの外観と内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf843-146">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="cf843-147">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cf843-147">New Window from Here</span></span>**  
<span data-ttu-id="cf843-148">選択したノードがルートノードとして新しい管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf843-148">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="cf843-149">Refresh</span><span class="sxs-lookup"><span data-stu-id="cf843-149">Refresh</span></span>**  
<span data-ttu-id="cf843-150">サーバーの表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="cf843-150">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="cf843-151">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="cf843-151">Export List</span></span>**  
<span data-ttu-id="cf843-152">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf843-152">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="cf843-153">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-153">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="cf843-154">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="cf843-154">Help</span></span>**  
<span data-ttu-id="cf843-155">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-155">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="cf843-156">[**スコープ**] ウィンドウの [**アプリケーションライセンス**] ノードの下に表示されるライセンスグループまたはライセンスをクリックすると、次の要素が利用可能になります。</span><span class="sxs-lookup"><span data-stu-id="cf843-156">If you click a license group or license that appears under the **Application Licenses** node in the **Scope** pane, the following elements are available.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="cf843-157">View</span><span class="sxs-lookup"><span data-stu-id="cf843-157">View</span></span>**  
<span data-ttu-id="cf843-158">[**結果**] ウィンドウの外観と内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf843-158">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="cf843-159">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="cf843-159">New Window from Here</span></span>**  
<span data-ttu-id="cf843-160">選択したノードがルートノードとして新しい管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="cf843-160">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="cf843-161">Delete</span><span class="sxs-lookup"><span data-stu-id="cf843-161">Delete</span></span>**  
<span data-ttu-id="cf843-162">[**結果**] ウィンドウからパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="cf843-162">Deletes a package from the **Results** pane.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="cf843-163">Rename</span><span class="sxs-lookup"><span data-stu-id="cf843-163">Rename</span></span>**  
<span data-ttu-id="cf843-164">[**結果**] ウィンドウでパッケージの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="cf843-164">Changes the name of a package in the **Results** pane.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="cf843-165">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="cf843-165">Export List</span></span>**  
<span data-ttu-id="cf843-166">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="cf843-166">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="cf843-167">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-167">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="cf843-168">プロパティ</span><span class="sxs-lookup"><span data-stu-id="cf843-168">Properties</span></span>**  
<span data-ttu-id="cf843-169">選択されたライセンスグループの [**プロパティ**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-169">Displays the **Properties** dialog box for the selected license group.</span></span> <span data-ttu-id="cf843-170">[**プロパティ**] ダイアログボックスの **[全般**] タブには、ライセンスグループに関する情報が表示され、[**ライセンスの有効期限] 警告**フィールドで時刻の値を変更できます。</span><span class="sxs-lookup"><span data-stu-id="cf843-170">The **General** tab of the **Properties** dialog box displays information about the license group and lets you change the time value in the **License Expiration Warning** field.</span></span> <span data-ttu-id="cf843-171">[**アプリケーション**] タブには、ライセンスグループに関連付けられているアプリケーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="cf843-171">The **Applications** tab displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="cf843-172">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="cf843-172">Help</span></span>**  
<span data-ttu-id="cf843-173">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="cf843-173">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="cf843-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cf843-174">Related topics</span></span>


[<span data-ttu-id="cf843-175">アプリケーション ライセンスについて</span><span class="sxs-lookup"><span data-stu-id="cf843-175">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="cf843-176">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="cf843-176">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="cf843-177">サーバー管理コンソール: アプリケーション ライセンス ノード</span><span class="sxs-lookup"><span data-stu-id="cf843-177">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





