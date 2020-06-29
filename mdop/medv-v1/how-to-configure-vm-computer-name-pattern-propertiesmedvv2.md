---
title: VM のコンピューター名パターンのプロパティを構成する方法
description: VM のコンピューター名パターンのプロパティを構成する方法
author: dansimp
ms.assetid: ddf79ace-8cc3-4ee6-be5a-5940b4df5c36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa171712b6624b73fb5e0756aaf56277baa4c8cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827077"
---
# <span data-ttu-id="3e968-103">VM のコンピューター名パターンのプロパティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="3e968-103">How to Configure VM Computer Name Pattern Properties</span></span>


<span data-ttu-id="3e968-104">仮想マシンのコンピューター名パターンは、revertible と永続的な MED-V ワークスペースの両方に割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e968-104">A virtual machine computer name pattern can be assigned both for revertible and for persistent MED-V workspaces.</span></span>

-   <span data-ttu-id="3e968-105">Revertible: 管理者は、同じ MED-V ワークスペースを使用して複数のコンピューターを区別するために、固有の名前を各 Revertible MED ワークスペースインスタンスに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="3e968-105">Revertible—Administrators can assign a unique name to each revertible MED-V workspace instance to differentiate between multiple computers using the same MED-V workspace.</span></span>

-   <span data-ttu-id="3e968-106">Persistent: 永続的な MED-V ワークスペースでは、管理者は、セットアップスクリプト中にコンピューターの名前を変更するように設定できます。</span><span class="sxs-lookup"><span data-stu-id="3e968-106">Persistent—In a persistent MED-V workspace, administrators can set a computer to be renamed during a setup script.</span></span>

## <span data-ttu-id="3e968-107">仮想マシンのコンピューター名パターンを Revertible MED-V ワークスペースに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="3e968-107">How to Assign a Virtual Machine Computer Name Pattern to a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="3e968-108">仮想マシンのコンピューター名パターンを revertible MED ワークスペースに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3e968-108">To assign a virtual machine computer name pattern to a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="3e968-109">構成する revertible MED ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e968-109">Click the revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="3e968-110">[ **REVERTIBLE Vm セットアップ**] セクションで、[**コンピューター名パターンに基づいて VM の名前を変更**する] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="3e968-110">In the **Revertible VM Setup** section, select the **Rename the VM based on the computer name pattern** check box.</span></span>

3.  <span data-ttu-id="3e968-111">[ **VM コンピューター名パターン**] セクションで、次のオプションを使用して仮想マシンのイメージの名前を指定するために使用するパターンを入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-111">In the **VM Computer Name Pattern** section, enter the pattern to use for naming virtual machine images, using the following options:</span></span>

    -   <span data-ttu-id="3e968-112">**定数**— med-v ワークスペースを使用して、すべてのコンピューターで定数となる無料のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-112">**Constant**—Enter free text that will be constant on all computers using the MED-V workspace.</span></span>

    -   <span data-ttu-id="3e968-113">[**変数] — [** 変数の**挿入**] をクリックして変数を入力し、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e968-113">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="3e968-114">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="3e968-114">User name</span></span>**

        -   **<span data-ttu-id="3e968-115">Domain name</span><span class="sxs-lookup"><span data-stu-id="3e968-115">Domain name</span></span>**

        -   **<span data-ttu-id="3e968-116">ホスト名</span><span class="sxs-lookup"><span data-stu-id="3e968-116">Host name</span></span>**

        -   **<span data-ttu-id="3e968-117">ワークスペース名</span><span class="sxs-lookup"><span data-stu-id="3e968-117">Workspace name</span></span>**

        -   **<span data-ttu-id="3e968-118">仮想マシン名</span><span class="sxs-lookup"><span data-stu-id="3e968-118">Virtual machine name</span></span>**

        <span data-ttu-id="3e968-119">選択された変数は、MED-V ワークスペースを使用しているコンピューターに固有のものになります。</span><span class="sxs-lookup"><span data-stu-id="3e968-119">The variable selected will be specific to the computer using the MED-V workspace.</span></span> <span data-ttu-id="3e968-120">たとえば、[ **Domain name** ] が選択されている場合、各コンピューターの一意の名前には、コンピューターのドメイン名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e968-120">For example, if **Domain name** is selected, the unique name for each computer will include the computer's domain name.</span></span>

    -   <span data-ttu-id="3e968-121">**ランダム文字**—パターンに含める各ランダム文字に「\ #」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-121">**Random characters**—Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="3e968-122">MED-V ワークスペースを使用する各コンピューターには、指定した長さのサフィックスが表示されます。これはランダムに生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e968-122">Each computer using the MED-V workspace will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="3e968-123">注</span><span class="sxs-lookup"><span data-stu-id="3e968-123">Note</span></span>**  
    <span data-ttu-id="3e968-124">コンピューター名の上限は15文字です。</span><span class="sxs-lookup"><span data-stu-id="3e968-124">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="3e968-125">パターンが上限を超えている場合は、切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="3e968-125">If the pattern exceeds the limit, it will be truncated.</span></span>



4.  <span data-ttu-id="3e968-126">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3e968-126">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="3e968-127">注</span><span class="sxs-lookup"><span data-stu-id="3e968-127">Note</span></span>**  
    <span data-ttu-id="3e968-128">Revertible VM コンピューター名パターンを割り当てることができるのは、**コンピューター名パターンに基づいて vm の**名前を変更する場合のみです (「 **revertible VM セットアップ**セクションの場合)。</span><span class="sxs-lookup"><span data-stu-id="3e968-128">A revertible VM computer name pattern can be assigned only when **Rename the VM based on the computer name patterns** (in the **Revertible VM Setup** section) is checked.</span></span>



