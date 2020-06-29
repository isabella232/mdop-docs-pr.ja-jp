---
title: MED-V クライアントと MED-V 管理コンソールをインストールする方法
description: MED-V クライアントと MED-V 管理コンソールをインストールする方法
author: dansimp
ms.assetid: 8a5f3010-3a50-487e-99d8-e352e5cb51c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a486cc7cf5534171f80b08dc93742e03cd4a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826984"
---
# <span data-ttu-id="82a84-103">MED-V クライアントと MED-V 管理コンソールをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="82a84-103">How to Install MED-V Client and MED-V Management Console</span></span>


<span data-ttu-id="82a84-104">Client.msi パッケージには、次の MED-V コンポーネントが含まれています。</span><span class="sxs-lookup"><span data-stu-id="82a84-104">The following MED-V components are included in the client .msi package:</span></span>

-   <span data-ttu-id="82a84-105">Med-v クライアント-med-v ワークスペースを実行するためにクライアントコンピューターにインストールする必要がある MED-V ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="82a84-105">MED-V client—The MED-V software that must be installed on client computers for running MED-V workspaces.</span></span>

-   <span data-ttu-id="82a84-106">MED-V 管理コンソール—管理者が、イメージ、MED-V ワークスペース、ポリシーを作成および管理するために使用できる管理ツールです。</span><span class="sxs-lookup"><span data-stu-id="82a84-106">MED-V management console—The administrative tool that administrators can use to create and maintain images, MED-V workspaces, and policies.</span></span>

<span data-ttu-id="82a84-107">MED-V 管理コンソールと MED-V クライアントは、どちらも MED-V の client.msi パッケージからインストールされます。</span><span class="sxs-lookup"><span data-stu-id="82a84-107">The MED-V management console and the MED-V client are both installed from the MED-V client .msi package.</span></span> <span data-ttu-id="82a84-108">ただし、MED-V クライアントは、インストール中に [ **Med-v management application をインストール**する] チェックボックスをオフにすることによって、med-v 管理コンソールなしで個別にインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="82a84-108">The MED-V client, however, can be installed independently without the MED-V management console by clearing the **Install the MED-V Management application** check box during installation.</span></span>

**<span data-ttu-id="82a84-109">注</span><span class="sxs-lookup"><span data-stu-id="82a84-109">Note</span></span>**  
<span data-ttu-id="82a84-110">MED-V クライアントと MED-V の管理コンソールは、Windows 7、Windows Vista、Windows XP ベースのコンピューターにのみインストールできます。</span><span class="sxs-lookup"><span data-stu-id="82a84-110">The MED-V client and MED-V management console can only be installed on Windows 7-, Windows Vista-, and Windows XP-based computers.</span></span> <span data-ttu-id="82a84-111">サーバー製品にインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="82a84-111">They cannot be installed on server products.</span></span>



**<span data-ttu-id="82a84-112">注</span><span class="sxs-lookup"><span data-stu-id="82a84-112">Note</span></span>**  
<span data-ttu-id="82a84-113">Windows **runas**コマンドを使用して、med-v クライアントをインストールしないでください。</span><span class="sxs-lookup"><span data-stu-id="82a84-113">Do not install the MED-V client using the Windows **runas** command.</span></span>



**<span data-ttu-id="82a84-114">MED-V クライアントをインストールするには</span><span class="sxs-lookup"><span data-stu-id="82a84-114">To install the MED-V client</span></span>**

1.  <span data-ttu-id="82a84-115">ローカルコンピューターのローカル管理者の権限を持つユーザーとしてログインします。</span><span class="sxs-lookup"><span data-stu-id="82a84-115">Log in as a user with local administrator rights on the local computer.</span></span>

2.  <span data-ttu-id="82a84-116">MED-V パッケージを実行します。</span><span class="sxs-lookup"><span data-stu-id="82a84-116">Run the MED-V .msi package.</span></span>

    <span data-ttu-id="82a84-117">MED-V パッケージは*MED-V\_x.msi*と呼ばれます。ここで、 *x*はバージョン番号です。</span><span class="sxs-lookup"><span data-stu-id="82a84-117">The MED-V .msi package is called *MED-V\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="82a84-118">たとえば、 *MED-V\_1.0.65.msi*とします。</span><span class="sxs-lookup"><span data-stu-id="82a84-118">For example, *MED-V\_1.0.65.msi*.</span></span>

3.  <span data-ttu-id="82a84-119">**InstallShield ウィザード**の [ようこそ] 画面が表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82a84-119">When the **InstallShield Wizard Welcome** screen appears, click **Next**.</span></span>

