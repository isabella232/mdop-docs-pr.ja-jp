---
title: MBAM のネットワーク負荷分散を構成する方法
description: MBAM のネットワーク負荷分散を構成する方法
author: dansimp
ms.assetid: df2208c3-352b-4a48-9722-237b0c8cd6a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a04bc74a9dab7bfe18eed8e5a3c1b6ca64d88b5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825514"
---
# <span data-ttu-id="a7401-103">MBAM のネットワーク負荷分散を構成する方法</span><span class="sxs-lookup"><span data-stu-id="a7401-103">How to Configure Network Load Balancing for MBAM</span></span>


<span data-ttu-id="a7401-104">管理と監視サーバー機能をインストールするための前提条件とハードウェアとソフトウェアの要件を満たしていることを確認するには、「 [mbam 1.0 の展開に関する前提条件](mbam-10-deployment-prerequisites.md)と[Mbam 1.0 でサポートさ](mbam-10-supported-configurations.md)れている構成」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7401-104">To verify that you have met the prerequisites and hardware and software requirements to install the Administration and Monitoring Server feature, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="a7401-105">**注** セットアップログファイルを取得するには、 **msiexec**パッケージと **/l** location オプションを使用して、Microsoft BitLocker 管理と監視 (mbam) をインストールする必要があり &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="a7401-105">**Note** To obtain the setup log files, you must install Microsoft BitLocker Administration and Monitoring (MBAM) by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="a7401-106">指定した場所にログファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7401-106">The Log files are created in the location that you specify.</span></span>

<span data-ttu-id="a7401-107">追加のセットアップログファイルは、MBAM をインストールしたユーザーの% temp% フォルダーに作成されます。</span><span class="sxs-lookup"><span data-stu-id="a7401-107">Additional setup log files are created in the %temp% folder of the user who installs MBAM.</span></span>

 

<span data-ttu-id="a7401-108">管理と監視サーバー機能のネットワーク負荷分散 (NLB) クラスターは、MBAM でスケーラビリティを提供します。また、55000 MBAM クライアントコンピューターよりも多くの機能をサポートしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-108">The Network Load Balancing (NLB) clusters for the Administration and Monitoring Server feature provides scalability in MBAM and it should support more than 55,000 MBAM client computers.</span></span>

<span data-ttu-id="a7401-109">**注** Windows Server ネットワーク負荷分散は、1つのサーバークラスターに構成されている一連のサーバー間でクライアント要求を配布します。</span><span class="sxs-lookup"><span data-stu-id="a7401-109">**Note** Windows Server Network Load Balancing distributes client requests across a set of servers that are configured into a single server cluster.</span></span> <span data-ttu-id="a7401-110">クラスター内の各サーバー (ホスト) にネットワーク負荷分散がインストールされると、クラスターはクライアント要求に対して仮想 IP アドレスまたは完全修飾ドメイン名 (FQDN) を提示します。</span><span class="sxs-lookup"><span data-stu-id="a7401-110">When Network Load Balancing is installed on each of the servers (hosts) in a cluster, the cluster presents a virtual IP address or fully qualified domain name (FQDN) to client requests.</span></span> <span data-ttu-id="a7401-111">最初のクライアント要求は、クラスター内のすべてのホストに送信されますが、要求を受け入れて処理するホストは1つだけです。</span><span class="sxs-lookup"><span data-stu-id="a7401-111">The initial client requests go to all the hosts in the cluster, but only one host accepts and handles the request.</span></span>

<span data-ttu-id="a7401-112">NLB クラスターに参加するすべてのコンピューターには、次の要件があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-112">All computers that will be part of a NLB cluster have the following requirements:</span></span>

-   <span data-ttu-id="a7401-113">NLB クラスター内のすべてのコンピューターは、同じドメイン内に存在する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-113">All computers in the NLB cluster must be in the same domain.</span></span>

-   <span data-ttu-id="a7401-114">NLB クラスターの各コンピューターでは、静的な IP アドレスを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-114">Each computer in the NLB cluster must use a static IP address.</span></span>

-   <span data-ttu-id="a7401-115">NLB クラスターの各コンピューターでは、ネットワーク負荷分散を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-115">Each computer in the NLB cluster must have Network Load Balancing enabled.</span></span>

