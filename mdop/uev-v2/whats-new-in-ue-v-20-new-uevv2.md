---
title: UE-V 2.0 の新機能
description: UE-V 2.0 の新機能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824964"
---
# <span data-ttu-id="f0466-103">UE-V 2.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="f0466-103">What's New in UE-V 2.0</span></span>


<span data-ttu-id="f0466-104">Microsoft User Experience Virtualization (UE-V) 2.0 では、UE-V 1.0 と比べてこれらの新機能が提供されます。</span><span class="sxs-lookup"><span data-stu-id="f0466-104">Microsoft User Experience Virtualization (UE-V) 2.0 provides these new features and functionality compared to UE-V 1.0.</span></span> <span data-ttu-id="f0466-105">[Microsoft User Experience Virtualization (ue-v) 2.0 のリリースノート](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)には、ue-v 2.0 リリースに関する詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="f0466-105">The [Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md) provide more information about the UE-V 2.0 release.</span></span>

## <span data-ttu-id="f0466-106">クライアント側キャッシュ (CSC) は不要になりました</span><span class="sxs-lookup"><span data-stu-id="f0466-106">Client-side cache (CSC) no longer required</span></span>


<span data-ttu-id="f0466-107">このバージョンの UE-V は、**同期プロバイダー**を紹介しています。これにより、Windows のオフラインファイル機能の要件が、クライアント側の設定のキャッシュをサポートするように置き換えられます。</span><span class="sxs-lookup"><span data-stu-id="f0466-107">This version of UE-V introduces the **sync provider**, which replaces the requirement for the Windows Offline Files feature to support a client-side cache of settings.</span></span>

<span data-ttu-id="f0466-108">UE-V は、アプリケーションを開いたり閉じたりしたとき、または Windows がロックまたはロック解除されたとき、またはログオンまたはログオフしたときにのみ設定を同期するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="f0466-108">Whereas UE-V used to synchronize settings only when an application opened, closed, or when Windows locked or unlocked, or at logon or logoff, the sync provider also …</span></span>

-   <span data-ttu-id="f0466-109">"**Trigger events**" を使用してローカルアプリケーションと Windows の設定をアウトバンドで同期します。</span><span class="sxs-lookup"><span data-stu-id="f0466-109">Synchronizes local application and Windows settings out-of-band using "**trigger events**"</span></span>

-   <span data-ttu-id="f0466-110">スケジュールされた**タスク**を使用して、エンタープライズ要件に合わせて選んだ任意の間隔 (既定では30分ごと) に設定のストレージパッケージを同期します。</span><span class="sxs-lookup"><span data-stu-id="f0466-110">Uses a **scheduled task** to sync the settings storage package in any interval you choose for your enterprise requirements (every 30 minutes by default)</span></span>

<span data-ttu-id="f0466-111">特定の条件を使うと、同期の頻度が高くなります。</span><span class="sxs-lookup"><span data-stu-id="f0466-111">Certain conditions provide more frequent synchronization.</span></span>

-   <span data-ttu-id="f0466-112">ユーザーが新しい会社設定センターアプリケーションで [**今すぐ同期**] ボタンをクリックすると、設定が同期されます。</span><span class="sxs-lookup"><span data-stu-id="f0466-112">Settings synchronize when the user clicks the **Sync Now** button in the new Company Settings Center application.</span></span>

-   <span data-ttu-id="f0466-113">同期プロバイダーは、スケジュールされた同期タスクを待つことなく、1つのアプリケーションで開始することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0466-113">The sync provider can also start for a single application without waiting for the scheduled synchronization task.</span></span> <span data-ttu-id="f0466-114">たとえば、アプリケーションが閉じている場合、設定の変更はローカルキャッシュに書き込まれ、同期プロバイダープロセスは非同期的に実行され、新しい設定の変更は設定の保存場所に移動されます。</span><span class="sxs-lookup"><span data-stu-id="f0466-114">For example, when an application is closed, any settings changes are written to the local cache, and the sync provider process runs asynchronously to move those new settings changes to the settings storage location.</span></span>

## <span data-ttu-id="f0466-115">Windows アプリの同期</span><span class="sxs-lookup"><span data-stu-id="f0466-115">Windows app synchronization</span></span>


<span data-ttu-id="f0466-116">Windows アプリの開発者は、どの設定を同期するかを定義できます。これらの設定は、UE-V を使ってキャプチャおよび同期できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="f0466-116">The developer of a Windows app can define which settings, if any, are to be synchronized, and these settings can now be captured and synchronized with UE-V.</span></span>

