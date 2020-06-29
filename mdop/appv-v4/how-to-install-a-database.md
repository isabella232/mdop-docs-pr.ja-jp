---
title: データベースをインストールする方法
description: データベースをインストールする方法
author: dansimp
ms.assetid: 52e3a19d-b7cf-4f2c-8268-0f8361cc9766
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c5f42673c08744d17e1d2e0ef955ebed2848de18
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817377"
---
# <span data-ttu-id="6db0d-103">データベースをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="6db0d-103">How to Install a Database</span></span>


<span data-ttu-id="6db0d-104">データベースがまだ利用できない場合は、次の手順に従って、アプリケーションの仮想化のサーバーベースの展開用のデータベースをインストールすることができます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-104">You can use the following procedure to install a database for your server-based deployment of Application Virtualization if a database is not already available.</span></span> <span data-ttu-id="6db0d-105">通常、運用環境では、既存のデータベースに接続します。</span><span class="sxs-lookup"><span data-stu-id="6db0d-105">Typically, in a production environment, you will connect to an existing database.</span></span>

<span data-ttu-id="6db0d-106">**重要** データベースをインストールするには、適切な権限を持つネットワークアカウントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="6db0d-106">**Important** To install the database, you must use a network account with the appropriate permissions.</span></span> <span data-ttu-id="6db0d-107">データベースのアップグレードを作成して実行できるのは、組織でデータベース管理者のみが許可されている場合、このタスクを実行できるようにスクリプトを使用できます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-107">If your organization requires that only database administrators are allowed to create and conduct database upgrades, scripts are available that allow this task to be performed.</span></span>

 

**<span data-ttu-id="6db0d-108">データベースをインストールするには</span><span class="sxs-lookup"><span data-stu-id="6db0d-108">To install a database</span></span>**

1.  <span data-ttu-id="6db0d-109">ネットワーク上でアプリケーションの仮想化システムセットアッププログラムが保存されている場所に移動します。ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、[ **Setup.exe**] をダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-109">Navigate to the location of the Application Virtualization System setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click **Setup.exe**.</span></span>

2.  <span data-ttu-id="6db0d-110">[**ようこそ] ページ**で、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-110">On the **Welcome Page**, click **Next**.</span></span>

3.  <span data-ttu-id="6db0d-111">[**使用許諾契約**書] ページで、ライセンス契約に同意する場合は、[**ライセンス条項に同意**します] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-111">On the **License Agreement** page, to accept the license agreement, select **I accept the license terms and conditions**, and click **Next**.</span></span>

4.  <span data-ttu-id="6db0d-112">[**登録情報**] ページで、**ユーザー名**と**組織**の情報を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-112">On the **Registering Information** page, specify the **User Name** and **Organization** information, and then click **Next**.</span></span>

5.  <span data-ttu-id="6db0d-113">[**セットアップの種類**] ページで、[**カスタム**] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-113">On the **Setup Type** page, select **Custom** and then click **Next**.</span></span>

6.  <span data-ttu-id="6db0d-114">[**カスタムセットアップ**] ページで、[ **application virtualization Server**を除くすべての application virtualization システムコンポーネント] の選択を解除し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-114">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    <span data-ttu-id="6db0d-115">**注** コンポーネントがコンピューターに既にインストールされている場合は、[**カスタムセットアップ**] 画面でそのコンポーネントをオフにすると、自動的にアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-115">**Note** If a component is already installed on the computer, by deselecting it on the **Custom Setup** screen it will automatically be uninstalled.</span></span>

     

7.  <span data-ttu-id="6db0d-116">[**データベースサーバー** ] ページで、パスワードを入力し、インストールパスを割り当て、情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-116">On the **Database Server** page, type the passwords, assign an installation path, save the information, and click **Next**.</span></span>

8.  <span data-ttu-id="6db0d-117">データベースの名前を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-117">Select a name for the database, and then click **Next**.</span></span>

    <span data-ttu-id="6db0d-118">**注** この手順を完了しようとしたときにエラー25109が表示される場合は、データベースをインストールするのに必要なアクセス許可を正しく設定していません。</span><span class="sxs-lookup"><span data-stu-id="6db0d-118">**Note** If error 25109 is displayed when you try to complete this step, you have incorrectly set up the permissions necessary to install the database.</span></span> <span data-ttu-id="6db0d-119">必要な SQL 権限の設定の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=132144> 。</span><span class="sxs-lookup"><span data-stu-id="6db0d-119">For details on setting up the necessary SQL permissions, please see <https://go.microsoft.com/fwlink/?LinkId=132144>.</span></span>

     

9.  <span data-ttu-id="6db0d-120">[**ディレクトリサーバー** ] 画面で、アプリケーションの仮想化サーバーと管理 Web サービスがドメインコントローラーにアクセスするために使用するドメイン名と資格情報を入力し、この情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-120">On the **Directory Server** screen, enter a domain name and credentials that Application Virtualization Servers and the Management Web Service will use to access your domain controller, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="6db0d-121">**注** インストールは、現在のコンピューターのドメインに既定値が設定されます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-121">**Note** The installation will default to the domain of the current computer.</span></span>

     

10. <span data-ttu-id="6db0d-122">[**管理者グループ**] ページで、管理者特権を持つグループの名前を入力し、この情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-122">On the **Administrator Group** page, enter the name of a group that will have Administrator privileges, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="6db0d-123">**注** 管理者権限を持つグループの名前の最初の数文字を入力することもできます。 [**次へ**] をクリックし、[**管理者グループの選択**] 画面で、結果の一覧からグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-123">**Note** You can also enter the first few characters of the name of a group that will have Administration privileges, click **Next**, and on the **Select Administrator Group** screen, select the group from the resulting list.</span></span> <span data-ttu-id="6db0d-124">次に、この情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-124">Then save this information and click **Next**.</span></span>

     

11. <span data-ttu-id="6db0d-125">[**既定のプロバイダーグループ**] ページで、アプリケーションへのアクセスを制御するグループの完全な名前を入力し、この情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-125">On the **Default Provider Group** page, enter the complete name of a group that will control access to applications, save this information, and then click **Next**.</span></span>

    <span data-ttu-id="6db0d-126">**注** アプリケーションへのアクセスを制御するグループの名前の最初の数文字を入力することもできます。 [**次へ**] をクリックし、[**既定のプロバイダーグループの選択**] 画面で一覧からグループを選びます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-126">**Note** You can also enter the first few characters of the name of a group that will control access to applications, click **Next**, and on the **Select Default Provider Group** screen, select the group in the list.</span></span> <span data-ttu-id="6db0d-127">次に、この情報を保存して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="6db0d-127">Then save this information and click **Next**.</span></span>

     

12. <span data-ttu-id="6db0d-128">**インストールウィザード**の [完了] ページで、[**完了**] をクリックしてウィザードを閉じます。</span><span class="sxs-lookup"><span data-stu-id="6db0d-128">On the **Installation Wizard Completed** page, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="6db0d-129">**重要** インストールが完了するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="6db0d-129">**Important** The installation can take a few minutes to finish.</span></span> <span data-ttu-id="6db0d-130">Windows デスクトップ通知領域の上に、インストールが正常に完了したかどうかを示すステータスメッセージが点滅します。</span><span class="sxs-lookup"><span data-stu-id="6db0d-130">A status message will flash above the Windows desktop notification area, indicating whether the installation succeeded.</span></span>

     

## <span data-ttu-id="6db0d-131">関連トピック</span><span class="sxs-lookup"><span data-stu-id="6db0d-131">Related topics</span></span>


[<span data-ttu-id="6db0d-132">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="6db0d-132">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





