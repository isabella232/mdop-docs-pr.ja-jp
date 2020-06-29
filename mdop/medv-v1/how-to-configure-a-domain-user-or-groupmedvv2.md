---
title: ドメイン ユーザーまたはグループを構成する方法
description: ドメイン ユーザーまたはグループを構成する方法
author: dansimp
ms.assetid: 055aba81-a9c9-4b98-969d-775e603becf3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c51da13808df657c1341572767c24860d9d5e8b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827197"
---
# <span data-ttu-id="adbbf-103">ドメイン ユーザーまたはグループを構成する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-103">How to Configure a Domain User or Group</span></span>


<span data-ttu-id="adbbf-104">展開設定を使用すると、MED-V ワークスペースにアクセスできるユーザーまたはグループ、および MED-V ワークスペースを利用できる期間と、オフラインで使用できるかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-104">The deployment settings enable you to control which users or groups can access the MED-V workspace, as well as how long the MED-V workspace can be utilized and whether it can be used offline.</span></span> <span data-ttu-id="adbbf-105">また、MED-V ワークスペースとホストの間のアクセスを制御するための追加の規則を構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-105">You can also configure additional rules to control access between the MED-V workspace and the host.</span></span>

<span data-ttu-id="adbbf-106">すべての MED-V ワークスペースのアクセス許可は、[**展開**] タブの**ポリシー**モジュールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-106">All MED-V workspace permissions are configured in the **Policy** module, on the **Deployment** tab.</span></span>

<span data-ttu-id="adbbf-107">ユーザーが MED-V ワークスペースを利用できるようにするには、まずドメインユーザーまたはグループを MED-V ワークスペースのアクセス許可に追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-107">To allow users to utilize the MED-V workspace, you must first add domain users or groups to the MED-V workspace permissions.</span></span> <span data-ttu-id="adbbf-108">次に、ユーザーまたはグループごとにアクセス許可を設定できます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-108">You can then set permissions for each user or group.</span></span>

## <span data-ttu-id="adbbf-109">ドメインユーザーまたはグループを追加する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-109">How to Add a Domain User or Group</span></span>


**<span data-ttu-id="adbbf-110">ドメインユーザーまたはグループを追加するには</span><span class="sxs-lookup"><span data-stu-id="adbbf-110">To add a domain user or group</span></span>**

1.  <span data-ttu-id="adbbf-111">[**ユーザー/グループ**] ウィンドウで、[追加] をクリックし**ます。**</span><span class="sxs-lookup"><span data-stu-id="adbbf-111">In the **Users / Groups** window, click **Add.**</span></span>

