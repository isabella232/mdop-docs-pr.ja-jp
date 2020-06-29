---
title: App-V 4.5 SP2 リリース ノート
description: App-V 4.5 SP2 リリース ノート
author: dansimp
ms.assetid: 1b3a8a83-4523-4634-9f75-29bc22ca5815
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 35cff3b2a2c110a4d8beba883a4cf9332381ea60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10819854"
---
# <span data-ttu-id="6c8be-103">App-V 4.5 SP2 リリース ノート</span><span class="sxs-lookup"><span data-stu-id="6c8be-103">App-V 4.5 SP2 Release Notes</span></span>


<span data-ttu-id="6c8be-104">これらのリリースノートを検索するには、CTRL キーを押しながら F キーを押します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="6c8be-105">**重要** Microsoft Application Virtualization Management System をインストールする前に、これらのリリースノートをよくお読みください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-105">**Important** Read these Release Notes thoroughly before you install the Microsoft Application Virtualization Management System.</span></span> <span data-ttu-id="6c8be-106">これらのリリースノートには、Application Virtualization 管理システムを正常にインストールするために必要な情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="6c8be-107">これらのリリースノートには、製品のマニュアルに記載されていない情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-107">These Release Notes contain information that is not available in the product documentation.</span></span> <span data-ttu-id="6c8be-108">これらのリリースノートとその他の Application Virtualization 管理システムのドキュメントの間に不一致がある場合は、最新の変更を、権限のあるものと見なす必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span>

 

