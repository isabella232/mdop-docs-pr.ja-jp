---
title: Microsoft Application Virtualization Management System のリリースノート
description: Microsoft Application Virtualization Management System のリリースノート
author: dansimp
ms.assetid: e1a4d5ee-53c7-4b48-814c-a34ce0e698dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c34abab9a49bd69f760a9b531d0950cc581253c1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816164"
---
# <span data-ttu-id="cd8d6-103">Microsoft Application Virtualization Management System のリリースノート</span><span class="sxs-lookup"><span data-stu-id="cd8d6-103">Microsoft Application Virtualization Management System Release Notes</span></span>


<span data-ttu-id="cd8d6-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="cd8d6-105">**重要** アプリケーションの仮想化管理システムをインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-105">**Important** Read these Release Notes thoroughly before you install the Application Virtualization Management System.</span></span> <span data-ttu-id="cd8d6-106">これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="cd8d6-107">このドキュメントには、製品のドキュメントでは利用できない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="cd8d6-108">これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="cd8d6-109">これらのリリースノートは、この製品に含まれているコンテンツに置き換わるものです。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-109">These Release Notes supersede the content included with this product.</span></span>

 

<span data-ttu-id="cd8d6-110">既知の問題に関する最新情報については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=122918> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-110">For updated information about known issues, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=122918>.</span></span>

## <span data-ttu-id="cd8d6-111">Microsoft Application Virtualization 4.5 累積更新プログラムについて1</span><span class="sxs-lookup"><span data-stu-id="cd8d6-111">About Microsoft Application Virtualization 4.5 Cumulative Update 1</span></span>


<span data-ttu-id="cd8d6-112">これらのリリースノートは、Microsoft Application Virtualization 4.5 累積的な Update1 (app-v 4.5 CU1) で導入された変更を反映するように更新されています。これは、Application Virtualization (App-v) 4.5 の最新の更新プログラムを提供します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-112">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization4.5 Cumulative Update1 (App-V4.5 CU1), which provides the latest updates to Application Virtualization (App-V)4.5.</span></span> <span data-ttu-id="cd8d6-113">この累積的な更新プログラムには、次の変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-113">This cumulative update contains the following changes:</span></span>

-   <span data-ttu-id="cd8d6-114">Windows7 ベータ版と Windows Server2008R2 ベータ版のサポート: App-V 4.5 CU1 では、Windows7 ベータ版と Windows Server2008R2 ベータ版との互換性の問題に対処しています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-114">Support for Windows7 Beta and Windows Server2008R2 Beta: App-V4.5 CU1 addresses compatibility issues with Windows7 Beta and Windows Server2008R2 Beta.</span></span> <span data-ttu-id="cd8d6-115">Windows7 のプレ RTM バージョンのテスト環境では、CU1 が実行されていないことを示すブロックの問題についてサポートが提供されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-115">Support will be provided for blocking issues that prevent App-V4.5 CU1 running in a test environment on pre-RTM versions of Windows7.</span></span> <span data-ttu-id="cd8d6-116">これにより、アプリの Hyper-v 4.5 クライアントと Windows7 ベータの間の互換性が必要なテスト環境で仮想アプリケーションを正常に実行できることを確認できます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-116">This will help ensure that your virtual applications can run successfully in a test environment where compatibility between App-V4.5 Client and Windows7 Beta is required.</span></span>

    <span data-ttu-id="cd8d6-117">**重要** ライブオペレーティング環境の任意のバージョンの Windows7 または Windows Server2008R2 での CU1 の実行はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-117">**Important** Running App-V4.5 CU1 on any version of Windows7 or Windows Server2008R2 in a live operating environment is not supported.</span></span>

     

-   <span data-ttu-id="cd8d6-118">.NET Framework のシーケンス処理のサポートが改善されました: App-v 4.5 CU1 は、.NET Framework 3.5 以前のバージョンでは、WindowsXP (SP2 以降) でのシーケンスの問題に対応しています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-118">Improved support for sequencing the .NET Framework: App-V4.5 CU1 addresses previous issues with sequencing the .NET Framework3.5 and earlier on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="cd8d6-119">新機能の詳細については、TechNet の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-119">For more information about the new capabilities, see the TechNet article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

