---
title: Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート
description: Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート
author: dansimp
ms.assetid: 79a36c77-fa0c-4651-8028-4a79763a2fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0677dda93f2c2dc60ec627ae0c3f4bd8c199db6c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825277"
---
# <span data-ttu-id="3c53f-103">Microsoft User Experience Virtualization (UE-V) 2.1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="3c53f-103">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>


<span data-ttu-id="3c53f-104">Microsoft User Experience Virtualization (UE-V) 2.0 のリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-104">To search Microsoft User Experience Virtualization (UE-V) 2.0 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="3c53f-105">UE-V をインストールする前に、これらのリリースノートを完全に読む必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="3c53f-106">リリースノートには、ユーザーエクスペリエンスの仮想化を正常にインストールするために必要な情報や、製品のドキュメントに記載されていない追加情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="3c53f-107">これらのリリースノートと他の UE-V ドキュメントの違いがある場合は、最新の変更を、権威を持つものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="3c53f-108">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="3c53f-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="3c53f-109">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="3c53f-109">Providing feedback</span></span>


<span data-ttu-id="3c53f-110">フィードバックとコメントを提供して、MDOP のドキュメントについてご意見をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="3c53f-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="3c53f-111">ドキュメントのフィードバックを[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)に送信します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="3c53f-112">UE-V の既知の問題</span><span class="sxs-lookup"><span data-stu-id="3c53f-112">UE-V known issues</span></span>


<span data-ttu-id="3c53f-113">このセクションには、ユーザーエクスペリエンスの仮想化のリリースノートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="3c53f-114">Skype の UE-V 設定場所テンプレート skype がクラッシュする原因</span><span class="sxs-lookup"><span data-stu-id="3c53f-114">UE-V settings location templates for Skype cause Skype to crash</span></span>

<span data-ttu-id="3c53f-115">ユーザーが Skype デスクトップアプリケーション用に有効な設定場所テンプレートを生成し、それを登録して、skype デスクトップアプリケーションを起動すると、Skype がクラッシュします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-115">When a user generates a valid settings location template for the Skype desktop application, registers it, and then launches the Skype desktop application, Skype crashes.</span></span> <span data-ttu-id="3c53f-116">ACCESS \ _VIOLATION は、アプリケーションイベントログに記録されます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-116">An ACCESS\_VIOLATION is recorded in the Application Event Log.</span></span>

<span data-ttu-id="3c53f-117">回避策: skype のテンプレートを削除するか、登録を解除して、Skype を再び使用できるようにします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-117">WORKAROUND: Remove or unregister the Skype template to allow Skype to work again.</span></span>

### <span data-ttu-id="3c53f-118">UE-V のサイレントインストール用の既存のスクリプトが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="3c53f-118">Existing scripts for silent installations of UE-V may fail</span></span>

<span data-ttu-id="3c53f-119">UE-V インストーラーに対して2つの変更を行うと、UE-V 2.1 をインストールするときに、以前のバージョンの UE-V で動作していたサイレントインストールスクリプトが失敗する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-119">Two changes made to the UE-V installer can cause silent installation scripts that worked for previous versions of UE-V to fail when installing UE-V 2.1.</span></span> <span data-ttu-id="3c53f-120">1つ目は、サイレントインストール中でも、ユーザーがライセンス条項に同意し、カスタマーエクスペリエンス向上プログラム (CEIP) への参加を承諾または拒否する必要がある新しい要件です。</span><span class="sxs-lookup"><span data-stu-id="3c53f-120">The first is a new requirement that users must accept the license terms and agree to or decline participation in the Customer Experience Improvement Program (CEIP), even during a silent installation.</span></span> <span data-ttu-id="3c53f-121">/Q パラメーターを使用すると、CEIP に参加するためのライセンス条項とライセンス契約の同意を示す必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-121">Using the /q parameter is no longer sufficient to indicate acceptance of the license terms and agreement to participate in CEIP.</span></span>

<span data-ttu-id="3c53f-122">次に、UE-V エージェントをインストールした後、インストーラーによってコンピューターが強制的に再起動されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="3c53f-122">Second, the installer now forces a computer restart after installing the UE-V Agent.</span></span> <span data-ttu-id="3c53f-123">このため、再起動が想定されていない場合は、インストールスクリプトが失敗する可能性があります (たとえば、最初に UE-V Agent をインストールしてから、すぐにジェネレーターをインストールします)。</span><span class="sxs-lookup"><span data-stu-id="3c53f-123">This can cause an install script to fail if it is not expecting the restart (for example, it installs the UE-V Agent first and then immediately installs the generator).</span></span>

