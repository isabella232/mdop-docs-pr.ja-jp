---
title: MED-V コンポーネントをアンインストールする方法
description: MED-V コンポーネントをアンインストールする方法
author: dansimp
ms.assetid: c121dd27-6b2f-4d41-a21a-c6e8608c5c41
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 514ec8227b858b34289ca2330f7cfb038bc4f00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813027"
---
# <span data-ttu-id="a167a-103">MED-V コンポーネントをアンインストールする方法</span><span class="sxs-lookup"><span data-stu-id="a167a-103">How to Uninstall the MED-V Components</span></span>


<span data-ttu-id="a167a-104">状況によっては、企業から Microsoft Enterprise デスクトップ仮想化 (MED-V) 2.0 コンポーネントのすべてまたは一部をアンインストールすることが必要な場合があります。</span><span class="sxs-lookup"><span data-stu-id="a167a-104">Under certain circumstances, you might want to uninstall all or part of the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components from your enterprise.</span></span> <span data-ttu-id="a167a-105">たとえば、すべてのアプリケーションオペレーティングシステムの互換性の問題を解決した場合、またはエンタープライズで別の MED-V ワークスペースを展開したい場合があります。</span><span class="sxs-lookup"><span data-stu-id="a167a-105">For example, you have resolved all application operating system compatibility issues, or you want to deploy a different MED-V workspace in your enterprise.</span></span>

<span data-ttu-id="a167a-106">通常、Windows ベースのインストーラーを使用して、電子ソフトウェア配布 (ESD) システムを構成して、MED-V コンポーネントをアンインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="a167a-106">Typically, you can configure your electronic software distribution (ESD) system to uninstall the MED-V components by using a Windows-based Installer.</span></span> <span data-ttu-id="a167a-107">または、すべてまたは一部の MED-V コンポーネントを手動でアンインストールすることもできます。</span><span class="sxs-lookup"><span data-stu-id="a167a-107">Alternately, you can uninstall all or some MED-V components manually.</span></span>

<span data-ttu-id="a167a-108">**重要** MED-V Host Agent をアンインストールする前に、インストールされている MED-V ワークスペースをアンインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a167a-108">**Important** Before you can uninstall the MED-V Host Agent, you must first uninstall any installed MED-V workspace.</span></span>

 

<span data-ttu-id="a167a-109">エンタープライズから MED-V コンポーネントをアンインストールするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="a167a-109">Use the following procedures to uninstall the MED-V components from your enterprise.</span></span>

**<span data-ttu-id="a167a-110">電子ソフトウェア配布システムを使用して MED-V をアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="a167a-110">To uninstall MED-V using an electronic software distribution System</span></span>**

1.  <span data-ttu-id="a167a-111">ESD システムを使って、アンインストールするすべての MED-V ワークスペースの uninstall.exe 実行可能プログラムを呼び出すスクリプトを配布します。</span><span class="sxs-lookup"><span data-stu-id="a167a-111">Use your ESD system to distribute a script that invokes the uninstall.exe executable program for every MED-V workspace that you want to uninstall.</span></span> <span data-ttu-id="a167a-112">ファイルは C:\\ProgramData\\Microsoft\\Medv\\Workspace. にあります。</span><span class="sxs-lookup"><span data-stu-id="a167a-112">The file is located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span> <span data-ttu-id="a167a-113">エンドユーザーに対してアンインストールが認識されないように、実行可能ファイルをサイレントモードで実行するようにフラグを設定することができます。</span><span class="sxs-lookup"><span data-stu-id="a167a-113">You can set a flag to run the uninstall executable program silently so that end users are unaware of the uninstallation.</span></span>

2.  <span data-ttu-id="a167a-114">パッケージを作成して、MED-V ワークスペースがアンインストールされた各コンピューターに MED-V Host Agent インストールファイルを配布します。</span><span class="sxs-lookup"><span data-stu-id="a167a-114">Create a package to distribute the MED-V Host Agent installation file to each computer on which a MED-V workspace was uninstalled.</span></span> <span data-ttu-id="a167a-115">サイレントモードでアンインストールを実行するようにパッケージを構成します。</span><span class="sxs-lookup"><span data-stu-id="a167a-115">Configure the package to run the uninstallation in silent mode.</span></span>

<span data-ttu-id="a167a-116">ESD クライアントは、新しいパッケージが利用可能になるタイミングを認識し、定義および要件に従ってパッケージのアンインストールを開始します。</span><span class="sxs-lookup"><span data-stu-id="a167a-116">The ESD client recognizes when the new packages are available and starts to uninstall the packages per the definition and requirements.</span></span>

**<span data-ttu-id="a167a-117">MED-V ワークスペースを手動でアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="a167a-117">To manually uninstall a MED-V workspace</span></span>**