-   <span data-ttu-id="cd8d6-120">カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 CU1 には、app-v 4.5 RTM リリース以降に見つかった問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-120">Customer Feedback and Hotfix Rollup: App-V4.5 CU1 also includes a rollup up of fixes to address issues found since the App-V4.5 RTM release.</span></span> <span data-ttu-id="cd8d6-121">これには、既知の問題と、社内チーム、パートナー、および App-v 4.5 を使用しているお客様からのお客様からのフィードバックの組み合わせが含まれます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-121">This includes a combination of known issues and customer feedback from our internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="cd8d6-122">含まれている更新プログラムの完全な一覧については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=141258> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-122">For a full list of the included updates, see the KB article at <https://go.microsoft.com/fwlink/?LinkId=141258>.</span></span>

## <span data-ttu-id="cd8d6-123">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="cd8d6-123">About the Product Documentation</span></span>


<span data-ttu-id="cd8d6-124">Application Virtualization (app-v) の包括的なドキュメントは、Microsoft TechNet の Application Virtualization (App-v) TechCenter で入手でき <https://go.microsoft.com/fwlink/?LinkId=122939> ます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-124">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the Application Virtualization (App-V) TechCenter at <https://go.microsoft.com/fwlink/?LinkId=122939>.</span></span> <span data-ttu-id="cd8d6-125">TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-125">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Client, and the Application Virtualization Server.</span></span> <span data-ttu-id="cd8d6-126">また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-126">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="cd8d6-127">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="cd8d6-127">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="cd8d6-128">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアに使用できる最新のセキュリティ更新プログラムをインストールすることが重要です。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-128">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="cd8d6-129">詳細については、Microsoft セキュリティ Web サイトを参照してください <https://go.microsoft.com/fwlink/?LinkId=3482> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-129">For more information, see the Microsoft Security Web site at <https://go.microsoft.com/fwlink/?LinkId=3482>.</span></span>

## <span data-ttu-id="cd8d6-130">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="cd8d6-130">Providing Feedback</span></span>


<span data-ttu-id="cd8d6-131">Microsoft application virtualization TechCenter () のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ <https://go.microsoft.com/fwlink/?LinkId=122917> ます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-131">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System via a community forum on the Microsoft Application Virtualization TechCenter (<https://go.microsoft.com/fwlink/?LinkId=122917>).</span></span>

<span data-ttu-id="cd8d6-132">ドキュメントについてのフィードバックは、App-v ドキュメントチームに直接提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-132">You can also provide your feedback on the documentation directly to the App-V documentation team.</span></span> <span data-ttu-id="cd8d6-133">ドキュメントのフィードバックを appvdocs@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-133">Send your documentation feedback to appvdocs@microsoft.com.</span></span>

## <span data-ttu-id="cd8d6-134">Application Virtualization 4.5 CU1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="cd8d6-134">Known Issues with Application Virtualization4.5 CU1</span></span>


<span data-ttu-id="cd8d6-135">このセクションでは、Microsoft Application Virtualization (App-v) 4.5 CU1 の問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-135">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5 CU1.</span></span> <span data-ttu-id="cd8d6-136">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-136">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="cd8d6-137">この問題は、可能な限り将来のリリースで解決されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-137">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="cd8d6-138">setup.msi を使用してクライアントをアプリにインストールまたはアップグレードするためのガイダンス CU1</span><span class="sxs-lookup"><span data-stu-id="cd8d6-138">Guidance for installing or upgrading clients to App-V4.5 CU1 using setup.msi</span></span>

<span data-ttu-id="cd8d6-139">setup.msi を使用して app-v クライアントを App-v 4.5 CU1 にインストールまたはアップグレードする場合、前提条件は自動的にインストールされません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-139">When installing or upgrading your App-V clients to App-V4.5 CU1 by using setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="cd8d6-140">回避策いただけは、App-v クライアントを 4.5 CU1 にインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-140">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V client to4.5 CU1.</span></span> <span data-ttu-id="cd8d6-141">前提条件と App-v クライアントをインストールするための詳細な手順については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=144106> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-141">For detailed procedures for installing the prerequisites and the App-V client, see <https://go.microsoft.com/fwlink/?LinkId=144106>.</span></span>

