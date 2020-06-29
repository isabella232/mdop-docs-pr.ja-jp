---
title: Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要
description: Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825764"
---
# <span data-ttu-id="e3e0a-103">MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ</span><span class="sxs-lookup"><span data-stu-id="e3e0a-103">High-level architecture of MBAM 2.5 with Configuration Manager Integration topology</span></span>

<span data-ttu-id="e3e0a-104">このトピックでは、Configuration Manager 統合トポロジを使用して、Microsoft BitLocker 管理と監視 (MBAM) を展開するための推奨アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="e3e0a-105">このトポロジは、MBAM を System Center Configuration Manager と統合したものです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-105">This topology integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="e3e0a-106">スタンドアロントポロジで MBAM を導入する場合は、「 [mbam 2.5 の高レベルアーキテクチャとスタンドアロントポロジ](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-106">To deploy MBAM with the Stand-alone topology, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

<span data-ttu-id="e3e0a-107">このトピックで説明しているソフトウェアのサポートされているバージョンの一覧については、「 [Mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-107">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="e3e0a-108">**重要** Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-108">**Important** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="e3e0a-109">推奨されるサーバー数とクライアント数</span><span class="sxs-lookup"><span data-stu-id="e3e0a-109">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="e3e0a-110">運用環境での推奨されるサーバー数とサポートされているクライアント数は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-110">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e3e0a-111">推奨されるアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e3e0a-111">Recommended architecture</span></span></th>
<th align="left"><span data-ttu-id="e3e0a-112">詳細</span><span class="sxs-lookup"><span data-stu-id="e3e0a-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-113">サーバーとその他のコンピューターの数</span><span class="sxs-lookup"><span data-stu-id="e3e0a-113">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-114">3台のサーバー</span><span class="sxs-lookup"><span data-stu-id="e3e0a-114">Three servers</span></span></p>
<p><span data-ttu-id="e3e0a-115">1つのワークステーション</span><span class="sxs-lookup"><span data-stu-id="e3e0a-115">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e3e0a-116">サポートされているクライアントコンピューターの数</span><span class="sxs-lookup"><span data-stu-id="e3e0a-116">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-117">50万</span><span class="sxs-lookup"><span data-stu-id="e3e0a-117">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e3e0a-118">Configuration Manager の統合とスタンドアロントポロジの違い</span><span class="sxs-lookup"><span data-stu-id="e3e0a-118">Differences between Configuration Manager Integration and stand-alone topologies</span></span>


<span data-ttu-id="e3e0a-119">トポロジ間の主な違いは次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-119">The main differences between the topologies are:</span></span>

-   <span data-ttu-id="e3e0a-120">コンプライアンス機能とレポート機能は、MBAM から削除され、構成マネージャーからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-120">The compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

-   <span data-ttu-id="e3e0a-121">レポートは、Configuration Manager 管理コンソールから表示されます。回復監査レポートは除き、MBAM 管理と監視 Web サイトから引き続き表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-121">Reports are viewed from the Configuration Manager Management Console, with the exception of the Recovery Audit Report, which you continue to view from the MBAM Administration and Monitoring Website.</span></span>

## <span data-ttu-id="e3e0a-122">Configuration Manager の統合トポロジを使用した、推奨される MBAM 高レベルアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="e3e0a-122">Recommended MBAM high-level architecture with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="e3e0a-123">次の図と表は、Configuration Manager 統合トポロジでの MBAM の推奨される高レベルアーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-123">The following diagram and table describe the recommended high-level architecture for MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="e3e0a-124">MBAM 複数フォレスト展開には、一方向または双方向の信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-124">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="e3e0a-125">一方向の信頼には、サーバーのドメインがクライアントドメインを信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-125">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2\-5](images/mbam2-5-cmserver.png)

### <span data-ttu-id="e3e0a-127">データベースサーバー</span><span class="sxs-lookup"><span data-stu-id="e3e0a-127">Database server</span></span>

#### <span data-ttu-id="e3e0a-128">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="e3e0a-128">Recovery database</span></span>

<span data-ttu-id="e3e0a-129">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-129">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="e3e0a-130">**回復データベース**には、Mbam クライアントコンピューターから収集された回復データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-130">The **Recovery Database** stores recovery data that is collected from MBAM Client computers.</span></span>

#### <span data-ttu-id="e3e0a-131">監査データベース</span><span class="sxs-lookup"><span data-stu-id="e3e0a-131">Audit database</span></span>

<span data-ttu-id="e3e0a-132">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-132">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="e3e0a-133">**監査データベース**には、回復データにアクセスしたクライアントコンピューターから収集された監査アクティビティデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-133">The **Audit Database** stores audit activity data that is collected from client computers that have accessed recovery data.</span></span>

#### <span data-ttu-id="e3e0a-134">レポート</span><span class="sxs-lookup"><span data-stu-id="e3e0a-134">Reports</span></span>

<span data-ttu-id="e3e0a-135">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-135">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="e3e0a-136">組織内のクライアントコンピューターの回復監査データは、**レポート**によって提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-136">The **Reports** provide recovery audit data for the client computers in your enterprise.</span></span> <span data-ttu-id="e3e0a-137">レポートは、Configuration Manager コンソールから、または SQL Server Reporting Services から直接表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-137">You can view reports from the Configuration Manager console or directly from SQL Server Reporting Services.</span></span>

### <span data-ttu-id="e3e0a-138">Configuration Manager プライマリサイトサーバー</span><span class="sxs-lookup"><span data-stu-id="e3e0a-138">Configuration Manager primary site server</span></span>

<span data-ttu-id="e3e0a-139">System Center Configuration Manager の統合機能</span><span class="sxs-lookup"><span data-stu-id="e3e0a-139">System Center Configuration Manager Integration feature</span></span>

-   <span data-ttu-id="e3e0a-140">この機能は構成マネージャーのプライマリサイトサーバーで構成されます。これは、構成マネージャーインフラストラクチャのトップ層サーバーです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-140">This feature is configured on the Configuration Manager Primary Site Server, which is the top-tier server in your Configuration Manager infrastructure.</span></span>

-   <span data-ttu-id="e3e0a-141">**Configuration Manager サーバー**は、クライアントコンピューターからハードウェアインベントリ情報を収集し、クライアントコンピューターの BitLocker のコンプライアンスを報告するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-141">The **Configuration Manager Server** collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span>

-   <span data-ttu-id="e3e0a-142">Microsoft BitLocker の管理と監視のセットアップウィザードを実行してサーバーソフトウェアをインストールする場合、MBAM がサポートするコンピューターのコレクション、構成基準、およびレポートは、Configuration Manager プライマリサイトサーバーで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-142">When you run the Microsoft BitLocker Administration and Monitoring Setup wizard to install the server software, the MBAM Supported Computers collection, configuration baseline, and reports are configured on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="e3e0a-143">MBAM サーバーソフトウェアをインストールするコンピューターと同じコンピューターに**Configuration Manager コンソール**をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-143">The **Configuration Manager console** must be installed on the same computer on which you install the MBAM Server software.</span></span>

### <span data-ttu-id="e3e0a-144">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="e3e0a-144">Administration and monitoring server</span></span>

#### <span data-ttu-id="e3e0a-145">管理と監視の web サイト</span><span class="sxs-lookup"><span data-stu-id="e3e0a-145">Administration and monitoring website</span></span>

<span data-ttu-id="e3e0a-146">この機能は、Windows Server が実行されているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-146">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="e3e0a-147">**管理と監視の web サイト**を使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-147">The **Administration and monitoring website** is used to:</span></span>

-   <span data-ttu-id="e3e0a-148">ロックアウトされている場合、エンドユーザーが自分のコンピューターにアクセスできるようにします。(Web サイトのこの領域は、一般にヘルプデスクと呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-148">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="e3e0a-149">クライアントコンピューターの回復アクティビティが表示されている回復監査レポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-149">View the Recovery Audit Report, which shows recovery activity for client computers.</span></span> <span data-ttu-id="e3e0a-150">その他のレポートは、Configuration Manager コンソールから表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-150">Other reports are viewed from the Configuration Manager console.</span></span>

#### <span data-ttu-id="e3e0a-151">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="e3e0a-151">Self-service portal</span></span>

<span data-ttu-id="e3e0a-152">この機能は、Windows Server が実行されているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-152">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="e3e0a-153">**セルフサービスポータル**は、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れるということを確認するために、個別に web サイトにログオンして回復キーを取得できるようにする web サイトです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-153">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

#### <span data-ttu-id="e3e0a-154">この web サイトの web サービスを監視する</span><span class="sxs-lookup"><span data-stu-id="e3e0a-154">Monitoring web services for this website</span></span>

<span data-ttu-id="e3e0a-155">この機能は、Windows Server が実行されているコンピューターにインストールされています。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-155">This feature is installed on a computer running Windows Server.</span></span>

<span data-ttu-id="e3e0a-156">この**監視 web サービス**は、Mbam クライアントと web サイトでデータベースと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-156">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

**<span data-ttu-id="e3e0a-157">重要</span><span class="sxs-lookup"><span data-stu-id="e3e0a-157">Important</span></span>**<br><span data-ttu-id="e3e0a-158">MBAM web サイトは、回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-158">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span> 

 

### <span data-ttu-id="e3e0a-159">管理ワークステーション</span><span class="sxs-lookup"><span data-stu-id="e3e0a-159">Management workstation</span></span>

#### <span data-ttu-id="e3e0a-160">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="e3e0a-160">MBAM group policy templates</span></span>

-   <span data-ttu-id="e3e0a-161">**Mbam グループポリシーテンプレート**は、BitLocker ドライブ暗号化を管理するための、mbam の実装設定を定義するグループポリシー設定です。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-161">The **MBAM Group Policy Templates** are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker drive encryption.</span></span>

-   <span data-ttu-id="e3e0a-162">MBAM を実行する前に、グループポリシーテンプレートをダウンロードして、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)し、サポートされている windows サーバーまたは windows オペレーティングシステムを実行しているサーバーまたはワークステーションにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-162">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

    **<span data-ttu-id="e3e0a-163">注</span><span class="sxs-lookup"><span data-stu-id="e3e0a-163">NOTE</span></span>**<br><span data-ttu-id="e3e0a-164">ワークステーションは専用のコンピュータである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-164">The workstation does not have to be a dedicated computer.</span></span>

     

### <span data-ttu-id="e3e0a-165">MBAM クライアントと Configuration Manager クライアントコンピューター</span><span class="sxs-lookup"><span data-stu-id="e3e0a-165">MBAM Client and Configuration Manager Client computer</span></span>

#### <span data-ttu-id="e3e0a-166">MBAM クライアントソフトウェア</span><span class="sxs-lookup"><span data-stu-id="e3e0a-166">MBAM Client software</span></span>

<span data-ttu-id="e3e0a-167">**Mbam クライアント**:</span><span class="sxs-lookup"><span data-stu-id="e3e0a-167">The **MBAM Client**:</span></span>

-   <span data-ttu-id="e3e0a-168">グループポリシーオブジェクトを使用して、企業内のクライアントコンピューターで BitLocker ドライブ暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-168">Uses Group Policy Objects to enforce BitLocker drive encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="e3e0a-169">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブル (USB) データドライブの3種類のデータドライブの BitLocker 回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-169">Collects the BitLocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="e3e0a-170">クライアントコンピューターに関する回復情報とコンピューターに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-170">Collects recovery information and computer information about the client computers.</span></span>

#### <span data-ttu-id="e3e0a-171">構成マネージャー クライアント</span><span class="sxs-lookup"><span data-stu-id="e3e0a-171">Configuration Manager Client</span></span>

<span data-ttu-id="e3e0a-172">Configuration manager**クライアント**は、クライアントコンピューターに関するハードウェア互換性データを収集し、コンプライアンス情報を報告できるようにします。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-172">The **Configuration Manager Client** enables Configuration Manager to collect hardware compatibility data about the client computers and report compliance information.</span></span>

 

## <span data-ttu-id="e3e0a-173">サポートされている Configuration Manager バージョン向けの MBAM 展開の相違点</span><span class="sxs-lookup"><span data-stu-id="e3e0a-173">Differences in MBAM deployment for supported Configuration Manager versions</span></span>


<span data-ttu-id="e3e0a-174">Configuration Manager の統合トポロジを使用して MBAM を展開する場合は、プライマリサイトサーバーに MBAM をインストールできます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-174">When you deploy MBAM with the Configuration Manager Integration topology, you can install MBAM on a primary site server.</span></span> <span data-ttu-id="e3e0a-175">ただし、MBAM インストールの動作は、システム Center2012 構成マネージャーと構成 Manager2007 によって異なります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-175">However, the MBAM installation works differently for System Center2012 Configuration Manager and Configuration Manager2007.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e3e0a-176">Configuration Manager のバージョン</span><span class="sxs-lookup"><span data-stu-id="e3e0a-176">Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="e3e0a-177">説明</span><span class="sxs-lookup"><span data-stu-id="e3e0a-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-178">System Center2012 R2 構成マネージャー</span><span class="sxs-lookup"><span data-stu-id="e3e0a-178">System Center2012 R2 Configuration Manager</span></span></p>
<p><span data-ttu-id="e3e0a-179">System Center2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e3e0a-179">System Center2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-180">MBAM をプライマリサイトサーバーまたはサーバーの全体管理サーバーにインストールする場合、MBAM はそのサイトサーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-180">If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e3e0a-181">構成 Manager2007 R2</span><span class="sxs-lookup"><span data-stu-id="e3e0a-181">Configuration Manager2007 R2</span></span></p>
<p><span data-ttu-id="e3e0a-182">構成 Manager2007</span><span class="sxs-lookup"><span data-stu-id="e3e0a-182">Configuration Manager2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-183">大規模なサイトの親サーバーを持つ大きな Configuration Manager 階層の一部であるプライマリサイトサーバーに MBAM をインストールする場合、MBAM はセントラルサイトの親サーバーを識別し、その親サーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-183">If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy with a central site parent server, MBAM identifies the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="e3e0a-184">インストールには、前提条件の確認および Configuration Manager のオブジェクトとレポートのインストールが含まれます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-184">The installation includes checking prerequisites and installing the Configuration Manager objects and reports.</span></span></p>
<p><span data-ttu-id="e3e0a-185">たとえば、セントラルサイトの親サーバーの子であるプライマリサイトサーバーに MBAM をインストールすると、MBAM は親サーバー上のすべての Configuration Manager オブジェクトとレポートをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-185">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="e3e0a-186">MBAM を親サーバーにインストールする場合、MBAM はその親サーバー上のすべてのインストールアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-186">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e3e0a-187">構成マネージャーを使用した MBAM の動作</span><span class="sxs-lookup"><span data-stu-id="e3e0a-187">How MBAM works with Configuration Manager</span></span>


<span data-ttu-id="e3e0a-188">MBAM と Configuration Manager の統合は、次の表で説明されている項目をインストールする構成パックに基づいています。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-188">The integration of MBAM with Configuration Manager is based on a configuration pack that installs the items described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e3e0a-189">構成マネージャーにインストールされたアイテム</span><span class="sxs-lookup"><span data-stu-id="e3e0a-189">Items installed into Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="e3e0a-190">説明</span><span class="sxs-lookup"><span data-stu-id="e3e0a-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-191">構成データ</span><span class="sxs-lookup"><span data-stu-id="e3e0a-191">Configuration data</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-192">構成データは、次の2つの構成項目を含む、"BitLocker Protection" と呼ばれる構成基準をインストールします。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-192">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3e0a-193">BitLocker オペレーティングシステムドライブの保護</span><span class="sxs-lookup"><span data-stu-id="e3e0a-193">BitLocker Operating System Drive Protection</span></span></p></li>
<li><p><span data-ttu-id="e3e0a-194">BitLocker 固定データドライブの保護</span><span class="sxs-lookup"><span data-stu-id="e3e0a-194">BitLocker Fixed Data Drives Protection</span></span></p></li>
</ul>
<p><span data-ttu-id="e3e0a-195">構成基準は、mbam でサポートされているコンピューターのコレクションに展開されます。これは、MBAM をインストールしたときにも作成されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-195">The configuration baseline is deployed to the MBAM Supported Computers collection, which is also created when MBAM is installed.</span></span></p>
<p><span data-ttu-id="e3e0a-196">2つの構成項目は、クライアントコンピューターのコンプライアンスの状態を評価するための基礎となります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-196">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="e3e0a-197">この情報は、構成マネージャーでキャプチャ、保存、評価されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-197">This information is captured, stored, and evaluated in Configuration Manager.</span></span></p>
<p><span data-ttu-id="e3e0a-198">構成項目は、オペレーティングシステムドライブと固定データドライブのコンプライアンス要件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-198">The configuration items are based on the compliance requirements for operating system drives and fixed data drives.</span></span> <span data-ttu-id="e3e0a-199">展開されたコンピューターに必要な詳細情報が収集されて、それらのドライブの種類のコンプライアンスが評価されるようになります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-199">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span></p>
<p><span data-ttu-id="e3e0a-200">既定では、構成基準はコンプライアンスの状態の every12 hours を評価し、コンプライアンスデータを Configuration Manager に送信します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-200">By default, the configuration baseline evaluates the compliance status every12 hours and sends the compliance data to Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e3e0a-201">MBAM サポートされているコンピューターコレクション</span><span class="sxs-lookup"><span data-stu-id="e3e0a-201">MBAM Supported Computers collection</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-202">MBAM サポートされているコンピューターと呼ばれるコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-202">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="e3e0a-203">構成基準は、このコレクション内のクライアントコンピューターを対象としています。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-203">The configuration baseline is targeted to client computers that are in this collection.</span></span></p>
<p><span data-ttu-id="e3e0a-204">これは動的なコレクションです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-204">This is a dynamic collection.</span></span> <span data-ttu-id="e3e0a-205">既定では、every12 時間が実行され、次の3つの条件に基づいてメンバーシップが評価されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-205">By default, it runs every12 hours and evaluates membership, based on three criteria:</span></span></p>
<ul>
<li><p><span data-ttu-id="e3e0a-206">コンピューターは、サポートされている Windows オペレーティングシステムのバージョンです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-206">The computer is a supported version of the Windows operating system.</span></span></p></li>
<li><p><span data-ttu-id="e3e0a-207">コンピューターは物理コンピューターです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-207">The computer is a physical computer.</span></span> <span data-ttu-id="e3e0a-208">仮想マシンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-208">Virtual machines are not supported.</span></span></p></li>
<li><p><span data-ttu-id="e3e0a-209">コンピューターには、利用可能なトラステッドプラットフォームモジュール (TPM) があります。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-209">The computer has a Trusted Platform Module (TPM) that is available.</span></span> <span data-ttu-id="e3e0a-210">Windows7 には、互換性のあるバージョンの TPM 1.2 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-210">A compatible version of TPM1.2 or later is required for Windows7.</span></span> <span data-ttu-id="e3e0a-211">Windows 10、Windows 8.1、Windows8、および Windows To Go では、TPM は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-211">Windows10, Windows8.1, Windows8, and Windows To Go do not require a TPM.</span></span></p></li>
</ul>
<p><span data-ttu-id="e3e0a-212">コレクションは、すべてのコンピューターに対して評価され、互換性のあるコンピューターのサブセットが作成されます。これにより、MBAM 統合のコンプライアンス評価と報告の基礎が提供されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-212">The collection is evaluated against all computers and a subset of compatible computers is created, which provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-213">レポート</span><span class="sxs-lookup"><span data-stu-id="e3e0a-213">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-214">Configuration Manager の統合トポロジで MBAM を構成すると、[Configuration Manager] ですべてのレポートを表示します。回復監査レポートは、従来の MBAM 管理と監視の Web サイトで引き続き表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-214">When you configure MBAM with the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit Report, the latter of which you continue to view in the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="e3e0a-215">構成マネージャーで利用可能なレポートは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-215">The reports available in Configuration Manager are:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e3e0a-216">レポート</span><span class="sxs-lookup"><span data-stu-id="e3e0a-216">Report</span></span></th>
<th align="left"><span data-ttu-id="e3e0a-217">説明</span><span class="sxs-lookup"><span data-stu-id="e3e0a-217">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-218">BitLocker エンタープライズコンプライアンスダッシュボード</span><span class="sxs-lookup"><span data-stu-id="e3e0a-218">BitLocker Enterprise Compliance Dashboard</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-219">IT 管理者に対して、1つのレポート内の情報の3つのビューを提供します。これは、コンプライアンスステータスの配布、非準拠–エラーの分布、およびドライブの種類別のコンプライアンスステータスの配布です。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-219">Gives IT administrators three views of information in a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="e3e0a-220">レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-220">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e3e0a-221">BitLocker Enterprise コンプライアンスの詳細</span><span class="sxs-lookup"><span data-stu-id="e3e0a-221">BitLocker Enterprise Compliance Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-222">IT 管理者は、企業の BitLocker 暗号化のコンプライアンスステータスに関する情報を表示し、各コンピューターのコンプライアンスの状態を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-222">Lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="e3e0a-223">レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-223">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e3e0a-224">BitLocker コンピューターのコンプライアンス</span><span class="sxs-lookup"><span data-stu-id="e3e0a-224">BitLocker Computer Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-225">IT 管理者が個々のコンピューターを表示し、それが準拠しているかどうかについて報告された理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-225">Lets IT administrators view an individual computer and determine why it was reported with a status of compliant or not compliant.</span></span> <span data-ttu-id="e3e0a-226">このレポートには、オペレーティングシステムドライブと固定データドライブの暗号化状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-226">The report also displays the encryption state of the operating system drives and fixed data drives.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e3e0a-227">BitLocker Enterprise コンプライアンスの概要</span><span class="sxs-lookup"><span data-stu-id="e3e0a-227">BitLocker Enterprise Compliance Summary</span></span></p></td>
<td align="left"><p><span data-ttu-id="e3e0a-228">IT 管理者は、組織内の MBAM ポリシーのコンプライアンスの状態を表示できます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-228">Lets IT administrators view the status of MBAM policy compliance in the enterprise.</span></span> <span data-ttu-id="e3e0a-229">各コンピューターの状態が評価され、ポリシーに対する企業内のすべてのコンピューターのコンプライアンスの概要がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-229">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="e3e0a-230">レポートのドリルダウンオプションを使用すると、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-230">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="e3e0a-231">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e3e0a-231">Related topics</span></span>


[<span data-ttu-id="e3e0a-232">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="e3e0a-232">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="e3e0a-233">スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要</span><span class="sxs-lookup"><span data-stu-id="e3e0a-233">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[<span data-ttu-id="e3e0a-234">MBAM 2.5 展開の機能の図</span><span class="sxs-lookup"><span data-stu-id="e3e0a-234">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <span data-ttu-id="e3e0a-235">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-235">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e3e0a-236">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-236">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e3e0a-237">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="e3e0a-237">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




