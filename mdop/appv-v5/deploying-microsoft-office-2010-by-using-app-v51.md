---
title: APP-V を使用した Microsoft Office 2010 の展開
description: APP-V を使用した Microsoft Office 2010 の展開
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814626"
---
# <span data-ttu-id="9e9e9-103">APP-V を使用した Microsoft Office 2010 の展開</span><span class="sxs-lookup"><span data-stu-id="9e9e9-103">Deploying Microsoft Office 2010 by Using App-V</span></span>


<span data-ttu-id="9e9e9-104">Microsoft Application Virtualization (App-v) 5.1 用の Office 2010 パッケージを作成するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-104">You can create Office 2010 packages for Microsoft Application Virtualization (App-V) 5.1 using one of the following methods:</span></span>

-   <span data-ttu-id="9e9e9-105">Application Virtualization (App-v) Sequencer</span><span class="sxs-lookup"><span data-stu-id="9e9e9-105">Application Virtualization (App-V) Sequencer</span></span>

-   <span data-ttu-id="9e9e9-106">Application Virtualization (App-v) パッケージアクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-106">Application Virtualization (App-V) Package Accelerator</span></span>

## <span data-ttu-id="9e9e9-107">Office 2010 用の app-v サポート</span><span class="sxs-lookup"><span data-stu-id="9e9e9-107">App-V support for Office 2010</span></span>


<span data-ttu-id="9e9e9-108">次の表は、App-v のバージョン、Office パッケージの作成方法、サポートされているライセンス、Office 2010 のサポートされている展開方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-108">The following table shows the App-V versions, methods of Office package creation, supported licensing, and supported deployments for Office 2010.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9e9e9-109">サポートされるアイテム</span><span class="sxs-lookup"><span data-stu-id="9e9e9-109">Supported item</span></span></th>
<th align="left"><span data-ttu-id="9e9e9-110">サポートのレベル</span><span class="sxs-lookup"><span data-stu-id="9e9e9-110">Level of support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-111">サポートされている App-v のバージョン</span><span class="sxs-lookup"><span data-stu-id="9e9e9-111">Supported App-V versions</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9e9e9-112">4.6</span><span class="sxs-lookup"><span data-stu-id="9e9e9-112">4.6</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-113">5.0</span><span class="sxs-lookup"><span data-stu-id="9e9e9-113">5.0</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-114">5.1</span><span class="sxs-lookup"><span data-stu-id="9e9e9-114">5.1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-115">パッケージ作成</span><span class="sxs-lookup"><span data-stu-id="9e9e9-115">Package creation</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9e9e9-116">付け</span><span class="sxs-lookup"><span data-stu-id="9e9e9-116">Sequencing</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-117">パッケージアクセラレータ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-117">Package Accelerator</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-118">Office 展開キット</span><span class="sxs-lookup"><span data-stu-id="9e9e9-118">Office Deployment Kit</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-119">サポートされているライセンス</span><span class="sxs-lookup"><span data-stu-id="9e9e9-119">Supported licensing</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-120">ボリューム ライセンス</span><span class="sxs-lookup"><span data-stu-id="9e9e9-120">Volume Licensing</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-121">サポートされる展開</span><span class="sxs-lookup"><span data-stu-id="9e9e9-121">Supported deployments</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="9e9e9-122">Desktop</span><span class="sxs-lookup"><span data-stu-id="9e9e9-122">Desktop</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-123">パーソナル VDI</span><span class="sxs-lookup"><span data-stu-id="9e9e9-123">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="9e9e9-124">RDS</span><span class="sxs-lookup"><span data-stu-id="9e9e9-124">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9e9e9-125">Sequencer を使用した Office 2010 App-V 5.1 の作成</span><span class="sxs-lookup"><span data-stu-id="9e9e9-125">Creating Office 2010 App-V 5.1 using the sequencer</span></span>