2.  <span data-ttu-id="adbbf-112">[**ユーザーまたはグループ名の入力**] ダイアログボックスで、次のいずれかの操作を行ってドメインユーザーまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-112">In the **Enter User or Group names** dialog box, select domain users or groups by doing one of the following:</span></span>

    -   <span data-ttu-id="adbbf-113">[**ユーザーまたはグループ名の入力**] フィールドに、ドメイン内に存在するか、またはコンピューター上のローカルユーザーまたはグループとして存在するユーザーまたはグループを入力します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-113">In the **Enter User or Group names** field, type a user or group that exists in the domain or as a local user or group on the computer.</span></span> <span data-ttu-id="adbbf-114">次に、[**名前の確認**] をクリックして、存在する完全な名前に解決します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-114">Then click **Check Names** to resolve it to the full existent name.</span></span>

    -   <span data-ttu-id="adbbf-115">[**検索**] をクリックして、[標準の**ユーザーまたはグループの選択**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-115">Click **Find** to open the standard **Select Users or Groups** dialog box.</span></span> <span data-ttu-id="adbbf-116">次に、[ドメインユーザーまたはグループ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-116">Then select domain users or groups.</span></span>

3.  <span data-ttu-id="adbbf-117">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-117">Click **OK**.</span></span>

    <span data-ttu-id="adbbf-118">ドメインユーザーまたはグループが追加されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-118">The domain users or groups are added.</span></span>

    **<span data-ttu-id="adbbf-119">注</span><span class="sxs-lookup"><span data-stu-id="adbbf-119">Note</span></span>**  
    <span data-ttu-id="adbbf-120">信頼されたドメインのユーザーは手動で追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-120">Users from trusted domains should be added manually.</span></span>



~~~
**Warning**  
Do not run the management application from a computer that is part of a domain that is not trusted by the domain the server is installed on.
~~~



## <span data-ttu-id="adbbf-121">ドメインユーザーまたはグループを削除する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-121">How to Remove a Domain User or Group</span></span>


**<span data-ttu-id="adbbf-122">ドメインユーザーまたはグループを削除するには</span><span class="sxs-lookup"><span data-stu-id="adbbf-122">To remove a domain user or group</span></span>**

1.  <span data-ttu-id="adbbf-123">[**ユーザー/グループ**] ウィンドウで、ユーザーまたはグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-123">In the **Users / Groups** window, select a user or group.</span></span>

2.  <span data-ttu-id="adbbf-124">[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-124">Click **Remove**.</span></span>

    <span data-ttu-id="adbbf-125">ユーザーまたはグループが削除されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-125">The user or group is deleted.</span></span>

## <span data-ttu-id="adbbf-126">ユーザーまたはグループに対して権限を設定する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-126">How to Set Permissions for a User or a Group</span></span>


**<span data-ttu-id="adbbf-127">ユーザーまたはグループに対してアクセス許可を設定するには</span><span class="sxs-lookup"><span data-stu-id="adbbf-127">To set permissions for a user or a group</span></span>**

1.  <span data-ttu-id="adbbf-128">権限を設定するユーザーまたはグループをクリックします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-128">Click the user or group for which you are setting the permissions.</span></span>

2.  <span data-ttu-id="adbbf-129">次の表で説明するように、MED-V ワークスペースのプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-129">Configure the MED-V workspace properties as described in the following table.</span></span>

3.  <span data-ttu-id="adbbf-130">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-130">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="adbbf-131">ワークスペース展開のプロパティ</span><span class="sxs-lookup"><span data-stu-id="adbbf-131">Workspace Deployment Properties</span></span>**

<span data-ttu-id="adbbf-132">プロパティの説明の*概要*</span><span class="sxs-lookup"><span data-stu-id="adbbf-132">Property Description *General*</span></span>

<span data-ttu-id="adbbf-133">ユーザーまたはグループのワークスペースを有効にする &lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="adbbf-133">Enable Workspace for &lt;user or group&gt;</span></span>

<span data-ttu-id="adbbf-134">このユーザーまたはグループの MED-V ワークスペースを有効にするには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-134">Select this check box to enable the MED-V workspace for this user or group.</span></span>

<span data-ttu-id="adbbf-135">この日付にワークスペースの有効期限が切れます</span><span class="sxs-lookup"><span data-stu-id="adbbf-135">Workspace expires on this date</span></span>

<span data-ttu-id="adbbf-136">このチェックボックスをオンにすると、このユーザーまたはグループに設定されているアクセス許可の有効期限が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-136">Select this check box to assign an expiration date for the permissions set for this user or group.</span></span>

<span data-ttu-id="adbbf-137">選択すると、[日付] ボックスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-137">When selected, the date box is enabled.</span></span> <span data-ttu-id="adbbf-138">日付を設定すると、指定した日付の最後にアクセス許可の有効期限が切れます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-138">Set the date, and permissions will expire at the end of the date specified.</span></span>

<span data-ttu-id="adbbf-139">オフライン作業は、に制限されています</span><span class="sxs-lookup"><span data-stu-id="adbbf-139">Offline work is restricted to</span></span>

<span data-ttu-id="adbbf-140">このチェックボックスをオンにすると、このユーザーまたはグループに対してポリシーを更新する必要がある期間が割り当てられます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-140">Select this check box to assign a time period in which the policy must be refreshed for this user or group.</span></span> <span data-ttu-id="adbbf-141">選択すると、[期間] ボックスが有効になります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-141">When selected, the time period box is enabled.</span></span> <span data-ttu-id="adbbf-142">日数または時間数を設定すると、指定した期間の終了時に、ユーザーまたはグループは、ポリシーが更新されていない場合は接続できなくなります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-142">Set the number of days or hours, and at the end of the specified time period, the user or group will not be able to connect if the policy is not refreshed.</span></span>

<span data-ttu-id="adbbf-143">ワークスペースの削除オプション</span><span class="sxs-lookup"><span data-stu-id="adbbf-143">Workspace deletion options</span></span>

<span data-ttu-id="adbbf-144">クリックして、MED-V ワークスペースの削除オプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-144">Click to set the MED-V workspace deletion options.</span></span> <span data-ttu-id="adbbf-145">詳細については、「 [Med-v ワークスペースの削除オプションを設定する方法](how-to-set-med-v-workspace-deletion-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbbf-145">For more information, see [How to Set MED-V Workspace Deletion Options](how-to-set-med-v-workspace-deletion-options.md).</span></span>

*<span data-ttu-id="adbbf-146">データの転送</span><span class="sxs-lookup"><span data-stu-id="adbbf-146">Data Transfer</span></span>*

<span data-ttu-id="adbbf-147">ホストとワークスペースの間のクリップボードのサポート</span><span class="sxs-lookup"><span data-stu-id="adbbf-147">Support clipboard between host and Workspace</span></span>

<span data-ttu-id="adbbf-148">このチェックボックスをオンにすると、ホストと MED-V ワークスペースの間でコピーと貼り付けを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-148">Select this check box to enable copying and pasting between the host and the MED-V workspace.</span></span>

<span data-ttu-id="adbbf-149">ホストとワークスペース間のファイル転送をサポートする</span><span class="sxs-lookup"><span data-stu-id="adbbf-149">Support file transfer between the host and Workspace</span></span>

<span data-ttu-id="adbbf-150">このチェックボックスをオンにすると、host と MED-V のワークスペースとの間でファイルを転送できるようになります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-150">Select this check box to enable transferring files between the host and MED-V workspace.</span></span> <span data-ttu-id="adbbf-151">[**ファイルの転送**] ボックスで、次のいずれかのオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="adbbf-151">Select one of the following options from the **File Transfer** box:</span></span>

-   <span data-ttu-id="adbbf-152">**Both**: ホストと med-v ワークスペースの間でのファイルの転送を有効にします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-152">**Both**—Enable transferring files between the host and the MED-V workspace.</span></span>

-   <span data-ttu-id="adbbf-153">[**ホストからワークスペースへ**] —ホストから med-v ワークスペースにファイルを転送できるようにします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-153">**Host to Workspace**—Enable transferring files from the host to the MED-V workspace.</span></span>

-   <span data-ttu-id="adbbf-154">[**ホストへのワークスペース**] — med-v ワークスペースからホストにファイルを転送できるようにします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-154">**Workspace to Host**—Enable transferring files from the MED-V workspace to the host.</span></span>

**<span data-ttu-id="adbbf-155">注</span><span class="sxs-lookup"><span data-stu-id="adbbf-155">Note</span></span>**  
<span data-ttu-id="adbbf-156">アクセス許可を持たないユーザーがファイルを転送しようとした場合、ファイル送信を実行する権限を持つユーザーの資格情報を入力するように求めるウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-156">If a user without permissions attempts to transfer files, a window will appear prompting him to enter the credentials of a user with permissions to perform the file transfer.</span></span>



**<span data-ttu-id="adbbf-157">重要</span><span class="sxs-lookup"><span data-stu-id="adbbf-157">Important</span></span>**  
<span data-ttu-id="adbbf-158">Windows XP SP3 でのファイル送信をサポートするには、次のようにレジストリを編集して、オフラインファイルの同期を無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-158">To support file transfer in Windows XP SP3, you must disable offline file synchronization by editing the registry as follows:</span></span>

`REG ADD HKLM\software\microsoft\windows\currentversion\netcache /V Enabled /T REG_DWORD /F /D 0`



<span data-ttu-id="adbbf-159">詳細設定</span><span class="sxs-lookup"><span data-stu-id="adbbf-159">Advanced</span></span>

<span data-ttu-id="adbbf-160">[詳細なファイル転送] オプションを設定するには、をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adbbf-160">Click to set the advanced file transfer options.</span></span> <span data-ttu-id="adbbf-161">詳細については、「[詳細なファイル転送オプションを設定する方法](how-to-set-advanced-file-transfer-options.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="adbbf-161">For more information, see [How to Set Advanced File Transfer Options](how-to-set-advanced-file-transfer-options.md).</span></span>

*<span data-ttu-id="adbbf-162">デバイスコントロール</span><span class="sxs-lookup"><span data-stu-id="adbbf-162">Device Control</span></span>*

<span data-ttu-id="adbbf-163">ホストに接続されているプリンターへの印刷を有効にする</span><span class="sxs-lookup"><span data-stu-id="adbbf-163">Enable printing to printers connected to the host</span></span>

<span data-ttu-id="adbbf-164">このチェックボックスをオンにすると、ユーザーはホストプリンターを使用して、MED-V ワークスペースから印刷できるようになります。</span><span class="sxs-lookup"><span data-stu-id="adbbf-164">Select this check box to enable users to print from the MED-V workspace using the host printer.</span></span>

**<span data-ttu-id="adbbf-165">注</span><span class="sxs-lookup"><span data-stu-id="adbbf-165">Note</span></span>**  
<span data-ttu-id="adbbf-166">印刷は、ホストで定義されているプリンターによって実行されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-166">The printing is performed by the printers defined on the host.</span></span>



<span data-ttu-id="adbbf-167">CD/DVD へのアクセスを有効にする</span><span class="sxs-lookup"><span data-stu-id="adbbf-167">Enable access to CD / DVD</span></span>

<span data-ttu-id="adbbf-168">このチェックボックスをオンにすると、この MED-V ワークスペースから CD または DVD ドライブへのアクセスが許可されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-168">Select this check box to allow access to a CD or DVD drive from this MED-V workspace.</span></span>



**<span data-ttu-id="adbbf-169">複数のメンバーシップ</span><span class="sxs-lookup"><span data-stu-id="adbbf-169">Multiple Memberships</span></span>**

1.  <span data-ttu-id="adbbf-170">ユーザーがグループの一部であり、ユーザーがそのグループの一部であるグループにもアクセス許可を適用する場合、すべてのアクセス許可が適用されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-170">If the user is part of a group and permissions are applied to the user as well as to the group they are part of, all permissions are applied.</span></span>

2.  <span data-ttu-id="adbbf-171">ユーザーが2つの異なるグループのメンバーである場合は、最も制限の少ないアクセス許可が適用されます。</span><span class="sxs-lookup"><span data-stu-id="adbbf-171">If the user is a member of two different groups, the least restrictive permissions are applied.</span></span>

## <span data-ttu-id="adbbf-172">関連トピック</span><span class="sxs-lookup"><span data-stu-id="adbbf-172">Related topics</span></span>


[<span data-ttu-id="adbbf-173">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="adbbf-173">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="adbbf-174">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="adbbf-174">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="adbbf-175">MED-V ワークスペース削除オプションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-175">How to Set MED-V Workspace Deletion Options</span></span>](how-to-set-med-v-workspace-deletion-options.md)

[<span data-ttu-id="adbbf-176">高度なファイル転送のオプションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="adbbf-176">How to Set Advanced File Transfer Options</span></span>](how-to-set-advanced-file-transfer-options.md)









