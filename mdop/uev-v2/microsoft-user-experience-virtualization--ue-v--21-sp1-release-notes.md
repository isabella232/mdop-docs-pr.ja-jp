---
title: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825534"
---
# <span data-ttu-id="6f3f1-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6f3f1-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>


<span data-ttu-id="6f3f1-104">Microsoft User Experience Virtualization 2.1 SP1 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-104">To search Microsoft User Experience Virtualization 2.1 SP1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="6f3f1-105">UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="6f3f1-106">リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="6f3f1-107">これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="6f3f1-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="6f3f1-109">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="6f3f1-109">Providing feedback</span></span>


<span data-ttu-id="6f3f1-110">フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="6f3f1-111">ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="6f3f1-112">UE-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="6f3f1-112">UE-V known issues</span></span>


<span data-ttu-id="6f3f1-113">このセクションには、ユーザーエクスペリエンスの仮想化 2.1 SP1 のリリースノートが記載されています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-113">This section contains release notes for User Experience Virtualization 2.1 SP1.</span></span>

### <span data-ttu-id="6f3f1-114">Skype の UE-V 設定場所テンプレート skype がクラッシュする原因</span><span class="sxs-lookup"><span data-stu-id="6f3f1-114">UE-V settings location templates for Skype cause Skype to crash</span></span>

<span data-ttu-id="6f3f1-115">ユーザーが Skype デスクトップアプリケーション用に有効な設定場所テンプレートを生成し、それを登録して、skype デスクトップアプリケーションを起動すると、Skype がクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-115">When a user generates a valid settings location template for the Skype desktop application, registers it, and then launches the Skype desktop application, Skype crashes.</span></span> <span data-ttu-id="6f3f1-116">ACCESS \ _VIOLATION は、アプリケーションイベントログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-116">An ACCESS\_VIOLATION is recorded in the Application Event Log.</span></span>

<span data-ttu-id="6f3f1-117">回避策: skype のテンプレートを削除するか、登録を解除して、Skype を再び使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-117">WORKAROUND: Remove or unregister the Skype template to allow Skype to work again.</span></span>

### <span data-ttu-id="6f3f1-118">UE-V のサイレントインストール用の既存のスクリプトが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="6f3f1-118">Existing scripts for silent installations of UE-V may fail</span></span>

<span data-ttu-id="6f3f1-119">UE-V インストーラーを2つ変更すると、UE-V 2.1 SP1 をインストールするときに、以前のバージョンの UE-V で動作していたサイレントインストールスクリプトが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-119">Two changes made to the UE-V installer can cause silent installation scripts that worked for previous versions of UE-V to fail when installing UE-V 2.1 SP1.</span></span> <span data-ttu-id="6f3f1-120">1つ目は、サイレントインストール中でも、ユーザーがライセンス条項に同意し、カスタマーエクスペリエンス向上プログラム (CEIP) への参加を承諾または拒否する必要がある新しい要件です。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-120">The first is a new requirement that users must accept the license terms and agree to or decline participation in the Customer Experience Improvement Program (CEIP), even during a silent installation.</span></span> <span data-ttu-id="6f3f1-121">/Q パラメーターを使用すると、CEIP に参加するためのライセンス条項とライセンス契約の同意を示す必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-121">Using the /q parameter is no longer sufficient to indicate acceptance of the license terms and agreement to participate in CEIP.</span></span>

<span data-ttu-id="6f3f1-122">次に、UE-V エージェントをインストールした後、インストーラーによってコンピューターが強制的に再起動されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-122">Second, the installer now forces a computer restart after installing the UE-V Agent.</span></span> <span data-ttu-id="6f3f1-123">このため、再起動が想定されていない場合は、インストールスクリプトが失敗する可能性があります (たとえば、最初に UE-V Agent をインストールしてから、すぐにジェネレーターをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-123">This can cause an install script to fail if it is not expecting the restart (for example, it installs the UE-V Agent first and then immediately installs the generator).</span></span>

