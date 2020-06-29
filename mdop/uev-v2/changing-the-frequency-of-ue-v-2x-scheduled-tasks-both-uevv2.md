---
title: UE-V 2. x のスケジュールされたタスクの頻度の変更
description: UE-V 2. x のスケジュールされたタスクの頻度の変更
author: dansimp
ms.assetid: ee486570-c6cf-4fd9-ba48-0059ba877c10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/29/2016
ms.openlocfilehash: 1c1e3c091431dc56068dcd1fe0e849b0df1f6aa0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824427"
---
# <span data-ttu-id="8a8ed-103">UE-V 2. x のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="8a8ed-103">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>


<span data-ttu-id="8a8ed-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 Agent installer の AgentSetup.exe では、UE-V エージェントのインストール中に次のスケジュールされたタスクが作成されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 Agent installer, AgentSetup.exe, creates the following scheduled tasks during the UE-V Agent installation:</span></span>

-   **<span data-ttu-id="8a8ed-105">アプリケーションの設定を監視する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-105">Monitor Application Settings</span></span>**

-   **<span data-ttu-id="8a8ed-106">同期コントローラーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8a8ed-106">Sync Controller Application</span></span>**

-   **<span data-ttu-id="8a8ed-107">ログオフ時に設定を同期する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-107">Synchronize Settings at Logoff</span></span>**

-   **<span data-ttu-id="8a8ed-108">テンプレートの自動更新</span><span class="sxs-lookup"><span data-stu-id="8a8ed-108">Template Auto Update</span></span>**

-   **<span data-ttu-id="8a8ed-109">CEIP データを収集する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-109">Collect CEIP data</span></span>**

-   **<span data-ttu-id="8a8ed-110">CEIP データをアップロードする</span><span class="sxs-lookup"><span data-stu-id="8a8ed-110">Upload CEIP Data</span></span>**

<span data-ttu-id="8a8ed-111">**注** 収集した CEIP データを除き、UE-V は使用できないため、これらのタスクは有効のままにしておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-111">**Note** With the exception of Collect CEIP Data, these tasks must remain enabled as UE-V cannot function without them.</span></span>

 

