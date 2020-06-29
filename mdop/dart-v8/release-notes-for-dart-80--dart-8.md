---
title: DaRT 8.0 のリリース ノート
description: DaRT 8.0 のリリース ノート
author: dansimp
ms.assetid: e8b373c8-7aa5-4930-a8f9-743d26145dad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 894708585ff4006c37085e71f365690b8424d43e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824787"
---
# <span data-ttu-id="8463b-103">DaRT 8.0 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="8463b-103">Release Notes for DaRT 8.0</span></span>


**<span data-ttu-id="8463b-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="8463b-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="8463b-105">Microsoft 診断/回復ツールセット (DaRT) 8.0 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="8463b-105">Read these release notes thoroughly before you install Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span>

<span data-ttu-id="8463b-106">これらのリリースノートには、DaRT 8.0 を正常にインストールするために必要な情報が記載されています。</span><span class="sxs-lookup"><span data-stu-id="8463b-106">These release notes contain information that is required to successfully install DaRT 8.0.</span></span> <span data-ttu-id="8463b-107">リリースノートには、製品ドキュメントに記載されていない情報も含まれています。</span><span class="sxs-lookup"><span data-stu-id="8463b-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="8463b-108">これらのリリースノートとその他の DaRT ドキュメントの間に違いがある場合は、最新の変更を、権限のあるものとして扱う必要があります。</span><span class="sxs-lookup"><span data-stu-id="8463b-108">If there is a difference between these release notes and other DaRT documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="8463b-109">これらのリリースノートは、この製品に含まれているコンテンツに代わるものです。</span><span class="sxs-lookup"><span data-stu-id="8463b-109">These release notes supersede the content that is included with this product.</span></span>

