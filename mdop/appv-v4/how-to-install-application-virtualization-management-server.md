---
title: Application Virtualization Management Server をインストールする方法
description: Application Virtualization Management Server をインストールする方法
author: dansimp
ms.assetid: 8184be79-8c27-4328-a3c1-183791b5556c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dfd06ee1d2448990d5a740f3d59b0e5e4b45be4d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817364"
---
# <span data-ttu-id="db639-103">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="db639-103">How to Install Application Virtualization Management Server</span></span>


<span data-ttu-id="db639-104">Application Virtualization Management Server は、アプリケーションをクライアントに公開します。</span><span class="sxs-lookup"><span data-stu-id="db639-104">The Application Virtualization Management Server publishes its applications to clients.</span></span> <span data-ttu-id="db639-105">大規模な展開の一般的な負荷分散環境では、サーバーグループ内のすべてのサーバーが同じアプリケーションをストリーミングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db639-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="db639-106">Application Virtualization Management Server がさまざまなアプリケーションを公開する場合は、サーバーをさまざまなサーバーグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="db639-106">If Application Virtualization Management Servers are to publish different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="db639-107">この場合、サーバーグループの容量を増やす必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="db639-107">In this case, you also might need to increase a server group's capacity.</span></span>

<span data-ttu-id="db639-108">ネットワーク上でターゲットコンピューターを指定していて、ローカル管理者権限を持つログインアカウントを使用している場合は、次の手順に従って、Application Virtualization Management Server をインストールし、適切なサーバーグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="db639-108">If you have designated a target computer on the network, with a login account having local Administrator privileges, you can use the following procedure to install the Application Virtualization Management Server and assign it to the appropriate server group.</span></span>

**<span data-ttu-id="db639-109">注</span><span class="sxs-lookup"><span data-stu-id="db639-109">Note</span></span>**  
<span data-ttu-id="db639-110">インストールウィザードでは、サーバーグループレコード (存在しない場合) と、Application Virtualization Management Server のメンバーシップのレコードをこのグループに作成できます。</span><span class="sxs-lookup"><span data-stu-id="db639-110">The Installation Wizard can create a server group record, if one does not exist, as well as a record of the Application Virtualization Management Server's membership in this group.</span></span>



<span data-ttu-id="db639-111">インストールプロセスが完了したら、サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="db639-111">After you complete the installation process, reboot the server.</span></span>

**<span data-ttu-id="db639-112">Application Virtualization Management Server をインストールするには</span><span class="sxs-lookup"><span data-stu-id="db639-112">To install an Application Virtualization Management Server</span></span>**

1.  <span data-ttu-id="db639-113">ターゲットコンピューターにインストールされている Application Virtualization Management Server の以前のバージョンを確認し、必要に応じてアンインストールします。</span><span class="sxs-lookup"><span data-stu-id="db639-113">Verify and, if necessary, uninstall previous versions of the Application Virtualization Management Server that are installed on the target computer.</span></span>

2.  <span data-ttu-id="db639-114">**Microsoft Application Virtualization Management Server インストール**ウィザードを開くには、ネットワーク上のアプリケーションの仮想化システム**setup.exe**プログラムの場所に移動します。このプログラムをネットワークから実行するか、またはターゲットコンピューターにディレクトリをコピーして、 **Setup.exe**ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-114">To open the **Microsoft Application Virtualization Management Server installation** wizard, navigate to the location of the Application Virtualization System **setup.exe** program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="db639-115">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-115">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="db639-116">[**使用許諾契約書**] ページで、ライセンス契約を読み、ライセンス契約に同意する場合は、[**ライセンス条項に同意**する] を選択します。</span><span class="sxs-lookup"><span data-stu-id="db639-116">On the **License Agreement** page, read the license agreement and, to accept the license agreement, select **I accept the license terms and conditions**.</span></span> <span data-ttu-id="db639-117">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-117">Click **Next**.</span></span>

5.  <span data-ttu-id="db639-118">[**登録情報**] ページで、ユーザー名と**組織**を入力する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db639-118">On the **Registering Information** page, you must enter the user name and the **Organization**.</span></span> <span data-ttu-id="db639-119">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-119">Click **Next**.</span></span>

