---
title: PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理
description: PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812491"
---
# <span data-ttu-id="00c0c-103">PowerShell と WMI を使用した UE-V 1.0 設定場所テンプレートの管理</span><span class="sxs-lookup"><span data-stu-id="00c0c-103">Managing UE-V 1.0 Settings Location Templates Using PowerShell and WMI</span></span>


<span data-ttu-id="00c0c-104">Microsoft User Experience Virtualization (UE-V) では、ユーザーエクスペリエンスの仮想化によってキャプチャおよび適用される設定を定義する設定場所テンプレート (XML ファイル) を使用します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="00c0c-105">UE-V には、標準設定の場所テンプレートのセットが含まれています。</span><span class="sxs-lookup"><span data-stu-id="00c0c-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="00c0c-106">また、カスタム設定の場所テンプレートを作成できる UE-V Generator ツールも含まれています。</span><span class="sxs-lookup"><span data-stu-id="00c0c-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="00c0c-107">設定場所テンプレートを作成して展開すると、PowerShell または WMI を使ってそれらのテンプレートを管理できます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-107">After you create and deploy settings location templates you can manage those templates using PowerShell or WMI.</span></span>

## <span data-ttu-id="00c0c-108">WMI と PowerShell を使用して設定場所テンプレートを管理する</span><span class="sxs-lookup"><span data-stu-id="00c0c-108">Manage settings location templates with WMI and PowerShell</span></span>


<span data-ttu-id="00c0c-109">UE-V の WMI および PowerShell 機能には、設定場所テンプレートの有効化、無効化、登録、更新、および登録解除機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="00c0c-109">The WMI and PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="00c0c-110">これらの機能を使用すると、テンプレートの登録、更新、または登録解除のプロセスを、UE-V agent で自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-110">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V agent.</span></span> <span data-ttu-id="00c0c-111">また、WMI コマンドと PowerShell コマンドを使って手動でテンプレートを登録することもできます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-111">You can also manually register templates using WMI and PowerShell commands.</span></span> <span data-ttu-id="00c0c-112">これらの機能を電子的なソフトウェア配布ソリューション、グループポリシー、またはスクリプトなどの自動化された展開方法と組み合わせて使用することで、そのプロセスをさらに自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-112">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="00c0c-113">設定場所テンプレートの更新、登録、または登録解除を行うには、管理者権限が必要です。</span><span class="sxs-lookup"><span data-stu-id="00c0c-113">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="00c0c-114">テンプレートを有効または無効にするには、管理者権限は必要ありません。</span><span class="sxs-lookup"><span data-stu-id="00c0c-114">Administrator permissions are not required to enable or disable templates.</span></span>

