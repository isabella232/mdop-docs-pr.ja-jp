---
title: Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825284"
---
# <span data-ttu-id="31fad-103">Microsoft User Experience Virtualization (UE-V) 2.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="31fad-103">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>


<span data-ttu-id="31fad-104">Microsoft User Experience Virtualization (UE-V) 2.0 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="31fad-104">To search Microsoft User Experience Virtualization (UE-V) 2.0 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="31fad-105">UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="31fad-106">リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31fad-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="31fad-107">これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="31fad-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="31fad-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="31fad-109">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="31fad-109">Providing feedback</span></span>


<span data-ttu-id="31fad-110">フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="31fad-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="31fad-111">ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。</span><span class="sxs-lookup"><span data-stu-id="31fad-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="31fad-112">UE-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="31fad-112">UE-V known issues</span></span>


<span data-ttu-id="31fad-113">このセクションには、ユーザーエクスペリエンスの仮想化のリリースノートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31fad-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="31fad-114">同じコンピューター上の App-v とネイティブアプリケーションの間でレジストリ設定が同期されない</span><span class="sxs-lookup"><span data-stu-id="31fad-114">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="31fad-115">コンピューターに Application Virtualization (App-v) と Windows Installer (.msi) ファイルを使用してローカルにインストールされたアプリケーションがある場合、これらのテクノロジの間でレジストリベースの設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="31fad-115">When a computer has an application that is installed through both Application Virtualization (App-V) and a locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="31fad-116">**回避策:** この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="31fad-116">**WORKAROUND:** To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="31fad-117">ネットワーク共有がユーザーのドメイン外の場合、設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="31fad-117">Settings do not synchronization when network share is outside user’s domain</span></span>

<span data-ttu-id="31fad-118">Windows®8がオペレーティングシステム設定の同期を実行しようとすると、同期が失敗し、次のエラーメッセージが表示されます:**昇格:: filesystem:: 存在:: ユーザー名またはパスワードが正しくありませ**ん。</span><span class="sxs-lookup"><span data-stu-id="31fad-118">When Windows® 8 attempts operating system settings synchronization, the synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="31fad-119">このエラーは、ネットワーク共有がユーザーのドメインに含まれていないか、またはそのドメインとの信頼関係を持つドメインの外部にあることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-119">This error can indicate that the network share is outside the user’s domain or a domain with a trust relationship to that domain.</span></span> <span data-ttu-id="31fad-120">操作ログイベントを確認するには、**イベントビューアー**を開き、[**アプリケーションとサービスログ**] に移動し  /  **Microsoft**  /  ます。 Microsoft**User Experience Virtualization**  /  **Logging**  /  **operational**</span><span class="sxs-lookup"><span data-stu-id="31fad-120">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="31fad-121">UE-V の設定の保存場所に使用されるネットワーク共有は、ユーザーまたはユーザーのドメインの信頼済みドメインと同じ Active Directory ドメインに存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-121">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user or a trusted domain of the user’s domain.</span></span>

<span data-ttu-id="31fad-122">**回避策:** ユーザーと同じ Active Directory ドメインのネットワーク共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="31fad-122">**WORKAROUND:** Use network shares from the same Active Directory domain as the user.</span></span>

