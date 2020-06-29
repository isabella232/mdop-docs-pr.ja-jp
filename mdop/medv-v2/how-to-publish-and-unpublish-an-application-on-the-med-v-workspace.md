---
title: MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法
description: MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法
author: dansimp
ms.assetid: fd5a62e9-0577-44d2-ae17-61c0aef78ce8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc8f9579d800aa0e5da0d67e0cd71bcae5e912a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826924"
---
# <span data-ttu-id="bba03-103">MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法</span><span class="sxs-lookup"><span data-stu-id="bba03-103">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>


<span data-ttu-id="bba03-104">アプリケーションが MED-V ワークスペースにインストールされている場合でも、エンドユーザーがアプリを利用できるようになるには、アプリケーションを公開することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bba03-104">Even though an application is installed in a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="bba03-105">既定では、ほとんどのアプリケーションはインストール時に公開され、ショートカットが作成されて有効になります。</span><span class="sxs-lookup"><span data-stu-id="bba03-105">By default, most applications are published at the time that they are installed and shortcuts are created and enabled.</span></span>

<span data-ttu-id="bba03-106">場合によっては、アプリケーションをエンドユーザー (ウイルススキャンソフトウェアなど) で利用できるようにすることなく、MED-V ワークスペースにアプリケーションをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="bba03-106">In some cases, you might want to install applications on the MED-V workspace without making them available to the end user, for example, virus-scanning software.</span></span> <span data-ttu-id="bba03-107">同様に、以前はエンドユーザーが利用できなかった MED-V ワークスペースにインストールされているアプリケーションを公開することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bba03-107">Similarly, there are occasions in which you want to publish an application that is installed on the MED-V workspace that was previously unavailable to the end user.</span></span> <span data-ttu-id="bba03-108">たとえば、インストールによって [**スタート**] メニューにショートカットが自動的に作成されない場合は、インストールされているアプリケーションを公開しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="bba03-108">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span>

<span data-ttu-id="bba03-109">**重要** UNC パスをサポートしていないアプリケーションを公開する場合は、そのアプリケーションをドライブにマップすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="bba03-109">**Important** If you publish an application that does not support UNC paths, we recommend that you map the application to a drive.</span></span>

 

<span data-ttu-id="bba03-110">次のいずれかのタスクを実行することによって、展開された MED-V ワークスペースにアプリケーションを公開または非公開にすることができます。</span><span class="sxs-lookup"><span data-stu-id="bba03-110">You can publish or unpublish applications to a deployed MED-V workspace by performing one of the following tasks:</span></span>

**<span data-ttu-id="bba03-111">インストールされているアプリケーションを公開する、または発行を取り消すには</span><span class="sxs-lookup"><span data-stu-id="bba03-111">To publish or unpublish an installed application</span></span>**

1.  <span data-ttu-id="bba03-112">展開された MED-V ワークスペースでアプリケーションを公開するには、そのアプリケーションのショートカットを仮想マシン上の次のフォルダーにコピーします。</span><span class="sxs-lookup"><span data-stu-id="bba03-112">To publish an application on a deployed MED-V workspace, copy a shortcut for that application to the following folder on the virtual machine:</span></span>

    <span data-ttu-id="bba03-113">C:\\Documents と Settings\\All Users\\Start メニュー</span><span class="sxs-lookup"><span data-stu-id="bba03-113">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="bba03-114">必要に応じて、グループポリシーまたは ESD システムを使って、そのアプリケーションのショートカットを [すべての Users\\Start] メニューフォルダーにコピーするスクリプトを展開します。</span><span class="sxs-lookup"><span data-stu-id="bba03-114">If it is necessary, use Group Policy or an ESD system to deploy a script that copies the shortcut for that application to the All Users\\Start Menu folder.</span></span>

