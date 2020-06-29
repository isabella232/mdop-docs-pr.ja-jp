---
title: 以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード
description: 以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード
author: dansimp
ms.assetid: a9edb4b8-5d5e-42ab-8db6-619db2878e50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 07a03ebbbfce45f7f69a85000e18ddf1a58e53ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812754"
---
# <span data-ttu-id="87c02-103">以前のバージョンから MBAM 2.5 または MBAM 2.5 SP1 へのアップグレード</span><span class="sxs-lookup"><span data-stu-id="87c02-103">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>


<span data-ttu-id="87c02-104">このトピックでは、Microsoft BitLocker の管理と監視 (MBAM) サーバーと MBAM クライアントを以前のバージョンの MBAM からアップグレードするプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="87c02-104">This topic describes the process for upgrading the Microsoft BitLocker Administration and Monitoring (MBAM) Server and the MBAM Client from earlier versions of MBAM.</span></span>

<span data-ttu-id="87c02-105">**注** 以前のバージョンの MBAM から MBAM 2.5 または MBAM 2.5 SP1 に直接アップグレードすることができます。</span><span class="sxs-lookup"><span data-stu-id="87c02-105">**Note** You can upgrade directly to MBAM 2.5 or MBAM 2.5 SP1 from any previous version of MBAM.</span></span>

 

## <span data-ttu-id="87c02-106">アップグレードを開始する前に</span><span class="sxs-lookup"><span data-stu-id="87c02-106">Before you start the upgrade</span></span>


<span data-ttu-id="87c02-107">アップグレードを開始する前に、次の情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="87c02-107">Review the following information before you start the upgrade.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="87c02-108">始める前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="87c02-108">What to know before you start</span></span></th>
<th align="left"><span data-ttu-id="87c02-109">詳細</span><span class="sxs-lookup"><span data-stu-id="87c02-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87c02-110">MBAM web サイトを1つのサーバーと別のサーバー上の web サービスにインストールする場合は、Windows PowerShell コマンドレットを使用して構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87c02-110">If you are installing the MBAM websites on one server and the web services on another server, you have to use Windows PowerShell cmdlets to configure them.</span></span></p></td>
<td align="left"><p><span data-ttu-id="87c02-111">MBAM サーバーの構成ウィザードでは、1つのサーバーと別のサーバー上の web サービスで web サイトを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="87c02-111">The MBAM Server Configuration wizard does not support configuring the websites on one server and the web services on a different server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87c02-112">Windows Server2008 R2 の MBAM 2.0 または 2.0 SP1 から MBAM 2.5 または 2.5 SP1 にアップグレードする場合は、次の操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="87c02-112">If you are upgrading to MBAM2.5 or 2.5 SP1 from MBAM2.0 or 2.0 SP1 in Windows Server2008 R2:</span></span></p>
<p><span data-ttu-id="87c02-113">インターネットインフォメーションサービス (IIS) がすでにインストールされている場合は、管理と監視の Web サイトとセルフサービスポータルは使用できません。</span><span class="sxs-lookup"><span data-stu-id="87c02-113">The Administration and Monitoring Website and the Self-Service Portal will not work if you install the required .NET Framework4.5 software after Internet Information Services (IIS) is already installed.</span></span></p>
<p><span data-ttu-id="87c02-114">この問題が発生するのは、IIS をインストールした後で .NET Framework がインストールされた場合に、ASP.NET を IIS に正しく登録できないためです。</span><span class="sxs-lookup"><span data-stu-id="87c02-114">This issue occurs because ASP.NET cannot be registered correctly with IIS if the .NET Framework is installed after IIS has already been installed.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="87c02-115">この問題を解決するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="87c02-115">To resolve this issue:</span></span></strong></p>
<p><span data-ttu-id="87c02-116"><strong> </strong> 次の場所から aspnet_regiis – i を実行します。</span><span class="sxs-lookup"><span data-stu-id="87c02-116">Run <strong>aspnet_regiis –i</strong> from the following location:</span></span></p>
<p><span data-ttu-id="87c02-117">C:\windows\microsoft.net\Framework\v4.0.30319</span><span class="sxs-lookup"><span data-stu-id="87c02-117">C:\windows\microsoft.net\Framework\v4.0.30319</span></span></p>
<p><span data-ttu-id="87c02-118">詳細については、「 <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)"> ASP.NET IIS 登録ツール」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="87c02-118">For more information, see: <a href="https://go.microsoft.com/fwlink/?LinkId=393272" data-raw-source="[ASP.NET IIS Registration Tool](https://go.microsoft.com/fwlink/?LinkId=393272)">ASP.NET IIS Registration Tool</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87c02-119">次の条件がすべて満たされている場合は、アプリケーションプールアカウントに SPN を登録します。</span><span class="sxs-lookup"><span data-stu-id="87c02-119">Register an SPN on the application pool account if all of the following are true:</span></span></p>
<ul>
<li><p><span data-ttu-id="87c02-120">以前のバージョンの MBAM からアップグレードしようとしています。</span><span class="sxs-lookup"><span data-stu-id="87c02-120">You are upgrading from a previous version of MBAM.</span></span></p></li>
<li><p><span data-ttu-id="87c02-121">現時点では、ロードバランスまたは分散構成で MBAM web サイトを実行していませんが、MBAM 2.5 または 2.5 SP1 にアップグレードした場合は、このようにします。</span><span class="sxs-lookup"><span data-stu-id="87c02-121">Currently, you are not running the MBAM websites in a load-balanced or distributed configuration, but you would like to do so when you upgrade to MBAM2.5 or 2.5 SP1.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="87c02-122">手順については、「 <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)"> MBAM Web サイトをセキュリティで保護する方法を計画する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="87c02-122">For instructions, see <a href="planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md#bkmk-registerspn)">Planning How to Secure the MBAM Websites</a>.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="87c02-123">推奨事項</span><span class="sxs-lookup"><span data-stu-id="87c02-123">What we recommend</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="87c02-124">コンピューターアカウントの Spn が既に登録されている場合でも、アプリケーションプールアカウントのサービスプリンシパル名 (SPN) を登録します。</span><span class="sxs-lookup"><span data-stu-id="87c02-124">Register a service principal name (SPN) for the application pool account, even though you may already have registered SPNs for the machine account.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="87c02-125">推奨される理由</span><span class="sxs-lookup"><span data-stu-id="87c02-125">Why we recommend it</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="87c02-126">負荷分散または分散構成で web サイトを構成するには、アプリケーションプールアカウントに SPN を登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="87c02-126">Registering an SPN on the application pool account is required to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="87c02-127">コンピューターアカウントで Spn が既に構成されている場合はどうなりますか?</span><span class="sxs-lookup"><span data-stu-id="87c02-127">What happens if SPNs are already configured on a machine account?</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="87c02-128">MBAM は、既に登録済みの Spn を使用します。追加の Spn を構成する必要はありませんが、負荷分散または分散構成で web サイトを構成することはできません。</span><span class="sxs-lookup"><span data-stu-id="87c02-128">MBAM will use the SPNs that you have already registered, and you don’t need to configure additional SPNs, but you are not able to configure the websites in a load-balanced or distributed configuration.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="87c02-129">MBAM サーバーインフラストラクチャのアップグレード手順</span><span class="sxs-lookup"><span data-stu-id="87c02-129">Steps to upgrade the MBAM Server infrastructure</span></span>


