---
title: 仮想マシンの構成の例
description: 仮想マシンの構成の例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824587"
---
# <span data-ttu-id="5c9cb-103">仮想マシンの構成の例</span><span class="sxs-lookup"><span data-stu-id="5c9cb-103">Examples of Virtual Machine Configurations</span></span>


<span data-ttu-id="5c9cb-104">次に、一般的な仮想マシン構成の例を示します。1つは永続的な MED-V ワークスペース、もう1つは revertible MED ワークスペースです。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-104">The following are examples of typical virtual machine configurations: one in a persistent MED-V workspace and one in a revertible MED-V workspace.</span></span>

<span data-ttu-id="5c9cb-105">**注** 以下の例は、すべての環境での使用を目的としていません。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-105">**Note** These examples are not intended for use in all environments.</span></span> <span data-ttu-id="5c9cb-106">環境に合わせて構成を調整します。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-106">Adjust the configuration according to your environment.</span></span>

 

**<span data-ttu-id="5c9cb-107">永続的な MED-V ワークスペースで一般的なドメインのセットアップを構成するには</span><span class="sxs-lookup"><span data-stu-id="5c9cb-107">To configure a typical domain setup in a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="5c9cb-108">基本イメージで Sysprep を構成して、一意の SID を作成します。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-108">Configure Sysprep on the base image to create a unique SID.</span></span> <span data-ttu-id="5c9cb-109">詳細については、「 [med-v 用の仮想 PC イメージの作成](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-109">For more information, see [Creating a Virtual PC Image for MED-V](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages).</span></span>

2.  <span data-ttu-id="5c9cb-110">[ **Vm のセットアップ**] タブで、[ **Vm セットアップの実行**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-110">On the **VM Setup** tab, select the **Run VM Setup** check box.</span></span>

3.  <span data-ttu-id="5c9cb-111">[ **VM コンピューター名パターン**] セクションで、コンピューターイメージ名のパターンを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-111">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="5c9cb-112">詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-112">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

4.  <span data-ttu-id="5c9cb-113">[**スクリプトエディター**] をクリックし、[ **VM セットアップスクリプトエディター** ] ダイアログボックスで、次の操作を構成します。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-113">Click **Script Editor**, and in the **VM Setup Script Editor** dialog box, configure the following actions:</span></span>

    1.  **<span data-ttu-id="5c9cb-114">コンピューターの名前を変更する</span><span class="sxs-lookup"><span data-stu-id="5c9cb-114">Rename Computer</span></span>**

    2.  **<span data-ttu-id="5c9cb-115">Windows を再起動する</span><span class="sxs-lookup"><span data-stu-id="5c9cb-115">Restart Windows</span></span>**

    3.  **<span data-ttu-id="5c9cb-116">接続を確認する</span><span class="sxs-lookup"><span data-stu-id="5c9cb-116">Check Connectivity</span></span>**

    4.  **<span data-ttu-id="5c9cb-117">ドメインに参加する</span><span class="sxs-lookup"><span data-stu-id="5c9cb-117">Join Domain</span></span>**

    5.  **<span data-ttu-id="5c9cb-118">自動ログオンを無効にする</span><span class="sxs-lookup"><span data-stu-id="5c9cb-118">Disable Auto-Logon</span></span>**

    <span data-ttu-id="5c9cb-119">詳細については、「[スクリプト操作を設定する方法](how-to-set-up-script-actions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-119">For more information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

5.  <span data-ttu-id="5c9cb-120">[**ポリシー** ] メニューで、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-120">On the **Policy** menu, click **Commit**.</span></span>

**<span data-ttu-id="5c9cb-121">Revertible ワークスペースでの一般的なセットアップを構成するには</span><span class="sxs-lookup"><span data-stu-id="5c9cb-121">To configure a typical setup in a revertible workspace</span></span>**

1.  <span data-ttu-id="5c9cb-122">[ **Vm のセットアップ**] タブで、[**コンピューター名パターンに基づいて vm の名前を変更**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-122">On the **VM Setup** tab, select the **Rename the VM based on the computer name pattern** check box.</span></span>

2.  <span data-ttu-id="5c9cb-123">[ **VM コンピューター名パターン**] セクションで、コンピューターイメージ名のパターンを構成します。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-123">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="5c9cb-124">詳細については、「 [VM コンピューター名パターンプロパティを構成する方法](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-124">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

3.  <span data-ttu-id="5c9cb-125">[**ポリシー** ] メニューで、[**コミット**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="5c9cb-125">On the **Policy** menu, click **Commit**.</span></span>

## <span data-ttu-id="5c9cb-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5c9cb-126">Related topics</span></span>


[<span data-ttu-id="5c9cb-127">MED-V ワークスペースの仮想マシンのセットアップを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5c9cb-127">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="5c9cb-128">VM のコンピューター名パターンのプロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="5c9cb-128">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[<span data-ttu-id="5c9cb-129">スクリプトのアクションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="5c9cb-129">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

 

 