<span data-ttu-id="cd8d6-142">この操作が完了したら、昇格された権限を持つ setup.msi を使用して、App V 4.5 CU1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-142">When this has been completed, install the App-V4.5 CU1 client by using setup.msi with elevated privileges.</span></span> <span data-ttu-id="cd8d6-143">このファイルは、インストーラ \ クライアントフォルダの App-v CU1 release メディアで入手できます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-143">This file is available on the App-V4.5 CU1 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="cd8d6-144">Microsoft アプリケーションエラー報告をインストールするときに、アプリ-V 4.5 CU1 デスクトップクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-144">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V4.5 CU1 Desktop client:</span></span>

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="cd8d6-145">または、App-v 4.5 CU1 ターミナルサービスクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-145">Alternatively, if you are installing or upgrading to the App-V 4.5 CU1 Terminal Services client, use the following command:</span></span>

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="cd8d6-146">**注** APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-146">**Note** The APPGUID parameter references the product code of the App-V client that you install or upgrade to.</span></span> <span data-ttu-id="cd8d6-147">製品コードは setup.msi ごとに固有です。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-147">The product code is unique for each setup.msi.</span></span> <span data-ttu-id="cd8d6-148">Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-148">You can use the Orca database editor or similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="cd8d6-149">この手順は、すべてのインストールまたは App-v 4.5 CU1 へのアップグレードのために必要です。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-149">This step is required for all installs or upgrades to App-V4.5 CU1.</span></span>

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a><span data-ttu-id="cd8d6-150">Windows7 ベータ版でシーケンス処理を行うときに、一部のアプリケーションが監視フェーズ中にインストールに失敗する場合がある</span><span class="sxs-lookup"><span data-stu-id="cd8d6-150">Some applications might fail to install during the monitoring phase when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="cd8d6-151">Windows7 ベータまたは Windows Installer 5.0 を搭載したコンピューターでシーケンスを実行している場合、監視フェーズ中に一部のアプリケーションがインストールに失敗することがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-151">When sequencing on Windows7 Beta or on a computer with Windows Installer5.0, some applications might fail to install during the monitoring phase.</span></span>

<span data-ttu-id="cd8d6-152">回避策いただけでは、Everyone グループに次のレジストリキーへのフルコントロールのアクセス許可を手動で与える必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-152">WORKAROUNDYou must manually grant the Everyone group Full Control permissions to the following registry key:</span></span>

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

<span data-ttu-id="cd8d6-153">**重要** [このオブジェクトの親から継承可能なアクセス許可を含める] オプションを設定するには、 **[詳細設定**] ボタンを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-153">**Important** You must use the **Advanced** button to set the “Include inheritable permissions from this object’s parent” option.</span></span>

 

### <span data-ttu-id="cd8d6-154">Windows7 ベータ版でシーケンス処理中にパッケージを保存できない</span><span class="sxs-lookup"><span data-stu-id="cd8d6-154">Unable to save packages when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="cd8d6-155">Windows7 ベータ版でシーケンスを実行している場合、共有違反のため、シーケンス処理されたパッケージを保存できない場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-155">When sequencing on Windows7 Beta, you might be unable to save your sequenced package because of a sharing violation.</span></span>

<span data-ttu-id="cd8d6-156">WORKAROUNDAs Microsoft Application Virtualization 4.5 シーケンスガイドの [ベストプラクティス] セクションで指定されています (「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=144108> )。シーケンスを開始する前に、次のソフトウェアプログラムをシャットダウンして無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-156">WORKAROUNDAs specified in the best practices section of the Microsoft Application Virtualization4.5 Sequencing Guide (see <https://go.microsoft.com/fwlink/?LinkId=144108>), you must shutdown and disable the following software programs before you begin sequencing:</span></span>

-   <span data-ttu-id="cd8d6-157">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="cd8d6-157">Windows Defender</span></span>

-   <span data-ttu-id="cd8d6-158">ウイルス対策ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cd8d6-158">Antivirus software</span></span>

-   <span data-ttu-id="cd8d6-159">ディスクの最適化ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="cd8d6-159">Disk defragmentation software</span></span>

-   <span data-ttu-id="cd8d6-160">Windows Search</span><span class="sxs-lookup"><span data-stu-id="cd8d6-160">Windows Search</span></span>

