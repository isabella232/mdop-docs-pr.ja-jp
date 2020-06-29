---
title: MED-V ワークスペースに仮想マシンの設定を適用する方法
description: MED-V ワークスペースに仮想マシンの設定を適用する方法
author: dansimp
ms.assetid: b50d0dfb-8d61-4543-9607-a29bbb1ed45f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9662bb8202285d51971eeea8beaef938b98ed6b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825974"
---
# <span data-ttu-id="57be4-103">MED-V ワークスペースに仮想マシンの設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="57be4-103">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>


<span data-ttu-id="57be4-104">すべての MED-V ワークスペースには、Microsoft 仮想 PC の画像が関連付けられている必要があります。</span><span class="sxs-lookup"><span data-stu-id="57be4-104">Every MED-V workspace must have a Microsoft Virtual PC image associated with it.</span></span> <span data-ttu-id="57be4-105">仮想マシンの設定では、仮想 PC イメージの割り当てだけでなく、仮想マシンの他のプロパティを設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="57be4-105">The virtual machine settings enable you to assign a Virtual PC image as well as set other virtual machine properties.</span></span>

<span data-ttu-id="57be4-106">すべての仮想マシン設定は、[**仮想マシンの設定**] タブの**ポリシー**モジュールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-106">All virtual machine settings are configured in the **Policy** module, on the **Virtual Machine Settings** tab.</span></span>

**<span data-ttu-id="57be4-107">仮想マシンの設定を MED-V ワークスペースに適用するには</span><span class="sxs-lookup"><span data-stu-id="57be4-107">To apply virtual machine settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="57be4-108">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="57be4-108">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="57be4-109">次の表で説明するように、仮想マシンのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="57be4-109">Configure the virtual machine properties as described in the following table.</span></span>

3.  <span data-ttu-id="57be4-110">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="57be4-110">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="57be4-111">仮想マシンのプロパティ</span><span class="sxs-lookup"><span data-stu-id="57be4-111">Virtual Machine Properties</span></span>**

<span data-ttu-id="57be4-112">プロパティの説明の*仮想マシンの設定*</span><span class="sxs-lookup"><span data-stu-id="57be4-112">Property Description *Virtual Machine Settings*</span></span>

<span data-ttu-id="57be4-113">割り当てられた画像</span><span class="sxs-lookup"><span data-stu-id="57be4-113">Assigned Image</span></span>

<span data-ttu-id="57be4-114">MED-V ワークスペースに割り当てられている実際の Microsoft 仮想 PC イメージ。</span><span class="sxs-lookup"><span data-stu-id="57be4-114">The actual Microsoft Virtual PC image assigned to the MED-V workspace.</span></span> <span data-ttu-id="57be4-115">メニューには、使用可能なすべての Virtual PC イメージの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-115">The menu provides a list of all available Virtual PC images.</span></span> <span data-ttu-id="57be4-116">次の種類の画像は、**アクティブな**画像リストに含まれています。</span><span class="sxs-lookup"><span data-stu-id="57be4-116">The following image types are in the **Active** image list:</span></span>

-   <span data-ttu-id="57be4-117">**ローカルのテストイメージ**—まだパックされていないローカルコンピューター上の画像。</span><span class="sxs-lookup"><span data-stu-id="57be4-117">**Local test images**—Images on the local computer that are not yet packed.</span></span> <span data-ttu-id="57be4-118">これらの画像名の後には、かっこ内に "test" という単語が続くため、テスト目的でのみ使用されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-118">These image names are followed by the word “test” in parentheses (test) and are for testing purposes only.</span></span>

-   <span data-ttu-id="57be4-119">**ローカルのパック**された画像-ローカルコンピューター上のパックされた画像。</span><span class="sxs-lookup"><span data-stu-id="57be4-119">**Local packed images**—Packed images on the local computer.</span></span> <span data-ttu-id="57be4-120">これらの画像の後には、かっこ内に "local" という語が続くため、管理者がサーバーにアップロードするまでは、クライアントでダウンロードすることはできません。</span><span class="sxs-lookup"><span data-stu-id="57be4-120">These images are followed by the word “local” in parentheses (local) and cannot be downloaded by clients until the administrator uploads them to the server.</span></span>

    <span data-ttu-id="57be4-121">[ローカルイメージ] は、リムーバブルメディア (USB や DVD など) 経由でクライアントに配布されるパッケージを作成する場合に選択できます。</span><span class="sxs-lookup"><span data-stu-id="57be4-121">A local image can be selected if you are creating a package that will be distributed to the client via removable media (such as USB or DVD).</span></span>