-   <span data-ttu-id="a7401-116">NLB クラスターには静的 IP アドレスが必要です。また、ホストレコードは、ドメインネームシステム (DNS) で手動で作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-116">The NLB cluster requires a static IP address, and a host record must be manually created in the domain name system (DNS).</span></span>

 

## <span data-ttu-id="a7401-117">MBAM 管理および監視サーバーのネットワーク負荷分散の構成</span><span class="sxs-lookup"><span data-stu-id="a7401-117">Configuring Network Load Balancing for MBAM Administration and Monitoring Servers</span></span>


<span data-ttu-id="a7401-118">次の手順では、2つの MBAM 管理および監視サーバーの NLB クラスター仮想名と IP アドレスを構成する方法、および NLB クラスターを使用するために MBAM クライアントを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a7401-118">The following steps describe how to configure an NLB cluster virtual name and IP address for two MBAM Administration and Monitoring servers, and how to configure MBAM Clients to use the NLB Cluster.</span></span>

<span data-ttu-id="a7401-119">このトピックで説明した手順を開始する前に、MBAM サーバー機能のインストールと NLB のクラスター構成の両方の前提条件を満たしている2つの別個のサーバーコンピューターで同じ IIS ポートバインドを使用して、MBAM 管理および監視サーバー機能が正常にインストールされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-119">Before you begin the procedures described in this topic, you must have the MBAM Administration and Monitoring Server feature successfully installed by using the same IIS port binding on two separate server computers that meet the prerequisites for both MBAM Server feature installation and NLB Cluster configuration.</span></span>

