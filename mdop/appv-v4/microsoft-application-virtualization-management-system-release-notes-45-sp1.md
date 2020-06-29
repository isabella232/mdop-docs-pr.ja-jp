---
title: Microsoft Application Virtualization Management System のリリースノート 4.5 SP1
description: Microsoft Application Virtualization Management System のリリースノート 4.5 SP1
author: dansimp
ms.assetid: 5d6b11ea-7b87-4084-9a7c-0d831f247aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c24d2e98ad09460ca22e4b29d75ae2b9c72d0bf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816157"
---
# <span data-ttu-id="2e489-103">Microsoft Application Virtualization Management System のリリースノート 4.5 SP1</span><span class="sxs-lookup"><span data-stu-id="2e489-103">Microsoft Application Virtualization Management System Release Notes 4.5 SP1</span></span>


<span data-ttu-id="2e489-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="2e489-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="2e489-105">**重要** アプリケーションの仮想化管理システムをインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="2e489-105">**Important** Read these Release Notes thoroughly before you install the Application Virtualization Management System.</span></span> <span data-ttu-id="2e489-106">これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="2e489-107">これらのリリースノートには、製品のマニュアルに記載されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-107">These Release Notes contain information that is not available in the product documentation.</span></span> <span data-ttu-id="2e489-108">これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span>

 

<span data-ttu-id="2e489-109">既知の問題に関する最新情報については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=122918> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-109">For updated information about known issues, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=122918>.</span></span>

## <span data-ttu-id="2e489-110">Microsoft Application Virtualization 4.5 Service Pack 1 について</span><span class="sxs-lookup"><span data-stu-id="2e489-110">About Microsoft Application Virtualization 4.5 Service Pack 1</span></span>


<span data-ttu-id="2e489-111">これらのリリースノートは、Microsoft Application Virtualization (App-v) 4.5 Service Pack1 (SP1) で導入された変更を反映するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="2e489-111">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization (App-V)4.5 Service Pack1 (SP1).</span></span> <span data-ttu-id="2e489-112">この service pack には、次の変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-112">This service pack contains the following changes:</span></span>

-   <span data-ttu-id="2e489-113">Windows 7 および Windows Server 2008 R2: App-v 4.5 SP1 は、windows 7 および Windows Server 2008 R2 のサポートを提供します。これには、タスクバー、AppLocker、BranchCache、BitLocker To Go などの Windows 7 機能のサポートが含まれます。</span><span class="sxs-lookup"><span data-stu-id="2e489-113">Support for Windows 7 and Windows Server 2008 R2: App-V 4.5 SP1 provides support for Windows 7 and Windows Server 2008 R2, including support for Windows 7 features such as the taskbar, AppLocker, BranchCache, and BitLocker To Go.</span></span><span data-ttu-id="2e489-114">Windows Server 2008 R2 のサポートは、Application Virtualization サーバーのみを対象としています。</span><span class="sxs-lookup"><span data-stu-id="2e489-114"> Windows Server 2008 R2 support is for the Application Virtualization Server only.</span></span> <span data-ttu-id="2e489-115">Windows 7 の AppLocker のサポートについて詳しくは、「」をご覧ください <https://go.microsoft.com/fwlink/?LinkID=156732> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-115">For more information on AppLocker support in Windows 7, see <https://go.microsoft.com/fwlink/?LinkID=156732>.</span></span>

-   <span data-ttu-id="2e489-116">サードパーティの Kerberos 領域のサポート: App-v 4.5 SP1 は、信頼関係と、Windows ドメインと MIT Kerberos 領域間のマッピングされたユーザーアカウントを持ち、多くの大学で共通するシナリオである環境をサポートします。</span><span class="sxs-lookup"><span data-stu-id="2e489-116">Support for 3rd Party Kerberos Realms: App-V 4.5 SP1 provides support for environments that have a trust relationship and mapped user accounts between a Windows domain and an MIT Kerberos realm, which is a scenario that is common at many universities.</span></span> <span data-ttu-id="2e489-117">このサポートを有効にする方法については、Microsoft TechNet ライブラリのを参照してください <https://go.microsoft.com/fwlink/?LinkId=166004> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-117">For information on how to enable this support, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=166004>.</span></span>

