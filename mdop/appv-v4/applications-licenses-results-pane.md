---
title: アプリケーション ライセンスの結果ウィンドウ
description: アプリケーション ライセンスの結果ウィンドウ
author: dansimp
ms.assetid: 8b519715-b2fe-451e-ad9b-e9b73f454961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5a86c22e67e061ec873317c455958536fae75b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819507"
---
# <span data-ttu-id="a0dc9-103">アプリケーション ライセンスの結果ウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-103">Applications Licenses Results Pane</span></span>


<span data-ttu-id="a0dc9-104">Application Virtualization Server 管理コンソールの [**アプリケーションライセンスの結果**] ウィンドウには、利用可能なアプリケーションライセンスグループとアプリケーションライセンスの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-104">The **Applications Licenses Results** pane in the Application Virtualization Server Management Console displays a list of the available application license groups and application licenses.</span></span>

<span data-ttu-id="a0dc9-105">任意のアプリケーションライセンスグループを右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-105">Right-click any application license group to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="a0dc9-106">新規実質無制限のライセンス</span><span class="sxs-lookup"><span data-stu-id="a0dc9-106">New Unlimited License</span></span>**  
<span data-ttu-id="a0dc9-107">新しい無制限のライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-107">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="a0dc9-108">このオプションは、ライセンスグループにライセンスがない場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-108">This option is available only when the license group has no licenses.</span></span> <span data-ttu-id="a0dc9-109">このウィザードは、次の3つのページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-109">This wizard consists of three pages:</span></span>