<span data-ttu-id="3c53f-124">回避策: UE-V installer (.msi) には、サイレントインストールをサポートする2つの新しいコマンドラインパラメーターがあります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-124">WORKAROUND: The UE-V installer (.msi) has two new command-line parameters that support silent installations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3c53f-125">パラメーター</span><span class="sxs-lookup"><span data-stu-id="3c53f-125">Parameter</span></span></th>
<th align="left"><span data-ttu-id="3c53f-126">説明</span><span class="sxs-lookup"><span data-stu-id="3c53f-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3c53f-127">/Acceptlicenseterms = True</span><span class="sxs-lookup"><span data-stu-id="3c53f-127">/ACCEPTLICENSETERMS=True</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3c53f-128"><strong>Ue-v をサイレントインストールするには、このパラメーターを True に設定 </strong> します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-128">Set this parameter to <strong>True</strong> to install UE-V silently.</span></span> <span data-ttu-id="3c53f-129">このパラメーターを追加すると、ユーザーは UE-V ライセンス条項 (既定で) を受け取ることになります。%ProgramFiles%\Microsoft User Experience Virtualization\Agent</span><span class="sxs-lookup"><span data-stu-id="3c53f-129">Adding this parameter implies that the user accepts the UE-V license terms, which are found (by default) here: %ProgramFiles%\Microsoft User Experience Virtualization\Agent</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3c53f-130">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="3c53f-130">/NORESTART</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3c53f-131">このパラメーターを指定すると、UE-V エージェントをインストールした後に、必須の再起動が行われません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-131">This parameter prevents the mandatory restart after the UE-V agent is installed.</span></span> <span data-ttu-id="3c53f-132">リターンコード3010は、UE-V を使う前に再起動が必要であることを示します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-132">A return code of 3010 indicates that a restart is required prior to using UE-V.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3c53f-133">同じコンピューター上の App-v とネイティブアプリケーションの間でレジストリ設定が同期されない</span><span class="sxs-lookup"><span data-stu-id="3c53f-133">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="3c53f-134">コンピューターに、Application Virtualization (App-v) と Windows Installer (.msi) ファイルを使ってインストールされたアプリケーションがある場合、これらのテクノロジの間でレジストリベースの設定は同期されません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-134">When a computer has an application that is installed through both Application Virtualization (App-V) and locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="3c53f-135">対応策: この問題を解決するには、2つのテクノロジのどちらか1つを選択してアプリケーションを実行します。両方を選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-135">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="3c53f-136">Office 2010 と Office 2013 の両方で予期しない結果が表示される</span><span class="sxs-lookup"><span data-stu-id="3c53f-136">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="3c53f-137">ユーザーに Office 2010 と Office 2013 の両方がインストールされている場合、2つのバージョンの Office 間の一般的な設定は、UE-V によってローミングされます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-137">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="3c53f-138">このため、Office 2010 パッケージのサイズが大きすぎるか、特に Office 365 が使用されている場合は、予期しない2013との競合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-138">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="3c53f-139">回避策: いずれかのバージョンの Office をインストールするか、UE-V で同期される設定を制限します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-139">WORKAROUND: Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="3c53f-140">Windows 8 アプリをアンインストールして再インストールすると、設定が初期状態に戻ります</span><span class="sxs-lookup"><span data-stu-id="3c53f-140">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="3c53f-141">Windows 8 アプリで UE-V 設定の同期を使用しているときに、ユーザーがアプリをアンインストールしてから、アプリを再インストールすると、アプリの設定は既定値に戻ります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-141">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="3c53f-142">この問題が発生するのは、アンインストールによってアプリの設定のローカル (キャッシュされた) コピーが削除されますが、ローカルの UE-V 設定パッケージは削除されないためです。</span><span class="sxs-lookup"><span data-stu-id="3c53f-142"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="3c53f-143">アプリを再インストールして起動すると、UE-V は、アプリの既定値にリセットされたアプリの設定を収集し、中央の保存場所に既定の設定をアップロードします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-143"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="3c53f-144">その他のアプリを実行しているコンピューターで、既定の設定をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-144"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="3c53f-145">この動作は、デスクトップアプリケーションの動作と同じです。</span><span class="sxs-lookup"><span data-stu-id="3c53f-145"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="3c53f-146">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="3c53f-146">WORKAROUND: None.</span></span>

### <span data-ttu-id="3c53f-147">UE-V は、32ビット版と64ビット版の Microsoft Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-147">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="3c53f-148">32ビットと64ビットの両方のオペレーティングシステムに対して、32ビット版の Microsoft Office をインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-148">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="3c53f-149">必要な Microsoft Office のバージョンを選択するには、ここをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-149">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="3c53f-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="3c53f-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="3c53f-151">UE-V は、同じアーキテクチャバージョンの Office 間のローミング設定をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-151">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="3c53f-152">たとえば、32ビット版の office の設定は、すべての32ビット版の Office インスタンス間でローミングされます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-152">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="3c53f-153">UE-V は、32ビット版と64ビット版の Office 間でのローミング設定をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-153">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="3c53f-154">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="3c53f-154">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="3c53f-155">MSI がローカライズされていない</span><span class="sxs-lookup"><span data-stu-id="3c53f-155">MSI’s are not localized</span></span>

