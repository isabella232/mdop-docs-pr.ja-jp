---
title: DaRT 7.0 のリリース ノート
description: DaRT 7.0 のリリース ノート
author: dansimp
ms.assetid: fad227d0-5c22-4efd-9187-0e5922f7250b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5114acfe5a46a2c78f722a2bb6394c0dbef55dd4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822764"
---
# <span data-ttu-id="76346-103">DaRT 7.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="76346-103">Release Notes for DaRT 7.0</span></span>


**<span data-ttu-id="76346-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="76346-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="76346-105">Microsoft 診断/回復ツールセット (DaRT) 7 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="76346-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT)7.</span></span>

## <span data-ttu-id="76346-106">Microsoft 診断/回復ツールセット7.0 について</span><span class="sxs-lookup"><span data-stu-id="76346-106">About Microsoft Diagnostics and Recovery Toolset 7.0</span></span>


<span data-ttu-id="76346-107">これらのリリースノートには、DaRT7 を正常にインストールするために必要な情報が含まれており、製品のドキュメントでは使用できない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="76346-107">These release notes contain information that is required to successfully install DaRT7 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="76346-108">これらのリリースノートとその他の DaRT プラットフォームのドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="76346-108">If there is a difference between these release notes and other DaRT platform documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="76346-109">これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="76346-109">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="76346-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="76346-110">About the Product Documentation</span></span>


<span data-ttu-id="76346-111">Microsoft 診断/回復ツールセットのドキュメント (DaRT) 7 は製品と接続サイトに配布されています。</span><span class="sxs-lookup"><span data-stu-id="76346-111">Documentation for Microsoft Diagnostics and Recovery Toolset (DaRT)7 is distributed with the product and on the Connect site.</span></span>

<span data-ttu-id="76346-112">DaRT7 でのツールの使用方法について詳しくは、「**診断と回復のツールセット**」メニューで利用できるヘルプファイルをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="76346-112">For detailed help about how to use the tools in DaRT7, see the Help file available on the **Diagnostics and Recovery Toolset** menu.</span></span>

## <span data-ttu-id="76346-113">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="76346-113">Providing feedback</span></span>


<span data-ttu-id="76346-114">DaRT7 についてのご意見をお寄せしております。</span><span class="sxs-lookup"><span data-stu-id="76346-114">We are interested in your feedback on DaRT7.</span></span> <span data-ttu-id="76346-115">Dart7feedback@microsoft.com にフィードバックを送信できます。</span><span class="sxs-lookup"><span data-stu-id="76346-115">You can send your feedback to dart7feedback@microsoft.com.</span></span> <span data-ttu-id="76346-116">このメールアドレスはサポートチャネルではありませんが、お客様からのフィードバックは、将来のお客様にとってより便利になるように、将来の変更を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="76346-116">This email address is not a support channel, but your feedback will help us to plan future changes for these tools to make them more useful to you in the future.</span></span>

## <span data-ttu-id="76346-117">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="76346-117">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="76346-118">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="76346-118">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="76346-119">詳細については、「 [Microsoft セキュリティ](https://go.microsoft.com/fwlink/?LinkId=3482)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="76346-119">For more information, see [Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="76346-120">DaRT 7.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="76346-120">Known Issues with DaRT 7.0</span></span>


### <span data-ttu-id="76346-121">スタンドアロンのシステム Sweeper が開いている場合、SFC スキャンを開始できない</span><span class="sxs-lookup"><span data-stu-id="76346-121">SFC Scan cannot start if Standalone System Sweeper is open</span></span>

<span data-ttu-id="76346-122">スタンドアロンのシステム Sweeper が実行されている場合は、2つのツール間でリソースの競合が発生しているため、SFC スキャンを開始または実行できません。</span><span class="sxs-lookup"><span data-stu-id="76346-122">If the Standalone System Sweeper is running, SFC Scan cannot start or run because of a resource conflict between the two tools.</span></span>

<span data-ttu-id="76346-123">**回避策:** SFC スキャンツールを開いたり実行したりする前に、スタンドアロンシステム Sweeper を閉じます。</span><span class="sxs-lookup"><span data-stu-id="76346-123">**Workaround:** Close the Standalone System Sweeper before you try to open or run the SFC Scan tool.</span></span>

### <span data-ttu-id="76346-124">ファイル名に Unicode 文字が表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="76346-124">Unicode characters may not be displayed in file names</span></span>

