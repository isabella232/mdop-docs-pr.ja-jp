---
title: UE-V 2. x で管理バックアップと復元を管理する
description: UE-V 2. x で管理バックアップと復元を管理する
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827387"
---
# <span data-ttu-id="6cf5f-103">UE-V 2. x で管理バックアップと復元を管理する</span><span class="sxs-lookup"><span data-stu-id="6cf5f-103">Manage Administrative Backup and Restore in UE-V 2.x</span></span>


<span data-ttu-id="6cf5f-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、または 2.1 SP1 の管理者は、アプリケーションと Windows の設定を元の状態に戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-104">As an administrator of Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you can restore application and Windows settings to their original state.</span></span> <span data-ttu-id="6cf5f-105">さらに、UE-V 2.1 では、ユーザーが新しいデバイスを採用したときに追加設定を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-105">And new in UE-V 2.1, you can also restore additional settings when a user adopts a new device.</span></span>

## <span data-ttu-id="6cf5f-106">ユーザーが新しいデバイスを採用したときに、UE-V 2.1 または UE-V 2.1 SP1 の設定を復元する</span><span class="sxs-lookup"><span data-stu-id="6cf5f-106">Restore Settings in UE-V 2.1 or UE-V 2.1 SP1 when a User Adopts a New Device</span></span>


<span data-ttu-id="6cf5f-107">ユーザーが新しいデバイスを採用したときに設定を復元するには、Set-UevTemplateProfile PowerShell コマンドレットを使用して、設定場所テンプレートを**バックアップ**または**ローミング (既定)** プロファイルに配置できます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-107">To restore settings when a user adopts a new device, you can put a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="6cf5f-108">これにより、ユーザー設定に加えて、コンピューターの設定を新しいコンピューターと同期することができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-108">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="6cf5f-109">バックアッププロファイルに割り当てられたテンプレートは、そのデバイスにバックアップされ、デバイスごとに構成されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-109">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="6cf5f-110">テンプレートのバックアップ設定を行うには、Windows PowerShell で次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-110">To backup settings for a template, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   <span data-ttu-id="6cf5f-111">&lt;TemplateID &gt; は Ue-v テンプレート ID です</span><span class="sxs-lookup"><span data-stu-id="6cf5f-111">&lt;TemplateID&gt; is the UE-V Template ID</span></span>

-   <span data-ttu-id="6cf5f-112">&lt;バックアップ &gt; はバックアップまたはローミングのいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-112">&lt;backup&gt; can either be Backup or Roaming</span></span>

<span data-ttu-id="6cf5f-113">ユーザーのドメイン、ユーザー名、およびデバイス名がすべて一致する場合、ユーザーのデバイスの UE-V を置き換えると、設定が自動的に復元されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-113">When replacing a user’s device UE-V automatically restores settings if the user’s domain, username, and device name all match.</span></span> <span data-ttu-id="6cf5f-114">すべての同期データとバックアップデータは、デバイス上で自動的に復元されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-114">All synchronized and any backup data is restored on the device automatically.</span></span>

