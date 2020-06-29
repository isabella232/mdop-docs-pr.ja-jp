---
title: Sequencer をインストールする方法
description: Sequencer をインストールする方法
author: dansimp
ms.assetid: a122caf0-f408-458c-b119-dc84123c1d58
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a8542abfecd7f1d543228ab1a86a59b9ee918947
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813954"
---
# <span data-ttu-id="5bf3b-103">Sequencer をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="5bf3b-103">How to Install the Sequencer</span></span>


<span data-ttu-id="5bf3b-104">Microsoft Application Virtualization (App-v) 5.0 sequencer をインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-104">Use the following procedure to install the Microsoft Application Virtualization (App-V) 5.0 sequencer.</span></span> <span data-ttu-id="5bf3b-105">Sequencer を実行するコンピューターは、どのバージョンの App-v 5.0 クライアントも実行していない必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-105">The computer that will run the sequencer must not be running any version of the App-V 5.0 client.</span></span>

<span data-ttu-id="5bf3b-106">以前のバージョンの App-v のインストールのアップグレードはサポートされません。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-106">Upgrading a previous installation of the App-V sequencer is not supported.</span></span>

<span data-ttu-id="5bf3b-107">**重要** Sequencer の要件の一覧については、「 [app-v 5.0 の前提条件](app-v-50-prerequisites.md)と[アプリ-v 5.0 でサポートされている構成](app-v-50-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-107">**Important** For a full list of the sequencer requirements see sequencer sections of [App-V 5.0 Prerequisites](app-v-50-prerequisites.md) and [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

 

<span data-ttu-id="5bf3b-108">コマンドラインを使って、App-v 5.0 sequencer をインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-108">You can also use the command line to install the App-V 5.0 sequencer.</span></span> <span data-ttu-id="5bf3b-109">次の一覧は、コマンドラインと**appv\_sequencer\_setup.exe**を使って sequencer をインストールするためのオプションに関する情報を示しています。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-109">The following list displays information about options for installing the sequencer using the command line and **appv\_sequencer\_setup.exe**:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5bf3b-110">コマンド</span><span class="sxs-lookup"><span data-stu-id="5bf3b-110">Command</span></span></th>
<th align="left"><span data-ttu-id="5bf3b-111">説明</span><span class="sxs-lookup"><span data-stu-id="5bf3b-111">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5bf3b-112">/INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="5bf3b-112">/INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-113">インストールディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-113">Specifies the installation directory.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5bf3b-114">/CEIPOPTIN</span><span class="sxs-lookup"><span data-stu-id="5bf3b-114">/CEIPOPTIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-115">Microsoft カスタマーエクスペリエンス向上プログラムへの参加を有効にします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-115">Enables participation in the Microsoft Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5bf3b-116">/Log</span><span class="sxs-lookup"><span data-stu-id="5bf3b-116">/Log</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-117">インストールログが保存される場所を指定します。既定の場所は <strong> % Temp% です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-117">Specifies where the installation log will be saved, the default location is <strong>%Temp%</strong>.</span></span> <span data-ttu-id="5bf3b-118">たとえば、 <strong> C:\ログに </strong> 記録します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-118">For example, <strong>C:\ Logs \ log.log</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5bf3b-119">/q</span><span class="sxs-lookup"><span data-stu-id="5bf3b-119">/q</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-120">Quiet またはサイレントインストールを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-120">Specifies a quiet or silent installation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5bf3b-121">/Uninstall</span><span class="sxs-lookup"><span data-stu-id="5bf3b-121">/Uninstall</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-122">Sequencer の削除を指定します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-122">Specifies the removal of the sequencer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5bf3b-123">/ACCEPTEULA</span><span class="sxs-lookup"><span data-stu-id="5bf3b-123">/ACCEPTEULA</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-124">ライセンス契約を承諾します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-124">Accepts the license agreement.</span></span> <span data-ttu-id="5bf3b-125">これは、無人インストールの場合に必要になります。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-125">This is required for an unattended installation.</span></span> <span data-ttu-id="5bf3b-126">使用例: <strong> /ACCEPTEULA </strong> または <strong> /ACCEPTEULA = 1 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-126">Example usage: <strong>/ACCEPTEULA</strong> or <strong>/ACCEPTEULA=1</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5bf3b-127">/レイアウト</span><span class="sxs-lookup"><span data-stu-id="5bf3b-127">/LAYOUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-128">関連付けられているレイアウトアクションを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-128">Specifies the associated layout action.</span></span> <span data-ttu-id="5bf3b-129">また、Windows インストーラー (.msi) とスクリプトファイルも、App-v 5.0 をインストールせずにフォルダーに展開します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-129">It also extracts the Windows Installer (.msi) and script files to a folder without installing App-V 5.0.</span></span> <span data-ttu-id="5bf3b-130">値は予期されません。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-130">No value is expected.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5bf3b-131">/Layoutdir</span><span class="sxs-lookup"><span data-stu-id="5bf3b-131">/LAYOUTDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-132">レイアウトディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-132">Specifies the layout directory.</span></span> <span data-ttu-id="5bf3b-133">文字列値が必要です。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-133">Requires a string value.</span></span> <span data-ttu-id="5bf3b-134">使用例: <strong> /layoutdir = "C:\ Application Virtualization Client" </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-134">Example usage: <strong>/LAYOUTDIR=”C:\Application Virtualization Client”</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5bf3b-135">/?</span><span class="sxs-lookup"><span data-stu-id="5bf3b-135">/?</span></span> <span data-ttu-id="5bf3b-136">または/h または/help</span><span class="sxs-lookup"><span data-stu-id="5bf3b-136">Or /h or /help</span></span></p></td>
<td align="left"><p><span data-ttu-id="5bf3b-137">関連するヘルプを表示します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-137">Displays associated help.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="5bf3b-138">App-v 5.0 sequencer をインストールするには</span><span class="sxs-lookup"><span data-stu-id="5bf3b-138">To install the App-V 5.0 sequencer</span></span>**

1.  <span data-ttu-id="5bf3b-139">アプリがインストールされているコンピューターに、App-v 5.0 sequencer インストールファイルをコピーします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-139">Copy the App-V 5.0 sequencer installation files to the computer on which it will be installed.</span></span> <span data-ttu-id="5bf3b-140">**appv\_sequencer\_setup.exe**をダブルクリックし、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-140">Double-click **appv\_sequencer\_setup.exe** and then click **Install**.</span></span>

2.  <span data-ttu-id="5bf3b-141">[**ソフトウェアライセンス条項**] ページで、ライセンス条項を確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-141">On the **Software License Terms** page, you should review the license terms.</span></span> <span data-ttu-id="5bf3b-142">ライセンス条項に同意するには、[**ライセンス条項に同意**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-142">To accept the license terms select **I accept the license terms.**</span></span> <span data-ttu-id="5bf3b-143">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-143">Click **Next**.</span></span>

3.  <span data-ttu-id="5bf3b-144">[ **Microsoft update を使用してコンピューターをセキュリティで保護し**、最新の状態に維持する] ページで、microsoft update を有効にするには、[**更新プログラムをチェックするときに Microsoft update を使用する (推奨)** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-144">On the **Use Microsoft Update to help keep your computer secure and up-to-date** page, to enable Microsoft updates select **Use Microsoft Update when I check for updates (recommended).**</span></span> <span data-ttu-id="5bf3b-145">Microsoft 更新プログラムの実行を無効にするには、[ **Microsoft Update を使用しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-145">To disable Microsoft updates from running select **I don’t want to use Microsoft Update**.</span></span> <span data-ttu-id="5bf3b-146">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-146">Click **Next**.</span></span>

4.  <span data-ttu-id="5bf3b-147">プログラムに参加するための [**カスタマーエクスペリエンス向上プログラム**] ページで、[**カスタマーエクスペリエンス向上プログラムに参加**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-147">On the **Customer Experience Improvement Program** page, to participate in the program select **Join the Customer Experience Improvement Program**.</span></span> <span data-ttu-id="5bf3b-148">これにより、App-v 5.0 の使用方法に関する情報を収集することができます。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-148">This will allow information to be collected about how you are using App-V 5.0.</span></span> <span data-ttu-id="5bf3b-149">プログラムに参加したくない場合は、[**プログラムに参加しない**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-149">If you don’t want to participate in the program select **I don’t want to join the program at this time**.</span></span> <span data-ttu-id="5bf3b-150">**[インストール]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-150">Click **Install**.</span></span>

5.  <span data-ttu-id="5bf3b-151">Sequencer を開くには、[**スタート**] をクリックし、[ **Microsoft Application Virtualization sequencer**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-151">To open the sequencer, click **Start** and then click **Microsoft Application Virtualization Sequencer**.</span></span>

**<span data-ttu-id="5bf3b-152">App-v 5.0 sequencer のインストールのトラブルシューティングを行うには</span><span class="sxs-lookup"><span data-stu-id="5bf3b-152">To troubleshoot the App-V 5.0 sequencer installation</span></span>**

-   <span data-ttu-id="5bf3b-153">Sequencer のインストールの詳細については、 **% temp%** フォルダーのエラーログを参照してください。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-153">For more information regarding the sequencer installation, you can view the error log in the **%temp%** folder.</span></span> <span data-ttu-id="5bf3b-154">ログファイルを確認するには、[**スタート**] をクリックし、「 **% temp%**」と入力して、 **appv\_ ログ**を探します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-154">To review the log files, click **Start**, type **%temp%**, and then look for the **appv\_ log**.</span></span>

    <span data-ttu-id="5bf3b-155">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-155">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="5bf3b-156">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-156">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="5bf3b-157">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="5bf3b-157">Got an App-V issue?</span></span>** <span data-ttu-id="5bf3b-158">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="5bf3b-158">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="5bf3b-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5bf3b-159">Related topics</span></span>


[<span data-ttu-id="5bf3b-160">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="5bf3b-160">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





