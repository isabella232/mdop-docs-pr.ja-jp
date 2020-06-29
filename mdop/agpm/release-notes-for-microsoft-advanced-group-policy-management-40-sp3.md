---
title: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP3 リリース ノート
description: Microsoft Advanced Group Policy Management (AGPM) 4.0 SP3 リリース ノート
author: dansimp
ms.assetid: 955d7674-a8d9-4fc5-b18a-5a1639e38014
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 6e0da04d67b3d29135071e0bc82b8e01789e4e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10818524"
---
# <span data-ttu-id="00699-103">Microsoft Advanced Group Policy Management (AGPM) 4.0 SP3 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="00699-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>


<span data-ttu-id="00699-104">これらのリリースノートを検索するには、Ctrl キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="00699-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="00699-105">Microsoft Advanced Group Policy Management (AGPM) 4.0 Service Pack3 (SP3) をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="00699-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="00699-106">これらのリリースノートには、AGPM 4.0 SP3 を正常にインストールするために必要な情報が含まれており、製品のドキュメントでは提供されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00699-106">These release notes contain information that is required to successfully install AGPM4.0 SP3 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="00699-107">これらのリリースノートとその他の AGPM ドキュメントの間に違いがある場合は、最新の変更についても考慮してください。</span><span class="sxs-lookup"><span data-stu-id="00699-107">If there is a difference between these release notes and other AGPM documentation, consider the latest change authoritative.</span></span> <span data-ttu-id="00699-108">これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="00699-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="00699-109">AGPM 4.0 SP3 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="00699-109">AGPM4.0 SP3 known issues</span></span>


<span data-ttu-id="00699-110">このセクションでは、AGPM 4.0 SP3 の既知の問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="00699-110">This section describes the known issues for AGPM 4.0 SP3.</span></span>

### <span data-ttu-id="00699-111">Windows 10 で AGPM インストールが失敗する</span><span class="sxs-lookup"><span data-stu-id="00699-111">AGPM installation fails in Windows 10</span></span>

<span data-ttu-id="00699-112">AGPM は、インストール時に Windows Communication Foundation (WCF) 非 Http アクティブ化機能を内部的に有効にします。</span><span class="sxs-lookup"><span data-stu-id="00699-112">AGPM internally enables the Windows Communication Foundation (WCF)-NonHTTP-Activation feature during installation.</span></span> <span data-ttu-id="00699-113">Windows 10 では、wcf の非アクティブ化機能を有効にした後、Windows を再起動するための要件が WCF に含まれるようになりました。</span><span class="sxs-lookup"><span data-stu-id="00699-113">In Windows 10, WCF now includes a requirement to restart Windows after enabling the WCF NonHTTP-Activation feature.</span></span> <span data-ttu-id="00699-114">ただし、現在の AGPM インストーラコードは、この再起動要件を処理せず、サービスのアクティブ化を待機して応答を停止します。</span><span class="sxs-lookup"><span data-stu-id="00699-114">However, the current AGPM installer code does not handle this restart requirement and stops responding while it waits for the service to be activated.</span></span>

<span data-ttu-id="00699-115">**回避策:** AGPM インストーラーを実行する前に、WCF 非 HTTP ライセンス認証機能を有効にして、Windows を再起動してください。</span><span class="sxs-lookup"><span data-stu-id="00699-115">**Workaround:** Before you run the AGPM installer, enable the WCF Non-HTTP Activation feature and then restart Windows.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="00699-116">AGPM サーバー設定を変更しようとすると、コントロールパネルの "アンインストール" ツールが機能しないことがある</span><span class="sxs-lookup"><span data-stu-id="00699-116">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="00699-117">コントロールパネルのプログラムをアンインストールまたは変更するために使用するツールが、AGPM サーバーの設定を変更しようとしても動作しないことがあります。</span><span class="sxs-lookup"><span data-stu-id="00699-117">The tool in Control Panel that you use to uninstall or change a program may not work when you try to change AGPM Server settings.</span></span>

<span data-ttu-id="00699-118">**回避策:** コントロールパネルを使用して AGPM サーバー設定を変更しようとする前に、AGPM アーカイブフォルダーのコピーを作成します。</span><span class="sxs-lookup"><span data-stu-id="00699-118">**Workaround:** Before you try to change AGPM Server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="00699-119">次に、Setup.exe を使って AGPM サーバーを再インストールし、必要な構成パラメーターを選びます。</span><span class="sxs-lookup"><span data-stu-id="00699-119">You can then use Setup.exe to reinstall the AGPM Server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="00699-120">グループポリシーオブジェクトに追加されたリンクはレポートに表示されない</span><span class="sxs-lookup"><span data-stu-id="00699-120">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="00699-121">AGPM 設定と差分レポートには、グループポリシーオブジェクト (GPO) に追加されたリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="00699-121">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="00699-122">**回避策:** レポート内のリンクを表示するには、グループポリシー管理コンソール (GPMC) で GPO を選んでから、右側のウィンドウで [**設定**] タブをクリックします。</span><span class="sxs-lookup"><span data-stu-id="00699-122">**Workaround:** To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and then click the **Settings** tab in the right pane.</span></span>

