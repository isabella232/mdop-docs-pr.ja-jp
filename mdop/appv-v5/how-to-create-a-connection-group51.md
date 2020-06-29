---
title: 接続グループを作成する方法
description: 接続グループを作成する方法
author: dansimp
ms.assetid: 221e2eed-7ebb-42e3-b3d6-11c37c0578e6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f20b3e71c7c0b72d66700bbad945860112ffd03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10814331"
---
# <span data-ttu-id="02e9d-103">接続グループを作成する方法</span><span class="sxs-lookup"><span data-stu-id="02e9d-103">How to Create a Connection Group</span></span>


<span data-ttu-id="02e9d-104">以下の手順を使用して、App-v 管理コンソールを使用して接続グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-104">Use these steps to create a connection group by using the App-V Management Console.</span></span> <span data-ttu-id="02e9d-105">PowerShell を使用して接続グループを作成する方法については、「 [Powershell を使用してスタンドアロンコンピューターで接続グループを管理する方法](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="02e9d-105">To use PowerShell to create connection groups, see [How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md).</span></span>

<span data-ttu-id="02e9d-106">接続グループにパッケージを配置すると、そのパッケージのルートパスがマージされます。</span><span class="sxs-lookup"><span data-stu-id="02e9d-106">When you place packages in a connection group, their package root paths are merged.</span></span> <span data-ttu-id="02e9d-107">パッケージを削除した場合、残りのパッケージだけがマージされたルートを保持します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-107">If you remove packages, only the remaining packages maintain the merged root.</span></span>

**<span data-ttu-id="02e9d-108">接続グループを作成するには</span><span class="sxs-lookup"><span data-stu-id="02e9d-108">To create a connection group</span></span>**

1.  <span data-ttu-id="02e9d-109">App-v 5.1 管理コンソールで、[**接続グループ**] を選択して、接続グループライブラリを表示します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-109">In the App-V 5.1 Management Console, select **CONNECTION GROUPS** to display the Connection Groups library.</span></span>

2.  <span data-ttu-id="02e9d-110">[**接続グループの追加**] を選択して、新しい接続グループを作成します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-110">Select **ADD CONNECTION GROUP** to create a new connection group.</span></span>

3.  <span data-ttu-id="02e9d-111">[**新しい接続グループ**] ウィンドウで、グループの説明を入力します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-111">In the **New Connection Group** pane, type a description for the group.</span></span>

4.  <span data-ttu-id="02e9d-112">[接続**されているパッケージ**] ウィンドウで [**編集**] をクリックして、新しいアプリケーションを接続グループに追加します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-112">Click **EDIT** in the **CONNECTED PACKAGES** pane to add a new application to the connection group.</span></span>

5.  <span data-ttu-id="02e9d-113">[**ライブラリ全体のパッケージ**] ウィンドウで、追加するアプリケーションを選択し、矢印をクリックしてアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-113">In the **PACKAGES Entire Library** pane, select the application to be added, and click the arrow to add the application.</span></span>

    <span data-ttu-id="02e9d-114">アプリケーションを削除するには、[パッケージ] ウィンドウ**で**削除するアプリケーションを選択し、矢印をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e9d-114">To remove an application, select the application to be removed in the **PACKAGES IN** pane and click the arrow.</span></span>

    <span data-ttu-id="02e9d-115">接続グループ内のアプリケーションの優先順位を再度するには、 **[パッケージ**] ウィンドウの [パッケージ] の矢印を使用します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-115">To reprioritize the applications in your connection group, use the arrows in the **PACKAGES IN** pane.</span></span>

    <span data-ttu-id="02e9d-116">**重要** 既定では、特定のアプリケーションに関連付けられている Active Directory ドメインサービスのアクセス構成は、接続グループに追加されません。</span><span class="sxs-lookup"><span data-stu-id="02e9d-116">**Important** By default, the Active Directory Domain Services access configurations that are associated with a specific application are not added to the connection group.</span></span> <span data-ttu-id="02e9d-117">Active Directory access の構成を移行するには、[**パッケージアクセスの追加**] を選択します。これは、[**パッケージ**] ウィンドウにあります。</span><span class="sxs-lookup"><span data-stu-id="02e9d-117">To transfer the Active Directory access configuration, select **ADD PACKAGE ACCESS TO GROUP ACCESS**, which is located in the **PACKAGES IN** pane.</span></span>

     

6.  <span data-ttu-id="02e9d-118">すべてのアプリケーションを追加して Active Directory アクセスを構成したら、[**適用**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="02e9d-118">After adding all the applications and configuring Active Directory access, click **Apply**.</span></span>

    <span data-ttu-id="02e9d-119">App-v**の提案をお寄せ**ください。</span><span class="sxs-lookup"><span data-stu-id="02e9d-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="02e9d-120">[ここで](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="02e9d-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="02e9d-121">App-v の問題が発生しましたか?</span><span class="sxs-lookup"><span data-stu-id="02e9d-121">Got an App-V issue?</span></span>** <span data-ttu-id="02e9d-122">App-v の[TechNet フォーラム](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)を使用します。</span><span class="sxs-lookup"><span data-stu-id="02e9d-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="02e9d-123">関連トピック</span><span class="sxs-lookup"><span data-stu-id="02e9d-123">Related topics</span></span>


[<span data-ttu-id="02e9d-124">APP-V 5.1 の操作</span><span class="sxs-lookup"><span data-stu-id="02e9d-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="02e9d-125">接続グループの管理</span><span class="sxs-lookup"><span data-stu-id="02e9d-125">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





