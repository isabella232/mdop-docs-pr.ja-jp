---
title: Windows Virtual PC アプリケーションの除外一覧
description: Windows Virtual PC アプリケーションの除外一覧
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823694"
---
# <span data-ttu-id="ead7e-103">Windows Virtual PC アプリケーションの除外一覧</span><span class="sxs-lookup"><span data-stu-id="ead7e-103">Windows Virtual PC Application Exclude List</span></span>


<span data-ttu-id="ead7e-104">場合によっては、MED-V ワークスペースにインストールされているアプリケーションを、ホストコンピューターの [**スタート**] メニューに公開する必要がないことがあります。</span><span class="sxs-lookup"><span data-stu-id="ead7e-104">In some instances, you might not want applications that are installed in the MED-V workspace to be published to the host computer **Start** menu.</span></span> <span data-ttu-id="ead7e-105">このようなアプリケーションは、 [Med-v ワークスペースでアプリケーションを公開し、発行を取り下げる方法](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)の指示に従って、未発行にすることができます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-105">You can unpublish these applications by following the instructions at [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span> <span data-ttu-id="ead7e-106">ただし、プログラムが自動的に更新される場合は、自動的に再公開されることもあります。</span><span class="sxs-lookup"><span data-stu-id="ead7e-106">However, if the program ever automatically updates, it might also be automatically republished.</span></span> <span data-ttu-id="ead7e-107">これにより、アプリケーションの発行を取り消す必要があります。</span><span class="sxs-lookup"><span data-stu-id="ead7e-107">This causes you to have to unpublish the application again.</span></span>

<span data-ttu-id="ead7e-108">Windows 仮想 PC には、ホストの [**スタート**] メニューに公開しないインストール済みのアプリケーションを指定できる "除外リスト" と呼ばれる機能が含まれています。</span><span class="sxs-lookup"><span data-stu-id="ead7e-108">Windows Virtual PC includes a feature known as the "Exclude List" that lets you specify certain installed applications that you do not want published to the host **Start** menu.</span></span> <span data-ttu-id="ead7e-109">"除外リスト" は、HKLM\\Software\\Microsoft\\Windows nt¥ currentversion¥ Virtual Machine\\ vpcvappexcludelist key のゲストレジストリにあり、ホストの [**スタート**] メニューに公開されていないアプリケーションの一覧を示しています。</span><span class="sxs-lookup"><span data-stu-id="ead7e-109">The "Exclude List" is located in the guest registry in the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList key and lists those applications that are not published to the host **Start** menu.</span></span> <span data-ttu-id="ead7e-110">リストされているアプリケーションの自動更新によって自動的に再公開されることはないため、"除外リスト" は、指定したアプリケーションの完全な未発行として考えることができます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-110">You can think of the “Exclude List” as permanently unpublishing the specified applications because any automatic updates to the applications that are listed will not cause them to be automatically republished.</span></span>

## <span data-ttu-id="ead7e-111">Windows 仮想 PC の除外リストを使用してアプリケーションを管理する</span><span class="sxs-lookup"><span data-stu-id="ead7e-111">Managing Applications by Using the Exclude List in Windows Virtual PC</span></span>


****

