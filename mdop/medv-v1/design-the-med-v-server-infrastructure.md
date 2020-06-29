---
title: MED-V サーバー インフラストラクチャを設計する
description: MED-V サーバー インフラストラクチャを設計する
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824184"
---
# <span data-ttu-id="0a71b-103">MED-V サーバー インフラストラクチャを設計する</span><span class="sxs-lookup"><span data-stu-id="0a71b-103">Design the MED-V Server Infrastructure</span></span>


<span data-ttu-id="0a71b-104">このトピックでは、各 MED-V インスタンスのサーバーインフラストラクチャを設計します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-104">In this topic, you will design the server infrastructure for each MED-V instance.</span></span> <span data-ttu-id="0a71b-105">これには、SQL Server インスタンスが MED-V サーバーに存在するか、リモートサーバー上にあるかと、SQL Server データベースのサイズが指定されているかを確認することが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-105">This includes determining whether the SQL Server instance will exist on the MED-V server or on a remote server, as well as the size of the SQL Server database.</span></span> <span data-ttu-id="0a71b-106">管理コンソールの場所も決定されます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-106">You will also determine the location of the management console.</span></span>

## <span data-ttu-id="0a71b-107">各 MED-V インスタンス用にサーバーを設計して配置する</span><span class="sxs-lookup"><span data-stu-id="0a71b-107">Design and Place the Server for Each MED-V Instance</span></span>


<span data-ttu-id="0a71b-108">MED-V サーバーは、ポリシーを実装し、クライアントに関する状態と履歴データを格納します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-108">The MED-V server implements policies and stores state and history data about its clients.</span></span>

### <span data-ttu-id="0a71b-109">フォームファクター</span><span class="sxs-lookup"><span data-stu-id="0a71b-109">Form Factor</span></span>

<span data-ttu-id="0a71b-110">MED-V では、2 GB の RAM で 2.8 GHz デュアルコア CPU サーバーを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0a71b-110">MED-V recommends using a 2.8-GHz dual core CPU server with 2GB of RAM.</span></span> <span data-ttu-id="0a71b-111">この推奨事項は、MED-V サーバーが専用のコンピューターで実行されることを前提としており、SQL Server と MED-V の管理コンソールが別々のコンピューターで実行されることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0a71b-111">This recommendation is based on the assumption that the MED-V server will run on a dedicated machine and that SQL Server and the MED-V management console will run on separate machines.</span></span>

<span data-ttu-id="0a71b-112">この作業負荷の場合、MED-V サーバーは比較的負荷の低い状態にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-112">Given this workload, the MED-V server should be relatively lightly loaded.</span></span> <span data-ttu-id="0a71b-113">サーバーフォームファクターに具体的なアーキテクチャガイダンスがない場合は、MED-V 勧告を使用してサーバーを設計し、組織の標準のフォームファクターと一致するメモリを使用します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-113">In the absence of specific architectural guidance on the server form factor, design the server using the MED-V recommendation, with memory that matches the organization’s standard form factor.</span></span> <span data-ttu-id="0a71b-114">MED-V サーバーは、Windows Server2008 Hyper-v の仮想マシン (VM) で実行できます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-114">The MED-V server can be run on a virtual machine (VM) on Windows Server2008 Hyper-V.</span></span> <span data-ttu-id="0a71b-115">VM を使用する場合は、物理マシンに対して指定されているものと同等の CPU とメモリリソースにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-115">If a VM will be used, ensure that it has access to CPU and memory resources equivalent to those specified for a physical machine.</span></span>

<span data-ttu-id="0a71b-116">Med-v サーバーが必要とするディスク容量は、MED-V ワークスペース構成ファイルを保存するのに十分なものである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-116">The disk capacity the MED-V server requires must be sufficient to store the MED-V workspace configuration files.</span></span> <span data-ttu-id="0a71b-117">MED-V ワークスペースでは、1つ以上のユーザーに対して1つの VM と1つのポリシーのみを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-117">A MED-V workspace can only use one VM, and one policy, for one or more users.</span></span> <span data-ttu-id="0a71b-118">したがって、保存する必要がある MED-V ワークスペースの数は、同じ VM のユーザーごとに異なるポリシーが必要となる程度、および使用される Vm の数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-118">Therefore, the number of MED-V workspaces that must be stored depends on the degree to which different policies are required for different users of the same VM, as well as the number of VMs that will be used.</span></span> <span data-ttu-id="0a71b-119">MED-V ワークスペースの XML ファイルは、標準の MED-V ワークスペースで約30KB のサイズになります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-119">The MED-V workspace XML files are around 30KB in size for a typical MED-V workspace.</span></span> <span data-ttu-id="0a71b-120">必要なディスク容量を判断するには、MED-V サーバーが格納する MED-V ワークスペースの数を 30 KB にします。</span><span class="sxs-lookup"><span data-stu-id="0a71b-120">To determine the required disk capacity, multiply 30 KB by the number of MED-V workspaces that the MED-V server will store.</span></span>

