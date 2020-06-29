---
title: MED-V ワークスペースの作成
description: MED-V ワークスペースの作成
author: dansimp
ms.assetid: 9578bb99-8a09-44c1-b88f-538901f16ad3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 189da6b28515f0d234c8a258138a27be7a7375d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10824864"
---
# <span data-ttu-id="fdfeb-103">MED-V ワークスペースの作成</span><span class="sxs-lookup"><span data-stu-id="fdfeb-103">Creating a MED-V Workspace</span></span>


<span data-ttu-id="fdfeb-104">MED-V ワークスペースは、MED-V によって提供される仮想マシンとエンドユーザーがやり取りするデスクトップ環境です。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-104">A MED-V workspace is the desktop environment in which end users interact with the virtual machine provided by MED-V.</span></span> <span data-ttu-id="fdfeb-105">MED-V ワークスペースは、管理者によって作成およびカスタマイズされます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-105">The MED-V workspace is created and customized by the administrator.</span></span> <span data-ttu-id="fdfeb-106">この画像は、MED-V ワークスペースの規則と機能を定義するイメージとポリシーで構成されています。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-106">It consists of an image and the policy, which defines the rules and functionality of the MED-V workspace.</span></span> <span data-ttu-id="fdfeb-107">複数の MED-V ワークスペースを作成して、それぞれ独自の構成、設定、およびルールでカスタマイズすることができます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-107">Multiple MED-V workspaces can be created, each customized with its own configuration, settings, and rules.</span></span> <span data-ttu-id="fdfeb-108">ユーザー、グループ、または複数のユーザーまたはグループを各 MED-V ワークスペースに関連付けることができるので、MED-V ワークスペースは、関連付けられたユーザーまたはグループのコンピューターでのみ使用できます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-108">A user, group, or multiple users or groups can be associated with each MED-V workspace, thereby making the MED-V workspace available only for the associated user's or group's computers.</span></span>

## <span data-ttu-id="fdfeb-109">MED-V ワークスペースを追加する方法</span><span class="sxs-lookup"><span data-stu-id="fdfeb-109">How to Add a MED-V Workspace</span></span>


**<span data-ttu-id="fdfeb-110">MED-V ワークスペースを追加するには</span><span class="sxs-lookup"><span data-stu-id="fdfeb-110">To add a MED-V workspace</span></span>**

1.  <span data-ttu-id="fdfeb-111">[**ポリシー**の管理] をクリックして、**ポリシー**モジュールを開きます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-111">Click the **Policy** management button to open the **Policy** module.</span></span>

    <span data-ttu-id="fdfeb-112">**ポリシー**モジュールは、左側の [**ワークスペース**] メニューと [**全般**]、[**仮想マシン**]、[**展開**]、[**アプリケーション**]、[ **Web**]、[ **VM のセットアップ**]、[**ネットワーク**]、[**パフォーマンス**] の各タブで構成されます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-112">The **Policy** module consists of the **Workspaces** menu on the left and the **General**, **Virtual Machine**, **Deployment**, **Applications**, **Web**, **VM Setup**, **Network**, and **Performance** tabs.</span></span>

2.  <span data-ttu-id="fdfeb-113">[**ポリシー** ] メニューで、[**新しいワークスペース**] を選択するか、[**追加**] をクリックして新しい med-v ワークスペースを作成します。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-113">On the **Policy** menu, select **New Workspace**, or click **Add** to create a new MED-V workspace.</span></span>

3.  <span data-ttu-id="fdfeb-114">[**全般**] タブの [**名前**] フィールドに、med-v ワークスペースの名前を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-114">On the **General** tab, in the **Name** field, enter the name of the MED-V workspace.</span></span>

4.  <span data-ttu-id="fdfeb-115">[**説明**] フィールドに、med-v ワークスペースの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-115">In the **Description** field, enter a description for the MED-V workspace.</span></span>

5.  <span data-ttu-id="fdfeb-116">「**サポート連絡先情報**」フィールドに、テクニカルサポートの連絡先情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-116">In the **Support contact info** field, enter the contact information for technical support.</span></span>

    <span data-ttu-id="fdfeb-117">MED-V ワークスペースの構成の詳細については、「 [Med-v ワークスペースポリシーを構成する](configuring-med-v-workspace-policies.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-117">For more information about configuring a MED-V workspace, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

## <span data-ttu-id="fdfeb-118">MED-V ワークスペースの複製方法</span><span class="sxs-lookup"><span data-stu-id="fdfeb-118">How to Clone a MED-V Workspace</span></span>


<span data-ttu-id="fdfeb-119">MED-V ワークスペースは、既存の MED-V ワークスペースと同一の MED-V ワークスペースを作成できるように複製することができます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-119">A MED-V workspace can be cloned so that you can create a MED-V workspace identical to an existing MED-V workspace.</span></span>

**<span data-ttu-id="fdfeb-120">MED-V ワークスペースの複製を作成するには</span><span class="sxs-lookup"><span data-stu-id="fdfeb-120">To clone a MED-V workspace</span></span>**

1.  <span data-ttu-id="fdfeb-121">複製する MED-V ワークスペースをクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-121">Click the MED-V workspace to clone.</span></span>

2.  <span data-ttu-id="fdfeb-122">[**ポリシー** ] メニューで、[**ワークスペースの複製**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-122">On the **Policy** menu, select **Clone Workspace**.</span></span>

    <span data-ttu-id="fdfeb-123">新しい MED-V ワークスペースを作成するには、" &lt; 元の med-v ワークスペース名-2" という名前を付け &gt; ます。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-123">A new MED-V workspace is created with the name &lt;Original MED-V workspace name&gt; - 2.</span></span>

## <span data-ttu-id="fdfeb-124">MED-V ワークスペースを削除する方法</span><span class="sxs-lookup"><span data-stu-id="fdfeb-124">How to Delete a MED-V Workspace</span></span>


**<span data-ttu-id="fdfeb-125">MED-V ワークスペースを削除するには</span><span class="sxs-lookup"><span data-stu-id="fdfeb-125">To delete a MED-V workspace</span></span>**

-   <span data-ttu-id="fdfeb-126">**ポリシー**モジュールで、ワークスペースウィンドウがフォーカスされている状態で、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="fdfeb-126">In the **Policy** module, while the workspace pane is in focus, click **Remove**.</span></span>

## <span data-ttu-id="fdfeb-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="fdfeb-127">Related topics</span></span>


[<span data-ttu-id="fdfeb-128">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="fdfeb-128">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