-   <span data-ttu-id="cd8d6-161">開いている Windows エクスプローラーセッション</span><span class="sxs-lookup"><span data-stu-id="cd8d6-161">Any open Windows Explorer session</span></span>

<span data-ttu-id="cd8d6-162">また、シーケンスステーションで Microsoft Update を実行していて、パッケージの更新プロセス中に更新プログラムをキャプチャしている場合は、シーケンスを開始する前に、VFS の除外として "C:\\Windows\\SoftwareDistribution" を追加する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-162">In addition, if you have Microsoft Update running on the sequencing station to capture updates during the package update process, you will need to add “C:\\Windows\\SoftwareDistribution” as a VFS exclusion before you start sequencing.</span></span>

### <span data-ttu-id="cd8d6-163">.NET Framework をシーケンス処理するときのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="cd8d6-163">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="cd8d6-164">.NET Framework のシーケンスを行うときに、Microsoft .NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとするため、システムのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-164">When sequencing the .NET Framework, you might experience reduced system performance because the Microsoft .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="cd8d6-165">WORKAROUNDWhen の順序付け .NET Framework では、監視フェーズを完了した後で、Microsoft .NET Framework NGEN サービス (mscorsvw.exe) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-165">WORKAROUNDWhen sequencing the .NET Framework, disable the Microsoft .NET Framework NGEN service (mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="cd8d6-166">Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [無効] に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-166">You must use the **Virtual Services** tab in the Sequencer and change the startup type to disabled.</span></span>

### <span data-ttu-id="cd8d6-167">Windows7 タスクバーの相互運用性に関する問題</span><span class="sxs-lookup"><span data-stu-id="cd8d6-167">Interoperability issues with the Windows7 Taskbar</span></span>

<span data-ttu-id="cd8d6-168">Windows7 で Application Virtualization クライアントを実行した場合、Windows7 タスクバーでは、仮想アプリケーションの複数のインスタンスが1つのタスクバーボタンに折りたたまれることはありません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-168">When you run the Application Virtualization Client on Windows7, the Windows7 taskbar does not collapse multiple instances of a virtual application into a single taskbar button.</span></span> <span data-ttu-id="cd8d6-169">さらに、アプリケーションが Windows7 タスクバーにピン留めされていない場合は、仮想アプリケーションのタスクバーボタンを右クリックしても、ジャンプリストは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-169">In addition, jump Lists do not appear when you right-click a taskbar button of a virtual application, unless the application has been pinned to the Windows7 taskbar.</span></span>

### <span data-ttu-id="cd8d6-170">Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行したユーザーに関連付けられているユーザー設定は削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-170">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstall will be deleted</span></span>

<span data-ttu-id="cd8d6-171">Microsoft Application Virtualization クライアントをアンインストールすると、Windows インストーラーによって、現在のユーザーのプロファイルから Application Virtualization の設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-171">When you uninstall the Microsoft Application Virtualization Client, the Windows Installer will remove Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="cd8d6-172">コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-172">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="cd8d6-173">回避策いただけは、仮想アプリケーションの実行に使用されない管理者アカウントを使用して、App-v クライアントのアンインストールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-173">WORKAROUNDYou should perform the App-V Client uninstall with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="cd8d6-174">シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-174">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="cd8d6-175">アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、[仮想ファイルシステム] タブまたは [仮想レジストリ] タブでパッケージを変更した場合、これらの変更は自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-175">If you open a package to perform an upgrade or have already run the Sequencing wizard with a new package and you make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="cd8d6-176">ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-176">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="cd8d6-177">コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-177">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="cd8d6-178">コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-178">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="cd8d6-179">昇格されたコマンドプロンプトを使ってコマンドライン Sequencer を WORKAROUNDRun します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-179">WORKAROUNDRun the command-line Sequencer using an elevated command prompt.</span></span>

### <span data-ttu-id="cd8d6-180">分散環境でのサーバー管理コンソールの構成</span><span class="sxs-lookup"><span data-stu-id="cd8d6-180">Server Management Console configuration in distributed environments</span></span>

<span data-ttu-id="cd8d6-181">主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理コンポーネントをインストールする必要がある場合、サーバーのインストールでは、適切に構成されている場合に、プライマリアプリケーション仮想化サーバーから別のサーバーに管理コンソールと Web サービスをインストールすることがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-181">If you need to install management components onto systems other than the primary Application Virtualization publishing and streaming server, the server install supports installing our management console and Web service on separate servers from the primary Application Virtualization Server when properly configured.</span></span>

