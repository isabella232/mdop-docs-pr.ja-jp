---
title: 接続グループでオプション パッケージを使用する方法
description: 接続グループでオプション パッケージを使用する方法
author: dansimp
ms.assetid: 4d08a81b-55e5-471a-91dc-9a684fb3c9a1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 64a2c0758294bfa617d3d85f888cfce3a2c0d21e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813634"
---
# <span data-ttu-id="17d04-103">接続グループでオプション パッケージを使用する方法</span><span class="sxs-lookup"><span data-stu-id="17d04-103">How to Use Optional Packages in Connection Groups</span></span>


<span data-ttu-id="17d04-104">Microsoft Application Virtualization (App-v) 5.0 SP3 以降では、接続グループにオプションのパッケージを追加して、接続グループの管理を簡単にすることができます。</span><span class="sxs-lookup"><span data-stu-id="17d04-104">Starting in Microsoft Application Virtualization (App-V) 5.0 SP3, you can add optional packages to your connection groups to simplify connection group management.</span></span> <span data-ttu-id="17d04-105">次の表は、オプションのパッケージを使用して作業をより簡単に完了できるタスクをまとめたものです。各タスクの手順へのリンクが用意されています。</span><span class="sxs-lookup"><span data-stu-id="17d04-105">The following table summarizes the tasks that you can complete more easily by using optional packages, and provides links to instructions for each task.</span></span>

