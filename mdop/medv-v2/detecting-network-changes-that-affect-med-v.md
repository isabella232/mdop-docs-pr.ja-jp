---
title: MED-V に影響を与えるネットワークの変更の検出
description: MED-V に影響を与えるネットワークの変更の検出
author: dansimp
ms.assetid: fd29b95a-cda2-464d-b86d-50b6bd64b4ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5f43c30dee9ef8e06a7ae226849a4f21e83257c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823374"
---
# <span data-ttu-id="58895-103">MED-V に影響を与えるネットワークの変更の検出</span><span class="sxs-lookup"><span data-stu-id="58895-103">Detecting Network Changes that Affect MED-V</span></span>


<span data-ttu-id="58895-104">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 ソリューションを使用すると、MED-V ワークスペースの展開後に発生する可能性のある特定のネットワーク変更を検出し、MED-V に影響を与える可能性のある特定のネットワーク変更を検出するように環境を構成できます。</span><span class="sxs-lookup"><span data-stu-id="58895-104">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution lets you configure your environment to detect certain network changes that might occur after MED-V workspaces are deployed and that can affect MED-V.</span></span>

<span data-ttu-id="58895-105">この機能には、ゲストオペレーティングシステムで実行されているコンポーネントが含まれており、ホストコンピューターでのネットワーク構成の変更について通知されます。</span><span class="sxs-lookup"><span data-stu-id="58895-105">The feature includes a component running in the guest operating system that is notified of network configuration changes on the host computer.</span></span> <span data-ttu-id="58895-106">これにより、ゲストで実行されている Microsoft 以外の ESD または他のアプリケーションが、ホストの ESD またはアプリケーションで解決されるのと同じネットワークエンドポイントに解決することができます。</span><span class="sxs-lookup"><span data-stu-id="58895-106">It allows a non-Microsoft ESD or other application that is running in the guest to resolve to the same network endpoints that the host ESD or application resolves to.</span></span>

<span data-ttu-id="58895-107">**注** この機能は、仮想マシンがネットワークアドレス変換 (NAT) モード用に構成されている場合にのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="58895-107">**Note** This feature is only available if the virtual machine is configured for network address translation (NAT) mode.</span></span> <span data-ttu-id="58895-108">仮想マシンがブリッジモードに構成されている場合、変更のインジケーターは生成されません。</span><span class="sxs-lookup"><span data-stu-id="58895-108">If the virtual machine is configured for BRIDGED mode, no change indications are generated.</span></span>

 

<span data-ttu-id="58895-109">このセクションでは、MED-V に影響を与える可能性があるネットワークの変更を監視する際に役立つ情報と手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="58895-109">This section provides information and instruction to assist you in monitoring those network changes that can affect MED-V.</span></span>

## <span data-ttu-id="58895-110">MED-V のネットワーク変更を検出するには</span><span class="sxs-lookup"><span data-stu-id="58895-110">To detect network changes for MED-V</span></span>


<span data-ttu-id="58895-111">MED-V のワークスペースを展開した後、次のタスクを事前に構成することで、特定のネットワーク構成の変更を監視できます。</span><span class="sxs-lookup"><span data-stu-id="58895-111">After you have deployed your MED-V workspaces, you can monitor changes to certain network configurations by preforming the following tasks:</span></span>

1. <span data-ttu-id="58895-112">監視するネットワーク構成の変更を検索する管理オブジェクト形式 (MOF) ファイルを作成します。</span><span class="sxs-lookup"><span data-stu-id="58895-112">Create a Managed Object Format (MOF) file that will look for the network configuration changes that you want to monitor.</span></span> <span data-ttu-id="58895-113">次のコードは、作成できる MOF ファイルの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="58895-113">The following code shows an example of the MOF file that you can create.</span></span>

   ``` syntax
   #pragma namespace ("\\\\.\\root\\ccm\\NetworkConfig")

   class CCM_IPConfig
   {
       [NotNull: ToInstance ToSubClass] uint32 AddressFamily; // AF_INET, AF_INET6
       [Key, NotNull: ToInstance ToSubClass] string IPAddress; // IPv4 or IPv6 address
       [NotNull: ToInstance ToSubClass] string SubnetMask; // IPv4 subnet mask
   };

   class CCM_NetworkAdapter
   {
       [Key, NotNull: ToInstance ToSubClass] string Name;
       [NotNull: ToInstance ToSubClass] uint32 DHCPEnabled = 0; 
       [NotNull: ToInstance ToSubClass] uint32 Quarantined = 0; // To check if it is quarantined.
       CCM_IPConfig IPConfigInfo[];
   };

   [singleton]
   class CCM_NetworkAdapters
   {
       [NotNull: ToInstance ToSubClass] String ProviderName; // MED-V or other provider
       CCM_NetworkAdapter AdaptersInfo[];
   };
   ```

