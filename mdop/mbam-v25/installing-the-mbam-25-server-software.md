---
title: MBAM 2.5 サーバー ソフトウェアのインストール
description: MBAM 2.5 サーバー ソフトウェアのインストール
author: dansimp
ms.assetid: b9dbe697-5400-4bac-acfb-ee6dc6586c30
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6612bf52aa53ae693694d7ac02c5cab212d4e24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823394"
---
# <span data-ttu-id="46de1-103">MBAM 2.5 サーバー ソフトウェアのインストール</span><span class="sxs-lookup"><span data-stu-id="46de1-103">Installing the MBAM 2.5 Server Software</span></span>


<span data-ttu-id="46de1-104">このトピックでは、microsoft bitlocker の管理と監視 (MBAM) 2.5 サーバーソフトウェアをインストールする方法について説明します。 Microsoft BitLocker の管理と監視のセットアップウィザードを使用するか、コマンドラインパラメーターを使用します。</span><span class="sxs-lookup"><span data-stu-id="46de1-104">This topic describes how to install the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard or by using command-line parameters.</span></span> <span data-ttu-id="46de1-105">MBAM 2.5 サーバー機能を構成している各サーバーに対して、サーバーのインストールプロセスを繰り返します。</span><span class="sxs-lookup"><span data-stu-id="46de1-105">Repeat the server installation process for each server on which you are configuring MBAM 2.5 Server features.</span></span> <span data-ttu-id="46de1-106">インストールが完了したら、サーバー機能を構成する手順について「 [MBAM 2.5 サーバー機能を構成](configuring-the-mbam-25-server-features.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="46de1-106">After you finish the installation, see [Configuring the MBAM 2.5 Server Features](configuring-the-mbam-25-server-features.md) for steps about configuring the Server features.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="46de1-107">開始する前に</span><span class="sxs-lookup"><span data-stu-id="46de1-107">Before you start</span></span></th>
<th align="left"><span data-ttu-id="46de1-108">説明</span><span class="sxs-lookup"><span data-stu-id="46de1-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46de1-109">MBAM 2.5 の計画情報を確認する</span><span class="sxs-lookup"><span data-stu-id="46de1-109">Review the MBAM 2.5 planning information</span></span></p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)"><span data-ttu-id="46de1-110">スタンドアロン トポロジおよび Configuration Manager 統合トポロジの MBAM 2.5 サーバー前提条件</span><span class="sxs-lookup"><span data-stu-id="46de1-110">MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies</span></span></a></p></li>
<li><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)"><span data-ttu-id="46de1-111">MBAM 2.5 がサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="46de1-111">MBAM 2.5 Supported Configurations</span></span></a></p></li>
<li><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="46de1-112">MBAM 2.5 のアーキテクチャの概要</span><span class="sxs-lookup"><span data-stu-id="46de1-112">High-Level Architecture for MBAM 2.5</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46de1-113">ログファイルを取得する方法を確認する</span><span class="sxs-lookup"><span data-stu-id="46de1-113">Read how to get log files</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-114">既定では、ログファイルはローカルコンピューターの% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="46de1-114">By default, log files are created in the local computer’s %temp% folder.</span></span> <span data-ttu-id="46de1-115">ログファイルを% temp% フォルダーではなく特定の場所に書き込むには <strong> </strong> 、/log の <strong> location 引数を使用し </strong> &lt; <em> </em> &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="46de1-115">To write the log files to a specific location rather than to the <strong>%temp</strong>% folder, use the <strong>/log</strong> &lt;<em>location</em>&gt; argument.</span></span></p>
<p><span data-ttu-id="46de1-116">追加のイベントは、 <strong> Mbam セットアップ </strong> または <strong> Mbam-Web </strong> ノード ([ <strong> アプリケーションとサービスログ] の [Microsoft Windows] の下 &gt; &gt; </strong> ) の [イベントビューアー] に記録される場合があります。</span><span class="sxs-lookup"><span data-stu-id="46de1-116">Additional events might be logged in Event Viewer in the <strong>MBAM-Setup</strong> or <strong>MBAM-Web</strong> nodes under <strong>Applications and Services Logs &gt; Microsoft &gt; Windows</strong>.</span></span> <span data-ttu-id="46de1-117">たとえば、MBAM をアンインストールした場合、アンインストーラーは、EventViewer の MBAM セットアップと MBAM Web ログもアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="46de1-117">For example, if you uninstall MBAM, the uninstaller will also uninstall the MBAM-Setup and MBAM-Web logs in EventViewer.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="46de1-118">Microsoft BitLocker の管理と監視のセットアップウィザードを使用して MBAM 2.5 サーバーソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="46de1-118">Installing the MBAM 2.5 Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard</span></span>