2.  <span data-ttu-id="bba03-115">展開された MED-V ワークスペースでアプリケーションの発行を取り消すには、仮想マシン上の次のフォルダーからそのアプリケーションのショートカットを削除します。</span><span class="sxs-lookup"><span data-stu-id="bba03-115">To unpublish an application on a deployed MED-V workspace, delete the shortcut for that application from the following folder on the virtual machine:</span></span>

    <span data-ttu-id="bba03-116">C:\\Documents と Settings\\All Users\\Start メニュー</span><span class="sxs-lookup"><span data-stu-id="bba03-116">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="bba03-117">必要な場合は、グループポリシーまたは ESD システムを使用して、[すべての Users\\Start] メニューフォルダーからそのアプリケーションのショートカットを削除するスクリプトを展開します。</span><span class="sxs-lookup"><span data-stu-id="bba03-117">If it is necessary, use Group Policy or an ESD system to deploy a script that deletes the shortcut for that application from the All Users\\Start Menu folder.</span></span>

    <span data-ttu-id="bba03-118">**注** 多くの場合、アプリケーションをアンインストールすると、ホストコンピューターの [**スタート**] メニューからショートカットが自動的に削除されます。</span><span class="sxs-lookup"><span data-stu-id="bba03-118">**Note** Frequently, the shortcut is automatically deleted from the host computer **Start** menu when you uninstall the application.</span></span> <span data-ttu-id="bba03-119">ただし、共有コンピューターのすべてのユーザーに対して構成されている MED-V ワークスペースなど、場合によっては、アプリケーションをアンインストールした後に、**スタート**メニューのショートカットを手動で削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="bba03-119">However, in some cases, such as for a MED-V workspace that is configured for all users of a shared computer, you might have to manually delete the shortcut on the **Start** menu after the application is uninstalled.</span></span> <span data-ttu-id="bba03-120">エンドユーザーは、ショートカットを右クリックして [**削除**] を選ぶことで、これを行うことができます。</span><span class="sxs-lookup"><span data-stu-id="bba03-120">The end-user can do this by right-clicking the shortcut and selecting **Delete**.</span></span>

     

<span data-ttu-id="bba03-121">アプリケーションが公開されていること、または未公開であることをテストするには、MED-V ワークスペースで対応するショートカットが使用可能かどうかを確認します。</span><span class="sxs-lookup"><span data-stu-id="bba03-121">To test that the application was published or unpublished, verify on the MED-V workspace whether the corresponding shortcut is available or not.</span></span>

