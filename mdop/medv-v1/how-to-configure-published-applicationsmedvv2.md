---
title: 公開されたアプリケーションを構成する方法
description: 公開されたアプリケーションを構成する方法
author: dansimp
ms.assetid: 43a59ff7-5d4e-49dc-84e5-1082bc4dd8f4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cb5736382f03e818ef10aa814a8e61044ca2b73a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824314"
---
# <span data-ttu-id="ddb82-103">公開されたアプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-103">How to Configure Published Applications</span></span>


<span data-ttu-id="ddb82-104">ホストオペレーティングシステムと互換性のないアプリケーションは、MED-V ワークスペース内で実行し、デスクトップから開始する場合と同じ方法で、[スタート] メニューまたはローカルのホストショートカットから開始する方法と同じ方法で、med-v ワークスペース内で実行できます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-104">Applications that are not compatible with the host operating system can be run within the MED-V workspace and initiated from within the MED-V workspace the same way they are initiated from the desktop—from the Start menu or from a local host shortcut.</span></span> <span data-ttu-id="ddb82-105">選択して定義されたアプリケーションは、"公開アプリケーション" と呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-105">Applications selected and defined are called published applications.</span></span> <span data-ttu-id="ddb82-106">このセクションの手順では、公開されたアプリケーションを追加および削除する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-106">The procedures in this section describe how to add and remove published applications.</span></span>

<span data-ttu-id="ddb82-107">アプリケーションは、次のいずれかの方法で公開できます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-107">An application can be published in one of the following ways:</span></span>

-   <span data-ttu-id="ddb82-108">アプリケーションとして: アプリケーションのコマンドラインに入力して、特定のアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-108">As an application—Select a specific application by typing in the command line for the application.</span></span> <span data-ttu-id="ddb82-109">選択されたアプリケーションのみが公開されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-109">Only the application selected is published.</span></span>

-   <span data-ttu-id="ddb82-110">メニューとして: 複数のアプリケーションが含まれているフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-110">As a menu—Select a folder that contains multiple applications.</span></span> <span data-ttu-id="ddb82-111">フォルダー内のすべてのアプリケーションが公開され、メニューとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-111">All applications within the folder are published and displayed as a menu.</span></span>

## <a href="" id="bkmk-addingapublishedapplication"></a><span data-ttu-id="ddb82-112">公開されたアプリケーションを MED-V ワークスペースに追加する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-112">How to Add a Published Application to a MED-V Workspace</span></span>


**<span data-ttu-id="ddb82-113">MED-V ワークスペースにアプリケーションを追加するには</span><span class="sxs-lookup"><span data-stu-id="ddb82-113">To add an application to the MED-V workspace</span></span>**

1.  <span data-ttu-id="ddb82-114">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-114">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="ddb82-115">[**アプリケーション**] ウィンドウの [公開された**アプリケーション**] セクションで、[**追加**] をクリックして新しいアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-115">In the **Applications** pane, in the **Published Applications** section, click **Add** to add a new application.</span></span>

3.  <span data-ttu-id="ddb82-116">次の表で説明するように、アプリケーションのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-116">Configure the application properties as described in the following table.</span></span>

4.  <span data-ttu-id="ddb82-117">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-117">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="ddb82-118">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-118">Note</span></span>**  
    <span data-ttu-id="ddb82-119">Web リダイレクションが適切に動作するように Internet Explorer を公開アプリケーションとして設定している場合は、パラメーターがかっこ内にないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="ddb82-119">If you are setting Internet Explorer as a published application to ensure that Web redirection works properly, make certain that any parameters are not in parentheses.</span></span>



