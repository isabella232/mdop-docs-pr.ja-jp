---
title: はじめに - MBAM と Configuration Manager の使用
description: はじめに - MBAM と Configuration Manager の使用
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 654de38918102a41395efe37dc593ce8f49113e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825167"
---
# <span data-ttu-id="cfa76-103">はじめに - MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="cfa76-103">Getting Started - Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="cfa76-104">Microsoft BitLocker の管理と監視 (MBAM) をインストールするときに、MBAM を Configuration Manager 2007 または SystemCenter2012 ConfigurationManager と統合するトポロジを選ぶことができます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose a topology that integrates MBAM with Configuration Manager 2007 or SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="cfa76-105">MBAM がサポートしている Configuration Manager のサポートされているバージョンの一覧については、「 [Configuration manager を使用して MBAM を展開するための計画](planning-to-deploy-mbam-with-configuration-manager-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cfa76-105">For a list of the supported versions of Configuration Manager that MBAM supports, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span> <span data-ttu-id="cfa76-106">統合トポロジでは、ハードウェアのコンプライアンスとレポート機能は MBAM から削除され、構成マネージャーからアクセスされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-106">In the integrated topology, the hardware compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

<span data-ttu-id="cfa76-107">**重要** Configuration Manager 2007 で MBAM の統合トポロジをインストールする場合、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="cfa76-107">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="cfa76-108">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="cfa76-108">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="cfa76-109">MBAM の統合は、次の3つの項目を Configuration Manager 2007 または SystemCenter2012 ConfigurationManager にインストールする新しい構成パックに基づいています。これについては、次のセクションで詳しく説明します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-109">The integration of MBAM is based on a new Configuration Pack that installs the following three items into Configuration Manager 2007 or SystemCenter2012 ConfigurationManager, which are described in detail in the following sections:</span></span>

<span data-ttu-id="cfa76-110">構成項目と構成基準で構成される構成データ</span><span class="sxs-lookup"><span data-stu-id="cfa76-110">Configuration data that consists of configuration items and a configuration baseline</span></span>

<span data-ttu-id="cfa76-111">コレクション</span><span class="sxs-lookup"><span data-stu-id="cfa76-111">Collection</span></span>

<span data-ttu-id="cfa76-112">レポート</span><span class="sxs-lookup"><span data-stu-id="cfa76-112">Reports</span></span>

### <span data-ttu-id="cfa76-113">構成データ</span><span class="sxs-lookup"><span data-stu-id="cfa76-113">Configuration Data</span></span>

<span data-ttu-id="cfa76-114">構成データは、"bitlocker の保護" と呼ばれる構成のベースラインをインストールします。これには、"BitLocker オペレーティングシステムドライブの保護" と "BitLocker 固定データドライブの保護" という2つの構成項目が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-114">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items: “BitLocker Operating System Drive Protection” and “BitLocker Fixed Data Drives Protection.”</span></span> <span data-ttu-id="cfa76-115">構成基準は、MBAM をインストールしたときにも作成されるコレクションに展開されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-115">The configuration baseline is deployed to the collection, which is also created when MBAM is installed.</span></span> <span data-ttu-id="cfa76-116">2つの構成項目は、クライアントコンピューターのコンプライアンスの状態を評価するための基礎となります。</span><span class="sxs-lookup"><span data-stu-id="cfa76-116">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="cfa76-117">この情報は、構成マネージャーでキャプチャ、保存、評価されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-117">This information is captured, stored, and evaluated in Configuration Manager.</span></span> <span data-ttu-id="cfa76-118">構成項目は、オペレーティングシステムドライブ (OSDs) と固定データドライブ (FDDs) のコンプライアンス要件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-118">The configuration items are based on the compliance requirements for operating system drives (OSDs) and Fixed Data Drives (FDDs).</span></span> <span data-ttu-id="cfa76-119">展開されたコンピューターに必要な詳細情報が収集されて、それらのドライブの種類のコンプライアンスが評価されるようになります。</span><span class="sxs-lookup"><span data-stu-id="cfa76-119">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span> <span data-ttu-id="cfa76-120">既定では、構成基準は、コンプライアンスの状態を12時間ごとに評価し、コンプライアンスデータを Configuration Manager に送信します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-120">By default, the configuration baseline evaluates the compliance status every 12 hours and sends the compliance data to Configuration Manager.</span></span>

