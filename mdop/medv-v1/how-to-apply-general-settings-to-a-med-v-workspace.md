---
title: MED-V ワークスペースに全般設定を適用する方法
description: MED-V ワークスペースに全般設定を適用する方法
author: dansimp
ms.assetid: 6152dced-e301-4fa2-bfa0-aecf3c23f23a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 176564ae1d22b27a24625d988f46c9746b291748
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826537"
---
# <span data-ttu-id="121c5-103">MED-V ワークスペースに全般設定を適用する方法</span><span class="sxs-lookup"><span data-stu-id="121c5-103">How to Apply General Settings to a MED-V Workspace</span></span>


<span data-ttu-id="121c5-104">一般的な設定では、med-v ワークスペースがシームレスな統合と完全なデスクトップモードのどちらで表示されるかを定義することで、MED-V ワークスペースを操作するときの基本的なユーザーエクスペリエンスを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="121c5-104">The general settings enable you to configure the basic user experience when working with a MED-V workspace, by defining whether the MED-V workspace will appear in seamless integration or full desktop mode.</span></span> <span data-ttu-id="121c5-105">シームレスな統合には、ホストデスクトップのレガシアプリケーションが含まれているため、ホスト上に直接インストールされているかのように表示されます。</span><span class="sxs-lookup"><span data-stu-id="121c5-105">Seamless integration includes legacy applications in the host desktop so that they appear as if they are installed directly on the host.</span></span> <span data-ttu-id="121c5-106">[完全なデスクトップ] は、ホスト上の独立したウィンドウでの MED-V ワークスペースオペレーティングシステムのデスクトップを示します。</span><span class="sxs-lookup"><span data-stu-id="121c5-106">Full desktop presents the desktop of the MED-V workspace operating system in a separate window on the host.</span></span>

<span data-ttu-id="121c5-107">すべての一般的な設定は、**ポリシー**モジュールの **[全般**] タブに構成されています。</span><span class="sxs-lookup"><span data-stu-id="121c5-107">All general settings are configured in the **Policy** module, on the **General** tab.</span></span>

**<span data-ttu-id="121c5-108">一般設定を MED-V ワークスペースに適用するには</span><span class="sxs-lookup"><span data-stu-id="121c5-108">To apply general settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="121c5-109">構成する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="121c5-109">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="121c5-110">次の表で説明するように、一般的なプロパティを設定します。</span><span class="sxs-lookup"><span data-stu-id="121c5-110">Configure the general properties as described in the following table.</span></span>

