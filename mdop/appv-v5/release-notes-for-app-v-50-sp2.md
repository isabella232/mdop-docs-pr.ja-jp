---
title: App-V 5.0 SP2 リリース ノート
description: App-V 5.0 SP2 リリース ノート
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813330"
---
# <span data-ttu-id="49b87-103">App-V 5.0 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="49b87-103">Release Notes for App-V 5.0 SP2</span></span>


**<span data-ttu-id="49b87-104">これらのリリースノートで特定の問題を検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="49b87-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="49b87-105">App-v 5.0 SP2 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="49b87-105">Read these release notes thoroughly before you install App-V 5.0 SP2.</span></span>

<span data-ttu-id="49b87-106">これらのリリースノートには、App-v 5.0 SP2 を正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="49b87-106">These release notes contain information that is required to successfully install App-V 5.0 SP2.</span></span> <span data-ttu-id="49b87-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="49b87-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="49b87-108">これらのリリースノートと他の App-v 5.0 ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-108">If there are differences between these release notes and other App-V 5.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="49b87-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="49b87-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="49b87-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="49b87-110">About the Product Documentation</span></span>


<span data-ttu-id="49b87-111">App-v 5.0 ドキュメントの詳細については、Microsoft TechNet の「App-v 5.0 のホームページ」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="49b87-111">For information about App-V 5.0 documentation, see the App-V 5.0 home page on Microsoft TechNet.</span></span>

## <span data-ttu-id="49b87-112">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="49b87-112">Provide Feedback</span></span>


<span data-ttu-id="49b87-113">弊社では、App-v 5.0 についてご意見をお寄せしています。</span><span class="sxs-lookup"><span data-stu-id="49b87-113">We are interested in your feedback on App-V 5.0.</span></span> <span data-ttu-id="49b87-114">にフィードバックを送信でき <mdopdocs@microsoft.com> ます。</span><span class="sxs-lookup"><span data-stu-id="49b87-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="49b87-115">**注** このメールアドレスはサポートチャネルではありませんが、お客様のフィードバックは、今後のドキュメントや製品リリースの将来の変更を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="49b87-115">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="49b87-116">MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49b87-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="49b87-117">新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="49b87-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="49b87-118">アプリケーションの仮想化 5.0 SP2 の修正プログラムパッケージ4の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49b87-118">Known Issues with Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>


### <span data-ttu-id="49b87-119">Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をアンインストールした後、パッケージが機能しなくなる</span><span class="sxs-lookup"><span data-stu-id="49b87-119">Packages stop working after you uninstall Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>

<span data-ttu-id="49b87-120">Application virtualization 5.0 SP2 の修正プログラムパッケージ4を適用したときに公開されるパッケージは、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4が削除された場合に機能しなくなります。</span><span class="sxs-lookup"><span data-stu-id="49b87-120">Packages published when Hotfix Package 4 for Application Virtualization 5.0 SP2 is applied stop working when Hotfix Package 4 for Application Virtualization 5.0 SP2 is removed.</span></span>

<span data-ttu-id="49b87-121">ところ</span><span class="sxs-lookup"><span data-stu-id="49b87-121">WORKAROUND:</span></span>

<span data-ttu-id="49b87-122">次のフォルダーが存在する場合は、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-122">If the following folder exists, then you must delete it:</span></span>

<span data-ttu-id="49b87-123">**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **クライアント**  \\ **VFS**  \\ 公開された各パッケージの\*\* &lt; パッケージ ID &gt; \*\* 。</span><span class="sxs-lookup"><span data-stu-id="49b87-123">**%localappdata%** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **VFS** \\ **&lt;package ID&gt;** for each package that was published.</span></span>

<span data-ttu-id="49b87-124">**注** このフォルダーを削除するには、管理者特権が必要です。</span><span class="sxs-lookup"><span data-stu-id="49b87-124">**Note** You must have elevated privileges to delete this folder.</span></span>

 

