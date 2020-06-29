---
title: DaRT 回復イメージを使用してリモート コンピューターを回復する方法
description: DaRT 回復イメージを使用してリモート コンピューターを回復する方法
author: dansimp
ms.assetid: c0062208-39cd-4e01-adf8-36a11386e2ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 42d49c6c5c494da866785764e1c93a6bda2d667e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822594"
---
# <span data-ttu-id="39197-103">DaRT 回復イメージを使用してリモート コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="39197-103">How to Recover Remote Computers by Using the DaRT Recovery Image</span></span>


<span data-ttu-id="39197-104">Microsoft 診断/回復ツールセット (DaRT) 10 のリモート接続機能を使用して、エンドユーザーのコンピューターで DaRT ツールをリモートで実行します。</span><span class="sxs-lookup"><span data-stu-id="39197-104">Use the Remote Connection feature in Microsoft Diagnostics and Recovery Toolset (DaRT) 10 to run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="39197-105">エンドユーザーが管理者またはヘルプデスクの担当者に特定の情報を提供した後、IT 管理者またはヘルプデスクのワーカーは、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="39197-105">After the end user provides the administrator or help desk worker with certain information, the IT administrator or help desk worker can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

<span data-ttu-id="39197-106">回復イメージを作成したときに DaRT ツールを無効にした場合でも、すべてのツールにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="39197-106">If you disabled the DaRT tools when you created the recovery image, you still have access to all of the tools.</span></span> <span data-ttu-id="39197-107">リモート接続を除くすべてのツールは、エンドユーザーが利用できません。</span><span class="sxs-lookup"><span data-stu-id="39197-107">All of the tools, except Remote Connection, are unavailable to end users.</span></span>

**<span data-ttu-id="39197-108">DaRT リカバリイメージを使用してリモートコンピューターを回復するには</span><span class="sxs-lookup"><span data-stu-id="39197-108">To recover a remote computer by using the DaRT recovery image</span></span>**

