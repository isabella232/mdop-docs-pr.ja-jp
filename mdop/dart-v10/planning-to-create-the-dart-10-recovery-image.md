---
title: DaRT 10 の回復イメージの作成計画
description: DaRT 10 の回復イメージの作成計画
author: dansimp
ms.assetid: a0087d93-b88f-454b-81b2-3c7ce3718023
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 44cf052eaffd19645885618da9104e5b0a50cfd5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822977"
---
# <span data-ttu-id="3be0f-103">DaRT 10 の回復イメージの作成計画</span><span class="sxs-lookup"><span data-stu-id="3be0f-103">Planning to Create the DaRT 10 Recovery Image</span></span>


<span data-ttu-id="3be0f-104">Microsoft 診断/回復ツールセット (DaRT) 10 復元イメージの作成を計画している場合は、このセクションの情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="3be0f-104">Use the information in this section when you are planning to create the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

## <span data-ttu-id="3be0f-105">DaRT 10 の回復イメージの作成を計画する</span><span class="sxs-lookup"><span data-stu-id="3be0f-105">Planning to create the DaRT 10 recovery image</span></span>


<span data-ttu-id="3be0f-106">DaRT リカバリ画像を作成する場合は、イメージに含めるツールを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be0f-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="3be0f-107">決定を行うには、エンドユーザーがこれらのツールにアクセスできる可能性があることを考慮してください。</span><span class="sxs-lookup"><span data-stu-id="3be0f-107">To make the decision, consider that end users may have access to those tools.</span></span> <span data-ttu-id="3be0f-108">サポートエンジニアが回復イメージメディアを使用して、問題を診断している場合は、回復イメージにすべてのツールをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="3be0f-108">If support engineers will take the recovery image media to end users’ computers to diagnose issues, you may want to install all of the tools on the recovery image.</span></span> <span data-ttu-id="3be0f-109">エンドユーザーのコンピューターをリモートで診断することを計画している場合は、ディスクワイプやレジストリエディターなどのツールの一部を無効にして、リモート接続など、他のツールを有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="3be0f-109">If you plan to diagnose end user’s computers remotely, you may want to disable some of the tools, such as Disk Wipe and Registry Editor, and then enable other tools, including Remote Connection.</span></span>

<span data-ttu-id="3be0f-110">DaRT リカバリ画像を作成する場合は、追加のドライバまたはファイルを含めるかどうかも指定します。</span><span class="sxs-lookup"><span data-stu-id="3be0f-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="3be0f-111">DaRT リカバリ画像に含める追加のドライバーまたはファイルの場所を確認します。</span><span class="sxs-lookup"><span data-stu-id="3be0f-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="3be0f-112">DaRT ツールの詳細については、「 [dart 10 のツールの概要](overview-of-the-tools-in-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be0f-112">For more information about the DaRT tools, see [Overview of the Tools in DaRT 10](overview-of-the-tools-in-dart-10.md).</span></span> <span data-ttu-id="3be0f-113">セキュリティで保護された回復イメージを作成する方法の詳細については、「 [DaRT 10 のセキュリティに関する考慮事項](security-considerations-for-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3be0f-113">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 10](security-considerations-for-dart-10.md).</span></span>

## <span data-ttu-id="3be0f-114">回復イメージの前提条件</span><span class="sxs-lookup"><span data-stu-id="3be0f-114">Prerequisites for the recovery image</span></span>


<span data-ttu-id="3be0f-115">DaRT リカバリ画像を作成するには、次の項目が必要または推奨されます。</span><span class="sxs-lookup"><span data-stu-id="3be0f-115">The following items are required or recommended for creating the DaRT recovery image:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3be0f-116">受講</span><span class="sxs-lookup"><span data-stu-id="3be0f-116">Prerequisite</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="3be0f-117">詳細</span><span class="sxs-lookup"><span data-stu-id="3be0f-117">Details</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3be0f-118">Windows 10 のソースファイル</span><span class="sxs-lookup"><span data-stu-id="3be0f-118">Windows 10 source files</span></span></p></td>
<td align="left"><p><span data-ttu-id="3be0f-119">DaRT リカバリ画像の作成に必要。</span><span class="sxs-lookup"><span data-stu-id="3be0f-119">Required to create the DaRT recovery image.</span></span> <span data-ttu-id="3be0f-120">Windows 10 DVD または Windows 10 のソースファイルのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="3be0f-120">Provide the path of a Windows 10 DVD or of Windows 10 source files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3be0f-121">プラットフォーム用の Windows デバッグツール</span><span class="sxs-lookup"><span data-stu-id="3be0f-121">Windows Debugging Tools for your platform</span></span></p></td>
<td align="left"><p><span data-ttu-id="3be0f-122"><strong>クラッシュアナライザーを実行して、 </strong> コンピューターの障害の原因を特定する場合に必要です。</span><span class="sxs-lookup"><span data-stu-id="3be0f-122">Required when you run the <strong>Crash Analyzer</strong> to determine the cause of a computer failure.</span></span> <span data-ttu-id="3be0f-123">DaRT リカバリ画像を作成するときに、Windows のデバッグツールのパスを指定することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3be0f-123">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="3be0f-124">Windows デバッグツールをダウンロードするには、次の手順を実行します。 <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)"> windows 用のデバッグツールをダウンロードしてインストール </a> します。</span><span class="sxs-lookup"><span data-stu-id="3be0f-124">You can download the Windows Debugging Tools here: <a href="https://docs.microsoft.com/windows-hardware/drivers/debugger/" data-raw-source="[Download and Install Debugging Tools for Windows](https://docs.microsoft.com/windows-hardware/drivers/debugger/)">Download and Install Debugging Tools for Windows</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3be0f-125">オプション: Crash Analyzer で使用する Windows のシンボルファイル <strong></span><span class="sxs-lookup"><span data-stu-id="3be0f-125">Optional: Windows symbols files for use with <strong>Crash Analyzer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3be0f-126">通常、デバッグ情報は、プログラムとは別のシンボルファイルに格納されます。</span><span class="sxs-lookup"><span data-stu-id="3be0f-126">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="3be0f-127">動作が停止した場合など、応答が停止しているアプリケーションをデバッグするときは、シンボル情報へのアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3be0f-127">You must have access to the symbol information when you debug an application that has stopped responding, for example, if it stopped working.</span></span> <span data-ttu-id="3be0f-128">詳細については、「 <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)"> クラッシュアナライザーによるシステム障害の診断」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="3be0f-128">For more information, see <a href="diagnosing-system-failures-with-crash-analyzer-dart-10.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer-dart-10.md)">Diagnosing System Failures with Crash Analyzer</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3be0f-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3be0f-129">Related topics</span></span>

[<span data-ttu-id="3be0f-130">DaRT 10 の展開計画</span><span class="sxs-lookup"><span data-stu-id="3be0f-130">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 




