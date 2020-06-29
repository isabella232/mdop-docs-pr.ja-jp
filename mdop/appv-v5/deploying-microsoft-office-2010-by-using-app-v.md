---
title: APP-V を使用した Microsoft Office 2010 の展開
description: APP-V を使用した Microsoft Office 2010 の展開
author: dansimp
ms.assetid: 0a9e496e-82a1-4dc0-a496-7b21eaa00f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 303a44d921e40a411a4c4ea4622f06a76b8ed9c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814635"
---
# <span data-ttu-id="87251-103">APP-V を使用した Microsoft Office 2010 の展開</span><span class="sxs-lookup"><span data-stu-id="87251-103">Deploying Microsoft Office 2010 by Using App-V</span></span>


<span data-ttu-id="87251-104">Application Virtualization 5.0 用の Office 2010 パッケージは、次のいずれかの方法を使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="87251-104">You can create Office 2010 packages for Application Virtualization 5.0 using one of the following methods:</span></span>

-   <span data-ttu-id="87251-105">Application Virtualization (App-v) Sequencer</span><span class="sxs-lookup"><span data-stu-id="87251-105">Application Virtualization (App-V) Sequencer</span></span>

-   <span data-ttu-id="87251-106">Application Virtualization (App-v) パッケージアクセラレータ</span><span class="sxs-lookup"><span data-stu-id="87251-106">Application Virtualization (App-V) Package Accelerator</span></span>

## <span data-ttu-id="87251-107">Office 2010 用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="87251-107">App-V support for Office 2010</span></span>


<span data-ttu-id="87251-108">次の表は、App-v のバージョン、Office パッケージの作成方法、サポートされているライセンス、Office 2010 のサポートされている展開方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="87251-108">The following table shows the App-V versions, methods of Office package creation, supported licensing, and supported deployments for Office 2010.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="87251-109">サポートされるアイテム</span><span class="sxs-lookup"><span data-stu-id="87251-109">Supported item</span></span></th>
<th align="left"><span data-ttu-id="87251-110">サポートのレベル</span><span class="sxs-lookup"><span data-stu-id="87251-110">Level of support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-111">サポートされている App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="87251-111">Supported App-V versions</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="87251-112">4.6</span><span class="sxs-lookup"><span data-stu-id="87251-112">4.6</span></span></p></li>
<li><p><span data-ttu-id="87251-113">5.0</span><span class="sxs-lookup"><span data-stu-id="87251-113">5.0</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-114">パッケージ作成</span><span class="sxs-lookup"><span data-stu-id="87251-114">Package creation</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="87251-115">付け</span><span class="sxs-lookup"><span data-stu-id="87251-115">Sequencing</span></span></p></li>
<li><p><span data-ttu-id="87251-116">パッケージアクセラレータ</span><span class="sxs-lookup"><span data-stu-id="87251-116">Package Accelerator</span></span></p></li>
<li><p><span data-ttu-id="87251-117">Office 展開キット</span><span class="sxs-lookup"><span data-stu-id="87251-117">Office Deployment Kit</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-118">サポートされているライセンス</span><span class="sxs-lookup"><span data-stu-id="87251-118">Supported licensing</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-119">ボリューム ライセンス</span><span class="sxs-lookup"><span data-stu-id="87251-119">Volume Licensing</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-120">サポートされる展開</span><span class="sxs-lookup"><span data-stu-id="87251-120">Supported deployments</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="87251-121">Desktop</span><span class="sxs-lookup"><span data-stu-id="87251-121">Desktop</span></span></p></li>
<li><p><span data-ttu-id="87251-122">パーソナル VDI</span><span class="sxs-lookup"><span data-stu-id="87251-122">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="87251-123">RDS</span><span class="sxs-lookup"><span data-stu-id="87251-123">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="87251-124">Sequencer を使用した Office 2010 App-V 5.0 の作成</span><span class="sxs-lookup"><span data-stu-id="87251-124">Creating Office 2010 App-V 5.0 using the sequencer</span></span>


<span data-ttu-id="87251-125">シーケンス Office 2010 は、App-v 5.0 で Office 2010 パッケージを作成するための主な方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="87251-125">Sequencing Office 2010 is one of the main methods for creating an Office 2010 package on App-V 5.0.</span></span> <span data-ttu-id="87251-126">Microsoft は、サポート技術情報の記事を通じて詳細なレシピを提供しています。</span><span class="sxs-lookup"><span data-stu-id="87251-126">Microsoft has provided a detailed recipe through a Knowledge Base article.</span></span> <span data-ttu-id="87251-127">App-v 5.0 で Office 2010 パッケージを作成するには、詳細な手順については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="87251-127">To create an Office 2010 package on App-V 5.0, refer to the following link for detailed instructions:</span></span>

