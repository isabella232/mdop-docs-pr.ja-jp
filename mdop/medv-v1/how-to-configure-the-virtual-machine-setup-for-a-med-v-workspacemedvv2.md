---
title: MED-V ワークスペースの仮想マシンのセットアップを構成する方法
description: MED-V ワークスペースの仮想マシンのセットアップを構成する方法
author: dansimp
ms.assetid: 50bbf58b-842c-4b63-bb93-3783903f6c7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0ba24f0e9aa5befeaf385acf06273a53feaae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827074"
---
# <span data-ttu-id="8ebfb-103">MED-V ワークスペースの仮想マシンのセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ebfb-103">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>


<span data-ttu-id="8ebfb-104">すべての仮想マシンセットアップ構成設定は、[ **VM のセットアップ**] タブの**ポリシー**モジュールで構成されます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-104">All virtual machine setup configuration settings are configured in the **Policy** module, on the **VM Setup** tab.</span></span>

## <span data-ttu-id="8ebfb-105">永続的な MED-V ワークスペースの仮想マシンセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ebfb-105">How to Configure the Virtual Machine Setup for a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="8ebfb-106">永続的な MED-V ワークスペースの仮想マシンのセットアップを構成するには</span><span class="sxs-lookup"><span data-stu-id="8ebfb-106">To configure the virtual machine setup for a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="8ebfb-107">構成する永続的な MED ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-107">Click a persistent MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="8ebfb-108">[**永続的な VM のセットアップ**] セクションで、次の表の説明に従ってプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-108">In the **Persistent VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="8ebfb-109">注</span><span class="sxs-lookup"><span data-stu-id="8ebfb-109">Note</span></span>**  
    <span data-ttu-id="8ebfb-110">永続的な VM のセットアッププロパティは、持続的な MED-V ワークスペースでのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-110">The persistent VM setup properties are enabled only for a persistent MED-V workspace.</span></span>



3.  <span data-ttu-id="8ebfb-111">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-111">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="8ebfb-112">永続的な VM のセットアッププロパティ</span><span class="sxs-lookup"><span data-stu-id="8ebfb-112">Persistent VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8ebfb-113">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ebfb-113">Property</span></span></th>
<th align="left"><span data-ttu-id="8ebfb-114">説明</span><span class="sxs-lookup"><span data-stu-id="8ebfb-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ebfb-115">VM セットアップを実行する</span><span class="sxs-lookup"><span data-stu-id="8ebfb-115">Run VM Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ebfb-116">このチェックボックスをオンにすると、MED-V ワークスペースを初めて実行したときにセットアップスクリプトが実行されます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-116">Select this check box to run a setup script the first time the MED-V workspace is run.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8ebfb-117">スクリプトエディター</span><span class="sxs-lookup"><span data-stu-id="8ebfb-117">Script Editor</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ebfb-118">[] をクリックして、セットアップスクリプトを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-118">Click to configure the setup script.</span></span> <span data-ttu-id="8ebfb-119">詳細については、「 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> スクリプト操作を設定する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-119">For more information, see <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)">How to Set Up Script Actions</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8ebfb-120">注</span><span class="sxs-lookup"><span data-stu-id="8ebfb-120">Note</span></span></strong><br/><p><span data-ttu-id="8ebfb-121">このボタンは <strong> 、[VM のセットアップスクリプトを実行] が選択されている場合にのみ有効です </strong> 。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-121">This button is enabled only when <strong>Run VM Setup script</strong> is selected.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ebfb-122">スクリプトの実行時に表示されるメッセージ</span><span class="sxs-lookup"><span data-stu-id="8ebfb-122">Message displayed when script is running</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ebfb-123">スクリプトの実行中に表示されるメッセージ。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-123">A message to be displayed while the script is running.</span></span> <span data-ttu-id="8ebfb-124">空白のままにすると、既定のメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-124">If left blank, the default message is displayed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="8ebfb-125">注</span><span class="sxs-lookup"><span data-stu-id="8ebfb-125">Note</span></span></strong><br/><p><span data-ttu-id="8ebfb-126">このフィールドは <strong> 、VM セットアップスクリプトを実行した場合にのみ有効になり </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-126">This field is enabled only when <strong>Run VM Setup script</strong> is checked.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8ebfb-127">Revertible MED-V ワークスペースの仮想マシンセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="8ebfb-127">How to Configure the Virtual Machine Setup for a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="8ebfb-128">Revertible MED-V ワークスペースの仮想マシンのセットアップを構成するには</span><span class="sxs-lookup"><span data-stu-id="8ebfb-128">To configure the virtual machine setup for a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="8ebfb-129">構成する revertible MED ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-129">Click a revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="8ebfb-130">**REVERTIBLE VM のセットアップ**セクションで、次の表の説明に従ってプロパティを構成します。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-130">In the **Revertible VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="8ebfb-131">注</span><span class="sxs-lookup"><span data-stu-id="8ebfb-131">Note</span></span>**  
    <span data-ttu-id="8ebfb-132">Revertible VM のセットアッププロパティは、revertible MED ワークスペースに対してのみ有効になります。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-132">The revertible VM setup properties are enabled only for a revertible MED-V workspace.</span></span>



3.  <span data-ttu-id="8ebfb-133">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-133">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="8ebfb-134">Revertible VM のセットアッププロパティ</span><span class="sxs-lookup"><span data-stu-id="8ebfb-134">Revertible VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8ebfb-135">プロパティ</span><span class="sxs-lookup"><span data-stu-id="8ebfb-135">Property</span></span></th>
<th align="left"><span data-ttu-id="8ebfb-136">説明</span><span class="sxs-lookup"><span data-stu-id="8ebfb-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8ebfb-137">コンピューター名パターンに基づいて VM の名前を変更する</span><span class="sxs-lookup"><span data-stu-id="8ebfb-137">Rename the VM based on the computer name pattern</span></span></p></td>
<td align="left"><p><span data-ttu-id="8ebfb-138">このチェックボックスをオンにすると、同じ MED-V ワークスペースを使用して複数のコンピューターを区別できるように、MED-V ワークスペースを使用して、各コンピューターに一意の名前を割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-138">Select this check box to assign a unique name to each computer using the MED-V workspace so that you can differentiate between multiple computers using the same MED-V workspace.</span></span></p>
<p><span data-ttu-id="8ebfb-139">コンピューターのイメージ名の構成の詳細については、「 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> VM コンピューター名パターンプロパティを構成する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="8ebfb-139">For more information on configuring computer image names, see <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)">How to Configure VM Computer Name Pattern Properties</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="8ebfb-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="8ebfb-140">Related topics</span></span>


[<span data-ttu-id="8ebfb-141">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="8ebfb-141">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="8ebfb-142">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="8ebfb-142">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="8ebfb-143">仮想マシンの構成の例</span><span class="sxs-lookup"><span data-stu-id="8ebfb-143">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