<span data-ttu-id="cd8d6-182">複数のサーバー間で管理コンポーネントを配布するには、Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-182">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Web service is installed.</span></span>

### <span data-ttu-id="cd8d6-183">OSD ファイルで短い path 変数名を使うとエラーが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="cd8d6-183">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="cd8d6-184">エラー450478が表示された場合: 1F702339-0000010B "クライアントで仮想アプリケーションを起動すると、OSD の変数が正しく設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-184">If you receive error 450478-1F702339-0000010B “The directory name is invalid” when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="cd8d6-185">これは、アプリケーションのインストーラーでシーケンス中に短いパス名が設定されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-185">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="cd8d6-186">OSD ファイルに存在する任意の CSIDL 変数から末尾のチルダを WORKAROUNDRemove します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-186">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="cd8d6-187">コマンドライン Sequencer の DECODEPATH パラメーターの正しい構文</span><span class="sxs-lookup"><span data-stu-id="cd8d6-187">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="cd8d6-188">コマンドライン Sequencer でパッケージを開いて、そのパッケージを Q ドライブのルートにデコードする場合、 *DECODEPATH*パラメーターの構文に末尾のスラッシュを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-188">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of the Q drive, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="cd8d6-189">回避策いただけでは、 **Q:\\** (末尾の "\ \" 文字を省略します)**を使うこと**ができます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-189">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing “\\” character).</span></span>

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="cd8d6-190">4.2 パッケージをアップグレードするときに、仮想ファイルシステムの Windows Installer ファイルが原因で問題が発生する</span><span class="sxs-lookup"><span data-stu-id="cd8d6-190">When upgrading4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="cd8d6-191">4.2 からパッケージをアップグレードするときに問題が発生する可能性があります。これは、4.2 に既定で含まれていた Windows installer のシステムファイルと、シーケンス用のワークステーションにローカルにインストールされている Windows Installer ライブラリに関連する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-191">When upgrading a package from4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="cd8d6-192">次のファイルは、CSIDL \ _SYSTEM \ \ に保存されています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-192">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="cd8d6-193">cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="cd8d6-193">cabinet.dll</span></span>

<span data-ttu-id="cd8d6-194">msi.dll</span><span class="sxs-lookup"><span data-stu-id="cd8d6-194">msi.dll</span></span>

<span data-ttu-id="cd8d6-195">msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="cd8d6-195">msiexec.exe</span></span>

<span data-ttu-id="cd8d6-196">msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="cd8d6-196">msihnd.dll</span></span>

<span data-ttu-id="cd8d6-197">msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="cd8d6-197">msimsg.dlll</span></span>

<span data-ttu-id="cd8d6-198">上記のすべてのファイルをパッケージから WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-198">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="cd8d6-199">[ **VFS** ] タブのマッピングと、デコードパスにある CSIDL \ _SYSTEM フォルダー内の実際のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-199">Delete the mappings on the **VFS** tab as well as the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a><span data-ttu-id="cd8d6-200">WindowsXP では、クライアントのインストールログは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-200">On WindowsXP, client install logging is not enabled by default</span></span>

<span data-ttu-id="cd8d6-201">クライアントをインストールするときに、トラブルシューティングのためにインストールエラーがキャプチャされていることを確認するには、コマンドラインを使用してログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-201">When installing the client, to ensure that any install errors are captured for troubleshooting purposes, you should enable logging by using the command line.</span></span>

<span data-ttu-id="cd8d6-202">次の例に示すように、パラメーター */l\ \* vx! log.txt*をコマンドラインに WORKAROUNDAdd します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-202">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

<span data-ttu-id="cd8d6-203">setup.exe/s/v "/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="cd8d6-203">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="cd8d6-204">log.txt "</span><span class="sxs-lookup"><span data-stu-id="cd8d6-204">log.txt”</span></span>

<span data-ttu-id="cd8d6-205">msiexec.exe/i setup.msi/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="cd8d6-205">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="cd8d6-206">log.txt</span><span class="sxs-lookup"><span data-stu-id="cd8d6-206">log.txt</span></span>

