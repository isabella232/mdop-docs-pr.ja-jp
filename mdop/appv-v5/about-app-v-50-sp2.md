---
title: App-V 5.0 SP2 について
description: App-V 5.0 SP2 について
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814987"
---
# <span data-ttu-id="11c1f-103">App-V 5.0 SP2 について</span><span class="sxs-lookup"><span data-stu-id="11c1f-103">About App-V 5.0 SP2</span></span>


<span data-ttu-id="11c1f-104">App-v 5.0 SP2 は、強化された統合プラットフォーム、より柔軟な仮想化、仮想化されたアプリケーションのための強力な管理機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="11c1f-104">App-V 5.0SP2 provides an improved integrated platform, more flexible virtualization, and powerful management for virtualized applications.</span></span> <span data-ttu-id="11c1f-105">詳細については、「 [app-v 5.0 の概要](https://go.microsoft.com/fwlink/p/?LinkId=325265)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=325265) 。</span><span class="sxs-lookup"><span data-stu-id="11c1f-105">For more information see, [App-V 5.0 Overview](https://go.microsoft.com/fwlink/p/?LinkId=325265) (https://go.microsoft.com/fwlink/?LinkId=325265).</span></span>

## <span data-ttu-id="11c1f-106">標準アプリ-V 5.0 SP2 の機能の変更点</span><span class="sxs-lookup"><span data-stu-id="11c1f-106">Changes in Standard App-V 5.0SP2 Functionality</span></span>


<span data-ttu-id="11c1f-107">以下のセクションでは、App-v 5.0 SP2 の標準機能の変更点について説明します。</span><span class="sxs-lookup"><span data-stu-id="11c1f-107">The following sections contain information about the changes in standard functionality for App-V 5.0SP2.</span></span>

### <a href="" id="bkmk-sp2-supported-cfg"></a><span data-ttu-id="11c1f-108">Windows Server 2012 R2 および Windows 8.1 のサポート</span><span class="sxs-lookup"><span data-stu-id="11c1f-108">Support for Windows Server 2012 R2 and Windows 8.1</span></span>

<span data-ttu-id="11c1f-109">App-v 5.0 には Windows Server 2012 R2 および Windows 8.1 のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-109">App-V 5.0 includes support for Windows Server 2012 R2 and Windows 8.1</span></span>

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> <span data-ttu-id="11c1f-110">App-v 5.0 SP2 では、ユーザーのローミングの AppData ディレクトリのフォルダーリダイレクションがサポートされるようになりました</span><span class="sxs-lookup"><span data-stu-id="11c1f-110">App-V 5.0SP2 now supports folder redirection for the user’s roaming AppData directory</span></span>

<span data-ttu-id="11c1f-111">App-v 5.0 SP2 はローミング AppData (% AppData%) をサポートしていますフォルダリダイレクション。</span><span class="sxs-lookup"><span data-stu-id="11c1f-111">App-V 5.0SP2 supports roaming AppData (%AppData%) folder redirection.</span></span> <span data-ttu-id="11c1f-112">詳細については、「 [app-v でフォルダーリダイレクションを使用するための計画](planning-to-use-folder-redirection-with-app-v.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c1f-112">For more information, see the [Planning to Use Folder Redirection with App-V](planning-to-use-folder-redirection-with-app-v.md).</span></span>

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a><span data-ttu-id="11c1f-113">パッケージのアップグレードの改善と保留中のタスク</span><span class="sxs-lookup"><span data-stu-id="11c1f-113">Package upgrade improvements and pending tasks</span></span>

<span data-ttu-id="11c1f-114">App-v 5.0 SP2 では、新しいバージョンのパッケージまたは接続グループが公開されている場合、実行中の仮想アプリケーションを閉じるように求められなくなりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-114">In App-V 5.0SP2, you are no longer prompted to close a running virtual application when a newer version of the package or connection group is published.</span></span> <span data-ttu-id="11c1f-115">関連タスクを実行しようとしたときに、パッケージまたは接続グループが使用されている場合は、オブジェクトが使用中であることを示すメッセージが表示され、その操作は後で実行されます。</span><span class="sxs-lookup"><span data-stu-id="11c1f-115">If a package or connection group is in use when you try to perform a related task, a message displays to indicate that the object is in use, and that the operation will be attempted at a later time.</span></span>

<span data-ttu-id="11c1f-116">保留状態になっているタスクは、次の規則に従って実行されます。</span><span class="sxs-lookup"><span data-stu-id="11c1f-116">Tasks that have been placed in a pending state will be performed according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="11c1f-117">タスクの種類</span><span class="sxs-lookup"><span data-stu-id="11c1f-117">Task type</span></span></th>
<th align="left"><span data-ttu-id="11c1f-118">該当するルール</span><span class="sxs-lookup"><span data-stu-id="11c1f-118">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11c1f-119">ユーザーベースのタスク (パッケージをユーザーに公開するなど)</span><span class="sxs-lookup"><span data-stu-id="11c1f-119">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c1f-120">保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="11c1f-120">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11c1f-121">グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</span><span class="sxs-lookup"><span data-stu-id="11c1f-121">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c1f-122">保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="11c1f-122">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="11c1f-123">タスクが保留状態になっている場合、App-v クライアントは、次のように、保留中のタスクのレジストリキーも生成します。</span><span class="sxs-lookup"><span data-stu-id="11c1f-123">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="11c1f-124">ユーザーベースまたはグローバルベースのタスク</span><span class="sxs-lookup"><span data-stu-id="11c1f-124">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="11c1f-125">レジストリキーが生成される場所</span><span class="sxs-lookup"><span data-stu-id="11c1f-125">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11c1f-126">ユーザーベースのタスク</span><span class="sxs-lookup"><span data-stu-id="11c1f-126">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c1f-127">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="11c1f-127">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11c1f-128">グローバルに基づくタスク</span><span class="sxs-lookup"><span data-stu-id="11c1f-128">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="11c1f-129">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="11c1f-129">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="11c1f-130">App-v 5.0 を使用した Microsoft Office 2013 および Microsoft Office 2010 の仮想化</span><span class="sxs-lookup"><span data-stu-id="11c1f-130">Virtualizing Microsoft Office 2013 and Microsoft Office 2010 using App-V 5.0</span></span>

<span data-ttu-id="11c1f-131">App-v 5.0 でサポートされている Microsoft Office シナリオの詳細については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c1f-131">Use the following link for more information about App-V 5.0 supported Microsoft Office scenarios.</span></span>

[<span data-ttu-id="11c1f-132">Application Virtualization (APP-V) 5.0 向けの Microsoft Office 2013 の仮想化</span><span class="sxs-lookup"><span data-stu-id="11c1f-132">Virtualizing Microsoft Office 2013 for Application Virtualization (App-V) 5.0</span></span>](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

<span data-ttu-id="11c1f-133">**注** このドキュメントでは、Microsoft Office 2013 App-v 5.0 パッケージの作成に重点を置いて説明します。</span><span class="sxs-lookup"><span data-stu-id="11c1f-133">**Note** This document focuses on creating a Microsoft Office 2013 App-V 5.0 Package.</span></span> <span data-ttu-id="11c1f-134">また、Microsoft Office 2010 のシナリオについては、「App-v 5.0」もご覧ください。</span><span class="sxs-lookup"><span data-stu-id="11c1f-134">However, it also provides information about scenarios for Microsoft Office 2010 with App-V 5.0.</span></span>

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> <span data-ttu-id="11c1f-135">App-v 5.0 クライアント管理ユーザーインターフェイスアプリケーション</span><span class="sxs-lookup"><span data-stu-id="11c1f-135">App-V 5.0 Client Management User Interface Application</span></span>

<span data-ttu-id="11c1f-136">以前のバージョンの App-v 5.0 では、クライアント管理ユーザーインターフェイス (UI) は、App-v 5.0 クライアントインストールを使って提供されていました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-136">In previous versions of App-V 5.0 the Client Management User Interface (UI) was provided with the App-V 5.0 Client installation.</span></span> <span data-ttu-id="11c1f-137">App-v 5.0 SP2 の場合、これはサポートされなくなりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-137">With App-V 5.0SP2 this is no longer the case.</span></span> <span data-ttu-id="11c1f-138">管理者は、(サポートされているすべての App-v 展開構成を使用して) 仮想アプリケーションとして、またはインストール済みアプリケーションとして、App-v 5.0 クライアント UI を展開するオプションを使用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-138">Administrators now have the option to deploy the App-V 5.0 Client UI as a Virtual Application (using all supported App-V deployment configurations) or as an installed application.</span></span>

<span data-ttu-id="11c1f-139">詳細については、「 [Microsoft Application Virtualization 5.0 クライアント UI アプリケーション](https://go.microsoft.com/fwlink/p/?LinkId=386345)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=386345) 。</span><span class="sxs-lookup"><span data-stu-id="11c1f-139">For more information see [Microsoft Application Virtualization 5.0 Client UI Application](https://go.microsoft.com/fwlink/p/?LinkId=386345) (https://go.microsoft.com/fwlink/?LinkId=386345).</span></span>

### <span data-ttu-id="11c1f-140">Side-by-side (SxS) アセンブリの自動パッケージと展開</span><span class="sxs-lookup"><span data-stu-id="11c1f-140">Side-by-Side (SxS) Assembly Automatic Packaging and Deployment</span></span>

<span data-ttu-id="11c1f-141">App-v 5.0 SP2 は、side-by-side (SxS) アセンブリと、App-v 5.0 SP2 クライアントを実行しているコンピューター上での展開を自動的に検出するようになりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-141">App-V 5.0SP2 now automatically detects side-by-side (SxS) assemblies, and deployment on the computer running the App-V 5.0SP2 client.</span></span> <span data-ttu-id="11c1f-142">SxS アセンブリは、主に VC + + 実行時の依存関係または MSXML で構成されています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-142">A SxS assembly primarily consists of VC++ run-time dependencies or MSXML.</span></span> <span data-ttu-id="11c1f-143">以前のバージョンの App-v では、VC ランタイムとの依存関係を持つ仮想アプリケーションでは、これらの依存関係が、App-v 5.0 SP2 クライアントを実行しているコンピューター上でローカルである必要がありました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-143">In previous versions of App-V, virtual applications that had dependencies on VC run-times required these dependencies to be locally on the computer running the App-V 5.0SP2 client.</span></span>

<span data-ttu-id="11c1f-144">次の機能がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-144">The following functionality is now supported:</span></span>

-   <span data-ttu-id="11c1f-145">アプリ-V 5.0 sequencer は、sequencer を実行しているコンピューターに VC ランタイムが既にインストールされているかどうかに関係なく、パッケージ内の SxS アセンブリを自動的にキャプチャします。</span><span class="sxs-lookup"><span data-stu-id="11c1f-145">The App-V 5.0 sequencer automatically captures the SxS assembly in the package regardless of whether the VC run-time has already been installed on the computer running the sequencer.</span></span>

-   <span data-ttu-id="11c1f-146">App-v 5.0 クライアントは、発行時に必要に応じてクライアントを実行しているコンピューターに、必要な SxS アセンブリを自動的にインストールします。</span><span class="sxs-lookup"><span data-stu-id="11c1f-146">The App-V 5.0 client automatically installs the required SxS assembly to the computer running the client as required at publishing time.</span></span>

-   <span data-ttu-id="11c1f-147">アプリ-V 5.0 sequencer は、sequencer のレポートメカニズムを使って、VC ランタイム依存関係を報告します。</span><span class="sxs-lookup"><span data-stu-id="11c1f-147">The App-V 5.0 sequencer reports the VC run-time dependency using the sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="11c1f-148">App-v 5.0 sequencer では、sequencer を実行しているコンピューターで依存関係が既に利用可能であることを示すイベントで、VC ランタイム依存関係を除外することができるようになりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-148">The App-V 5.0 sequencer now allows you to exclude the VC run-time dependency in the event that the dependency is already available on the computer running the sequencer.</span></span>

### <span data-ttu-id="11c1f-149">公開の更新の改善</span><span class="sxs-lookup"><span data-stu-id="11c1f-149">Publishing Refresh Improvements</span></span>

<span data-ttu-id="11c1f-150">App-v 5.0 は、特定のユーザーの一連のアプリケーションを更新する全体的なエクスペリエンスを向上させるために、いくつかの機能をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-150">App-V 5.0 supports several features were added to improve the overall experience of refreshing a set of applications for a specific user.</span></span>

<span data-ttu-id="11c1f-151">次の一覧は、公開更新の拡張機能を示しています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-151">The following list displays the publishing refresh enhancements:</span></span>

<span data-ttu-id="11c1f-152">次の一覧には、新しい公開の更新を有効にする方法についての詳細情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-152">The following list contains more information about how to enable the new publishing refresh improvements.</span></span>

-   <span data-ttu-id="11c1f-153">**EnablePublishingRefreshUI** -App-v 5.0 クライアントを実行しているコンピューターの公開更新進行状況バーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="11c1f-153">**EnablePublishingRefreshUI** - Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span>

-   <span data-ttu-id="11c1f-154">**Hideui** -手動同期中に発行更新の進行状況バーを非表示にします。</span><span class="sxs-lookup"><span data-stu-id="11c1f-154">**HideUI** - Hides the publishing refresh progress bar during a manual sync.</span></span>

### <span data-ttu-id="11c1f-155">新しいクライアント構成の設定</span><span class="sxs-lookup"><span data-stu-id="11c1f-155">New Client Configuration Setting</span></span>

<span data-ttu-id="11c1f-156">次の新しいクライアント構成設定は、App-v 5.0 SP2 で利用できます。</span><span class="sxs-lookup"><span data-stu-id="11c1f-156">The following new client configuration setting is available with App-V 5.0 SP2:</span></span>

<span data-ttu-id="11c1f-157">**Enabledynamicvirtualization** -サポートされているシェルの拡張機能、ブラウザーヘルパーオブジェクト、アクティブな X コントロールを仮想アプリケーションで仮想化して実行できるようにします。</span><span class="sxs-lookup"><span data-stu-id="11c1f-157">**EnableDynamicVirtualization** - Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span>

<span data-ttu-id="11c1f-158">詳細については、「[クライアント構成の設定につい](about-client-configuration-settings.md)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c1f-158">For more information, see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span>

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> <span data-ttu-id="11c1f-159">App-v 5.0 シェル拡張機能</span><span class="sxs-lookup"><span data-stu-id="11c1f-159">App-V 5.0 Shell extensions</span></span>

<span data-ttu-id="11c1f-160">App-v 5.0 SP2 では、シェルの拡張機能がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="11c1f-160">App-V 5.0 SP2 now supports shell extensions.</span></span>

<span data-ttu-id="11c1f-161">詳細については、「app-v 5.0 で仮想化された[アプリケーションを作成および管理](creating-and-managing-app-v-50-virtualized-applications.md)する」の「APP-V **5.0 sp2 シェル extension のサポート**」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="11c1f-161">For more information see the **App-V 5.0SP2 shell extension support** section of [Creating and Managing App-V 5.0 Virtualized Applications](creating-and-managing-app-v-50-virtualized-applications.md).</span></span>

## <a href="" id="---------app-v-5-0-documentation-updates"></a> <span data-ttu-id="11c1f-162">App-v 5.0 ドキュメントの更新</span><span class="sxs-lookup"><span data-stu-id="11c1f-162">App-V 5.0 documentation updates</span></span>


<span data-ttu-id="11c1f-163">App-v 5.0 SP2 には、次のシナリオの更新されたドキュメントが用意されています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-163">App-V 5.0 SP2 provides updated documentation for the following scenarios:</span></span>

-   [<span data-ttu-id="11c1f-164">旧バージョンからの移行</span><span class="sxs-lookup"><span data-stu-id="11c1f-164">Migrating from a Previous Version</span></span>](migrating-from-a-previous-version-app-v-50.md)

-   [<span data-ttu-id="11c1f-165">App-V 5.0 について</span><span class="sxs-lookup"><span data-stu-id="11c1f-165">About App-V 5.0</span></span>](about-app-v-50.md)

-   <span data-ttu-id="11c1f-166">[App-v 5.0 レポートについて](about-app-v-50-reporting.md)(よく寄せられる質問セクション)</span><span class="sxs-lookup"><span data-stu-id="11c1f-166">[About App-V 5.0 Reporting](about-app-v-50-reporting.md) (frequently asked questions section)</span></span>

## <span data-ttu-id="11c1f-167">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="11c1f-167">How to Get MDOP Technologies</span></span>


<span data-ttu-id="11c1f-168">App-v 5.0 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="11c1f-168">App-V 5.0 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="11c1f-169">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="11c1f-169">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="11c1f-170">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="11c1f-170">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="11c1f-171">関連トピック</span><span class="sxs-lookup"><span data-stu-id="11c1f-171">Related topics</span></span>


[<span data-ttu-id="11c1f-172">App-V 5.0 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="11c1f-172">Release Notes for App-V 5.0 SP2</span></span>](release-notes-for-app-v-50-sp2.md)

 

 





