---
title: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法
description: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813915"
---
# <span data-ttu-id="0c2b1-103">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.1 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="0c2b1-103">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>


<span data-ttu-id="0c2b1-104">以下のセクションでは、PowerShell を使用して、スタンドアロンクライアントコンピューターでさまざまな管理タスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-104">The following sections explain how to perform various management tasks on a stand-alone client computer by using PowerShell:</span></span>

-   [<span data-ttu-id="0c2b1-105">パッケージの一覧を返すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-105">To return a list of packages</span></span>](#bkmk-return-pkgs-standalone-posh)

-   [<span data-ttu-id="0c2b1-106">パッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-106">To add a package</span></span>](#bkmk-add-pkgs-standalone-posh)

-   [<span data-ttu-id="0c2b1-107">パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-107">To publish a package</span></span>](#bkmk-pub-pkg-standalone-posh)

-   [<span data-ttu-id="0c2b1-108">パッケージを特定のユーザーに発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-108">To publish a package to a specific user</span></span>](#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="0c2b1-109">パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-109">To add and publish a package</span></span>](#bkmk-add-pub-pkg-standalone-posh)

-   [<span data-ttu-id="0c2b1-110">既存のパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-110">To unpublish an existing package</span></span>](#bkmk-unpub-pkg-standalone-posh)

-   [<span data-ttu-id="0c2b1-111">特定のユーザーに対してパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-111">To unpublish a package for a specific user</span></span>](#bkmk-unpub-pkg-specfc-use)

-   [<span data-ttu-id="0c2b1-112">既存のパッケージを削除するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-112">To remove an existing package</span></span>](#bkmk-remove-pkg-standalone-posh)

-   [<span data-ttu-id="0c2b1-113">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-113">To enable only administrators to publish or unpublish packages</span></span>](#bkmk-admins-pub-pkgs)

-   [<span data-ttu-id="0c2b1-114">保留中のパッケージについて (UserPending および GlobalPending)</span><span class="sxs-lookup"><span data-stu-id="0c2b1-114">Understanding pending packages (UserPending and GlobalPending)</span></span>](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a><span data-ttu-id="0c2b1-115">パッケージの一覧を返すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-115">To return a list of packages</span></span>


<span data-ttu-id="0c2b1-116">特定のユーザーに与えられているパッケージの一覧を返すには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-116">Use the following information to return a list of packages that are entitled to a specific user:</span></span>

<span data-ttu-id="0c2b1-117">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-117">**Cmdlet**: Get-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-118">**パラメーター**:-Name-バージョン-PackageID-VersionID</span><span class="sxs-lookup"><span data-stu-id="0c2b1-118">**Parameters**: -Name -Version -PackageID -VersionID</span></span>

<span data-ttu-id="0c2b1-119">**例**: AppvClientPackage – Name "ContosoApplication"-バージョン2</span><span class="sxs-lookup"><span data-stu-id="0c2b1-119">**Example**: Get-AppvClientPackage –Name “ContosoApplication” -Version 2</span></span>

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a><span data-ttu-id="0c2b1-120">パッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-120">To add a package</span></span>


<span data-ttu-id="0c2b1-121">パッケージをコンピューターに追加するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-121">Use the following information to add a package to a computer.</span></span>

<span data-ttu-id="0c2b1-122">**重要** この例では、パッケージのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-122">**Important** This example only adds a package.</span></span> <span data-ttu-id="0c2b1-123">パッケージはユーザーまたはコンピューターに発行されません。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-123">It does not publish the package to the user or the computer.</span></span>

 

<span data-ttu-id="0c2b1-124">**コマンドレット**: Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-124">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-125">**例**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span><span class="sxs-lookup"><span data-stu-id="0c2b1-125">**Example**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span></span>

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a><span data-ttu-id="0c2b1-126">パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-126">To publish a package</span></span>


<span data-ttu-id="0c2b1-127">特定のユーザーに追加された、またはコンピューター上のすべてのユーザーに対してグローバルに追加されたパッケージを公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-127">Use the following information to publish a package that has been added to a specific user or globally to any user on the computer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c2b1-128">公開方法</span><span class="sxs-lookup"><span data-stu-id="0c2b1-128">Publishing method</span></span></th>
<th align="left"><span data-ttu-id="0c2b1-129">コマンドレットと例</span><span class="sxs-lookup"><span data-stu-id="0c2b1-129">Cmdlet and example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c2b1-130">ユーザーへの公開</span><span class="sxs-lookup"><span data-stu-id="0c2b1-130">Publishing to the user</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="0c2b1-131">コマンドレット </strong> : Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-131">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="0c2b1-132">例 </strong> : Publish-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="0c2b1-132">Example</strong>: Publish-AppvClientPackage “ContosoApplication”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c2b1-133">グローバルに公開する</span><span class="sxs-lookup"><span data-stu-id="0c2b1-133">Publishing globally</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="0c2b1-134">コマンドレット </strong> : Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-134">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="0c2b1-135">例 </strong> : Publish-AppvClientPackage "ContosoApplication"-グローバル</span><span class="sxs-lookup"><span data-stu-id="0c2b1-135">Example</strong>: Publish-AppvClientPackage “ContosoApplication” -Global</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a><span data-ttu-id="0c2b1-136">パッケージを特定のユーザーに発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-136">To publish a package to a specific user</span></span>


<span data-ttu-id="0c2b1-137">**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-137">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="0c2b1-138">管理者は、 **AppvClientPackage**コマンドレットでオプションの**UserSID**パラメーターを指定して、特定のユーザーにパッケージを発行できます。このパラメーターは、エンドユーザーのセキュリティ識別子 (SID)**を表します**。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-138">An administrator can publish a package to a specific user by specifying the optional **–UserSID** parameter with the **Publish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="0c2b1-139">このパラメーターを使用するには:</span><span class="sxs-lookup"><span data-stu-id="0c2b1-139">To use this parameter:</span></span>

-   <span data-ttu-id="0c2b1-140">このコマンドレットは、ユーザーまたは管理者セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-140">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="0c2b1-141">パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-141">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="0c2b1-142">エンドユーザーはログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-142">The end user must be logged in.</span></span>

-   <span data-ttu-id="0c2b1-143">エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-143">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="0c2b1-144">**コマンドレット**: Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-144">**Cmdlet**: Publish-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-145">**例**: Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="0c2b1-145">**Example**: Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a><span data-ttu-id="0c2b1-146">パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-146">To add and publish a package</span></span>


<span data-ttu-id="0c2b1-147">パッケージをコンピューターに追加してユーザーに公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-147">Use the following information to add a package to a computer and publish it to the user.</span></span>

<span data-ttu-id="0c2b1-148">**コマンドレット**: Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-148">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-149">**例**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-149">**Example**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv | Publish-AppvClientPackage</span></span>

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a><span data-ttu-id="0c2b1-150">既存のパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-150">To unpublish an existing package</span></span>


<span data-ttu-id="0c2b1-151">次の情報を使用して、ユーザーに資格があり、コンピューターからパッケージを削除しないパッケージの発行を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-151">Use the following information to unpublish a package which has been entitled to a user but not remove the package from the computer.</span></span>

<span data-ttu-id="0c2b1-152">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-152">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-153">**例**: AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="0c2b1-153">**Example**: Unpublish-AppvClientPackage “ContosoApplication”</span></span>

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a><span data-ttu-id="0c2b1-154">特定のユーザーに対してパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-154">To unpublish a package for a specific user</span></span>


<span data-ttu-id="0c2b1-155">**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-155">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="0c2b1-156">管理者は、オプション **– usersid**パラメーターとして**AppvClientPackage**コマンドレットを使用して、特定のユーザーのパッケージの発行を取り下げることができます。ここで、 **-UserSID**はエンドユーザーのセキュリティ識別子 (SID) を表します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-156">An administrator can unpublish a package for a specific user by using the optional **–UserSID** parameter with the **Unpublish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="0c2b1-157">このパラメーターを使用するには:</span><span class="sxs-lookup"><span data-stu-id="0c2b1-157">To use this parameter:</span></span>

-   <span data-ttu-id="0c2b1-158">このコマンドレットは、ユーザーまたは管理者セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-158">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="0c2b1-159">パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-159">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="0c2b1-160">エンドユーザーはログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-160">The end user must be logged in.</span></span>

-   <span data-ttu-id="0c2b1-161">エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-161">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="0c2b1-162">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-162">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-163">**例**: AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="0c2b1-163">**Example**: Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a><span data-ttu-id="0c2b1-164">既存のパッケージを削除するには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-164">To remove an existing package</span></span>


<span data-ttu-id="0c2b1-165">コンピューターからパッケージを削除するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-165">Use the following information to remove a package from the computer.</span></span>

<span data-ttu-id="0c2b1-166">**コマンドレット**: Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="0c2b1-166">**Cmdlet**: Remove-AppvClientPackage</span></span>

<span data-ttu-id="0c2b1-167">**例**: Remove-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="0c2b1-167">**Example**: Remove-AppvClientPackage “ContosoApplication”</span></span>

<span data-ttu-id="0c2b1-168">**注** アプリ-V コマンドレットは、わかりやすくするために、前の例の変数に割り当てられています。課題は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-168">**Note** App-V cmdlets have been assigned to variables for the previous examples for clarity only; assignment is not a requirement.</span></span> <span data-ttu-id="0c2b1-169">[パッケージを追加して公開するに](#bkmk-add-pub-pkg-standalone-posh)は、ほとんどのコマンドレットをに示されているように組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-169">Most cmdlets can be combined as displayed in [To add and publish a package](#bkmk-add-pub-pkg-standalone-posh).</span></span> <span data-ttu-id="0c2b1-170">詳細なチュートリアルについては、「 [app-v 5.0 クライアント PowerShell (詳細](https://go.microsoft.com/fwlink/?LinkId=324466))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-170">For a detailed tutorial, see [App-V 5.0 Client PowerShell Deep Dive](https://go.microsoft.com/fwlink/?LinkId=324466).</span></span>

 

## <a href="" id="bkmk-admins-pub-pkgs"></a><span data-ttu-id="0c2b1-171">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="0c2b1-171">To enable only administrators to publish or unpublish packages</span></span>


<span data-ttu-id="0c2b1-172">**注** 
**この機能は、app-v 5.0 SP3 以降でサポートされています。**</span><span class="sxs-lookup"><span data-stu-id="0c2b1-172">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="0c2b1-173">次のコマンドレットとパラメーターを使用して、(エンドユーザーではなく) 管理者のみがパッケージを公開または非公開にすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-173">Use the following cmdlet and parameter to enable only administrators (not end users) to publish or unpublish packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="0c2b1-174">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="0c2b1-174">Cmdlet</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-175">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="0c2b1-175">Set-AppvClientConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="0c2b1-176">パラメーター</span><span class="sxs-lookup"><span data-stu-id="0c2b1-176">Parameter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-177">-RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="0c2b1-177">-RequirePublishAsAdmin</span></span></p>
<p><span data-ttu-id="0c2b1-178">パラメーターの値:</span><span class="sxs-lookup"><span data-stu-id="0c2b1-178">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c2b1-179">0-偽</span><span class="sxs-lookup"><span data-stu-id="0c2b1-179">0 - False</span></span></p></li>
<li><p><span data-ttu-id="0c2b1-180">1-True</span><span class="sxs-lookup"><span data-stu-id="0c2b1-180">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="0c2b1-181">例: </strong> AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="0c2b1-181">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0c2b1-182">App-v 管理コンソールを使ってこの構成を設定する方法については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-182">To use the App-V Management console to set this configuration, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

## <a href="" id="bkmk-understd-pend-pkgs"></a><span data-ttu-id="0c2b1-183">保留中のパッケージについて (UserPending および GlobalPending)</span><span class="sxs-lookup"><span data-stu-id="0c2b1-183">Understanding pending packages (UserPending and GlobalPending)</span></span>


<span data-ttu-id="0c2b1-184">**App-v 5.0 SP2 以降**: 現在使用されているパッケージに影響を与える PowerShell コマンドレットを実行すると、実行しようとしているタスクは保留中の状態に置かれます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-184">**Starting in App-V 5.0 SP2**: If you run a PowerShell cmdlet that affects a package that is currently in use, the task that you are trying to perform is placed in a pending state.</span></span> <span data-ttu-id="0c2b1-185">たとえば、パッケージ内のアプリケーションを使っているときにパッケージを公開しようとした場合、 **AppvClientPackage**を実行すると、次のように、コマンドレットの出力に保留状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-185">For example, if you try to publish a package when an application in that package is being used, and then run **Get-AppvClientPackage**, the pending status appears in the cmdlet output as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c2b1-186">コマンドレットの出力項目</span><span class="sxs-lookup"><span data-stu-id="0c2b1-186">Cmdlet output item</span></span></th>
<th align="left"><span data-ttu-id="0c2b1-187">説明</span><span class="sxs-lookup"><span data-stu-id="0c2b1-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c2b1-188">UserPending</span><span class="sxs-lookup"><span data-stu-id="0c2b1-188">UserPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-189">表示されているパッケージに、ユーザーに適用されている保留中のタスクがあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-189">Indicates whether the listed package has a pending task that is being applied to the user:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c2b1-190">True</span><span class="sxs-lookup"><span data-stu-id="0c2b1-190">True</span></span></p></li>
<li><p><span data-ttu-id="0c2b1-191">False</span><span class="sxs-lookup"><span data-stu-id="0c2b1-191">False</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c2b1-192">GlobalPending</span><span class="sxs-lookup"><span data-stu-id="0c2b1-192">GlobalPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-193">表示されているパッケージに、コンピューターにグローバルに適用される保留中のタスクが含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-193">Indicates whether the listed package has a pending task that is being applied globally to the computer:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c2b1-194">True</span><span class="sxs-lookup"><span data-stu-id="0c2b1-194">True</span></span></p></li>
<li><p><span data-ttu-id="0c2b1-195">False</span><span class="sxs-lookup"><span data-stu-id="0c2b1-195">False</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0c2b1-196">保留中のタスクは、次のルールに従って後で実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-196">The pending task will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0c2b1-197">タスクの種類</span><span class="sxs-lookup"><span data-stu-id="0c2b1-197">Task type</span></span></th>
<th align="left"><span data-ttu-id="0c2b1-198">該当するルール</span><span class="sxs-lookup"><span data-stu-id="0c2b1-198">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0c2b1-199">ユーザーベースのタスク (パッケージをユーザーに公開するなど)</span><span class="sxs-lookup"><span data-stu-id="0c2b1-199">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-200">保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-200">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0c2b1-201">グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</span><span class="sxs-lookup"><span data-stu-id="0c2b1-201">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="0c2b1-202">保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-202">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0c2b1-203">保留中のタスクの詳細については、「 [app-v 5.0 SP2 につい](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-203">For more information about pending tasks, see [About App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks).</span></span>

<span data-ttu-id="0c2b1-204">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-204">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="0c2b1-205">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-205">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="0c2b1-206">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="0c2b1-206">Got an App-V issue?</span></span>** <span data-ttu-id="0c2b1-207">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="0c2b1-207">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="0c2b1-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0c2b1-208">Related topics</span></span>


[<span data-ttu-id="0c2b1-209">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="0c2b1-209">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="0c2b1-210">PowerShell を使用した App-V 5.1 の管理</span><span class="sxs-lookup"><span data-stu-id="0c2b1-210">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