-   <span data-ttu-id="2e489-118">HTTP/HTTPS を介したアプリケーションの発行とストリーミングのサポートが改善されました: App-v 4.5 SP1 では、Windows XP Home Edition、windows Vista Home Basic、Windows 7 Home Basic の HTTP/HTTPS プロトコルを使用して、アプリケーションの発行とストリーミングをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="2e489-118">Improved support for application publishing and streaming via HTTP/HTTPS: App-V 4.5 SP1 provides support for application publishing and streaming via the HTTP/HTTPS protocols for Windows XP Home Edition, Windows Vista Home Basic, and Windows 7 Home Basic.</span></span>

-   <span data-ttu-id="2e489-119">カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 SP1 には、Microsoft Application Virtualization (App-v) 4.5 CU1 リリース以降で検出された問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-119">Customer Feedback and Hotfix Rollup: App-V4.5 SP1 also includes a rollup up of fixes to address issues found since the Microsoft Application Virtualization (App-V)4.5 CU1 release.</span></span> <span data-ttu-id="2e489-120">この更新プログラムは、microsoft の内部チーム、パートナー、およびアプリ-V 4.5 を使用しているお客様からの既知の問題とお客様からのフィードバックによって生じます。</span><span class="sxs-lookup"><span data-stu-id="2e489-120">The updates are a result of a combination of known issues and customer feedback from our internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="2e489-121">更新プログラムの完全な一覧については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=167121> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-121">For a full list of the updates, see the KB article at <https://go.microsoft.com/fwlink/?LinkId=167121>.</span></span>

## <span data-ttu-id="2e489-122">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="2e489-122">About the Product Documentation</span></span>


<span data-ttu-id="2e489-123">Application Virtualization (app-v) の包括的なドキュメントは、Microsoft TechNet の Application Virtualization (App-v) TechCenter で入手でき <https://go.microsoft.com/fwlink/?LinkId=122939> ます。</span><span class="sxs-lookup"><span data-stu-id="2e489-123">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the Application Virtualization (App-V) TechCenter at <https://go.microsoft.com/fwlink/?LinkId=122939>.</span></span> <span data-ttu-id="2e489-124">TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-124">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Client, and the Application Virtualization Server.</span></span> <span data-ttu-id="2e489-125">また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="2e489-125">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="2e489-126">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="2e489-126">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="2e489-127">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="2e489-127">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="2e489-128">詳細については、Microsoft セキュリティ Web サイトを参照してください <https://go.microsoft.com/fwlink/?LinkId=3482> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-128">For more information, see the Microsoft Security Web site at <https://go.microsoft.com/fwlink/?LinkId=3482>.</span></span>

## <span data-ttu-id="2e489-129">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="2e489-129">Providing Feedback</span></span>


<span data-ttu-id="2e489-130">Microsoft application virtualization TechCenter () のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ <https://go.microsoft.com/fwlink/?LinkId=122917> ます。</span><span class="sxs-lookup"><span data-stu-id="2e489-130">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System via a community forum on the Microsoft Application Virtualization TechCenter (<https://go.microsoft.com/fwlink/?LinkId=122917>).</span></span>

<span data-ttu-id="2e489-131">ドキュメントについてのフィードバックは、App-v ドキュメントチームに直接提供することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e489-131">You can also provide your feedback on the documentation directly to the App-V documentation team.</span></span> <span data-ttu-id="2e489-132">ドキュメントのフィードバックを appvdocs@microsoft.com に送信します。</span><span class="sxs-lookup"><span data-stu-id="2e489-132">Send your documentation feedback to appvdocs@microsoft.com.</span></span>

## <span data-ttu-id="2e489-133">Application Virtualization 4.5 SP1 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="2e489-133">Known Issues with Application Virtualization4.5 SP1</span></span>