### <span data-ttu-id="31fad-123">Office 2010 と Office 2013 の両方で予期しない結果が表示される</span><span class="sxs-lookup"><span data-stu-id="31fad-123">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="31fad-124">ユーザーに Office 2010 と Office 2013 の両方がインストールされている場合、2つのバージョンの Office 間の一般的な設定は、UE-V によってローミングされます。</span><span class="sxs-lookup"><span data-stu-id="31fad-124">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="31fad-125">このため、Office 2010 パッケージのサイズが大きすぎるか、特に Office 365 が使用されている場合は、予期しない2013との競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-125">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="31fad-126">**回避策:** 1つのバージョンの Office のみをインストールするか、UE-V で同期される設定を制限します。</span><span class="sxs-lookup"><span data-stu-id="31fad-126">**WORKAROUND:** Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="31fad-127">Windows 8 アプリをアンインストールして再インストールすると、設定が初期状態に戻ります</span><span class="sxs-lookup"><span data-stu-id="31fad-127">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="31fad-128">Windows 8 アプリで UE-V 設定の同期を使用しているときに、ユーザーがアプリをアンインストールしてから、アプリを再インストールすると、アプリの設定は既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="31fad-128">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="31fad-129">この問題が発生するのは、アンインストールによってアプリの設定のローカル (キャッシュされた) コピーが削除されますが、ローカルの UE-V 設定パッケージは削除されないためです。</span><span class="sxs-lookup"><span data-stu-id="31fad-129"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="31fad-130">アプリを再インストールして起動すると、UE-V は、アプリの既定値にリセットされたアプリの設定を収集し、中央の保存場所に既定の設定をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="31fad-130"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="31fad-131">その他のアプリを実行しているコンピューターで、既定の設定をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="31fad-131"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="31fad-132">この動作は、デスクトップアプリケーションの動作と同じです。</span><span class="sxs-lookup"><span data-stu-id="31fad-132"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="31fad-133">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="31fad-133">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="31fad-134">Outlook 2010 のメール署名のローミング</span><span class="sxs-lookup"><span data-stu-id="31fad-134">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="31fad-135">UE-V は、Outlook 2010 の署名ファイルをデバイス間でローミングします。</span><span class="sxs-lookup"><span data-stu-id="31fad-135">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="31fad-136">ただし、新しいメッセージ、返信、転送の既定の署名オプションは同期されません。</span><span class="sxs-lookup"><span data-stu-id="31fad-136">However, the default signature options for new messages and replies or forwards are not synchronized.</span></span> <span data-ttu-id="31fad-137">この2つの設定は Outlook プロファイルに保存され、UE-V はローミングしません。</span><span class="sxs-lookup"><span data-stu-id="31fad-137">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="31fad-138">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="31fad-138">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="31fad-139">UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="31fad-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="31fad-140">最新のコンピューターには、64ビット版の Microsoft Office をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="31fad-140">We recommend that you install the 64-bit version of Microsoft Office for modern computers.</span></span> <span data-ttu-id="31fad-141">必要なバージョンを特定するには、[ここをクリック](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)します。</span><span class="sxs-lookup"><span data-stu-id="31fad-141">To determine which version you need, [click here](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions).</span></span> <span data-ttu-id="31fad-142">UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="31fad-142">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="31fad-143">たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="31fad-143">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="31fad-144">UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="31fad-144">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="31fad-145">**回避策:**-</span><span class="sxs-lookup"><span data-stu-id="31fad-145">**WORKAROUND:** None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="31fad-146">MSI がローカライズされていない</span><span class="sxs-lookup"><span data-stu-id="31fad-146">MSI’s are not localized</span></span>

<span data-ttu-id="31fad-147">UE-V 2.0 には、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="31fad-147">UE-V 2.0 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="31fad-148">これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="31fad-148">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="31fad-149">英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。</span><span class="sxs-lookup"><span data-stu-id="31fad-149">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="31fad-150">**回避策:**-</span><span class="sxs-lookup"><span data-stu-id="31fad-150">**WORKAROUND:** None</span></span>