### <span data-ttu-id="cfa76-121">コレクション</span><span class="sxs-lookup"><span data-stu-id="cfa76-121">Collection</span></span>

<span data-ttu-id="cfa76-122">MBAM サポートされているコンピューターと呼ばれるコレクションを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-122">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="cfa76-123">構成基準は、このコレクション内のクライアントコンピューターを対象としています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-123">The configuration baseline is targeted to client computers that are in this collection.</span></span> <span data-ttu-id="cfa76-124">これは動的なコレクションであり、既定では12時間ごとに実行され、メンバーシップが評価されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-124">This is a dynamic collection that, by default, runs every 12 hours and evaluates membership.</span></span> <span data-ttu-id="cfa76-125">メンバーシップは、次の3つの条件に基づいています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-125">Membership is based on three criteria:</span></span>

-   <span data-ttu-id="cfa76-126">これは、Windows オペレーティングシステムでサポートされているバージョンです。</span><span class="sxs-lookup"><span data-stu-id="cfa76-126">It is a supported version of the Windows operating system.</span></span> <span data-ttu-id="cfa76-127">現時点では、windows To Go が Windows 8 Enterprise で実行されている場合、MBAM は Windows 7 Enterprise と windows 7 Ultimate、windows 8 Enterprise、および Windows To Go のみをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-127">Currently, MBAM supports only Windows 7 Enterprise and Windows 7 Ultimate, Windows 8 Enterprise, and Windows To Go, when Windows To Go is running on Windows 8 Enterprise.</span></span>

-   <span data-ttu-id="cfa76-128">これは物理的なコンピューターです。</span><span class="sxs-lookup"><span data-stu-id="cfa76-128">It is a physical computer.</span></span> <span data-ttu-id="cfa76-129">仮想マシンはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="cfa76-129">Virtual machines are not supported.</span></span>

-   <span data-ttu-id="cfa76-130">トラステッドプラットフォームモジュール (TPM) は使用できます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-130">Trusted Platform Module (TPM) is available.</span></span> <span data-ttu-id="cfa76-131">Windows 7 では、互換性のあるバージョンの TPM 1.2 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="cfa76-131">A compatible version of TPM 1.2 or later is required for Windows 7.</span></span> <span data-ttu-id="cfa76-132">Windows 8 と Windows To Go では、TPM は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="cfa76-132">Windows 8 and Windows To Go do not require a TPM.</span></span>

<span data-ttu-id="cfa76-133">このコレクションは、すべてのコンピューターに対して評価され、MBAM 統合のコンプライアンス評価と報告の基礎となる、互換性のあるコンピューターのサブセットを作成します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-133">The collection is evaluated against all computers and creates the subset of compatible computers that provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span>

### <span data-ttu-id="cfa76-134">レポート</span><span class="sxs-lookup"><span data-stu-id="cfa76-134">Reports</span></span>

<span data-ttu-id="cfa76-135">コンプライアンスを表示するために使用できるレポートは4つあります。</span><span class="sxs-lookup"><span data-stu-id="cfa76-135">There are four reports that you can use to view compliance.</span></span> <span data-ttu-id="cfa76-136">以下のとおりです。</span><span class="sxs-lookup"><span data-stu-id="cfa76-136">They are:</span></span>

-   <span data-ttu-id="cfa76-137">**BitLocker Enterprise コンプライアンスダッシュボード**– IT 管理者は、1つのレポートに関する情報の3つの異なるビューを提供します。コンプライアンスステータスの配布、非準拠–エラーの分布、およびドライブの種類別のコンプライアンスステータスの配布。</span><span class="sxs-lookup"><span data-stu-id="cfa76-137">**BitLocker Enterprise Compliance Dashboard** – gives IT administrators three different views of information on a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="cfa76-138">レポートのドリルダウンオプションを使うと、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-138">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="cfa76-139">**Bitlocker enterprise のコンプライアンスの詳細**– IT 管理者は、組織の bitlocker 暗号化のコンプライアンスの状態に関する情報を表示し、各コンピューターのコンプライアンスの状態を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-139">**BitLocker Enterprise Compliance Details** – lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="cfa76-140">レポートのドリルダウンオプションを使うと、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-140">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="cfa76-141">**BitLocker コンピューターのコンプライアンス**– it 管理者が個々のコンピューターを表示して、特定の状態に準拠している、または準拠していないと報告された理由を確認できます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-141">**BitLocker Computer Compliance** – lets IT administrators view an individual computer and determine why it was reported with a given status of compliant or not compliant.</span></span> <span data-ttu-id="cfa76-142">このレポートには、オペレーティングシステムドライブ (OSD) と固定データドライブ (FDDs) の暗号化状態も表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-142">The report also displays the encryption state of the operating system drives (OSD) and fixed data drives (FDDs).</span></span>