1.  <span data-ttu-id="a0dc9-110">[**アプリケーションライセンスグループ名**] フィールドにグループ名を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-110">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="a0dc9-111">(0 ~ 100 の任意の値を入力できます。)また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-111">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="a0dc9-112">[**ライセンスの説明**] フィールドに簡単な説明テキストを入力し、[**有効**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-112">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box.</span></span> <span data-ttu-id="a0dc9-113">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-113">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="a0dc9-114">[既定] チェックボックスをオンにするか、カレンダーユーティリティを使用して目的の有効期限日を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-114">You can select the default check box or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="a0dc9-115">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-115">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="a0dc9-116">新しい同時ライセンス</span><span class="sxs-lookup"><span data-stu-id="a0dc9-116">New Concurrent License</span></span>**  
<span data-ttu-id="a0dc9-117">新しい同時ライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-117">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="a0dc9-118">このオプションは、ライセンスグループに無制限のライセンスがない場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-118">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="a0dc9-119">このウィザードは、次のページで構成されており、実質無制限のライセンスウィザードとほぼ同じです。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-119">This wizard consists of the following pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="a0dc9-120">[**アプリケーションライセンスグループ名**] フィールドにグループ名を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-120">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="a0dc9-121">(0 ~ 100 の任意の値を入力できます。)また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-121">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="a0dc9-122">[**ライセンスの説明**] フィールドに簡単な説明テキストを入力し、[**同時ライセンス数**] フィールドに値を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-122">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span> <span data-ttu-id="a0dc9-123">また、上下の矢印を使用して、同時ライセンス数を指定することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-123">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="a0dc9-124">ライセンスを有効にするには、[**有効**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-124">Select the **Enabled** check box to enable the license.</span></span> <span data-ttu-id="a0dc9-125">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を選択できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-125">Optionally, you can use the **Expiration Date** field to select an expiration date for the license.</span></span> <span data-ttu-id="a0dc9-126">表示される有効期限の日付を使用する場合は、チェックボックスをオンにしてください。または、予定表ユーティリティを使用して、目的の有効期限の日付を参照することもできます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-126">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="a0dc9-127">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-127">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="a0dc9-128">新しい名前付きライセンス</span><span class="sxs-lookup"><span data-stu-id="a0dc9-128">New Named License</span></span>**  
<span data-ttu-id="a0dc9-129">新しい名前付きライセンスウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-129">Displays the New Named License Wizard.</span></span> <span data-ttu-id="a0dc9-130">このオプションは、ライセンスグループに無制限のライセンスがない場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-130">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="a0dc9-131">このウィザードは、次のページで構成されています。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-131">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="a0dc9-132">[**アプリケーションライセンスグループ名**] フィールドにグループ名を入力し、[**ライセンスの有効期限] 警告**フィールドに値 (分単位) を入力します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-132">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="a0dc9-133">(0 ~ 100 の任意の値を入力できます。)また、上矢印と下矢印を使用して分数を選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-133">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="a0dc9-134">[**ライセンスの説明**] に簡単な説明テキストを入力し、[**有効**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-134">Enter brief descriptive text in the **License Description**, and select the **Enabled** check box.</span></span> <span data-ttu-id="a0dc9-135">必要に応じて、[**有効期限の日付**] フィールドを使用して、ライセンスの有効期限を指定することができます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-135">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="a0dc9-136">このチェックボックスをオンにして表示された有効期限を使用するか、カレンダーユーティリティを使用して目的の有効期限日を参照することができます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-136">You can select the check box to use the displayed expiration date, or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="a0dc9-137">[指定したユーザーの**追加**、**編集**、**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-137">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="a0dc9-138">[**完了**] をクリックして、新しいライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-138">Click **Finish** to add the new license.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="a0dc9-139">ここから新しいウィンドウ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-139">New Window from Here</span></span>**  
<span data-ttu-id="a0dc9-140">選択したノードがルートノードとして新しい管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-140">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="a0dc9-141">Delete</span><span class="sxs-lookup"><span data-stu-id="a0dc9-141">Delete</span></span>**  
<span data-ttu-id="a0dc9-142">ライセンスグループを一覧から削除します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-142">Deletes the license group from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="a0dc9-143">Rename</span><span class="sxs-lookup"><span data-stu-id="a0dc9-143">Rename</span></span>**  
<span data-ttu-id="a0dc9-144">アプリケーションライセンスグループの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-144">Changes the name of the applications license group.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="a0dc9-145">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-145">Properties</span></span>**  
<span data-ttu-id="a0dc9-146">選択されたアプリケーションライセンスグループの [**プロパティ**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-146">Displays the **Properties** dialog box for the selected application license groups.</span></span> <span data-ttu-id="a0dc9-147">このダイアログボックスには、次のタブがあります。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-147">This dialog box has the following tabs:</span></span>

-   <span data-ttu-id="a0dc9-148">**[全般**] タブ—ライセンスグループに関する一般的な情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-148">**General** tab—Displays general information about the license group.</span></span> <span data-ttu-id="a0dc9-149">このタブでは、[**ライセンスの有効期限] 警告**フィールドで時刻の値 (分単位) を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-149">From this tab, you can change the time value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="a0dc9-150">0 ~ 100 の任意の値を入力できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-150">You can enter any value from 0–100.</span></span>

-   <span data-ttu-id="a0dc9-151">[**アプリケーション**] タブ—ライセンスグループに関連付けられているアプリケーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-151">**Applications** tab—Displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="a0dc9-152">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-152">Help</span></span>**  
<span data-ttu-id="a0dc9-153">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-153">Displays the Application Virtualization Server Management Console help system.</span></span>

<span data-ttu-id="a0dc9-154">[**結果**] ウィンドウにアプリケーションライセンスグループが表示されたら、[**結果**] ウィンドウ内の任意の場所を右クリックし (ライセンスグループを除く)、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-154">When the **Results** pane displays application license groups, right-click anywhere in the **Results** pane, except on a license group, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="a0dc9-155">Refresh</span><span class="sxs-lookup"><span data-stu-id="a0dc9-155">Refresh</span></span>**  
<span data-ttu-id="a0dc9-156">サーバーの表示を更新します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-156">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="a0dc9-157">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="a0dc9-157">Export List</span></span>**  
<span data-ttu-id="a0dc9-158">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-158">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="a0dc9-159">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-159">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="a0dc9-160">View</span><span class="sxs-lookup"><span data-stu-id="a0dc9-160">View</span></span>**  
<span data-ttu-id="a0dc9-161">[**結果**] ウィンドウの外観と内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-161">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="a0dc9-162">整列/行アップアイコン</span><span class="sxs-lookup"><span data-stu-id="a0dc9-162">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="a0dc9-163">[**結果**] ウィンドウでのアイコンの表示方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-163">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="a0dc9-164">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-164">Help</span></span>**  
<span data-ttu-id="a0dc9-165">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-165">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="a0dc9-166">[**結果**] ウィンドウにライセンスが表示されたら、任意のアプリケーションライセンスを右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-166">When the **Results** pane displays licenses, right-click any application license to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="a0dc9-167">Delete</span><span class="sxs-lookup"><span data-stu-id="a0dc9-167">Delete</span></span>**  
<span data-ttu-id="a0dc9-168">リストからライセンスを削除します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-168">Deletes the license from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="a0dc9-169">Rename</span><span class="sxs-lookup"><span data-stu-id="a0dc9-169">Rename</span></span>**  
<span data-ttu-id="a0dc9-170">ライセンスの名前を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-170">Changes the name of the license.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="a0dc9-171">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-171">Properties</span></span>**  
<span data-ttu-id="a0dc9-172">選択されたアプリケーションライセンスの [**プロパティ**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-172">Displays the **Properties** dialog box for the selected application license.</span></span>

<span data-ttu-id="a0dc9-173">[**プロパティ**] ダイアログボックスの **[全般**] タブには、ライセンスに関する情報が表示され、有効状態、ライセンスの有効期限、およびライセンスキーの情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-173">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="a0dc9-174">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-174">Help</span></span>**  
<span data-ttu-id="a0dc9-175">サーバー管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-175">Displays the server management console help system.</span></span>

<span data-ttu-id="a0dc9-176">[**結果**] ウィンドウにライセンスが表示されたら、[**結果**] ウィンドウ内の任意の場所 (ライセンス以外) を右クリックして、次の要素を含むポップアップメニューを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-176">When the **Results** pane displays licenses, right-click anywhere in the **Results** pane, except on a license, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="a0dc9-177">エクスポートリスト</span><span class="sxs-lookup"><span data-stu-id="a0dc9-177">Export List</span></span>**  
<span data-ttu-id="a0dc9-178">**結果**ペインの内容を含むタブ区切りのテキストファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-178">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="a0dc9-179">この項目は、作成するテキストファイルの場所を指定する、標準の [**ファイルの保存**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-179">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="a0dc9-180">View</span><span class="sxs-lookup"><span data-stu-id="a0dc9-180">View</span></span>**  
<span data-ttu-id="a0dc9-181">[**結果**] ウィンドウの外観と内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-181">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="a0dc9-182">整列/行アップアイコン</span><span class="sxs-lookup"><span data-stu-id="a0dc9-182">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="a0dc9-183">[**結果**] ウィンドウでのアイコンの表示方法を変更します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-183">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="a0dc9-184">プロパティ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-184">Properties</span></span>**  
<span data-ttu-id="a0dc9-185">選択されたライセンスの [**プロパティ**] ダイアログボックスを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-185">Displays the **Properties** dialog box for the selected license.</span></span>

<span data-ttu-id="a0dc9-186">[**プロパティ**] ダイアログボックスの **[全般**] タブには、ライセンスに関する情報が表示され、有効状態、ライセンスの有効期限、およびライセンスキーの情報を変更できます。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-186">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="a0dc9-187">ヘルプ</span><span class="sxs-lookup"><span data-stu-id="a0dc9-187">Help</span></span>**  
<span data-ttu-id="a0dc9-188">Application Virtualization Server 管理コンソールのヘルプシステムを表示します。</span><span class="sxs-lookup"><span data-stu-id="a0dc9-188">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="a0dc9-189">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a0dc9-189">Related topics</span></span>


[<span data-ttu-id="a0dc9-190">アプリケーション ライセンスについて</span><span class="sxs-lookup"><span data-stu-id="a0dc9-190">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="a0dc9-191">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a0dc9-191">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="a0dc9-192">サーバー管理コンソール: アプリケーション ライセンス ノード</span><span class="sxs-lookup"><span data-stu-id="a0dc9-192">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





