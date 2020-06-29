---
title: UE-V 2.1 の新機能
description: UE-V 2.1 の新機能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826264"
---
# <span data-ttu-id="05427-103">UE-V 2.1 の新機能</span><span class="sxs-lookup"><span data-stu-id="05427-103">What's New in UE-V 2.1</span></span>


<span data-ttu-id="05427-104">ユーザーエクスペリエンスの仮想化2.1 には、UE-V 2.0 と比較して、これらの新機能が用意されています。</span><span class="sxs-lookup"><span data-stu-id="05427-104">User Experience Virtualization 2.1 provides these new features and functionality compared to UE-V 2.0.</span></span> <span data-ttu-id="05427-105">[Microsoft User Experience Virtualization (ue-v) 2.1 のリリースノート](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)には、ue-v 2.1 リリースに関する詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="05427-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md) provide more information about the UE-V 2.1 release.</span></span>

## <span data-ttu-id="05427-106">Office 2013 の設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="05427-106">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="05427-107">UE-V 2.1 には、Outlook 署名のサポートが強化された Microsoft Office 2013 の設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="05427-107">UE-V 2.1 includes the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="05427-108">UE-V 2.1 では、署名データはユーザーデバイス間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="05427-108">In UE-V 2.1, the signature data synchronizes between user devices.</span></span> <span data-ttu-id="05427-109">新規、返信、転送メールの既定の署名設定の同期が追加されました。</span><span class="sxs-lookup"><span data-stu-id="05427-109">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="05427-110">ユーザーは、既定の署名設定を選択する必要がなくなりました。</span><span class="sxs-lookup"><span data-stu-id="05427-110">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="05427-111">**注** ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="05427-111">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="05427-112">プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="05427-112">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="05427-113">以前の UE-V には、自動的に配布され、UE-V エージェントに登録された Microsoft Office 2010 設定場所テンプレートが含まれていました。</span><span class="sxs-lookup"><span data-stu-id="05427-113">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="05427-114">UE-V 2.1 は Office 365 と連携して、office 2013 の設定が Office 365 によってローミングされているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="05427-114">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="05427-115">設定が Office 365 によってローミングされている場合は、UE-V でローミングされません。</span><span class="sxs-lookup"><span data-stu-id="05427-115">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="05427-116">[Office 2013 のユーザーとローミングの設定の概要](https://go.microsoft.com/fwlink/p/?LinkID=391220)については、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="05427-116">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="05427-117">UE-V 2.1 を使用して設定の同期を有効にするには、次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="05427-117">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="05427-118">グループポリシーを使用して Office 365 の同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="05427-118">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="05427-119">Office 2013 のインストール中に Office 365 の同期操作を有効にしない</span><span class="sxs-lookup"><span data-stu-id="05427-119">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="05427-120">UE-V 2.1 は[、office 2013 と office 2010 のテンプレートを](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)同梱しています。</span><span class="sxs-lookup"><span data-stu-id="05427-120">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="05427-121">このリリースでは、Office 2007 テンプレートが削除されます。</span><span class="sxs-lookup"><span data-stu-id="05427-121">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="05427-122">ユーザーは、引き続き UE-V 2.0 以前の Office 2007 テンプレートを使うことができます。また、[ここ](https://go.microsoft.com/fwlink/p/?LinkID=246589)に記載されている ue-v テンプレートギャラリーからテンプレートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="05427-122">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>

## <span data-ttu-id="05427-123">分散ファイルシステムの名前空間ユーザーの修正</span><span class="sxs-lookup"><span data-stu-id="05427-123">Fix for Distributed File System Namespace Users</span></span>