<span data-ttu-id="9e9e9-126">シーケンス Office 2010 は、App-v 5.1 で Office 2010 パッケージを作成するための主な方法の1つです。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-126">Sequencing Office 2010 is one of the main methods for creating an Office 2010 package on App-V 5.1.</span></span> <span data-ttu-id="9e9e9-127">Microsoft は、サポート技術情報の記事を通じて詳細なレシピを提供しています。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-127">Microsoft has provided a detailed recipe through a Knowledge Base article.</span></span> <span data-ttu-id="9e9e9-128">App-v 5.1 で Office 2010 パッケージを作成するには、詳細な手順については、次のリンクを参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-128">To create an Office 2010 package on App-V 5.1, refer to the following link for detailed instructions:</span></span>

[<span data-ttu-id="9e9e9-129">Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="9e9e9-129">How To Sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## <span data-ttu-id="9e9e9-130">パッケージアクセラレータを使用した Office 2010 App-V 5.1 パッケージの作成</span><span class="sxs-lookup"><span data-stu-id="9e9e9-130">Creating Office 2010 App-V 5.1 packages using package accelerators</span></span>


<span data-ttu-id="9e9e9-131">Office 2010 アプリ-V 5.1 パッケージは、パッケージアクセラレータを使用して作成できます。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-131">Office 2010 App-V 5.1 packages can be created through package accelerators.</span></span> <span data-ttu-id="9e9e9-132">Microsoft は、windows 10、Windows 8、Windows 7 で Office 2010 を作成するためのパッケージアクセラレータを提供しています。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-132">Microsoft has provided package accelerators for creating Office 2010 on Windows 10, Windows 8 and Windows 7.</span></span> <span data-ttu-id="9e9e9-133">パッケージアクセラレータを使用して App-v で Office 2010 パッケージを作成するには、次のページを参照して適切なパッケージアクセラレータにアクセスしてください。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-133">To create Office 2010 packages on App-V using Package accelerators, refer to the following pages to access the appropriate package accelerator:</span></span>

-   [<span data-ttu-id="9e9e9-134">Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 8)</span><span class="sxs-lookup"><span data-stu-id="9e9e9-134">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 8</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [<span data-ttu-id="9e9e9-135">Office Professional Plus 2010 用の app-v 5.0 パッケージアクセラレーター (Windows 7)</span><span class="sxs-lookup"><span data-stu-id="9e9e9-135">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 7</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330678)

<span data-ttu-id="9e9e9-136">App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法の詳細については、「 [App-v パッケージアクセラレータを使用して仮想アプリケーションパッケージを作成する方法](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-136">For detailed instructions on how to create virtual application packages using App-V package accelerators, see [How to Create a Virtual Application Package Using an App-V Package Accelerator](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md).</span></span>

## <span data-ttu-id="9e9e9-137">App-v 5.1 用 Microsoft Office パッケージの展開</span><span class="sxs-lookup"><span data-stu-id="9e9e9-137">Deploying the Microsoft Office package for App-V 5.1</span></span>


<span data-ttu-id="9e9e9-138">Office 2010 パッケージを展開するには、次のいずれかの App-v 展開方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-138">You can deploy Office 2010 packages by using any of the following App-V deployment methods:</span></span>

-   <span data-ttu-id="9e9e9-139">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9e9e9-139">System Center Configuration Manager</span></span>

-   <span data-ttu-id="9e9e9-140">App-v server</span><span class="sxs-lookup"><span data-stu-id="9e9e9-140">App-V server</span></span>

-   <span data-ttu-id="9e9e9-141">PowerShell コマンドを使用したスタンドアロン</span><span class="sxs-lookup"><span data-stu-id="9e9e9-141">Stand-alone through PowerShell commands</span></span>

## <span data-ttu-id="9e9e9-142">Office App-v パッケージの管理とカスタマイズ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-142">Office App-V package management and customization</span></span>


<span data-ttu-id="9e9e9-143">Office 2010 パッケージは、既知のパッケージ管理メカニズムを通じて、他の App-v 5.1 パッケージと同じように管理できます。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-143">Office 2010 packages can be managed like any other App-V 5.1 packages through known package management mechanisms.</span></span> <span data-ttu-id="9e9e9-144">Office パッケージの追加、公開、発行取り消し、削除など、特別な手順は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-144">No special instructions are needed, for example, to add, publish, unpublish, or remove Office packages.</span></span>

## <span data-ttu-id="9e9e9-145">Microsoft Office と Windows の統合</span><span class="sxs-lookup"><span data-stu-id="9e9e9-145">Microsoft Office integration with Windows</span></span>


<span data-ttu-id="9e9e9-146">次の表では、Office 2010 でサポートされている統合ポイントの完全な一覧を示します。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-146">The following table provides a full list of supported integration points for Office 2010.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9e9e9-147">拡張点</span><span class="sxs-lookup"><span data-stu-id="9e9e9-147">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="9e9e9-148">説明</span><span class="sxs-lookup"><span data-stu-id="9e9e9-148">Description</span></span></th>
<th align="left"><span data-ttu-id="9e9e9-149">Office 2010</span><span class="sxs-lookup"><span data-stu-id="9e9e9-149">Office 2010</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-150">Firefox および Chrome 用の Lync 会議参加プラグイン</span><span class="sxs-lookup"><span data-stu-id="9e9e9-150">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-151">ユーザーは Firefox と Chrome から Lync 会議に参加できます</span><span class="sxs-lookup"><span data-stu-id="9e9e9-151">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-152">OneNote プリンタードライバーに送信されました</span><span class="sxs-lookup"><span data-stu-id="9e9e9-152">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-153">ユーザーは OneNote に印刷できます</span><span class="sxs-lookup"><span data-stu-id="9e9e9-153">User can print to OneNote</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-154">あり</span><span class="sxs-lookup"><span data-stu-id="9e9e9-154">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-155">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="9e9e9-155">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-156">OneNote のリンクノート</span><span class="sxs-lookup"><span data-stu-id="9e9e9-156">OneNote Linked Notes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-157">OneNote Internet Explorer アドインに送る</span><span class="sxs-lookup"><span data-stu-id="9e9e9-157">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-158">ユーザーは IE から OneNote に送信できます</span><span class="sxs-lookup"><span data-stu-id="9e9e9-158">User can send to OneNote from IE</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-159">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="9e9e9-159">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-160">Lync と Outlook のファイアウォール例外</span><span class="sxs-lookup"><span data-stu-id="9e9e9-160">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-161">MAPI クライアント</span><span class="sxs-lookup"><span data-stu-id="9e9e9-161">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-162">ネイティブアプリとアドインは、MAPI 経由で仮想 Outlook を操作できます。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-162">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-163">Firefox 用 SharePoint プラグイン</span><span class="sxs-lookup"><span data-stu-id="9e9e9-163">SharePoint Plugin for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-164">ユーザーは Firefox の SharePoint 機能を使用できる</span><span class="sxs-lookup"><span data-stu-id="9e9e9-164">User can use SharePoint features in Firefox</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-165">メールコントロールパネルアプレット</span><span class="sxs-lookup"><span data-stu-id="9e9e9-165">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-166">ユーザーが Outlook の [メールコントロールパネル] アプレットを取得します</span><span class="sxs-lookup"><span data-stu-id="9e9e9-166">User gets the mail control panel applet in Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-167">あり</span><span class="sxs-lookup"><span data-stu-id="9e9e9-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-168">プライマリ相互運用機能アセンブリ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-168">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-169">マネージアドインのサポート</span><span class="sxs-lookup"><span data-stu-id="9e9e9-169">Support managed add-ins</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-170">Office ドキュメントキャッシュハンドラー</span><span class="sxs-lookup"><span data-stu-id="9e9e9-170">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-171">Office アプリケーションのドキュメントキャッシュを許可します</span><span class="sxs-lookup"><span data-stu-id="9e9e9-171">Allows Document Cache for Office applications</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-172">Outlook プロトコルの検索ハンドラー</span><span class="sxs-lookup"><span data-stu-id="9e9e9-172">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-173">ユーザーが outlook で検索できる</span><span class="sxs-lookup"><span data-stu-id="9e9e9-173">User can search in outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-174">あり</span><span class="sxs-lookup"><span data-stu-id="9e9e9-174">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e9e9-175">Active X コントロール:</span><span class="sxs-lookup"><span data-stu-id="9e9e9-175">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-176">ActiveX コントロールの詳細については、「 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex コントロール API リファレンス」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="9e9e9-176">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-177">Groove の各モバイルの場合</span><span class="sxs-lookup"><span data-stu-id="9e9e9-177">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-178">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-178">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-179">PortalConnect サイト</span><span class="sxs-lookup"><span data-stu-id="9e9e9-179">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-180">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-180">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-181">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="9e9e9-181">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-182">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-182">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-183">SharePoint のエクスポートデータベース</span><span class="sxs-lookup"><span data-stu-id="9e9e9-183">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-184">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-184">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-185">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="9e9e9-185">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-186">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-186">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-187">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="9e9e9-187">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-188">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-188">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-189">SharePoint. DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="9e9e9-189">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-190">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-190">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-191">SharePoint. DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="9e9e9-191">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-192">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-192">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-193">Sharepoint Xmldocuments</span><span class="sxs-lookup"><span data-stu-id="9e9e9-193">Sharpoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-194">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-194">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-195">Sharepoint のクリップボード Ctl</span><span class="sxs-lookup"><span data-stu-id="9e9e9-195">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-196">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-196">Active X control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-197">WinProj</span><span class="sxs-lookup"><span data-stu-id="9e9e9-197">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-198">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-198">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-199">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="9e9e9-199">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-200">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-200">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-201">STSUPld</span><span class="sxs-lookup"><span data-stu-id="9e9e9-201">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-202">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-202">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-203">CommunicatorMeetingJoinAx マネージャー</span><span class="sxs-lookup"><span data-stu-id="9e9e9-203">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-204">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-204">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="9e9e9-205">LISTNETListnet</span><span class="sxs-lookup"><span data-stu-id="9e9e9-205">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-206">Active X コントロール</span><span class="sxs-lookup"><span data-stu-id="9e9e9-206">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="9e9e9-207">OneDrive Pro ブラウザーヘルパー</span><span class="sxs-lookup"><span data-stu-id="9e9e9-207">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-208">アクティブエックスコントロール]</span><span class="sxs-lookup"><span data-stu-id="9e9e9-208">Active X Control]</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e9e9-209">OneDrive Pro アイコンのオーバーレイ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-209">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e9e9-210">ユーザーがフォルダーの OneDrive Pro フォルダーを表示すると、Windows エクスプローラーシェルアイコンがオーバーレイされる</span><span class="sxs-lookup"><span data-stu-id="9e9e9-210">Windows explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9e9e9-211">その他の情報</span><span class="sxs-lookup"><span data-stu-id="9e9e9-211">Additional resources</span></span>


