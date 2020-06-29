---
title: MBAM 2.0 SP1 の概要
description: MBAM 2.0 SP1 の概要
author: dansimp
ms.assetid: 5ba89ed8-bb6e-407b-82c2-e2e36dd1078e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 73b92cd852d4f75f63f3dcba9f18167012b61401
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823554"
---
# <span data-ttu-id="10be0-103">MBAM 2.0 SP1 の概要</span><span class="sxs-lookup"><span data-stu-id="10be0-103">About MBAM 2.0 SP1</span></span>

<span data-ttu-id="10be0-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) 2.0 Service Pack 1 (SP1) での変更について説明します。</span><span class="sxs-lookup"><span data-stu-id="10be0-104">This topic describes the changes in Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="10be0-105">MBAM の一般的な説明については、「 [mbam 2.0](getting-started-with-mbam-20-mbam-2.md)の概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10be0-105">For a general description of MBAM, see [Getting Started with MBAM 2.0](getting-started-with-mbam-20-mbam-2.md).</span></span>

## <a href="" id="what-s-new-in-mbam-2-0-sp1"></a><span data-ttu-id="10be0-106">MBAM 2.0 SP1 の新機能</span><span class="sxs-lookup"><span data-stu-id="10be0-106">What’s new in MBAM 2.0 SP1</span></span>

<span data-ttu-id="10be0-107">このバージョンの MBAM には、次のような新機能があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-107">This version of MBAM provides the following new features and functionality.</span></span>

### <span data-ttu-id="10be0-108">Windows 8.1、Windows Server 2012 R2、System Center 2012 R2 構成マネージャーのサポート</span><span class="sxs-lookup"><span data-stu-id="10be0-108">Support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager</span></span>

<span data-ttu-id="10be0-109">Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) では、Windows 8.1、Windows Server 2012 R2、System Center 2012 R2 構成マネージャーのサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="10be0-109">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Windows 8.1, Windows Server 2012 R2, and System Center 2012 R2 Configuration Manager.</span></span>

### <span data-ttu-id="10be0-110">Microsoft SQL Server 2008 R2 SP2 のサポート</span><span class="sxs-lookup"><span data-stu-id="10be0-110">Support for Microsoft SQL Server 2008 R2 SP2</span></span>

<span data-ttu-id="10be0-111">Microsoft BitLocker 管理および監視 (MBAM) 2.0 Service Pack 1 (SP1) では、Microsoft SQL Server 2008 R2 SP2 のサポートが追加されています。</span><span class="sxs-lookup"><span data-stu-id="10be0-111">Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1) adds support for Microsoft SQL Server 2008 R2 SP2.</span></span> <span data-ttu-id="10be0-112">Microsoft System Center Configuration Manager 2007 R2 を実行している場合は、Microsoft SQL Server 2008 R2 以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-112">You must use Microsoft SQL Server 2008 R2 or higher if you are running Microsoft System Center Configuration Manager 2007 R2.</span></span>

### <span data-ttu-id="10be0-113">顧客フィードバックの重ね合わせ</span><span class="sxs-lookup"><span data-stu-id="10be0-113">Customer feedback rollup</span></span>

<span data-ttu-id="10be0-114">MBAM 2.0 SP1 には、Microsoft BitLocker の管理と監視 (MBAM) 2.0 リリース以降に検出された問題に対処するための修正プログラムが含まれています。</span><span class="sxs-lookup"><span data-stu-id="10be0-114">MBAM 2.0 SP1 includes a rollup of fixes to address issues that were found since the Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 release.</span></span> <span data-ttu-id="10be0-115">これらの変更の一部として、Microsoft System Center Configuration Manager 2007 で MBAM を実行すると、[コンピューター名] フィールドが [BitLocker コンピューターのコンプライアンスと BitLocker エンタープライズ準拠の詳細] に表示されるようになりました。</span><span class="sxs-lookup"><span data-stu-id="10be0-115">As part of these changes, the Computer Name field now appears in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007.</span></span>

### <span data-ttu-id="10be0-116">セルフサービスポータルと管理と監視の web サイトのポートにファイアウォールの例外を設定する必要がある</span><span class="sxs-lookup"><span data-stu-id="10be0-116">Firewall exception must be set on ports for the Self-Service Portal and the Administration and Monitoring website</span></span>

<span data-ttu-id="10be0-117">セルフサービスポータルと管理/監視 web サイトを構成するときは、指定したポートを介した通信を有効にするために、ファイアウォールの例外を設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-117">When you configure the Self-Service Portal and the Administration and Monitoring website, you must set a firewall exception to enable communication through the specified ports.</span></span> <span data-ttu-id="10be0-118">以前は、MBAM サーバーのインストールでは、Windows ファイアウォールでポートが自動的に開かれました。</span><span class="sxs-lookup"><span data-stu-id="10be0-118">Previously, the MBAM server installation opened the ports automatically in Windows Firewall.</span></span>

### <span data-ttu-id="10be0-119">Configuration Manager で MBAM レポートの場所が変更されている</span><span class="sxs-lookup"><span data-stu-id="10be0-119">Location of MBAM reports has changed in Configuration Manager</span></span>

<span data-ttu-id="10be0-120">Configuration Manager の統合トポロジの MBAM レポートは、MBAM ノード内のサブフォルダーで利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="10be0-120">MBAM reports for the Configuration Manager integrated topology are now available under subfolders within the MBAM node.</span></span> <span data-ttu-id="10be0-121">サブフォルダー名は、サブフォルダー内のレポートの言語を表します。</span><span class="sxs-lookup"><span data-stu-id="10be0-121">The subfolder names represent the language of the reports within the subfolder.</span></span>

### <span data-ttu-id="10be0-122">Configuration Manager を使用して MBAM をインストールするときに、プライマリサイトサーバーに MBAM をインストールする機能</span><span class="sxs-lookup"><span data-stu-id="10be0-122">Ability to install MBAM on a primary site server when you install MBAM with Configuration Manager</span></span>