-   <span data-ttu-id="cfa76-143">**BitLocker Enterprise コンプライアンスサマリー** – IT 管理者は、mbam ポリシーを使用して企業のコンプライアンスの状態を表示することができます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-143">**BitLocker Enterprise Compliance Summary** – lets IT administrators view the status of the compliance of the enterprise with MBAM policy.</span></span> <span data-ttu-id="cfa76-144">各コンピューターの状態が評価され、ポリシーに対する企業内のすべてのコンピューターのコンプライアンスの概要がレポートに表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-144">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="cfa76-145">レポートのドリルダウンオプションを使うと、IT 管理者はデータをクリックして、選択した状態に一致するコンピューターの一覧を表示できます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-145">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

## <span data-ttu-id="cfa76-146">構成マネージャーを使用した MBAM の高レベルアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="cfa76-146">High-Level Architecture of MBAM with Configuration Manager</span></span>


<span data-ttu-id="cfa76-147">次の図は、Configuration Manager トポロジを使用した MBAM アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-147">The following image shows the MBAM architecture with the Configuration Manager topology.</span></span> <span data-ttu-id="cfa76-148">この構成では、運用環境で最大 20万 MBAM クライアントをサポートしています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-148">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span>

![mbam アーキテクチャと構成マネージャー](images/mbam2-cmserver.gif)

<span data-ttu-id="cfa76-150">このアーキテクチャのサーバー、データベース、および機能について説明します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-150">A description of the servers, databases, and features of this architecture follows.</span></span> <span data-ttu-id="cfa76-151">アーキテクチャイメージのサーバー機能とデータベースは、インストールすることを勧めるコンピューターまたはサーバーの下に表示されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-151">The server features and databases in the architecture image are listed under the computer or server where we recommend that you install them.</span></span>

-   <span data-ttu-id="cfa76-152">**データベースサーバー** –**回復データベース**、**監査データベース**、および**監査レポート**は、Windows Server とサポートされている SQLServer インスタンスにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-152">**Database Server** – The **Recovery Database**, **Audit Database**, and **Audit Reports** are installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="cfa76-153">回復データベースには、MBAM クライアントコンピューターから収集された回復データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-153">The Recovery database stores recovery data that is collected from MBAM client computers.</span></span> <span data-ttu-id="cfa76-154">監査データベースには、回復データにアクセスしたクライアントコンピューターから収集された監査アクティビティデータが格納されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-154">The Audit Database stores audit activity data that is collected from client computers that have accessed recovery data.</span></span> <span data-ttu-id="cfa76-155">監査レポートは、企業内のクライアントコンピューターのコンプライアンスの状態に関するデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-155">The Audit Reports provide data about the compliance status of client computers in your enterprise.</span></span>