<span data-ttu-id="05427-124">UE-V では、Syncproviderping が有効になっている UE-V 構成を追加することで、分散ファイルシステム名前空間 (DFSN) のサポートが強化されています。</span><span class="sxs-lookup"><span data-stu-id="05427-124">UE-V has improved Distributed File System Namespace (DFSN) support by adding a UE-V configuration called SyncProviderPingEnabled.</span></span> <span data-ttu-id="05427-125">PowerShell または WMI を使ってこの構成を無効にすると、ユーザーは UE-V ping を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="05427-125">Disabling this configuration using PowerShell or WMI allows users to disable the UE-V ping.</span></span> <span data-ttu-id="05427-126">DFSN サーバーを使用すると、これらのサーバーが ping に応答しないため、UE-V ping でエラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="05427-126">The UE-V ping causes an error when using DFSN servers because these servers do not respond to pings.</span></span> <span data-ttu-id="05427-127">応答不可は、UE-V が設定を同期しないようにします。</span><span class="sxs-lookup"><span data-stu-id="05427-127">The non-response prevents UE-V from synchronizing settings.</span></span> <span data-ttu-id="05427-128">UE-V による ping を無効にすると、UE-V の同期が正常に機能します。</span><span class="sxs-lookup"><span data-stu-id="05427-128">Disabling the UE-V ping allows UE-V synchronization to work normally.</span></span>

<span data-ttu-id="05427-129">UE-V ping を無効にするには、次の PowerShell コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="05427-129">To disable UE-V ping, use this PowerShell cmdlet:</span></span>

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## <span data-ttu-id="05427-130">資格情報の同期</span><span class="sxs-lookup"><span data-stu-id="05427-130">Synchronization for Credentials</span></span>


