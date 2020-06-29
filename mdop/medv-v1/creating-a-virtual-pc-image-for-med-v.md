---
title: MED-V の仮想 PC イメージの作成
description: MED-V の仮想 PC イメージの作成
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823664"
---
# <span data-ttu-id="69a42-103">MED-V の仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="69a42-103">Creating a Virtual PC Image for MED-V</span></span>


<span data-ttu-id="69a42-104">MED-V 用の仮想 PC (VPC) イメージを作成するには、次の手順を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a42-104">To create a Virtual PC (VPC) image for MED-V, you must perform the following:</span></span>

1.  <span data-ttu-id="69a42-105">[VPC イメージを作成](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)します。</span><span class="sxs-lookup"><span data-stu-id="69a42-105">[Create a VPC image](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc).</span></span>

2.  <span data-ttu-id="69a42-106">[MED ワークスペースの .msi パッケージを VPC イメージにインストール](#bkmk-howtoinstallthemedvworkspacemsipackage)します。</span><span class="sxs-lookup"><span data-stu-id="69a42-106">[Install the MED-V workspace .msi package onto the VPC image](#bkmk-howtoinstallthemedvworkspacemsipackage).</span></span>

3.  <span data-ttu-id="69a42-107">[VPC イメージに対して、med-v 仮想マシンの前提条件ツールを実行](#bkmk-howtorunthevirtualmachineprerequisitestool)します。</span><span class="sxs-lookup"><span data-stu-id="69a42-107">[Run the MED-V virtual machine prerequisites tool on the VPC image](#bkmk-howtorunthevirtualmachineprerequisitestool).</span></span>

4.  <span data-ttu-id="69a42-108">[VPC イメージの仮想マシンの前提条件を手動で構成](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)します。</span><span class="sxs-lookup"><span data-stu-id="69a42-108">[Manually configure virtual machine prerequisites on the VPC image](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites).</span></span>

5.  <span data-ttu-id="69a42-109">[Sysprep を med-v イメージ用に構成](#bkmk-howtoconfiguresysprepformedvimages)します (省略可能)。</span><span class="sxs-lookup"><span data-stu-id="69a42-109">[Configure Sysprep for MED-V images](#bkmk-howtoconfiguresysprepformedvimages) (optional).</span></span>

6.  <span data-ttu-id="69a42-110">[Microsoft VIRTUAL PC をオフに](#bkmk-turningoffmicrosoftvirtualpc)します。</span><span class="sxs-lookup"><span data-stu-id="69a42-110">[Turn off Microsoft Virtual PC](#bkmk-turningoffmicrosoftvirtualpc).</span></span>

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="69a42-111">Microsoft Virtual PC を使用して仮想 PC イメージを作成する</span><span class="sxs-lookup"><span data-stu-id="69a42-111">Creating a Virtual PC Image by Using Microsoft Virtual PC</span></span>


<span data-ttu-id="69a42-112">Microsoft Virtual PC を使用して仮想 PC イメージを作成する方法については、「仮想 pc のドキュメント」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a42-112">To create a Virtual PC image using Microsoft Virtual PC, refer to the Virtual PC documentation.</span></span>

<span data-ttu-id="69a42-113">詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a42-113">For more information, see the following:</span></span>

-   [<span data-ttu-id="69a42-114">Windows Virtual PC のヘルプ</span><span class="sxs-lookup"><span data-stu-id="69a42-114">Windows Virtual PC Help</span></span>](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [<span data-ttu-id="69a42-115">仮想マシンを作成し、ゲストオペレーティングシステムをインストールする</span><span class="sxs-lookup"><span data-stu-id="69a42-115">Create a virtual machine and install a guest operating system</span></span>](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a><span data-ttu-id="69a42-116">MED-V のワークスペース .msi パッケージをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="69a42-116">How to Install the MED-V Workspace .msi Package</span></span>


<span data-ttu-id="69a42-117">仮想 PC イメージを作成したら、MED-V workspace .msi パッケージをイメージにインストールします。</span><span class="sxs-lookup"><span data-stu-id="69a42-117">After the Virtual PC image is created, install the MED-V workspace .msi package onto the image.</span></span>

**<span data-ttu-id="69a42-118">MED-V ワークスペースのイメージをインストールするには</span><span class="sxs-lookup"><span data-stu-id="69a42-118">To install the MED-V workspace image</span></span>**

1.  <span data-ttu-id="69a42-119">仮想マシンを起動して、MED-V の workspace パッケージを内部にコピーします。</span><span class="sxs-lookup"><span data-stu-id="69a42-119">Start the virtual machine, and copy the MED-V workspace .msi package inside.</span></span>

    <span data-ttu-id="69a42-120">MED-V のワークスペースパッケージは*MED-V\_workspace\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="69a42-120">The MED-V workspace .msi package is called *MED-V\_workspace\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="69a42-121">たとえば、 *MED-V\_workspace\_1.0.65.msi*とします。</span><span class="sxs-lookup"><span data-stu-id="69a42-121">For example, *MED-V\_workspace\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="69a42-122">MED-V のワークスペース .msi パッケージをダブルクリックして、インストールウィザードの指示に従います。</span><span class="sxs-lookup"><span data-stu-id="69a42-122">Double-click the MED-V workspace .msi package, and follow the installation wizard instructions.</span></span>

    **<span data-ttu-id="69a42-123">注</span><span class="sxs-lookup"><span data-stu-id="69a42-123">Note</span></span>**  
    <span data-ttu-id="69a42-124">新しい MED-V バージョンがリリースされ、既存の Virtual PC イメージが更新されたら、既存の MED-V workspace パッケージをアンインストールし、コンピューターを再起動して、新しい MED-V workspace パッケージをインストールします。</span><span class="sxs-lookup"><span data-stu-id="69a42-124">When a new MED-V version is released, and an existing Virtual PC image is updated, uninstall the existing MED-V workspace .msi package, reboot the computer, and install the new MED-V workspace .msi package.</span></span>



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a><span data-ttu-id="69a42-125">仮想マシンの前提条件ツールを実行する方法</span><span class="sxs-lookup"><span data-stu-id="69a42-125">How to Run the Virtual Machine Prerequisites Tool</span></span>


<span data-ttu-id="69a42-126">仮想マシン (VM) の前提条件ツールは、いくつかの前提条件を自動化するためのウィザードです。</span><span class="sxs-lookup"><span data-stu-id="69a42-126">The virtual machine (VM) prerequisites tool is a wizard that automates several of the prerequisites.</span></span>

**<span data-ttu-id="69a42-127">注</span><span class="sxs-lookup"><span data-stu-id="69a42-127">Note</span></span>**  
<span data-ttu-id="69a42-128">ウィザードでは多くのパラメーターを設定できますが、MED-V の適切な機能に必要なプロパティは構成できません。</span><span class="sxs-lookup"><span data-stu-id="69a42-128">Although many parameters are configurable in the wizard, the properties required for the proper functioning of MED-V are not configurable.</span></span>



**<span data-ttu-id="69a42-129">仮想マシンの前提条件ツールを実行するには</span><span class="sxs-lookup"><span data-stu-id="69a42-129">To run the virtual machine prerequisites tool</span></span>**

1.  <span data-ttu-id="69a42-130">MED-V のワークスペース .msi パッケージをインストールした後、Windows の [**スタート**] メニューで [すべてのプログラム] を選びます\*\* &gt; &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="69a42-130">After the MED-V workspace .msi package is installed, on the Windows **Start** menu, select **All Programs &gt; MED-V &gt; VM Prerequisites Tool**.</span></span>

    **<span data-ttu-id="69a42-131">注</span><span class="sxs-lookup"><span data-stu-id="69a42-131">Note</span></span>**  
    <span data-ttu-id="69a42-132">仮想マシンの前提条件ツールを実行しているユーザーは、ローカル管理者権限が必要であり、ログインしているユーザーだけである必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a42-132">The user running the virtual machine prerequisites tool must have local administrator rights and must be the only user logged in.</span></span>



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. <span data-ttu-id="69a42-133">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-133">Click **Next**.</span></span>

3. <span data-ttu-id="69a42-134">[ **Windows の設定**] ページで、次の構成プロパティから構成するものを選択します。</span><span class="sxs-lookup"><span data-stu-id="69a42-134">On the **Windows Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="69a42-135">ユーザーの個人の履歴情報をクリアする</span><span class="sxs-lookup"><span data-stu-id="69a42-135">Clear users’ personal history information</span></span>**

   -   **<span data-ttu-id="69a42-136">ローカルプロファイルの一時ディレクトリをクリアする</span><span class="sxs-lookup"><span data-stu-id="69a42-136">Clear local profiles temp directory</span></span>**

   -   **<span data-ttu-id="69a42-137">[開始]、[ログオン]、[ログオフ] を使用して、次の Windows イベントのサウンドを無効にする</span><span class="sxs-lookup"><span data-stu-id="69a42-137">Disable sounds on following Windows events: start, logon, logoff</span></span>**

   **<span data-ttu-id="69a42-138">注</span><span class="sxs-lookup"><span data-stu-id="69a42-138">Note</span></span>**  
   <span data-ttu-id="69a42-139">グループポリシーでは、Windows のページセーバーを有効にしないでください。</span><span class="sxs-lookup"><span data-stu-id="69a42-139">Do not enable Windows page saver in a group policy.</span></span>



4. <span data-ttu-id="69a42-140">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-140">Click **Next**.</span></span>

5. <span data-ttu-id="69a42-141">**Internet Explorer**の [設定] ページで、次の構成可能なプロパティから、構成するものを選択します。</span><span class="sxs-lookup"><span data-stu-id="69a42-141">On the **Internet Explorer Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="69a42-142">オートコンプリート機能を使用しない</span><span class="sxs-lookup"><span data-stu-id="69a42-142">Don't use auto complete features</span></span>**

   -   **<span data-ttu-id="69a42-143">ショートカットを起動するための windows の再使用を無効にする</span><span class="sxs-lookup"><span data-stu-id="69a42-143">Disable reuse of windows for launching shortcuts</span></span>**

   -   **<span data-ttu-id="69a42-144">閲覧の履歴を消去する</span><span class="sxs-lookup"><span data-stu-id="69a42-144">Clear browsing history</span></span>**

   -   **<span data-ttu-id="69a42-145">Internet Explorer 7 でタブ表示を有効にする</span><span class="sxs-lookup"><span data-stu-id="69a42-145">Enable tabbed browsing in Internet Explorer 7</span></span>**

6. <span data-ttu-id="69a42-146">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-146">Click **Next**.</span></span>

7. <span data-ttu-id="69a42-147">[ **Windows Services** ] ページで、次の構成プロパティから構成するものを選択します。</span><span class="sxs-lookup"><span data-stu-id="69a42-147">On the **Windows Services** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="69a42-148">セキュリティセンターサービス</span><span class="sxs-lookup"><span data-stu-id="69a42-148">Security center service</span></span>**

   -   **<span data-ttu-id="69a42-149">タスクスケジューラサービス</span><span class="sxs-lookup"><span data-stu-id="69a42-149">Task scheduler service</span></span>**

   -   **<span data-ttu-id="69a42-150">自動更新サービス</span><span class="sxs-lookup"><span data-stu-id="69a42-150">Automatic updates service</span></span>**

   -   **<span data-ttu-id="69a42-151">システムの復元サービス</span><span class="sxs-lookup"><span data-stu-id="69a42-151">System restore service</span></span>**

   -   **<span data-ttu-id="69a42-152">インデックスサービス</span><span class="sxs-lookup"><span data-stu-id="69a42-152">Indexing service</span></span>**

   -   **<span data-ttu-id="69a42-153">ワイヤレスゼロ構成</span><span class="sxs-lookup"><span data-stu-id="69a42-153">Wireless Zero Configuration</span></span>**

   -   **<span data-ttu-id="69a42-154">ユーザーの切り替えの高速化</span><span class="sxs-lookup"><span data-stu-id="69a42-154">Fast User Switching Compatibility</span></span>**

8. <span data-ttu-id="69a42-155">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-155">Click **Next**.</span></span>

9. <span data-ttu-id="69a42-156">Windows の**自動ログオン**ページで、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="69a42-156">On the **Windows Auto Logon** page, do the following:</span></span>

   1.  <span data-ttu-id="69a42-157">[ **Windows の自動ログオンを有効にする**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="69a42-157">Select the **Enable Windows Auto Logon** check box.</span></span>

   2.  <span data-ttu-id="69a42-158">**ユーザー名**と**パスワード**を割り当てます。</span><span class="sxs-lookup"><span data-stu-id="69a42-158">Assign a **User name** and **Password**.</span></span>

10. <span data-ttu-id="69a42-159">[**適用**] をクリックし、表示される確認ボックスで [**はい]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-159">Click **Apply**, and in the confirmation box that appears, click **Yes**.</span></span>

11. <span data-ttu-id="69a42-160">[**概要**] ページで、[**完了**] をクリックしてウィザードを終了します。</span><span class="sxs-lookup"><span data-stu-id="69a42-160">On the **Summary** page, click **Finish** to quit the wizard</span></span>

**<span data-ttu-id="69a42-161">注</span><span class="sxs-lookup"><span data-stu-id="69a42-161">Note</span></span>**  
<span data-ttu-id="69a42-162">グループポリシーによって、前提条件ツールで設定した必須設定が上書きされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a42-162">Verify that group policies do not overwrite the mandatory settings set in the prerequisites tool.</span></span>



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a><span data-ttu-id="69a42-163">MED-V 仮想マシンの手動インストールの前提条件を構成する方法</span><span class="sxs-lookup"><span data-stu-id="69a42-163">How to Configure MED-V Virtual Machine Manual Installation Prerequisites</span></span>


<span data-ttu-id="69a42-164">仮想マシンの前提条件ツールを使用して構成することはできません。また、手動で実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a42-164">Several of the configurations cannot be configured through the virtual machine prerequisites tool and must be performed manually.</span></span>

-   <span data-ttu-id="69a42-165">仮想マシンの設定</span><span class="sxs-lookup"><span data-stu-id="69a42-165">Virtual Machine Settings</span></span>

    <span data-ttu-id="69a42-166">Microsoft Virtual PC 本体で次の仮想マシン設定を構成することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="69a42-166">It is recommended to configure the following virtual machine settings in the Microsoft Virtual PC console:</span></span>

    -   <span data-ttu-id="69a42-167">フロッピーディスクドライブを無効にします。</span><span class="sxs-lookup"><span data-stu-id="69a42-167">Disable floppy disk drives.</span></span>

    -   <span data-ttu-id="69a42-168">元に戻す-ディスク (**設定の &gt; 取り消し-ディスク**) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="69a42-168">Disable undo-disks (**Settings &gt; undo-disks**).</span></span>

    -   <span data-ttu-id="69a42-169">画像に仮想 CPU が1つしかないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a42-169">Ensure that the image has only one virtual CPU.</span></span>

    -   <span data-ttu-id="69a42-170">仮想マシンとユーザーの間の相互作用を排除します (たとえば、ユーザー入力を要求するメッセージなどの公開されたアプリケーションに関連していない場合)。</span><span class="sxs-lookup"><span data-stu-id="69a42-170">Eliminate interactions between the virtual machine and the user, where they are not related to published applications (such as, messages requiring user input).</span></span>

-   <span data-ttu-id="69a42-171">イメージの設定</span><span class="sxs-lookup"><span data-stu-id="69a42-171">Image Settings</span></span>

    <span data-ttu-id="69a42-172">イメージ内で次の手動設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="69a42-172">Configure the following manual settings inside the image:</span></span>

    1.  <span data-ttu-id="69a42-173">[**電源オプションのプロパティ**] ウィンドウで、休止状態とスリープを無効にします。</span><span class="sxs-lookup"><span data-stu-id="69a42-173">In the **Power Options Properties** window, disable hibernation and sleep.</span></span>

    2.  <span data-ttu-id="69a42-174">最新の Windows 更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="69a42-174">Apply the most recent Windows updates.</span></span>

    3.  <span data-ttu-id="69a42-175">[ **Windows の起動と回復**] ダイアログボックスの [**システムエラー** ] セクションで、[**自動的に再起動**する] チェックボックスをオフにします。</span><span class="sxs-lookup"><span data-stu-id="69a42-175">In the **Windows Startup and Recovery** dialog box, in the **System Failure** section, clear the **Automatically restart** check box.</span></span>

    4.  <span data-ttu-id="69a42-176">画像が VLK のライセンスキーを使用していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="69a42-176">Ensure that the image uses a VLK license key.</span></span>

-   <span data-ttu-id="69a42-177">VPC の追加機能のインストール</span><span class="sxs-lookup"><span data-stu-id="69a42-177">Installing VPC Additions</span></span>

    <span data-ttu-id="69a42-178">[**操作**] メニューで、[ **Virtual Machine の追加機能のインストールまたは更新**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="69a42-178">On the **Action** menu, select **Install or Update Virtual Machine Additions**.</span></span>

-   <span data-ttu-id="69a42-179">印刷を設定する</span><span class="sxs-lookup"><span data-stu-id="69a42-179">Configuring Printing</span></span>

    <span data-ttu-id="69a42-180">MED-V ワークスペースからの印刷は、次のいずれかの方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="69a42-180">You can configure printing from the MED-V workspace in either of the following ways:</span></span>

    -   <span data-ttu-id="69a42-181">仮想マシンにプリンターを追加します。</span><span class="sxs-lookup"><span data-stu-id="69a42-181">Add a printer to the virtual machine.</span></span>

    -   <span data-ttu-id="69a42-182">ホストコンピューターで構成されているプリンターを使用して印刷を許可します。</span><span class="sxs-lookup"><span data-stu-id="69a42-182">Allow printing with printers that are configured on the host computer.</span></span>

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a><span data-ttu-id="69a42-183">Sysprep を MED-V イメージ用に構成する方法</span><span class="sxs-lookup"><span data-stu-id="69a42-183">How to Configure Sysprep for MED-V Images</span></span>


<span data-ttu-id="69a42-184">MED-V ワークスペースでは、固有のセキュリティ ID (SID) を割り当てるために Sysprep を構成できます。特に、複数の MED-V ワークスペースが1台のコンピューターで実行されている場合です。</span><span class="sxs-lookup"><span data-stu-id="69a42-184">In a MED-V workspace, Sysprep can be configured in order to assign unique security ID (SID), particularly when multiple MED-V workspaces are run on a single computer.</span></span> <span data-ttu-id="69a42-185">Sysprep を使ってドメインに参加することはお勧めしません。代わりに、「[スクリプトアクションのセットアップ方法](how-to-set-up-script-actions.md)」の説明に従って、med-v join domain スクリプトアクションを使います。</span><span class="sxs-lookup"><span data-stu-id="69a42-185">It is not recommended to use Sysprep to join a domain; instead, use the MED-V join domain script action as described in [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

**<span data-ttu-id="69a42-186">注</span><span class="sxs-lookup"><span data-stu-id="69a42-186">Note</span></span>**  
<span data-ttu-id="69a42-187">Sysprep は、Windows オペレーティングシステム用の Microsoft のシステム準備ユーティリティです。</span><span class="sxs-lookup"><span data-stu-id="69a42-187">Sysprep is Microsoft's system preparation utility for the Windows operating system.</span></span>



**<span data-ttu-id="69a42-188">MED-V ワークスペースで Sysprep を構成するには</span><span class="sxs-lookup"><span data-stu-id="69a42-188">To configure Sysprep in a MED-V workspace</span></span>**

1.  <span data-ttu-id="69a42-189">*Sysprep*という名前のシステムドライブのルートにディレクトリを作成します。</span><span class="sxs-lookup"><span data-stu-id="69a42-189">Create a directory in the root of the system drive named *Sysprep*.</span></span>

2.  <span data-ttu-id="69a42-190">Windows インストール CD からシステムドライブのルートに*deploy.cab*を抽出するか、Microsoft Web サイトから最新の展開ツールの更新プログラムをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="69a42-190">From the Windows installation CD, extract *deploy.cab* to the root of the system drive, or download the latest Deployment Tools update from the Microsoft Web site.</span></span>

    -   <span data-ttu-id="69a42-191">Windows 2000 の場合は、「 [windows 2000 の展開ツールの更新プログラム](https://go.microsoft.com/fwlink/?LinkId=143001)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a42-191">For Windows 2000, see [Deployment Tools update for Windows 2000](https://go.microsoft.com/fwlink/?LinkId=143001).</span></span>

    -   <span data-ttu-id="69a42-192">Windows XP の場合は、「 [WINDOWS xp の展開ツールの更新プログラム](https://go.microsoft.com/fwlink/?LinkId=143000)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="69a42-192">For Windows XP, see [Deployment Tools update for Windows XP](https://go.microsoft.com/fwlink/?LinkId=143000).</span></span>

3.  <span data-ttu-id="69a42-193">**セットアップマネージャー** (setupmgr.exe) を実行します。</span><span class="sxs-lookup"><span data-stu-id="69a42-193">Run **Setup Manager** (setupmgr.exe).</span></span>

4.  <span data-ttu-id="69a42-194">セットアップマネージャーウィザードに従います。</span><span class="sxs-lookup"><span data-stu-id="69a42-194">Follow the Setup Manager wizard.</span></span>

<span data-ttu-id="69a42-195">Sysprep を構成し、MED-V ワークスペースを作成したら、Sysprep を実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="69a42-195">After Sysprep is configured and the MED-V workspace is created, Sysprep must be executed.</span></span>

**<span data-ttu-id="69a42-196">Sysprep を実行するには</span><span class="sxs-lookup"><span data-stu-id="69a42-196">To run Sysprep</span></span>**

1.  <span data-ttu-id="69a42-197">システムドライブのルートにある Sysprep フォルダーで、システム準備ツール (Sysprep.exe) を実行します。</span><span class="sxs-lookup"><span data-stu-id="69a42-197">From the Sysprep folder located in the root of the system drive, run the System Preparation Tool (Sysprep.exe).</span></span>

2.  <span data-ttu-id="69a42-198">警告メッセージボックスが表示されたら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-198">In the warning message box that appears, click **OK**.</span></span>

3.  <span data-ttu-id="69a42-199">[ **Sysprep のプロパティ**] ダイアログボックスで、[**ライセンス認証の猶予期間をリセット**し、**ミニセットアップを使用する**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="69a42-199">In the **Sysprep Properties** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes.</span></span>

4.  <span data-ttu-id="69a42-200">[再**シール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="69a42-200">Click **Reseal**.</span></span>

5.  <span data-ttu-id="69a42-201">表示される確認メッセージボックスに記載されている情報に問題がある場合は、[**キャンセル**] をクリックして選択内容を変更します。</span><span class="sxs-lookup"><span data-stu-id="69a42-201">If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and change the selections.</span></span>

6.  <span data-ttu-id="69a42-202">[ **OK** ] をクリックして、システム準備プロセスを完了します。</span><span class="sxs-lookup"><span data-stu-id="69a42-202">Click **OK** to complete the system preparation process.</span></span>

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a><span data-ttu-id="69a42-203">Microsoft Virtual PC の無効化</span><span class="sxs-lookup"><span data-stu-id="69a42-203">Turning Off Microsoft Virtual PC</span></span>


<span data-ttu-id="69a42-204">すべてのコンポーネントをインストールして構成したら、Microsoft Virtual PC を閉じて、[**無効にする**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="69a42-204">After all the components are installed and configured, close Microsoft Virtual PC and select **Turn Off**.</span></span>

## <span data-ttu-id="69a42-205">関連トピック</span><span class="sxs-lookup"><span data-stu-id="69a42-205">Related topics</span></span>


<span data-ttu-id="69a42-206">MED-V イメージの作成[スクリプトアクションのセットアップ方法](how-to-set-up-script-actions.md)</span><span class="sxs-lookup"><span data-stu-id="69a42-206">Creating a MED-V Image [How to Set Up Script Actions](how-to-set-up-script-actions.md)</span></span>









