---
title: リモート パーティションとして DaRT の回復イメージを展開する方法
description: リモート パーティションとして DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 757c9340-8eac-42e8-85de-4302e436713a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a3acdbf72a2c6dac0238f868c7280f1c389b1311
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823567"
---
# <span data-ttu-id="c1fbc-103">リモート パーティションとして DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c1fbc-103">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="c1fbc-104">DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、ネットワーク上のリモートパーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-104">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

**<span data-ttu-id="c1fbc-105">DaRT をリモートパーティションとして展開するには</span><span class="sxs-lookup"><span data-stu-id="c1fbc-105">To deploy DaRT as a remote partition</span></span>**

1.  <span data-ttu-id="c1fbc-106">DaRT ISO イメージファイルから boot.ini ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-106">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="c1fbc-107">画像をマウントするための会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-107">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="c1fbc-108">ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-108">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="c1fbc-109">**注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-109">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="c1fbc-110">これにより、イメージのマウントの必要性をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-110">This lets you skip the need to mount the image.</span></span>

         

2.  <span data-ttu-id="c1fbc-111">エンタープライズ内のエンドユーザーコンピューターからアクセスできる WDS サーバーに boot.ini ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-111">Deploy the boot.wim file to a WDS server that can be accessed from end-user computers in your enterprise.</span></span>

3.  <span data-ttu-id="c1fbc-112">標準の WDS 展開手順に従って、DaRT 用の boot.ini ファイルを使用するように WDS サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-112">Configure the WDS server to use the boot.wim file for DaRT by following your standard WDS deployment procedures.</span></span>

<span data-ttu-id="c1fbc-113">DaRT をリモートパーティションとして展開する方法の詳細については、次を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c1fbc-113">For more information about how to deploy DaRT as a remote partition, see the following:</span></span>

-   [<span data-ttu-id="c1fbc-114">チュートリアル: PXE を使用して画像を展開する</span><span class="sxs-lookup"><span data-stu-id="c1fbc-114">Walkthrough: Deploy an Image by Using PXE</span></span>](https://go.microsoft.com/fwlink/?LinkId=212108)

-   [<span data-ttu-id="c1fbc-115">Windows 展開サービスのクイックスタートガイド</span><span class="sxs-lookup"><span data-stu-id="c1fbc-115">Windows Deployment Services Getting Started Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=212106)

## <span data-ttu-id="c1fbc-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c1fbc-116">Related topics</span></span>


[<span data-ttu-id="c1fbc-117">DaRT 7.0 の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="c1fbc-117">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





