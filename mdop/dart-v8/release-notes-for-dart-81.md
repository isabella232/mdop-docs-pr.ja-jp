---
title: DaRT 8.1 のリリース ノート
description: DaRT 8.1 のリリース ノート
author: dansimp
ms.assetid: 44303107-60f4-485c-848a-7e0529f142d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d0ba817ddd5bbdefcf7fed833f4c47e7b9d9ce0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824764"
---
# <span data-ttu-id="9c739-103">DaRT 8.1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="9c739-103">Release Notes for DaRT 8.1</span></span>


**<span data-ttu-id="9c739-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="9c739-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="9c739-105">Microsoft 診断/回復ツールセット (DaRT) 8.1 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="9c739-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.1.</span></span>

<span data-ttu-id="9c739-106">これらのリリースノートには、診断と回復ツールセットの8.1 を正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c739-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 8.1.</span></span> <span data-ttu-id="9c739-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="9c739-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="9c739-108">これらのリリースノートとその他の DaRT ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="9c739-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="9c739-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="9c739-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="9c739-110">DaRT 8.1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="9c739-110">Known issues with DaRT 8.1</span></span>


### <span data-ttu-id="9c739-111">Windows 8.1 の物理パーティション内の破損したマスターブートレコードを、ディスクコマンダーが修復できない</span><span class="sxs-lookup"><span data-stu-id="9c739-111">Disk Commander is unable to repair a corrupt master boot record in a physical partition in Windows 8.1</span></span>

<span data-ttu-id="9c739-112">Windows 8.1 の場合、ディスクコマンダーの "マスターブートレコード (MBR)" または "GUID パーティションテーブル (GPT)" オプションの値を復元できません。物理パーティション内の破損したマスターブートレコードを修復できないため、クライアントコンピューターを起動できません。</span><span class="sxs-lookup"><span data-stu-id="9c739-112">In Windows 8.1, the “Restore the Master Boot Record (MBR) or the header of the GUID Partition Table (GPT)” option in Disk Commander is unable to repair a corrupt master boot record in a physical partition, and therefore is unable to boot the client computer.</span></span>