<span data-ttu-id="6f3f1-124">回避策: UE-V installer (.msi) には、サイレントインストールをサポートする2つの新しいコマンドラインパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-124">WORKAROUND: The UE-V installer (.msi) has two new command-line parameters that support silent installations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6f3f1-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="6f3f1-125">Parameter</span></span></th>
<th align="left"><span data-ttu-id="6f3f1-126">説明</span><span class="sxs-lookup"><span data-stu-id="6f3f1-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6f3f1-127">/Acceptlicenseterms = True</span><span class="sxs-lookup"><span data-stu-id="6f3f1-127">/ACCEPTLICENSETERMS=True</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-128"><strong>Ue-v をサイレントインストールするには、このパラメーターを True に設定 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-128">Set this parameter to <strong>True</strong> to install UE-V silently.</span></span> <span data-ttu-id="6f3f1-129">このパラメーターを追加すると、ユーザーは UE-V ライセンス条項 (既定で) を受け取ることになります。%ProgramFiles%\Microsoft User Experience Virtualization\Agent</span><span class="sxs-lookup"><span data-stu-id="6f3f1-129">Adding this parameter implies that the user accepts the UE-V license terms, which are found (by default) here: %ProgramFiles%\Microsoft User Experience Virtualization\Agent</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6f3f1-130">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="6f3f1-130">/NORESTART</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-131">このパラメーターを指定すると、UE-V エージェントをインストールした後に、必須の再起動が行われません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-131">This parameter prevents the mandatory restart after the UE-V agent is installed.</span></span> <span data-ttu-id="6f3f1-132">リターンコード3010は、UE-V を使う前に再起動が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-132">A return code of 3010 indicates that a restart is required prior to using UE-V.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6f3f1-133">同じコンピューター上の App-v とネイティブアプリケーションの間でレジストリ設定が同期されない</span><span class="sxs-lookup"><span data-stu-id="6f3f1-133">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="6f3f1-134">コンピューターに、Application Virtualization (App-v) と Windows Installer (.msi) ファイルを使ってインストールされたアプリケーションがある場合、これらのテクノロジの間でレジストリベースの設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-134">When a computer has an application that is installed through both Application Virtualization (App-V) and locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="6f3f1-135">対応策: この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-135">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="6f3f1-136">Office 2010 と Office 2013 の両方で予期しない結果が表示される</span><span class="sxs-lookup"><span data-stu-id="6f3f1-136">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="6f3f1-137">ユーザーに Office 2010 と Office 2013 の両方がインストールされている場合、2つのバージョンの Office 間の一般的な設定は、UE-V によってローミングされます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-137">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="6f3f1-138">このため、Office 2010 パッケージのサイズが大きすぎるか、特に Office 365 が使用されている場合は、予期しない2013との競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-138">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="6f3f1-139">回避策: いずれかのバージョンの Office をインストールするか、UE-V で同期される設定を制限します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-139">WORKAROUND: Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="6f3f1-140">Windows 8 アプリをアンインストールして再インストールすると、設定が初期状態に戻ります</span><span class="sxs-lookup"><span data-stu-id="6f3f1-140">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="6f3f1-141">Windows 8 アプリで UE-V 設定の同期を使用しているときに、ユーザーがアプリをアンインストールしてから、アプリを再インストールすると、アプリの設定は既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-141">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="6f3f1-142">この問題が発生するのは、アンインストールによってアプリの設定のローカル (キャッシュされた) コピーが削除されますが、ローカルの UE-V 設定パッケージは削除されないためです。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-142"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="6f3f1-143">アプリを再インストールして起動すると、UE-V は、アプリの既定値にリセットされたアプリの設定を収集し、中央の保存場所に既定の設定をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-143"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="6f3f1-144">その他のアプリを実行しているコンピューターで、既定の設定をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-144"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="6f3f1-145">この動作は、デスクトップアプリケーションの動作と同じです。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-145"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="6f3f1-146">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-146">WORKAROUND: None.</span></span>

### <span data-ttu-id="6f3f1-147">UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-147">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="6f3f1-148">32ビットと64ビットの両方のオペレーティングシステムに対して、32ビット版の Microsoft Office をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-148">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="6f3f1-149">必要な Microsoft Office のバージョンを選択するには、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-149">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="6f3f1-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="6f3f1-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="6f3f1-151">UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-151">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="6f3f1-152">たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-152">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="6f3f1-153">UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-153">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="6f3f1-154">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="6f3f1-154">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="6f3f1-155">MSI がローカライズされていない</span><span class="sxs-lookup"><span data-stu-id="6f3f1-155">MSI’s are not localized</span></span>