<span data-ttu-id="05427-131">UE-V 2.1 を使用すると、ユーザーは Windows Credential Manager に保存されている資格情報と証明書を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="05427-131">UE-V 2.1 gives customers the ability to synchronize credentials and certificates stored in the Windows Credential Manager.</span></span> <span data-ttu-id="05427-132">このコンポーネントは既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="05427-132">This component is disabled by default.</span></span> <span data-ttu-id="05427-133">このコンポーネントを有効にすると、ユーザーはドメインの資格情報と証明書を同期したままにすることができます。ユーザーはデバイスで1回サインインすることができます。これらの資格情報は、そのユーザーが UE-V 対応のすべてのデバイスでローミングします。</span><span class="sxs-lookup"><span data-stu-id="05427-133">Enabling this component lets users keep their domain credentials and certificates in sync. Users can sign in one time on a device, and these credentials will roam for that user across all of their UE-V enabled devices.</span></span> <span data-ttu-id="05427-134">[Ue-v 2.1 で資格情報を管理](https://technet.microsoft.com/library/dn458932.aspx#creds)する詳細情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="05427-134">[Manage Credentials with UE-V 2.1](https://technet.microsoft.com/library/dn458932.aspx#creds) provides more information.</span></span>

<span data-ttu-id="05427-135">**注** Windows 8 以降では、Credential Manager には web 資格情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05427-135">**Note** In Windows 8 and later, Credential Manager contains web credentials.</span></span> <span data-ttu-id="05427-136">これらの資格情報は、ユーザーのデバイス間で同期されません。</span><span class="sxs-lookup"><span data-stu-id="05427-136">These credentials are not synchronized between users’ devices.</span></span>

 

## <span data-ttu-id="05427-137">UE-V と Microsoft アカウントの同期</span><span class="sxs-lookup"><span data-stu-id="05427-137">UE-V and Microsoft Account Synchronization</span></span>


<span data-ttu-id="05427-138">UE-V は、Microsoft アカウントの同期とも呼ばれる、OneDrive との同期設定がオンになっているかどうかを検出します。</span><span class="sxs-lookup"><span data-stu-id="05427-138">UE-V detects if “Sync settings with OneDrive”, also known as Microsoft Account synchronization, is on.</span></span> <span data-ttu-id="05427-139">Microsoft アカウントが設定を同期するように構成されていない場合、UE-V は、Windows アプリ、AppX パッケージ、および Windows デスクトップのデバイス間の設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="05427-139">If the Microsoft Account is not configured to synchronize settings, UE-V synchronizes Windows apps, AppX packages, and Windows desktop settings between devices.</span></span> <span data-ttu-id="05427-140">これにより、ユーザーは、エンタープライズファイアウォールの外部との同期を行わずに、ストアアプリ、音楽、画像、その他の Microsoft アカウント対応アプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="05427-140">This lets users access their Store apps, music, pictures and other Microsoft Account-enabled applications without syncing outside of the enterprise firewall.</span></span> <span data-ttu-id="05427-141">UE-V は、グループポリシーが OneDrive との設定の同期を停止するかどうかを確認します。または、ユーザーがユーザーコントロールで**このコンピューターの設定の同期**を無効にしているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="05427-141">UE-V checks whether Group Policy will stop synchronizing settings with OneDrive or if the user disables **Sync your settings on this computer** in the user controls.</span></span>

## <span data-ttu-id="05427-142">外部の SyncMethod のサポート</span><span class="sxs-lookup"><span data-stu-id="05427-142">Support for the SyncMethod External</span></span>


<span data-ttu-id="05427-143">**外部**と呼ばれる新しい[syncmethod の構成](https://technet.microsoft.com/library/dn554321.aspx)では、ユーザーコンピューター上のローカルフォルダーに ue-v 設定が書き込まれる場合、任意の外部同期エンジン (OneDrive For business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="05427-143">A new [SyncMethod configuration](https://technet.microsoft.com/library/dn554321.aspx) called **External** specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

## <span data-ttu-id="05427-144">VDI モードのサポートの強化</span><span class="sxs-lookup"><span data-stu-id="05427-144">Enhanced Support for VDI Mode</span></span>


<span data-ttu-id="05427-145">UE-V 2.1 には、エンドユーザー間で共有される[VDI セッションのサポート](https://technet.microsoft.com/library/dn458932.aspx#vdi)が含まれています。</span><span class="sxs-lookup"><span data-stu-id="05427-145">UE-V 2.1 includes [support for VDI sessions](https://technet.microsoft.com/library/dn458932.aspx#vdi) that are shared among end users.</span></span> <span data-ttu-id="05427-146">管理者として、特殊な VDI テンプレートを登録して構成することができます。これにより、UE-V は永続的でない VDI セッションに対してすべての機能をそのまま維持できます。</span><span class="sxs-lookup"><span data-stu-id="05427-146">As an administrator, you can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

<span data-ttu-id="05427-147">**注** 非永続的な VDI セッションで VDI モードを有効にしていない場合、バックアップ/復元や LKG などの一部の機能は動作しません。</span><span class="sxs-lookup"><span data-stu-id="05427-147">**Note** If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as back-up/restore and LKG.</span></span>

 

## <span data-ttu-id="05427-148">管理のバックアップと復元</span><span class="sxs-lookup"><span data-stu-id="05427-148">Administrative Backup and Restore</span></span>


<span data-ttu-id="05427-149">Set-UevTemplateProfile PowerShell コマンドレットを使用して、**バックアップ**または**ローミング (既定)** プロファイルに設定場所テンプレートを配置することにより、ユーザーが新しいデバイスを採用したときに追加の設定を復元することができます。</span><span class="sxs-lookup"><span data-stu-id="05427-149">You can restore additional settings when a user adopts a new device by putting a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="05427-150">これにより、ユーザー設定に加えて、コンピューターの設定を新しいコンピューターと同期することができます。</span><span class="sxs-lookup"><span data-stu-id="05427-150">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="05427-151">バックアッププロファイルに割り当てられたテンプレートは、そのデバイスにバックアップされ、デバイスごとに構成されます。</span><span class="sxs-lookup"><span data-stu-id="05427-151">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="05427-152">[Ue-v で管理バックアップと復元を管理](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)する詳細については、「x」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="05427-152">[Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md) provides more information.</span></span>

## <span data-ttu-id="05427-153">追加の Windows 設定の同期</span><span class="sxs-lookup"><span data-stu-id="05427-153">Synchronization for Additional Windows Settings</span></span>


<span data-ttu-id="05427-154">UE-V は、タッチキーボードのパーソナライズとスペルチェック辞書を同期し、最近のアプリと画面の端の設定のアプリ切り替えを有効にして、Windows 8 と Windows 8.1 デバイスの間で同期します。</span><span class="sxs-lookup"><span data-stu-id="05427-154">UE-V now synchronizes touch keyboard personalization, the spelling dictionary, and enables the App Switching for recent apps and screen edge settings to synchronize between Windows 8 and Windows 8.1 devices.</span></span>






## <span data-ttu-id="05427-155">関連トピック</span><span class="sxs-lookup"><span data-stu-id="05427-155">Related topics</span></span>


[<span data-ttu-id="05427-156">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="05427-156">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="05427-157">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="05427-157">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="05427-158">Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="05427-158">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