**<span data-ttu-id="ddb82-120">公開されたアプリケーションのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ddb82-120">Published Application Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ddb82-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ddb82-121">Property</span></span></th>
<th align="left"><span data-ttu-id="ddb82-122">説明</span><span class="sxs-lookup"><span data-stu-id="ddb82-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ddb82-123">有効</span><span class="sxs-lookup"><span data-stu-id="ddb82-123">Enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-124">公開されているアプリケーションを有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-124">Select this check box to enable the published application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ddb82-125">表示名</span><span class="sxs-lookup"><span data-stu-id="ddb82-125">Display name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-126">ユーザー&#39;s Windows の [スタート] メニューのショートカットの名前。</span><span class="sxs-lookup"><span data-stu-id="ddb82-126">The name of the shortcut in the user&#39;s Windows Start menu.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ddb82-127">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-127">Note</span></span></strong><br/><p><span data-ttu-id="ddb82-128">表示名には <strong> 、 </strong> 大文字と小文字は区別されません。</span><span class="sxs-lookup"><span data-stu-id="ddb82-128">The display name is <strong>not</strong> case sensitive.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ddb82-129">説明</span><span class="sxs-lookup"><span data-stu-id="ddb82-129">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-130">公開されたアプリケーションの説明。ユーザー&#39;s マウスをショートカットの上に置いたときにヒントとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-130">A description of the published application, which appears as a tooltip when the user&#39;s mouse hovers over the shortcut.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ddb82-131">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="ddb82-131">Command line</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-132">MED-V ワークスペース内からアプリケーションを実行するために使用されるコマンド。</span><span class="sxs-lookup"><span data-stu-id="ddb82-132">The command used to run the application from within the MED-V workspace.</span></span> <span data-ttu-id="ddb82-133">完全なパスが必要であり、他の Windows コマンドと同様の方法でパラメーターをアプリケーションに渡すことができます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-133">The full path is required, and the parameters can be passed to the application in a similar fashion as in any other Windows command.</span></span></p>
<p><span data-ttu-id="ddb82-134">Revertible MED ワークスペースでは、mapnetworkdrive のパスを使ったネットワークドライブ &quot; <em> &lt; &gt; &lt; &gt; </em> &quot; ( &quot; <em> mapnetworkdrive t: \ tux\ date など) </em> &quot; をマップできます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-134">In a revertible MED-V workspace, you can map a network drive with MapNetworkDrive syntax: &quot;<em>MapNetworkDrive &lt;drive&gt; &lt;path&gt;</em>&quot;—for example, &quot;<em>MapNetworkDrive t: \tux\date</em>&quot;.</span></span></p>
<p><span data-ttu-id="ddb82-135">たとえば、Windows エクスプローラーを公開するには、次の構文を使用します。 &quot; <em> c: &lt; /em &gt; &quot; または &quot; <em> c:\windows </em> 。&quot;</span><span class="sxs-lookup"><span data-stu-id="ddb82-135">For example, to publish Windows Explorer, use the following syntax: &quot;<em>c:&lt;/em&gt;&quot; or &quot;<em>c:\windows</em>.&quot;</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ddb82-136">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-136">Note</span></span></strong><br/><p><span data-ttu-id="ddb82-137">名前解決を行うには、次のいずれかを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb82-137">To have a name resolution, you need to perform one of the following:</span></span></p>
</div>
<div>

</div>
<ul>
<li><p><span data-ttu-id="ddb82-138">ベースの MED-V ワークスペースイメージで DNS を構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-138">Configure the DNS in the base MED-V workspace image.</span></span></p></li>
<li><p><span data-ttu-id="ddb82-139">DNS 解決がホストで定義されていることを確認し、ホスト DNS を使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-139">Verify the DNS resolution is defined in the host, and configure it to use the host DNS.</span></span></p></li>
<li><p><span data-ttu-id="ddb82-140">ネットワークドライブの定義には IP を使用します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-140">Use the IP for defining the network drive.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="ddb82-141">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-141">Note</span></span></strong><br/><p><span data-ttu-id="ddb82-142">パスにスペースが含まれている場合は、パス全体を引用符で囲む必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb82-142">If the path includes spaces, the entire path must be inside quotation marks.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="ddb82-143">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-143">Note</span></span></strong><br/><p><span data-ttu-id="ddb82-144">パスの末尾にはバックスラッシュ () を使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="ddb82-144">The path should not end with a backslash ().</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ddb82-145">スタート メニュー</span><span class="sxs-lookup"><span data-stu-id="ddb82-145">Start menu</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-146">このチェックボックスをオンにすると、ユーザー&#39;s Windows の [スタート] メニューにアプリケーションのショートカットが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-146">Select this check box to create a shortcut for the application in the user&#39;s Windows Start menu.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="ddb82-147">公開されているすべてのアプリケーションは、Windows の [**スタート**] メニューにショートカットとして表示されます ([**すべてのプログラム] &gt; &gt; med-v アプリケーションを起動**します)。</span><span class="sxs-lookup"><span data-stu-id="ddb82-147">All published applications appear as shortcuts in the Windows **Start** menu (**Start &gt;All Programs&gt; MED-V Applications**).</span></span>

