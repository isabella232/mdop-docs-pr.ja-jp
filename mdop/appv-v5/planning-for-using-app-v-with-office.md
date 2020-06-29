---
title: APP-V で Office を使用するための計画
description: APP-V で Office を使用するための計画
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813426"
---
# <span data-ttu-id="11275-103">APP-V で Office を使用するための計画</span><span class="sxs-lookup"><span data-stu-id="11275-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="11275-104">以下の情報を使用して、App-v を使って Office を展開する方法を計画します。</span><span class="sxs-lookup"><span data-stu-id="11275-104">Use the following information to plan how to deploy Office by using App-V.</span></span> <span data-ttu-id="11275-105">この記事の内容は次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="11275-105">This article includes:</span></span>

-   [<span data-ttu-id="11275-106">言語パック用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="11275-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="11275-107">サポートされている Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="11275-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="11275-108">共存バージョンの Office での App-v の使用を計画する</span><span class="sxs-lookup"><span data-stu-id="11275-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="11275-109">Office を展開するときに Office を展開するときに Windows と統合する方法</span><span class="sxs-lookup"><span data-stu-id="11275-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="11275-110">言語パック用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="11275-110">App-V support for Language Packs</span></span>


<span data-ttu-id="11275-111">アプリ-V 5.0 Sequencer を使って、言語パック、言語インターフェイスパック、校正ツール、ポップヒント言語用のプラグインパッケージを作成できます。</span><span class="sxs-lookup"><span data-stu-id="11275-111">You can use the App-V 5.0 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="11275-112">その後、Office 展開ツールキットを使って作成した Office 2013 パッケージと共に、接続グループにプラグインパッケージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="11275-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="11275-113">Office アプリケーションとプラグイン言語パックは、接続グループで一緒にグループ化されている他のパッケージと同じように、同じ接続グループでシームレスにやり取りされます。</span><span class="sxs-lookup"><span data-stu-id="11275-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

<span data-ttu-id="11275-114">**注** Microsoft Visio および Microsoft Project は、タイ語言語パックのサポートを提供していません。</span><span class="sxs-lookup"><span data-stu-id="11275-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="11275-115">サポートされている Microsoft Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="11275-115">Supported versions of Microsoft Office</span></span>


<span data-ttu-id="11275-116">次の表に、App-v でサポートされている Microsoft Office のバージョン、Office パッケージの作成方法、サポートされているライセンス、サポートされている展開の一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="11275-116">The following table lists the versions of Microsoft Office that App-V supports, methods of Office package creation, supported licensing, and supported deployments.</span></span>

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
<th align="left"><span data-ttu-id="11275-117">サポートされている Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="11275-117">Supported Office Version</span></span></th>
<th align="left"><span data-ttu-id="11275-118">サポートされている App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="11275-118">Supported App-V Versions</span></span></th>
<th align="left"><span data-ttu-id="11275-119">パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="11275-119">Package Creation</span></span></th>
<th align="left"><span data-ttu-id="11275-120">サポートされているライセンス</span><span class="sxs-lookup"><span data-stu-id="11275-120">Supported Licensing</span></span></th>
<th align="left"><span data-ttu-id="11275-121">サポートされている展開</span><span class="sxs-lookup"><span data-stu-id="11275-121">Supported Deployments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-122">エンタープライズ向けの Microsoft 365 アプリ</span><span class="sxs-lookup"><span data-stu-id="11275-122">Microsoft 365 Apps for enterprise</span></span></p>
<p><span data-ttu-id="11275-123">以下もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11275-123">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="11275-124">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="11275-124">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="11275-125">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="11275-125">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="11275-126">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="11275-126">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="11275-127">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="11275-127">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="11275-128">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="11275-128">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="11275-129">Office 展開ツール</span><span class="sxs-lookup"><span data-stu-id="11275-129">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-130">サブスクリプション</span><span class="sxs-lookup"><span data-stu-id="11275-130">Subscription</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="11275-131">Desktop</span><span class="sxs-lookup"><span data-stu-id="11275-131">Desktop</span></span></p></li>
<li><p><span data-ttu-id="11275-132">パーソナル VDI</span><span class="sxs-lookup"><span data-stu-id="11275-132">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="11275-133">プールされた VDI</span><span class="sxs-lookup"><span data-stu-id="11275-133">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="11275-134">RDS</span><span class="sxs-lookup"><span data-stu-id="11275-134">RDS</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-135">Office Professional Plus 2013</span><span class="sxs-lookup"><span data-stu-id="11275-135">Office Professional Plus 2013</span></span></p>
<p><span data-ttu-id="11275-136">以下もサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11275-136">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="11275-137">Visio Professional 2013</span><span class="sxs-lookup"><span data-stu-id="11275-137">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="11275-138">Project Professional 2013</span><span class="sxs-lookup"><span data-stu-id="11275-138">Project Professional 2013</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="11275-139">App-v 5.0</span><span class="sxs-lookup"><span data-stu-id="11275-139">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="11275-140">App-v 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="11275-140">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="11275-141">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="11275-141">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="11275-142">Office 展開ツール</span><span class="sxs-lookup"><span data-stu-id="11275-142">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-143">ボリューム ライセンス</span><span class="sxs-lookup"><span data-stu-id="11275-143">Volume Licensing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="11275-144">Desktop</span><span class="sxs-lookup"><span data-stu-id="11275-144">Desktop</span></span></p></li>
<li><p><span data-ttu-id="11275-145">パーソナル VDI</span><span class="sxs-lookup"><span data-stu-id="11275-145">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="11275-146">プールされた VDI</span><span class="sxs-lookup"><span data-stu-id="11275-146">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="11275-147">RDS</span><span class="sxs-lookup"><span data-stu-id="11275-147">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="11275-148">共存バージョンの Office での App-v の使用を計画する</span><span class="sxs-lookup"><span data-stu-id="11275-148">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="11275-149">"Microsoft Office の共存" を使用すると、同じコンピューターに複数のバージョンの Microsoft Office を同時にインストールできます。</span><span class="sxs-lookup"><span data-stu-id="11275-149">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="11275-150">Windows Installer ベース (MSi) バージョンの Office、クイック実行、および App-v 5.0 SP2 を使用して、office のすべての主要バージョンとインストール方法を組み合わせて、office を共存させることができます。</span><span class="sxs-lookup"><span data-stu-id="11275-150">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.0 SP2.</span></span> <span data-ttu-id="11275-151">ただし、Microsoft では Office の共存を使用することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="11275-151">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="11275-152">Microsoft の推奨されるベストプラクティスは、互換性の問題を回避するために、Office を完全に共存させないようにすることです。</span><span class="sxs-lookup"><span data-stu-id="11275-152">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="11275-153">ただし、新しいバージョンの Office に移行する場合は、すぐに解決できない問題が発生する可能性があるため、一時的に共存を実装して、最新の製品バージョンへの移行を容易にすることができます。</span><span class="sxs-lookup"><span data-stu-id="11275-153">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="11275-154">長期ベースで Office の共存を使用することはお勧めしません。また、組織では、すぐに完全に移行するための計画が必要です。</span><span class="sxs-lookup"><span data-stu-id="11275-154">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="11275-155">Office の共存を実装する前に</span><span class="sxs-lookup"><span data-stu-id="11275-155">Before you implement Office coexistence</span></span>

<span data-ttu-id="11275-156">Office の共存を実装する前に、次の Office ドキュメントを確認してください。</span><span class="sxs-lookup"><span data-stu-id="11275-156">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="11275-157">共存を実装する予定の最新バージョンの Office に対応する記事を選択します。</span><span class="sxs-lookup"><span data-stu-id="11275-157">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="11275-158">Office のバージョン</span><span class="sxs-lookup"><span data-stu-id="11275-158">Office version</span></span></th>
<th align="left"><span data-ttu-id="11275-159">ガイダンスへのリンク</span><span class="sxs-lookup"><span data-stu-id="11275-159">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-160">Office 2013</span><span class="sxs-lookup"><span data-stu-id="11275-160">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="11275-161">他のバージョンの Office を実行しているコンピューターで Office 2013 スイートとプログラム (MSI 展開) を使用する方法についての情報</span><span class="sxs-lookup"><span data-stu-id="11275-161">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-162">Office 2010</span><span class="sxs-lookup"><span data-stu-id="11275-162">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="11275-163">他のバージョンの Office を実行しているコンピューターで Office 2010 スイートとプログラムを使用する方法についての情報</span><span class="sxs-lookup"><span data-stu-id="11275-163">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="11275-164">Office ドキュメントでは、Windows Installer ベース (MSi) およびクイック実行インストールの Office の共存に関する広範なガイダンスを提供しています。</span><span class="sxs-lookup"><span data-stu-id="11275-164">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="11275-165">このアプリの共存に関するこのトピックでは、App-v の展開に固有の情報を使用して Office ガイダンスを補足します。</span><span class="sxs-lookup"><span data-stu-id="11275-165">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="11275-166">サポートされている Office の共存シナリオ</span><span class="sxs-lookup"><span data-stu-id="11275-166">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="11275-167">次の表は、サポートされている共存シナリオをまとめたものです。</span><span class="sxs-lookup"><span data-stu-id="11275-167">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="11275-168">これらは、最初に使用しているバージョンと展開方法と、移行するバージョンおよび展開方法に従って構成されます。</span><span class="sxs-lookup"><span data-stu-id="11275-168">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="11275-169">実働の対象ユーザーに展開する前に、すべての共存ソリューションを完全にテストしてください。</span><span class="sxs-lookup"><span data-stu-id="11275-169">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

<span data-ttu-id="11275-170">**注** Microsoft は、リモートデスクトップセッションホストの役割サービスが有効になっている Windows Server 環境での複数バージョンの Office の使用をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="11275-170">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="11275-171">Office の共存シナリオを実行するには、この役割サービスを無効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11275-171">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="11275-172">Windows 統合 & Office の共存</span><span class="sxs-lookup"><span data-stu-id="11275-172">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="11275-173">Windows Installer ベースおよびクイック実行の Office インストール方法は、基になる Windows オペレーティングシステムの特定のポイントと統合されます。</span><span class="sxs-lookup"><span data-stu-id="11275-173">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="11275-174">共存を使用すると、2つの Office バージョン間での一般的なオペレーティングシステムの統合が競合し、互換性とユーザーエクスペリエンスの問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11275-174">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="11275-175">App-v では、特定のバージョンの Office をシーケンスして、統合を除外し、オペレーティングシステムから "分離" することができます。</span><span class="sxs-lookup"><span data-stu-id="11275-175">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="11275-176">このバージョンの Office を順序指定できるモード (App-v)</span><span class="sxs-lookup"><span data-stu-id="11275-176">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-177">Office 2007</span><span class="sxs-lookup"><span data-stu-id="11275-177">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-178">常に統合されていない。</span><span class="sxs-lookup"><span data-stu-id="11275-178">Always non-integrated.</span></span> <span data-ttu-id="11275-179">App-v は、仮想化されたバージョンの Office 2007 とのオペレーティングシステム統合を提供しません。</span><span class="sxs-lookup"><span data-stu-id="11275-179">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-180">Office 2010</span><span class="sxs-lookup"><span data-stu-id="11275-180">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-181">統合モードと非統合モード。</span><span class="sxs-lookup"><span data-stu-id="11275-181">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-182">Office 2013</span><span class="sxs-lookup"><span data-stu-id="11275-182">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-183">常に統合されます。</span><span class="sxs-lookup"><span data-stu-id="11275-183">Always integrated.</span></span> <span data-ttu-id="11275-184">Windows オペレーティングシステムの統合を無効にすることはできません。</span><span class="sxs-lookup"><span data-stu-id="11275-184">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="11275-185">Microsoft では、統合された Office インスタンスを1つだけ使用して Office を共存させることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="11275-185">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="11275-186">たとえば、Office 2010 と Office 2013 を展開するために App-v を使っている場合は、非統合モードで Office 2010 をシーケンスする必要があります。</span><span class="sxs-lookup"><span data-stu-id="11275-186">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="11275-187">統合されていない (分離) モードでの Office の優先順位については、「microsoft [Application Virtualization 5.0 で Microsoft office 2010 の順序を付ける方法](https://support.microsoft.com/kb/2830069)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="11275-187">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="11275-188">Office の共存シナリオの既知の制限事項</span><span class="sxs-lookup"><span data-stu-id="11275-188">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="11275-189">以下のセクションでは、App-v を使用して Office との共存を実装するときに発生する可能性のあるいくつかの問題について説明します。</span><span class="sxs-lookup"><span data-stu-id="11275-189">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="11275-190">Windows Installer ベースまたはクイック実行および App-v Office の共存シナリオに関する制限事項</span><span class="sxs-lookup"><span data-stu-id="11275-190">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="11275-191">同じコンピューターに次のバージョンの Office をインストールすると、次のような制限が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="11275-191">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="11275-192">Windows インストーラーベースのバージョンを使用した Office 2010 の場合</span><span class="sxs-lookup"><span data-stu-id="11275-192">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="11275-193">Office 2013 (app-v を使用)</span><span class="sxs-lookup"><span data-stu-id="11275-193">Office 2013 by using App-V</span></span>

<span data-ttu-id="11275-194">以前のバージョンの Windows Installer ベースの Office 2010 を使用して、Office 2013 を side-by-side 使用して公開した後、Windows インストーラーが起動されることがあります。</span><span class="sxs-lookup"><span data-stu-id="11275-194">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="11275-195">これは、Windows Installer ベースまたはクイック実行バージョンの Office 2010 が、自動的にそのコンピューターに登録しようとしているためです。</span><span class="sxs-lookup"><span data-stu-id="11275-195">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="11275-196">ネイティブ Word 2010 の自動登録操作をバイパスするには、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="11275-196">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="11275-197">Word 2010 を終了します。</span><span class="sxs-lookup"><span data-stu-id="11275-197">Exit Word 2010.</span></span>

2.  <span data-ttu-id="11275-198">次の操作を行って、レジストリエディターを起動します。</span><span class="sxs-lookup"><span data-stu-id="11275-198">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="11275-199">Windows 7 の場合: [**スタート**] ボタンをクリックし、[検索の開始] ボックスに「 **regedit** 」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="11275-199">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="11275-200">Windows 8 では、スタートページで enter キー**を押し、enter キーを**押します。</span><span class="sxs-lookup"><span data-stu-id="11275-200">In Windows 8, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="11275-201">管理者パスワードまたは確認のメッセージが表示された場合は、パスワードを入力するか、[**続行**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11275-201">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="11275-202">次のレジストリサブキーを見つけて選択します。</span><span class="sxs-lookup"><span data-stu-id="11275-202">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="11275-203">[**編集**] メニューの [**新規作成**] をクリックし、[ **DWORD 値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11275-203">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="11275-204">「 **NoReReg**」と入力して、enter キーを押します。</span><span class="sxs-lookup"><span data-stu-id="11275-204">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="11275-205">[ **NoReReg** ] を右クリックし、[**変更**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11275-205">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="11275-206">[ **Valuedata** ] ボックスに「 **1**」と入力し、[ **OK**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="11275-206">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="11275-207">[ファイル] メニューの [**終了**] をクリックして、レジストリエディターを終了します。</span><span class="sxs-lookup"><span data-stu-id="11275-207">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="11275-208">App-v を使用して Office を展開するときの、Office と Windows との統合方法</span><span class="sxs-lookup"><span data-stu-id="11275-208">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="11275-209">App-v を使用して Office 2013 を展開すると、Office はオペレーティングシステムと完全に統合されます。これにより、office は、アプリを展開した場合と同じ機能と機能をエンドユーザーに提供します。</span><span class="sxs-lookup"><span data-stu-id="11275-209">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="11275-210">Office 2013 App-v パッケージでは、次の統合ポイントが Windows オペレーティングシステムと共にサポートされています。</span><span class="sxs-lookup"><span data-stu-id="11275-210">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="11275-211">拡張点</span><span class="sxs-lookup"><span data-stu-id="11275-211">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="11275-212">説明</span><span class="sxs-lookup"><span data-stu-id="11275-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-213">Firefox および Chrome 用の Lync 会議参加プラグイン</span><span class="sxs-lookup"><span data-stu-id="11275-213">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-214">ユーザーは Firefox と Chrome から Lync 会議に参加できます</span><span class="sxs-lookup"><span data-stu-id="11275-214">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-215">OneNote プリンタードライバーに送信されました</span><span class="sxs-lookup"><span data-stu-id="11275-215">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-216">ユーザーは OneNote に印刷できます</span><span class="sxs-lookup"><span data-stu-id="11275-216">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-217">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="11275-217">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-218">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="11275-218">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-219">OneNote Internet Explorer アドインに送る</span><span class="sxs-lookup"><span data-stu-id="11275-219">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-220">ユーザーは IE から OneNote に送信できます</span><span class="sxs-lookup"><span data-stu-id="11275-220">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-221">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="11275-221">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-222">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="11275-222">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-223">MAPI クライアント</span><span class="sxs-lookup"><span data-stu-id="11275-223">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-224">ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</span><span class="sxs-lookup"><span data-stu-id="11275-224">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-225">Firefox 用 SharePoint プラグイン</span><span class="sxs-lookup"><span data-stu-id="11275-225">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-226">ユーザーは Firefox の SharePoint 機能を使用できる</span><span class="sxs-lookup"><span data-stu-id="11275-226">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-227">メールコントロールパネルアプレット</span><span class="sxs-lookup"><span data-stu-id="11275-227">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-228">ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</span><span class="sxs-lookup"><span data-stu-id="11275-228">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-229">プライマリ相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="11275-229">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-230">マネージアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="11275-230">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-231">Office ドキュメントキャッシュハンドラー</span><span class="sxs-lookup"><span data-stu-id="11275-231">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-232">Office アプリケーションのドキュメントキャッシュを許可します</span><span class="sxs-lookup"><span data-stu-id="11275-232">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-233">Outlook プロトコルの検索ハンドラー</span><span class="sxs-lookup"><span data-stu-id="11275-233">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-234">ユーザーが outlook で検索できる</span><span class="sxs-lookup"><span data-stu-id="11275-234">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-235">Active X コントロール:</span><span class="sxs-lookup"><span data-stu-id="11275-235">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-236">ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="11275-236">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-237">Groove の各モバイルの場合</span><span class="sxs-lookup"><span data-stu-id="11275-237">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-238">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-239">PortalConnect サイト</span><span class="sxs-lookup"><span data-stu-id="11275-239">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-240">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-240">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-241">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="11275-241">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-242">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-242">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-243">SharePoint のエクスポートデータベース</span><span class="sxs-lookup"><span data-stu-id="11275-243">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-244">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-244">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-245">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="11275-245">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-246">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-246">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-247">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="11275-247">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-248">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-248">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-249">SharePoint. DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="11275-249">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-250">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-250">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-251">SharePoint. DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="11275-251">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-252">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-252">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-253">Sharepoint の OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="11275-253">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-254">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-254">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-255">Sharepoint のクリップボード Ctl</span><span class="sxs-lookup"><span data-stu-id="11275-255">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-256">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-256">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-257">WinProj</span><span class="sxs-lookup"><span data-stu-id="11275-257">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-258">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-258">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-259">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="11275-259">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-260">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-260">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-261">STSUPld</span><span class="sxs-lookup"><span data-stu-id="11275-261">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-262">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-262">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-263">CommunicatorMeetingJoinAx マネージャー</span><span class="sxs-lookup"><span data-stu-id="11275-263">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-264">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-264">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="11275-265">LISTNETListnet</span><span class="sxs-lookup"><span data-stu-id="11275-265">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-266">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="11275-266">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="11275-267">OneDrive Pro ブラウザーヘルパー</span><span class="sxs-lookup"><span data-stu-id="11275-267">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-268">アクティブエックスコントロール]</span><span class="sxs-lookup"><span data-stu-id="11275-268">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-269">OneDrive Pro アイコンのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="11275-269">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="11275-270">ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</span><span class="sxs-lookup"><span data-stu-id="11275-270">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-271">シェル拡張</span><span class="sxs-lookup"><span data-stu-id="11275-271">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="11275-272">ショートカット</span><span class="sxs-lookup"><span data-stu-id="11275-272">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="11275-273">Windows Search</span><span class="sxs-lookup"><span data-stu-id="11275-273">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





