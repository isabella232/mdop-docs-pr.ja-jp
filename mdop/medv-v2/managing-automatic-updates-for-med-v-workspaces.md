---
title: MED-V ワークスペースの自動更新の管理
description: MED-V ワークスペースの自動更新の管理
author: dansimp
ms.assetid: 306f28a2-d653-480d-b737-4b8b3132de5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b22d3250db806e740c1d62da4fed98d5956b0eeb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825294"
---
# <span data-ttu-id="8002f-103">MED-V ワークスペースの自動更新の管理</span><span class="sxs-lookup"><span data-stu-id="8002f-103">Managing Automatic Updates for MED-V Workspaces</span></span>


<span data-ttu-id="8002f-104">MED-V ワークスペースは、個別のオペレーティングシステムを含む仮想マシンであり、自動ソフトウェア更新プロセスは、企業の物理コンピューターと同じように管理する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-104">The MED-V workspace is a virtual machine that contains a separate operating system, whose automatic software update process must be managed just like the physical computers in your enterprise.</span></span> <span data-ttu-id="8002f-105">ゲストオペレーティングシステムは、ホストのオペレーティングシステムが実行されているときに必ずしも実行されるとは限りません。そのため、必要に応じてゲストオペレーティングシステムにソフトウェアの更新プログラムを適用できるように、MED-V 仮想マシンが構成されていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-105">Because the guest operating system is not always necessarily running when the host operating system is running, you must ensure that the MED-V virtual machine is configured in such a way that software updates can be applied to the guest operating system as required.</span></span> <span data-ttu-id="8002f-106">Microsoft Enterprise Desktop Virtualization (MED) 2.0 ソリューションには、MED-V ワークスペースでの自動ソフトウェア更新プログラムの処理方法を決定できる機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="8002f-106">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution provides the functionality that lets you determine how automatic software updates are processed in a MED-V workspace.</span></span>

## <span data-ttu-id="8002f-107">MED-V ワークスペースのウェイクアップポリシーを管理する</span><span class="sxs-lookup"><span data-stu-id="8002f-107">Managing MED-V Workspace Wake-Up Policy</span></span>


<span data-ttu-id="8002f-108">MED-V workspace ウェークアップポリシーは、med-v 仮想マシンが、MED-V 構成設定で指定した時間の間、更新が利用できるようにすることを保証します。</span><span class="sxs-lookup"><span data-stu-id="8002f-108">The MED-V workspace wake-up policy guarantees that the MED-V virtual machine is made available for updates for the time that you specify in your MED-V configuration settings.</span></span> <span data-ttu-id="8002f-109">これは、microsoft から公開された更新プログラムや更新プログラム、および Microsoft 以外のソリューション (ウイルス対策アプリケーションなど) によって展開および管理される更新プログラムに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-109">This applies to both updates that are published from Microsoft through Windows Update and updates deployed and controlled by non-Microsoft solutions, such as antivirus applications.</span></span>

