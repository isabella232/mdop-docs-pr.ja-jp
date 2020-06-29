---
title: DaRT 8.0 を使用したコンピューターの回復
description: DaRT 8.0 を使用したコンピューターの回復
author: dansimp
ms.assetid: 0caeb7d9-c1e6-4f32-bc27-157b91630989
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 39bab02488252b53deb971d35bc6872c0a2df73b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824867"
---
# <span data-ttu-id="6d8c0-103">DaRT 8.0 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="6d8c0-103">Recovering Computers Using DaRT 8.0</span></span>


<span data-ttu-id="6d8c0-104">Microsoft Diagnostics and Recovery ツールセット (DaRT) 8.0 回復イメージを展開した後、DaRT 8.0 を使用してコンピューターを回復できます。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-104">After deploying the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image, you can use DaRT 8.0 to recover computers.</span></span> <span data-ttu-id="6d8c0-105">このセクションの情報では、実行できる回復タスクについて説明します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-105">The information in this section describes the recovery tasks that you can perform.</span></span>

<span data-ttu-id="6d8c0-106">Dart リカバリ画像の展開方法によっては、DaRT を起動するためのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-106">You have several different methods to choose from to boot into DaRT, depending on how you deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="6d8c0-107">問題のあるコンピューターに DaRT 回復イメージ CD、DVD、または USB フラッシュドライブを挿入し、それを使用してコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-107">Insert a DaRT recovery image CD, DVD, or USB flash drive into the problem computer and use it to boot into the computer.</span></span>

-   <span data-ttu-id="6d8c0-108">問題のあるコンピューターの回復パーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-108">Boot into DaRT from a recovery partition on the problem computer.</span></span>

-   <span data-ttu-id="6d8c0-109">ネットワーク上のリモートパーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-109">Boot into DaRT from a remote partition on the network.</span></span>

<span data-ttu-id="6d8c0-110">各方法の長所と短所については、「 [DaRT 8.0 回復イメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-110">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="6d8c0-111">DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-111">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

<span data-ttu-id="6d8c0-112">**注** BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-112">**Note** Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>

 

## <span data-ttu-id="6d8c0-113">DaRT リカバリイメージを使用してローカルコンピューターを回復する</span><span class="sxs-lookup"><span data-stu-id="6d8c0-113">Recover a local computer by using the DaRT recovery image</span></span>


<span data-ttu-id="6d8c0-114">DaRT を使用してローカルコンピューターを復元するには、DaRT を必要とする問題が発生しているエンドユーザーのコンピューターに物理的に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-114">To recover a local computer by using DaRT, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span>

[<span data-ttu-id="6d8c0-115">DaRT 回復イメージを使用してローカル コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="6d8c0-115">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-local-computers-by-using-the-dart-recovery-image-dart-8.md)

## <span data-ttu-id="6d8c0-116">DaRT リカバリイメージを使用してリモートコンピューターを回復する</span><span class="sxs-lookup"><span data-stu-id="6d8c0-116">Recover a remote computer by using the DaRT recovery image</span></span>


<span data-ttu-id="6d8c0-117">DaRT のリモート接続機能により、IT 管理者は、エンドユーザのコンピュータで DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-117">The Remote Connection feature in DaRT lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="6d8c0-118">エンドユーザー (またはエンドユーザーのコンピューターで作業しているヘルプデスクプロフェッショナル) によって特定の情報が提供されると、IT 管理者またはヘルプデスクの担当者は、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-118">After certain information is provided by the end user (or by a help desk professional working on the end-user computer), the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="6d8c0-119">**重要** リモート接続を確立する2台のコンピューターは、同じネットワークの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-119">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

<span data-ttu-id="6d8c0-120">**診断/回復ツールセット**ウィンドウには、エンドユーザーのコンピューターで DaRT を管理者コンピューターからリモートで実行するオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-120">The **Diagnostics and Recovery Toolset** window includes the option to run DaRT on an end-user computer remotely from an administrator computer.</span></span> <span data-ttu-id="6d8c0-121">エンドユーザーは、問題のあるコンピューターで DaRT ツールを開き、[**リモート接続**] をクリックしてリモートセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-121">The end user opens the DaRT tools on the problem computer and starts the remote session by clicking **Remote Connection**.</span></span>

<span data-ttu-id="6d8c0-122">エンドユーザーコンピューターのリモート接続機能は、チケット番号、ポート、および利用可能なすべての IP アドレスの一覧という接続情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-122">The Remote Connection feature on the end-user computer creates the following connection information: a ticket number, a port, and a list of all available IP addresses.</span></span> <span data-ttu-id="6d8c0-123">チケット番号とポートはランダムに生成されます。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-123">The ticket number and port are generated randomly.</span></span>

<span data-ttu-id="6d8c0-124">IT 管理者またはヘルプデスクの担当者は、 **DaRT リモート接続ビューアー**にこの情報を入力して、エンドユーザーコンピューターへのターミナルサービス接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-124">The IT administrator or help desk worker enters this information into the **DaRT Remote Connection Viewer** to establish the terminal services connection to the end-user computer.</span></span> <span data-ttu-id="6d8c0-125">確立されたターミナルサービス接続によって、IT 管理者は、エンドユーザーのコンピューター上の DaRT ツールをリモートで操作することができます。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-125">The terminal services connection that is established lets an IT administrator remotely interact with the DaRT tools on the end-user computer.</span></span> <span data-ttu-id="6d8c0-126">エンドユーザーコンピューターは、接続情報を処理し、画面を共有して、IT 管理者コンピューターからの指示に応答します。</span><span class="sxs-lookup"><span data-stu-id="6d8c0-126">The end-user computer then processes the connection information, shares its screen, and responds to instructions from the IT administrator computer.</span></span>

[<span data-ttu-id="6d8c0-127">DaRT 回復イメージを使用してリモート コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="6d8c0-127">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-8.md)

## <span data-ttu-id="6d8c0-128">DaRT 8.0 を使用してコンピューターを回復するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="6d8c0-128">Other resources for recovering computers using DaRT 8.0</span></span>


[<span data-ttu-id="6d8c0-129">DaRT 8.0 の操作</span><span class="sxs-lookup"><span data-stu-id="6d8c0-129">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

 

 