[<span data-ttu-id="87251-128">Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="87251-128">How To Sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## <span data-ttu-id="87251-129">パッケージアクセラレータを使用した Office 2010 App-V 5.0 パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="87251-129">Creating Office 2010 App-V 5.0 packages using package accelerators</span></span>


<span data-ttu-id="87251-130">Office 2010 アプリ-V 5.0 パッケージは、パッケージアクセラレータを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="87251-130">Office 2010 App-V 5.0 packages can be created through package accelerators.</span></span> <span data-ttu-id="87251-131">Microsoft は、Windows 8 と Windows 7 で Office 2010 を作成するためのパッケージアクセラレータを提供しています。</span><span class="sxs-lookup"><span data-stu-id="87251-131">Microsoft has provided package accelerators for creating Office 2010 on Windows 8 and Windows 7.</span></span> <span data-ttu-id="87251-132">パッケージアクセラレータを使用して App-v で Office 2010 パッケージを作成するには、次のページを参照して適切なパッケージアクセラレータにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="87251-132">To create Office 2010 packages on App-V using Package accelerators, refer to the following pages to access the appropriate package accelerator:</span></span>

-   [<span data-ttu-id="87251-133">Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 8)</span><span class="sxs-lookup"><span data-stu-id="87251-133">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 8</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [<span data-ttu-id="87251-134">Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 7)</span><span class="sxs-lookup"><span data-stu-id="87251-134">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 7</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330678)

<span data-ttu-id="87251-135">App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法の詳細については、「 [App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="87251-135">For detailed instructions on how to create virtual application packages using App-V package accelerators, see [How to Create a Virtual Application Package Using an App-V Package Accelerator](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md).</span></span>

## <span data-ttu-id="87251-136">App-v 5.0 用 Microsoft Office パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="87251-136">Deploying the Microsoft Office package for App-V 5.0</span></span>


<span data-ttu-id="87251-137">Office 2010 パッケージを展開するには、次のいずれかの App-v 展開方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="87251-137">You can deploy Office 2010 packages by using any of the following App-V deployment methods:</span></span>

-   <span data-ttu-id="87251-138">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87251-138">System Center Configuration Manager</span></span>

-   <span data-ttu-id="87251-139">App-v server</span><span class="sxs-lookup"><span data-stu-id="87251-139">App-V server</span></span>

-   <span data-ttu-id="87251-140">PowerShell コマンドを使用したスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="87251-140">Stand-alone through PowerShell commands</span></span>

## <span data-ttu-id="87251-141">Office App-v パッケージの管理とカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="87251-141">Office App-V package management and customization</span></span>


<span data-ttu-id="87251-142">Office 2010 パッケージは、既知のパッケージ管理メカニズムを通じて、他の App-v 5.0 パッケージと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="87251-142">Office 2010 packages can be managed like any other App-V 5.0 packages through known package management mechanisms.</span></span> <span data-ttu-id="87251-143">Office パッケージの追加、公開、発行取り消し、削除など、特別な手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="87251-143">No special instructions are needed, for example, to add, publish, unpublish, or remove Office packages.</span></span>

## <span data-ttu-id="87251-144">Microsoft Office と Windows の統合</span><span class="sxs-lookup"><span data-stu-id="87251-144">Microsoft Office integration with Windows</span></span>


<span data-ttu-id="87251-145">次の表では、Office 2010 でサポートされている統合ポイントの完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="87251-145">The following table provides a full list of supported integration points for Office 2010.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="87251-146">拡張点</span><span class="sxs-lookup"><span data-stu-id="87251-146">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="87251-147">説明</span><span class="sxs-lookup"><span data-stu-id="87251-147">Description</span></span></th>
<th align="left"><span data-ttu-id="87251-148">Office 2010</span><span class="sxs-lookup"><span data-stu-id="87251-148">Office 2010</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-149">Firefox および Chrome 用の Lync 会議参加プラグイン</span><span class="sxs-lookup"><span data-stu-id="87251-149">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-150">ユーザーは Firefox と Chrome から Lync 会議に参加できます</span><span class="sxs-lookup"><span data-stu-id="87251-150">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-151">OneNote プリンタードライバーに送信されました</span><span class="sxs-lookup"><span data-stu-id="87251-151">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-152">ユーザーは OneNote に印刷できます</span><span class="sxs-lookup"><span data-stu-id="87251-152">User can print to OneNote</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-153">あり</span><span class="sxs-lookup"><span data-stu-id="87251-153">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-154">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="87251-154">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-155">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="87251-155">OneNote Linked Notes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-156">OneNote Internet Explorer アドインに送る</span><span class="sxs-lookup"><span data-stu-id="87251-156">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-157">ユーザーは IE から OneNote に送信できます</span><span class="sxs-lookup"><span data-stu-id="87251-157">User can send to OneNote from IE</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-158">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="87251-158">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-159">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="87251-159">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-160">MAPI クライアント</span><span class="sxs-lookup"><span data-stu-id="87251-160">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-161">ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</span><span class="sxs-lookup"><span data-stu-id="87251-161">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-162">Firefox 用 SharePoint プラグイン</span><span class="sxs-lookup"><span data-stu-id="87251-162">SharePoint Plugin for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-163">ユーザーは Firefox の SharePoint 機能を使用できる</span><span class="sxs-lookup"><span data-stu-id="87251-163">User can use SharePoint features in Firefox</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-164">メールコントロールパネルアプレット</span><span class="sxs-lookup"><span data-stu-id="87251-164">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-165">ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</span><span class="sxs-lookup"><span data-stu-id="87251-165">User gets the mail control panel applet in Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-166">あり</span><span class="sxs-lookup"><span data-stu-id="87251-166">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-167">プライマリ相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="87251-167">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-168">マネージアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="87251-168">Support managed add-ins</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-169">Office ドキュメントキャッシュハンドラー</span><span class="sxs-lookup"><span data-stu-id="87251-169">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-170">Office アプリケーションのドキュメントキャッシュを許可します</span><span class="sxs-lookup"><span data-stu-id="87251-170">Allows Document Cache for Office applications</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-171">Outlook プロトコルの検索ハンドラー</span><span class="sxs-lookup"><span data-stu-id="87251-171">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-172">ユーザーが outlook で検索できる</span><span class="sxs-lookup"><span data-stu-id="87251-172">User can search in outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-173">あり</span><span class="sxs-lookup"><span data-stu-id="87251-173">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="87251-174">Active X コントロール:</span><span class="sxs-lookup"><span data-stu-id="87251-174">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-175">ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="87251-175">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-176">Groove の各モバイルの場合</span><span class="sxs-lookup"><span data-stu-id="87251-176">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-177">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-177">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-178">PortalConnect サイト</span><span class="sxs-lookup"><span data-stu-id="87251-178">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-179">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-179">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-180">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="87251-180">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-181">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-181">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-182">SharePoint のエクスポートデータベース</span><span class="sxs-lookup"><span data-stu-id="87251-182">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-183">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-183">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-184">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="87251-184">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-185">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-185">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-186">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="87251-186">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-187">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-187">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-188">SharePoint. DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="87251-188">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-189">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-189">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-190">SharePoint. DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="87251-190">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-191">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-191">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-192">Sharepoint Xmldocuments</span><span class="sxs-lookup"><span data-stu-id="87251-192">Sharpoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-193">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-193">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-194">Sharepoint のクリップボード Ctl</span><span class="sxs-lookup"><span data-stu-id="87251-194">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-195">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-195">Active X control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-196">WinProj</span><span class="sxs-lookup"><span data-stu-id="87251-196">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-197">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-197">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-198">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="87251-198">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-199">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-199">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-200">STSUPld</span><span class="sxs-lookup"><span data-stu-id="87251-200">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-201">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-201">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-202">CommunicatorMeetingJoinAx マネージャー</span><span class="sxs-lookup"><span data-stu-id="87251-202">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-203">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-203">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="87251-204">LISTNETListnet</span><span class="sxs-lookup"><span data-stu-id="87251-204">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-205">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="87251-205">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="87251-206">OneDrive Pro ブラウザーヘルパー</span><span class="sxs-lookup"><span data-stu-id="87251-206">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-207">アクティブエックスコントロール]</span><span class="sxs-lookup"><span data-stu-id="87251-207">Active X Control]</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="87251-208">OneDrive Pro アイコンのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="87251-208">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="87251-209">ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</span><span class="sxs-lookup"><span data-stu-id="87251-209">Windows explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="87251-210">その他の情報</span><span class="sxs-lookup"><span data-stu-id="87251-210">Additional resources</span></span>


