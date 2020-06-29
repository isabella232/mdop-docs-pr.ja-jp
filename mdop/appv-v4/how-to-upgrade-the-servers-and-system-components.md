---
title: サーバーおよびシステム コンポーネントをアップグレードする方法
description: サーバーおよびシステム コンポーネントをアップグレードする方法
author: dansimp
ms.assetid: 7d8374fe-5897-452e-923e-556a854b2024
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 61f8742a2f5e3c17083a77b839dfbee85ea00e24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816424"
---
# <span data-ttu-id="57044-103">サーバーおよびシステム コンポーネントをアップグレードする方法</span><span class="sxs-lookup"><span data-stu-id="57044-103">How to Upgrade the Servers and System Components</span></span>


<span data-ttu-id="57044-104">すべての Application Virtualization システムコンピューターにインストールされているソフトウェアコンポーネントをアップグレードするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="57044-104">Use the following procedure to upgrade software components installed on all Application Virtualization System computers.</span></span> <span data-ttu-id="57044-105">アプリケーションの仮想化システムサービスは、アップグレードされた後、各コンピューターで自動的に再開されます。</span><span class="sxs-lookup"><span data-stu-id="57044-105">Application Virtualization System services will be restarted automatically on each computer after it has been upgraded.</span></span>

**<span data-ttu-id="57044-106">注</span><span class="sxs-lookup"><span data-stu-id="57044-106">Note</span></span>**  
-   <span data-ttu-id="57044-107">アップグレードプロセスでは、すべての Application Virtualization システムサービスが停止するため、システムがサービスを利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="57044-107">The upgrade process stops all Application Virtualization System services, thereby taking the system out of service.</span></span> <span data-ttu-id="57044-108">アップグレードプロセスを開始する前に、ユーザーセッションを終了する必要があります。また、環境内の Application Virtualization Server サービスをすべて停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57044-108">User sessions should be shut down before you begin the upgrade process, and you should stop all Application Virtualization Server services in your environment.</span></span>

-   <span data-ttu-id="57044-109">Application Virtualization データベースへのアクセスを共有しているサーバーが複数ある場合は、データベースのアップグレード中にそれらのすべてのサーバーをオフラインにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57044-109">If you have more than one server that is sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="57044-110">データベースのアップグレードについては、通常のビジネス慣行に従う必要がありますが、最初にテストサーバーでデータベースのバックアップコピーを使用してデータベースのアップグレードをテストすることをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="57044-110">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="57044-111">次に、最初のアップグレード用にいずれかのサーバーを選択する必要があります。これにより、データベーススキーマがアップグレードされます。</span><span class="sxs-lookup"><span data-stu-id="57044-111">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="57044-112">運用データベースのアップグレードが正常に完了したら、他のサーバーをアップグレードできます。</span><span class="sxs-lookup"><span data-stu-id="57044-112">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

-   <span data-ttu-id="57044-113">Microsoft Application Virtualization (App V) 4.5 にアップグレードできるのは、Microsoft Application Virtualization (App-v) 4.1 または 4.1 SP1 のみです。</span><span class="sxs-lookup"><span data-stu-id="57044-113">You can upgrade to Microsoft Application Virtualization (App-V)4.5 only from Microsoft Application Virtualization (App-V)4.1 or4.1 SP1.</span></span> <span data-ttu-id="57044-114">App-v 4.0 以降を実行するには、アプリをアンインストールするか、4.1 または 4.1 SP1 にアップグレードする必要があります。</span><span class="sxs-lookup"><span data-stu-id="57044-114">App-V4.0 and earlier must be uninstalled or upgraded to4.1 or4.1 SP1 before upgrading to App-V4.5.</span></span>

 

**<span data-ttu-id="57044-115">Application Virtualization システムコンピューターのソフトウェアコンポーネントをアップグレードするには</span><span class="sxs-lookup"><span data-stu-id="57044-115">To upgrade software components on Application Virtualization System computers</span></span>**

1.  <span data-ttu-id="57044-116">ネットワーク上のセットアッププログラムの場所に移動し、ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、Setup.exe ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-116">Navigate to the location of the Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the Setup.exe file.</span></span>