4.  <span data-ttu-id="82a84-120">[**使用**許諾契約書] 画面で、使用許諾契約書を読み、[**使用許諾契約書に同意**します] をクリックして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82a84-120">On the **License Agreement** screen, read the license agreement, click **I accept the terms in the license agreement**, and click **Next**.</span></span>

    <span data-ttu-id="82a84-121">[**インポート先のフォルダー** ] 画面が表示され、既定のインストールフォルダーが表示されます。</span><span class="sxs-lookup"><span data-stu-id="82a84-121">The **Destination Folder** screen appears, with the default installation folder displayed.</span></span>

    <span data-ttu-id="82a84-122">既定のインストールフォルダーは、オペレーティングシステムがインストールされているディレクトリです。</span><span class="sxs-lookup"><span data-stu-id="82a84-122">The default installation folder is the directory where the operating system is installed.</span></span>

    -   <span data-ttu-id="82a84-123">MED-V をインストールする必要があるフォルダーを変更するには、[**変更**] をクリックし、既存のフォルダーを参照します。</span><span class="sxs-lookup"><span data-stu-id="82a84-123">To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.</span></span>

5.  <span data-ttu-id="82a84-124">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82a84-124">Click **Next**.</span></span>

6.  <span data-ttu-id="82a84-125">[ **Med-v の設定**] 画面で、次のように med-v のインストールを構成します。</span><span class="sxs-lookup"><span data-stu-id="82a84-125">On the **MED-V Settings** screen, configure the MED-V installation as follows:</span></span>

    -   <span data-ttu-id="82a84-126">[ **Med-v management application をインストール**する] チェックボックスをオンにして、管理コンポーネントをインストールに含めます。</span><span class="sxs-lookup"><span data-stu-id="82a84-126">Select the **Install the MED-V management application** check box to include the management component in the installation.</span></span>

        **<span data-ttu-id="82a84-127">注</span><span class="sxs-lookup"><span data-stu-id="82a84-127">Note</span></span>**  
        <span data-ttu-id="82a84-128">エンタープライズデスクトップ仮想化の管理者は、MED-V 管理アプリケーションをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="82a84-128">Enterprise Desktop Virtualization administrators should install the MED-V management application.</span></span> <span data-ttu-id="82a84-129">このアプリケーションは、デスクトップイメージと MED-V のワークスペースを構成するために必要です。</span><span class="sxs-lookup"><span data-stu-id="82a84-129">This application is required for configuring desktop images and MED-V workspaces.</span></span>



~~~
-   Select the **Load MED-V when Windows starts** check box to start MED-V automatically on startup.

-   Select the **Add a MED-V shortcut to my desktop** check box to create a MED-V shortcut on your desktop.

-   In the **Server address** field, type the server address.

-   In the **Server port** field, type the server's port.

-   Select the **Server requires encrypted connections (https)** check box to work with https.

-   The default virtual machine images folder is displayed. The default installation folder is *%systemdrive%\\MED-V Images\\*. To change the folder where MED-V should be installed, click **Change**, and browse to an existing folder.
~~~

7. <span data-ttu-id="82a84-130">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82a84-130">Click **Next**.</span></span>

8. <span data-ttu-id="82a84-131">[**プログラムをインストールする準備ができ**ました] 画面で、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="82a84-131">On the **Ready to Install the Program** screen, click **Install**.</span></span>

   <span data-ttu-id="82a84-132">MED-V クライアントのインストールが開始されます。</span><span class="sxs-lookup"><span data-stu-id="82a84-132">The MED-V client installation starts.</span></span> <span data-ttu-id="82a84-133">これには数分かかることがあり、画面にテキストが表示されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="82a84-133">This can take several minutes, and the screen might not display text.</span></span> <span data-ttu-id="82a84-134">インストール中に、いくつかの進行状況画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82a84-134">During installation, several progress screens appear.</span></span> <span data-ttu-id="82a84-135">メッセージが表示されたら、表示される指示に従います。</span><span class="sxs-lookup"><span data-stu-id="82a84-135">If a message appears, follow the instructions provided.</span></span>

   <span data-ttu-id="82a84-136">インストールが正常に完了すると、 **InstallShield ウィザード**の [完了] 画面が表示されます。</span><span class="sxs-lookup"><span data-stu-id="82a84-136">Upon successful installation, the **InstallShield Wizard Completed** screen appears.</span></span>

9. <span data-ttu-id="82a84-137">[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="82a84-137">Click **Finish** to close the wizard.</span></span>

## <span data-ttu-id="82a84-138">関連トピック</span><span class="sxs-lookup"><span data-stu-id="82a84-138">Related topics</span></span>


[<span data-ttu-id="82a84-139">サポートされる構成</span><span class="sxs-lookup"><span data-stu-id="82a84-139">Supported Configurations</span></span>](supported-configurationsmedv-orientation.md)

[<span data-ttu-id="82a84-140">インストールとアップグレードのチェックリスト</span><span class="sxs-lookup"><span data-stu-id="82a84-140">Installation and Upgrade Checklists</span></span>](installation-and-upgrade-checklists.md)