~~~
**Note**  
A unique computer name can be assigned only if it is configured prior to MED-V workspace setup. Changing the name will not affect MED-V workspaces that were already set up.
~~~



## <span data-ttu-id="3e968-129">仮想マシンのコンピューター名パターンを永続的な MED-V ワークスペースに割り当てる方法</span><span class="sxs-lookup"><span data-stu-id="3e968-129">How to Assign a Virtual Machine Computer Name Pattern to a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="3e968-130">仮想マシンのコンピューター名パターンを永続的な MED-V ワークスペースに割り当てるには</span><span class="sxs-lookup"><span data-stu-id="3e968-130">To assign a virtual machine computer name pattern to a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="3e968-131">構成する永続的な MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e968-131">Click the persistent MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="3e968-132">[**永続的な VM のセットアップ**] セクションで、[**スクリプトエディター**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e968-132">In the **Persistent VM Setup** section, click **Script Editor**.</span></span>

3.  <span data-ttu-id="3e968-133">[**スクリプト操作**] ダイアログボックスの [**追加**] をクリックし、サブメニューの [**コンピューター名の変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="3e968-133">In the **Script Actions** dialog box, click **Add**, and on the submenu, click **Rename Computer**.</span></span>

4.  <span data-ttu-id="3e968-134">[ **OK** ] をクリックして [**スクリプト操作**] ダイアログボックスを閉じます。</span><span class="sxs-lookup"><span data-stu-id="3e968-134">Click **OK** to close the **Script Actions** dialog box.</span></span>

5.  <span data-ttu-id="3e968-135">[ **Vm のセットアップ**] タブの [ **Vm コンピューター名パターン**] セクションで、コンピューター名の変更に使用するパターンを、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-135">On the **VM Setup** tab, in the **VM Computer Name Pattern** section, enter the pattern to use for renaming the computer, using the following:</span></span>

    -   <span data-ttu-id="3e968-136">**定数**—コンピューター名に含まれる無料のテキストを入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-136">**Constant**— Enter free text that will be included in the computer name.</span></span>

    -   <span data-ttu-id="3e968-137">[**変数] — [** 変数の**挿入**] をクリックして変数を入力し、次のいずれかを選択します。</span><span class="sxs-lookup"><span data-stu-id="3e968-137">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="3e968-138">ユーザー名</span><span class="sxs-lookup"><span data-stu-id="3e968-138">User name</span></span>**

        -   **<span data-ttu-id="3e968-139">Domain name</span><span class="sxs-lookup"><span data-stu-id="3e968-139">Domain name</span></span>**

        -   **<span data-ttu-id="3e968-140">ホスト名</span><span class="sxs-lookup"><span data-stu-id="3e968-140">Host name</span></span>**

        -   **<span data-ttu-id="3e968-141">ワークスペース名</span><span class="sxs-lookup"><span data-stu-id="3e968-141">Workspace name</span></span>**

        -   **<span data-ttu-id="3e968-142">仮想マシン名</span><span class="sxs-lookup"><span data-stu-id="3e968-142">Virtual machine name</span></span>**

        <span data-ttu-id="3e968-143">選択された変数は、名前を変更するコンピューターに固有のものになります。</span><span class="sxs-lookup"><span data-stu-id="3e968-143">The variable selected will be specific to the computer that is being renamed.</span></span> <span data-ttu-id="3e968-144">たとえば、[ **Domain name** ] が選択されている場合、コンピューター名にはコンピューターのドメイン名が含まれます。</span><span class="sxs-lookup"><span data-stu-id="3e968-144">For example, if **Domain name** is selected, the computer name will include the computer's domain name.</span></span>

    -   <span data-ttu-id="3e968-145">**ランダム文字**—パターンに含める各ランダム文字に「\ #」と入力します。</span><span class="sxs-lookup"><span data-stu-id="3e968-145">**Random characters**— Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="3e968-146">コンピューターには、指定した長さのサフィックスが指定されます。これはランダムに生成されます。</span><span class="sxs-lookup"><span data-stu-id="3e968-146">The computer will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="3e968-147">注</span><span class="sxs-lookup"><span data-stu-id="3e968-147">Note</span></span>**  
    <span data-ttu-id="3e968-148">コンピューター名の上限は15文字です。</span><span class="sxs-lookup"><span data-stu-id="3e968-148">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="3e968-149">パターンが上限を超えている場合は、切り捨てられます。</span><span class="sxs-lookup"><span data-stu-id="3e968-149">If the pattern exceeds the limit, it will be truncated.</span></span>



6.  <span data-ttu-id="3e968-150">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="3e968-150">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="3e968-151">注</span><span class="sxs-lookup"><span data-stu-id="3e968-151">Note</span></span>**  
    <span data-ttu-id="3e968-152">[**スクリプトアクション**] ダイアログボックスでアクションとして設定されている場合にのみ、コンピューターの名前が変更されます。</span><span class="sxs-lookup"><span data-stu-id="3e968-152">The computer will be renamed only if it is set as an action in the **Script Actions** dialog box.</span></span> <span data-ttu-id="3e968-153">詳細については、「[スクリプト操作を設定する方法](how-to-set-up-script-actions.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3e968-153">For detailed information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>



## <span data-ttu-id="3e968-154">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3e968-154">Related topics</span></span>


[<span data-ttu-id="3e968-155">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="3e968-155">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="3e968-156">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="3e968-156">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="3e968-157">スクリプトのアクションを設定する方法</span><span class="sxs-lookup"><span data-stu-id="3e968-157">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

[<span data-ttu-id="3e968-158">仮想マシンの構成の例</span><span class="sxs-lookup"><span data-stu-id="3e968-158">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









