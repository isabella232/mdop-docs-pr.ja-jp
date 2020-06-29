---
title: USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法
description: USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823667"
---
# <span data-ttu-id="6905a-103">USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6905a-103">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="6905a-104">**DaRT Recovery イメージウィザード**の実行が完了したら、のツールを使って、 <https://go.microsoft.com/fwlink/?LinkId=218888> USB フラッシュドライブ (UFD) に ISO 画像ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="6905a-104">After you have finished running the **DaRT Recovery Image Wizard**, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

<span data-ttu-id="6905a-105">このセクションで説明する手順に従って、手動で ISO イメージファイルを UFD にコピーすることもできます。</span><span class="sxs-lookup"><span data-stu-id="6905a-105">You can also manually copy the ISO image file to a UFD by following the steps provided in this section.</span></span>

**<span data-ttu-id="6905a-106">DaRT リカバリ画像を USB フラッシュドライブに保存するには</span><span class="sxs-lookup"><span data-stu-id="6905a-106">To save the DaRT recovery image to a USB flash drive</span></span>**

1.  <span data-ttu-id="6905a-107">USB フラッシュドライブの書式を設定します。</span><span class="sxs-lookup"><span data-stu-id="6905a-107">Format the USB flash drive.</span></span>

    1.  <span data-ttu-id="6905a-108">実行されている有効なオペレーティングシステムまたは WindowsPE セッションから、UFD を挿入します。</span><span class="sxs-lookup"><span data-stu-id="6905a-108">From a running valid operating system or WindowsPE session, insert your UFD.</span></span>

    2.  <span data-ttu-id="6905a-109">管理者権限を持つコマンドプロンプトで、「 **DISKPART** 」と入力して、「 **LIST DISK**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="6905a-109">At the command prompt with administrator permissions, type **DISKPART** and then type **LIST DISK**.</span></span>

        <span data-ttu-id="6905a-110">[コマンドプロンプト] ウィンドウに、**ディスク 1**などの UFD のディスク番号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="6905a-110">The Command Prompt window displays the disk number of your UFD, for example **DISK 1**.</span></span>

    3.  <span data-ttu-id="6905a-111">コマンドプロンプトで、次のコマンドを一度に1つずつ入力します。</span><span class="sxs-lookup"><span data-stu-id="6905a-111">Enter the following commands one at a time at the command prompt.</span></span>

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        <span data-ttu-id="6905a-112">**注** 前のコード例では、Disk1 が UFD であることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="6905a-112">**Note** The previous code example assumes Disk1 is the UFD.</span></span> <span data-ttu-id="6905a-113">必要に応じて、ディスク1をディスク番号に置き換えます。</span><span class="sxs-lookup"><span data-stu-id="6905a-113">If it is necessary, replace DISK 1 with your disk number.</span></span>

         

2.  <span data-ttu-id="6905a-114">会社の推奨される方法でイメージをマウントすることによって、 **DaRT 回復イメージウィザード**の [**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。</span><span class="sxs-lookup"><span data-stu-id="6905a-114">By using your company’s preferred method of mounting an image, mount the ISO image file that you created in the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="6905a-115">このためには、画像ファイルをマウントするためのメソッドを用意する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6905a-115">This requires that you have a method available to mount an image file.</span></span>

3.  <span data-ttu-id="6905a-116">マウントされた ISO イメージファイルを開き、そのすべての内容を、書式設定された USB フラッシュドライブにコピーします。</span><span class="sxs-lookup"><span data-stu-id="6905a-116">Open the mounted ISO image file and copy all its contents to the formatted USB flash drive.</span></span>

    <span data-ttu-id="6905a-117">**注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、コンテンツを UFD にコピーできます。</span><span class="sxs-lookup"><span data-stu-id="6905a-117">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the contents to the UFD.</span></span> <span data-ttu-id="6905a-118">これにより、イメージのマウントの必要性をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="6905a-118">This lets you skip the need to mount the image.</span></span>

     

## <span data-ttu-id="6905a-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6905a-119">Related topics</span></span>


[<span data-ttu-id="6905a-120">DaRT 7.0 の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="6905a-120">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