<span data-ttu-id="46de1-119">Microsoft BitLocker の管理と監視のセットアップウィザードを使用して、MBAM サーバーソフトウェアをインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="46de1-119">Use these steps to install the MBAM Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="46de1-120">ウィザードを使用して MBAM 2.5 サーバーソフトウェアをインストールするには</span><span class="sxs-lookup"><span data-stu-id="46de1-120">To install the MBAM 2.5 Server software by using the wizard</span></span>**

1.  <span data-ttu-id="46de1-121">MBAM をインストールするサーバーで**MBAMserversetup.exe**を実行して、Microsoft BitLocker の管理と監視のセットアップウィザードを開始します。</span><span class="sxs-lookup"><span data-stu-id="46de1-121">On the server where you want to install MBAM, run **MBAMserversetup.exe** to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2.  <span data-ttu-id="46de1-122">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46de1-122">On the **Welcome** page, click **Next**.</span></span>

3.  <span data-ttu-id="46de1-123">Microsoft ソフトウェアライセンス条項を読んで同意し、[**次へ**] をクリックしてインストールを続行します。</span><span class="sxs-lookup"><span data-stu-id="46de1-123">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="46de1-124">更新プログラムを確認するときに Microsoft Update を使用するかどうかを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46de1-124">Choose whether to use Microsoft Update when you check for updates, and then click **Next**.</span></span>

5.  <span data-ttu-id="46de1-125">カスタマーエクスペリエンス向上プログラムに参加するかどうかを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46de1-125">Choose whether to participate in the Customer Experience Improvement Program, and then click **Next**.</span></span>

6.  <span data-ttu-id="46de1-126">インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46de1-126">To start the installation, click **Install**.</span></span>