<span data-ttu-id="bba03-122">**注** Windows XP SP3 に含まれていて、仮想マシンの [スタート] メニューフォルダーに配置されているアプリケーションは、ホストに自動的には公開されません。</span><span class="sxs-lookup"><span data-stu-id="bba03-122">**Note** Applications that are included in Windows XP SP3 and are located in the virtual machine Start Menu folder are not automatically published to the host.</span></span> <span data-ttu-id="bba03-123">自動発行をブロックするレジストリ設定によって制御されます。</span><span class="sxs-lookup"><span data-stu-id="bba03-123">They are controlled by registry settings that block automatic publishing.</span></span> <span data-ttu-id="bba03-124">詳細については、「 [Windows 仮想 PC アプリケーションの除外リスト](windows-virtual-pc-application-exclude-list.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="bba03-124">For more information, see [Windows Virtual PC Application Exclude List](windows-virtual-pc-application-exclude-list.md).</span></span>

 

**<span data-ttu-id="bba03-125">コントロールパネルの項目を公開するには</span><span class="sxs-lookup"><span data-stu-id="bba03-125">To publish Control Panel items</span></span>**

1.  <span data-ttu-id="bba03-126">ターゲットが、C:\\WINDOWS\\system32\\appwiz.cpl などの項目の名前である仮想マシンにショートカットを作成します。</span><span class="sxs-lookup"><span data-stu-id="bba03-126">Create a shortcut on the virtual machine where the target is the name of the item, such as C:\\WINDOWS\\system32\\appwiz.cpl.</span></span>

    <span data-ttu-id="bba03-127">ショートカットは、"%ALLUSERSPROFILE%\\Start Menu\\" フォルダーまたはそのサブフォルダーのいずれかに作成または移動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba03-127">The shortcut must be either created in or moved to the "%ALLUSERSPROFILE%\\Start Menu\\" folder or one of its subfolders.</span></span>

    <span data-ttu-id="bba03-128">ホストコンピューターには、ホストのスタートメニューフォルダー内の対応する場所にアイテムが公開されます。</span><span class="sxs-lookup"><span data-stu-id="bba03-128">The item will be published to the host computer in the corresponding location in the host Start Menu folder.</span></span>

2.  <span data-ttu-id="bba03-129">ホストのアイテムのショートカットを開始します。</span><span class="sxs-lookup"><span data-stu-id="bba03-129">Start the shortcut for the item in the host.</span></span>

<span data-ttu-id="bba03-130">**注意** ショートカットを作成する場合は、% SystemRoot% \\control.exe を指定しないでください。</span><span class="sxs-lookup"><span data-stu-id="bba03-130">**Caution** When you create the shortcut, do not specify %SystemRoot%\\control.exe.</span></span> <span data-ttu-id="bba03-131">このアプリケーションは、自動発行をブロックするレジストリ設定に含まれているため、公開されません。</span><span class="sxs-lookup"><span data-stu-id="bba03-131">This application will not be published because it is contained in the registry settings that block automatic publishing.</span></span>

 

**<span data-ttu-id="bba03-132">MED-V でアプリケーションの自動発行を処理する方法</span><span class="sxs-lookup"><span data-stu-id="bba03-132">How MED-V handles automatic application publishing</span></span>**

1.  <span data-ttu-id="bba03-133">アプリケーションの発行中、MED-V はゲスト仮想マシンからホストコンピューターにショートカットをコピーします。ゲストのフォルダー階層と一致させます。</span><span class="sxs-lookup"><span data-stu-id="bba03-133">During application publishing, MED-V copies the shortcuts from the guest virtual machine to the host computer by trying to match the folder hierarchy that exists in the guest.</span></span> <span data-ttu-id="bba03-134">これにより、MED-V は次の手順に従ってゲストからホストへのショートカットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bba03-134">By doing this, MED-V copies shortcuts from the guest to the host by following these steps:</span></span>

    1.  <span data-ttu-id="bba03-135">MED-V は、ショートカットが存在するゲストのフォルダーと同じ名前のホストコンピューターで、[スタートメニュー] の下にあるフォルダーを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="bba03-135">MED-V tries to locate a folder under Start Menu\\Programs in the host computer that is named the same as the folder in the guest where the shortcut resides.</span></span>

    2.  <span data-ttu-id="bba03-136">一致するフォルダーがない場合、MED-V は、ショートカットが存在するゲストのフォルダーと同じ名前の、ホストのスタートメニューフォルダー内のフォルダーを見つけようとします。</span><span class="sxs-lookup"><span data-stu-id="bba03-136">If there is no matching folder, MED-V then tries to locate a folder in the host Start Menu folder that is named the same as the folder in the guest where the shortcut resides.</span></span>

    3.  <span data-ttu-id="bba03-137">一致するフォルダーがない場合、MED-V は、ホスト上の既定のフォルダーのショートカットをコピーします。 [スタートメニュー] \\ [プログラム] フォルダーを選びます。</span><span class="sxs-lookup"><span data-stu-id="bba03-137">If there is no matching folder, MED-V copies the shortcut to the default folder on the host, the Start Menu\\Programs folder.</span></span>

2.  <span data-ttu-id="bba03-138">アプリケーション公開プロセスの例:</span><span class="sxs-lookup"><span data-stu-id="bba03-138">Example of application publishing process:</span></span>

    1.  <span data-ttu-id="bba03-139">アプリケーションのショートカットがゲストの Start Menu\\Programs\\AppShortcuts フォルダーに公開されている場合、MED-V はホストコンピューターで Start Menu\\Programs\\ AppShortcuts フォルダーを探し、見つかった場合は、そのフォルダーへのショートカットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bba03-139">If an application shortcut is published to the Start Menu\\Programs\\AppShortcuts folder in the guest, then MED-V looks in the host computer for a Start Menu\\Programs\\ AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    2.  <span data-ttu-id="bba03-140">フォルダーが見つからない場合、MED-V はホストコンピューターで [スタートメニュー] ¥ [appshortcut] フォルダーを探し、見つかった場合はそのフォルダーへのショートカットをコピーします。</span><span class="sxs-lookup"><span data-stu-id="bba03-140">If the folder is not found, then MED-V looks in the host computer for a Start Menu\\AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    3.  <span data-ttu-id="bba03-141">フォルダーが見つからない場合は、MED によって [スタートメニュー] ¥ [プログラム] フォルダーにショートカットがコピーされます。</span><span class="sxs-lookup"><span data-stu-id="bba03-141">If the folder is not found, then MED-V copies the shortcut to the Start Menu\\Programs folder.</span></span>

<span data-ttu-id="bba03-142">**注** ショートカットをコピーするには、MED-V のホストコンピューターのスタートメニューフォルダーにフォルダーが既に存在している必要があります。</span><span class="sxs-lookup"><span data-stu-id="bba03-142">**Note** A folder must already exist in the host computer Start Menu folder for MED-V to copy the shortcut there.</span></span> <span data-ttu-id="bba03-143">MED-V はまだ存在しない場合はフォルダーを作成しません。</span><span class="sxs-lookup"><span data-stu-id="bba03-143">MED-V does not create the folder if it does not already exist.</span></span>

 

## <span data-ttu-id="bba03-144">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bba03-144">Related topics</span></span>


[<span data-ttu-id="bba03-145">MED-V ワークスペースでのアプリケーションのインストールと削除</span><span class="sxs-lookup"><span data-stu-id="bba03-145">Installing and Removing an Application on the MED-V Workspace</span></span>](installing-and-removing-an-application-on-the-med-v-workspace.md)

[<span data-ttu-id="bba03-146">MED-V ワークスペースのソフトウェア更新プログラムの管理</span><span class="sxs-lookup"><span data-stu-id="bba03-146">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

[<span data-ttu-id="bba03-147">Windows Virtual PC アプリケーションの除外一覧</span><span class="sxs-lookup"><span data-stu-id="bba03-147">Windows Virtual PC Application Exclude List</span></span>](windows-virtual-pc-application-exclude-list.md)

 

 