<span data-ttu-id="8463b-110">DaRT ソフトウェアの入手方法については、「 [MDOP の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8463b-110">To get the DaRT software, see [How to Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="8463b-111">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="8463b-111">About the product documentation</span></span>


<span data-ttu-id="8463b-112">DaRT のマニュアルについては、Microsoft TechNet の[DaRT のホームページ](https://go.microsoft.com/fwlink/?LinkID=252096)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8463b-112">For information about documentation for DaRT, see the [DaRT home page](https://go.microsoft.com/fwlink/?LinkID=252096) on Microsoft TechNet.</span></span>

<span data-ttu-id="8463b-113">DaRT ドキュメントのダウンロード可能なコピーを入手するには、 <https://go.microsoft.com/fwlink/?LinkID=267420> Microsoft ダウンロードセンターを参照してください。</span><span class="sxs-lookup"><span data-stu-id="8463b-113">To obtain a downloadable copy of DaRT documentation, see <https://go.microsoft.com/fwlink/?LinkID=267420> on the Microsoft Download Center.</span></span>

## <span data-ttu-id="8463b-114">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="8463b-114">Providing feedback</span></span>


<span data-ttu-id="8463b-115">DaRT 8.0 についてご意見をお寄せしております。</span><span class="sxs-lookup"><span data-stu-id="8463b-115">We are interested in your feedback on DaRT 8.0.</span></span> <span data-ttu-id="8463b-116">にフィードバックを送信でき <mdopdocs@microsoft.com> ます。</span><span class="sxs-lookup"><span data-stu-id="8463b-116">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="8463b-117">**注** このメールアドレスはサポートチャネルではありませんが、お客様からのフィードバックは、弊社のドキュメントと製品リリースの将来の変更を計画するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="8463b-117">**Note** This email address is not a support channel, but your feedback will help us to plan future changes for our documentation and product releases.</span></span>

 

<span data-ttu-id="8463b-118">MDOP と追加のラーニングリソースに関する最新情報については、「 [mdop の情報エクスペリエンス](https://go.microsoft.com/fwlink/p/?LinkId=236032)」ページをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8463b-118">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="8463b-119">新しい更新プログラムまたはフィードバックを提供する方法について詳しくは、 [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)または[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="8463b-119">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="8463b-120">DaRT 8.0 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="8463b-120">Known issues with DaRT 8.0</span></span>


### <span data-ttu-id="8463b-121">Locksmith またはレジストリエディターを実行すると、システムの復元に失敗する</span><span class="sxs-lookup"><span data-stu-id="8463b-121">System restore fails when you run Locksmith or Registry Editor</span></span>

<span data-ttu-id="8463b-122">Locksmith、Registry Editor、その他のツールを実行した場合、システムの復元は失敗します。</span><span class="sxs-lookup"><span data-stu-id="8463b-122">If you run Locksmith, Registry Editor, and possibly other tools, System Restore fails.</span></span>

<span data-ttu-id="8463b-123">**回避策:** DaRT を閉じてから再起動してから、システムの復元を開始します。</span><span class="sxs-lookup"><span data-stu-id="8463b-123">**Workaround:** Close and restart DaRT and then start System Restore.</span></span>

### <span data-ttu-id="8463b-124">Locksmith またはコンピューターの管理を起動して閉じると、SFC スキャンが実行されない</span><span class="sxs-lookup"><span data-stu-id="8463b-124">SFC scan fails to run after you launch and close Locksmith or Computer Management</span></span>

<span data-ttu-id="8463b-125">Locksmith またはコンピューター管理ツールを起動して閉じた場合、システムファイルチェッカーは実行できません。</span><span class="sxs-lookup"><span data-stu-id="8463b-125">If you start and then close the Locksmith or Computer Management tools, System File Checker fails to run.</span></span>

<span data-ttu-id="8463b-126">**回避策:** DaRT を閉じてから再起動し、SFC を起動します。</span><span class="sxs-lookup"><span data-stu-id="8463b-126">**Workaround:** Close and restart DaRT and then start SFC.</span></span>

### <a href="" id="-------------dart-installer-does-not-fail-when-adk-has-not-been-installed"></a> <span data-ttu-id="8463b-127">ADK がインストールされていないと DaRT インストーラーが失敗しない</span><span class="sxs-lookup"><span data-stu-id="8463b-127">DaRT installer does not fail when ADK has not been installed</span></span>

<span data-ttu-id="8463b-128">コマンドラインを使って MSI を実行して DaRT 8.0 をインストールした場合に、ADK がインストールされていないと、DaRT のインストールは失敗します。</span><span class="sxs-lookup"><span data-stu-id="8463b-128">If you install DaRT 8.0 by using the command line to execute the MSI, and the ADK has not been installed, the DaRT installation should fail.</span></span> <span data-ttu-id="8463b-129">現時点では、dart 8.0 installer は DaRT 8.0 リカバリ画像を除くすべてのコンポーネントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="8463b-129">Currently, the DaRT 8.0 installer installs all components except the DaRT 8.0 recovery image.</span></span>

<span data-ttu-id="8463b-130">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="8463b-130">**Workaround:** None.</span></span>

### <span data-ttu-id="8463b-131">Locksmith、RegEdit、Crash Analyzer、およびコンピューター管理を起動した後、Defender を起動できない</span><span class="sxs-lookup"><span data-stu-id="8463b-131">Defender cannot be launched after Locksmith, RegEdit, Crash Analyzer, and Computer Management are launched</span></span>

<span data-ttu-id="8463b-132">Locksmith、RegEdit、Crash Analyzer、コンピューター管理を既に起動している場合、Defender は起動しません。</span><span class="sxs-lookup"><span data-stu-id="8463b-132">Defender does not launch if you have already launched Locksmith, RegEdit, Crash Analyzer, and Computer Management.</span></span>

<span data-ttu-id="8463b-133">**回避策:** DaRT を閉じてから再起動してから、Defender を起動します。</span><span class="sxs-lookup"><span data-stu-id="8463b-133">**Workaround:** Close and restart DaRT and then launch Defender.</span></span>

### <span data-ttu-id="8463b-134">Defender の起動に時間がかかる場合がある</span><span class="sxs-lookup"><span data-stu-id="8463b-134">Defender may be slow to launch</span></span>

<span data-ttu-id="8463b-135">Defender の起動には数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="8463b-135">Defender sometimes takes a few minutes to launch.</span></span> <span data-ttu-id="8463b-136">進行状況バーは、現在の読み込みの状態を示します。</span><span class="sxs-lookup"><span data-stu-id="8463b-136">The progress bar indicates the current loading status.</span></span>

<span data-ttu-id="8463b-137">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="8463b-137">**Workaround:** None.</span></span>

## <span data-ttu-id="8463b-138">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="8463b-138">Release notes copyright information</span></span>


<span data-ttu-id="8463b-139">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、microsoft Intune、WindowsPowerShell は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="8463b-139">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="8463b-140">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="8463b-140">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="8463b-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8463b-141">Related topics</span></span>


[<span data-ttu-id="8463b-142">DaRT 8.0 について</span><span class="sxs-lookup"><span data-stu-id="8463b-142">About DaRT 8.0</span></span>](about-dart-80-dart-8.md)

 

 