<span data-ttu-id="2e489-134">このセクションでは、Microsoft Application Virtualization (App-v) 4.5 SP1 の問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="2e489-134">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5 SP1.</span></span> <span data-ttu-id="2e489-135">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e489-135">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="2e489-136">この問題は、可能な限り、ソフトウェアの以降のリリースで対処される予定です。</span><span class="sxs-lookup"><span data-stu-id="2e489-136">Whenever possible, these issues will be addressed in later releases of the software.</span></span>

### <span data-ttu-id="2e489-137">サーバー管理コンソールをインストールするためのガイダンス</span><span class="sxs-lookup"><span data-stu-id="2e489-137">Guidance for installing Server Management Console</span></span>

<span data-ttu-id="2e489-138">主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理ソフトウェアをインストールする必要がある場合、サーバーのインストールでは、管理コンソールと管理 Web サービスを、プライマリアプリの管理サーバーから別のサーバーにインストールすることがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e489-138">If you need to install management software onto systems other than the primary Application Virtualization publishing and streaming server, the server install supports installing the Management Console and Management Web service on separate servers from the primary App-V Management Server.</span></span> <span data-ttu-id="2e489-139">複数のサーバー間で管理コンポーネントを配布するには、Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-139">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Web service is installed.</span></span> <span data-ttu-id="2e489-140">このサポートを有効にする方法については、Microsoft TechNet ライブラリの次のページを参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e489-140">For information on how to enable this support, please visit the Microsoft TechNet Library at</span></span> <https://go.microsoft.com/fwlink/?LinkId=166682>

### <span data-ttu-id="2e489-141">setup.msi を使用してクライアントをアプリ-V 4.5 SP1 にインストールまたはアップグレードするためのガイダンス</span><span class="sxs-lookup"><span data-stu-id="2e489-141">Guidance for installing or upgrading clients to App-V4.5 SP1 using setup.msi</span></span>

<span data-ttu-id="2e489-142">setup.msi を使用して app-v クライアントを App-v 4.5 SP1 にインストールまたはアップグレードすると、前提条件が自動的にインストールされることはありません。</span><span class="sxs-lookup"><span data-stu-id="2e489-142">When installing or upgrading your App-V clients to App-V 4.5 SP1 by using setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="2e489-143">回避策いただけは、app-v client toApp-V 4.5 SP1 をインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-143">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V client toApp-V 4.5 SP1.</span></span> <span data-ttu-id="2e489-144">前提条件と App-v クライアントをインストールするための詳細な手順については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=144106> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-144">For detailed procedures for installing the prerequisites and the App-V client, see <https://go.microsoft.com/fwlink/?LinkId=144106>.</span></span>

<span data-ttu-id="2e489-145">この操作が完了したら、昇格された特権で setup.msi を使って、App-v 4.5 SP1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="2e489-145">When this has been completed, install the App-V 4.5 SP1 client by using setup.msi with elevated privileges.</span></span> <span data-ttu-id="2e489-146">このファイルは、インストーラ \ クライアントフォルダーの App-v 4.5 SP1 リリースメディアで入手できます。</span><span class="sxs-lookup"><span data-stu-id="2e489-146">This file is available on the App-V 4.5 SP1 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="2e489-147">Microsoft アプリケーションエラー報告をインストールするときに、アプリ-V 4.5 SP1 デスクトップクライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e489-147">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V 4.5 SP1 Desktop client:</span></span>

    msiexec /i dw20shared.msi APPGUID={93468B43-C19D-44F9-8BCC-114076DB0443}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="2e489-148">または、リモートデスクトップサービス (以前のターミナルサービス) 用の App-v 4.5 SP1 クライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="2e489-148">Alternatively, if you are installing or upgrading to the App-V 4.5 SP1 Client for Remote Desktop Services (formerly Terminal Services), use the following command:</span></span>

    msiexec /i dw20shared.msi APPGUID={0042AD3C-99A4-4E58-B5F0-744D5AD96E1C} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="2e489-149">**注** APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。</span><span class="sxs-lookup"><span data-stu-id="2e489-149">**Note** The APPGUID parameter references the product code of the App-V client that you install or upgrade.</span></span> <span data-ttu-id="2e489-150">製品コードは setup.msi ごとに固有です。</span><span class="sxs-lookup"><span data-stu-id="2e489-150">The product code is unique for each setup.msi.</span></span> <span data-ttu-id="2e489-151">Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="2e489-151">You can use the Orca database editor or a similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="2e489-152">この手順は、すべてのインストールまたは App-v 4.5 SP1 へのアップグレードに必要です。</span><span class="sxs-lookup"><span data-stu-id="2e489-152">This step is required for all installations or upgrades to App-V 4.5 SP1.</span></span>

 