3.  <span data-ttu-id="121c5-111">[**ポリシー** ] メニューで、[**コミット**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="121c5-111">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="121c5-112">ワークスペースの一般的なプロパティ</span><span class="sxs-lookup"><span data-stu-id="121c5-112">General Workspace Properties</span></span>**

<span data-ttu-id="121c5-113">プロパティ説明*ワークスペースのプロパティ*</span><span class="sxs-lookup"><span data-stu-id="121c5-113">Property Description *Workspace Properties*</span></span>

<span data-ttu-id="121c5-114">名前</span><span class="sxs-lookup"><span data-stu-id="121c5-114">Name</span></span>

<span data-ttu-id="121c5-115">MED-V ワークスペースの名前。</span><span class="sxs-lookup"><span data-stu-id="121c5-115">The name of the MED-V workspace.</span></span>

<span data-ttu-id="121c5-116">**警告** クライアントコンピューターで実行している場合は、既存の MED-V ワークスペースの名前を変更しないでください。</span><span class="sxs-lookup"><span data-stu-id="121c5-116">**Warning** Do not rename an existing MED-V workspace while it is running on a client computer.</span></span>

 

<span data-ttu-id="121c5-117">説明</span><span class="sxs-lookup"><span data-stu-id="121c5-117">Description</span></span>

<span data-ttu-id="121c5-118">Med-v ワークスペースの説明。 MED-V ワークスペースのコンテンツや状態、その他の有用な情報を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="121c5-118">Description of the MED-V workspace, which can include the content or status of the MED-V workspace and any other useful information.</span></span>

<span data-ttu-id="121c5-119">**注** この説明は管理者が使用するためのものであり、ポリシーに影響を与えることはありません。</span><span class="sxs-lookup"><span data-stu-id="121c5-119">**Note** The description is for administrator use and has no impact on the policy.</span></span>

 

<span data-ttu-id="121c5-120">サポートの問い合わせ先情報</span><span class="sxs-lookup"><span data-stu-id="121c5-120">Support contact info</span></span>

<span data-ttu-id="121c5-121">テクニカルサポートの連絡先情報。</span><span class="sxs-lookup"><span data-stu-id="121c5-121">The contact information for technical support.</span></span> <span data-ttu-id="121c5-122">入力した情報は、MED-V クライアント通知領域からアクセスできる [サポート連絡先情報] 画面に表示されます。</span><span class="sxs-lookup"><span data-stu-id="121c5-122">The information entered will be displayed in the support contact information screen that can be accessed from the MED-V client notification area.</span></span>

*<span data-ttu-id="121c5-123">ワークスペースの UI</span><span class="sxs-lookup"><span data-stu-id="121c5-123">Workspace UI</span></span>*

<span data-ttu-id="121c5-124">シームレスな統合</span><span class="sxs-lookup"><span data-stu-id="121c5-124">Seamless Integration</span></span>

<span data-ttu-id="121c5-125">ホストデスクトップにシームレスに統合するには、MED-V ワークスペースウィンドウ、タスクバー、通知領域の各アイコンに対して、このオプションを選択します。</span><span class="sxs-lookup"><span data-stu-id="121c5-125">Select this option for the MED-V workspace windows, taskbar, and notification area icons to integrate seamlessly into the host desktop.</span></span>

<span data-ttu-id="121c5-126">各ワークスペースウィンドウの周りにフレームを描画する</span><span class="sxs-lookup"><span data-stu-id="121c5-126">Draw a frame around each workspace window</span></span>

<span data-ttu-id="121c5-127">シームレスな統合を使用する場合は、このオプションを選択して、MED-V ワークスペース内で実行されているすべてのアプリケーションの周りに色付きの枠線を作成し、すべてのタスクバーボタンアイコンに色付きの背景を作成します。</span><span class="sxs-lookup"><span data-stu-id="121c5-127">When using seamless integration, select this option to create a colored border around all applications running within the MED-V workspace and a colored background for all taskbar button icons.</span></span> <span data-ttu-id="121c5-128">[**フレームの色**] フィールドで、色を選択します。</span><span class="sxs-lookup"><span data-stu-id="121c5-128">In the **Frame color** field, select the color.</span></span>

<span data-ttu-id="121c5-129">完全なデスクトップ</span><span class="sxs-lookup"><span data-stu-id="121c5-129">Full Desktop</span></span>

<span data-ttu-id="121c5-130">このチェックボックスをオンにすると、ホストとの統合を行わずに、デスクトップ全体として MED-V ワークスペースが表示されます。</span><span class="sxs-lookup"><span data-stu-id="121c5-130">Select this option to display the MED-V workspace as the entire desktop, without integrating with the host.</span></span>

*<span data-ttu-id="121c5-131">ホストの確認</span><span class="sxs-lookup"><span data-stu-id="121c5-131">Host Verification</span></span>*

<span data-ttu-id="121c5-132">コマンド ライン</span><span class="sxs-lookup"><span data-stu-id="121c5-132">Command line</span></span>

<span data-ttu-id="121c5-133">MED-V ワークスペースを起動する前に、ホスト上で実行するコマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="121c5-133">Type a command line to run on the host before starting the MED-V workspace.</span></span>

<span data-ttu-id="121c5-134">検証が失敗した場合にワークスペースを開始しない (終了コードは ' 0 ' ではありません)</span><span class="sxs-lookup"><span data-stu-id="121c5-134">Do not start the Workspace if the verification fails (exit code is not '0')</span></span>

<span data-ttu-id="121c5-135">コマンドラインを使用していて、スクリプトが正常に完了した場合にのみ、MED-V ワークスペースを開始する場合は、このチェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="121c5-135">Select this check box if you are using a command line and want to start the MED-V workspace only if the script is completed successfully.</span></span>

 

<span data-ttu-id="121c5-136">MED-V ワークスペースを開始する前に、コマンドラインをホスト上で実行することができます。</span><span class="sxs-lookup"><span data-stu-id="121c5-136">A command line can be run on the host prior to starting the MED-V workspace.</span></span>

**<span data-ttu-id="121c5-137">MED-V ワークスペースを起動する前にコマンドラインを実行するには</span><span class="sxs-lookup"><span data-stu-id="121c5-137">To run a command line before starting a MED-V workspace</span></span>**

1.  <span data-ttu-id="121c5-138">[**コマンドライン**] フィールドに、コマンドラインを入力します。</span><span class="sxs-lookup"><span data-stu-id="121c5-138">In the **Command line** field, enter a command line.</span></span>

2.  <span data-ttu-id="121c5-139">コマンドラインが正常に完了した場合にのみ、MED-V ワークスペースを開始するには、[**確認が失敗した場合はワークスペースを起動しない**] チェックボックスをオンにします。</span><span class="sxs-lookup"><span data-stu-id="121c5-139">To start the MED-V workspace only if the command line was successful, select the **Do not start the workspace if the verification fails** check box.</span></span>

## <span data-ttu-id="121c5-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="121c5-140">Related topics</span></span>


[<span data-ttu-id="121c5-141">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="121c5-141">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="121c5-142">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="121c5-142">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





