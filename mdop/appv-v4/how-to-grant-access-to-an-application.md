---
title: アプリケーションへのアクセスを許可する方法
description: アプリケーションへのアクセスを許可する方法
author: dansimp
ms.assetid: e54d9e84-21f5-488f-b040-25f374d9289f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9cd3dfe4661f09bb7e7d3514a397955cb892be81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817434"
---
# <span data-ttu-id="2d358-103">アプリケーションへのアクセスを許可する方法</span><span class="sxs-lookup"><span data-stu-id="2d358-103">How to Grant Access to an Application</span></span>


<span data-ttu-id="2d358-104">管理者は、Application Virtualization Server 管理コンソールを使用して、どのユーザーがどのアプリケーションにアクセスできるかを判断することができます。</span><span class="sxs-lookup"><span data-stu-id="2d358-104">As the administrator, you can use the Application Virtualization Server Management Console to determine which users can access which applications.</span></span> <span data-ttu-id="2d358-105">この操作は、Sequencer プロジェクト (SPRJ) または Open Software Descriptor (OSD) ファイルをインポートするとき、またはアプリケーションの [**プロパティ**] ダイアログボックスを使っていつでも実行できます。</span><span class="sxs-lookup"><span data-stu-id="2d358-105">You can do this when you import the Sequencer Project (SPRJ) or Open Software Descriptor (OSD) file or at anytime using the application's **Properties** dialog box.</span></span> <span data-ttu-id="2d358-106">どちらの方法でも、[**アクセス許可**] オプションを使用してユーザーを追加します。</span><span class="sxs-lookup"><span data-stu-id="2d358-106">With both methods, use the **Access Permissions** options to add users.</span></span>

**<span data-ttu-id="2d358-107">アプリケーションへのアクセスを許可するには</span><span class="sxs-lookup"><span data-stu-id="2d358-107">To grant access to an application</span></span>**

1.  <span data-ttu-id="2d358-108">既存のアプリケーションの場合は、左側のウィンドウで [**アプリケーション**] ノードをクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d358-108">For an existing application, click the **Applications** node in the left pane.</span></span> <span data-ttu-id="2d358-109">右側のウィンドウでアプリケーションを右クリックし、[**プロパティ**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2d358-109">Right-click an application in the right pane, and choose **Properties**.</span></span>

2.  <span data-ttu-id="2d358-110">[**アクセス許可**] タブを選択します。</span><span class="sxs-lookup"><span data-stu-id="2d358-110">Select the **Access Permissions** tab.</span></span>

3.  <span data-ttu-id="2d358-111">ユーザーグループを追加するには、[**追加**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d358-111">To add user groups, click **Add**.</span></span>

4.  <span data-ttu-id="2d358-112">[**ユーザーグループの追加/編集**] ダイアログボックスで、[ユーザー] グループに移動します。</span><span class="sxs-lookup"><span data-stu-id="2d358-112">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="2d358-113">各フィールドに情報を入力して、ドメインとグループを入力することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d358-113">You can also enter the domain and group by typing the information in the respective fields.</span></span>

5.  <span data-ttu-id="2d358-114">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d358-114">Click **OK**.</span></span> <span data-ttu-id="2d358-115">同じページを持つ他のグループを追加することもできます。</span><span class="sxs-lookup"><span data-stu-id="2d358-115">You can add other groups with the same pages.</span></span>

6.  <span data-ttu-id="2d358-116">ウィザードが再び表示されたら、[ **OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="2d358-116">When the wizard reappears, click **OK**.</span></span>

    <span data-ttu-id="2d358-117">**注** アプリケーションへのアクセス許可を付与する前に、Active Directory ドメインサービスでグループを設定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2d358-117">**Note** You must set up your groups in Active Directory Domain Services before you attempt to grant access to applications.</span></span>

     

## <span data-ttu-id="2d358-118">関連トピック</span><span class="sxs-lookup"><span data-stu-id="2d358-118">Related topics</span></span>


[<span data-ttu-id="2d358-119">アプリケーションへのアクセスを拒否する方法</span><span class="sxs-lookup"><span data-stu-id="2d358-119">How to Deny Access to an Application</span></span>](how-to-deny-access-to-an-application.md)

[<span data-ttu-id="2d358-120">サーバー管理コンソールでアプリケーション グループを管理する方法</span><span class="sxs-lookup"><span data-stu-id="2d358-120">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="2d358-121">サーバー管理コンソールでアプリケーション ライセンスを管理する方法</span><span class="sxs-lookup"><span data-stu-id="2d358-121">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="2d358-122">アプリケーションを手動で追加する方法</span><span class="sxs-lookup"><span data-stu-id="2d358-122">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





