---
title: DaRT 7.0 を使用したコンピューターの回復
description: DaRT 7.0 を使用したコンピューターの回復
author: dansimp
ms.assetid: bcded7ca-237b-4971-ac34-4394b05cbc50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 44dd48146155294bd8013b4b5a9bf23ffb3e8316
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822767"
---
# <span data-ttu-id="02393-103">DaRT 7.0 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="02393-103">Recovering Computers Using DaRT 7.0</span></span>


<span data-ttu-id="02393-104">Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 を使用してコンピューターを回復するには、2つの方法があります。</span><span class="sxs-lookup"><span data-stu-id="02393-104">There are two methods available to recover computers using Microsoft Diagnostics and Recovery Toolset (DaRT)7.</span></span> <span data-ttu-id="02393-105">DaRT7 回復イメージをローカルで実行するか、DaRT7 で利用可能なリモート接続機能を使ってリモートコンピューターを回復することができます。</span><span class="sxs-lookup"><span data-stu-id="02393-105">You can either run the DaRT7 recovery image locally or use The Remote Connection feature available in DaRT7 to recover a remote computer.</span></span> <span data-ttu-id="02393-106">どちらの方法についても、このセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="02393-106">Both methods are described in more detail in this section.</span></span>

## <span data-ttu-id="02393-107">DaRT リカバリイメージを使用してローカルコンピューターを回復する</span><span class="sxs-lookup"><span data-stu-id="02393-107">Recover Local Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="02393-108">DaRT7 を使用してローカルコンピューターを回復するには、DaRT を必要とする問題が発生しているエンドユーザーのコンピューターに物理的に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="02393-108">To recover a local computer by using DaRT7, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span>

<span data-ttu-id="02393-109">Dart リカバリ画像の展開方法によっては、DaRT を起動するためのさまざまな方法があります。</span><span class="sxs-lookup"><span data-stu-id="02393-109">You have several different methods to choose from to boot into DaRT, depending on how you deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="02393-110">問題のあるコンピューターに DaRT 回復イメージ CD、DVD、または USB フラッシュドライブを挿入し、それを使用してコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="02393-110">Insert a DaRT recovery image CD, DVD, or USB flash drive into the problem computer and use it to boot into the computer.</span></span>

-   <span data-ttu-id="02393-111">問題のあるコンピューターの回復パーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="02393-111">Boot into DaRT from a recovery partition on the problem computer.</span></span>

-   <span data-ttu-id="02393-112">ネットワーク上のリモートパーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="02393-112">Boot into DaRT from a remote partition on the network.</span></span>

<span data-ttu-id="02393-113">各方法の長所と短所については、「 [DaRT 7.0 回復イメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02393-113">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 7.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md).</span></span>

<span data-ttu-id="02393-114">DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="02393-114">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

<span data-ttu-id="02393-115">**注** BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。</span><span class="sxs-lookup"><span data-stu-id="02393-115">**Note** Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>

 

[<span data-ttu-id="02393-116">DaRT の回復イメージを使用してローカル コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="02393-116">How to Recover Local Computers Using the DaRT Recovery Image</span></span>](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)

## <span data-ttu-id="02393-117">DaRT リカバリイメージを使用してリモートコンピューターを回復する</span><span class="sxs-lookup"><span data-stu-id="02393-117">Recover Remote Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="02393-118">DaRT のリモート接続機能により、IT 管理者は、エンドユーザのコンピュータで DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="02393-118">The Remote Connection feature in DaRT lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="02393-119">エンドユーザー (またはエンドユーザーのコンピューターでのヘルプデスクプロフェッショナル) によって特定の情報が提供されると、IT 管理者またはヘルプデスクエージェントは、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="02393-119">After certain information is provided by the end user (or by a helpdesk professional working on the end-user computer), the IT administrator or helpdesk agent can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="02393-120">**重要** リモート接続を確立する2台のコンピューターは、同じネットワークの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="02393-120">**Important** The two computers establishing a remote connection must be part of the same network.</span></span>

 

<span data-ttu-id="02393-121">**診断/回復ツールセット**ウィンドウには、エンドユーザーのコンピューターで DaRT を管理者コンピューターからリモートで実行するオプションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="02393-121">The **Diagnostics and Recovery Toolset** window includes the option to run DaRT on an end-user computer remotely from an administrator computer.</span></span> <span data-ttu-id="02393-122">エンドユーザーは、問題のあるコンピューターで DaRT ツールを開き、[**リモート接続**] をクリックしてリモートセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="02393-122">The end user opens the DaRT tools on the problem computer and starts the remote session by clicking **Remote Connection**.</span></span>

<span data-ttu-id="02393-123">エンドユーザーコンピューターのリモート接続機能は、チケット番号、ポート、および利用可能なすべての IP アドレスの一覧という接続情報を作成します。</span><span class="sxs-lookup"><span data-stu-id="02393-123">The Remote Connection feature on the end-user computer creates the following connection information: a ticket number, a port, and a list of all available IP addresses.</span></span> <span data-ttu-id="02393-124">チケット番号とポートはランダムに生成されます。</span><span class="sxs-lookup"><span data-stu-id="02393-124">The ticket number and port are generated randomly.</span></span>

<span data-ttu-id="02393-125">IT 管理者またはヘルプデスクエージェントが、この情報を**DaRT リモート接続ビューアー**に入力して、エンドユーザーコンピューターへのターミナルサービス接続を確立します。</span><span class="sxs-lookup"><span data-stu-id="02393-125">The IT administrator or helpdesk agent enters this information into the **DaRT Remote Connection Viewer** to establish the terminal services connection to the end-user computer.</span></span> <span data-ttu-id="02393-126">確立されたターミナルサービス接続によって、IT 管理者は、エンドユーザーのコンピューター上の DaRT ツールをリモートで操作することができます。</span><span class="sxs-lookup"><span data-stu-id="02393-126">The terminal services connection that is established lets an IT administrator remotely interact with the DaRT tools on the end-user computer.</span></span> <span data-ttu-id="02393-127">エンドユーザーコンピューターは、接続情報を処理し、画面を共有して、IT 管理者コンピューターからの指示に応答します。</span><span class="sxs-lookup"><span data-stu-id="02393-127">The end-user computer then processes the connection information, shares its screen, and responds to instructions from the IT administrator computer.</span></span>

[<span data-ttu-id="02393-128">DaRT の回復イメージを使用してリモート コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="02393-128">How to Recover Remote Computers Using the DaRT Recovery Image</span></span>](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)

## <span data-ttu-id="02393-129">DaRT7 を使用してコンピューターを回復するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="02393-129">Other resources for recovering computers using DaRT7</span></span>


[<span data-ttu-id="02393-130">DaRT 7.0 の操作</span><span class="sxs-lookup"><span data-stu-id="02393-130">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