<span data-ttu-id="3c53f-156">UE-V 2.0 には、UE-V Agent と UE-V generator の両方のローカライズされたセットアッププログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-156">UE-V 2.0 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="3c53f-157">これらの MSI ファイルは引き続き使用できますが、ユーザーインターフェイスは最小化され、MSI は英語でのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-157">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="3c53f-158">英語版のファイルにもかかわらず、セットアッププログラムはインストール中にサポートされるすべての言語をインストールします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-158">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="3c53f-159">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="3c53f-159">WORKAROUND: None</span></span>

### <span data-ttu-id="3c53f-160">Internet Explorer 9 のお気に入りに関連付けられている Favicons はローミングされません</span><span class="sxs-lookup"><span data-stu-id="3c53f-160">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="3c53f-161">Internet Explorer 9 のお気に入りに関連付けられている favicons は、ユーザーエクスペリエンスの仮想化によってローミングされず、新しいコンピューターでお気に入りが最初に表示されたときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-161">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="3c53f-162">回避策: Internet Explorer 9 ブラウザーでブックマークを使用してキャッシュすると、Favicons が関連するお気に入りと共に表示されます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-162">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="3c53f-163">ファイル設定のパスはレジストリに保存される</span><span class="sxs-lookup"><span data-stu-id="3c53f-163">File settings paths are stored in registry</span></span>

<span data-ttu-id="3c53f-164">一部のアプリケーション設定では、構成ファイルと設定ファイルのパスがレジストリの値として格納されています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-164">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="3c53f-165">設定がコンピューター間でローミングするときに、レジストリでパスとして参照されているファイルを同期する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-165">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="3c53f-166">回避策: フォルダーリダイレクションまたはその他の技術を使用して、ファイル設定パスとして参照されているすべてのファイルが、設定をローミングするすべてのコンピューターの同じ場所に配置されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-166">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="3c53f-167">長い設定の記憶域のパスでエラーが発生することがある</span><span class="sxs-lookup"><span data-stu-id="3c53f-167">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="3c53f-168">設定のストレージパスをできるだけ短くします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-168">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="3c53f-169">長いパスを使えば、解決や同期ができなくなることがあります。</span><span class="sxs-lookup"><span data-stu-id="3c53f-169">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="3c53f-170">UE-V は、設定を保存するための計算パスの一部として、設定の記憶域パスを使用します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-170">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="3c53f-171">このパスは次のように計算されます。設定の保存パス + "settingspackages" + パッケージディレクトリ (テンプレート ID) + パッケージ名 (テンプレート ID) と pkgx。</span><span class="sxs-lookup"><span data-stu-id="3c53f-171">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="3c53f-172">この計算パスが260文字を超える場合、パッケージストレージは失敗し、UE-V の操作イベントログで次のエラーメッセージが生成されます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-172">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="3c53f-173">操作ログイベントを確認するには、イベントビューアーを開き、[アプリケーションとサービスログ]、[Microsoft/ユーザーエクスペリエンスの仮想化/ログ/運用] の順に移動します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-173">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="3c53f-174">回避策: なし。</span><span class="sxs-lookup"><span data-stu-id="3c53f-174">WORKAROUND: None.</span></span>

### <span data-ttu-id="3c53f-175">一部のオペレーティングシステム設定は、同じバージョンのオペレーティングシステム間でのみローミングします。</span><span class="sxs-lookup"><span data-stu-id="3c53f-175">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="3c53f-176">ナレーターのオペレーティングシステム設定と、ロケールに固有の通貨文字 (言語と地域の設定など) は、オペレーティングシステムバージョンの Windows と同じようにローミングされます。</span><span class="sxs-lookup"><span data-stu-id="3c53f-176">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="3c53f-177">たとえば、Windows 7 と Windows 8 の間では、通貨文字はローミングされません。</span><span class="sxs-lookup"><span data-stu-id="3c53f-177">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="3c53f-178">回避策: なし</span><span class="sxs-lookup"><span data-stu-id="3c53f-178">WORKAROUND: None</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="3c53f-179">Ue-v 2 テンプレートを実行しているときに UE-V 1 agent がエラーを生成する</span><span class="sxs-lookup"><span data-stu-id="3c53f-179">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="3c53f-180">Ue-v 2 設定の場所テンプレートが UE-V 1 エージェントと共にインストールされたコンピューターに配布されている場合、一部の設定はコンピューター間で同期されず、エージェントはイベントログのエラーを報告します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-180">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="3c53f-181">回避策: UE-V 1 から UE-V 2 に移行するときに、以前のバージョンのエージェントを実行しているコンピューターが存在する可能性がある場合は、ue-v 2.0 エージェントとテンプレートをサポートするために、別の UE-V 2.0 カタログを作成します。</span><span class="sxs-lookup"><span data-stu-id="3c53f-181">WORKAROUND: When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.0 catalog to support the UE-V 2.0 Agent and templates.</span></span>