<span data-ttu-id="17d04-106">**注** 
**省略可能なパッケージは、app-v 5.0 SP3 でのみサポートされます。**</span><span class="sxs-lookup"><span data-stu-id="17d04-106">**Note**
**Optional packages are supported only in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="17d04-107">オプションのパッケージを使用する前に、「[接続グループでオプションパッケージを使用するための要件](#bkmk-reqs-using-cg)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17d04-107">Before using optional packages, see [Requirements for using optional packages in connection groups](#bkmk-reqs-using-cg).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-108">手順へのリンク</span><span class="sxs-lookup"><span data-stu-id="17d04-108">Link to instructions</span></span></th>
<th align="left"><span data-ttu-id="17d04-109">タスク</span><span class="sxs-lookup"><span data-stu-id="17d04-109">Task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)"><span data-ttu-id="17d04-110">異なるパッケージを持つ複数のユーザーに対して、オプションのパッケージと共に1つの接続グループを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d04-110">Use one connection group, with optional packages, for multiple users who have different packages entitled to them</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="17d04-111">単一の接続グループを使用して、さまざまなエンドユーザーが使用できるアプリケーションとプラグインのグループを作成します。</span><span class="sxs-lookup"><span data-stu-id="17d04-111">Use a single connection group to make different groups of applications and plug-ins available to different end users.</span></span></p>
<p><span data-ttu-id="17d04-112">たとえば、すべてのエンドユーザーに Microsoft Office を配布する必要がありますが、さまざまなユーザーのサブセットにさまざまなプラグインを配布します。</span><span class="sxs-lookup"><span data-stu-id="17d04-112">For example, you want to distribute Microsoft Office to all end users, but distribute different plug-ins to different subsets of users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)"><span data-ttu-id="17d04-113">省略可能なパッケージを非公開にする、または削除する、またはオプションのパッケージを公開し、後で再公開する (接続グループを変更しない)</span><span class="sxs-lookup"><span data-stu-id="17d04-113">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="17d04-114">App-v クライアントで接続グループを無効にしたり、削除したり、追加したり、再度有効にしたりすることなく、省略可能なパッケージを公開、削除、または再公開します。</span><span class="sxs-lookup"><span data-stu-id="17d04-114">Unpublish, delete, or republish an optional package without having to disable, remove, edit, add, and re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="17d04-115">また、オプションパッケージの発行を停止し、後で再公開することもできます。これにより、接続グループを無効にしたり、再公開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17d04-115">You can also unpublish the optional package and republish it later without having to disable or republish the connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a><span data-ttu-id="17d04-116">異なるパッケージを持つ複数のユーザーに対して、オプションのパッケージと共に1つの接続グループを使用する</span><span class="sxs-lookup"><span data-stu-id="17d04-116">Use one connection group, with optional packages, for multiple users with different packages entitled to them</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-117">タスクの説明</span><span class="sxs-lookup"><span data-stu-id="17d04-117">Task description</span></span></th>
<th align="left"><span data-ttu-id="17d04-118">タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="17d04-118">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="17d04-119">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="17d04-119">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="17d04-120">オプションのパッケージを接続グループに追加することができます。これにより、アプリケーションとプラグインのさまざまな組み合わせをさまざまなエンドユーザーに提供できます。</span><span class="sxs-lookup"><span data-stu-id="17d04-120">You can add optional packages to connection groups, which enables you to provide different combinations of applications and plug-ins to different end users.</span></span></p>
<p><strong><span data-ttu-id="17d04-121">例 </strong> : Microsoft Office をエンドユーザーに配布し、一部のユーザーのみに対して特定のプラグインを有効にします。</span><span class="sxs-lookup"><span data-stu-id="17d04-121">Example</strong>: You want to distribute Microsoft Office to your end users, but enable a certain plug-in for only a subset of users.</span></span></p>
<p><span data-ttu-id="17d04-122">これを行うには、Office のパッケージと、Office プラグインを含む別のパッケージを含む接続グループを作成し、プラグインパッケージをオプションにします。</span><span class="sxs-lookup"><span data-stu-id="17d04-122">To do this, create a connection group that contains a package with Office, and another package with Office plug-ins, and then make the plug-ins package optional.</span></span></p>
<p><span data-ttu-id="17d04-123">プラグインパッケージに対応していないエンドユーザーは、引き続き Office を実行することができます。</span><span class="sxs-lookup"><span data-stu-id="17d04-123">End users who are not entitled to the plug-in package will still be able to run Office.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-124">メソッド</span><span class="sxs-lookup"><span data-stu-id="17d04-124">Method</span></span></th>
<th align="left"><span data-ttu-id="17d04-125">手順</span><span class="sxs-lookup"><span data-stu-id="17d04-125">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17d04-126">App-v Server –管理コンソール</span><span class="sxs-lookup"><span data-stu-id="17d04-126">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="17d04-127">管理コンソールで、[パッケージ] を選択し <strong> </strong> て [パッケージ] ページを開きます。</span><span class="sxs-lookup"><span data-stu-id="17d04-127">In the Management Console, select <strong>PACKAGES</strong> to open the PACKAGES page.</span></span></p></li>
<li><p><span data-ttu-id="17d04-128">[接続グループ] を選択し <strong> </strong> て、接続グループライブラリを表示します。</span><span class="sxs-lookup"><span data-stu-id="17d04-128">Select <strong>CONNECTION GROUPS</strong> to display the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="17d04-129">接続グループライブラリから適切な接続グループを選択します。</span><span class="sxs-lookup"><span data-stu-id="17d04-129">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="17d04-130">[ <strong> </strong> 接続されているパッケージ] ウィンドウで [編集] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="17d04-130">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="17d04-131"><strong> </strong> パッケージ名の横にある [オプション] を選択します。</span><span class="sxs-lookup"><span data-stu-id="17d04-131">Select <strong>Optional</strong> next to the package name.</span></span></p></li>
<li><p><span data-ttu-id="17d04-132">[ <strong> パッケージアクセスをグループアクセスに追加する] チェックボックスをオンにし </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17d04-132">Select the <strong>ADD PACKAGE ACCESS TO GROUP ACCESS</strong> check box.</span></span> <span data-ttu-id="17d04-133">この必須の手順は、Active Directory グループにパッケージを割り当てたときに、以前に構成したパッケージの権利を接続グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="17d04-133">This required step adds to the connection group the package entitlements that you configured earlier when you assigned packages to Active Directory groups.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17d04-134">App-v Server-PowerShell コマンドレット</span><span class="sxs-lookup"><span data-stu-id="17d04-134">App-V Server - PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="17d04-135">次のコマンドレットを使用して、 <strong> -オプションパラメーターを指定し </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17d04-135">Use the following cmdlet, and specify the <strong>-Optional</strong> parameter:</span></span></p>
<p><strong><span data-ttu-id="17d04-136">Add-AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="17d04-136">Add-AppvServerConnectionGroupPackage</span></span></strong></p>
<p><strong><span data-ttu-id="17d04-137">引数</span><span class="sxs-lookup"><span data-stu-id="17d04-137">Syntax:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong><span data-ttu-id="17d04-138">例:</span><span class="sxs-lookup"><span data-stu-id="17d04-138">Example:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17d04-139">スタンドアロンコンピューター上の app-v クライアント</span><span class="sxs-lookup"><span data-stu-id="17d04-139">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="17d04-140">接続グループ XML ドキュメントを作成し、 <strong> Package </strong> tag 属性を <strong> </strong> <strong> "true" に設定します。</span><span class="sxs-lookup"><span data-stu-id="17d04-140">Create the connection group XML document, and set the <strong>Package</strong> tag attribute <strong>IsOptional</strong> to <strong>“true”.</span></span></strong></p></li>
<li><p><span data-ttu-id="17d04-141">次のコマンドレットを使用して、接続グループを追加して有効にします。</span><span class="sxs-lookup"><span data-stu-id="17d04-141">Use the following cmdlets to add and enable the connection group:</span></span></p>
<ul>
<li><p><span data-ttu-id="17d04-142">Add-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="17d04-142">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="17d04-143">Enable-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="17d04-143">Enable-AppvClientConnectionGroup</span></span></p></li>
</ul></li>
</ol>
<p><strong><span data-ttu-id="17d04-144">オプションのパッケージを含む接続グループ XML ドキュメントの例:</span><span class="sxs-lookup"><span data-stu-id="17d04-144">Example connection group XML document with optional packages:</span></span></strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="17d04-145">App-v 5.0 SP3 より前のバージョンの場合</span><span class="sxs-lookup"><span data-stu-id="17d04-145">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="17d04-146">特定のアプリケーションとプラグインの組み合わせを特定のユーザーが利用できるようにするには、複数の接続グループを作成する必要がありました。</span><span class="sxs-lookup"><span data-stu-id="17d04-146">You had to create many connection groups to make specific application and plug-in combinations available to specific users.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a><span data-ttu-id="17d04-147">省略可能なパッケージを非公開にする、または削除する、またはオプションのパッケージを公開し、後で再公開する (接続グループを変更しない)</span><span class="sxs-lookup"><span data-stu-id="17d04-147">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-148">タスクの説明</span><span class="sxs-lookup"><span data-stu-id="17d04-148">Task description</span></span></th>
<th align="left"><span data-ttu-id="17d04-149">タスクを実行する方法</span><span class="sxs-lookup"><span data-stu-id="17d04-149">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="17d04-150">App-v 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="17d04-150">With App-V 5.0 SP3</span></span></strong></p>
<p><span data-ttu-id="17d04-151">接続グループ内の省略可能なパッケージの公開取り消し、削除、または再公開を行うことができます。これは、App-v クライアントで接続グループを無効にするか、再び有効にする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17d04-151">You can unpublish, delete, or republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="17d04-152">また、オプションのパッケージを非公開にし、後で再公開することもできます。これにより、接続グループを無効にしたり、再公開する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17d04-152">You can also unpublish an optional package and republish it later without having to disable or republish the connection group.</span></span></p>
<p><strong><span data-ttu-id="17d04-153">例 </strong> : Microsoft Office プラグインを含むオプションのパッケージを公開し、プラグインを削除したい場合は、接続グループを無効にすることなく、パッケージの発行を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="17d04-153">Example</strong>: If you publish an optional package that contains a Microsoft Office plug-in, and you want to remove the plug-in, you can unpublish the package without having to disable the connection group.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-154">メソッド</span><span class="sxs-lookup"><span data-stu-id="17d04-154">Method</span></span></th>
<th align="left"><span data-ttu-id="17d04-155">手順</span><span class="sxs-lookup"><span data-stu-id="17d04-155">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17d04-156">App-v Server –管理コンソール</span><span class="sxs-lookup"><span data-stu-id="17d04-156">App-V Server – Management Console</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="17d04-157">パッケージの発行を取り消すには: 管理コンソールで [パッケージの選択] ページを選び <strong> </strong> 、発行を取り消すパッケージを右クリックして、[発行の取り消し] をクリックし <strong> </strong> ます。</span><span class="sxs-lookup"><span data-stu-id="17d04-157">To unpublish the package: In the Management Console, select elect the <strong>PACKAGES</strong> page, right-click the package that you want to unpublish, and click <strong>unpublish</strong>.</span></span></p></li>
<li><p><span data-ttu-id="17d04-158">接続グループからオプションのパッケージを削除するには: [ <strong> 接続グループ </strong> ] ページで、削除するパッケージを選択し、右矢印をクリックして、左下の [接続] グループウィンドウからパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="17d04-158">To remove an optional package from a connection group: On the <strong>CONNECTION GROUPS</strong> page, select the package that you want to remove, and click the right arrow to remove the package from the connection group pane on the bottom left.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17d04-159">スタンドアロンコンピューター上の app-v クライアント</span><span class="sxs-lookup"><span data-stu-id="17d04-159">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="17d04-160">次の既存のコマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="17d04-160">Use the following existing cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="17d04-161">未発行-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="17d04-161">Unpublish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="17d04-162">Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="17d04-162">Remove-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="17d04-163">詳細については、「 <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> PowerShell を使用してスタンドアロンコンピューターで実行されている app-v 5.0 パッケージを管理する方法」を参照してください </a> 。</span><span class="sxs-lookup"><span data-stu-id="17d04-163">For more information, see <a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="17d04-164">App-v 5.0 SP3 より前のバージョンの場合</span><span class="sxs-lookup"><span data-stu-id="17d04-164">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="17d04-165">次のことを行う必要がありました。</span><span class="sxs-lookup"><span data-stu-id="17d04-165">You had to:</span></span></p>
<ol>
<li><p><span data-ttu-id="17d04-166">有効になっている各 App-v クライアントコンピューターから接続グループを削除します。</span><span class="sxs-lookup"><span data-stu-id="17d04-166">Remove the connection group from each App-V Client computer where it was enabled.</span></span></p></li>
<li><p><span data-ttu-id="17d04-167">パッケージの発行を停止します。</span><span class="sxs-lookup"><span data-stu-id="17d04-167">Unpublish the package.</span></span></p></li>
<li><p><span data-ttu-id="17d04-168">接続グループの定義からパッケージを削除します。</span><span class="sxs-lookup"><span data-stu-id="17d04-168">Remove the package from the connection group’s definition.</span></span></p></li>
<li><p><span data-ttu-id="17d04-169">接続グループを再公開します。</span><span class="sxs-lookup"><span data-stu-id="17d04-169">Republish the connection group.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a><span data-ttu-id="17d04-170">接続グループでオプションのパッケージを使用するための要件</span><span class="sxs-lookup"><span data-stu-id="17d04-170">Requirements for using optional packages in connection groups</span></span>