**<span data-ttu-id="00c0c-115">PowerShell を使用して設定場所テンプレートを管理するには</span><span class="sxs-lookup"><span data-stu-id="00c0c-115">To manage settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="00c0c-116">管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-116">Use an account with administrator rights to open a Windows PowerShell window.</span></span> <span data-ttu-id="00c0c-117">**MICROSOFT Ue-v powershell**モジュールをインポートするには、PowerShell コマンドプロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-117">To import the **Microsoft UE-V PowerShell** module, type the following command at the PowerShell command prompt.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="00c0c-118">次の PowerShell コマンドレットを使用して、UE-V 設定の場所テンプレートを登録および管理します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-118">Use the following PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="00c0c-119">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="00c0c-119">PowerShell command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="00c0c-120">説明</span><span class="sxs-lookup"><span data-stu-id="00c0c-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-121">取得-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-121">Get-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-122">コンピューターに登録されているすべての設定場所テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-122">Lists all the settings location templates registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-123">登録-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-123">Register-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-124">設定場所テンプレートを UE-V に登録します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-124">Registers a settings location template with UE-V.</span></span> <span data-ttu-id="00c0c-125">テンプレートが登録されると、UE-V によってテンプレートが登録されているコンピューター間のテンプレートで定義された設定が同期されます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-125">Once a template is registered, UE-V will synchronize the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-126">登録解除-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-126">Unregister-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-127">UE-V を使用して、設定場所テンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-127">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="00c0c-128">テンプレートの登録を解除すると、そのテンプレートで定義されている設定が、UE-V によってコンピューター間で同期されなくなります。</span><span class="sxs-lookup"><span data-stu-id="00c0c-128">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-129">更新-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-129">Update-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-130">テンプレートの最新バージョンを使用して、設定場所テンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-130">Updates a settings location template with a more recent version of the template.</span></span> <span data-ttu-id="00c0c-131">新しいテンプレートには、既存のテンプレートよりも新しいバージョンが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c0c-131">The new template should have a version that is later than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-132">無効-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-132">Disable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-133">コンピューターの現在のユーザーの設定場所テンプレートを無効にします。</span><span class="sxs-lookup"><span data-stu-id="00c0c-133">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-134">Enable-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-134">Enable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-135">コンピューターの現在のユーザーの設定場所テンプレートを有効にします。</span><span class="sxs-lookup"><span data-stu-id="00c0c-135">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-136">テスト-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="00c0c-136">Test-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-137">指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-137">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="00c0c-138">UE-V PowerShell 機能を使用すると、エンタープライズで展開された設定テンプレートのグループを管理できます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-138">The UE-V PowerShell features allow you to manage a group of settings templates deployed in your enterprise.</span></span> <span data-ttu-id="00c0c-139">PowerShell を使用してテンプレートのグループを管理するには、次の操作を行います。</span><span class="sxs-lookup"><span data-stu-id="00c0c-139">To manage a group of templates using PowerShell, do the following.</span></span>

**<span data-ttu-id="00c0c-140">PowerShell を使用して設定場所テンプレートのグループを管理するには</span><span class="sxs-lookup"><span data-stu-id="00c0c-140">To manage a group of settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="00c0c-141">目的の設定の場所テンプレートを変更または更新します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-141">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="00c0c-142">ローカルコンピューターでアクセス可能なフォルダーに、目的の設定の場所テンプレートを配置します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-142">Deploy the desired settings location templates to a folder accessible to the local computer.</span></span>

3.  <span data-ttu-id="00c0c-143">ローカルコンピューターで、管理者権限で Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-143">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="00c0c-144">次のコマンドを入力して、Microsoft UE-V PowerShell モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="00c0c-144">Import the Microsoft UE-V PowerShell module, by typing the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

5.  <span data-ttu-id="00c0c-145">次のコマンドを入力して、以前に登録されたすべてのバージョンのテンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-145">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    <span data-ttu-id="00c0c-146">これにより、コンピューター上のすべてのアクティブなテンプレートの登録が解除されます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-146">This will unregister all active templates on the computer.</span></span>

6.  <span data-ttu-id="00c0c-147">次のコマンドを入力して、更新されたテンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-147">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="00c0c-148">指定されたテンプレートフォルダーにあるすべての設定場所テンプレートを登録します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-148">This will register all of the settings location templates located in the specified template folder.</span></span>

<span data-ttu-id="00c0c-149">ユーザーエクスペリエンスの仮想化には、次のような WMI コマンドのセットが用意されています。</span><span class="sxs-lookup"><span data-stu-id="00c0c-149">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="00c0c-150">管理者は、これらのインターフェイスを使って、Windows PowerShell から設定場所テンプレートを管理し、テンプレートの管理タスクを自動化することができます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-150">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="00c0c-151">WMI を使用して設定場所テンプレートを管理するには</span><span class="sxs-lookup"><span data-stu-id="00c0c-151">To manage settings location templates with WMI</span></span>**