<span data-ttu-id="49b87-125">スクリプトを使用するには、コンピューター上の各ユーザーアカウントと、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をインストールした後に公開された各パッケージ id について、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="49b87-125">To use a script, for each user account on the computer and for each package id that was published after installing Hotfix Package 4 for Application Virtualization 5.0 SP2:</span></span>

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   <span data-ttu-id="49b87-126">ショートカットは、前のセクションのディレクトリからフォルダーを削除した後でも、ユーザーセッションのままになり、ショートカットをクリックしてアプリケーションを再実行することができます。</span><span class="sxs-lookup"><span data-stu-id="49b87-126">The shortcuts will remain with the user sessions even after deleting the folder from the directory in the previous section, so you can click on the shortcut to run the application again.</span></span> <span data-ttu-id="49b87-127">アプリケーションを再公開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49b87-127">There is no need to re-publish the application.</span></span>

-   <span data-ttu-id="49b87-128">この問題は、Microsoft 2013 など、公開されたパッケージとグローバルに公開されたパッケージの両方に対して発生します。</span><span class="sxs-lookup"><span data-stu-id="49b87-128">This issue happens for both user published packaged and globally published packages for example, Microsoft Office2013.</span></span> <span data-ttu-id="49b87-129">どちらの種類のパッケージでも、フォルダーを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-129">The folder must be deleted for both types of packages.</span></span>

-   <span data-ttu-id="49b87-130">ローミングアプリデータ (**% appdata%**) の VFS フォルダーを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="49b87-130">You do not need to delete the VFS folder in the Roaming app data (**%appdata%**).</span></span> <span data-ttu-id="49b87-131">**% Localappdata%** のみを削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-131">Only the **%localappdata%** must be deleted.</span></span>

### <span data-ttu-id="49b87-132">Microsoft Office 統合で間違ったファイルシステムの場所が参照されている</span><span class="sxs-lookup"><span data-stu-id="49b87-132">Microsoft Office integration points to wrong file system location</span></span>

<span data-ttu-id="49b87-133">Microsoft Office の統合で、誤ったファイルシステムの場所 (Groove.exe のエラーメッセージ) が表示されます。</span><span class="sxs-lookup"><span data-stu-id="49b87-133">Microsoft Office integration points to wrong file system location (Groove.exe error message).</span></span>

<span data-ttu-id="49b87-134">ところ</span><span class="sxs-lookup"><span data-stu-id="49b87-134">WORKAROUND:</span></span>

<span data-ttu-id="49b87-135">以下の方法のうちのいずれか 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="49b87-135">Use one of the following methods:</span></span>

1.  <span data-ttu-id="49b87-136">アップグレード後に、スタートアップフォルダーのショートカットを削除します。</span><span class="sxs-lookup"><span data-stu-id="49b87-136">Delete the shortcut in the start-up folder after upgrade.</span></span>

2.  <span data-ttu-id="49b87-137">スクリプトを使用して、スタートアップフォルダーのショートカットを変更します。</span><span class="sxs-lookup"><span data-stu-id="49b87-137">Change the shortcut in the start-up folder using a script.</span></span>

3.  <span data-ttu-id="49b87-138">展開構成ファイルを使用して、統合ルートへのショートカットのターゲットを指定します。</span><span class="sxs-lookup"><span data-stu-id="49b87-138">Use the deployment configuration file to specify the shortcut target to the integration root.</span></span>

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> <span data-ttu-id="49b87-139">アプリケーションの仮想化 5.0 SP2 インストーラーの修正プログラムパッケージ4には長い時間がかかることがある</span><span class="sxs-lookup"><span data-stu-id="49b87-139">Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can take a long time</span></span>

<span data-ttu-id="49b87-140">Application Virtualization 5.0 SP2 インストーラーの修正プログラムパッケージ4では、既存のパッケージキャッシュに保存されているファイルの数によって、時間がかかる場合があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-140">The Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can potentially take a long time depending on how many files are stored in the existing package cache.</span></span>

<span data-ttu-id="49b87-141">アプリケーションの仮想化 5.0 SP2 インストールの修正プログラムパッケージ4で関連付けられているパッケージのセキュリティ記述子を更新すると、インストールにかかる時間が大幅に大きく影響します。</span><span class="sxs-lookup"><span data-stu-id="49b87-141">Updating associated package security descriptors during the Hotfix Package 4 for Application Virtualization 5.0 SP2 installation has a significant impact on how long it takes the installation will take.</span></span> <span data-ttu-id="49b87-142">以前は、インストールのインストールは期間内に標準でした。</span><span class="sxs-lookup"><span data-stu-id="49b87-142">Previously, the installation install was standard in duration.</span></span> <span data-ttu-id="49b87-143">ただし、これは、パッケージキャッシュにステージングしたファイルの数に依存するようになりました。</span><span class="sxs-lookup"><span data-stu-id="49b87-143">However, it now depends on how many files you have staged in the package cache.</span></span>

