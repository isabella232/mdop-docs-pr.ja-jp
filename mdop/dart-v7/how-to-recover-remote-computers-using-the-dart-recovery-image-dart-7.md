---
title: DaRT の回復イメージを使用してリモート コンピューターを回復する方法
description: DaRT の回復イメージを使用してリモート コンピューターを回復する方法
author: dansimp
ms.assetid: 66bc45fb-dc40-4d47-b583-5bb1ff5c97a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 885ab1d1cf8f51dc4fd4613e41a20a2525ea7d6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822794"
---
# <span data-ttu-id="ee433-103">DaRT の回復イメージを使用してリモート コンピューターを回復する方法</span><span class="sxs-lookup"><span data-stu-id="ee433-103">How to Recover Remote Computers Using the DaRT Recovery Image</span></span>


<span data-ttu-id="ee433-104">Microsoft 診断/回復ツールセット (DaRT) 7 のリモート接続機能により、IT 管理者は、エンドユーザーのコンピューターで DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ee433-104">The Remote Connection feature in Microsoft Diagnostics and Recovery Toolset (DaRT) 7 lets an IT administrator run the DaRT tools remotely on an end-user computer.</span></span> <span data-ttu-id="ee433-105">エンドユーザー (またはエンドユーザーのコンピューターでのヘルプデスクプロフェッショナル) によって特定の情報が提供されると、IT 管理者またはヘルプデスクエージェントは、エンドユーザーのコンピューターを制御し、必要な DaRT ツールをリモートで実行することができます。</span><span class="sxs-lookup"><span data-stu-id="ee433-105">After certain information is provided by the end user (or by a helpdesk professional working on the end-user computer), the IT administrator or helpdesk agent can take control of the end user's computer and run the necessary DaRT tools remotely.</span></span>

**<span data-ttu-id="ee433-106">重要</span><span class="sxs-lookup"><span data-stu-id="ee433-106">Important</span></span>**  
<span data-ttu-id="ee433-107">リモート接続を確立する2台のコンピューターは、同じネットワークの一部である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee433-107">The two computers establishing a remote connection must be part of the same network.</span></span>



**<span data-ttu-id="ee433-108">DaRT を使用してリモートコンピューターを回復するには</span><span class="sxs-lookup"><span data-stu-id="ee433-108">To recover a remote computer by using DaRT</span></span>**

