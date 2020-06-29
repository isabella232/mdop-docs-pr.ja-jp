---
title: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート
description: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818534"
---
# <span data-ttu-id="fe66c-103">Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="fe66c-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>


<span data-ttu-id="fe66c-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="fe66c-105">Microsoft Advanced グループポリシー管理 (AGPM) 4.0 SP1 をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="fe66c-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="fe66c-106">これらのリリースノートには、AGPM 4.0 SP1 を正常にインストールするために必要な情報が含まれており、製品のドキュメントでは提供されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe66c-106">These release notes contain information that is required to successfully install AGPM 4.0 SP1 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="fe66c-107">これらのリリースノートとその他の AGPM ドキュメントの間に違いがある場合は、最新の変更を、権威を持つものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="fe66c-107">If there is a difference between these release notes and other AGPM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="fe66c-108">これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="fe66c-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="fe66c-109">AGPM 4.0 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="fe66c-109">AGPM 4.0 SP1 known issues</span></span>


<span data-ttu-id="fe66c-110">このセクションには、AGPM 4.0 SP1 のリリースノートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="fe66c-110">This section contains release notes for AGPM 4.0 SP1.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="fe66c-111">AGPM サーバー設定を変更しようとすると、コントロールパネルの "アンインストール" ツールが機能しないことがある</span><span class="sxs-lookup"><span data-stu-id="fe66c-111">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="fe66c-112">コントロールパネルのツールで、AGPM サーバーの設定を変更しようとしても、プログラムをアンインストールまたは変更できないことがあります。</span><span class="sxs-lookup"><span data-stu-id="fe66c-112">The tool in Control Panel that lets you uninstall or change a program may not work when you try to change AGPM server settings.</span></span>

<span data-ttu-id="fe66c-113">対応策: コントロールパネルを使用して AGPM サーバーの設定を変更する前に、AGPM アーカイブフォルダーのコピーを作成してください。</span><span class="sxs-lookup"><span data-stu-id="fe66c-113">WORKAROUND: Before you try to change AGPM server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="fe66c-114">次に、Setup.exe を使って AGPM サーバーを再インストールし、必要な構成パラメーターを選びます。</span><span class="sxs-lookup"><span data-stu-id="fe66c-114">You can then use Setup.exe to reinstall the AGPM server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="fe66c-115">グループポリシーオブジェクトに追加されたリンクはレポートに表示されない</span><span class="sxs-lookup"><span data-stu-id="fe66c-115">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="fe66c-116">AGPM 設定と差分レポートには、グループポリシーオブジェクト (GPO) に追加されたリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-116">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="fe66c-117">対応策: レポート内のリンクを表示するには、グループポリシー管理コンソール (GPMC) で GPO を選んで、右側のウィンドウで [**設定**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fe66c-117">WORKAROUND: To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and click the **Settings** tab in the right pane.</span></span>

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a><span data-ttu-id="fe66c-118">レポートにすべての [選択肢オプションプロパティ] の設定が表示されない</span><span class="sxs-lookup"><span data-stu-id="fe66c-118">Reports do not display all “Choice Options Properties” settings</span></span>

<span data-ttu-id="fe66c-119">AGPM 設定と差分レポートでは、グループポリシーオブジェクトエディターの [オプションの選択] ダイアログボックスで選択されたすべての設定が表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-119">The AGPM settings and difference reports do not display all of the settings that were selected on the Choice Options Properties window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="fe66c-120">回避策: GPMC を使用して、レポートで選択した選択オプションのプロパティの設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-120">WORKAROUND: Use the GPMC to view the selected Choice Options Properties settings in the reports.</span></span>

### <span data-ttu-id="fe66c-121">特定のブラウザーで [表示] と [非表示] のタブが表示されないレポート</span><span class="sxs-lookup"><span data-stu-id="fe66c-121">Reports do not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="fe66c-122">AGPM 設定と差分レポートの右側に表示される [表示] タブと [非表示] タブは、Google Chrome または Mozilla Firefox でレポートを表示するときには表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-122">The Show and Hide tabs, shown on the right side of the AGPM settings and difference reports, are not displayed when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="fe66c-123">回避策: Internet Explorer を使用してレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-123">WORKAROUND: View the reports by using Internet Explorer.</span></span>