**<span data-ttu-id="9e9e9-212">Office 2013 App-v パッケージのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="9e9e9-212">Office 2013 App-V Packages Additional Resources</span></span>**

[<span data-ttu-id="9e9e9-213">シーケンス付きの App-v パッケージとして Microsoft Office を展開する場合のサポートされるシナリオ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-213">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="9e9e9-214">Office 2010 App-v パッケージ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-214">Office 2010 App-V Packages</span></span>**

[<span data-ttu-id="9e9e9-215">Microsoft Application Virtualization 5.0 用 microsoft Office 2010 シーケンスキット</span><span class="sxs-lookup"><span data-stu-id="9e9e9-215">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="9e9e9-216">App-v 5.0 Office 2010 パッケージを作成または使用するときの既知の問題</span><span class="sxs-lookup"><span data-stu-id="9e9e9-216">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="9e9e9-217">Microsoft Application Virtualization 5.0 で Microsoft Office 2010 をシーケンス処理する方法</span><span class="sxs-lookup"><span data-stu-id="9e9e9-217">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="9e9e9-218">接続グループ</span><span class="sxs-lookup"><span data-stu-id="9e9e9-218">Connection Groups</span></span>**

[<span data-ttu-id="9e9e9-219">Microsoft App での接続グループの展開-V v5</span><span class="sxs-lookup"><span data-stu-id="9e9e9-219">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="9e9e9-220">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="9e9e9-220">Managing Connection Groups</span></span>](managing-connection-groups51.md)

**<span data-ttu-id="9e9e9-221">動的構成</span><span class="sxs-lookup"><span data-stu-id="9e9e9-221">Dynamic Configuration</span></span>**

[<span data-ttu-id="9e9e9-222">App-V 5.1 の動的構成について</span><span class="sxs-lookup"><span data-stu-id="9e9e9-222">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)






 

 