### <span data-ttu-id="31fad-151">Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません</span><span class="sxs-lookup"><span data-stu-id="31fad-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="31fad-152">Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="31fad-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="31fad-153">**回避策:** ブックマークを使用して Internet Explorer 9 ブラウザーでキャッシュすると、Favicons に関連付けられたお気に入りが表示されます。</span><span class="sxs-lookup"><span data-stu-id="31fad-153">**WORKAROUND:** Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="31fad-154">ファイル設定のパスはレジストリに保存される</span><span class="sxs-lookup"><span data-stu-id="31fad-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="31fad-155">一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="31fad-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="31fad-156">設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="31fad-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="31fad-157">**回避策:** フォルダーリダイレクションなどの技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターで同じ場所に配置されるようにします。</span><span class="sxs-lookup"><span data-stu-id="31fad-157">**WORKAROUND:** Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="31fad-158">長い設定の記憶域のパスでエラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="31fad-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="31fad-159">設定のストレージパスをできるだけ短くします。</span><span class="sxs-lookup"><span data-stu-id="31fad-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="31fad-160">長いパスを使えば、解決や同期ができなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="31fad-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="31fad-161">UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="31fad-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="31fad-162">このパスは次のように計算されます。設定の保存パス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID) と pkgx。</span><span class="sxs-lookup"><span data-stu-id="31fad-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="31fad-163">この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="31fad-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="31fad-164">操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="31fad-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="31fad-165">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="31fad-165">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="31fad-166">一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="31fad-166">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="31fad-167">ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字 (言語と地域の設定など) は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。</span><span class="sxs-lookup"><span data-stu-id="31fad-167">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="31fad-168">たとえば、Windows 7 と Windows 8 の間では、通貨文字はローミングされません。</span><span class="sxs-lookup"><span data-stu-id="31fad-168">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="31fad-169">**回避策:**-</span><span class="sxs-lookup"><span data-stu-id="31fad-169">**WORKAROUND:** None</span></span>

### <span data-ttu-id="31fad-170">Windows 8 アプリが予期せずに終了した後にアプリを再起動したときに、設定が同期されない</span><span class="sxs-lookup"><span data-stu-id="31fad-170">Windows 8 apps do not sync settings when the app restarts after closing unexpectedly</span></span>

<span data-ttu-id="31fad-171">起動後に Windows 8 アプリが予期せずに終了した場合、アプリケーションを再起動すると、アプリケーションの設定が同期されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="31fad-171">If a Windows 8 app closes unexpectedly soon after startup, settings for the application may not be synchronized when the application is restarted.</span></span>

<span data-ttu-id="31fad-172">**回避策:** Windows 8 アプリを閉じ、UevAppMonitor.exe アプリケーションを終了して再起動し (TaskManager を使用)、Windows 8 アプリを再起動します。</span><span class="sxs-lookup"><span data-stu-id="31fad-172">**WORKAROUND:** Close the Windows 8 app, close and restart the UevAppMonitor.exe application (can use TaskManager), and then restart the Windows 8 app.</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="31fad-173">Ue-v 2 テンプレートを実行しているときに UE-V 1 agent がエラーを生成する</span><span class="sxs-lookup"><span data-stu-id="31fad-173">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="31fad-174">Ue-v 2 設定の場所テンプレートが UE-V 1 エージェントと共にインストールされたコンピューターに配布されている場合、一部の設定はコンピューター間で同期されず、エージェントはイベントログのエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="31fad-174">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="31fad-175">**回避策:** UE-V 1 から UE-V 2 に移行するときに、以前のバージョンのエージェントを実行しているコンピューターが存在する可能性がある場合は、ue-v 2.0 エージェントとテンプレートをサポートするために、個別の UE-V 2.0 カタログを作成します。</span><span class="sxs-lookup"><span data-stu-id="31fad-175">**WORKAROUND:** When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.0 catalog to support the UE-V 2.0 Agent and templates.</span></span>

## <span data-ttu-id="31fad-176">UE-V 2.0 の修正プログラムとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="31fad-176">Hotfixes and Knowledge Base articles for UE-V 2.0</span></span>


