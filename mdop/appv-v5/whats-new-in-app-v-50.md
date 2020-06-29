---
title: App-V 5.0 の新機能
description: App-V 5.0 の新機能
author: dansimp
ms.assetid: 79ff6e02-e926-4803-87d8-248a6b28099d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dabe264f033bd5c9897f07d931f799a42e6b72e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813219"
---
# <span data-ttu-id="55709-103">App-V 5.0 の新機能</span><span class="sxs-lookup"><span data-stu-id="55709-103">What's New in App-V 5.0</span></span>


<span data-ttu-id="55709-104">このセクションは、既に App-v に精通していて、アプリ5.0 で何が変更されたかを確認する必要があるユーザーを対象としています。既に App-v に慣れていない場合は、まず「 [app-v 5.0 の計画](planning-for-app-v-50-rc.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55709-104">This section is for users who are already familiar with App-V and want to know what has changed in App-V 5.0 If you are not already familiar with App-V, you should start by reading [Planning for App-V 5.0](planning-for-app-v-50-rc.md).</span></span>

## <span data-ttu-id="55709-105">標準機能の変更点</span><span class="sxs-lookup"><span data-stu-id="55709-105">Changes in Standard Functionality</span></span>


<span data-ttu-id="55709-106">以下のセクションでは、App-v 5.0 の標準機能の変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="55709-106">The following sections contain information about the changes in standard functionality for App-V 5.0.</span></span>

### <span data-ttu-id="55709-107">サポートされているオペレーティングシステムの変更</span><span class="sxs-lookup"><span data-stu-id="55709-107">Changes to Supported Operating Systems</span></span>

<span data-ttu-id="55709-108">詳細については、「 [app-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55709-108">For more information, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

## <span data-ttu-id="55709-109">Sequencer の変更点</span><span class="sxs-lookup"><span data-stu-id="55709-109">Changes to the sequencer</span></span>


<span data-ttu-id="55709-110">以下のセクションでは、App-v 5.0 sequencer での変更に関する情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="55709-110">The following sections contain information about the changes in the App-V 5.0 sequencer.</span></span>

### <span data-ttu-id="55709-111">Sequencer に対する特定の変更</span><span class="sxs-lookup"><span data-stu-id="55709-111">Specific change to the sequencer</span></span>

<span data-ttu-id="55709-112">次の表には、App-v 5.0 sequencer で変更された内容に関する情報が表示されています。</span><span class="sxs-lookup"><span data-stu-id="55709-112">The following table displays information about what has changed with the App-V 5.0 sequencer</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="55709-113">Sequencer 機能</span><span class="sxs-lookup"><span data-stu-id="55709-113">Sequencer Feature</span></span></th>
<th align="left"><span data-ttu-id="55709-114">App-v 5.0 Sequencer の機能</span><span class="sxs-lookup"><span data-stu-id="55709-114">App-V 5.0 Sequencer Functionality</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-115">再起動処理</span><span class="sxs-lookup"><span data-stu-id="55709-115">Reboot processing</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-116">アプリケーションで再起動を求めるメッセージが表示されたら、アプリが sequencer を実行しているコンピューターを再起動することを許可する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55709-116">When an application prompts for a restart, you should allow the application to restart the computer running the sequencer.</span></span> <span data-ttu-id="55709-117">Sequencer を実行しているコンピューターが再起動し、監視モードで sequencer が再開されます。</span><span class="sxs-lookup"><span data-stu-id="55709-117">The computer running the sequencer will restart and the sequencer will resume in monitoring mode.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-118">仮想アプリケーションディレクトリの指定</span><span class="sxs-lookup"><span data-stu-id="55709-118">Specifying the virtual application directory</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-119">仮想アプリケーションディレクトリは必須のパラメーターです。</span><span class="sxs-lookup"><span data-stu-id="55709-119">Virtual Application Directory is a mandatory parameter.</span></span> <span data-ttu-id="55709-120">最善の結果を得るには、アプリケーションインストーラーのインストールディレクトリと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="55709-120">For best results, it should match the installation directory of the application installer.</span></span> <span data-ttu-id="55709-121">これにより、パフォーマンスとアプリケーションの互換性が最適化されます。</span><span class="sxs-lookup"><span data-stu-id="55709-121">This results in more optimal performance and application compatibility.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-122">編集ショートカット/FTAs</span><span class="sxs-lookup"><span data-stu-id="55709-122">Editing shortcuts/FTAs</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-123">[ショートカット/FTA] ページは <strong> 、 </strong> シーケンスウィザードが完了した後の [詳細編集] ページにあります。</span><span class="sxs-lookup"><span data-stu-id="55709-123">The Shortcuts/FTA page is on the <strong>Advanced</strong> editing page after the sequencing wizard has completed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-124">[変更履歴] タブ</span><span class="sxs-lookup"><span data-stu-id="55709-124">Change History Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-125">App-V 5.0 の [変更履歴] タブが削除されました。</span><span class="sxs-lookup"><span data-stu-id="55709-125">The Change History tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-126">[OSD] タブ</span><span class="sxs-lookup"><span data-stu-id="55709-126">OSD Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-127">[OSD] タブは、App-v 5.0 用に削除されました。</span><span class="sxs-lookup"><span data-stu-id="55709-127">The OSD tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-128">[仮想サービス] タブ</span><span class="sxs-lookup"><span data-stu-id="55709-128">Virtual Services Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-129">App-V 5.0 の [仮想サービス] タブが削除されました。</span><span class="sxs-lookup"><span data-stu-id="55709-129">The virtual services tab has been removed for App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-130">[ファイル]/[仮想ファイルシステム] タブ</span><span class="sxs-lookup"><span data-stu-id="55709-130">Files/Virtual File System Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-131">これらのタブは、パッケージファイルを変更できるようになっています。</span><span class="sxs-lookup"><span data-stu-id="55709-131">These tabs are combined and allow you to modify package files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-132">[展開] タブ</span><span class="sxs-lookup"><span data-stu-id="55709-132">Deployment Tab</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-133">パッケージでサーバーの URL を構成するためのオプションはありません。</span><span class="sxs-lookup"><span data-stu-id="55709-133">There are no longer options to configure the server URL in the packages.</span></span> <span data-ttu-id="55709-134">これは、展開構成、または管理サーバーを使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="55709-134">You should configure this now using deployment configuration, or the management server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-135">パッケージコンバーターツール</span><span class="sxs-lookup"><span data-stu-id="55709-135">Package Converter Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-136">PowerShell を使用して、以前のバージョンで作成されたパッケージを変換できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="55709-136">You can now use PowerShell to convert packages created in previous versions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-137">アドオン/ミドルウェア</span><span class="sxs-lookup"><span data-stu-id="55709-137">Add-on/Middleware</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-138">アドオンまたはミドルウェアアプリケーションの順序を付けている場合は、親パッケージを展開できます。</span><span class="sxs-lookup"><span data-stu-id="55709-138">You can expand parent packages when you are sequencing an Add-On or Middleware application.</span></span> <span data-ttu-id="55709-139">アドオンとミドルウェアパッケージは、App-v 5.0 の接続グループを使用して接続されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="55709-139">Add-ons and Middleware packages must be connected using connection groups in App-V 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-140">ファイルの出力</span><span class="sxs-lookup"><span data-stu-id="55709-140">Files output</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-141">次のファイルは、App-v 5.0、Windows Installer (.msi)、appv、展開構成、ユーザー構成、Report.XML を使って作成されます。</span><span class="sxs-lookup"><span data-stu-id="55709-141">The following files are created with App-V 5.0, Windows Installer (.msi), .appv, deployment configuration, user configuration, and the Report.XML.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-142">圧縮/セキュリティ記述子/MSI パッケージ</span><span class="sxs-lookup"><span data-stu-id="55709-142">Compression/Security descriptors/MSI packages</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-143">Windows Installer (.msi) ファイルの圧縮と作成は、すべてのパッケージで自動的に行われるため、今後セキュリティ記述子を上書きすることはできません。</span><span class="sxs-lookup"><span data-stu-id="55709-143">Compression and the creation of a Windows Installer (.msi) file are automatic for all packages and you can no longer override security descriptors.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-144">ツール/オプション</span><span class="sxs-lookup"><span data-stu-id="55709-144">Tools / Options</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-145">診断ウィンドウも削除されました。その他の設定もいくつかあります。</span><span class="sxs-lookup"><span data-stu-id="55709-145">The Diagnostics window has been removed as well as several other settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-146">インストールドライブ</span><span class="sxs-lookup"><span data-stu-id="55709-146">Installation Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-147">アプリケーションをインストールするときに、インストールドライブは不要になりました。</span><span class="sxs-lookup"><span data-stu-id="55709-147">An installation drive is no longer required when you install an application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="55709-148">OOS ストリーミング</span><span class="sxs-lookup"><span data-stu-id="55709-148">OOS Streaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="55709-149">ストリームの最適化が実行されていない場合、アプリが起動されるまで、アプリが app-v 5.0 クライアントを実行しているコンピューターから要求された場合、パッケージはストリームの途中で処理されません。</span><span class="sxs-lookup"><span data-stu-id="55709-149">If no stream optimization is performed, packages are stream faulted when they are requested by computers running the App-V 5.0 client until they can launch.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="55709-150">Q: &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="55709-150">Q:&lt;/p&gt;</span></span></td>
<td align="left"><p><span data-ttu-id="55709-151">App-v 5.0 はネイティブファイルシステムを使用し、Q:. は不要になります。</span><span class="sxs-lookup"><span data-stu-id="55709-151">App-V 5.0 uses the native file system and no longer requires a Q:.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="55709-152">シーケンスエラーの検出</span><span class="sxs-lookup"><span data-stu-id="55709-152">Sequencing error detection</span></span>


<span data-ttu-id="55709-153">アプリ-V 5.0 sequencer は、シーケンス中に一般的なシーケンスの問題を検出できます。</span><span class="sxs-lookup"><span data-stu-id="55709-153">The App-V 5.0 sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="55709-154">シーケンスウィザードの最後にある [**インストールレポート**] ページには、問題の重大度に応じて、**エラー**、**警告**、および**情報**に分類された診断メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="55709-154">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="55709-155">イベントに関する詳細情報を表示するには、レポートでレビューするアイテムをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="55709-155">To display more detailed information about an event, double-click the item you want to review in the report.</span></span> <span data-ttu-id="55709-156">シーケンスの問題と、問題の解決方法に関する提案が表示されます。</span><span class="sxs-lookup"><span data-stu-id="55709-156">The sequencing issues, as well as suggestions about how to resolve the issues are displayed.</span></span> <span data-ttu-id="55709-157">パッケージの作成が完了すると、システム準備レポートとインストールレポートの情報が集計されます。</span><span class="sxs-lookup"><span data-stu-id="55709-157">Information from the system preparation report and the installation report are summarized when you have finished creating a package.</span></span> <span data-ttu-id="55709-158">次のリストは、レポートで利用可能な問題の種類を示しています。</span><span class="sxs-lookup"><span data-stu-id="55709-158">The following list displays the types of issues available in the report:</span></span>

-   <span data-ttu-id="55709-159">除外されたファイル。</span><span class="sxs-lookup"><span data-stu-id="55709-159">Excluded files.</span></span>

-   <span data-ttu-id="55709-160">ドライバー情報。</span><span class="sxs-lookup"><span data-stu-id="55709-160">Driver information.</span></span>

-   <span data-ttu-id="55709-161">COM + システムの相違点。</span><span class="sxs-lookup"><span data-stu-id="55709-161">COM+ system differences.</span></span>

-   <span data-ttu-id="55709-162">Side-by-side (SxS) の競合。</span><span class="sxs-lookup"><span data-stu-id="55709-162">Side-by-side (SxS) conflicts.</span></span>

-   <span data-ttu-id="55709-163">シェルの拡張機能。</span><span class="sxs-lookup"><span data-stu-id="55709-163">Shell Extensions.</span></span>

-   <span data-ttu-id="55709-164">サポートされていないサービスに関する情報。</span><span class="sxs-lookup"><span data-stu-id="55709-164">Information about unsupported services.</span></span>

-   <span data-ttu-id="55709-165">分散.</span><span class="sxs-lookup"><span data-stu-id="55709-165">DCOM.</span></span>

## <span data-ttu-id="55709-166">接続グループ</span><span class="sxs-lookup"><span data-stu-id="55709-166">Connection Groups</span></span>


<span data-ttu-id="55709-167">以前は**動的 Suite コンポジション**と呼ばれていた app-v 機能が、app-v 5.0 で**接続グループ**として参照されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="55709-167">The App-V feature formerly known as **Dynamic Suite Composition** is now referred to as **Connection Groups** in App-V 5.0.</span></span> <span data-ttu-id="55709-168">接続グループの使用の詳細については、「[接続グループを管理する](managing-connection-groups.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="55709-168">For more information about using Connection Groups see [Managing Connection Groups](managing-connection-groups.md).</span></span>

## <span data-ttu-id="55709-169">ライセンスとメータリングの機能</span><span class="sxs-lookup"><span data-stu-id="55709-169">Licensing and Metering Functionality</span></span>


<span data-ttu-id="55709-170">アプリケーションとライセンス機能は、App-v 5.0 では削除されています。</span><span class="sxs-lookup"><span data-stu-id="55709-170">The application and licensing functionality has been removed in App-V 5.0.</span></span> <span data-ttu-id="55709-171">環境内の実際のライセンスの位置は、関連付けられているライセンス条項によって付与される特定のソフトウェアタイトルライセンスおよび使用権によって異なります。</span><span class="sxs-lookup"><span data-stu-id="55709-171">The actual license positions in your environment depend on the specific software title license and usage rights granted by the associated license terms.</span></span>

## <span data-ttu-id="55709-172">ファイルとアプリケーションのキャッシュ</span><span class="sxs-lookup"><span data-stu-id="55709-172">File and Application Cache</span></span>


<span data-ttu-id="55709-173">App-v 5.0 では、ファイルまたはアプリケーションのキャッシュは利用できません。</span><span class="sxs-lookup"><span data-stu-id="55709-173">There is no file or application cache available with App-V 5.0.</span></span>






## <span data-ttu-id="55709-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="55709-174">Related topics</span></span>


[<span data-ttu-id="55709-175">App-V 5.0 について</span><span class="sxs-lookup"><span data-stu-id="55709-175">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





