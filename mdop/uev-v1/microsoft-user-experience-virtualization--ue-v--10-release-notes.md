---
title: Microsoft User Experience Virtualization (UE-V) 1.0 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 1.0 リリース ノート
author: dansimp
ms.assetid: 920f3fae-e9b5-4b94-beda-32c19d31e94b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9f9942eef7ea84cf7010a0c0173427827a512216
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812490"
---
# <span data-ttu-id="5977f-103">Microsoft User Experience Virtualization (UE-V) 1.0 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="5977f-103">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>


<span data-ttu-id="5977f-104">Microsoft User Experience Virtualization (UE-V) のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="5977f-104">To search Microsoft User Experience Virtualization (UE-V) release notes, press Ctrl+F.</span></span>

<span data-ttu-id="5977f-105">UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="5977f-106">リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="5977f-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="5977f-107">これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="5977f-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="5977f-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="5977f-109">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="5977f-109">Providing feedback</span></span>


<span data-ttu-id="5977f-110">フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="5977f-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="5977f-111">ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。</span><span class="sxs-lookup"><span data-stu-id="5977f-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="5977f-112">UE-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="5977f-112">UE-V known issues</span></span>


<span data-ttu-id="5977f-113">このセクションには、ユーザーエクスペリエンスの仮想化のリリースノートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="5977f-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="5977f-114">同じコンピューター上の App-v とネイティブアプリケーション間でのレジストリ設定の同期が失敗する</span><span class="sxs-lookup"><span data-stu-id="5977f-114">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="5977f-115">Application Virtualization (App-v) アプリケーションとネイティブインストールアプリケーション (.msi ファイルを使用してインストールされているもの) の両方で使用できるアプリケーションがコンピューターにある場合は、これらのテクノロジの間でレジストリベースの設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="5977f-115">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application (installed with an .msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="5977f-116">対応策: この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="5977f-116">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="5977f-117">Windows 8 の設定の同期に失敗します。 "昇格:: filesystem:: 存在:: ユーザー名またはパスワードが間違っています" というエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="5977f-117">Windows 8 setting synchronization fails with error: "boost::filesystem::exists::Incorrect user name or password"</span></span>

<span data-ttu-id="5977f-118">Windows®8オペレーティングシステムの設定の同期に失敗し、次のエラーメッセージが表示されます:**ブースト:: filesystem:: exists:: ユーザー名またはパスワードが正しく**ありません。</span><span class="sxs-lookup"><span data-stu-id="5977f-118">The Windows® 8 operating system settings synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="5977f-119">操作ログイベントを確認するには、**イベントビューアー**を開き、[**アプリケーションとサービスログ**] に移動し  /  **Microsoft**  /  ます。 Microsoft**User Experience Virtualization**  /  **Logging**  /  **operational**</span><span class="sxs-lookup"><span data-stu-id="5977f-119">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="5977f-120">UE-V の設定の保存場所に使用されるネットワーク共有は、ユーザーと同じ Active Directory ドメイン内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-120">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span> <span data-ttu-id="5977f-121">そうしないと、"ユーザー名またはパスワードが間違っています" というエラーが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-121">Otherwise, the following error might occur: "Incorrect user name or password".</span></span>

<span data-ttu-id="5977f-122">回避策: ユーザーと同じ Active Directory ドメインのネットワーク共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="5977f-122">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="5977f-123">.</span><span class="sxs-lookup"><span data-stu-id="5977f-123">.</span></span>

### <span data-ttu-id="5977f-124">Outlook 2010 のメール署名のローミング</span><span class="sxs-lookup"><span data-stu-id="5977f-124">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="5977f-125">UE-V は、Outlook 2010 の署名ファイルをデバイス間でローミングします。</span><span class="sxs-lookup"><span data-stu-id="5977f-125">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="5977f-126">ただし、新規メッセージと返信/転送の既定の署名オプションは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5977f-126">However, the default signature options for new messages and replies/forwards are not.</span></span><span data-ttu-id="5977f-127">この2つの設定は Outlook プロファイルに保存され、UE-V はローミングしません。</span><span class="sxs-lookup"><span data-stu-id="5977f-127"> These two settings are stored in the Outlook profile, which UE-Vdoes not roam.</span></span>

