---
title: MED-V イメージをパックする方法
description: MED-V イメージをパックする方法
author: dansimp
ms.assetid: e1ce2307-0f1b-4bf8-b146-e4012dc138d2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a330b8feca922239691bed083767c3acc57105d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824677"
---
# <span data-ttu-id="adb09-103">MED-V イメージをパックする方法</span><span class="sxs-lookup"><span data-stu-id="adb09-103">How to Pack a MED-V Image</span></span>


<span data-ttu-id="adb09-104">MED-V イメージは、展開パッケージに追加したり、サーバーにアップロードしたりする前に、パックする必要があります。</span><span class="sxs-lookup"><span data-stu-id="adb09-104">A MED-V image must be packed before it can be added to a deployment package or uploaded to the server.</span></span>

**<span data-ttu-id="adb09-105">パックされた MED イメージを作成するには</span><span class="sxs-lookup"><span data-stu-id="adb09-105">To create a packed MED-V image</span></span>**

1.  <span data-ttu-id="adb09-106">[**イメージ**管理] ボタンをクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb09-106">Click the **Images** management button.</span></span>

2.  <span data-ttu-id="adb09-107">**Images**モジュールの [**ローカルパック**されたイメージ] ウィンドウで、[**新規**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb09-107">In the **Images** module, in the **Local Packed Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="adb09-108">[パックされた**画像の作成**] ダイアログボックスで、次のいずれかの操作を行って、仮想マシンのイメージを選択します。</span><span class="sxs-lookup"><span data-stu-id="adb09-108">In the **Packed Image Creation** dialog box, select the virtual machine image by doing one of the following:</span></span>

    -   <span data-ttu-id="adb09-109">[ **Base image file** ] フィールドに、med-v 用に準備された MICROSOFT 仮想 PC イメージが配置されているディレクトリへのフルパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="adb09-109">In the **Base image file** field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="adb09-110">[**参照**] をクリックして、med-v 用に準備されている MICROSOFT 仮想 PC イメージが配置されているディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="adb09-110">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="adb09-111">次のいずれかの操作を行って、新しい画像の名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="adb09-111">Specify the name of the new image by doing one of the following:</span></span>

    -   <span data-ttu-id="adb09-112">[**イメージ名**] フィールドに、目的の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="adb09-112">In the **Image name** field, type the desired name.</span></span>

        **<span data-ttu-id="adb09-113">注</span><span class="sxs-lookup"><span data-stu-id="adb09-113">Note</span></span>**  
        <span data-ttu-id="adb09-114">画像名には、次の文字を含めることはできません: space " &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="adb09-114">The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>



~~~
    A new packed image will be created.

-   From the drop-down list, select an existing name.

    A new version of the existing image will be created.
~~~

5. <span data-ttu-id="adb09-115">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="adb09-115">Click **OK**.</span></span>

   <span data-ttu-id="adb09-116">次の表で定義されたプロパティを使用して、新しい MED-V パックされた画像がホストコンピューター上に作成されます。</span><span class="sxs-lookup"><span data-stu-id="adb09-116">A new MED-V packed image is created on your host computer with the properties defined in the following table.</span></span>

**<span data-ttu-id="adb09-117">注</span><span class="sxs-lookup"><span data-stu-id="adb09-117">Note</span></span>**  
<span data-ttu-id="adb09-118">ローカルの**パック**された画像と**サーバーウィンドウ上のパック**された画像では、各画像の最新バージョンが親ノードとして表示されます。</span><span class="sxs-lookup"><span data-stu-id="adb09-118">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="adb09-119">親ノードをクリックして、その他のすべての既存バージョンの画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="adb09-119">Click the parent node to view all other existing versions of the image.</span></span>



**<span data-ttu-id="adb09-120">ローカルのパックされた画像のプロパティ</span><span class="sxs-lookup"><span data-stu-id="adb09-120">Local Packed Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="adb09-121">プロパティ</span><span class="sxs-lookup"><span data-stu-id="adb09-121">Property</span></span></th>
<th align="left"><span data-ttu-id="adb09-122">説明</span><span class="sxs-lookup"><span data-stu-id="adb09-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="adb09-123">画像名</span><span class="sxs-lookup"><span data-stu-id="adb09-123">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="adb09-124">管理者がイメージを作成したときに定義されたパックされたイメージの名前です。</span><span class="sxs-lookup"><span data-stu-id="adb09-124">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="adb09-125">バージョン</span><span class="sxs-lookup"><span data-stu-id="adb09-125">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="adb09-126">表示される画像のバージョン。</span><span class="sxs-lookup"><span data-stu-id="adb09-126">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="adb09-127">注</span><span class="sxs-lookup"><span data-stu-id="adb09-127">Note</span></span></strong><br/><p><span data-ttu-id="adb09-128">削除しない限り、以前のすべてのバージョンは保持されます。</span><span class="sxs-lookup"><span data-stu-id="adb09-128">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="adb09-129">ファイルサイズ (圧縮済み)</span><span class="sxs-lookup"><span data-stu-id="adb09-129">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="adb09-130">画像の物理圧縮サイズ。</span><span class="sxs-lookup"><span data-stu-id="adb09-130">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="adb09-131">画像サイズ (非圧縮)</span><span class="sxs-lookup"><span data-stu-id="adb09-131">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="adb09-132">画像の圧縮されていない物理サイズ。</span><span class="sxs-lookup"><span data-stu-id="adb09-132">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="adb09-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="adb09-133">Related topics</span></span>


[<span data-ttu-id="adb09-134">MED-V クライアントと MED-V 管理コンソールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="adb09-134">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="adb09-135">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="adb09-135">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="adb09-136">MED-V の仮想 PC イメージの作成</span><span class="sxs-lookup"><span data-stu-id="adb09-136">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)









