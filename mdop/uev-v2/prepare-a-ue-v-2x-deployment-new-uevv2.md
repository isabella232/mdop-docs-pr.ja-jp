---
title: UE-V の展開を準備する
description: UE-V の展開を準備する
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826424"
---
# <span data-ttu-id="0bc6e-103">UE-V の展開を準備する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-103">Prepare a UE-V 2.x Deployment</span></span>


<span data-ttu-id="0bc6e-104">Microsoft User Experience Virtualization (UE-V) 2.0 または2.1 を、ユーザーがエンタープライズでアクセスするデバイス間で設定を同期するためのソリューションとして展開する前に、いくつかの計画と準備を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-104">There is some planning and preparation to do before you deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 as a solution for synchronizing settings between devices that users access in your enterprise.</span></span> <span data-ttu-id="0bc6e-105">このトピックでは、展開を成功させるために、どのような種類の展開を事前に決定するかを決定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-105">This topic helps you determine what type of deployment you'll be doing and what preparation you can make beforehand so that your deployment is successful.</span></span>

<span data-ttu-id="0bc6e-106">まず、UE-V を展開するタスクを見てみましょう。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-106">First, let’s look at the tasks you’ll do to deploy UE-V:</span></span>

-   <span data-ttu-id="0bc6e-107">UE-V の展開を計画する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-107">Plan your UE-V Deployment</span></span>

    <span data-ttu-id="0bc6e-108">何かを展開する前に、展開する UE-V 機能を決定するために、少し計画を立てることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-108">Before you deploy anything, a good first step is to do a little bit of planning so that you can determine which UE-V features you’ll deploy.</span></span> <span data-ttu-id="0bc6e-109">このページから離れる場合は、以下の計画情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-109">So if you leave this page, make sure you come back and read through the planning information below.</span></span>