<span data-ttu-id="cd8d6-207">または、レジストリキーを次の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-207">Alternatively, you can set the registry key to the following value:</span></span>

<span data-ttu-id="cd8d6-208">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging" = "voicewarmupx!"</span><span class="sxs-lookup"><span data-stu-id="cd8d6-208">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>

### <span data-ttu-id="cd8d6-209">Kerberos 認証が機能するためには、サービスプリンシパル名 (Spn) が IIS に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-209">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="cd8d6-210">IIS 6.0 または 7.0 for the icon または OSD ファイルの取得とストリーミングを使用する場合、Kerberos 認証を有効にするには、Spn を次のように登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-210">When using IIS6.0 or7.0 for icon or OSD file retrieval and streaming of packages, for Kerberos authentication to be enabled, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="cd8d6-211">IIS サーバーで SETSPN.EXE リソースキットツールを使用して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-211">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="cd8d6-212">サーバーの完全修飾ドメイン名 (FQDN) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-212">The server fully qualified domain name (FQDN) must be used.</span></span>

    <span data-ttu-id="cd8d6-213">Setspn-r SOFTGRID/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="cd8d6-213">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>

    <span data-ttu-id="cd8d6-214">Setspn-r HTTP/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="cd8d6-214">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>

<span data-ttu-id="cd8d6-215">詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=131407> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-215">For more information, see <https://go.microsoft.com/fwlink/?LinkId=131407>.</span></span>

### <span data-ttu-id="cd8d6-216">RC からアップグレードする場合、クライアントログの既定のアクセス許可では、管理者以外のユーザーがトラブルシューティングとサポートのためにログにアクセスすることは許可されていません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-216">On upgrade from RC, the default permissions on client logs do not allow for non-admin users to access the logs for troubleshooting and support</span></span>

<span data-ttu-id="cd8d6-217">Application VirtualizationRC クライアントのクライアントログの既定のアクセス許可では、管理者以外の方法でログファイルにアクセスすることはできませんでしたが、これらのログアクセス許可に対する手動の変更は、クライアントが再起動したときに元に戻されました。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-217">The default permissions on client logs for the Application VirtualizationRC client did not allow for non-admin access to log files, and manual changes to these log permissions were reverted when clients were restarted.</span></span> <span data-ttu-id="cd8d6-218">これは、新しいクライアントのインストールのために RTM リリースで修正されましたが、RC からアップグレードした場合、既存のログファイルに対するカスタムアクセス許可はリセットされません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-218">This has been corrected in the RTM release for new client installs, but on upgrade from RC, the custom permissions on existing log files are not reset.</span></span> <span data-ttu-id="cd8d6-219">ただし、新しいログが作成された場合、またはログのリセット後に、ファイルに新しい既定のアクセス許可が設定されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-219">However, when any new logs are created or after a log reset, the files will have the new default permissions.</span></span>

<span data-ttu-id="cd8d6-220">回避策: アップグレードを実行するか、既存のクライアントログをリセットするか、手動でアクセス許可を変更します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-220">WORKAROUNDAfter the upgrade, reset existing client logs or manually change their permissions.</span></span>

### <span data-ttu-id="cd8d6-221">.NET の互換性の変更</span><span class="sxs-lookup"><span data-stu-id="cd8d6-221">.NET compatibility changes</span></span>

<span data-ttu-id="cd8d6-222">Microsoft Application Virtualization 累積 Update1 は、WindowsXP (SP2 以降) での .NET Framework のシーケンスをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-222">Microsoft Application Virtualization Cumulative Update1 supports sequencing the .NET Framework on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="cd8d6-223">SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-223">Sequencing routines for .NET applications that were written for SoftGrid4.2 might need to be updated when used with the App-V4.5 Sequencer.</span></span> <span data-ttu-id="cd8d6-224">詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-224">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="cd8d6-225">App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない</span><span class="sxs-lookup"><span data-stu-id="cd8d6-225">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="cd8d6-226">ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-226">Check for the following error in the log: ”The Application Virtualization Client could not parse the OSD file”.</span></span> <span data-ttu-id="cd8d6-227">Microsoft Application Virtualization 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-227">The Microsoft Application Virtualization4.5 client filters out applications that have an OSD file containing an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="cd8d6-228">OSD ファイルから空の OS タグを WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-228">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="cd8d6-229">特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です</span><span class="sxs-lookup"><span data-stu-id="cd8d6-229">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="cd8d6-230">サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーなどのサーバーのコアプロセスは、ファイアウォールを介してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-230">For the server to stream applications correctly, the server's core processes, including the dispatcher, need access through the firewall.</span></span>