1.  <span data-ttu-id="ee433-109">DaRT 回復イメージを使用して、エンドユーザーのコンピューターを起動します。</span><span class="sxs-lookup"><span data-stu-id="ee433-109">Boot an end-user computer by using the DaRT recovery image.</span></span>

    <span data-ttu-id="ee433-110">通常、次のいずれかの方法を使用して、dart の回復イメージの展開方法に応じて DaRT を起動し、リモートコンピューターを回復します。</span><span class="sxs-lookup"><span data-stu-id="ee433-110">You will typically use one of the following methods to boot into DaRT to recover a remote computer, depending on how you deploy the DaRT recovery image.</span></span> <span data-ttu-id="ee433-111">DaRT リカバリ画像の展開について詳しくは、「 [dart 7.0 リカバリイメージの展開](deploying-the-dart-70-recovery-image-dart-7.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ee433-111">For more information about deploying the DaRT recovery image, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

    -   <span data-ttu-id="ee433-112">問題のあるコンピューターの回復パーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="ee433-112">Boot into DaRT from a recovery partition on the problem computer.</span></span>

    -   <span data-ttu-id="ee433-113">ネットワーク上のリモートパーティションから DaRT に起動します。</span><span class="sxs-lookup"><span data-stu-id="ee433-113">Boot into DaRT from a remote partition on the network.</span></span>

    <span data-ttu-id="ee433-114">各方法の長所と短所については、「 [DaRT 7.0 回復イメージの保存と展開の計画](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee433-114">For information about the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 7.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-70-recovery-image.md).</span></span>

    <span data-ttu-id="ee433-115">DaRT を起動するために使用する方法にかかわらず、エンドユーザーが使用できるようにするブートオプションについては、BIOS でブートデバイスを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee433-115">Whichever method that you use to boot into DaRT, you must enable the boot device in the BIOS for the boot option or options that you want to make available to the end user.</span></span>

    **<span data-ttu-id="ee433-116">注</span><span class="sxs-lookup"><span data-stu-id="ee433-116">Note</span></span>**  
    <span data-ttu-id="ee433-117">BIOS の構成は、ハードディスクドライブの種類、ネットワークアダプター、および組織で使用されているその他のハードウェアに応じて固有です。</span><span class="sxs-lookup"><span data-stu-id="ee433-117">Configuring the BIOS is unique, depending on the kind of hard disk drive, network adapters, and other hardware that is used in your organization.</span></span>



2.  <span data-ttu-id="ee433-118">コンピュータが DaRT リカバリイメージとして起動すると、 **Netstart**ダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-118">As the computer is booting into the DaRT recovery image, the **NetStart** dialog box appears.</span></span> <span data-ttu-id="ee433-119">ネットワークサービスを初期化するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-119">You are asked whether you want to initialize network services.</span></span> <span data-ttu-id="ee433-120">[**はい**] をクリックすると、ネットワークに DHCP サーバーが存在し、サーバーから IP アドレスを取得しようとしたと見なされます。</span><span class="sxs-lookup"><span data-stu-id="ee433-120">If you click **Yes**, it is assumed that a DHCP server is present on the network and an attempt is made to obtain an IP address from the server.</span></span> <span data-ttu-id="ee433-121">ネットワークで DHCP の代わりに静的 IP アドレスを使用している場合は、後で DaRT の**Tcp/ip 構成**ツールを使って静的 ip アドレスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="ee433-121">If the network uses static IP addresses instead of DHCP, you can later use the **TCP/IP Configuration** tool in DaRT to specify a static IP address.</span></span>

    <span data-ttu-id="ee433-122">ネットワーク初期化プロセスをスキップするには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee433-122">To skip the network initialization process, click **No**.</span></span>

3.  <span data-ttu-id="ee433-123">[ネットワークの初期化] ダイアログボックスで、ドライブ文字を再マップするかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-123">Following the network initialization dialog box, you are asked whether you want to remap the drive letters.</span></span> <span data-ttu-id="ee433-124">Windows online を実行すると、通常、システムボリュームは C ドライブにマップされます。ただし、WinRE で Windows オフラインを実行すると、元のシステムボリュームが別のドライブにマップされている可能性があります。これによって混乱が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee433-124">When you run Windows online, the system volume is typically mapped to drive C. However, when you run Windows offline under WinRE, the original system volume might be mapped to another drive, and this can cause confusion.</span></span> <span data-ttu-id="ee433-125">再マッピングする場合、DaRT はオンラインのドライブ文字と一致するように、オフラインのドライブ文字をマッピングしようとします。</span><span class="sxs-lookup"><span data-stu-id="ee433-125">If you decide to remap, DaRT tries to map the offline drive letters to match the online drive letters.</span></span> <span data-ttu-id="ee433-126">再マッピングは、起動プロセスでオフラインのオペレーティングシステムが選択されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-126">Remapping is performed only if an offline operating system is selected later in the startup process.</span></span>

4.  <span data-ttu-id="ee433-127">[再マッピング] ダイアログボックスで、[**システム回復オプション**] ダイアログボックスが表示され、キーボードレイアウトを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ee433-127">Following the remapping dialog box, a **System Recovery Options** dialog box appears and asks you to select a keyboard layout.</span></span> <span data-ttu-id="ee433-128">次に、システムルートディレクトリ、インストールされているオペレーティングシステムの種類、パーティションサイズが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-128">Then it displays the system root directory, the kind of operating system installed, and the partition size.</span></span> <span data-ttu-id="ee433-129">使用しているオペレーティングシステムが表示されず、ドライバーが見つからないことが原因で問題が発生している可能性がある場合は、[**ドライバーの読み込み**] をクリックして問題のあるドライバーを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="ee433-129">If you do not see your operating system listed, and suspect that the lack of drivers is a possible cause of the failure, click **Load Drivers** to load the suspect drivers.</span></span> <span data-ttu-id="ee433-130">デバイスのインストールメディアを挿入して、ドライバーを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ee433-130">This prompts you to insert the installation media for the device and to select the driver.</span></span> <span data-ttu-id="ee433-131">修復または診断するインストールを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee433-131">Select the installation that you want to repair or diagnose, and then click **Next**.</span></span>

    **<span data-ttu-id="ee433-132">注</span><span class="sxs-lookup"><span data-stu-id="ee433-132">Note</span></span>**  
    <span data-ttu-id="ee433-133">Windows 回復環境 (WinRE) で、前回の試用時に Windows 7 が正常に起動しなかったことが検出された場合は、**スタートアップ修復**が自動的に開始されることがあります。</span><span class="sxs-lookup"><span data-stu-id="ee433-133">If the Windows Recovery Environment (WinRE) detects or suspects that Windows 7 did not start correctly the last time that it was tried, **Startup Repair** might start to run automatically.</span></span> <span data-ttu-id="ee433-134">この問題を解決する方法などの状況については、「 [DaRT 7.0 のトラブルシューティング](troubleshooting-dart-70-new-ia.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee433-134">For information about this situation including how to resolve it, see [Troubleshooting DaRT 7.0](troubleshooting-dart-70-new-ia.md).</span></span>



~~~
If any of the registry hives are corrupted or missing, Registry Editor, and several other DaRT utilities, will have limited functionality. If no operating system is selected, some tools will not be available.

The **System Recovery Options** window appears and lists various recovery tools.
~~~

5. <span data-ttu-id="ee433-135">[**システム回復オプション**] ウィンドウで、[ **Microsoft 診断/回復ツールセット**] を選択し、[**診断/回復ツールセット**] ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee433-135">On the **System Recovery Options** window, select **Microsoft Diagnostics and Recovery Toolset** to open the **Diagnostics and Recovery Toolset** window.</span></span>

6. <span data-ttu-id="ee433-136">[**診断/回復ツールセット**] ウィンドウで、[**リモート接続**] をクリックして**DaRT リモート接続**ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="ee433-136">On the **Diagnostics and Recovery Toolset** window, click **Remote Connection** to open the **DaRT Remote Connection** window.</span></span> <span data-ttu-id="ee433-137">ヘルプデスクのリモートアクセスの指定を求められたら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee433-137">If you are prompted to give the help desk remote access, click **OK**.</span></span>

   <span data-ttu-id="ee433-138">DaRT リモート接続ウィンドウが開き、チケット番号、IP アドレス、ポート情報が表示されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-138">The DaRT Remote Connection window opens and displays a ticket number, IP address, and port information.</span></span>

7. <span data-ttu-id="ee433-139">ヘルプデスクエージェントのコンピューターで、 **DaRT リモート接続ビューアー**を開きます。</span><span class="sxs-lookup"><span data-stu-id="ee433-139">On the helpdesk agent computer, open the **DaRT Remote Connection Viewer**.</span></span>

   <span data-ttu-id="ee433-140">[**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Dart 7**]、[ **dart リモート接続ビューアー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee433-140">Click **Start**, click **All Programs**, click **Microsoft DaRT 7**, and then click **DaRT Remote Connection Viewer**.</span></span>

8. <span data-ttu-id="ee433-141">**DaRT リモート接続**ウィンドウで、必要なチケット、IP アドレス、ポート情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="ee433-141">In the **DaRT Remote Connection** window, enter the required ticket, IP address, and port information.</span></span>

   **<span data-ttu-id="ee433-142">注</span><span class="sxs-lookup"><span data-stu-id="ee433-142">Note</span></span>**  
   <span data-ttu-id="ee433-143">この情報は、エンドユーザーのコンピューター上に作成され、エンドユーザーによって提供される必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee433-143">This information is created on the end-user computer and must be provided by the end user.</span></span> <span data-ttu-id="ee433-144">エンドユーザーコンピューターで利用可能な IP アドレスの数に応じて、複数の IP アドレスを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="ee433-144">There might be multiple IP addresses to choose from, depending on how many are available on the end-user computer.</span></span>



9. <span data-ttu-id="ee433-145">**[接続]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ee433-145">Click **Connect**.</span></span>

<span data-ttu-id="ee433-146">IT 管理者は、エンドユーザーのコンピューターの制御を前提としており、DaRT ツールをリモートで実行できます。</span><span class="sxs-lookup"><span data-stu-id="ee433-146">The IT administrator now assumes control of the end-user computer and can run the DaRT tools remotely.</span></span>

**<span data-ttu-id="ee433-147">注</span><span class="sxs-lookup"><span data-stu-id="ee433-147">Note</span></span>**  
<span data-ttu-id="ee433-148">inv32.xml という名前のファイルが用意されており、ポート番号や IP アドレスなどのリモート接続情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ee433-148">A file is provided that is named inv32.xml and contains remote connection information, such as the port number and IP address.</span></span> <span data-ttu-id="ee433-149">既定では、ファイルは%windir%\\system32. にあります。</span><span class="sxs-lookup"><span data-stu-id="ee433-149">By default, the file is typically located at %windir%\\system32.</span></span>



**<span data-ttu-id="ee433-150">リモート接続プロセスをカスタマイズするには</span><span class="sxs-lookup"><span data-stu-id="ee433-150">To customize the Remote Connection process</span></span>**

1. <span data-ttu-id="ee433-151">winpeshl.ini ファイルを編集することで、リモート接続プロセスをカスタマイズできます。</span><span class="sxs-lookup"><span data-stu-id="ee433-151">You can customize the Remote Connection process by editing the winpeshl.ini file.</span></span> <span data-ttu-id="ee433-152">winpeshl.ini ファイルを編集する方法の詳細については、「 [Winpeshl.ini ファイル](https://go.microsoft.com/fwlink/?LinkId=219413)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ee433-152">For more information about how to edit the winpeshl.ini file, see [Winpeshl.ini Files](https://go.microsoft.com/fwlink/?LinkId=219413).</span></span>

   <span data-ttu-id="ee433-153">次のコマンドとパラメーターを指定して、エンドユーザーのコンピューターとのリモート接続の確立方法をカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="ee433-153">Specify the following commands and parameters to customize how a remote connection is established with an end-user computer:</span></span>

   <table>
   <colgroup>
   <col width="33%" />
   <col width="33%" />
   <col width="33%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="ee433-154">コマンド</span><span class="sxs-lookup"><span data-stu-id="ee433-154">Command</span></span></th>
   <th align="left"><span data-ttu-id="ee433-155">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee433-155">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="ee433-156">説明</span><span class="sxs-lookup"><span data-stu-id="ee433-156">Description</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="ee433-157">RemoteRecovery.exe</span><span class="sxs-lookup"><span data-stu-id="ee433-157">RemoteRecovery.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ee433-158">-nomessage</span><span class="sxs-lookup"><span data-stu-id="ee433-158">-nomessage</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ee433-159">確認メッセージが表示されないように指定します。</span><span class="sxs-lookup"><span data-stu-id="ee433-159">Specifies that the confirmation prompt is not displayed.</span></span> <strong><span data-ttu-id="ee433-160">リモート接続は </strong> 、エンドユーザーによって &quot; [はい] が確認プロンプトに応答した場合と同じように継続さ &quot; れます。</span><span class="sxs-lookup"><span data-stu-id="ee433-160">Remote Connection</strong> continues just as if the end user had responded &quot;Yes&quot; to the confirmation prompt.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="ee433-161">WaitForConnection.exe</span><span class="sxs-lookup"><span data-stu-id="ee433-161">WaitForConnection.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="ee433-162">なし</span><span class="sxs-lookup"><span data-stu-id="ee433-162">none</span></span></p></td>
   <td align="left"><p><span data-ttu-id="ee433-163"><strong>リモート接続が実行されて </strong> いないか、エンドユーザーのコンピューターとの接続が確立されるまで、カスタムスクリプトが続行されないようにします。</span><span class="sxs-lookup"><span data-stu-id="ee433-163">Prevents a custom script from continuing until either <strong>Remote Connection</strong> is not running or a valid connection is established with the end-user computer.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="ee433-164">重要</span><span class="sxs-lookup"><span data-stu-id="ee433-164">Important</span></span></strong><br/><p><span data-ttu-id="ee433-165">このコマンドは、個別に指定されている場合は関数を提供しません。</span><span class="sxs-lookup"><span data-stu-id="ee433-165">This command serves no function if it is specified independently.</span></span> <span data-ttu-id="ee433-166">正しく機能するためには、スクリプトで指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ee433-166">It must be specified in a script to function correctly.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="ee433-167">DaRT を起動しようとするとすぐに**リモート接続**ツールを開くようにカスタマイズされた winpeshl.ini ファイルの例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="ee433-167">The following is an example of a winpeshl.ini file that is customized to open the **Remote Connection** tool as soon as an attempt is made to boot into DaRT:</span></span>

   ```ini
   [LaunchApps]
   "%windir%\system32\netstart.exe -network -remount"
   "cmd /C start %windir%\system32\RemoteRecovery.exe -nomessage"
   "%windir%\system32\WaitForConnection.exe"
   "%SYSTEMDRIVE%\sources\recovery\recenv.exe"
   ```

**<span data-ttu-id="ee433-168">コマンドプロンプトでリモート接続ビューアーを実行するには</span><span class="sxs-lookup"><span data-stu-id="ee433-168">To run the Remote Connection Viewer at the command prompt</span></span>**

1.  <span data-ttu-id="ee433-169">コマンドプロンプトで**DaRT リモート接続ビューアー**を実行するには、 **DartRemoteViewer.exe**コマンドを指定し、次のパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="ee433-169">You can run the **DaRT Remote Connection Viewer** at the command prompt by specifying the **DartRemoteViewer.exe** command and by using the following parameters:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="ee433-170">パラメーター</span><span class="sxs-lookup"><span data-stu-id="ee433-170">Parameter</span></span></th>
    <th align="left"><span data-ttu-id="ee433-171">説明</span><span class="sxs-lookup"><span data-stu-id="ee433-171">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ee433-172">-ticket = &lt; <em> ticketnumber</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="ee433-172">-ticket=&lt;<em>ticketnumber</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ee433-173">ここで &lt; <em> </em> &gt; 、Ticketnumber は、リモート接続によって生成される、ダッシュを含むチケット番号です。</span><span class="sxs-lookup"><span data-stu-id="ee433-173">Where &lt;<em>ticketnumber</em>&gt; is the ticket number, including the dashes, that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ee433-174">-ipaddress = &lt; <em> ipaddress</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="ee433-174">-ipaddress=&lt;<em>ipaddress</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ee433-175">&lt; <em> Ipaddress </em> &gt; は、リモート接続によって生成される IP アドレスです。</span><span class="sxs-lookup"><span data-stu-id="ee433-175">Where &lt;<em>ipaddress</em>&gt; is the IP address that is generated by Remote Connection.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ee433-176">-port = &lt; <em> port</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="ee433-176">-port=&lt;<em>port</em>&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ee433-177">&lt; <em> Port </em> &gt; は、指定された IP アドレスに対応するポートです。</span><span class="sxs-lookup"><span data-stu-id="ee433-177">Where &lt;<em>port</em>&gt; is the port that corresponds to the specified IP address.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
The variables for these parameters are created on the end-user computer and must be provided by the end user.
~~~



2. <span data-ttu-id="ee433-178">3つのパラメーターがすべて指定されていて、データが有効である場合は、プログラムが起動すると直ちに接続が試行されます。</span><span class="sxs-lookup"><span data-stu-id="ee433-178">If all three parameters are specified and the data is valid, a connection is immediately tried when the program starts.</span></span> <span data-ttu-id="ee433-179">いずれかのパラメーターが有効でない場合は、パラメーターが指定されていないかのようにプログラムが開始します。</span><span class="sxs-lookup"><span data-stu-id="ee433-179">If any parameter is not valid, the program starts as if there were no parameters specified.</span></span>

## <span data-ttu-id="ee433-180">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ee433-180">Related topics</span></span>


[<span data-ttu-id="ee433-181">DaRT 7.0 を使用したコンピューターの回復</span><span class="sxs-lookup"><span data-stu-id="ee433-181">Recovering Computers Using DaRT 7.0</span></span>](recovering-computers-using-dart-70-dart-7.md)