<span data-ttu-id="0a71b-121">MED-V サーバーの最も重要なネットワーク接続はクライアントへのリンクです。そのため、利用可能な帯域幅の最も高いネットワーク上の場所にサーバーを配置します。そのため、クライアントへの最も信頼性の高いリンクを提供します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-121">The MED-V server’s most important network connections are the links to its clients, therefore place the server in a network location that provides the most available bandwidth and the most robust links to its clients.</span></span>

### <span data-ttu-id="0a71b-122">フォールトトレランス</span><span class="sxs-lookup"><span data-stu-id="0a71b-122">Fault Tolerance</span></span>

<span data-ttu-id="0a71b-123">有効な MED-V サーバーは、MED-V インスタンスには1つしか使用できません。また、MED-V には、サーバーを Microsoft Cluster Server (MSCS) クラスターに配置してフォールトトレランスを提供するための標準機能は含まれていません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-123">There can only be one active MED-V server in a MED-V instance, and MED-V does not include standard capabilities to place the server in a Microsoft Cluster Server (MSCS) cluster to provide fault tolerance.</span></span> <span data-ttu-id="0a71b-124">パッシブバックアップサーバーを手動で構成することができます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-124">A passive backup server can be manually configured.</span></span>

<span data-ttu-id="0a71b-125">パッシブバックアップサーバーを MED-V インスタンス用に手動で構成する必要があるかどうかを判断するには、オフラインモードでの MED-V イメージの使用をユーザーに許可するかどうかを決定します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-125">To decide whether a passive backup server should be manually configured for the MED-V instance, determine whether users will be permitted to use the MED-V images in offline mode.</span></span> <span data-ttu-id="0a71b-126">オフラインモードの詳細について[は、「ドメインユーザーまたはグループを構成する方法](how-to-configure-a-domain-user-or-groupmedvv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a71b-126">For information on offline mode, see [How to Configure a Domain User or Group](how-to-configure-a-domain-user-or-groupmedvv2.md).</span></span> <span data-ttu-id="0a71b-127">ユーザーがオフラインで作業することを許可されていない場合は、med-v ワークスペースがクライアントで既に開始されている場合でも、MED-V サーバーの障害が発生した場合でも操作を続行することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-127">If users are not allowed to work offline, they will be unable to continue working in the event of a MED-V server failure, even if the MED-V workspace has already been started on the client.</span></span> <span data-ttu-id="0a71b-128">各 MED-V ワークスペースに対してオフライン作業が許可されている場合は、認証を必要とする前に、クライアントがオフラインで作業できる期間を決定します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-128">If offline work is permitted, for each MED-V workspace, determine how long the client is allowed to work offline before it must authenticate.</span></span> <span data-ttu-id="0a71b-129">この値は、サーバーを利用できない最大時間です。</span><span class="sxs-lookup"><span data-stu-id="0a71b-129">This is the maximum amount of time that the server can be unavailable.</span></span>

## <span data-ttu-id="0a71b-130">SQL Server データベースの設計と配置</span><span class="sxs-lookup"><span data-stu-id="0a71b-130">Design and Place the SQL Server Database</span></span>


<span data-ttu-id="0a71b-131">MED-V サーバーでは、SQL Server データベースを使ってクライアントの状態とイベントを保存します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-131">The MED-V server uses the SQL Server database to store client status and events.</span></span> <span data-ttu-id="0a71b-132">SQL Server データベースは、MED-V サーバーと同じコンピューター上にインストールすることも、SQL Server を実行している別のサーバー上に配置することもできます。これは、必要に応じてリモートでもかまいません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-132">You can install the SQL Server database on the same machine as the MED-V server or you can place it on a separate server running SQL Server, which can optionally be remote.</span></span> <span data-ttu-id="0a71b-133">データベースを他の MED-V インスタンスと共有することができます。この場合、これらのインスタンスからのイベントと警告は同じデータベースに格納され、レポートにはすべてのインスタンスからのイベントが含まれます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-133">You can share the database with other MED-V instances, in which case events and alerts from those instances will be stored in the same database, and reports will include events from all instances.</span></span> <span data-ttu-id="0a71b-134">既存の SQL Server インスタンスにデータベースをインストールして、他の MED-V サーバーのデータベースを同じインスタンスに配置することができます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-134">You can install the database in an existing SQL Server instance, and the databases of other MED-V servers can reside in that same instance.</span></span>