## <span data-ttu-id="ddb82-148">MED-V ワークスペースから公開されたアプリケーションを削除する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-148">How to Remove a Published Application from a MED-V Workspace</span></span>


**<span data-ttu-id="ddb82-149">MED-V ワークスペースからアプリケーションを削除するには</span><span class="sxs-lookup"><span data-stu-id="ddb82-149">To remove an application from the MED-V workspace</span></span>**

1.  <span data-ttu-id="ddb82-150">MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-150">Click a MED-V workspace.</span></span>

2.  <span data-ttu-id="ddb82-151">[**アプリケーション**] ウィンドウの [公開された**アプリケーション**] セクションで、削除するアプリケーションを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-151">In the **Applications** pane, in the **Published Applications** section, select an application to remove.</span></span>

3.  <span data-ttu-id="ddb82-152">[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-152">Click **Remove**.</span></span>

    <span data-ttu-id="ddb82-153">アプリケーションが公開されたアプリケーションのリストから削除されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-153">The application is removed from the list of published applications.</span></span>

4.  <span data-ttu-id="ddb82-154">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-154">On the **Policy** menu, select **Commit**.</span></span>

## <span data-ttu-id="ddb82-155">公開したメニューを MED-V ワークスペースに追加する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-155">How to Add a Published Menu to a MED-V Workspace</span></span>


**<span data-ttu-id="ddb82-156">公開したメニューを MED-V ワークスペースに追加するには</span><span class="sxs-lookup"><span data-stu-id="ddb82-156">To add a published menu to the MED-V workspace</span></span>**

1.  <span data-ttu-id="ddb82-157">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-157">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="ddb82-158">[**アプリケーション**] ウィンドウの [**発行済みメニュー** ] セクションで、[**追加**] をクリックして新しいメニューを追加します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-158">In the **Applications** pane, in the **Published Menus** section, click **Add** to add a new menu.</span></span>

3.  <span data-ttu-id="ddb82-159">次の表で説明するように、メニューのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-159">Configure the menu properties as described in the following table.</span></span>

4.  <span data-ttu-id="ddb82-160">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-160">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="ddb82-161">発行済みメニューのプロパティ</span><span class="sxs-lookup"><span data-stu-id="ddb82-161">Published Menu Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ddb82-162">プロパティ</span><span class="sxs-lookup"><span data-stu-id="ddb82-162">Property</span></span></th>
<th align="left"><span data-ttu-id="ddb82-163">説明</span><span class="sxs-lookup"><span data-stu-id="ddb82-163">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ddb82-164">有効</span><span class="sxs-lookup"><span data-stu-id="ddb82-164">Enabled</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-165">このチェックボックスをオンにすると、公開されたメニューが有効になります。</span><span class="sxs-lookup"><span data-stu-id="ddb82-165">Select this check box to enable the published menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ddb82-166">表示名</span><span class="sxs-lookup"><span data-stu-id="ddb82-166">Display name</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-167">ユーザー&#39;s Windows の [スタート] メニューのショートカットの名前。</span><span class="sxs-lookup"><span data-stu-id="ddb82-167">The name of the shortcut in the user&#39;s Windows Start menu.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ddb82-168">説明</span><span class="sxs-lookup"><span data-stu-id="ddb82-168">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-169">ユーザー&#39;s マウスをショートカットの上に置いたときのヒントとして表示される説明。</span><span class="sxs-lookup"><span data-stu-id="ddb82-169">The description, which appears as a tooltip when the user&#39;s mouse hovers over the shortcut.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ddb82-170">ワークスペース内のフォルダー</span><span class="sxs-lookup"><span data-stu-id="ddb82-170">Folder in workspace</span></span></p></td>
<td align="left"><p><span data-ttu-id="ddb82-171">フォルダー内のすべてのアプリケーションを含むメニューとして公開するフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-171">Select the folder to publish as a menu containing all the applications within the folder.</span></span></p>
<p><span data-ttu-id="ddb82-172">表示されるテキストは、[プログラム] フォルダーからの相対パスです。</span><span class="sxs-lookup"><span data-stu-id="ddb82-172">The text displayed is a relative path from the Programs folder.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ddb82-173">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-173">Note</span></span></strong><br/><p><span data-ttu-id="ddb82-174">空白のままにすると、ホスト上のすべてのプログラムがメニューとして発行されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-174">If left blank, all programs on the host will be published as a menu.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="ddb82-175">公開されているすべてのメニューは、Windows の [**スタート**] メニュー ([すべてのプログラム]、[\*\* &gt; すべて &gt; のプログラム\*\*]) にショートカットとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-175">All published menus appear as shortcuts in the Windows **Start** menu (**Start &gt;All Programs&gt; MED-V Applications**).</span></span> <span data-ttu-id="ddb82-176">ショートカットの名前を変更するには、[**スタート] メニューのショートカットフォルダ**フィールドを設定します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-176">You can change the name of the shortcut in the **Start-menu shortcuts folder** field.</span></span>

**<span data-ttu-id="ddb82-177">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-177">Note</span></span>**  
<span data-ttu-id="ddb82-178">2つの MED-V ワークスペースを構成するときは、[スタート] メニューのショートカットフォルダーに対して別の名前を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-178">When configuring two MED-V workspaces, it is recommended to configure a different name for the Start menu shortcuts folder.</span></span>



## <span data-ttu-id="ddb82-179">MED-V ワークスペースから公開されたメニューを削除する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-179">How to Remove a Published Menu from a MED-V Workspace</span></span>


**<span data-ttu-id="ddb82-180">MED-V ワークスペースから公開されたメニューを削除するには</span><span class="sxs-lookup"><span data-stu-id="ddb82-180">To remove a published menu from a MED-V workspace</span></span>**

1.  <span data-ttu-id="ddb82-181">MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-181">Click a MED-V workspace.</span></span>

2.  <span data-ttu-id="ddb82-182">[**アプリケーション**] ウィンドウの [**発行済みメニュー** ] セクションで、削除するメニューを選択します。</span><span class="sxs-lookup"><span data-stu-id="ddb82-182">In the **Applications** pane, in the **Published Menus** section, select a menu to remove.</span></span>

3.  <span data-ttu-id="ddb82-183">[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ddb82-183">Click **Remove**.</span></span>

    <span data-ttu-id="ddb82-184">メニューが公開されたメニューの一覧から削除されます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-184">The menu is removed from the list of published menus.</span></span>

4.  <span data-ttu-id="ddb82-185">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-185">On the **Policy** menu, select **Commit**.</span></span>

## <span data-ttu-id="ddb82-186">クライアントのコマンドラインから公開されたアプリケーションを実行する</span><span class="sxs-lookup"><span data-stu-id="ddb82-186">Running a Published Application from a Command Line on the Client</span></span>


<span data-ttu-id="ddb82-187">管理者は、次のコマンドを使用して、デスクトップショートカットなど、任意の場所から公開されたアプリケーションを実行できます。</span><span class="sxs-lookup"><span data-stu-id="ddb82-187">The administrator can run published applications from any location, such as a desktop shortcut, using the following command:</span></span>

``` syntax
"<Install path>\Manager\KidaroCommands.exe" /run "<published application name>" "<MED-V workspace name>"
```

**<span data-ttu-id="ddb82-188">注</span><span class="sxs-lookup"><span data-stu-id="ddb82-188">Note</span></span>**  
<span data-ttu-id="ddb82-189">公開したアプリケーションが定義されている MED-V ワークスペースが実行されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ddb82-189">The MED-V workspace in which the published application is defined must be running.</span></span>



## <span data-ttu-id="ddb82-190">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ddb82-190">Related topics</span></span>


[<span data-ttu-id="ddb82-191">高度な設定で公開されたアプリケーションを編集する方法</span><span class="sxs-lookup"><span data-stu-id="ddb82-191">How to Edit a Published Application with Advanced Settings</span></span>](how-to-edit-a-published-application-with-advanced-settings.md)

[<span data-ttu-id="ddb82-192">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="ddb82-192">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="ddb82-193">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="ddb82-193">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)









