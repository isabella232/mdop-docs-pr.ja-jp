---
title: DaRT の回復イメージを使用してローカル コンピューターを回復する方法
description: DaRT の回復イメージを使用してローカル コンピューターを回復する方法
author: dansimp
ms.assetid: be29b5a8-be08-4cf2-822e-77a51d3f3b65
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c605db895b5ea812d90db51d3c2de9653e2dd2d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823764"
---
# <span data-ttu-id="b90c2-103">DaRT の回復イメージを使用してローカル コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="b90c2-103">How to Recover Local Computers Using the DaRT Recovery Image</span></span>


<span data-ttu-id="b90c2-104">Microsoft Diagnostics and Recovery ツールセット (DaRT) 7 を使用してローカルコンピューターを回復するには、DaRT を必要とする問題が発生しているエンドユーザーのコンピューターに物理的に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="b90c2-104">To recover a local computer by using Microsoft Diagnostics and Recovery Toolset (DaRT) 7, you must be physically present at the end-user computer that is experiencing problems that require DaRT.</span></span> <span data-ttu-id="b90c2-105">Dart[リカバリ画像を使ってリモートコンピューターを回復する方法](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)については、次の手順に従って dart をリモートで実行することもできます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-105">You can also run DaRT remotely by following the instructions at [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

**<span data-ttu-id="b90c2-106">DaRT を使用してローカルコンピューターを回復するには</span><span class="sxs-lookup"><span data-stu-id="b90c2-106">To recover a local computer by using DaRT</span></span>**

1.  <span data-ttu-id="b90c2-107">コンピュータが DaRT リカバリイメージとして起動すると、 **Netstart**ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-107">As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.</span></span> <span data-ttu-id="b90c2-108">ネットワークサービスを初期化するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-108">You are asked whether you want to initialize network services.</span></span> <span data-ttu-id="b90c2-109">[**はい**] をクリックすると、ネットワークに DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-109">If you click **Yes**, it is assumed that a DHCP server is present on the network and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="b90c2-110">ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="b90c2-111">ネットワーク初期化プロセスをスキップするには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-111">To skip the network initialization process, click **No**.</span></span>

2.  <span data-ttu-id="b90c2-112">[ネットワークの初期化] ダイアログボックスで、ドライブ文字を再マップするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-112">Following the network initialization dialog box, you are asked whether you want to remap the drive letters.</span></span> <span data-ttu-id="b90c2-113">Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="b90c2-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="b90c2-114">再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="b90c2-115">再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

3.  <span data-ttu-id="b90c2-116">[再マッピング] ダイアログボックスで、[**システム回復オプション**] ダイアログボックスが表示され、キーボードレイアウトを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-116">Following the remapping dialog box, a **System Recovery Options** dialog box appears and asks you to select a keyboard layout.</span></span> <span data-ttu-id="b90c2-117">次に、システムルートディレクトリ、インストールされているオペレーティングシステムの種類、パーティションサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-117">Then it displays the system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="b90c2-118">使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers.</span></span> <span data-ttu-id="b90c2-119">デバイスのインストールメディアを挿入して、ドライバーを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-119">This prompts you to insert the installation media for the device and to select the driver.</span></span> <span data-ttu-id="b90c2-120">修復または診断するインストールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-120">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="b90c2-121">注</span><span class="sxs-lookup"><span data-stu-id="b90c2-121">Note</span></span>**  
    <span data-ttu-id="b90c2-122">Windows 回復環境 (WinRE) で、前回の試用時に Windows 7 が正常に起動しなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。</span><span class="sxs-lookup"><span data-stu-id="b90c2-122">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 7 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

4. <span data-ttu-id="b90c2-123">[**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-123">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="b90c2-124">[**診断/回復ツールセット**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-124">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="b90c2-125">DaRT リカバリ画像の作成時に含まれていた個々のツールまたはウィザードを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="b90c2-125">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="b90c2-126">**診断/回復ツールセット**ウィンドウの [**ヘルプ**] をクリックすると、個々の DaRT ツールの実行に必要な詳しい手順と情報を提供しているクライアントヘルプファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-126">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="b90c2-127">[**診断/回復ツールセット**] ウィンドウで**ソリューションウィザード**をクリックして、ウィザードで提供される短い面接に基づいて、状況に最適なツールを選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-127">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="b90c2-128">DaRT ツールについての一般的な情報については、「 [dart 7.0 でのツールの概要](overview-of-the-tools-in-dart-70-new-ia.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="b90c2-128">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

**<span data-ttu-id="b90c2-129">コマンドプロンプトで DaRT を実行するには</span><span class="sxs-lookup"><span data-stu-id="b90c2-129">To run DaRT at the command prompt</span></span>**

1. <span data-ttu-id="b90c2-130">コマンドプロンプトで DaRT を実行するには、 **netstart.exe**コマンドを指定し、次のいずれかのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="b90c2-130">You can run DaRT at the command prompt by specifying the **netstart.exe** command and by using any of the following parameters:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="b90c2-131">パラメーター</span><span class="sxs-lookup"><span data-stu-id="b90c2-131">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="b90c2-132">説明</span><span class="sxs-lookup"><span data-stu-id="b90c2-132">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="b90c2-133">-ネットワーク</span><span class="sxs-lookup"><span data-stu-id="b90c2-133">-network</span></span></p></td>
   <td align="left"><p><span data-ttu-id="b90c2-134">ネットワークサービスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="b90c2-134">Initializes the network services.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="b90c2-135">-再マウント</span><span class="sxs-lookup"><span data-stu-id="b90c2-135">-remount</span></span></p></td>
   <td align="left"><p><span data-ttu-id="b90c2-136">ドライブ文字を再マッピングします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-136">Remaps the drive letters.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="b90c2-137">-プロンプト</span><span class="sxs-lookup"><span data-stu-id="b90c2-137">-prompt</span></span></p></td>
   <td align="left"><p><span data-ttu-id="b90c2-138">ネットワークを初期化してドライブを再マッピングするかどうかをエンドユーザーに指定するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="b90c2-138">Displays messages asking the end user to specify whether to initialize the network and remap the drives.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="b90c2-139">重要</span><span class="sxs-lookup"><span data-stu-id="b90c2-139">Important</span></span></strong><br/><p><span data-ttu-id="b90c2-140">プロンプトに対するエンドユーザーの応答は、ネットワークと再マウントのスイッチを上書きします。</span><span class="sxs-lookup"><span data-stu-id="b90c2-140">The end user’s response to the prompts overrides the -network and -remount switches.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="b90c2-141">Dart をブートしているコンピュータが**リモート**接続ツールを自動的に起動するように dart をカスタマイズして、ヘルプデスクとのリモート接続を確立することができます。</span><span class="sxs-lookup"><span data-stu-id="b90c2-141">You can customize DaRT so that a computer that boots into DaRT automatically opens the **Remote Connection** tool that is used to establish a remote connection with the help desk.</span></span>

## <span data-ttu-id="b90c2-142">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b90c2-142">Related topics</span></span>


[<span data-ttu-id="b90c2-143">DaRT 7.0 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="b90c2-143">Recovering Computers Using DaRT 7.0</span></span>](recovering-computers-using-dart-70-dart-7.md)