<span data-ttu-id="76346-125">ファイル名に Unicode 文字を含むファイルを削除した場合、ファイルの復元ツールを使用してファイルを復元しようとすると、ファイルが見つかりません。</span><span class="sxs-lookup"><span data-stu-id="76346-125">If you delete a file that has Unicode characters in its file name and try to restore the file by using the File Restore tool, the file is not found.</span></span> <span data-ttu-id="76346-126">これは、回復イメージの作成に使用された Windows DVD の言語以外の言語の文字を使用している場合にのみ発生します。</span><span class="sxs-lookup"><span data-stu-id="76346-126">This only occurs when you use characters from a language other than the language of the Windows DVD that was used to create the recovery image.</span></span>

<span data-ttu-id="76346-127">**回避策:** DaRT で使用される言語が、ファイルを復元しようとしているオペレーティングシステムで使用されている言語と一致していることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76346-127">**Workaround:** Make sure that the language that is used by DaRT matches the language that is used by the operating system from which it is trying to restore files.</span></span>

### <span data-ttu-id="76346-128">DaRT コマンドラインのインストールに失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="76346-128">DaRT command-line installation may fail silently</span></span>

<span data-ttu-id="76346-129">自動管理者権限を使用して実行されていない場合、DaRT コマンドラインのインストールは、quiet モードオプションで実行しても、通知なしで失敗します。</span><span class="sxs-lookup"><span data-stu-id="76346-129">DaRT command-line installation fails silently if run with the quiet mode option unless it is run by using elevated administrator permissions.</span></span>