2. <span data-ttu-id="58895-114">MOF ファイルをコンパイルします。</span><span class="sxs-lookup"><span data-stu-id="58895-114">Compile the MOF file.</span></span>

3. <span data-ttu-id="58895-115">ゲストに MOF ファイルをインストールします。</span><span class="sxs-lookup"><span data-stu-id="58895-115">Install the MOF file in the guest.</span></span>

<span data-ttu-id="58895-116">MOF ファイルをインストールしたら、 **CCM \ _NetworkAdapters**クラスの Windows Management INSTRUMENTATION (WMI) 作成イベント、変更イベント、削除イベントにサブスクライブするイベントサブスクリプションを作成できます。</span><span class="sxs-lookup"><span data-stu-id="58895-116">After you have installed the MOF file, you can create an event subscription that subscribes to Windows Management Instrumentation (WMI) creation, modification, or deletion events for the **CCM\_NetworkAdapters** class.</span></span> <span data-ttu-id="58895-117">これにより、ホストに次の変更が検出されます。</span><span class="sxs-lookup"><span data-stu-id="58895-117">This detects the following changes to the host:</span></span>

<span data-ttu-id="58895-118">IP アドレスやネットワークアダプターの変更など、ネットワークの構成が変更されているかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="58895-118">Are there any configuration changes to the network, such as changes to the IP address or network adapter?</span></span>

<span data-ttu-id="58895-119">ネットワークが利用可能かどうか、または利用できませんか?</span><span class="sxs-lookup"><span data-stu-id="58895-119">Is the network available or unavailable?</span></span>

<span data-ttu-id="58895-120">ネットワーク設定がブリッジモードから NAT モードに変更されましたか?</span><span class="sxs-lookup"><span data-stu-id="58895-120">Was the network setup changed from BRIDGED mode to NAT mode?</span></span>

<span data-ttu-id="58895-121">ネットワーク設定が NAT モードからブリッジモードに変更されましたか?</span><span class="sxs-lookup"><span data-stu-id="58895-121">Was the network setup changed from NAT mode to BRIDGED mode?</span></span>

<span data-ttu-id="58895-122">ホスト上の MED-V コンポーネントによって、ネットワークが監視され、変更のゲストが通知されます。</span><span class="sxs-lookup"><span data-stu-id="58895-122">A MED-V component on the host monitors the network for these changes and then signals the guest of the change.</span></span> <span data-ttu-id="58895-123">ゲストのコンポーネントによって、これらの変更について MED-V ワークスペースを監視する WMI インスタンスが作成されます。</span><span class="sxs-lookup"><span data-stu-id="58895-123">A component in the guest creates a WMI instance to monitor the MED-V workspace for these changes.</span></span>

<span data-ttu-id="58895-124">作成したイベントサブスクリプションは、1つ以上のネットワーク変更 (作成、変更、または削除) が発生したときに、WMI システム経由で通知を提供します。</span><span class="sxs-lookup"><span data-stu-id="58895-124">The event subscription you created provides notification through the WMI system when one or more of these network changes – creation, modification, or deletion – occurs.</span></span>

## <span data-ttu-id="58895-125">関連トピック</span><span class="sxs-lookup"><span data-stu-id="58895-125">Related topics</span></span>


[<span data-ttu-id="58895-126">MED-V ワークスペースを監視する</span><span class="sxs-lookup"><span data-stu-id="58895-126">Monitor MED-V Workspaces</span></span>](monitor-med-v-workspaces.md)

[<span data-ttu-id="58895-127">MED-V ワークスペースの設定を管理する</span><span class="sxs-lookup"><span data-stu-id="58895-127">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





