---
title: Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する
description: Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812882"
---
# <span data-ttu-id="d7ddd-103">Windows PowerShell と WMI を使って UE-V の [設定] の場所テンプレートを管理する</span><span class="sxs-lookup"><span data-stu-id="d7ddd-103">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</span></span>


<span data-ttu-id="d7ddd-104">Microsoft User Experience Virtualization (UE-V) 2.0、2.1、2.1 SP1 では、ユーザーエクスペリエンスの仮想化と適用される設定を定義するために XML 設定の場所テンプレートを使用しています。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the settings that User Experience Virtualization captures and applies.</span></span> <span data-ttu-id="d7ddd-105">UE-V には、標準設定の場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="d7ddd-106">また、カスタム設定の場所テンプレートを作成できる UE-V Generator ツールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="d7ddd-107">設定場所テンプレートを作成して展開した後は、Windows PowerShell と Windows Management Instrumentation (WMI) を使って、これらのテンプレートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-107">After you create and deploy settings location templates, you can manage those templates by using Windows PowerShell and the Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="d7ddd-108">UE-V PowerShell コマンドレットの完全な一覧については、「 [ue-v 2 コマンドレットリファレンス](https://go.microsoft.com/fwlink/p/?LinkId=393495)(」を参照してください https://go.microsoft.com/fwlink/p/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-108">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/p/?LinkId=393495) (https://go.microsoft.com/fwlink/p/?LinkId=393495).</span></span>

## <span data-ttu-id="d7ddd-109">Windows PowerShell を使用して UE-V 2 設定の場所テンプレートを管理する</span><span class="sxs-lookup"><span data-stu-id="d7ddd-109">Manage UE-V 2 settings location templates by using Windows PowerShell</span></span>


<span data-ttu-id="d7ddd-110">UE-V の WMI および Windows PowerShell 機能には、設定場所テンプレートの有効化、無効化、登録、更新、および登録解除の機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-110">The WMI and Windows PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="d7ddd-111">これらの機能を使用すると、テンプレートの登録、更新、または登録解除のプロセスを、UE-V Agent で自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-111">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V Agent.</span></span> <span data-ttu-id="d7ddd-112">また、WMI コマンドと Windows PowerShell コマンドを使用して、手動でテンプレートを登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-112">You can also manually register templates by using WMI and Windows PowerShell commands.</span></span> <span data-ttu-id="d7ddd-113">これらの機能を電子的なソフトウェア配布ソリューション、グループポリシー、またはスクリプトなどの自動化された展開方法と組み合わせて使用することで、そのプロセスをさらに自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-113">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="d7ddd-114">設定場所テンプレートの更新、登録、または登録解除を行うには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-114">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="d7ddd-115">テンプレートを有効または無効にするには、管理者権限は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-115">Administrator permissions are not required to enable, disable, or list templates.</span></span>

***<em><span data-ttu-id="d7ddd-116">Windows PowerShell を使用して設定場所テンプレートを管理するには</span><span class="sxs-lookup"><span data-stu-id="d7ddd-116">To manage settings location templates by using Windows PowerShell</span></span>ell</em>***

1.  <span data-ttu-id="d7ddd-117">管理者権限を持つアカウントを使用して、Windows PowerShell コマンドプロンプトを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-117">Use an account with administrator rights to open a Windows PowerShell command prompt.</span></span>

2.  <span data-ttu-id="d7ddd-118">次の Windows PowerShell コマンドレットを使用して、UE-V 設定の場所テンプレートを登録および管理します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-118">Use the following Windows PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="d7ddd-119">Windows PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="d7ddd-119">Windows PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="d7ddd-120">説明</span><span class="sxs-lookup"><span data-stu-id="d7ddd-120">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-121">コンピューターに登録されているすべての設定場所テンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-121">Lists all the settings location templates that are registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-122">アプリケーション名またはテンプレート名に文字列が含まれているコンピューターに登録されているすべての設定場所テンプレートを一覧表示し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-122">Lists all the settings location templates that are registered on the computer where the application name or template name contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-123">テンプレート ID に文字列が含まれているコンピューターに登録されているすべての設定の場所テンプレートを一覧表示し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-123">Lists all the settings location templates that are registered on the computer where the template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-124">アプリケーションまたはテンプレートの名前、またはテンプレート ID に文字列が含まれているコンピューターに登録されているすべての設定場所テンプレートを一覧表示し &lt; &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-124">Lists all the settings location templates that are registered on the computer where the application or template name, or template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-125">テンプレート ID に依存するプログラムの名前とバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-125">Gets the name of the program and version information, which depend on the template ID.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-126">Windows アプリの有効な一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-126">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-127">コンピューターに対して構成されている Windows アプリの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-127">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-128">現在のユーザーに対して構成されている Windows アプリの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-128">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-129">相対パスまたはワイルドカード文字を使用して、UE-V を使って1つまたは複数の設定場所テンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-129">Registers one or more settings location template with UE-V by using relative paths and/or wildcard characters in file paths.</span></span> <span data-ttu-id="d7ddd-130">テンプレートが登録されると、UE-V は、テンプレートが登録されているコンピューター間のテンプレートで定義された設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-130">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-131">リテラルパスを使用して、1つまたは複数の設定場所テンプレートを UE-V に登録します。このテンプレートでは、ワイルドカード文字として解釈することはできません。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-131">Registers one or more settings location template with UE-V by using literal paths, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="d7ddd-132">テンプレートが登録されると、UE-V は、テンプレートが登録されているコンピューター間のテンプレートで定義された設定を同期します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-132">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-133">UE-V を使用して、設定場所テンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-133">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="d7ddd-134">テンプレートの登録を解除すると、UE-V は、テンプレートで定義されているコンピューター間の設定を同期しなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-134">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-135">UE-V を使用して、設定場所テンプレートの登録をすべて解除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-135">Unregisters all settings location templates with UE-V.</span></span> <span data-ttu-id="d7ddd-136">テンプレートの登録を解除すると、UE-V は、テンプレートで定義されているコンピューター間の設定を同期しなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-136">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-137">テンプレートの最新バージョンを使用して、1つまたは複数の設定場所テンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-137">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="d7ddd-138">ファイルパスには、相対パスまたはワイルドカード文字を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-138">Use relative paths and/or wildcard characters in the file paths.</span></span> <span data-ttu-id="d7ddd-139">新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-139">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-140">テンプレートの最新バージョンを使用して、1つまたは複数の設定場所テンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-140">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="d7ddd-141">テンプレートファイルには完全なパスを使用します。ここでは、ワイルドカード文字として解釈できる文字はありません。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-141">Use full paths to template files, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="d7ddd-142">新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-142">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-143">コンピューターの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-143">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-144">現在のユーザーの Windows アプリの一覧から Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-144">Removes Windows app from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-145">コンピューターの Windows アプリの一覧からすべての Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-145">Removes all Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-146">現在のユーザーの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-146">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-147">現在のユーザーの Windows アプリの一覧からすべての Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-147">Removes all Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-148">コンピューターの現在のユーザーの設定場所テンプレートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-148">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-149">コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-149">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-150">現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-150">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-151">コンピューターの現在のユーザーの設定場所テンプレートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-151">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-152">コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-152">Enables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-153">現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-153">Enables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-154">1つまたは複数の設定場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-154">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="d7ddd-155">相対パスとワイルドカード文字を使うことができます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-155">Can use relative paths and wildcard characters.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-156">1つまたは複数の設定場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-156">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="d7ddd-157">パスには、テンプレートファイルへのフルパスを指定する必要がありますが、ワイルドカード文字は含まれません。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-157">The path must be a full path to the template file, but does not include wildcard characters.</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="d7ddd-158">UE-V Windows PowerShell 機能を使用すると、企業に展開される設定テンプレートのグループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-158">The UE-V Windows PowerShell features enable you to manage a group of settings templates that are deployed in your enterprise.</span></span> <span data-ttu-id="d7ddd-159">Windows PowerShell を使用してテンプレートのグループを管理するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-159">Use the following procedure to manage a group of templates by using Windows PowerShell.</span></span>

**<span data-ttu-id="d7ddd-160">Windows PowerShell を使用して設定場所テンプレートのグループを管理するには</span><span class="sxs-lookup"><span data-stu-id="d7ddd-160">To manage a group of settings location templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="d7ddd-161">目的の設定の場所テンプレートを変更または更新します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-161">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="d7ddd-162">設定の場所テンプレートを変更または更新する場合は、ローカルコンピューターからアクセスできるフォルダーに設定場所テンプレートを展開します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-162">If you want to modify or update the settings location templates, deploy those settings location templates to a folder that is accessible to the local computer.</span></span>

3.  <span data-ttu-id="d7ddd-163">ローカルコンピューターで、管理者権限で Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-163">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="d7ddd-164">次のコマンドを入力して、以前に登録されたすべてのバージョンのテンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-164">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Unregister-UevTemplate -All
    ```

    <span data-ttu-id="d7ddd-165">このコマンドは、コンピューター上のすべてのアクティブなテンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-165">This command unregisters all active templates on the computer.</span></span>

5.  <span data-ttu-id="d7ddd-166">次のコマンドを入力して、更新されたテンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-166">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="d7ddd-167">このコマンドによって、指定したテンプレートフォルダーにあるすべての設定場所テンプレートが登録されます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-167">This command registers all of the settings location templates that are located in the specified template folder.</span></span>

### <a href="" id="win8applist"></a><span data-ttu-id="d7ddd-168">Windows アプリの一覧</span><span class="sxs-lookup"><span data-stu-id="d7ddd-168">Windows app list</span></span>

<span data-ttu-id="d7ddd-169">Windows アプリの一覧に Windows アプリの一覧を表示することで、そのアプリが設定の同期に対して有効または無効になるかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-169">By listing a Windows app in the Windows app list, you specify whether that app is enabled or disabled for settings synchronization.</span></span> <span data-ttu-id="d7ddd-170">アプリは、パッケージファミリ名によって一覧に表示され、そのアプリで設定の同期を有効または無効にするかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-170">Apps are identified in the list by their Package Family name and whether settings synchronization should be enabled or disabled for that app.</span></span> <span data-ttu-id="d7ddd-171">これらの設定を、一覧表示されていない既定の同期動作設定と共に使用すると、Windows アプリを同期するかどうかを制御できます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-171">When you use these settings along with the Unlisted Default Sync Behavior setting, you can control whether Windows apps are synchronized.</span></span>

<span data-ttu-id="d7ddd-172">インストールされている Windows アプリのパッケージファミリ名を表示するには、Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-172">To display the Package Family Name of installed Windows apps, at a Windows PowerShell command prompt, enter:</span></span>

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

<span data-ttu-id="d7ddd-173">Windows PowerShell のコマンドプロンプトで、コンピューターの設定をパッケージファミリ名、有効状態、有効なソースに同期できる Windows アプリの一覧を表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-173">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="d7ddd-174">UevAppxPackage プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="d7ddd-174">Definitions of Get-UevAppxPackage properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="d7ddd-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d7ddd-175">DisplayName</span></span>**  
<span data-ttu-id="d7ddd-176">会社設定センターアプリケーションでユーザーに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-176">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="d7ddd-177">`DisplayName`プロパティはプロパティから派生し `PackageFamilyName` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-177">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="d7ddd-178">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="d7ddd-178">PackageFamilyName</span></span>**  
<span data-ttu-id="d7ddd-179">現在のユーザー用にインストールされているパッケージの名前です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-179">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="d7ddd-180">有効</span><span class="sxs-lookup"><span data-stu-id="d7ddd-180">Enabled</span></span>**  
<span data-ttu-id="d7ddd-181">アプリの設定を同期するように構成するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-181">Defines whether the settings for the app are configured to synchronize.</span></span>

<a href="" id="enabledsource"></a>**<span data-ttu-id="d7ddd-182">EnabledSource</span><span class="sxs-lookup"><span data-stu-id="d7ddd-182">EnabledSource</span></span>**  
<span data-ttu-id="d7ddd-183">アプリを有効または無効にする構成が設定されている場所。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-183">The location where the configuration that enables or disables the app is set.</span></span> <span data-ttu-id="d7ddd-184">指定できる値は、 *NotSet*、 *LocalMachine*、 *LocalUser*、 *policymachine*、 *policymachine*です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-184">Possible values are: *NotSet*, *LocalMachine*, *LocalUser*, *PolicyMachine*, and *PolicyUser*.</span></span>

<a href="" id="notset"></a>**<span data-ttu-id="d7ddd-185">NotSet</span><span class="sxs-lookup"><span data-stu-id="d7ddd-185">NotSet</span></span>**  
<span data-ttu-id="d7ddd-186">ポリシーはこのアプリを同期するように構成されていません。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-186">The policy is not configured to synchronize this app.</span></span>

<a href="" id="localmachine"></a>**<span data-ttu-id="d7ddd-187">LocalMachine</span><span class="sxs-lookup"><span data-stu-id="d7ddd-187">LocalMachine</span></span>**  
<span data-ttu-id="d7ddd-188">有効状態は、レジストリの [ローカルコンピューター] セクションで設定します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-188">The enabled state is set in the local computer section of the registry.</span></span>

<a href="" id="localuser"></a>**<span data-ttu-id="d7ddd-189">LocalUser</span><span class="sxs-lookup"><span data-stu-id="d7ddd-189">LocalUser</span></span>**  
<span data-ttu-id="d7ddd-190">有効状態は、レジストリの [現在のユーザー] セクションで設定します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-190">The enabled state is set in the current user section of the registry.</span></span>

<a href="" id="policymachine"></a>**<span data-ttu-id="d7ddd-191">PolicyMachine</span><span class="sxs-lookup"><span data-stu-id="d7ddd-191">PolicyMachine</span></span>**  
<span data-ttu-id="d7ddd-192">有効状態は、レジストリの [ローカルコンピューター] セクションの [ポリシー] セクションで設定します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-192">The enabled state is set in the policy section of the local computer section of the registry.</span></span>

<span data-ttu-id="d7ddd-193">Windows アプリのユーザーが設定した一覧を取得するには、Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-193">To get the user-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –CurrentComputerUser`

<span data-ttu-id="d7ddd-194">コンピューターで構成された Windows アプリの一覧を取得するには、Windows PowerShell コマンドプロンプトで次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-194">To get the computer-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –Computer`

<span data-ttu-id="d7ddd-195">CurrentComputerUser または Computer のいずれかの場合、コマンドレットは、ユーザーまたはコンピューターレベルで構成されている Windows アプリの一覧を返します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-195">For either parameter, CurrentComputerUser or Computer, the cmdlet returns a list of the Windows apps that are configured at the user or at the computer level.</span></span>

**<span data-ttu-id="d7ddd-196">プロパティの定義</span><span class="sxs-lookup"><span data-stu-id="d7ddd-196">Definitions of properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="d7ddd-197">DisplayName</span><span class="sxs-lookup"><span data-stu-id="d7ddd-197">DisplayName</span></span>**  
<span data-ttu-id="d7ddd-198">会社設定センターアプリケーションでユーザーに表示される名前です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-198">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="d7ddd-199">`DisplayName`プロパティはプロパティから派生し `PackageFamilyName` ます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-199">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="d7ddd-200">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="d7ddd-200">PackageFamilyName</span></span>**  
<span data-ttu-id="d7ddd-201">現在のユーザー用にインストールされているパッケージの名前です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-201">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="d7ddd-202">有効</span><span class="sxs-lookup"><span data-stu-id="d7ddd-202">Enabled</span></span>**  
<span data-ttu-id="d7ddd-203">指定したスイッチ (**ユーザー**または**コンピューター**) に対して、アプリの設定を同期するように構成するかどうかを定義します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-203">Defines whether the settings for the app are configured to synchronize for the specified switch, that is, **user** or **computer**.</span></span>

<a href="" id="installed"></a>**<span data-ttu-id="d7ddd-204">インストール済み</span><span class="sxs-lookup"><span data-stu-id="d7ddd-204">Installed</span></span>**  
<span data-ttu-id="d7ddd-205">アプリが、現在のユーザーに対して、"パッケージ" という名前のアプリがインストールされている場合は True です。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-205">True if the app, that is, the PackageFamilyName is installed for the current user.</span></span>

### <span data-ttu-id="d7ddd-206">WMI を使用して UE-V 2 設定場所テンプレートを管理する</span><span class="sxs-lookup"><span data-stu-id="d7ddd-206">Manage UE-V 2 settings location templates by using WMI</span></span>

<span data-ttu-id="d7ddd-207">ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-207">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="d7ddd-208">管理者は、これらのインターフェイスを使って、Windows PowerShell から設定場所テンプレートを管理し、テンプレートの管理タスクを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-208">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="d7ddd-209">WMI を使用して設定場所テンプレートを管理するには</span><span class="sxs-lookup"><span data-stu-id="d7ddd-209">To manage settings location templates by using WMI</span></span>**

1.  <span data-ttu-id="d7ddd-210">管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-210">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="d7ddd-211">次の WMI コマンドを使用して、UE-V 設定の場所テンプレートを登録および管理します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-211">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="d7ddd-212">説明</span><span class="sxs-lookup"><span data-stu-id="d7ddd-212">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-213">コンピューターに登録されているすべての設定場所テンプレートを一覧表示します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-213">Lists all the settings location templates that are registered for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-214">テンプレート名に応じて、プログラムの名前とバージョン情報を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-214">Gets the name of the program and version information, which depends on the template name.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-215">Windows アプリの有効な一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-215">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="d7ddd-216">WmiObject-名前空間 root\Microsoft\UEV MachineConfiguredWindows8App</span><span class="sxs-lookup"><span data-stu-id="d7ddd-216">Get-WmiObject -Namespace root\Microsoft\UEV MachineConfiguredWindows8App</span></span></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-217">コンピューターに対して構成されている Windows アプリの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-217">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-218">現在のユーザーに対して構成されている Windows アプリの一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-218">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-219">設定場所テンプレートを UE-V に登録します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-219">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-220">UE-V を使用して、設定場所テンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-220">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="d7ddd-221">テンプレートの登録が解除されるとすぐに、UE-V はテンプレートで定義されている設定をコンピューター間で同期しなくなります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-221">As soon as a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-222">UE-V を使用して設定場所テンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-222">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="d7ddd-223">新しいテンプレートは、既存のテンプレートよりも新しいバージョンである必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-223">The new template should be a newer version than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-224">コンピューターの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-224">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-225">現在のユーザーの Windows アプリの一覧から1つまたは複数の Windows アプリを削除します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-225">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-226">UE-V を使用して、1つ以上の設定場所テンプレートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-226">Disables one or more settings location templates with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-227">コンピューターの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-227">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-228">現在のユーザーの Windows アプリの一覧で、1つ以上の Windows アプリを無効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-228">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-229">UE-V を使用して設定場所テンプレートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-229">Enables a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-230">コンピューターの Windows アプリリストで Windows アプリを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-230">Enables Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-231">現在のユーザーの Windows アプリの一覧で Windows アプリを有効にします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-231">Enables Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="d7ddd-232">指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-232">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### <span data-ttu-id="d7ddd-233">Windows PowerShell を使用した UE-V エージェントの展開</span><span class="sxs-lookup"><span data-stu-id="d7ddd-233">Deploying the UE-V Agent using Windows PowerShell</span></span>

**<span data-ttu-id="d7ddd-234">Windows PowerShell を使用して UE-V Agent を展開する方法</span><span class="sxs-lookup"><span data-stu-id="d7ddd-234">How to deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="d7ddd-235">UE-V Agent インストールパッケージを、アクセス可能なネットワーク共有にステージします。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-235">Stage the UE-V Agent installation package in an accessible network share.</span></span>

    **<span data-ttu-id="d7ddd-236">注</span><span class="sxs-lookup"><span data-stu-id="d7ddd-236">Note</span></span>**  
    <span data-ttu-id="d7ddd-237">AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-237">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="d7ddd-238">Windows Installer パッケージ、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-238">The Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="d7ddd-239">インストールファイルを使用して、後で UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-239">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="d7ddd-240">UE-V Agent をインストールするには、次の Windows PowerShell コマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-240">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

<span data-ttu-id="d7ddd-241">**Ue-v のご提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-241">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="d7ddd-242">[ここで](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-242">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="d7ddd-243">**Ue-v の問題が発生した場合**</span><span class="sxs-lookup"><span data-stu-id="d7ddd-243">**Got a UE-V issue**?</span></span> <span data-ttu-id="d7ddd-244">Ue-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)を使用します。</span><span class="sxs-lookup"><span data-stu-id="d7ddd-244">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="d7ddd-245">関連トピック</span><span class="sxs-lookup"><span data-stu-id="d7ddd-245">Related topics</span></span>


[<span data-ttu-id="d7ddd-246">Windows PowerShell と WMI を使用した UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="d7ddd-246">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="d7ddd-247">UE-V 2. x の管理</span><span class="sxs-lookup"><span data-stu-id="d7ddd-247">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