<span data-ttu-id="cd8d6-231">次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 sghwsvr.exe と sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-231">WORKAROUNDSet exemptions in the server's firewall for the following processes: sghwsvr.exe and sghwdsptr.exe.</span></span> <span data-ttu-id="cd8d6-232">これは、App-v 管理サーバーと App-v Streaming Server に適用されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-232">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="cd8d6-233">新しい Visual Basic ランタイムを必要とするシーケンスパッケージが失敗することがある</span><span class="sxs-lookup"><span data-stu-id="cd8d6-233">Sequencing packages that require new Visual Basic runtimes might fail</span></span>

<span data-ttu-id="cd8d6-234">古いバージョンの VBruntime がインストールされているシステムで、新しいバージョンの Visual Basic (VB) ランタイムを使っているパッケージをシーケンスすると、パッケージを使おうとすると、クラッシュまたはその他の予期しない動作が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-234">If you sequence a package that uses a newer version of a Visual Basic (VB) runtime on a system where an older version of the VBruntime is installed, you might see a crash or other unexpected behavior when you try to use your package.</span></span> <span data-ttu-id="cd8d6-235">たとえば、vbruntime のバージョン6.00.9782 を使う Microsoft Money2007 を、6.00.9690 のバージョンの WindowsXP システムで使っている場合、その古い VBruntime を使って別の WindowsXP システムで実行しようとすると、請求書デザイナーでクラッシュが発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-235">For example, if you try to sequence Microsoft Money2007, which uses version6.00.9782 of the VBruntime, on a WindowsXP system with version6.00.9690 of the VBruntime, you might see a crash in the Invoice Designer when you try to run it on another WindowsXP system with that older VBruntime.</span></span>

<span data-ttu-id="cd8d6-236">回避策: アプリケーションをシーケンスコンピューターにインストールしているときに、まだ監視しているときに、適切な (新しい) VBruntime を、実行可能ファイルが開始されたパッケージ内のディレクトリにコピーします。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-236">WORKAROUNDAfter installing the application on the sequencing computer, while still monitoring, copy the correct (newer) VBruntime to the directory in the package from where the executable is started.</span></span> <span data-ttu-id="cd8d6-237">これにより、シーケンス処理されたアプリケーションで、開始時に、必要なバージョンの VBruntime を見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-237">This allows the sequenced application to find the expected version of the VBruntime when it is started.</span></span>

<span data-ttu-id="cd8d6-238">**重要** この問題は、Microsoft Application Virtualization 4.5 の累積 Update1 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-238">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

### <span data-ttu-id="cd8d6-239">サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない</span><span class="sxs-lookup"><span data-stu-id="cd8d6-239">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="cd8d6-240">App-v Management Server は、MSXML6 によって異なります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-240">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="cd8d6-241">ただし、たとえば、MSXML6 がまだインストールされていないシステム上で "msiexec.exe-i setup.msi/qn" というコマンドを使用してインストーラーをサイレントモードで実行した場合、インストーラーでは見つからない依存関係が表示されず、そのままインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-241">However, if you run the installer in silent mode—for example, by using the command “msiexec -i setup.msi /qn” on a system where MSXML6 is not already installed—the installer does not notice the missing dependency and installs anyway.</span></span> <span data-ttu-id="cd8d6-242">最も一般的な結果として、クライアントが App-v Management Server から発行情報を更新しようとすると、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-242">The most common result is that when clients attempt to refresh publishing information from the App-V Management Server, they will see failures.</span></span>

<span data-ttu-id="cd8d6-243">WORKAROUNDVerify は、MSXML6 がシステムにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-243">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent install of the App-V Management Server.</span></span>