2.  <span data-ttu-id="57044-117">インストールウィザードの [**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-117">On the **Welcome** page of the Installation Wizard, click **Next**.</span></span>

3.  <span data-ttu-id="57044-118">[**使用許諾契約書**] ページで、使用許諾契約書を読み、[**使用許諾契約書に同意**します] をオンにして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-118">On the **License Agreement** page, read the license agreement, check **I accept the terms in the license agreement**, and click **Next**.</span></span>

4.  <span data-ttu-id="57044-119">[**インストールさ**れたソフトウェア] ページが開き、インストールされている Application Virtualization システムコンポーネントと各コンポーネントのバージョンの一覧が表示されたら、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-119">When the **Installed Software** page opens and displays a list of the installed Application Virtualization System components and the version of each component, click **Next**.</span></span>

5.  <span data-ttu-id="57044-120">[**セッション損失の警告**] ページで、表示されたメッセージを読み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-120">On the **Session Loss Warning** page, read the displayed message and click **Next**.</span></span>

6.  <span data-ttu-id="57044-121">[**構成データベースへの接続**] ページで、ページ上のコンテンツを確認し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-121">On the **Connect to Configuration Database** page, review the content on the page and click **Next**.</span></span>

7.  <span data-ttu-id="57044-122">[**データベースのアップグレードが必要**] ページが表示されている場合は、データベースのアップグレードが必要です。</span><span class="sxs-lookup"><span data-stu-id="57044-122">If the **Database Upgrade Required** page is displayed, a database upgrade is required.</span></span> <span data-ttu-id="57044-123">データベース管理者の資格情報を入力し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-123">Enter the database administrative credentials, and then click **Next**.</span></span> <span data-ttu-id="57044-124">このページが表示されない場合は、手順9に進んでください。</span><span class="sxs-lookup"><span data-stu-id="57044-124">If this page is not displayed, skip to Step 9.</span></span>

8.  <span data-ttu-id="57044-125">[**バックアップ構成データベース**] ページで適切なチェックボックスをオンにしてバックアップを実行し、既存の場所にエクスポートして、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-125">On the **Backup Configuration Database** page, check the appropriate boxes to perform the backup and export it to an existing location, and then click **Next**.</span></span>

    <span data-ttu-id="57044-126">**重要** アップグレードに失敗した場合に、以前のバージョンに戻すことができるようにするには、[**構成データベースのバックアップを実行**する] チェックボックスをオンにしてください。構成データは失われます。</span><span class="sxs-lookup"><span data-stu-id="57044-126">**Important** If you want to be able to roll back to the previous version in the event of an upgrade failure, make sure you check the **Perform a backup of the configuration database** box, or you will lose the configuration data.</span></span>

    <span data-ttu-id="57044-127">VSS を使用してデータベースを復元する場合は、まず管理サーバー上の App-v Server サービスを停止する必要があります。</span><span class="sxs-lookup"><span data-stu-id="57044-127">When you want to restore a database with VSS, you must first stop the App-V Server Service on the Management Server.</span></span> <span data-ttu-id="57044-128">この操作は、同じデータベースに複数のサーバーが接続されている場合に、すべての管理サーバーで行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="57044-128">This should be done on every Management server if there is more than one server connected to the same database.</span></span>

     

9.  <span data-ttu-id="57044-129">[パッケージの最初の**検証**] ページで、コンテンツを読み、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-129">On the first **Package Validation** page, read the content and then click **Next**.</span></span>

10. <span data-ttu-id="57044-130">2番目の [**パッケージの検証**] ページで、[メモ帳] ウィンドウにパッケージの検証の詳細を表示するオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="57044-130">On the second **Package Validation** page, you have the option of displaying the details of the package validation in a Notepad window.</span></span> <span data-ttu-id="57044-131">詳細を表示するには、[**詳細**] をクリックします。それ以外の場合は、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-131">To see the details, click **Details**; otherwise, click **Next**.</span></span>

11. <span data-ttu-id="57044-132">[**プログラムをアップグレードする準備ができ**ました] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-132">On the **Ready to Upgrade the Program** page, click **Next**.</span></span>

12. <span data-ttu-id="57044-133">**インストールウィザード**の [完了] ページで、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="57044-133">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

13. <span data-ttu-id="57044-134">Application Virtualization 管理コンソールまたは Application Virtualization Server ソフトウェアコンポーネントをインストールした他のすべてのコンピューターで、手順 1 ~ 12 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="57044-134">Repeat steps 1–12 on all other computers where you installed the Application Virtualization Management Console or the Application Virtualization Server software component.</span></span>

    <span data-ttu-id="57044-135">データストアをアップグレードした後で、通常の操作を再開できます。</span><span class="sxs-lookup"><span data-stu-id="57044-135">After upgrading the data store, you can resume normal operation.</span></span> <span data-ttu-id="57044-136">(サーバーまたは App-v 管理 Web サービスをアップグレードすると、データストアがアップグレードされます)。</span><span class="sxs-lookup"><span data-stu-id="57044-136">(The data store is upgraded when you upgrade any server or the App-V Management Web Service.)</span></span>

## <span data-ttu-id="57044-137">関連トピック</span><span class="sxs-lookup"><span data-stu-id="57044-137">Related topics</span></span>


[<span data-ttu-id="57044-138">Application Virtualization の展開およびアップグレードに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="57044-138">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