-   <span data-ttu-id="57be4-122">**サーバー上のパック**された画像 (サーバー上の画像、クライアントからダウンロード可能)。</span><span class="sxs-lookup"><span data-stu-id="57be4-122">**Packed images on server**—Images that are on the server and are available for download by clients.</span></span> <span data-ttu-id="57be4-123">[更新] をクリックして、画像の一覧を更新します。</span><span class="sxs-lookup"><span data-stu-id="57be4-123">Click Refresh to refresh the images list.</span></span>

    <span data-ttu-id="57be4-124">**注** 各 MED-V ワークスペースの画像は、1つの Windows ユーザーのみが使用できます。</span><span class="sxs-lookup"><span data-stu-id="57be4-124">**Note** Each MED-V workspace image can only be used by one Windows user.</span></span>

     

<span data-ttu-id="57be4-125">ワークスペースは永続的</span><span class="sxs-lookup"><span data-stu-id="57be4-125">Workspace is persistent</span></span>

<span data-ttu-id="57be4-126">MED-V ワークスペースを永続的として構成するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="57be4-126">Select this check box to configure the MED-V workspace as persistent.</span></span> <span data-ttu-id="57be4-127">永続的な MED ワークスペースでは、MED-V ワークスペースが停止すると、med-v ワークスペースの変更と追加が、MED-V ワークスペースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-127">In a persistent MED-V workspace, when the MED-V workspace is stopped, changes and additions to the MED-V workspace are saved in the MED-V workspace.</span></span>

<span data-ttu-id="57be4-128">ドメイン MED-V ワークスペースの場合は、このオプションを選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57be4-128">For a Domain MED-V workspace, this option must be selected.</span></span>

<span data-ttu-id="57be4-129">**注** MED-V ワークスペースをユーザーに展開した後は、この設定を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="57be4-129">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="57be4-130">ワークスペースを停止するときに VM をシャットダウンする</span><span class="sxs-lookup"><span data-stu-id="57be4-130">Shut down the VM when stopping the Workspace</span></span>

<span data-ttu-id="57be4-131">このチェックボックスをオンにすると、MED-V ワークスペースの停止時に仮想マシンがシャットダウンされます。</span><span class="sxs-lookup"><span data-stu-id="57be4-131">Select this check box to shut down the virtual machine when stopping the MED-V workspace.</span></span> <span data-ttu-id="57be4-132">このチェックボックスをオフにすると、各セッションが完了したときに仮想マシンはシャットダウンされず、仮想マシンのスナップショットを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="57be4-132">If this check box is cleared, at the completion of each session, the virtual machine is not shut down but instead takes a snapshot of the virtual machine.</span></span> <span data-ttu-id="57be4-133">新しいセッションが開始されると、Windows はスナップショットから開始されます (つまり、Windows は再起動せず、ログインは必要ありません)。</span><span class="sxs-lookup"><span data-stu-id="57be4-133">Upon the initiation of a new session, Windows starts from the snapshot (that is, Windows does not restart and no login is required).</span></span>

<span data-ttu-id="57be4-134">**注** このプロパティは、**ワークスペースが永続的**に選択されている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="57be4-134">**Note** This property is enabled only if **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="57be4-135">MED-V の資格情報 (SSO) を使って、VM で Windows にログオンする</span><span class="sxs-lookup"><span data-stu-id="57be4-135">Logon to Windows in VM using MED-V credentials (SSO)</span></span>

<span data-ttu-id="57be4-136">このチェックボックスをオンにすると、MED-V クライアントにログインしたときに入力した MED-V 資格情報を使用して仮想マシン上の Windows にログインします。</span><span class="sxs-lookup"><span data-stu-id="57be4-136">Select this check box to log in to Windows on the virtual machine by using the MED-V credentials entered when logging in to MED-V client.</span></span>