<span data-ttu-id="17d04-171">接続グループでオプションのパッケージを使用する前に、次の要件を確認します。</span><span class="sxs-lookup"><span data-stu-id="17d04-171">Review the following requirements before using optional packages in connection groups:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17d04-172">要件</span><span class="sxs-lookup"><span data-stu-id="17d04-172">Requirement</span></span></th>
<th align="left"><span data-ttu-id="17d04-173">詳細</span><span class="sxs-lookup"><span data-stu-id="17d04-173">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17d04-174">接続グループには、オプション以外のパッケージが少なくとも1つ含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17d04-174">Connection groups must contain at least one non-optional package.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="17d04-175">この要件を満たしていることを確認します。これは、App-v Server と PowerShell コマンドレットで、要件が満たされていることを検証しないことを確認してください。</span><span class="sxs-lookup"><span data-stu-id="17d04-175">Check carefully that you meet this requirement, as the App-V Server and the PowerShell cmdlet don’t validate that the requirement has been met.</span></span></p></li>
<li><p><span data-ttu-id="17d04-176">1つ以上の省略可能なパッケージが含まれていない接続グループを誤って作成した場合、エンドユーザーがその接続グループでパッケージ化されたアプリケーションを開こうとすると、接続グループは失敗します。</span><span class="sxs-lookup"><span data-stu-id="17d04-176">If you accidentally create a connection group that does not contain at least one non-optional package, and the end user tries to open a packaged application in that connection group, the connection group will fail.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="17d04-177">ユーザーに公開された接続グループには、グローバルに、またはユーザーに公開されるパッケージを含めることができます。</span><span class="sxs-lookup"><span data-stu-id="17d04-177">User-published connection groups can contain packages that are published globally or to the user.</span></span></p></li>
<li><p><span data-ttu-id="17d04-178">グローバルに公開された接続グループには、グローバルに公開されたパッケージのみを含める必要があります</span><span class="sxs-lookup"><span data-stu-id="17d04-178">Globally published connection groups must contain only globally published packages.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="17d04-179">グローバルに公開された接続グループには、接続グループの仮想環境を開始するときにパッケージが利用できるようにするためにグローバルに公開されるパッケージが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="17d04-179">Globally published connection groups must contain packages that are published globally to ensure that the packages will be available when starting the connection group’s virtual environment.</span></span></p>
<p><span data-ttu-id="17d04-180">ユーザーが公開したパッケージを含むグローバルに公開された接続グループを追加または有効にしようとしても、接続グループは失敗します。</span><span class="sxs-lookup"><span data-stu-id="17d04-180">If you try to add or enable globally published connection groups that contain user-published packages, the connection group will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17d04-181">これらのパッケージを含む接続グループを公開する前に、省略可能なすべてのパッケージを公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17d04-181">You must publish all non-optional packages before publishing the connection group that contains those packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="17d04-182">接続グループの仮想環境は、省略可能なパッケージが見つからない場合は開始できません。</span><span class="sxs-lookup"><span data-stu-id="17d04-182">A connection group’s virtual environment cannot start if any non-optional packages are missing.</span></span></p>
<p><span data-ttu-id="17d04-183">オプション以外のパッケージが公開されていない場合、App-v クライアントは、接続グループの追加または有効化に失敗します。</span><span class="sxs-lookup"><span data-stu-id="17d04-183">The App-V Client fails to add or enable a connection group if any non-optional packages have not been published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="17d04-184">グローバルに公開されたパッケージを公開する前に、そのコンピューター上のすべてのユーザーに与えられている接続グループが、パッケージを必要としなくなったことを確認します。</span><span class="sxs-lookup"><span data-stu-id="17d04-184">Before you unpublish a globally published package, ensure that the connection groups that are entitled to all the users on that computer no longer require the package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="17d04-185">パッケージが別のユーザーの接続グループの一部であるかどうかは、システムによって確認されません。</span><span class="sxs-lookup"><span data-stu-id="17d04-185">The system does not check whether the package is part of another user’s connection group.</span></span> <span data-ttu-id="17d04-186">グローバルパッケージの発行を解除すると、そのコンピューター上のすべてのユーザーが使用できなくなります。そのため、各ユーザーの接続グループにパッケージが含まれていないことを確認するか、パッケージをオプションにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="17d04-186">Unpublishing a global package will make it unavailable to every user on that computer, so make sure that each user’s connection groups no longer contain the package, or alternatively make the package optional.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="17d04-187">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17d04-187">Related topics</span></span>


[<span data-ttu-id="17d04-188">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="17d04-188">Managing Connection Groups</span></span>](managing-connection-groups.md)

 

 