6.  <span data-ttu-id="db639-120">[**セットアップの種類**] ページで、[**カスタム**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="db639-120">On the **Setup Type** page, select **Custom**.</span></span> <span data-ttu-id="db639-121">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-121">Click **Next**.</span></span> <span data-ttu-id="db639-122">[**カスタムセットアップ**] ページで、[ **application virtualization Server**を除くすべての application virtualization システムコンポーネント] の選択を解除し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-122">On the **Custom Setup** page, deselect all Application Virtualization System components except **Application Virtualization Server**, and then click **Next**.</span></span>

    **<span data-ttu-id="db639-123">注意</span><span class="sxs-lookup"><span data-stu-id="db639-123">Caution</span></span>**  
    <span data-ttu-id="db639-124">コンポーネントがコンピューターに既にインストールされている場合、[**カスタムセットアップ**] ウィンドウで選択を解除すると、コンポーネントが自動的にアンインストールされます。</span><span class="sxs-lookup"><span data-stu-id="db639-124">If a component is already installed on the computer, when you deselect it in the **Custom Setup** window, the component is automatically uninstalled.</span></span>



7.  <span data-ttu-id="db639-125">[**構成データベース**] ページで、使用可能なサーバーの一覧からデータベースサーバーを選ぶか、[**次のホスト名を使用**する] を選んで**サーバー名**と**ポート番号**のデータを指定して、サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="db639-125">On the **Configuration Database** page, select a database server from the list of available servers or add a server by selecting **Use the following host name** and specifying the **Server Name** and **Port Number** data.</span></span> <span data-ttu-id="db639-126">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-126">Click **Next**.</span></span>

    **<span data-ttu-id="db639-127">注</span><span class="sxs-lookup"><span data-stu-id="db639-127">Note</span></span>**  
    <span data-ttu-id="db639-128">Application Virtualization Management Server は、大文字と小文字を区別する SQL をサポートしていません。</span><span class="sxs-lookup"><span data-stu-id="db639-128">The Application Virtualization Management Server does not support case sensitive SQL.</span></span>



~~~
If a database is available, click the radio button, select the database from the list, and then click **Next**. Setup will upgrade it to this newer version. If the name does not appear in the list, enter the name in the space provided.

**Note**  
When naming a server, do not use the backslash character (/) in the server name.

If you need to install a database, see [How to Install a Database](how-to-install-a-database.md). If you would like to create a new database for this version, select **Create a new database** and specify the name that will be assigned to the new database. You can also specify a new location for the database by selecting the check box and entering the path.
~~~



8. <span data-ttu-id="db639-129">[**接続セキュリティモード**] ページで、ドロップダウンリストから目的の証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="db639-129">On the **Connection Security Mode** page, select the desired certificate from the drop-down list.</span></span> <span data-ttu-id="db639-130">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-130">Click **Next**.</span></span>

   **<span data-ttu-id="db639-131">注</span><span class="sxs-lookup"><span data-stu-id="db639-131">Note</span></span>**  
   <span data-ttu-id="db639-132">**セキュリティで保護された接続モード**の設定では、サーバー証明書が公開キー基盤からプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="db639-132">The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="db639-133">サーバー証明書がサーバーにインストールされていない場合、このオプションは利用できません。選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="db639-133">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="db639-134">使用されている証明書へのネットワークサービスアカウントの読み取りアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="db639-134">You must grant the Network Service account read access to the certificate being used.</span></span>



9. <span data-ttu-id="db639-135">[ **TCP ポートの構成**] ページで、既定のポート (554) を使用するには、[ **use default port (554)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="db639-135">On the **TCP Port Configuration** page, to use the default port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="db639-136">カスタムポートを指定するには、[**カスタムポートを使用**する] を選択し、使用するポート番号を指定します。</span><span class="sxs-lookup"><span data-stu-id="db639-136">To specify a custom port, select **Use custom port** and specify the port number that will be used.</span></span> <span data-ttu-id="db639-137">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-137">Click **Next**.</span></span>

   **<span data-ttu-id="db639-138">注</span><span class="sxs-lookup"><span data-stu-id="db639-138">Note</span></span>**  
   <span data-ttu-id="db639-139">セキュリティで保護されていない環境にサーバーをインストールする場合は、既定のポート (554) を使用するか、カスタムポートを定義できます。</span><span class="sxs-lookup"><span data-stu-id="db639-139">When you install the server in a nonsecure environment, you can use the default port (554) or you can define a custom port.</span></span>



10. <span data-ttu-id="db639-140">[**管理者グループ**] ページで、[**グループ名**] にこのサーバーを管理する権限が与えられているセキュリティグループの名前を指定します。</span><span class="sxs-lookup"><span data-stu-id="db639-140">On the **Administrator Group** page, specify the name of the security group authorized to manage this server in **Group Name**.</span></span> <span data-ttu-id="db639-141">**[次へ]** をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-141">Click **Next**.</span></span> <span data-ttu-id="db639-142">指定したグループを確認して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-142">Confirm the group specified and click **Next**.</span></span>

11. <span data-ttu-id="db639-143">[**既定のプロバイダーグループ**] ページで、既定のプロバイダーグループの名前を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-143">On the **Default Provider Group** page, specify the name of the default provider group, and then click **Next**.</span></span>

12. <span data-ttu-id="db639-144">[**コンテンツパス**] ページで、SFT ファイルが保存されるターゲットコンピューター上の場所を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-144">On the **Content Path** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

   **<span data-ttu-id="db639-145">注</span><span class="sxs-lookup"><span data-stu-id="db639-145">Note</span></span>**  
   <span data-ttu-id="db639-146">管理サーバーの HTTP または RTSP ポートが既に割り当てられている場合は、新しいポートを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="db639-146">If the HTTP or RTSP port for the Management Server is already allocated, you will be prompted to choose a new port.</span></span> <span data-ttu-id="db639-147">目的のポートを選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-147">Select the desired port, and then click **Next**.</span></span>



13. <span data-ttu-id="db639-148">[**プログラムをインストールする準備ができ**ました] ページで、Application Virtualization Management Server をインストールするには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-148">On the **Ready to Install the Program** page, to install the Application Virtualization Management Server, click **Install**.</span></span>

   **<span data-ttu-id="db639-149">注</span><span class="sxs-lookup"><span data-stu-id="db639-149">Note</span></span>**  
   <span data-ttu-id="db639-150">この手順を完了しようとしたときにエラー25120が表示される場合は、IIS**管理スクリプトとツール**を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="db639-150">If error 25120 is displayed when you try to complete this step, you need to enable IIS **Management Scripts and Tools**.</span></span> <span data-ttu-id="db639-151">この Windows 機能を有効にするには、[**プログラムと機能**] コントロールパネルを開き、[ **Windows 機能を有効または無効**にする] を選択して、[**インターネットインフォメーションサービス**] に移動します。</span><span class="sxs-lookup"><span data-stu-id="db639-151">To enable this Windows feature, open the **Programs and Features** control panel, select **Turn Windows features on or off**, and navigate to **Internet Information Services.**</span></span>

   <span data-ttu-id="db639-152">[ **Web 管理ツール**] で、 **IIS 管理スクリプトとツール**を有効にします。</span><span class="sxs-lookup"><span data-stu-id="db639-152">Under **Web Management Tools**, enable **IIS Management Scripts and Tools**.</span></span>



14. <span data-ttu-id="db639-153">**インストールウィザードの完了**画面で、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="db639-153">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

   **<span data-ttu-id="db639-154">重要</span><span class="sxs-lookup"><span data-stu-id="db639-154">Important</span></span>**  
   <span data-ttu-id="db639-155">インストールが完了するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="db639-155">The installation can take a few minutes to finish.</span></span> <span data-ttu-id="db639-156">Windows デスクトップ通知領域の上に、インストールが成功したことを示す状態メッセージが点滅します。</span><span class="sxs-lookup"><span data-stu-id="db639-156">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

   <span data-ttu-id="db639-157">プロンプトが表示された場合は、コンピューターを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="db639-157">It is not necessary to reboot the computer when prompted.</span></span> <span data-ttu-id="db639-158">ただし、システムのパフォーマンスを最適化するには、再起動をお勧めします。</span><span class="sxs-lookup"><span data-stu-id="db639-158">However, to optimize system performance, a reboot is recommended.</span></span>



## <span data-ttu-id="db639-159">関連トピック</span><span class="sxs-lookup"><span data-stu-id="db639-159">Related topics</span></span>


[<span data-ttu-id="db639-160">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="db639-160">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)