<span data-ttu-id="a7401-120">**注** このトピックでは、ネットワーク負荷分散マネージャーを使用して NLB クラスターを作成する基本的なプロセスについて説明します。</span><span class="sxs-lookup"><span data-stu-id="a7401-120">**Note** This topic describes the basic process of using Network Load Balancing Manager to create an NLB Cluster.</span></span> <span data-ttu-id="a7401-121">NLB クラスターの一部として Windows Server を構成するための正確な手順は、使用中の Windows Server のバージョンによって異なります。</span><span class="sxs-lookup"><span data-stu-id="a7401-121">The exact steps to configure a Windows Server as part of an NLB cluster depend on the Windows Server version in use..</span></span> <span data-ttu-id="a7401-122">WindowsServer2008 で NLBs を作成する方法の詳細については、「Windows Server2008 TechNet ライブラリでの[ネットワーク負荷分散クラスターの作成](https://go.microsoft.com/fwlink/?LinkId=197176)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7401-122">For more information about how to create NLBs on WindowsServer2008, see [Creating Network Load Balancing Clusters](https://go.microsoft.com/fwlink/?LinkId=197176) in the Windows Server2008 TechNet library.</span></span>

 

**<span data-ttu-id="a7401-123">2つの MBAM 管理および監視サーバーの NLB クラスター仮想名と IP アドレスを構成するには</span><span class="sxs-lookup"><span data-stu-id="a7401-123">To configure an NLB Cluster Virtual Name and IP address for two MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="a7401-124">[**スタート**] をクリックし、[**すべてのプログラム**]、[**管理ツール**]、[**ネットワーク負荷分散マネージャー**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-124">Click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Network Load Balancing Manager**.</span></span>

    <span data-ttu-id="a7401-125">**注** NLB マネージャーが存在しない場合は、WindowsServer 機能としてインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a7401-125">**Note** If the NLB Manager is not present, you can install it as a WindowsServer feature.</span></span> <span data-ttu-id="a7401-126">この機能は、NLB クラスターに構成する必要がある場合は、MBAM 管理と監視サーバーの両方にインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-126">You must install this feature on both MBAM Administration and Monitoring servers if you want to configure it into the NLB cluster.</span></span>

     

2.  <span data-ttu-id="a7401-127">メニューバーで、[**クラスター**] をクリックし、[**新規作成**] をクリックして [**クラスターのパラメーター** ] ダイアログボックスを開きます。</span><span class="sxs-lookup"><span data-stu-id="a7401-127">On the menu bar, click **Cluster**, and then click **New** to open the **Cluster Parameters** dialog box.</span></span>

3.  <span data-ttu-id="a7401-128">[**クラスターのパラメーター** ] ダイアログボックスで、NLB クラスターの IP 構成の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="a7401-128">In the **Cluster Parameters** dialog box, enter the information for the NLB cluster IP configuration:</span></span>

    -   <span data-ttu-id="a7401-129">**IP アドレス:** DNS に登録されている NLB クラスター IP アドレス</span><span class="sxs-lookup"><span data-stu-id="a7401-129">**IP address:** NLB cluster IP address registered in DNS</span></span>

    -   <span data-ttu-id="a7401-130">**サブネットマスク:** DNS に登録されている NLB クラスター IP アドレスサブネットマスク</span><span class="sxs-lookup"><span data-stu-id="a7401-130">**Subnet mask:** NLB cluster IP address subnet mask registered in DNS</span></span>

    -   <span data-ttu-id="a7401-131">**完全なインターネット名:** DNS に登録されている NLB クラスター名の FQDN</span><span class="sxs-lookup"><span data-stu-id="a7401-131">**Full Internet name:** FQDN of NLB cluster name registered in DNS</span></span>

4.  <span data-ttu-id="a7401-132">[**クラスターの操作モード**] で [**ユニキャスト**] が選択されていることを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-132">Ensure that **Unicast** is selected in **Cluster operation mode**, and then click **Next**.</span></span>

5.  <span data-ttu-id="a7401-133">[**クラスターの IP アドレス**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-133">On the **Cluster IP Addresses** page, click **Next**.</span></span>

6.  <span data-ttu-id="a7401-134">[**ポートの規則**] ページで、[**編集**] をクリックして、nlb クラスターが応答するポートを定義し、サイトに対して定義されているように、クライアント間のシステム通信に使用するポートを設定するか、[**次へ**] をクリックして、すべての tcp/ip ポートに対して nlb クラスター IP アドレスを有効にします。</span><span class="sxs-lookup"><span data-stu-id="a7401-134">On the **Port Rules** page, click **Edit** to define the ports that the NLB cluster will respond to and configure the ports that are used for client-to-site system communication as they are defined for the site, or click **Next** to enable the NLB cluster IP address to respond to all TCP/IP ports.</span></span>

    <span data-ttu-id="a7401-135">**注** **アフィニティ**が**Single**に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7401-135">**Note** Ensure that **Affinity** is set to **Single**.</span></span>

     

7.  <span data-ttu-id="a7401-136">[**接続**] ページで、Mbam 管理と監視サーバーインスタンスのホスト名を**ホスト**の NLB クラスターの一部として入力し、[**接続**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-136">On the **Connect** page, enter an MBAM Administration and Monitoring server instance host name that will be part of the NLB cluster in **Host**, and then click **Connect**.</span></span>

8.  <span data-ttu-id="a7401-137">**新しいクラスターを構成するために使用できるインターフェイス**で、NLB クラスター通信に応答するように構成されるネットワークインターフェイスを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-137">In **Interfaces available for configuring a new cluster**, select the networking interface that will be configured to respond to NLB cluster communication, and then click **Next**.</span></span>

9.  <span data-ttu-id="a7401-138">[ **Host Parameters** ] ページで、[**専用 ip 構成**] 設定によって、適切な NLB クラスターホストの専用ホスト IP 構成が表示されていることを確認します。次に、[ホストの初期状態 **:** ] が [**開始**] になっていることを確認し、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a7401-138">On the **Host Parameters** page, review the information displayed to ensure that the **Dedicated IP configuration** settings display the dedicated host IP configuration for the correct NLB cluster host, check that the Initial host state **Default state:** is **Started**, and then click **Finish**.</span></span>

    <span data-ttu-id="a7401-139">**注** [ **Host Parameters** ] ページには、NLB クラスターホストの優先順位 (1 ~ 32) も表示されます。</span><span class="sxs-lookup"><span data-stu-id="a7401-139">**Note** The **Host Parameters** page also displays the NLB cluster host priority, which is 1 through 32.</span></span> <span data-ttu-id="a7401-140">新しいホストが NLB クラスターに追加されると、ホストの優先順位は、以前に追加したホストとは異なるものにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-140">As new hosts are added to the NLB cluster, the host priority must differ from the previously added hosts.</span></span> <span data-ttu-id="a7401-141">ネットワーク負荷分散マネージャーを使用すると、優先順位が自動的に増加します。</span><span class="sxs-lookup"><span data-stu-id="a7401-141">The priority is automatically incremented when you use the Network Load Balancing Manager.</span></span>

     

10. <span data-ttu-id="a7401-142">[ \*\* &lt; Nlb クラスター名 &gt; \*\* ] をクリックして、続行する前に Nlb ホストインターフェイスの**状態**が**収束**していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7401-142">Click **&lt;NLB cluster name&gt;** and ensure that the NLB host interface **Status** displays **Converged** before you continue.</span></span> <span data-ttu-id="a7401-143">この手順では、nlb マネージャーによって変更されているホストの TCP/IP 構成として NLB クラスター表示を更新する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="a7401-143">This step might require that you refresh the NLB cluster display as the host TCP/IP configuration that is being modified by the NLB Manager.</span></span>

11. <span data-ttu-id="a7401-144">NLB クラスターにさらにホストを追加するには、[ \*\* &lt; nlb クラスター &gt; 名**] を右クリックし、[**クラスターにホストを追加\*\*] をクリックして、NLB クラスターの一部となるサイトシステムごとに、手順 7 ~ 10 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="a7401-144">To add additional hosts to the NLB cluster, right-click **&lt;NLB cluster name&gt;**, click **Add Host to Cluster,** and then repeat steps 7 through 10 for each site system that will be part of the NLB cluster.</span></span>

12. <span data-ttu-id="a7401-145">MBAM グループポリシーテンプレートがインストールされているコンピューターの場合は、mbam グループポリシー設定を変更して、NLB クラスター名と適切な IIS ポートバインディングを使用して、nlb クラスターコンピューターにインストールされている MBAM 管理および監視サーバー機能にアクセスするように、MBAM サービスのエンドポイントを構成します。</span><span class="sxs-lookup"><span data-stu-id="a7401-145">On a computer that has MBAM Group Policy template installed, modify the MBAM Group Policy settings to configure the MBAM services endpoints to use the NLB Cluster name and the appropriate IIS port binding to access the MBAM Administration and Monitoring Server features that are installed on the NLB Cluster computers.</span></span> <span data-ttu-id="a7401-146">MBAM GPO 設定の編集方法の詳細については、「 [mbam 1.0 Gpo 設定を編集する方法](how-to-edit-mbam-10-gpo-settings.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7401-146">For more information about how to edit MBAM GPO settings, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span> <span data-ttu-id="a7401-147">MBAM 管理と監視サーバーが環境を初めて使用する場合は、必要なローカルセキュリティグループのメンバーシップが適切に構成されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7401-147">If the MBAM Administration and Monitoring servers are new to your environment, ensure that the required local security group memberships have been properly configured.</span></span> <span data-ttu-id="a7401-148">セキュリティグループの要件の詳細については、「 [MBAM 1.0 管理者ロールの計画](planning-for-mbam-10-administrator-roles.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a7401-148">For more information about security group requirements, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

13. <span data-ttu-id="a7401-149">NLB クラスター構成が完了したら、MBAM 管理と NLB クラスターの監視が機能することを検証することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a7401-149">When the NLB Cluster configuration is complete, we recommend that you validate that the MBAM Administration and Monitoring NLB Cluster is functional.</span></span> <span data-ttu-id="a7401-150">これを行うには、NLB で構成されているサーバー以外のコンピューターで web ブラウザーを開き、この NLB FQDN を使用して、MBAM 管理と監視 web サイトにアクセスできることを確認します。</span><span class="sxs-lookup"><span data-stu-id="a7401-150">To do this, open a web browser on a computer other than the servers that are configured in the NLB, and ensure that you can access the MBAM Administration and Monitoring web site by using the NLB FQDN.</span></span>

## <span data-ttu-id="a7401-151">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a7401-151">Related topics</span></span>


[<span data-ttu-id="a7401-152">MBAM 1.0 サーバー インフラストラクチャの展開</span><span class="sxs-lookup"><span data-stu-id="a7401-152">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