<span data-ttu-id="76346-130">**回避策:** 管理者権限を使用して、コマンドラインインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="76346-130">**Workaround:** Run the command-line installation by using elevated administrator permissions.</span></span> <span data-ttu-id="76346-131">DaRT のインストールでは、コマンドラインインストールの一般的な Windows Installer オプションがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="76346-131">DaRT installation supports the typical Windows Installer options for command-line installation.</span></span> <span data-ttu-id="76346-132">利用可能ないくつかのスイッチの詳細については、「Windows インストーラーの[コマンドラインオプション](https://go.microsoft.com/fwlink/?LinkId=160689)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="76346-132">Please see [Command-Line Options](https://go.microsoft.com/fwlink/?LinkId=160689) for Windows Installer for more information about the several available switches.</span></span>

### <span data-ttu-id="76346-133">ファイル検索でフォルダーを別のボリュームに移動できない</span><span class="sxs-lookup"><span data-stu-id="76346-133">File Search cannot move a folder to a different volume</span></span>

<span data-ttu-id="76346-134">ファイル検索アプリケーションでは、ボリューム間でフォルダーを移動することはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="76346-134">Moving folders between volumes is not supported by the File Search application.</span></span> <span data-ttu-id="76346-135">ファイル検索でフォルダーを別のボリュームに移動しようとすると、次のエラーが返されます。 "ファイル\* &lt; 名 &gt; \*の書き込み中にエラーが発生しました。</span><span class="sxs-lookup"><span data-stu-id="76346-135">If you try to move a folder to a different volume in File Search, the following error is returned: "An error occurred while writing the file *&lt;filename&gt;*.</span></span> <span data-ttu-id="76346-136">ドライブに十分な領域があり、移動先のパスがアクセス可能であることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="76346-136">Make sure that the drive has sufficient space and the destination path is accessible."</span></span>

<span data-ttu-id="76346-137">**回避策:** エクスプローラーを使用して、フォルダーを別のボリュームに移動します。</span><span class="sxs-lookup"><span data-stu-id="76346-137">**Workaround:** Use the Explorer to move a folder to a different volume.</span></span>

### <span data-ttu-id="76346-138">ドライブ文字が再割り当てされているコンピューターで一部のデータを使用できない場合がある</span><span class="sxs-lookup"><span data-stu-id="76346-138">Some data may not be available on computers where the drive letters are remapped</span></span>

<span data-ttu-id="76346-139">この問題は、BitLocker が有効なコンピューターとマルチブートコンピューターで発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76346-139">This problem can occur on BitLocker-enabled computers and multiboot computers.</span></span> <span data-ttu-id="76346-140">この問題が発生するのは、オフラインのレジストリの一部のドライブ文字がハードコードされていて、DaRT で同じボリュームに異なる文字が使用されているためです。</span><span class="sxs-lookup"><span data-stu-id="76346-140">This occurs because some information in the offline registry has hard-coded drive letters, and DaRT uses different letters for the same volumes.</span></span> <span data-ttu-id="76346-141">一般的な効果として、レジストリエディターで特定のローカルユーザーアカウントにアクセスすることはできません。</span><span class="sxs-lookup"><span data-stu-id="76346-141">The typical effects include not having access to certain local user accounts in Registry Editor.</span></span> <span data-ttu-id="76346-142">さらに、一部のツールでは、ファイルパスの解決に依存するプロパティを取得できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="76346-142">Additionally, some tools may be unable to obtain properties that rely on resolving file paths.</span></span>

<span data-ttu-id="76346-143">**回避策:** DaRT が起動するときにドライブ文字を再マップするオプションを使用します。</span><span class="sxs-lookup"><span data-stu-id="76346-143">**Workaround:** Use the option to remap the drive letters as DaRT starts.</span></span> <span data-ttu-id="76346-144">通常、通常のドライブ文字が予期したとおりに配置されます。</span><span class="sxs-lookup"><span data-stu-id="76346-144">This usually aligns the typical drive letters to what is expected.</span></span>

### <span data-ttu-id="76346-145">修正プログラムのアンインストールで特定の更新プログラムがアンインストールされない場合がある</span><span class="sxs-lookup"><span data-stu-id="76346-145">Hotfix Uninstall might not uninstall certain updates</span></span>

<span data-ttu-id="76346-146">一部の更新プログラムと service pack はアンインストールできない場合があります。これらは、インストール外としてマークされている場合、または Windows 7 内からアンインストールする必要があるためです。</span><span class="sxs-lookup"><span data-stu-id="76346-146">Some updates and service packs cannot be uninstalled because they are marked as un-installable or because they need to be uninstalled from within Windows 7.</span></span> <span data-ttu-id="76346-147">このような場合、Hotfix アンインストールツールは、これらの更新プログラムがインストールされていないにもかかわらずアンインストールされたことを示す場合があります。</span><span class="sxs-lookup"><span data-stu-id="76346-147">In these instances, the Hotfix Uninstall tool may indicate that these updates have been uninstalled even though they have not been.</span></span>

<span data-ttu-id="76346-148">**回避策:** これらの問題のある更新プログラムを Windows 7 からアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="76346-148">**Workaround:** Uninstall these problematic updates from Windows 7.</span></span>

### <span data-ttu-id="76346-149">ディスクワイプ: スパンボリューム、ストライプボリューム、またはミラーボリュームを含むディスクは削除できません。</span><span class="sxs-lookup"><span data-stu-id="76346-149">Disk Wipe: Disks with spanned volumes, striped volumes, or mirrored volumes cannot be deleted</span></span>

<span data-ttu-id="76346-150">ディスクワイプは、1つ以上のボリューム間でスパン、ミラー、またはストライプ化されているディスクの削除をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="76346-150">Disk Wipe does not support deleting disks that are spanned, mirrored, or striped across one or more volumes.</span></span>

<span data-ttu-id="76346-151">**回避策:** ボリューム内の各ディスクを個別に選択して削除します。</span><span class="sxs-lookup"><span data-stu-id="76346-151">**Workaround:** Select and delete each disk in the volume separately.</span></span>

## <span data-ttu-id="76346-152">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="76346-152">Release Notes Copyright Information</span></span>


<span data-ttu-id="76346-153">このドキュメントは "現在のところ" として提供されています。</span><span class="sxs-lookup"><span data-stu-id="76346-153">This document is provided “as-is”.</span></span> <span data-ttu-id="76346-154">このドキュメントで説明されている情報とビュー (URL などのインターネット web サイトの参照を含む) は、予告なしに変更される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="76346-154">Information and views expressed in this document, including URL and other Internet website references, may change without notice.</span></span> <span data-ttu-id="76346-155">使用のリスクを負うことができます。</span><span class="sxs-lookup"><span data-stu-id="76346-155">You bear the risk of using it.</span></span>

<span data-ttu-id="76346-156">ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。</span><span class="sxs-lookup"><span data-stu-id="76346-156">Some examples depicted herein are provided for illustration only and are fictitious.</span></span><span data-ttu-id="76346-157">実際の関連付けや接続は意図していないか、または推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="76346-157">No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="76346-158">このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。</span><span class="sxs-lookup"><span data-stu-id="76346-158">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="76346-159">このドキュメントは、Microsoft にとって社外秘であり、所有権を持っています。</span><span class="sxs-lookup"><span data-stu-id="76346-159">This document is confidential and proprietary to Microsoft.</span></span> <span data-ttu-id="76346-160">このサービスは公開されており、守秘義務契約に基づいてのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="76346-160">It is disclosed and can be used only pursuant to a nondisclosure agreement.</span></span>



<span data-ttu-id="76346-161">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="76346-161">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="76346-162">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="76346-162">All other trademarks are property of their respective owners.</span></span>

## <span data-ttu-id="76346-163">関連トピック</span><span class="sxs-lookup"><span data-stu-id="76346-163">Related topics</span></span>


[<span data-ttu-id="76346-164">DaRT 7.0 について</span><span class="sxs-lookup"><span data-stu-id="76346-164">About DaRT 7.0</span></span>](about-dart-70-new-ia.md)

 

 





