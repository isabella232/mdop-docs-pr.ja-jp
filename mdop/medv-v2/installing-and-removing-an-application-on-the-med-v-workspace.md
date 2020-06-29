---
title: MED-V ワークスペースでのアプリケーションのインストールと削除
description: MED-V ワークスペースでのアプリケーションのインストールと削除
author: dansimp
ms.assetid: 24f32720-51ab-4385-adfe-4f5a65e45fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 22cb98c167b53b1b206b8b5be2ba18fc0fba4f06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10827217"
---
# <span data-ttu-id="e06f5-103">MED-V ワークスペースでのアプリケーションのインストールと削除</span><span class="sxs-lookup"><span data-stu-id="e06f5-103">Installing and Removing an Application on the MED-V Workspace</span></span>


<span data-ttu-id="e06f5-104">ホストオペレーティングシステムに対応していないアプリケーションは、MED-V ワークスペースで実行し、ホストコンピューターから開いた場合と同じ方法 ([**スタート**] メニュー)、または localhost ショートカットを使用して、med-v ワークスペースで開くことができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-104">Applications that are incompatible with the host operating system can be run in the MED-V workspace and opened in the MED-V workspace in the same manner in which they are opened from the host computer, on the **Start** menu or by using a localhost shortcut.</span></span>

<span data-ttu-id="e06f5-105">MED-V ワークスペースを展開した後は、MED-V ワークスペースにアプリケーションをインストールして削除するためのさまざまなオプションが用意されています。</span><span class="sxs-lookup"><span data-stu-id="e06f5-105">After you have deployed a MED-V workspace, you have several different options available to you for installing and removing applications in the MED-V workspace.</span></span> <span data-ttu-id="e06f5-106">次のようなオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-106">These options include the following:</span></span>