## <span data-ttu-id="3c53f-182">UE-V 2.1 の修正プログラムとサポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="3c53f-182">Hotfixes and Knowledge Base articles for UE-V 2.1</span></span>


<span data-ttu-id="3c53f-183">このセクションには、UE-V 2.1 の修正プログラムとサポート技術情報の記事が含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c53f-183">This section contains hotfixes and KB articles for UE-V 2.1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="3c53f-184">サポート技術情報の記事</span><span class="sxs-lookup"><span data-stu-id="3c53f-184">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="3c53f-185">タイトル</span><span class="sxs-lookup"><span data-stu-id="3c53f-185">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="3c53f-186">リンク</span><span class="sxs-lookup"><span data-stu-id="3c53f-186">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-187">3018608</span><span class="sxs-lookup"><span data-stu-id="3c53f-187">3018608</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-188">Ue-v WMI クラスが見つからない場合に、UE-V 2.1-TemplateConsole.exe がクラッシュする</span><span class="sxs-lookup"><span data-stu-id="3c53f-188">UE-V 2.1 - TemplateConsole.exe crashes when UE-V WMI classes are missing</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)"><span data-ttu-id="3c53f-189">support.microsoft.com/kb/3018608/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-189">support.microsoft.com/kb/3018608/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-190">2903501</span><span class="sxs-lookup"><span data-stu-id="3c53f-190">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-191">UE-V: user Experience Virtualization (UE-V) ユーザープロファイルとの互換性</span><span class="sxs-lookup"><span data-stu-id="3c53f-191">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="3c53f-192">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-192">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-193">2770042</span><span class="sxs-lookup"><span data-stu-id="3c53f-193">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-194">UE-V のレジストリ設定</span><span class="sxs-lookup"><span data-stu-id="3c53f-194">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="3c53f-195">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-195">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-196">2847017</span><span class="sxs-lookup"><span data-stu-id="3c53f-196">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-197">Internet Explorer によってレプリケートされた UE-V の設定</span><span class="sxs-lookup"><span data-stu-id="3c53f-197">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="3c53f-198">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-198">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-199">2769631</span><span class="sxs-lookup"><span data-stu-id="3c53f-199">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-200">破損した UE-V のインストールを修復する方法</span><span class="sxs-lookup"><span data-stu-id="3c53f-200">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="3c53f-201">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-201">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-202">2850989</span><span class="sxs-lookup"><span data-stu-id="3c53f-202">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-203">Microsoft UE-V での MAPI プロファイルの移行はサポートされていません</span><span class="sxs-lookup"><span data-stu-id="3c53f-203">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="3c53f-204">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-204">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-205">2769586</span><span class="sxs-lookup"><span data-stu-id="3c53f-205">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-206">UE-V ローミング: 空のフォルダーとレジストリキー</span><span class="sxs-lookup"><span data-stu-id="3c53f-206">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="3c53f-207">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-207">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-208">2782997</span><span class="sxs-lookup"><span data-stu-id="3c53f-208">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-209">Microsoft User Experience Virtualization (UE-V) でデバッグログを有効にする方法</span><span class="sxs-lookup"><span data-stu-id="3c53f-209">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="3c53f-210">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-210">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-211">2769570</span><span class="sxs-lookup"><span data-stu-id="3c53f-211">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-212">UE-V で RDS または VDI セッションのテーマが更新されない</span><span class="sxs-lookup"><span data-stu-id="3c53f-212">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="3c53f-213">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-213">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-214">2850582</span><span class="sxs-lookup"><span data-stu-id="3c53f-214">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-215">App-v アプリケーションで Microsoft ユーザーエクスペリエンス仮想化を使用する方法</span><span class="sxs-lookup"><span data-stu-id="3c53f-215">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="3c53f-216">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-216">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3c53f-217">3041879</span><span class="sxs-lookup"><span data-stu-id="3c53f-217">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-218">Microsoft User Experience Virtualization の現在のファイルバージョン</span><span class="sxs-lookup"><span data-stu-id="3c53f-218">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="3c53f-219">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-219">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3c53f-220">2843592</span><span class="sxs-lookup"><span data-stu-id="3c53f-220">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="3c53f-221">ユーザーエクスペリエンスの仮想化と高可用性に関する情報</span><span class="sxs-lookup"><span data-stu-id="3c53f-221">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="3c53f-222">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="3c53f-222">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 






 

 




