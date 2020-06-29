---
title: 回復パーティションの一部として DaRT の回復イメージを展開する方法
description: 回復パーティションの一部として DaRT の回復イメージを展開する方法
author: dansimp
ms.assetid: 07c5d539-51d9-4759-adc7-72b40d5d7bb3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e3647d684f64a0635e2875314498bde841204369
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824384"
---
# <span data-ttu-id="2c282-103">回復パーティションの一部として DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="2c282-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="2c282-104">Microsoft 診断/回復ツールセット (DaRT) 8.0 回復イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、Windows 8 イメージの回復パーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2c282-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span> <span data-ttu-id="2c282-105">Windows オペレーティングシステムを起動できない破損の問題によっては、回復イメージも開始できないため、パーティションをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2c282-105">A partition is recommended, because any corruption issues that prevent the Windows operating system from starting would also prevent the recovery image from starting.</span></span> <span data-ttu-id="2c282-106">別のパーティションを使うと、BitLocker 回復キーを2回入力する必要もなくなります。</span><span class="sxs-lookup"><span data-stu-id="2c282-106">A separate partition also eliminates the need to provide the BitLocker recovery key twice.</span></span> <span data-ttu-id="2c282-107">ユーザーがファイルを保存できないように、パーティションを非表示にすることを検討してください。</span><span class="sxs-lookup"><span data-stu-id="2c282-107">Consider hiding the partition to prevent users from storing files on it.</span></span>

**<span data-ttu-id="2c282-108">Windows 8 イメージの回復パーティションに DaRT を展開するには</span><span class="sxs-lookup"><span data-stu-id="2c282-108">To deploy DaRT in the recovery partition of a Windows 8 image</span></span>**

1.  <span data-ttu-id="2c282-109">**DaRT 8.0 の回復イメージウィザード**を使って作成した ISO イメージファイルのサイズと等しい、またはそれ以上のサイズのターゲットパーティションを Windows 8 イメージで作成します。</span><span class="sxs-lookup"><span data-stu-id="2c282-109">Create a target partition in your Windows 8 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT 8.0 Recovery Image wizard**.</span></span>

    <span data-ttu-id="2c282-110">DaRT のパーティションに必要な最小サイズは、DaRT のリモート接続機能に合わせて500MB ます。</span><span class="sxs-lookup"><span data-stu-id="2c282-110">The minimum size required for a DaRT partition is 500MB to accommodate the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="2c282-111">DaRT ISO イメージファイルから boot.ini ファイルを抽出します。</span><span class="sxs-lookup"><span data-stu-id="2c282-111">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="2c282-112">会社の推奨される方法を使用して、[**スタートアップイメージの作成**] ページで作成した ISO イメージファイルをマウントします。</span><span class="sxs-lookup"><span data-stu-id="2c282-112">Using your company’s preferred method, mount the ISO image file that you created on the **Create Startup Image** page.</span></span>

    2.  <span data-ttu-id="2c282-113">ISO イメージファイルを開き、マウントされた画像の \\ ソースフォルダーからコンピューター上または外部ドライブ上の場所に boot.ini ファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="2c282-113">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="2c282-114">**注** 回復イメージの CD、DVD、または USB を書き込んだ場合は、リムーバブルメディア上のファイルを開いて、\\ ソースフォルダーから boot.ini ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="2c282-114">**Note** If you burned a CD, DVD, or USB of the recovery image, you can open the files on the removable media and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="2c282-115">Boot.ini ファイルをコピーする場合は、イメージをマウントする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="2c282-115">If you copy boot.wim file, you don’t need to mount the image.</span></span>

         

3.  <span data-ttu-id="2c282-116">Boot.ini ファイルを使用して、ユーザー設定の Windows RE イメージを作成するための会社の標準的な方法を使用して、起動可能な回復パーティションを作成します。</span><span class="sxs-lookup"><span data-stu-id="2c282-116">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="2c282-117">回復パーティションを作成またはカスタマイズする方法の詳細については、「 [WINDOWS RE エクスペリエンスをカスタマイズ](https://go.microsoft.com/fwlink/?LinkId=214222)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2c282-117">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="2c282-118">Windows 8 イメージのターゲットパーティションを回復パーティションと置き換えます。</span><span class="sxs-lookup"><span data-stu-id="2c282-118">Replace the target partition in your Windows 8 image with the recovery partition.</span></span>

    <span data-ttu-id="2c282-119">システム障害が発生した場合に、回復ソリューションを展開してファクトリイメージを再インストールする方法について詳しくは、「[システム回復イメージの展開](https://go.microsoft.com/fwlink/?LinkId=214221)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="2c282-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="2c282-120">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2c282-120">Related topics</span></span>


[<span data-ttu-id="2c282-121">DaRT 8.0 の回復イメージの作成</span><span class="sxs-lookup"><span data-stu-id="2c282-121">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

[<span data-ttu-id="2c282-122">DaRT の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="2c282-122">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

[<span data-ttu-id="2c282-123">DaRT 8.0 の計画</span><span class="sxs-lookup"><span data-stu-id="2c282-123">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

 

 