<span data-ttu-id="31fad-177">このセクションには、UE-V 2.0 の修正プログラムとサポート技術情報の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="31fad-177">This section contains hotfixes and KB articles for UE-V 2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="31fad-178">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="31fad-178">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="31fad-179">タイトル</span><span class="sxs-lookup"><span data-stu-id="31fad-179">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="31fad-180">リンク</span><span class="sxs-lookup"><span data-stu-id="31fad-180">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-181">2927019</span><span class="sxs-lookup"><span data-stu-id="31fad-181">2927019</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-182">Microsoft User Experience Virtualization 2.0 の修正プログラムパッケージ1</span><span class="sxs-lookup"><span data-stu-id="31fad-182">Hotfix Package 1 for Microsoft User Experience Virtualization 2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)"><span data-ttu-id="31fad-183">support.microsoft.com/kb/2927019</span><span class="sxs-lookup"><span data-stu-id="31fad-183">support.microsoft.com/kb/2927019</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-184">2903501</span><span class="sxs-lookup"><span data-stu-id="31fad-184">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-185">UE-V: user Experience Virtualization (UE-V) ユーザープロファイルとの互換性</span><span class="sxs-lookup"><span data-stu-id="31fad-185">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="31fad-186">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-186">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-187">2770042</span><span class="sxs-lookup"><span data-stu-id="31fad-187">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-188">UE-V のレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="31fad-188">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="31fad-189">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-189">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-190">2847017</span><span class="sxs-lookup"><span data-stu-id="31fad-190">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-191">Internet Explorer によってレプリケートされた UE-V の設定</span><span class="sxs-lookup"><span data-stu-id="31fad-191">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="31fad-192">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-192">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-193">2930271</span><span class="sxs-lookup"><span data-stu-id="31fad-193">2930271</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-194">Microsoft UE-V でのローミング Outlook 署名の制限事項について</span><span class="sxs-lookup"><span data-stu-id="31fad-194">Understanding the limitations of roaming Outlook signatures in Microsoft UE-V</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)"><span data-ttu-id="31fad-195">support.microsoft.com/kb/2930271/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-195">support.microsoft.com/kb/2930271/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-196">2769631</span><span class="sxs-lookup"><span data-stu-id="31fad-196">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-197">破損した UE-V のインストールを修復する方法</span><span class="sxs-lookup"><span data-stu-id="31fad-197">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="31fad-198">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-198">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-199">2850989</span><span class="sxs-lookup"><span data-stu-id="31fad-199">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-200">Microsoft UE-V での MAPI プロファイルの移行はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="31fad-200">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="31fad-201">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-201">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-202">2769586</span><span class="sxs-lookup"><span data-stu-id="31fad-202">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-203">UE-V ローミング: 空のフォルダーとレジストリキー</span><span class="sxs-lookup"><span data-stu-id="31fad-203">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="31fad-204">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-204">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-205">2782997</span><span class="sxs-lookup"><span data-stu-id="31fad-205">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-206">Microsoft User Experience Virtualization (UE-V) でデバッグログを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="31fad-206">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="31fad-207">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-207">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-208">2769570</span><span class="sxs-lookup"><span data-stu-id="31fad-208">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-209">UE-V で RDS または VDI セッションのテーマが更新されない</span><span class="sxs-lookup"><span data-stu-id="31fad-209">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="31fad-210">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-210">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-211">2901856</span><span class="sxs-lookup"><span data-stu-id="31fad-211">2901856</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-212">UE-V を有効にしているコンピューターで再起動すると、アプリケーションの設定が同期されない</span><span class="sxs-lookup"><span data-stu-id="31fad-212">Application settings do not sync after you force a restart on a UE-V-enabled computer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)"><span data-ttu-id="31fad-213">support.microsoft.com/kb/2901856/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-213">support.microsoft.com/kb/2901856/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-214">2850582</span><span class="sxs-lookup"><span data-stu-id="31fad-214">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-215">App-v アプリケーションで Microsoft ユーザーエクスペリエンス仮想化を使用する方法</span><span class="sxs-lookup"><span data-stu-id="31fad-215">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="31fad-216">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-216">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="31fad-217">3041879</span><span class="sxs-lookup"><span data-stu-id="31fad-217">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-218">Microsoft User Experience Virtualization の現在のファイルバージョン</span><span class="sxs-lookup"><span data-stu-id="31fad-218">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="31fad-219">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-219">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="31fad-220">2843592</span><span class="sxs-lookup"><span data-stu-id="31fad-220">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="31fad-221">ユーザーエクスペリエンスの仮想化と高可用性に関する情報</span><span class="sxs-lookup"><span data-stu-id="31fad-221">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="31fad-222">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="31fad-222">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





