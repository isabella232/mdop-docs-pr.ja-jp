---
title: MED-V ワークスペースの数と種類の特定
description: MED-V ワークスペースの数と種類の特定
author: dansimp
ms.assetid: 11642253-6b1f-4c4a-a11e-48d8a360e1ea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e0c9ed4b0ce92d0ca752525b847405bbce90a270
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827264"
---
# <span data-ttu-id="b6248-103">MED-V ワークスペースの数と種類の特定</span><span class="sxs-lookup"><span data-stu-id="b6248-103">Identifying the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="b6248-104">MED-V は、Windows XP を必要とする、またはホストコンピューター上のバージョンとは異なるバージョンの Internet Explorer が必要なアプリケーションを実行するための仮想環境を作成します。</span><span class="sxs-lookup"><span data-stu-id="b6248-104">MED-V creates a virtual environment for running applications that require Windows XP or that require a version of Internet Explorer that differs from the version on the host computer.</span></span> <span data-ttu-id="b6248-105">この仮想環境は、MED-V ワークスペースと呼ばれます。</span><span class="sxs-lookup"><span data-stu-id="b6248-105">This virtual environment is known as a MED-V workspace.</span></span>

<span data-ttu-id="b6248-106">Windows 7 に移行する際に、組織が直面するアプリケーションの互換性の要件によっては、特定のユーザーまたは部門のみが、MED-V ワークスペースを必要とする場合があります。</span><span class="sxs-lookup"><span data-stu-id="b6248-106">Depending on the application compatibility requirements faced by your organization as you migrate to Windows 7, only certain users or departments might require MED-V workspaces.</span></span> <span data-ttu-id="b6248-107">展開を計画するときは、企業で必要な MED-V ワークスペースの数を決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6248-107">As you plan your deployment, you have to determine the number of MED-V workspaces required in your enterprise.</span></span> <span data-ttu-id="b6248-108">また、各 MED-V ワークスペースの要件も定義する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6248-108">You also have to define the requirements of each MED-V workspace.</span></span>

## <span data-ttu-id="b6248-109">MED-V ワークスペースの数と種類を特定する</span><span class="sxs-lookup"><span data-stu-id="b6248-109">Identify the Number and Types of MED-V Workspaces</span></span>


<span data-ttu-id="b6248-110">MED-V ワークスペースを作成する企業のコンピューターとグループを特定します。</span><span class="sxs-lookup"><span data-stu-id="b6248-110">Identify the computers and groups in your enterprise for which you will be creating MED-V workspaces.</span></span> <span data-ttu-id="b6248-111">通常、これらは、Windows 7 に移行できないアプリケーションへのアクセスを必要とするユーザーです。</span><span class="sxs-lookup"><span data-stu-id="b6248-111">Typically, these are the users who require access to those applications that cannot be migrated to Windows 7.</span></span> <span data-ttu-id="b6248-112">移行できないアプリケーションと、これらのアプリケーションを実行するために MED-V ワークスペースが必要なユーザーを特定します。</span><span class="sxs-lookup"><span data-stu-id="b6248-112">Identify those applications that cannot be migrated and the users who require a MED-V workspace to run these applications.</span></span>

<span data-ttu-id="b6248-113">さらに、Windows 7 用に最適化されていないイントラネットアドレスがある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b6248-113">You might also have intranet addresses that have not yet been optimized for Windows 7.</span></span> <span data-ttu-id="b6248-114">MED-V ワークスペースには、Internet Explorer ブラウザーが用意されており、Windows 7 に移行する準備がまだできていない web アドレスにエンドユーザーがアクセスできるようになっています。</span><span class="sxs-lookup"><span data-stu-id="b6248-114">The MED-V workspace provides an Internet Explorer browser through which end users can better access those web addresses that are not yet ready for the migration to Windows 7.</span></span> <span data-ttu-id="b6248-115">MED-V の展開を準備および計画する際には、ホストコンピューターの Internet Explorer から MED-V ワークスペースの Internet Explorer にリダイレクトする URL アドレスの一覧を特定してコンパイルする必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6248-115">As you are preparing and planning your MED-V deployment, you will have to identify and compile a list of the URL addresses to redirect from Internet Explorer on the host computer to Internet Explorer in the MED-V workspace.</span></span>

