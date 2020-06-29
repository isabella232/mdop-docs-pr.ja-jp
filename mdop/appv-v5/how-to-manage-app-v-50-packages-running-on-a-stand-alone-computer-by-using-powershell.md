---
title: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法
description: PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法
author: dansimp
ms.assetid: 1d6c2d25-81ec-4ff8-9262-6b4cf484a376
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b7af1781a7a443a4fcfc8e7d4a92525b34986763
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813922"
---
# <span data-ttu-id="a830f-103">PowerShell を使用してスタンドアロン コンピューターで実行されている App-V 5.0 パッケージを管理する方法</span><span class="sxs-lookup"><span data-stu-id="a830f-103">How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>


<span data-ttu-id="a830f-104">以下のセクションでは、PowerShell を使用して、スタンドアロンクライアントコンピューターでさまざまな管理タスクを実行する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="a830f-104">The following sections explain how to perform various management tasks on a stand-alone client computer by using PowerShell:</span></span>

-   [<span data-ttu-id="a830f-105">パッケージの一覧を返すには</span><span class="sxs-lookup"><span data-stu-id="a830f-105">To return a list of packages</span></span>](#bkmk-return-pkgs-standalone-posh)

-   [<span data-ttu-id="a830f-106">パッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="a830f-106">To add a package</span></span>](#bkmk-add-pkgs-standalone-posh)

-   [<span data-ttu-id="a830f-107">パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-107">To publish a package</span></span>](#bkmk-pub-pkg-standalone-posh)

-   [<span data-ttu-id="a830f-108">パッケージを特定のユーザーに発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-108">To publish a package to a specific user</span></span>](#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="a830f-109">パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-109">To add and publish a package</span></span>](#bkmk-add-pub-pkg-standalone-posh)

-   [<span data-ttu-id="a830f-110">既存のパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="a830f-110">To unpublish an existing package</span></span>](#bkmk-unpub-pkg-standalone-posh)

-   [<span data-ttu-id="a830f-111">特定のユーザーに対してパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="a830f-111">To unpublish a package for a specific user</span></span>](#bkmk-unpub-pkg-specfc-use)

-   [<span data-ttu-id="a830f-112">既存のパッケージを削除するには</span><span class="sxs-lookup"><span data-stu-id="a830f-112">To remove an existing package</span></span>](#bkmk-remove-pkg-standalone-posh)

-   [<span data-ttu-id="a830f-113">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="a830f-113">To enable only administrators to publish or unpublish packages</span></span>](#bkmk-admins-pub-pkgs)

-   [<span data-ttu-id="a830f-114">保留中のパッケージについて (UserPending および GlobalPending)</span><span class="sxs-lookup"><span data-stu-id="a830f-114">Understanding pending packages (UserPending and GlobalPending)</span></span>](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a><span data-ttu-id="a830f-115">パッケージの一覧を返すには</span><span class="sxs-lookup"><span data-stu-id="a830f-115">To return a list of packages</span></span>


<span data-ttu-id="a830f-116">特定のユーザーに与えられているパッケージの一覧を返すには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-116">Use the following information to return a list of packages that are entitled to a specific user:</span></span>

<span data-ttu-id="a830f-117">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-117">**Cmdlet**: Get-AppvClientPackage</span></span>

<span data-ttu-id="a830f-118">**パラメーター**:-Name-バージョン-PackageID-VersionID</span><span class="sxs-lookup"><span data-stu-id="a830f-118">**Parameters**: -Name -Version -PackageID -VersionID</span></span>

<span data-ttu-id="a830f-119">**例**: AppvClientPackage – Name "ContosoApplication"-バージョン2</span><span class="sxs-lookup"><span data-stu-id="a830f-119">**Example**: Get-AppvClientPackage –Name “ContosoApplication” -Version 2</span></span>

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a><span data-ttu-id="a830f-120">パッケージを追加するには</span><span class="sxs-lookup"><span data-stu-id="a830f-120">To add a package</span></span>


<span data-ttu-id="a830f-121">パッケージをコンピューターに追加するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-121">Use the following information to add a package to a computer.</span></span>

<span data-ttu-id="a830f-122">**重要** この例では、パッケージのみが追加されます。</span><span class="sxs-lookup"><span data-stu-id="a830f-122">**Important** This example only adds a package.</span></span> <span data-ttu-id="a830f-123">パッケージはユーザーまたはコンピューターに発行されません。</span><span class="sxs-lookup"><span data-stu-id="a830f-123">It does not publish the package to the user or the computer.</span></span>

 

<span data-ttu-id="a830f-124">**コマンドレット**: Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-124">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="a830f-125">**例**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span><span class="sxs-lookup"><span data-stu-id="a830f-125">**Example**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span></span>

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a><span data-ttu-id="a830f-126">パッケージを発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-126">To publish a package</span></span>


<span data-ttu-id="a830f-127">特定のユーザーに追加された、またはコンピューター上のすべてのユーザーに対してグローバルに追加されたパッケージを公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-127">Use the following information to publish a package that has been added to a specific user or globally to any user on the computer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a830f-128">公開方法</span><span class="sxs-lookup"><span data-stu-id="a830f-128">Publishing method</span></span></th>
<th align="left"><span data-ttu-id="a830f-129">コマンドレットと例</span><span class="sxs-lookup"><span data-stu-id="a830f-129">Cmdlet and example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a830f-130">ユーザーへの公開</span><span class="sxs-lookup"><span data-stu-id="a830f-130">Publishing to the user</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="a830f-131">コマンドレット </strong> : Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-131">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="a830f-132">例 </strong> : Publish-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="a830f-132">Example</strong>: Publish-AppvClientPackage “ContosoApplication”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a830f-133">グローバルに公開する</span><span class="sxs-lookup"><span data-stu-id="a830f-133">Publishing globally</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="a830f-134">コマンドレット </strong> : Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-134">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="a830f-135">例 </strong> : Publish-AppvClientPackage "ContosoApplication"-グローバル</span><span class="sxs-lookup"><span data-stu-id="a830f-135">Example</strong>: Publish-AppvClientPackage “ContosoApplication” -Global</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a><span data-ttu-id="a830f-136">パッケージを特定のユーザーに発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-136">To publish a package to a specific user</span></span>


<span data-ttu-id="a830f-137">**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-137">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="a830f-138">管理者は、 **AppvClientPackage**コマンドレットでオプションの**UserSID**パラメーターを指定して、特定のユーザーにパッケージを発行できます。このパラメーターは、エンドユーザーのセキュリティ識別子 (SID)**を表します**。</span><span class="sxs-lookup"><span data-stu-id="a830f-138">An administrator can publish a package to a specific user by specifying the optional **–UserSID** parameter with the **Publish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="a830f-139">このパラメーターを使用するには:</span><span class="sxs-lookup"><span data-stu-id="a830f-139">To use this parameter:</span></span>

-   <span data-ttu-id="a830f-140">このコマンドレットは、ユーザーまたは管理者セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a830f-140">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="a830f-141">パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-141">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="a830f-142">エンドユーザーはログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-142">The end user must be logged in.</span></span>

-   <span data-ttu-id="a830f-143">エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-143">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="a830f-144">**コマンドレット**: Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-144">**Cmdlet**: Publish-AppvClientPackage</span></span>

<span data-ttu-id="a830f-145">**例**: Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="a830f-145">**Example**: Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a><span data-ttu-id="a830f-146">パッケージを追加して発行するには</span><span class="sxs-lookup"><span data-stu-id="a830f-146">To add and publish a package</span></span>


<span data-ttu-id="a830f-147">パッケージをコンピューターに追加してユーザーに公開するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-147">Use the following information to add a package to a computer and publish it to the user.</span></span>

<span data-ttu-id="a830f-148">**コマンドレット**: Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-148">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="a830f-149">**例**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |公開-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-149">**Example**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv | Publish-AppvClientPackage</span></span>

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a><span data-ttu-id="a830f-150">既存のパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="a830f-150">To unpublish an existing package</span></span>


<span data-ttu-id="a830f-151">次の情報を使用して、ユーザーに資格があり、コンピューターからパッケージを削除しないパッケージの発行を取り消すことができます。</span><span class="sxs-lookup"><span data-stu-id="a830f-151">Use the following information to unpublish a package which has been entitled to a user but not remove the package from the computer.</span></span>

<span data-ttu-id="a830f-152">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-152">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="a830f-153">**例**: AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="a830f-153">**Example**: Unpublish-AppvClientPackage “ContosoApplication”</span></span>

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a><span data-ttu-id="a830f-154">特定のユーザーに対してパッケージの発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="a830f-154">To unpublish a package for a specific user</span></span>


<span data-ttu-id="a830f-155">**注** このパラメーターを使用するには、App-v 5.0 SP2 ホットフィックスパッケージ5以降を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-155">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="a830f-156">管理者は、オプション **– usersid**パラメーターとして**AppvClientPackage**コマンドレットを使用して、特定のユーザーのパッケージの発行を取り下げることができます。ここで、 **-UserSID**はエンドユーザーのセキュリティ識別子 (SID) を表します。</span><span class="sxs-lookup"><span data-stu-id="a830f-156">An administrator can unpublish a package for a specific user by using the optional **–UserSID** parameter with the **Unpublish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="a830f-157">このパラメーターを使用するには:</span><span class="sxs-lookup"><span data-stu-id="a830f-157">To use this parameter:</span></span>

-   <span data-ttu-id="a830f-158">このコマンドレットは、ユーザーまたは管理者セッションから実行できます。</span><span class="sxs-lookup"><span data-stu-id="a830f-158">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="a830f-159">パラメーターを使用するには、管理者の資格情報を使ってログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-159">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="a830f-160">エンドユーザーはログインしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-160">The end user must be logged in.</span></span>

-   <span data-ttu-id="a830f-161">エンドユーザーのセキュリティ識別子 (SID) を指定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a830f-161">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="a830f-162">**コマンドレット**: AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-162">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="a830f-163">**例**: AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="a830f-163">**Example**: Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a><span data-ttu-id="a830f-164">既存のパッケージを削除するには</span><span class="sxs-lookup"><span data-stu-id="a830f-164">To remove an existing package</span></span>


<span data-ttu-id="a830f-165">コンピューターからパッケージを削除するには、次の情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-165">Use the following information to remove a package from the computer.</span></span>

<span data-ttu-id="a830f-166">**コマンドレット**: Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="a830f-166">**Cmdlet**: Remove-AppvClientPackage</span></span>

<span data-ttu-id="a830f-167">**例**: Remove-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="a830f-167">**Example**: Remove-AppvClientPackage “ContosoApplication”</span></span>

<span data-ttu-id="a830f-168">**注** アプリ-V コマンドレットは、わかりやすくするために、前の例の変数に割り当てられています。課題は必須ではありません。</span><span class="sxs-lookup"><span data-stu-id="a830f-168">**Note** App-V cmdlets have been assigned to variables for the previous examples for clarity only; assignment is not a requirement.</span></span> <span data-ttu-id="a830f-169">[パッケージを追加して公開するに](#bkmk-add-pub-pkg-standalone-posh)は、ほとんどのコマンドレットをに示されているように組み合わせることができます。</span><span class="sxs-lookup"><span data-stu-id="a830f-169">Most cmdlets can be combined as displayed in [To add and publish a package](#bkmk-add-pub-pkg-standalone-posh).</span></span> <span data-ttu-id="a830f-170">詳細なチュートリアルについては、「 [app-v 5.0 クライアント PowerShell (詳細](https://go.microsoft.com/fwlink/?LinkId=324466))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a830f-170">For a detailed tutorial, see [App-V 5.0 Client PowerShell Deep Dive](https://go.microsoft.com/fwlink/?LinkId=324466).</span></span>

 

## <a href="" id="bkmk-admins-pub-pkgs"></a><span data-ttu-id="a830f-171">管理者のみがパッケージの発行または発行を取り消すことができるようにするには</span><span class="sxs-lookup"><span data-stu-id="a830f-171">To enable only administrators to publish or unpublish packages</span></span>


<span data-ttu-id="a830f-172">**注** 
**この機能は、app-v 5.0 SP3 以降でサポートされています。**</span><span class="sxs-lookup"><span data-stu-id="a830f-172">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="a830f-173">次のコマンドレットとパラメーターを使用して、(エンドユーザーではなく) 管理者のみがパッケージを公開または非公開にすることを許可します。</span><span class="sxs-lookup"><span data-stu-id="a830f-173">Use the following cmdlet and parameter to enable only administrators (not end users) to publish or unpublish packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="a830f-174">コマンドレット</span><span class="sxs-lookup"><span data-stu-id="a830f-174">Cmdlet</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a830f-175">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="a830f-175">Set-AppvClientConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="a830f-176">パラメーター</span><span class="sxs-lookup"><span data-stu-id="a830f-176">Parameter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="a830f-177">-RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="a830f-177">-RequirePublishAsAdmin</span></span></p>
<p><span data-ttu-id="a830f-178">パラメーターの値:</span><span class="sxs-lookup"><span data-stu-id="a830f-178">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="a830f-179">0-偽</span><span class="sxs-lookup"><span data-stu-id="a830f-179">0 - False</span></span></p></li>
<li><p><span data-ttu-id="a830f-180">1-True</span><span class="sxs-lookup"><span data-stu-id="a830f-180">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="a830f-181">例: </strong> AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="a830f-181">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a830f-182">App-v 管理コンソールを使ってこの構成を設定する方法については、「[管理コンソールを使用してパッケージを公開する方法](how-to-publish-a-package-by-using-the-management-console-50.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a830f-182">To use the App-V Management console to set this configuration, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md).</span></span>

## <a href="" id="bkmk-understd-pend-pkgs"></a><span data-ttu-id="a830f-183">保留中のパッケージについて (UserPending および GlobalPending)</span><span class="sxs-lookup"><span data-stu-id="a830f-183">Understanding pending packages (UserPending and GlobalPending)</span></span>


<span data-ttu-id="a830f-184">**App-v 5.0 SP2 以降**: 現在使用されているパッケージに影響を与える PowerShell コマンドレットを実行すると、実行しようとしているタスクは保留中の状態に置かれます。</span><span class="sxs-lookup"><span data-stu-id="a830f-184">**Starting in App-V 5.0 SP2**: If you run a PowerShell cmdlet that affects a package that is currently in use, the task that you are trying to perform is placed in a pending state.</span></span> <span data-ttu-id="a830f-185">たとえば、パッケージ内のアプリケーションを使っているときにパッケージを公開しようとした場合、 **AppvClientPackage**を実行すると、次のように、コマンドレットの出力に保留状態が表示されます。</span><span class="sxs-lookup"><span data-stu-id="a830f-185">For example, if you try to publish a package when an application in that package is being used, and then run **Get-AppvClientPackage**, the pending status appears in the cmdlet output as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a830f-186">コマンドレットの出力項目</span><span class="sxs-lookup"><span data-stu-id="a830f-186">Cmdlet output item</span></span></th>
<th align="left"><span data-ttu-id="a830f-187">説明</span><span class="sxs-lookup"><span data-stu-id="a830f-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a830f-188">UserPending</span><span class="sxs-lookup"><span data-stu-id="a830f-188">UserPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="a830f-189">表示されているパッケージに、ユーザーに適用されている保留中のタスクがあるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a830f-189">Indicates whether the listed package has a pending task that is being applied to the user:</span></span></p>
<ul>
<li><p><span data-ttu-id="a830f-190">True</span><span class="sxs-lookup"><span data-stu-id="a830f-190">True</span></span></p></li>
<li><p><span data-ttu-id="a830f-191">False</span><span class="sxs-lookup"><span data-stu-id="a830f-191">False</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a830f-192">GlobalPending</span><span class="sxs-lookup"><span data-stu-id="a830f-192">GlobalPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="a830f-193">表示されているパッケージに、コンピューターにグローバルに適用される保留中のタスクが含まれているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="a830f-193">Indicates whether the listed package has a pending task that is being applied globally to the computer:</span></span></p>
<ul>
<li><p><span data-ttu-id="a830f-194">True</span><span class="sxs-lookup"><span data-stu-id="a830f-194">True</span></span></p></li>
<li><p><span data-ttu-id="a830f-195">False</span><span class="sxs-lookup"><span data-stu-id="a830f-195">False</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a830f-196">保留中のタスクは、次のルールに従って後で実行されます。</span><span class="sxs-lookup"><span data-stu-id="a830f-196">The pending task will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a830f-197">タスクの種類</span><span class="sxs-lookup"><span data-stu-id="a830f-197">Task type</span></span></th>
<th align="left"><span data-ttu-id="a830f-198">該当するルール</span><span class="sxs-lookup"><span data-stu-id="a830f-198">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a830f-199">ユーザーベースのタスク (パッケージをユーザーに公開するなど)</span><span class="sxs-lookup"><span data-stu-id="a830f-199">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="a830f-200">保留中のタスクは、ユーザーがログオフしてから再びログインした後に実行されます。</span><span class="sxs-lookup"><span data-stu-id="a830f-200">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a830f-201">グローバルに基づくタスク (例: 接続グループをグローバルに有効にする)</span><span class="sxs-lookup"><span data-stu-id="a830f-201">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="a830f-202">保留中のタスクは、コンピューターをシャットダウンしてから再起動したときに実行されます。</span><span class="sxs-lookup"><span data-stu-id="a830f-202">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="a830f-203">保留中のタスクの詳細については、「 [app-v 5.0 SP2 につい](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="a830f-203">For more information about pending tasks, see [About App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks).</span></span>

<span data-ttu-id="a830f-204">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="a830f-204">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a830f-205">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="a830f-205">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a830f-206">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="a830f-206">Got an App-V issue?</span></span>** <span data-ttu-id="a830f-207">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="a830f-207">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a830f-208">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a830f-208">Related topics</span></span>


[<span data-ttu-id="a830f-209">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="a830f-209">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="a830f-210">PowerShell を使用した App-V の管理</span><span class="sxs-lookup"><span data-stu-id="a830f-210">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





