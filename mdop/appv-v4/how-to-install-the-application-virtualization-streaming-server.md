---
title: Application Virtualization Streaming Server をインストールする方法
description: Application Virtualization Streaming Server をインストールする方法
author: dansimp
ms.assetid: a3065257-fb5a-4d92-98f8-7ef996c61db9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4e4f8421ef1c0e60a7df92d41be98a5d2bc0132
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817327"
---
# <span data-ttu-id="67112-103">Application Virtualization Streaming Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="67112-103">How to Install the Application Virtualization Streaming Server</span></span>


<span data-ttu-id="67112-104">Application Virtualization Streaming Server は、アプリケーションをクライアントに公開します。</span><span class="sxs-lookup"><span data-stu-id="67112-104">The Application Virtualization Streaming Server publishes its applications to clients.</span></span> <span data-ttu-id="67112-105">大規模な展開の一般的な負荷分散環境では、サーバーグループ内のすべてのサーバーが同じアプリケーションをストリーミングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="67112-105">In a load-balanced environment, which is typical of large deployments, all servers in a server group should stream the same applications.</span></span> <span data-ttu-id="67112-106">Application Virtualization ストリーミングサーバーがさまざまなアプリケーションをストリーミングする場合は、サーバーをさまざまなサーバーグループに割り当てます。</span><span class="sxs-lookup"><span data-stu-id="67112-106">If Application Virtualization Streaming Servers are to stream different applications, assign the servers to different server groups.</span></span> <span data-ttu-id="67112-107">この場合、サーバーグループの容量を増やす必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="67112-107">In this case, you might also have to increase a server group's capacity.</span></span>

<span data-ttu-id="67112-108">ネットワーク上でターゲットコンピューターを指定していて、ローカル管理者権限を持つログオンアカウントを使用している場合は、次の手順に従って、Application Virtualization Streaming Server をインストールし、適切なサーバーグループに割り当てることができます。</span><span class="sxs-lookup"><span data-stu-id="67112-108">If you have designated a target computer on the network, with a logon account having local administrative privileges, you can use the following procedure to install the Application Virtualization Streaming Server and assign it to the appropriate server group.</span></span>

<span data-ttu-id="67112-109">**注** インストールウィザードでは、サーバーグループレコード (存在しない場合) と、Application Virtualization ストリーミングサーバーメンバーシップの記録をこのグループに作成できます。</span><span class="sxs-lookup"><span data-stu-id="67112-109">**Note** The Installation Wizard can create a server group record, if one does not exist, and a record of the Application Virtualization Streaming Server membership in this group.</span></span>

 

<span data-ttu-id="67112-110">インストールプロセスが完了したら、サーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="67112-110">After you complete the installation process, restart the server.</span></span>

**<span data-ttu-id="67112-111">Application Virtualization ストリーミングサーバーをインストールするには</span><span class="sxs-lookup"><span data-stu-id="67112-111">To install an Application Virtualization Streaming Server</span></span>**

1.  <span data-ttu-id="67112-112">以前のバージョンの Application Virtualization Streaming Server がターゲットコンピューターにインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="67112-112">Verify that no earlier versions of the Application Virtualization Streaming Server are installed on your target computer.</span></span>

    <span data-ttu-id="67112-113">**重要** このコンピューターに App-v Management Server がインストールされていないことを確認します。</span><span class="sxs-lookup"><span data-stu-id="67112-113">**Important** Make sure that the App-V Management Server is not installed on this computer.</span></span> <span data-ttu-id="67112-114">2つの製品を同じコンピューターにインストールすることはできません。</span><span class="sxs-lookup"><span data-stu-id="67112-114">The two products cannot be installed on the same computer.</span></span>

     

2.  <span data-ttu-id="67112-115">ネットワーク上でアプリケーションの仮想化システムセットアッププログラムが保存されている場所に移動します。ネットワークからこのプログラムを実行するか、またはターゲットコンピューターにディレクトリをコピーして、 **Setup.exe**ファイルをダブルクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-115">Navigate to the location of the Application Virtualization System Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the **Setup.exe** file.</span></span>

3.  <span data-ttu-id="67112-116">[**ようこそ**] ページで、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-116">On the **Welcome** page, click **Next**.</span></span>