<span data-ttu-id="5977f-128">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="5977f-128">WORKAROUND: None.</span></span>

### <span data-ttu-id="5977f-129">低速リンクモードで実行しているときに同期設定が予期した間隔で同期されない</span><span class="sxs-lookup"><span data-stu-id="5977f-129">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="5977f-130">[通常の条件] の [設定の保存場所] は、高速リンクネットワーク接続を介して使用できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-130">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="5977f-131">低速リンクモードでは、同期は定期的にのみ行われます。</span><span class="sxs-lookup"><span data-stu-id="5977f-131">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="5977f-132">既定では、低速リンクモードの同期スケジュールは、360分ごとに設定されます。</span><span class="sxs-lookup"><span data-stu-id="5977f-132">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="5977f-133">対応策: 低速リンクモードのコンピューターのバックグラウンド同期の頻度を変更するには、**オフラインファイル**のバックグラウンド同期ポリシーのグループポリシーを構成できます。</span><span class="sxs-lookup"><span data-stu-id="5977f-133">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="5977f-134">特殊文字が同期しない</span><span class="sxs-lookup"><span data-stu-id="5977f-134">Special characters do not synchronize</span></span>

<span data-ttu-id="5977f-135">一部の文字 (通貨記号など) は、UE-V agent を実行している Windows 7 と Windows 8 コンピューターでは同期されません。</span><span class="sxs-lookup"><span data-stu-id="5977f-135">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="5977f-136">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="5977f-136">WORKAROUND: None.</span></span>

### <span data-ttu-id="5977f-137">UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5977f-137">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="5977f-138">32ビットと64ビットの両方のオペレーティングシステムに対して、32ビット版の Microsoft Office をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5977f-138">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="5977f-139">必要な Microsoft Office のバージョンを選択するには、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="5977f-139">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="5977f-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="5977f-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="5977f-141">UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="5977f-141">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="5977f-142">たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="5977f-142">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="5977f-143">UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="5977f-143">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="5977f-144">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="5977f-144">WORKAROUND: None</span></span>

### <span data-ttu-id="5977f-145">設定の保存場所を持つ共有の他のフォルダーは、低速接続モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5977f-145">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="5977f-146">設定ストアの共有は、常に利用可能にする必要がある他のフォルダーに使用されるネットワーク共有上に配置しないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-146">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="5977f-147">設定の保存場所をホストするネットワーク共有が低速接続モードになると、利用可能なフォルダーは [設定の保存場所] フォルダーのみになります。</span><span class="sxs-lookup"><span data-stu-id="5977f-147">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="5977f-148">共有上の他のフォルダーは、低速接続モードでは使用できません。</span><span class="sxs-lookup"><span data-stu-id="5977f-148">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="5977f-149">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="5977f-149">Workaround: None</span></span>

### <span data-ttu-id="5977f-150">Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません</span><span class="sxs-lookup"><span data-stu-id="5977f-150">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="5977f-151">Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="5977f-151">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="5977f-152">回避策: Internet Explorer 9 ブラウザーでブックマークを使用してキャッシュすると、Favicons が関連するお気に入りと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="5977f-152">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="5977f-153">ファイル設定のパスはレジストリに保存される</span><span class="sxs-lookup"><span data-stu-id="5977f-153">File settings paths are stored in registry</span></span>

<span data-ttu-id="5977f-154">一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="5977f-154">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="5977f-155">設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-155">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="5977f-156">回避策: フォルダーリダイレクションまたはその他の技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターの同じ場所に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="5977f-156">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="5977f-157">260文字を超えるパスはサポートされない</span><span class="sxs-lookup"><span data-stu-id="5977f-157">Paths longer than 260 characters are not supported</span></span>