<span data-ttu-id="10be0-123">Configuration Manager の統合トポロジを使用して MBAM をインストールする場合は、プライマリサイトサーバーまたは中央管理サイトサーバーに MBAM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="10be0-123">You can install MBAM on a primary site server or a central administration site server when you install MBAM with the Configuration Manager integrated topology.</span></span> <span data-ttu-id="10be0-124">以前は、中央管理サイトサーバーに MBAM をインストールする必要がありました。</span><span class="sxs-lookup"><span data-stu-id="10be0-124">Previously, you were required to install MBAM on a central administration site server.</span></span>

**<span data-ttu-id="10be0-125">重要</span><span class="sxs-lookup"><span data-stu-id="10be0-125">Important</span></span>**  
<span data-ttu-id="10be0-126">MBAM をインストールするサーバーは、階層のトップ層サーバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-126">The server on which you install MBAM must be the top-tier server in your hierarchy.</span></span>



<span data-ttu-id="10be0-127">MBAM インストールの動作は、Microsoft System Center Configuration Manager 2007 と Microsoft System Center 2012 構成マネージャーと次のように異なります。</span><span class="sxs-lookup"><span data-stu-id="10be0-127">The MBAM installation works differently for Microsoft System Center Configuration Manager 2007 and Microsoft System Center 2012 Configuration Manager as follows:</span></span>

-   <span data-ttu-id="10be0-128">**Configuration manager 2007** : 大規模な configuration manager 階層の一部であり、セントラルサイトの親サーバーがあるプライマリサイトサーバーに mbam をインストールすると、mbam はセントラルサイトの親サーバーを解決し、その親サーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-128">**Configuration Manager 2007** : If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy and has a central site parent server, MBAM resolves the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="10be0-129">インストールアクションには、前提条件の確認や Configuration Manager オブジェクトとレポートのインストールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="10be0-129">The installation actions include checking prerequisites and installing the Configuration Manager objects and reports.</span></span> <span data-ttu-id="10be0-130">たとえば、セントラルサイトの親サーバーの子であるプライマリサイトサーバーに MBAM をインストールすると、MBAM は親サーバー上のすべての Configuration Manager オブジェクトとレポートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="10be0-130">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="10be0-131">MBAM を親サーバーにインストールする場合、MBAM はその親サーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-131">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span>

-   <span data-ttu-id="10be0-132">**System Center 2012 構成マネージャー** : mbam をプライマリサイトサーバーまたはサーバーの全体管理サーバーにインストールする場合、mbam はそのサイトサーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-132">**System Center 2012 Configuration Manager** : If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span>

### <a href="" id="-------------configuration-manager-console-must-be-installed-on-the--computer-on-which-you-install-the-mbam-server"></a> <span data-ttu-id="10be0-133">MBAM サーバーをインストールするコンピューターに Configuration Manager コンソールがインストールされている必要がある</span><span class="sxs-lookup"><span data-stu-id="10be0-133">Configuration Manager Console must be installed on the computer on which you install the MBAM Server</span></span>

<span data-ttu-id="10be0-134">Configuration Manager の統合トポロジを使用して MBAM をインストールする場合は、MBAM をインストールするコンピューターに Configuration Manager コンソールをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-134">When you install MBAM with the Configuration Manager integrated topology, you must install the Configuration Manager Console on the same computer on which MBAM will be installed.</span></span> <span data-ttu-id="10be0-135">推奨されるアーキテクチャ (「はじめに」「 [Configuration manager での MBAM の使用](getting-started---using-mbam-with-configuration-manager.md)」で説明) を使用する場合は、Configuration Manager プライマリサイトサーバーに mbam をインストールします。</span><span class="sxs-lookup"><span data-stu-id="10be0-135">If you use the recommended architecture, which is described in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md), you would install MBAM on the Configuration Manager Primary Site Server.</span></span>