<span data-ttu-id="0a71b-135">MED-V サーバーのリモートの場所にデータベースサーバーを配置する場合、十分な帯域幅がないネットワークリンク間では、レポートが本体に読み込まれず、クライアントからの最新データが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-135">If you place the database server in a location that is remote from the MED-V server, across networks links that do not have sufficient bandwidth available, reports may be slow to load in the console and may not display the latest data from clients.</span></span> <span data-ttu-id="0a71b-136">「[プロジェクトの範囲を定義](define-the-project-scope.md)する」で決定した組織のサービスレベルの要件を参照し、その情報を使用して SQL Server データベースを配置する場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-136">Refer to the organization service level expectations that you determined in [Define the Project Scope](define-the-project-scope.md) and use that information to decide where to place the SQL Server database.</span></span>

### <span data-ttu-id="0a71b-137">フォームファクター</span><span class="sxs-lookup"><span data-stu-id="0a71b-137">Form Factor</span></span>

<span data-ttu-id="0a71b-138">SQL Server を MED-V と同じサーバーで実行し、SQL Server がそのサーバーのデータを保存するためだけに使用される場合は、MED-V の推奨事項から始めて、SQL Server のロード用のリソースを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-138">If you will run SQL Server on the same server as MED-V, and if SQL Server will only be used to store data for that server, start with the MED-V recommendation and add resources for the SQL Server load.</span></span> <span data-ttu-id="0a71b-139">SQL Server が複数の MED-V インスタンスからイベントとアラートを格納する場合、サーバーフォームファクターのスケールアップの詳細については、「[インフラストラクチャの計画と設計 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)ガイド (http://go.microsoft.com/fwlink/?LinkId=163302)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a71b-139">If SQL Server will store events and alerts from more than one MED-V instance, for information on how to scale up the server form factor, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (http:// go.microsoft.com/fwlink/?LinkId=163302).</span></span>

<span data-ttu-id="0a71b-140">データベースのサイズは、データベースに保存されるクライアントイベントの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-140">The size of the database depends on the number of client events that the database will store.</span></span> <span data-ttu-id="0a71b-141">イベントは、MED-V ワークスペースが開始された場合や、MED-V ワークスペースにエラーが発生した場合など、クライアントの通常の操作によって作成されます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-141">Events are created by normal operation of the client, such as when a MED-V workspace is started, or when there is an error in the MED-V workspace.</span></span> <span data-ttu-id="0a71b-142">クライアントがイベントを送信する既定の間隔は1分です。</span><span class="sxs-lookup"><span data-stu-id="0a71b-142">The default interval at which the client sends events is 1 minute.</span></span>

<span data-ttu-id="0a71b-143">データベースのサイズを見積もるには、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-143">To estimate the size of the database, determine the following:</span></span>

-   <span data-ttu-id="0a71b-144">MED-V インスタンスのクライアント数。</span><span class="sxs-lookup"><span data-stu-id="0a71b-144">Number of clients in the MED-V instance.</span></span> <span data-ttu-id="0a71b-145">最大値は5000です。</span><span class="sxs-lookup"><span data-stu-id="0a71b-145">The maximum is 5,000.</span></span>

-   <span data-ttu-id="0a71b-146">一般的なイベント到着率。</span><span class="sxs-lookup"><span data-stu-id="0a71b-146">Typical event arrival rate.</span></span> <span data-ttu-id="0a71b-147">この率はクライアントの使用の動作によって異なりますが、クライアントごとの1日あたり約 15 ~ 20 イベントになります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-147">This rate depends on client usage behavior but is approximately 15 to 20 events per day per client.</span></span>

-   <span data-ttu-id="0a71b-148">イベントサイズ。</span><span class="sxs-lookup"><span data-stu-id="0a71b-148">Event size.</span></span> <span data-ttu-id="0a71b-149">通常、サイズは約200バイトです。</span><span class="sxs-lookup"><span data-stu-id="0a71b-149">The size is typically around 200 bytes.</span></span>

-   <span data-ttu-id="0a71b-150">容量。</span><span class="sxs-lookup"><span data-stu-id="0a71b-150">Storage amount.</span></span> <span data-ttu-id="0a71b-151">イベントが保存される日数。</span><span class="sxs-lookup"><span data-stu-id="0a71b-151">The number of days for which events will be stored.</span></span>

<span data-ttu-id="0a71b-152">これらの値を組み合わせて、必要なデータ記憶域のサイズ (バイト単位) を計算し、次の項目を考慮して安全係数を追加します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-152">Multiply these values together to calculate the size of the required data storage in bytes, and then add a safety factor to account for the following:</span></span>

-   <span data-ttu-id="0a71b-153">このエラーは、短時間でクライアントから大量のイベントを作成する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-153">Errors, which could create a large number of events from a client in a short period of time.</span></span>

-   <span data-ttu-id="0a71b-154">データベーステーブルと組織用スペース。</span><span class="sxs-lookup"><span data-stu-id="0a71b-154">Database table and organizational space.</span></span>

<span data-ttu-id="0a71b-155">インフラストラクチャ最適化の毎秒 (IOPs) 要件を推定するには、上記の値を使って、通常のイベント着信率をインスタンスのクライアント数で乗算します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-155">To approximate the infrastructure optimization per second (IOPs) requirement, use the above values, multiplying the typical event arrival rate by the number of clients in the instance.</span></span> <span data-ttu-id="0a71b-156">これにより、1日に書き込むことができるレコード数が返されます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-156">This yields the number of records that can be written per day.</span></span> <span data-ttu-id="0a71b-157">この数値を86400で除算して、1秒あたりに書き込まれたレコード数を導出します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-157">Divide that number by 86,400 to derive the number of records written per second.</span></span> <span data-ttu-id="0a71b-158">1つのインフラストラクチャ最適化 (IO) 操作で書き込み操作を equated できる場合、この数値は、必要な書き込み IOPs です。</span><span class="sxs-lookup"><span data-stu-id="0a71b-158">If a write operations can be equated with a single infrastructure optimization (IO) operation, this number is the write IOPs required.</span></span> <span data-ttu-id="0a71b-159">レポートアクティビティ用のバッファーを追加します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-159">Add a buffer to that for reporting activity.</span></span> <span data-ttu-id="0a71b-160">この場合、そのインスタンスで使用されている本体の数と、レポートを生成するために使用する頻度によって判断が困難です。</span><span class="sxs-lookup"><span data-stu-id="0a71b-160">This is difficult to determine but depends on the number of consoles in use with the instance and the frequency with which they are used to generate reports.</span></span>

### <span data-ttu-id="0a71b-161">フォールトトレランス</span><span class="sxs-lookup"><span data-stu-id="0a71b-161">Fault Tolerance</span></span>

<span data-ttu-id="0a71b-162">MED-V クライアントを実行しているときに、サーバーが利用できない場合、クライアントでイベントがバックアップされ、管理コンソールではレポートを使用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-162">When MED-V client is running, if the server is unavailable, events will be backed up on the client and reports will be unavailable in the management console.</span></span> <span data-ttu-id="0a71b-163">「[プロジェクトのスコープを定義](define-the-project-scope.md)する」で判断された、フォールトトレラントな SQL Server インフラストラクチャの設計が必要かどうかを決定する、組織のサービスレベルについて参照してください。</span><span class="sxs-lookup"><span data-stu-id="0a71b-163">Refer to the organization’s service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to decide whether the design of a fault-tolerant SQL Server infrastructure is necessary.</span></span>

<span data-ttu-id="0a71b-164">MED-V は、MSCS クラスターで SQL Server を実行するためのサポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-164">MED-V does not provide support for running SQL Server in an MSCS cluster.</span></span> <span data-ttu-id="0a71b-165">ウォームスタンバイを提供し、エラーが発生した場合のデータの損失を防ぐために、SQL Server をログ配布構成に配置できます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-165">In order to provide warm standby and to avoid data loss in the event of a failure, you can place SQL Server in a log shipping configuration.</span></span> <span data-ttu-id="0a71b-166">ログの配布の詳細については、「 [MICROSOFT SQL Server 2008 ガイド () のインフラストラクチャ計画と設計](https://go.microsoft.com/fwlink/?LinkId=163302)」を参照してください https://go.microsoft.com/fwlink/?LinkId=163302) 。</span><span class="sxs-lookup"><span data-stu-id="0a71b-166">For information on log shipping, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (https://go.microsoft.com/fwlink/?LinkId=163302).</span></span>

## <span data-ttu-id="0a71b-167">管理コンソールの設計</span><span class="sxs-lookup"><span data-stu-id="0a71b-167">Design the Management Console</span></span>


<span data-ttu-id="0a71b-168">MED-V 管理コンソールの機能の一部は、MED-V クライアントに配布するためにパックされる前に、Vm をテストすることです。</span><span class="sxs-lookup"><span data-stu-id="0a71b-168">Part of the functionality of the MED-V management console is to test VMs before they are packed for distribution to MED-V clients.</span></span> <span data-ttu-id="0a71b-169">そのため、管理コンソールは、一般的な MED-V クライアントマシンのフォームファクターで可能な限り近いフォームファクターで設計する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0a71b-169">Therefore, the management console should be designed with a form factor that resembles, as closely as possible, the form factor of a typical MED-V client machine.</span></span>

<span data-ttu-id="0a71b-170">管理コンソールアプリケーションは、MED-V クライアントと共にインストールされ、microsoft のサポート技術情報の記事974918で説明されている修正プログラムと共に Microsoft Virtual PC2007 SP1 を使用します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-170">The management console application is installed together with the MED-V client and uses Microsoft Virtual PC2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918.</span></span> <span data-ttu-id="0a71b-171">クライアントオペレーティングシステムを使用する必要があります。med-v 管理コンソールは、MED-V サーバーと同じシステム上で実行することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-171">A client operating system must be used; the MED-V management console cannot run on the same system as the MED-V server.</span></span>

<span data-ttu-id="0a71b-172">管理コンソールを複数の MED-V サーバーインスタンスと共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-172">You cannot share a management console with multiple MED-V server instances.</span></span> <span data-ttu-id="0a71b-173">MED-V サーバーのアドレスは、管理コンソールの MED-V クライアントのインストール中に指定されます。この操作はインストール後に変更できますが、いつでも、管理コンソールは1つの MED-V サーバーでしか動作できません。</span><span class="sxs-lookup"><span data-stu-id="0a71b-173">The address of the MED-V server is specified during the installation of the management console’s MED-V client; this can be changed after installation, but at any time the management console can only work with a single MED-V server.</span></span>

<span data-ttu-id="0a71b-174">複数の管理コンソールは、単一の MED-V サーバーで使うことができます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-174">You can use multiple management consoles with a single MED-V server.</span></span> <span data-ttu-id="0a71b-175">競合を避けるために、ある本体が MED-V ワークスペースに変更を加えたときに、他のコンソールユーザーに通知するメカニズムを利用できます。</span><span class="sxs-lookup"><span data-stu-id="0a71b-175">To avoid conflicts, a mechanism is available that notifies other console users when one console has made changes to a MED-V workspace.</span></span>

<span data-ttu-id="0a71b-176">各 MED-V インスタンスについて、必要な管理コンソールの数と配置場所を決定します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-176">For each MED-V instance, determine how many management consoles will be needed and where they will be placed.</span></span> <span data-ttu-id="0a71b-177">管理コンソールに使用する一般的な MED-V クライアントのフォームファクターを選択します。</span><span class="sxs-lookup"><span data-stu-id="0a71b-177">Select a typical MED-V client form factor to be used for the management console.</span></span>

## <span data-ttu-id="0a71b-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0a71b-178">Related topics</span></span>


[<span data-ttu-id="0a71b-179">MED-V 1.0 SP1 でサポートされる構成</span><span class="sxs-lookup"><span data-stu-id="0a71b-179">MED-V 1.0 SP1 Supported Configurations</span></span>](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[<span data-ttu-id="0a71b-180">クラスター モードの MED-V サーバーの構成</span><span class="sxs-lookup"><span data-stu-id="0a71b-180">Configuring MED-V Server for Cluster Mode</span></span>](configuring-med-v-server-for-cluster-mode.md)

[<span data-ttu-id="0a71b-181">MED-V クライアントと MED-V 管理コンソールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0a71b-181">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="0a71b-182">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="0a71b-182">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