### <span data-ttu-id="2e489-153">.NET Framework をシーケンス処理するときのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="2e489-153">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="2e489-154">.NET Framework のシーケンスを行うときに、Microsoft .NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとするため、システムのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="2e489-154">When sequencing the .NET Framework, you might experience reduced system performance because the Microsoft .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="2e489-155">WORKAROUNDWhen の順序付け .NET Framework では、監視フェーズを完了した後で、Microsoft .NET Framework NGEN サービス (mscorsvw.exe) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="2e489-155">WORKAROUNDWhen sequencing the .NET Framework, disable the Microsoft .NET Framework NGEN service (mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="2e489-156">Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [無効] に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-156">You must use the **Virtual Services** tab in the Sequencer and change the startup type to disabled.</span></span>

### <span data-ttu-id="2e489-157">Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行したユーザーに関連付けられているユーザー設定は削除されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-157">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstall will be deleted</span></span>

<span data-ttu-id="2e489-158">App-v クライアントをアンインストールすると、Windows インストーラーによって、現在のユーザーのプロファイルから Application Virtualization の設定が削除されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-158">When you uninstall the App-V Client, the Windows Installer will remove Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="2e489-159">コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="2e489-159">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="2e489-160">回避策いただけは、仮想アプリケーションの実行に使用されない管理者アカウントを使用して、App-v クライアントのアンインストールを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-160">WORKAROUNDYou should perform the App-V Client uninstall with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="2e489-161">シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-161">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="2e489-162">アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、仮想ファイルシステムまたは仮想レジストリタブでパッケージを変更した場合、これらの変更は自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="2e489-162">If you open a package to perform an upgrade, or if you have already run the Sequencing wizard with a new package and make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="2e489-163">ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。</span><span class="sxs-lookup"><span data-stu-id="2e489-163">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="2e489-164">コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-164">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="2e489-165">コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="2e489-165">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="2e489-166">昇格されたコマンドプロンプトを使ってコマンドライン Sequencer を WORKAROUNDRun します。</span><span class="sxs-lookup"><span data-stu-id="2e489-166">WORKAROUNDRun the command-line Sequencer using an elevated command prompt.</span></span>

### <span data-ttu-id="2e489-167">OSD ファイルで短い path 変数名を使うとエラーが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="2e489-167">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="2e489-168">エラー450478が表示された場合: 1F702339-0000010B "クライアントで仮想アプリケーションを起動すると、OSD の変数が正しく設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-168">If you receive error 450478-1F702339-0000010B “The directory name is invalid” when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="2e489-169">これは、アプリケーションのインストーラーでシーケンス中に短いパス名が設定されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-169">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="2e489-170">OSD ファイルに存在する任意の CSIDL 変数から末尾のチルダを WORKAROUNDRemove します。</span><span class="sxs-lookup"><span data-stu-id="2e489-170">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="2e489-171">コマンドライン Sequencer の DECODEPATH パラメーターの正しい構文</span><span class="sxs-lookup"><span data-stu-id="2e489-171">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="2e489-172">コマンドライン Sequencer でパッケージを開いて、そのパッケージを Q ドライブのルートにデコードする場合、 *DECODEPATH*パラメーターの構文に末尾のスラッシュを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="2e489-172">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of the Q drive, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="2e489-173">回避策いただけでは、 **Q:\\** (末尾の "\ \" 文字を省略します)**を使うこと**ができます。</span><span class="sxs-lookup"><span data-stu-id="2e489-173">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing “\\” character).</span></span>

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="2e489-174">4.2 パッケージをアップグレードするときに、仮想ファイルシステムの Windows Installer ファイルが原因で問題が発生する</span><span class="sxs-lookup"><span data-stu-id="2e489-174">When upgrading4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="2e489-175">4.2 からパッケージをアップグレードするときに問題が発生する可能性があります。これは、4.2 に既定で含まれていた Windows installer のシステムファイルと、シーケンス用のワークステーションにローカルにインストールされている Windows Installer ライブラリに関連する問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-175">When upgrading a package from4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="2e489-176">次のファイルは、CSIDL \ _SYSTEM \ \ に保存されています。</span><span class="sxs-lookup"><span data-stu-id="2e489-176">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="2e489-177">cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="2e489-177">cabinet.dll</span></span>