### <span data-ttu-id="cd8d6-244">Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800</span><span class="sxs-lookup"><span data-stu-id="cd8d6-244">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="cd8d6-245">Application virtualization management Service server のローカル管理者ではない Application Virtualization 管理者が、Application Virtualization 管理コンソールに接続しようとしたときに、エラー (エラーコード: 000C800) を受け取ります。この場合は、Sftmmc/.udl へのアクセスが拒否されたことを示します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-245">An Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server will receive an error (Error code: 000C800) when attempting to connect to the Application Virtualization Management Console, and the sftmmc.log entry will indicate that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="cd8d6-246">Application virtualization 管理コンソールに正常に接続するには、application Virtualization Management Service サーバーのローカル管理者ではないアプリケーション仮想化管理者が、少なくとも SftMgmt .udl ファイルへの読み取りと実行のアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-246">To successfully connect to the Application Virtualization Management Console, an Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server must have at least read and execute access to the SftMgmt.udl file.</span></span>

<span data-ttu-id="cd8d6-247">アプリケーションの仮想化管理者には、% s ドライブ% ¥ Program filesの Virt ファイルに対する読み取りと実行のアクセス許可を付与する必要があります。 Microsoft System Center App Management server¥ Virt Management Service。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-247">The Application Virtualization administrators must be given read and execute permissions to the SftMgmt.UDL file under %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="cd8d6-248">KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される</span><span class="sxs-lookup"><span data-stu-id="cd8d6-248">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="cd8d6-249">KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-249">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="cd8d6-250">WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-250">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1 and then set the other parameters after deployment.</span></span> <span data-ttu-id="cd8d6-251">App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-251">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="cd8d6-252">ADM テンプレートはにあり <https://go.microsoft.com/fwlink/?LinkId=121835> ます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-252">The ADM Template can be found at <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

### <span data-ttu-id="cd8d6-253">シマンテック Endpoint Protection での仮想アプリケーションの初期化エラー</span><span class="sxs-lookup"><span data-stu-id="cd8d6-253">Error initializing virtual applications with Symantec Endpoint Protection</span></span>

<span data-ttu-id="cd8d6-254">アプリケーションとデバイスコントロール機能を有効にして Symantec Endpoint Protection を使用すると、仮想アプリケーションの起動に失敗することがあります。 "アプリケーションは適切に初期化できませんでした (0xc000007b)" というエラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-254">When using Symantec Endpoint Protection with the Application and Device Control feature enabled, virtual applications might fail to start, with the error “The application failed to initialize properly (0xc000007b)”.</span></span> <span data-ttu-id="cd8d6-255">詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=125851> 。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-255">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=125851>.</span></span>

<span data-ttu-id="cd8d6-256">**重要** この問題は、Microsoft Application Virtualization 4.5 の累積 Update1 で修正されました。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-256">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

## <span data-ttu-id="cd8d6-257">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="cd8d6-257">Release Notes Copyright Information</span></span>


<span data-ttu-id="cd8d6-258">このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-258">Information in this document, including URL and other Internet Web site references, is subject to change without notice, and is provided for informational purposes only.</span></span> <span data-ttu-id="cd8d6-259">このドキュメントを使用することによるすべてのリスクは、ユーザーにはとどまりません。 Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-259">The entire risk of the use or results of the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="cd8d6-260">ここで例示した会社、組織、製品、人物、イベントの例は架空のものです。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-260">The example companies, organizations, products, people and events depicted herein are fictitious.</span></span> <span data-ttu-id="cd8d6-261">実際の会社、組織、製品、人物、またはイベントとの関係はありません。また、推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-261">No association with any real company, organization, product, person or event is intended or should be inferred.</span></span> <span data-ttu-id="cd8d6-262">お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-262">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="cd8d6-263">このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-263">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="cd8d6-264">Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-264">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="cd8d6-265">Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-265">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="cd8d6-266">Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory、および ActiveSync は、U.S.A. やその他の国において、マイクロソフトコーポレーションの登録商標または商標です。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-266">Microsoft, MS-DOS, Windows, WindowsServer, Windows Vista, Active Directory, and ActiveSync are either registered trademarks or trademarks of MicrosoftCorporation in the U.S.A. and/or other countries.</span></span>

<span data-ttu-id="cd8d6-267">ここに記載されている実際の会社と製品の名前は、各所有者の商標である場合があります。</span><span class="sxs-lookup"><span data-stu-id="cd8d6-267">The names of actual companies and products mentioned herein may be the trademarks of their respective owners.</span></span>

 

 