-   [<span data-ttu-id="e06f5-107">グループポリシーを使用する</span><span class="sxs-lookup"><span data-stu-id="e06f5-107">Using Group Policy</span></span>](#bkmk-grouppolicy)

-   [<span data-ttu-id="e06f5-108">電子ソフトウェア配布システムを使用する</span><span class="sxs-lookup"><span data-stu-id="e06f5-108">Using an Electronic Software Distribution System</span></span>](#bkmk-esd)

-   [<span data-ttu-id="e06f5-109">Application Virtualization (APP-V) を使用する</span><span class="sxs-lookup"><span data-stu-id="e06f5-109">Using Application Virtualization (APP-V)</span></span>](#bkmk-appv)

-   [<span data-ttu-id="e06f5-110">コアイメージの更新</span><span class="sxs-lookup"><span data-stu-id="e06f5-110">Updating the Core Image</span></span>](#bkmk-coreimage)

<span data-ttu-id="e06f5-111">**重要** インストールされているアプリケーションがホストに自動的に公開されるようにするには、すべての**ユーザー**の仮想マシンにアプリケーションをインストールします。</span><span class="sxs-lookup"><span data-stu-id="e06f5-111">**Important** To make sure that an installed application is automatically published to the host, install the application on the virtual machine for **All Users**.</span></span> <span data-ttu-id="e06f5-112">アプリケーションの発行の詳細については、「 [Med-v ワークスペースでアプリケーションを公開および公開解除する方法](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e06f5-112">For more information about application publishing, see [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span>

 

<span data-ttu-id="e06f5-113">**ヒント** MED-V は、MED-V ワークスペースの Internet Explorer で Microsoft Word 文書をダブルクリックするなど、コンテンツ処理のゲスト間のリダイレクションをサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="e06f5-113">**Tip** MED-V does not support guest-to-host redirection for content handling, such as double-clicking a Microsoft Word document in Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="e06f5-114">したがって、Microsoft Word などの必須アプリケーションは、エンドユーザーが想定する既定のコンテンツ処理機能を提供するために、MED-V ワークスペースにインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-114">Therefore, the required applications, such as Microsoft Word, must be installed in MED-V workspace to provide the default content handling functionality that an end user might expect.</span></span>

 

## <a href="" id="bkmk-grouppolicy"></a> <span data-ttu-id="e06f5-115">グループポリシーを使用したアプリケーションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="e06f5-115">Adding and Removing Applications by Using Group Policy</span></span>


<span data-ttu-id="e06f5-116">グループポリシーおよびグループポリシーオブジェクトを使用して、組織内のすべてまたは一部の MED-V ワークスペースにアプリケーションを割り当てたり公開したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-116">You can use Group Policy and Group Policy objects to assign or publish applications to all or some MED-V workspaces in your enterprise.</span></span> <span data-ttu-id="e06f5-117">割り当てられたアプリケーションの場合、エンドユーザーがコンピューターにログオンすると、アプリは [**スタート**] メニューに表示されます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-117">For assigned applications, when an end user logs on to their computer, the application appears on the **Start** menu.</span></span> <span data-ttu-id="e06f5-118">初めて新しいアプリケーションを選択すると、アプリケーションがインストールされて使用できるようになります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-118">When they select the new application for the first time, the application installs and is ready for use.</span></span> <span data-ttu-id="e06f5-119">公開されたアプリケーションの場合、アプリは [**スタート**] メニューに表示されません。</span><span class="sxs-lookup"><span data-stu-id="e06f5-119">For published applications, the application does not appear on the **Start** menu.</span></span> <span data-ttu-id="e06f5-120">この機能は、エンドユーザーが**コントロールパネル**の [**プログラムの追加と削除**] を使用するか、アプリケーションに関連付けられているファイルを開くことによってのみ、インストールできます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-120">It is only available for the end user to install by using **Add or Remove Programs** in **Control Panel** or by opening a file that is associated with the application.</span></span>

<span data-ttu-id="e06f5-121">また、同じ方法でグループポリシーとグループポリシーオブジェクトを使用して、MED-V ワークスペースからアプリケーションを削除することもできます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-121">You can also use Group Policy and Group Policy objects in the same manner to remove applications from the MED-V workspace.</span></span>

<span data-ttu-id="e06f5-122">グループポリシーを使用してアプリケーションを追加および削除する方法の詳細については、「[グループポリシーソフトウェアインストール](https://go.microsoft.com/fwlink/?LinkId=195931)()」を参照してください https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="e06f5-122">For more information about how to add and remove applications by using Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

## <a href="" id="bkmk-esd"></a> <span data-ttu-id="e06f5-123">ESD システムを使用したアプリケーションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="e06f5-123">Adding and Removing Applications by Using an ESD System</span></span>


<span data-ttu-id="e06f5-124">電子ソフトウェア配布 (ESD) システムは、ネットワーク接続を介して多くの異なるコンピューターにソフトウェアやその他の情報を効率的に展開するように設計されています。</span><span class="sxs-lookup"><span data-stu-id="e06f5-124">An electronic software distribution (ESD) system is designed to efficiently deploy software and other information to many different computers over network connections.</span></span> <span data-ttu-id="e06f5-125">組織が ESD システムを使ってソフトウェアを展開している場合は、物理コンピューターにアプリケーションを追加したり、削除したりするときと同じように、アプリを使用して、MED-V ワークスペースでアプリケーションを追加および削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-125">If your organization uses an ESD system to deploy software, you can use it to add and remove applications on MED-V workspaces just as you add and remove applications on physical computers.</span></span>

## <a href="" id="bkmk-appv"></a> <span data-ttu-id="e06f5-126">APP-V を使用したアプリケーションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="e06f5-126">Adding and Removing Applications by Using APP-V</span></span>


<span data-ttu-id="e06f5-127">Microsoft Application Virtualization (App-v) には、アプリケーションをエンドユーザーのコンピューターで利用できるようにする管理機能が用意されています。これらのコンピューターにアプリケーションを直接インストールする必要はありません。</span><span class="sxs-lookup"><span data-stu-id="e06f5-127">Microsoft Application Virtualization (App-V) provides the administrative capability to make applications available to end-user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="e06f5-128">たとえば、Windows XP で App-v を使ってシーケンスしたアプリケーションが組織に存在していて、それを再設定すると、Windows 7 への移行が遅延する場合があります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-128">You might want to use MED-V and App-V together if, for example, your organization has applications that you sequenced with App-V in Windows XP, and re-sequencing them would delay your migration to Windows 7.</span></span>

<span data-ttu-id="e06f5-129">MED-V と App-v を併用すると、展開された MED-V ワークスペースで仮想アプリケーションを追加したり、削除したりできます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-129">You can use MED-V together with App-V to add and remove virtual applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="e06f5-130">この方法でアプリケーションを管理するには、まず MED-V ゲストオペレーティングシステムに App-v agent をインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-130">To manage applications in this manner, you must first install the App-V agent on the MED-V guest operating system.</span></span> <span data-ttu-id="e06f5-131">次に、MED-V ワークスペースで App-v を使用して、仮想アプリケーションを追加し、削除することができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-131">You can then use App-V in the MED-V workspace to add and remove the virtual applications.</span></span>

<span data-ttu-id="e06f5-132">App-v をインストールして使用する方法については、「 [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="e06f5-132">For information about how to install and use App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

<span data-ttu-id="e06f5-133">**重要** MED-V ワークスペースに発行する app-v アプリケーションには、ホストコンピューターからゲスト仮想マシンにリダイレクトできないファイルの種類の関連付けが含まれています。</span><span class="sxs-lookup"><span data-stu-id="e06f5-133">**Important** App-V applications that you publish to the MED-V workspace have file-type associations that cannot redirect from the host computer to the guest virtual machine.</span></span> <span data-ttu-id="e06f5-134">ただし、エンドユーザーは [**ファイル**] をクリックし、公開された app-v アプリケーションで [**開く**] をクリックすることで、これらのファイルの種類に引き続きアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-134">However, the end user can still access these file types by clicking **File**, and then by clicking **Open** on the published App-V application.</span></span>

<span data-ttu-id="e06f5-135">これらのファイルの種類の関連付けのリダイレクトを強制するには、ゲスト仮想マシンのコマンドプロンプトで次のように入力して、マップされたファイルの種類の関連付けに対して query App-v を実行します。 **sftmime/QUERY OBJ: 型**。</span><span class="sxs-lookup"><span data-stu-id="e06f5-135">To force redirection of those file-type associations, query App-V for mapped file type associations by typing the following at a command prompt in the guest virtual machine: **sftmime /QUERY OBJ:TYPE**.</span></span> <span data-ttu-id="e06f5-136">次に、これらのファイルの種類の関連付けをホストコンピューターにマップします。</span><span class="sxs-lookup"><span data-stu-id="e06f5-136">Then, map those file type associations in the host computer.</span></span>

 

## <a href="" id="bkmk-coreimage"></a> <span data-ttu-id="e06f5-137">コアイメージに対するアプリケーションの追加と削除</span><span class="sxs-lookup"><span data-stu-id="e06f5-137">Adding and Removing Applications on the Core Image</span></span>


<span data-ttu-id="e06f5-138">MED-V のベストプラクティスとは見なされませんが、コアイメージ上でアプリケーションを直接追加したり、削除したりすることができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-138">Although not considered a MED-V best practice, you can add and remove applications directly on the core image.</span></span> <span data-ttu-id="e06f5-139">アプリケーションを追加または削除した後、展開したときと同じように、MED-V ワークスペースをエンタープライズに再展開することができます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-139">After you have added or removed an application, you can redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

<span data-ttu-id="e06f5-140">コアイメージ上のアプリケーションを追加または削除する方法の詳細については、「 [Windows 仮想 PC イメージにアプリケーションをインストール](installing-applications-on-a-windows-virtual-pc-image.md)する」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="e06f5-140">For more information about how to add or remove applications on the core image, see [Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md).</span></span>

<span data-ttu-id="e06f5-141">**重要** この方法では、この方法でアプリケーションを管理することはお勧めしません。</span><span class="sxs-lookup"><span data-stu-id="e06f5-141">**Important** We do not recommend this method of managing applications.</span></span> <span data-ttu-id="e06f5-142">コアイメージ上のアプリケーションを追加または削除して、MED-V ワークスペースをエンタープライズに再展開する場合は、最初にセットアップをもう一度実行する必要があります。仮想マシンに保存されたデータはすべて失われます。</span><span class="sxs-lookup"><span data-stu-id="e06f5-142">If you add or remove applications on the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved on the virtual machine is lost.</span></span>

 

<span data-ttu-id="e06f5-143">**注** アプリケーションが MED-V ワークスペースにインストールされている場合でも、エンドユーザーがアプリを利用できるようになるには、アプリケーションを公開することが必要になる場合もあります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-143">**Note** Even though an application is installed into a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="e06f5-144">たとえば、インストールによって [**スタート**] メニューにショートカットが自動的に作成されない場合は、インストールされているアプリケーションを公開しなければならない場合があります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-144">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span> <span data-ttu-id="e06f5-145">同様に、アプリケーションの発行を取り消すには、[**スタート**] メニューからショートカットを手動で削除する必要がある場合があります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-145">Likewise, to unpublish an application, you might have to manually remove a shortcut from the **Start** menu.</span></span>

<span data-ttu-id="e06f5-146">既定では、ほとんどのアプリケーションはインストール時に公開されます。ショートカットは、自動的に作成され、有効になります。</span><span class="sxs-lookup"><span data-stu-id="e06f5-146">By default, most applications are published at the time that they are installed, when shortcuts are automatically created and enabled.</span></span>

 

## <span data-ttu-id="e06f5-147">関連トピック</span><span class="sxs-lookup"><span data-stu-id="e06f5-147">Related topics</span></span>


[<span data-ttu-id="e06f5-148">アプリケーションの公開をテストする方法</span><span class="sxs-lookup"><span data-stu-id="e06f5-148">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="e06f5-149">MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法</span><span class="sxs-lookup"><span data-stu-id="e06f5-149">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