<span data-ttu-id="8a8ed-112">これらのスケジュールされたタスクは、UE-V ツールで構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-112">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="8a8ed-113">これらのアイテムのスケジュールされたタスクを変更する管理者は、Schtasks.exe のコマンドラインオプションを使用するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-113">Administrators who want to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="8a8ed-114">Schtasks.exe の詳細については、「 [Schtasks、exe を使用して Windows Server 2003 でタスクをスケジュールする方法](https://go.microsoft.com/fwlink/?LinkID=264854)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-114">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

<span data-ttu-id="8a8ed-115">詳細情報</span><span class="sxs-lookup"><span data-stu-id="8a8ed-115">For more information about</span></span>

## <span data-ttu-id="8a8ed-116">UE-V のスケジュールされたタスク</span><span class="sxs-lookup"><span data-stu-id="8a8ed-116">UE-V Scheduled Tasks</span></span>


<span data-ttu-id="8a8ed-117">スケジュールされたタスクの設定コマンドを使用して、次のスケジュールされたタスクが UE-V 2 に含まれています。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-117">The following scheduled tasks are included in UE-V 2 with sample scheduled task configuration commands.</span></span>

### <span data-ttu-id="8a8ed-118">CEIP データを収集する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-118">Collect CEIP Data</span></span>

<span data-ttu-id="8a8ed-119">インストール時に、ユーザーまたは管理者によって、カスタマーエクスペリエンス向上プログラム (CEIP) に参加するようになります。 UE-V は、将来のリリースで製品の改善に役立つデータを収集します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-119">If upon installation the user or administrator choses to participate in the Customer Experience Improvement Program (CEIP), UE-V collects data to help improve the product in future releases.</span></span> <span data-ttu-id="8a8ed-120">このスケジュールされたタスクは、ログオン時にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-120">This scheduled task only runs at logon.</span></span> <span data-ttu-id="8a8ed-121">**CEIP データ収集**タスクは、ue-v agent のインストールディレクトリにある UevSqmSession.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-121">The **Collect CEIP Data** task runs the UevSqmSession.exe, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-122">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-122">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-123">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-123">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-124">\Microsoft\UE-V\Collect CEIP データ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-124">\Microsoft\UE-V\Collect CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-125">ログオン</span><span class="sxs-lookup"><span data-stu-id="8a8ed-125">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8a8ed-126">アプリケーションの設定を監視する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-126">Monitor Application Settings</span></span>

<span data-ttu-id="8a8ed-127">[**アプリケーション設定の監視**] タスクは、Windows アプリの設定を同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-127">The **Monitor Application Settings** task is used to synchronize settings for Windows apps.</span></span> <span data-ttu-id="8a8ed-128">ログオン時に実行されますが、ログオン detrimentally に影響しないため、30秒ほど遅延します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-128">It is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span> <span data-ttu-id="8a8ed-129">アプリケーションの状態の監視タスクは、UE-V Agent のインストールディレクトリにある UevAppMonitor.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-129">The Monitor Application Status task runs the UevAppMonitor.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-130">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-130">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-131">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-131">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-132">\Microsoft\UE-V\Monitor アプリケーションの状態</span><span class="sxs-lookup"><span data-stu-id="8a8ed-132">\Microsoft\UE-V\Monitor Application Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-133">ログオン</span><span class="sxs-lookup"><span data-stu-id="8a8ed-133">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8a8ed-134">同期コントローラーアプリケーション</span><span class="sxs-lookup"><span data-stu-id="8a8ed-134">Sync Controller Application</span></span>

<span data-ttu-id="8a8ed-135">**同期コントローラーアプリケーション**タスクを使って、設定をコンピューターから設定の保存場所に同期する同期コントローラーを開始します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-135">The **Sync Controller Application** task is used to start the Sync Controller to synchronize settings from the computer to the settings storage location.</span></span> <span data-ttu-id="8a8ed-136">既定では、タスクは30分ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-136">By default, the task runs every 30 minutes.</span></span> <span data-ttu-id="8a8ed-137">この時点では、ローカル設定が設定の保存場所に同期され、設定の保存場所の更新された設定がコンピューターに同期されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-137">At that time, local settings are synchronized to the settings storage location, and updated settings on the settings storage location are synchronized to the computer.</span></span> <span data-ttu-id="8a8ed-138">同期コントローラーアプリケーションは、UE-V Agent のインストールディレクトリにある Microsoft.Uev.SyncController.exe を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-138">The Sync Controller application runs the Microsoft.Uev.SyncController.exe, which is located in the UE-V Agent installation directory.</span></span>
<span data-ttu-id="8a8ed-139">**注:**[**アプリケーション設定の監視**] タスクでは、このタスクはログオン時に実行されますが、ログオン detrimentally に影響を与えないために30秒ほど遅延します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-139">**Note:** As per the **Monitor Application Settings** task, this task is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-140">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-140">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-141">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-141">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-142">\Microsoft\UE-V\Sync Controller アプリケーション</span><span class="sxs-lookup"><span data-stu-id="8a8ed-142">\Microsoft\UE-V\Sync Controller Application</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-143">ログオンとその後30分ごと</span><span class="sxs-lookup"><span data-stu-id="8a8ed-143">Logon, and every 30 minutes thereafter</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8a8ed-144">たとえば、次のコマンドは、既定の30分ではなく15分ごとに設定を同期するようにエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-144">For example, the following command configures the agent to synchronize settings every 15 minutes instead of the default 30 minutes.</span></span>

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### <span data-ttu-id="8a8ed-145">ログオフ時に設定を同期する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-145">Synchronize Settings at Logoff</span></span>

<span data-ttu-id="8a8ed-146">ログオフ時の**同期設定**は、ue-v のログオフ時のアプリケーションの同期を制御する、ログオン時にアプリケーションを起動するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-146">The **Synchronize Settings at Logoff** task is used to start an application at logon that controls the synchronization of applications at logoff for UE-V.</span></span> <span data-ttu-id="8a8ed-147">ログオフタスクで設定を同期すると、UE-V Agent のインストールディレクトリにある Microsoft.Uev.SyncController.exe ファイルが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-147">The Synchronize Settings at Logoff task runs the Microsoft.Uev.SyncController.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-148">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-148">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-149">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-149">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-150">\Microsoft\UE-V\Synchronize 設定のログオフ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-150">\Microsoft\UE-V\Synchronize Settings at Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-151">ログオン</span><span class="sxs-lookup"><span data-stu-id="8a8ed-151">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8a8ed-152">テンプレートの自動更新</span><span class="sxs-lookup"><span data-stu-id="8a8ed-152">Template Auto Update</span></span>

<span data-ttu-id="8a8ed-153">**テンプレートの自動更新**タスクは、新規作成、更新、または削除されたテンプレートの設定テンプレートカタログをチェックします。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-153">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="8a8ed-154">このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-154">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="8a8ed-155">**テンプレートの自動更新**タスクは、ue-v agent のインストールディレクトリにある ApplySettingsCatalog.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-155">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-156">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-156">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-157">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-157">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-158">\Microsoft\UE-V\Template の自動更新</span><span class="sxs-lookup"><span data-stu-id="8a8ed-158">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-159">システムの起動時と 3:30 AM (1 時間のウィンドウ内のランダムな時刻)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-159">System startup and at 3:30 AM every day, at a random time within a 1-hour window</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8a8ed-160">**例:** 次のコマンドは、UE-V Agent を構成して、設定テンプレートカタログストアを1時間おきに確認します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-160">**Example:** The following command configures the UE-V Agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### <span data-ttu-id="8a8ed-161">CEIP データをアップロードする</span><span class="sxs-lookup"><span data-stu-id="8a8ed-161">Upload CEIP Data</span></span>

<span data-ttu-id="8a8ed-162">ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加することを選択した場合、 **Ceip データのアップロード**タスクはインストール中に実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-162">The **Upload CEIP Data** task runs during the installation if the user or the administrator chose to participate in the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="8a8ed-163">このタスクにより、データが CEIP サーバーにアップロードされ、将来のリリースでの製品の改善に役立てることができます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-163">This task uploads the data to the CEIP servers where the data is used to help improve the product for future releases of UE-V.</span></span> <span data-ttu-id="8a8ed-164">このスケジュールされたタスクは、ログオン時と4時間おきに実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-164">This scheduled task runs at logon and every 4 hours afterwards.</span></span> <span data-ttu-id="8a8ed-165">**CEIP データのアップロード**タスクは、ue-v agent のインストールディレクトリにある UevSqmUploader.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-165">The **Upload CEIP data** task runs the UevSqmUploader.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8a8ed-166">タスク名</span><span class="sxs-lookup"><span data-stu-id="8a8ed-166">Task name</span></span></th>
<th align="left"><span data-ttu-id="8a8ed-167">既定のイベント</span><span class="sxs-lookup"><span data-stu-id="8a8ed-167">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8a8ed-168">\Microsoft\UE-V\Upload CEIP データ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-168">\Microsoft\UE-V\Upload CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-169">ログオン時と4時間ごと</span><span class="sxs-lookup"><span data-stu-id="8a8ed-169">At logon and every 4 hours</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8a8ed-170">UE-V 2 スケジュールされたタスクの詳細</span><span class="sxs-lookup"><span data-stu-id="8a8ed-170">UE-V 2 Scheduled Task Details</span></span>


<span data-ttu-id="8a8ed-171">次の表は、UE-V 2 のスケジュールされたタスクに関する追加情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-171">The following chart provides additional information about scheduled tasks for UE-V 2:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8a8ed-172">タスク名 </strong> (ファイル名)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-172">Task Name</strong> (file name)</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="8a8ed-173">既定の頻度</span><span class="sxs-lookup"><span data-stu-id="8a8ed-173">Default Frequency</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8a8ed-174">Power トグル</span><span class="sxs-lookup"><span data-stu-id="8a8ed-174">Power Toggle</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8a8ed-175">Idle のみ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-175">Idle Only</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8a8ed-176">ネットワーク接続</span><span class="sxs-lookup"><span data-stu-id="8a8ed-176">Network Connection</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8a8ed-177">説明</span><span class="sxs-lookup"><span data-stu-id="8a8ed-177">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8a8ed-178">アプリケーションの設定を監視する </strong> (UevAppMonitor.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-178">Monitor Application Settings</strong> (UevAppMonitor.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-179">ログオン後30秒で開始し、ログオフするまで続行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-179">Starts 30 seconds after logon and continues until logoff.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-180">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-181">あり</span><span class="sxs-lookup"><span data-stu-id="8a8ed-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-182">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-182">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-183">Windows (AppX) アプリの設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-183">Synchronizes settings for Windows (AppX) apps.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8a8ed-184">同期コントローラーアプリケーション </strong> (Microsoft.Uev.SyncController.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-184">Sync Controller Application</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-185">ログオン時と30分間隔。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-185">At logon and every 30 min thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-186">あり</span><span class="sxs-lookup"><span data-stu-id="8a8ed-186">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-187">要</span><span class="sxs-lookup"><span data-stu-id="8a8ed-187">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-188">ネットワークが接続されている場合のみ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-188">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-189">ローカル設定と設定の保存場所を同期する同期コントローラーを開始します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-189">Starts the Sync Controller which synchronizes local settings with the settings storage location.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8a8ed-190">ログオフ時に設定を同期する </strong> (Microsoft.Uev.SyncController.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-190">Synchronize Settings at Logoff</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-191">ログオン時に実行され、ログオフの間待機して設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-191">Runs at logon and then waits for Logoff to Synchronize settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-192">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-192">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-193">あり</span><span class="sxs-lookup"><span data-stu-id="8a8ed-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-194">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-194">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-195">ログオン時に、ログオフ時のアプリケーションの同期を制御するアプリケーションを起動します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-195">Start an application at logon that controls the synchronization of applications at logoff.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8a8ed-196">テンプレートの自動更新 </strong> (ApplySettingsCatalog.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-196">Template Auto Update</strong> (ApplySettingsCatalog.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-197">最初のログオン時と3:30 午前時に実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-197">Runs at initial logon and at 3:30 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-198">可</span><span class="sxs-lookup"><span data-stu-id="8a8ed-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-199">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-199">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-200">該当せず</span><span class="sxs-lookup"><span data-stu-id="8a8ed-200">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-201">新規、更新、または削除されたテンプレートの設定テンプレートカタログを確認します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-201">Checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="8a8ed-202">このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-202">This task only runs if SettingsTemplateCatalog is configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8a8ed-203">CEIP データの収集 </strong> (UevSqmSession.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-203">Collect CEIP data</strong> (UevSqmSession.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-204">ログオン時にサービスを起動する</span><span class="sxs-lookup"><span data-stu-id="8a8ed-204">At logon launches service</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-205">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-205">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-206">あり</span><span class="sxs-lookup"><span data-stu-id="8a8ed-206">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-207">該当せず</span><span class="sxs-lookup"><span data-stu-id="8a8ed-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-208">ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加した場合、このタスクでは、UE-V の将来のリリースを改善するために役立つデータが収集されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-208">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task collects data that helps improve UE-V future releases.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8a8ed-209">CEIP データをアップロードする </strong> (UevSqmUploader.exe)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-209">Upload CEIP Data</strong> (UevSqmUploader.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-210">ログオン時に実行され、その後は 4:00 AM に実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-210">Runs at logon and at 4:00 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-211">なし</span><span class="sxs-lookup"><span data-stu-id="8a8ed-211">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-212">あり</span><span class="sxs-lookup"><span data-stu-id="8a8ed-212">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-213">ネットワークが接続されている場合のみ</span><span class="sxs-lookup"><span data-stu-id="8a8ed-213">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="8a8ed-214">ユーザーまたは管理者がカスタマーエクスペリエンス向上プログラム (CEIP) に参加した場合、このタスクはデータを CEIP サーバーにアップロードします。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-214">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task uploads the data to the CEIP servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="8a8ed-215">伝説</span><span class="sxs-lookup"><span data-stu-id="8a8ed-215">Legend</span></span>**

-   <span data-ttu-id="8a8ed-216">**Power トグル**–タスクスケジューラは、AC 電源に接続されていないときに電力消費を最適化します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-216">**Power Toggle** – Task Scheduler will optimize power consumption when not connected to AC power.</span></span> <span data-ttu-id="8a8ed-217">コンピューターがバッテリ電源に切り替わった場合、タスクの実行が停止することがあります。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-217">The task might stop running if the computer switches to battery power.</span></span>

-   <span data-ttu-id="8a8ed-218">[**アイドルのみ**]-コンピューターがアイドル状態になっていない場合、タスクは実行を停止します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-218">**Idle Only** – The task will stop running if the computer ceases to be idle.</span></span> <span data-ttu-id="8a8ed-219">既定では、コンピューターがもう一度アイドル状態になると、タスクは再起動されません。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-219">By default the task will not restart when the computer is idle again.</span></span> <span data-ttu-id="8a8ed-220">代わりに、次のタスクトリガーでタスクが再び開始されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-220">Instead the task will begin again on the next task trigger.</span></span>

-   <span data-ttu-id="8a8ed-221">**ネットワーク接続**–コンピューターにネットワーク接続がある場合にのみ、"はい" とマークされたタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-221">**Network Connection** – Tasks marked “Yes” only run if the computer has a network connection available.</span></span> <span data-ttu-id="8a8ed-222">"N/A" とマークされたタスクは、ネットワーク接続に関係なく実行されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-222">Tasks marked “N/A” run regardless of network connectivity.</span></span>

### <span data-ttu-id="8a8ed-223">スケジュールされたタスクを管理する方法</span><span class="sxs-lookup"><span data-stu-id="8a8ed-223">How to Manage Scheduled Tasks</span></span>

<span data-ttu-id="8a8ed-224">スケジュールされたタスクを見つけるには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-224">To find Scheduled Tasks, perform the following:</span></span>

1.  <span data-ttu-id="8a8ed-225">ユーザーのコンピューターで、[タスクのスケジュール] を開きます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-225">Open “Schedule Tasks” on the user computer.</span></span>

2.  <span data-ttu-id="8a8ed-226">移動先: タスクスケジューラ- &gt; タスクスケジューラライブラリ- &gt; Microsoft- &gt; ue-v</span><span class="sxs-lookup"><span data-stu-id="8a8ed-226">Navigate to: Task Scheduler -&gt; Task Scheduler Library -&gt; Microsoft -&gt; UE-V</span></span>

3.  <span data-ttu-id="8a8ed-227">[詳細] ウィンドウで、管理して構成するスケジュールされたタスクを選びます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-227">Select the scheduled task you wish to manage and configure in the details pane.</span></span>

### <span data-ttu-id="8a8ed-228">追加情報</span><span class="sxs-lookup"><span data-stu-id="8a8ed-228">Additional information</span></span>

<span data-ttu-id="8a8ed-229">次の追加情報は、UE-V のスケジュールされたタスクに適用されます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-229">The following additional information applies to UE-V scheduled tasks:</span></span>

-   <span data-ttu-id="8a8ed-230">ll タスクシーケンスプログラムは、既定で UE-V Agent のインストールフォルダーにあり `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` ます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-230">ll task sequence programs are located in the UE-V Agent installation folder, `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\`, by default.</span></span>

-   <span data-ttu-id="8a8ed-231">同期コントローラーアプリケーションのスケジュールされたタスクは、UE-V SyncMethod が "Syncmethod" (UE-V 2 の既定の構成) に設定されている場合に、重要なコンポーネントです。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-231">The Sync Controller Application Scheduled task is the crucial component when the UE-V SyncMethod is set to “SyncProvider” (UE-V 2 default configuration).</span></span> <span data-ttu-id="8a8ed-232">このスケジュールされたタスクは、設定パッケージファイルのローカルにキャッシュされたバージョンとの SettingsSToragePath の同期を維持します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-232">This scheduled task keeps the SettingsSToragePath synchronized with the locally cached versions of the settings package files.</span></span> <span data-ttu-id="8a8ed-233">設定が十分な頻度で同期されないとユーザーから苦情があった場合、スケジュールされたタスクの設定を1分以内に減らすことができます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-233">If users complain that settings do not synchronize often enough, then you can reduce the scheduled task setting to as little as 1 minute.</span></span><span data-ttu-id="8a8ed-234">必要に応じて、30分の既定値をより高い金額に増やすこともできます。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-234"> You can also increase the 30 min default to a higher amount if necessary.</span></span> <span data-ttu-id="8a8ed-235">ログオン時に設定が十分な速度で同期されないという苦情がある場合は、スケジュールされたタスクの遅延設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-235">If users complain that settings do not synchronize fast enough on logon, then you can remove the delay setting for the scheduled task.</span></span> <span data-ttu-id="8a8ed-236">([**トリガーの編集**] ダイアログボックスで遅延設定を確認できます)</span><span class="sxs-lookup"><span data-stu-id="8a8ed-236">(You can find the delay setting in the **Edit Trigger** dialogue box)</span></span>

-   <span data-ttu-id="8a8ed-237">他の方法を使用してクライアントのテンプレートを同期しておく場合 (グループポリシーまたは Configuration Manager のベースラインなど)、別の方法でテンプレートの自動更新を無効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-237">You do not need to disable the Template Auto Update scheduled task if you use another method to keep the clients’ templates in sync (i.e. Group Policy or Configuration Manager Baselines).</span></span> <span data-ttu-id="8a8ed-238">SettingsTemplateCatalog プロパティ値を空のままにすると、UE-V はカスタムテンプレートの設定カタログを確認できなくなります。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-238">Leaving the SettingsTemplateCatalog property value blank prevents UE-V from checking the settings catalog for custom templates.</span></span> <span data-ttu-id="8a8ed-239">このスケジュールされたタスクは ApplySettingsCatalog.exe 実行され、実質的にすぐに戻ります。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-239">This scheduled task runs ApplySettingsCatalog.exe and will essentially return immediately.</span></span>

-   <span data-ttu-id="8a8ed-240">[アプリケーション設定の監視] スケジュールされたタスクは、各アプリに組み込まれている Windows アプリプログラムの設定トリガーに基づいて、リアルタイムで Windows アプリ (AppX) 設定を更新します。</span><span class="sxs-lookup"><span data-stu-id="8a8ed-240">The Monitor Application Settings scheduled task will update Windows app (AppX) settings in real time, based on Windows app program setting triggers built into each app.</span></span>






## <span data-ttu-id="8a8ed-241">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8a8ed-241">Related topics</span></span>


[<span data-ttu-id="8a8ed-242">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="8a8ed-242">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="8a8ed-243">カスタムアプリケーションの UE-V 2. x の展開</span><span class="sxs-lookup"><span data-stu-id="8a8ed-243">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