### <span data-ttu-id="10be0-136">Configuration Manager の統合トポロジの新しいセットアップコマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="10be0-136">New setup command-line parameters for the Configuration Manager integrated topology</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="10be0-137">コマンドラインパラメーター</span><span class="sxs-lookup"><span data-stu-id="10be0-137">Command-Line Parameter</span></span></th>
<th align="left"><span data-ttu-id="10be0-138">説明</span><span class="sxs-lookup"><span data-stu-id="10be0-138">Description</span></span></th>
<th align="left"><span data-ttu-id="10be0-139">例</span><span class="sxs-lookup"><span data-stu-id="10be0-139">Example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="10be0-140">CM_SSRS_REMOTE_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="10be0-140">CM_SSRS_REMOTE_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-141">MBAM がインストールされている同じ Configuration Manager サイトの一部であるリモートの SQL Server Reporting Services (SSRS) サーバーに Configuration Manager レポートをインストールできるようにします。</span><span class="sxs-lookup"><span data-stu-id="10be0-141">Enables you to install the Configuration Manager reports on a remote SQL Server Reporting Services (SSRS) server that is part of the same Configuration Manager site to which MBAM is installed.</span></span> <span data-ttu-id="10be0-142">この値は、リモートの SSRS ポイントの役割サーバーの完全修飾ドメイン名に設定できます。</span><span class="sxs-lookup"><span data-stu-id="10be0-142">You can set the value to the fully qualified domain name of the remote SSRS point role server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME = ssrsServer: .com</span><span class="sxs-lookup"><span data-stu-id="10be0-143">MbamSetup.exe CM_SSRS_REMOTE_SERVER_NAME=ssrsServer.Contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="10be0-144">CM_REPORTS_ONLY</span><span class="sxs-lookup"><span data-stu-id="10be0-144">CM_REPORTS_ONLY</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-145">Configuration Manager レポートのみをインストールできるようにします。これには、ベースライン、コレクション、構成項目などの他の Configuration Manager オブジェクトは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="10be0-145">Enables you to install only the Configuration Manager reports, without other Configuration Manager objects, such as the baseline, collection, and configuration items.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="10be0-146">注</span><span class="sxs-lookup"><span data-stu-id="10be0-146">Note</span></span></strong><br/><p><span data-ttu-id="10be0-147">このパラメーターを CM_REPORTS_COLLECTION_ID パラメーターと組み合わせる必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-147">You must combine this parameter with the CM_REPORTS_COLLECTION_ID parameter.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="10be0-148">有効なパラメーター値:</span><span class="sxs-lookup"><span data-stu-id="10be0-148">Valid parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="10be0-149">True</span><span class="sxs-lookup"><span data-stu-id="10be0-149">True</span></span></p></li>
<li><p><span data-ttu-id="10be0-150">False</span><span class="sxs-lookup"><span data-stu-id="10be0-150">False</span></span></p></li>
</ul>
<p><span data-ttu-id="10be0-151">リモートの SSRS ポイントの役割サーバーにのみレポートをインストールする場合は、このパラメーターを CM_SSRS_REMOTE_SERVER_NAME パラメーターと組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="10be0-151">You can combine this parameter with the CM_SSRS_REMOTE_SERVER_NAME parameter if you want to install the reports only to a remote SSRS point role server.</span></span></p>
<p><span data-ttu-id="10be0-152">パラメーターを設定していない場合、または False に設定した場合、MBAM Setup はレポートを含むすべての Configuration Manager オブジェクトをインストールします。</span><span class="sxs-lookup"><span data-stu-id="10be0-152">If you do not set the parameter or if you set it to False, MBAM Setup installs all of the Configuration Manager objects, including the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-153">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="10be0-153">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="10be0-154">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="10be0-154">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="10be0-155">CM_REPORTS_COLLECTION_ID</span><span class="sxs-lookup"><span data-stu-id="10be0-155">CM_REPORTS_COLLECTION_ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-156">レポートのコンプライアンスデータが表示されるコレクションを識別する既存のコレクション ID。</span><span class="sxs-lookup"><span data-stu-id="10be0-156">An existing collection ID that identifies the collection for which reporting compliance data will be displayed.</span></span> <span data-ttu-id="10be0-157">任意のコレクション ID を指定できます。</span><span class="sxs-lookup"><span data-stu-id="10be0-157">You can specify any collection ID.</span></span> <span data-ttu-id="10be0-158">"MBAM サポートされているコンピューター" コレクション ID を使用する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10be0-158">You are not required to use the “MBAM Supported Computers” collection ID.</span></span></p></td>
<td align="left"><p><span data-ttu-id="10be0-159">MbamSetup.exe CM_REPORTS_ONLY = True</span><span class="sxs-lookup"><span data-stu-id="10be0-159">MbamSetup.exe CM_REPORTS_ONLY=True</span></span></p>
<p><span data-ttu-id="10be0-160">CM_REPORTS_COLLECTION_ID = SMS00001</span><span class="sxs-lookup"><span data-stu-id="10be0-160">CM_REPORTS_COLLECTION_ID=SMS00001</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="10be0-161">セルフサービスポータルの通知テキストを有効または無効にする機能</span><span class="sxs-lookup"><span data-stu-id="10be0-161">Ability to turn Self-Service Portal notice text on or off</span></span>

<span data-ttu-id="10be0-162">MBAM 2.0 SP1 では、セルフサービスポータルの通知テキストをオフにすることができます。</span><span class="sxs-lookup"><span data-stu-id="10be0-162">MBAM 2.0 SP1 enables you to turn off the notice text on the Self-Service Portal.</span></span> <span data-ttu-id="10be0-163">以前は、通知テキストは既定で表示されていましたが、オフにすることはできませんでした。</span><span class="sxs-lookup"><span data-stu-id="10be0-163">Previously, the notice text displayed by default, and you could not turn it off.</span></span>

**<span data-ttu-id="10be0-164">通知テキストをオフにするには</span><span class="sxs-lookup"><span data-stu-id="10be0-164">To turn off the notice text</span></span>**

1.  <span data-ttu-id="10be0-165">セルフサービスポータルをインストールしたサーバーで、[インターネットインフォメーションサービス (IIS)] を開き、[ \*\* &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視\*\*] のサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="10be0-165">On the server where you installed the Self-Service Portal, open Internet Information Services (IIS) and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="10be0-166">[**名前**] 列で、[ **displaynotice**] を選択し、値を**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="10be0-166">From the **Name** column, select **DisplayNotice**, and set the value to **false**.</span></span>

### <span data-ttu-id="10be0-167">ユーザーがより多くのセルフサービスポータル情報を参照するように、ヘルプデスクのテキストステートメントをローカライズする機能</span><span class="sxs-lookup"><span data-stu-id="10be0-167">Ability to localize the HelpdeskText statement that points users to more Self-Service Portal information</span></span>

<span data-ttu-id="10be0-168">ユーザーがセルフサービスポータルを使用しているときに追加のヘルプを取得する方法については、ローカライズされたバージョンのセルフサービスポータル "Helpデスクテキスト" ステートメントを構成できます。</span><span class="sxs-lookup"><span data-stu-id="10be0-168">You can configure a localized version of the Self-Service Portal “HelpdeskText” statement, which tells end users how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="10be0-169">次の手順で説明するように、ステートメントのローカライズされたテキストを構成すると、MBAM にローカライズされたバージョンが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-169">If you configure localized text for the statement, as described in the following instructions, MBAM will display the localized version.</span></span> <span data-ttu-id="10be0-170">MBAM でローカライズされたバージョンが見つからない場合は、 **Helpデスクテキスト**パラメーターの値が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-170">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