<span data-ttu-id="6cf5f-115">新しい PowerShell コマンドレットの Restore-UevBackup を使用して、別のデバイスから設定を復元することもできます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-115">You can also use the new PowerShell cmdlet, Restore-UevBackup, to restore settings from a different device.</span></span> <span data-ttu-id="6cf5f-116">新しいデバイスの設定パッケージを複製するには、Windows PowerShell の次のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-116">To clone the settings packages for the new device, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Restore-UevBackup –Machine <MachineName>
```

<span data-ttu-id="6cf5f-117">ここで、 &lt; MachineName &gt; はデバイスのコンピューター名です。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-117">where &lt;MachineName&gt; is the computer name of the device.</span></span>

<span data-ttu-id="6cf5f-118">多くのアプリケーションが含まれている Office 2013 テンプレートなどのテンプレートは、すべて、ローミング (既定) またはバックアップされたプロファイルに含めることができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-118">Templates such as the Office 2013 template that include many applications can either all be included in the roamed (default) or backed up profile.</span></span> <span data-ttu-id="6cf5f-119">テンプレートスイート内の個々のアプリは、グループに従います。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-119">Individual apps in a template suite follow the group.</span></span> <span data-ttu-id="6cf5f-120">Office 2013 の in box テンプレートには、ローミングとバックアップのみの設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-120">Office 2013 in-box templates include both roaming and backup-only settings.</span></span> <span data-ttu-id="6cf5f-121">ローミングプロファイルにバックアップ専用の設定を含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-121">Backup-only settings cannot be included in a roaming profile.</span></span>

<span data-ttu-id="6cf5f-122">バックアップ/復元機能の一部として、UE-V は、[設定] にロールバックするためのオプション**に追加されました。**</span><span class="sxs-lookup"><span data-stu-id="6cf5f-122">As part of the Backup/Restore feature, UE-V added **last known good (LKG)** to the options for rolling back to settings.</span></span> <span data-ttu-id="6cf5f-123">このリリースでは、元の設定または LKG 設定のいずれかにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-123">In this release, you can roll back to either the original settings or LKG settings.</span></span> <span data-ttu-id="6cf5f-124">LKG 設定を使用すると、ユーザーは設定の事前の中間状態に進んで安定したポイントにロールバックすることができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-124">The LKG settings let users roll back to an intermediate and stable point ahead of the pre-UE-V state of the settings.</span></span>

### <span data-ttu-id="6cf5f-125">UE-V を使用してテンプレートをバックアップ/復元する方法</span><span class="sxs-lookup"><span data-stu-id="6cf5f-125">How to Backup/Restore Templates with UE-V</span></span>

<span data-ttu-id="6cf5f-126">以下は、UE-V の主要なバックアップと復元の構成要素です。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-126">These are the key backup and restore components of UE-V:</span></span>

-   <span data-ttu-id="6cf5f-127">テンプレートプロファイル</span><span class="sxs-lookup"><span data-stu-id="6cf5f-127">Template profiles</span></span>

-   <span data-ttu-id="6cf5f-128">設定の記憶域の場所テンプレート内の設定パッケージの場所</span><span class="sxs-lookup"><span data-stu-id="6cf5f-128">Settings packages location within the Settings Storage Location template</span></span>

-   <span data-ttu-id="6cf5f-129">バックアップトリガー</span><span class="sxs-lookup"><span data-stu-id="6cf5f-129">Backup trigger</span></span>

-   <span data-ttu-id="6cf5f-130">設定の復元方法</span><span class="sxs-lookup"><span data-stu-id="6cf5f-130">How settings are restored</span></span>

**<span data-ttu-id="6cf5f-131">テンプレートプロファイル</span><span class="sxs-lookup"><span data-stu-id="6cf5f-131">Template Profiles</span></span>**

<span data-ttu-id="6cf5f-132">UE-V のテンプレートプロファイルは、テンプレートがデバイスに登録されたとき、または PowerShell/WMI 構成ユーティリティを使用して登録をポストしたときに定義されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-132">A UE-V template profile is defined when the template is registered on the device or post registration through the PowerShell/WMI configuration utility.</span></span> <span data-ttu-id="6cf5f-133">プロファイルの種類には、次のものがあります。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-133">The profile types include:</span></span>

-   <span data-ttu-id="6cf5f-134">ローミング (既定)</span><span class="sxs-lookup"><span data-stu-id="6cf5f-134">Roaming (default)</span></span>

-   <span data-ttu-id="6cf5f-135">バックアップ</span><span class="sxs-lookup"><span data-stu-id="6cf5f-135">Backup</span></span>

-   <span data-ttu-id="6cf5f-136">BackupOnly</span><span class="sxs-lookup"><span data-stu-id="6cf5f-136">BackupOnly</span></span>

<span data-ttu-id="6cf5f-137">他の指定がない限り、登録時にすべてのテンプレートがローミングプロファイルに含まれます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-137">All templates are included in the roaming profile when registered unless otherwise specified.</span></span> <span data-ttu-id="6cf5f-138">これらのテンプレートは、対応するテンプレートが有効になっているすべての UE-V 対応デバイスに設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-138">These templates synchronize settings to all UE-V enabled devices with the corresponding template enabled.</span></span>

<span data-ttu-id="6cf5f-139">Set-UevTemplateProfile コマンドレットを使用して、PowerShell または WMI でバックアッププロファイルにテンプレートを追加することができます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-139">Templates can be added to the Backup Profile with PowerShell or WMI using the Set-UevTemplateProfile cmdlet.</span></span> <span data-ttu-id="6cf5f-140">バックアッププロファイルのテンプレートは、これらの設定を、特別なデバイス名ディレクトリの設定の保存場所にバックアップします。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-140">Templates in the Backup Profile back up these settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="6cf5f-141">指定した設定は、この場所にバックアップされます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-141">Specified settings are backed up to this location.</span></span>

<span data-ttu-id="6cf5f-142">テンプレート指定のバックアップには、明示的に復元しない限り、同期しないデバイス固有の設定のみが含まれます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-142">Templates designated BackupOnly include settings specific to that device that should not be synchronized unless explicitly restored.</span></span> <span data-ttu-id="6cf5f-143">これらの設定は、Backedup 設定として、設定の保存場所のデバイス固有の設定パッケージの同じ場所に格納されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-143">These settings are stored in the same device-specific settings package location on the settings storage location as the Backedup Settings.</span></span> <span data-ttu-id="6cf5f-144">これらのテンプレートには、テンプレートに埋め込まれた特別な識別子があり、このプロファイルの一部として指定します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-144">These templates have a special identifier embedded in the template that specifies they should be part of this profile.</span></span>

**<span data-ttu-id="6cf5f-145">設定の記憶域の場所テンプレート内の設定パッケージの場所</span><span class="sxs-lookup"><span data-stu-id="6cf5f-145">Settings packages location within the Settings Storage Location template</span></span>**

<span data-ttu-id="6cf5f-146">ローミングプロファイル設定は、設定の保存場所に保存されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-146">Roaming Profile settings are stored on the settings storage location.</span></span> <span data-ttu-id="6cf5f-147">バックアップまたは BackupOnly プロファイルに割り当てられたテンプレートは、特別なデバイス名ディレクトリの設定の保存場所に設定を保存します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-147">Templates assigned to the Backup or the BackupOnly profile store their settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="6cf5f-148">これらのプロファイルのテンプレートを持つ各デバイスには、独自のデバイス名があります。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-148">Each device with templates in these profiles has its own device name.</span></span> <span data-ttu-id="6cf5f-149">UE-V はこれらのディレクトリをクリーンアップしません。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-149">UE-V does not clean up these directories.</span></span>

**<span data-ttu-id="6cf5f-150">バックアップトリガー</span><span class="sxs-lookup"><span data-stu-id="6cf5f-150">Backup trigger</span></span>**

<span data-ttu-id="6cf5f-151">Backup は、UE-V 同期をトリガーする同じイベントによってトリガーされます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-151">Backup is triggered by the same events that trigger a UE-V synchronization.</span></span>

**<span data-ttu-id="6cf5f-152">設定の復元方法</span><span class="sxs-lookup"><span data-stu-id="6cf5f-152">How settings are restored</span></span>**

<span data-ttu-id="6cf5f-153">ユーザーのデバイスを復元すると、現在登録されているテンプレートの設定が、別のデバイスのバックアップフォルダーと、すべての同期された設定から現在のコンピューターに復元されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-153">Restoring a user’s device restores the currently registered Template’s settings from another device’s backup folder and all synchronized settings to the current machine.</span></span> <span data-ttu-id="6cf5f-154">設定は次の2つの方法で復元されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-154">Settings are restored in these two ways:</span></span>

-   **<span data-ttu-id="6cf5f-155">自動復元</span><span class="sxs-lookup"><span data-stu-id="6cf5f-155">Automatic restore</span></span>**

    <span data-ttu-id="6cf5f-156">ユーザーの UE-V 設定の記憶域のパス、ドメイン、コンピューター名が現在のユーザーと一致する場合は、そのユーザーのすべての設定が同期され、最新の設定のみが適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-156">If the user’s UE-V settings storage path, domain, and Computer name match the current user then all of the settings for that user are synchronized, with only the latest settings applied.</span></span> <span data-ttu-id="6cf5f-157">ユーザーが初めて新しいデバイスにログオンしたときに、これらの条件が満たされた場合、設定データがそのデバイスに適用されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-157">If a user logs on to a new device for the first time and these criteria are met, the settings data is applied to that device.</span></span>

    **<span data-ttu-id="6cf5f-158">注</span><span class="sxs-lookup"><span data-stu-id="6cf5f-158">Note</span></span>**  
    <span data-ttu-id="6cf5f-159">アクセシビリティと Windows デスクトップの設定では、ユーザーが Windows に再ログオンして適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-159">Accessibility and Windows Desktop settings require the user to re-logon to Windows to be applied.</span></span>



-   **<span data-ttu-id="6cf5f-160">手動復元</span><span class="sxs-lookup"><span data-stu-id="6cf5f-160">Manual Restore</span></span>**

    <span data-ttu-id="6cf5f-161">更新中にデバイスを復元してユーザーを支援したい場合は、Restore-UevBackup コマンドレットを使用することを選択できます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-161">If you want to assist users by restoring a device during a refresh, you can choose to use the Restore-UevBackup cmdlet.</span></span> <span data-ttu-id="6cf5f-162">このコマンドを実行すると、設定の保存場所からユーザーの設定がダウンロードされます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-162">This command causes the user’s settings to be downloaded from the Settings Storage Location.</span></span>

## <span data-ttu-id="6cf5f-163">アプリケーションと Windows の設定を元の状態に復元する</span><span class="sxs-lookup"><span data-stu-id="6cf5f-163">Restore Application and Windows Settings to Original State</span></span>


<span data-ttu-id="6cf5f-164">WMI コマンドと Windows PowerShell コマンドを使用すると、アプリケーションと Windows の設定を、UE-V Agent をインストールした後に初めてアプリケーションを起動したときにコンピューター上の設定値に復元できます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-164">WMI and Windows PowerShell commands let you restore application and Windows settings to the settings values that were on the computer the first time that the application started after the UE-V Agent was installed.</span></span> <span data-ttu-id="6cf5f-165">この復元アクションは、アプリケーションごとまたは Windows の設定ごとに実行されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-165">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="6cf5f-166">設定は、次にアプリケーションを実行するときに復元されます。または、ユーザーがオペレーティングシステムにログオンしたときに設定が復元されます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-166">The settings are restored the next time that the application runs, or the settings are restored when the user logs on to the operating system.</span></span>

**<span data-ttu-id="6cf5f-167">Windows PowerShell for UE-V でアプリケーション設定と Windows 設定を復元するには</span><span class="sxs-lookup"><span data-stu-id="6cf5f-167">To restore application settings and Windows settings with Windows PowerShell for UE-V 2.x</span></span>**

1.  <span data-ttu-id="6cf5f-168">Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-168">Open the Windows PowerShell window.</span></span>

2.  <span data-ttu-id="6cf5f-169">次の Windows PowerShell コマンドレットを入力して、アプリケーションの設定と Windows の設定を復元します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-169">Enter the following Windows PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="6cf5f-170">Windows PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="6cf5f-170">Windows PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="6cf5f-171">説明</span><span class="sxs-lookup"><span data-stu-id="6cf5f-171">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="6cf5f-172">アプリケーションのユーザー設定を復元するか、Windows の設定のグループを復元します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-172">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="6cf5f-173">WMI を使用してアプリケーション設定と Windows 設定を復元するには</span><span class="sxs-lookup"><span data-stu-id="6cf5f-173">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="6cf5f-174">Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-174">Open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="6cf5f-175">次の WMI コマンドを入力して、アプリケーションの設定と Windows の設定を復元します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-175">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="6cf5f-176">WMI コマンド</span><span class="sxs-lookup"><span data-stu-id="6cf5f-176">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="6cf5f-177">説明</span><span class="sxs-lookup"><span data-stu-id="6cf5f-177">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="6cf5f-178">アプリケーションのユーザー設定を復元するか、Windows の設定のグループを復元します。</span><span class="sxs-lookup"><span data-stu-id="6cf5f-178">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## <span data-ttu-id="6cf5f-179">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6cf5f-179">Related topics</span></span>


[<span data-ttu-id="6cf5f-180">Windows PowerShell と WMI を使用した UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="6cf5f-180">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="6cf5f-181">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="6cf5f-181">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









