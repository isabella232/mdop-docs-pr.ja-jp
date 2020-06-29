---
title: MED-V イメージを作成してテストする方法
description: MED-V イメージを作成してテストする方法
author: dansimp
ms.assetid: 40e4aba6-12cb-4794-967d-2c09dc20d808
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f7989871a695b09c987124ab02c0143082148f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827044"
---
# <span data-ttu-id="1e49c-103">MED-V イメージを作成してテストする方法</span><span class="sxs-lookup"><span data-stu-id="1e49c-103">How to Create and Test a MED-V Image</span></span>


<span data-ttu-id="1e49c-104">MED-V 管理者は、med-v イメージを作成して、MED-V ワークスペースと関連付けられた後、Web 経由でクライアントに配布し、MED-V パッケージに追加するか、サードパーティシステムを使用してクライアントにダウンロードすることができます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-104">The MED-V administrator creates a MED-V image so that it can be uploaded, associated with a MED-V workspace, and then distributed to the client over the Web, added to a MED-V package, or downloaded to the client by using a third-party system.</span></span> <span data-ttu-id="1e49c-105">最初にテストイメージを作成し、MED-V クライアントで展開する前にテストイメージをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-105">It is recommended to first create a test image and test it on MED-V client before deploying it.</span></span>

<span data-ttu-id="1e49c-106">MED-V イメージを作成する場合は、次のステージを経ます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-106">When creating a MED-V image, it goes through the following stages:</span></span>

1.  <span data-ttu-id="1e49c-107">**ローカルテストイメージ**—ローカルでテストできる基本的な画像。</span><span class="sxs-lookup"><span data-stu-id="1e49c-107">**Local test image**—A basic image that can be tested locally.</span></span>

2.  <span data-ttu-id="1e49c-108">**ローカルのパック**された画像: イメージのテスト後、イメージはテスト前のイメージとしてパックされます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-108">**Local packed image**—After the image is tested, the image is packed as it existed prior to testing.</span></span> <span data-ttu-id="1e49c-109">テスト中に行われた変更はパックされたイメージに含まれません。</span><span class="sxs-lookup"><span data-stu-id="1e49c-109">No changes made during testing are included in the packed image.</span></span>

3.  <span data-ttu-id="1e49c-110">**サーバー上のパック**された画像: パックされた画像がサーバーにアップロードされます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-110">**Packed image on server**—The packed image is uploaded to the server.</span></span>

## <span data-ttu-id="1e49c-111">MED-V のテストイメージを作成する方法</span><span class="sxs-lookup"><span data-stu-id="1e49c-111">How to Create a MED-V Test Image</span></span>


**<span data-ttu-id="1e49c-112">新しい MED-V テストイメージを作成するには</span><span class="sxs-lookup"><span data-stu-id="1e49c-112">To create a new MED-V test image</span></span>**

