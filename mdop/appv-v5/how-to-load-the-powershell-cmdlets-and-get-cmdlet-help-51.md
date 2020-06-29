---
title: PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法
description: PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法
author: dansimp
ms.assetid: b6ae5460-2c3a-4030-b132-394d9d5a541e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 32b5bb26331f204acffbf96ea119ac4209c3cd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813947"
---
# <span data-ttu-id="7c89c-103">PowerShell コマンドレットを読み込んでコマンドレットのヘルプを取得する方法</span><span class="sxs-lookup"><span data-stu-id="7c89c-103">How to Load the PowerShell Cmdlets and Get Cmdlet Help</span></span>


<span data-ttu-id="7c89c-104">このトピックについては、次のトピックをご覧ください。</span><span class="sxs-lookup"><span data-stu-id="7c89c-104">What this topic covers:</span></span>

-   [<span data-ttu-id="7c89c-105">PowerShell コマンドレットを使うための要件</span><span class="sxs-lookup"><span data-stu-id="7c89c-105">Requirements for using PowerShell cmdlets</span></span>](#bkmk-reqs-using-posh)

-   [<span data-ttu-id="7c89c-106">PowerShell コマンドレットの読み込み</span><span class="sxs-lookup"><span data-stu-id="7c89c-106">Loading the PowerShell cmdlets</span></span>](#bkmk-load-cmdlets)

-   [<span data-ttu-id="7c89c-107">PowerShell コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="7c89c-107">Getting help for the PowerShell cmdlets</span></span>](#bkmk-get-cmdlet-help)

-   [<span data-ttu-id="7c89c-108">PowerShell コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="7c89c-108">Displaying the help for a PowerShell cmdlet</span></span>](#bkmk-display-help-cmdlet)

## <a href="" id="bkmk-reqs-using-posh"></a><span data-ttu-id="7c89c-109">PowerShell コマンドレットを使うための要件</span><span class="sxs-lookup"><span data-stu-id="7c89c-109">Requirements for using PowerShell cmdlets</span></span>


<span data-ttu-id="7c89c-110">App-v PowerShell コマンドレットを使用するための次の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-110">Review the following requirements for using the App-V PowerShell cmdlets:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c89c-111">要件</span><span class="sxs-lookup"><span data-stu-id="7c89c-111">Requirement</span></span></th>
<th align="left"><span data-ttu-id="7c89c-112">詳細</span><span class="sxs-lookup"><span data-stu-id="7c89c-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-113">ユーザーは、次のいずれかの方法を使用して、アクセス権を付与した場合にのみ、App-v Server コマンドレットを実行できます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-113">Users can run App-V Server cmdlets only if you grant them access by using one of the following methods:</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="7c89c-114">App-v Server を展開して構成する場合 </strong> :</span><span class="sxs-lookup"><span data-stu-id="7c89c-114">When you are deploying and configuring the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="7c89c-115">Active Directory グループ、または App-v 環境を管理する権限を持つ個々のユーザーを指定します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-115">Specify an Active Directory group or individual user that has permissions to manage the App-V environment.</span></span> <span data-ttu-id="7c89c-116">「 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> App-v 5.1 サーバーを展開する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="7c89c-116">See <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)">How to Deploy the App-V 5.1 Server</a>.</span></span></p></li>
<li><p><strong><span data-ttu-id="7c89c-117">App-v Server を展開した後は、 </strong> 次の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="7c89c-117">After you’ve deployed the App-V Server</strong>:</span></span></p>
<p><span data-ttu-id="7c89c-118">App-v 管理コンソールを使用して、追加の Active Directory グループまたはユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-118">Use the App-V Management console to add an additional Active Directory group or user.</span></span> <span data-ttu-id="7c89c-119"><a href="how-to-add-or-remove-an-administrator-by-using-the-management-console51.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)">管理コンソールを使用して管理者を追加または削除する方法について説明し </a> ます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-119">See <a href="how-to-add-or-remove-an-administrator-by-using-the-management-console51.md" data-raw-source="[How to Add or Remove an Administrator by Using the Management Console](how-to-add-or-remove-an-administrator-by-using-the-management-console51.md)">How to Add or Remove an Administrator by Using the Management Console</a>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c89c-120">昇格されたコマンドプロンプトを必要とするコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7c89c-120">Cmdlets that require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7c89c-121">Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="7c89c-121">Add-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="7c89c-122">Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="7c89c-122">Remove-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="7c89c-123">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="7c89c-123">Set-AppvClientConfiguration</span></span></p></li>
<li><p><span data-ttu-id="7c89c-124">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="7c89c-124">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="7c89c-125">Remove-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="7c89c-125">Remove-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="7c89c-126">Add-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="7c89c-126">Add-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="7c89c-127">Remove-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="7c89c-127">Remove-AppvPublishingServer</span></span></p></li>
<li><p><span data-ttu-id="7c89c-128">送信-AppvClientReport</span><span class="sxs-lookup"><span data-stu-id="7c89c-128">Send-AppvClientReport</span></span></p></li>
<li><p><span data-ttu-id="7c89c-129">Set-AppvClientMode</span><span class="sxs-lookup"><span data-stu-id="7c89c-129">Set-AppvClientMode</span></span></p></li>
<li><p><span data-ttu-id="7c89c-130">Set-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="7c89c-130">Set-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="7c89c-131">Set-AppvPublishingServer</span><span class="sxs-lookup"><span data-stu-id="7c89c-131">Set-AppvPublishingServer</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-132">管理者特権のコマンドプロンプトを要求するように構成していない場合は、エンドユーザーが実行できるコマンドレット</span><span class="sxs-lookup"><span data-stu-id="7c89c-132">Cmdlets that end users can run, unless you configure them to require an elevated command prompt</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="7c89c-133">公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="7c89c-133">Publish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="7c89c-134">未発行-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="7c89c-134">Unpublish-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="7c89c-135">管理者特権でコマンドプロンプトを要求するようにこれらのコマンドレットを構成するには、次のいずれかの方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-135">To configure these cmdlets to require an elevated command prompt, use one of the following methods:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c89c-136">メソッド</span><span class="sxs-lookup"><span data-stu-id="7c89c-136">Method</span></span></th>
<th align="left"><span data-ttu-id="7c89c-137">その他のリソース</span><span class="sxs-lookup"><span data-stu-id="7c89c-137">More resources</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-138"><strong> </strong> <strong> -Requirepublishasadmin パラメーターを指定して AppvClientConfiguration コマンドレットを実行し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-138">Run the <strong>Set-AppvClientConfiguration</strong> cmdlet with the <strong>-RequirePublishAsAdmin</strong> parameter.</span></span></p></td>
<td align="left"><ul>
<li><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md#bkmk-admin-only-posh-topic-cg" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md#bkmk-admin-only-posh-topic-cg)"><span data-ttu-id="7c89c-139">PowerShell を使用してスタンドアロン コンピューターで接続グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="7c89c-139">How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell</span></span></a></p></li>
<li><p><a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"><span data-ttu-id="7c89c-140">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="7c89c-140">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span></a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c89c-141">App-v クライアントの [管理者として発行する] グループポリシー設定を有効にします。</span><span class="sxs-lookup"><span data-stu-id="7c89c-141">Enable the “Require publish as administrator” Group Policy setting for App-V Clients.</span></span></p></td>
<td align="left"><p><a href="how-to-publish-a-package-by-using-the-management-console-51.md" data-raw-source="[How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md)"><span data-ttu-id="7c89c-142">管理コンソールを使用してパッケージを公開する方法</span><span class="sxs-lookup"><span data-stu-id="7c89c-142">How to Publish a Package by Using the Management Console</span></span></a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-load-cmdlets"></a><span data-ttu-id="7c89c-143">PowerShell コマンドレットの読み込み</span><span class="sxs-lookup"><span data-stu-id="7c89c-143">Loading the PowerShell cmdlets</span></span>

<span data-ttu-id="7c89c-144">PowerShell コマンドレットモジュールを読み込むには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c89c-144">To load the PowerShell cmdlet modules:</span></span>

1.  <span data-ttu-id="7c89c-145">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-145">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="7c89c-146">次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-146">Type one of the following commands to load the cmdlets for the module you want:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c89c-147">App-v コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7c89c-147">App-V component</span></span></th>
<th align="left"><span data-ttu-id="7c89c-148">入力するコマンド</span><span class="sxs-lookup"><span data-stu-id="7c89c-148">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-149">App-v Server</span><span class="sxs-lookup"><span data-stu-id="7c89c-149">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-150">インポート-モジュール AppvServer</span><span class="sxs-lookup"><span data-stu-id="7c89c-150">Import-Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c89c-151">App-v Sequencer</span><span class="sxs-lookup"><span data-stu-id="7c89c-151">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-152">インポート-モジュール AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="7c89c-152">Import-Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-153">App-v クライアント</span><span class="sxs-lookup"><span data-stu-id="7c89c-153">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-154">インポート-モジュール AppvClient</span><span class="sxs-lookup"><span data-stu-id="7c89c-154">Import-Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>

## <a href="" id="bkmk-get-cmdlet-help"></a><span data-ttu-id="7c89c-155">PowerShell コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="7c89c-155">Getting help for the PowerShell cmdlets</span></span>
<span data-ttu-id="7c89c-156">App-v 5.0 SP3 以降では、コマンドレットのヘルプは次の2つの形式で提供されます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-156">Starting in App-V 5.0 SP3, cmdlet help is available in two formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c89c-157">形式</span><span class="sxs-lookup"><span data-stu-id="7c89c-157">Format</span></span></th>
<th align="left"><span data-ttu-id="7c89c-158">説明</span><span class="sxs-lookup"><span data-stu-id="7c89c-158">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-159">ダウンロード可能なモジュールとして</span><span class="sxs-lookup"><span data-stu-id="7c89c-159">As a downloadable module</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-160">コマンドレットモジュールをダウンロードした後、最新のヘルプをダウンロードするには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c89c-160">To download the latest help after downloading the cmdlet module:</span></span></p>
<ol>
<li><p><span data-ttu-id="7c89c-161">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-161">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span></p></li>
<li><p><span data-ttu-id="7c89c-162">次のいずれかのコマンドを入力して、目的のモジュールのコマンドレットを読み込みます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-162">Type one of the following commands to load the cmdlets for the module you want:</span></span></p></li>
</ol>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c89c-163">App-v コンポーネント</span><span class="sxs-lookup"><span data-stu-id="7c89c-163">App-V component</span></span></th>
<th align="left"><span data-ttu-id="7c89c-164">入力するコマンド</span><span class="sxs-lookup"><span data-stu-id="7c89c-164">Command to type</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-165">App-v Server</span><span class="sxs-lookup"><span data-stu-id="7c89c-165">App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-166">更新-ヘルプ-モジュール AppvServer</span><span class="sxs-lookup"><span data-stu-id="7c89c-166">Update-Help -Module AppvServer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c89c-167">App-v Sequencer</span><span class="sxs-lookup"><span data-stu-id="7c89c-167">App-V Sequencer</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-168">更新-ヘルプ-モジュール AppvSequencer</span><span class="sxs-lookup"><span data-stu-id="7c89c-168">Update-Help -Module AppvSequencer</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c89c-169">App-v クライアント</span><span class="sxs-lookup"><span data-stu-id="7c89c-169">App-V Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-170">更新-ヘルプ-モジュール AppvClient</span><span class="sxs-lookup"><span data-stu-id="7c89c-170">Update-Help -Module AppvClient</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c89c-171">Web ページとしての TechNet の場合</span><span class="sxs-lookup"><span data-stu-id="7c89c-171">On TechNet as web pages</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c89c-172">「 <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)"> Windows PowerShell での Microsoft デスクトップ最適化パックオートメーション」の下の [App-V] ノードを参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="7c89c-172">See the App-V node under <a href="https://technet.microsoft.com/library/dn520245.aspx" data-raw-source="[Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://technet.microsoft.com/library/dn520245.aspx)">Microsoft Desktop Optimization Pack Automation with Windows PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>

## <a href="" id="bkmk-display-help-cmdlet"></a><span data-ttu-id="7c89c-173">PowerShell コマンドレットのヘルプの表示</span><span class="sxs-lookup"><span data-stu-id="7c89c-173">Displaying the help for a PowerShell cmdlet</span></span>
<span data-ttu-id="7c89c-174">特定の PowerShell コマンドレットのヘルプを表示するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="7c89c-174">To display help for a specific PowerShell cmdlet:</span></span>

1.  <span data-ttu-id="7c89c-175">Windows PowerShell または Windows PowerShell Integrated Scripting Environment (ISE) を開きます。</span><span class="sxs-lookup"><span data-stu-id="7c89c-175">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="7c89c-176">「 **Get-ヘルプ** &lt; *」コマンドレット*を入力し &gt; ます。たとえば、「 **AppvClientPackage**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-176">Type **Get-Help** &lt;*cmdlet*&gt;, for example, **Get-Help Publish-AppvClientPackage**.</span></span>

<span data-ttu-id="7c89c-177">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="7c89c-177">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="7c89c-178">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="7c89c-178">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="7c89c-179">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="7c89c-179">Got an App-V issue?</span></span>** <span data-ttu-id="7c89c-180">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="7c89c-180">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

 

 





