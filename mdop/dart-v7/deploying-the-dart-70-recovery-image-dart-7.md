---
title: DaRT 7.0 の回復イメージの展開
description: DaRT 7.0 の回復イメージの展開
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812658"
---
# <span data-ttu-id="3b6f2-103">DaRT 7.0 の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="3b6f2-103">Deploying the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="3b6f2-104">Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 の回復イメージを含む国際標準化機構 (ISO) ファイルを作成した後、エンドユーザーとヘルプデスクの担当者が利用できるように、企業全体で DaRT 回復イメージを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image, you can deploy the DaRT recovery image throughout your enterprise so that it is available to end users and helpdesk agents.</span></span> <span data-ttu-id="3b6f2-105">DaRT リカバリイメージの展開に使用できる、4つのサポートされるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="3b6f2-106">ISO イメージファイルを CD または DVD に書き込む</span><span class="sxs-lookup"><span data-stu-id="3b6f2-106">Burn the ISO image file to a CD or DVD</span></span>

-   <span data-ttu-id="3b6f2-107">ISO イメージファイルのコンテンツを USB フラッシュドライブ (UFD) に保存する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-107">Save the contents of the ISO image file to a USB Flash Drive (UFD)</span></span>

-   <span data-ttu-id="3b6f2-108">ISO イメージから boot.ini ファイルを抽出し、エンドユーザーのコンピューターで使用できるリモートパーティションとして展開する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-108">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

-   <span data-ttu-id="3b6f2-109">ISO イメージから boot.ini ファイルを抽出し、新しい Windows 7 インストールの回復パーティションに展開する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-109">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 7 installation</span></span>

<span data-ttu-id="3b6f2-110">**重要** **DaRT Recovery イメージウィザード**では、CD または DVD の書き込みオプションのみが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-110">**Important** The **DaRT Recovery Image Wizard** only provides the option to burn a CD or DVD.</span></span> <span data-ttu-id="3b6f2-111">回復イメージを保存および展開するその他のすべての方法については、DaRT に含まれていないツールに関連する追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-111">All other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="3b6f2-112">このセクションでは、これらの他の方法に関するガイダンスとリンクをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="3b6f2-113">USB フラッシュドライブを使用して DaRT リカバリ画像を展開する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-113">Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="3b6f2-114">DaRT Recovery イメージウィザードの実行が完了したら、のツールを使って、 <https://go.microsoft.com/fwlink/?LinkId=218888> USB フラッシュドライブ (UFD) に ISO 画像ファイルをコピーできます。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-114">After you have finished running the DaRT Recovery Image Wizard, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

[<span data-ttu-id="3b6f2-115">USB フラッシュ ドライブを使用して DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="3b6f2-115">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## <span data-ttu-id="3b6f2-116">DaRT リカバリ画像を回復パーティションの一部として展開する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-116">Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="3b6f2-117">DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出して、Windows 7 イメージの回復パーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-117">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

[<span data-ttu-id="3b6f2-118">回復パーティションの一部として DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="3b6f2-118">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## <span data-ttu-id="3b6f2-119">DaRT リカバリ画像をリモートのパーティションとして展開する</span><span class="sxs-lookup"><span data-stu-id="3b6f2-119">Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="3b6f2-120">DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出し、ネットワーク上のリモートパーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="3b6f2-120">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

[<span data-ttu-id="3b6f2-121">リモート パーティションとして DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="3b6f2-121">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## <span data-ttu-id="3b6f2-122">DaRT リカバリイメージの展開を管理するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="3b6f2-122">Other resources for maintaining Deploying the DaRT Recovery Image</span></span>


-   [<span data-ttu-id="3b6f2-123">DaRT 7.0 の展開</span><span class="sxs-lookup"><span data-stu-id="3b6f2-123">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





