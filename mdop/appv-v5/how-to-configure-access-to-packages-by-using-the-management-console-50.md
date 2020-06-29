---
title: 管理コンソールを使用してパッケージへのアクセスを構成する方法
description: 管理コンソールを使用してパッケージへのアクセスを構成する方法
author: dansimp
ms.assetid: 8f4c91e4-f4e6-48cf-aa94-6085a054e8f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e1f5b51b118dc7b783a4a550e19fd39a61a0ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814419"
---
# <span data-ttu-id="9d55d-103">管理コンソールを使用してパッケージへのアクセスを構成する方法</span><span class="sxs-lookup"><span data-stu-id="9d55d-103">How to Configure Access to Packages by Using the Management Console</span></span>


<span data-ttu-id="9d55d-104">App-v 5.0 の仮想化されたパッケージを展開する前に、アプリケーションのアクセスと実行が許可される Active Directory ドメインサービス (AD DS) セキュリティグループを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="9d55d-104">Before you deploy an App-V 5.0 virtualized package, you must configure the Active Directory Domain Services (AD DS) security groups that will be allowed to access and run the applications.</span></span> <span data-ttu-id="9d55d-105">セキュリティグループには、コンピューターまたはユーザーが含まれている場合があります。</span><span class="sxs-lookup"><span data-stu-id="9d55d-105">The security groups may contain computers or users.</span></span> <span data-ttu-id="9d55d-106">パッケージをコンピューターグループに Entitling すると、パッケージはグループ内のすべてのコンピューターにグローバルに公開されます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-106">Entitling a package to a computer group publishes the package globally to all computers in the group.</span></span>

<span data-ttu-id="9d55d-107">仮想化されたパッケージへのアクセスを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-107">Use the following procedure to configure access to virtualized packages.</span></span>

**<span data-ttu-id="9d55d-108">App-v 5.0 パッケージへのアクセスを許可するには</span><span class="sxs-lookup"><span data-stu-id="9d55d-108">To grant access to an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="9d55d-109">構成するパッケージを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-109">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="9d55d-110">App-v 5.0 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-110">Open the App-V 5.0 Management console.</span></span>

    2.  <span data-ttu-id="9d55d-111">**広告アクセス**ページを表示するには、構成するパッケージを右クリックして、[ **active Directory アクセスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-111">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="9d55d-112">または、パッケージを選択し、**広告アクセス**ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-112">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="9d55d-113">パッケージのセキュリティグループをプロビジョニングします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-113">Provision a security group for the package:</span></span>

    1.  <span data-ttu-id="9d55d-114">[**有効な ACTIVE DIRECTORY 名を検索してアクセス許可**] ページに移動します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-114">Go to the **FIND VALID ACTIVE DIRECTORY NAMES AND GRANT ACCESS** page.</span></span>

    2.  <span data-ttu-id="9d55d-115">" **Mydomain**" の書式設定を使用して、  \\  **groupname**Active Directory グループオブジェクトの名前または名前の一部を入力し、[**確認**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-115">Using the format **mydomain** \\ **groupname**, type the name or part of the name of an Active Directory group object, and click **Check**.</span></span>

        <span data-ttu-id="9d55d-116">**注** 検索するグループに関連付けられているドメイン名を指定していることを確認します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-116">**Note** Ensure that you provide an associated domain name for the group that you are searching for.</span></span>

         

3.  <span data-ttu-id="9d55d-117">パッケージへのアクセスを許可するには、目的のグループを選択し、[**アクセスの許可**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-117">To grant access to the package, select the desired group and click **Grant Access**.</span></span> <span data-ttu-id="9d55d-118">新しく追加されたグループが、[アクセス] ウィンドウの**広告エンティティ**に表示されます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-118">The newly added group is displayed in the **AD ENTITIES WITH ACCESS** pane.</span></span>

4.  

    <span data-ttu-id="9d55d-119">既定の設定をそのまま使用して**広告アクセス**ページを閉じるには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-119">To accept the default configuration settings and close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="9d55d-120">特定のグループの構成をカスタマイズするには、[**割り当てられた構成**] ドロップダウンをクリックして、[**カスタム**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-120">To customize configurations for a specific group, click the **ASSIGNED CONFIGURATIONS** drop-down and select **Custom**.</span></span> <span data-ttu-id="9d55d-121">カスタム構成を構成するには、[**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-121">To configure the custom configurations, click **EDIT**.</span></span> <span data-ttu-id="9d55d-122">アクセスを許可したら、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-122">After you grant access, click **Close**.</span></span>

**<span data-ttu-id="9d55d-123">App-v 5.0 パッケージへのアクセスを削除するには</span><span class="sxs-lookup"><span data-stu-id="9d55d-123">To remove access to an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="9d55d-124">構成するパッケージを見つけます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-124">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="9d55d-125">App-v 5.0 管理コンソールを開きます。</span><span class="sxs-lookup"><span data-stu-id="9d55d-125">Open the App-V 5.0 Management console.</span></span>

    2.  <span data-ttu-id="9d55d-126">**広告アクセス**ページを表示するには、構成するパッケージを右クリックして、[ **active Directory アクセスの編集**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-126">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="9d55d-127">または、パッケージを選択し、**広告アクセス**ウィンドウで [**編集**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-127">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="9d55d-128">削除するグループを選択し、[**削除**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-128">Select the group you want to remove, and click **DELETE**.</span></span>

3.  <span data-ttu-id="9d55d-129">**広告アクセス**ページを閉じるには、[**閉じる**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="9d55d-129">To close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="9d55d-130">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="9d55d-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="9d55d-131">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="9d55d-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="9d55d-132">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="9d55d-132">Got an App-V issue?</span></span>** <span data-ttu-id="9d55d-133">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="9d55d-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="9d55d-134">関連トピック</span><span class="sxs-lookup"><span data-stu-id="9d55d-134">Related topics</span></span>


[<span data-ttu-id="9d55d-135">APP-V 5.0 の操作</span><span class="sxs-lookup"><span data-stu-id="9d55d-135">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





