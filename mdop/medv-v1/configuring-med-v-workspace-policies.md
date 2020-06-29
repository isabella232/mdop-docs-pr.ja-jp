---
title: MED-V ワークスペース ポリシーの構成
description: MED-V ワークスペース ポリシーの構成
author: dansimp
ms.assetid: 0eaed981-cbf3-4b16-a4b7-4705c5705dc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84bdae38b1c801e2c2be2a3dd1d12dd2ca7d932d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824857"
---
# <span data-ttu-id="10ab4-103">MED-V ワークスペース ポリシーの構成</span><span class="sxs-lookup"><span data-stu-id="10ab4-103">Configuring MED-V Workspace Policies</span></span>


<span data-ttu-id="10ab4-104">MED-V ワークスペースポリシーは、仮想化された環境やアプリケーションがホストコンピューターで実行する方法を定義する、構成可能な設定のグループです。</span><span class="sxs-lookup"><span data-stu-id="10ab4-104">A MED-V workspace policy is a group of configurable settings that define how the virtualized environment and applications perform on the host machine.</span></span> <span data-ttu-id="10ab4-105">このセクションのトピックでは、MED-V ワークスペースポリシーのすべての構成可能な設定について説明し、これらの設定が MED-V ワークスペースに与える影響についても説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-105">The topics in this section describe all the configurable settings in the MED-V workspace policy as well as how these settings influence the MED-V workspace.</span></span>

<span data-ttu-id="10ab4-106">次の MED-V ワークスペースの種類を使用できます。</span><span class="sxs-lookup"><span data-stu-id="10ab4-106">The following MED-V workspace types are available:</span></span>

-   <span data-ttu-id="10ab4-107">**Persistent**: 永続的な med-v ワークスペースでは、ユーザーが med-v ワークスペースに対して行ったすべての変更と追加が、セッション間の med-v ワークスペースに保存されます。</span><span class="sxs-lookup"><span data-stu-id="10ab4-107">**Persistent**—In a persistent MED-V workspace, all changes and additions the user makes to the MED-V workspace are saved in the MED-V workspace between sessions.</span></span> <span data-ttu-id="10ab4-108">さらに、永続的な MED-V ワークスペースは、通常、ドメイン環境で使用されます。</span><span class="sxs-lookup"><span data-stu-id="10ab4-108">Additionally, a persistent MED-V workspace is generally used in a domain environment.</span></span>

-   <span data-ttu-id="10ab4-109">**Revertible**: Revertible MED ワークスペースでは、各セッションの完了時 (つまり、med-v ワークスペースが停止されたとき) に、med-v ワークスペースは展開時に元の状態に戻ります。</span><span class="sxs-lookup"><span data-stu-id="10ab4-109">**Revertible**—In a revertible MED-V workspace, at the completion of each session (that is, when the MED-V workspace is stopped), the MED-V workspace reverts to its original state during deployment.</span></span> <span data-ttu-id="10ab4-110">ユーザーが行った変更や追加は、セッション間の MED-V ワークスペースに保存されません。</span><span class="sxs-lookup"><span data-stu-id="10ab4-110">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span> <span data-ttu-id="10ab4-111">Revertible MED ワークスペースは、ドメイン環境では使用できません。</span><span class="sxs-lookup"><span data-stu-id="10ab4-111">A revertible MED-V workspace cannot be used in a domain environment.</span></span>

<span data-ttu-id="10ab4-112">ポリシーがユーザーに展開された後に、med-v ワークスペースの種類を再構成することは推奨されないため、MED-V ワークスペースを展開する前に作成している MED-V ワークスペースの種類を決定することが重要です。</span><span class="sxs-lookup"><span data-stu-id="10ab4-112">It is important to decide on the type of MED-V workspace you are creating before deploying the MED-V workspace, because it is not recommended to reconfigure the type of MED-V workspace after a policy has been deployed to users.</span></span>

<span data-ttu-id="10ab4-113">**注** ポリシーを構成するときに、入力されていない必須フィールドの横に警告記号が表示されます。</span><span class="sxs-lookup"><span data-stu-id="10ab4-113">**Note** When configuring a policy, a warning symbol appears next to mandatory fields that are not filled in.</span></span> <span data-ttu-id="10ab4-114">必須フィールドが入力されていない場合は、その記号もタブに表示されます。</span><span class="sxs-lookup"><span data-stu-id="10ab4-114">If a mandatory field is not filled in, the symbol appears on the tab as well.</span></span>

 

## <span data-ttu-id="10ab4-115">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="10ab4-115">In This Section</span></span>


<a href="" id="how-to-apply-general-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-116">MED-V ワークスペースに全般設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-116">How to Apply General Settings to a MED-V Workspace</span></span>](how-to-apply-general-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-117">MED-V ワークスペースの全般的な設定と、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-117">Describes the general settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-virtual-machine-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-118">MED-V ワークスペースに仮想マシンの設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-118">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-119">MED-V ワークスペースの仮想マシン設定と、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-119">Describes the virtual machine settings for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-a-domain-user-or-group"></a>[<span data-ttu-id="10ab4-120">ドメイン ユーザーまたはグループを構成する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-120">How to Configure a Domain User or Group</span></span>](how-to-configure-a-domain-user-or-groupmedvv2.md)  
<span data-ttu-id="10ab4-121">ドメインユーザーとグループを構成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-121">Describes how to configure domain users and groups.</span></span>

<a href="" id="how-to-configure-published-applications"></a>[<span data-ttu-id="10ab4-122">公開されたアプリケーションを構成する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-122">How to Configure Published Applications</span></span>](how-to-configure-published-applicationsmedvv2.md)  
<span data-ttu-id="10ab4-123">公開されているアプリケーションとメニューと、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-123">Describes published applications and menus, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-web-settings-for-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-124">MED-V ワークスペースの Web 設定を構成する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-124">How to Configure Web Settings for a MED-V Workspace</span></span>](how-to-configure-web-settings-for-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-125">MED-V ワークスペースで利用可能な Web 設定と、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-125">Describes the Web settings available for a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-126">MED-V ワークスペースの仮想マシンのセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-126">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-127">MED-V ワークスペースの仮想マシンのセットアップと、それをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-127">Describes the virtual machine setup for a MED-V workspace, and how to apply it to a policy.</span></span>

<a href="" id="how-to-apply-network-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-128">MED-V ワークスペースにネットワーク設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-128">How to Apply Network Settings to a MED-V Workspace</span></span>](how-to-apply-network-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-129">MED-V ワークスペースのネットワーク設定と、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-129">Describes the network settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-apply-performance-settings-to-a-med-v-workspace"></a>[<span data-ttu-id="10ab4-130">MED-V ワークスペースにパフォーマンス設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-130">How to Apply Performance Settings to a MED-V Workspace</span></span>](how-to-apply-performance-settings-to-a-med-v-workspace.md)  
<span data-ttu-id="10ab4-131">MED-V ワークスペースのパフォーマンス設定と、それらをポリシーに適用する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-131">Describes the performance settings of a MED-V workspace, and how to apply them to a policy.</span></span>

<a href="" id="how-to-import-and-export-a-policy"></a>[<span data-ttu-id="10ab4-132">ポリシーをインポートおよびエクスポートする方法</span><span class="sxs-lookup"><span data-stu-id="10ab4-132">How to Import and Export a Policy</span></span>](how-to-import-and-export-a-policy.md)  
<span data-ttu-id="10ab4-133">ポリシーをインポートおよびエクスポートする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="10ab4-133">Describes how to import and export a policy.</span></span>

 

 





