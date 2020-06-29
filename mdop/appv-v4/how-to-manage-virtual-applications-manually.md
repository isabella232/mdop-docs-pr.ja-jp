---
title: 仮想アプリケーションを手動で管理する方法
description: 仮想アプリケーションを手動で管理する方法
author: dansimp
ms.assetid: 583c5255-d3f4-4197-85cd-2a59868d85de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e8dd5bb9d62950ac1a03ad0ec14802d9e0ff56e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817114"
---
# <span data-ttu-id="87193-103">仮想アプリケーションを手動で管理する方法</span><span class="sxs-lookup"><span data-stu-id="87193-103">How to Manage Virtual Applications Manually</span></span>


<span data-ttu-id="87193-104">Application Virtualization (App-v) クライアント管理コンソールを使用して、アプリ V デスクトップクライアントまたはリモートデスクトップサービス (旧ターミナルサービス) の App-v クライアントで仮想アプリケーションを管理できます。</span><span class="sxs-lookup"><span data-stu-id="87193-104">You can use the Application Virtualization (App-V) Client Management Console to manage virtual applications in the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="87193-105">App-v 管理者は、次の作業を実行できます。</span><span class="sxs-lookup"><span data-stu-id="87193-105">App-V administrators can use perform the following tasks:</span></span>

## <span data-ttu-id="87193-106">App-v アプリケーションを読み込む、またはアンロードする方法</span><span class="sxs-lookup"><span data-stu-id="87193-106">How to Load or Unload an App-V Application</span></span>


<span data-ttu-id="87193-107">次の手順を使用して、アプリケーションの仮想化クライアント管理コンソールの [**アプリケーション**] ノードの [**結果**] ウィンドウから直接、キャッシュからアプリケーションを読み込みまたはアンロードできます。</span><span class="sxs-lookup"><span data-stu-id="87193-107">You can use the following procedures to load or unload an application from the cache, directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="87193-108">このノードを選択すると、[**結果**] ウィンドウにアプリケーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-108">When you select this node, the **Results** pane displays a list of applications.</span></span>