<span data-ttu-id="9c739-113">**回避策:\*\*\*\*スタートアップ修復**を開始して、[**トラブルシューティング**] をクリックし、[**詳細オプション**] をクリックして、[**修復の開始**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9c739-113">**Workaround:** Start **Startup Repair**, click **Troubleshoot**, click **Advanced options**, and then click **Start repair**.</span></span>

### <span data-ttu-id="9c739-114">同じドライブをターゲットとするディスクワイプの複数のインスタンスで、障害を報告するために最後のインスタンス以外のすべてのインスタンスが発生する</span><span class="sxs-lookup"><span data-stu-id="9c739-114">Multiple instances of Disk Wipe that target the same drive cause all instances except the last one to report a failure</span></span>

<span data-ttu-id="9c739-115">ディスクワイプの複数のインスタンスを開始して、2つの別個のディスクワイプインスタンスを使って同じドライブをワイプしようとすると、最後の1つを除くすべてのインスタンスが、ドライブのワイプに失敗したことを報告します。</span><span class="sxs-lookup"><span data-stu-id="9c739-115">If you start multiple instances of Disk Wipe, and then try to wipe the same drive by using two separate Disk Wipe instances, all instances except the last one report a failure to wipe the drive.</span></span>

<span data-ttu-id="9c739-116">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="9c739-116">**Workaround:** None.</span></span>

### <span data-ttu-id="9c739-117">フラッシュメモリを搭載したソリッドステートドライブ上のすべてのデータをディスクワイプで消去できないことがある</span><span class="sxs-lookup"><span data-stu-id="9c739-117">Disk Wipe may not clear all data on solid-state drives that have flash memory</span></span>

<span data-ttu-id="9c739-118">ディスクワイプを使ってフラッシュメモリを搭載したソリッドステートドライブ (SSD) 上のデータをクリアすると、すべてのデータが消去される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="9c739-118">If you use Disk Wipe to clear data on a solid-state drive (SSD) that has flash memory, all of the data may not be erased.</span></span> <span data-ttu-id="9c739-119">この問題は、ディスクワイプが実行されているときに、SSD ファームウェアによって書き込みの物理的な場所が制御されるために発生します。</span><span class="sxs-lookup"><span data-stu-id="9c739-119">This issue occurs because the SSD firmware controls the physical location of writes while Disk Wipe is running.</span></span>

<span data-ttu-id="9c739-120">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="9c739-120">**Workaround:** None.</span></span>

### <span data-ttu-id="9c739-121">Locksmith ウィザードまたはレジストリエディターを実行すると、システムの復元に失敗する</span><span class="sxs-lookup"><span data-stu-id="9c739-121">System restore fails when you run Locksmith Wizard or Registry Editor</span></span>

<span data-ttu-id="9c739-122">Locksmith ウィザード、レジストリエディター、その他のツールを実行した場合、システムの復元は失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c739-122">If you run Locksmith Wizard, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="9c739-123">**回避策:** DaRT を閉じて再起動し、システムの復元を開始します。</span><span class="sxs-lookup"><span data-stu-id="9c739-123">**Workaround:** Close and restart DaRT, and then start System Restore.</span></span>

### <span data-ttu-id="9c739-124">起動して Locksmith ウィザードまたはコンピューターの管理を閉じると、システムファイルチェッカー (SFC) スキャンが実行されない</span><span class="sxs-lookup"><span data-stu-id="9c739-124">System File Checker (SFC) Scan fails to run after you start and close Locksmith Wizard or Computer Management</span></span>

<span data-ttu-id="9c739-125">コンピューターの管理で Locksmith ウィザードまたは [ツール] を閉じてから終了すると、システムファイルチェッカーの実行に失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c739-125">If you start and then close Locksmith Wizard or tools in Computer Management, System File Checker fails to run.</span></span>

<span data-ttu-id="9c739-126">**回避策:** DaRT を閉じて再起動し、システムファイルチェッカーを起動します。</span><span class="sxs-lookup"><span data-stu-id="9c739-126">**Workaround:** Close and restart DaRT, and then start System File Checker.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-the-windows-assessment-and-deployment-kit-is-not-installed"></a> <span data-ttu-id="9c739-127">Windows アセスメントと展開キットがインストールされていないと DaRT インストーラーが失敗しない</span><span class="sxs-lookup"><span data-stu-id="9c739-127">DaRT installer does not fail when the Windows Assessment and Deployment Kit is not installed</span></span>

<span data-ttu-id="9c739-128">コマンドラインを使用して Windows Installer (.msi) を実行することによって DaRT 8.1 をインストールした場合に、Windows アセスメント & デプロイメントキット (WindowsADK) がインストールされていないと、DaRT のインストールに失敗します。</span><span class="sxs-lookup"><span data-stu-id="9c739-128">If you install DaRT 8.1 by using the command line to run the Windows Installer (.msi), and the Windows Assessment and Deployment Kit (WindowsADK) has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="9c739-129">現時点では、dart 8.1 インストーラは DaRT リカバリ画像を除くすべてのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="9c739-129">Currently, the DaRT 8.1 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="9c739-130">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="9c739-130">**Workaround:** None.</span></span>

### <span data-ttu-id="9c739-131">Locksmith Wizard、Registry Editor、Crash Analyzer、コンピューター管理が開始された後に、Windows Defender を起動できない</span><span class="sxs-lookup"><span data-stu-id="9c739-131">Windows Defender cannot start after Locksmith Wizard, Registry Editor, Crash Analyzer, and Computer Management are started</span></span>

<span data-ttu-id="9c739-132">Locksmith Wizard、Registry Editor、Crash Analyzer、コンピューター管理を既に開始している場合は、Windows Defender が起動しません。</span><span class="sxs-lookup"><span data-stu-id="9c739-132">Windows Defender does not start if you have already started Locksmith Wizard, Registry Editor, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="9c739-133">**回避策:** DaRT を閉じて再起動し、Windows Defender を起動します。</span><span class="sxs-lookup"><span data-stu-id="9c739-133">**Workaround:** Close and restart DaRT, and then start Windows Defender.</span></span>

### <span data-ttu-id="9c739-134">Windows Defender の起動に時間がかかる場合がある</span><span class="sxs-lookup"><span data-stu-id="9c739-134">Windows Defender may be slow to start</span></span>

<span data-ttu-id="9c739-135">Windows Defender が起動するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="9c739-135">Windows Defender sometimes takes a few minutes to start.</span></span> <span data-ttu-id="9c739-136">進行状況バーは、現在の読み込みの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="9c739-136">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="9c739-137">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="9c739-137">**Workaround:** None.</span></span>

## <span data-ttu-id="9c739-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9c739-138">Related topics</span></span>


[<span data-ttu-id="9c739-139">DaRT 8.1 について</span><span class="sxs-lookup"><span data-stu-id="9c739-139">About DaRT 8.1</span></span>](about-dart-81.md)

 

 




