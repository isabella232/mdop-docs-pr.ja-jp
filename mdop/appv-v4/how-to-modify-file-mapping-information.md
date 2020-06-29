---
title: ファイルマッピング情報を変更する方法
description: ファイルマッピング情報を変更する方法
author: dansimp
ms.assetid: d3a9d10a-6cc8-4399-9479-b20f729c4dd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6dbc030367408299e0daaf06f7f97ab5369574db
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817024"
---
# <span data-ttu-id="c7e00-103">ファイルマッピング情報を変更する方法</span><span class="sxs-lookup"><span data-stu-id="c7e00-103">How to Modify File-Mapping Information</span></span>


<span data-ttu-id="c7e00-104">アプリケーションをシーケンスした後に保存する前に、仮想ファイルシステムを手動で変更することができます。</span><span class="sxs-lookup"><span data-stu-id="c7e00-104">After you sequence an application but before you save it, you can manually modify the virtual file system.</span></span> <span data-ttu-id="c7e00-105">仮想ファイルシステムでファイルを追加、削除、または編集するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-105">Use the following procedures to add, delete, or edit a file in the virtual file system.</span></span>

**<span data-ttu-id="c7e00-106">ファイルシステムにファイルを追加するには</span><span class="sxs-lookup"><span data-stu-id="c7e00-106">To add a file in the file system</span></span>**

1.  <span data-ttu-id="c7e00-107">[**仮想ファイルシステム**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-107">Click the **Virtual File System** tab.</span></span>

2.  <span data-ttu-id="c7e00-108">左側のウィンドウで、仮想ファイルシステムルートの下にあるファイルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-108">Right-click a file under the virtual file system root in the left pane.</span></span> <span data-ttu-id="c7e00-109">メニューの [**追加**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-109">On the menu, select **Add**.</span></span>

3.  <span data-ttu-id="c7e00-110">[**新しい仮想ファイルシステムマッピング**] ダイアログボックスで、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-110">Complete the following tasks in the **New Virtual File System Mapping** dialog box:</span></span>

    1.  <span data-ttu-id="c7e00-111">新しいファイルの関連付けを指定するには、新しいファイルへの完全なネットワークパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-111">To specify the new file association type the full network path to the new file.</span></span>

    2.  <span data-ttu-id="c7e00-112">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-112">Click **OK**.</span></span>

4.  <span data-ttu-id="c7e00-113">ローカルディレクトリを上書きするには、追加したファイルを右クリックし、メニューの [**ローカルディレクトリの上書き**] を選択します。または、ローカルディレクトリと結合するには、[**ローカルディレクトリと結合**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c7e00-113">To override the local directory, right-click the file you just added and, on the menu, select **Override Local Directory**; or to merge with the local directory, select **Merge with Local Directory**.</span></span>

5.  <span data-ttu-id="c7e00-114">[**ファイル**] メニューの [**保存**] をクリックして、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-114">On the **File** menu, select **Save** to save this change.</span></span>

**<span data-ttu-id="c7e00-115">ファイルシステム内のファイルを削除するには</span><span class="sxs-lookup"><span data-stu-id="c7e00-115">To delete a file in the file system</span></span>**

1.  <span data-ttu-id="c7e00-116">[**仮想ファイルシステム**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-116">Click the **Virtual File System** tab.</span></span>

2.  <span data-ttu-id="c7e00-117">仮想ファイルシステム内のファイルを右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-117">Right-click a file in the virtual file system, and select **Delete**.</span></span>

3.  <span data-ttu-id="c7e00-118">**[OK]** をクリックして、確認メッセージを承諾します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-118">Accept the confirmation message by clicking **OK**.</span></span>

4.  <span data-ttu-id="c7e00-119">[**ファイル**] メニューの [**保存**] をクリックして、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-119">On the **File** menu, select **Save** to save this change.</span></span>

**<span data-ttu-id="c7e00-120">ファイルシステム内のファイルを編集するには</span><span class="sxs-lookup"><span data-stu-id="c7e00-120">To edit a file in the file system</span></span>**

1.  <span data-ttu-id="c7e00-121">[**仮想ファイルシステム**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-121">Click the **Virtual File System** tab.</span></span>

2.  <span data-ttu-id="c7e00-122">仮想ファイルシステム内のファイルを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-122">Right-click a file in the virtual file system.</span></span> <span data-ttu-id="c7e00-123">メニューの [**編集**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="c7e00-123">On the menu, select **Edit**.</span></span>

3.  <span data-ttu-id="c7e00-124">[**仮想ファイルシステムのマッピングの編集**] ダイアログボックスで、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-124">Complete the following tasks in the **Edit Virtual File System Mapping** dialog box:</span></span>

    1.  <span data-ttu-id="c7e00-125">ファイルの関連付けを編集するには、新しいファイルへの完全なネットワークパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-125">To edit the file association, specify the full network path to the new file.</span></span>

    2.  <span data-ttu-id="c7e00-126">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="c7e00-126">Click **OK**.</span></span>

4.  <span data-ttu-id="c7e00-127">ローカルディレクトリを上書きするには、編集したばかりのファイルを右クリックし、メニューの [**ローカルディレクトリの上書き**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-127">To override the local directory, right-click the file you just edited and, on the menu, select **Override Local Directory**.</span></span>

5.  <span data-ttu-id="c7e00-128">[**ファイル**] メニューの [**保存**] をクリックして、変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="c7e00-128">On the **File** menu, select **Save** to save this change.</span></span>

## <span data-ttu-id="c7e00-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c7e00-129">Related topics</span></span>


[<span data-ttu-id="c7e00-130">[仮想ファイル システム] タブについて</span><span class="sxs-lookup"><span data-stu-id="c7e00-130">About the Virtual File System Tab</span></span>](about-the-virtual-file-system-tab.md)

[<span data-ttu-id="c7e00-131">Sequencer Console</span><span class="sxs-lookup"><span data-stu-id="c7e00-131">Sequencer Console</span></span>](sequencer-console.md)

 

 