### <span data-ttu-id="00699-123">すべての選択オプションのプロパティの設定がレポートに表示されない</span><span class="sxs-lookup"><span data-stu-id="00699-123">Reports do not display all Choice Options Properties settings</span></span>

<span data-ttu-id="00699-124">AGPM 設定と差分レポートでは、グループポリシーオブジェクトエディターの [**選択オプション] プロパティ**ウィンドウで選択されたすべての設定が表示されません。</span><span class="sxs-lookup"><span data-stu-id="00699-124">The AGPM settings and difference reports do not display all of the settings that were selected in the **Choice Options Properties** window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="00699-125">**回避策:** GPMC を使用して、レポートで選択した選択**オプションのプロパティ**の設定を表示します。</span><span class="sxs-lookup"><span data-stu-id="00699-125">**Workaround:** Use the GPMC to view the selected **Choice Options Properties** settings in the reports.</span></span>

### <span data-ttu-id="00699-126">特定のブラウザーで [表示] と [非表示] のタブが表示されない場合がある</span><span class="sxs-lookup"><span data-stu-id="00699-126">Reports may not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="00699-127">AGPM の設定と差のレポートの右側に表示される [**表示]** タブと [**非表示**] タブは、Google Chrome または Mozilla Firefox でレポートを表示したときに表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="00699-127">The **Show** and **Hide** tabs, on the right side of the AGPM settings and difference reports, may not appear when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="00699-128">**回避策:** Internet Explorer ブラウザーを使用してレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="00699-128">**Workaround:** View the reports by using the Internet Explorer browser.</span></span>

### <span data-ttu-id="00699-129">AGPM の設定と差分レポートでは、GPMC レポートのさまざまなコンテンツが表示される場合がある</span><span class="sxs-lookup"><span data-stu-id="00699-129">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="00699-130">AGPM 設定と差分レポートでは、GPMC のレポートと同じコンテンツが表示されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="00699-130">The AGPM settings and difference reports may not show the same content as reports in the GPMC.</span></span>

<span data-ttu-id="00699-131">**回避策:** GPMC を使って AGPM レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="00699-131">**Workaround:** Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="00699-132">ドメインコントローラーがオフラインになっている場合、AGPM サービスが開始しない</span><span class="sxs-lookup"><span data-stu-id="00699-132">AGPM Service does not start if the domain controller is offline</span></span>

<span data-ttu-id="00699-133">Windows®8オペレーティングシステム以降のオペレーティングシステム上のドメインコントローラーに AGPM サービスがインストールされている場合、ドメインコントローラーがオフラインになっていると、サービスは開始されません。</span><span class="sxs-lookup"><span data-stu-id="00699-133">When the AGPM Service is installed on a domain controller on the Windows® 8 operating systems or later operating systems, the service does not start if the domain controller is offline.</span></span>

<span data-ttu-id="00699-134">**回避策:** ドメインコントローラーがオンラインになったら、AGPM サービスを手動で開始します。</span><span class="sxs-lookup"><span data-stu-id="00699-134">**Workaround:** Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="00699-135">Agpm 4.0 リリース plus の hotfix1 からアップグレードすると、AGPM サーバーから AGPM 4.0 SP2 へのアップグレードがブロックされる</span><span class="sxs-lookup"><span data-stu-id="00699-135">Upgrade of AGPM Server to AGPM4.0 SP2 is blocked when you upgrade from the AGPM4.0 release plus hotfix1</span></span>