<span data-ttu-id="2e489-178">msi.dll</span><span class="sxs-lookup"><span data-stu-id="2e489-178">msi.dll</span></span>

<span data-ttu-id="2e489-179">msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="2e489-179">msiexec.exe</span></span>

<span data-ttu-id="2e489-180">msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="2e489-180">msihnd.dll</span></span>

<span data-ttu-id="2e489-181">msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="2e489-181">msimsg.dlll</span></span>

<span data-ttu-id="2e489-182">上記のすべてのファイルをパッケージから WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="2e489-182">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="2e489-183">[ **VFS** ] タブのマッピングと、デコードパスにある CSIDL \ _SYSTEM フォルダー内の実際のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="2e489-183">Delete the mappings on the **VFS** tab as well as the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a><span data-ttu-id="2e489-184">WindowsXP では、クライアントのインストールログは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="2e489-184">On WindowsXP, client install logging is not enabled by default</span></span>

<span data-ttu-id="2e489-185">クライアントをインストールするときに、トラブルシューティングのためにインストールエラーがキャプチャされていることを確認するには、コマンドラインを使用してログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-185">When installing the client, to ensure that any install errors are captured for troubleshooting purposes, you should enable logging by using the command line.</span></span>

<span data-ttu-id="2e489-186">次の例に示すように、パラメーター */l\ \* vx! log.txt*をコマンドラインに WORKAROUNDAdd します。</span><span class="sxs-lookup"><span data-stu-id="2e489-186">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

<span data-ttu-id="2e489-187">setup.exe/s/v "/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="2e489-187">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="2e489-188">log.txt "</span><span class="sxs-lookup"><span data-stu-id="2e489-188">log.txt”</span></span>

<span data-ttu-id="2e489-189">msiexec.exe/i setup.msi/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="2e489-189">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="2e489-190">log.txt</span><span class="sxs-lookup"><span data-stu-id="2e489-190">log.txt</span></span>

<span data-ttu-id="2e489-191">または、レジストリキーを次の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="2e489-191">Alternatively, you can set the registry key to the following value:</span></span>

<span data-ttu-id="2e489-192">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging" = "voicewarmupx!"</span><span class="sxs-lookup"><span data-stu-id="2e489-192">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>

### <span data-ttu-id="2e489-193">Kerberos 認証が機能するためには、サービスプリンシパル名 (Spn) が IIS に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-193">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="2e489-194">IIS 6.0 または 7.0 for the icon または OSD ファイルの取得とストリーミングを使用する場合、Kerberos 認証を有効にするには、Spn を次のように登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-194">When using IIS6.0 or7.0 for icon or OSD file retrieval and streaming of packages, for Kerberos authentication to be enabled, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="2e489-195">IIS サーバーで SETSPN.EXE リソースキットツールを使用して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="2e489-195">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="2e489-196">サーバーの完全修飾ドメイン名 (FQDN) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-196">The server fully qualified domain name (FQDN) must be used.</span></span>

    <span data-ttu-id="2e489-197">Setspn-r SOFTGRID/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="2e489-197">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>

    <span data-ttu-id="2e489-198">Setspn-r HTTP/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="2e489-198">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>

<span data-ttu-id="2e489-199">詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=131407> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-199">For more information, see <https://go.microsoft.com/fwlink/?LinkId=131407>.</span></span>