1.  <span data-ttu-id="1e49c-113">[**イメージ**管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-113">Click the **Images** management button.</span></span>

    <span data-ttu-id="1e49c-114">**Images**モジュールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-114">The **Images** module appears.</span></span>

    -   <span data-ttu-id="1e49c-115">**Images**モジュールは、次のウィンドウで構成されています。</span><span class="sxs-lookup"><span data-stu-id="1e49c-115">The **Images** module consists of the following panes:</span></span>

        -   <span data-ttu-id="1e49c-116">**ローカルのテストイメージ**—ローカルに展開した画像。</span><span class="sxs-lookup"><span data-stu-id="1e49c-116">**Local Test Images**—Local unpacked images.</span></span>

        -   <span data-ttu-id="1e49c-117">**ローカルのパック**された画像: ローカルコンピューター上のすべてのパックされた画像。</span><span class="sxs-lookup"><span data-stu-id="1e49c-117">**Local Packed Images**—All packed images on the local computer.</span></span>

        -   <span data-ttu-id="1e49c-118">**サーバー上のパック**された画像: パックされてサーバーにアップロードされたすべての画像。</span><span class="sxs-lookup"><span data-stu-id="1e49c-118">**Packed Images on Server**—All images that have been packed and uploaded to the server.</span></span>

    -   <span data-ttu-id="1e49c-119">ローカルの**パック**された画像と**サーバーウィンドウ上のパック**された画像では、各画像の最新バージョンが親ノードとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-119">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="1e49c-120">親ノードをクリックして、その他のすべての既存バージョンの画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-120">Click the parent node to view all other existing versions of the image.</span></span>

2.  <span data-ttu-id="1e49c-121">[**ローカルテストイメージ**] ウィンドウで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-121">In the **Local Test Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="1e49c-122">[**テストイメージの作成**] ダイアログボックスで、次のいずれかの操作を行って、med-v テストイメージとして構成する仮想マシンイメージを選びます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-122">On the **Test Image Creation** dialog box, select the virtual machine image that you want to configure as a MED-V test image by doing one of the following:</span></span>

    -   <span data-ttu-id="1e49c-123">[ **Base image** file] フィールドに、med-v 用に準備された MICROSOFT 仮想 PC イメージが配置されているディレクトリへのフルパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-123">In the **Base image** file field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="1e49c-124">[**参照**] をクリックして、med-v 用に準備されている MICROSOFT 仮想 PC イメージが配置されているディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-124">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="1e49c-125">[**イメージ名**] フィールドで、目的の名前を入力するか選択します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-125">In the **Image name** field, type or select the desired name.</span></span>

    <span data-ttu-id="1e49c-126">**注** 画像名には、次の文字を含めることはできません: space " &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="1e49c-126">**Note** The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>

     

5.  <span data-ttu-id="1e49c-127">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-127">Click **OK**.</span></span>

    <span data-ttu-id="1e49c-128">次の表で定義されたプロパティを使用して、新しい MED-V テストイメージがホストコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-128">A new MED-V test image is created on your host computer with the properties defined in the following table.</span></span>

    <span data-ttu-id="1e49c-129">MED-V ワークスペースイメージの構成の詳細については、「 [Med-v ワークスペースポリシーの構成](configuring-med-v-workspace-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e49c-129">For more information about configuring the MED-V workspace image, refer to [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

**<span data-ttu-id="1e49c-130">ローカルのテストイメージのプロパティ</span><span class="sxs-lookup"><span data-stu-id="1e49c-130">Local Test Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1e49c-131">プロパティ</span><span class="sxs-lookup"><span data-stu-id="1e49c-131">Property</span></span></th>
<th align="left"><span data-ttu-id="1e49c-132">説明</span><span class="sxs-lookup"><span data-stu-id="1e49c-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1e49c-133">画像名</span><span class="sxs-lookup"><span data-stu-id="1e49c-133">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="1e49c-134">管理者がイメージを作成したときに定義されたテストイメージの名前です。</span><span class="sxs-lookup"><span data-stu-id="1e49c-134">The name of the test image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1e49c-135">画像のパス</span><span class="sxs-lookup"><span data-stu-id="1e49c-135">Image Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="1e49c-136">テストイメージのローカルパス。</span><span class="sxs-lookup"><span data-stu-id="1e49c-136">The local path of the test image.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1e49c-137">Created</span><span class="sxs-lookup"><span data-stu-id="1e49c-137">Created</span></span></p></td>
<td align="left"><p><span data-ttu-id="1e49c-138">テストイメージが作成された日付。</span><span class="sxs-lookup"><span data-stu-id="1e49c-138">The date the test image was created.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="1e49c-139">Med-v クライアントから MED-V イメージをテストする方法</span><span class="sxs-lookup"><span data-stu-id="1e49c-139">How to Test a MED-V Image from the MED-V Client</span></span>


<span data-ttu-id="1e49c-140">MED-V のテストイメージを作成した後、次の手順を使用して、画像をローカルでテストします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-140">After a MED-V test image is created, use the following procedure to test the image locally.</span></span>

**<span data-ttu-id="1e49c-141">MED-V イメージをテストするには</span><span class="sxs-lookup"><span data-stu-id="1e49c-141">To test a MED-V image</span></span>**

1.  <span data-ttu-id="1e49c-142">[**ポリシー**管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-142">Click the **Policy** management button.</span></span>

2.  <span data-ttu-id="1e49c-143">**ポリシー**モジュールで、次の操作を行って、med-v テストイメージを med-v ワークスペースに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-143">In the **Policy** module, assign the MED-V test image to a MED-V workspace by doing the following:</span></span>

    1.  <span data-ttu-id="1e49c-144">[**仮想マシン**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-144">Click the **Virtual Machine** tab.</span></span>

    2.  <span data-ttu-id="1e49c-145">[**割り当てられたイメージ**] フィールドで、作成した med-v のテストイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-145">In the **Assigned Image** field, select the MED-V test image you created.</span></span> <span data-ttu-id="1e49c-146">テストイメージが一覧に表示されない場合は、[**更新**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-146">If your test image is not in the list, click **Refresh**.</span></span>

    3.  <span data-ttu-id="1e49c-147">ツールバーで、[ **Save changes**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-147">On the toolbar, click **Save changes**.</span></span>

3.  <span data-ttu-id="1e49c-148">テストするその他の MED-V ワークスペース設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-148">Configure any other MED-V workspace settings to be tested.</span></span> <span data-ttu-id="1e49c-149">詳細については、「 [Med-v ワークスペースポリシーを構成する](configuring-med-v-workspace-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e49c-149">For more information, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

4.  <span data-ttu-id="1e49c-150">MED-V クライアントを起動します。</span><span class="sxs-lookup"><span data-stu-id="1e49c-150">Start MED-V client.</span></span>

5.  <span data-ttu-id="1e49c-151">[**実行中のテストの確認**] 確認ボックスで、[**テストイメージの使用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-151">In the **Confirm Running Test** confirmation box, click **Use Test Image**.</span></span>

6.  <span data-ttu-id="1e49c-152">MED-V ワークスペーステストのイメージをテストします。</span><span class="sxs-lookup"><span data-stu-id="1e49c-152">Test the MED-V workspace test image.</span></span>

    <span data-ttu-id="1e49c-153">MED-V クライアントの起動と実行の詳細については、「 [Med-v クライアントの操作](med-v-client-operations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="1e49c-153">For information about starting and running MED-V client, see [MED-V Client Operations](med-v-client-operations.md).</span></span>

<span data-ttu-id="1e49c-154">**注** 画像をテストするときには、VPC を開かず、画像に変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-154">**Note** While testing an image, do not open VPC and make changes to the image.</span></span>

 

<span data-ttu-id="1e49c-155">**注** 画像をテストする場合、セッション間の画像には変更は保存されません。代わりに、個別の一時ファイルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="1e49c-155">**Note** When testing an image, no changes are saved to the image between sessions; instead, they are saved in a separate, temporary file.</span></span> <span data-ttu-id="1e49c-156">これは、イメージがパックされ、実稼働環境で実行されるときに、元のクリーンな画像であることを確認するためです。</span><span class="sxs-lookup"><span data-stu-id="1e49c-156">This is to ensure that when the image is packed and run on the production environment, it is the original, clean image.</span></span>

 

## <span data-ttu-id="1e49c-157">関連トピック</span><span class="sxs-lookup"><span data-stu-id="1e49c-157">Related topics</span></span>


[<span data-ttu-id="1e49c-158">MED-V の仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="1e49c-158">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="1e49c-159">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="1e49c-159">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="1e49c-160">MED-V ワークスペース ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="1e49c-160">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="1e49c-161">MED-V クライアントの操作</span><span class="sxs-lookup"><span data-stu-id="1e49c-161">MED-V Client Operations</span></span>](med-v-client-operations.md)

 

 