<span data-ttu-id="87c02-130">スタンドアロントポロジまたは System Center Configuration Manager の統合トポロジ用に MBAM をアップグレードするには、次のセクションの手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="87c02-130">Use the steps in the following sections to upgrade MBAM for the Stand-alone topology or the System Center Configuration Manager Integration topology.</span></span>

**<span data-ttu-id="87c02-131">スタンドアロントポロジのために MBAM サーバーインフラストラクチャをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="87c02-131">To upgrade the MBAM Server infrastructure for Stand-alone topology</span></span>**

1.  <span data-ttu-id="87c02-132">以前のバージョンの MBAM を**プログラムと機能**および web サーバーからアンインストールして、情報が mbam クライアントから mbam インフラストラクチャに書き込まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="87c02-132">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="87c02-133">手順について[は、「MBAM サーバーの機能またはソフトウェアの削除](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87c02-133">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="87c02-134">データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="87c02-134">Back up your databases.</span></span>

3.  <span data-ttu-id="87c02-135">SQL server Reporting Services を使用して MBAM レポートをホストしている SQL Server など、**プログラムと機能**を使って、sql server から以前のバージョンの mbam をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-135">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="87c02-136">残りのすべての MBAM サーバーの一時ファイルまたはフォルダーをデータベースサーバーと reporting services から削除します。</span><span class="sxs-lookup"><span data-stu-id="87c02-136">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

    <span data-ttu-id="87c02-137">**注** データベースは削除されず、すべてのコンプライアンスデータと回復データはデータベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="87c02-137">**Note** The databases will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

4.  <span data-ttu-id="87c02-138">MBAM 2.5 または 2.5 SP1 のデータベース、レポート、および web アプリケーションをその順序でインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="87c02-138">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, and web applications, in that order.</span></span> <span data-ttu-id="87c02-139">データベースが適切にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="87c02-139">The databases are upgraded in place.</span></span>

5.  <span data-ttu-id="87c02-140">MBAM 2.5 テンプレートを使用してグループポリシーオブジェクト (Gpo) を更新し、暗号化の強制などの MBAM の新機能を利用します。</span><span class="sxs-lookup"><span data-stu-id="87c02-140">Update the Group Policy Objects (GPOs) using the MBAM 2.5 Templates to leverage the new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="87c02-141">Gpo と MBAM クライアントを MBAM 2.5 に更新しない場合、以前のバージョンの MBAM クライアントは、機能が制限された現在の Gpo に対して引き続き報告されます。</span><span class="sxs-lookup"><span data-stu-id="87c02-141">If you do not update the GPOs and the MBAM client to MBAM 2.5, earlier versions of MBAM clients will continue to report against your current GPOs with reduced functionality.</span></span> <span data-ttu-id="87c02-142">最新の ADMX テンプレートをダウンロードするために、 [MDOP グループポリシー (admx) テンプレートを取得する方法](https://www.microsoft.com/download/details.aspx?id=41183)について説明します。</span><span class="sxs-lookup"><span data-stu-id="87c02-142">See [How to Get MDOP Group Policy (.admx) Templates](https://www.microsoft.com/download/details.aspx?id=41183) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="87c02-143">MBAM サーバーインフラストラクチャをアップグレードした後、既存のクライアントコンピューターは、MBAM 2.5 または 2.5 SP1 サーバーに引き続き正常に報告し、回復データは保存されたままになります。</span><span class="sxs-lookup"><span data-stu-id="87c02-143">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

6.  <span data-ttu-id="87c02-144">最新の MBAM 2.5 または 2.5 SP1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-144">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="87c02-145">クライアントコンピューターは、展開後に再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87c02-145">Client computers do not need to be rebooted after the deployment.</span></span>

**<span data-ttu-id="87c02-146">System Center Configuration Manager の統合トポロジ用の MBAM インフラストラクチャをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="87c02-146">To upgrade the MBAM infrastructure for System Center Configuration Manager Integration topology</span></span>**

1.  <span data-ttu-id="87c02-147">以前のバージョンの MBAM を**プログラムと機能**および web サーバーからアンインストールして、情報が mbam クライアントから mbam インフラストラクチャに書き込まれないようにします。</span><span class="sxs-lookup"><span data-stu-id="87c02-147">Uninstall previous versions of MBAM from **Programs and Features** and from web servers to make sure that information is not being written from MBAM clients to the MBAM infrastructure.</span></span> <span data-ttu-id="87c02-148">手順について[は、「MBAM サーバーの機能またはソフトウェアの削除](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87c02-148">For instructions, see [Removing MBAM Server Features or Software](removing-mbam-server-features-or-software.md#bkmk-removeserverfeatures).</span></span>

2.  <span data-ttu-id="87c02-149">データベースをバックアップします。</span><span class="sxs-lookup"><span data-stu-id="87c02-149">Back up your databases.</span></span>

3.  <span data-ttu-id="87c02-150">SQL server Reporting Services を使用して MBAM レポートをホストしている SQL Server など、**プログラムと機能**を使って、sql server から以前のバージョンの mbam をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-150">Uninstall previous versions of MBAM from SQL Server by using **Programs and Features**, including SQL Servers hosting the MBAM reports via SQL Server Reporting Services.</span></span> <span data-ttu-id="87c02-151">残りのすべての MBAM サーバーの一時ファイルまたはフォルダーをデータベースサーバーと reporting services から削除します。</span><span class="sxs-lookup"><span data-stu-id="87c02-151">Remove any remaining MBAM server temporary files or folders from the database server and reporting services.</span></span>

4.  <span data-ttu-id="87c02-152">Configuration Manager サーバーから MBAM をアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-152">Uninstall MBAM from the Configuration Manager server.</span></span>

    <span data-ttu-id="87c02-153">**注** データベースと Configuration Manager オブジェクト (baseline、MBAM サポートされているコンピューターのコレクション、およびレポート) は削除されず、すべてのコンプライアンスデータと回復データはデータベースに保持されます。</span><span class="sxs-lookup"><span data-stu-id="87c02-153">**Note** The databases and the Configuration Manager objects (baseline, MBAM supported computers collection, and Reports) will not be removed, and all compliance and recovery data is maintained in the database.</span></span>

     

5.  <span data-ttu-id="87c02-154">.Mof ファイルを更新します。</span><span class="sxs-lookup"><span data-stu-id="87c02-154">Update the .mof files.</span></span>

6.  <span data-ttu-id="87c02-155">MBAM 2.5 または 2.5 SP1 データベース、レポート、web アプリケーション、構成マネージャーの統合をその順序でインストールして構成します。</span><span class="sxs-lookup"><span data-stu-id="87c02-155">Install and configure the MBAM2.5 or 2.5 SP1 databases, reports, web applications, and Configuration Manager integration, in that order.</span></span> <span data-ttu-id="87c02-156">データベースと構成マネージャーのオブジェクトが適切にアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="87c02-156">The databases and Configuration Manager objects are upgraded in place.</span></span>

7.  <span data-ttu-id="87c02-157">必要に応じて、[暗号化の強制] などの新しい機能を MBAM に実装する場合は、グループポリシーオブジェクト (Gpo) を更新し、設定を編集します。</span><span class="sxs-lookup"><span data-stu-id="87c02-157">Optionally, update the Group Policy Objects (GPOs), and edit the settings if you want to implement new features in MBAM, such as enforced encryption.</span></span> <span data-ttu-id="87c02-158">Gpo を更新しない場合、MBAM は現在の Gpo に対して引き続き報告します。</span><span class="sxs-lookup"><span data-stu-id="87c02-158">If you do not update the GPOs, MBAM will continue to report against your current GPOs.</span></span> <span data-ttu-id="87c02-159">最新の ADMX テンプレートをダウンロードするために、 [MDOP グループポリシー (admx) テンプレートを取得する方法](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)について説明します。</span><span class="sxs-lookup"><span data-stu-id="87c02-159">See [How to Get MDOP Group Policy (.admx) Templates](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates) to download the latest ADMX templates.</span></span>

    <span data-ttu-id="87c02-160">MBAM サーバーインフラストラクチャをアップグレードした後、既存のクライアントコンピューターは、MBAM 2.5 または 2.5 SP1 サーバーに引き続き正常に報告し、回復データは保存されたままになります。</span><span class="sxs-lookup"><span data-stu-id="87c02-160">After you upgrade the MBAM Server infrastructure, the existing client computers continue to successfully report to the MBAM2.5 or 2.5 SP1 Server, and recovery data continues to be stored.</span></span>

8.  <span data-ttu-id="87c02-161">最新の MBAM 2.5 または 2.5 SP1 クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-161">Install the latest MBAM2.5 or 2.5 SP1 Client.</span></span> <span data-ttu-id="87c02-162">クライアントコンピューターは、展開後に再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="87c02-162">Client computers do not need to be rebooted after the deployment.</span></span>

## <span data-ttu-id="87c02-163">MBAM クライアントのアップグレードのサポート</span><span class="sxs-lookup"><span data-stu-id="87c02-163">Upgrade support for the MBAM Client</span></span>


<span data-ttu-id="87c02-164">MBAM は、以前のバージョンの MBAM クライアントから MBAM 2.5 クライアントへのアップグレードをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="87c02-164">MBAM supports upgrades to the MBAM2.5 Client from any earlier version of the MBAM Client.</span></span>

**<span data-ttu-id="87c02-165">MBAM クライアントをインストールする方法:</span><span class="sxs-lookup"><span data-stu-id="87c02-165">Ways to install the MBAM Client:</span></span>**

-   <span data-ttu-id="87c02-166">Mbam クライアントを実行しているコンピューターを一度にすべて、または MBAM 2.5 Server インフラストラクチャのインストール後に段階的にアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="87c02-166">Upgrade the computers running MBAM Client all at once or gradually after you install the MBAM2.5 Server infrastructure.</span></span>

-   <span data-ttu-id="87c02-167">電子ソフトウェア配布システムまたは Active Directory Domain Services または System Center Configuration Manager などのツールを使用して、MBAM クライアントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="87c02-167">Install the MBAM Client through an electronic software distribution system or through tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>



## <span data-ttu-id="87c02-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="87c02-168">Related topics</span></span>


[<span data-ttu-id="87c02-169">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="87c02-169">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="87c02-170">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="87c02-170">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="87c02-171">MBAM 2.5 サーバー機能の構成</span><span class="sxs-lookup"><span data-stu-id="87c02-171">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)

 

## <span data-ttu-id="87c02-172">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="87c02-172">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="87c02-173">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="87c02-173">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="87c02-174">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="87c02-174">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