<span data-ttu-id="49b87-144">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="49b87-144">WORKAROUND: None</span></span>

### <span data-ttu-id="49b87-145">JIT パッケージを使用している場合に、Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をアンインストールできない</span><span class="sxs-lookup"><span data-stu-id="49b87-145">Uninstalling Hotfix Package 4 for Application Virtualization 5.0 SP2 fails if JIT-V package is in use</span></span>

<span data-ttu-id="49b87-146">Application Virtualization 5.0 SP2 の修正プログラムパッケージ4をインストールして、ジャストインタイム仮想化 (JIT) を使用しているときに、この修正プログラムをアンインストールしようとすると、次のすべての条件に該当する場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="49b87-146">If you install Hotfix Package 4 for Application Virtualization 5.0 SP2 and then try to uninstall the hotfix when just-in-time virtualization (JIT-V) is being used, the operation will fail if all of the following conditions are true:</span></span>

-   <span data-ttu-id="49b87-147">Windows Installer ファイル (.msi) を使ってインストールした後、Microsoft インストーラーの修正プログラムファイル (.msp) を使用して更新プログラムを適用します。</span><span class="sxs-lookup"><span data-stu-id="49b87-147">You installed by using a Windows Installer file (.msi), and then you apply updates by using a Microsoft Installer Patch File (.msp).</span></span>

-   <span data-ttu-id="49b87-148">コントロールパネルの [プログラムの追加と削除] を使用して、更新プログラムをアンインストールしようとしています。</span><span class="sxs-lookup"><span data-stu-id="49b87-148">You try to uninstall an update by using the Add or Remove Programs item in Control Panel.</span></span>

-   <span data-ttu-id="49b87-149">コンピューターで JIT 対応パッケージが実行されています。</span><span class="sxs-lookup"><span data-stu-id="49b87-149">A JIT-V-enabled package is running on the computer.</span></span>

<span data-ttu-id="49b87-150">回避策: 次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="49b87-150">WORKAROUND: Complete the following steps:</span></span>

1.  <span data-ttu-id="49b87-151">Windows PowerShell を開き、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="49b87-151">Open Windows PowerShell and run the following commands:</span></span>

    -   **<span data-ttu-id="49b87-152">インポート-モジュール appvclient</span><span class="sxs-lookup"><span data-stu-id="49b87-152">Import-module appvclient</span></span>**

    -   **<span data-ttu-id="49b87-153">Get-AppvClientPackage |AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="49b87-153">Get-AppvClientPackage | Stop-AppvClientPackage</span></span>**

