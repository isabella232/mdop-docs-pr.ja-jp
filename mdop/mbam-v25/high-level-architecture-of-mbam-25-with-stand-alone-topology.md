---
title: スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要
description: スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826557"
---
# <span data-ttu-id="8f97e-103">スタンドアロン トポロジを使用した MBAM 2.5 のアーキテクチャ概要</span><span class="sxs-lookup"><span data-stu-id="8f97e-103">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>


<span data-ttu-id="8f97e-104">このトピックでは、構成マネージャー単体のトポロジを使用して、Microsoft BitLocker 管理と監視 (MBAM) を展開するための推奨アーキテクチャについて説明します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Stand-alone topology.</span></span> <span data-ttu-id="8f97e-105">このトポロジでは、MBAM はスタンドアロン製品として展開されています。</span><span class="sxs-lookup"><span data-stu-id="8f97e-105">In this topology, MBAM is deployed as a stand-alone product.</span></span> <span data-ttu-id="8f97e-106">または、Configuration manager の統合トポロジを使用して MBAM を展開することもできます。これは、構成マネージャーとして MBAM を統合します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-106">You can alternatively deploy MBAM with the Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span> <span data-ttu-id="8f97e-107">詳細については、「 [MBAM 2.5 の高レベルアーキテクチャと構成マネージャーの統合トポロジ](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f97e-107">For more information, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="8f97e-108">このトピックで説明しているソフトウェアのサポートされているバージョンの一覧については、「 [Mbam 2.5 でサポートされている構成](mbam-25-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="8f97e-108">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="8f97e-109">**注** テスト環境でのみ、単一サーバーアーキテクチャを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="8f97e-109">**Note** We recommend you use a single-server architecture in test environments only.</span></span>

 

## <span data-ttu-id="8f97e-110">推奨されるサーバー数とクライアント数</span><span class="sxs-lookup"><span data-stu-id="8f97e-110">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="8f97e-111">運用環境での推奨されるサーバー数とサポートされているクライアント数は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="8f97e-111">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8f97e-112">運用環境での推奨アーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8f97e-112">Recommended architecture in a production environment</span></span></th>
<th align="left"><span data-ttu-id="8f97e-113">詳細</span><span class="sxs-lookup"><span data-stu-id="8f97e-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8f97e-114">サーバーとその他のコンピューターの数</span><span class="sxs-lookup"><span data-stu-id="8f97e-114">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f97e-115">2つのサーバー</span><span class="sxs-lookup"><span data-stu-id="8f97e-115">Two servers</span></span></p>
<p><span data-ttu-id="8f97e-116">1つのワークステーション</span><span class="sxs-lookup"><span data-stu-id="8f97e-116">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8f97e-117">サポートされているクライアントコンピューターの数</span><span class="sxs-lookup"><span data-stu-id="8f97e-117">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="8f97e-118">50万</span><span class="sxs-lookup"><span data-stu-id="8f97e-118">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="8f97e-119">単体のトポロジを備えた、お勧めの MBAM 高レベルのアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="8f97e-119">Recommended MBAM high-level architecture with the Stand-alone topology</span></span>


<span data-ttu-id="8f97e-120">次の図と表は、スタンドアロントポロジでの MBAM の推奨される高レベルの 2 server アーキテクチャを示しています。</span><span class="sxs-lookup"><span data-stu-id="8f97e-120">The following diagram and table describe the recommended high-level, two-server architecture for MBAM with the Stand-alone topology.</span></span> <span data-ttu-id="8f97e-121">MBAM 複数フォレスト展開には、一方向または双方向の信頼が必要です。</span><span class="sxs-lookup"><span data-stu-id="8f97e-121">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="8f97e-122">一方向の信頼には、サーバーのドメインがクライアントドメインを信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f97e-122">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2](images/mbam2-5-2servers.png)

<span data-ttu-id="8f97e-124">このサーバーの説明データベースサーバーで構成するサーバー機能</span><span class="sxs-lookup"><span data-stu-id="8f97e-124">Server Features to configure on this server Description Database server</span></span>

<span data-ttu-id="8f97e-125">コンプライアンスと監査データベース</span><span class="sxs-lookup"><span data-stu-id="8f97e-125">Compliance and Audit Database</span></span>

<span data-ttu-id="8f97e-126">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="8f97e-126">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="8f97e-127">**コンプライアンスと監査データベース**は、主に SQL Server Reporting Services がホストするレポートに使用されるコンプライアンスデータを格納します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-127">The **Compliance and Audit Database** stores compliance data, which is used primarily for reports that SQL Server Reporting Services hosts.</span></span>

<span data-ttu-id="8f97e-128">回復用データベース</span><span class="sxs-lookup"><span data-stu-id="8f97e-128">Recovery Database</span></span>

<span data-ttu-id="8f97e-129">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="8f97e-129">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="8f97e-130">**回復データベース**には、mbam クライアントコンピューターから収集された回復データが格納されます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-130">The **Recovery Database** stores recovery data that is collected from MBAM client computers.</span></span>

<span data-ttu-id="8f97e-131">レポート</span><span class="sxs-lookup"><span data-stu-id="8f97e-131">Reports</span></span>

<span data-ttu-id="8f97e-132">この機能は、Windows Server とサポートされている SQL Server インスタンスを実行しているサーバーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="8f97e-132">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="8f97e-133">**レポート**は、企業内のクライアントコンピューターに関する回復監査およびコンプライアンスステータスのデータを提供します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-133">The **Reports** provide recovery audit and compliance status data about the client computers in your enterprise.</span></span> <span data-ttu-id="8f97e-134">管理と監視の Web サイトから、または SQL Server Reporting Services から直接レポートにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-134">You can access the reports from the Administration and Monitoring Website or directly from SQL Server Reporting Services.</span></span>

<span data-ttu-id="8f97e-135">管理と監視サーバー</span><span class="sxs-lookup"><span data-stu-id="8f97e-135">Administration and Monitoring Server</span></span>

<span data-ttu-id="8f97e-136">管理と監視の Web サイト</span><span class="sxs-lookup"><span data-stu-id="8f97e-136">Administration and Monitoring Website</span></span>

<span data-ttu-id="8f97e-137">この機能は、Windows Server が実行されているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-137">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="8f97e-138">**管理と監視の Web サイト**を使用して、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="8f97e-138">The **Administration and Monitoring Website** is used to:</span></span>

-   <span data-ttu-id="8f97e-139">ロックアウトされている場合、エンドユーザーが自分のコンピューターにアクセスできるようにします。(Web サイトのこの領域は、一般にヘルプデスクと呼ばれます)。</span><span class="sxs-lookup"><span data-stu-id="8f97e-139">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="8f97e-140">クライアントコンピューターのコンプライアンス状態と回復アクティビティを表示するレポートを表示します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-140">View reports that show compliance status and recovery activity for client computers.</span></span>

<span data-ttu-id="8f97e-141">セルフサービスポータル</span><span class="sxs-lookup"><span data-stu-id="8f97e-141">Self-Service Portal</span></span>

<span data-ttu-id="8f97e-142">この機能は、Windows Server が実行されているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-142">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="8f97e-143">**セルフサービスポータル**は、クライアントコンピューターのエンドユーザーが、自分の BitLocker パスワードを紛失または忘れるということを確認するために、個別に web サイトにログオンして回復キーを取得できるようにする web サイトです。</span><span class="sxs-lookup"><span data-stu-id="8f97e-143">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

<span data-ttu-id="8f97e-144">この web サイトの web サービスを監視する</span><span class="sxs-lookup"><span data-stu-id="8f97e-144">Monitoring web services for this website</span></span>

<span data-ttu-id="8f97e-145">この機能は、Windows Server が実行されているコンピューターで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-145">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="8f97e-146">この**監視 web サービス**は、Mbam クライアントと web サイトでデータベースと通信するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="8f97e-146">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

<span data-ttu-id="8f97e-147">**重要** MBAM web サイトは、回復データベースと直接通信しているため、監視 Web サービスは Microsoft BitLocker の管理と監視 (MBAM) 2.5 SP1 では利用できなくなりました。</span><span class="sxs-lookup"><span data-stu-id="8f97e-147">**Important** The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span>

 

<span data-ttu-id="8f97e-148">管理ワークステーション</span><span class="sxs-lookup"><span data-stu-id="8f97e-148">Management workstation</span></span>

<span data-ttu-id="8f97e-149">MBAM グループポリシーテンプレート</span><span class="sxs-lookup"><span data-stu-id="8f97e-149">MBAM Group Policy Templates</span></span>

-   <span data-ttu-id="8f97e-150">MBAM グループポリシーテンプレートは、BitLocker ドライブ暗号化を管理するための、MBAM の実装設定を定義するグループポリシー設定です。</span><span class="sxs-lookup"><span data-stu-id="8f97e-150">The MBAM Group Policy Templates are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker Drive Encryption.</span></span>

-   <span data-ttu-id="8f97e-151">MBAM を実行する前に、グループポリシーテンプレートをダウンロードして、 [MDOP グループポリシー (admx) テンプレートを取得](https://go.microsoft.com/fwlink/p/?LinkId=393941)し、サポートされている windows サーバーまたは windows オペレーティングシステムを実行しているサーバーまたはワークステーションにコピーする必要があります。</span><span class="sxs-lookup"><span data-stu-id="8f97e-151">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

-   <span data-ttu-id="8f97e-152">ワークステーションは専用のコンピュータである必要はありません。</span><span class="sxs-lookup"><span data-stu-id="8f97e-152">The workstation does not have to be a dedicated computer.</span></span>

<span data-ttu-id="8f97e-153">MBAM クライアントと Configuration Manager クライアントコンピューター</span><span class="sxs-lookup"><span data-stu-id="8f97e-153">MBAM Client and Configuration Manager client computer</span></span>

<span data-ttu-id="8f97e-154">MBAM クライアントソフトウェア</span><span class="sxs-lookup"><span data-stu-id="8f97e-154">MBAM Client software</span></span>

<span data-ttu-id="8f97e-155">MBAM クライアント:</span><span class="sxs-lookup"><span data-stu-id="8f97e-155">The MBAM Client:</span></span>

-   <span data-ttu-id="8f97e-156">グループポリシーオブジェクトを使用して、企業内のクライアントコンピューターで BitLocker ドライブ暗号化を適用します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-156">Uses Group Policy Objects to enforce BitLocker Drive Encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="8f97e-157">オペレーティングシステムドライブ、固定データドライブ、およびリムーバブル (USB) データドライブの3種類のデータドライブの Bitlocker 回復キーを収集します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-157">Collects the Bitlocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="8f97e-158">クライアントコンピューターに関する回復情報とコンピューターに関する情報を収集します。</span><span class="sxs-lookup"><span data-stu-id="8f97e-158">Collects recovery information and computer information about the client computers.</span></span>



## <span data-ttu-id="8f97e-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8f97e-159">Related topics</span></span>


[<span data-ttu-id="8f97e-160">MBAM 2.5 をお使いになる前に</span><span class="sxs-lookup"><span data-stu-id="8f97e-160">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="8f97e-161">Configuration Manager 統合トポロジを使用した MBAM 2.5 のアーキテクチャ概要</span><span class="sxs-lookup"><span data-stu-id="8f97e-161">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span>](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[<span data-ttu-id="8f97e-162">MBAM 2.5 展開の機能の図</span><span class="sxs-lookup"><span data-stu-id="8f97e-162">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

## <span data-ttu-id="8f97e-163">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="8f97e-163">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="8f97e-164">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="8f97e-164">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="8f97e-165">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="8f97e-165">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