-   <span data-ttu-id="cfa76-156">**Configuration Manager プライマリサイトサーバー** – Configuration manager サーバーには、configuration manager プライマリサイトサーバーにインストールする必要がある、System Center Configuration manager 統合トポロジを含む mbam server インストールが含まれています。</span><span class="sxs-lookup"><span data-stu-id="cfa76-156">**Configuration Manager Primary Site Server** – The Configuration Manager Server contains of the MBAM server installation with the System Center Configuration Manager Integration topology, which must be installed on a Configuration Manager primary site server.</span></span> <span data-ttu-id="cfa76-157">Configuration Manager サーバーは、クライアントコンピューターからハードウェアインベントリ情報を収集し、クライアントコンピューターの BitLocker のコンプライアンスを報告するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-157">The Configuration Manager Server collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span> <span data-ttu-id="cfa76-158">MBAM セットアップサーバーのインストールを実行すると、コレクションと構成データが Configuration Manager プライマリサイトサーバーにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-158">When you run the MBAM Setup server installation, a collection and the configuration data are installed on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="cfa76-159">**管理と監視サーバー** -**管理および監視サーバー**は Windows サーバーにインストールされ、管理と監視の web サイトと監視 web サービスで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-159">**Administration and Monitoring Server** - The **Administration and Monitoring Server** is installed on a Windows server and consists of the Administration and Monitoring website and the monitoring web services.</span></span> <span data-ttu-id="cfa76-160">管理と監視の web サイトは、アクティビティの監査や回復データ (BitLocker 回復キーなど) へのアクセスに使用されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-160">The Administration and Monitoring website is used to audit activity and to access recovery data (for example, BitLocker recovery keys).</span></span> <span data-ttu-id="cfa76-161">**セルフサービスポータル**は、管理/監視サーバーにもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-161">The **Self-Service Portal** is also installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="cfa76-162">ポータルを使用すると、クライアントコンピューターのエンドユーザーは、自分の BitLocker パスワードを紛失または忘れた場合に、回復キーを取得するために個別に web サイトにログオンできます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-162">The Portal enables end users on client computers to independently log onto a website to get a recovery key if they lose or forget their BitLocker password.</span></span> <span data-ttu-id="cfa76-163">監査レポートは、管理/監視サーバーにもインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-163">The Audit reports are also installed on the Administration and Monitoring Server.</span></span>

-   <span data-ttu-id="cfa76-164">**管理ワークステーション**-**ポリシーテンプレート**は、BitLocker ドライブ暗号化の mbam 実装設定を定義するグループポリシーオブジェクトで構成されます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-164">**Management Workstation** - The **Policy Template** consists of Group Policy Objects that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="cfa76-165">ポリシーテンプレートは任意のサーバーまたはワークステーションにインストールできますが、一般的には、サポートされている Windows サーバーまたはクライアントコンピューターである管理ワークステーションにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="cfa76-165">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation that is a supported Windows server or client computer.</span></span> <span data-ttu-id="cfa76-166">ワークステーションは専用のコンピュータである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="cfa76-166">The workstation does not have to be a dedicated computer.</span></span>

-   <span data-ttu-id="cfa76-167">**Mbam クライアント**と**Configuration Manager クライアント**コンピューター</span><span class="sxs-lookup"><span data-stu-id="cfa76-167">**MBAM Client** and **Configuration Manager Client** computer</span></span>

    -   <span data-ttu-id="cfa76-168">**Mbam クライアント**は、次のタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-168">The **MBAM Client** performs the following tasks:</span></span>

        -   <span data-ttu-id="cfa76-169">グループポリシーオブジェクトを使用して、企業内のクライアントコンピューターの BitLocker 暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-169">Uses Group Policy Objects to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

        -   <span data-ttu-id="cfa76-170">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブルデータ (USB) ドライブの3つの BitLocker データドライブの種類の回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-170">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

        -   <span data-ttu-id="cfa76-171">クライアントコンピューターに関する回復情報とコンピューターに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="cfa76-171">Collects recovery information and computer information about the client computers.</span></span>

    -   <span data-ttu-id="cfa76-172">**Configuration Manager クライアント**– configuration manager クライアントでは、configuration manager クライアントで、クライアントコンピューターに関するハードウェアの互換性データを収集し、構成マネージャーがコンプライアンス情報を報告できるようにします。</span><span class="sxs-lookup"><span data-stu-id="cfa76-172">**Configuration Manager Client** – The Configuration Manager client enables Configuration Manager to collect hardware compatibility data about the client computers, and enables Configuration Manager to report compliance information.</span></span>

## <span data-ttu-id="cfa76-173">関連トピック</span><span class="sxs-lookup"><span data-stu-id="cfa76-173">Related topics</span></span>


[<span data-ttu-id="cfa76-174">MBAM と Configuration Manager の使用</span><span class="sxs-lookup"><span data-stu-id="cfa76-174">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