<span data-ttu-id="b6248-116">最後に、ディスク容量の要件を評価する必要があります。</span><span class="sxs-lookup"><span data-stu-id="b6248-116">Finally, you have to evaluate your disk space requirements.</span></span> <span data-ttu-id="b6248-117">ほとんどの MED-V ワークスペースは、2ギガバイト (GB) 以上です。</span><span class="sxs-lookup"><span data-stu-id="b6248-117">Most MED-V workspaces are 2 gigabytes (GB) or larger.</span></span> <span data-ttu-id="b6248-118">システムで利用可能なディスク領域は、ユーザーの数と MED-V の構成によっては、すぐに使うことができます。</span><span class="sxs-lookup"><span data-stu-id="b6248-118">The available disk space on a system can be consumed quickly, depending on the number of users and the configuration of MED-V.</span></span> <span data-ttu-id="b6248-119">また、会社の優先する配布方法では、追加のスペースが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="b6248-119">Also, your company’s preferred method of distribution can require additional space.</span></span> <span data-ttu-id="b6248-120">通常、MED-V ワークスペースを使用するには、少なくとも 10 GB のディスク領域を解放する必要がありますが、画像のサイズによって大きく異なります。</span><span class="sxs-lookup"><span data-stu-id="b6248-120">Generally, you should free a minimum of 10 GB of disk space for a MED-V workspace, but this varies greatly, depending on the size of the image.</span></span>

### <span data-ttu-id="b6248-121">MED-V ワークスペースに必要なディスク領域を計算する</span><span class="sxs-lookup"><span data-stu-id="b6248-121">Calculate the Disk Space Requirements for MED-V Workspaces</span></span>

<span data-ttu-id="b6248-122">MED-V workspace には、インストールされているホストコンピューターのメモリとディスク領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6248-122">A MED-V workspace requires memory and disk space from the host computer on which it is installed.</span></span> <span data-ttu-id="b6248-123">少なくとも、ホストには 2 GB のディスク領域が必要です。</span><span class="sxs-lookup"><span data-stu-id="b6248-123">At a minimum, 2 GB of disk space are required on the host.</span></span> <span data-ttu-id="b6248-124">ディスク領域は可変であり、ユーザーの MED-V ワークスペースのアプリケーションとデータの数によって異なります。</span><span class="sxs-lookup"><span data-stu-id="b6248-124">Disk space is variable and depends on the number of applications and the data in a user’s MED-V workspace.</span></span>

<span data-ttu-id="b6248-125">MED-V には、最低 10 GB のディスク領域をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="b6248-125">We recommend a minimum of 10 GB of disk space for MED-V.</span></span> <span data-ttu-id="b6248-126">この金額は、基本的な Windows XP ワークスペースと、基本的にインストールされたアプリケーションと web リダイレクションを使用できます。</span><span class="sxs-lookup"><span data-stu-id="b6248-126">This amount allows for a basic Windows XP workspace and some basic installed applications and web redirection.</span></span> <span data-ttu-id="b6248-127">また、ホストスワップドライブで利用可能な領域も用意されています。</span><span class="sxs-lookup"><span data-stu-id="b6248-127">It also provides available space for the host swap drive.</span></span> <span data-ttu-id="b6248-128">基本構成では、MED-V と1つの展開された MED-V ワークスペースで、6 ~ 8 GB の範囲で利用できます。</span><span class="sxs-lookup"><span data-stu-id="b6248-128">In a basic configuration, MED-V and a single deployed MED-V workspace consume as much as 6 to 8 GB.</span></span> <span data-ttu-id="b6248-129">MED-V ワークスペースに多数のアプリケーションを含める場合、またはコンピューターあたり複数のユーザーがいる場合は、次の計算を使用して、MED-V ワークスペースで必要なディスク領域をより正確に特定できます。</span><span class="sxs-lookup"><span data-stu-id="b6248-129">If you include lots of applications on the MED-V workspace or have more than one user per computer, then you can use the following calculation to more accurately determine the disk space your MED-V workspace requires:</span></span>

