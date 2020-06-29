---
title: PowerShell を使用してパッケージ アクセラレータを作成する方法
description: PowerShell を使用してパッケージ アクセラレータを作成する方法
author: dansimp
ms.assetid: 8e527363-d961-4153-826a-446a4ad8d980
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4270db9a5f0603cff1f33e6244a5abb517572d97
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814298"
---
# <span data-ttu-id="00964-103">PowerShell を使用してパッケージ アクセラレータを作成する方法</span><span class="sxs-lookup"><span data-stu-id="00964-103">How to Create a Package Accelerator by Using PowerShell</span></span>


<span data-ttu-id="00964-104">アプリ-V 5.0 パッケージアクセラレータは、大規模で複雑なアプリケーションを自動的に処理します。</span><span class="sxs-lookup"><span data-stu-id="00964-104">App-V 5.0 package accelerators automatically sequence large, complex applications.</span></span> <span data-ttu-id="00964-105">さらに、App-v 5.0 パッケージアクセラレータを適用するときに、仮想化されたパッケージを作成するためにアプリケーションを手動でインストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="00964-105">Additionally, when you apply an App-V 5.0 package accelerator, you are not always required to manually install an application to create the virtualized package.</span></span>

**<span data-ttu-id="00964-106">パッケージアクセラレータを作成するには</span><span class="sxs-lookup"><span data-stu-id="00964-106">To create a package accelerator</span></span>**

1.  <span data-ttu-id="00964-107">App-v 5.0 sequencer をインストールします。</span><span class="sxs-lookup"><span data-stu-id="00964-107">Install the App-V 5.0 sequencer.</span></span> <span data-ttu-id="00964-108">Sequencer のインストールの詳細について[は、「sequencer をインストールする方法」を](how-to-install-the-sequencer-beta-gb18030.md)参照してください。</span><span class="sxs-lookup"><span data-stu-id="00964-108">For more information about installing the sequencer see [How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md).</span></span>

2.  <span data-ttu-id="00964-109">PowerShell 本体を開くには、[**開始**] をクリックし、「 **powershell**」と入力します。</span><span class="sxs-lookup"><span data-stu-id="00964-109">To open a PowerShell console click **Start** and type **PowerShell**.</span></span> <span data-ttu-id="00964-110">**[Windows PowerShell]** を右クリックし、**[管理者として実行]** を選択します。</span><span class="sxs-lookup"><span data-stu-id="00964-110">Right-click **Windows PowerShell** and select **Run as Administrator**.</span></span> <span data-ttu-id="00964-111">**AppvPackageAccelerator**コマンドレットを使用します。</span><span class="sxs-lookup"><span data-stu-id="00964-111">Use the **New-AppvPackageAccelerator** cmdlet.</span></span>

3.  <span data-ttu-id="00964-112">パッケージアクセラレータを作成するには、accelerator パッケージを使って、アクセラレータの作成元、インストールメディアまたはインストールファイル、必要に応じて読み取り専用ファイルを作成して使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="00964-112">To create a package accelerator, make sure that you have the .appv package to create an accelerator from, the installation media or installation files, and optionally a read me file for consumers of the accelerator to use.</span></span> <span data-ttu-id="00964-113">パッケージアクセラレータコマンドレットを使うには、次のパラメーターが必要です。</span><span class="sxs-lookup"><span data-stu-id="00964-113">The following parameters are required to use the package accelerator cmdlet:</span></span>

    -   <span data-ttu-id="00964-114">[インストールされている**ファイルのパス**-アプリケーションのインストールパスを指定してください。</span><span class="sxs-lookup"><span data-stu-id="00964-114">**InstalledFilesPath** - specifies the application installation path.</span></span>

    -   <span data-ttu-id="00964-115">**インストーラ**–アプリケーションインストーラメディアへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="00964-115">**Installer** – specifies the path to the application installer media</span></span>

    -   <span data-ttu-id="00964-116">**InputPackagePath** – appv パッケージへのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="00964-116">**InputPackagePath** – specifies the path to the .appv package</span></span>

    -   <span data-ttu-id="00964-117">**Path** –パッケージの出力ディレクトリを指定します。</span><span class="sxs-lookup"><span data-stu-id="00964-117">**Path** – specifies the output directory for the package.</span></span>

    <span data-ttu-id="00964-118">次の例は、app-v パッケージとインストールメディアを使ってパッケージアクセラレータを作成する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="00964-118">The following example displays how you can create a package accelerator with an .appv package and the installation media:</span></span>

    **<span data-ttu-id="00964-119">AppvPackageAccelerator-InputPackagePath path: &lt; app-v ファイルへのパス &gt; -インストーラーの &lt; 実行可能ファイルへのインストーラーパス- &gt; &lt; 出力パスの path ディレクトリ&gt;</span><span class="sxs-lookup"><span data-stu-id="00964-119">New-AppvPackageAccelerator -InputPackagePath &lt;path to the .appv file&gt; -Installer &lt;path to the installer executable&gt; -Path &lt;directory of the output path&gt;</span></span>**

    <span data-ttu-id="00964-120">**AppvPackageAccelerator**コマンドレットで使用できる追加のオプションパラメーターは、次の一覧に表示されます。</span><span class="sxs-lookup"><span data-stu-id="00964-120">Additional optional parameters that can be used with the **New-AppvPackageAccelerator** cmdlet are displayed in the following list:</span></span>

    -   <span data-ttu-id="00964-121">**AcceleratorDescriptionFile** -ユーザーが作成したパッケージアクセラレータ命令へのパスを指定します。</span><span class="sxs-lookup"><span data-stu-id="00964-121">**AcceleratorDescriptionFile** - specifies the path to user created package accelerator instructions.</span></span> <span data-ttu-id="00964-122">パッケージアクセラレータの手順は、パッケージアクセラレータを使用して作成されたパッケージと共にパッケージ化される **.txt**または **.rtf**の説明ファイルです。</span><span class="sxs-lookup"><span data-stu-id="00964-122">The package accelerator instructions are **.txt** or **.rtf** description files that will be packaged with the package created using the package accelerator.</span></span>

    <span data-ttu-id="00964-123">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="00964-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="00964-124">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="00964-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="00964-125">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="00964-125">Got an App-V issue?</span></span>** <span data-ttu-id="00964-126">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="00964-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="00964-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="00964-127">Related topics</span></span>


[<span data-ttu-id="00964-128">PowerShell を使用した App-V の管理</span><span class="sxs-lookup"><span data-stu-id="00964-128">Administering App-V by Using PowerShell</span></span>](administering-app-v-by-using-powershell.md)

 

 