<span data-ttu-id="8002f-110">**重要** MED-V ワークスペースのウェイクアップポリシーは、Microsoft Update インフラストラクチャに最適化されています。</span><span class="sxs-lookup"><span data-stu-id="8002f-110">**Important** The MED-V workspace wake-up policy is optimized for the Microsoft Update infrastructure.</span></span> <span data-ttu-id="8002f-111">Microsoft System Center Configuration Manager を使用して Microsoft 以外の更新プログラムを展開している場合は、System Center Updates Publisher も使用することをお勧めします。これにより、Microsoft Update と同じインフラストラクチャを活用します。そのため、MED-V ワークスペースのウェイクアップポリシーを利用すると便利です。</span><span class="sxs-lookup"><span data-stu-id="8002f-111">If you are using Microsoft System Center Configuration Manager to deploy non-Microsoft updates, we recommend that you also use the System Center Updates Publisher, which takes advantage of the same infrastructure as Microsoft Update and therefore benefits from the MED-V workspace wake-up policy.</span></span> <span data-ttu-id="8002f-112">詳細については、「 [System Center Updates Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=200035) 。</span><span class="sxs-lookup"><span data-stu-id="8002f-112">For more information, see [System Center Updates Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) (https://go.microsoft.com/fwlink/?LinkId=200035).</span></span>

 

<span data-ttu-id="8002f-113">MED-V ワークスペースパッケージを作成した場合、エンドユーザーがログオンするタイミングと開始方法 (**ファストスタート**)、またはエンドユーザーが公開されたアプリケーション (**正常起動時**) を最初に開くときに構成します。</span><span class="sxs-lookup"><span data-stu-id="8002f-113">When you created your MED-V workspace package, you configured when and how it starts, either when the end user logs on (**Fast Start**) or when the end user first opens a published application (**Normal Start**).</span></span> <span data-ttu-id="8002f-114">または、エンドユーザーがこの設定を制御できるようにオプションを設定します。</span><span class="sxs-lookup"><span data-stu-id="8002f-114">Or you set the option to let the end user control this setting.</span></span>

<span data-ttu-id="8002f-115">どちらの場合も、**ファストスタート**オプションが選択されているときは、med-v ホストがユーザーとしてログオンしている限り、仮想マシンの実行が続行されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-115">Either way, whenever the **Fast Start** option is selected, the virtual machine continues to run as long as the MED-V host is logged on as User.</span></span> <span data-ttu-id="8002f-116">この構成では、ホストがアクティブなときに MED-V がアクティブになるため、MED-V からの追加の処理を必要とせずに、自動更新が適用されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-116">In this configuration, because MED-V is active when the host is active, automatic updates are applied without requiring any extra processing from MED-V.</span></span>

<span data-ttu-id="8002f-117">ただし、**ファストスタート**が指定されていない場合、または仮想マシンの休止状態または停止時に、med-v が定期的に使用されていない場合でも、ゲストオペレーティングシステムが定期的に更新されている、med-v ワークスペースのウェイクアップポリシーを通じて、med-v が保証されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-117">However, for those cases in which **Fast Start** is not specified or the virtual machine hibernates or stops, MED-V guarantees through its MED-V workspace wake-up policy that the guest operating system is being regularly updated even when MED-V is not used regularly.</span></span> <span data-ttu-id="8002f-118">MED-V は、指定した構成設定に基づいて仮想マシンを定期的にスリープ状態にして、この機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="8002f-118">MED-V performs this function by regularly waking up the virtual machine based on the configuration settings that you specify.</span></span> <span data-ttu-id="8002f-119">これにより、仮想マシンの自動更新クライアントが、その構成に基づいて実行されるようになります。</span><span class="sxs-lookup"><span data-stu-id="8002f-119">This enables the automatic update clients in the virtual machine to execute based on their configurations.</span></span><span data-ttu-id="8002f-120">MED-V 構成設定で定義された期間が経過すると、MED-V は仮想マシンを前の状態に戻します。</span><span class="sxs-lookup"><span data-stu-id="8002f-120">After the time period defined by the MED-V configuration setting elapses, MED-V returns the virtual machine to its previous state.</span></span>

<span data-ttu-id="8002f-121">**注** エンドユーザーが更新期間中に公開されたアプリケーションを開くと、必要な更新プログラムが適用されますが、MED-V は更新期間が終了した後に自動的に休止されたり、シャットダウンされたりすることはありません。</span><span class="sxs-lookup"><span data-stu-id="8002f-121">**Note** If the end user opens a published application during the update period, the required updates are applied, but MED-V is not automatically hibernated or shut down after the update period ends.</span></span> <span data-ttu-id="8002f-122">代わりに、MED-V は実行され続けます。</span><span class="sxs-lookup"><span data-stu-id="8002f-122">Instead, MED-V continues running.</span></span>

 

<span data-ttu-id="8002f-123">MED-V ワークスペースのウェイクアップポリシーには、3つの主なコンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="8002f-123">The MED-V workspace wake-up policy includes three main components:</span></span>

**<span data-ttu-id="8002f-124">ゲスト更新マネージャー</span><span class="sxs-lookup"><span data-stu-id="8002f-124">Guest Update Manager</span></span>**

<span data-ttu-id="8002f-125">MED-V ホストに常駐している場合は、スタンドアロンの実行可能プログラムによって、事前定義されたスケジュールに従って仮想マシンを起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-125">Residing on the MED-V host, this stand-alone executable program is responsible for waking up the virtual machine according to a predefined, configurable schedule.</span></span> <span data-ttu-id="8002f-126">更新プログラムマネージャーによる仮想マシンのアクティブな実行時間、更新プログラムの適用を許可するために仮想マシンをスリープ状態にする時間 (分) を指定する構成設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="8002f-126">Specify the configuration settings to indicate at what time the update manager should wake up the virtual machine every day, and how long the virtual machine should be kept awake (in minutes) to allow for updates to be applied.</span></span> <span data-ttu-id="8002f-127">指定した分数が経過すると、ゲスト更新マネージャーによって仮想マシンが休止状態になり、次の使用のために準備されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-127">After the number of minutes specified has been reached, the guest update manager puts the virtual machine into hibernation, prepared for the next use.</span></span> <span data-ttu-id="8002f-128">Windows タスクマネージャーを使って、この実行可能プログラムの実行をスケジュールできます。</span><span class="sxs-lookup"><span data-stu-id="8002f-128">You can schedule the execution of this executable program through the Windows Task Manager.</span></span>

**<span data-ttu-id="8002f-129">ゲストの再起動管理サービス</span><span class="sxs-lookup"><span data-stu-id="8002f-129">Guest Restart Management Service</span></span>**

<span data-ttu-id="8002f-130">MED-V ホストに常駐している場合、このサービスには3つの主な責任があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-130">Residing on the MED-V host, this service has three primary responsibilities.</span></span> <span data-ttu-id="8002f-131">ゲスト更新マネージャーと共に、必要に応じて、ユーザーログオン時に仮想マシンの再起動を管理します。</span><span class="sxs-lookup"><span data-stu-id="8002f-131">Along with the Guest Update Manager, it manages the restart of the virtual machine at user logon, if it is required.</span></span> <span data-ttu-id="8002f-132">更新プログラムがインストールされているために、仮想マシンの再起動が必要になることが検出されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-132">It detects when virtual machine restarts are required caused by updates being installed.</span></span> <span data-ttu-id="8002f-133">また、ゲスト更新マネージャーのタスクは、常に構成に従ってスケジュールされます。</span><span class="sxs-lookup"><span data-stu-id="8002f-133">And it ensures that the task for the Guest Update Manager is always scheduled according to configuration.</span></span>

**<span data-ttu-id="8002f-134">ゲスト更新サービス</span><span class="sxs-lookup"><span data-stu-id="8002f-134">Guest Update Service</span></span>**

<span data-ttu-id="8002f-135">MED-V 仮想マシン上に存在する場合、この Windows サービスは、インストールされている更新プログラムの再起動が必要な場合に監視する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-135">Residing on the MED-V virtual machine, this Windows service has the responsibility of monitoring when installed updates require a restart.</span></span> <span data-ttu-id="8002f-136">サービスが再起動の必要性を認識すると、ホストでゲストの再起動管理サービスに通知されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-136">After the service becomes aware of the need for a restart, it notifies the guest restart management service on the host.</span></span>

### <span data-ttu-id="8002f-137">MED-V Workspace ウェイクアップポリシーの構成設定</span><span class="sxs-lookup"><span data-stu-id="8002f-137">Configuration Settings for MED-V Workspace Wake-Up Policy</span></span>

<span data-ttu-id="8002f-138">仮想マシンで自動更新を受信するタイミングと時間を制御するには、レジストリで次の2つの構成値を定義します。</span><span class="sxs-lookup"><span data-stu-id="8002f-138">You control when and for how long the virtual machine awakens to receive automatic updates by defining the following two configuration values in the registry.</span></span> <span data-ttu-id="8002f-139">これらの値はどちらも、HKLM\\Software\\Microsoft\\MEDV\\v2\\VM キーの下にあります。</span><span class="sxs-lookup"><span data-stu-id="8002f-139">Both of these values are located under the HKLM\\Software\\Microsoft\\MEDV\\v2\\VM key.</span></span>

<span data-ttu-id="8002f-140">**Guestupdatetime** – MED が24時間制の標準に基づいて更新のために仮想マシンをウェイクアップするときの時間と分を構成します。</span><span class="sxs-lookup"><span data-stu-id="8002f-140">**GuestUpdateTime** – Configures the hour and minute each day when MED-V must wake up the virtual machine for updating, based on the 24-hour clock standard.</span></span> <span data-ttu-id="8002f-141">HH: MM の形式で時刻を指定します。</span><span class="sxs-lookup"><span data-stu-id="8002f-141">Specify the time in the format HH:MM.</span></span> <span data-ttu-id="8002f-142">既定値は、00:00 (深夜) です。</span><span class="sxs-lookup"><span data-stu-id="8002f-142">The default value is 00:00 (midnight).</span></span>

<span data-ttu-id="8002f-143">**Guestupdateduration** – med-v が仮想マシンの更新を開始するまでの時間を分単位で構成します。これは、Guestupdateduration 構成の設定で指定された時間になります。</span><span class="sxs-lookup"><span data-stu-id="8002f-143">**GuestUpdateDuration** – Configures the number of minutes that MED-V must keep the virtual machine awake for updating, starting at the time specified in the GuestUpdateTime configuration setting.</span></span> <span data-ttu-id="8002f-144">既定値は 240 (4 時間) です。</span><span class="sxs-lookup"><span data-stu-id="8002f-144">The default value is 240 (4 hours).</span></span> <span data-ttu-id="8002f-145">この値をゼロ (0) に設定すると、MED-V workspace ウェイクアップポリシーが無効になります。</span><span class="sxs-lookup"><span data-stu-id="8002f-145">Setting this value to zero (0) disables the MED-V workspace wake-up policy.</span></span>

<span data-ttu-id="8002f-146">MED-V 構成値の定義方法の詳細については、「 [Med-v ワークスペース構成設定を管理](managing-med-v-workspace-configuration-settings.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8002f-146">For more information about how to define your MED-V configuration values, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="8002f-147">**注** MED-V のベストプラクティスは、MED-V 仮想マシンが定期的に更新される予定の時刻に合わせて、スリープ状態を設定することです。</span><span class="sxs-lookup"><span data-stu-id="8002f-147">**Note** A MED-V best practice is to set your wake up interval to match the time when MED-V virtual machines are planned to be updated regularly.</span></span> <span data-ttu-id="8002f-148">また、これらの設定は、ホストコンピューターの動作に似た構成にすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8002f-148">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

 

### <span data-ttu-id="8002f-149">ESD システムを使った再起動通知</span><span class="sxs-lookup"><span data-stu-id="8002f-149">Reboot Notification Using your ESD System</span></span>

<span data-ttu-id="8002f-150">自動更新が適用された後に、MED-V ワークスペースの再起動が必要になるたびに、MED-V に通知するように ESD システムを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="8002f-150">You can configure your ESD system to notify MED-V whenever a restart is required for the MED-V workspace after automatic updates have been applied.</span></span> <span data-ttu-id="8002f-151">再起動が必要であることがわかっている ESD システムで自動更新を適用する場合は、MED-V ワークスペースで次のグローバルイベントを通知するスクリプトを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-151">When you apply automatic updates through your ESD system that you know require a restart, you should write a script to signal the following global event on the MED-V workspace:</span></span>

<span data-ttu-id="8002f-152">**重要** [変更] 権限を持つイベントを開き、シグナルを送る必要があります。</span><span class="sxs-lookup"><span data-stu-id="8002f-152">**Important** You must open the event with Modify Only rights and then signal it.</span></span> <span data-ttu-id="8002f-153">適切な権限を持っていない場合は、正常に動作しません。</span><span class="sxs-lookup"><span data-stu-id="8002f-153">If you do not open it with the correct permissions, it does not work.</span></span>

 

``` syntax
/// <summary>
/// The guest is required to be restarted due to an ESD update.
/// </summary>
public const string MedvGuestRebootRequiredEventName = @"Global\MedvGuestRebootRequiredEvent";
using (EventWaitHandle notificationEvent = 
EventWaitHandle.OpenExisting(eventName, EventWaitHandleRights.Modify))
{
notificationEvent.Set();
}
```

<span data-ttu-id="8002f-154">このイベントを通知すると、MED-V がキャプチャされ、再起動が必要であることが仮想マシンに通知されます。</span><span class="sxs-lookup"><span data-stu-id="8002f-154">When you signal this event, MED-V captures it and informs the virtual machine that a restart is required.</span></span>

## <span data-ttu-id="8002f-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8002f-155">Related topics</span></span>


[<span data-ttu-id="8002f-156">MED-V ワークスペースのソフトウェア更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="8002f-156">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

 

 