<span data-ttu-id="00699-136">AGPM サーバーを AGPM 4.0 にアップグレードしようとした場合。</span><span class="sxs-lookup"><span data-stu-id="00699-136">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="00699-137">AGPM 4.0 サーバーをインストールしてから、AGPM 4.0 という名前の AGPM ホットフィックスをインストールすると、HTML レポートで間違った違いが報告される (サポート技術情報の記事[2643502](https://go.microsoft.com/fwlink/?LinkId=254474))。アップグレードは失敗し、完了することはできません。</span><span class="sxs-lookup"><span data-stu-id="00699-137">SP2 after installing AGPM 4.0 Server and then installing the AGPM hotfix named AGPM 4.0 reports incorrect differences in the HTML report (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="00699-138">**回避策:** AGPM 4.0 サーバーをアンインストールしてから、AGPM 4.0 SP2 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="00699-138">**Workaround:** Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="00699-139">レポートに組織単位のリンクが表示されない</span><span class="sxs-lookup"><span data-stu-id="00699-139">Reports do not display organizational unit links</span></span>

<span data-ttu-id="00699-140">制御されていない GPO を組織単位にリンクして、AGPM を使ってその GPO を制御した場合、AGPM 設定と差分レポートには組織単位のリンクは表示されません。</span><span class="sxs-lookup"><span data-stu-id="00699-140">If you link an uncontrolled GPO to an organizational unit and then control that GPO by using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="00699-141">**回避策:**[**設定の変更**] ノードの [**管理**] タブで、GPO を右クリックし、[**設定**] をクリックし、[ **GPO リンク**] をクリックして組織リンクを表示します。</span><span class="sxs-lookup"><span data-stu-id="00699-141">**Workaround:** On the **Controlled** tab of the **Change Settings** node, right-click the GPO, click **Settings**, and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="00699-142">または、GPMC を使用して、[**スコープ**] タブから GPO へのリンクを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="00699-142">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

### <span data-ttu-id="00699-143">[変更]、[修復]、または [AGPM クライアントの削除] ダイアログボックスの [戻る] ボタンをクリックするとエラーが表示される</span><span class="sxs-lookup"><span data-stu-id="00699-143">AGPM displays an error if you click the Back button from the Change, Repair, or Remove AGPM Client dialog box</span></span>

<span data-ttu-id="00699-144">[コントロールパネル] の [**プログラムと機能**] を参照して、[ **Microsoft Advanced グループポリシーの管理-クライアント**] を選ぶと、 **[変更] をクリックし**、[変更]、[修復]、**または [agpm クライアントの削除**] ダイアログボックスの [**戻る**] ボタンをクリックした場合にエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="00699-144">If you browse to **Programs and Features** in Control Panel and then select **Microsoft Advanced Group Policy Management – Client**, AGPM displays an error if you click **Modify** and then click the **Back** button in the **Change, Repair, or Remove AGPM Client** dialog box.</span></span>

<span data-ttu-id="00699-145">**回避策:**[**キャンセル**] をクリックしてエラーを消去し、プロセスをもう一度開始します。</span><span class="sxs-lookup"><span data-stu-id="00699-145">**Workaround:** Click **Cancel** to clear the error, and then start the process again.</span></span> <span data-ttu-id="00699-146">[**変更**] をクリックした後、[**戻る**] ボタンをクリックしないでください。</span><span class="sxs-lookup"><span data-stu-id="00699-146">Do not click the **Back** button after you click **Modify** .</span></span>

### <span data-ttu-id="00699-147">承認者が GPO を展開してコメントを入力したときに、[履歴] ウィンドウにコメントが表示されない</span><span class="sxs-lookup"><span data-stu-id="00699-147">Comment fails to appear in the History window when the Approver deploys a GPO and enters a comment</span></span>

<span data-ttu-id="00699-148">編集者の役割を持つユーザーが GPO を展開するための要求を送信した場合に、承認者の役割を持つユーザーが GPO を展開してコメントを入力すると、[**履歴**] ウィンドウにコメントが表示されません。</span><span class="sxs-lookup"><span data-stu-id="00699-148">If a user who has the Editor role submits a request to deploy a GPO, and the user who has the Approver role then deploys the GPO and enters a comment, the comment fails to appear in the **History** window.</span></span>

<span data-ttu-id="00699-149">**回避策:**-.</span><span class="sxs-lookup"><span data-stu-id="00699-149">**Workaround:** None.</span></span>

### <span data-ttu-id="00699-150">GPO のアクセス許可の変更を削除するための AGPM の既定の動作をオーバーライドするためのメカニズムを追加しました</span><span class="sxs-lookup"><span data-stu-id="00699-150">Added mechanism to override AGPM default behavior of removing GPO permission changes</span></span>

<span data-ttu-id="00699-151">HF02 の場合、AGPM では、既定の AGPM GPO のアクセス許可の動作を上書きできるようにレジストリキーを追加しています。</span><span class="sxs-lookup"><span data-stu-id="00699-151">As of HF02, AGPM has added a registry key to enable overriding the default AGPM GPO permission behavior.</span></span> <span data-ttu-id="00699-152">詳細については、「 [AGPM によるグループポリシーオブジェクトのアクセス許可の変更を無視する](https://support.microsoft.com/kb/3174540)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="00699-152">For more information, please see [Changes to Group Policy object permissions through AGPM are ignored](https://support.microsoft.com/kb/3174540)</span></span>

## <span data-ttu-id="00699-153">関連トピック</span><span class="sxs-lookup"><span data-stu-id="00699-153">Related topics</span></span>


[<span data-ttu-id="00699-154">高度なグループ ポリシーの管理</span><span class="sxs-lookup"><span data-stu-id="00699-154">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="00699-155">AGPM 4.0 SP3 の新機能</span><span class="sxs-lookup"><span data-stu-id="00699-155">What's New in AGPM 4.0 SP3</span></span>](whats-new-in-agpm-40-sp3.md)

 

 





