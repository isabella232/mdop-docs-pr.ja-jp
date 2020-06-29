---
title: MED-V ワークスペースにネットワーク設定を適用する方法
description: MED-V ワークスペースにネットワーク設定を適用する方法
author: dansimp
ms.assetid: 641f46b3-a56f-478a-823b-1d90aa1716b3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a13227518945e74be9e4b3772af97eadbce3fc4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826517"
---
# <span data-ttu-id="18a21-103">MED-V ワークスペースにネットワーク設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="18a21-103">How to Apply Network Settings to a MED-V Workspace</span></span>


<span data-ttu-id="18a21-104">管理者は、各 MED-V ワークスペースのネットワーク設定を定義できます。</span><span class="sxs-lookup"><span data-stu-id="18a21-104">Administrators can define the network settings for each MED-V workspace.</span></span>

<span data-ttu-id="18a21-105">[**ネットワーク**] タブの**ポリシー**モジュールで、すべてのネットワーク設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="18a21-105">All network settings are configured in the **Policy** module, on the **Network** tab.</span></span>

**<span data-ttu-id="18a21-106">MED-V ワークスペースにネットワーク設定を適用するには</span><span class="sxs-lookup"><span data-stu-id="18a21-106">To apply network settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="18a21-107">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="18a21-107">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="18a21-108">[**ネットワーク**] ウィンドウで、次の表の説明に従って設定を構成します。</span><span class="sxs-lookup"><span data-stu-id="18a21-108">In the **Network** pane, configure the settings as described in the following table.</span></span>

3.  <span data-ttu-id="18a21-109">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="18a21-109">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="18a21-110">MED ワークスペースのネットワークプロパティ</span><span class="sxs-lookup"><span data-stu-id="18a21-110">MED-V Workspace Network Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="18a21-111">プロパティ</span><span class="sxs-lookup"><span data-stu-id="18a21-111">Property</span></span></th>
<th align="left"><span data-ttu-id="18a21-112">説明</span><span class="sxs-lookup"><span data-stu-id="18a21-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18a21-113">TCP/IP のプロパティ</span><span class="sxs-lookup"><span data-stu-id="18a21-113">TCP/IP Properties</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="18a21-114">ホストの IP アドレス (NAT) を使用 </strong> —ワークスペースでは、NAT を使って、発信トラフィック用にホストの ip を共有します。</span><span class="sxs-lookup"><span data-stu-id="18a21-114">Use host's IP address (NAT)</strong>—The workspace will use NAT to share the host's IP for outgoing traffic.</span></span></p></li>
<li><p><strong><span data-ttu-id="18a21-115">ホスト (ブリッジ) とは異なる IP アドレスを使用します </strong> 。 med-v ワークスペースには独自のネットワークアドレスが割り当てられます。通常は DHCP 経由で取得します。</span><span class="sxs-lookup"><span data-stu-id="18a21-115">Use different IP address than host (Bridge)</strong>—The MED-V workspace will have its own network address, usually obtained via DHCP.</span></span></p></li>
</ul>
<p><span data-ttu-id="18a21-116"><strong>ホストコンピューターに複数のアダプターがある場合は、[複数のアダプターをワークスペースにマップ </strong> する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="18a21-116">Select the <strong>Map multiple adapters into Workspace</strong> check box when the host computer has multiple adapters.</span></span> <span data-ttu-id="18a21-117">ホストがさまざまなアダプターを使って異なるネットワーク間を移動する場合は、この構成を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="18a21-117">It is recommended to use this configuration when the host moves between different networks using different adapters.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18a21-118">DNS サーバー</span><span class="sxs-lookup"><span data-stu-id="18a21-118">DNS Server</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="18a21-119">変更しない </strong> — med-v ワークスペース仮想マシン内で設定されている DNS 設定は変更されません。</span><span class="sxs-lookup"><span data-stu-id="18a21-119">Don't change</strong>—DNS settings that are set within the MED-V workspace virtual machine will not be changed.</span></span></p></li>
<li><p><strong><span data-ttu-id="18a21-120">[Host の DNS アドレスを使用する] </strong> : med-v workspace の dns 設定は、ホストの設定と一致するように同期されます。</span><span class="sxs-lookup"><span data-stu-id="18a21-120">Use Host's DNS address</strong>—MED-V workspace DNS settings will be synchronized to match the host's settings.</span></span> <span data-ttu-id="18a21-121">DNS の同期は動的です。</span><span class="sxs-lookup"><span data-stu-id="18a21-121">The DNS synchronization is dynamic.</span></span> <span data-ttu-id="18a21-122">ホスト上で変更された場合は、MED-V ワークスペースで動的に変更されるように、ホストと定期的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="18a21-122">It is synchronized periodically with the host so that if it is changed on the host, it will change dynamically in the MED-V workspace.</span></span></p></li>
<li><p><strong><span data-ttu-id="18a21-123">特定の DNS アドレスを使い </strong> ます。 med-v ワークスペースでは、指定されている特定の dns が使用されます。</span><span class="sxs-lookup"><span data-stu-id="18a21-123">Use specific DNS addresses</strong>—The MED-V workspace will use a specific DNS, as specified.</span></span></p>
<p><span data-ttu-id="18a21-124">" <strong> プライマリ" </strong> フィールドと "セカンダリ" フィールドに、 <strong> </strong> プライマリおよびセカンダリの DNS アドレスを入力します。</span><span class="sxs-lookup"><span data-stu-id="18a21-124">In the <strong>Primary</strong> and <strong>Secondary</strong> fields, enter the primary and secondary DNS addresses.</span></span></p>
<p><span data-ttu-id="18a21-125">[ <strong> Host の dns アドレスを追加 </strong> する] チェックボックスをオンにして、構成済みの dns アドレスにホストを追加します。</span><span class="sxs-lookup"><span data-stu-id="18a21-125">Select the <strong>Append Host's DNS addresses</strong> check box to append the host to the configured DNS addresses.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18a21-126">DNS サフィックスを割り当てる</span><span class="sxs-lookup"><span data-stu-id="18a21-126">Assign DNS Suffixes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="18a21-127">次のサフィックスを割り当てる </strong> : 特定の DNS サフィックスを割り当てるには、このチェックボックスをオンにします。このボックスに、サフィックスを入力するか、カンマで区切った複数のサフィックスを入力します。</span><span class="sxs-lookup"><span data-stu-id="18a21-127">Assign the following suffixes</strong>—Select this check box to assign specific DNS suffixes; in the box, enter a suffix or multiple suffixes separated by commas.</span></span></p></li>
<li><p><strong><span data-ttu-id="18a21-128">[Host サフィックス </strong> の追加] — DNS アドレスにホストサフィックスを追加するには、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="18a21-128">Append host suffixes</strong>—Select this check box to append the host suffixes to the DNS address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="18a21-129">関連トピック</span><span class="sxs-lookup"><span data-stu-id="18a21-129">Related topics</span></span>


[<span data-ttu-id="18a21-130">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="18a21-130">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="18a21-131">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="18a21-131">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