<span data-ttu-id="87193-109">**注** パッケージを読み込みまたはアンロードすると、パッケージ内のすべてのアプリケーションがキャッシュに読み込まれるか、またはキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="87193-109">**Note** When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span> <span data-ttu-id="87193-110">パッケージを読み込むときに、キャッシュ内にアプリケーションを読み込むための十分な領域がない場合は、キャッシュサイズを大きくします。</span><span class="sxs-lookup"><span data-stu-id="87193-110">When loading a package, if you do not have adequate space in cache to load the applications, increase your cache size.</span></span> <span data-ttu-id="87193-111">キャッシュサイズの詳細については、「[キャッシュサイズとドライブ文字の指定を変更する方法](how-to-change-the-cache-size-and-the-drive-letter-designation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87193-111">For more information about cache size, see [How to Change the Cache Size and the Drive Letter Designation](how-to-change-the-cache-size-and-the-drive-letter-designation.md).</span></span>

 

**<span data-ttu-id="87193-112">App-v アプリケーションを読み込むには</span><span class="sxs-lookup"><span data-stu-id="87193-112">To load an App-V application</span></span>**

1.  <span data-ttu-id="87193-113">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**読み込み**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-113">Move the cursor to the **Results** pane, right-click the desired application, and select **Load** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-114">アプリケーションが自動的に読み込まれます。</span><span class="sxs-lookup"><span data-stu-id="87193-114">The application is automatically loaded.</span></span> <span data-ttu-id="87193-115">進捗状況は、[**パッケージステータス**というラベルの列で追跡されます。</span><span class="sxs-lookup"><span data-stu-id="87193-115">The progress is tracked in the column labeled **Package Status**.</span></span> <span data-ttu-id="87193-116">ロードが完了していることを確認するか、進行状況を表示するには、ビューを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87193-116">You must refresh the view to see that the load is complete or to see the progress.</span></span>

**<span data-ttu-id="87193-117">App-v アプリケーションをアンロードするには</span><span class="sxs-lookup"><span data-stu-id="87193-117">To unload an App-V application</span></span>**

1.  <span data-ttu-id="87193-118">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**アンロード**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-118">Move the cursor to the **Results** pane, right-click the desired application, and select **Unload** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-119">アプリケーションは自動的にアンロードされ、[**パッケージの状態**] 列が更新されて変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="87193-119">The application is automatically unloaded, and the **Package Status** column is updated to reflect the change.</span></span>

## <span data-ttu-id="87193-120">App-v アプリケーションの消去方法</span><span class="sxs-lookup"><span data-stu-id="87193-120">How to clear an App-V application</span></span>


<span data-ttu-id="87193-121">アプリケーションの仮想化クライアント管理コンソールの [**アプリケーション**] ノードの [**結果**] ウィンドウから、アプリケーションをコンソールから直接消去できます。</span><span class="sxs-lookup"><span data-stu-id="87193-121">You can clear an application from the console directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="87193-122">アプリケーションをクリアすると、そのアプリケーションに対応する設定、ショートカット、ファイルの種類の関連付けがシステムによって削除され、ユーザーのアプリケーションの一覧からもアプリケーションが削除されます。</span><span class="sxs-lookup"><span data-stu-id="87193-122">When you clear an application, the system removes the settings, shortcuts, and file type associations that correspond to the application and also removes the application from the user’s list of applications.</span></span>

<span data-ttu-id="87193-123">**注** コンソールからアプリケーションをクリアすると、そのアプリケーションは使えなくなります。</span><span class="sxs-lookup"><span data-stu-id="87193-123">**Note** When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="87193-124">ただし、アプリケーションはキャッシュ内に保持され、同じシステム上の他のユーザーは引き続き使用できます。</span><span class="sxs-lookup"><span data-stu-id="87193-124">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="87193-125">公開したアプリが更新されると、消去されたアプリケーションが再び利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="87193-125">After a publishing refresh, the cleared applications will again become available to you.</span></span> <span data-ttu-id="87193-126">パッケージに複数のアプリケーションがある場合、すべてのアプリケーションが消去されるまで、ユーザーの設定は削除されません。</span><span class="sxs-lookup"><span data-stu-id="87193-126">If there are multiple applications in a package, the user's settings are not removed until all of the applications are cleared.</span></span>

 

**<span data-ttu-id="87193-127">コンソールからアプリケーションをクリアするには</span><span class="sxs-lookup"><span data-stu-id="87193-127">To clear an application from the console</span></span>**

1.  <span data-ttu-id="87193-128">カーソルを [**結果**] ウィンドウに移動し、目的のアプリケーションを右クリックし、ポップアップメニューから [**クリア**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-128">Move the cursor to the **Results** pane, right-click the desired application, and select **Clear** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-129">確認メッセージが表示され**たら**、[はい] をクリックしてアプリケーションを削除するか、[**いいえ**] をクリックして操作を取り消します。</span><span class="sxs-lookup"><span data-stu-id="87193-129">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="87193-130">App-v アプリケーションを修復する方法</span><span class="sxs-lookup"><span data-stu-id="87193-130">How to Repair an App-V application</span></span>


<span data-ttu-id="87193-131">選択したアプリケーションを修復するには、Application Virtualization クライアント管理コンソールの**アプリケーション**ノードの [**結果**] ウィンドウから直接次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="87193-131">To repair a selected application, you can perform the following procedure directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="87193-132">アプリケーションを修復する場合は、カスタムユーザー設定を削除して、既定の設定に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="87193-132">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="87193-133">この操作では、ショートカットやファイルの種類の関連付けは変更または削除されず、キャッシュからアプリケーションが削除されることはありません。</span><span class="sxs-lookup"><span data-stu-id="87193-133">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

**<span data-ttu-id="87193-134">App-v アプリケーションを修復するには</span><span class="sxs-lookup"><span data-stu-id="87193-134">To repair an App-V application</span></span>**

1.  <span data-ttu-id="87193-135">[**結果**] ウィンドウにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="87193-135">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="87193-136">目的のアプリケーションを右クリックし、ポップアップメニューから [**修復**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-136">Right-click the desired application, and select **Repair** from the pop-up menu.</span></span>

3.  <span data-ttu-id="87193-137">確認メッセージが表示され**たら**、[はい] をクリックしてアプリケーションを修復するか、[**いいえ**] をクリックしてキャンセルします。</span><span class="sxs-lookup"><span data-stu-id="87193-137">At the confirmation prompt, click **Yes** to repair the application or **No** to cancel.</span></span>

## <span data-ttu-id="87193-138">App-v アプリケーションをインポートする方法</span><span class="sxs-lookup"><span data-stu-id="87193-138">How to import an App-V application</span></span>


<span data-ttu-id="87193-139">次の手順を使用して、application Virtualization クライアント管理コンソールの**アプリケーション**ノードの**結果**ウィンドウからキャッシュにアプリケーションを直接インポートできます。</span><span class="sxs-lookup"><span data-stu-id="87193-139">You can use the following procedure to import an application into the cache directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="87193-140">App-v アプリケーションをインポートするには</span><span class="sxs-lookup"><span data-stu-id="87193-140">To import an App-V application</span></span>**

1.  <span data-ttu-id="87193-141">カーソルを [**結果**] ウィンドウに移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**インポート**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-141">Move the cursor to the **Results** pane, right-click the desired application, and select **Import** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-142">[**参照**] ウィンドウで、目的のアプリケーションのパッケージファイルが保存されている場所に移動し、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-142">From the **Browse** window, navigate to the location of the package file for the desired application, and then click **OK**.</span></span>

    <span data-ttu-id="87193-143">**注** インポート検索パスを既に構成しているか、または SFT ファイルが最後に正常にインポートされたときと同じパスにある場合は、手順2を行う必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87193-143">**Note** If you have already configured an import search path or if the SFT file is in the same path as the last successful import, step 2 is not required.</span></span>

     

## <span data-ttu-id="87193-144">App-v アプリケーションをロックまたはロック解除する方法</span><span class="sxs-lookup"><span data-stu-id="87193-144">How to lock or unlock an App-V application</span></span>


<span data-ttu-id="87193-145">次の手順を使用して、Application Virtualization デスクトップクライアントキャッシュまたはリモートデスクトップサービス (以前のターミナルサービス) キャッシュのクライアントで、任意のアプリケーションのロックまたはロック解除を行うことができます。</span><span class="sxs-lookup"><span data-stu-id="87193-145">You can use the following procedures to lock or unlock any application in the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services (formerly Terminal Services) cache.</span></span> <span data-ttu-id="87193-146">ロックされたアプリケーションをキャッシュから削除して、新しいアプリケーションのためのスペースを確保することはできません。</span><span class="sxs-lookup"><span data-stu-id="87193-146">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="87193-147">ロックされているアプリケーションを、Application Virtualization デスクトップクライアントキャッシュまたはリモートデスクトップサービスキャッシュのクライアントから削除するには、まずロックを解除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87193-147">To remove a locked application from the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services cache, you must first unlock it.</span></span>

**<span data-ttu-id="87193-148">アプリケーションをロックするには</span><span class="sxs-lookup"><span data-stu-id="87193-148">To lock an application</span></span>**

1.  <span data-ttu-id="87193-149">[**結果**] ウィンドウにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="87193-149">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="87193-150">目的のアプリケーションを右クリックし、ポップアップメニューから [**ロック**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-150">Right-click the desired application, and select **Lock** from the pop-up menu.</span></span> <span data-ttu-id="87193-151">選択したアプリケーションがキャッシュ内でロックされます。</span><span class="sxs-lookup"><span data-stu-id="87193-151">The selected application is locked in the cache.</span></span>

**<span data-ttu-id="87193-152">アプリケーションのロックを解除するには</span><span class="sxs-lookup"><span data-stu-id="87193-152">To unlock an application</span></span>**

1.  <span data-ttu-id="87193-153">[**結果**] ウィンドウにカーソルを移動します。</span><span class="sxs-lookup"><span data-stu-id="87193-153">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="87193-154">目的のアプリケーションを右クリックし、ポップアップメニューから [**ロック解除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-154">Right-click the desired application, and select **Unlock** from the pop-up menu.</span></span> <span data-ttu-id="87193-155">選択したアプリケーションはキャッシュのロックが解除され、削除できます。</span><span class="sxs-lookup"><span data-stu-id="87193-155">The selected application is unlocked in the cache and can be removed.</span></span>

## <span data-ttu-id="87193-156">App-v アプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="87193-156">How to delete an App-V application</span></span>


<span data-ttu-id="87193-157">Application Virtualization クライアント管理コンソールで**アプリケーション**ノードを選択すると、[**結果**] ウィンドウにアプリケーションの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-157">When you select the **Application** node in the Application Virtualization Client Management Console, the **Results** pane displays a list of applications.</span></span> <span data-ttu-id="87193-158">次の手順を使用して、[**結果**] ウィンドウからアプリケーションを削除します。これにより、アプリケーションもキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="87193-158">You can use the following procedure to delete an application from the **Results** pane, which also removes the application from the cache.</span></span>

<span data-ttu-id="87193-159">**注** アプリケーションを削除すると、そのクライアントのユーザーは選択したアプリケーションを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="87193-159">**Note** When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="87193-160">ショートカットとファイルの種類の関連付けが非表示になり、アプリケーションがキャッシュから削除されます。</span><span class="sxs-lookup"><span data-stu-id="87193-160">Shortcuts and file type associations are hidden, and the application is deleted from cache.</span></span> <span data-ttu-id="87193-161">ただし、選択したアプリケーションのファイルシステムキャッシュデータのデータを別のアプリケーションが参照している場合、これらの項目は削除されません。</span><span class="sxs-lookup"><span data-stu-id="87193-161">However, if another application refers to data in the file system cache data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="87193-162">公開した後は、削除されたアプリケーションを再び利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="87193-162">After a publishing refresh, the deleted applications will again become available to you.</span></span>

 

**<span data-ttu-id="87193-163">アプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="87193-163">To delete an application</span></span>**

1.  <span data-ttu-id="87193-164">カーソルを [**結果**] ウィンドウに移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-164">Move the cursor to the **Results** pane, right-click the desired application, and select **Delete** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-165">確認メッセージが表示され**たら**、[はい] をクリックしてアプリケーションを削除するか、[**いいえ**] をクリックして操作を取り消します。</span><span class="sxs-lookup"><span data-stu-id="87193-165">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="87193-166">App-v アプリケーションアイコンを変更する方法</span><span class="sxs-lookup"><span data-stu-id="87193-166">How to change an App-V application icon</span></span>


<span data-ttu-id="87193-167">次の手順を使用して、選択したアプリケーションに関連付けられているアイコンを、Application Virtualization クライアント管理コンソールの**アプリケーション**ノードの [**結果**] ウィンドウから直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="87193-167">You can use the following procedure to change an icon associated with the selected application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="87193-168">アプリケーションアイコンを変更するには</span><span class="sxs-lookup"><span data-stu-id="87193-168">To change an application icon</span></span>**

1.  <span data-ttu-id="87193-169">カーソルを [**結果**] ウィンドウに移動し、目的のアプリケーションを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-169">Move the cursor to the **Results** pane, and right-click the desired application.</span></span>

2.  <span data-ttu-id="87193-170">[**プロパティ**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="87193-170">Select **Properties**.</span></span>

3.  <span data-ttu-id="87193-171">[**全般**] タブで、[**アイコンの変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-171">On the **General** tab, click **Change Icon**.</span></span>

4.  <span data-ttu-id="87193-172">目的のアイコンを選択するか、別の場所を参照してアイコンを選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-172">Select the desired icon, or browse to another location to select the icon.</span></span> <span data-ttu-id="87193-173">アイコンを選択したら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-173">After you've selected the icon, click **OK**.</span></span> <span data-ttu-id="87193-174">[**結果**] ウィンドウに新しいアイコンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-174">The new icon appears in the **Results** pane.</span></span>

## <span data-ttu-id="87193-175">App-v アプリケーションを追加する方法</span><span class="sxs-lookup"><span data-stu-id="87193-175">How to add an App-V application</span></span>


<span data-ttu-id="87193-176">次の手順を使用して、application Virtualization クライアント管理コンソールの**アプリケーション**ノードの [**結果**] ウィンドウからアプリケーションを直接追加することができます。</span><span class="sxs-lookup"><span data-stu-id="87193-176">You can use the following procedure to add an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="87193-177">アプリケーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="87193-177">To add an application</span></span>**

1.  <span data-ttu-id="87193-178">[**結果**] ウィンドウで右クリックし、ポップアップメニューから [**新しいアプリケーション**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-178">In the **Results** pane, right-click and select **New Application** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-179">ウィザードのページでは、次のタスクを実行できます。</span><span class="sxs-lookup"><span data-stu-id="87193-179">On the wizard page, you can perform the following tasks:</span></span>

    1.  <span data-ttu-id="87193-180">**変更アイコン**-標準の Windows アイコンのブラウザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-180">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="87193-181">目的のアイコンを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-181">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="87193-182">[ **OSD File Path または url**] —ローカル絶対パス、完全な UNC パス (ネットワーク上の共有ファイルまたはディレクトリ)、または HTTP URL を入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-182">**OSD File Path or URL**—Enter a local absolute path, a full UNC path (shared file or directory on a network), or an HTTP URL.</span></span>

    3.  <span data-ttu-id="87193-183">**(OSD 参照ボタン)**—標準ウィンドウの **[ファイルを開く**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-183">**(OSD browse button)**—Displays the standard Windows **Open File** dialog box.</span></span> <span data-ttu-id="87193-184">目的のファイルを参照して見つけます。</span><span class="sxs-lookup"><span data-stu-id="87193-184">Browse to find the desired file.</span></span>

3.  <span data-ttu-id="87193-185">[**完了**] をクリックして、[**結果**] ウィンドウにアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="87193-185">Click **Finish** to add the application to the **Results** pane.</span></span>

## <span data-ttu-id="87193-186">App-v アプリケーションのショートカットを公開する方法</span><span class="sxs-lookup"><span data-stu-id="87193-186">How to publish an App-V application shortcut</span></span>


<span data-ttu-id="87193-187">次の手順を使用して、application Virtualization クライアント管理コンソールの**アプリケーション**ノードの [**結果**] ウィンドウから、アプリケーションに直接ショートカットを公開できます。</span><span class="sxs-lookup"><span data-stu-id="87193-187">You can use the following procedure to publish shortcuts to an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="87193-188">アプリケーションのショートカットを発行するには</span><span class="sxs-lookup"><span data-stu-id="87193-188">To publish application shortcuts</span></span>**

1.  <span data-ttu-id="87193-189">[**結果**] ウィンドウにカーソルを移動し、目的のアプリケーションを右クリックして、ポップアップメニューから [**新しいショートカット**] を選んで、新しいショートカットウィザードを表示します。</span><span class="sxs-lookup"><span data-stu-id="87193-189">Move the cursor to the **Results** pane, right-click the desired application, and select **New Shortcut** from the pop-up menu to display the New Shortcut Wizard.</span></span>

2.  <span data-ttu-id="87193-190">新しいショートカットウィザードの最初のページで、アイコンを選択して、ショートカットの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="87193-190">On the first page of the New Shortcut Wizard, select an icon and specify a name for the shortcut.</span></span>

    1.  <span data-ttu-id="87193-191">**変更アイコン**-標準の Windows アイコンのブラウザーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-191">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="87193-192">目的のアイコンを参照して選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-192">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="87193-193">[**ショートカットのタイトル**の指定: ショートカットの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-193">**Shortcut Title**—Enter the name you want to give the shortcut.</span></span> <span data-ttu-id="87193-194">このフィールドの既定値は、アプリケーションの既存名とバージョンです。</span><span class="sxs-lookup"><span data-stu-id="87193-194">This field defaults to the existing name and version of the application.</span></span>

3.  <span data-ttu-id="87193-195">ウィザードの2ページ目で、公開されたショートカットの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="87193-195">On the second page of the wizard, determine the location of the published shortcut.</span></span>

    1.  <span data-ttu-id="87193-196">[**デスクトップ**] —ショートカットをデスクトップに発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87193-196">**The Desktop**—Select this check box to publish the shortcut to the desktop.</span></span>

    2.  <span data-ttu-id="87193-197">**クイック起動ツールバー**: クイック起動ツールバーにショートカットを発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87193-197">**The Quick Launch Toolbar**—Select this check box to publish the shortcut to the Quick Launch toolbar.</span></span>

    3.  <span data-ttu-id="87193-198">[**送信] メニュー**: ショートカットを [**送信**] メニューに発行するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87193-198">**The Send To Menu**—Select this check box to publish the shortcut to the **Send To** menu.</span></span>

    4.  <span data-ttu-id="87193-199">[**スタート] メニュー**の [プログラム] チェックボックスをオンにすると、この**フィールドがアクティブ**になります。</span><span class="sxs-lookup"><span data-stu-id="87193-199">**Programs in the Start Menu**—When you select the **Start Menu** check box, this field becomes active.</span></span> <span data-ttu-id="87193-200">ショートカットを [プログラム] フォルダーのルートに直接公開するには、このフィールドを空白のままにします。または、"My \ _Computer ¥ Office アプリケーション" などのフォルダー名または階層を入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-200">Leave this field blank to publish the shortcut directly to the root of the Programs folder, or enter a folder name or hierarchy—for example, "My\_Computer\\Office Applications."</span></span> <span data-ttu-id="87193-201">この方法で作成されたショートカットは、現在のユーザーに対してのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="87193-201">Shortcuts created this way are available only for the current user.</span></span>

    5.  <span data-ttu-id="87193-202">**別の場所**と**参照**ボタン— [別の**場所**] チェックボックスをオンにすると、このフィールドがアクティブになります。</span><span class="sxs-lookup"><span data-stu-id="87193-202">**Another location** and **Browse** button—When you select the **Another location** check box, this field becomes active.</span></span> <span data-ttu-id="87193-203">コンピューター上の有効な場所、または利用可能な UNC パス (ネットワーク上の共有ファイルまたはディレクトリ) を入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-203">Enter any valid location on the computer or any available UNC path (shared file or directory on a network).</span></span> <span data-ttu-id="87193-204">[**参照**] ボタンをクリックすると、Windows の標準的な **[ファイルを開く**] ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-204">The **Browse** button displays a standard Windows **File Open** dialog box.</span></span>

4.  <span data-ttu-id="87193-205">ウィザードの3ページ目で、必要なコマンドラインパラメーターを入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-205">On the third page of the wizard, enter desired command-line parameters.</span></span>

5.  <span data-ttu-id="87193-206">[**完了**] をクリックして、ショートカットを発行し、[**結果**] ウィンドウに退出します。</span><span class="sxs-lookup"><span data-stu-id="87193-206">Click **Finish** to publish the shortcuts and exit to the **Results** pane.</span></span>

## <span data-ttu-id="87193-207">App-v アプリケーションにファイルの種類の関連付けを追加する方法</span><span class="sxs-lookup"><span data-stu-id="87193-207">How to add a file type association for an App-V application</span></span>


<span data-ttu-id="87193-208">次の手順を使用して、Application Virtualization クライアント管理コンソールの [**ファイルの種類の関連付け**] ノードを使用して、ファイルの種類の関連付けを追加できます。</span><span class="sxs-lookup"><span data-stu-id="87193-208">You can use the following procedure to add a file type association, using the **File Type Associations** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="87193-209">ファイルの種類の関連付けを追加するには</span><span class="sxs-lookup"><span data-stu-id="87193-209">To add a file type association</span></span>**

1.  <span data-ttu-id="87193-210">[**ファイルの種類の関連付け**] ノードを右クリックし、ポップアップメニューから [**新しい関連付け**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-210">Right-click the **File Type Associations** node, and select **New Association** from the pop-up menu.</span></span>

2.  <span data-ttu-id="87193-211">次の情報を入力して、ダイアログボックスの最初の手順を完了し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-211">Complete the first step of the dialog box by completing the following information, and then click **Next**:</span></span>

    1.  <span data-ttu-id="87193-212">[ **Extension**—新しいファイル名の拡張子を入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-212">**Extension**—Enter a new file name extension.</span></span> <span data-ttu-id="87193-213">既定では、このフィールドは空白になります。</span><span class="sxs-lookup"><span data-stu-id="87193-213">This field is blank by default.</span></span>

    2.  <span data-ttu-id="87193-214">[**この説明を付けて新しいファイルの種類を作成**する]: アクティブなフィールドに新しいファイルの種類の説明を入力するには、このラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-214">**Create a new file type with this description**—Select this radio button to enter a new file type description in the active field.</span></span> <span data-ttu-id="87193-215">このボタンは既定でオンになっていますが、[アクティブ] フィールドが空白になっています。</span><span class="sxs-lookup"><span data-stu-id="87193-215">This button is selected by default, and the active field is blank.</span></span>

    3.  <span data-ttu-id="87193-216">[**このファイルの種類をすべてのユーザーに適用**] —すべてのユーザーに対してこの関連付けをグローバルにする場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="87193-216">**Apply this file type to all users**—Select this check box when you want this association to be global for all users.</span></span> <span data-ttu-id="87193-217">既定では、このボックスはオフになっています。</span><span class="sxs-lookup"><span data-stu-id="87193-217">By default, this box is cleared.</span></span>

    4.  <span data-ttu-id="87193-218">[**この拡張子を既存のファイルの種類にリンク**する] —拡張子を既存のファイルの種類に関連付けるには、このラジオボタンを選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-218">**Link this extension with an existing file type**—Select this radio button to associate the extension with an existing file type.</span></span> <span data-ttu-id="87193-219">ドロップダウンリストからファイルの種類を選びます。</span><span class="sxs-lookup"><span data-stu-id="87193-219">Pick a file type from the drop-down list.</span></span> <span data-ttu-id="87193-220">このオプションを選択すると、[**次へ**] が **[終了**] に変わります。</span><span class="sxs-lookup"><span data-stu-id="87193-220">When you choose this option, **Next** is changed to **Finish**.</span></span>

3.  <span data-ttu-id="87193-221">次の情報を入力して、ダイアログボックスの2番目の手順を完了し、[**完了**] をクリックしてクライアント管理コンソールに戻ります。</span><span class="sxs-lookup"><span data-stu-id="87193-221">Complete the second step of the dialog box by completing the following information, and then click **Finish** to return to the Client Management Console:</span></span>

    1.  <span data-ttu-id="87193-222">[**アイコンの変更**]: アプリケーションアイコンを変更するには、このボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-222">**Change Icon**—Click this button to change the application icon.</span></span> <span data-ttu-id="87193-223">利用可能なアイコンの1つを選ぶか、新しい場所を参照してアイコンを選びます。</span><span class="sxs-lookup"><span data-stu-id="87193-223">Select one of the available icons, or browse to a new location and select an icon.</span></span>

    2.  <span data-ttu-id="87193-224">[選択した**アプリケーションでファイルを開く**]: このラジオボタンを選択して、既存のアプリケーションでファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="87193-224">**Open files with the selected application**—Select this radio button to open the file with an existing application.</span></span> <span data-ttu-id="87193-225">使用可能なアプリケーションのドロップダウンリストからアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-225">Choose an application from the drop-down list of available applications.</span></span>

    3.  <span data-ttu-id="87193-226">**この OSD ファイルで説明されている関連付けを使用してファイルを開く**: このラジオボタンを選択して、ファイルを開くために使用するアプリケーションを決定するオープンソフトウェア記述子 (OSD) ファイルを指定します。</span><span class="sxs-lookup"><span data-stu-id="87193-226">**Open file with the association described in this OSD file**—Select this radio button to specify an Open Software Descriptor (OSD) file that determines the application used to open the file.</span></span> <span data-ttu-id="87193-227">[参照] ボタンを使用して既存の場所を選ぶか、パスまたは HTTP 形式の URL をこのフィールドに入力します。</span><span class="sxs-lookup"><span data-stu-id="87193-227">Use the browse button to select an existing location, or enter a path or HTTP-formatted URL in this field.</span></span>

## <span data-ttu-id="87193-228">App-v アプリケーションのファイルの種類の関連付けを削除する方法</span><span class="sxs-lookup"><span data-stu-id="87193-228">How to delete a file type association for an App-V application</span></span>


<span data-ttu-id="87193-229">次の手順を使用して、ファイルの種類の関連付けを削除することができます。</span><span class="sxs-lookup"><span data-stu-id="87193-229">You can use the following procedure to delete a file type association.</span></span> <span data-ttu-id="87193-230">[**ファイルの種類の関連付け**] ノードは、**スコープ**ウィンドウの**Application Virtualization**ノードの1つ下のレベルです。</span><span class="sxs-lookup"><span data-stu-id="87193-230">The **File Type Associations** node is one level below the **Application Virtualization** node in the **Scope** pane.</span></span> <span data-ttu-id="87193-231">このノードを選択すると、[**結果**] ウィンドウにファイルの種類の関連付けの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="87193-231">When you select this node, the **Results** pane displays a list of file type associations.</span></span>

**<span data-ttu-id="87193-232">ファイルの種類の関連付けを削除するには</span><span class="sxs-lookup"><span data-stu-id="87193-232">To remove a file type association</span></span>**

1.  <span data-ttu-id="87193-233">[**結果**] ウィンドウで、削除するファイルの種類の関連付けの拡張子を右クリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-233">In the **Results** pane, right-click the extension of the file type association you want to delete.</span></span>

2.  <span data-ttu-id="87193-234">ポップアップメニューから [**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="87193-234">Select **Delete** from the pop-up menu.</span></span>

3.  <span data-ttu-id="87193-235">関連付けを削除するには [**はい]** をクリックし、[**結果**] ウィンドウに戻るには [**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="87193-235">Click **Yes** to delete the association, or click **No** to return to the **Results** pane.</span></span>

## <span data-ttu-id="87193-236">関連トピック</span><span class="sxs-lookup"><span data-stu-id="87193-236">Related topics</span></span>


[<span data-ttu-id="87193-237">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="87193-237">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