1.  <span data-ttu-id="00c0c-152">管理者権限を持つアカウントを使用して、Windows PowerShell ウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-152">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="00c0c-153">次の WMI コマンドを使用して、UE-V 設定の場所テンプレートを登録および管理します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-153">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="00c0c-154">PowerShell コマンド</span><span class="sxs-lookup"><span data-stu-id="00c0c-154">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="00c0c-155">説明</span><span class="sxs-lookup"><span data-stu-id="00c0c-155">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-156">WmiObject-Namespace root\Microsoft\UEV SettingsLocationTemplate |Select-Object TemplateId、TemplateName、TemplateVersion、Enabled |書式設定-表-Autosize</span><span class="sxs-lookup"><span data-stu-id="00c0c-156">Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-157">コンピューターに登録されているすべての設定場所テンプレートの一覧が表示されます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-157">Lists all the settings location templates registered for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-158">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate-Name Register-ArgumentList &lt; template path&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-158">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-159">設定場所テンプレートを UE-V に登録します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-159">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-160">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name UnregisterByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-160">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-161">UE-V を使用して、設定場所テンプレートの登録を解除します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-161">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="00c0c-162">テンプレートの登録を解除すると、そのテンプレートで定義されている設定が、UE-V によってコンピューター間で同期されなくなります。</span><span class="sxs-lookup"><span data-stu-id="00c0c-162">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-163">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name EnableByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-163">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-164">UE-V を使用して設定場所テンプレートを有効にします</span><span class="sxs-lookup"><span data-stu-id="00c0c-164">Enables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-165">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name DisableByTemplateId-ArgumentList &lt; TEMPLATE ID&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-165">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-166">UE-V を使用して設定場所テンプレートを無効にします</span><span class="sxs-lookup"><span data-stu-id="00c0c-166">Disables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="00c0c-167">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name Update-ArgumentList &lt; template path&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-167">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-168">UE-V を使用して設定場所テンプレートを更新します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-168">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="00c0c-169">新しいテンプレートには、既存のテンプレートよりも高いバージョンが含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c0c-169">The new template should have a version that is higher than the existing one.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="00c0c-170">Invoke メソッド-Namespace root\Microsoft\UEV-Class SettingsLocationTemplate Name Validate-ArgumentList &lt; template path&gt;</span><span class="sxs-lookup"><span data-stu-id="00c0c-170">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="00c0c-171">指定された設定の場所テンプレートがその XML スキーマに準拠しているかどうかを判断します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-171">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="00c0c-172">PowerShell で UE-V agent を展開する方法</span><span class="sxs-lookup"><span data-stu-id="00c0c-172">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="00c0c-173">UE-V インストーラファイルをアクセシビリティ対応のネットワーク共有にステージングします。</span><span class="sxs-lookup"><span data-stu-id="00c0c-173">Stage the UE-V installer file in an accessible network share.</span></span>

    <span data-ttu-id="00c0c-174">**注** AgentSetup.exe を使って、32ビットと64ビットの両方のバージョンの UE-V Agent を展開します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-174">**Note** Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="00c0c-175">Windows Installer ファイルのバージョン、AgentSetupx86.msi、AgentSetupx64.msi は、各アーキテクチャで利用できます。</span><span class="sxs-lookup"><span data-stu-id="00c0c-175">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="00c0c-176">インストールファイルを使用して後から UE-V エージェントをアンインストールするには、同じ種類のファイルを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00c0c-176">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>

     

2.  <span data-ttu-id="00c0c-177">エージェントをインストールするには、次の PowerShell コマンドのいずれかを使用します。</span><span class="sxs-lookup"><span data-stu-id="00c0c-177">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## <span data-ttu-id="00c0c-178">関連トピック</span><span class="sxs-lookup"><span data-stu-id="00c0c-178">Related topics</span></span>


[<span data-ttu-id="00c0c-179">PowerShell と WMI を使用した UE-V 1.0 エージェントの管理</span><span class="sxs-lookup"><span data-stu-id="00c0c-179">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[<span data-ttu-id="00c0c-180">UE-V 1.0 の管理</span><span class="sxs-lookup"><span data-stu-id="00c0c-180">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="00c0c-181">UE-V 1.0 の操作</span><span class="sxs-lookup"><span data-stu-id="00c0c-181">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





