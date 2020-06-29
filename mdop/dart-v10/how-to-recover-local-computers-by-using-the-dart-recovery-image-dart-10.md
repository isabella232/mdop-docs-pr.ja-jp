---
title: DaRT 回復イメージを使用してローカル コンピューターを回復する方法
description: DaRT 回復イメージを使用してローカル コンピューターを回復する方法
author: dansimp
ms.assetid: a6adc717-827c-45e8-b9c3-06d0e919e0bd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 06e8ad82f869568c9fa25fcbb16825b2abff06f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822587"
---
# <span data-ttu-id="a209b-103">DaRT 回復イメージを使用してローカル コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="a209b-103">How to Recover Local Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="a209b-104">問題が発生しているエンドユーザーのコンピューターに物理的に表示されているコンピューターを回復するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a209b-104">Use these instructions to recover a computer when you are physically present at the end-user computer that is experiencing problems.</span></span>

**<span data-ttu-id="a209b-105">DaRT リカバリイメージを使用してローカルコンピューターを復元する方法</span><span class="sxs-lookup"><span data-stu-id="a209b-105">How to recover a local computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="a209b-106">Microsoft 診断/回復ツールセット (DaRT) 10 の回復イメージを使用して、エンドユーザーのコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="a209b-106">Boot the end-user computer by using the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

    <span data-ttu-id="a209b-107">コンピューターが DaRT 10 の回復イメージとして起動すると、 **Netstart**ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a209b-107">As the computer is booting into the DaRT 10 recovery image, the **NetStart** dialog box appears.</span></span>

2.  <span data-ttu-id="a209b-108">ネットワークサービスを初期化するかどうかを確認するメッセージが表示されたら、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="a209b-108">When you are asked whether you want to initialize network services, select one of the following:</span></span>

    <span data-ttu-id="a209b-109">**はい**。ネットワーク上に DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="a209b-109">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="a209b-110">ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="a209b-110">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="a209b-111">**いいえ**。ネットワーク初期化プロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="a209b-111">**No** - skip the network initialization process.</span></span>