1.  <span data-ttu-id="39197-109">DaRT 回復イメージを使用して、エンドユーザーのコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="39197-109">Boot an end-user computer by using the DaRT recovery image.</span></span>

    <span data-ttu-id="39197-110">通常、次のいずれかの方法を使用して、dart の回復イメージの展開方法に応じて DaRT を起動し、リモートコンピューターを回復します。</span><span class="sxs-lookup"><span data-stu-id="39197-110">You will typically use one of the following methods to boot into DaRT to recover a remote computer, depending on how you deploy the DaRT recovery image.</span></span> <span data-ttu-id="39197-111">DaRT リカバリ画像の展開について詳しくは、「 [dart 10 の展開](deploying-dart-10.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="39197-111">For more information about deploying the DaRT recovery image, see [Deploying DaRT 10](deploying-dart-10.md).</span></span>

    -   <span data-ttu-id="39197-112">問題のあるコンピューターの回復パーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="39197-112">Boot into DaRT from a recovery partition on the problem computer.</span></span>

    -   <span data-ttu-id="39197-113">ネットワーク上のリモートパーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="39197-113">Boot into DaRT from a remote partition on the network.</span></span>

    <span data-ttu-id="39197-114">各方法の長所と短所については、「 [DaRT 10 の回復イメージを保存して展開する方法を計画する](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39197-114">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 10 Recovery Image](planning-how-to-save-and-deploy-the-dart-10-recovery-image.md).</span></span>

    <span data-ttu-id="39197-115">DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="39197-115">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

    **<span data-ttu-id="39197-116">注</span><span class="sxs-lookup"><span data-stu-id="39197-116">Note</span></span>**  
    <span data-ttu-id="39197-117">BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。</span><span class="sxs-lookup"><span data-stu-id="39197-117">Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>



~~~
As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.
~~~

2. <span data-ttu-id="39197-118">ネットワークサービスを初期化するかどうかを確認するメッセージが表示されたら、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="39197-118">When you are asked whether you want to initialize network services, select one of the following:</span></span>

   <span data-ttu-id="39197-119">**はい**。ネットワーク上に DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしていることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="39197-119">**Yes** - it is assumed that a DHCP server is present on the network, and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="39197-120">ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="39197-120">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

   <span data-ttu-id="39197-121">**いいえ**。ネットワーク初期化プロセスをスキップします。</span><span class="sxs-lookup"><span data-stu-id="39197-121">**No** - skip the network initialization process.</span></span>

3. <span data-ttu-id="39197-122">ドライブ文字を再マッピングするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="39197-122">Indicate whether you want to remap the drive letters.</span></span> <span data-ttu-id="39197-123">Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="39197-123">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="39197-124">再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。</span><span class="sxs-lookup"><span data-stu-id="39197-124">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="39197-125">再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="39197-125">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4. <span data-ttu-id="39197-126">[**システム回復オプション**] ダイアログボックスで、キーボードレイアウトを選択します。</span><span class="sxs-lookup"><span data-stu-id="39197-126">On the **System Recovery Options** dialog box, select a keyboard layout.</span></span>

5. <span data-ttu-id="39197-127">表示されたシステムルートディレクトリ、インストールされているオペレーティングシステムの種類、およびパーティションサイズを確認します。</span><span class="sxs-lookup"><span data-stu-id="39197-127">Check the displayed system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="39197-128">使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込み、デバイスのインストールメディアを挿入して、ドライバーを選びます。</span><span class="sxs-lookup"><span data-stu-id="39197-128">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers, and then insert the installation media for the device and select the driver.</span></span>

6. <span data-ttu-id="39197-129">修復または診断するインストールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39197-129">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

   **<span data-ttu-id="39197-130">注</span><span class="sxs-lookup"><span data-stu-id="39197-130">Note</span></span>**  
   <span data-ttu-id="39197-131">Windows 回復環境 (WinRE) で、前回の試用時に Windows 10 が正しく開始されなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。</span><span class="sxs-lookup"><span data-stu-id="39197-131">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 10 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span> <span data-ttu-id="39197-132">この問題を解決する方法については、「 [DaRT 10 のトラブルシューティング](troubleshooting-dart-10.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39197-132">For information about how to resolve this issue, see [Troubleshooting DaRT 10](troubleshooting-dart-10.md).</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor and several other DaRT utilities will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

7. <span data-ttu-id="39197-133">[**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] をクリックし、**診断/回復ツールセット**を開きます。</span><span class="sxs-lookup"><span data-stu-id="39197-133">On the **System Recovery Options** window, click **Microsoft Diagnostics and Recovery Toolset** to open the **Diagnostics and Recovery Toolset**.</span></span>

8. <span data-ttu-id="39197-134">[**診断/回復ツールセット**] ウィンドウで、[**リモート接続**] をクリックして**DaRT リモート接続**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="39197-134">On the **Diagnostics and Recovery Toolset** window, click **Remote Connection** to open the **DaRT Remote Connection** window.</span></span> <span data-ttu-id="39197-135">ヘルプデスクのリモートアクセスの指定を求められたら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39197-135">If you are prompted to give the help desk remote access, click **OK**.</span></span>

   <span data-ttu-id="39197-136">DaRT リモート接続ウィンドウが開き、チケット番号、IP アドレス、ポート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="39197-136">The DaRT Remote Connection window opens and displays a ticket number, IP address, and port information.</span></span>

9. <span data-ttu-id="39197-137">ヘルプデスクコンピューターで、 **DaRT リモート接続ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="39197-137">On the help desk computer, open the **DaRT Remote Connection Viewer**.</span></span>

10. <span data-ttu-id="39197-138">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Dart 10**]、[ **dart リモート接続ビューアー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="39197-138">Click **Start**, click **All Programs**, click **Microsoft DaRT 10**, and then click **DaRT Remote Connection Viewer**.</span></span>

11. <span data-ttu-id="39197-139">**DaRT リモート接続**ウィンドウで、必要なチケット、IP アドレス、ポート情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="39197-139">In the **DaRT Remote Connection** window, enter the required ticket, IP address, and port information.</span></span>

   **<span data-ttu-id="39197-140">注</span><span class="sxs-lookup"><span data-stu-id="39197-140">Note</span></span>**  
   <span data-ttu-id="39197-141">この情報は、エンドユーザーのコンピューター上に作成され、エンドユーザーによって提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="39197-141">This information is created on the end-user computer and must be provided by the end user.</span></span> <span data-ttu-id="39197-142">エンドユーザーコンピューターで利用可能な IP アドレスの数に応じて、複数の IP アドレスを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="39197-142">There might be multiple IP addresses to choose from, depending on how many are available on the end-user computer.</span></span>



12. <span data-ttu-id="39197-143">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="39197-143">Click **Connect**.</span></span>

<span data-ttu-id="39197-144">IT 管理者は、エンドユーザーのコンピューターの制御を前提としており、DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="39197-144">The IT administrator now assumes control of the end-user computer and can run the DaRT tools remotely.</span></span>

**<span data-ttu-id="39197-145">注</span><span class="sxs-lookup"><span data-stu-id="39197-145">Note</span></span>**  
<span data-ttu-id="39197-146">inv32.xml という名前のファイルが用意されており、ポート番号や IP アドレスなどのリモート接続情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="39197-146">A file is provided that is named inv32.xml and contains remote connection information, such as the port number and IP address.</span></span> <span data-ttu-id="39197-147">既定では、ファイルは%windir%\\system32. にあります。</span><span class="sxs-lookup"><span data-stu-id="39197-147">By default, the file is typically located at %windir%\\system32.</span></span>



**<span data-ttu-id="39197-148">リモート接続プロセスをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="39197-148">To customize the Remote Connection process</span></span>**

1. <span data-ttu-id="39197-149">winpeshl.ini ファイルを編集することで、リモート接続プロセスをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="39197-149">You can customize the Remote Connection process by editing the winpeshl.ini file.</span></span> <span data-ttu-id="39197-150">winpeshl.ini ファイルを編集する方法の詳細については、「 [Winpeshl.ini ファイル](https://go.microsoft.com/fwlink/?LinkId=219413)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="39197-150">For more information about how to edit the winpeshl.ini file, see [Winpeshl.ini Files](https://go.microsoft.com/fwlink/?LinkId=219413).</span></span>

   <span data-ttu-id="39197-151">次のコマンドとパラメーターを指定して、エンドユーザーのコンピューターとのリモート接続の確立方法をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="39197-151">Specify the following commands and parameters to customize how a remote connection is established with an end-user computer:</span></span>

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="39197-152">コマンド</span><span class="sxs-lookup"><span data-stu-id="39197-152">Command</span></span></th>
   <th align="left"><span data-ttu-id="39197-153">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39197-153">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="39197-154">説明</span><span class="sxs-lookup"><span data-stu-id="39197-154">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="39197-155">RemoteRecovery.exe</span><span class="sxs-lookup"><span data-stu-id="39197-155">RemoteRecovery.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="39197-156">-nomessage</span><span class="sxs-lookup"><span data-stu-id="39197-156">-nomessage</span></span></p></td>
   <td align="left"><p><span data-ttu-id="39197-157">確認メッセージが表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="39197-157">Specifies that the confirmation prompt is not displayed.</span></span> <strong><span data-ttu-id="39197-158">リモート接続は </strong> 、エンドユーザーによって &quot; [はい] が確認プロンプトに応答した場合と同じように継続さ &quot; れます。</span><span class="sxs-lookup"><span data-stu-id="39197-158">Remote Connection</strong> continues just as if the end user had responded &quot;Yes&quot; to the confirmation prompt.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="39197-159">WaitForConnection.exe</span><span class="sxs-lookup"><span data-stu-id="39197-159">WaitForConnection.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="39197-160">なし</span><span class="sxs-lookup"><span data-stu-id="39197-160">none</span></span></p></td>
   <td align="left"><p><span data-ttu-id="39197-161"><strong>リモート接続が実行されて </strong> いないか、エンドユーザーのコンピューターとの接続が確立されるまで、カスタムスクリプトが続行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="39197-161">Prevents a custom script from continuing until either <strong>Remote Connection</strong> is not running or a valid connection is established with the end-user computer.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="39197-162">重要</span><span class="sxs-lookup"><span data-stu-id="39197-162">Important</span></span></strong><br/><p><span data-ttu-id="39197-163">このコマンドは、個別に指定されている場合は関数を提供しません。</span><span class="sxs-lookup"><span data-stu-id="39197-163">This command serves no function if it is specified independently.</span></span> <span data-ttu-id="39197-164">正しく機能するためには、スクリプトで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="39197-164">It must be specified in a script to function correctly.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="39197-165">DaRT を起動しようとするとすぐに**リモート接続**ツールを開くようにカスタマイズされた winpeshl.ini ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="39197-165">The following is an example of a winpeshl.ini file that is customized to open the **Remote Connection** tool as soon as an attempt is made to boot into DaRT:</span></span>

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

<span data-ttu-id="39197-166">DaRT が起動すると、RAM ディスク上の \\Windows\\System32\\ にファイル inv32.xml が作成されます。</span><span class="sxs-lookup"><span data-stu-id="39197-166">When DaRT starts, it creates the file inv32.xml in \\Windows\\System32\\ on the RAM disk.</span></span> <span data-ttu-id="39197-167">このファイルには、IP アドレス、ポート、チケット番号などの接続情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="39197-167">This file contains connection information: IP address, port, and ticket number.</span></span> <span data-ttu-id="39197-168">このファイルをネットワーク共有にコピーして、ヘルプデスクワークフローをトリガーすることができます。</span><span class="sxs-lookup"><span data-stu-id="39197-168">You can copy this file to a network share to trigger a Help desk workflow.</span></span> <span data-ttu-id="39197-169">たとえば、カスタムプログラムで接続ファイルのネットワーク共有を確認し、サポートチケットを作成したり、メール通知を送信したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="39197-169">For example, a custom program can check the network share for connection files, and then create a support ticket or send email notifications.</span></span>

**<span data-ttu-id="39197-170">コマンドプロンプトでリモート接続ビューアーを実行するには</span><span class="sxs-lookup"><span data-stu-id="39197-170">To run the Remote Connection Viewer at the command prompt</span></span>**

1.  <span data-ttu-id="39197-171">コマンドプロンプトで**DaRT リモート接続ビューアー**を実行するには、 **DartRemoteViewer.exe**コマンドを指定し、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="39197-171">To run the **DaRT Remote Connection Viewer** at the command prompt, specify the **DartRemoteViewer.exe** command and use the following parameters:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="39197-172">パラメーター</span><span class="sxs-lookup"><span data-stu-id="39197-172">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="39197-173">説明</span><span class="sxs-lookup"><span data-stu-id="39197-173">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="39197-174">-ticket = &lt; <em> ticketnumber</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="39197-174">-ticket=&lt;<em>ticketnumber</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="39197-175">ここで &lt; <em> </em> &gt; 、Ticketnumber は、リモート接続によって生成される、ダッシュを含むチケット番号です。</span><span class="sxs-lookup"><span data-stu-id="39197-175">Where &lt;<em>ticketnumber</em>&gt; is the ticket number, including the dashes, that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="39197-176">-ipaddress = &lt; <em> ipaddress</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="39197-176">-ipaddress=&lt;<em>ipaddress</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="39197-177">&lt; <em> Ipaddress </em> &gt; は、リモート接続によって生成される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="39197-177">Where &lt;<em>ipaddress</em>&gt; is the IP address that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="39197-178">-port = &lt; <em> port</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="39197-178">-port=&lt;<em>port</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="39197-179">&lt; <em> Port </em> &gt; は、指定された IP アドレスに対応するポートです。</span><span class="sxs-lookup"><span data-stu-id="39197-179">Where &lt;<em>port</em>&gt; is the port that corresponds to the specified IP address.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. <span data-ttu-id="39197-180">3つのパラメーターがすべて指定されていて、データが有効である場合は、プログラムが起動すると直ちに接続が試行されます。</span><span class="sxs-lookup"><span data-stu-id="39197-180">If all three parameters are specified and the data is valid, a connection is immediately tried when the program starts.</span></span> <span data-ttu-id="39197-181">いずれかのパラメーターが有効でない場合は、パラメーターが指定されていないかのようにプログラムが開始します。</span><span class="sxs-lookup"><span data-stu-id="39197-181">If any parameter is not valid, the program starts as if there were no parameters specified.</span></span>

## <span data-ttu-id="39197-182">関連トピック</span><span class="sxs-lookup"><span data-stu-id="39197-182">Related topics</span></span>


[<span data-ttu-id="39197-183">DaRT 10 の操作</span><span class="sxs-lookup"><span data-stu-id="39197-183">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

[<span data-ttu-id="39197-184">DaRT 10 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="39197-184">Recovering Computers Using DaRT 10</span></span>](recovering-computers-using-dart-10.md)