<span data-ttu-id="57be4-137">**注** このプロパティは、**ワークスペースが永続的**に選択されている場合にのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="57be4-137">**Note** This property is enabled only when **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="57be4-138">ワークスペースは revertible</span><span class="sxs-lookup"><span data-stu-id="57be4-138">Workspace is revertible</span></span>

<span data-ttu-id="57be4-139">このチェックボックスをオンにすると、MED-V ワークスペースが revertible として構成されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-139">Select this check box to configure the MED-V workspace as revertible.</span></span> <span data-ttu-id="57be4-140">Revertible MED ワークスペースでは、各セッションが完了すると (つまり、ユーザーが MED-V ワークスペースを停止したとき)、MED-V ワークスペースは展開時に表示されていた元の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="57be4-140">In a revertible MED-V workspace, at the completion of each session (that is, when the user stops the MED-V workspace), the MED-V workspace reverts to the original state it was in during deployment.</span></span> <span data-ttu-id="57be4-141">ユーザーが行った変更や追加は、セッション間の MED-V ワークスペースに保存されません。</span><span class="sxs-lookup"><span data-stu-id="57be4-141">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span>

<span data-ttu-id="57be4-142">**注** MED-V ワークスペースをユーザーに展開した後は、この設定を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="57be4-142">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="57be4-143">ワークスペースのタイムゾーンをホストと同期する</span><span class="sxs-lookup"><span data-stu-id="57be4-143">Synchronize Workspace time zone with host</span></span>

<span data-ttu-id="57be4-144">このチェックボックスをオンにすると、MED-V ワークスペースのタイムゾーンがホストと同期されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-144">Select this check box to synchronize the time zone in the MED-V workspace with the host.</span></span>

<span data-ttu-id="57be4-145">MED-V ワークスペースが常設か revertible かによって、次のように同期の動作が異なります。</span><span class="sxs-lookup"><span data-stu-id="57be4-145">The synchronization works differently depending on whether the MED-V workspace is persistent or revertible, as follows:</span></span>

-   <span data-ttu-id="57be4-146">永続的な MED-V ワークスペースでは、タイムゾーンは最初にサーバーとの同期を試みます。</span><span class="sxs-lookup"><span data-stu-id="57be4-146">In a persistent MED-V workspace, the time zone first tries to synchronize with the server.</span></span> <span data-ttu-id="57be4-147">失敗した場合は、ホストと同期します。</span><span class="sxs-lookup"><span data-stu-id="57be4-147">If that fails, it synchronizes with the host.</span></span>

-   <span data-ttu-id="57be4-148">Revertible MED ワークスペースでは、タイムゾーンはホストと同期されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-148">In a revertible MED-V workspace, the time zone synchronizes with the host.</span></span>

*<span data-ttu-id="57be4-149">ロック設定</span><span class="sxs-lookup"><span data-stu-id="57be4-149">Lock Settings</span></span>*

<span data-ttu-id="57be4-150">Host standby/hibernate イベントのワークスペースをロックする</span><span class="sxs-lookup"><span data-stu-id="57be4-150">Lock the Workspace on host standby/hibernate event</span></span>

<span data-ttu-id="57be4-151">ホストコンピューターがスタンバイまたは休止状態になったときに、MED-V ワークスペースを自動的にロックするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="57be4-151">Select this check box to automatically lock the MED-V workspace when the host computer goes into standby or hibernate.</span></span>

<span data-ttu-id="57be4-152">ワークスペースをロックするのは、</span><span class="sxs-lookup"><span data-stu-id="57be4-152">Lock the Workspace after</span></span>

<span data-ttu-id="57be4-153">このチェックボックスをオンにすると、MED-V ワークスペースが指定した期間アイドル状態にあるときに、MED-V ワークスペースがロックされます。</span><span class="sxs-lookup"><span data-stu-id="57be4-153">Select this check box to lock the MED-V workspace when the MED-V workspace is idle for a specified period of time.</span></span> <span data-ttu-id="57be4-154">選択すると、[番号] ボックスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="57be4-154">When selected, the number box is enabled.</span></span> <span data-ttu-id="57be4-155">MED-V ワークスペースをロックするまでのアイドル時間 (分) を入力します。</span><span class="sxs-lookup"><span data-stu-id="57be4-155">Enter the number of minutes of idle time before locking the MED-V workspace.</span></span>

