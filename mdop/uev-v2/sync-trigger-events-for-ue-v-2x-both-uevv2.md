---
title: UE-V 2.x の同期トリガー イベント
description: UE-V 2.x の同期トリガー イベント
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826797"
---
# <span data-ttu-id="92059-103">UE-V 2.x の同期トリガー イベント</span><span class="sxs-lookup"><span data-stu-id="92059-103">Sync Trigger Events for UE-V 2.x</span></span>


<span data-ttu-id="92059-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 を使用すると、ドメインに参加しているすべてのデバイスでアプリケーションと Windows の設定を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="92059-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 lets you synchronize your application and Windows settings across all your domain-joined devices.</span></span> <span data-ttu-id="92059-105">*同期トリガーイベント*は、ue-v エージェントが設定の保存場所とこれらの設定を同期するタイミングを定義します。</span><span class="sxs-lookup"><span data-stu-id="92059-105">*Sync trigger events* define when the UE-V Agent synchronizes those settings with the settings storage location.</span></span> <span data-ttu-id="92059-106">UE-V 2 には、 *Syncprovider*と呼ばれる新しい*同期メソッド*が導入されています。</span><span class="sxs-lookup"><span data-stu-id="92059-106">UE-V 2 introduces a new *Sync Method* called the *SyncProvider*.</span></span> <span data-ttu-id="92059-107">同期メソッドの構成の詳細については、「 [ue-v の同期メソッド](sync-methods-for-ue-v-2x-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92059-107">For more information about Sync Method configuration, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="92059-108">UE-V 2 同期トリガーイベント</span><span class="sxs-lookup"><span data-stu-id="92059-108">UE-V 2 Sync Trigger Events</span></span>


<span data-ttu-id="92059-109">次の表では、従来のアプリケーションと Windows 設定のトリガーイベントについて説明します。</span><span class="sxs-lookup"><span data-stu-id="92059-109">The following table explains the trigger events for classic applications and Windows settings.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92059-110">UE-V 2 トリガーイベント</span><span class="sxs-lookup"><span data-stu-id="92059-110">UE-V 2 Trigger Event</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="92059-111">SyncMethod = Syncmethod</span><span class="sxs-lookup"><span data-stu-id="92059-111">SyncMethod=SyncProvider</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="92059-112">SyncMethod = None</span><span class="sxs-lookup"><span data-stu-id="92059-112">SyncMethod=None</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92059-113">Windows ログオン</span><span class="sxs-lookup"><span data-stu-id="92059-113">Windows Logon</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="92059-114">アプリケーションと Windows の設定は、設定の保存場所からローカルキャッシュにインポートされます。</span><span class="sxs-lookup"><span data-stu-id="92059-114">Application and Windows settings are imported to the local cache from the settings storage location.</span></span></p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)"><span data-ttu-id="92059-115">非同期の Windows 設定 </a> が適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-115">Asynchronous Windows settings</a> are applied.</span></span></p></li>
<li><p><span data-ttu-id="92059-116">同期ウィンドウの設定は、次の Windows ログオン時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-116">Synchronous Windows settings will be applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="92059-117">アプリケーションの設定は、アプリケーションの起動時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-117">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="92059-118">アプリケーションと Windows の設定は、[設定の保存] の場所から直接読み取ります。</span><span class="sxs-lookup"><span data-stu-id="92059-118">Application and Windows settings are read directly from the settings storage location.</span></span></p></li>
<li><p><span data-ttu-id="92059-119">非同期および同期ウィンドウの設定が適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-119">Asynchronous and synchronous Windows settings are applied.</span></span></p></li>
<li><p><span data-ttu-id="92059-120">アプリケーションの設定は、アプリケーションの起動時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-120">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92059-121">Windows のログオフ</span><span class="sxs-lookup"><span data-stu-id="92059-121">Windows Logoff</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-122">変更をローカルに保存して、非同期および同期の Windows 設定を設定のストレージロケーションサーバーにコピーして (使用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="92059-122">Store changes locally and cache and copy asynchronous and synchronous Windows settings to the settings storage location server, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-123">非同期および同期の Windows 設定の保存場所への変更を保存する</span><span class="sxs-lookup"><span data-stu-id="92059-123">Store changes to asynchronous and synchronous Windows settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92059-124">Windows Connect (RDP)/ロック解除</span><span class="sxs-lookup"><span data-stu-id="92059-124">Windows Connect (RDP) / Unlock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-125">任意の非同期 Windows 設定を設定の保存場所からローカルキャッシュに同期します (可能な場合)。</span><span class="sxs-lookup"><span data-stu-id="92059-125">Synchronize any asynchronous Windows settings from settings storage location to local cache, if available.</span></span></p>
<p><span data-ttu-id="92059-126">キャッシュされた Windows の設定を適用する</span><span class="sxs-lookup"><span data-stu-id="92059-126">Apply cached Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-127">設定の保存場所から非同期 windows 設定をダウンロードして適用する</span><span class="sxs-lookup"><span data-stu-id="92059-127">Download and apply asynchronous windows settings from settings storage location</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92059-128">Windows Disconnect (RDP)/ロック</span><span class="sxs-lookup"><span data-stu-id="92059-128">Windows Disconnect (RDP) / Lock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-129">非同期の Windows 設定の変更をローカルキャッシュに保存します。</span><span class="sxs-lookup"><span data-stu-id="92059-129">Store asynchronous Windows settings changes to the local cache.</span></span></p>
<p><span data-ttu-id="92059-130">任意の非同期 Windows 設定をローカルキャッシュから設定の保存場所に同期する (利用可能な場合)</span><span class="sxs-lookup"><span data-stu-id="92059-130">Synchronize any asynchronous Windows settings from the local cache to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-131">非同期の Windows 設定の変更を設定の保存場所に保存する</span><span class="sxs-lookup"><span data-stu-id="92059-131">Store asynchronous Windows settings changes to the settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92059-132">アプリケーションの開始</span><span class="sxs-lookup"><span data-stu-id="92059-132">Application start</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-133">アプリケーションの起動時にローカルキャッシュからアプリケーションの設定を適用する</span><span class="sxs-lookup"><span data-stu-id="92059-133">Apply application settings from local cache as the application starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-134">アプリケーションの起動時に、設定の保存場所からアプリケーション設定を適用する</span><span class="sxs-lookup"><span data-stu-id="92059-134">Apply application settings from settings storage location as the application starts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92059-135">アプリケーションが閉じる</span><span class="sxs-lookup"><span data-stu-id="92059-135">Application closes</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-136">アプリケーション設定の変更をローカルキャッシュに保存し、[設定の保存場所] (使用可能な場合) に設定をコピーします。</span><span class="sxs-lookup"><span data-stu-id="92059-136">Store any application settings changes to the local cache and copy settings to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-137">アプリケーション設定の変更を設定の保存場所に保存する</span><span class="sxs-lookup"><span data-stu-id="92059-137">Store any application settings changes to settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="92059-138">同期コントローラーのスケジュールされたタスクまたは "今すぐ同期" が会社の設定センターから実行される</span><span class="sxs-lookup"><span data-stu-id="92059-138">Sync Controller Scheduled Task or “Sync Now” is run from the Company Settings Center</span></span></strong></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="92059-139">アプリケーションと Windows の設定は、設定の保存場所とローカルキャッシュの間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="92059-139">Application and Windows settings are synchronized between the settings storage location and the local cache.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="92059-140">注</span><span class="sxs-lookup"><span data-stu-id="92059-140">Note</span></span></strong><br/><p><span data-ttu-id="92059-141">設定の変更は、アプリケーションが閉じるまでローカルにキャッシュされません。</span><span class="sxs-lookup"><span data-stu-id="92059-141">Settings changes are not cached locally until an application closes.</span></span> <span data-ttu-id="92059-142">このトリガーは、現在実行中のアプリケーションに加えられた変更をエクスポートしません。</span><span class="sxs-lookup"><span data-stu-id="92059-142">This trigger will not export changes made to a currently running application.</span></span></p>
<p><span data-ttu-id="92059-143">Windows の設定では、次のロック (非同期) またはログオフ (非同期および同期) まで、すべての変更がローカルにキャッシュされ、エクスポートされることを意味します。</span><span class="sxs-lookup"><span data-stu-id="92059-143">For Windows settings, this means that any changes will not be cached locally and exported until the next Lock (Asynchronous) or Logoff (Asynchronous and Synchronous).</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="92059-144">設定は次の場合に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-144">Settings are applied in these cases:</span></span></p>
<ul>
<li><p><span data-ttu-id="92059-145">非同期の Windows 設定が直接適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-145">Asynchronous Windows settings are applied directly.</span></span></p></li>
<li><p><span data-ttu-id="92059-146">アプリケーションの設定は、アプリケーションの起動時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-146">Application settings are applied when the application starts.</span></span></p></li>
<li><p><span data-ttu-id="92059-147">非同期と同期の両方の Windows の設定は、次の Windows ログオン時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-147">Both asynchronous and synchronous Windows settings are applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="92059-148">Windows アプリ (AppX) の設定は、次の更新時に適用されます。</span><span class="sxs-lookup"><span data-stu-id="92059-148">Windows app (AppX) settings are applied during the next refresh.</span></span> <span data-ttu-id="92059-149"><a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)"> </a> 詳細については、「アプリケーションの設定を監視する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="92059-149">See <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)">Monitor Application Settings</a> for more information.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="92059-150">NA</span><span class="sxs-lookup"><span data-stu-id="92059-150">NA</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="92059-151">リモートストアで更新された非同期設定 \*</span><span class="sxs-lookup"><span data-stu-id="92059-151">Asynchronous Settings updated on remote store\*</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="92059-152">キャッシュから新しい非同期設定を読み込んで適用します。</span><span class="sxs-lookup"><span data-stu-id="92059-152">Load and apply new asynchronous settings from the cache.</span></span></p></td>
<td align="left"><p><span data-ttu-id="92059-153">中央サーバーから設定を読み込んで適用する</span><span class="sxs-lookup"><span data-stu-id="92059-153">Load and apply settings from central server</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="92059-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="92059-154">Related topics</span></span>


[<span data-ttu-id="92059-155">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="92059-155">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

[<span data-ttu-id="92059-156">UE-V 2. x のスケジュールされたタスクの頻度の変更</span><span class="sxs-lookup"><span data-stu-id="92059-156">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[<span data-ttu-id="92059-157">UE-V 2. x の構成方法を選択します。</span><span class="sxs-lookup"><span data-stu-id="92059-157">Choose the Configuration Method for UE-V 2.x</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)









