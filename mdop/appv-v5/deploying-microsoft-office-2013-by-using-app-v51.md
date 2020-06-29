---
title: APP-V を使用した Microsoft Office 2013 の展開
description: APP-V を使用した Microsoft Office 2013 の展開
author: dansimp
ms.assetid: 9a7be05e-2a7a-4874-af25-09c0f5037876
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: f6a54cadce79ff3680fd69206eba8ac3fbe83a68
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814627"
---
# <span data-ttu-id="66f19-103">APP-V を使用した Microsoft Office 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="66f19-103">Deploying Microsoft Office 2013 by Using App-V</span></span>


<span data-ttu-id="66f19-104">この記事の情報は、Microsoft Application Virtualization (App-v) 5.1 以降のバージョンを使用して、Microsoft Office 2013 を仮想化されたアプリケーションとして組織内のコンピューターに配信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-104">Use the information in this article to use Microsoft Application Virtualization (App-V) 5.1, or later versions, to deliver Microsoft Office 2013 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="66f19-105">Office 2010 を提供するために app-v を使用する方法については、「 [App-v を使用して Microsoft Office 2010 を展開](deploying-microsoft-office-2010-by-using-app-v51.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f19-105">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v51.md).</span></span> <span data-ttu-id="66f19-106">App-v を使用して Office 2013 を正常に展開するには、Office 2013 とアプリについて理解している必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-106">To successfully deploy Office 2013 with App-V, you need to be familiar with Office 2013 and App-V.</span></span>

<span data-ttu-id="66f19-107">ここでは、以下のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66f19-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="66f19-108">始める前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="66f19-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="66f19-109">Office 展開ツールを使用して、App-v 用の Office 2013 パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="66f19-109">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="66f19-110">Office パッケージを App-v で公開する-V 5.1</span><span class="sxs-lookup"><span data-stu-id="66f19-110">Publishing the Office package for App-V 5.1</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="66f19-111">Office App-v パッケージのカスタマイズと管理</span><span class="sxs-lookup"><span data-stu-id="66f19-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="66f19-112">始める前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="66f19-112">What to know before you start</span></span>


<span data-ttu-id="66f19-113">App-v を使用して Office 2013 を展開する前に、次の計画情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="66f19-113">Before you deploy Office 2013 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="66f19-114">サポートされている Office のバージョンと Office の共存</span><span class="sxs-lookup"><span data-stu-id="66f19-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="66f19-115">次の表を使用して、サポートされているバージョンの Office と、共存バージョンの Office の実行に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="66f19-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-116">レビューする情報</span><span class="sxs-lookup"><span data-stu-id="66f19-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="66f19-117">説明</span><span class="sxs-lookup"><span data-stu-id="66f19-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="66f19-118">APP-V で Office を使用するための計画</span><span class="sxs-lookup"><span data-stu-id="66f19-118">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-119">サポートされている Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="66f19-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="66f19-120">サポートされている展開の種類 (デスクトップ、個人用仮想デスクトップインフラストラクチャ (VDI)、プールされた VDI)</span><span class="sxs-lookup"><span data-stu-id="66f19-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="66f19-121">Office のライセンスオプション</span><span class="sxs-lookup"><span data-stu-id="66f19-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with Office](planning-for-using-app-v-with-office51.md#bkmk-plan-coexisting)"><span data-ttu-id="66f19-122">APP-V で Office を使用するための計画</span><span class="sxs-lookup"><span data-stu-id="66f19-122">Planning for Using App-V with Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="66f19-123">異なるバージョンの Office を同じコンピューターにインストールする場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="66f19-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>


### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="66f19-124">パッケージ化、発行、展開の要件</span><span class="sxs-lookup"><span data-stu-id="66f19-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="66f19-125">App-v を使用して Office を展開する前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="66f19-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-126">タスク</span><span class="sxs-lookup"><span data-stu-id="66f19-126">Task</span></span></th>
<th align="left"><span data-ttu-id="66f19-127">要件</span><span class="sxs-lookup"><span data-stu-id="66f19-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-128">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="66f19-128">Packaging</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-129">ユーザーに展開するすべての Office アプリケーションが1つのパッケージに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="66f19-130">App-v 5.1 以降では、Office 展開ツールを使用してパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-130">In App-V 5.1 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="66f19-131">Sequencer は使用できません。</span><span class="sxs-lookup"><span data-stu-id="66f19-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="66f19-132">Microsoft Visio 2013 と Microsoft Project 2013 を Office と共に展開する場合は、それらを Office と同じパッケージに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-132">If you are deploying Microsoft Visio 2013 and Microsoft Project 2013 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="66f19-133">詳細については、「 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)"> Visio 2013 および Project 2013 を Office と共に展開する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2013 and Project 2013 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2013 and Project 2013 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-134">Publishing</span><span class="sxs-lookup"><span data-stu-id="66f19-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-135">各クライアントコンピューターには、1つの Office パッケージのみを公開できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="66f19-136">Office パッケージをグローバルに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-136">You must publish the Office package globally.</span></span> <span data-ttu-id="66f19-137">ユーザーに公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="66f19-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-138">次の製品を共有コンピューターに展開する (たとえば、リモートデスクトップサービスを使用する)。</span><span class="sxs-lookup"><span data-stu-id="66f19-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="66f19-139">エンタープライズ向けの Microsoft 365 アプリ</span><span class="sxs-lookup"><span data-stu-id="66f19-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="66f19-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="66f19-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="66f19-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="66f19-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="66f19-142">共有コンピューターのライセンス認証を有効にする必要があり <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="66f19-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
<p><span data-ttu-id="66f19-143">次のようなボリュームライセンス製品を展開している場合は、共有コンピューターのライセンス認証は使用されません。</span><span class="sxs-lookup"><span data-stu-id="66f19-143">You don’t use shared computer activation if you’re deploying a volume licensed product, such as:</span></span></p>
<ul>
<li><p><span data-ttu-id="66f19-144">Office Professional Plus 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-144">Office Professional Plus 2013</span></span></p></li>
<li><p><span data-ttu-id="66f19-145">Visio Professional 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-145">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="66f19-146">Project Professional 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-146">Project Professional 2013</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="66f19-147">パッケージからの Office アプリケーションの除外</span><span class="sxs-lookup"><span data-stu-id="66f19-147">Excluding Office applications from a package</span></span>

