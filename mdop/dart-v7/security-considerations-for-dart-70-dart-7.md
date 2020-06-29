---
title: DaRT 7.0 のセキュリティに関する考慮事項
description: DaRT 7.0 のセキュリティに関する考慮事項
author: dansimp
ms.assetid: 52ad7e6c-c169-4ba4-aa76-56335a585eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739c0319195aeb26e38d55ffe01d14b623de7f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822734"
---
# <span data-ttu-id="c9957-103">DaRT 7.0 のセキュリティに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="c9957-103">Security Considerations for DaRT 7.0</span></span>


<span data-ttu-id="c9957-104">Microsoft 診断/回復ツールセット (DaRT) 7 には、エンドユーザーのコンピューターでの問題を解決するために、管理者が DaRT ツールをリモートで実行できる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="c9957-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes functionality that lets an administrator run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="c9957-105">以前の DaRT のリリースでは、ヘルプデスクの技術者または管理者が、DaRT リカバリ画像が含まれている CD または DVD を使って DaRT を起動する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="c9957-105">In earlier releases of DaRT, a help desk technician or administrator had to physically be at an end-user computer and boot into DaRT by using the CD or DVD that included the DaRT recovery image.</span></span> <span data-ttu-id="c9957-106">これで、ヘルプデスクの技術者または管理者は、同じ手順をリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="c9957-106">Now, the help desk technician or administrator can perform the same procedures remotely.</span></span>

<span data-ttu-id="c9957-107">また、DaRT7 でも、CD または DVD の書き込みに加えて、国際標準化機構 (ISO) の画像を USB フラッシュドライブに保存することができます。</span><span class="sxs-lookup"><span data-stu-id="c9957-107">Also in DaRT7, in addition to burning a CD or DVD, you are now able to save the International Organization for Standardization (ISO) image to a USB flash drive.</span></span> <span data-ttu-id="c9957-108">また、ネットワーク上に ISO 画像を配置したり、コンピューターのハードディスク上に回復パーティションとして追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9957-108">You can also put the ISO image on a network or include its contents as a recovery partition on a computer hard disk.</span></span>

<span data-ttu-id="c9957-109">DaRT7 の**リモート接続**機能により、エンドユーザーは、これらの新しい展開方法のいずれかを使用して DaRT にアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="c9957-109">The **Remote Connection** feature in DaRT7 lets end users access DaRT by using one of these new deployment methods.</span></span> <span data-ttu-id="c9957-110">そのため、DaRT の起動と DaRT ツールへのアクセスが簡単になります。</span><span class="sxs-lookup"><span data-stu-id="c9957-110">Therefore, they can more easily start DaRT and access the DaRT tools.</span></span>

<span data-ttu-id="c9957-111">DaRT7 の新しい機能により、企業での DaRT の使用方法がより柔軟になります。</span><span class="sxs-lookup"><span data-stu-id="c9957-111">The new functionalities in DaRT7 provide much more flexibility in how you use DaRT in your enterprise.</span></span> <span data-ttu-id="c9957-112">ただし、独自のセキュリティ問題のセットも作成して、対処する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9957-112">However, they also create their own set of security issues that must be addressed.</span></span> <span data-ttu-id="c9957-113">DaRT を構成する際には、以下のセキュリティのヒントを考慮することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9957-113">We recommend that you consider the following security tips when you configure DaRT.</span></span>

## <span data-ttu-id="c9957-114">DaRT リカバリ画像の作成時にセキュリティを維持するため</span><span class="sxs-lookup"><span data-stu-id="c9957-114">To help maintain security when you create the DaRT recovery image</span></span>


<span data-ttu-id="c9957-115">DaRT リカバリ画像を作成する場合、含めるツールを選択できます。</span><span class="sxs-lookup"><span data-stu-id="c9957-115">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="c9957-116">セキュリティ上の理由から、ディスクワイプや Locksmith など、より強力な DaRT ツールへのエンドユーザーのアクセスを制限することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9957-116">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="c9957-117">DaRT7 では、構成時に特定のツールを無効にすることができます。また、エンドユーザーがリモート接続機能を開始したときに、ヘルプデスクエージェントで利用できるようにすることもできます。</span><span class="sxs-lookup"><span data-stu-id="c9957-117">In DaRT7, you can disable certain tools during configuration and still make them available to helpdesk agents when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="c9957-118">また、リモート接続セッションを開始するオプションがエンドユーザーが利用できる唯一のツールとなるように、DaRT イメージを構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="c9957-118">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="c9957-119">**重要** リモート接続が確立されると、その回復イメージに含まれているすべてのツール (エンドユーザーが利用できないものも含む) は、エンドユーザーのコンピューターで動作するヘルプデスクエージェントで利用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="c9957-119">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to the helpdesk agent working on the end–user computer.</span></span>

 

<span data-ttu-id="c9957-120">DaRT リカバリ画像にツールを含める方法について詳しくは、「 [Dart Recovery イメージウィザードを使用して回復イメージを作成する方法](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="c9957-120">For more information about including tools in the DaRT recovery image, see [How to Use the DaRT Recovery Image Wizard to Create the Recovery Image](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="c9957-121">DaRT リカバリイメージを暗号化してセキュリティを維持するには</span><span class="sxs-lookup"><span data-stu-id="c9957-121">To help maintain security by encrypting the DaRT recovery image</span></span>


<span data-ttu-id="c9957-122">DaRT7 で新しい展開オプションのいずれかを使用している場合、たとえば、USB フラッシュドライブに保存したり、リモートパーティションや回復パーティションを作成したりする場合は、お客様の会社の推奨されるドライブ暗号化方法を ISO に含めることができます。</span><span class="sxs-lookup"><span data-stu-id="c9957-122">If you use one of the deployment options new in DaRT7, for example, saving to a USB flash drive or creating a remote partition or a recovery partition, you can include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="c9957-123">これにより、エンドユーザーは DaRT の機能を使用して回復イメージにアクセスできないようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="c9957-123">This will help make sure that an end user cannot use the functionality of DaRT should they gain access to the recovery image.</span></span> <span data-ttu-id="c9957-124">また、他のユーザに所属しているコンピュータでは、不正ユーザが DaRT を起動することができなくなります。</span><span class="sxs-lookup"><span data-stu-id="c9957-124">And it will also make sure that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span>

<span data-ttu-id="c9957-125">暗号化の方法は、すべてのコンピューターで展開して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="c9957-125">Your encryption method should be deployed and enabled in all computers.</span></span>

<span data-ttu-id="c9957-126">**注** DaRT7 は、BitLocker をネイティブでサポートしています。</span><span class="sxs-lookup"><span data-stu-id="c9957-126">**Note** DaRT7 supports BitLocker natively.</span></span>

 

## <span data-ttu-id="c9957-127">リモート接続中に2台のコンピューター間のセキュリティを維持するには</span><span class="sxs-lookup"><span data-stu-id="c9957-127">To help maintain security between two computers during Remote Connection</span></span>


<span data-ttu-id="c9957-128">既定では、**リモート接続**セッションを確立した2台のコンピューター間の通信は暗号化されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="c9957-128">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="c9957-129">そのため、2台のコンピューター間のセキュリティを維持するために、両方のコンピューターが同じネットワークの一部であることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="c9957-129">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="c9957-130">関連トピック</span><span class="sxs-lookup"><span data-stu-id="c9957-130">Related topics</span></span>


[<span data-ttu-id="c9957-131">DaRT 7.0 の操作</span><span class="sxs-lookup"><span data-stu-id="c9957-131">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