### <span data-ttu-id="fe66c-124">AGPM の設定と差分レポートでは、GPMC レポートのさまざまなコンテンツが表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="fe66c-124">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="fe66c-125">AGPM 設定と差分レポートでは、グループポリシー管理コンソール (GPMC) のレポートと同じコンテンツが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fe66c-125">The AGPM settings and difference reports may not show the same content as reports in the Group Policy Management Console (GPMC).</span></span>

<span data-ttu-id="fe66c-126">回避策: GPMC を使って AGPM レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-126">WORKAROUND: Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="fe66c-127">ドメインコントローラーがオンラインでない場合、AGPM サービスが開始されない</span><span class="sxs-lookup"><span data-stu-id="fe66c-127">AGPM Service does not start if the domain controller is not online</span></span>

<span data-ttu-id="fe66c-128">Windows 8 のドメインコントローラーに AGPM サービスがインストールされている場合、そのドメインコントローラーがオンラインでない場合はサービスが開始されません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-128">When the AGPM Service is installed on a domain controller on Windows 8, the Service does not start if the domain controller is not online.</span></span>

<span data-ttu-id="fe66c-129">回避策: ドメインコントローラーがオンラインになったら、AGPM サービスを手動で開始します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-129">WORKAROUND: Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="fe66c-130">Agpm 4.0 リリースと修正プログラムのどちらからアップグレードしても、agpm サーバーから AGPM 4.0 SP1 へのアップグレードがブロックされます。</span><span class="sxs-lookup"><span data-stu-id="fe66c-130">Upgrade of AGPM Server to AGPM 4.0 SP1 is blocked when you upgrade from the AGPM 4.0 release plus the hotfix</span></span>

<span data-ttu-id="fe66c-131">AGPM サーバーを AGPM 4.0 にアップグレードしようとした場合。</span><span class="sxs-lookup"><span data-stu-id="fe66c-131">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="fe66c-132">[SP1] AGPM 4.0 をインストールしてから AGPM ホットフィックスをインストールする (「サポート技術情報の記事[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)」を参照)、アップグレードは失敗し、完了することができません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-132">SP1 after installing AGPM 4.0 and then installing the AGPM hotfix (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="fe66c-133">回避策: AGPM 4.0 サーバーをアンインストールしてから、AGPM 4.0 SP1 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="fe66c-133">WORKAROUND: Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP1.</span></span>

### <span data-ttu-id="fe66c-134">レポートに組織単位のリンクが表示されない</span><span class="sxs-lookup"><span data-stu-id="fe66c-134">Reports do not display organizational unit links</span></span>

<span data-ttu-id="fe66c-135">制御されていない GPO を組織単位にリンクして、AGPM を使ってその GPO を制御した場合、AGPM 設定と差分レポートには組織単位のリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="fe66c-135">If you link an uncontrolled GPO to an organizational unit and then control that GPO using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="fe66c-136">回避策: [**設定の変更**] ノードの [**コントロール**] タブで、gpo を右クリックして [**設定**] をクリックし、[ **gpo リンク**] をクリックして組織リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="fe66c-136">WORKAROUND: From the **Controlled** tab of the **Change Settings** node, right-click the GPO and click **Settings** and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="fe66c-137">または、GPMC を使用して、[**スコープ**] タブから GPO へのリンクを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="fe66c-137">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

## <span data-ttu-id="fe66c-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fe66c-138">Related topics</span></span>


[<span data-ttu-id="fe66c-139">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="fe66c-139">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="fe66c-140">AGPM 4.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="fe66c-140">What's New in AGPM 4.0 SP1</span></span>](whats-new-in-agpm-40-sp1.md)

 

 