7.  <span data-ttu-id="46de1-127">MBAM サーバーソフトウェアのインストールが完了した後でサーバーの機能を構成するには、[**ウィザードを終了した後に MBAM サーバーの構成を実行**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="46de1-127">To configure the server features after the MBAM Server software finishes installing, select the **Run MBAM Server Configuration after the wizard closes** check box.</span></span> <span data-ttu-id="46de1-128">または、[**スタート**] メニューで作成した**mbam server 構成**ショートカットを使用して、mbam を後で構成することもできます。</span><span class="sxs-lookup"><span data-stu-id="46de1-128">Alternatively, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.</span></span>

8.  <span data-ttu-id="46de1-129">**[完了]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="46de1-129">Click **Finish**.</span></span>

## <span data-ttu-id="46de1-130">コマンドプロンプトウィンドウを使用して MBAM 2.5 サーバーソフトウェアをインストールする</span><span class="sxs-lookup"><span data-stu-id="46de1-130">Installing the MBAM 2.5 Server software by using a Command Prompt window</span></span>


<span data-ttu-id="46de1-131">コマンドプロンプトで、次のコマンドのようなコマンドを入力して、MBAM サーバーソフトウェアをインストールします。</span><span class="sxs-lookup"><span data-stu-id="46de1-131">At a command prompt, type a command similar to the following command to install the MBAM Server software.</span></span>

``` syntax
MbamServerSetup.exe MBAMServerInstall.log
CEIPENABLED=True OPTIN_FOR_MICROFOST_UPDATES=True INSTALLDIR=c:\mbaminstall
```

<span data-ttu-id="46de1-132">次の表では、MBAM 2.5 サーバーソフトウェアをインストールするためのコマンドラインパラメーターについて説明します。</span><span class="sxs-lookup"><span data-stu-id="46de1-132">The following table describes the command-line parameters for installing the MBAM 2.5 Server software.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="46de1-133">パラメーター</span><span class="sxs-lookup"><span data-stu-id="46de1-133">Parameter</span></span></th>
<th align="left"><span data-ttu-id="46de1-134">パラメーター値</span><span class="sxs-lookup"><span data-stu-id="46de1-134">Parameter value</span></span></th>
<th align="left"><span data-ttu-id="46de1-135">説明</span><span class="sxs-lookup"><span data-stu-id="46de1-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46de1-136">CEIPENABLED</span><span class="sxs-lookup"><span data-stu-id="46de1-136">CEIPENABLED</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-137">True False</span><span class="sxs-lookup"><span data-stu-id="46de1-137">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-138">True-カスタマーエクスペリエンス向上プログラムに参加します。これにより、どの MBAM 機能を改善することができます。</span><span class="sxs-lookup"><span data-stu-id="46de1-138">True - participate in the Customer Improvement Experience Program, which helps Microsoft identify which MBAM features to improve.</span></span></p>
<p><span data-ttu-id="46de1-139">False –カスタマーエクスペリエンス向上プログラムに参加しないでください。</span><span class="sxs-lookup"><span data-stu-id="46de1-139">False – do not participate in the Customer Improvement Experience Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46de1-140">OPTIN_FOR_MICROSOFT_UPDATES</span><span class="sxs-lookup"><span data-stu-id="46de1-140">OPTIN_FOR_MICROSOFT_UPDATES</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-141">True False</span><span class="sxs-lookup"><span data-stu-id="46de1-141">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-142">True-Microsoft Update を使用して、コンピューターをセキュリティで保護し、Windows やその他の Microsoft 製品 (MBAM を含む) を最新の状態に保ちます。</span><span class="sxs-lookup"><span data-stu-id="46de1-142">True - use Microsoft Update to keep your computer secure and up-to-date for Windows and other Microsoft products, including MBAM.</span></span></p>
<p><span data-ttu-id="46de1-143">False – Microsoft Update を使用しない</span><span class="sxs-lookup"><span data-stu-id="46de1-143">False – do not use Microsoft Update</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="46de1-144">INSTALLDIR</span><span class="sxs-lookup"><span data-stu-id="46de1-144">INSTALLDIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-145">&lt;パス&gt;</span><span class="sxs-lookup"><span data-stu-id="46de1-145">&lt;Path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-146">MBAM をインストールする場所。</span><span class="sxs-lookup"><span data-stu-id="46de1-146">Location where you want to install MBAM.</span></span></p>
<p><span data-ttu-id="46de1-147">例:</span><span class="sxs-lookup"><span data-stu-id="46de1-147">Example:</span></span></p>
<p><span data-ttu-id="46de1-148">INSTALLDIR = c:\ mbaminstall</span><span class="sxs-lookup"><span data-stu-id="46de1-148">INSTALLDIR=c:\mbaminstall</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="46de1-149">FORCE_UNINSTALL</span><span class="sxs-lookup"><span data-stu-id="46de1-149">FORCE_UNINSTALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-150">True False</span><span class="sxs-lookup"><span data-stu-id="46de1-150">True False</span></span></p></td>
<td align="left"><p><span data-ttu-id="46de1-151">True-すべての機能を削除できない場合でも、MBAM のアンインストールプロセスを続行します。</span><span class="sxs-lookup"><span data-stu-id="46de1-151">True - continue the process of uninstalling MBAM, even if any features fail to be removed.</span></span></p>
<p><span data-ttu-id="46de1-152">アンインストールカスタムアクションによって追加された MBAM サーバー機能の削除に失敗した場合は、アンインストールは失敗し、MBAM はインストールされたままになります。</span><span class="sxs-lookup"><span data-stu-id="46de1-152">False (default) if the uninstallation custom action fails to remove an added MBAM Server feature, the uninstallation fails, and MBAM remains installed.</span></span></p>
<p><span data-ttu-id="46de1-153">どちらの場合も、MBAM をアンインストールしようとしたときに正常に削除されたすべての機能は削除されます。</span><span class="sxs-lookup"><span data-stu-id="46de1-153">In both instances, any features that were successfully removed during the attempt to uninstall MBAM stay removed.</span></span></p></td>
</tr>
</tbody>
</table>

 



## <span data-ttu-id="46de1-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="46de1-154">Related topics</span></span>


[<span data-ttu-id="46de1-155">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="46de1-155">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="46de1-156">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="46de1-156">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="46de1-157">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="46de1-157">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="46de1-158">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="46de1-158">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="46de1-159">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="46de1-159">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