**<span data-ttu-id="87251-211">Office 2013 アプリ-V 5.0 パッケージ5.0 その他のリソース</span><span class="sxs-lookup"><span data-stu-id="87251-211">Office 2013 App-V 5.0 Packages 5.0 Additional Resources</span></span>**

[<span data-ttu-id="87251-212">シーケンス付きの App-v パッケージとして Microsoft Office を展開する場合のサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="87251-212">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="87251-213">Office 2010 アプリ-V 5.0 パッケージ</span><span class="sxs-lookup"><span data-stu-id="87251-213">Office 2010 App-V 5.0 Packages</span></span>**

[<span data-ttu-id="87251-214">Microsoft Application Virtualization 5.0 用 microsoft Office 2010 シーケンスキット</span><span class="sxs-lookup"><span data-stu-id="87251-214">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="87251-215">App-v 5.0 Office 2010 パッケージを作成または使用するときの既知の問題</span><span class="sxs-lookup"><span data-stu-id="87251-215">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="87251-216">Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="87251-216">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="87251-217">接続グループ</span><span class="sxs-lookup"><span data-stu-id="87251-217">Connection Groups</span></span>**

[<span data-ttu-id="87251-218">Microsoft App での接続グループの展開-V v5</span><span class="sxs-lookup"><span data-stu-id="87251-218">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="87251-219">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="87251-219">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="87251-220">動的構成</span><span class="sxs-lookup"><span data-stu-id="87251-220">Dynamic Configuration</span></span>**

[<span data-ttu-id="87251-221">App-V 5.0 の動的構成について</span><span class="sxs-lookup"><span data-stu-id="87251-221">About App-V 5.0 Dynamic Configuration</span></span>](about-app-v-50-dynamic-configuration.md)






 

 