### <span data-ttu-id="2e489-200">.NET の互換性の変更</span><span class="sxs-lookup"><span data-stu-id="2e489-200">.NET compatibility changes</span></span>

<span data-ttu-id="2e489-201">Microsoft Application Virtualization (App-v) 累積 Update1 以降では、WindowsXP (SP2 以降) での .NET Framework のシーケンスがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="2e489-201">Microsoft Application Virtualization (App-V) Cumulative Update1 or later supports sequencing the .NET Framework on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="2e489-202">SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="2e489-202">Sequencing routines for .NET applications that were written for SoftGrid4.2 might need to be updated when used with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="2e489-203">詳細と回避策については、のサポート技術情報の記事を参照してください <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="2e489-203">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="2e489-204">App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない</span><span class="sxs-lookup"><span data-stu-id="2e489-204">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="2e489-205">ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。</span><span class="sxs-lookup"><span data-stu-id="2e489-205">Check for the following error in the log: ”The Application Virtualization Client could not parse the OSD file”.</span></span> <span data-ttu-id="2e489-206">App-v 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="2e489-206">The App-V 4.5 client filters out applications that have an OSD file containing an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="2e489-207">OSD ファイルから空の OS タグを WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="2e489-207">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="2e489-208">特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です</span><span class="sxs-lookup"><span data-stu-id="2e489-208">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="2e489-209">サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーなどのサーバーのコアプロセスは、ファイアウォールを介してアクセスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-209">For the server to stream applications correctly, the server's core processes, including the dispatcher, need access through the firewall.</span></span>

<span data-ttu-id="2e489-210">次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 sghwsvr.exe と sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="2e489-210">WORKAROUNDSet exemptions in the server's firewall for the following processes: sghwsvr.exe and sghwdsptr.exe.</span></span> <span data-ttu-id="2e489-211">これは、App-v 管理サーバーと App-v Streaming Server に適用されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-211">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="2e489-212">サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない</span><span class="sxs-lookup"><span data-stu-id="2e489-212">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="2e489-213">App-v Management Server は、MSXML6 によって異なります。</span><span class="sxs-lookup"><span data-stu-id="2e489-213">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="2e489-214">ただし、サイレントモードでインストーラーを実行している場合 (たとえば、MSXML6 がまだインストールされていないシステム上で "msiexec.exe-i setup.msi/qn" というコマンドを使用した場合など)、インストーラーでは見つからない依存関係が検出されず、そのままインストールされます。</span><span class="sxs-lookup"><span data-stu-id="2e489-214">However, if you run the installer in silent mode—for example, by using the command “msiexec -i setup.msi /qn” on a system where MSXML6 is not already installed—the installer does not detect the missing dependency and installs anyway.</span></span> <span data-ttu-id="2e489-215">そのため、クライアントは、アプリからの公開情報を更新しようとすると、エラーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-215">Therefore, when clients attempt to refresh publishing information from the App-V Management Server, they will see failures.</span></span>

<span data-ttu-id="2e489-216">WORKAROUNDVerify は、MSXML6 がシステムにインストールされていることを示します。</span><span class="sxs-lookup"><span data-stu-id="2e489-216">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent install of the App-V Management Server.</span></span>

### <span data-ttu-id="2e489-217">Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800</span><span class="sxs-lookup"><span data-stu-id="2e489-217">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="2e489-218">Application hyper-v 管理 Web サービスサーバーのローカル管理者ではないアプリケーション仮想化管理者が、App-v 管理コンソールに接続しようとしたときにエラー (エラーコード: 000C800) を受け取ります。この場合は、sftmmc 対するアクセスが拒否されたことを示すメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-218">An Application Virtualization administrator who is not a local administrator on the App-V Management Web Service server will receive an error (Error code: 000C800) when attempting to connect to the App-V Management Console, and the sftmmc.log entry will indicate that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="2e489-219">App-v 管理コンソールに正常に接続するには、App-v Management Web サービスサーバーのローカル管理者権限を持たない管理者が、SftMgmt .udl ファイルの読み取りおよび実行のアクセス許可を少なくとも持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-219">To successfully connect to the App-V Management Console, an administrator who does not have local administrator rights on the App-V Management Web Service server must have at least read and execute permissions to the SftMgmt.udl file.</span></span>