<span data-ttu-id="6c8be-109">既知の問題に関する最新情報については、Microsoft TechNet ライブラリの「 [app-v 4.5 SP2 リリースノート](https://go.microsoft.com/fwlink/?LinkId=184640)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=184640) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-109">For updated information about known issues, please visit the Microsoft TechNet Library at [App-V 4.5 SP2 Release Notes](https://go.microsoft.com/fwlink/?LinkId=184640) (https://go.microsoft.com/fwlink/?LinkId=184640).</span></span>

## <span data-ttu-id="6c8be-110">Microsoft Application Virtualization 4.5 Service Pack 2 について</span><span class="sxs-lookup"><span data-stu-id="6c8be-110">About Microsoft Application Virtualization 4.5 Service Pack 2</span></span>


<span data-ttu-id="6c8be-111">これらのリリースノートは、Microsoft Application Virtualization (App-v) 4.5 Service Pack2 (SP2) で導入された変更を反映するように更新されています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-111">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization (App-V)4.5 Service Pack2 (SP2).</span></span> <span data-ttu-id="6c8be-112">この service pack には、次の変更が含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-112">This service pack contains the following changes:</span></span>

-   <span data-ttu-id="6c8be-113">Office 2010 のサポート: App-V 4.5 SP2 では、Microsoft Office 2010 の仮想化がサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6c8be-113">Support for Office 2010: App-V4.5SP2 now supports the virtualization of Microsoft Office 2010.</span></span> <span data-ttu-id="6c8be-114">Microsoft Office 2010 を App-v 4.5 SP2 と順序付けるための規範となるガイダンスについては、「 [Microsoft App-v 4.6 で office 2010 をシーケンス処理するための規範ガイダンス](https://go.microsoft.com/fwlink/?LinkId=191539)」を参照してください https://go.microsoft.com/fwlink/?LinkId=191539) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-114">For prescriptive guidance for sequencing Microsoft Office 2010 with App-V 4.5 SP2, see [Prescriptive guidance for sequencing Office 2010 in Microsoft App-V 4.6](https://go.microsoft.com/fwlink/?LinkId=191539) (https://go.microsoft.com/fwlink/?LinkId=191539).</span></span>

-   <span data-ttu-id="6c8be-115">データベースミラーリングのサポート: App-v 4.5 SP2 では、Microsoft SQL Server データベースのミラーリングがサポートされるようになりました。</span><span class="sxs-lookup"><span data-stu-id="6c8be-115">Support for Database Mirroring: App-V4.5SP2 now supports Microsoft SQL Server Database Mirroring.</span></span> <span data-ttu-id="6c8be-116">App-v 環境でのデータベースミラーリングの構成の詳細については、「 [app-v () の MICROSOFT SQL Server ミラーリングサポートを構成する方法](https://go.microsoft.com/fwlink/?LinkId=190880)」を参照してください https://go.microsoft.com/fwlink/?LinkId=190880) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-116">For more information about configuring database mirroring in your App-V environment, see [How to Configure Microsoft SQL Server Mirroring Support for App-V](https://go.microsoft.com/fwlink/?LinkId=190880) (https://go.microsoft.com/fwlink/?LinkId=190880).</span></span>

-   <span data-ttu-id="6c8be-117">カスタマーフィードバックと修正プログラムのロールアップ: アプリ-V 4.5 SP2 には、アプリ-v 4.5 SP1 の後に見つかった問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-117">Customer Feedback and Hotfix Rollup: App-V4.5 SP2 also includes a rollup of fixes to address issues found after the App-V 4.5SP1 release.</span></span> <span data-ttu-id="6c8be-118">この更新プログラムでは、Microsoft の内部チーム、パートナー、および App-v を使用しているユーザーからの既知の問題とお客様からのフィードバックの組み合わせについて対処します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-118">The updates address a combination of known issues and customer feedback from Microsoft internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="6c8be-119">更新プログラムの完全な一覧については、 [Microsoft Application Virtualization 4.5 Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=191540) () に関する説明を参照して、Microsoft サポート技術情報の記事980847を参照してください https://go.microsoft.com/fwlink/?LinkId=191540) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-119">For a full list of the updates, see article 980847 in the Microsoft Knowledge Base (KB) at [Description of Microsoft Application Virtualization 4.5 Service Pack 2](https://go.microsoft.com/fwlink/?LinkId=191540) (https://go.microsoft.com/fwlink/?LinkId=191540).</span></span>

## <span data-ttu-id="6c8be-120">製品ドキュメントについて</span><span class="sxs-lookup"><span data-stu-id="6c8be-120">About the Product Documentation</span></span>


<span data-ttu-id="6c8be-121">Application Virtualization (App-v) の包括的なドキュメントは、 [Application Virtualization TechCenter ライブラリ](https://go.microsoft.com/fwlink/?LinkId=122939)() の Microsoft TechNet で入手でき https://go.microsoft.com/fwlink/?LinkId=122939) ます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-121">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the [Application Virtualization TechCenter Library](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span> <span data-ttu-id="6c8be-122">TechNet のドキュメントには、Application Virtualization Sequencer、Application Virtualization クライアント、Application Virtualization Server のオンラインヘルプが含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-122">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Clients, and the Application Virtualization Server.</span></span> <span data-ttu-id="6c8be-123">また、Application Virtualization Planning and Deployment Guide と Application Virtualization 運用ガイドも含まれています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-123">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="6c8be-124">セキュリティの脆弱性とウイルスから保護する</span><span class="sxs-lookup"><span data-stu-id="6c8be-124">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="6c8be-125">セキュリティの脆弱性やウイルスから保護するために、インストールされている新しいソフトウェアには、使用可能な最新のセキュリティ更新プログラムをインストールすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-125">To help protect against security vulnerabilities and viruses, we recommend that you install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="6c8be-126">詳細については、「 [Microsoft セキュリティ](https://go.microsoft.com/fwlink/?LinkId=3482)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=3482) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-126">For more information, see [Microsoft Security](https://go.microsoft.com/fwlink/?LinkId=3482) (https://go.microsoft.com/fwlink/?LinkId=3482).</span></span>

## <span data-ttu-id="6c8be-127">フィードバックの提供</span><span class="sxs-lookup"><span data-stu-id="6c8be-127">Provide Feedback</span></span>


<span data-ttu-id="6c8be-128">Application Virtualization TechCenter[アプリ-v ドキュメントフォーラム ()](https://go.microsoft.com/fwlink/?LinkId=122917)のコミュニティフォーラムを通じて、フィードバックを提供したり、提案を行ったり、問題を報告したりすることができ https://go.microsoft.com/fwlink/?LinkId=122917) ます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-128">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System through the community forum on the Application Virtualization TechCenter [App-V Documentation Forum](https://go.microsoft.com/fwlink/?LinkId=122917) (https://go.microsoft.com/fwlink/?LinkId=122917).</span></span>

<span data-ttu-id="6c8be-129">ドキュメントのフィードバックは、の App-v ドキュメントチームに直接送信することもでき <appvdocs@microsoft.com> ます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-129">You can also send your documentation feedback directly to the App-V documentation team at <appvdocs@microsoft.com>.</span></span>

## <span data-ttu-id="6c8be-130">Application Virtualization 4.5 SP2 の既知の問題</span><span class="sxs-lookup"><span data-stu-id="6c8be-130">Known Issues with Application Virtualization4.5SP2</span></span>


<span data-ttu-id="6c8be-131">このセクションでは、Microsoft Application Virtualization (App-v) 4.5 SP2 の問題に関する最新情報について説明します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-131">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5SP2.</span></span> <span data-ttu-id="6c8be-132">これらの問題は製品ドキュメントには記載されていないため、場合によっては、既存の製品ドキュメントに矛盾が生じることがあります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-132">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="6c8be-133">この問題は、可能な限り、ソフトウェアの以降のリリースで対処される予定です。</span><span class="sxs-lookup"><span data-stu-id="6c8be-133">Whenever possible, these issues will be addressed in later releases of the software.</span></span>

### <span data-ttu-id="6c8be-134">サーバー管理コンソールをインストールするためのガイダンス</span><span class="sxs-lookup"><span data-stu-id="6c8be-134">Guidance for installing Server Management Console</span></span>

<span data-ttu-id="6c8be-135">主要アプリケーション仮想化パブリッシングとストリーミングサーバー以外のシステムに管理ソフトウェアをインストールする必要がある場合、サーバーのインストールでは、Application Virtualization 管理コンソールと Application Virtualization 管理 Web サービスを、プライマリアプリの管理サーバーから別のサーバーにインストールすることがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-135">If you have to install management software on systems other than the primary Application Virtualization publishing and streaming server, the server installation supports installing the Application Virtualization Management Console and Application Virtualization Management Web service on separate servers from the primary App-V Management Server.</span></span> <span data-ttu-id="6c8be-136">複数のサーバー間で管理コンポーネントを配布するには、Application Virtualization Web サービスがインストールされているサーバーで Kerberos 委任を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-136">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Application Virtualization Web service is installed.</span></span> <span data-ttu-id="6c8be-137">このサポートを有効にする方法については、「[委任に対して信頼されるようにサーバーを構成する方法](https://go.microsoft.com/fwlink/?LinkId=166682)(」を参照してください https://go.microsoft.com/fwlink/?LinkId=166682) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-137">For information about how to enable this support, see [How to Configure the Server to be Trusted for Delegation](https://go.microsoft.com/fwlink/?LinkId=166682) (https://go.microsoft.com/fwlink/?LinkId=166682).</span></span>

### <span data-ttu-id="6c8be-138">Setup.msi を使用して、クライアントを App-v 4.5 SP2 にインストールまたはアップグレードするためのガイダンス</span><span class="sxs-lookup"><span data-stu-id="6c8be-138">Guidance for installing or upgrading clients to App-V4.5 SP2 by using Setup.msi</span></span>

<span data-ttu-id="6c8be-139">Setup.msi を使用して app-v クライアントを App-v 4.5 SP2 にインストールまたはアップグレードすると、前提条件が自動的にインストールされることはありません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-139">When installing or upgrading your App-V Clients to App-V 4.5 SP2 by using Setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="6c8be-140">回避策いただけは、アプリ-V 4.5 SP2 に App-v クライアントをインストールまたはアップグレードする前に、前提条件を手動でインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-140">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V Clients to App-V 4.5SP2.</span></span> <span data-ttu-id="6c8be-141">前提条件と App-v クライアントをインストールする方法について詳しくは、「[コマンドラインを使用してクライアントをインストールする方法](https://go.microsoft.com/fwlink/?LinkId=144106)」をご覧ください https://go.microsoft.com/fwlink/?LinkId=144106) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-141">For detailed procedures about how to install the prerequisites and the App-V Client, see [How to Install the Client by Using the Command Line](https://go.microsoft.com/fwlink/?LinkId=144106) (https://go.microsoft.com/fwlink/?LinkId=144106).</span></span>

<span data-ttu-id="6c8be-142">この操作が完了したら、管理者の資格情報を使用して Setup.msi を使用して、App-v 4.5 SP2 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-142">When this has been completed, install the App-V 4.5 SP2 Clients by using Setup.msi with administrative credentials.</span></span> <span data-ttu-id="6c8be-143">このファイルは、インストーラ \ \ クライアントフォルダーの App-v 4.5 SP2 リリースメディアで利用できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-143">This file is available on the App-V 4.5 SP2 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="6c8be-144">Microsoft アプリケーションエラー報告をインストールするときに、4.5 アプリをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-144">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V 4.5 SP2 Desktop Client:</span></span>

**<span data-ttu-id="6c8be-145">msiexec/i dw20shared.msi APPGUID = {C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D} allusers = 1 再起動 = 抑制 = すべての REINSTALLMODE = vomus</span><span class="sxs-lookup"><span data-stu-id="6c8be-145">msiexec /i dw20shared.msi APPGUID={C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus</span></span>**

<span data-ttu-id="6c8be-146">または、リモートデスクトップサービス (旧ターミナルサービス) 用の App-v 4.5 SP2 クライアントをインストールまたはアップグレードする場合は、次のコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-146">Alternatively, if you are installing or upgrading to the App-V 4.5 SP2 Client for Remote Desktop Services (formerly Terminal Services), use the following command:</span></span>

**<span data-ttu-id="6c8be-147">msiexec/i dw20shared.msi APPGUID = {ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5} allusers = 1 再起動 = 抑制 = すべての REINSTALLMODE = vomus</span><span class="sxs-lookup"><span data-stu-id="6c8be-147">msiexec /i dw20shared.msi APPGUID={ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus</span></span>**

**<span data-ttu-id="6c8be-148">注</span><span class="sxs-lookup"><span data-stu-id="6c8be-148">Note</span></span>**  
-   <span data-ttu-id="6c8be-149">APPGUID パラメーターは、インストールまたはアップグレードする App-v クライアントの製品コードを参照します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-149">The APPGUID parameter references the product code of the App-V Clients that you install or upgrade.</span></span> <span data-ttu-id="6c8be-150">製品コードは Setup.msi ごとに固有です。</span><span class="sxs-lookup"><span data-stu-id="6c8be-150">The product code is unique for each Setup.msi.</span></span> <span data-ttu-id="6c8be-151">Orca データベースエディターまたは同様のツールを使用して、Windows インストーラファイルを調査し、製品コードを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-151">You can use the Orca Database Editor or a similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="6c8be-152">この手順は、すべてのインストールまたは App-v 4.5 SP2 へのアップグレードに必要です。</span><span class="sxs-lookup"><span data-stu-id="6c8be-152">This step is required for all installations or upgrades to App-V 4.5 SP2.</span></span>

-   <span data-ttu-id="6c8be-153">アップグレードしていて、Dw20shared.msi を既にインストールしている場合は、この手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-153">This step is not required if you are upgrading and have previously installed Dw20shared.msi.</span></span>

 

### <span data-ttu-id="6c8be-154">.NET Framework をシーケンス処理するときのパフォーマンスを向上させる</span><span class="sxs-lookup"><span data-stu-id="6c8be-154">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="6c8be-155">.NET Framework NGEN サービスがバックグラウンドタスクとしてアセンブリをプリコンパイルしようとしているため、Microsoft .NET Framework の順序を示すときに、システムのパフォーマンスが低下することがあります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-155">When sequencing the Microsoft .NET Framework, you might experience reduced system performance because the .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="6c8be-156">WORKAROUNDWhen シーケンス .NET Framework では、監視フェーズを完了した後で .NET Framework NGEN サービス (Mscorsvw.exe) を無効にします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-156">WORKAROUNDWhen sequencing the .NET Framework, disable the .NET Framework NGEN service (Mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="6c8be-157">App-v の Sequencer で [**仮想サービス**] タブを使用し、スタートアップの種類を [**無効**] に変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-157">You must use the **Virtual Services** tab in the App-V Sequencer and change the startup type to **Disabled**.</span></span>

### <span data-ttu-id="6c8be-158">Microsoft Application Virtualization クライアントをアンインストールすると、アンインストールを実行しているユーザーに関連付けられているユーザー設定が削除される</span><span class="sxs-lookup"><span data-stu-id="6c8be-158">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstallation are deleted</span></span>

<span data-ttu-id="6c8be-159">App-v クライアントをアンインストールすると、Windows インストーラーは、現在のユーザーのプロファイルからアプリケーションの仮想化設定を削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-159">When you uninstall the App-V Client, the Windows Installer removes Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="6c8be-160">コンピューターでローミングプロファイルを使用している場合は、お使いのコンピューター上の仮想アプリケーションの設定が削除されるため、お客様のパーソナルネットワークアカウントを使用してクライアントをアンインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="6c8be-160">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="6c8be-161">回避策いただけは、仮想アプリケーションの実行に使用されていない管理者アカウントを使用して、App-v クライアントをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-161">WORKAROUNDYou must uninstall the App-V Client with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="6c8be-162">シーケンスウィザードの実行中に、仮想ファイルシステムと仮想レジストリタブで行った編集を保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-162">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="6c8be-163">アップグレードを実行するためにパッケージを開いた場合、またはシーケンスウィザードを新しいパッケージで既に実行していて、仮想ファイルシステムまたは仮想レジストリタブでパッケージを変更した場合、これらの変更は自動的に保存されません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-163">If you open a package to perform an upgrade, or if you have already run the Sequencing wizard with a new package and make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="6c8be-164">ウィザードを再実行する前に変更を WORKAROUNDSave し、ウィザードの仮想環境に確実に反映されるようにします。</span><span class="sxs-lookup"><span data-stu-id="6c8be-164">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="6c8be-165">コマンドラインの Sequencer は、昇格されたコマンドプロンプトから実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-165">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="6c8be-166">コマンドライン Sequencer を使用しても、昇格のメッセージは表示されません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-166">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="6c8be-167">昇格されたコマンドプロンプトを使用して、コマンドライン Sequencer を WORKAROUNDRun します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-167">WORKAROUNDRun the command-line Sequencer by using an elevated command prompt.</span></span>

### <span data-ttu-id="6c8be-168">OSD ファイルで短い path 変数名を使うとエラーが発生する場合がある</span><span class="sxs-lookup"><span data-stu-id="6c8be-168">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="6c8be-169">エラー450478が表示された場合: 1F702339-0000010B "クライアントで仮想アプリケーションを起動すると、OSD の変数が正しく設定されていない可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-169">If you receive error 450478-1F702339-0000010B "The directory name is invalid" when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="6c8be-170">これは、アプリケーションのインストーラーでシーケンス中に短いパス名が設定されている場合に発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-170">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="6c8be-171">OSD ファイルに存在する任意の CSIDL 変数から末尾のチルダを WORKAROUNDRemove します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-171">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="6c8be-172">コマンドライン Sequencer の DECODEPATH パラメーターの正しい構文</span><span class="sxs-lookup"><span data-stu-id="6c8be-172">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="6c8be-173">コマンドライン Sequencer でパッケージを開いて、ドライブ Q のルートにデコードする場合、 *DECODEPATH*パラメーターの構文に末尾のスラッシュを含めることはできません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-173">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of drive Q, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="6c8be-174">回避策いただけでは、 **Q:\\** (末尾の "\ \" 文字を省略します)**を使うこと**ができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-174">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing "\\" character).</span></span>

### <a href="" id="when-upgrading-app-v-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="6c8be-175">App-v 4.2 パッケージをアップグレードするときに、仮想ファイルシステムの Windows インストーラーファイルが原因で発生する問題が発生します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-175">When upgradingAPP-V 4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="6c8be-176">App-v 4.2 からパッケージをアップグレードするときに問題が発生する可能性があります。 Windows インストーラーのシステムファイルが、アプリ-V 4.2 に既定で含まれていましたが、シーケンスワークステーションにローカルにインストールされている Windows Installer ライブラリに関する問題が発生する場合があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-176">When upgrading a package from APP-V4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in APP-V4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="6c8be-177">次のファイルは、CSIDL \ _SYSTEM \ \ に保存されています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-177">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="6c8be-178">Cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="6c8be-178">Cabinet.dll</span></span>

<span data-ttu-id="6c8be-179">Msi.dll</span><span class="sxs-lookup"><span data-stu-id="6c8be-179">Msi.dll</span></span>

<span data-ttu-id="6c8be-180">Msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="6c8be-180">Msiexec.exe</span></span>

<span data-ttu-id="6c8be-181">Msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="6c8be-181">Msihnd.dll</span></span>

<span data-ttu-id="6c8be-182">Msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="6c8be-182">Msimsg.dlll</span></span>

<span data-ttu-id="6c8be-183">上記のすべてのファイルをパッケージから WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-183">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="6c8be-184">[ **VFS** ] タブのマッピングと、デコードパスにある CSIDL \ _SYSTEM フォルダー内の実際のファイルを削除します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-184">Delete the mappings on the **VFS** tab and the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--by-default--client-installation-logging-is-not-enabled-"></a><span data-ttu-id="6c8be-185">WindowsXP では、クライアントのインストールログは既定で有効になっていません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-185">On WindowsXP, by default, client installation logging is not enabled</span></span>

<span data-ttu-id="6c8be-186">クライアントをインストールするときに、トラブルシューティングのためにインストールエラーがキャプチャされていることを確認するには、コマンドラインを使用してログを有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-186">When installing the client, to ensure that any install errors are captured for troubleshooting, you must enable logging by using the command line.</span></span>

<span data-ttu-id="6c8be-187">次の例に示すように、パラメーター */l\ \* vx! log.txt*をコマンドラインに WORKAROUNDAdd します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-187">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

**<span data-ttu-id="6c8be-188">setup.exe/s/v "/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="6c8be-188">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="6c8be-189">log.txt "</span><span class="sxs-lookup"><span data-stu-id="6c8be-189">log.txt”</span></span>**

**<span data-ttu-id="6c8be-190">msiexec.exe/i setup.msi/qn/l\ \* vx!</span><span class="sxs-lookup"><span data-stu-id="6c8be-190">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="6c8be-191">log.txt</span><span class="sxs-lookup"><span data-stu-id="6c8be-191">log.txt</span></span>**

<span data-ttu-id="6c8be-192">または、レジストリキーを次の値に設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-192">Alternatively, you can set the registry key to the following value:</span></span>

**<span data-ttu-id="6c8be-193">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging" = "voicewarmupx!"</span><span class="sxs-lookup"><span data-stu-id="6c8be-193">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>**

### <span data-ttu-id="6c8be-194">Kerberos 認証が機能するためには、サービスプリンシパル名 (Spn) が IIS に登録されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-194">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="6c8be-195">インターネットインフォメーションサービス (IIS) 6.0 orIIS 7.0 のアイコンまたは OSD ファイルの取得とストリーミングを使用している場合、Kerberos 認証を有効にするには、次のように Spn を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-195">When using Internet Information Services (IIS)6.0 orIIS7.0 for icon or OSD file retrieval and streaming of packages, to enable Kerberos authentication, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="6c8be-196">IIS サーバーで SETSPN.EXE リソースキットツールを使用して、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-196">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="6c8be-197">サーバーの完全修飾ドメイン名 (FQDN) を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-197">The server fully qualified domain name (FQDN) must be used.</span></span>

    **<span data-ttu-id="6c8be-198">Setspn-r SOFTGRID/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="6c8be-198">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>**

    **<span data-ttu-id="6c8be-199">Setspn-r HTTP/ &lt; SERVER FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="6c8be-199">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>**

<span data-ttu-id="6c8be-200">詳細については、「[統合 Windows 認証 (IIS 6.0) (IIS) ()](https://go.microsoft.com/fwlink/?LinkId=131407) 」を参照してください https://go.microsoft.com/fwlink/?LinkId=131407) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-200">For more information, see [Integrated Windows Authentication (IIS 6.0)](https://go.microsoft.com/fwlink/?LinkId=131407) (https://go.microsoft.com/fwlink/?LinkId=131407).</span></span>

### <span data-ttu-id="6c8be-201">.NET の互換性の変更</span><span class="sxs-lookup"><span data-stu-id="6c8be-201">.NET compatibility changes</span></span>

<span data-ttu-id="6c8be-202">Microsoft Application Virtualization (App-v) 累積 Update1 以降では、「WindowsXP SP2 以降での .NET Framework のシーケンス処理がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="6c8be-202">Microsoft Application Virtualization (App-V) Cumulative Update1 or later supports sequencing the .NET Framework on WindowsXP SP2 or later.</span></span> <span data-ttu-id="6c8be-203">SoftGrid 4.2 用に記述された .NET アプリケーションのシーケンス処理ルーチンは、App-v 4.5 Sequencer と共に使用する場合に更新が必要になることがあります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-203">Sequencing routines for .NET applications that were written for SoftGrid4.2 might have to be updated when used with the App-V 4.5 Sequencer.</span></span> <span data-ttu-id="6c8be-204">詳細と回避策については、「 [Microsoft Application virtualization 4.5 での .net のサポート](https://go.microsoft.com/fwlink/?LinkId=123412)」の「Application virtualization TechCenter の記事」を参照してください https://go.microsoft.com/fwlink/?LinkId=123412) 。</span><span class="sxs-lookup"><span data-stu-id="6c8be-204">For details and workarounds, see the Application Virtualization TechCenter article at [Support for .NET in Microsoft Application Virtualization 4.5](https://go.microsoft.com/fwlink/?LinkId=123412) (https://go.microsoft.com/fwlink/?LinkId=123412).</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="6c8be-205">App-v 4.2 からクライアントにアップグレードした後、一部のアプリケーションが表示されない</span><span class="sxs-lookup"><span data-stu-id="6c8be-205">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="6c8be-206">ログに次のエラーがあるかどうかを確認します。 "アプリケーション仮想化クライアントは OSD ファイルを解析できませんでした"。</span><span class="sxs-lookup"><span data-stu-id="6c8be-206">Check for the following error in the log: "The Application Virtualization Client could not parse the OSD file".</span></span> <span data-ttu-id="6c8be-207">App-v 4.5 クライアントは、空の OS タグ (os/Os) を含む OSD ファイルが含まれているアプリケーションをフィルター処理し &lt; &gt; &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-207">The App-V 4.5 Client filters out applications that have an OSD file that contains an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="6c8be-208">OSD ファイルから空の OS タグを WORKAROUNDDelete します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-208">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="6c8be-209">特定のプロセスについては、App-v server でファイアウォールの適用除外が必要です</span><span class="sxs-lookup"><span data-stu-id="6c8be-209">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="6c8be-210">サーバーがアプリケーションを適切にストリーミングするために、ディスパッチャーを含むサーバーのコアプロセスでは、ファイアウォール経由のアクセスが必要になります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-210">For the server to stream applications correctly, the server's core processes, including the dispatcher, require access through the firewall.</span></span>

<span data-ttu-id="6c8be-211">次のプロセスについて、サーバーのファイアウォールの WORKAROUNDSet を除外します。 Sghwsvr.exe と Sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="6c8be-211">WORKAROUNDSet exemptions in the server's firewall for the following processes: Sghwsvr.exe and Sghwdsptr.exe.</span></span> <span data-ttu-id="6c8be-212">これは、App-v 管理サーバーと App-v Streaming Server に適用されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-212">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="6c8be-213">サーバーインストーラーがサイレントモードで実行されているときに、MSXML6 が正しくチェックされない</span><span class="sxs-lookup"><span data-stu-id="6c8be-213">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="6c8be-214">App-v Management Server は、MSXML6 によって異なります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-214">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="6c8be-215">ただし、たとえば、MSXML6 がまだインストールされていないシステム上で、コマンド**setup.msi msiexec.exe**を使ってサイレントモードでインストーラーを実行した場合、インストーラーでは見つからない依存関係が検出されず、インストールが行われません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-215">However, if you run the installer in silent mode—for example, by using the command **msiexec -i setup.msi /qn** on a system where MSXML6 is not already installed—the installer does not detect the missing dependency and installs anyway.</span></span> <span data-ttu-id="6c8be-216">そのため、クライアントは、アプリからの公開情報を更新しようとすると、エラーが発生します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-216">Therefore, when clients attempt to refresh publishing information from the App-V Management Server, they will get errors.</span></span>

<span data-ttu-id="6c8be-217">WORKAROUNDVerify は、MSXML6 がシステムにインストールされてから、アプリのサイレントインストールを実行します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-217">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent installation of the App-V Management Server.</span></span>

### <span data-ttu-id="6c8be-218">Application Virtualization 管理コンソールに接続しようとしたときに発生するエラーコード000C800</span><span class="sxs-lookup"><span data-stu-id="6c8be-218">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="6c8be-219">Application Virtualization 管理者が、app-v management Web Service server のローカル管理者ではない場合、app-v 管理コンソールに接続しようとすると、エラー (エラーコード: 000C800) が発生します。この場合は、Sftmmc .udl へのアクセスが拒否されていることを示します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-219">An Application Virtualization administrator who is not a local administrator on the App-V Management Web Service server receives an error (Error code: 000C800) when attempting to connect to the App-V Management Console, and the Sftmmc.log entry indicates that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="6c8be-220">App-v 管理コンソールに正常に接続するには、App-v Management Web サービスサーバーのローカル管理者権限を持たない管理者が、SftMgmt .udl ファイルの読み取りおよび実行のアクセス許可を少なくとも持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-220">To successfully connect to the App-V Management Console, an administrator who does not have local administrator rights on the App-V Management Web Service server must have at least Read and Execute permissions to the SftMgmt.udl file.</span></span>

<span data-ttu-id="6c8be-221">アプリケーションの仮想化管理者は、フォルダー% ¥ xxx xxx xxx Virt xxx xxx xxx Virt xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx xxx</span><span class="sxs-lookup"><span data-stu-id="6c8be-221">Application Virtualization administrators must have Read and Execute permissions to the SftMgmt.UDL file in folder %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="6c8be-222">KEEPCURRENTSETTINGS = 1 と組み合わせて使用すると、クライアントインストーラーのコマンドラインパラメーターが無視される</span><span class="sxs-lookup"><span data-stu-id="6c8be-222">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="6c8be-223">KEEPCURRENTSETTINGS = 1 と組み合わせて使用する場合、次のクライアントインストーラーコマンドラインパラメーターは無視されます。 SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTARGET、SWIUSERDATA、および REQUIRESECURECONNECTION。</span><span class="sxs-lookup"><span data-stu-id="6c8be-223">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="6c8be-224">WORKAROUNDIf 設定を保持するには、[KEEPCURRENTSETTINGS = 1] を使用し、展開後に他のパラメーターを設定します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-224">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1, and then set the other parameters after deployment.</span></span> <span data-ttu-id="6c8be-225">App-v ADM テンプレートを使って、次のクライアント設定を設定できます。 APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTARGET、DOTIMEOUTMINUTES、ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="6c8be-225">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="6c8be-226">Microsoft ダウンロードセンターの ADM テンプレートは、 [Microsoft Application Virtualization 管理用テンプレート (Adm テンプレート) (Adm テンプレート) ()](https://go.microsoft.com/fwlink/?LinkId=121835)からダウンロードでき https://go.microsoft.com/fwlink/?LinkId=121835) ます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-226">You can download the ADM Template from the Microsoft DownLoad Center at [Microsoft Application Virtualization Administrative Template (ADM Template)](https://go.microsoft.com/fwlink/?LinkId=121835) (https://go.microsoft.com/fwlink/?LinkId=121835).</span></span>

### <span data-ttu-id="6c8be-227">リリースノートの著作権情報</span><span class="sxs-lookup"><span data-stu-id="6c8be-227">Release Notes Copyright Information</span></span>

<span data-ttu-id="6c8be-228">このドキュメントは「現状有姿のまま」提供されます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-228">This document is provided "as-is".</span></span> <span data-ttu-id="6c8be-229">このドキュメントに記載されている情報および見解 (URL 等のインターネット Web サイトに関する情報を含む) は、将来予告なしに変更されることがあります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-229">Information and views expressed in this document, including URL and other Internet Web site references, may change without notice.</span></span> <span data-ttu-id="6c8be-230">使用のリスクを負うことができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-230">You bear the risk of using it.</span></span>

<span data-ttu-id="6c8be-231">ここに示すいくつかの例は、例示のためだけに用意されており、架空のものでもあります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-231">Some examples depicted herein are provided for illustration only and are fictitious.</span></span><span data-ttu-id="6c8be-232">実際の関連付けや接続は意図していないか、または推定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6c8be-232"> No real association or connection is intended or should be inferred.</span></span>

<span data-ttu-id="6c8be-233">このドキュメントは、マイクロソフト製品に含まれる知的財産に対していかなる法的権利も付与しません。</span><span class="sxs-lookup"><span data-stu-id="6c8be-233">This document does not provide you with any legal rights to any intellectual property in any Microsoft product.</span></span> <span data-ttu-id="6c8be-234">お客様は、内部的な参照目的に限り、このドキュメントを複製して使用することができます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-234">You may copy and use this document for your internal, reference purposes.</span></span> <span data-ttu-id="6c8be-235">このドキュメントは、内部的な参照目的に合わせて変更できます。</span><span class="sxs-lookup"><span data-stu-id="6c8be-235">You may modify this document for your internal, reference purposes.</span></span>



<span data-ttu-id="6c8be-236">Microsoft、Active Directory、ActiveSync、MS-DOS、Windows、WindowsServer、Windows Vista は、Microsoft の会社グループの商標です。</span><span class="sxs-lookup"><span data-stu-id="6c8be-236">Microsoft, Active Directory, ActiveSync, MS-DOS, Windows, WindowsServer, and Windows Vista are trademarks of the Microsoft group of companies.</span></span>

<span data-ttu-id="6c8be-237">その他のすべての商標は、該当する所有者に帰属します。</span><span class="sxs-lookup"><span data-stu-id="6c8be-237">All other trademarks are property of their respective owners.</span></span>

 

 





