---
title: MED-V ワークスペースの再開とリセット
description: MED-V ワークスペースの再開とリセット
author: dansimp
ms.assetid: a959cdb3-a727-47c7-967e-e58f224e74de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 48a644c2ed1668f87eb6e1a78521e780e8b783dd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825424"
---
# <span data-ttu-id="a2d08-103">MED-V ワークスペースの再開とリセット</span><span class="sxs-lookup"><span data-stu-id="a2d08-103">Restarting and Resetting a MED-V Workspace</span></span>


<span data-ttu-id="a2d08-104">トラブルシューティング中に、MED-V ワークスペースを再起動またはリセットする必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a2d08-104">During troubleshooting, you may sometimes find it necessary to restart or reset the MED-V workspace.</span></span> <span data-ttu-id="a2d08-105">MED-V ワークスペースの再起動は、基本的に物理コンピューターの再起動と同じです。</span><span class="sxs-lookup"><span data-stu-id="a2d08-105">Restarting the MED-V workspace is basically the same as restarting a physical computer.</span></span> <span data-ttu-id="a2d08-106">MED-V ワークスペースの再インストールをリセットすると、仮想マシンに保存されているすべてのデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-106">Resetting the MED-V workspace reruns first time setup and deletes all data that is stored in the virtual machine.</span></span> <span data-ttu-id="a2d08-107">保存されているデータはすべて削除されるため、通常は、MED-V ワークスペースをリセットして、最も重大なトラブルシューティングの問題を解決するか、以前に動作していた MED-V ワークスペースを正常に動作する状態に戻す必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2d08-107">Because all stored data is deleted, you typically should only reset the MED-V workspace to resolve the most serious troubleshooting issues, or to restore a previously working MED-V workspace back to a working state.</span></span>

<span data-ttu-id="a2d08-108">MED-V 管理ツールキットを開く方法の詳細については、「[管理ツールキットを使用した med-v のトラブルシューティング](troubleshooting-med-v-by-using-the-administration-toolkit.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a2d08-108">For information about how to open the MED-V Administration Toolkit, see [Troubleshooting MED-V by Using the Administration Toolkit](troubleshooting-med-v-by-using-the-administration-toolkit.md).</span></span>

**<span data-ttu-id="a2d08-109">MED-V ワークスペースを再起動する</span><span class="sxs-lookup"><span data-stu-id="a2d08-109">Restarting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="a2d08-110">[ **Med-v 管理ツールキット**] ウィンドウで、[ **Med-v を再起動**する] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-110">On the **MED-V Administration Toolkit** window, click **Restart MED-V Workspace**.</span></span> <span data-ttu-id="a2d08-111">ダイアログウィンドウが開き、MED-V ワークスペースを再起動する必要があることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2d08-111">A dialog window opens in which you must confirm that you want to restart the MED-V workspace.</span></span>

2.  <span data-ttu-id="a2d08-112">[**再起動**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-112">Click **Restart**.</span></span>

    <span data-ttu-id="a2d08-113">実行されている、または既にリダイレクトされている web サイトを開いているアプリケーションは、MED-V ワークスペースの再起動時に終了されます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-113">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace restarts.</span></span>

**<span data-ttu-id="a2d08-114">MED-V ワークスペースのリセット</span><span class="sxs-lookup"><span data-stu-id="a2d08-114">Resetting a MED-V Workspace</span></span>**

1.  <span data-ttu-id="a2d08-115">[ **Med-v 管理ツールキット**] ウィンドウで、[ **Med-v Workspace のリセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-115">On the **MED-V Administration Toolkit** window, click **Reset MED-V Workspace**.</span></span> <span data-ttu-id="a2d08-116">ダイアログウィンドウが開き、MED-V ワークスペースのリセットを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a2d08-116">A dialog window opens in which you must confirm that you want to reset the MED-V workspace.</span></span>

    <span data-ttu-id="a2d08-117">**警告** MED-V ワークスペースをリセットすると、初回のセットアップが再び実行され、元の仮想ハードディスクが再ロードされます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-117">**Warning** Resetting the MED-V workspace causes first time setup to run again, and thus reloads the original virtual hard disk.</span></span> <span data-ttu-id="a2d08-118">最初にセットアップを実行してから、MED-V ワークスペースに保存されているすべてのデータが削除されます。</span><span class="sxs-lookup"><span data-stu-id="a2d08-118">All data that is stored in the MED-V workspace since first time setup was originally run will be deleted.</span></span>

     

2.  <span data-ttu-id="a2d08-119">**[初期状態に戻す]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a2d08-119">Click **Reset**.</span></span>

    <span data-ttu-id="a2d08-120">実行されているか、開かれている web サイトが既に存在する場合は、MED-V ワークスペースをリセットすると、公開されたアプリケーションが終了します。</span><span class="sxs-lookup"><span data-stu-id="a2d08-120">Any published applications that are running or redirected web sites that are open will be closed when the MED-V workspace resets.</span></span>

## <span data-ttu-id="a2d08-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a2d08-121">Related topics</span></span>


[<span data-ttu-id="a2d08-122">MED-V ログの表示と構成</span><span class="sxs-lookup"><span data-stu-id="a2d08-122">Viewing and Configuring MED-V Logs</span></span>](viewing-and-configuring-med-v-logs.md)

[<span data-ttu-id="a2d08-123">MED-V ワークスペースの構成の表示</span><span class="sxs-lookup"><span data-stu-id="a2d08-123">Viewing MED-V Workspace Configurations</span></span>](viewing-med-v-workspace-configurations.md)

 

 





