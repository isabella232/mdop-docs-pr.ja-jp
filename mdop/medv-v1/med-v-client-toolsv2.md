---
title: MED-V クライアント ツール
description: MED-V クライアント ツール
author: dansimp
ms.assetid: ea18d82e-2433-4754-85ac-6eac84bcbb01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e4ae67b8327e41bf5798c1d0d3fcb6253bf3b02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824017"
---
# <span data-ttu-id="92763-103">MED-V クライアント ツール</span><span class="sxs-lookup"><span data-stu-id="92763-103">MED-V Client Tools</span></span>


<span data-ttu-id="92763-104">MED-V には、次のクライアントツールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="92763-104">MED-V includes the following client tools:</span></span>

-   [<span data-ttu-id="92763-105">ファイル送信ツール</span><span class="sxs-lookup"><span data-stu-id="92763-105">File Transfer Tool</span></span>](#bkmk-filetransfertool)

-   [<span data-ttu-id="92763-106">画像のダウンロード</span><span class="sxs-lookup"><span data-stu-id="92763-106">Image Downloads</span></span>](#bkmk-imagedownloads)

-   [<span data-ttu-id="92763-107">診断</span><span class="sxs-lookup"><span data-stu-id="92763-107">Diagnostics</span></span>](#bkmk-diagnostics)

## <a href="" id="bkmk-filetransfertool"></a><span data-ttu-id="92763-108">ファイル送信ツール</span><span class="sxs-lookup"><span data-stu-id="92763-108">File Transfer Tool</span></span>


<span data-ttu-id="92763-109">ファイル転送ツールを使用すると、MED-V ワークスペースからホストにファイルまたはフォルダーをコピーすることができます。また、その逆もできます。</span><span class="sxs-lookup"><span data-stu-id="92763-109">The File Transfer Tool can be used to copy files or folders from the MED-V workspace to the host and vice versa.</span></span>

<span data-ttu-id="92763-110">**注** ファイル転送ツールは、MED-V ワークスペースが実行されている場合にのみ有効です。</span><span class="sxs-lookup"><span data-stu-id="92763-110">**Note** The File Transfer Tool is enabled only when the MED-V workspace is running.</span></span>

 

**<span data-ttu-id="92763-111">現在実行されている MED-V ワークスペースからファイルまたはフォルダーをコピーするには</span><span class="sxs-lookup"><span data-stu-id="92763-111">To copy files or folders from a MED-V workspace that is currently running</span></span>**

1.  <span data-ttu-id="92763-112">通知領域で、MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-112">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="92763-113">サブメニューで、[**ツール**] をポイントし、[**ファイル送信**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-113">On the submenu, point to **Tools**, and then click **File Transfer**.</span></span>

3.  <span data-ttu-id="92763-114">**ファイル転送**ツールの **[転送の方向の選択**] フィールドで、次のいずれかの転送オプションをクリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-114">In the **File Transfer** tool, in the **Select transfer direction** field, click one of the following transfer options:</span></span>

    -   <span data-ttu-id="92763-115">**[マイコンピューター] から [既定のワークスペース] ワークスペースにコピー**-ホストからアクティブな med-v ワークスペースにファイルまたはフォルダーを転送します。</span><span class="sxs-lookup"><span data-stu-id="92763-115">**Copy from My Computer to 'default workspace' Workspace**—Transfer a file or folder from the host to the active MED-V workspace.</span></span>

    -   <span data-ttu-id="92763-116">**"既定のワークスペース" ワークスペースから [マイコンピューター] にコピー**します。アクティブな med-v ワークスペースからホストにファイルまたはフォルダーを転送します。</span><span class="sxs-lookup"><span data-stu-id="92763-116">**Copy from 'default workspace' Workspace to My Computer**—Transfer a file or folder from the active MED-V workspace to the host.</span></span>

4.  <span data-ttu-id="92763-117">次のいずれかの操作を行って、コピーするファイルまたはフォルダーを選択します。</span><span class="sxs-lookup"><span data-stu-id="92763-117">Select the file or folder to copy by doing one of the following:</span></span>

    -   <span data-ttu-id="92763-118">[**コピーするファイル**] フィールドに、コピーするファイルまたはフォルダーが保存されているディレクトリへのフルパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="92763-118">In the **File to copy** field, type the full path to the directory where the file or folder to copy is located.</span></span>

    -   <span data-ttu-id="92763-119">[**参照**] をクリックして、コピーするファイルまたはフォルダーが保存されているディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="92763-119">Click **Browse** to browse the directory where the file or folder to copy is located.</span></span>

5.  <span data-ttu-id="92763-120">フォルダー全体をコピーするには、[**フォルダーのコピー** ] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="92763-120">Select the **Copy a folder** check box to copy an entire folder.</span></span>

6.  <span data-ttu-id="92763-121">次のいずれかの操作を行って、ファイルの転送先を選択します。</span><span class="sxs-lookup"><span data-stu-id="92763-121">Select the destination where the file is being transferred by doing one of the following:</span></span>

    -   <span data-ttu-id="92763-122">[ **Destination** ] フィールドに、ファイルまたはフォルダーが転送されるディレクトリの完全なパスを入力します。</span><span class="sxs-lookup"><span data-stu-id="92763-122">In the **Destination** field, type the full path of the directory where the file or folder will be transferred.</span></span>

    -   <span data-ttu-id="92763-123">[**参照**] をクリックして、ファイルまたはフォルダーが転送されるディレクトリを参照します。</span><span class="sxs-lookup"><span data-stu-id="92763-123">Click **Browse** to browse to the directory where the file or folder will be transferred.</span></span>

7.  <span data-ttu-id="92763-124">**[開始]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-124">Click **Start**.</span></span>

    <span data-ttu-id="92763-125">ファイル送信が開始されます。</span><span class="sxs-lookup"><span data-stu-id="92763-125">The file transfer begins.</span></span>

## <a href="" id="bkmk-imagedownloads"></a><span data-ttu-id="92763-126">画像のダウンロード</span><span class="sxs-lookup"><span data-stu-id="92763-126">Image Downloads</span></span>


<span data-ttu-id="92763-127">MED-V ワークスペースと MED-V ワークスペースの新しいイメージ更新が利用可能になると、ユーザーは新しい画像をダウンロードする準備ができたことを示すメッセージを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="92763-127">When a new image update is available for a MED-V workspace and the MED-V workspace is active, the user receives a message indicating that a new image is ready for download.</span></span>

**<span data-ttu-id="92763-128">ダウンロード可能な画像を表示するには</span><span class="sxs-lookup"><span data-stu-id="92763-128">To view available images for download</span></span>**

1.  <span data-ttu-id="92763-129">通知領域で、MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-129">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="92763-130">サブメニューで、[**ツール**] をポイントし、[**イメージのダウンロード**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-130">On the submenu, point to **Tools**, and then click **Image Downloads**.</span></span>

    <span data-ttu-id="92763-131">使用可能なすべてのイメージのダウンロードが表示されます。</span><span class="sxs-lookup"><span data-stu-id="92763-131">All available image downloads are displayed.</span></span>

## <a href="" id="bkmk-diagnostics"></a><span data-ttu-id="92763-132">診断</span><span class="sxs-lookup"><span data-stu-id="92763-132">Diagnostics</span></span>


<span data-ttu-id="92763-133">診断ツールは、すべての診断情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="92763-133">The diagnostics tool provides all diagnostic information.</span></span>

**<span data-ttu-id="92763-134">診断を表示するには</span><span class="sxs-lookup"><span data-stu-id="92763-134">To view diagnostics</span></span>**

1.  <span data-ttu-id="92763-135">通知領域で、MED-V アイコンを右クリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-135">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="92763-136">サブメニューで [**ヘルプ**] をポイントし、[ **med-v 診断**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="92763-136">On the submenu, point to **Help**, and then click **MED-V Diagnostics**.</span></span>

3.  <span data-ttu-id="92763-137">**診断**ツールで、すべての診断情報を確認します。</span><span class="sxs-lookup"><span data-stu-id="92763-137">In the **Diagnostics** tool, review all diagnostic information.</span></span>

<span data-ttu-id="92763-138">診断ツールを使って、次の機能を実行できます。</span><span class="sxs-lookup"><span data-stu-id="92763-138">The following functions can be performed using the diagnostic tool:</span></span>

-   <span data-ttu-id="92763-139">診断ログを収集し、診断ログを収集してデスクトップに配置します。</span><span class="sxs-lookup"><span data-stu-id="92763-139">Gather diagnostic logs—Gather the diagnostic logs, and place them on the desktop.</span></span>

-   <span data-ttu-id="92763-140">更新ポリシー: MED-V ワークスペースポリシーは、MED-V サーバーに自動的に接続して、15分ごとにポリシーを更新します。</span><span class="sxs-lookup"><span data-stu-id="92763-140">Update policy—The MED-V workspace policy automatically connects to the MED-V server to refresh the policy every 15 minutes.</span></span> <span data-ttu-id="92763-141">ただし、ユーザーはこのオプションを使用して手動の更新を直ちに実行することができます。</span><span class="sxs-lookup"><span data-stu-id="92763-141">However, a user can use this option to perform a manual refresh immediately.</span></span>

-   <span data-ttu-id="92763-142">診断モードの有効化または無効化: 仮想マシンのウィンドウを表示します。</span><span class="sxs-lookup"><span data-stu-id="92763-142">Enable or Disable diagnostic mode—Display the virtual machine window.</span></span> <span data-ttu-id="92763-143">この関数は、たとえば、表示されていない MED ワークスペースウィンドウを表示する必要がある場合に役立ちます。</span><span class="sxs-lookup"><span data-stu-id="92763-143">This function is helpful when, for example, you need to see MED-V workspace windows that are not displayed.</span></span>

-   <span data-ttu-id="92763-144">イメージストアの参照-利用可能なすべての MED-V ワークスペースの画像を表示します。</span><span class="sxs-lookup"><span data-stu-id="92763-144">Browse image store—View all available MED-V workspace images.</span></span>

 

 