4.  <span data-ttu-id="67112-117">[**ライセンス契約**] ページでライセンス条項に同意するには、[ライセンス**条項に同意**します] を選択し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-117">On the **License Agreement** page, to accept the license terms, select **I accept the licensing terms and conditions**, and then click **Next**.</span></span>

5.  <span data-ttu-id="67112-118">[ユーザー**情報**] ページで、**ユーザー名**と組織を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-118">On the **Customer Information** page, specify the **User name** and the organization, and then click **Next**.</span></span>

6.  <span data-ttu-id="67112-119">[**インストールパス**] ページで [**参照**] をクリックし、ストリーミングサーバーをインストールする場所を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-119">On the **Installation Path** page, click **Browse**, specify the location where you want to install the Streaming Server, and then click **Next**.</span></span>

7.  <span data-ttu-id="67112-120">[**接続セキュリティモード**] ページで、ドロップダウンリストから目的の証明書を選び、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-120">On the **Connection Security Mode** page, select the desired certificate from the drop-down list, and then click **Next**.</span></span>

    <span data-ttu-id="67112-121">**注** **セキュリティで保護された接続モード**の設定では、サーバー証明書が公開キー基盤からプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="67112-121">**Note** The **Secure Connection Mode** setting requires the server to have a server certificate provisioned to it from a public key infrastructure.</span></span> <span data-ttu-id="67112-122">サーバー証明書がサーバーにインストールされていない場合、このオプションは利用できません。選択することはできません。</span><span class="sxs-lookup"><span data-stu-id="67112-122">If a server certificate is not installed on the server, this option is unavailable and cannot be selected.</span></span> <span data-ttu-id="67112-123">使用されている証明書へのネットワークサービスアカウントの読み取りアクセス権を付与する必要があります。</span><span class="sxs-lookup"><span data-stu-id="67112-123">You must grant the Network Service account read access to the certificate being used.</span></span>

     

8.  <span data-ttu-id="67112-124">[ **TCP ポートの構成**] ページで、標準ポート (554) を使用するには、[ **use default port (554)**] を選びます。</span><span class="sxs-lookup"><span data-stu-id="67112-124">On the **TCP Port Configuration** page, to use the standard port (554), select **Use default port (554)**.</span></span> <span data-ttu-id="67112-125">カスタムポートを指定するには、[**カスタムポートを使用**する] を選択し、提供されたフィールドにポート番号を指定して、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-125">To specify a custom port, select **Use custom port**, specify the port number in the field provided, and then click **Next**.</span></span>

    <span data-ttu-id="67112-126">**注** セキュリティで保護されていないシナリオにサーバーをインストールする場合は、既定のポート (554) を使用するか、カスタムポートを定義することができます。</span><span class="sxs-lookup"><span data-stu-id="67112-126">**Note** When you install the server in a nonsecure scenario, you can use the default port (554), or you can define a custom port.</span></span>

     