2.  <span data-ttu-id="49b87-154">[プログラムの追加と削除を使用して更新プログラムをアンインストールする。</span><span class="sxs-lookup"><span data-stu-id="49b87-154">Uninstall the update using Add or Remove Programs.</span></span>

## <span data-ttu-id="49b87-155">App-v 5.0 SP2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="49b87-155">Known Issues with App-V 5.0 SP2</span></span>


### <a href="" id="bkmk-folderredirection"></a><span data-ttu-id="49b87-156">App-v クライアントフォルダーリダイレクションが、ファイルを% AppData% から% に移動することができない場合がある</span><span class="sxs-lookup"><span data-stu-id="49b87-156">App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%</span></span>

<span data-ttu-id="49b87-157">% AppData% が、フォルダーリダイレクション用に構成した共有ネットワークフォルダーである場合、コンピューターを切り替えるか、またはログオフしてもう一度ログインするときに、エンドユーザーが AppData (ローミング) に加えた変更が失われる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-157">When %AppData% is a shared network folder that you have configured for folder redirection, the changes that end users make to AppData (Roaming) can be lost when they switch computers or when their local AppData is cleared when they log off and then log back on.</span></span> <span data-ttu-id="49b87-158">このエラーは、最後の既知のアップロードを示すレジストリキー (AppDataTime) がローカルにキャッシュされた AppData との同期を終了するために発生します。</span><span class="sxs-lookup"><span data-stu-id="49b87-158">This error occurs because the registry key (AppDataTime), which indicates the last known upload, gets out of synchronization with the local cached AppData.</span></span>

<span data-ttu-id="49b87-159">回避策: エンドユーザーがログオンまたはログオフしたときに、関連するパッケージごとに次のレジストリキーを手動で削除します。</span><span class="sxs-lookup"><span data-stu-id="49b87-159">WORKAROUND: Manually delete the following registry key for each relevant package when an end user logs on or off:</span></span>

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

<span data-ttu-id="49b87-160">アプリがログインした後、エンドユーザーがパッケージでアプリケーションを初めて起動すると、アプリ-V は、% LocalAppData% が既に最新の状態である場合でも、zip% AppData% を強制的にダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="49b87-160">The first time that end users start an application in the package after they log in, App-V forces a download of the zipped %AppData%, even if %LocalAppData% is already up to date.</span></span>

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> <span data-ttu-id="49b87-161">App-v 5.0 Service Pack 2 (App-v 5.0 SP2) には、新しいバージョンの App-v Server が含まれていない</span><span class="sxs-lookup"><span data-stu-id="49b87-161">App-V 5.0 Service Pack 2 (App-V 5.0 SP2) does not include a new version of the App-V Server</span></span>

<span data-ttu-id="49b87-162">App-v 5.0 SP2 には、新しいバージョンの App-v Server が含まれていません。</span><span class="sxs-lookup"><span data-stu-id="49b87-162">App-V 5.0SP2 does not include a new version of the App-V Server.</span></span> <span data-ttu-id="49b87-163">Windows 8.1 を実行している環境で App-v 5.0 SP2 クライアントを展開し、App-v インフラストラクチャを使ってクライアントを管理することを計画している場合は、 [Microsoft Application Virtualization 5.0 Service Pack 1 用の修正プログラムパッケージ2を](https://go.microsoft.com/fwlink/?LinkId=386634)インストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-163">If you deploy App-V 5.0 SP2 clients running Windows 8.1 in your environment and plan to manage the clients using the App-V infrastructure, you must install [Hotfix Package 2 for Microsoft Application Virtualization 5.0 Service Pack 1](https://go.microsoft.com/fwlink/?LinkId=386634).</span></span> <span data-ttu-id="49b87-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span><span class="sxs-lookup"><span data-stu-id="49b87-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span></span>

<span data-ttu-id="49b87-165">次のいずれかの方法を使用して App-v 5.0 SP2 クライアントを実行して管理している場合、クライアントの更新は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="49b87-165">If you are running and managing App-V 5.0 SP2 clients using any of the following methods no client update is required:</span></span>

-   <span data-ttu-id="49b87-166">スタンドアロン モード。</span><span class="sxs-lookup"><span data-stu-id="49b87-166">Standalone mode.</span></span>

-   <span data-ttu-id="49b87-167">Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="49b87-167">Configuration Manager.</span></span>

-   <span data-ttu-id="49b87-168">サードパーティの ESD。</span><span class="sxs-lookup"><span data-stu-id="49b87-168">Third party ESD.</span></span>

<span data-ttu-id="49b87-169">App-v 5.0 SP2 クライアントは、Windows 8.1 と完全に互換性があります。</span><span class="sxs-lookup"><span data-stu-id="49b87-169">The App-V 5.0 SP2 client is fully compatible with Windows 8.1</span></span>

<span data-ttu-id="49b87-170">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="49b87-170">WORKAROUND: None.</span></span>

## <span data-ttu-id="49b87-171">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="49b87-171">Release Notes Copyright Information</span></span>


<span data-ttu-id="49b87-172">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="49b87-172">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="49b87-173">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="49b87-173">All other trademarks are property of their respective owners.</span></span>








## <span data-ttu-id="49b87-174">関連トピック</span><span class="sxs-lookup"><span data-stu-id="49b87-174">Related topics</span></span>


[<span data-ttu-id="49b87-175">App-V 5.0 SP2 について</span><span class="sxs-lookup"><span data-stu-id="49b87-175">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

 

 





