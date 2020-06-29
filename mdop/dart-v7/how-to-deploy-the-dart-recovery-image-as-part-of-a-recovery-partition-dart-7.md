---
title: 回復パーティションの一部として DaRT の回復イメージを展開する方法
description: 回復パーティションの一部として DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823557"
---
# <span data-ttu-id="f204b-103">回復パーティションの一部として DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="f204b-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="f204b-104">DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出して、Windows 7 イメージの回復パーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="f204b-104">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

**<span data-ttu-id="f204b-105">Windows 7 イメージの回復パーティションに DaRT を展開するには</span><span class="sxs-lookup"><span data-stu-id="f204b-105">To deploy DaRT in the recovery partition of a Windows 7 image</span></span>**

1.  <span data-ttu-id="f204b-106">**DaRT 回復イメージウィザード**を使用して作成した ISO イメージファイルと同じサイズまたは大きいサイズのターゲットパーティションを Windows 7 イメージで作成します。</span><span class="sxs-lookup"><span data-stu-id="f204b-106">Create a target partition in your Windows 7 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT Recovery Image Wizard**.</span></span>

    <span data-ttu-id="f204b-107">DaRT パーティションに必要な最小サイズは約300MB です。</span><span class="sxs-lookup"><span data-stu-id="f204b-107">The minimum size required for a DaRT partition is approximately 300MB.</span></span> <span data-ttu-id="f204b-108">ただし、DaRT のリモート接続機能に対応する450MB をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="f204b-108">However, we recommend 450MB to accommodate for the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="f204b-109">DaRT ISO イメージファイルから boot.ini ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="f204b-109">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="f204b-110">画像をマウントするための会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ダイアログボックスで作成した ISO イメージファイルをマウントします。</span><span class="sxs-lookup"><span data-stu-id="f204b-110">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="f204b-111">ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="f204b-111">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="f204b-112">**注** 回復イメージの CD または DVD を書き込んだ場合、CD または DVD 上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="f204b-112">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="f204b-113">これにより、イメージのマウントの必要性をスキップできます。</span><span class="sxs-lookup"><span data-stu-id="f204b-113">This lets you skip the need to mount the image.</span></span>

         

3.  <span data-ttu-id="f204b-114">Boot.ini ファイルを使用して、ユーザー設定の Windows RE イメージを作成するための会社の標準的な方法を使用して、起動可能な回復パーティションを作成します。</span><span class="sxs-lookup"><span data-stu-id="f204b-114">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="f204b-115">回復パーティションを作成またはカスタマイズする方法の詳細については、「 [WINDOWS RE エクスペリエンスをカスタマイズ](https://go.microsoft.com/fwlink/?LinkId=214222)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f204b-115">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="f204b-116">Windows 7 イメージのターゲットパーティションを回復パーティションと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="f204b-116">Replace the target partition in your Windows 7 image with the recovery partition.</span></span>

<span data-ttu-id="f204b-117">Windows 7 の画像の準備ができたら、会社の標準の画像展開プロセスを使用して、画像を社内のコンピューターに配布します。</span><span class="sxs-lookup"><span data-stu-id="f204b-117">After your Windows 7 image is ready, distribute the image to computers in your enterprise by using your company’s standard image deployment process.</span></span> <span data-ttu-id="f204b-118">Windows 7 イメージの作成方法の詳細については、「 [windows 7 の標準イメージの構築: ステップバイステップガイド](https://go.microsoft.com/fwlink/?LinkId=212103)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f204b-118">For more information about how to create a Windows 7 image, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=212103).</span></span>

<span data-ttu-id="f204b-119">システム障害が発生した場合に、回復ソリューションを展開してファクトリイメージを再インストールする方法について詳しくは、「[システム回復イメージの展開](https://go.microsoft.com/fwlink/?LinkId=214221)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="f204b-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="f204b-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f204b-120">Related topics</span></span>


[<span data-ttu-id="f204b-121">DaRT 7.0 の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="f204b-121">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