<span data-ttu-id="6f3f1-156">UE-V は、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムを備えています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-156">UE-V includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="6f3f1-157">これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-157">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="6f3f1-158">英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-158">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="6f3f1-159">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="6f3f1-159">WORKAROUND: None</span></span>

### <span data-ttu-id="6f3f1-160">Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません</span><span class="sxs-lookup"><span data-stu-id="6f3f1-160">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="6f3f1-161">Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-161">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="6f3f1-162">回避策: Internet Explorer 9 ブラウザーでブックマークを使用してキャッシュすると、Favicons が関連するお気に入りと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-162">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="6f3f1-163">ファイル設定のパスはレジストリに保存される</span><span class="sxs-lookup"><span data-stu-id="6f3f1-163">File settings paths are stored in registry</span></span>

<span data-ttu-id="6f3f1-164">一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-164">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="6f3f1-165">設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-165">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="6f3f1-166">回避策: フォルダーリダイレクションまたはその他の技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターの同じ場所に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-166">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="6f3f1-167">長い設定の記憶域のパスでエラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="6f3f1-167">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="6f3f1-168">設定のストレージパスをできるだけ短くします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-168">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="6f3f1-169">長いパスを使えば、解決や同期ができなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-169">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="6f3f1-170">UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-170">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="6f3f1-171">このパスは次のように計算されます。設定の保存パス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID) と pkgx。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-171">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="6f3f1-172">この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-172">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="6f3f1-173">操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-173">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="6f3f1-174">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-174">WORKAROUND: None.</span></span>

### <span data-ttu-id="6f3f1-175">一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-175">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="6f3f1-176">ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字 (言語と地域の設定など) は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-176">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="6f3f1-177">たとえば、Windows 7 と Windows 8 の間では、通貨文字はローミングされません。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-177">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="6f3f1-178">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="6f3f1-178">WORKAROUND: None</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="6f3f1-179">Ue-v 2 テンプレートを実行しているときに UE-V 1 agent がエラーを生成する</span><span class="sxs-lookup"><span data-stu-id="6f3f1-179">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="6f3f1-180">Ue-v 2 設定の場所テンプレートが UE-V 1 エージェントと共にインストールされたコンピューターに配布されている場合、一部の設定はコンピューター間で同期されず、エージェントはイベントログのエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-180">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="6f3f1-181">回避策: UE-V 1 から UE-V 2 に移行するときに、以前のバージョンのエージェントを実行しているコンピューターがある可能性がある場合は、ue-v Agent とテンプレートをサポートするために、別の UE-V catalog を作成します。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-181">WORKAROUND: When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.x catalog to support the UE-V 2.x Agent and templates.</span></span>

### <span data-ttu-id="6f3f1-182">UE-V のログオフ遅延</span><span class="sxs-lookup"><span data-stu-id="6f3f1-182">UE-V logoff delay</span></span>