<span data-ttu-id="f0466-117">既定では、UE-V は、windows 8 と Windows 8.1 に含まれている多くの Windows アプリの設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="f0466-117">By default, UE-V synchronizes the settings of many of the Windows apps included in Windows 8 and Windows 8.1.</span></span> <span data-ttu-id="f0466-118">同期されたアプリの一覧は、Windows PowerShell、Windows Management Instrumentation (WMI)、またはグループポリシーを使って変更できます。</span><span class="sxs-lookup"><span data-stu-id="f0466-118">You can modify the list of synchronized apps with Windows PowerShell, Windows Management Instrumentation (WMI), or Group Policy.</span></span>

<span data-ttu-id="f0466-119">**注** UE-V は、ドメインユーザーがサインイン資格情報を Microsoft アカウントにリンクしている場合、Windows アプリの設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="f0466-119">**Note** UE-V does not synchronize Windows app settings if the domain users link their sign-in credentials to their Microsoft account.</span></span> <span data-ttu-id="f0466-120">このリンクにより、設定が Microsoft OneDrive に同期されるため、UE-V のみがデスクトップアプリケーションを同期します。</span><span class="sxs-lookup"><span data-stu-id="f0466-120">This linking synchronizes settings to Microsoft OneDrive so UE-V only synchronizes the desktop applications.</span></span>

 

## <span data-ttu-id="f0466-121">Microsoft アカウントのリンク</span><span class="sxs-lookup"><span data-stu-id="f0466-121">Microsoft account linking</span></span>


<span data-ttu-id="f0466-122">Microsoft アカウントでサインインしている場合、または Microsoft アカウントをドメインアカウントにリンクしている場合、OneDrive を使用した設定の同期は Windows 8 に新しくなりました。</span><span class="sxs-lookup"><span data-stu-id="f0466-122">Settings synchronization via OneDrive is new to Windows 8 when you are signed in with a Microsoft account or if you link your Microsoft account to your domain account.</span></span> <span data-ttu-id="f0466-123">ドメインユーザーが UE-V を使用し、Microsoft アカウントにサインインしている場合は、次のようにします。</span><span class="sxs-lookup"><span data-stu-id="f0466-123">If a domain user uses UE-V and has signed in to a Microsoft account, then…</span></span>

-   <span data-ttu-id="f0466-124">UE-V はデスクトップアプリケーションの設定のみを同期します。</span><span class="sxs-lookup"><span data-stu-id="f0466-124">UE-V only synchronizes settings for desktop applications</span></span>

-   <span data-ttu-id="f0466-125">Microsoft アカウントでは、Windows アプリの設定と Windows デスクトップの設定が処理されます</span><span class="sxs-lookup"><span data-stu-id="f0466-125">Microsoft account handles Windows app settings and Windows desktop settings</span></span>

## <span data-ttu-id="f0466-126">会社設定センター</span><span class="sxs-lookup"><span data-stu-id="f0466-126">Company Settings Center</span></span>


<span data-ttu-id="f0466-127">会社設定センターという UE-V 2 のアプリケーションを介して、どの設定を同期するかをユーザーが制御できるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="f0466-127">You can provide your users with some control over which settings are synchronized through an application in UE-V 2 called Company Settings Center.</span></span> <span data-ttu-id="f0466-128">[会社の設定] センターは、UE-V エージェントと共にインストールされ、ユーザーはコントロールパネル、[**スタート**] メニューまたは**スタート**画面、および ue-v 通知領域のアイコンからアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="f0466-128">Company Settings Center is installed along with the UE-V Agent, and users can access it from Control Panel, the **Start** menu or **Start** screen, and from the UE-V notification area icon.</span></span>

<span data-ttu-id="f0466-129">[会社設定センター] には、同期されている設定が表示され、ユーザーは UE-V の同期状態を確認できます。</span><span class="sxs-lookup"><span data-stu-id="f0466-129">Company Settings Center displays which settings are synchronized and lets users see the synchronization status of UE-V.</span></span> <span data-ttu-id="f0466-130">ユーザーに許可した場合、ユーザーは会社設定センターを使用して、同期する設定を選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="f0466-130">If you let them, users can use Company Settings Center to select which settings to synchronize.</span></span> <span data-ttu-id="f0466-131">[**今すぐ同期**] ボタンをクリックして、すべての設定をすぐに同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="f0466-131">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span>






## <span data-ttu-id="f0466-132">関連トピック</span><span class="sxs-lookup"><span data-stu-id="f0466-132">Related topics</span></span>


[<span data-ttu-id="f0466-133">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="f0466-133">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="f0466-134">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="f0466-134">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="f0466-135">Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="f0466-135">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





