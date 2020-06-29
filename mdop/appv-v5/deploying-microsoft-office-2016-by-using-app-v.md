---
title: APP-V を使用した Microsoft Office 2016 の展開
description: APP-V を使用した Microsoft Office 2016 の展開
author: dansimp
ms.assetid: cc675cde-cb8d-4b7c-a700-6104b78f1d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 07/25/2017
ms.openlocfilehash: dfedab98e0bdf0a0d5f5e407d9bedadbbf56ad69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814619"
---
# <span data-ttu-id="de6ba-103">APP-V を使用した Microsoft Office 2016 の展開</span><span class="sxs-lookup"><span data-stu-id="de6ba-103">Deploying Microsoft Office 2016 by Using App-V</span></span>


<span data-ttu-id="de6ba-104">この記事の情報は、Microsoft Application Virtualization 5.0 以降のバージョンを使用して、Microsoft Office 2016 を仮想化されたアプリケーションとして組織内のコンピューターに配信するために使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-104">Use the information in this article to use Microsoft Application Virtualization 5.0, or later versions, to deliver Microsoft Office 2016 as a virtualized application to computers in your organization.</span></span> <span data-ttu-id="de6ba-105">Office 2013 を提供するために app-v を使用する方法については、「 [App-v を使用して Microsoft Office 2013 を展開](deploying-microsoft-office-2013-by-using-app-v.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-105">For information about using App-V to deliver Office 2013, see [Deploying Microsoft Office 2013 by Using App-V](deploying-microsoft-office-2013-by-using-app-v.md).</span></span> <span data-ttu-id="de6ba-106">Office 2010 を提供するために app-v を使用する方法については、「 [App-v を使用して Microsoft Office 2010 を展開](deploying-microsoft-office-2010-by-using-app-v.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-106">For information about using App-V to deliver Office 2010, see [Deploying Microsoft Office 2010 by Using App-V](deploying-microsoft-office-2010-by-using-app-v.md).</span></span>

<span data-ttu-id="de6ba-107">ここでは、以下のトピックについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-107">This topic contains the following sections:</span></span>

-   [<span data-ttu-id="de6ba-108">始める前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="de6ba-108">What to know before you start</span></span>](#bkmk-before-you-start)

-   [<span data-ttu-id="de6ba-109">Office 展開ツールを使用して、App-v 用の Office 2016 パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="de6ba-109">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>](#bkmk-create-office-pkg)

-   [<span data-ttu-id="de6ba-110">Office パッケージを App-v で公開する-V 5.0</span><span class="sxs-lookup"><span data-stu-id="de6ba-110">Publishing the Office package for App-V 5.0</span></span>](#bkmk-pub-pkg-office)

-   [<span data-ttu-id="de6ba-111">Office App-v パッケージのカスタマイズと管理</span><span class="sxs-lookup"><span data-stu-id="de6ba-111">Customizing and managing Office App-V packages</span></span>](#bkmk-custmz-manage-office-pkgs)

## <a href="" id="bkmk-before-you-start"></a><span data-ttu-id="de6ba-112">始める前に知っておくべきこと</span><span class="sxs-lookup"><span data-stu-id="de6ba-112">What to know before you start</span></span>


<span data-ttu-id="de6ba-113">App-v を使用して Office 2016 を展開する前に、次の計画情報を確認してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-113">Before you deploy Office 2016 by using App-V, review the following planning information.</span></span>

### <a href="" id="bkmk-supp-vers-coexist"></a><span data-ttu-id="de6ba-114">サポートされている Office のバージョンと Office の共存</span><span class="sxs-lookup"><span data-stu-id="de6ba-114">Supported Office versions and Office coexistence</span></span>

<span data-ttu-id="de6ba-115">次の表を使用して、サポートされているバージョンの Office と、共存バージョンの Office の実行に関する情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-115">Use the following table to get information about supported versions of Office and about running coexisting versions of Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-116">レビューする情報</span><span class="sxs-lookup"><span data-stu-id="de6ba-116">Information to review</span></span></th>
<th align="left"><span data-ttu-id="de6ba-117">説明</span><span class="sxs-lookup"><span data-stu-id="de6ba-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv" data-raw-source="[Supported versions of Microsoft Office](planning-for-using-app-v-with-office.md#bkmk-office-vers-supp-appv)"><span data-ttu-id="de6ba-118">サポートされている Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="de6ba-118">Supported versions of Microsoft Office</span></span></a></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="de6ba-119">サポートされている Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="de6ba-119">Supported versions of Office</span></span></p></li>
<li><p><span data-ttu-id="de6ba-120">サポートされている展開の種類 (デスクトップ、個人用仮想デスクトップインフラストラクチャ (VDI)、プールされた VDI)</span><span class="sxs-lookup"><span data-stu-id="de6ba-120">Supported deployment types (for example, desktop, personal Virtual Desktop Infrastructure (VDI), pooled VDI)</span></span></p></li>
<li><p><span data-ttu-id="de6ba-121">Office のライセンスオプション</span><span class="sxs-lookup"><span data-stu-id="de6ba-121">Office licensing options</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><a href="planning-for-using-app-v-with-office.md#bkmk-plan-coexisting" data-raw-source="[Planning for Using App-V with coexisting versions of Office](planning-for-using-app-v-with-office.md#bkmk-plan-coexisting)"><span data-ttu-id="de6ba-122">共存バージョンの Office での App-v の使用を計画する</span><span class="sxs-lookup"><span data-stu-id="de6ba-122">Planning for Using App-V with coexisting versions of Office</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="de6ba-123">異なるバージョンの Office を同じコンピューターにインストールする場合の考慮事項</span><span class="sxs-lookup"><span data-stu-id="de6ba-123">Considerations for installing different versions of Office on the same computer</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pkg-pub-reqs"></a><span data-ttu-id="de6ba-124">パッケージ化、発行、展開の要件</span><span class="sxs-lookup"><span data-stu-id="de6ba-124">Packaging, publishing, and deployment requirements</span></span>

<span data-ttu-id="de6ba-125">App-v を使用して Office を展開する前に、次の要件を確認してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-125">Before you deploy Office by using App-V, review the following requirements.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-126">タスク</span><span class="sxs-lookup"><span data-stu-id="de6ba-126">Task</span></span></th>
<th align="left"><span data-ttu-id="de6ba-127">要件</span><span class="sxs-lookup"><span data-stu-id="de6ba-127">Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-128">パッケージ化</span><span class="sxs-lookup"><span data-stu-id="de6ba-128">Packaging</span></span></p></td>
<td align="left">
<ul>
<li><p><span data-ttu-id="de6ba-129">ユーザーに展開するすべての Office アプリケーションが1つのパッケージに含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-129">All of the Office applications that you want to deploy to users must be in a single package.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-130">App-v 5.0 以降では、Office 展開ツールを使用してパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-130">In App-V 5.0 and later, you must use the Office Deployment Tool to create packages.</span></span> <span data-ttu-id="de6ba-131">Sequencer は使用できません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-131">You cannot use the Sequencer.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-132">Microsoft Visio 2016 と Microsoft Project 2016 を Office と共に展開する場合は、それらを Office と同じパッケージに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-132">If you are deploying Microsoft Visio 2016 and Microsoft Project 2016 along with Office, you must include them in the same package with Office.</span></span> <span data-ttu-id="de6ba-133">詳細については、「 <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)"> Visio 2016 および Project 2016 を Office と共に展開する」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="de6ba-133">For more information, see <a href="#bkmk-deploy-visio-project" data-raw-source="[Deploying Visio 2016 and Project 2016 with Office](#bkmk-deploy-visio-project)">Deploying Visio 2016 and Project 2016 with Office</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-134">Publishing</span><span class="sxs-lookup"><span data-stu-id="de6ba-134">Publishing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="de6ba-135">各クライアントコンピューターには、1つの Office パッケージのみを公開できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-135">You can publish only one Office package to each client computer.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-136">Office パッケージをグローバルに公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-136">You must publish the Office package globally.</span></span> <span data-ttu-id="de6ba-137">ユーザーに公開することはできません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-137">You cannot publish to the user.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-138">次の製品を共有コンピューターに展開する (たとえば、リモートデスクトップサービスを使用する)。</span><span class="sxs-lookup"><span data-stu-id="de6ba-138">Deploying any of the following products to a shared computer, for example, by using Remote Desktop Services:</span></span></p>
<ul>
<li><p><span data-ttu-id="de6ba-139">エンタープライズ向けの Microsoft 365 アプリ</span><span class="sxs-lookup"><span data-stu-id="de6ba-139">Microsoft 365 Apps for enterprise</span></span></p></li>
<li><p><span data-ttu-id="de6ba-140">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="de6ba-140">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="de6ba-141">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="de6ba-141">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="de6ba-142">共有コンピューターのライセンス認証を有効にする必要があり <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)"> </a> ます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-142">You must enable <a href="https://technet.microsoft.com/library/dn782860.aspx" data-raw-source="[shared computer activation](https://technet.microsoft.com/library/dn782860.aspx)">shared computer activation</a>.</span></span></p>
</td>
</tr>
</tbody>
</table>



### <span data-ttu-id="de6ba-143">パッケージからの Office アプリケーションの除外</span><span class="sxs-lookup"><span data-stu-id="de6ba-143">Excluding Office applications from a package</span></span>

<span data-ttu-id="de6ba-144">次の表では、特定の Office アプリケーションをパッケージから除外するための推奨される方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-144">The following table describes the recommended methods for excluding specific Office applications from a package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-145">タスク</span><span class="sxs-lookup"><span data-stu-id="de6ba-145">Task</span></span></th>
<th align="left"><span data-ttu-id="de6ba-146">詳細</span><span class="sxs-lookup"><span data-stu-id="de6ba-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-147"><strong> </strong> Office 展開ツールを使用してパッケージを作成する場合は、excludeapp 設定を使います。</span><span class="sxs-lookup"><span data-stu-id="de6ba-147">Use the <strong>ExcludeApp</strong> setting when you create the package by using the Office Deployment Tool.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="de6ba-148">Office 展開ツールがパッケージを作成するときに、特定の Office アプリケーションをパッケージから除外できるようにします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-148">Enables you to exclude specific Office applications from the package when the Office Deployment Tool creates the package.</span></span> <span data-ttu-id="de6ba-149">たとえば、この設定を使って、Microsoft Word のみを含むパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-149">For example, you can use this setting to create a package that contains only Microsoft Word.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-150">詳細については、「excludeapp 要素」を参照してください <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="de6ba-150">For more information, see <a href="https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement" data-raw-source="[ExcludeApp element](https://technet.microsoft.com/library/jj219426.aspx#bkmk-excludeappelement)">ExcludeApp element</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-151">DeploymentConfig.xml ファイルを変更する</span><span class="sxs-lookup"><span data-stu-id="de6ba-151">Modify the DeploymentConfig.xml file</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="de6ba-152">パッケージを作成した後で DeploymentConfig.xml ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-152">Modify the DeploymentConfig.xml file after the package has been created.</span></span> <span data-ttu-id="de6ba-153">このファイルには、App-v クライアントを実行しているコンピューター上のすべてのユーザーの既定のパッケージ設定が含まれています。</span><span class="sxs-lookup"><span data-stu-id="de6ba-153">This file contains the default package settings for all users on a computer that is running the App-V Client.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-154">詳細については、「 <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)"> Office 2016 アプリケーションを無効にする」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="de6ba-154">For more information, see <a href="#bkmk-disable-office-apps" data-raw-source="[Disabling Office 2016 applications](#bkmk-disable-office-apps)">Disabling Office 2016 applications</a>.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-create-office-pkg"></a><span data-ttu-id="de6ba-155">Office 展開ツールを使用して、App-v 用の Office 2016 パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="de6ba-155">Creating an Office 2016 package for App-V with the Office Deployment Tool</span></span>


<span data-ttu-id="de6ba-156">次の手順を実行して、App-v 5.0 以降の Office 2016 パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-156">Complete the following steps to create an Office 2016 package for App-V 5.0 or later.</span></span>

><span data-ttu-id="de6ba-157">**Important** &nbsp; 重要 &nbsp;App-v 5.0 以降では、Office 展開ツールを使用してパッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-157">**Important**&nbsp;&nbsp;In App-V 5.0 and later, you must use the Office Deployment Tool to create a package.</span></span> <span data-ttu-id="de6ba-158">Sequencer を使ってパッケージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-158">You cannot use the Sequencer to create packages.</span></span>

### <span data-ttu-id="de6ba-159">Office 展開ツールを使用するための前提条件を確認する</span><span class="sxs-lookup"><span data-stu-id="de6ba-159">Review prerequisites for using the Office Deployment Tool</span></span>

<span data-ttu-id="de6ba-160">Office 展開ツールをインストールするコンピューターには、次のものが必要です。</span><span class="sxs-lookup"><span data-stu-id="de6ba-160">The computer on which you are installing the Office Deployment Tool must have:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-161">受講</span><span class="sxs-lookup"><span data-stu-id="de6ba-161">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="de6ba-162">説明</span><span class="sxs-lookup"><span data-stu-id="de6ba-162">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-163">必須ソフトウェア</span><span class="sxs-lookup"><span data-stu-id="de6ba-163">Prerequisite software</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-164">.Net Framework 4</span><span class="sxs-lookup"><span data-stu-id="de6ba-164">.Net Framework 4</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-165">サポートされているオペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="de6ba-165">Supported operating systems</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="de6ba-166">64ビット版の Windows 10</span><span class="sxs-lookup"><span data-stu-id="de6ba-166">64-bit version of Windows 10</span></span></p></li>
<li><p><span data-ttu-id="de6ba-167">64ビット版の Windows 8 または8.1</span><span class="sxs-lookup"><span data-stu-id="de6ba-167">64-bit version of Windows 8 or 8.1</span></span></p></li>
<li><p><span data-ttu-id="de6ba-168">64ビット版の Windows 7</span><span class="sxs-lookup"><span data-stu-id="de6ba-168">64-bit version of Windows 7</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


><span data-ttu-id="de6ba-169">**注** このトピックでは、"Office 2016 App-v パッケージ" という用語は、サブスクリプションライセンスを示しています。</span><span class="sxs-lookup"><span data-stu-id="de6ba-169">**Note**  In this topic, the term “Office 2016 App-V package” refers to subscription licensing.</span></span>


### <span data-ttu-id="de6ba-170">Office 展開ツールを使用して Office 2016 App-v パッケージを作成する</span><span class="sxs-lookup"><span data-stu-id="de6ba-170">Create Office 2016 App-V Packages Using Office Deployment Tool</span></span>

<span data-ttu-id="de6ba-171">Office 2016 App-v パッケージを作成するには、Office 展開ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-171">You create Office 2016 App-V packages by using the Office Deployment Tool.</span></span> <span data-ttu-id="de6ba-172">次の手順では、サブスクリプションのライセンスを持つ Office 2016 App-v パッケージを作成する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-172">The following instructions explain how to create an Office 2016 App-V package with Subscription Licensing.</span></span>

<span data-ttu-id="de6ba-173">64ビットの Windows コンピューター上で Office 2016 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-173">Create Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="de6ba-174">作成された Office 2016 App-v パッケージは、32ビットおよび64ビットの Windows 7、Windows 8.1、Windows 10 のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-174">Once created, the Office 2016 App-V package will run on 32-bit and 64-bit Windows 7, Windows 8.1, and Windows 10 computers.</span></span>

### <span data-ttu-id="de6ba-175">Office 展開ツールをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="de6ba-175">Download the Office Deployment Tool</span></span>

<span data-ttu-id="de6ba-176">Office 2016 App-v パッケージは、office 展開ツールを使って作成されます。このパッケージは、office 2016 App-v パッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-176">Office 2016 App-V Packages are created using the Office Deployment Tool, which generates an Office 2016 App-V Package.</span></span> <span data-ttu-id="de6ba-177">App-v sequencer でパッケージを作成または変更することはできません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-177">The package cannot be created or modified through the App-V sequencer.</span></span> <span data-ttu-id="de6ba-178">パッケージの作成を開始するには:</span><span class="sxs-lookup"><span data-stu-id="de6ba-178">To begin package creation:</span></span>

1.  <span data-ttu-id="de6ba-179">[クイック実行用に Office 2016 展開ツール](https://www.microsoft.com/download/details.aspx?id=49117)をダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-179">Download the [Office 2016 Deployment Tool for Click-to-Run](https://www.microsoft.com/download/details.aspx?id=49117).</span></span>

> <span data-ttu-id="de6ba-180">**重要**Office 2016 展開ツールを使用して、Office 2016 App-v パッケージを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-180">**Important** You must use the Office 2016 Deployment Tool to create Office 2016 App-V Packages.</span></span>
> 2. <span data-ttu-id="de6ba-181">.Exe ファイルを実行し、目的の場所にその機能を抽出します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-181">Run the .exe file and extract its features into the desired location.</span></span> <span data-ttu-id="de6ba-182">このプロセスをより簡単にするために、機能を保存する共有ネットワークフォルダーを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-182">To make this process easier, you can create a shared network folder where the features will be saved.</span></span>

    Example: \\\\Server\\Office2016

3. <span data-ttu-id="de6ba-183">setup.exe と configuration.xml ファイルが存在し、指定した場所にあることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-183">Check that a setup.exe and a configuration.xml file exist and are in the location you specified.</span></span>

### <span data-ttu-id="de6ba-184">Office 2016 アプリケーションをダウンロードする</span><span class="sxs-lookup"><span data-stu-id="de6ba-184">Download Office 2016 applications</span></span>

<span data-ttu-id="de6ba-185">Office 展開ツールをダウンロードしたら、それを使って最新の Office 2016 アプリケーションを入手できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-185">After you download the Office Deployment Tool, you can use it to get the latest Office 2016 applications.</span></span> <span data-ttu-id="de6ba-186">Office アプリケーションを入手したら、Office 2016 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-186">After getting the Office applications, you create the Office 2016 App-V package.</span></span>

<span data-ttu-id="de6ba-187">Office 展開ツールに含まれている XML ファイルでは、対象となる言語や Office アプリケーションなどの製品の詳細を指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-187">The XML file that is included in the Office Deployment Tool specifies the product details, such as the languages and Office applications included.</span></span>

1. <span data-ttu-id="de6ba-188">**サンプルの XML 構成ファイルをカスタマイズします。** Office 展開ツールと共にダウンロードしたサンプル XML 構成ファイルを使用して、Office アプリケーションをカスタマイズします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-188">**Customize the sample XML configuration file:** Use the sample XML configuration file that you downloaded with the Office Deployment Tool to customize the Office applications:</span></span>

   1. <span data-ttu-id="de6ba-189">メモ帳またはお気に入りのテキストエディターでサンプル XML ファイルを開きます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-189">Open the sample XML file in Notepad or your favorite text editor.</span></span>

   2. <span data-ttu-id="de6ba-190">サンプルの configuration.xml ファイルを開いて編集する準備ができたら、製品、言語、Office 2016 アプリケーションの保存先のパスを指定できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-190">With the sample configuration.xml file open and ready for editing, you can specify products, languages, and the path to which you save the Office 2016 applications.</span></span> <span data-ttu-id="de6ba-191">configuration.xml ファイルの基本的な例を次に示します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-191">The following is a basic example of the configuration.xml file:</span></span>

      ```xml
      <Configuration>
         <Add SourcePath= "\\Server\Office2016” OfficeClientEdition="32" >
          <Product ID="O365ProPlusRetail ">
            <Language ID="en-us" />
          </Product>
          <Product ID="VisioProRetail">
            <Language ID="en-us" />
          </Product>
        </Add>
      </Configuration>
      ```

      ><span data-ttu-id="de6ba-192">**注** 構成 XML はサンプルの XML ファイルです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-192">**Note**  The configuration XML is a sample XML file.</span></span> <span data-ttu-id="de6ba-193">ファイルには、コメントアウトされた行が含まれています。ファイルを使用して追加の設定をカスタマイズするには、これらの行のコメントを解除します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-193">The file includes lines that are commented out. You can “uncomment” these lines to customize additional settings with the file.</span></span> <span data-ttu-id="de6ba-194">これらの行のコメントを解除するには、「<」を削除します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-194">To “uncomment” these lines, remove the "<!</span></span> <span data-ttu-id="de6ba-195">------->--------------------------------------</span><span class="sxs-lookup"><span data-stu-id="de6ba-195">- -" from the beginning of the line, and the "-- >" from the end of the line.</span></span>

      <span data-ttu-id="de6ba-196">上の XML 構成ファイルを使用すると、Office 2016 ProPlus 32 ビット版 (Visio ProPlus を含む) が2016英語でダウンロードされます。これは、Office アプリケーションが保存される場所です。</span><span class="sxs-lookup"><span data-stu-id="de6ba-196">The above XML configuration file specifies that Office 2016 ProPlus 32-bit edition, including Visio ProPlus, will be downloaded in English to the \\\\server\\Office 2016, which is the location where Office applications will be saved to.</span></span> <span data-ttu-id="de6ba-197">アプリケーションの製品 ID は、Office の最終的なライセンスに影響を与えないことに注意してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-197">Note that the Product ID of the applications will not affect the final licensing of Office.</span></span> <span data-ttu-id="de6ba-198">さまざまなライセンスを持つ Office 2016 アプリ V パッケージは、後の段階でライセンスを指定することによって同じアプリケーションから作成できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-198">Office 2016 App-V packages with various licensing can be created from the same applications through specifying licensing in a later stage.</span></span> <span data-ttu-id="de6ba-199">次の表は、XML ファイルのカスタマイズ可能な属性と要素をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-199">The table below summarizes the customizable attributes and elements of XML file:</span></span>

      <table>
      <colgroup>
      <col width="33%" />
      <col width="33%" />
      <col width="33%" />
      </colgroup>
      <thead>
      <tr class="header">
      <th align="left"><span data-ttu-id="de6ba-200">入力</span><span class="sxs-lookup"><span data-stu-id="de6ba-200">Input</span></span></th>
      <th align="left"><span data-ttu-id="de6ba-201">説明</span><span class="sxs-lookup"><span data-stu-id="de6ba-201">Description</span></span></th>
      <th align="left"><span data-ttu-id="de6ba-202">例</span><span class="sxs-lookup"><span data-stu-id="de6ba-202">Example</span></span></th>
      </tr>
      </thead>
      <tbody>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="de6ba-203">要素の追加</span><span class="sxs-lookup"><span data-stu-id="de6ba-203">Add element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-204">パッケージに含める製品と言語を指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-204">Specifies the products and languages to include in the package.</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-205">なし</span><span class="sxs-lookup"><span data-stu-id="de6ba-205">N/A</span></span></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="de6ba-206">OfficeClientEdition (Add 要素の属性)</span><span class="sxs-lookup"><span data-stu-id="de6ba-206">OfficeClientEdition (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-207">使用する Office 2016 製品のバージョン (32 ビットまたは64ビット) を指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-207">Specifies the edition of Office 2016 product to use: 32-bit or 64-bit.</span></span> <span data-ttu-id="de6ba-208"><strong>OfficeClientEdition </strong> が有効な値に設定されていない場合、操作は失敗します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-208">The operation fails if <strong>OfficeClientEdition</strong> is not set to a valid value.</span></span></p></td>
      <td align="left"><p><strong><span data-ttu-id="de6ba-209">OfficeClientEdition </strong> = &quot; 32&quot;</span><span class="sxs-lookup"><span data-stu-id="de6ba-209">OfficeClientEdition</strong>=&quot;32&quot;</span></span></p>
      <p><strong><span data-ttu-id="de6ba-210">OfficeClientEdition </strong> = &quot; 64&quot;</span><span class="sxs-lookup"><span data-stu-id="de6ba-210">OfficeClientEdition</strong>=&quot;64&quot;</span></span></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="de6ba-211">Product 要素</span><span class="sxs-lookup"><span data-stu-id="de6ba-211">Product element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-212">アプリケーションを指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-212">Specifies the application.</span></span> <span data-ttu-id="de6ba-213">プロジェクト2016と Visio 2016 は、追加された製品としてアプリケーションに含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-213">Project 2016 and Visio 2016 must be specified here as an added product to be included in the applications.</span></span>

      <span data-ttu-id="de6ba-214">製品 Id の詳細については、「 <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)"> クイック実行用に Office 展開ツールでサポートされている製品 id」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-214">For more information about the product IDs, see <a href="https://support.microsoft.com/kb/2842297" data-raw-source="[Product IDs that are supported by the Office Deployment Tool for Click-to-Run](https://support.microsoft.com/kb/2842297)">Product IDs that are supported by the Office Deployment Tool for Click-to-Run</span></span></a>
      </p></td>
      <td align="left"><p><code>Product ID =&quot;O365ProPlusRetail &quot;</code></p>
      <p><code>Product ID =&quot;VisioProRetail&quot;</code></p>
      <p><code>Product ID =&quot;ProjectProRetail&quot;</code></p>
      </td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="de6ba-215">Language 要素</span><span class="sxs-lookup"><span data-stu-id="de6ba-215">Language element</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-216">アプリケーションでサポートされる言語を指定します</span><span class="sxs-lookup"><span data-stu-id="de6ba-216">Specifies the language supported in the applications</span></span></p></td>
      <td align="left"><p><code>Language ID=&quot;en-us&quot;</code></p></td>
      </tr>
      <tr class="odd">
      <td align="left"><p><span data-ttu-id="de6ba-217">Version (Add 要素の属性)</span><span class="sxs-lookup"><span data-stu-id="de6ba-217">Version (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-218">省略可能。</span><span class="sxs-lookup"><span data-stu-id="de6ba-218">Optional.</span></span> <span data-ttu-id="de6ba-219">パッケージに使用するビルドを指定します</span><span class="sxs-lookup"><span data-stu-id="de6ba-219">Specifies a build to use for the package</span></span></p>
      <p><span data-ttu-id="de6ba-220">既定では、[最新のアドバタイズされたビルド] (Office ソースの v32.CAB で定義)</span><span class="sxs-lookup"><span data-stu-id="de6ba-220">Defaults to latest advertised build (as defined in v32.CAB at the Office source).</span></span></p></td>
      <td align="left"><p><code>16.1.2.3</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="de6ba-221">SourcePath (Add 要素の属性)</span><span class="sxs-lookup"><span data-stu-id="de6ba-221">SourcePath (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-222">アプリケーションが保存される場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-222">Specifies the location in which the applications will be saved to.</span></span></p></td>
      <td align="left"><p><code>Sourcepath = &quot;\Server\Office2016”</code></p></td>
      </tr>
      <tr class="even">
      <td align="left"><p><span data-ttu-id="de6ba-223">Channel (Add 要素の属性)</span><span class="sxs-lookup"><span data-stu-id="de6ba-223">Channel (attribute of Add element)</span></span></p></td>
      <td align="left"><p><span data-ttu-id="de6ba-224">省略可能。</span><span class="sxs-lookup"><span data-stu-id="de6ba-224">Optional.</span></span> <span data-ttu-id="de6ba-225">ダウンロードまたはインストールする製品の更新チャネルを指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-225">Specifies the update channel for the product that you want to download or install.</span></span> </p><p><span data-ttu-id="de6ba-226">更新プログラムチャネルの詳細については、「エンタープライズ向けの Microsoft 365 アプリの更新プログラムチャネルの概要」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-226">For more information about update channels, see Overview of update channels for Microsoft 365 Apps for enterprise.</span></span></p></td>
      <td align="left"><p><code>Channel=&quot;Deferred&quot;</code></p></td>
      </tr>
      </tbody>
      </table>

      <span data-ttu-id="de6ba-227">configuration.xml ファイルを編集して、目的の製品、言語、および Office 2016 アプリケーションの保存場所を指定した後、Customconfig.xml として構成ファイルを保存できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-227">After editing the configuration.xml file to specify the desired product, languages, and also the location which the Office 2016 applications will be saved onto, you can save the configuration file, for example, as Customconfig.xml.</span></span>

2. <span data-ttu-id="de6ba-228">**指定した場所にアプリケーションをダウンロードします。** 昇格したコマンドプロンプトと64ビットのオペレーティングシステムを使って、後で App-v パッケージに変換される Office 2016 アプリケーションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-228">**Download the applications into the specified location:** Use an elevated command prompt and a 64 bit operating system to download the Office 2016 applications that will later be converted into an App-V package.</span></span> <span data-ttu-id="de6ba-229">詳細については、次のコマンド例を参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-229">Below is an example command with a description of details:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /download \\server\Office2016\Customconfig.xml
   ```

   <span data-ttu-id="de6ba-230">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-230">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-231">\ server office2016</span><span class="sxs-lookup"><span data-stu-id="de6ba-231">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-232">は、Office 展開ツールとカスタム Configuration.xml ファイル (Customconfig.xml を含むネットワーク共有の場所です。</span><span class="sxs-lookup"><span data-stu-id="de6ba-232">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="de6ba-233">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="de6ba-233">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-234">は Office 展開ツールです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-234">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-235">/download</span><span class="sxs-lookup"><span data-stu-id="de6ba-235">/download</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-236">customConfig.xml ファイルで指定した Office 2016 アプリケーションをダウンロードします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-236">downloads the Office 2016 applications that you specify in the customConfig.xml file.</span></span> <span data-ttu-id="de6ba-237">これらの bits は、ボリュームライセンスを持つ Office 2016 App-v パッケージで後で変換することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-237">These bits can be later converted in an Office 2016 App-V package with Volume Licensing.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="de6ba-238">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="de6ba-238">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-239">ダウンロードプロセスを完了するために必要な XML 構成ファイルを渡します。この例では、customconfig.xml を実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-239">passes the XML configuration file required to complete the download process, in this example, customconfig.xml.</span></span> <span data-ttu-id="de6ba-240">[ダウンロード] コマンドを使用した後、Office アプリケーションは、構成 xml ファイルで指定されている場所 (この例では \ 2016office) にあります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-240">After using the download command, Office applications should be found in the location specified in the configuration xml file, in this example \Server\Office2016.</span></span></p></td>
   </tr>
   </tbody>
   </table>



### <span data-ttu-id="de6ba-241">Office アプリケーションを App-v パッケージに変換する</span><span class="sxs-lookup"><span data-stu-id="de6ba-241">Convert the Office applications into an App-V package</span></span>

<span data-ttu-id="de6ba-242">Office 展開ツールを使用して Office 2016 アプリケーションをダウンロードした後、Office 展開ツールを使用して office 2016 App-v パッケージに変換します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-242">After you download the Office 2016 applications through the Office Deployment Tool, use the Office Deployment Tool to convert them into an Office 2016 App-V package.</span></span> <span data-ttu-id="de6ba-243">ライセンスモデルに対応する手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-243">Complete the steps that correspond to your licensing model.</span></span>

**<span data-ttu-id="de6ba-244">必要な作業の概要:</span><span class="sxs-lookup"><span data-stu-id="de6ba-244">Summary of what you’ll need to do:</span></span>**

-   <span data-ttu-id="de6ba-245">64ビットの Windows コンピューター上で Office 2016 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-245">Create the Office 2016 App-V packages on 64-bit Windows computers.</span></span> <span data-ttu-id="de6ba-246">ただし、パッケージは、32ビットおよび64ビットの Windows 7、Windows 8、8.1、Windows 10 のコンピューターで実行されます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-246">However, the package will run on 32-bit and 64-bit Windows 7, Windows 8 or 8.1, and Windows 10 computers.</span></span>

-   <span data-ttu-id="de6ba-247">Office 展開ツールを使用してサブスクリプションライセンスパッケージの Office App-v パッケージを作成し、CustomConfig.xml 構成ファイルを変更します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-247">Create an Office App-V package for Subscription Licensing package by using the Office Deployment Tool, and then modify the CustomConfig.xml configuration file.</span></span>

    <span data-ttu-id="de6ba-248">次の表は、使用しているライセンスモデルの CustomConfig.xml ファイルに入力する必要がある値をまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-248">The following table summarizes the values you need to enter in the CustomConfig.xml file for the licensing model you’re using.</span></span> <span data-ttu-id="de6ba-249">表に記載されているセクションの手順では、実行する必要がある正確なエントリを指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-249">The steps in the sections that follow the table will specify the exact entries you need to make.</span></span>

><span data-ttu-id="de6ba-250">**Note** &nbsp; 注 &nbsp;Office 展開ツールを使用して、enterprise 用の Microsoft 365 アプリの App-v パッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-250">**Note**&nbsp;&nbsp;You can use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="de6ba-251">ボリュームライセンス版の Office Professional Plus または Office Standard のパッケージの作成はサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-251">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-252">製品 ID</span><span class="sxs-lookup"><span data-stu-id="de6ba-252">Product ID</span></span></th>
<th align="left"><span data-ttu-id="de6ba-253">サブスクリプションのライセンス</span><span class="sxs-lookup"><span data-stu-id="de6ba-253">Subscription Licensing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="de6ba-254">Office 2016</span><span class="sxs-lookup"><span data-stu-id="de6ba-254">Office 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="de6ba-255">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-255">O365ProPlusRetail</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="de6ba-256">Visio 2016 での Office 2016</span><span class="sxs-lookup"><span data-stu-id="de6ba-256">Office 2016 with Visio 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="de6ba-257">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-257">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="de6ba-258">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-258">VisioProRetail</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="de6ba-259">Office 2016 と Visio 2016、および Project 2016</span><span class="sxs-lookup"><span data-stu-id="de6ba-259">Office 2016 with Visio 2016 and Project 2016</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="de6ba-260">O365ProPlusRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-260">O365ProPlusRetail</span></span></p>
<p><span data-ttu-id="de6ba-261">VisioProRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-261">VisioProRetail</span></span></p>
<p><span data-ttu-id="de6ba-262">ProjectProRetail</span><span class="sxs-lookup"><span data-stu-id="de6ba-262">ProjectProRetail</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="de6ba-263">Office アプリケーションを App-v パッケージに変換する方法</span><span class="sxs-lookup"><span data-stu-id="de6ba-263">How to convert the Office applications into an App-V package</span></span>**

1. <span data-ttu-id="de6ba-264">メモ帳で CustomConfig.xml ファイルをもう一度開き、ファイルに次の変更を加えます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-264">In Notepad, reopen the CustomConfig.xml file, and make the following changes to the file:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="de6ba-265">パラメーター</span><span class="sxs-lookup"><span data-stu-id="de6ba-265">Parameter</span></span></th>
   <th align="left"><span data-ttu-id="de6ba-266">値を次のように変更する</span><span class="sxs-lookup"><span data-stu-id="de6ba-266">What to change the value to</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="de6ba-267">SourcePath</span><span class="sxs-lookup"><span data-stu-id="de6ba-267">SourcePath</span></span></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-268">前にダウンロードした Office アプリケーションをポイントします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-268">Point to the Office applications downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="de6ba-269">ProductID</span><span class="sxs-lookup"><span data-stu-id="de6ba-269">ProductID</span></span></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-270">次の例に示すように、サブスクリプションのライセンスを指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-270">Specify Subscription licensing, as shown in the following example:</span></span></p>
   <pre class="syntax" space="preserve"><code>&lt;Configuration&gt;
      &lt;Add SourcePath= &quot;\server\Office 2016&quot; OfficeClientEdition=&quot;32&quot; &gt;
       &lt;Product ID=&quot;O365ProPlusRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
       &lt;Product ID=&quot;VisioProRetail&quot;&gt;
         &lt;Language ID=&quot;en-us&quot; /&gt;
       &lt;/Product&gt;
     &lt;/Add&gt;
   &lt;/Configuration&gt; </code></pre>
   <p><span data-ttu-id="de6ba-271">この例では、サブスクリプションのライセンスを持つパッケージを作成するために、次の変更が加えられました。</span><span class="sxs-lookup"><span data-stu-id="de6ba-271">In this example, the following changes were made to create a package with Subscription licensing:</span></span></p>
   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-272">SourcePath</span><span class="sxs-lookup"><span data-stu-id="de6ba-272">SourcePath</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-273">は、以前にダウンロードした Office アプリケーションを指すように変更されたパスです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-273">is the path, which was changed to point to the Office applications that were downloaded earlier.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="de6ba-274">製品 ID</span><span class="sxs-lookup"><span data-stu-id="de6ba-274">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-275">Office のはに変更されました <code>O365ProPlusRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="de6ba-275">for Office was changed to <code>O365ProPlusRetail</code>.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-276">製品 ID</span><span class="sxs-lookup"><span data-stu-id="de6ba-276">Product ID</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-277">がに変更されました <code>VisioProRetail</code> 。</span><span class="sxs-lookup"><span data-stu-id="de6ba-277">for Visio was changed to <code>VisioProRetail</code>.</span></span></p></td>
   </tr>
   </tbody>
   </table>
   <p></p>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="de6ba-278">ExcludeApp (省略可能)</span><span class="sxs-lookup"><span data-stu-id="de6ba-278">ExcludeApp (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-279">Office 展開ツールによって作成される App-v パッケージに含まれない Office プログラムを指定できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-279">Lets you specify Office programs that you don’t want included in the App-V package that the Office Deployment Tool creates.</span></span> <span data-ttu-id="de6ba-280">たとえば、Access や InfoPath を除外することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-280">For example, you can exclude Access and InfoPath.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="de6ba-281">PACKAGEGUID (省略可能)</span><span class="sxs-lookup"><span data-stu-id="de6ba-281">PACKAGEGUID (optional)</span></span></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-282">既定では、Office 展開ツールによって作成されたすべての App-v パッケージは、同じアプリ-V パッケージ ID を共有します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-282">By default, all App-V packages created by the Office Deployment Tool share the same App-V Package ID.</span></span> <span data-ttu-id="de6ba-283">PACKAGEGUID を使用して、各パッケージに異なるパッケージ ID を指定することができます。これにより、Office 展開ツールによって作成された複数の App-v パッケージを公開して、アプリを管理することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-283">You can use PACKAGEGUID to specify a different package ID for each package, which allows you to publish multiple App-V packages, created by the Office Deployment Tool, and manage them by using the App-V Server.</span></span></p>
   <p><span data-ttu-id="de6ba-284">このパラメーターを使用する場合の例として、さまざまなユーザーに対して異なるパッケージを作成する場合が挙げられます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-284">An example of when to use this parameter is if you create different packages for different users.</span></span> <span data-ttu-id="de6ba-285">たとえば、一部のユーザーについては Office 2016 だけでパッケージを作成し、別のユーザーには Office 2016 と Visio 2016 を使用して別のパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-285">For example, you can create a package with just Office 2016 for some users, and create another package with Office 2016 and Visio 2016 for another set of users.</span></span></p>
<span data-ttu-id="de6ba-286">&gt;<strong>注: </strong> 一意のパッケージ id を使用している場合でも、1つのデバイスに1つの app-v パッケージを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-286">&gt;<strong>Note</strong> Even if you use unique package IDs, you can still deploy only one App-V package to a single device.</span></span>
   </td>
   </tr>
   </tbody>
   </table>



2. <span data-ttu-id="de6ba-287">Office アプリケーションを Office 2016 App-v パッケージに変換するには、/パッケージャーコマンドを使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-287">Use the /packager command to convert the Office applications to an Office 2016 App-V package.</span></span>

   <span data-ttu-id="de6ba-288">以下に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-288">For example:</span></span>

   ``` syntax
   \\server\Office2016\setup.exe /packager \\server\Office2016\Customconfig.xml  \\server\share\Office2016AppV
   ```

   <span data-ttu-id="de6ba-289">次に例を示します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-289">In the example:</span></span>

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <tbody>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-290">\ server office2016</span><span class="sxs-lookup"><span data-stu-id="de6ba-290">\server\Office2016</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-291">は、Office 展開ツールとカスタム Configuration.xml ファイル (Customconfig.xml を含むネットワーク共有の場所です。</span><span class="sxs-lookup"><span data-stu-id="de6ba-291">is the network share location that contains the Office Deployment Tool and the custom Configuration.xml file, Customconfig.xml.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="de6ba-292">Setup.exe</span><span class="sxs-lookup"><span data-stu-id="de6ba-292">Setup.exe</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-293">は Office 展開ツールです。</span><span class="sxs-lookup"><span data-stu-id="de6ba-293">is the Office Deployment Tool.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-294">/パッケージャー</span><span class="sxs-lookup"><span data-stu-id="de6ba-294">/packager</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-295">customConfig.xml ファイルで指定されたライセンスの種類を使用して、Office 2016 App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-295">creates the Office 2016 App-V package with the type of licensing specified in the customConfig.xml file.</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><strong><span data-ttu-id="de6ba-296">\server\Office2016\Customconfig.xml</span><span class="sxs-lookup"><span data-stu-id="de6ba-296">\server\Office2016\Customconfig.xml</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-297">パッケージステージの準備が整った構成 XML ファイル (この場合は、customConfig) を渡します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-297">passes the configuration XML file (in this case customConfig) that has been prepared for the packaging stage.</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><strong><span data-ttu-id="de6ba-298">\ \ sharepoint/Office 2016AppV</span><span class="sxs-lookup"><span data-stu-id="de6ba-298">\server\share\Office 2016AppV</span></span></strong></p></td>
   <td align="left"><p><span data-ttu-id="de6ba-299">新しく作成された Office App-v パッケージの場所を指定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-299">specifies the location of the newly created Office App-V package.</span></span></p></td>
   </tr>
   </tbody>
   </table>



~~~
After you run the **/packager** command, the following folders appear up in the directory where you specified the package should be saved:

-   **App-V Packages** – contains an Office 2016 App-V package and two deployment configuration files.

-   **WorkingDir**

**Note** To troubleshoot any issues, see the log files in the %temp% directory (default).
~~~



3. <span data-ttu-id="de6ba-300">Office 2016 App-v パッケージが正しく動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-300">Verify that the Office 2016 App-V package works correctly:</span></span>

   1.  <span data-ttu-id="de6ba-301">グローバルに作成した Office 2016 App-v パッケージをテストコンピューターに発行し、Office 2016 のショートカットが表示されることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-301">Publish the Office 2016 App-V package, which you created globally, to a test computer, and verify that the Office 2016 shortcuts appear.</span></span>

   2.  <span data-ttu-id="de6ba-302">いくつかの Office 2016 アプリケーション (Excel や Word など) を起動して、パッケージが期待どおりに動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-302">Start a few Office 2016 applications, such as Excel or Word, to ensure that your package is working as expected.</span></span>

## <a href="" id="bkmk-pub-pkg-office"></a><span data-ttu-id="de6ba-303">Office パッケージを App-v 用に発行する-V</span><span class="sxs-lookup"><span data-stu-id="de6ba-303">Publishing the Office package for App-V</span></span>


<span data-ttu-id="de6ba-304">Office パッケージを公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-304">Use the following information to publish an Office package.</span></span>

### <span data-ttu-id="de6ba-305">Office App-v パッケージを発行するためのメソッド</span><span class="sxs-lookup"><span data-stu-id="de6ba-305">Methods for publishing Office App-V packages</span></span>

<span data-ttu-id="de6ba-306">他のパッケージと同じ方法を使用して、Office 2016 用の App-v パッケージを展開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-306">Deploy the App-V package for Office 2016 by using the same methods you use for any other package:</span></span>

-   <span data-ttu-id="de6ba-307">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="de6ba-307">System Center Configuration Manager</span></span>

-   <span data-ttu-id="de6ba-308">App-v Server</span><span class="sxs-lookup"><span data-stu-id="de6ba-308">App-V Server</span></span>

-   <span data-ttu-id="de6ba-309">PowerShell コマンドを使用したスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="de6ba-309">Stand-alone through PowerShell commands</span></span>

### <span data-ttu-id="de6ba-310">発行の前提条件と要件</span><span class="sxs-lookup"><span data-stu-id="de6ba-310">Publishing prerequisites and requirements</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-311">前提条件または要件</span><span class="sxs-lookup"><span data-stu-id="de6ba-311">Prerequisite or requirement</span></span></th>
<th align="left"><span data-ttu-id="de6ba-312">詳細</span><span class="sxs-lookup"><span data-stu-id="de6ba-312">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-313">App-v クライアントで PowerShell スクリプトを有効にする</span><span class="sxs-lookup"><span data-stu-id="de6ba-313">Enable PowerShell scripting on the App-V clients</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-314">Office 2016 パッケージを発行するには、スクリプトを実行する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-314">To publish Office 2016 packages, you must run a script.</span></span></p>
<p><span data-ttu-id="de6ba-315">App-v クライアントでは、パッケージスクリプトは既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="de6ba-315">Package scripts are disabled by default on App-V clients.</span></span> <span data-ttu-id="de6ba-316">スクリプトを有効にするには、次の PowerShell コマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-316">To enable scripting, run the following PowerShell command:</span></span></p>
<pre class="syntax" space="preserve"><code>Set-AppvClientConfiguration –EnablePackageScripts 1</code></pre></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-317">Office 2016 パッケージをグローバルに公開する</span><span class="sxs-lookup"><span data-stu-id="de6ba-317">Publish the Office 2016 package globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-318">Office App-v パッケージの拡張ポイントは、コンピューターレベルでインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-318">Extension points in the Office App-V package require installation at the computer level.</span></span></p>
<p><span data-ttu-id="de6ba-319">コンピューターレベルで公開する場合、必要な操作または再配布は不要であり、Office 2016 パッケージでは、ネイティブにインストールされた Office と同じようにアプリをグローバルに使用できるため、管理者がパッケージをカスタマイズする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-319">When you publish at the computer level, no prerequisite actions or redistributables are needed, and the Office 2016 package globally enables its applications to work like natively installed Office, eliminating the need for administrators to customize packages.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="de6ba-320">Office パッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="de6ba-320">How to publish an Office package</span></span>

<span data-ttu-id="de6ba-321">Office パッケージをグローバルに公開するには、次のコマンドを実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-321">Run the following command to publish an Office package globally:</span></span>

-   `Add-AppvClientPackage <Path_to_AppV_Package> | Publish-AppvClientPackage –global`

-   <span data-ttu-id="de6ba-322">App-v Server の Web 管理コンソールから、ユーザーグループではなく、コンピューターのグループにアクセス許可を追加して、パッケージを対応するグループ内のコンピューターにグローバルに公開することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-322">From the Web Management Console on the App-V Server, you can add permissions to a group of computers instead of to a user group to enable packages to be published globally to the computers in the corresponding group.</span></span>

## <a href="" id="bkmk-custmz-manage-office-pkgs"></a><span data-ttu-id="de6ba-323">Office App-v パッケージのカスタマイズと管理</span><span class="sxs-lookup"><span data-stu-id="de6ba-323">Customizing and managing Office App-V packages</span></span>


<span data-ttu-id="de6ba-324">Office App-v パッケージを管理するには、他のパッケージと同じ操作を実行しますが、次のセクションで説明するように、いくつかの例外があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-324">To manage your Office App-V packages, use the same operations as you would for any other package, but there are a few exceptions, as outlined in the following sections.</span></span>

-   [<span data-ttu-id="de6ba-325">接続グループを使用して Office プラグインを有効にする</span><span class="sxs-lookup"><span data-stu-id="de6ba-325">Enabling Office plug-ins by using connection groups</span></span>](#bkmk-enable-office-plugins)

-   [<span data-ttu-id="de6ba-326">Office 2016 アプリケーションの無効化</span><span class="sxs-lookup"><span data-stu-id="de6ba-326">Disabling Office 2016 applications</span></span>](#bkmk-disable-office-apps)

-   [<span data-ttu-id="de6ba-327">Office 2016 ショートカットを無効にする</span><span class="sxs-lookup"><span data-stu-id="de6ba-327">Disabling Office 2016 shortcuts</span></span>](#bkmk-disable-shortcuts)

-   [<span data-ttu-id="de6ba-328">Office 2016 パッケージのアップグレードの管理</span><span class="sxs-lookup"><span data-stu-id="de6ba-328">Managing Office 2016 package upgrades</span></span>](#bkmk-manage-office-pkg-upgrd)

-   [<span data-ttu-id="de6ba-329">Office で Visio 2016 と Project 2016 を展開する</span><span class="sxs-lookup"><span data-stu-id="de6ba-329">Deploying Visio 2016 and Project 2016 with Office</span></span>](#bkmk-deploy-visio-project)

### <a href="" id="bkmk-enable-office-plugins"></a><span data-ttu-id="de6ba-330">接続グループを使用して Office プラグインを有効にする</span><span class="sxs-lookup"><span data-stu-id="de6ba-330">Enabling Office plug-ins by using connection groups</span></span>

<span data-ttu-id="de6ba-331">このセクションの手順を使用して、office パッケージで Office プラグインを有効にします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-331">Use the steps in this section to enable Office plug-ins with your Office package.</span></span> <span data-ttu-id="de6ba-332">Office プラグインを使うには、アプリ-V シーケンサーを使って、プラグインだけを含む個別のパッケージを作成する必要があります。Office 展開ツールを使用して、プラグインパッケージを作成することはできません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-332">To use Office plug-ins, you must use the App-V Sequencer to create a separate package that contains just the plug-ins. You cannot use the Office Deployment Tool to create the plug-ins package.</span></span> <span data-ttu-id="de6ba-333">次に、次の手順で説明するように、Office パッケージとプラグインパッケージを含む接続グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-333">You then create a connection group that contains the Office package and the plug-ins package, as described in the following steps.</span></span>

**<span data-ttu-id="de6ba-334">Office App-v パッケージのプラグインを有効にするには</span><span class="sxs-lookup"><span data-stu-id="de6ba-334">To enable plug-ins for Office App-V packages</span></span>**

1.  <span data-ttu-id="de6ba-335">App-v Server、System Center Configuration Manager、または PowerShell コマンドレットを使用して、接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-335">Add a Connection Group through App-V Server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

2.  <span data-ttu-id="de6ba-336">App-v Sequencer を使ってプラグインの順序を作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-336">Sequence your plug-ins using the App-V Sequencer.</span></span> <span data-ttu-id="de6ba-337">プラグインの順序を示すために使用されているコンピューターに Office 2016 がインストールされていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-337">Ensure that Office 2016 is installed on the computer being used to sequence the plug-in.</span></span> <span data-ttu-id="de6ba-338">Office 2016 プラグインをシーケンス処理するときは、シーケンスコンピューターで Microsoft 365 アプリを使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-338">It is recommended you use Microsoft 365 Apps for enterprise(non-virtual) on the sequencing computer when you sequence Office 2016 plug-ins.</span></span>

3.  <span data-ttu-id="de6ba-339">目的のプラグインを含む App-v パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-339">Create an App-V package that includes the desired plug-ins.</span></span>

4.  <span data-ttu-id="de6ba-340">App-v server、System Center Configuration Manager、または PowerShell コマンドレットを使用して、接続グループを追加します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-340">Add a Connection Group through App-V server, System Center Configuration Manager, or a PowerShell cmdlet.</span></span>

5.  <span data-ttu-id="de6ba-341">作成した接続グループに並べた Office 2016 アプリとプラグインパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-341">Add the Office 2016 App-V package and the plug-ins package you sequenced to the Connection Group you created.</span></span>

    ><span data-ttu-id="de6ba-342">**重要**接続グループ内のパッケージの順序によって、パッケージコンテンツのマージ順序が決まります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-342">**Important** The order of the packages in the Connection Group determines the order in which the package contents are merged.</span></span> <span data-ttu-id="de6ba-343">接続グループ記述子ファイルで、最初に Office 2016 App-V パッケージを追加してから、プラグインの App-v パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-343">In your Connection group descriptor file, add the Office 2016 App-V package first, and then add the plug-in App-V package.</span></span>



6.  <span data-ttu-id="de6ba-344">両方のパッケージがターゲットコンピューターに公開されていること、およびプラグインパッケージがグローバルに公開された Office 2016 App-v パッケージのグローバル設定と一致するように公開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-344">Ensure that both packages are published to the target computer and that the plug-in package is published globally to match the global settings of the published Office 2016 App-V package.</span></span>

7.  <span data-ttu-id="de6ba-345">プラグインパッケージの展開構成ファイルの設定が、Office 2016 App-v パッケージの設定と同じであることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-345">Verify that the Deployment Configuration File of the plug-in package has the same settings that the Office 2016 App-V package has.</span></span>

    <span data-ttu-id="de6ba-346">Office 2016 App-v パッケージはオペレーティングシステムと統合されているため、プラグインパッケージの設定は一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-346">Since the Office 2016 App-V package is integrated with the operating system, the plug-in package settings should match.</span></span> <span data-ttu-id="de6ba-347">展開構成ファイルで "COM モード" を検索し、プラグインパッケージの値が "Integrated" として設定されていること、および "InProcessEnabled" と "OutOfProcessEnabled" の両方が、公開した Office 2016 App-v パッケージの設定と一致していることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-347">You can search the Deployment Configuration File for “COM Mode” and ensure that your plug-ins package has that value set as “Integrated” and that both "InProcessEnabled" and "OutOfProcessEnabled" match the settings of the Office 2016 App-V package you published.</span></span>

8.  <span data-ttu-id="de6ba-348">展開構成ファイルを開き、**有効なオブジェクト**の値を**false**に設定します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-348">Open the Deployment Configuration File and set the value for **Objects Enabled** to **false**.</span></span>

9.  <span data-ttu-id="de6ba-349">シーケンス後に展開構成ファイルに変更を加えた場合は、プラグインパッケージがファイルと共に公開されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-349">If you made any changes to the Deployment Configuration file after sequencing, ensure that the plug-in package is published with the file.</span></span>

10. <span data-ttu-id="de6ba-350">作成した接続グループが、目的のコンピューターに有効になっていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-350">Ensure that the Connection Group you created is enabled onto your desired computer.</span></span> <span data-ttu-id="de6ba-351">接続グループが有効になっている場合、作成された接続グループは、Office 2016 App-v パッケージを使用している場合、"保留" される可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-351">The Connection Group created will likely “pend” if the Office 2016 App-V package is in use when the Connection Group is enabled.</span></span> <span data-ttu-id="de6ba-352">この問題が発生した場合は、再起動して接続グループを正常に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-352">If that happens, you have to reboot to successfully enable the Connection Group.</span></span>

11. <span data-ttu-id="de6ba-353">両方のパッケージを正常に公開し、接続グループを有効にした後、ターゲットの Office 2016 アプリケーションを起動して、接続グループに公開して追加したプラグインが正常に動作することを確認します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-353">After you successfully publish both packages and enable the Connection Group, start the target Office 2016 application and verify that the plug-in you published and added to the connection group works as expected.</span></span>

### <a href="" id="bkmk-disable-office-apps"></a><span data-ttu-id="de6ba-354">Office 2016 アプリケーションの無効化</span><span class="sxs-lookup"><span data-stu-id="de6ba-354">Disabling Office 2016 applications</span></span>

<span data-ttu-id="de6ba-355">Office App-v パッケージで特定のアプリケーションを無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-355">You may want to disable specific applications in your Office App-V package.</span></span> <span data-ttu-id="de6ba-356">たとえば、Access を無効にすることはできますが、その他のすべての Office アプリケーションはそのまま使用できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-356">For instance, you can disable Access, but leave all other Office application main available.</span></span> <span data-ttu-id="de6ba-357">アプリケーションを無効にすると、エンドユーザーにそのアプリケーションのショートカットが表示されなくなります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-357">When you disable an application, the end user will no longer see the shortcut for that application.</span></span> <span data-ttu-id="de6ba-358">アプリケーションの順序を再設定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="de6ba-358">You do not have to re-sequence the application.</span></span> <span data-ttu-id="de6ba-359">Office 2016 App-v パッケージが公開された後に展開構成ファイルを変更した場合は、変更内容を保存して、Office 2016 App-v パッケージを追加し、新しい展開構成ファイルを使って Office 2016 App-v パッケージアプリケーションに新しい設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-359">When you change the Deployment Configuration File after the Office 2016 App-V package has been published, you will save the changes, add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

><span data-ttu-id="de6ba-360">**注**Office 展開ツールを使用して app-v パッケージを作成するときに、特定の Office アプリケーション (Access や InfoPath など) を除外するには、 **Excludeapp**設定を使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-360">**Note** To exclude specific Office applications (for example, Access and InfoPath) when you create the App-V package with the Office Deployment Tool, use the **ExcludeApp** setting.</span></span>


**<span data-ttu-id="de6ba-361">Office 2016 アプリケーションを無効にするには</span><span class="sxs-lookup"><span data-stu-id="de6ba-361">To disable an Office 2016 application</span></span>**

1.  <span data-ttu-id="de6ba-362">**メモ帳**などのテキストエディターで展開構成ファイルを開き、"アプリケーション" を検索します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-362">Open a Deployment Configuration File with a text editor such as **Notepad** and search for “Applications."</span></span>

2.  <span data-ttu-id="de6ba-363">無効にする Office アプリケーション (Access 2016 など) を検索します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-363">Search for the Office application you want to disable, for example, Access 2016.</span></span>

3.  <span data-ttu-id="de6ba-364">"有効" の値を "true" から "false" に変更します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-364">Change the value of "Enabled" from "true" to "false."</span></span>

4.  <span data-ttu-id="de6ba-365">展開構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-365">Save the Deployment Configuration File.</span></span>

5.  <span data-ttu-id="de6ba-366">新しい展開構成ファイルを使用して、Office 2016 App-v パッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-366">Add the Office 2016 App-V Package with the new Deployment Configuration File.</span></span>

    ```xml
    <Application Id="[{AppVPackageRoot}]\office16\lync.exe" Enabled="true">
      <VisualElements>
        <Name>Lync 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    <Application Id="[(AppVPackageRoot}]\office16\MSACCESS.EXE" Enabled="true">
      <VisualElements>
        <Name>Access 2016</Name>
        <Icon />
        <Description />
      </VisualElements>
    </Application>
    ```

6.  <span data-ttu-id="de6ba-367">Office 2016 App-v パッケージを再度追加し、新しい展開構成ファイルを使用して再公開し、新しい設定を Office 2016 App-v パッケージアプリケーションに適用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-367">Re-add the Office 2016 App-V package, and then republish it with the new Deployment Configuration File to apply the new settings to Office 2016 App-V Package applications.</span></span>

### <a href="" id="bkmk-disable-shortcuts"></a><span data-ttu-id="de6ba-368">Office 2016 ショートカットを無効にする</span><span class="sxs-lookup"><span data-stu-id="de6ba-368">Disabling Office 2016 shortcuts</span></span>

<span data-ttu-id="de6ba-369">特定の Office アプリケーションのショートカットを無効にすることもできます。その場合は、パッケージを非公開にするか、削除する必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-369">You may want to disable shortcuts for certain Office applications instead of unpublishing or removing the package.</span></span> <span data-ttu-id="de6ba-370">次の例は、Microsoft Access のショートカットキーを無効にする方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="de6ba-370">The following example shows how to disable shortcuts for Microsoft Access.</span></span>

**<span data-ttu-id="de6ba-371">Office 2016 アプリケーションのショートカットを無効にするには</span><span class="sxs-lookup"><span data-stu-id="de6ba-371">To disable shortcuts for Office 2016 applications</span></span>**

1.  <span data-ttu-id="de6ba-372">メモ帳で展開構成ファイルを開き、"ショートカット" を検索します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-372">Open a Deployment Configuration File in Notepad and search for “Shortcuts”.</span></span>

2.  <span data-ttu-id="de6ba-373">特定のショートカットを無効にするには、必要のない特定のショートカットを削除またはコメントアウトします。</span><span class="sxs-lookup"><span data-stu-id="de6ba-373">To disable certain shortcuts, delete or comment out the specific shortcuts you don’t want.</span></span> <span data-ttu-id="de6ba-374">サブシステムを常に表示して有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-374">You must keep the subsystem present and enabled.</span></span> <span data-ttu-id="de6ba-375">たとえば、次の例では、サブシステムのショートカットまたは &lt; &gt; &lt; ショートカットをそのままにして &gt; microsoft access ショートカットを無効にして、microsoft access のショートカットを削除します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-375">For example, in the example below, delete the Microsoft Access shortcuts, while keeping the subsystems &lt;shortcut&gt; &lt;/shortcut&gt; intact to disable the Microsoft Access shortcut.</span></span>

    ``` syntax
    Shortcuts

    -->
     <Shortcuts Enabled="true">
      <Extensions>
        <Extension Category="AppV.Shortcut">
          <Shortcut>
           <File>[{Common Programs}]\Microsoft Office 2016\Access 2016.lnk</File>
           <Target>[{AppvPackageRoot}])office16\MSACCESS.EXE</Target>
           <Icon>[{Windows}]\Installer\{90150000-000F-0000-0000-000000FF1CE)\accicons.exe.Ø.ico</Icon>
           <Arguments />
           <WorkingDirectory />
           <AppuserModelId>Microsoft.Office.MSACCESS.EXE.15</AppUserModelId>
           <AppUserModelExcludeFromShowInNewInstall>true</AppUserModelExcludeFromShowInNewInstall>
           <Description>Build a professional app quickly to manage data.</Description>
           <ShowCommand>l</ShowCommand>
           <ApplicationId>[{AppVPackageRoot}]\office16\MSACCESS.EXE</ApplicationId>
        </Shortcut>
    ```

3.  <span data-ttu-id="de6ba-376">展開構成ファイルを保存します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-376">Save the Deployment Configuration File.</span></span>

4.  <span data-ttu-id="de6ba-377">新しい展開構成ファイルを使用して、Office 2016 App-v パッケージを再公開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-377">Republish Office 2016 App-V Package with new Deployment Configuration File.</span></span>

<span data-ttu-id="de6ba-378">他にも多くの設定を変更するには、たとえば、ファイルの種類の関連付け、仮想ファイルシステムなどの App-v パッケージの展開構成を変更します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-378">Many additional settings can be changed through modifying the Deployment Configuration for App-V packages, for example, file type associations, Virtual File System, and more.</span></span> <span data-ttu-id="de6ba-379">展開構成ファイルを使用して App-v パッケージの設定を変更する方法の詳細については、このドキュメントの最後にある「その他のリソース」セクションを参照してください。</span><span class="sxs-lookup"><span data-stu-id="de6ba-379">For additional information on how to use Deployment Configuration Files to change App-V package settings, refer to the additional resources section at the end of this document.</span></span>

### <a href="" id="bkmk-manage-office-pkg-upgrd"></a><span data-ttu-id="de6ba-380">Office 2016 パッケージのアップグレードの管理</span><span class="sxs-lookup"><span data-stu-id="de6ba-380">Managing Office 2016 package upgrades</span></span>

<span data-ttu-id="de6ba-381">Office 2016 パッケージをアップグレードするには、Office 展開ツールを使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-381">To upgrade an Office 2016 package, use the Office Deployment Tool.</span></span> <span data-ttu-id="de6ba-382">以前に展開された Office 2016 パッケージをアップグレードするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-382">To upgrade a previously deployed Office 2016 package, perform the following steps.</span></span>

**<span data-ttu-id="de6ba-383">以前に展開された Office 2016 パッケージのアップグレード方法</span><span class="sxs-lookup"><span data-stu-id="de6ba-383">How to upgrade a previously deployed Office 2016 package</span></span>**

1. <span data-ttu-id="de6ba-384">最新の Office 2016 アプリケーションソフトウェアを使用している Office 展開ツールを使用して、新しい Office 2016 パッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-384">Create a new Office 2016 package through the Office Deployment Tool that uses the most recent Office 2016 application software.</span></span> <span data-ttu-id="de6ba-385">最新の Office 2016 bits は、Office 2016 App-v パッケージを作成するためのダウンロード段階でいつでも入手できます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-385">The most recent Office 2016 bits can always be obtained through the download stage of creating an Office 2016 App-V Package.</span></span> <span data-ttu-id="de6ba-386">新しく作成された Office 2016 パッケージには、最新の更新プログラムと新しいバージョン ID が含まれています。</span><span class="sxs-lookup"><span data-stu-id="de6ba-386">The newly created Office 2016 package will have the most recent updates and a new Version ID.</span></span> <span data-ttu-id="de6ba-387">Office 展開ツールを使用して作成されたすべてのパッケージは、同じ系列になります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-387">All packages created using the Office Deployment Tool have the same lineage.</span></span>

   > <span data-ttu-id="de6ba-388">**注**Office App-V パッケージには2つのバージョン Id があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-388">**Note** Office App-V packages have two Version IDs:</span></span>
   > <ul>
   > <li><span data-ttu-id="de6ba-389">Office 展開ツールを使用して作成されたすべてのパッケージ間で一意の Office 2016 App-v パッケージバージョン ID。</span><span class="sxs-lookup"><span data-stu-id="de6ba-389">An Office 2016 App-V Package Version ID that is unique across all packages created using the Office Deployment Tool.</span></span></li>
   > <li><span data-ttu-id="de6ba-390">新しいバージョンの Office 自体がある場合にのみ変更される AppX マニフェストなどの、2つ目の App-v パッケージバージョン ID である x.x.x.x のバージョン。</span><span class="sxs-lookup"><span data-stu-id="de6ba-390">A second App-V Package Version ID, x.x.x.x for example, in the AppX manifest that will only change if there is a new version of Office itself.</span></span> <span data-ttu-id="de6ba-391">たとえば、アップグレード機能付きの新しい Office 2016 リリースが用意されていて、Office 展開ツールを使用してこれらのアップグレードを組み込むパッケージを作成した場合、X.x.x.x のバージョン ID が変更され、Office バージョンの変更が反映されます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-391">For example, if a new Office 2016 release with upgrades is available, and a package is created through the Office Deployment Tool to incorporate these upgrades, the X.X.X.X version ID will change to reflect that the Office version itself has changed.</span></span> <span data-ttu-id="de6ba-392">App-v server は、x.x.x.x バージョン ID を使ってこのパッケージを区別し、以前に公開されたパッケージへの新しいアップグレードが含まれていることを認識し、その結果として、既存の Office 2016 パッケージへのアップグレードとして発行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-392">The App-V server will use the X.X.X.X version ID to differentiate this package and recognize that it contains new upgrades to the previously published package, and as a result, publish it as an upgrade to the existing Office 2016 package.</span></span></li>
   > </ul>


2. <span data-ttu-id="de6ba-393">新しく作成された Office 2016 App-v パッケージを、新しい更新プログラムを適用するコンピューター上にグローバルに公開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-393">Globally publish the newly created Office 2016 App-V Packages onto computers where you would like to apply the new updates.</span></span> <span data-ttu-id="de6ba-394">新しいパッケージは、古い Office 2016 App-v パッケージの系列と同じであるため、更新プログラムを使用して新しいパッケージを公開しても、古いパッケージに新しい変更が適用されるため、高速になります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-394">Since the new package has the same lineage of the older Office 2016 App-V Package, publishing the new package with the updates will only apply the new changes to the old package, and thus will be fast.</span></span>

3. <span data-ttu-id="de6ba-395">アップグレードは、グローバルに公開された App-v パッケージと同じ方法で適用されます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-395">Upgrades will be applied in the same manner of any globally published App-V Packages.</span></span> <span data-ttu-id="de6ba-396">アプリケーションはおそらく使用されているため、コンピューターが再起動されるまで、アップグレードの遅延が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-396">Because applications will probably be in use, upgrades might be delayed until the computer is rebooted.</span></span>


### <a href="" id="bkmk-deploy-visio-project"></a><span data-ttu-id="de6ba-397">Office で Visio 2016 と Project 2016 を展開する</span><span class="sxs-lookup"><span data-stu-id="de6ba-397">Deploying Visio 2016 and Project 2016 with Office</span></span>

<span data-ttu-id="de6ba-398">次の表では、Visio 2016 と Project 2016 を Office と共に展開するための要件とオプションについて説明します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-398">The following table describes the requirements and options for deploying Visio 2016 and Project 2016 with Office.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-399">タスク</span><span class="sxs-lookup"><span data-stu-id="de6ba-399">Task</span></span></th>
<th align="left"><span data-ttu-id="de6ba-400">詳細</span><span class="sxs-lookup"><span data-stu-id="de6ba-400">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-401">Visio 2016 および Project 2016 を Office と共にパッケージ化して発行するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="de6ba-401">How do I package and publish Visio 2016 and Project 2016 with Office?</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-402">Office と同じパッケージに Visio 2016 と Project 2016 を含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="de6ba-402">You must include Visio 2016 and Project 2016 in the same package with Office.</span></span></p>
<p><span data-ttu-id="de6ba-403">Office を展開していない場合は、このトピックで説明されているパッケージ化、発行、展開の要件に従う限り、Visio または Project を含むパッケージを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-403">If you aren’t deploying Office, you can create a package that contains Visio and/or Project, as long as you follow the packaging, publishing, and deployment requirements described in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-404">Visio 2016 と Project 2016 を特定のユーザーに展開するにはどうすればよいですか?</span><span class="sxs-lookup"><span data-stu-id="de6ba-404">How can I deploy Visio 2016 and Project 2016 to specific users?</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-405">以下の方法のうちのいずれか 1 つを使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-405">Use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="de6ba-406">目的の処理</span><span class="sxs-lookup"><span data-stu-id="de6ba-406">If you want to...</span></span></th>
<th align="left"><span data-ttu-id="de6ba-407">...次に、この方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-407">...then use this method</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="de6ba-408">2つの異なるパッケージを作成し、それぞれを別のユーザーグループに展開する</span><span class="sxs-lookup"><span data-stu-id="de6ba-408">Create two different packages and deploy each one to a different group of users</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-409">次のパッケージを作成して展開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-409">Create and deploy the following packages:</span></span></p>
<ul>
<li><p><span data-ttu-id="de6ba-410">Office のみを含むパッケージで、ユーザーが Office のみを必要とするコンピューターに展開されます。</span><span class="sxs-lookup"><span data-stu-id="de6ba-410">A package that contains only Office - deploy to computers whose users need only Office.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-411">Office、Visio、Project を含むパッケージ。ユーザーが3つのアプリケーションを必要とするコンピューターに展開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-411">A package that contains Office, Visio, and Project - deploy to computers whose users need all three applications.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="de6ba-412">組織全体に対してパッケージを1つだけ追加する場合、またはコンピューターを共有しているユーザーがいる場合は、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="de6ba-412">If you want only one package for the whole organization, or if you have users who share computers:</span></span></p></td>
<td align="left"><p><span data-ttu-id="de6ba-413">次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-413">Follows these steps:</span></span></p>
<ol>
<li><p><span data-ttu-id="de6ba-414">Office、Visio、および Project を含むパッケージを作成します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-414">Create a package that contains Office, Visio, and Project.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-415">パッケージをすべてのユーザーに展開します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-415">Deploy the package to all users.</span></span></p></li>
<li><p><span data-ttu-id="de6ba-416"><a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker を使用し </a> て、特定のユーザーによる Visio と Project の使用を防止します。</span><span class="sxs-lookup"><span data-stu-id="de6ba-416">Use <a href="https://technet.microsoft.com/library/dd723678.aspx" data-raw-source="[Microsoft AppLocker](https://technet.microsoft.com/library/dd723678.aspx)">Microsoft AppLocker</a> to prevent specific users from using Visio and Project.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="de6ba-417">その他の情報</span><span class="sxs-lookup"><span data-stu-id="de6ba-417">Additional resources</span></span>


[<span data-ttu-id="de6ba-418">APP-V を使用した Microsoft Office 2013 の展開</span><span class="sxs-lookup"><span data-stu-id="de6ba-418">Deploying Microsoft Office 2013 by Using App-V</span></span>](deploying-microsoft-office-2013-by-using-app-v.md)

[<span data-ttu-id="de6ba-419">APP-V を使用した Microsoft Office 2010 の展開</span><span class="sxs-lookup"><span data-stu-id="de6ba-419">Deploying Microsoft Office 2010 by Using App-V</span></span>](deploying-microsoft-office-2010-by-using-app-v.md)

[<span data-ttu-id="de6ba-420">クイック実行用の Office 2016 展開ツール</span><span class="sxs-lookup"><span data-stu-id="de6ba-420">Office 2016 Deployment Tool for Click-to-Run</span></span>](https://www.microsoft.com/download/details.aspx?id=49117)

**<span data-ttu-id="de6ba-421">接続グループ</span><span class="sxs-lookup"><span data-stu-id="de6ba-421">Connection Groups</span></span>**

[<span data-ttu-id="de6ba-422">Microsoft App での接続グループの展開-V v5</span><span class="sxs-lookup"><span data-stu-id="de6ba-422">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="de6ba-423">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="de6ba-423">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="de6ba-424">動的構成</span><span class="sxs-lookup"><span data-stu-id="de6ba-424">Dynamic Configuration</span></span>**

[<span data-ttu-id="de6ba-425">App-V 5.1 の動的構成について</span><span class="sxs-lookup"><span data-stu-id="de6ba-425">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)