*<span data-ttu-id="b6248-130">ベース VHD + (コンピューターあたり x (差分ディスク + 保存された状態))</span><span class="sxs-lookup"><span data-stu-id="b6248-130">Base VHD + (User per computer x (Difference Disk + Saved State))</span></span>*

<span data-ttu-id="b6248-131">必要なディスク領域を計算するには、次のことを確認します。</span><span class="sxs-lookup"><span data-stu-id="b6248-131">To calculate the required disk space, determine the following:</span></span>

-   <span data-ttu-id="b6248-132">**ベース VHD のサイズ**– med-v ワークスペースの作成に使用された仮想ハードディスク。</span><span class="sxs-lookup"><span data-stu-id="b6248-132">**Size of the base VHD** – the virtual hard disk that was used to create the MED-V workspace.</span></span>

    <span data-ttu-id="b6248-133">**重要** Medv ファイルが圧縮されているため、medv ファイルのサイズを計算に使用しないでください。</span><span class="sxs-lookup"><span data-stu-id="b6248-133">**Important** Do not use the .medv file size for your calculation because the .medv file is compressed.</span></span>

     

-   <span data-ttu-id="b6248-134">[**コンピューターごと**] – med-v は、コンピューター上のユーザーごとに med-v ワークスペースを作成します。MED-V ワークスペースでは、ユーザーがログオンするたびにディスク領域が消費され、MED-V ワークスペースが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6248-134">**Users per computer** – MED-V creates a MED-V workspace for each user on a computer; the MED-V workspace consumes disk space as each user logs on and the MED-V workspace is created.</span></span>

-   <span data-ttu-id="b6248-135">**差分ディスクのサイズ**-基本 VHD との差を追跡するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6248-135">**Size of the differencing disk** – used to track the difference from the base VHD.</span></span> <span data-ttu-id="b6248-136">このサイズは、仮想ハードディスクにアプリケーションとソフトウェア更新プログラムを追加するときに異なります。</span><span class="sxs-lookup"><span data-stu-id="b6248-136">This size varies as you add applications and software updates to the virtual hard disk.</span></span> <span data-ttu-id="b6248-137">差分ディスクは、med-v を初めて起動したときに、各 Hyper-v ユーザーに対して作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6248-137">A differencing disk is created for each MED-V user when they start MED-V for the first time.</span></span>

-   <span data-ttu-id="b6248-138">保存された**状態ファイルのサイズ**。仮想マシンで状態を維持するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="b6248-138">**Size of the Saved State file** – used to maintain state in the virtual machine.</span></span> <span data-ttu-id="b6248-139">通常、これは、仮想マシンに割り当てられている RAM よりわずかに大きくなります。</span><span class="sxs-lookup"><span data-stu-id="b6248-139">Typically, this is just a bit larger than the allocated RAM for the virtual machine.</span></span> <span data-ttu-id="b6248-140">たとえば、1 GB の RAM を割り当てると、1081000 KB のファイルが作成されます。</span><span class="sxs-lookup"><span data-stu-id="b6248-140">For example, 1 GB of RAM allocated creates a file about 1,081,000 KB.</span></span>

<span data-ttu-id="b6248-141">次の例は、2.6 GB の仮想ハードディスクを持つ MED-V ワークスペースの3人のユーザーに基づいて計算したものです。</span><span class="sxs-lookup"><span data-stu-id="b6248-141">The following example shows a calculation based on three users of a MED-V workspace that has a 2.6 GB virtual hard disk:</span></span>

*<span data-ttu-id="b6248-142">2.6 gb + (3 x (1.5 gb + 1gb)) = 10.1 gb</span><span class="sxs-lookup"><span data-stu-id="b6248-142">2.6gb + (3 x (1.5gb + 1gb)) = 10.1gb</span></span>*

<span data-ttu-id="b6248-143">**注** MED-V のベストプラクティスは、ラボ展開を使用して要件を検証することで、必要な領域を計算することです。</span><span class="sxs-lookup"><span data-stu-id="b6248-143">**Note** A MED-V best practice is to calculate the required space by using a lab deployment to validate the requirements.</span></span>

 

