---
title: MED-V 管理コンソールのユーザー インターフェイスの使用
description: MED-V 管理コンソールのユーザー インターフェイスの使用
author: dansimp
ms.assetid: f42714d7-6f0c-4995-ab31-d4ef0845a22c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22fc98c3edbea48847e1a00369bea21a470e66b7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825847"
---
# <span data-ttu-id="132e6-103">MED-V 管理コンソールのユーザー インターフェイスの使用</span><span class="sxs-lookup"><span data-stu-id="132e6-103">Using the MED-V Management Console User Interface</span></span>


<span data-ttu-id="132e6-104">コンソールのユーザーインターフェイスは、次のセクションに分かれています。</span><span class="sxs-lookup"><span data-stu-id="132e6-104">The console user interface is divided into the following sections:</span></span>

-   <span data-ttu-id="132e6-105">3つのモジュールに対応する、次の**med-v 管理ボタン**。</span><span class="sxs-lookup"><span data-stu-id="132e6-105">The following **MED-V management buttons**, which correspond to the three modules:</span></span>

    -   <span data-ttu-id="132e6-106">**ポリシー**:**ポリシー**モジュールを使って、med-v ワークスペースとその関連の設定とアクセス許可を定義します。</span><span class="sxs-lookup"><span data-stu-id="132e6-106">**Policy**—The **Policy** module is used to define the MED-V workspaces and their related settings and permissions.</span></span>

    -   <span data-ttu-id="132e6-107">**画像**— **images**モジュールは、med-v ワークスペースの画像を管理するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-107">**Images**—The **Images** module is used to manage MED-V workspace images.</span></span>

    -   <span data-ttu-id="132e6-108">**レポート**:**レポート**モジュールは、med-v ワークスペースレポートを生成および表示するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-108">**Reports**—The **Reports** module is used for generating and viewing MED-V workspace reports.</span></span>

-   <span data-ttu-id="132e6-109">**ツールバー**には、選択したボタンに関連するショートカットが表示されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-109">The **toolbar** displays shortcuts relevant to the button selected.</span></span>

-   <span data-ttu-id="132e6-110">**表示ウィンドウ**には、選択されているボタンに対応するモジュールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-110">The **display pane** displays a module corresponding to the button that is selected.</span></span>

![](images/medv-ui-console-general.gif)

## <span data-ttu-id="132e6-111">MED-V 管理コンソールにログインする方法</span><span class="sxs-lookup"><span data-stu-id="132e6-111">How to Log In to the MED-V Management Console</span></span>


**<span data-ttu-id="132e6-112">MED-V 管理コンソールを開くには</span><span class="sxs-lookup"><span data-stu-id="132e6-112">To open the MED-V management console</span></span>**

-   <span data-ttu-id="132e6-113">Windows の [**スタート**] メニューで、[すべてのプログラム] を選択するか、またはデスクトップで [Med-v の管理] アイコンをダブルクリックします。 \*\* &gt; &gt; \*\*</span><span class="sxs-lookup"><span data-stu-id="132e6-113">On the Windows **Start** menu, select **All Programs &gt; MED-V &gt; MED-V Management**, or on the desktop, double-click the MED-V Management icon.</span></span>

    <span data-ttu-id="132e6-114">**Med-v 管理ログイン**ウィンドウが表示されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-114">The **MED-V Management Login** window appears.</span></span>

<span data-ttu-id="132e6-115">**注** セキュリティ上の理由から、MED-V 管理コンソールにログインする最初のユーザーは、そのコンピューター上で管理コンソールへのアクセスが許可されているユーザーのみになります。</span><span class="sxs-lookup"><span data-stu-id="132e6-115">**Note** For security reasons, the first user to log in to the MED-V management console will become the only user on that computer allowed to access the management console.</span></span>

 

**<span data-ttu-id="132e6-116">ログインするには</span><span class="sxs-lookup"><span data-stu-id="132e6-116">To log in</span></span>**

1.  <span data-ttu-id="132e6-117">ドメインユーザーの資格情報を次の形式で入力します。</span><span class="sxs-lookup"><span data-stu-id="132e6-117">Type in your domain user credentials in the following format:</span></span>

    <span data-ttu-id="132e6-118">"ドメイン \ _name \\ user\ _name"、"password"</span><span class="sxs-lookup"><span data-stu-id="132e6-118">"domain\_name\\user\_name", "password"</span></span>

    <span data-ttu-id="132e6-119">**注** サーバーを構成するときに、フルアクセス権を持つユーザーだけでなく、読み取り専用アクセス権を持つユーザーも定義されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-119">**Note** When configuring the server, users with full access as well as users with read-only access are defined.</span></span> <span data-ttu-id="132e6-120">すべてのユーザーがドメインユーザーである必要があります。</span><span class="sxs-lookup"><span data-stu-id="132e6-120">All users must be domain users.</span></span> <span data-ttu-id="132e6-121">ドメインユーザー名とパスワードは、MED-V 管理ログインに使用されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-121">The domain user name and password is used for MED-V management login.</span></span>

     

2.  <span data-ttu-id="132e6-122">**[OK]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="132e6-122">Click **OK**.</span></span>

    <span data-ttu-id="132e6-123">**Med-v 管理**コンソールが表示されます。</span><span class="sxs-lookup"><span data-stu-id="132e6-123">The **MED-V Management** console appears.</span></span>

## <span data-ttu-id="132e6-124">関連トピック</span><span class="sxs-lookup"><span data-stu-id="132e6-124">Related topics</span></span>


[<span data-ttu-id="132e6-125">MED-V クライアントと MED-V 管理コンソールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="132e6-125">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

 

 