9.  <span data-ttu-id="67112-127">[**コンテンツルート**] ページで、SFT ファイルが保存されるターゲットコンピューター上の場所を指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-127">On the **Content Root** page, specify the location on the target computer where SFT files will be saved, and then click **Next**.</span></span>

    <span data-ttu-id="67112-128">**注** 仮想アプリケーションストリーミングサーバーの HTTP または RTSP ポートが既に割り当てられている場合は、新しいポートを選択するように求められます。</span><span class="sxs-lookup"><span data-stu-id="67112-128">**Note** If the HTTP or RTSP port for the Virtual Application Streaming Server is already allocated, you will be prompted to select a new port.</span></span> <span data-ttu-id="67112-129">目的のポートを指定し、[**次へ**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-129">Specify the desired port, and then click **Next**.</span></span>

     

10. <span data-ttu-id="67112-130">[**詳細設定**] 画面で、次の情報を入力します。</span><span class="sxs-lookup"><span data-stu-id="67112-130">On the **Advanced Setting** screen, enter the following information:</span></span>

    1.  **<span data-ttu-id="67112-131">クライアント接続の最大数</span><span class="sxs-lookup"><span data-stu-id="67112-131">Max client connections</span></span>**

    2.  **<span data-ttu-id="67112-132">接続タイムアウト (秒)</span><span class="sxs-lookup"><span data-stu-id="67112-132">Connection timeout (sec)</span></span>**

    3.  **<span data-ttu-id="67112-133">RTSP スレッドプールサイズ</span><span class="sxs-lookup"><span data-stu-id="67112-133">RTSP thread pool size</span></span>**

    4.  **<span data-ttu-id="67112-134">RTSP タイムアウト (秒)</span><span class="sxs-lookup"><span data-stu-id="67112-134">RTSP timeout (sec)</span></span>**

    5.  **<span data-ttu-id="67112-135">コアプロセスの数</span><span class="sxs-lookup"><span data-stu-id="67112-135">Number of core processes</span></span>**

    6.  **<span data-ttu-id="67112-136">コアタイムアウト (秒)</span><span class="sxs-lookup"><span data-stu-id="67112-136">Core timeout (sec)</span></span>**

    7.  **<span data-ttu-id="67112-137">ユーザー認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="67112-137">Enable User authentication</span></span>**

    8.  **<span data-ttu-id="67112-138">ユーザー認証を有効にする</span><span class="sxs-lookup"><span data-stu-id="67112-138">Enable User authorization</span></span>**

    9.  **<span data-ttu-id="67112-139">キャッシュブロックサイズ (KB)</span><span class="sxs-lookup"><span data-stu-id="67112-139">Cache block size (KB)</span></span>**

    10. **<span data-ttu-id="67112-140">キャッシュの最大サイズ (MB)</span><span class="sxs-lookup"><span data-stu-id="67112-140">Maximum cache size (MB)</span></span>**

    <span data-ttu-id="67112-141">**注** App-v ストリーミングサーバーは、NTFS ファイルシステムのアクセス許可を使用して、コンテンツ共有の下にあるアプリケーションへのアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="67112-141">**Note** The App-V Streaming Server uses NTFS file system permissions to control access to the applications under the Content share.</span></span> <span data-ttu-id="67112-142">**ユーザー認証を有効**にし、**ユーザー認証を有効**にして、サーバーがこれらのアクセス制御リスト (acl) をチェックして強制するかどうかを制御します。</span><span class="sxs-lookup"><span data-stu-id="67112-142">Use **Enable User authentication** and **Enable User authorization** to control whether the server checks and enforces those access control lists (ACLs) or not.</span></span>

     

11. <span data-ttu-id="67112-143">[**プログラムをインストールする準備ができ**ました] ページで、インストールを開始するには、[**インストール**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-143">On the **Ready to Install the Program** page, to start the installation, click **Install**.</span></span>

12. <span data-ttu-id="67112-144">**インストールウィザードの完了**画面で、[**完了**] をクリックします。</span><span class="sxs-lookup"><span data-stu-id="67112-144">On the **Installation Wizard Completed** screen, to close the wizard, click **Finish**.</span></span>

    <span data-ttu-id="67112-145">**重要** インストールが完了するまで数分かかることがあります。</span><span class="sxs-lookup"><span data-stu-id="67112-145">**Important** The installation can take several minutes to finish.</span></span> <span data-ttu-id="67112-146">Windows デスクトップ通知領域の上に、インストールが成功したことを示す状態メッセージが点滅します。</span><span class="sxs-lookup"><span data-stu-id="67112-146">A status message will flash above the Windows desktop notification area, indicating that the installation succeeded.</span></span>

    <span data-ttu-id="67112-147">メッセージが表示されたときに、コンピューターを再起動する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="67112-147">It is not required to restart the computer when you are prompted.</span></span> <span data-ttu-id="67112-148">ただし、システムのパフォーマンスを最適化するには、再起動することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="67112-148">However, to optimize system performance, we recommend a restart.</span></span>

     

13. <span data-ttu-id="67112-149">インストールする仮想アプリケーションサーバーごとに、手順 1 ~ 12 を繰り返します。</span><span class="sxs-lookup"><span data-stu-id="67112-149">Repeat Steps 1–12 for each Virtual Application Server that you have to install.</span></span>

## <span data-ttu-id="67112-150">関連トピック</span><span class="sxs-lookup"><span data-stu-id="67112-150">Related topics</span></span>


[<span data-ttu-id="67112-151">サーバーおよびシステム コンポーネントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="67112-151">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