<span data-ttu-id="57be4-156">**注** アイドル時間は、(ホストアプリケーションではなく) MED-V ワークスペースアプリケーションを指します。</span><span class="sxs-lookup"><span data-stu-id="57be4-156">**Note** The idle time refers to the MED-V workspace applications (not the host applications).</span></span>

 

*<span data-ttu-id="57be4-157">イメージの更新設定</span><span class="sxs-lookup"><span data-stu-id="57be4-157">Image Update Settings</span></span>*

<span data-ttu-id="57be4-158">保持</span><span class="sxs-lookup"><span data-stu-id="57be4-158">Keep only</span></span>

<span data-ttu-id="57be4-159">このチェックボックスをオンにすると、保持する古い画像のバージョンの数が制限されます。</span><span class="sxs-lookup"><span data-stu-id="57be4-159">Select this check box to limit the number of old image versions to keep.</span></span>

<span data-ttu-id="57be4-160">選択すると、[番号] ボックスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="57be4-160">When selected, the number box is enabled.</span></span> <span data-ttu-id="57be4-161">保持する以前のバージョンの数を入力します。</span><span class="sxs-lookup"><span data-stu-id="57be4-161">Enter the number of old versions to keep.</span></span>

<span data-ttu-id="57be4-162">新しいバージョンが利用可能になったときに更新プログラムを提案する</span><span class="sxs-lookup"><span data-stu-id="57be4-162">Suggest update when a new version is available</span></span>

<span data-ttu-id="57be4-163">このチェックボックスをオンにすると、画像の新しいバージョンが利用可能になったときに、更新プログラムが提案されます (強制されません)。</span><span class="sxs-lookup"><span data-stu-id="57be4-163">Select this check box to suggest (but not force) an update when a new version of the image is available.</span></span>

<span data-ttu-id="57be4-164">クライアントは、このワークスペースの画像をダウンロードするときに、トリミング転送を使用する必要があります</span><span class="sxs-lookup"><span data-stu-id="57be4-164">Clients should use Trim Transfer when downloading images for this Workspace</span></span>

<span data-ttu-id="57be4-165">このチェックボックスをオンにすると、この MED-V ワークスペースに関連付けられている画像をダウンロードするときに、トリム転送が有効になります (詳細については、「 [Med-v トリム転送テクノロジ](med-v-trim-transfer-technology-medvv2.md)」を参照してください)。</span><span class="sxs-lookup"><span data-stu-id="57be4-165">Select this check box to enable Trim Transfer (for more information, see [MED-V Trim Transfer Technology](med-v-trim-transfer-technology-medvv2.md)) when downloading images associated with this MED-V workspace.</span></span> <span data-ttu-id="57be4-166">このチェックボックスをオフにすると、完全な画像がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="57be4-166">If this check box is cleared, the full image will be downloaded.</span></span>

<span data-ttu-id="57be4-167">**注** トリミング転送にはハードドライブのインデックスを作成する必要があります。これには時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="57be4-167">**Note** Trim Transfer requires indexing the hard drive, which might take a considerable amount of time.</span></span> <span data-ttu-id="57be4-168">ハードドライブのインデックスを作成する場合は、既存のバージョンと同じバージョンのイメージをダウンロードする場合など、新しい画像バージョンをダウンロードするよりも、トリミング転送を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57be4-168">It is recommended to use Trim Transfer when indexing the hard drive is more efficient than downloading the new image version, such as when downloading an image version that is similar to the existing version.</span></span>

 

 

## <span data-ttu-id="57be4-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="57be4-169">Related topics</span></span>


[<span data-ttu-id="57be4-170">MED-V イメージの作成</span><span class="sxs-lookup"><span data-stu-id="57be4-170">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="57be4-171">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="57be4-171">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="57be4-172">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="57be4-172">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





