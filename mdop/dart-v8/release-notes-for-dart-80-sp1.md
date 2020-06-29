---
title: DaRT 8.0 SP1 のリリース ノート
description: DaRT 8.0 SP1 のリリース ノート
author: dansimp
ms.assetid: fa7512d8-fb00-4c27-8f65-c15f3a8ff1cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a4c49d12fed07f507d2db4d56969d8e7b0559c64
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824774"
---
# <span data-ttu-id="63efc-103">DaRT 8.0 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="63efc-103">Release Notes for DaRT 8.0 SP1</span></span>


**<span data-ttu-id="63efc-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="63efc-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="63efc-105">Microsoft 診断/回復ツールセット (DaRT) 8.0 Service Pack 1 (SP1) をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="63efc-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Service Pack 1 (SP1).</span></span>

<span data-ttu-id="63efc-106">これらのリリースノートには、診断/回復ツールセット 8.0 SP1 を正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="63efc-106">These release notes contain information that is required to successfully install Diagnostics and Recovery Toolset 8.0 SP1.</span></span> <span data-ttu-id="63efc-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="63efc-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="63efc-108">これらのリリースノートとその他の DaRT ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="63efc-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="63efc-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="63efc-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="63efc-110">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="63efc-110">About the product documentation</span></span>


<span data-ttu-id="63efc-111">DaRT のマニュアルについては、Microsoft TechNet の[DaRT のホームページ](https://go.microsoft.com/fwlink/?LinkID=252096)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="63efc-111">For information about documentation for DaRT, see the [DaRT home page](https://go.microsoft.com/fwlink/?LinkID=252096) on Microsoft TechNet.</span></span>

## <span data-ttu-id="63efc-112">DaRT 8.0 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="63efc-112">Known issues with DaRT 8.0 SP1</span></span>


### <span data-ttu-id="63efc-113">Locksmith またはレジストリエディターを実行すると、システムの復元に失敗する</span><span class="sxs-lookup"><span data-stu-id="63efc-113">System restore fails when you run Locksmith or Registry Editor</span></span>

<span data-ttu-id="63efc-114">Locksmith、Registry Editor、その他のツールを実行した場合、システムの復元は失敗します。</span><span class="sxs-lookup"><span data-stu-id="63efc-114">If you run Locksmith, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="63efc-115">**回避策:** DaRT を閉じてから再起動してから、システムの復元を開始します。</span><span class="sxs-lookup"><span data-stu-id="63efc-115">**Workaround:** Close and restart DaRT and then start System Restore.</span></span>

### <span data-ttu-id="63efc-116">Locksmith またはコンピューターの管理を起動して閉じると、SFC スキャンが実行されない</span><span class="sxs-lookup"><span data-stu-id="63efc-116">SFC scan fails to run after you launch and close Locksmith or Computer Management</span></span>

<span data-ttu-id="63efc-117">Locksmith またはコンピューター管理ツールを起動して閉じた場合、システムファイルチェッカーは実行できません。</span><span class="sxs-lookup"><span data-stu-id="63efc-117">If you start and then close the Locksmith or Computer Management tools, System File Checker fails to run.</span></span>

<span data-ttu-id="63efc-118">**回避策:** DaRT を閉じてから再起動し、SFC を起動します。</span><span class="sxs-lookup"><span data-stu-id="63efc-118">**Workaround:** Close and restart DaRT and then start SFC.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> <span data-ttu-id="63efc-119">ADK がインストールされていないと DaRT インストーラーが失敗しない</span><span class="sxs-lookup"><span data-stu-id="63efc-119">DaRT installer does not fail when ADK has not been installed</span></span>

<span data-ttu-id="63efc-120">コマンドラインを使って MSI を実行して DaRT 8.0 SP1 をインストールした場合、ADK がインストールされていないと、DaRT のインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="63efc-120">If you install DaRT 8.0 SP1 by using the command line to run the MSI, and the ADK has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="63efc-121">現時点では、dart 8.0 SP1 インストーラは DaRT リカバリ画像を除くすべてのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="63efc-121">Currently, the DaRT 8.0 SP1 installer installs all components except the DaRT recovery image.</span></span>

<span data-ttu-id="63efc-122">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="63efc-122">**Workaround:** None.</span></span>

### <span data-ttu-id="63efc-123">Locksmith、RegEdit、Crash Analyzer、およびコンピューター管理を起動した後、Defender を起動できない</span><span class="sxs-lookup"><span data-stu-id="63efc-123">Defender cannot be launched after Locksmith, RegEdit, Crash Analyzer, and Computer Management are launched</span></span>

<span data-ttu-id="63efc-124">Locksmith、RegEdit、Crash Analyzer、コンピューター管理を既に起動している場合、Defender は起動しません。</span><span class="sxs-lookup"><span data-stu-id="63efc-124">Defender does not launch if you have already launched Locksmith, RegEdit, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="63efc-125">**回避策:** DaRT を閉じてから再起動してから、Defender を起動します。</span><span class="sxs-lookup"><span data-stu-id="63efc-125">**Workaround:** Close and restart DaRT and then launch Defender.</span></span>

### <span data-ttu-id="63efc-126">Defender の起動に時間がかかる場合がある</span><span class="sxs-lookup"><span data-stu-id="63efc-126">Defender may be slow to launch</span></span>

<span data-ttu-id="63efc-127">Defender の起動には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="63efc-127">Defender sometimes takes a few minutes to launch.</span></span> <span data-ttu-id="63efc-128">進行状況バーは、現在の読み込みの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="63efc-128">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="63efc-129">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="63efc-129">**Workaround:** None.</span></span>

## <span data-ttu-id="63efc-130">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="63efc-130">Release notes copyright information</span></span>


<span data-ttu-id="63efc-131">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="63efc-131">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="63efc-132">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="63efc-132">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="63efc-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="63efc-133">Related topics</span></span>


[<span data-ttu-id="63efc-134">DaRT 8.0 SP1 について</span><span class="sxs-lookup"><span data-stu-id="63efc-134">About DaRT 8.0 SP1</span></span>](about-dart-80-sp1.md)

 

 





