---
title: キャッシュ サイズおよびドライブ文字の指定を変更する方法
description: キャッシュ サイズおよびドライブ文字の指定を変更する方法
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818037"
---
# <span data-ttu-id="06ea6-103">キャッシュ サイズおよびドライブ文字の指定を変更する方法</span><span class="sxs-lookup"><span data-stu-id="06ea6-103">How to Change the Cache Size and the Drive Letter Designation</span></span>


<span data-ttu-id="06ea6-104">キャッシュサイズとドライブ文字の指定は、Application Virtualization クライアント管理コンソールの**アプリケーション仮想化**ノードから直接変更できます。</span><span class="sxs-lookup"><span data-stu-id="06ea6-104">You can change the cache size and drive letter designation directly from the **Application Virtualization** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="06ea6-105">注</span><span class="sxs-lookup"><span data-stu-id="06ea6-105">Note</span></span>**  
<span data-ttu-id="06ea6-106">キャッシュサイズを設定した後は、サイズを小さくすることはできません。</span><span class="sxs-lookup"><span data-stu-id="06ea6-106">After the cache size has been set, it cannot be made smaller.</span></span>



**<span data-ttu-id="06ea6-107">キャッシュサイズを変更するには</span><span class="sxs-lookup"><span data-stu-id="06ea6-107">To change the cache size</span></span>**

1.  <span data-ttu-id="06ea6-108">[ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="06ea6-109">[**プロパティ**] ダイアログボックスの [**ファイルシステム**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-109">Select the **File System** tab on the **Properties** dialog box.</span></span> <span data-ttu-id="06ea6-110">[**クライアントキャッシュ構成の設定**] セクションで、次のいずれかのラジオボタンをクリックして、キャッシュ領域の管理方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-110">In the **Client Cache Configuration Settings** section, click one of the following radio buttons to choose how to manage the cache space:</span></span>

    **<span data-ttu-id="06ea6-111">重要</span><span class="sxs-lookup"><span data-stu-id="06ea6-111">Important</span></span>**  
    <span data-ttu-id="06ea6-112">[**空きディスク領域のしきい値を使用**する] 設定を選択した場合、入力した値によってキャッシュサイズは、ディスクの合計サイズから、入力した空きディスク領域のしきい値を差し引いた値に設定されます。</span><span class="sxs-lookup"><span data-stu-id="06ea6-112">If you select the **Use free disk space threshold** setting, the value you enter will set the cache size to the total disk size minus the free disk space threshold number you entered.</span></span> <span data-ttu-id="06ea6-113">[**最大キャッシュサイズの使用**] 設定を [元に戻す] を使用したい場合は、既存のキャッシュサイズよりも大きい値を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="06ea6-113">If you then want revert to using the **Use maximum cache size** setting, you must specify a larger number than the existing cache size.</span></span> <span data-ttu-id="06ea6-114">そうしないと、"新しいサイズは既存のキャッシュサイズより大きくなければなりません" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="06ea6-114">Otherwise, the error “New size must be larger than the existing cache size” will appear.</span></span>



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. <span data-ttu-id="06ea6-115">[ **OK]** または [**適用**] をクリックして設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="06ea6-116">ドライブ文字の指定を変更するには</span><span class="sxs-lookup"><span data-stu-id="06ea6-116">To change the drive letter designation</span></span>**

1.  <span data-ttu-id="06ea6-117">[ **Application Virtualization** ] ノードを右クリックし、ポップアップメニューから [**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="06ea6-118">[**プロパティ**] ダイアログボックスの [**ファイルシステム**] タブの [**使用するドライブ**] フィールドで、使用可能なドライブ文字のドロップダウンリストから目的のドライブ文字を選びます。</span><span class="sxs-lookup"><span data-stu-id="06ea6-118">On the **File System** tab in the **Properties** dialog box, in the **Drive to use** field, select the desired drive letter from the drop-down list of available drive letters.</span></span> <span data-ttu-id="06ea6-119">この設定は、コンピューターを再起動すると有効になります。</span><span class="sxs-lookup"><span data-stu-id="06ea6-119">This setting becomes effective when the computer is rebooted.</span></span>

3.  <span data-ttu-id="06ea6-120">[ **OK]** または [**適用**] をクリックして設定を変更します。</span><span class="sxs-lookup"><span data-stu-id="06ea6-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="06ea6-121">関連トピック</span><span class="sxs-lookup"><span data-stu-id="06ea6-121">Related topics</span></span>


[<span data-ttu-id="06ea6-122">Application Virtualization Client Management Console でクライアントを構成する方法</span><span class="sxs-lookup"><span data-stu-id="06ea6-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









