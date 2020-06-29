---
title: リモート パーティションとして DaRT の回復イメージを展開する方法
description: リモート パーティションとして DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 06a5e250-b992-4f6a-ad74-e7715f9e96e7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3cdb1313a64bacd652a5253c09f36fa792d0fa3c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813066"
---
# <span data-ttu-id="6525d-103">リモート パーティションとして DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="6525d-103">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="6525d-104">Microsoft 診断/回復ツールセット (DaRT) 10 回復イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、ネットワーク上のリモートパーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="6525d-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

**<span data-ttu-id="6525d-105">DaRT 10 をリモートパーティションとして展開するには</span><span class="sxs-lookup"><span data-stu-id="6525d-105">To deploy DaRT 10 as a remote partition</span></span>**

1.  <span data-ttu-id="6525d-106">DaRT ISO イメージファイルから boot.ini ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="6525d-106">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="6525d-107">画像をマウントするための会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。</span><span class="sxs-lookup"><span data-stu-id="6525d-107">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="6525d-108">ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="6525d-108">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="6525d-109">**注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="6525d-109">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="6525d-110">これにより、イメージのマウントの必要性をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="6525d-110">This lets you skip the need to mount the image.</span></span>

         

2.  <span data-ttu-id="6525d-111">エンタープライズ内のエンドユーザーコンピューターからアクセスできる WDS サーバーに boot.ini ファイルを展開します。</span><span class="sxs-lookup"><span data-stu-id="6525d-111">Deploy the boot.wim file to a WDS server that can be accessed from end-user computers in your enterprise.</span></span>

3.  <span data-ttu-id="6525d-112">標準の WDS 展開手順に従って、DaRT 用の boot.ini ファイルを使用するように WDS サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="6525d-112">Configure the WDS server to use the boot.wim file for DaRT by following your standard WDS deployment procedures.</span></span>

<span data-ttu-id="6525d-113">DaRT をリモートパーティションとして展開する方法の詳細については、「チュートリアル: PXE と[Windows 展開サービスのクイックスタートガイド](https://go.microsoft.com/fwlink/?LinkId=212106)を[使用したイメージの展開](https://go.microsoft.com/fwlink/?LinkId=212108)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6525d-113">For more information about how to deploy DaRT as a remote partition, see [Walkthrough: Deploy an Image by Using PXE](https://go.microsoft.com/fwlink/?LinkId=212108) and [Windows Deployment Services Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=212106).</span></span>

## <span data-ttu-id="6525d-114">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6525d-114">Related topics</span></span>


[<span data-ttu-id="6525d-115">DaRT 10 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="6525d-115">Creating the DaRT 10 Recovery Image</span></span>](creating-the-dart-10-recovery-image.md)

[<span data-ttu-id="6525d-116">DaRT の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="6525d-116">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-10.md)

[<span data-ttu-id="6525d-117">DaRT 10 の計画</span><span class="sxs-lookup"><span data-stu-id="6525d-117">Planning for DaRT 10</span></span>](planning-for-dart-10.md)

 

 