3.  <span data-ttu-id="a209b-112">ドライブ文字を再マッピングするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="a209b-112">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="a209b-113">Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="a209b-113">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="a209b-114">再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。</span><span class="sxs-lookup"><span data-stu-id="a209b-114">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="a209b-115">再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="a209b-115">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4.  <span data-ttu-id="a209b-116">[**システム回復オプション**] ダイアログボックスで、キーボードレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="a209b-116">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5.  <span data-ttu-id="a209b-117">表示されたシステムルートディレクトリ、インストールされているオペレーティングシステムの種類、およびパーティションサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="a209b-117">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="a209b-118">使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込み、デバイスのインストールメディアを挿入して、ドライバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="a209b-118">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6.  <span data-ttu-id="a209b-119">修復または診断するインストールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a209b-119">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="a209b-120">注</span><span class="sxs-lookup"><span data-stu-id="a209b-120">Note</span></span>**  
    <span data-ttu-id="a209b-121">Windows 回復環境 (WinRE) で、前回の試用時に Windows 10 が正しく開始されなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。</span><span class="sxs-lookup"><span data-stu-id="a209b-121">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 10 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="a209b-122">[**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a209b-122">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset**.</span></span>

   <span data-ttu-id="a209b-123">[**診断/回復ツールセット**] ウィンドウが開きます。</span><span class="sxs-lookup"><span data-stu-id="a209b-123">The **Diagnostics and Recovery Toolset** window opens.</span></span> <span data-ttu-id="a209b-124">DaRT リカバリ画像の作成時に含まれていた個々のツールまたはウィザードを実行できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="a209b-124">You can now run any of the individual tools or wizards that were included when the DaRT recovery image was created.</span></span>

<span data-ttu-id="a209b-125">**診断/回復ツールセット**ウィンドウの [**ヘルプ**] をクリックすると、個々の DaRT ツールの実行に必要な詳しい手順と情報を提供しているクライアントヘルプファイルを開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a209b-125">You can click **Help** on the **Diagnostics and Recovery Toolset** window to open the client Help file that provides detailed instruction and information needed to run the individual DaRT tools.</span></span> <span data-ttu-id="a209b-126">[**診断/回復ツールセット**] ウィンドウで**ソリューションウィザード**をクリックして、ウィザードで提供される短い面接に基づいて、状況に最適なツールを選ぶこともできます。</span><span class="sxs-lookup"><span data-stu-id="a209b-126">You can also click the **Solution Wizard** on the **Diagnostics and Recovery Toolset** window to choose the best tool for the situation, based on a brief interview that the wizard provides.</span></span>

<span data-ttu-id="a209b-127">DaRT ツールについての一般的な情報については、「 [dart 10 のツールの概要](overview-of-the-tools-in-dart-10.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="a209b-127">For general information about any of the DaRT tools, see [Overview of the Tools in DaRT 10](overview-of-the-tools-in-dart-10.md).</span></span>

**<span data-ttu-id="a209b-128">コマンドプロンプトで DaRT を実行する方法</span><span class="sxs-lookup"><span data-stu-id="a209b-128">How to run DaRT at the command prompt</span></span>**

- <span data-ttu-id="a209b-129">コマンドプロンプトで DaRT を実行するには、 **netstart.exe**コマンドを指定し、次のいずれかのパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="a209b-129">To run DaRT at the command prompt, specify the **netstart.exe** command then use any of the following parameters:</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <tbody>
  <tr class="odd">
  <td align="left"><p><strong><span data-ttu-id="a209b-130">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a209b-130">Parameter</span></span></strong></p></td>
  <td align="left"><p><strong><span data-ttu-id="a209b-131">説明</span><span class="sxs-lookup"><span data-stu-id="a209b-131">Description</span></span></strong></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="a209b-132">-ネットワーク</span><span class="sxs-lookup"><span data-stu-id="a209b-132">-network</span></span></p></td>
  <td align="left"><p><span data-ttu-id="a209b-133">ネットワークサービスを初期化します。</span><span class="sxs-lookup"><span data-stu-id="a209b-133">Initializes the network services.</span></span></p></td>
  </tr>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="a209b-134">-再マウント</span><span class="sxs-lookup"><span data-stu-id="a209b-134">-remount</span></span></p></td>
  <td align="left"><p><span data-ttu-id="a209b-135">ドライブ文字を再マッピングします。</span><span class="sxs-lookup"><span data-stu-id="a209b-135">Remaps the drive letters.</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="a209b-136">-プロンプト</span><span class="sxs-lookup"><span data-stu-id="a209b-136">-prompt</span></span></p></td>
  <td align="left"><p><span data-ttu-id="a209b-137">ネットワークを初期化してドライブを再マップするかどうかをエンドユーザーに指定するように求めるメッセージを表示します。</span><span class="sxs-lookup"><span data-stu-id="a209b-137">Displays messages that ask the end user to specify whether to initialize the network and remap the drives.</span></span></p>
  <div class="alert">
  <strong><span data-ttu-id="a209b-138">Warning</span><span class="sxs-lookup"><span data-stu-id="a209b-138">Warning</span></span></strong><br/><p><span data-ttu-id="a209b-139">プロンプトに対するエンドユーザーの応答は、–ネットワークと再マウントのスイッチを上書きします。</span><span class="sxs-lookup"><span data-stu-id="a209b-139">The end user’s response to the prompt overrides the –network and –remount switches.</span></span></p>
  </div>
  <div>

  </div></td>
  </tr>
  </tbody>
  </table>



## <span data-ttu-id="a209b-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a209b-140">Related topics</span></span>


[<span data-ttu-id="a209b-141">DaRT 10 の操作</span><span class="sxs-lookup"><span data-stu-id="a209b-141">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

[<span data-ttu-id="a209b-142">DaRT 10 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="a209b-142">Recovering Computers Using DaRT 10</span></span>](recovering-computers-using-dart-10.md)