<span data-ttu-id="5977f-158">260文字より長い設定記憶域のパスはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5977f-158">Settings storage paths that are longer than 260 characters are not supported.</span></span> <span data-ttu-id="5977f-159">UE-V 設定パッケージをコピーして、260文字を超える設定記憶域のパスを作成すると失敗し、UE-V の操作イベントログで次の例外メッセージが生成されます: **\ [ブースト:: filesystem:: copy \ _file: 指定されたパスが見つかりません**。</span><span class="sxs-lookup"><span data-stu-id="5977f-159">Copying the UE-V settings packages to settings storage paths that are longer than 260 characters will fail and generate the following exception message in the UE-V operational event log: **\[boost::filesystem::copy\_file: The system cannot find the path specified\]**.</span></span> <span data-ttu-id="5977f-160">操作ログイベントを確認するには、**イベントビューアー**を開き、[**アプリケーションとサービスログ**] に移動し  /  **Microsoft**  /  ます。 Microsoft**User Experience Virtualization**  /  **Logging**  /  **operational**</span><span class="sxs-lookup"><span data-stu-id="5977f-160">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span>

<span data-ttu-id="5977f-161">260文字より長いファイル設定のパスは、現在サポートされていません。</span><span class="sxs-lookup"><span data-stu-id="5977f-161">File settings paths that are longer than 260 characters are not currently supported.</span></span> <span data-ttu-id="5977f-162">UE-V 設定の場所テンプレートで参照されているファイル設定は、260文字よりも長いディレクトリパスに配置することはできません。</span><span class="sxs-lookup"><span data-stu-id="5977f-162">File settings that are referenced in UE-V settings location templates cannot be located in a directory path that is longer than 260 characters.</span></span>

<span data-ttu-id="5977f-163">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="5977f-163">WORKAROUND: None.</span></span>

### <span data-ttu-id="5977f-164">UE-V agent がログアウトまたはログインしたときに遅延する</span><span class="sxs-lookup"><span data-stu-id="5977f-164">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="5977f-165">オフラインファイルで低速リンクが設定されていることがわかっている場合は、ログアウトまたはログインが遅れる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-165">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="5977f-166">オフラインファイル機能は、現在のネットワークの状態を検出するまでに最大3分かかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="5977f-166">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="5977f-167">コンピューターが低速リンクに接続されていることが確認される前にログオンまたはシャットダウンが行われると、ローカルキャッシュではなく、UE-V 設定パッケージがサーバーに送信されます。</span><span class="sxs-lookup"><span data-stu-id="5977f-167">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="5977f-168">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="5977f-168">WORKAROUND: None.</span></span>

### <span data-ttu-id="5977f-169">Windows 8 でオペレーティングシステム設定をローミングしようとすると、設定が競合する</span><span class="sxs-lookup"><span data-stu-id="5977f-169">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="5977f-170">Windows 8 では、Microsoft アカウントの同期が、オペレーティングシステム設定用の UE-V と共に有効になっている場合、適用される設定に一貫性がないことがあります。</span><span class="sxs-lookup"><span data-stu-id="5977f-170">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="5977f-171">回避策: 次のいずれかの操作を行います。</span><span class="sxs-lookup"><span data-stu-id="5977f-171">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="5977f-172">UE-V を使用してオペレーティングシステムの設定をローミングしている場合は、Microsoft アカウントの同期を無効にする</span><span class="sxs-lookup"><span data-stu-id="5977f-172">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="5977f-173">オペレーティングシステム設定で UE-V を無効にする</span><span class="sxs-lookup"><span data-stu-id="5977f-173">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="5977f-174">一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="5977f-174">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="5977f-175">ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。</span><span class="sxs-lookup"><span data-stu-id="5977f-175">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="5977f-176">たとえば、通貨文字は Windows 7 から Windows 7 にのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="5977f-176">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="5977f-177">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="5977f-177">WORKAROUND: None</span></span>

### <span data-ttu-id="5977f-178">Internet explorer のブックマークが Internet Explorer の smartbar に表示されない</span><span class="sxs-lookup"><span data-stu-id="5977f-178">Internet Explorer bookmarks do not appear in the Internet Explorer smartbar</span></span>

<span data-ttu-id="5977f-179">Internet Explorer のブックマークを1台のコンピューターから別のコンピューターに移動しても、2台目のコンピューターのインデックスは更新できないので、アドレスバーに入力すると、お気に入りはコンピューター2の検索結果として表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="5977f-179">When Internet Explorer bookmarks roam from one computer to another computer, the index on the second computer cannot update, so when typing in the address bar, the favorite will not appear as a possible search result on computer 2.</span></span>

<span data-ttu-id="5977f-180">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="5977f-180">WORKAROUND: None</span></span>

 

 





