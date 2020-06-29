---
title: Microsoft User Experience Virtualization (UE-V) 1.0 SP1 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 1.0 SP1 リリース ノート
author: dansimp
ms.assetid: 447fae0c-fe87-4d1c-b616-6f92fbdaf6d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8584999d9fdbdfccc3e9b2b1486cb97635475747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812483"
---
# <span data-ttu-id="71c4c-103">Microsoft User Experience Virtualization (UE-V) 1.0 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="71c4c-103">Microsoft User Experience Virtualization (UE-V) 1.0 SP1 Release Notes</span></span>


<span data-ttu-id="71c4c-104">Microsoft User Experience Virtualization (UE-V) 1.0 Service Pack 1 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="71c4c-104">To search Microsoft User Experience Virtualization (UE-V) 1.0 Service Pack 1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="71c4c-105">UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="71c4c-106">リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="71c4c-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="71c4c-107">これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="71c4c-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="71c4c-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="71c4c-109">UE-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="71c4c-109">UE-V known issues</span></span>


<span data-ttu-id="71c4c-110">このセクションには、ユーザーエクスペリエンスの仮想化 1.0 SP1 のリリースノートが記載されています。</span><span class="sxs-lookup"><span data-stu-id="71c4c-110">This section contains release notes for User Experience Virtualization 1.0 SP1.</span></span>

### <span data-ttu-id="71c4c-111">同じコンピューター上の App-v とネイティブアプリケーション間でのレジストリ設定の同期が失敗する</span><span class="sxs-lookup"><span data-stu-id="71c4c-111">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="71c4c-112">Application Virtualization (App-v) アプリケーションと、Windows Installer (.msi ファイル) と共にインストールされたネイティブインストールアプリケーションの両方を通じて使用できるアプリケーションがコンピューターにある場合、レジストリベースの設定はテクノロジ間で同期されません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-112">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application installed with a Windows Installer (.msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="71c4c-113">対応策: この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-113">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="windows-8-setting-synchronization-fails-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="71c4c-114">ネットワーク共有がユーザーのドメイン外にある場合、Windows 8 の設定の同期が失敗する</span><span class="sxs-lookup"><span data-stu-id="71c4c-114">Windows 8 setting synchronization fails when network share is outside user’s domain</span></span>

<span data-ttu-id="71c4c-115">Windows®8がオペレーティングシステム設定の同期を実行しようとすると、synchrnization が次のエラーメッセージを表示して失敗します:**昇格:: filesystem:: 存在:: ユーザー名またはパスワードが正しく**ありません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-115">When Windows® 8 attempts operating system settings synchronization, the synchrnization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="71c4c-116">このエラーは、ネットワーク共有がユーザーのドメイン外であることを示している可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-116">This error can indicate that the network share is outside the user’s domain.</span></span> <span data-ttu-id="71c4c-117">操作ログイベントを確認するには、**イベントビューアー**を開き、[**アプリケーションとサービスログ**] に移動し  /  **Microsoft**  /  ます。 Microsoft**User Experience Virtualization**  /  **Logging**  /  **operational**</span><span class="sxs-lookup"><span data-stu-id="71c4c-117">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="71c4c-118">UE-V の設定の保存場所に使用されるネットワーク共有は、ユーザーと同じ Active Directory ドメイン内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-118">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span>

<span data-ttu-id="71c4c-119">回避策: ユーザーと同じ Active Directory ドメインのネットワーク共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="71c4c-119">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="71c4c-120">.</span><span class="sxs-lookup"><span data-stu-id="71c4c-120">.</span></span>

### <span data-ttu-id="71c4c-121">Outlook 2010 のメール署名のローミング</span><span class="sxs-lookup"><span data-stu-id="71c4c-121">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="71c4c-122">UE-V は、Outlook 2010 の署名ファイルをデバイス間でローミングします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-122">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="71c4c-123">ただし、新規メッセージと返信/転送の既定の署名オプションはローミングされません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-123">However, the default signature options for new messages and replies/forwards are not roamed.</span></span> <span data-ttu-id="71c4c-124">この2つの設定は Outlook プロファイルに保存され、UE-V はローミングしません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-124">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="71c4c-125">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="71c4c-125">WORKAROUND: None.</span></span>

### <span data-ttu-id="71c4c-126">低速リンクモードで実行しているときに同期設定が予期した間隔で同期されない</span><span class="sxs-lookup"><span data-stu-id="71c4c-126">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="71c4c-127">[通常の条件] の [設定の保存場所] は、高速リンクネットワーク接続を介して使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-127">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="71c4c-128">低速リンクモードでは、同期は定期的にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-128">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="71c4c-129">既定では、低速リンクモードの同期スケジュールは、360分ごとに設定されます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-129">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="71c4c-130">対応策: 低速リンクモードのコンピューターのバックグラウンド同期の頻度を変更するには、**オフラインファイル**のバックグラウンド同期ポリシーのグループポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-130">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="71c4c-131">特殊文字が同期しない</span><span class="sxs-lookup"><span data-stu-id="71c4c-131">Special characters do not synchronize</span></span>