### <span data-ttu-id="b6248-144">ファイルのサイズを確認するためのファイルを見つける</span><span class="sxs-lookup"><span data-stu-id="b6248-144">Locate the Files to Determine File Size</span></span>

<span data-ttu-id="b6248-145">次の場所には、コンピューターとユーザー設定のファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="b6248-145">The following locations contain the files for the computer and user settings:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b6248-146">型</span><span class="sxs-lookup"><span data-stu-id="b6248-146">Type</span></span></th>
<th align="left"><span data-ttu-id="b6248-147">位置情報</span><span class="sxs-lookup"><span data-stu-id="b6248-147">Location</span></span></th>
<th align="left"><span data-ttu-id="b6248-148">ファイル</span><span class="sxs-lookup"><span data-stu-id="b6248-148">Files</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b6248-149">ベース VHD</span><span class="sxs-lookup"><span data-stu-id="b6248-149">Base VHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="b6248-150">%ProgramData%\Microsoft\Medv\Workspace</span><span class="sxs-lookup"><span data-stu-id="b6248-150">%ProgramData%\Microsoft\Medv\Workspace</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="b6248-151">InternalName </em> - <em> InternalName </em> は、Med-v ワークスペースパッケージャーで選択した仮想ハードディスクの名前です。</span><span class="sxs-lookup"><span data-stu-id="b6248-151">InternalName</em>.vhd - Where <em>InternalName</em> is the name of the virtual hard disk that you selected in the MED-V Workspace Packager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b6248-152">差分ディスク</span><span class="sxs-lookup"><span data-stu-id="b6248-152">Differencing Disk</span></span></p></td>
<td align="left"><p><span data-ttu-id="b6248-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual マシン</span><span class="sxs-lookup"><span data-stu-id="b6248-153">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="b6248-154">WorkspaceName </em></span><span class="sxs-lookup"><span data-stu-id="b6248-154">WorkspaceName</em>.vhd</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b6248-155">保存された状態ファイル</span><span class="sxs-lookup"><span data-stu-id="b6248-155">Saved State File</span></span></p></td>
<td align="left"><p><span data-ttu-id="b6248-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual マシン</span><span class="sxs-lookup"><span data-stu-id="b6248-156">%LocalAppData%\Microsoft\MEDV\v2\Virtual Machines</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="b6248-157">WorkspaceName </em> vsv</span><span class="sxs-lookup"><span data-stu-id="b6248-157">WorkspaceName</em>.vsv</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="b6248-158">共有の MED-V ワークスペースに必要なディスク領域を計算する</span><span class="sxs-lookup"><span data-stu-id="b6248-158">Calculate the Disk Space Requirements for Shared MED-V Workspaces</span></span>

<span data-ttu-id="b6248-159">1台のコンピューターで共有の MED-V ワークスペースの展開を計算する場合、MED-V では、すべてのユーザーに対して1つの差分ディスクしか構成されていないため、計算でコンピューターあたりのユーザー数は "1" になります。</span><span class="sxs-lookup"><span data-stu-id="b6248-159">If you are calculating for a shared MED-V workspace deployment on a single computer, then the number of users per computer in your calculation is always “1” because MED-V only configures a single differencing disk for all users.</span></span>

<span data-ttu-id="b6248-160">%ProgramData%\\Microsoft\\Medv\\AllUsers. では、差分ディスクと、共有された MED-V ワークスペースの保存された状態ファイルを見つけることができます。</span><span class="sxs-lookup"><span data-stu-id="b6248-160">You can find the differencing disk and the saved state file for shared MED-V workspaces in %ProgramData%\\Microsoft\\Medv\\AllUsers.</span></span>

## <span data-ttu-id="b6248-161">関連トピック</span><span class="sxs-lookup"><span data-stu-id="b6248-161">Related topics</span></span>


[<span data-ttu-id="b6248-162">MED-V 展開を定義して計画する</span><span class="sxs-lookup"><span data-stu-id="b6248-162">Define and Plan your MED-V Deployment</span></span>](define-and-plan-your-med-v-deployment.md)

[<span data-ttu-id="b6248-163">MED-V の計画</span><span class="sxs-lookup"><span data-stu-id="b6248-163">Planning for MED-V</span></span>](planning-for-med-v.md)

 

 





