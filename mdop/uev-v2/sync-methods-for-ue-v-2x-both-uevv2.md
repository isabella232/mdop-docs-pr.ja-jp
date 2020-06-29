---
title: UE-V 2.x の同期方法
description: UE-V 2.x の同期方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823577"
---
# <span data-ttu-id="343aa-103">UE-V 2.x の同期方法</span><span class="sxs-lookup"><span data-stu-id="343aa-103">Sync Methods for UE-V 2.x</span></span>


<span data-ttu-id="343aa-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 エージェントを使用すると、ユーザーのアプリケーションと Windows の設定を設定の保存場所と同期することができます。</span><span class="sxs-lookup"><span data-stu-id="343aa-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent lets you synchronize users’ application and Windows settings with the settings storage location.</span></span> <span data-ttu-id="343aa-105">*同期方法*の構成では、ue-v Agent がアップロードし、これらの設定を設定の保存場所にダウンロードする方法を定義します。</span><span class="sxs-lookup"><span data-stu-id="343aa-105">The *Sync Method* configuration defines how the UE-V Agent uploads and downloads those settings to the settings storage location.</span></span> <span data-ttu-id="343aa-106">UE-V は、 *Syncmethod*と呼ばれる新しい syncmethod を紹介します。</span><span class="sxs-lookup"><span data-stu-id="343aa-106">UE-V 2.x introduces a new SyncMethod called the *SyncProvider*.</span></span> <span data-ttu-id="343aa-107">アプリケーションと Windows の設定の同期を開始するトリガーイベントについて詳しくは、「 [ue-v 2. x の同期トリガーイベント](sync-trigger-events-for-ue-v-2x-both-uevv2.md)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="343aa-107">For more information about trigger events that start the synchronization of application and Windows settings, see [Sync Trigger Events for UE-V 2.x](sync-trigger-events-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="343aa-108">同期メソッドの構成</span><span class="sxs-lookup"><span data-stu-id="343aa-108">SyncMethod Configuration</span></span>


<span data-ttu-id="343aa-109">次の表では、UE-V V 1.0 から v 2.0 への変更、および各構成の設定について説明します。</span><span class="sxs-lookup"><span data-stu-id="343aa-109">This table explains the changes to SyncMethod from UE-V v1.0 to v2.0 to v2.1, as well as the settings for each configuration:</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="343aa-110">同期メソッドの構成</span><span class="sxs-lookup"><span data-stu-id="343aa-110">SyncMethod Configuration</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="343aa-111">V 1.0</span><span class="sxs-lookup"><span data-stu-id="343aa-111">V1.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="343aa-112">V 2.0</span><span class="sxs-lookup"><span data-stu-id="343aa-112">V2.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="343aa-113">V 2.1 および V 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="343aa-113">V2.1 and V2.1 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="343aa-114">説明</span><span class="sxs-lookup"><span data-stu-id="343aa-114">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="343aa-115">SyncProvider</span><span class="sxs-lookup"><span data-stu-id="343aa-115">SyncProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-116">n/a</span><span class="sxs-lookup"><span data-stu-id="343aa-116">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-117">既定値</span><span class="sxs-lookup"><span data-stu-id="343aa-117">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-118">既定値</span><span class="sxs-lookup"><span data-stu-id="343aa-118">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-119">特定のアプリケーションまたはグローバル Windows デスクトップ設定の設定の変更は、キャッシュフォルダーにローカルに保存されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-119">Settings changes for a specific application or for global Windows desktop settings are saved locally to a cache folder.</span></span> <span data-ttu-id="343aa-120">これらの変更は、同期トリガーイベントが発生したときの設定の保存場所と同期されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-120">These changes are then synchronized with the settings storage location when a synchronization trigger event takes place.</span></span> <span data-ttu-id="343aa-121">変更を反映すると、設定の保存パスにローカルの変更が保存されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-121">Pushing out changes will save the local changes to the settings storage path.</span></span></p>
<p><span data-ttu-id="343aa-122">この既定の設定は、コンピューターの標準です。</span><span class="sxs-lookup"><span data-stu-id="343aa-122">This default setting is the gold standard for computers.</span></span> <span data-ttu-id="343aa-123">このオプションでは、アプリケーションまたはオペレーティングシステムの起動時の遅延が長期間に合わない場合に、しばらくの間、設定の同期とタイムアウトが試行されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-123">This option attempts to synchronize the setting and times out after a short delay to ensure that the application or operating system startup isn’t delayed for a long period of time.</span></span></p>
<p><span data-ttu-id="343aa-124">この機能は、スケジュールされたタスク–同期コントローラーアプリケーションにも関連付けられています。</span><span class="sxs-lookup"><span data-stu-id="343aa-124">This functionality is also tied to the Scheduled task – Sync Controller Application.</span></span> <span data-ttu-id="343aa-125">スケジュールされたタスクの頻度は管理者が管理します。</span><span class="sxs-lookup"><span data-stu-id="343aa-125">The administrator controls the frequency of the Scheduled task.</span></span> <span data-ttu-id="343aa-126">既定では、コンピューターはログオン後30分ごとに設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="343aa-126">By default, computers synchronize their settings every 30 min after logging on.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="343aa-127">OfflineFiles</span><span class="sxs-lookup"><span data-stu-id="343aa-127">OfflineFiles</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-128">既定値</span><span class="sxs-lookup"><span data-stu-id="343aa-128">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-129">非推奨</span><span class="sxs-lookup"><span data-stu-id="343aa-129">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-130">非推奨</span><span class="sxs-lookup"><span data-stu-id="343aa-130">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-131">V 2.0 の SyncProvider と同じように動作します。</span><span class="sxs-lookup"><span data-stu-id="343aa-131">Behaves the same as SyncProvider in V2.0.</span></span></p>
<p><span data-ttu-id="343aa-132">オフラインファイルが有効になっていて、フォルダーがピン留めされている場合、UE-V はこのフォルダーの固定を解除し、中央の SMB ディレクトリに直接同期します。</span><span class="sxs-lookup"><span data-stu-id="343aa-132">If Offline files are enabled and the folder is pinned then UE-V will unpin this folder and sync directly to the central SMB directory.</span></span></p>
<p><strong><span data-ttu-id="343aa-133">注: ネットワーク </strong> 接続されていない方法 (ノート pc を使用している場合) で ue-v を使用する場合は、オフラインファイルを使用して設定を移動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="343aa-133">NOTE:</strong> In V1.0 if you wanted to use UE-V in a CorpNet disconnected manner (aka traveling with a Laptop), then the guidance is to use Offline Files to ensure that your settings roamed.</span></span><span data-ttu-id="343aa-134">オフラインファイルを有効にするためのお客様からのフィードバックは、単純なエンタープライズブロックではありません。</span><span class="sxs-lookup"><span data-stu-id="343aa-134"> We received sufficient customer feedback that turning on Offline files is a non-trivial enterprise blocker.</span></span> <span data-ttu-id="343aa-135">したがって、UE-V 2 では、密結合の同期エンジンを作成してデータをローカルにキャッシュし、設定を中央のサーバーと同期します。</span><span class="sxs-lookup"><span data-stu-id="343aa-135">So in UE-V 2, we created a tightly coupled synchronization engine to cache your data locally and synchronize the settings to the central server.</span></span> <span data-ttu-id="343aa-136">この機能エリアでは、オフラインファイルまたはフォルダーリダイレクションは置き換えられません。</span><span class="sxs-lookup"><span data-stu-id="343aa-136">This feature area does not replace Offline Files or Folder Redirection.</span></span></p>
<p><span data-ttu-id="343aa-137">UE-V 2 はオフラインフォルダーでは適切に動作しないため、このガイダンスでは、固定されたオフラインまたは CSC フォルダーへの設定の記憶域パスを設定しません。</span><span class="sxs-lookup"><span data-stu-id="343aa-137">UE-V 2 does not work well with Offline folders so the guidance is not to set the settings storage path to a pinned Offline or CSC folder.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="343aa-138">外部</span><span class="sxs-lookup"><span data-stu-id="343aa-138">External</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-139">n/a</span><span class="sxs-lookup"><span data-stu-id="343aa-139">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-140">n/a</span><span class="sxs-lookup"><span data-stu-id="343aa-140">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-141">サポートされています</span><span class="sxs-lookup"><span data-stu-id="343aa-141">Supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-142">UE-V 2.1 では、この構成メソッドを使用して、ユーザーコンピューター上のローカルフォルダーに UE-V 設定が書き込まれる場合に、任意の外部同期エンジン (OneDrive for Business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="343aa-142">New in UE-V 2.1, this configuration method specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="343aa-143">なし</span><span class="sxs-lookup"><span data-stu-id="343aa-143">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-144">あり</span><span class="sxs-lookup"><span data-stu-id="343aa-144">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-145">あり</span><span class="sxs-lookup"><span data-stu-id="343aa-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-146">あり</span><span class="sxs-lookup"><span data-stu-id="343aa-146">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="343aa-147">この構成設定は、主に仮想デスクトップインフラストラクチャ (VDI) とストリーミングされたアプリケーションエクスペリエンス向けに設計されています。</span><span class="sxs-lookup"><span data-stu-id="343aa-147">This configuration setting is designed for the Virtual Desktop Infrastructure (VDI) and Streamed Application experience primarily.</span></span> <span data-ttu-id="343aa-148">この設定は、データセンターで使用されている Windows Server のボックスで使用する必要があります。この設定は、接続を常に利用できます。</span><span class="sxs-lookup"><span data-stu-id="343aa-148">This setting should be used on Windows Server boxes used in a datacenter, where the connection will always be available.</span></span></p>
<p><span data-ttu-id="343aa-149">設定の変更は、サーバーに直接保存されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-149">Any settings changes are saved directly to the server.</span></span> <span data-ttu-id="343aa-150">設定の記憶域パスへのネットワーク接続が利用できない場合は、設定の変更はデバイスにキャッシュされ、次に同期プロバイダーが実行されるときに同期されます。</span><span class="sxs-lookup"><span data-stu-id="343aa-150">If the network connection to the settings storage path is not available, then the settings changes are cached on the device and are synchronized the next time that the Sync Provider runs.</span></span> <span data-ttu-id="343aa-151">設定の保存パスが見つからず、ログオフ時にプールされた VDI 環境からユーザープロファイルが削除された場合、これらの設定の変更は保存されません。ユーザーは、コンピューターがもう一度設定の記憶域のパスに到達したときに変更を再適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="343aa-151">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, then these settings changes are lost, and the user must reapply the change when the computer can again reach the settings storage path.</span></span></p>
<p><span data-ttu-id="343aa-152">アプリと OS は、場所が存在するまで無期限に待機します。</span><span class="sxs-lookup"><span data-stu-id="343aa-152">Apps and OS will wait indefinitely for the location to be present.</span></span> <span data-ttu-id="343aa-153">これにより、アプリの読み込みまたは OS のログオン時間が、場所が見つからない場合に大幅に増大する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="343aa-153">This could cause App load or OS logon time to dramatically increase if the location is not found.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="343aa-154">同期方法は、次の方法で構成できます。</span><span class="sxs-lookup"><span data-stu-id="343aa-154">You can configure the sync method in these ways:</span></span>

-   <span data-ttu-id="343aa-155">コマンドラインパラメーターまたはバッチスクリプトを使用[して Ue-v agent を展開](https://technet.microsoft.com/library/dn458891.aspx#agent)する場合</span><span class="sxs-lookup"><span data-stu-id="343aa-155">When you [Deploy the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="343aa-156">[グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)設定を使用する</span><span class="sxs-lookup"><span data-stu-id="343aa-156">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="343aa-157">UE-V の[System Center 構成パック](https://technet.microsoft.com/library/dn458917.aspx)</span><span class="sxs-lookup"><span data-stu-id="343aa-157">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="343aa-158">UE-V Agent をインストールした後、 [Windows PowerShell または Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)を使用する</span><span class="sxs-lookup"><span data-stu-id="343aa-158">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>






## <span data-ttu-id="343aa-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="343aa-159">Related topics</span></span>


[<span data-ttu-id="343aa-160">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="343aa-160">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[<span data-ttu-id="343aa-161">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="343aa-161">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[<span data-ttu-id="343aa-162">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="343aa-162">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