-   [<span data-ttu-id="0bc6e-110">UE-V 2.x の必要な機能を展開する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-110">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    <span data-ttu-id="0bc6e-111">すべての UE-V の展開では、次の操作が必要です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-111">Every UE-V deployment requires these activities:</span></span>

    -   [<span data-ttu-id="0bc6e-112">設定の保存場所を定義する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-112">Define a settings storage location</span></span>](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [<span data-ttu-id="0bc6e-113">UE-V エージェントを展開して UE-V 構成を管理する方法を決定する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-113">Decide how to deploy the UE-V Agent and manage UE-V configurations</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   <span data-ttu-id="0bc6e-114">設定を同期する必要があるすべてのユーザーコンピューターに[Ue-v agent をインストール](https://technet.microsoft.com/library/dn458891.aspx#agent)する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-114">[Install the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) on every user computer that needs settings synchronized</span></span>

-   <span data-ttu-id="0bc6e-115">必要に応じ[て、カスタムアプリケーションの ue-v 2. x を展開](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)することができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-115">Optionally, you can [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span></span>

    <span data-ttu-id="0bc6e-116">計画は、カスタムアプリケーション (サードパーティまたは基幹業務) の設定の同期を UE-V がサポートしているかどうかを確認するのに役立ちます。これには、次のような UE-V の機能が必要です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-116">Planning will help you figure out whether you want UE-V to support the synchronization of settings for custom applications (third-party or line-of-business), which requires these UE-V features:</span></span>

    -   <span data-ttu-id="0bc6e-117">カスタムのアプリケーション設定を同期するために必要なカスタム設定の場所テンプレートを作成、編集、検証できるように[、UEV Generator をインストール](https://technet.microsoft.com/library/dn458942.aspx#uevgen)します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-117">[Install the UEV Generator](https://technet.microsoft.com/library/dn458942.aspx#uevgen) so you can create, edit, and validate the custom settings location templates required to synchronize custom application settings</span></span>

    -   <span data-ttu-id="0bc6e-118">UE-V Generator を使用して[カスタム設定場所テンプレートを作成](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-118">[Create custom settings location templates](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates) by using the UE-V Generator</span></span>

    -   <span data-ttu-id="0bc6e-119">カスタム設定の場所テンプレートを格納するために使用する[ue-v 設定テンプレートカタログを展開](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-119">[Deploy a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue) that you use to store your custom settings location templates</span></span>

<span data-ttu-id="0bc6e-120">このワークフロー図は、UE-V の展開と、企業への UE-V の展開方法を決定する決定についての高度な知識を提供します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-120">This workflow diagram provides a high-level understanding of a UE-V deployment and the decisions that determine how you deploy UE-V in your enterprise.</span></span>

![deploymentworkflow](images/deploymentworkflow.png)

<span data-ttu-id="0bc6e-122">**Ue-v の展開を計画する:** 最初に、展開する UE-V コンポーネントを特定できるように、若干の計画を立てておきます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-122">**Planning a UE-V deployment:** First, you want to do a little bit of planning so that you can determine which UE-V components you’ll be deploying.</span></span> <span data-ttu-id="0bc6e-123">UE-V の展開を計画するには、次のことを行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-123">Planning a UE-V deployment involves these things:</span></span>

-   [<span data-ttu-id="0bc6e-124">カスタムアプリケーションの設定を同期するかどうかを決定する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-124">Decide whether to synchronize settings for custom applications</span></span>](#deciding)

    <span data-ttu-id="0bc6e-125">これにより、展開中に UE-V Generator をインストールするかどうかを決定します。これにより、カスタム設定の場所テンプレートを作成できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-125">This determines whether you will install the UE-V Generator during deployment, which lets you create custom settings location templates.</span></span> <span data-ttu-id="0bc6e-126">次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-126">It involves the following:</span></span>

    <span data-ttu-id="0bc6e-127">[Ue-v 展開で自動的に同期される設定](#autosyncsettings)を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-127">Review the [settings that are synchronized automatically in a UE-V deployment](#autosyncsettings).</span></span>

    <span data-ttu-id="0bc6e-128">[他のアプリケーションの設定を同期する必要があるかどうかを確認](#determinesettingssync)します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-128">[Determine whether you need settings synchronized for other applications](#determinesettingssync).</span></span>

-   <span data-ttu-id="0bc6e-129">高可用性、キャパシティ計画など、 [ue-v の展開に関するその他の考慮事項](#considerations)を確認します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-129">Review [other considerations for deploying UE-V](#considerations), such as high availability and capacity planning.</span></span>

-   [<span data-ttu-id="0bc6e-130">UE-V の前提条件とサポートされる構成を確認する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-130">Confirm prerequisites and supported configurations for UE-V</span></span>](#prereqs)

## <a href="" id="deciding"></a><span data-ttu-id="0bc6e-131">カスタムアプリケーションの設定を同期するかどうかを決定する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-131">Decide Whether to Synchronize Settings for Custom Applications</span></span>


<span data-ttu-id="0bc6e-132">UE-V の展開では、多くの設定が自動的に同期されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-132">In a UE-V deployment, many settings are automatically synchronized.</span></span> <span data-ttu-id="0bc6e-133">しかし、UE-V をカスタマイズして、基幹業務やサードパーティのアプリなど、他のアプリケーションの設定を同期することもできます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-133">But you can also customize UE-V to synchronize settings for other applications, such as line-of-business and third-party apps.</span></span>

<span data-ttu-id="0bc6e-134">UE-V を使用してカスタムアプリケーションの設定を同期するかどうかを判断することは、UE-V の展開を計画するうえで最も重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-134">Deciding if you want UE-V to synchronize settings for custom applications is probably the most important part of planning your UE-V deployment.</span></span> <span data-ttu-id="0bc6e-135">このセクションのトピックは、この決定を行うのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-135">The topics in this section will help you make that decision.</span></span>

### <a href="" id="autosyncsettings"></a><span data-ttu-id="0bc6e-136">UE-V 展開で自動的に同期される設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-136">Settings that are automatically synchronized in a UE-V deployment</span></span>

<span data-ttu-id="0bc6e-137">このセクションでは、UE-V で既定で同期される設定について説明します。次の情報が含まれます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-137">This section provides information about the settings that are synchronized by default in UE-V, including the following:</span></span>

<span data-ttu-id="0bc6e-138">既定で同期されている設定を持つデスクトップアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-138">Desktop applications whose settings are synchronized by default</span></span>

<span data-ttu-id="0bc6e-139">既定で同期される Windows デスクトップの設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-139">Windows desktop settings that are synchronized by default</span></span>

<span data-ttu-id="0bc6e-140">Windows アプリ設定の同期のサポートのステートメント</span><span class="sxs-lookup"><span data-stu-id="0bc6e-140">A statement of support for Windows app setting synchronization</span></span>

<span data-ttu-id="0bc6e-141">UE-V で同期されている特定の Microsoft Office 2013、Microsoft Office 2010、および Microsoft Office 2007 の設定の完全な一覧をダウンロードするには、 [Microsoft office のユーザーエクスペリエンスの仮想化 (ue-v) 設定テンプレート](https://www.microsoft.com/download/details.aspx?id=46367)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-141">See [User Experience Virtualization (UE-V) settings templates for Microsoft Office](https://www.microsoft.com/download/details.aspx?id=46367) to download a complete list of the specific Microsoft Office 2013, Microsoft Office 2010, and Microsoft Office 2007 settings that are synchronized by UE-V.</span></span>

### <span data-ttu-id="0bc6e-142">UE-V 2.1 および UE-V 2.1 SP1 で既定で同期されているデスクトップアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-142">Desktop applications synchronized by default in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="0bc6e-143">UE-V 2.1 または 2.1 SP1 エージェントをインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする既定の設定場所テンプレートのグループが登録されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-143">When you install the UE-V 2.1 or 2.1 SP1 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="0bc6e-144">ヒント</span><span class="sxs-lookup"><span data-stu-id="0bc6e-144">Tip</span></span>**  
<span data-ttu-id="0bc6e-145">**Microsoft office 2007 の設定の同期**-ue-v 2.1 および 2.1 SP1 では、設定場所テンプレートが、Office 2007 アプリケーションに既定で含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-145">**Microsoft Office 2007 Settings Synchronization** – In UE-V 2.1 and 2.1 SP1, a settings location template is no longer included by default for Office 2007 applications.</span></span> <span data-ttu-id="0bc6e-146">ただし、Office 2007 テンプレートは UE-V 2.0 以前からも使用できます。また、 [ue-v テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkID=246589)からテンプレートを取得することもできます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-146">However, you can still use Office 2007 templates from UE-V 2.0 or earlier and can get the templates from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="0bc6e-147">アプリケーションカテゴリ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-147">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-148">説明</span><span class="sxs-lookup"><span data-stu-id="0bc6e-148">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-149">Microsoft Office 2010 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-149">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="0bc6e-150">(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</span><span class="sxs-lookup"><span data-stu-id="0bc6e-150">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-151">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-151">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="0bc6e-152">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-152">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="0bc6e-153">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-153">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="0bc6e-154">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-154">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="0bc6e-155">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-155">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="0bc6e-156">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-156">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="0bc6e-157">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-157">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="0bc6e-158">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-158">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="0bc6e-159">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-159">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="0bc6e-160">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-160">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="0bc6e-161">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-161">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="0bc6e-162">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-162">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="0bc6e-163">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-163">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-164">Microsoft Office 2013 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-164">Microsoft Office 2013 applications</span></span></p>
<p><span data-ttu-id="0bc6e-165">(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</span><span class="sxs-lookup"><span data-stu-id="0bc6e-165">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-166">Microsoft Word 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-166">Microsoft Word 2013</span></span></p>
<p><span data-ttu-id="0bc6e-167">Microsoft Excel 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-167">Microsoft Excel 2013</span></span></p>
<p><span data-ttu-id="0bc6e-168">Microsoft Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-168">Microsoft Outlook 2013</span></span></p>
<p><span data-ttu-id="0bc6e-169">Microsoft Access 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-169">Microsoft Access 2013</span></span></p>
<p><span data-ttu-id="0bc6e-170">Microsoft Project 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-170">Microsoft Project 2013</span></span></p>
<p><span data-ttu-id="0bc6e-171">Microsoft PowerPoint 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-171">Microsoft PowerPoint 2013</span></span></p>
<p><span data-ttu-id="0bc6e-172">Microsoft Publisher 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-172">Microsoft Publisher 2013</span></span></p>
<p><span data-ttu-id="0bc6e-173">Microsoft Visio 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-173">Microsoft Visio 2013</span></span></p>
<p><span data-ttu-id="0bc6e-174">Microsoft InfoPath 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-174">Microsoft InfoPath 2013</span></span></p>
<p><span data-ttu-id="0bc6e-175">Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-175">Microsoft Lync 2013</span></span></p>
<p><span data-ttu-id="0bc6e-176">Microsoft OneNote 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-176">Microsoft OneNote 2013</span></span></p>
<p><span data-ttu-id="0bc6e-177">Microsoft SharePoint Designer 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-177">Microsoft SharePoint Designer 2013</span></span></p>
<p><span data-ttu-id="0bc6e-178">Microsoft Office 2013 アップロードセンター</span><span class="sxs-lookup"><span data-stu-id="0bc6e-178">Microsoft Office 2013 Upload Center</span></span></p>
<p><span data-ttu-id="0bc6e-179">Microsoft OneDrive for Business 2013</span><span class="sxs-lookup"><span data-stu-id="0bc6e-179">Microsoft OneDrive for Business 2013</span></span></p>
<p><span data-ttu-id="0bc6e-180">UE-V 2.1 および 2.1 SP1 の Microsoft Office 2013 設定の場所テンプレートには、強化された Outlook 署名のサポートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-180">The UE-V 2.1 and 2.1 SP1 Microsoft Office 2013 settings location templates include improved Outlook signature support.</span></span> <span data-ttu-id="0bc6e-181">新規、返信、転送メールの既定の署名設定の同期が追加されました。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-181">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0bc6e-182">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-182">Note</span></span></strong><br/><p><span data-ttu-id="0bc6e-183">ユーザーが Outlook の署名を同期するすべてのデバイスに対して、Outlook プロファイルを作成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-183">An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="0bc6e-184">プロファイルがまだ作成されていない場合は、ユーザーがそれを作成し、そのデバイスで Outlook を再起動して、署名の同期を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-184">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-185">ブラウザーのオプション: Internet Explorer 8、Internet Explorer 9、Internet Explorer 10、Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="0bc6e-185">Browser options: Internet Explorer 8, Internet Explorer 9, Internet Explorer 10, and Internet Explorer 11</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-186">[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-186">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0bc6e-187">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-187">Note</span></span></strong><br/><p><span data-ttu-id="0bc6e-188">UE-V では、Internet Explorer cookie のローミング設定は行われません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-188">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-189">Windows アクセサリ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-189">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-190">Microsoft 電卓、メモ帳、ワードパッド。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-190">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="0bc6e-191">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-191">Note</span></span>**  
<span data-ttu-id="0bc6e-192">UE-V 2.1 SP1 は、以前のオペレーティングシステムでの Windows 10 と Microsoft 電卓の間の設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-192">UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>



### <span data-ttu-id="0bc6e-193">UE-V 2.0 で既定で同期されているデスクトップアプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-193">Desktop applications synchronized by default in UE-V 2.0</span></span>

<span data-ttu-id="0bc6e-194">UE-V 2.0 Agent をインストールすると、これらの一般的な Microsoft アプリケーションの設定値をキャプチャする、設定の場所テンプレートの既定のグループが登録されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-194">When you install the UE-V 2.0 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="0bc6e-195">ヒント</span><span class="sxs-lookup"><span data-stu-id="0bc6e-195">Tip</span></span>**  
<span data-ttu-id="0bc6e-196">**Microsoft office 2013 の設定の同期**-Ue-v 2.0 では、Office 2013 アプリケーションには既定で設定場所テンプレートが含まれていませんが、 [ue-v テンプレートギャラリー](https://go.microsoft.com/fwlink/p/?LinkID=246589)からダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-196">**Microsoft Office 2013 Settings Synchronization** – In UE-V 2.0, a settings location template is not included by default for Office 2013 applications, but is available for download from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span> <span data-ttu-id="0bc6e-197">[Office 2013 と ue-v 2.0 を同期すると](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)、office 2013 の設定を同期するサポートされているテンプレートの詳細が提供されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-197">[Synchronizing Office 2013 with UE-V 2.0](synchronizing-office-2013-with-ue-v-20-both-uevv2.md) provides details about the supported templates that synchronize Office 2013 settings.</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="0bc6e-198">アプリケーションカテゴリ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-198">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-199">説明</span><span class="sxs-lookup"><span data-stu-id="0bc6e-199">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-200">Microsoft Office 2007 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-200">Microsoft Office 2007 applications</span></span></p>
<p><span data-ttu-id="0bc6e-201">(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</span><span class="sxs-lookup"><span data-stu-id="0bc6e-201">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-202">Microsoft Access 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-202">Microsoft Access 2007</span></span></p>
<p><span data-ttu-id="0bc6e-203">Microsoft Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-203">Microsoft Communicator 2007</span></span></p>
<p><span data-ttu-id="0bc6e-204">Microsoft Excel 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-204">Microsoft Excel 2007</span></span></p>
<p><span data-ttu-id="0bc6e-205">Microsoft InfoPath 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-205">Microsoft InfoPath 2007</span></span></p>
<p><span data-ttu-id="0bc6e-206">Microsoft OneNote 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-206">Microsoft OneNote 2007</span></span></p>
<p><span data-ttu-id="0bc6e-207">Microsoft Outlook 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-207">Microsoft Outlook 2007</span></span></p>
<p><span data-ttu-id="0bc6e-208">Microsoft PowerPoint 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-208">Microsoft PowerPoint 2007</span></span></p>
<p><span data-ttu-id="0bc6e-209">Microsoft Project 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-209">Microsoft Project 2007</span></span></p>
<p><span data-ttu-id="0bc6e-210">Microsoft Publisher 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-210">Microsoft Publisher 2007</span></span></p>
<p><span data-ttu-id="0bc6e-211">Microsoft SharePoint Designer 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-211">Microsoft SharePoint Designer 2007</span></span></p>
<p><span data-ttu-id="0bc6e-212">Microsoft Visio 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-212">Microsoft Visio 2007</span></span></p>
<p><span data-ttu-id="0bc6e-213">Microsoft Word 2007</span><span class="sxs-lookup"><span data-stu-id="0bc6e-213">Microsoft Word 2007</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-214">Microsoft Office 2010 アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-214">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="0bc6e-215">(同期された <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> すべての設定のリストをダウンロードします </a> )</span><span class="sxs-lookup"><span data-stu-id="0bc6e-215">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-216">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-216">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="0bc6e-217">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-217">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="0bc6e-218">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-218">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="0bc6e-219">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-219">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="0bc6e-220">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-220">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="0bc6e-221">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-221">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="0bc6e-222">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-222">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="0bc6e-223">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-223">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="0bc6e-224">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-224">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="0bc6e-225">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-225">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="0bc6e-226">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-226">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="0bc6e-227">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-227">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="0bc6e-228">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="0bc6e-228">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-229">ブラウザーのオプション: Internet Explorer 8、Internet Explorer 9、Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="0bc6e-229">Browser options: Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-230">[お気に入り]、[ホーム] ページ、[タブ]、およびツールバー。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-230">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0bc6e-231">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-231">Note</span></span></strong><br/><p><span data-ttu-id="0bc6e-232">UE-V では、Internet Explorer cookie のローミング設定は行われません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-232">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-233">Windows アクセサリ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-233">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-234">Microsoft 電卓、メモ帳、ワードパッド。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-234">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a><span data-ttu-id="0bc6e-235">Windows の設定が既定で同期されている</span><span class="sxs-lookup"><span data-stu-id="0bc6e-235">Windows settings synchronized by default</span></span>

<span data-ttu-id="0bc6e-236">UE-V には、これらの Windows 設定の設定値をキャプチャする設定場所テンプレートが含まれています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-236">UE-V includes settings location templates that capture settings values for these Windows settings.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0bc6e-237">Windows の設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-237">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-238">説明</span><span class="sxs-lookup"><span data-stu-id="0bc6e-238">Description</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-239">適用対象</span><span class="sxs-lookup"><span data-stu-id="0bc6e-239">Apply on</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-240">エクスポートする</span><span class="sxs-lookup"><span data-stu-id="0bc6e-240">Export on</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-241">既定の状態</span><span class="sxs-lookup"><span data-stu-id="0bc6e-241">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-242">デスクトップの背景</span><span class="sxs-lookup"><span data-stu-id="0bc6e-242">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-243">現在アクティブなデスクトップの背景または壁紙。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-243">Currently active desktop background or wallpaper.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-244">ログオン、ロック解除、リモート接続、スケジュールされたタスクイベント。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-244">Logon, unlock, remote connect, Scheduled Task events.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-245">ログオフ、ロック、リモート切断、 <strong> 会社設定センターで [今すぐ同期] をクリックするか、スケジュールされた </strong> タスクの間隔</span><span class="sxs-lookup"><span data-stu-id="0bc6e-245">Logoff, lock, remote disconnect, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-246">有効</span><span class="sxs-lookup"><span data-stu-id="0bc6e-246">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-247">コンピューターの簡単操作</span><span class="sxs-lookup"><span data-stu-id="0bc6e-247">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-248">アクセシビリティと入力の設定、Microsoft 拡大鏡、ナレーター、スクリーンキーボード。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-248">Accessibility and input settings, Microsoft Magnifier, Narrator, and on-Screen Keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-249">ログオンのみ。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-249">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-250">ログオフ、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクの間隔</span><span class="sxs-lookup"><span data-stu-id="0bc6e-250">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-251">有効</span><span class="sxs-lookup"><span data-stu-id="0bc6e-251">Enabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-252">デスクトップの設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-252">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-253">[スタート] メニューとタスクバーの設定、フォルダーオプション、既定のデスクトップアイコン、追加の時計、および地域と言語の設定。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-253">Start menu and Taskbar settings, Folder options, Default desktop icons, Additional clocks, and Region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-254">ログオンのみ。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-254">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-255">ログオフ、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする、 </strong> またはスケジュールされたタスク</span><span class="sxs-lookup"><span data-stu-id="0bc6e-255">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-256">有効</span><span class="sxs-lookup"><span data-stu-id="0bc6e-256">Enabled</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="0bc6e-257">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-257">Note</span></span>**  
<span data-ttu-id="0bc6e-258">Windows 8 以降、UE-V は、スタート画面に関連する項目や場所などの設定をローミングしません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-258">Starting in Windows 8, UE-V does not roam settings related to the Start screen, such as items and locations.</span></span> <span data-ttu-id="0bc6e-259">また、UE-V は、固定されたタスクバー項目または Windows のファイルショートカットの同期をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-259">In addition, UE-V does not support synchronization of pinned taskbar items or Windows file shortcuts.</span></span>



**<span data-ttu-id="0bc6e-260">重要</span><span class="sxs-lookup"><span data-stu-id="0bc6e-260">Important</span></span>**  
<span data-ttu-id="0bc6e-261">UE-V 2.1 SP1 では、Windows 10 デバイス間のタスクバーの設定が移動します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-261">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="0bc6e-262">ただし、UE-V は、以前のオペレーティングシステムが実行されている Windows 10 デバイスとデバイスとの間で、タスクバーの設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-262">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0bc6e-263">設定グループ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-263">Settings group</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-264">カテゴリ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-264">Category</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-265">回収</span><span class="sxs-lookup"><span data-stu-id="0bc6e-265">Capture</span></span></th>
<th align="left"><span data-ttu-id="0bc6e-266">[適用]</span><span class="sxs-lookup"><span data-stu-id="0bc6e-266">Apply</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0bc6e-267">アプリケーションの設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-267">Application Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-268">Windows アプリ  </span><span class="sxs-lookup"><span data-stu-id="0bc6e-268">Windows apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-269">アプリを閉じる</span><span class="sxs-lookup"><span data-stu-id="0bc6e-269">Close app</span></span></p>
<p><span data-ttu-id="0bc6e-270">Windows アプリの設定の変更イベント</span><span class="sxs-lookup"><span data-stu-id="0bc6e-270">Windows app settings change event</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-271">起動時に UE-V App Monitor を起動する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-271">Start the UE-V App Monitor at startup</span></span></p>
<p><span data-ttu-id="0bc6e-272">アプリを開く</span><span class="sxs-lookup"><span data-stu-id="0bc6e-272">Open app</span></span></p>
<p><span data-ttu-id="0bc6e-273">Windows アプリの設定の変更イベント</span><span class="sxs-lookup"><span data-stu-id="0bc6e-273">Windows App Settings change event</span></span></p>
<p><span data-ttu-id="0bc6e-274">設定パッケージの到着</span><span class="sxs-lookup"><span data-stu-id="0bc6e-274">Arrival of a settings package</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-275">デスクトップ アプリケーション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-275">Desktop applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-276">アプリケーションが閉じる</span><span class="sxs-lookup"><span data-stu-id="0bc6e-276">Application closes</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-277">アプリケーションが開いて閉じます</span><span class="sxs-lookup"><span data-stu-id="0bc6e-277">Application opens and closes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0bc6e-278">デスクトップの設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-278">Desktop settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-279">デスクトップの背景</span><span class="sxs-lookup"><span data-stu-id="0bc6e-279">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-280">ロックまたはログオフ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-280">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-281">ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-281">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-282">簡単操作 (一般的–アクセシビリティ、ナレーター、拡大鏡、スクリーンキーボード)</span><span class="sxs-lookup"><span data-stu-id="0bc6e-282">Ease of Access (Common – Accessibility, Narrator, Magnifier, On-Screen-Keyboard)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-283">ロックまたはログオフ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-283">Lock or Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-284">ログオン</span><span class="sxs-lookup"><span data-stu-id="0bc6e-284">Logon</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-285">簡単操作 (シェルオーディオ、アクセシビリティ、キーボード、マウス)</span><span class="sxs-lookup"><span data-stu-id="0bc6e-285">Ease of Access (Shell - Audio, Accessibility, Keyboard, Mouse)</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-286">ロックまたはログオフ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-286">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-287">ログオン、ロック解除、リモート接続、新しいパッケージ到着の通知、ユーザーが <strong> 会社設定センターで [今すぐ同期] をクリックする </strong> か、スケジュールされたタスクが実行される</span><span class="sxs-lookup"><span data-stu-id="0bc6e-287">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-288">デスクトップの設定</span><span class="sxs-lookup"><span data-stu-id="0bc6e-288">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-289">ロックまたはログオフ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-289">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-290">ログオン</span><span class="sxs-lookup"><span data-stu-id="0bc6e-290">Logon</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="0bc6e-291">UE-V-Windows アプリのサポート</span><span class="sxs-lookup"><span data-stu-id="0bc6e-291">UE-V-support for Windows Apps</span></span>

<span data-ttu-id="0bc6e-292">Windows アプリの場合、アプリの開発者は同期される設定を指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-292">For Windows apps, the app developer specifies the settings that are synchronized.</span></span> <span data-ttu-id="0bc6e-293">どの Windows アプリで設定の同期を有効にするかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-293">You can specify which Windows apps are enabled for settings synchronization.</span></span>

<span data-ttu-id="0bc6e-294">Windows PowerShell のコマンドプロンプトで、コンピューターの設定をパッケージファミリ名、有効状態、有効なソースに同期できる Windows アプリの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-294">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="0bc6e-295">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-295">Note</span></span>**  
<span data-ttu-id="0bc6e-296">Windows 8 では、ドメインユーザーがサインイン資格情報を Microsoft アカウントにリンクした場合、UE-V は Windows アプリの設定を同期しません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-296">As of Windows 8, UE-V does not synchronize Windows app settings if the domain user links their sign-in credentials to their Microsoft Account.</span></span> <span data-ttu-id="0bc6e-297">このリンクにより、設定が Microsoft OneDrive (UE-V) に同期され、Windows アプリの設定の同期が無効になります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-297">This linking synchronizes settings to Microsoft OneDrive so UE-V, which disables synchronization of Windows app settings.</span></span>



### <span data-ttu-id="0bc6e-298">UE-V-ローミングプリンターのサポート</span><span class="sxs-lookup"><span data-stu-id="0bc6e-298">UE-V-support for Roaming Printers</span></span>

<span data-ttu-id="0bc6e-299">UE-V 2.1 SP1 では、ネットワークプリンターをデバイス間でローミングできるため、ネットワーク上のデバイスにログオンしたときに、ユーザーはネットワークプリンターにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-299">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="0bc6e-300">これには、既定として設定したプリンターのローミングも含まれます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-300">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="0bc6e-301">UE-V でのプリンターローミングには、次のいずれかのシナリオが必要です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-301">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="0bc6e-302">プリントサーバーは、新しいデバイスにローミングしたときに必要なドライバーをダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-302">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="0bc6e-303">ローミングネットワークプリンターのドライバーは、そのネットワークプリンターにアクセスする必要があるすべてのデバイスにプレインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-303">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="0bc6e-304">プリンタードライバーは、Windows Update から入手できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-304">The printer driver can be obtained from Windows Update.</span></span>

**<span data-ttu-id="0bc6e-305">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-305">Note</span></span>**  
<span data-ttu-id="0bc6e-306">UE-V プリンターローミング機能では、両面印刷などのプリンター設定や基本設定はローミング**されません**。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-306">The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>



### <a href="" id="determinesettingssync"></a><span data-ttu-id="0bc6e-307">他のアプリケーションの設定を同期する必要があるかどうかを判断する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-307">Determine whether you need settings synchronized for other applications</span></span>

<span data-ttu-id="0bc6e-308">UE-V の展開で自動的に同期される設定を確認した後で、他のアプリケーションの設定を同期するかどうかを決定します。これにより、企業全体で UE-V を展開する方法が決定されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-308">After you have reviewed the settings that are synchronized automatically in a UE-V deployment, you want to decide whether you will synchronize settings for other applications since this determines how you deploy UE-V throughout your enterprise.</span></span>

<span data-ttu-id="0bc6e-309">管理者として、どのデスクトップアプリケーションを UE-V ソリューションに含めるかを検討している場合は、ユーザーによってカスタマイズできる設定と、その設定をどのように保存するかを検討してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-309">As an administrator, when you consider which desktop applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="0bc6e-310">デスクトップアプリケーションによっては、カスタマイズ可能な設定や、ユーザーによって定期的にカスタマイズされる設定が含まれているわけではありません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-310">Not all desktop applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="0bc6e-311">また、すべてのデスクトップアプリケーションの設定が、複数のコンピューターまたは環境間で安全に同期されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-311">In addition, not all desktop applications settings can safely be synchronized across multiple computers or environments.</span></span>

<span data-ttu-id="0bc6e-312">一般的に、次の条件を満たす設定を同期することができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-312">In general, you can synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="0bc6e-313">ユーザーがアクセスできる場所に保存される設定。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-313">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="0bc6e-314">たとえば、System32 または registry の HKEY \ _CURRENT \ _USER (HKCU) セクションの外側に保存されている設定を同期しないようにします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-314">For example, do not synchronize settings that are stored in System32 or outside the HKEY\_CURRENT\_USER (HKCU) section of the registry.</span></span>

-   <span data-ttu-id="0bc6e-315">特定のコンピューターに固有の設定ではありません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-315">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="0bc6e-316">たとえば、ネットワークまたはハードウェアの構成を除外します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-316">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="0bc6e-317">データが破損していなくてもコンピューター間で同期できる設定。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-317">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="0bc6e-318">たとえば、データベースファイルに保存されている設定を使用しないようにします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-318">For example, do not use settings that are stored in a database file.</span></span>

### <a href="" id="checklistsettingssync"></a><span data-ttu-id="0bc6e-319">カスタムアプリケーションを評価するためのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="0bc6e-319">Checklist for evaluating custom applications</span></span>

<span data-ttu-id="0bc6e-320">他のアプリケーションの設定を同期する必要があると判断した場合は、このチェックリストを使用して、どのアプリケーションを含めるかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-320">If you’ve decided that you need settings synchronized for other applications, you can use this checklist to help figure out which applications you’ll include.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="0bc6e-321">説明</span><span class="sxs-lookup"><span data-stu-id="0bc6e-321">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-322">このアプリケーションには、ユーザーがカスタマイズできる設定が含まれていますか。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-322">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-323">これらの設定が同期されていることは、ユーザーにとって重要ですか?</span><span class="sxs-lookup"><span data-stu-id="0bc6e-323">Is it important for the user that these settings are synchronized?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-324">これらのユーザー設定は、既にアプリケーション管理または設定ポリシーソリューションによって管理されていますか。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-324">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="0bc6e-325">UE-V は、アプリケーションの起動時と Windows の設定で、ログオン、ロック解除、またはリモート接続イベントにアプリケーション設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-325">UE-V applies application settings at application startup and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="0bc6e-326">他の設定で UE-V を使用している場合、同期された設定の間に不整合が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-326">If you use UE-V with other settings sharing solutions, users might experience inconsistency across synchronized settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-327">アプリケーションの設定はコンピューターに固有のものですか?</span><span class="sxs-lookup"><span data-stu-id="0bc6e-327">Are the application settings specific to the computer?</span></span> <span data-ttu-id="0bc6e-328">ハードウェアまたは特定のコンピューターの構成に関連付けられたアプリケーションの環境設定とカスタマイズは、セッション間で一貫して同期されず、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-328">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently synchronize across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-329">アプリケーションは、Program Files ディレクトリか、または <strong> Users [ユーザー名] の強い AppData にあるファイルディレクトリの設定を保存してい </strong> &lt; &gt; </strong> &lt; &gt; </strong> ますか?</span><span class="sxs-lookup"><span data-stu-id="0bc6e-329">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong>[User name]&lt;strong&gt;AppData</strong>&lt;strong&gt;LocalLow</strong> directory?</span></span> <span data-ttu-id="0bc6e-330">通常、これらの場所のいずれかに保存されているアプリケーションデータは、コンピューターに固有のデータであるか、データが大きすぎて同期できないため、ユーザーと同期しないようにしてください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-330">Application data that is stored in either of these locations usually should not synchronize with the user, because this data is specific to the computer or because the data is too large to synchronize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-331">アプリケーションは、同期しない他のアプリケーションデータを含むファイルの設定を保存していますか。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-331">Does the application store any settings in a file that contains other application data that should not synchronize?</span></span> <span data-ttu-id="0bc6e-332">UE-V は、1つの単位としてファイルを同期します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-332">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="0bc6e-333">設定が設定以外のアプリケーションデータを含むファイルに保存されている場合は、この追加データを同期すると、アプリケーションのパフォーマンスが低下する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-333">If settings are stored in files that include application data other than settings, then synchronizing this additional data can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="0bc6e-334">設定を含むファイルのサイズはどのくらいですか?</span><span class="sxs-lookup"><span data-stu-id="0bc6e-334">How large are the files that contain the settings?</span></span> <span data-ttu-id="0bc6e-335">設定の同期のパフォーマンスは、大きなファイルの影響を受ける可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-335">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="0bc6e-336">大きなファイルを含めると、設定の同期のパフォーマンスに影響する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-336">Including large files can affect the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a><span data-ttu-id="0bc6e-337">UE-V 展開を準備する際のその他の考慮事項</span><span class="sxs-lookup"><span data-stu-id="0bc6e-337">Other Considerations when Preparing a UE-V Deployment</span></span>


<span data-ttu-id="0bc6e-338">UE-V の展開を準備している場合も、次の点について考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-338">You should also consider these things when you are preparing to deploy UE-V:</span></span>

-   [<span data-ttu-id="0bc6e-339">資格情報の同期を管理する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-339">Managing credentials synchronization</span></span>](#creds)

-   [<span data-ttu-id="0bc6e-340">Windows アプリの設定の同期</span><span class="sxs-lookup"><span data-stu-id="0bc6e-340">Windows app settings synchronization</span></span>](#appxsettings)

-   [<span data-ttu-id="0bc6e-341">カスタム UE-V 設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="0bc6e-341">Custom UE-V settings location templates</span></span>](#custom)

-   [<span data-ttu-id="0bc6e-342">意図しないユーザー設定の構成</span><span class="sxs-lookup"><span data-stu-id="0bc6e-342">Unintentional user settings configurations</span></span>](#prevent)

-   [<span data-ttu-id="0bc6e-343">パフォーマンスと容量</span><span class="sxs-lookup"><span data-stu-id="0bc6e-343">Performance and capacity</span></span>](#capacity)

-   [<span data-ttu-id="0bc6e-344">高可用性</span><span class="sxs-lookup"><span data-stu-id="0bc6e-344">High availability</span></span>](#high)

-   [<span data-ttu-id="0bc6e-345">コンピューターの時計の同期</span><span class="sxs-lookup"><span data-stu-id="0bc6e-345">Computer clock synchronization</span></span>](#clocksync)

### <a href="" id="creds"></a><span data-ttu-id="0bc6e-346">UE-V 2.1 および UE-V 2.1 SP1 での資格情報の同期の管理</span><span class="sxs-lookup"><span data-stu-id="0bc6e-346">Managing credentials synchronization in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="0bc6e-347">Microsoft Outlook や Lync など、多くのエンタープライズアプリケーションでは、ログイン時にドメインの資格情報をユーザーに確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-347">Many enterprise applications, including Microsoft Outlook and Lync, prompt users for their domain credentials at login.</span></span> <span data-ttu-id="0bc6e-348">ユーザーは、これらのアプリケーションを開くたびに入力する必要がないように、資格情報をディスクに保存するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-348">Users have the option of saving their credentials to disk to prevent having to enter them every time they open these applications.</span></span> <span data-ttu-id="0bc6e-349">ローミング資格情報の同期を有効にすると、ユーザーは自分の資格情報を1台のコンピューターに保存して、環境で使用するすべてのコンピューターに再入力することを防止できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-349">Enabling roaming credentials synchronization lets users save their credentials on one computer and avoid re-entering them on every computer they use in their environment.</span></span> <span data-ttu-id="0bc6e-350">ユーザーは、一部のドメイン資格情報を UE-V 2.1 および 2.1 SP1 と同期させることができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-350">Users can synchronize some domain credentials with UE-V 2.1 and 2.1 SP1.</span></span>

**<span data-ttu-id="0bc6e-351">重要</span><span class="sxs-lookup"><span data-stu-id="0bc6e-351">Important</span></span>**  
<span data-ttu-id="0bc6e-352">資格情報の同期は既定で無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-352">Credentials synchronization is disabled by default.</span></span> <span data-ttu-id="0bc6e-353">この機能を実装するには、展開中に資格情報の同期を明示的に有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-353">You must explicitly enable credentials synchronization during deployment to implement this feature.</span></span>



<span data-ttu-id="0bc6e-354">UE-V 2.1 および 2.1 SP1 は企業の資格情報を同期できますが、ローカルコンピューターでのみ使用する資格情報はローミングしません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-354">UE-V 2.1 and 2.1 SP1 can synchronize enterprise credentials, but do not roam credentials intended only for use on the local computer.</span></span>

<span data-ttu-id="0bc6e-355">資格情報は同期設定であり、ユーザーは UE-V の同期後に初めてコンピューターにログインしたときにプロファイルに適用されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-355">Credentials are synchronous settings, meaning they are applied to your profile the first time you log in to your computer after UE-V synchronizes.</span></span>

<span data-ttu-id="0bc6e-356">資格情報の同期は、独自の設定場所テンプレートによって管理されます。これは既定では無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-356">Credentials synchronization is managed by its own settings location template, which is disabled by default.</span></span> <span data-ttu-id="0bc6e-357">他のテンプレートと同じ方法で、このテンプレートを有効または無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-357">You can enable or disable this template through the same methods used for other templates.</span></span> <span data-ttu-id="0bc6e-358">この機能のテンプレート識別子は RoamingCredentialSettings です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-358">The template identifier for this feature is RoamingCredentialSettings.</span></span>

**<span data-ttu-id="0bc6e-359">重要</span><span class="sxs-lookup"><span data-stu-id="0bc6e-359">Important</span></span>**  
<span data-ttu-id="0bc6e-360">環境で Active Directory 資格情報のローミングを使用している場合は、UE-V 資格情報ローミングテンプレートを有効にしないことをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-360">If you are using Active Directory Credential Roaming in your environment, we recommend that you don’t enable the UE-V credential roaming template.</span></span>



<span data-ttu-id="0bc6e-361">資格情報の同期を有効にするには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-361">Use one of these methods to enable credentials synchronization:</span></span>

-   <span data-ttu-id="0bc6e-362">会社設定センター</span><span class="sxs-lookup"><span data-stu-id="0bc6e-362">Company Settings Center</span></span>

-   <span data-ttu-id="0bc6e-363">PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bc6e-363">PowerShell</span></span>

-   <span data-ttu-id="0bc6e-364">グループ ポリシー</span><span class="sxs-lookup"><span data-stu-id="0bc6e-364">Group Policy</span></span>

**<span data-ttu-id="0bc6e-365">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-365">Note</span></span>**  
<span data-ttu-id="0bc6e-366">資格情報は同期中に暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-366">Credentials are encrypted during synchronization.</span></span>



<span data-ttu-id="0bc6e-367">[会社設定センター](https://technet.microsoft.com/library/dn458903.aspx)**:** [Windows の設定] の [ローミングの資格情報の設定] チェックボックスをオンにして、資格情報の同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-367">[Company Settings Center](https://technet.microsoft.com/library/dn458903.aspx)**:** Check the Roaming Credential Settings check box under Windows Settings to enable credential synchronization.</span></span> <span data-ttu-id="0bc6e-368">チェックボックスをオフにして無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-368">Uncheck the box to disable it.</span></span> <span data-ttu-id="0bc6e-369">このチェックボックスは、アカウントが Microsoft アカウントを使用して設定を同期するように構成されていない場合にのみ、会社の設定センターに表示されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-369">This check box only appears in Company Settings Center if your account is not configured to synchronize settings using a Microsoft Account.</span></span>

<span data-ttu-id="0bc6e-370">[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**:** この PowerShell コマンドレットでは、資格情報の同期を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-370">[PowerShell](https://technet.microsoft.com/library/dn458937.aspx)**:** This PowerShell cmdlet enables credential synchronization:</span></span>

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="0bc6e-371">この PowerShell コマンドレットでは、資格情報の同期を無効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-371">This PowerShell cmdlet disables credential synchronization:</span></span>

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="0bc6e-372">[グループポリシー](https://technet.microsoft.com/library/dn458893.aspx)**:** グループポリシーを使用して資格情報の同期を有効にするには[、最新の MDOP ADMX テンプレートを展開](https://go.microsoft.com/fwlink/p/?LinkId=393944)する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-372">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You must [deploy the latest MDOP ADMX template](https://go.microsoft.com/fwlink/p/?LinkId=393944) to enable credential synchronization through group policy.</span></span> <span data-ttu-id="0bc6e-373">資格情報の同期は、Windows の設定で管理されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-373">Credentials synchronization is managed with the Windows settings.</span></span> <span data-ttu-id="0bc6e-374">グループポリシーを使ってこの機能を管理するには、[Windows の設定の同期] ポリシーを有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-374">To manage this feature with Group Policy, enable the Synchronize Windows settings policy.</span></span>

1.  <span data-ttu-id="0bc6e-375">グループポリシーエディターを開き、[**ユーザーの構成-管理用テンプレート– Windows コンポーネント– Microsoft User Experience Virtualization]** に移動します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-375">Open Group Policy Editor and navigate to **User Configuration – Administrative Templates – Windows Components – Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="0bc6e-376">[ **Windows の設定を同期する**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-376">Double-click on **Synchronize Windows settings**.</span></span>

3.  <span data-ttu-id="0bc6e-377">このポリシーが有効になっている場合は、[**ローミング資格情報**] チェックボックスをオンにして資格情報の同期を有効にするか、オフにして資格情報の同期を無効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-377">If this policy is enabled, you can enable credentials synchronization by checking the **Roaming Credentials** check box, or disable credentials synchronization by unchecking it.</span></span>

4.  <span data-ttu-id="0bc6e-378">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-378">Click **OK**.</span></span>

### <span data-ttu-id="0bc6e-379">UE-V で同期された資格情報の場所</span><span class="sxs-lookup"><span data-stu-id="0bc6e-379">Credential locations synchronized by UE-V</span></span>

<span data-ttu-id="0bc6e-380">アプリケーションによって保存された資格情報ファイルは、次の場所に同期されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-380">Credential files saved by applications into the following locations are synchronized:</span></span>

-   <span data-ttu-id="0bc6e-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span><span class="sxs-lookup"><span data-stu-id="0bc6e-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span></span>\\

-   <span data-ttu-id="0bc6e-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span><span class="sxs-lookup"><span data-stu-id="0bc6e-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span></span>\\

-   <span data-ttu-id="0bc6e-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span><span class="sxs-lookup"><span data-stu-id="0bc6e-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span></span>\\

-   <span data-ttu-id="0bc6e-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span><span class="sxs-lookup"><span data-stu-id="0bc6e-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span></span>\\

<span data-ttu-id="0bc6e-385">他の場所に保存された資格情報は、UE-V で同期されません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-385">Credentials saved to other locations are not synchronized by UE-V.</span></span>

### <a href="" id="appxsettings"></a><span data-ttu-id="0bc6e-386">Windows アプリの設定の同期</span><span class="sxs-lookup"><span data-stu-id="0bc6e-386">Windows app settings synchronization</span></span>

<span data-ttu-id="0bc6e-387">UE-V は、次の3つの方法で Windows アプリ設定の同期を管理します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-387">UE-V manages Windows app settings synchronization in three ways:</span></span>

-   <span data-ttu-id="0bc6e-388">**Windows アプリの同期:** Windows アプリの同期を許可または拒否する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-388">**Sync Windows Apps:** Allow or deny any Windows app synchronization</span></span>

-   <span data-ttu-id="0bc6e-389">**Windows アプリの一覧:** Windows アプリのリストを同期する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-389">**Windows App List:** Synchronize a list of Windows apps</span></span>

-   <span data-ttu-id="0bc6e-390">**一覧にない既定の同期動作:** Windows アプリリストにない Windows アプリの同期動作を決定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-390">**Unlisted Default Sync Behavior:** Determine the synchronization behavior of Windows apps that are not in the Windows app list.</span></span>

<span data-ttu-id="0bc6e-391">詳細については、「 [Windows アプリの一覧](https://technet.microsoft.com/library/dn458925.aspx#win8applist)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-391">For more information, see the [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

### <a href="" id="custom"></a><span data-ttu-id="0bc6e-392">カスタム UE-V 設定場所テンプレート</span><span class="sxs-lookup"><span data-stu-id="0bc6e-392">Custom UE-V settings location templates</span></span>

<span data-ttu-id="0bc6e-393">カスタムアプリケーションの設定を同期するために UE-V を展開する場合は、UE-V Generator を使って、これらのデスクトップアプリケーション用のカスタム設定の場所テンプレートを作成します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-393">If you are deploying UE-V to synchronize settings for custom applications, you will use the UE-V Generator to create custom settings location templates for those desktop applications.</span></span> <span data-ttu-id="0bc6e-394">テスト環境でカスタム設定場所テンプレートを作成してテストしたら、エンタープライズ内のコンピューターに設定場所テンプレートを展開できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-394">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="0bc6e-395">カスタム設定の場所テンプレートは、エンタープライズソフトウェアの配布 (ESD) など、System Center 構成マネージャーなどの既存の展開インフラストラクチャを使用して展開するか、UE-V 設定テンプレートカタログを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-395">Custom settings location templates must be deployed with an existing deployment infrastructure, like an enterprise software distribution (ESD) method such as System Center Configuration Manager, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="0bc6e-396">構成マネージャーまたはグループポリシーと共に展開されるテンプレートは、UE-V WMI または Windows PowerShell を使用して登録する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-396">Templates that are deployed with Configuration Manager or Group Policy must be registered by using UE-V WMI or Windows PowerShell.</span></span>

<span data-ttu-id="0bc6e-397">カスタム設定の場所テンプレートの詳細については、「[カスタムアプリケーション用に ue-v を展開する](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-397">For more information about custom settings location templates, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span> <span data-ttu-id="0bc6e-398">UE-V を構成マネージャーと共に使用する方法について詳しくは、「 [System Center Configuration manager 2012 で ue-v](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)を構成する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-398">For more information about using UE-V with Configuration Manager, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

### <a href="" id="prevent"></a><span data-ttu-id="0bc6e-399">意図しないユーザー設定の構成を防ぐ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-399">Prevent unintentional user settings configuration</span></span>

<span data-ttu-id="0bc6e-400">UE-V は、次のような場合に、設定の保存場所から新しいユーザー設定情報をダウンロードし、ローカルコンピューターに設定を適用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-400">UE-V downloads new user settings information from a settings storage location and applies the settings to the local computer in these instances:</span></span>

-   <span data-ttu-id="0bc6e-401">登録されている UE-V テンプレートを含むアプリケーションが起動されるたび。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-401">Every time an application is started that has a registered UE-V template.</span></span>

-   <span data-ttu-id="0bc6e-402">ユーザーがコンピューターにログオンしたとき。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-402">When a user logs on to a computer.</span></span>

-   <span data-ttu-id="0bc6e-403">ユーザーがコンピューターのロックを解除したとき。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-403">When a user unlocks a computer.</span></span>

-   <span data-ttu-id="0bc6e-404">UE-V がインストールされているリモートデスクトップコンピューターへの接続が行われた場合。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-404">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

-   <span data-ttu-id="0bc6e-405">同期コントローラーアプリケーションのスケジュールされたタスクが実行されたとき。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-405">When the Sync Controller Application scheduled task is run.</span></span>

<span data-ttu-id="0bc6e-406">UE-V がコンピューター A とコンピューター B にインストールされていて、アプリケーションに必要な設定がコンピューター A 上にある場合は、コンピューター A で最初にアプリケーションを開いて閉じる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-406">If UE-V is installed on computer A and computer B, and the settings that you want for the application are on computer A, then computer A should open and close the application first.</span></span> <span data-ttu-id="0bc6e-407">最初にコンピューター B でアプリを開いて閉じた場合は、コンピューター A 上のアプリケーション設定がコンピューター B 上のアプリケーション設定に設定されます。設定は、アプリケーションごとにコンピューター間で同期されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-407">If the application is opened and closed on computer B first, then the application settings on computer A are configured to the application settings on computer B. Settings are synchronized between computers on per-application basis.</span></span> <span data-ttu-id="0bc6e-408">時間の経過と共に、設定を使用してコンピューターを開いたり閉じたりすると、設定の一貫性が保たれます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-408">Over time, settings become consistent between computers as they are opened and closed with preferred settings.</span></span>

<span data-ttu-id="0bc6e-409">このシナリオは、Windows の設定にも適用されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-409">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="0bc6e-410">コンピューター B の Windows 設定がコンピューター A の Windows 設定と同じである必要がある場合は、ユーザーが最初にコンピューターにログオンしてログオフする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-410">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should log on and log off computer A first.</span></span>

<span data-ttu-id="0bc6e-411">ユーザーが必要としているユーザー設定が誤った順序で適用されている場合は、その設定が上書きされたコンピューター上の特定のアプリケーションまたは Windows 構成に対して復元操作を実行することで、ユーザー設定を回復できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-411">If the user settings that the user wants are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="0bc6e-412">詳細については、「 [ue-v で管理用のバックアップと復元を管理](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-412">For more information, see [Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md).</span></span>

### <a href="" id="capacity"></a><span data-ttu-id="0bc6e-413">パフォーマンスとキャパシティの計画</span><span class="sxs-lookup"><span data-stu-id="0bc6e-413">Performance and capacity planning</span></span>

<span data-ttu-id="0bc6e-414">標準のディスク容量とネットワーク正常性監視を使用して、UE-V の要件を指定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-414">Specify your requirements for UE-V with standard disk capacity and network health monitoring.</span></span>

<span data-ttu-id="0bc6e-415">UE-V は、設定パッケージの保存にサーバーメッセージブロック (SMB) 共有を使用します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-415">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="0bc6e-416">設定パッケージのサイズは、各アプリケーションの設定情報によって異なります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-416">The size of settings packages varies depending on the settings information for each application.</span></span> <span data-ttu-id="0bc6e-417">ほとんどの設定パッケージは小さいですが、デスクトップイメージなどの大きなファイルを同期すると、パフォーマンスが低下する可能性があります (特に低速ネットワーク)。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-417">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span>

<span data-ttu-id="0bc6e-418">ネットワーク待ち時間の問題を減らすために、ユーザーのコンピューターが存在する同じローカルネットワーク上に設定の保存場所を作成します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-418">To reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="0bc6e-419">設定の保存場所については、ユーザー1人につき 20 MB のディスク領域をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-419">We recommend 20 MB of disk space per user for the settings storage location.</span></span>

<span data-ttu-id="0bc6e-420">既定では、設定パッケージのサイズが大きいため、UE-V の同期は2秒後にタイムアウトします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-420">By default, UE-V synchronization times out after 2 seconds to prevent excessive lag due to a large settings package.</span></span> <span data-ttu-id="0bc6e-421">同期メソッド = Syncmethod の設定は、[グループポリシーオブジェクト](https://technet.microsoft.com/library/dn458893.aspx)を使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-421">You can configure the SyncMethod=SyncProvider setting by using [Group Policy Objects](https://technet.microsoft.com/library/dn458893.aspx).</span></span>

### <a href="" id="high"></a><span data-ttu-id="0bc6e-422">UE-V の高可用性</span><span class="sxs-lookup"><span data-stu-id="0bc6e-422">High Availability for UE-V</span></span>

<span data-ttu-id="0bc6e-423">UE-V の [設定] のストレージの場所と設定テンプレートカタログは、書き込み可能な共有にユーザーデータを格納することをサポートします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-423">The UE-V settings storage location and settings template catalog support storing user data on any writable share.</span></span> <span data-ttu-id="0bc6e-424">高可用性を確保するには、次の条件を満たしてください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-424">To ensure high availability, follow these criteria:</span></span>

-   <span data-ttu-id="0bc6e-425">記憶域ボリュームに NTFS ファイルシステムを設定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-425">Format the storage volume with an NTFS file system.</span></span>

-   <span data-ttu-id="0bc6e-426">共有では分散ファイルシステム (DFS) を使用できますが、制限があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-426">The share can use Distributed File System (DFS) but there are restrictions.</span></span>
<span data-ttu-id="0bc6e-427">特に、分散ファイルシステムのレプリケーション (DFS-R) では、分散ファイルシステムの名前空間 (DFS-R) を使用するか、またはそれを使わずに単一のターゲット構成がサポートされます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-427">Specifically, Distributed File System Replication (DFS-R) single target configuration with or without a Distributed File System Namespace (DFS-N) is supported.</span></span>
<span data-ttu-id="0bc6e-428">同様に、DFS-R でサポートされているターゲット構成は1つだけです。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-428">Likewise, only single target configuration is supported with DFS-N.</span></span>
<span data-ttu-id="0bc6e-429">詳細については、複製された[ユーザープロファイルデータに関する microsoft のサポート声明](https://go.microsoft.com/fwlink/p/?LinkId=313991)と、 [dfs および dfs 展開シナリオの microsoft サポートポリシーに関する情報](https://support.microsoft.com/kb/2533009)も参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-429">For detailed information, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://go.microsoft.com/fwlink/p/?LinkId=313991) and also [Information about Microsoft support policy for a DFS-R and DFS-N deployment scenario](https://support.microsoft.com/kb/2533009).</span></span>

    <span data-ttu-id="0bc6e-430">また、SYSVOL はレプリケーション用に DFS を使用するため、UE-V データファイルレプリケーションでは SYSVOL を使用できません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-430">In addition, because SYSVOL uses DFS-R for replication, SYSVOL cannot be used for UE-V data file replication.</span></span>

-   <span data-ttu-id="0bc6e-431">[Ue-v の [設定の保存場所](https://technet.microsoft.com/library/dn458891.aspx#ssl)] で指定されている共有アクセス許可と NTFS アクセス制御リスト (acl) を構成します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-431">Configure the share permissions and NTFS access control lists (ACLs) as specified in [Deploying the Settings Storage Location for UE-V 2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl).</span></span>

-   <span data-ttu-id="0bc6e-432">UE-V Agent と共にファイルサーバークラスタリングを使用して、通信エラーが発生したときにユーザー状態データのコピーへのアクセスを提供します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-432">Use file server clustering along with the UE-V Agent to provide access to copies of user state data in the event of communications failures.</span></span>

-   <span data-ttu-id="0bc6e-433">クラスター化された共有、DFS 共有、またはその両方に設定の記憶域パスデータ (ユーザーデータ) と設定テンプレートカタログテンプレートを保存できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-433">You can store the settings storage path data (user data) and settings template catalog templates on clustered shares, on DFS-N shares, or on both.</span></span>

### <a href="" id="clocksync"></a><span data-ttu-id="0bc6e-434">コンピューターの時計を同期させる (UE-V 設定の同期)</span><span class="sxs-lookup"><span data-stu-id="0bc6e-434">Synchronize computer clocks for UE-V settings synchronization</span></span>

<span data-ttu-id="0bc6e-435">UE-V エージェントを実行するコンピューターは、一貫した設定エクスペリエンスを維持するために、タイムサーバーを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-435">Computers that run the UE-V Agent must use a time server to maintain a consistent settings experience.</span></span> <span data-ttu-id="0bc6e-436">UE-V はタイムスタンプを使用して、設定の保存場所から設定を同期する必要があるかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-436">UE-V uses time stamps to determine if settings must be synchronized from the settings storage location.</span></span> <span data-ttu-id="0bc6e-437">コンピューターの時計が間違っている場合は、古い設定で新しい設定が上書きされる可能性があります。また、新しい設定が、設定の保存場所に保存されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-437">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span>

## <a href="" id="prereqs"></a><span data-ttu-id="0bc6e-438">UE-V の前提条件とサポートされる構成を確認する</span><span class="sxs-lookup"><span data-stu-id="0bc6e-438">Confirm Prerequisites and Supported Configurations for UE-V</span></span>


<span data-ttu-id="0bc6e-439">続行する前に、お使いの環境で UE-V を実行するための要件が含まれていることを確認してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-439">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

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
<th align="left"><strong><span data-ttu-id="0bc6e-440">オペレーティング システム</span><span class="sxs-lookup"><span data-stu-id="0bc6e-440">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-441">エディション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-441">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-442">Service pack</span><span class="sxs-lookup"><span data-stu-id="0bc6e-442">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-443">システムアーキテクチャ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-443">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-444">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0bc6e-444">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="0bc6e-445">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="0bc6e-445">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-446">Windows 7</span><span class="sxs-lookup"><span data-stu-id="0bc6e-446">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-447">Ultimate、Enterprise、または Professional エディション</span><span class="sxs-lookup"><span data-stu-id="0bc6e-447">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-448">SP1</span><span class="sxs-lookup"><span data-stu-id="0bc6e-448">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-449">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-449">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-450">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-450">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-451">.NET Framework 4.5 以上 (UE-V 2.1 の場合)</span><span class="sxs-lookup"><span data-stu-id="0bc6e-451">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="0bc6e-452">UE-V 2.0 向けの .NET Framework 4 以上。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-452">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-453">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="0bc6e-453">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-454">標準、エンタープライズ、データセンター、または Web サーバー</span><span class="sxs-lookup"><span data-stu-id="0bc6e-454">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-455">SP1</span><span class="sxs-lookup"><span data-stu-id="0bc6e-455">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-456">64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-456">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-457">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-457">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-458">.NET Framework 4.5 以上 (UE-V 2.1 の場合)</span><span class="sxs-lookup"><span data-stu-id="0bc6e-458">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="0bc6e-459">UE-V 2.0 向けの .NET Framework 4 以上。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-459">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-460">Windows 8 および Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="0bc6e-460">Windows 8 and Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-461">Enterprise または Pro</span><span class="sxs-lookup"><span data-stu-id="0bc6e-461">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-462">なし</span><span class="sxs-lookup"><span data-stu-id="0bc6e-462">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-463">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-463">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-464">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-464">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-465">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-465">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-466">Windows 10、1607以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="0bc6e-466">Windows 10, pre-1607 version</span></span></p>
<div class="alert">
<strong><span data-ttu-id="0bc6e-467">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-467">Note</span></span></strong><br/><p><span data-ttu-id="0bc6e-468">UE-V 2.1 SP1 のみがサポートされている Windows 10、1607以前のバージョン</span><span class="sxs-lookup"><span data-stu-id="0bc6e-468">Only UE-V 2.1 SP1 supports Windows 10, pre-1607 version</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="0bc6e-469">Enterprise または Pro</span><span class="sxs-lookup"><span data-stu-id="0bc6e-469">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-470">なし</span><span class="sxs-lookup"><span data-stu-id="0bc6e-470">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-471">32 ビットまたは 64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-471">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-472">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-472">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-473">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="0bc6e-473">.NET Framework 4.6</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0bc6e-474">Windows Server 2012 および Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="0bc6e-474">Windows Server 2012 and Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-475">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="0bc6e-475">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-476">なし</span><span class="sxs-lookup"><span data-stu-id="0bc6e-476">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-477">64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-477">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-478">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-478">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-479">.NET Framework 4.5 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-479">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0bc6e-480">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="0bc6e-480">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-481">標準またはデータセンター</span><span class="sxs-lookup"><span data-stu-id="0bc6e-481">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-482">なし</span><span class="sxs-lookup"><span data-stu-id="0bc6e-482">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-483">64 ビット</span><span class="sxs-lookup"><span data-stu-id="0bc6e-483">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-484">Windows PowerShell 3.0 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-484">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="0bc6e-485">.NET Framework 4.6 以降</span><span class="sxs-lookup"><span data-stu-id="0bc6e-485">.NET Framework 4.6 or higher</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="0bc6e-486">また。。。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-486">Also…</span></span>

-   <span data-ttu-id="0bc6e-487">**MDOP ライセンス:** この技術は、Microsoft デスクトップ最適化パック (MDOP) に含まれています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-487">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="0bc6e-488">企業のお客様は、Microsoft ソフトウェアアシュアランスで MDOP を入手できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-488">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="0bc6e-489">Microsoft ソフトウェアアシュアランスの詳細と MDOP の入手方法については、「MDOP の入手方法」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-489">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="0bc6e-490">インストールする任意のコンピューターの**管理者資格情報**</span><span class="sxs-lookup"><span data-stu-id="0bc6e-490">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

**<span data-ttu-id="0bc6e-491">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-491">Note</span></span>**  

-   <span data-ttu-id="0bc6e-492">WIndows 10 バージョン1607以降では、UE-V は[windows 10 For Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)に含まれており、Microsoft デスクトップ最適化パックの一部ではなくなっています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-492">Starting with WIndows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack.</span></span>

-   <span data-ttu-id="0bc6e-493">UE-V Agent の UE-V Windows PowerShell 機能を有効にするには、.NET Framework 4 以上と Windows PowerShell 3.0 以降が必要です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-493">The UE-V Windows PowerShell feature of the UE-V Agent requires .NET Framework 4 or higher and Windows PowerShell 3.0 or higher to be enabled.</span></span> <span data-ttu-id="0bc6e-494">[ここ](https://go.microsoft.com/fwlink/?LinkId=309609)に Windows PowerShell 3.0 をダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-494">Download Windows PowerShell 3.0 [here](https://go.microsoft.com/fwlink/?LinkId=309609).</span></span>

-   <span data-ttu-id="0bc6e-495">Windows 7 または Windows Server 2008 R2 オペレーティングシステムを実行しているコンピューターに、.NET Framework 4 または .NET Framework 4.5 をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-495">Install .NET Framework 4 or .NET Framework 4.5 on computers that run the Windows 7 or the Windows Server 2008 R2 operating system.</span></span> <span data-ttu-id="0bc6e-496">Windows 8、Windows 8.1、Windows Server 2012 オペレーティングシステムには、.NET Framework 4.5 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-496">The Windows 8, Windows 8.1, and Windows Server 2012 operating systems come with .NET Framework 4.5 installed.</span></span> <span data-ttu-id="0bc6e-497">Windows 10 オペレーティングシステムには、.NET Framework 4.6 がインストールされています。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-497">The Windows 10 operating system comes with .NET Framework 4.6 installed.</span></span>
-   <span data-ttu-id="0bc6e-498">必須プロファイルの "ローミングキャッシュの削除" ポリシーは、UE-V でサポートされていないため、使用できません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-498">The “Delete Roaming Cache” policy for Mandatory profiles is not supported with UE-V and should not be used.</span></span>



<span data-ttu-id="0bc6e-499">UE-V に固有の特殊なランダムアクセスメモリ (RAM) 要件はありません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-499">There are no special random access memory (RAM) requirements specific to UE-V.</span></span>

### <span data-ttu-id="0bc6e-500">同期プロバイダーによる設定の同期</span><span class="sxs-lookup"><span data-stu-id="0bc6e-500">Synchronization of Settings through the Sync Provider</span></span>

<span data-ttu-id="0bc6e-501">同期プロバイダーは、ユーザーの既定の設定です。この設定では、次のような場合に、ローカルキャッシュを設定の保存場所と同期します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-501">Sync Provider is the default setting for users, which synchronizes a local cache with the settings storage location in these instances:</span></span>

-   <span data-ttu-id="0bc6e-502">ログオン/ログオフ</span><span class="sxs-lookup"><span data-stu-id="0bc6e-502">Logon/logoff</span></span>

-   <span data-ttu-id="0bc6e-503">ロック/ロック解除</span><span class="sxs-lookup"><span data-stu-id="0bc6e-503">Lock/unlock</span></span>

-   <span data-ttu-id="0bc6e-504">リモートデスクトップの接続/切断</span><span class="sxs-lookup"><span data-stu-id="0bc6e-504">Remote desktop connect/disconnect</span></span>

-   <span data-ttu-id="0bc6e-505">アプリケーションを開く/閉じる</span><span class="sxs-lookup"><span data-stu-id="0bc6e-505">Application open/close</span></span>

<span data-ttu-id="0bc6e-506">スケジュールされたタスクは、この設定の同期を30分ごとに、または特定のアプリケーションの特定のトリガーイベントを使用して管理します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-506">A scheduled task manages this synchronization of settings every 30 minutes or through certain trigger events for certain applications.</span></span> <span data-ttu-id="0bc6e-507">詳細については、「 [ue-v のスケジュールされたタスクの頻度を変更する](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-507">For more information, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="0bc6e-508">UE-V Agent は、常に企業ネットワーク (リモートコンピューターおよびノート pc) に接続されていないコンピューター、および常にネットワークに接続されているコンピューター (Windows Server とホスト仮想デスクトップインターフェイス (VDI) セッションを実行しているコンピューター) のユーザー設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-508">The UE-V Agent synchronizes user settings for computers that are not always connected to the enterprise network (remote computers and laptops) and computers that are always connected to the network (computers that run Windows Server and host virtual desktop interface (VDI) sessions).</span></span>

<span data-ttu-id="0bc6e-509">**常に利用可能な接続を備えたコンピューターの同期:** 常にネットワークに接続されているコンピューターで UE-V を使用する場合は、 *Syncmethod = None*パラメーターを使用して設定を同期するように ue-v agent を構成する必要があります。これにより、設定ストレージサーバーは標準ネットワーク共有として扱われます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-509">**Synchronization for computers with always-available connections:** When you use UE-V on computers that are always connected to the network, you must configure the UE-V Agent to synchronize settings by using the *SyncMethod=None* parameter, which treats the settings storage server as a standard network share.</span></span> <span data-ttu-id="0bc6e-510">この構成では、アプリケーション設定のインポートが遅延しているかどうかを通知するように UE-V Agent を構成できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-510">In this configuration, the UE-V Agent can be configured to notify if the import of the application settings is delayed.</span></span>

<span data-ttu-id="0bc6e-511">次のいずれかの方法を使用して、この構成を有効にします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-511">Enable this configuration through one of these methods:</span></span>

-   <span data-ttu-id="0bc6e-512">UE-V のインストール中に、コマンドプロンプトで、またはバッチファイルで AgentSetup.exe パラメーター *Syncmethod = None*を設定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-512">During UE-V installation, at the command prompt or in a batch file, set the AgentSetup.exe parameter *SyncMethod = None*.</span></span> <span data-ttu-id="0bc6e-513">詳細につい[ては、Ue-v agent を使用して展開して](https://technet.microsoft.com/library/dn458891.aspx#agent)ください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-513">[Deploying the UE-V 2.x Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more information.</span></span>

-   <span data-ttu-id="0bc6e-514">UE-V のインストール後、System Center 2012 構成マネージャーまたは MDOP ADMX テンプレートの設定管理機能を使用して、 *Syncmethod = None*構成をプッシュします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-514">After the UE-V installation, use the Settings Management feature in System Center 2012 Configuration Manager or the MDOP ADMX templates to push the *SyncMethod = None* configuration.</span></span>

-   <span data-ttu-id="0bc6e-515">Windows PowerShell または Windows Management Instrumentation (WMI) を使って、 *Syncmethod = None*構成を設定します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-515">Use Windows PowerShell or Windows Management Instrumentation (WMI) to set the *SyncMethod = None* configuration.</span></span>

    **<span data-ttu-id="0bc6e-516">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-516">Note</span></span>**  
    <span data-ttu-id="0bc6e-517">これらの最後の2つの方法は、プールされた仮想デスクトップインフラストラクチャ (VDI) 環境では動作しません。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-517">These last two methods do not work for pooled virtual desktop infrastructure (VDI) environments.</span></span>



<span data-ttu-id="0bc6e-518">設定が同期を開始するには、コンピューターを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-518">You must restart the computer before the settings start to synchronize.</span></span>

**<span data-ttu-id="0bc6e-519">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-519">Note</span></span>**  
<span data-ttu-id="0bc6e-520">*Syncmethod = None*を設定すると、設定の変更はサーバーに直接保存されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-520">If you set *SyncMethod = None*, any settings changes are saved directly to the server.</span></span> <span data-ttu-id="0bc6e-521">設定の記憶域パスへのネットワーク接続が見つからない場合、設定の変更はデバイスにキャッシュされ、次に同期プロバイダーを実行するときに同期されます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-521">If the network connection to the settings storage path is not found, then the settings changes are cached on the device and are synchronized the next time that the sync provider runs.</span></span> <span data-ttu-id="0bc6e-522">設定の保存パスが見つからず、ログオフ時にプールされた VDI 環境からユーザープロファイルが削除された場合、設定の変更は失われ、ユーザーはコンピューターが設定の記憶域パスに再接続されたときに変更を再適用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-522">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, settings changes are lost and the user must reapply the change when the computer is reconnected to the settings storage path.</span></span>



<span data-ttu-id="0bc6e-523">\**外部同期エンジンの同期:\*\*\*Syncmethod = External* parameter は、ユーザーコンピューターのローカルフォルダーに ue-v 設定が書き込まれるかどうかを指定します。次に、任意の外部同期エンジン (OneDrive for Business、ワークフォルダー、Sharepoint、Dropbox など) を使って、これらの設定をユーザーがアクセスするさまざまなコンピューターに適用することができます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-523">**Synchronization for external sync engines:** The *SyncMethod=External* parameter specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

<span data-ttu-id="0bc6e-524">**共有 VDI セッションのサポート:** UE-V 2.1 および 2.1 SP1 は、エンドユーザー間で共有される VDI セッションのサポートを提供します。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-524">**Support for shared VDI sessions:** UE-V 2.1 and 2.1 SP1 provide support for VDI sessions that are shared among end users.</span></span> <span data-ttu-id="0bc6e-525">特殊な VDI テンプレートを登録して構成することができます。これにより、UE-V は永続的でない VDI セッションに対してすべての機能をそのまま維持できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-525">You can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

**<span data-ttu-id="0bc6e-526">注</span><span class="sxs-lookup"><span data-stu-id="0bc6e-526">Note</span></span>**  
<span data-ttu-id="0bc6e-527">非永続的な VDI セッションで VDI モードを有効にしていない場合、一部の機能が機能しなくなります。たとえば、[バックアップ/復元や前回正常](https://technet.microsoft.com/library/dn878331.aspx)に動作していた既知の良好 (lkg) などです。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-527">If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as [back-up/restore and last known good (LKG)](https://technet.microsoft.com/library/dn878331.aspx).</span></span>



<span data-ttu-id="0bc6e-528">VDI テンプレートは、UE-V 2.1 および 2.1 SP1 で提供され Virtualization\\Templates\\VdiState.xml ます。通常はインストール後に使用できます。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-528">The VDI template is provided with UE-V 2.1 and 2.1 SP1 and is typically available here after installation: C:\\Program Files\\Microsoft User Experience Virtualization\\Templates\\VdiState.xml</span></span>

### <span data-ttu-id="0bc6e-529">UE-V Generator のサポートに関する前提条件</span><span class="sxs-lookup"><span data-stu-id="0bc6e-529">Prerequisites for UE-V Generator support</span></span>

<span data-ttu-id="0bc6e-530">カスタム設定の場所テンプレートを作成するために使用されるコンピューターに、UE-V Generator をインストールします。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-530">Install the UE-V Generator on the computer that is used to create custom settings location templates.</span></span> <span data-ttu-id="0bc6e-531">このコンピューターでは、設定が同期されているアプリケーションを実行できる必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-531">This computer should be able to run the applications whose settings are synchronized.</span></span> <span data-ttu-id="0bc6e-532">UE-V Generator ソフトウェアを実行しているコンピューターの管理者グループのメンバーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-532">You must be a member of the Administrators group on the computer that runs the UE-V Generator software.</span></span>

<span data-ttu-id="0bc6e-533">UE-V Generator は、NTFS ファイルシステムを使用するコンピューターにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-533">The UE-V Generator must be installed on a computer that uses an NTFS file system.</span></span> <span data-ttu-id="0bc6e-534">UE-V Generator ソフトウェアには、.NET Framework 4 が必要です。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-534">The UE-V Generator software requires .NET Framework 4.</span></span> <span data-ttu-id="0bc6e-535">詳細については、「[カスタムアプリケーションの ue-v を展開する](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0bc6e-535">For more information, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <span data-ttu-id="0bc6e-536">この製品のその他のリソース</span><span class="sxs-lookup"><span data-stu-id="0bc6e-536">Other resources for this product</span></span>


-   [<span data-ttu-id="0bc6e-537">Microsoft User Experience Virtualization (UE-V) 2. x</span><span class="sxs-lookup"><span data-stu-id="0bc6e-537">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="0bc6e-538">UE-V 2.x の概要</span><span class="sxs-lookup"><span data-stu-id="0bc6e-538">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="0bc6e-539">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="0bc6e-539">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="0bc6e-540">UE-V 2. x のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="0bc6e-540">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="0bc6e-541">UE-V 2.x のテクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="0bc6e-541">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)














