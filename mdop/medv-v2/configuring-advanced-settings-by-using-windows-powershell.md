---
title: Windows PowerShell を使用した高度な設定の構成
description: Windows PowerShell を使用した高度な設定の構成
author: dansimp
ms.assetid: 437a31cc-2a11-456f-b448-b0b869fb53f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a3ece3f76f6e982913aad2b25cfe0084542f32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827394"
---
# <span data-ttu-id="ea313-103">Windows PowerShell を使用した高度な設定の構成</span><span class="sxs-lookup"><span data-stu-id="ea313-103">Configuring Advanced Settings by Using Windows PowerShell</span></span>


<span data-ttu-id="ea313-104">作成する MED-V ワークスペースパッケージには、MED-V ワークスペースパッケージをテストして展開する前に編集できる Windows PowerShell スクリプト (. ps1) ファイルが含まれています。</span><span class="sxs-lookup"><span data-stu-id="ea313-104">The MED-V workspace package that you create includes a Windows PowerShell script (.ps1) file that you can edit before you test and deploy your MED-V workspace package.</span></span> <span data-ttu-id="ea313-105">このセクションでは、MED-V ワークスペースを展開する前に Windows PowerShell を使用して、MED-V 構成設定を管理するための情報とガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="ea313-105">This section provides information and guidance to help you manage MED-V configuration settings by using Windows PowerShell before you deploy the MED-V workspaces.</span></span>

## <span data-ttu-id="ea313-106">MED-V での Windows PowerShell コマンドレットの使用</span><span class="sxs-lookup"><span data-stu-id="ea313-106">Using Windows PowerShell Cmdlets in MED-V</span></span>


<span data-ttu-id="ea313-107">Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 では、次の Windows PowerShell コマンドレットを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ea313-107">The following Windows PowerShell cmdlets are available in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0:</span></span>

**<span data-ttu-id="ea313-108">新規-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea313-108">New-MedvConfiguration</span></span>**

**<span data-ttu-id="ea313-109">エクスポート-MedvConfiguration</span><span class="sxs-lookup"><span data-stu-id="ea313-109">Export-MedvConfiguration</span></span>**

**<span data-ttu-id="ea313-110">新規-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="ea313-110">New-MedvWorkspace</span></span>**

**<span data-ttu-id="ea313-111">エクスポート-MedvWorkspace</span><span class="sxs-lookup"><span data-stu-id="ea313-111">Export-MedvWorkspace</span></span>**

<span data-ttu-id="ea313-112">MED-V の Windows PowerShell コマンドレットにアクセスするには、Windows PowerShell を開き、次のコマンドを入力して、MED-V モジュールをインポートします。</span><span class="sxs-lookup"><span data-stu-id="ea313-112">To access Windows PowerShell cmdlets for MED-V, open Windows PowerShell and type the following command to import the MED-V modules.</span></span>

``` syntax
Import-Module microsoft.medv
```

<span data-ttu-id="ea313-113">モジュールをインポートした後は、Windows PowerShell 標準のヘルプコマンド、 **man** 、または**get ヘルプ**を使用して、コマンドレットのインラインヘルプにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="ea313-113">After the modules are imported, you can access inline help for the cmdlets by using the standard Windows PowerShell Help commands, **man** or **get-help**.</span></span> <span data-ttu-id="ea313-114">たとえば、使用可能なパラメーターの完全な一覧を含む、**新しい-MedvConfiguration**コマンドレットの説明にアクセスするには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-114">For example, to access a description of the **New-MedvConfiguration** cmdlet including a complete list of available parameters, type the following command.</span></span>

``` syntax
get-help New-MedvConfiguration
```

<span data-ttu-id="ea313-115">特定のパラメーターのヘルプを表示することもできます。</span><span class="sxs-lookup"><span data-stu-id="ea313-115">You can also view help for specific parameters.</span></span> <span data-ttu-id="ea313-116">たとえば、VmMemory パラメーターのヘルプを表示するには、次のように入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-116">For example, to view help for the parameter VmMemory, type the following:</span></span>

``` syntax
get-help New-MedvConfiguration -parameter VmMemory
```

<span data-ttu-id="ea313-117">すべての MED-V 構成設定とその既定値の一覧を表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-117">To view a list of all MED-V configuration settings and their defaults, type the following command.</span></span>

``` syntax
New-MedvConfiguration -ForceDefaults
```

<span data-ttu-id="ea313-118">すべての MED-V 構成設定とその現在の値の一覧を表示するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-118">To view a list of all MED-V configuration settings and their current values, type the following command.</span></span>

``` syntax
gwmi -Class "Setting” -Namespace "root/microsoft/medv”
```

## <span data-ttu-id="ea313-119">カスタム設定での MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="ea313-119">Creating a MED-V Workspace with Custom Settings</span></span>