<span data-ttu-id="2e489-220">アプリケーションの仮想化管理者には、% s ドライブ% ¥ Program filesの Virt ファイルに対する読み取りと実行のアクセス許可を付与する必要があります。 Microsoft System Center App Management server¥ Virt Management Service。</span><span class="sxs-lookup"><span data-stu-id="2e489-220">The Application Virtualization administrators must be given read and execute permissions to the SftMgmt.UDL file under %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="2e489-221">KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される</span><span class="sxs-lookup"><span data-stu-id="2e489-221">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="2e489-222">KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。</span><span class="sxs-lookup"><span data-stu-id="2e489-222">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="2e489-223">WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="2e489-223">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1 and then set the other parameters after deployment.</span></span> <span data-ttu-id="2e489-224">App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="2e489-224">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="2e489-225">ADM テンプレートはにあり <https://go.microsoft.com/fwlink/?LinkId=121835> ます。</span><span class="sxs-lookup"><span data-stu-id="2e489-225">The ADM Template can be found at <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

## <span data-ttu-id="2e489-226">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="2e489-226">Release Notes Copyright Information</span></span>


<span data-ttu-id="2e489-227">このドキュメントに記載されている情報 (URL などのインターネット Web サイトへの参照を含む) は、予告なしに変更される可能性があり、情報提供のみを目的として提供されます。</span><span class="sxs-lookup"><span data-stu-id="2e489-227">Information in this document, including URL and other Internet Web site references, is subject to change without notice and is provided for informational purposes only.</span></span> <span data-ttu-id="2e489-228">このドキュメントを使用することによる使用または結果のすべてのリスクは、ユーザーにはとどまりません。また、Microsoft Corporation は、明示的または黙示を問わず、いかなる保証も行いません。</span><span class="sxs-lookup"><span data-stu-id="2e489-228">The entire risk of the use or results from the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="2e489-229">特に記載がない限り、ここに記載されている会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、およびイベントは架空のものです。</span><span class="sxs-lookup"><span data-stu-id="2e489-229">Unless otherwise noted, the companies, organizations, products, domain names, e-mail addresses, logos, people, places, and events depicted in examples herein are fictitious.</span></span> <span data-ttu-id="2e489-230">実際の会社、組織、製品、ドメイン名、電子メールアドレス、ロゴ、人物、場所、イベントなどとの関連付けは、意図したものであるか、または推測されるものではありません。</span><span class="sxs-lookup"><span data-stu-id="2e489-230">No association with any real company, organization, product, domain name, e-mail address, logo, person, place, or event is intended or should be inferred.</span></span> <span data-ttu-id="2e489-231">お客様ご自身の責任において、適用されるすべての著作権関連法規に従ったご使用をお願いします。</span><span class="sxs-lookup"><span data-stu-id="2e489-231">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="2e489-232">このドキュメントのいかなる部分も、米国 Microsoft Corporation の書面による許諾を受けることなく、検索システムに複製、格納、導入したり、その目的を問わず、いかなる形態や手段であっても、転送することは禁じられています。ここでいう手段とは、電子的、機械的、複写、録音など、すべての手段を含みます。ただしこれは、著作権法上のお客様の権利を制限するものではありません。</span><span class="sxs-lookup"><span data-stu-id="2e489-232">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="2e489-233">Microsoft は、このドキュメントに記載されている内容に関して、特許、特許申請、商標、著作権、またはその他の知的財産権を有する場合があります。</span><span class="sxs-lookup"><span data-stu-id="2e489-233">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="2e489-234">Microsoft による使用許諾契約書によって明示的に許可されている場合を除き、このドキュメントの提供によって、これらの特許権、商標、著作権、またはその他の知的財産権のライセンスが貴社に供与されることはありません。</span><span class="sxs-lookup"><span data-stu-id="2e489-234">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="2e489-235">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="2e489-235">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="2e489-236">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="2e489-236">All other trademarks are property of their respective owners.</span></span>

 

 