**<span data-ttu-id="10be0-171">Helpデスクテキストステートメントのローカライズされたバージョンを表示するには</span><span class="sxs-lookup"><span data-stu-id="10be0-171">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="10be0-172">セルフサービスポータルをインストールしたサーバーで、[IIS] を開き、[ \*\* &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視\*\*] のサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="10be0-172">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="10be0-173">[**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="10be0-173">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="10be0-174">[**名前**] フィールドに「**ヘルプ**」と入力し &lt; *language* &gt; ます。ここで、 &lt; *言語* &gt; は、テキストの適切な言語コードです。</span><span class="sxs-lookup"><span data-stu-id="10be0-174">In the **Name** field, type **HelpdeskText**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the text.</span></span> <span data-ttu-id="10be0-175">たとえば、ローカライズされたヘルプデスクのテキストステートメントをスペイン語で作成するには、パラメーターに「\ _es」という名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="10be0-175">For example, to create a localized HelpdeskText statement in Spanish, you would name the parameter HelpdeskText\_es-es.</span></span> <span data-ttu-id="10be0-176">使用できる有効な言語コードの一覧については、「[国内言語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10be0-176">For a list of the valid language codes that you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="10be0-177">[**値**] フィールドに、エンドユーザーに対して表示するローカライズされたテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="10be0-177">In the **Value** field, type the localized text that you want to display to end users.</span></span>

### <span data-ttu-id="10be0-178">セルフサービスポータルのヘルプの Url をローカライズする機能</span><span class="sxs-lookup"><span data-stu-id="10be0-178">Ability to localize the Self-Service Portal HelpdeskURL</span></span>

<span data-ttu-id="10be0-179">既定でエンドユーザーに表示する、セルフサービスポータルのヘルプデスク Url のローカライズされたバージョンを構成できます。</span><span class="sxs-lookup"><span data-stu-id="10be0-179">You can configure a localized version of the Self-Service Portal HelpdeskURL to display to end users by default.</span></span> <span data-ttu-id="10be0-180">次の手順で説明するように、ローカライズされたバージョンを作成すると、MBAM でローカライズされたバージョンが検索されて表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-180">If you create a localized version, as described in the following instructions, MBAM finds and displays the localized version.</span></span> <span data-ttu-id="10be0-181">MBAM でローカライズされたバージョンが見つからない場合は、Helpデスク Url パラメーターに対して構成されている URL が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-181">If MBAM does not find a localized version, it displays the URL that is configured for the HelpDeskURL parameter.</span></span>

**<span data-ttu-id="10be0-182">ローカライズされたヘルプデスクの Url を表示するには</span><span class="sxs-lookup"><span data-stu-id="10be0-182">To display a localized HelpdeskURL</span></span>**

1.  <span data-ttu-id="10be0-183">セルフサービスポータルをインストールしたサーバーで、[IIS] を開き、[ \*\* &gt; Microsoft BitLocker 管理] および [セルフ &gt; サービス &gt; アプリケーション設定の監視\*\*] のサイトに移動します。</span><span class="sxs-lookup"><span data-stu-id="10be0-183">On the server where you installed the Self-Service Portal, open IIS and browse to **Sites &gt; Microsoft BitLocker Administration and Monitoring &gt; SelfService &gt; Application Settings**.</span></span>

2.  <span data-ttu-id="10be0-184">[**操作**] ウィンドウの [**追加**] をクリックして、[**アプリケーション設定の追加**] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="10be0-184">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="10be0-185">[**名前**] フィールドに「**ヘルプ**」と入力し &lt; *language* &gt; ます。ここで、 &lt; *言語* &gt; は url の適切な言語コードです。</span><span class="sxs-lookup"><span data-stu-id="10be0-185">In the **Name** field, type **HelpdeskURL**\_&lt;*language*&gt;, where &lt;*language*&gt; is the appropriate language code for the URL.</span></span> <span data-ttu-id="10be0-186">たとえば、スペイン語でヘルプのローカライズされた Url を作成するには、パラメーター Help"Url \ _es という名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="10be0-186">For example, to create a localized HelpdeskURL in Spanish, you would name the parameter HelpdeskURL\_es-es.</span></span> <span data-ttu-id="10be0-187">使用できる有効な言語コードの一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="10be0-187">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="10be0-188">[**値**] フィールドに、エンドユーザーに表示するローカライズされたヘルプデスクの url を入力します。</span><span class="sxs-lookup"><span data-stu-id="10be0-188">In the **Value** field, type the localized HelpdeskURL that you want to display to end users.</span></span>

### <span data-ttu-id="10be0-189">セルフサービスポータル通知テキストのローカライズ機能</span><span class="sxs-lookup"><span data-stu-id="10be0-189">Ability to localize the Self-Service Portal notice text</span></span>

<span data-ttu-id="10be0-190">セルフサービスポータルで既定でエンドユーザーに表示する、ローカライズされた通知テキストを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="10be0-190">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="10be0-191">通知テキストが表示された notice.txt ファイルは、次のルートディレクトリにあります。</span><span class="sxs-lookup"><span data-stu-id="10be0-191">The notice.txt file, which displays the notice text, is located in the following root directory:</span></span>

<span data-ttu-id="10be0-192">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="10be0-192">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="10be0-193">ローカライズされた通知テキストを表示するには、ローカライズされた notice.txt ファイルを作成し、次のディレクトリの特定の言語フォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="10be0-193">To display localized notice text, you create a localized notice.txt file and save it under a specific language folder in the following directory:</span></span>

<span data-ttu-id="10be0-194">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="10be0-194">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="10be0-195">MBAM 次のルールに基づいて、通知テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-195">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="10be0-196">適切な言語フォルダーにローカライズされた notice.txt ファイルを作成すると、MBAM にローカライズされた通知テキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-196">If you create a localized notice.txt file in the appropriate language folder, MBAM displays the localized notice text.</span></span>

-   <span data-ttu-id="10be0-197">MBAM でローカライズされたバージョンの notice.txt ファイルが見つからない場合は、既定の notice.txt ファイルにテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-197">If MBAM does not find a localized version of the notice.txt file, it displays the text in the default notice.txt file.</span></span>

-   <span data-ttu-id="10be0-198">MBAM が既定の notice.txt ファイルを見つけられない場合は、セルフサービスポータルに既定のテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-198">If MBAM does not find a default notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

**<span data-ttu-id="10be0-199">注</span><span class="sxs-lookup"><span data-stu-id="10be0-199">Note</span></span>**  
<span data-ttu-id="10be0-200">エンドユーザーのブラウザーが、対応する言語のサブフォルダーまたは notice.txt のない言語に設定されている場合は、次のルートディレクトリの notice.txt ファイルに含まれているテキストが表示されます。</span><span class="sxs-lookup"><span data-stu-id="10be0-200">If an end user’s browser is set to a language that does not have a corresponding language subfolder or notice.txt, the text that is in the notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="10be0-201">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="10be0-201">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\



**<span data-ttu-id="10be0-202">ローカライズされた notice.txt ファイルを作成するには</span><span class="sxs-lookup"><span data-stu-id="10be0-202">To create a localized notice.txt file</span></span>**

1.  <span data-ttu-id="10be0-203">セルフサービスポータルをインストールしたサーバー上で、 &lt; 次のディレクトリに*言語*フォルダーを作成し &gt; ます。ここでは、言語がローカライズされた &lt; *language* &gt; 言語の名前であることを示します。</span><span class="sxs-lookup"><span data-stu-id="10be0-203">On the server where you installed the Self-Service Portal, create a &lt;*language*&gt; folder in the following directory, where &lt;*language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="10be0-204">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website</span><span class="sxs-lookup"><span data-stu-id="10be0-204">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    **<span data-ttu-id="10be0-205">注</span><span class="sxs-lookup"><span data-stu-id="10be0-205">Note</span></span>**  
    <span data-ttu-id="10be0-206">一部の言語フォルダーは既に存在しているため、作成する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10be0-206">Some language folders already exist, so you may not have to create one.</span></span> <span data-ttu-id="10be0-207">言語フォルダーを作成する必要がある場合は、言語フォルダーに使用できる有効な名前の一覧については、「[各国語サポート (NLS) API リファレンス](https://go.microsoft.com/fwlink/?LinkId=317947)」を参照してください &lt; *language* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="10be0-207">If you do need to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*language*&gt; folder.</span></span>



2.  <span data-ttu-id="10be0-208">ローカライズされた通知テキストを含む notice.txt ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="10be0-208">Create a notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="10be0-209">notice.txt ファイルを [言語] フォルダーに保存し &lt; *language* &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="10be0-209">Save the notice.txt file in the &lt;*language*&gt; folder.</span></span> <span data-ttu-id="10be0-210">たとえば、スペイン語でローカライズされた notice.txt ファイルを作成するには、ローカライズされた notice.txt ファイルを次のフォルダーに保存します。</span><span class="sxs-lookup"><span data-stu-id="10be0-210">For example, to create a localized notice.txt file in Spanish, you would save the localized notice.txt file in the following folder:</span></span>

    <span data-ttu-id="10be0-211">&lt;*Mbam セルフサービスインストールディレクトリ* &gt;\\ セルフサービスの Website\\es-es</span><span class="sxs-lookup"><span data-stu-id="10be0-211">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\es-es</span></span>

## <span data-ttu-id="10be0-212">MBAM 2.0 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="10be0-212">Upgrading to MBAM 2.0 SP1</span></span>


<span data-ttu-id="10be0-213">以前のバージョンの MBAM から MBAM 2.0 SP1 にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="10be0-213">You can upgrade to MBAM 2.0 SP1 from any previous version of MBAM.</span></span>

### <span data-ttu-id="10be0-214">MBAM インフラストラクチャのアップグレード</span><span class="sxs-lookup"><span data-stu-id="10be0-214">Upgrading the MBAM infrastructure</span></span>

<span data-ttu-id="10be0-215">MBAM サーバーインフラストラクチャを MBAM 2.0 SP1 にアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-215">You can upgrade the MBAM Server infrastructure to MBAM 2.0 SP1 as follows:</span></span>

<span data-ttu-id="10be0-216">**手動のインプレースサーバー置き換え**: 既存の mbam サーバーインフラストラクチャを手動でアンインストールしてから、mbam 2.0 SP1 サーバーインフラストラクチャをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-216">**Manual in-place server replacement**: You must manually uninstall the existing MBAM Server infrastructure, and then install the MBAM 2.0 SP1 Server infrastructure.</span></span> <span data-ttu-id="10be0-217">アップグレードを実行するためにデータベースを削除する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="10be0-217">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="10be0-218">代わりに、MBAM の以前のバージョンが作成された既存のデータベースを選択します。</span><span class="sxs-lookup"><span data-stu-id="10be0-218">Instead, you select the existing databases, which the previous version of MBAM created.</span></span> <span data-ttu-id="10be0-219">MBAM 2.0 SP1 アップグレードインストールでは、既存のデータベースを MBAM 2.0 SP1 に移行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-219">The MBAM 2.0 SP1 upgrade installation then migrates the existing databases to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="10be0-220">**分散クライアントアップグレード**: スタンドアロンの mbam トポロジを使用している場合は、mbam 2.0 SP1 サーバーインフラストラクチャをインストールした後、Mbam クライアントを段階的にアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="10be0-220">**Distributed client upgrade**: If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 SP1 Server infrastructure.</span></span>

<span data-ttu-id="10be0-221">Mbam Server インフラストラクチャをアップグレードした後、MBAM 1.0 または2.0 クライアントは、MBAM 2.0 SP1 サーバーに正常に報告し、回復データを保存しますが、コンプライアンスは、現在インストールされている MBAM クライアントバージョンで利用可能なポリシーに基づいています。</span><span class="sxs-lookup"><span data-stu-id="10be0-221">After you upgrade the MBAM Server infrastructure, MBAM 1.0 or 2.0 Clients will report to the MBAM 2.0 SP1 Server successfully and will store the recovery data, but compliance will be based on the policies available for the MBAM Client version that is currently installed.</span></span> <span data-ttu-id="10be0-222">MBAM 2.0 SP1 ポリシーに対してレポート機能を有効にするには、クライアントコンピューターを MBAM 2.0 SP1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-222">To enable reporting against MBAM 2.0 SP1 policies, you must upgrade client computers to MBAM 2.0 SP1.</span></span> <span data-ttu-id="10be0-223">クライアントコンピューターは、以前のクライアントをアンインストールせずに MBAM 2.0 SP1 クライアントにアップグレードできます。クライアントは、MBAM 2.0 SP1 ポリシーに基づいて、適用および報告を開始します。</span><span class="sxs-lookup"><span data-stu-id="10be0-223">You can upgrade the client computers to the MBAM 2.0 SP1 Client without uninstalling the previous Client, and the Client will start to apply and report, based on the MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="10be0-224">MBAM サーバーのアップグレードの詳細については、「[以前のバージョンの mbam からアップグレード](upgrading-from-previous-versions-of-mbam.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10be0-224">For more information about upgrading the MBAM servers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

### <span data-ttu-id="10be0-225">MBAM クライアントの MBAM 2.0 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="10be0-225">Upgrading the MBAM Client to MBAM 2.0 SP1</span></span>

<span data-ttu-id="10be0-226">エンドユーザーコンピューターを MBAM 2.0 SP1 クライアントにアップグレードするには、各クライアントコンピューターで**MbamClientSetup.exe**を実行します。</span><span class="sxs-lookup"><span data-stu-id="10be0-226">To upgrade end-user computers to the MBAM 2.0 SP1 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="10be0-227">インストーラーは、クライアントを MBAM 2.0 SP1 クライアントに自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="10be0-227">The installer automatically updates the Client to the MBAM 2.0 SP1 Client.</span></span> <span data-ttu-id="10be0-228">インストール後、クライアントコンピューターを再起動する必要はありません。 MBAM 2.0 SP1 クライアントは、MBAM 2.0 SP1 ポリシーの適用と報告を開始します。</span><span class="sxs-lookup"><span data-stu-id="10be0-228">After the installation, client computers do not have to be rebooted, and the MBAM 2.0 SP1 Client starts to apply and report against MBAM 2.0 SP1 policies.</span></span>

<span data-ttu-id="10be0-229">MBAM を Configuration Manager で使用している場合は、MBAM クライアントコンピューターを MBAM 2.0 SP1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-229">If you are using MBAM with Configuration Manager, you must upgrade the MBAM client computers to MBAM 2.0 SP1.</span></span>

<span data-ttu-id="10be0-230">MBAM クライアントコンピューターのアップグレードの詳細については、「[以前のバージョンの mbam からアップグレード](upgrading-from-previous-versions-of-mbam.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="10be0-230">For more information about upgrading the MBAM client computers, see [Upgrading from Previous Versions of MBAM](upgrading-from-previous-versions-of-mbam.md).</span></span>

## <span data-ttu-id="10be0-231">Configuration Manager を使用して MBAM 2.0 SP1 をインストールまたはアップグレードする</span><span class="sxs-lookup"><span data-stu-id="10be0-231">Installing or upgrading to MBAM 2.0 SP1 with Configuration Manager</span></span>


<span data-ttu-id="10be0-232">このセクションでは、MBAM 2.0 SP1 を新規インストールとしてインストールする場合、または以前の MBAM 2.0 SP1 インストールへのアップグレードとしてインストールする場合の要件について説明します。</span><span class="sxs-lookup"><span data-stu-id="10be0-232">This section describes the requirements when you are installing MBAM 2.0 SP1 as a new installation or as an upgrade to a previous MBAM 2.0 SP1 installation.</span></span>

### <span data-ttu-id="10be0-233">Mbam 2.0 SP1 をインストールするのに必要なファイル (MBAM を Configuration Manager で使用している場合)</span><span class="sxs-lookup"><span data-stu-id="10be0-233">Required files for installing MBAM 2.0 SP1 if you are using MBAM with Configuration Manager</span></span>

<span data-ttu-id="10be0-234">MBAM を初めてインストールするときに、MBAM 2.0 SP1 を System Center Configuration Manager で使用している場合、MBAM を構成マネージャーで正しく動作させるためには、mof ファイルを作成または編集する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-234">If you are installing MBAM for the first time and you are using MBAM 2.0 SP1 with System Center Configuration Manager, you must create or edit mof files to enable MBAM to work correctly with Configuration Manager.</span></span>

-   **<span data-ttu-id="10be0-235">構成の .mof ファイル</span><span class="sxs-lookup"><span data-stu-id="10be0-235">configuration.mof file</span></span>**

    -   <span data-ttu-id="10be0-236">Configuration Manager 2007 を使っている場合は、「 **mbam 2.0 SP1 にアップグレードした場合に、構成マネージャー2007で mbam を使用**していて、この項目の後に mbam を使っている場合、構成の .mof ファイルを更新する必要があります。」</span><span class="sxs-lookup"><span data-stu-id="10be0-236">If you are using Configuration Manager 2007, you must edit the configuration.mof file by completing step 3 from the item **Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007**, which follows this item.</span></span>

    -   <span data-ttu-id="10be0-237">System Center 2012 構成マネージャーを使用している場合は、「[構成の .Mof ファイルを編集](edit-the-configurationmof-file.md)する」の手順に従って構成の .mof ファイルを編集します。</span><span class="sxs-lookup"><span data-stu-id="10be0-237">If you are using System Center 2012 Configuration Manager, edit the configuration.mof file by following the instructions in [Edit the Configuration.mof File](edit-the-configurationmof-file.md).</span></span>

-   <span data-ttu-id="10be0-238">**sms \ _def ファイル**: 「 [sms \ _def .Mof ファイルを作成または編集](create-or-edit-the-sms-defmof-file.md)する」の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="10be0-238">**sms\_def.mof file** – follow the instructions in [Create or Edit the Sms\_def.mof File](create-or-edit-the-sms-defmof-file.md).</span></span>

### <span data-ttu-id="10be0-239">MBAM 2.0 SP1 にアップグレードして、Configuration Manager 2007 で MBAM を使用している場合に構成の .mof ファイルを更新する</span><span class="sxs-lookup"><span data-stu-id="10be0-239">Update the configuration.mof file if you upgrade to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007</span></span>

<span data-ttu-id="10be0-240">MBAM 2.0 SP1 にアップグレードしていて、MBAM を Configuration Manager 2007 で使用している場合は、MBAM 2.0 SP1 が正しく動作するように構成の .mof ファイルを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="10be0-240">If you are upgrading to MBAM 2.0 SP1 and you are using MBAM with Configuration Manager 2007, you must update the configuration.mof file to ensure that MBAM 2.0 SP1 works correctly.</span></span>

**<span data-ttu-id="10be0-241">構成の .mof ファイルを更新するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="10be0-241">To update the configuration.mof file:</span></span>**

1.  <span data-ttu-id="10be0-242">Configuration Manager サーバーで、構成の .mof ファイルの場所を参照します。</span><span class="sxs-lookup"><span data-stu-id="10be0-242">On the Configuration Manager Server, browse to the location of the Configuration.mof file:</span></span>

    <span data-ttu-id="10be0-243">&lt;CMInstallLocation &gt; \\Inboxes\\clifiles.src\\hinv</span><span class="sxs-lookup"><span data-stu-id="10be0-243">&lt;CMInstallLocation&gt;\\Inboxes\\clifiles.src\\hinv</span></span>\\

    <span data-ttu-id="10be0-244">既定のインストールの場合、インストール場所は \ systemsystem% ¥ Program Files (x86) \\ Microsoft 構成マネージャーです。</span><span class="sxs-lookup"><span data-stu-id="10be0-244">On a default installation, the installation location is %systemdrive%\\Program Files (x86)\\Microsoft Configuration Manager.</span></span>

2.  <span data-ttu-id="10be0-245">構成の .mof ファイルに追加したコードのブロックを確認して、削除します。</span><span class="sxs-lookup"><span data-stu-id="10be0-245">Review the block of code that you appended to the configuration.mof file, and delete it.</span></span> <span data-ttu-id="10be0-246">コードのブロックは、次の手順に示すようなものになります。</span><span class="sxs-lookup"><span data-stu-id="10be0-246">The block of code will be similar to the one shown in the following step.</span></span>

3.  <span data-ttu-id="10be0-247">次のコードブロックをコピーし、それを構成の .mof ファイルに追加して、次の必要な MBAM クラスをファイルに追加します。</span><span class="sxs-lookup"><span data-stu-id="10be0-247">Copy the following block of code, and then append it to the configuration.mof file to add the following required MBAM classes to the file:</span></span>

    ``` syntax
    //===================================================
    // Microsoft BitLocker Administration and Monitoring 
    //===================================================

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32_BitLockerEncryptionDetails", NOFAIL) 

    [Union, ViewSources{"select DeviceId, BitlockerPersistentVolumeId, BitLockerManagementPersistentVolumeId, BitLockerManagementVolumeType, DriveLetter, Compliant, ReasonsForNonCompliance, KeyProtectorTypes, EncryptionMethod, ConversionStatus, ProtectionStatus, IsAutoUnlockEnabled from Mbam_Volume"}, ViewSpaces{"\\\\.\\root\\microsoft\\mbam"}, dynamic, Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class Win32_BitLockerEncryptionDetails
    {
        [PropertySources{"DeviceId"},key]
        String     DeviceId;
        [PropertySources{"BitlockerPersistentVolumeId"}]
        String     BitlockerPersistentVolumeId;
        [PropertySources{"BitLockerManagementPersistentVolumeId"}]
        String     MbamPersistentVolumeId;
        //UNKNOWN = 0, OS_Volume = 1, FIXED_VOLUME = 2, REMOVABLE_VOLUME = 3
        [PropertySources{"BitLockerManagementVolumeType"}]
        SInt32     MbamVolumeType;
        [PropertySources{"DriveLetter"}]
        String     DriveLetter;
        //VOLUME_NOT_COMPLIANT = 0, VOLUME_COMPLIANT = 1, NOT_APPLICABLE = 2
        [PropertySources{"Compliant"}]
        SInt32     Compliant;
        [PropertySources{"ReasonsForNonCompliance"}]
        SInt32     ReasonsForNonCompliance[];
        [PropertySources{"KeyProtectorTypes"}]
        SInt32     KeyProtectorTypes[];
        [PropertySources{"EncryptionMethod"}]
        SInt32     EncryptionMethod;
        [PropertySources{"ConversionStatus"}]
        SInt32     ConversionStatus;
        [PropertySources{"ProtectionStatus"}]
        SInt32     ProtectionStatus;
        [PropertySources{"IsAutoUnlockEnabled"}]
        Boolean     IsAutoUnlockEnabled;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy", NOFAIL)
     [DYNPROPS]
    Class Win32Reg_MBAMPolicy
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate;
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

     [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy
    {
        KeyName="BitLocker policy";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("Win32Reg_MBAMPolicy_64", NOFAIL)
    [DYNPROPS]
    Class Win32Reg_MBAMPolicy_64
    {
        [key]
        string KeyName;

        //General encryption requirements
        UInt32    OsDriveEncryption;
        UInt32    FixedDataDriveEncryption;
        UInt32    EncryptionMethod;

        //Required protectors properties
        UInt32    OsDriveProtector;
        UInt32    FixedDataDriveAutoUnlock;
        UInt32    FixedDataDrivePassphrase;

        //MBAM agent fields
        Uint32    MBAMPolicyEnforced;
        string    LastConsoleUser;
        datetime  UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        UInt32    MBAMMachineError;

        // Encoded computer name
        string    EncodedComputerName;
    };

    [DYNPROPS]
    Instance of Win32Reg_MBAMPolicy_64
    {
        KeyName="BitLocker policy 64";

        //General encryption requirements
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptOsDrive"),Dynamic,Provider("RegPropProv")]
        OsDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|ShouldEncryptFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveEncryption;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|EncryptionMethod"),Dynamic,Provider("RegPropProv")]
        EncryptionMethod;

        //Required protectors properties
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|OSVolumeProtectorPolicy"),Dynamic,Provider("RegPropProv")]
        OsDriveProtector;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE\\MDOPBitLockerManagement|AutoUnlockFixedDataDrive"),Dynamic,Provider("RegPropProv")]
        FixedDataDriveAutoUnlock;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Policies\\Microsoft\\FVE|FDVPassphrase"),Dynamic,Provider("RegPropProv")]
        FixedDataDrivePassphrase;

        //MBAM agent fields
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMPolicyEnforced"),Dynamic,Provider("RegPropProv")]
        MBAMPolicyEnforced;
         [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|LastConsoleUser"),Dynamic,Provider("RegPropProv")]
        LastConsoleUser;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|UserExemptionDate"),Dynamic,Provider("RegPropProv")]
        UserExemptionDate; //Registry value should be string in the format of yyyymmddHHMMSS.mmmmmmsUUU
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|MBAMMachineError"),Dynamic,Provider("RegPropProv")]
        MBAMMachineError;
        [PropertyContext("Local|HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\MBAM|EncodedComputerName"),Dynamic,Provider("RegPropProv")]
        EncodedComputerName;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_OperatingSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,OperatingSystemSKU from Win32_OperatingSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_OperatingSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"OperatingSystemSKU"}]
        uint32     SKU;
    };

    # pragma namespace ("\\\\.\\root\\cimv2")
    # pragma deleteclass("CCM_ComputerSystemExtended", NOFAIL)
    [Union, ViewSources{"select Name,PCSystemType from Win32_ComputerSystem"}, ViewSpaces{"\\\\.\\root\\cimv2"},
    dynamic,Provider("MS_VIEW_INSTANCE_PROVIDER")]
    class CCM_ComputerSystemExtended
    {
        [PropertySources{"Name"},key]
        string     Name;
        [PropertySources{"PCSystemType"}]
        uint16     PCSystemType;
    };

    //=======================================================
    // Microsoft BitLocker Administration and Monitoring end
    //=======================================================

    ```

### <span data-ttu-id="10be0-248">MBAM 2.0 SP1 の翻訳</span><span class="sxs-lookup"><span data-stu-id="10be0-248">Translation of MBAM 2.0 SP1</span></span>

<span data-ttu-id="10be0-249">MBAM 2.0 SP1 は、次の言語で利用できるようになりました。</span><span class="sxs-lookup"><span data-stu-id="10be0-249">MBAM 2.0 SP1 is now available in the following languages:</span></span>

-   <span data-ttu-id="10be0-250">英語 (米国) en-us</span><span class="sxs-lookup"><span data-stu-id="10be0-250">English (United States) en-US</span></span>
-   <span data-ttu-id="10be0-251">フランス語 (フランス) fr-fr</span><span class="sxs-lookup"><span data-stu-id="10be0-251">French (France) fr-FR</span></span>
-   <span data-ttu-id="10be0-252">イタリア語 (イタリア) it IT IT</span><span class="sxs-lookup"><span data-stu-id="10be0-252">Italian (Italy) it-IT</span></span>
-   <span data-ttu-id="10be0-253">ドイツ語 (ドイツ) デデュープ</span><span class="sxs-lookup"><span data-stu-id="10be0-253">German (Germany) de-DE</span></span>
-   <span data-ttu-id="10be0-254">スペイン語、インターナショナルソート (スペイン) es</span><span class="sxs-lookup"><span data-stu-id="10be0-254">Spanish, International Sort (Spain) es-ES</span></span>
-   <span data-ttu-id="10be0-255">韓国語 (韓国) ko-KR</span><span class="sxs-lookup"><span data-stu-id="10be0-255">Korean (Korea) ko-KR</span></span>
-   <span data-ttu-id="10be0-256">日本語 (日本) ja-jp</span><span class="sxs-lookup"><span data-stu-id="10be0-256">Japanese (Japan) ja-JP</span></span>
-   <span data-ttu-id="10be0-257">ポルトガル語 (ブラジル) pt-BR</span><span class="sxs-lookup"><span data-stu-id="10be0-257">Portuguese (Brazil) pt-BR</span></span>
-   <span data-ttu-id="10be0-258">ロシア語 (ロシア) ru-RU</span><span class="sxs-lookup"><span data-stu-id="10be0-258">Russian (Russia) ru-RU</span></span>
-   <span data-ttu-id="10be0-259">繁体字中国語 zh-cn&platform</span><span class="sxs-lookup"><span data-stu-id="10be0-259">Chinese Traditional zh-TW</span></span>
-   <span data-ttu-id="10be0-260">簡体字中国語 zh-cn&platform-CN</span><span class="sxs-lookup"><span data-stu-id="10be0-260">Chinese Simplified zh-CN</span></span>

## <span data-ttu-id="10be0-261">MDOP 技術の入手方法</span><span class="sxs-lookup"><span data-stu-id="10be0-261">How to Get MDOP Technologies</span></span>

<span data-ttu-id="10be0-262">MBAM 2.0 SP1 は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="10be0-262">MBAM 2.0 SP1 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="10be0-263">MDOP は、Microsoft ソフトウェアアシュアランスの一部です。</span><span class="sxs-lookup"><span data-stu-id="10be0-263">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="10be0-264">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「 [mdop の入手方法](https://go.microsoft.com/fwlink/?LinkId=322049)」を参照してください https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="10be0-264">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="10be0-265">関連トピック</span><span class="sxs-lookup"><span data-stu-id="10be0-265">Related topics</span></span>

[<span data-ttu-id="10be0-266">MBAM 2.0 SP1 のリリース ノート</span><span class="sxs-lookup"><span data-stu-id="10be0-266">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)









