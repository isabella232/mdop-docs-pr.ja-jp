---
title: UE-V のスケジュールされたタスクの頻度の変更
description: UE-V のスケジュールされたタスクの頻度の変更
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822687"
---
# <span data-ttu-id="00a02-103">UE-V のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="00a02-103">Changing the Frequency of UE-V Scheduled Tasks</span></span>


<span data-ttu-id="00a02-104">Microsoft User Experience Virtualization (UE-V) Agent installer、AgentSetup.exe は、UE-V Agent のインストール中に2つのスケジュールされたタスクを作成します。</span><span class="sxs-lookup"><span data-stu-id="00a02-104">The Microsoft User Experience Virtualization (UE-V) Agent installer, AgentSetup.exe, creates two scheduled tasks during the UE-V Agent installation.</span></span> <span data-ttu-id="00a02-105">この2つのタスクは、**テンプレートの自動更新**タスクと、**保存場所の状態の設定**タスクの設定です。</span><span class="sxs-lookup"><span data-stu-id="00a02-105">The two tasks are the **Template Auto Update** task and the **Setting Storage Location Status** task.</span></span> <span data-ttu-id="00a02-106">これらのスケジュールされたタスクは、UE-V ツールで構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="00a02-106">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="00a02-107">これらのアイテムのスケジュールされたタスクを変更しようとしている管理者は、Schtasks.exe のコマンドラインオプションを使用するスクリプトを作成できます。</span><span class="sxs-lookup"><span data-stu-id="00a02-107">Administrators who wish to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="00a02-108">Schtasks.exe の詳細については、「 [Schtasks、exe を使用して Windows Server 2003 でタスクをスケジュールする方法](https://go.microsoft.com/fwlink/?LinkID=264854)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00a02-108">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

## <span data-ttu-id="00a02-109">テンプレートの自動更新</span><span class="sxs-lookup"><span data-stu-id="00a02-109">Template Auto-Update</span></span>


<span data-ttu-id="00a02-110">**テンプレートの自動更新**タスクは、新規作成、更新、または削除されたテンプレートの設定テンプレートカタログをチェックします。</span><span class="sxs-lookup"><span data-stu-id="00a02-110">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="00a02-111">このタスクは、SettingsTemplateCatalog が構成されている場合にのみ実行されます。</span><span class="sxs-lookup"><span data-stu-id="00a02-111">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="00a02-112">**テンプレートの自動更新**タスクは、ue-v agent のインストールディレクトリにある ApplySettingsCatalog.exe ファイルを実行します。</span><span class="sxs-lookup"><span data-stu-id="00a02-112">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent install directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="00a02-113">タスク名</span><span class="sxs-lookup"><span data-stu-id="00a02-113">Task name</span></span></th>
<th align="left"><span data-ttu-id="00a02-114">既定のトリガー</span><span class="sxs-lookup"><span data-stu-id="00a02-114">Default trigger</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="00a02-115">\Microsoft\UE-V\Template の自動更新</span><span class="sxs-lookup"><span data-stu-id="00a02-115">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="00a02-116">毎日 3:30 AM</span><span class="sxs-lookup"><span data-stu-id="00a02-116">3:30 AM every day</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="00a02-117">**例:** 次のコマンドは、設定テンプレートカタログストアを1時間おきに確認するようにエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="00a02-117">**Example:** The following command configures the agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## <span data-ttu-id="00a02-118">設定の保存場所の状態</span><span class="sxs-lookup"><span data-stu-id="00a02-118">Settings Storage Location Status</span></span>


<span data-ttu-id="00a02-119">**記憶域の場所の状態の設定**タスクは、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="00a02-119">The **Setting Storage Location Status** task performs the following actions:</span></span>

1.  <span data-ttu-id="00a02-120">UE-V フォルダーがオフラインファイル機能に固定されているか、登録されているかを確認します。</span><span class="sxs-lookup"><span data-stu-id="00a02-120">Checks to make sure the UE-V folders are still pinned or registered with the offline files feature.</span></span>

2.  <span data-ttu-id="00a02-121">設定の保存場所がオフラインかオンラインかを確認します。</span><span class="sxs-lookup"><span data-stu-id="00a02-121">Checks whether the settings storage location is offline or online.</span></span>

3.  <span data-ttu-id="00a02-122">オフラインファイルの既定の間隔ではなく、指定した間隔で強制的に同期を実行します。</span><span class="sxs-lookup"><span data-stu-id="00a02-122">Forces a synchronization on the specified interval instead of the default interval for offline files.</span></span>

4.  <span data-ttu-id="00a02-123">事前に取得されるように構成されている設定パッケージを同期します。</span><span class="sxs-lookup"><span data-stu-id="00a02-123">Synchronizes any settings packages that are configured to be pre-fetched.</span></span>

5.  <span data-ttu-id="00a02-124">Active Directory のホームディレクトリのパスが変更されたかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="00a02-124">Checks if the Active Directory home directory path has changed.</span></span>

6.  <span data-ttu-id="00a02-125">次の場所に現在の設定の記憶域構成を書き込みます</span><span class="sxs-lookup"><span data-stu-id="00a02-125">Writes the current settings storage configuration under the following location</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="00a02-126">タスク名</span><span class="sxs-lookup"><span data-stu-id="00a02-126">Task name</span></span></th>
    <th align="left"><span data-ttu-id="00a02-127">既定のトリガー</span><span class="sxs-lookup"><span data-stu-id="00a02-127">Default trigger</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00a02-128">\Microsoft\UE-V\Settings の保存場所の状態</span><span class="sxs-lookup"><span data-stu-id="00a02-128">\Microsoft\UE-V\Settings Storage Location Status</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00a02-129">任意のユーザーのログオン時–トリガー後は、30分間隔で何度も繰り返すことができます。</span><span class="sxs-lookup"><span data-stu-id="00a02-129">At logon of any user – After triggered, repeat every 30 minutes indefinitely.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="00a02-130">**例:** 次のコマンドは、1時間ごとに操作を実行するようにエージェントを構成します。</span><span class="sxs-lookup"><span data-stu-id="00a02-130">**Example:** The following command configures the agent to run the action above every hour.</span></span>

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## <span data-ttu-id="00a02-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="00a02-131">Related topics</span></span>


[<span data-ttu-id="00a02-132">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="00a02-132">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="00a02-133">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="00a02-133">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