1.  <span data-ttu-id="ead7e-112">フルスクリーンで MED-V ワークスペースを開きます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-112">Open the MED-V workspace in full screen.</span></span>

    <span data-ttu-id="ead7e-113">Med-v 管理ツールキットを使用して、全画面表示モードで MED-V ワークスペースを開く方法について詳しくは、「 [Med-v ワークスペース構成を表示](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)する」をご覧ください。</span><span class="sxs-lookup"><span data-stu-id="ead7e-113">For information about opening the MED-V workspace in full-screen mode by using the MED-V Administration Toolkit, see [Viewing MED-V Workspace Configurations](viewing-med-v-workspace-configurations.md#bkmk-fullscreen).</span></span> <span data-ttu-id="ead7e-114">または、[**スタート**] をクリックし、[**すべてのプログラム**]、[ **windows 仮想 pc**]、[windows 仮想 pc] の順にクリックして、[ **windows 仮想 pc**] をクリックし、med-v ワークスペースをダブルクリックして、完全な画面で手動で開くことができます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-114">Or you can manually open it in full screen by clicking **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, and then double-click the MED-V workspace.</span></span>

2.  <span data-ttu-id="ead7e-115">[MED-V workspace Windows Virtual PC] ウィンドウで、レジストリエディターを開きます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-115">In the MED-V workspace Windows Virtual PC window, open Registry Editor.</span></span>

    <span data-ttu-id="ead7e-116">[**スタート**] をクリックし、[**実行**] をクリックして、「regedit」と入力します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-116">Click **Start**, click **Run**, and then type regedit.</span></span> <span data-ttu-id="ead7e-117">[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ead7e-117">Then click **OK**.</span></span>

3.  <span data-ttu-id="ead7e-118">レジストリエディターで、HKLM\\Software\\Microsoft\\Windows nt¥のバージョン \ vp¥ # appexcludelist Registry key を見つけます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-118">In Registry Editor, locate the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList registry key.</span></span>

4.  <span data-ttu-id="ead7e-119">インストールされているアプリケーションの新しいレジストリ値を作成します。この値は、ホストコンピューターの [**スタート**] メニューに公開しないようにします。</span><span class="sxs-lookup"><span data-stu-id="ead7e-119">Create a new registry value for the installed application that you do not want published to the host computer **Start** menu.</span></span> <span data-ttu-id="ead7e-120">たとえば、自動的に公開されるプログラム Microsoft Silverlight の発行を停止する場合は、次の手順を実行します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-120">For example, if you want to unpublish the automatically published program Microsoft Silverlight, follow these steps:</span></span>

    1.  <span data-ttu-id="ead7e-121">VPCVAppExcludeList レジストリキーが強調表示されている状態で、[**編集**] をクリックし、[**新規作成**] をクリックして、[**文字列値**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="ead7e-121">With the VPCVAppExcludeList registry key highlighted, click **Edit**, click **New**, and then click **String Value**.</span></span>

    2.  <span data-ttu-id="ead7e-122">新しいレジストリ値の名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-122">Enter the name for the new registry value.</span></span> <span data-ttu-id="ead7e-123">たとえば、Microsoft Silverlight の場合、sllauncher.exe 入力します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-123">For example, for Microsoft Silverlight, you might enter sllauncher.exe.</span></span>

    3.  <span data-ttu-id="ead7e-124">新しいレジストリ値をダブルクリックして、値のデータを入力します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-124">Double-click the new registry value and enter the value data.</span></span>

        <span data-ttu-id="ead7e-125">[値のデータ] は、発行を取り消すコマンドの完全なパスです。</span><span class="sxs-lookup"><span data-stu-id="ead7e-125">The value data is the full path for the command that you want to unpublish.</span></span> <span data-ttu-id="ead7e-126">公開しないアプリケーションの [**スタート**] メニューのショートカットを右クリックして、[**プロパティ**] をクリックすると、完全なパスを確認できます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-126">You can find the full path by right-clicking on the shortcut on the **Start** menu for the application that you do not want published and then clicking **Properties**.</span></span> <span data-ttu-id="ead7e-127">[**ターゲット**] の下にある**ショートカット**タブに完全なパスが表示されます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-127">The full path is listed in the **Shortcut** tab under **Target**.</span></span>

        <span data-ttu-id="ead7e-128">たとえば、Microsoft Silverlight のプログラムでは、完全なパスは "C:\windows/ファイル名 \\ microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe" のようになります。</span><span class="sxs-lookup"><span data-stu-id="ead7e-128">For example, for the program Microsoft Silverlight, the full path might be "C:\\Program Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe."</span></span>

        <span data-ttu-id="ead7e-129">**重要** 必要に応じて、[値データ] フィールドに入力すると、完全パスから引用符が削除されます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-129">**Important** If applicable, remove the quotation marks from the full path when you enter it into the value data field.</span></span>

         

5.  <span data-ttu-id="ead7e-130">レジストリエディターを終了し、MED-V ワークスペース仮想マシンを再起動します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-130">Close Registry Editor and restart the MED-V workspace virtual machine.</span></span>

    <span data-ttu-id="ead7e-131">アプリケーションは、MED-V ワークスペースにまだインストールされていますが、ホストコンピューターの [**スタート**] メニューから削除されています。</span><span class="sxs-lookup"><span data-stu-id="ead7e-131">The application is still installed in the MED-V workspace but is now removed from the host computer **Start** menu.</span></span>

<span data-ttu-id="ead7e-132">また、[VPCVAppExcludeList] キーから対応する値を削除することで、除外されたアプリケーションを host **Start**メニューに再公開することもできます。</span><span class="sxs-lookup"><span data-stu-id="ead7e-132">You can also republish an excluded application to the host **Start** menu by deleting the corresponding value from the VPCVAppExcludeList key.</span></span> <span data-ttu-id="ead7e-133">たとえば、Microsoft Silverlight を再公開するには、レジストリ値 sllauncher.exe を右クリックし、[**削除**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="ead7e-133">For example, to republish Microsoft Silverlight, right-click the registry value sllauncher.exe and select **Delete**.</span></span>

## <span data-ttu-id="ead7e-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ead7e-134">Related topics</span></span>


[<span data-ttu-id="ead7e-135">MED-V テクニカル リファレンス</span><span class="sxs-lookup"><span data-stu-id="ead7e-135">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

[<span data-ttu-id="ead7e-136">MED-V ワークスペースでアプリケーションを公開および公開を取り消す方法</span><span class="sxs-lookup"><span data-stu-id="ead7e-136">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





