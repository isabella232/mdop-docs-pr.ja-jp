---
title: UE-V 2.x の概要
description: UE-V 2.x の概要
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823287"
---
# <span data-ttu-id="d5b73-103">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="d5b73-103">Get Started with UE-V 2.x</span></span>


<span data-ttu-id="d5b73-104">このガイドの手順に従って、小規模のテスト環境で Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 をすばやく展開します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-104">Follow the steps in this guide to quickly deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 in a small test environment.</span></span> <span data-ttu-id="d5b73-105">これにより、UE-V が企業内の複数のデバイスでユーザー設定を管理するための適切なソリューションであるかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-105">This helps you determine whether UE-V is the right solution to manage user settings across multiple devices within your enterprise.</span></span>

<span data-ttu-id="d5b73-106">**注** このセクションの情報は、ドキュメントの残りの部分でさらに詳しく説明されています。</span><span class="sxs-lookup"><span data-stu-id="d5b73-106">**Note** The information in this section is repeated in greater detail throughout the rest of the documentation.</span></span> <span data-ttu-id="d5b73-107">つまり、UE-V 2 が適切なソリューションであり、それを評価する必要がないとわかっている場合は、すぐに、 [ue-v 2 x の展開を準備](prepare-a-ue-v-2x-deployment-new-uevv2.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-107">So if you already know that UE-V 2 is the right solution and you don’t need to evaluate it, you can just go right to [Prepare a UE-V 2.x Deployment](prepare-a-ue-v-2x-deployment-new-uevv2.md).</span></span>

 

<span data-ttu-id="d5b73-108">UE-V の標準インストールでは、Microsoft Windows と Office の既定の設定と、多くの Windows アプリの設定が同期されます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-108">The standard installation of UE-V synchronizes the default Microsoft Windows and Office settings and many Windows app settings.</span></span> <span data-ttu-id="d5b73-109">テスト環境に、ネットワークアクセスを共有する2人以上のユーザーコンピューターが含まれていることを確認します。この場合は、短時間でのみ UE-V を評価します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-109">Make sure your test environment includes two or more user computers that share network access and you’ll be evaluating UE-V in just a short time.</span></span>

-   <span data-ttu-id="d5b73-110">[手順 1: 前提条件を確認](#step1)します。サポートされている構成の詳細など、環境が ue-v を実行できることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-110">[Step 1: Confirm Prerequisites](#step1): Make sure your environment is able to run UE-V, including details about supported configurations.</span></span>

-   <span data-ttu-id="d5b73-111">[手順 2: ue-v 2 の設定の保存場所を展開し](#step2)ます。すべての ue-v 展開では、同期された設定値を含む設定パッケージの場所が必要になります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-111">[Step 2: Deploy the Settings Storage Location for UE-V 2](#step2): All UE-V deployments require a location for settings packages that contain the synchronized setting values.</span></span>

-   <span data-ttu-id="d5b73-112">[手順 3: ue-v 2 エージェントを展開](#step3)する: ue-v を使用して設定を同期するには、デバイスで ue-v エージェントをインストールして実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-112">[Step 3: Deploy the UE-V 2 Agent](#step3): To synchronize settings using UE-V, devices must have the UE-V Agent installed and running.</span></span>

-   <span data-ttu-id="d5b73-113">[手順 4: ue-v 2 の評価展開をテスト](#step4)する: ue-v エージェントがインストールされている2台のコンピューターでいくつかのテストを実行し、ue-v のしくみを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-113">[Step 4: Test Your UE-V 2 Evaluation Deployment](#step4): Run a few tests on two computers that have the UE-V Agent installed and see how UE-V works.</span></span>

<span data-ttu-id="d5b73-114">それです！</span><span class="sxs-lookup"><span data-stu-id="d5b73-114">That’s it!</span></span> <span data-ttu-id="d5b73-115">この手順を実行すると、UE-V が企業でどのように機能するかを評価することができます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-115">Once you follow the steps, you’ll be able to evaluate how UE-V can work in your enterprise.</span></span>

<span data-ttu-id="d5b73-116">**さらに詳しい評価:** さらに、一部のサードパーティ製と基幹業務[用の](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)アプリケーションを構成して、ue-v を使って設定を同期するように設定することもできます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-116">**Further evaluation:** You can also perform additional steps to configure some third-party and line-of-business applications to synchronize their settings using UE-V as detailed in [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <a href="" id="step1"></a><span data-ttu-id="d5b73-117">手順 1: 前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="d5b73-117">Step 1: Confirm Prerequisites</span></span>


<span data-ttu-id="d5b73-118">続行する前に、お使いの環境で UE-V を実行するための要件が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5b73-118">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="d5b73-119">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="d5b73-119">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="d5b73-120">エディション</span><span class="sxs-lookup"><span data-stu-id="d5b73-120">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="d5b73-121">Service pack</span><span class="sxs-lookup"><span data-stu-id="d5b73-121">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="d5b73-122">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="d5b73-122">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="d5b73-123">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d5b73-123">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="d5b73-124">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d5b73-124">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d5b73-125">Windows7</span><span class="sxs-lookup"><span data-stu-id="d5b73-125">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-126">Ultimate、Enterprise、または Professional エディション</span><span class="sxs-lookup"><span data-stu-id="d5b73-126">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-127">SP1</span><span class="sxs-lookup"><span data-stu-id="d5b73-127">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-128">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-128">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-129">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-129">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-130">.NET Framework 4 以上</span><span class="sxs-lookup"><span data-stu-id="d5b73-130">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d5b73-131">Windows Server2008R2</span><span class="sxs-lookup"><span data-stu-id="d5b73-131">Windows Server2008R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-132">標準、エンタープライズ、データセンター、または Web サーバー</span><span class="sxs-lookup"><span data-stu-id="d5b73-132">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-133">SP1</span><span class="sxs-lookup"><span data-stu-id="d5b73-133">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-134">64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-134">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-135">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-135">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-136">.NET Framework 4 以上</span><span class="sxs-lookup"><span data-stu-id="d5b73-136">.NET Framework 4 or higher</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d5b73-137">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="d5b73-137">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-138">Enterprise または Pro</span><span class="sxs-lookup"><span data-stu-id="d5b73-138">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-139">なし</span><span class="sxs-lookup"><span data-stu-id="d5b73-139">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-140">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-140">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-141">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-141">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-142">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d5b73-142">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d5b73-143">Windows Server 2012 または Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="d5b73-143">Windows Server 2012 or Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-144">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="d5b73-144">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-145">なし</span><span class="sxs-lookup"><span data-stu-id="d5b73-145">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-146">64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-146">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-147">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-147">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-148">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d5b73-148">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d5b73-149">Windows 10、1607以前の verison</span><span class="sxs-lookup"><span data-stu-id="d5b73-149">Windows 10, pre-1607 verison</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-150">Enterprise または Pro</span><span class="sxs-lookup"><span data-stu-id="d5b73-150">Enterprise or Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="d5b73-151">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-151">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-152">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-152">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-153">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d5b73-153">.NET Framework 4.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d5b73-154">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="d5b73-154">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-155">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="d5b73-155">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-156">なし</span><span class="sxs-lookup"><span data-stu-id="d5b73-156">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-157">64 ビット</span><span class="sxs-lookup"><span data-stu-id="d5b73-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-158">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="d5b73-158">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="d5b73-159">.NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="d5b73-159">.NET Framework 4.5</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="d5b73-160">**注:** Windows 10 バージョン1607以降では、UE-V は[windows 10 For Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)に含まれており、Microsoft デスクトップ最適化パックの一部ではなくなっています。</span><span class="sxs-lookup"><span data-stu-id="d5b73-160">**Note:** Starting with Windows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack</span></span>

<span data-ttu-id="d5b73-161">また。。。</span><span class="sxs-lookup"><span data-stu-id="d5b73-161">Also…</span></span>

-   <span data-ttu-id="d5b73-162">**MDOP ライセンス:** この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="d5b73-162">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="d5b73-163">企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-163">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="d5b73-164">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「MDOP の入手方法」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="d5b73-164">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="d5b73-165">インストールする任意のコンピューターの**管理者資格情報**</span><span class="sxs-lookup"><span data-stu-id="d5b73-165">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

## <a href="" id="step2"></a><span data-ttu-id="d5b73-166">手順 2: UE-V 2 の設定の保存場所を展開する</span><span class="sxs-lookup"><span data-stu-id="d5b73-166">Step 2: Deploy the Settings Storage Location for UE-V 2</span></span>


<span data-ttu-id="d5b73-167">設定のパッケージファイルにユーザー設定が保存されている標準ネットワーク共有である、設定の保存場所を展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-167">You’ll need to deploy a settings storage location, a standard network share where user settings are stored in a settings package file.</span></span> <span data-ttu-id="d5b73-168">設定記憶域共有を作成する場合は、必要なユーザーへのアクセスを制限する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-168">When you create the settings storage share, you should limit access to users that require it.</span></span> <span data-ttu-id="d5b73-169">[設定を展開するストレージの場所の詳細に](https://technet.microsoft.com/library/dn458891.aspx#ssl)ついては、こちらを参照してください。</span><span class="sxs-lookup"><span data-stu-id="d5b73-169">[Deploy a Settings Storage Location](https://technet.microsoft.com/library/dn458891.aspx#ssl) provides more detailed information.</span></span>

**<span data-ttu-id="d5b73-170">ネットワーク共有を作成する</span><span class="sxs-lookup"><span data-stu-id="d5b73-170">Create a network share</span></span>**

1.  <span data-ttu-id="d5b73-171">新しいセキュリティグループを作成し、UE-V ユーザーをそのグループに追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-171">Create a new security group and add UE-V users to it.</span></span>

2.  <span data-ttu-id="d5b73-172">UE-V 設定パッケージが保存されている中央のコンピューターに新しいフォルダーを作成し、そのフォルダーへのグループアクセス許可を使用して、UE-V ユーザーにアクセスを許可します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-172">Create a new folder on the centrally located computer that stores the UE-V settings packages, and then grant the UE-V users access with group permissions to the folder.</span></span> <span data-ttu-id="d5b73-173">UE-V をサポートしている管理者は、この共有フォルダーへのアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-173">The administrator who supports UE-V must have permissions to this shared folder.</span></span>

3.  <span data-ttu-id="d5b73-174">ユーザーが接続したときにディレクトリを作成するためのアクセス許可を UE-V users に割り当てます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-174">Assign UE-V users permission to create a directory when they connect.</span></span> <span data-ttu-id="d5b73-175">そのディレクトリのすべてのサブディレクトリに完全なアクセス許可を付与しますが、上記のいずれにもアクセスをブロックします。</span><span class="sxs-lookup"><span data-stu-id="d5b73-175">Grant full permission to all subdirectories of that directory, but block access to anything above.</span></span>

    1.  <span data-ttu-id="d5b73-176">[設定の保存場所] フォルダーに対して、次の共有レベルのサーバーメッセージブロック (SMB) 権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-176">Set the following share-level Server Message Block (SMB) permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="d5b73-177">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="d5b73-177">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="d5b73-178">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5b73-178">Recommended permissions</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="d5b73-179">すべてのユーザー</span><span class="sxs-lookup"><span data-stu-id="d5b73-179">Everyone</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-180">権限なし</span><span class="sxs-lookup"><span data-stu-id="d5b73-180">No permissions</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="d5b73-181">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="d5b73-181">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-182">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="d5b73-182">Full control</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

    2.  <span data-ttu-id="d5b73-183">[設定の保存場所] フォルダーに、次の NTFS ファイルシステムの権限を設定します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-183">Set the following NTFS file system permissions for the settings storage location folder.</span></span>

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong><span data-ttu-id="d5b73-184">ユーザーアカウント</span><span class="sxs-lookup"><span data-stu-id="d5b73-184">User account</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="d5b73-185">推奨されるアクセス許可</span><span class="sxs-lookup"><span data-stu-id="d5b73-185">Recommended permissions</span></span></strong></th>
        <th align="left"><strong><span data-ttu-id="d5b73-186">Folder</span><span class="sxs-lookup"><span data-stu-id="d5b73-186">Folder</span></span></strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p><span data-ttu-id="d5b73-187">作成者/所有者</span><span class="sxs-lookup"><span data-stu-id="d5b73-187">Creator/owner</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-188">フルコントロール</span><span class="sxs-lookup"><span data-stu-id="d5b73-188">Full control</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-189">サブフォルダーとファイルのみ</span><span class="sxs-lookup"><span data-stu-id="d5b73-189">Subfolders and files only</span></span></p></td>
        </tr>
        <tr class="even">
        <td align="left"><p><span data-ttu-id="d5b73-190">UE-V ユーザーのセキュリティグループ</span><span class="sxs-lookup"><span data-stu-id="d5b73-190">Security group of UE-V users</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-191">フォルダーの一覧/データの読み取り、フォルダーの作成/データの追加を行う</span><span class="sxs-lookup"><span data-stu-id="d5b73-191">List folder/read data, create folders/append data</span></span></p></td>
        <td align="left"><p><span data-ttu-id="d5b73-192">このフォルダーのみ</span><span class="sxs-lookup"><span data-stu-id="d5b73-192">This folder only</span></span></p></td>
        </tr>
        </tbody>
        </table>

         

**<span data-ttu-id="d5b73-193">セキュリティに関するメモ:</span><span class="sxs-lookup"><span data-stu-id="d5b73-193">Security Note:</span></span>**

<span data-ttu-id="d5b73-194">Windows Server オペレーティングシステムを実行しているコンピューターで設定記憶域共有を作成する場合は、UE-V を構成して、ローカル管理者グループまたは現在のユーザーが、設定パッケージが保存されているフォルダーの所有者であるかどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-194">If you create the settings storage share on a computer running a Windows Server operating system, configure UE-V to verify that either the local Administrators group or the current user is the owner of the folder where settings packages are stored.</span></span> <span data-ttu-id="d5b73-195">この追加のセキュリティを有効にするには、Windows Server レジストリエディターで次の設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-195">To enable this additional security, specify this setting in the Windows Server Registry Editor:</span></span>

1.  <span data-ttu-id="d5b73-196">**"RepositoryOwnerCheckEnabled"** という名前の**REG \ _DWORD**のレジストリキーを**HKEY \ _LOCAL \ _MACHINE ¥**$ ¥の設定に追加します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-196">Add a **REG\_DWORD** registry key named **"RepositoryOwnerCheckEnabled"** to **HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\UEV\\Agent\\Configuration**.</span></span>

2.  <span data-ttu-id="d5b73-197">レジストリキーの値を*1*に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-197">Set the registry key value to *1*.</span></span>

## <a href="" id="step3"></a><span data-ttu-id="d5b73-198">手順 3: UE-V 2 エージェントを展開する</span><span class="sxs-lookup"><span data-stu-id="d5b73-198">Step 3: Deploy the UE-V 2 Agent</span></span>


<span data-ttu-id="d5b73-199">UE-V Agent は、ユーザーのコンピューターとデバイスの間でアプリケーションと Windows の設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-199">The UE-V Agent synchronizes application and Windows settings between users’ computers and devices.</span></span> <span data-ttu-id="d5b73-200">評価目的で、同じユーザーに属するテスト環境の少なくとも2台のコンピューターにエージェントをインストールします。</span><span class="sxs-lookup"><span data-stu-id="d5b73-200">For evaluation purposes, install the agent on at least two computers in your test environment that belong to the same user.</span></span>

<span data-ttu-id="d5b73-201">コマンドラインから AgentSetup.exe ファイルを実行して、UE-V Agent をインストールします。</span><span class="sxs-lookup"><span data-stu-id="d5b73-201">Run the AgentSetup.exe file from the command line to install the UE-V Agent.</span></span> <span data-ttu-id="d5b73-202">これは、32ビットと64ビットの両方のオペレーティングシステムにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-202">It installs on both 32-bit and 64-bit operating systems.</span></span>

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

<span data-ttu-id="d5b73-203">手順2でネットワーク共有として SettingsStoragePath コマンドラインパラメーターを指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d5b73-203">You must specify the SettingsStoragePath command line parameter as the network share from Step 2.</span></span> <span data-ttu-id="d5b73-204">[Ue-v agent を展開すると、](https://technet.microsoft.com/library/dn458891.aspx#agent)詳細な情報が提供されます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-204">[Deploy a UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more detailed information.</span></span>

## <a href="" id="step4"></a><span data-ttu-id="d5b73-205">手順 4: UE-V 2 の評価展開をテストする</span><span class="sxs-lookup"><span data-stu-id="d5b73-205">Step 4: Test Your UE-V 2 Evaluation Deployment</span></span>


<span data-ttu-id="d5b73-206">Ue-v の評価展開でいくつかのテストを実行できるようになりました。 UE-V のしくみについて説明します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-206">You can now run a few tests on your UE-V evaluation deployment to see how UE-V works.</span></span>

****

1.  <span data-ttu-id="d5b73-207">1台目のコンピューター (コンピューター A) で、次のような変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-207">On the first computer (Computer A), make one or more of these changes:</span></span>

    1.  <span data-ttu-id="d5b73-208">Windows デスクトップを開き、タスクバーをウィンドウの別の場所に移動します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-208">Open to Windows Desktop and move the taskbar to a different location in the window.</span></span>

    2.  <span data-ttu-id="d5b73-209">既定のフォントを変更します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-209">Change the default fonts.</span></span>

    3.  <span data-ttu-id="d5b73-210">電卓を開き、[**指数**] に設定します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-210">Open Calculator and set to **scientific**.</span></span>

    4.  <span data-ttu-id="d5b73-211">Windows [PowerShell と WMI を使った ue-v の設定の場所テンプレートの管理](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)に関する説明に従って、windows アプリの動作を変更します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-211">Change the behavior of any Windows app, as detailed in [Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    5.  <span data-ttu-id="d5b73-212">Microsoft アカウント設定の同期とローミングプロファイルを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d5b73-212">Disable Microsoft Account settings synchronization and Roaming Profiles.</span></span>

2.  <span data-ttu-id="d5b73-213">コンピューターからログオフする設定は、ユーザーがロック、ログオフ、アプリケーションの終了時、または同期プロバイダーの実行時 (既定では30分ごと) に、UE-V 設定パッケージに保存されます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-213">Log off Computer A. Settings are saved in a UE-V settings package when users lock, logoff, exit an application, or when the sync provider runs (every 30 minutes by default).</span></span>

3.  <span data-ttu-id="d5b73-214">2台目のコンピューター (コンピューター B) に、コンピューター A と同じユーザーとしてログインします。</span><span class="sxs-lookup"><span data-stu-id="d5b73-214">Log in to the second computer (Computer B) as the same user as Computer A.</span></span>

4.  <span data-ttu-id="d5b73-215">Windows デスクトップを開き、タスクバーの場所がコンピューター A と一致することを確認します。既定のフォントが一致していること、および電卓が [**指数**] に設定されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-215">Open to Windows Desktop and verify that the taskbar location matches that of Computer A. Verify that the default fonts match and that Calculator is set to **scientific**.</span></span> <span data-ttu-id="d5b73-216">また、Windows アプリに加えた変更も確認してください。</span><span class="sxs-lookup"><span data-stu-id="d5b73-216">Also verify the change you made to any Windows app.</span></span>

<span data-ttu-id="d5b73-217">コンピューター B の設定を元のコンピューターに戻すことができます。</span><span class="sxs-lookup"><span data-stu-id="d5b73-217">You can change the settings in Computer B back to the original Computer A settings.</span></span> <span data-ttu-id="d5b73-218">次に、コンピューター B をログオフし、コンピューター A にログインして変更を確認します。</span><span class="sxs-lookup"><span data-stu-id="d5b73-218">Then log off Computer B and log in to Computer A to verify the changes.</span></span>

## <span data-ttu-id="d5b73-219">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="d5b73-219">Other resources for this product</span></span>


-   [<span data-ttu-id="d5b73-220">Microsoft User Experience Virtualization (UE-V) 2. x</span><span class="sxs-lookup"><span data-stu-id="d5b73-220">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="d5b73-221">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="d5b73-221">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="d5b73-222">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="d5b73-222">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="d5b73-223">UE-V 2. x のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="d5b73-223">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="d5b73-224">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="d5b73-224">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