<span data-ttu-id="66f19-148">次の表では、特定の Office アプリケーションをパッケージから除外するための推奨される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66f19-148">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-149">タスク</span><span class="sxs-lookup"><span data-stu-id="66f19-149">Task</span></span></th>
<th align="left"><span data-ttu-id="66f19-150">詳細</span><span class="sxs-lookup"><span data-stu-id="66f19-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-151"><strong> </strong> Office 展開ツールを使用してパッケージを作成する場合は、excludeapp 設定を使います。</span><span class="sxs-lookup"><span data-stu-id="66f19-151">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-152">Office 展開ツールがパッケージを作成するときに、特定の Office アプリケーションをパッケージから除外できるようにします。</span><span class="sxs-lookup"><span data-stu-id="66f19-152">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="66f19-153">たとえば、この設定を使って、Microsoft Word のみを含むパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-153">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="66f19-154">詳細については、「excludeapp 要素」を参照してください <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-154">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-155">DeploymentConfig.xml ファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="66f19-155">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-156">パッケージを作成した後で DeploymentConfig.xml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="66f19-156">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="66f19-157">このファイルには、App-v クライアントを実行しているコンピューター上のすべてのユーザーの既定のパッケージ設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66f19-157">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="66f19-158">詳細については、「 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)"> Office 2013 アプリケーションを無効にする」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-158">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2013 applications](#bkmk-disable-office-apps)">Disabling Office 2013 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="66f19-159">Office 展開ツールを使用して、App-v 用の Office 2013 パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="66f19-159">Creating an Office 2013 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="66f19-160">次の手順を実行して、App-v 5.1 以降の Office 2013 パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-160">Complete the following steps to create an Office 2013 package for App-V 5.1 or later.</span></span>

**<span data-ttu-id="66f19-161">重要</span><span class="sxs-lookup"><span data-stu-id="66f19-161">Important</span></span>**  
<span data-ttu-id="66f19-162">App-v 5.1 以降では、Office 展開ツールを使用してパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-162">In App-V 5.1 and later, you must the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="66f19-163">Sequencer を使ってパッケージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="66f19-163">You cannot use the Sequencer to create packages.</span></span>



### <span data-ttu-id="66f19-164">Office 展開ツールを使用するための前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="66f19-164">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="66f19-165">Office 展開ツールをインストールするコンピューターには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="66f19-165">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-166">受講</span><span class="sxs-lookup"><span data-stu-id="66f19-166">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="66f19-167">説明</span><span class="sxs-lookup"><span data-stu-id="66f19-167">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-168">必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="66f19-168">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-169">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="66f19-169">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-170">サポートされているオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="66f19-170">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66f19-171">64ビット版の Windows 8 以降</span><span class="sxs-lookup"><span data-stu-id="66f19-171">64-bit version of Windows 8 or later</span></span></p></li>
<li><p><span data-ttu-id="66f19-172">64ビット版の Windows 7</span><span class="sxs-lookup"><span data-stu-id="66f19-172">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="66f19-173">注</span><span class="sxs-lookup"><span data-stu-id="66f19-173">Note</span></span>**  
<span data-ttu-id="66f19-174">このトピックでは、"Office 2013 App-v パッケージ" という用語は、サブスクリプションのライセンスとボリュームライセンスを指します。</span><span class="sxs-lookup"><span data-stu-id="66f19-174">In this topic, the term “Office 2013 App-V package” refers to subscription licensing and volume licensing.</span></span>



### <span data-ttu-id="66f19-175">Office 展開ツールを使用して Office 2013 App-v パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="66f19-175">Create Office 2013 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="66f19-176">Office 2013 App-v パッケージを作成するには、Office 展開ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-176">You create Office 2013 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="66f19-177">次の手順では、ボリュームライセンスまたはサブスクリプションライセンスを使用して Office 2013 App-v パッケージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="66f19-177">The following instructions explain how to create an Office 2013 App-V package with Volume Licensing or Subscription Licensing.</span></span>

<span data-ttu-id="66f19-178">64ビットの Windows コンピューター上で Office 2013 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-178">Create Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="66f19-179">作成された Office 2013 App-v パッケージは、32ビットおよび64ビットの Windows 7、Windows 8.1、Windows 10 のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="66f19-179">Once created, the Office 2013 App-V package will run on 32-bit and 64-bit Windows 7, Windows 8.1, and Windows 10 computers.</span></span>

### <span data-ttu-id="66f19-180">Office 展開ツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="66f19-180">Download the Office Deployment Tool</span></span>

<span data-ttu-id="66f19-181">Office 2013 App-v パッケージは、office 展開ツールを使って作成されます。このパッケージは、office 2013 App-v パッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-181">Office 2013 App-V Packages are created using the Office Deployment Tool, which generates an Office 2013 App-V Package.</span></span> <span data-ttu-id="66f19-182">App-v sequencer でパッケージを作成または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="66f19-182">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="66f19-183">パッケージの作成を開始するには:</span><span class="sxs-lookup"><span data-stu-id="66f19-183">To begin package creation:</span></span>

1.  <span data-ttu-id="66f19-184">[クイック実行用の Office 展開ツールを](https://www.microsoft.com/download/details.aspx?id=36778)ダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="66f19-184">Download the [Office Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=36778).</span></span>

2.  <span data-ttu-id="66f19-185">.Exe ファイルを実行し、目的の場所にその機能を抽出します。</span><span class="sxs-lookup"><span data-stu-id="66f19-185">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="66f19-186">このプロセスをより簡単にするために、機能を保存する共有ネットワークフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-186">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    <span data-ttu-id="66f19-187">例: \\ ¥ server \\ office2013</span><span class="sxs-lookup"><span data-stu-id="66f19-187">Example: \\\\Server\\Office2013</span></span>

3.  <span data-ttu-id="66f19-188">setup.exe と configuration.xml ファイルが存在し、指定した場所にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-188">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="66f19-189">Office 2013 アプリケーションをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="66f19-189">Download Office 2013 applications</span></span>

<span data-ttu-id="66f19-190">Office 展開ツールをダウンロードしたら、それを使って最新の Office 2013 アプリケーションを入手できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-190">After you download the Office Deployment Tool, you can use it to get the latest Office 2013 applications.</span></span> <span data-ttu-id="66f19-191">Office アプリケーションを入手したら、Office 2013 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-191">After getting the Office applications, you create the Office 2013 App-V package.</span></span>

<span data-ttu-id="66f19-192">Office 展開ツールに含まれている XML ファイルでは、対象となる言語や Office アプリケーションなどの製品の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="66f19-192">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1.  <span data-ttu-id="66f19-193">**サンプルの XML 構成ファイルをカスタマイズします。** Office 展開ツールと共にダウンロードしたサンプル XML 構成ファイルを使用して、Office アプリケーションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="66f19-193">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

    1.  <span data-ttu-id="66f19-194">メモ帳またはお気に入りのテキストエディターでサンプル XML ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="66f19-194">Open the sample XML file in Notepad or your favorite text editor.</span></span>

    2.  <span data-ttu-id="66f19-195">サンプルの configuration.xml ファイルを開いて編集する準備ができたら、製品、言語、Office 2013 アプリケーションの保存先のパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-195">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2013 applications.</span></span> <span data-ttu-id="66f19-196">configuration.xml ファイルの基本的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="66f19-196">The following is a basic example of the configuration.xml file:</span></span>

        ```xml
        <Configuration>
           <Add SourcePath= ”\\Server\Office2013” OfficeClientEdition="32" >
            <Product ID="O365ProPlusRetail ">
              <Language ID="en-us" />
            </Product>
            <Product ID="VisioProRetail">
              <Language ID="en-us" />
            </Product>
          </Add>
        </Configuration>
        ```

        **<span data-ttu-id="66f19-197">注</span><span class="sxs-lookup"><span data-stu-id="66f19-197">Note</span></span>**  
        <span data-ttu-id="66f19-198">構成 XML はサンプルの XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="66f19-198">The configuration XML is a sample XML file.</span></span> <span data-ttu-id="66f19-199">ファイルには、コメントアウトされた行が含まれています。ファイルを使用して追加の設定をカスタマイズするには、これらの行のコメントを解除します。</span><span class="sxs-lookup"><span data-stu-id="66f19-199">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span>



~~~
    The above XML configuration file specifies that Office 2013 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2013, which is the location where Office applications will be saved to. Note that the Product ID of the applications will not affect the final licensing of Office. Office 2013 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage. The table below summarizes the customizable attributes and elements of XML file:

    <table>
    <colgroup>
    <col width="33%" />
    <col width="33%" />
    <col width="33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">Input</th>
    <th align="left">Description</th>
    <th align="left">Example</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>Add element</p></td>
    <td align="left"><p>Specifies the products and languages to include in the package.</p></td>
    <td align="left"><p>N/A</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>OfficeClientEdition (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the edition of Office 2013 product to use: 32-bit or 64-bit. The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</p></td>
    <td align="left"><p><strong>OfficeClientEdition</strong>=&quot;32&quot;</p>
    <p><strong>OfficeClientEdition</strong>=&quot;64&quot;</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Product element</p></td>
    <td align="left"><p>Specifies the application. Project 2013 and Visio 2013 must be specified here as an added product to be included in the applications.</p></td>
    <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
    <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
    <p><code>Product ID =&quot;ProPlusVolume&quot;</code></p>
    <p><code>Product ID =&quot;VisioProVolume&quot;</code></p>
    <p><code>Product ID = &quot;ProjectProVolume&quot;</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Language element</p></td>
    <td align="left"><p>Specifies the language supported in the applications</p></td>
    <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Version (attribute of Add element)</p></td>
    <td align="left"><p>Optional. Specifies a build to use for the package</p>
    <p>Defaults to latest advertised build (as defined in v32.CAB at the Office source).</p></td>
    <td align="left"><p><code>15.1.2.3</code></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>SourcePath (attribute of Add element)</p></td>
    <td align="left"><p>Specifies the location in which the applications will be saved to.</p></td>
    <td align="left"><p><code>Sourcepath = &quot;\\Server\Office2013”</code></p></td>
    </tr>
    </tbody>
    </table>



    After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2013 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.
~~~

2. <span data-ttu-id="66f19-200">**指定した場所にアプリケーションをダウンロードします。** 昇格したコマンドプロンプトと64ビットのオペレーティングシステムを使って、後で App-v パッケージに変換される Office 2013 アプリケーションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="66f19-200">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2013 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="66f19-201">以下は、詳細を説明するコマンドの例です。</span><span class="sxs-lookup"><span data-stu-id="66f19-201">Below is an example command with description of details:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /download \\server\Office2013\Customconfig.xml
   ```

   <span data-ttu-id="66f19-202">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="66f19-202">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-203">\ \ office office 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-203">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-204">は、Office 展開ツールとカスタム Configuration.xml ファイル (Customconfig.xml を含むネットワーク共有の場所です。</span><span class="sxs-lookup"><span data-stu-id="66f19-204">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-205">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="66f19-205">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-206">は Office 展開ツールです。</span><span class="sxs-lookup"><span data-stu-id="66f19-206">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-207">/download</span><span class="sxs-lookup"><span data-stu-id="66f19-207">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-208">customConfig.xml ファイルで指定した Office 2013 アプリケーションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="66f19-208">downloads the Office 2013 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="66f19-209">これらの bits は、ボリュームライセンスを持つ Office 2013 App-v パッケージで後で変換することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-209">These bits can be later converted in an Office 2013 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-210">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="66f19-210">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-211">ダウンロードプロセスを完了するために必要な XML 構成ファイルを渡します。この例では、customconfig.xml を実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-211">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="66f19-212">[ダウンロード] コマンドを使用した後、Office アプリケーションは、構成 xml ファイルで指定されている場所 (この例では \ \ Office 2013 2013) にあります。</span><span class="sxs-lookup"><span data-stu-id="66f19-212">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2013.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="66f19-213">Office アプリケーションを App-v パッケージに変換する</span><span class="sxs-lookup"><span data-stu-id="66f19-213">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="66f19-214">Office 展開ツールを使用して Office 2013 アプリケーションをダウンロードした後、Office 展開ツールを使用して office 2013 App-v パッケージに変換します。</span><span class="sxs-lookup"><span data-stu-id="66f19-214">After you download the Office 2013 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2013 App-V package.</span></span> <span data-ttu-id="66f19-215">ライセンスモデルに対応する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-215">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="66f19-216">必要な作業の概要:</span><span class="sxs-lookup"><span data-stu-id="66f19-216">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="66f19-217">64ビットの Windows コンピューター上で Office 2013 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-217">Create the Office 2013 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="66f19-218">ただし、パッケージは、32ビットおよび64ビットの Windows 7、Windows 8、Windows 10 のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="66f19-218">However, the package will run on 32-bit and 64-bit Windows 7, Windows 8, and Windows 10 computers.</span></span>

-   <span data-ttu-id="66f19-219">Office 展開ツールを使用してサブスクリプションライセンスパッケージまたはボリュームライセンスの Office App-v パッケージを作成し、CustomConfig.xml 構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="66f19-219">Create an Office App-V package for either Subscription Licensing package or Volume Licensing by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="66f19-220">次の表は、使用しているライセンスモデルの CustomConfig.xml ファイルに入力する必要がある値をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="66f19-220">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="66f19-221">表に記載されているセクションの手順では、実行する必要がある正確なエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="66f19-221">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-222">製品 ID</span><span class="sxs-lookup"><span data-stu-id="66f19-222">Product ID</span></span></th>
<th align="left"><span data-ttu-id="66f19-223">ボリューム ライセンス</span><span class="sxs-lookup"><span data-stu-id="66f19-223">Volume Licensing</span></span></th>
<th align="left"><span data-ttu-id="66f19-224">サブスクリプションのライセンス</span><span class="sxs-lookup"><span data-stu-id="66f19-224">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66f19-225">Office 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-225">Office 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66f19-226">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-226">ProPlusVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-227">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-227">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66f19-228">Visio 2013 での Office 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-228">Office 2013 with Visio 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66f19-229">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-229">ProPlusVolume</span></span></p>
<p><span data-ttu-id="66f19-230">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-230">VisioProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-231">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-231">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="66f19-232">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-232">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66f19-233">Office 2013 と Visio 2013、および Project 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-233">Office 2013 with Visio 2013 and Project 2013</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66f19-234">ProPlusVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-234">ProPlusVolume</span></span></p>
<p><span data-ttu-id="66f19-235">VisioProVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-235">VisioProVolume</span></span></p>
<p><span data-ttu-id="66f19-236">ProjectProVolume</span><span class="sxs-lookup"><span data-stu-id="66f19-236">ProjectProVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-237">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-237">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="66f19-238">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-238">VisioProRetail</span></span></p>
<p><span data-ttu-id="66f19-239">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="66f19-239">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="66f19-240">Office アプリケーションを App-v パッケージに変換する方法</span><span class="sxs-lookup"><span data-stu-id="66f19-240">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="66f19-241">メモ帳で CustomConfig.xml ファイルをもう一度開き、ファイルに次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="66f19-241">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="66f19-242">パラメーター</span><span class="sxs-lookup"><span data-stu-id="66f19-242">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="66f19-243">値を次のように変更する</span><span class="sxs-lookup"><span data-stu-id="66f19-243">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="66f19-244">SourcePath</span><span class="sxs-lookup"><span data-stu-id="66f19-244">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="66f19-245">前にダウンロードした Office アプリケーションをポイントします。</span><span class="sxs-lookup"><span data-stu-id="66f19-245">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="66f19-246">ProductID</span><span class="sxs-lookup"><span data-stu-id="66f19-246">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="66f19-247">次の例に示すように、ライセンスの種類を指定します。</span><span class="sxs-lookup"><span data-stu-id="66f19-247">Specify the type of licensing, as shown in the following examples:</span></span></p>
   <ul>
   <li><p><span data-ttu-id="66f19-248">サブスクリプションのライセンス</span><span class="sxs-lookup"><span data-stu-id="66f19-248">Subscription Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="66f19-249">この例では、サブスクリプションのライセンスを持つパッケージを作成するために、次の変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="66f19-249">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-250">SourcePath</span><span class="sxs-lookup"><span data-stu-id="66f19-250">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-251">は、以前にダウンロードした Office アプリケーションを指すように変更されたパスです。</span><span class="sxs-lookup"><span data-stu-id="66f19-251">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-252">製品 ID</span><span class="sxs-lookup"><span data-stu-id="66f19-252">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-253">Office のはに変更されました <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-253">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-254">製品 ID</span><span class="sxs-lookup"><span data-stu-id="66f19-254">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-255">がに変更されました <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-255">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   <li><p><span data-ttu-id="66f19-256">ボリューム ライセンス</span><span class="sxs-lookup"><span data-stu-id="66f19-256">Volume Licensing</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\Server\Office2013&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;ProPlusVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProVolume&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt;</code></pre>
   <p><span data-ttu-id="66f19-257">この例では、ボリュームライセンスを使用したパッケージを作成するために、次の変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="66f19-257">In this example, the following changes were made to create a package with Volume licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-258">SourcePath</span><span class="sxs-lookup"><span data-stu-id="66f19-258">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-259">は、以前にダウンロードした Office アプリケーションを指すように変更されたパスです。</span><span class="sxs-lookup"><span data-stu-id="66f19-259">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-260">製品 ID</span><span class="sxs-lookup"><span data-stu-id="66f19-260">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-261">Office のはに変更されました <code>ProPlusVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-261">for Office was changed to <code>ProPlusVolume</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-262">製品 ID</span><span class="sxs-lookup"><span data-stu-id="66f19-262">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-263">がに変更されました <code>VisioProVolume</code> 。</span><span class="sxs-lookup"><span data-stu-id="66f19-263">for Visio was changed to <code>VisioProVolume</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p> </p>
   <p></p></li>
   </ul></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="66f19-264">ExcludeApp (省略可能)</span><span class="sxs-lookup"><span data-stu-id="66f19-264">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="66f19-265">Office 展開ツールによって作成される App-v パッケージに含まれない Office プログラムを指定できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-265">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="66f19-266">たとえば、Access や InfoPath を除外することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-266">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="66f19-267">PACKAGEGUID (省略可能)</span><span class="sxs-lookup"><span data-stu-id="66f19-267">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="66f19-268">既定では、Office 展開ツールによって作成されたすべての App-v パッケージは、同じアプリ-V パッケージ ID を共有します。</span><span class="sxs-lookup"><span data-stu-id="66f19-268">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="66f19-269">PACKAGEGUID を使用して、各パッケージに異なるパッケージ ID を指定することができます。これにより、Office 展開ツールによって作成された複数の App-v パッケージを公開して、アプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-269">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="66f19-270">このパラメーターを使用する場合の例として、さまざまなユーザーに対して異なるパッケージを作成する場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="66f19-270">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="66f19-271">たとえば、一部のユーザーについては Office 2013 だけでパッケージを作成し、別のユーザーには Office 2013 と Visio 2013 を使用して別のパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-271">For example, you can create a package with just Office 2013 for some users, and create another package with Office 2013 and Visio 2013 for another set of users.</span></span></p>
   <div class="alert">
   <strong><span data-ttu-id="66f19-272">注</span><span class="sxs-lookup"><span data-stu-id="66f19-272">Note</span></span></strong><br/><p><span data-ttu-id="66f19-273">一意のパッケージ Id を使用している場合でも、1つのデバイスに1つの App-v パッケージを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-273">Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span></p>
   </div>
   <div>

   </div></td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="66f19-274">Office アプリケーションを Office 2013 App-v パッケージに変換するには、/パッケージャーコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-274">Use the /packager command to convert the Office applications to an Office 2013 App-V package.</span></span>

   <span data-ttu-id="66f19-275">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="66f19-275">For example:</span></span>

   ``` syntax
   \\server\Office2013\setup.exe /packager \\server\Office2013\Customconfig.xml  \\server\share\Office2013AppV
   ```

   <span data-ttu-id="66f19-276">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="66f19-276">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-277">\ \ office office 2013</span><span class="sxs-lookup"><span data-stu-id="66f19-277">\server\Office2013</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-278">は、Office 展開ツールとカスタム Configuration.xml ファイル (Customconfig.xml を含むネットワーク共有の場所です。</span><span class="sxs-lookup"><span data-stu-id="66f19-278">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-279">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="66f19-279">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-280">は Office 展開ツールです。</span><span class="sxs-lookup"><span data-stu-id="66f19-280">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-281">/パッケージャー</span><span class="sxs-lookup"><span data-stu-id="66f19-281">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-282">customConfig.xml ファイルで指定されているように、ボリュームライセンスを使用して Office 2013 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-282">creates the Office 2013 App-V package with Volume Licensing as specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="66f19-283">\server\Office2013\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="66f19-283">\server\Office2013\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-284">パッケージステージの準備が整った構成 XML ファイル (この場合は、customConfig) を渡します。</span><span class="sxs-lookup"><span data-stu-id="66f19-284">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="66f19-285">\ \ sharepoint/Office 2013AppV</span><span class="sxs-lookup"><span data-stu-id="66f19-285">\server\share\Office 2013AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="66f19-286">新しく作成された Office App-v パッケージの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="66f19-286">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2013 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note**  
To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="66f19-287">Office 2013 App-v パッケージが正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-287">Verify that the Office 2013 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="66f19-288">グローバルに作成した Office 2013 App-v パッケージをテストコンピューターに発行し、Office 2013 のショートカットが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-288">Publish the Office 2013 App-V package, which you created globally, to a test computer, and verify that the Office 2013 shortcuts appear.</span></span>

   2.  <span data-ttu-id="66f19-289">いくつかの Office 2013 アプリケーション (Excel や Word など) を起動して、パッケージが期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-289">Start a few Office 2013 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="66f19-290">Office パッケージを App-v で公開する-V 5.1</span><span class="sxs-lookup"><span data-stu-id="66f19-290">Publishing the Office package for App-V 5.1</span></span>


<span data-ttu-id="66f19-291">Office パッケージを公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-291">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="66f19-292">Office App-v パッケージを発行するためのメソッド</span><span class="sxs-lookup"><span data-stu-id="66f19-292">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="66f19-293">他のパッケージと同じ方法を使用して、Office 2013 用の App-v パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-293">Deploy the App-V package for Office 2013 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="66f19-294">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66f19-294">System Center Configuration Manager</span></span>

-   <span data-ttu-id="66f19-295">App-v Server</span><span class="sxs-lookup"><span data-stu-id="66f19-295">App-V Server</span></span>

-   <span data-ttu-id="66f19-296">PowerShell コマンドを使用したスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="66f19-296">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="66f19-297">発行の前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="66f19-297">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-298">前提条件または要件</span><span class="sxs-lookup"><span data-stu-id="66f19-298">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="66f19-299">詳細</span><span class="sxs-lookup"><span data-stu-id="66f19-299">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-300">App-v クライアントで PowerShell スクリプトを有効にする</span><span class="sxs-lookup"><span data-stu-id="66f19-300">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-301">Office 2013 パッケージを発行するには、スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-301">To publish Office 2013 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="66f19-302">App-v クライアントでは、パッケージスクリプトは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="66f19-302">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="66f19-303">スクリプトを有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-303">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-304">Office 2013 パッケージをグローバルに公開する</span><span class="sxs-lookup"><span data-stu-id="66f19-304">Publish the Office 2013 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-305">Office App-v パッケージの拡張ポイントは、コンピューターレベルでインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-305">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="66f19-306">コンピューターレベルで公開する場合、必要な操作または再配布は不要であり、Office 2013 パッケージでは、ネイティブにインストールされた Office と同じようにアプリをグローバルに使用できるため、管理者がパッケージをカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66f19-306">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2013 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="66f19-307">Office パッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="66f19-307">How to publish an Office package</span></span>

<span data-ttu-id="66f19-308">Office パッケージをグローバルに公開するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-308">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="66f19-309">App-v Server の Web 管理コンソールから、ユーザーグループではなく、コンピューターのグループにアクセス許可を追加して、パッケージを対応するグループ内のコンピューターにグローバルに公開することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-309">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="66f19-310">Office App-v パッケージのカスタマイズと管理</span><span class="sxs-lookup"><span data-stu-id="66f19-310">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="66f19-311">Office App-v パッケージを管理するには、他のパッケージと同じ操作を実行しますが、次のセクションで説明するように、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-311">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="66f19-312">接続グループを使用して Office プラグインを有効にする</span><span class="sxs-lookup"><span data-stu-id="66f19-312">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="66f19-313">Office 2013 アプリケーションの無効化</span><span class="sxs-lookup"><span data-stu-id="66f19-313">Disabling Office 2013 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="66f19-314">Office 2013 ショートカットを無効にする</span><span class="sxs-lookup"><span data-stu-id="66f19-314">Disabling Office 2013 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="66f19-315">Office 2013 パッケージのアップグレードの管理</span><span class="sxs-lookup"><span data-stu-id="66f19-315">Managing Office 2013 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="66f19-316">Office 2013 ライセンスのアップグレードを管理する</span><span class="sxs-lookup"><span data-stu-id="66f19-316">Managing Office 2013 licensing upgrades</span></span>](#bkmk-manage-office-lic-upgrd)

-   [<span data-ttu-id="66f19-317">Office で Visio 2013 と Project 2013 を展開する</span><span class="sxs-lookup"><span data-stu-id="66f19-317">Deploying Visio 2013 and Project 2013 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="66f19-318">接続グループを使用して Office プラグインを有効にする</span><span class="sxs-lookup"><span data-stu-id="66f19-318">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="66f19-319">このセクションの手順を使用して、office パッケージで Office プラグインを有効にします。</span><span class="sxs-lookup"><span data-stu-id="66f19-319">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="66f19-320">Office プラグインを使うには、アプリ-V シーケンサーを使って、プラグインだけを含む個別のパッケージを作成する必要があります。Office 展開ツールを使用して、プラグインパッケージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="66f19-320">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="66f19-321">次に、次の手順で説明するように、Office パッケージとプラグインパッケージを含む接続グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-321">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="66f19-322">Office App-v パッケージのプラグインを有効にするには</span><span class="sxs-lookup"><span data-stu-id="66f19-322">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="66f19-323">App-v Server、System Center Configuration Manager、または PowerShell コマンドレットを使用して、接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-323">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="66f19-324">App-v 5.1 Sequencer を使って、プラグインの順序を作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-324">Sequence your plug-ins using the App-V 5.1 Sequencer.</span></span> <span data-ttu-id="66f19-325">プラグインの順序を示すために使用されているコンピューターに Office 2013 がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-325">Ensure that Office 2013 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="66f19-326">Office 2013 プラグインをシーケンス処理するときは、シーケンスコンピューターで Microsoft 365 アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="66f19-326">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2013 plug-ins.</span></span>

3.  <span data-ttu-id="66f19-327">目的のプラグインを含む App-v 5.1 パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-327">Create an App-V 5.1 package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="66f19-328">App-v server、System Center Configuration Manager、または PowerShell コマンドレットを使用して、接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-328">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="66f19-329">作成した接続グループに並べた Office 2013 アプリとプラグインパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-329">Add the Office 2013 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    **<span data-ttu-id="66f19-330">重要</span><span class="sxs-lookup"><span data-stu-id="66f19-330">Important</span></span>**  
    <span data-ttu-id="66f19-331">接続グループ内のパッケージの順序によって、パッケージコンテンツのマージ順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="66f19-331">The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="66f19-332">接続グループ記述子ファイルで、最初に Office 2013 App-V パッケージを追加してから、プラグインの App-v パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-332">In your Connection group descriptor file, add the Office 2013 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="66f19-333">両方のパッケージがターゲットコンピューターに公開されていること、およびプラグインパッケージがグローバルに公開された Office 2013 App-v パッケージのグローバル設定と一致するように公開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-333">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2013 App-V package.</span></span>

7.  <span data-ttu-id="66f19-334">プラグインパッケージの展開構成ファイルの設定が、Office 2013 App-v パッケージの設定と同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-334">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2013 App-V package has.</span></span>

    <span data-ttu-id="66f19-335">Office 2013 App-v パッケージはオペレーティングシステムと統合されているため、プラグインパッケージの設定は一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-335">Since the Office 2013 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="66f19-336">展開構成ファイルで "COM モード" を検索し、プラグインパッケージの値が "Integrated" として設定されていること、および "InProcessEnabled" と "OutOfProcessEnabled" の両方が、公開した Office 2013 App-v パッケージの設定と一致していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-336">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2013 App-V package you published.</span></span>

8.  <span data-ttu-id="66f19-337">展開構成ファイルを開き、**有効なオブジェクト**の値を**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="66f19-337">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="66f19-338">シーケンス後に展開構成ファイルに変更を加えた場合は、プラグインパッケージがファイルと共に公開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-338">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="66f19-339">作成した接続グループが、目的のコンピューターに有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-339">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="66f19-340">接続グループが有効になっている場合、作成された接続グループは、Office 2013 App-v パッケージを使用している場合、"保留" される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-340">The Connection Group created will likely “pend” if the Office 2013 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="66f19-341">この問題が発生した場合は、再起動して接続グループを正常に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-341">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="66f19-342">両方のパッケージを正常に公開し、接続グループを有効にした後、ターゲットの Office 2013 アプリケーションを起動して、接続グループに公開して追加したプラグインが正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="66f19-342">After you successfully publish both packages and enable the Connection Group, start the target Office 2013 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="66f19-343">Office 2013 アプリケーションの無効化</span><span class="sxs-lookup"><span data-stu-id="66f19-343">Disabling Office 2013 applications</span></span>

<span data-ttu-id="66f19-344">Office App-v パッケージで特定のアプリケーションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="66f19-344">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="66f19-345">たとえば、Access を無効にすることはできますが、その他のすべての Office アプリケーションはそのまま使用できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-345">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="66f19-346">アプリケーションを無効にすると、エンドユーザーにそのアプリケーションのショートカットが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="66f19-346">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="66f19-347">アプリケーションの順序を再設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="66f19-347">You do not have to re-sequence the application.</span></span> <span data-ttu-id="66f19-348">Office 2013 App-v パッケージが公開された後に展開構成ファイルを変更した場合は、変更内容を保存して、Office 2013 App-v パッケージを追加し、新しい展開構成ファイルを使って Office 2013 App-v パッケージアプリケーションに新しい設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-348">When you change the Deployment Configuration File after the Office 2013 App-V package has been published, you will save the changes, add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

**<span data-ttu-id="66f19-349">注</span><span class="sxs-lookup"><span data-stu-id="66f19-349">Note</span></span>**  
<span data-ttu-id="66f19-350">Office 展開ツールを使用して app-v パッケージを作成するときに、特定の Office アプリケーション (Access や InfoPath など) を除外するには、 **Excludeapp**設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-350">To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span> <span data-ttu-id="66f19-351">詳細については、「[クイック実行 configuration.xml ファイルのリファレンス](https://technet.microsoft.com/library/jj219426.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f19-351">For more information, see [Reference for Click-to-Run configuration.xml file](https://technet.microsoft.com/library/jj219426.aspx).</span></span>



**<span data-ttu-id="66f19-352">Office 2013 アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="66f19-352">To disable an Office 2013 application</span></span>**

1.  <span data-ttu-id="66f19-353">**メモ帳**などのテキストエディターで展開構成ファイルを開き、"アプリケーション" を検索します。</span><span class="sxs-lookup"><span data-stu-id="66f19-353">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="66f19-354">無効にする Office アプリケーション (Access 2013 など) を検索します。</span><span class="sxs-lookup"><span data-stu-id="66f19-354">Search for the Office application you want to disable, for example, Access 2013.</span></span>

3.  <span data-ttu-id="66f19-355">"有効" の値を "true" から "false" に変更します。</span><span class="sxs-lookup"><span data-stu-id="66f19-355">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="66f19-356">展開構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="66f19-356">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="66f19-357">新しい展開構成ファイルを使用して、Office 2013 App-v パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-357">Add the Office 2013 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot)]\officefl5\INFOPATH.EXE" Enabled="true">
      <VisualElements>
        <Name>InfoPath Filler 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[{AppVPackageRoot}]\office15\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office15\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2013</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="66f19-358">Office 2013 App-v パッケージを再度追加し、新しい展開構成ファイルを使用して再公開し、新しい設定を Office 2013 App-v パッケージアプリケーションに適用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-358">Re-add the Office 2013 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2013 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="66f19-359">Office 2013 ショートカットを無効にする</span><span class="sxs-lookup"><span data-stu-id="66f19-359">Disabling Office 2013 shortcuts</span></span>

<span data-ttu-id="66f19-360">特定の Office アプリケーションのショートカットを無効にすることもできます。その場合は、パッケージを非公開にするか、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-360">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="66f19-361">次の例は、Microsoft Access のショートカットキーを無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="66f19-361">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="66f19-362">Office 2013 アプリケーションのショートカットを無効にするには</span><span class="sxs-lookup"><span data-stu-id="66f19-362">To disable shortcuts for Office 2013 applications</span></span>**

1.  <span data-ttu-id="66f19-363">メモ帳で展開構成ファイルを開き、"ショートカット" を検索します。</span><span class="sxs-lookup"><span data-stu-id="66f19-363">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="66f19-364">特定のショートカットを無効にするには、必要のない特定のショートカットを削除またはコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="66f19-364">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="66f19-365">サブシステムを常に表示して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-365">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="66f19-366">たとえば、次の例では、サブシステムのショートカットまたは &lt; &gt; &lt; ショートカットをそのままにして &gt; microsoft access ショートカットを無効にして、microsoft access のショートカットを削除します。</span><span class="sxs-lookup"><span data-stu-id="66f19-366">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2013\Access 2013.lnk</File>
           <Target>[{AppvPackageRoot}])office15\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office15\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="66f19-367">展開構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="66f19-367">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="66f19-368">新しい展開構成ファイルを使用して、Office 2013 App-v パッケージを再公開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-368">Republish Office 2013 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="66f19-369">他にも多くの設定を変更するには、たとえば、ファイルの種類の関連付け、仮想ファイルシステムなどの App-v パッケージの展開構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="66f19-369">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="66f19-370">展開構成ファイルを使用して App-v パッケージの設定を変更する方法の詳細については、このドキュメントの最後にある「その他のリソース」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="66f19-370">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="66f19-371">Office 2013 パッケージのアップグレードの管理</span><span class="sxs-lookup"><span data-stu-id="66f19-371">Managing Office 2013 package upgrades</span></span>

<span data-ttu-id="66f19-372">Office 2013 パッケージをアップグレードするには、Office 展開ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-372">To upgrade an Office 2013 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="66f19-373">以前に展開された Office 2013 パッケージをアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-373">To upgrade a previously deployed Office 2013 package, perform the following steps.</span></span>

**<span data-ttu-id="66f19-374">以前に展開された Office 2013 パッケージのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="66f19-374">How to upgrade a previously deployed Office 2013 package</span></span>**

1.  <span data-ttu-id="66f19-375">最新の Office 2013 アプリケーションソフトウェアを使用している Office 展開ツールを使用して、新しい Office 2013 パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-375">Create a new Office 2013 package through the Office Deployment Tool that uses the most recent Office 2013 application software.</span></span> <span data-ttu-id="66f19-376">最新の Office 2013 bits は、Office 2013 App-v パッケージを作成するためのダウンロード段階でいつでも入手できます。</span><span class="sxs-lookup"><span data-stu-id="66f19-376">The most recent Office 2013 bits can always be obtained through the download stage of creating an Office 2013 App-V Package.</span></span> <span data-ttu-id="66f19-377">新しく作成された Office 2013 パッケージには、最新の更新プログラムと新しいバージョン ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="66f19-377">The newly created Office 2013 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="66f19-378">Office 展開ツールを使用して作成されたすべてのパッケージは、同じ系列になります。</span><span class="sxs-lookup"><span data-stu-id="66f19-378">All packages created using the Office Deployment Tool have the same lineage.</span></span>

    **<span data-ttu-id="66f19-379">注</span><span class="sxs-lookup"><span data-stu-id="66f19-379">Note</span></span>**  
    <span data-ttu-id="66f19-380">Office App-V パッケージには2つのバージョン Id があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-380">Office App-V packages have two Version IDs:</span></span>

    -   <span data-ttu-id="66f19-381">Office 展開ツールを使用して作成されたすべてのパッケージ間で一意の Office 2013 App-v パッケージバージョン ID。</span><span class="sxs-lookup"><span data-stu-id="66f19-381">An Office 2013 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span>

    -   <span data-ttu-id="66f19-382">新しいバージョンの Office 自体がある場合にのみ変更される AppX マニフェストなどの、2つ目の App-v パッケージバージョン ID である x.x.x.x のバージョン。</span><span class="sxs-lookup"><span data-stu-id="66f19-382">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="66f19-383">たとえば、アップグレード機能付きの新しい Office 2013 リリースが用意されていて、Office 展開ツールを使用してこれらのアップグレードを組み込むパッケージを作成した場合、X.x.x.x のバージョン ID が変更され、Office バージョンの変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="66f19-383">For example, if a new Office 2013 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="66f19-384">App-v server は、x.x.x.x バージョン ID を使ってこのパッケージを区別し、以前に公開されたパッケージへの新しいアップグレードが含まれていることを認識し、その結果として、既存の Office 2013 パッケージへのアップグレードとして発行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-384">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2013 package.</span></span>



2.  <span data-ttu-id="66f19-385">新しく作成された Office 2013 App-v パッケージを、新しい更新プログラムを適用するコンピューター上にグローバルに公開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-385">Globally publish the newly created Office 2013 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="66f19-386">新しいパッケージは、古い Office 2013 App-v パッケージの系列と同じであるため、更新プログラムを使用して新しいパッケージを公開しても、古いパッケージに新しい変更が適用されるため、高速になります。</span><span class="sxs-lookup"><span data-stu-id="66f19-386">Since the new package has the same lineage of the older Office 2013 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3.  <span data-ttu-id="66f19-387">アップグレードは、グローバルに公開された App-v パッケージと同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="66f19-387">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="66f19-388">アプリケーションはおそらく使用されているため、コンピューターが再起動されるまで、アップグレードの遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-388">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>

### <a href="" id="bkmk-manage-office-lic-upgrd"></a><span data-ttu-id="66f19-389">Office 2013 ライセンスのアップグレードを管理する</span><span class="sxs-lookup"><span data-stu-id="66f19-389">Managing Office 2013 licensing upgrades</span></span>

<span data-ttu-id="66f19-390">新しい Office 2013 App-v パッケージのライセンスが、現在展開されている Office 2013 App-v パッケージとは異なる場合。</span><span class="sxs-lookup"><span data-stu-id="66f19-390">If a new Office 2013 App-V Package has a different license than the Office 2013 App-V Package currently deployed.</span></span> <span data-ttu-id="66f19-391">たとえば、展開されている office 2013 パッケージがサブスクリプションベースの Office 2013 であり、新しい Office 2013 パッケージがボリュームライセンスを使用している場合は、次の手順に従って、スムーズなライセンスアップグレードを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-391">For instance, the Office 2013 package deployed is a subscription based Office 2013 and the new Office 2013 package is Volume Licensing based, the following instructions must be followed to ensure smooth licensing upgrade:</span></span>

**<span data-ttu-id="66f19-392">Office 2013 ライセンスのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="66f19-392">How to upgrade an Office 2013 License</span></span>**

1.  <span data-ttu-id="66f19-393">既に展開されている Office 2013 サブスクリプションのライセンスアプリ-V パッケージの発行を停止します。</span><span class="sxs-lookup"><span data-stu-id="66f19-393">Unpublish the already deployed Office 2013 Subscription Licensing App-V package.</span></span>

2.  <span data-ttu-id="66f19-394">未公開の Office 2013 サブスクリプションのライセンスアプリ-V パッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="66f19-394">Remove the unpublished Office 2013 Subscription Licensing App-V package.</span></span>

3.  <span data-ttu-id="66f19-395">コンピューターを再起動します。</span><span class="sxs-lookup"><span data-stu-id="66f19-395">Restart the computer.</span></span>

4.  <span data-ttu-id="66f19-396">新しい Office 2013 App-v パッケージボリュームライセンスを追加します。</span><span class="sxs-lookup"><span data-stu-id="66f19-396">Add the new Office 2013 App-V Package Volume Licensing.</span></span>

5.  <span data-ttu-id="66f19-397">追加された Office 2013 App-v パッケージをボリュームライセンスと共に公開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-397">Publish the added Office 2013 App-V Package with Volume Licensing.</span></span>

<span data-ttu-id="66f19-398">選択されたライセンスを使用した Office 2013 App V パッケージの展開が完了します。</span><span class="sxs-lookup"><span data-stu-id="66f19-398">An Office 2013 App-V Package with your chosen licensing will be successfully deployed.</span></span>

### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="66f19-399">Office で Visio 2013 と Project 2013 を展開する</span><span class="sxs-lookup"><span data-stu-id="66f19-399">Deploying Visio 2013 and Project 2013 with Office</span></span>

<span data-ttu-id="66f19-400">次の表では、Visio 2013 と Project 2013 を Office と共に展開するための要件とオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="66f19-400">The following table describes the requirements and options for deploying Visio 2013 and Project 2013 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-401">タスク</span><span class="sxs-lookup"><span data-stu-id="66f19-401">Task</span></span></th>
<th align="left"><span data-ttu-id="66f19-402">詳細</span><span class="sxs-lookup"><span data-stu-id="66f19-402">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-403">Visio 2013 および Project 2013 を Office と共にパッケージ化して発行するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="66f19-403">How do I package and publish Visio 2013 and Project 2013 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-404">Office と同じパッケージに Visio 2013 と Project 2013 を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="66f19-404">You must include Visio 2013 and Project 2013 in the same package with Office.</span></span></p>
<p><span data-ttu-id="66f19-405">Office を展開していない場合は、Microsoft Office 2010 を展開している限り、Visio または Project を含むパッケージを作成することができ <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="66f19-405">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow <a href="../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md" data-raw-source="[Deploying Microsoft Office 2010 by Using App-V](../appv-v5/deploying-microsoft-office-2010-by-using-app-v.md)">Deploying Microsoft Office 2010 by Using App-V</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-406">Visio 2013 と Project 2013 を特定のユーザーに展開するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="66f19-406">How can I deploy Visio 2013 and Project 2013 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-407">以下の方法のうちのいずれか 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-407">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66f19-408">目的の処理</span><span class="sxs-lookup"><span data-stu-id="66f19-408">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="66f19-409">...次に、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="66f19-409">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66f19-410">2つの異なるパッケージを作成し、それぞれを別のユーザーグループに展開する</span><span class="sxs-lookup"><span data-stu-id="66f19-410">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-411">次のパッケージを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-411">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="66f19-412">Office のみを含むパッケージで、ユーザーが Office のみを必要とするコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="66f19-412">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="66f19-413">Office、Visio、Project を含むパッケージ。ユーザーが3つのアプリケーションを必要とするコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-413">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66f19-414">組織全体に対してパッケージを1つだけ追加する場合、またはコンピューターを共有しているユーザーがいる場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="66f19-414">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="66f19-415">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="66f19-415">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="66f19-416">Office、Visio、および Project を含むパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="66f19-416">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="66f19-417">パッケージをすべてのユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="66f19-417">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="66f19-418"><a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker を使用し </a> て、特定のユーザーによる Visio と Project の使用を防止します。</span><span class="sxs-lookup"><span data-stu-id="66f19-418">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="66f19-419">その他の情報</span><span class="sxs-lookup"><span data-stu-id="66f19-419">Additional resources</span></span>


**<span data-ttu-id="66f19-420">Office 2013 App-v パッケージのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="66f19-420">Office 2013 App-V Packages Additional Resources</span></span>**

[<span data-ttu-id="66f19-421">クイック実行用の Office 展開ツール</span><span class="sxs-lookup"><span data-stu-id="66f19-421">Office Deployment Tool for Click-to-Run</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=330672)

[<span data-ttu-id="66f19-422">シーケンス付きの App-v パッケージとして Microsoft Office を展開する場合のサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="66f19-422">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="66f19-423">Office 2010 App-v パッケージ</span><span class="sxs-lookup"><span data-stu-id="66f19-423">Office 2010 App-V Packages</span></span>**

[<span data-ttu-id="66f19-424">Microsoft Application Virtualization 5.0 用 microsoft Office 2010 シーケンスキット</span><span class="sxs-lookup"><span data-stu-id="66f19-424">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="66f19-425">App-v 5.0 Office 2010 パッケージを作成または使用するときの既知の問題</span><span class="sxs-lookup"><span data-stu-id="66f19-425">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="66f19-426">Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="66f19-426">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="66f19-427">接続グループ</span><span class="sxs-lookup"><span data-stu-id="66f19-427">Connection Groups</span></span>**

[<span data-ttu-id="66f19-428">Microsoft App での接続グループの展開-V v5</span><span class="sxs-lookup"><span data-stu-id="66f19-428">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="66f19-429">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="66f19-429">Managing Connection Groups</span></span>](managing-connection-groups51.md)

**<span data-ttu-id="66f19-430">動的構成</span><span class="sxs-lookup"><span data-stu-id="66f19-430">Dynamic Configuration</span></span>**

[<span data-ttu-id="66f19-431">App-V 5.1 の動的構成について</span><span class="sxs-lookup"><span data-stu-id="66f19-431">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)