<span data-ttu-id="6f3f1-183">場合によっては、ログオフ時に、設定を同期するのに時間がかかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-183">Occasionally on logoff, UE-V takes a long time to sync settings.</span></span> <span data-ttu-id="6f3f1-184">通常、これは、待機時間の長いネットワーク、または Distrubuted ファイルシステム (DFS) の不適切な使用が原因です。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-184">Typically, this is due to a high latency network or incorrect use of Distrubuted File System (DFS).</span></span>
<span data-ttu-id="6f3f1-185">DFS のサポートについては、複製された[ユーザープロファイルデータに関連する Microsoft のサポートステートメント](https://support.microsoft.com/kb/2533009)で詳細を確認してください。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-185">For DFS support, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://support.microsoft.com/kb/2533009) for further details.</span></span>

<span data-ttu-id="6f3f1-186">回避策: HF03 から始めて、新しいレジストリキーが導入されました。次のレジストリキーでは、最大のログオフ遅延を指定できるようにするメカニズムを提供しています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-186">WORKAROUND: Starting with HF03, a new registry key has been introduced The following registry key provides a mechanism by which the maximum logoff delay can be specified \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span></span>

<span data-ttu-id="6f3f1-187">詳細については[、「ue-v のレジストリ設定](https://support.microsoft.com/kb/2770042)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-187">See [UE-V registry settings](https://support.microsoft.com/kb/2770042) for further details</span></span>

## <span data-ttu-id="6f3f1-188">UE-V 2.1 SP1 のホットフィックスとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="6f3f1-188">Hotfixes and Knowledge Base articles for UE-V 2.1 SP1</span></span>


<span data-ttu-id="6f3f1-189">このセクションには、UE-V 2.1 SP1 の修正プログラムとサポート技術情報の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6f3f1-189">This section contains hotfixes and KB articles for UE-V 2.1 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="6f3f1-190">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="6f3f1-190">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="6f3f1-191">タイトル</span><span class="sxs-lookup"><span data-stu-id="6f3f1-191">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="6f3f1-192">リンク</span><span class="sxs-lookup"><span data-stu-id="6f3f1-192">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-193">3018608</span><span class="sxs-lookup"><span data-stu-id="6f3f1-193">3018608</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-194">Ue-v WMI クラスが見つからない場合に、UE-V 2.1-TemplateConsole.exe がクラッシュする</span><span class="sxs-lookup"><span data-stu-id="6f3f1-194">UE-V 2.1 - TemplateConsole.exe crashes when UE-V WMI classes are missing</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)"><span data-ttu-id="6f3f1-195">support.microsoft.com/kb/3018608/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-195">support.microsoft.com/kb/3018608/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-196">2903501</span><span class="sxs-lookup"><span data-stu-id="6f3f1-196">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-197">UE-V: user Experience Virtualization (UE-V) ユーザープロファイルとの互換性</span><span class="sxs-lookup"><span data-stu-id="6f3f1-197">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="6f3f1-198">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-198">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-199">2770042</span><span class="sxs-lookup"><span data-stu-id="6f3f1-199">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-200">UE-V のレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="6f3f1-200">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="6f3f1-201">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-201">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-202">2847017</span><span class="sxs-lookup"><span data-stu-id="6f3f1-202">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-203">Internet Explorer によってレプリケートされた UE-V の設定</span><span class="sxs-lookup"><span data-stu-id="6f3f1-203">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="6f3f1-204">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-204">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-205">2769631</span><span class="sxs-lookup"><span data-stu-id="6f3f1-205">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-206">破損した UE-V のインストールを修復する方法</span><span class="sxs-lookup"><span data-stu-id="6f3f1-206">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="6f3f1-207">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-207">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-208">2850989</span><span class="sxs-lookup"><span data-stu-id="6f3f1-208">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-209">Microsoft UE-V での MAPI プロファイルの移行はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="6f3f1-209">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="6f3f1-210">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-210">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-211">2769586</span><span class="sxs-lookup"><span data-stu-id="6f3f1-211">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-212">UE-V ローミング: 空のフォルダーとレジストリキー</span><span class="sxs-lookup"><span data-stu-id="6f3f1-212">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="6f3f1-213">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-213">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-214">2782997</span><span class="sxs-lookup"><span data-stu-id="6f3f1-214">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-215">Microsoft User Experience Virtualization (UE-V) でデバッグログを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="6f3f1-215">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="6f3f1-216">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-216">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-217">2769570</span><span class="sxs-lookup"><span data-stu-id="6f3f1-217">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-218">UE-V で RDS または VDI セッションのテーマが更新されない</span><span class="sxs-lookup"><span data-stu-id="6f3f1-218">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="6f3f1-219">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-219">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-220">2850582</span><span class="sxs-lookup"><span data-stu-id="6f3f1-220">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-221">App-v アプリケーションで Microsoft ユーザーエクスペリエンス仮想化を使用する方法</span><span class="sxs-lookup"><span data-stu-id="6f3f1-221">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="6f3f1-222">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-222">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6f3f1-223">3041879</span><span class="sxs-lookup"><span data-stu-id="6f3f1-223">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-224">Microsoft User Experience Virtualization の現在のファイルバージョン</span><span class="sxs-lookup"><span data-stu-id="6f3f1-224">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="6f3f1-225">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-225">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6f3f1-226">2843592</span><span class="sxs-lookup"><span data-stu-id="6f3f1-226">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="6f3f1-227">ユーザーエクスペリエンスの仮想化と高可用性に関する情報</span><span class="sxs-lookup"><span data-stu-id="6f3f1-227">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="6f3f1-228">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="6f3f1-228">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 






 

 