<span data-ttu-id="71c4c-132">一部の文字 (通貨記号など) は、UE-V agent を実行している Windows 7 と Windows 8 コンピューターでは同期されません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-132">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="71c4c-133">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="71c4c-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="71c4c-134">UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-134">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="71c4c-135">32ビットと64ビットの両方のオペレーティングシステムに対して、32ビット版の Microsoft Office をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-135">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="71c4c-136">必要な Microsoft Office のバージョンを選択するには、ここ () をクリックし [http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623) ます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-136">To choose the Microsoft Office version that you need, click here ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="71c4c-137">UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="71c4c-137">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="71c4c-138">たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-138">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="71c4c-139">UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="71c4c-140">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="71c4c-140">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="71c4c-141">MSI がローカライズされていない</span><span class="sxs-lookup"><span data-stu-id="71c4c-141">MSI’s are not localized</span></span>

<span data-ttu-id="71c4c-142">UE-V 1.0 SP1 には、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="71c4c-142">UE-V 1.0 SP1 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="71c4c-143">これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-143">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="71c4c-144">英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-144">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="71c4c-145">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="71c4c-145">WORKAROUND: None</span></span>

### <span data-ttu-id="71c4c-146">設定の保存場所を持つ共有の他のフォルダーは、低速接続モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-146">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="71c4c-147">設定ストアの共有は、常に利用可能にする必要がある他のフォルダーに使用されるネットワーク共有上に配置しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-147">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="71c4c-148">設定の保存場所をホストするネットワーク共有が低速接続モードになると、利用可能なフォルダーは [設定の保存場所] フォルダーのみになります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-148">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="71c4c-149">共有上の他のフォルダーは、低速接続モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-149">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="71c4c-150">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="71c4c-150">Workaround: None</span></span>

### <span data-ttu-id="71c4c-151">Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません</span><span class="sxs-lookup"><span data-stu-id="71c4c-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="71c4c-152">Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="71c4c-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="71c4c-153">回避策: Internet Explorer 9 ブラウザーでブックマークを使用してキャッシュすると、Favicons が関連するお気に入りと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-153">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="71c4c-154">ファイル設定のパスはレジストリに保存される</span><span class="sxs-lookup"><span data-stu-id="71c4c-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="71c4c-155">一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="71c4c-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="71c4c-156">設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="71c4c-157">回避策: フォルダーリダイレクションまたはその他の技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターの同じ場所に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="71c4c-157">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="71c4c-158">長い設定の記憶域のパスでエラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="71c4c-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="71c4c-159">設定のストレージパスをできるだけ短くします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="71c4c-160">長いパスを使えば、解決や同期ができなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="71c4c-161">UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="71c4c-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="71c4c-162">このパスは次のように計算されます。設定記憶域のパス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID)。</span><span class="sxs-lookup"><span data-stu-id="71c4c-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID).</span></span> <span data-ttu-id="71c4c-163">この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="71c4c-164">操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="71c4c-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="71c4c-165">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="71c4c-165">WORKAROUND: None.</span></span>

### <span data-ttu-id="71c4c-166">UE-V agent がログアウトまたはログインしたときに遅延する</span><span class="sxs-lookup"><span data-stu-id="71c4c-166">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="71c4c-167">オフラインファイルで低速リンクが設定されていることがわかっている場合は、ログアウトまたはログインが遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-167">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="71c4c-168">オフラインファイル機能は、現在のネットワークの状態を検出するまでに最大3分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-168">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="71c4c-169">コンピューターが低速リンクに接続されていることが確認される前にログオンまたはシャットダウンが行われると、ローカルキャッシュではなく、UE-V 設定パッケージがサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-169">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="71c4c-170">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="71c4c-170">WORKAROUND: None.</span></span>

### <span data-ttu-id="71c4c-171">Windows 8 でオペレーティングシステム設定をローミングしようとすると、設定が競合する</span><span class="sxs-lookup"><span data-stu-id="71c4c-171">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="71c4c-172">Windows 8 では、Microsoft アカウントの同期が、オペレーティングシステム設定用の UE-V と共に有効になっている場合、適用される設定に一貫性がないことがあります。</span><span class="sxs-lookup"><span data-stu-id="71c4c-172">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="71c4c-173">回避策: 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="71c4c-173">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="71c4c-174">UE-V を使用してオペレーティングシステムの設定をローミングしている場合は、Microsoft アカウントの同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="71c4c-174">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="71c4c-175">オペレーティングシステム設定で UE-V を無効にする</span><span class="sxs-lookup"><span data-stu-id="71c4c-175">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="71c4c-176">一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-176">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="71c4c-177">ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。</span><span class="sxs-lookup"><span data-stu-id="71c4c-177">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="71c4c-178">たとえば、通貨文字は Windows 7 から Windows 7 にのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="71c4c-178">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="71c4c-179">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="71c4c-179">WORKAROUND: None</span></span>

 

 