1.  <span data-ttu-id="a167a-118">ホストコンピューターで [**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**プログラムと機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-118">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="a167a-119">[**プログラムと機能**] ウィンドウで、削除する med-v ワークスペースを選択し、[**アンインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-119">In the **Programs and Features** window, select the MED-V workspace that you want to remove, and then click **Uninstall**.</span></span> <span data-ttu-id="a167a-120">(MED-V ワークスペースの名前は "MED-V Workspace- &lt;*ワークスペース \ _name* &gt; ")。</span><span class="sxs-lookup"><span data-stu-id="a167a-120">(The MED-V workspace is named "MED-V Workspace - &lt;*workspace\_name*&gt;").</span></span> <span data-ttu-id="a167a-121">&lt;*ワークスペース \ _name* &gt; **セットアップウィザード**が開きます。</span><span class="sxs-lookup"><span data-stu-id="a167a-121">The &lt;*workspace\_name*&gt; **Setup Wizard** opens.</span></span>

3.  <span data-ttu-id="a167a-122">**セットアップウィザード**で、[**次へ**] をクリックし、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-122">On the **Setup Wizard**, click **Next**, and then click **Remove**.</span></span>

4.  <span data-ttu-id="a167a-123">必要に応じて、このチェックボックスをオンにして、MED-V で作成されたマスター VHD ディスクと差分ディスクを削除します。</span><span class="sxs-lookup"><span data-stu-id="a167a-123">If you prefer, select the check box to delete the master VHD disk and differencing disks created by MED-V.</span></span> <span data-ttu-id="a167a-124">これは必須ではありませんが、アンインストールが完了した後にディスク領域を解放します。</span><span class="sxs-lookup"><span data-stu-id="a167a-124">This is not required, but frees disk space after the uninstallation finishes.</span></span>

5.  <span data-ttu-id="a167a-125">[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-125">Click **Remove**.</span></span>

    <span data-ttu-id="a167a-126">**注** MED-V が現在実行されている場合は、ダイアログボックスが表示され、終了するかどうかを確認するメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a167a-126">**Note** If MED-V is currently running, a dialog box appears and prompts you whether you want to shut it down.</span></span> <span data-ttu-id="a167a-127">アンインストールを続行するには、[**はい**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-127">Click **Yes** to continue with the uninstallation.</span></span> <span data-ttu-id="a167a-128">アンインストールをキャンセルするには、[**いいえ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-128">Click **No** to cancel the uninstallation.</span></span>

     

<span data-ttu-id="a167a-129">または、 `uninstall.exe` 通常は C:\\ProgramData\\Microsoft\\Medv\\Workspace. にあるファイルを実行して、med-v ワークスペースを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="a167a-129">Alternately, you can remove a MED-V workspace by running the `uninstall.exe` file, typically located at C:\\ProgramData\\Microsoft\\Medv\\Workspace.</span></span>

**<span data-ttu-id="a167a-130">MED-V ホストエージェントを手動でアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="a167a-130">To manually uninstall the MED-V Host Agent</span></span>**

1.  <span data-ttu-id="a167a-131">Windows 7 のホストコンピューターで、[**スタート**] をクリックし、[**コントロールパネル**]、[**プログラムと機能**] の順にクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-131">On the Windows 7 host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="a167a-132">[**プログラムと機能**] ウィンドウで、[ **med-v Host Agent**] を選び、[**アンインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-132">In the **Programs and Features** window, select **MED-V Host Agent**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="a167a-133">Windows Installer は、MED-V ホストエージェントを削除します。</span><span class="sxs-lookup"><span data-stu-id="a167a-133">The Windows Installer removes the MED-V Host Agent.</span></span>

    <span data-ttu-id="a167a-134">**注** MED-V のワークスペースをアンインストールする前に、MED-V ホストエージェントをアンインストールしようとすると、まず MED-V ワークスペースをアンインストールする必要があることを示すダイアログボックスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="a167a-134">**Note** If you try to uninstall the MED-V Host Agent before you uninstall the MED-V workspace, a dialog box appears that states that you must first uninstall the MED-V workspace.</span></span> <span data-ttu-id="a167a-135">**[OK]** をクリックして続行します。</span><span class="sxs-lookup"><span data-stu-id="a167a-135">Click **OK** to continue.</span></span>

     

**<span data-ttu-id="a167a-136">MED-V ワークスペースパッケージャーを手動でアンインストールするには</span><span class="sxs-lookup"><span data-stu-id="a167a-136">To manually uninstall the MED-V Workspace Packager</span></span>**

1.  <span data-ttu-id="a167a-137">ホストコンピューターで [**スタート**] をクリックし、[**コントロールパネル**] をクリックして、[**プログラムと機能**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-137">On the host computer, click **Start**, click **Control Panel**, and then click **Programs and Features**.</span></span>

2.  <span data-ttu-id="a167a-138">[**プログラムと機能**] ウィンドウで、[ **med-v Workspace パッケージャー**] を選択し、[**アンインストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="a167a-138">In the **Programs and Features** window, select **MED-V Workspace Packager**, and then click **Uninstall**.</span></span>

    <span data-ttu-id="a167a-139">Windows インストーラーは、MED-V ワークスペースパッケージャーを削除します。</span><span class="sxs-lookup"><span data-stu-id="a167a-139">The Windows Installer removes the MED-V Workspace Packager.</span></span>

    <span data-ttu-id="a167a-140">**注** MED-V Workspace パッケージャーは、展開された MED-V ワークスペースに影響を与えずに、いつでもアンインストールできます。</span><span class="sxs-lookup"><span data-stu-id="a167a-140">**Note** You can uninstall the MED-V Workspace Packager at any time without affecting any deployed MED-V workspaces.</span></span>

     

## <span data-ttu-id="a167a-141">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a167a-141">Related topics</span></span>


[<span data-ttu-id="a167a-142">MED-V コンポーネントを展開する</span><span class="sxs-lookup"><span data-stu-id="a167a-142">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)

 

 





