---
title: DaRT の回復イメージの展開
description: DaRT の回復イメージの展開
author: dansimp
ms.assetid: df5cb54a-be8c-4ed2-89ea-d3c67c2ef4d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e445873324f005455ba3c96319847dea8ba761ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824114"
---
# <span data-ttu-id="96581-103">DaRT の回復イメージの展開</span><span class="sxs-lookup"><span data-stu-id="96581-103">Deploying the DaRT Recovery Image</span></span>


<span data-ttu-id="96581-104">Microsoft Diagnostics and Recovery ツールセット (DaRT) 8.0 回復イメージを含む国際標準化機構 (ISO) ファイルを作成した後、エンドユーザーやヘルプデスクの担当者が利用できるように、企業全体で DaRT 8.0 の回復イメージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="96581-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image, you can deploy the DaRT 8.0 recovery image throughout your enterprise so that it is available to end users and help desk workers.</span></span> <span data-ttu-id="96581-105">DaRT リカバリイメージの展開に使用できる、4つのサポートされるメソッドが用意されています。</span><span class="sxs-lookup"><span data-stu-id="96581-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span> <span data-ttu-id="96581-106">各方法の長所と短所を確認するには、「 [DaRT 8.0 回復イメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="96581-106">To review the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="96581-107">DaRT 回復イメージウィザードを使用して、ISO イメージファイルを CD または DVD に書き込む</span><span class="sxs-lookup"><span data-stu-id="96581-107">Burn the ISO image file to a CD or DVD by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="96581-108">DaRT 回復イメージウィザードを使用して、ISO イメージファイルのコンテンツを USB フラッシュドライブ (UFD) に保存します。</span><span class="sxs-lookup"><span data-stu-id="96581-108">Save the contents of the ISO image file to a USB Flash Drive (UFD) by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="96581-109">ISO イメージから boot.ini ファイルを抽出し、エンドユーザーのコンピューターで使用できるリモートパーティションとして展開する</span><span class="sxs-lookup"><span data-stu-id="96581-109">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

<span data-ttu-id="96581-110">ISO イメージから boot.ini ファイルを抽出し、新しい Windows 8 インストールの回復パーティションに展開する</span><span class="sxs-lookup"><span data-stu-id="96581-110">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 8 installation</span></span>

<span data-ttu-id="96581-111">**重要** **Dart の回復イメージウィザード**では、画像を CD、DVD、または UFD に書き込むことができます。ただし、回復イメージを保存および展開するその他の方法には、DaRT に含まれていないツールに関連する追加の手順が必要です。</span><span class="sxs-lookup"><span data-stu-id="96581-111">**Important** The **DaRT Recovery Image Wizard** provides the option to burn the image to a CD, DVD or UFD, but the other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="96581-112">このセクションでは、これらの他の方法に関するガイダンスとリンクをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="96581-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="96581-113">DaRT リカバリ画像を回復パーティションの一部として展開する</span><span class="sxs-lookup"><span data-stu-id="96581-113">Deploy the DaRT recovery image as part of a recovery partition</span></span>


<span data-ttu-id="96581-114">DaRT Recovery イメージウィザードの実行と回復イメージの作成が完了したら、ISO イメージファイルから boot.ini ファイルを抽出して、Windows 8 イメージの回復パーティションとして展開することができます。</span><span class="sxs-lookup"><span data-stu-id="96581-114">After you have finished running the DaRT Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span>

[<span data-ttu-id="96581-115">回復パーティションの一部として DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="96581-115">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-8.md)

## <span data-ttu-id="96581-116">DaRT リカバリ画像をリモートのパーティションとして展開する</span><span class="sxs-lookup"><span data-stu-id="96581-116">Deploy the DaRT recovery image as a remote partition</span></span>


<span data-ttu-id="96581-117">Windows 展開サービスなどの中央ネットワークブートサーバーで回復イメージをホストし、ユーザーまたはサポートスタッフがオンデマンドでコンピューターにイメージをストリーミングできるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="96581-117">You can host the recovery image on a central network boot server, such as Windows Deployment Services, and allow users or support staff to stream the image to computers on demand.</span></span>

[<span data-ttu-id="96581-118">リモート パーティションとして DaRT の回復イメージを展開する方法</span><span class="sxs-lookup"><span data-stu-id="96581-118">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-8.md)

## <span data-ttu-id="96581-119">DaRT リカバリイメージの展開に関するその他のリソース</span><span class="sxs-lookup"><span data-stu-id="96581-119">Other resources for deploying the DaRT recovery image</span></span>


[<span data-ttu-id="96581-120">DaRT 8.0 の展開</span><span class="sxs-lookup"><span data-stu-id="96581-120">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