<span data-ttu-id="ea313-120">MED-V Workspace パッケージャーを使って MED-V ワークスペースパッケージを正常に作成した後、Windows PowerShell スクリプトが、パッケージャーファイルを保存するために指定したフォルダーに生成されます。</span><span class="sxs-lookup"><span data-stu-id="ea313-120">After you successfully create a MED-V workspace package by using the MED-V Workspace Packager, a Windows PowerShell script is generated in the folder you specified for saving your packager files.</span></span> <span data-ttu-id="ea313-121">このスクリプトの内容は、編集可能な一部の MED-V 構成設定を示しています。</span><span class="sxs-lookup"><span data-stu-id="ea313-121">The contents of this script show some of the available MED-V configuration settings that you can edit.</span></span>

<span data-ttu-id="ea313-122">次の手順に従って、スクリプトをカスタマイズし、Windows PowerShell で実行して、新しい設定で MED-V ワークスペースを作成することができます。</span><span class="sxs-lookup"><span data-stu-id="ea313-122">Following these steps, you can customize the script and then run it in Windows PowerShell to create a MED-V workspace with the new settings.</span></span>

<span data-ttu-id="ea313-123">**重要** 管理者の資格情報で Windows PowerShell を実行し、Windows PowerShell の実行ポリシーによってスクリプトの実行が許可されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="ea313-123">**Important** Run Windows PowerShell with administrative credentials, and ensure that the Windows PowerShell execution policy allows the running of scripts.</span></span>

1.  <span data-ttu-id="ea313-124">MED-V Workspace パッケージャーによって生成された Windows PowerShell スクリプトを編集するか、または必要な構成設定で新しいスクリプトを作成します。</span><span class="sxs-lookup"><span data-stu-id="ea313-124">Edit the Windows PowerShell script that was generated by the MED-V Workspace Packager, or author a new script with the configuration settings that you want.</span></span>

2.  <span data-ttu-id="ea313-125">管理者の資格情報で Windows PowerShell を実行し、コマンドプロンプトで次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-125">Run Windows PowerShell with administrative credentials and at the command prompt, type the following command.</span></span>

    ``` syntax
    & “.\<workspacename>.ps1”
    ```

    <span data-ttu-id="ea313-126">このコマンドは、Windows PowerShell スクリプトを実行し **、新しい med-v ワークレットを**実行して新しい med-v ワークスペースパッケージを生成します。</span><span class="sxs-lookup"><span data-stu-id="ea313-126">This command runs the Windows PowerShell script and runs the **New-MedvWorkspace** cmdlet to generate a new MED-V workspace package.</span></span> <span data-ttu-id="ea313-127">新しいパッケージャーファイルは、MED-V ワークスペースパッケージャーファイルを保存するために最初に指定したフォルダーに保存されます。</span><span class="sxs-lookup"><span data-stu-id="ea313-127">The new packager files are saved in the folder that you originally specified for storing your MED-V Workspace Packager files.</span></span> <span data-ttu-id="ea313-128">このコマンドレットの詳細については、Windows PowerShell のヘルプを参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea313-128">For additional help about this cmdlet, see the Windows PowerShell Help.</span></span>

 

## <span data-ttu-id="ea313-129">レジストリファイルへの MED-V 構成のエクスポート</span><span class="sxs-lookup"><span data-stu-id="ea313-129">Exporting a MED-V Configuration to a Registry File</span></span>


<span data-ttu-id="ea313-130">Med-v のワークスペースをインストールした後で、MED-V 構成設定を更新できます。</span><span class="sxs-lookup"><span data-stu-id="ea313-130">You can update MED-V configuration settings after the MED-V workspace is installed.</span></span> <span data-ttu-id="ea313-131">**新しい-MedvConfiguration**コマンドレットを使用して、変更するパラメーターを指定します。</span><span class="sxs-lookup"><span data-stu-id="ea313-131">Use the **New-MedvConfiguration** cmdlet to specify the parameters that you want to change.</span></span> <span data-ttu-id="ea313-132">たとえば、仮想マシンのメモリ設定を変更するレジストリファイルを作成するには、次のコマンドを入力します。</span><span class="sxs-lookup"><span data-stu-id="ea313-132">For example, to create a registry file that changes the virtual machine memory setting, type the following commands.</span></span>

``` syntax
New-MedvConfiguration  -VmMemory 1024 | Export-MedvConfiguration -Path c:\medvConfiguration\myConfig.reg
```

<span data-ttu-id="ea313-133">生成されたレジストリファイルをホストコンピューターから MED-V ワークスペースにインポートして、新しい構成設定を適用することができます。</span><span class="sxs-lookup"><span data-stu-id="ea313-133">You can import the resultant registry file from the host computer to a MED-V workspace to apply the new configuration settings.</span></span>

## <span data-ttu-id="ea313-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ea313-134">Related topics</span></span>


[<span data-ttu-id="ea313-135">MED-V ワークスペースの構成設定の管理</span><span class="sxs-lookup"><span data-stu-id="ea313-135">Managing MED-V Workspace Configuration Settings</span></span>](managing-med-v-workspace-configuration-settings.md)

[<span data-ttu-id="ea313-136">MED-V ワークスペース パッケージをテストして展開する</span><span class="sxs-lookup"><span data-stu-id="ea313-136">Test And Deploy the MED-V Workspace Package</span></span>](test-and-deploy-the-med-v-workspace-package.md)

 

 





