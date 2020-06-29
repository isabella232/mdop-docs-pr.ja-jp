---
title: App-V 5.0 の高可用性の計画
description: App-V 5.0 の高可用性の計画
author: dansimp
ms.assetid: 6d9a6492-23f8-465c-82e5-49c863594156
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ebf586de7cae19d40d76c9c0c845f93e7bd9021b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10813491"
---
# <span data-ttu-id="12431-103">App-V 5.0 の高可用性の計画</span><span class="sxs-lookup"><span data-stu-id="12431-103">Planning for High Availability with App-V 5.0</span></span>


<span data-ttu-id="12431-104">Microsoft Application Virtualization 5.0 (App-v 5.0) システム構成は、利用可能な高レベルのサービスを維持するオプションを利用できます。</span><span class="sxs-lookup"><span data-stu-id="12431-104">Microsoft Application Virtualization 5.0 (App-V 5.0) system configurations can take advantage of options that maintain a high level of available service.</span></span>

<span data-ttu-id="12431-105">次のセクションの情報を使用して、高可用性構成で App-v 5.0 を展開するオプションについて理解してください。</span><span class="sxs-lookup"><span data-stu-id="12431-105">Use the information in the following sections to help you understand the options to deploy App-V 5.0 in a highly available configuration.</span></span>

-   [<span data-ttu-id="12431-106">Microsoft SQL Server クラスタリングのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-106">Support for Microsoft SQL Server clustering</span></span>](#bkmk-sqlcluster)

-   [<span data-ttu-id="12431-107">IIS ネットワーク負荷分散のサポート</span><span class="sxs-lookup"><span data-stu-id="12431-107">Support for IIS Network Load Balancing</span></span>](#bkmk-iisloadbal)

-   [<span data-ttu-id="12431-108">(SCS) モードでのクラスター化されたファイルサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-108">Support for clustered file servers when running (SCS) mode</span></span>](#bkmk-clusterscsmode)

-   [<span data-ttu-id="12431-109">Microsoft SQL Server ミラーリングのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-109">Support for Microsoft SQL Server Mirroring</span></span>](#bkmk-sqlmirroring)

-   [<span data-ttu-id="12431-110">Microsoft SQL Server が常にサポートされる</span><span class="sxs-lookup"><span data-stu-id="12431-110">Support for Microsoft SQL Server Always On</span></span>](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a><span data-ttu-id="12431-111">Microsoft SQL Server クラスタリングのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-111">Support for Microsoft SQL Server clustering</span></span>


<span data-ttu-id="12431-112">Microsoft SQL Server クラスターを実行しているコンピューターで、App-v 管理データベースとレポートデータベースを実行できます。</span><span class="sxs-lookup"><span data-stu-id="12431-112">You can run the App-V Management database and Reporting database on computers that are running Microsoft SQL Server clusters.</span></span> <span data-ttu-id="12431-113">ただし、スクリプトを使用してデータベースをインストールする必要があります。</span><span class="sxs-lookup"><span data-stu-id="12431-113">However, you must install the databases using scripts.</span></span>

<span data-ttu-id="12431-114">手順については、「 [SQL スクリプトを使用して App-v データベースを展開する方法](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-114">For instructions, see [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md).</span></span>

## <a href="" id="bkmk-iisloadbal"></a><span data-ttu-id="12431-115">IIS ネットワーク負荷分散のサポート</span><span class="sxs-lookup"><span data-stu-id="12431-115">Support for IIS Network Load Balancing</span></span>


<span data-ttu-id="12431-116">インターネットインフォメーションサービス (IIS) のネットワーク負荷分散を使って、アプリを実行しているコンピューターに対して可用性の高い環境を構成することができます。これは、IIS によって展開される、管理、公開、レポートサービスです。</span><span class="sxs-lookup"><span data-stu-id="12431-116">You can use Internet Information Services (IIS) Network Load Balancing to configure a highly available environment for computers running the App-V 5.x Management, Publishing, and Reporting services which are deployed through IIS.</span></span>

<span data-ttu-id="12431-117">Windows Server オペレーティングシステムを実行しているコンピューターで IIS とネットワーク負荷分散を構成する方法については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-117">Review the following for more information about configuring IIS and Network Load Balancing for computers running Windows Server operating systems:</span></span>

-   <span data-ttu-id="12431-118">インターネットインフォメーションサービス (IIS) 7.0 の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="12431-118">Provides information about configuring Internet Information Services (IIS) 7.0.</span></span>

    <span data-ttu-id="12431-119">[高可用性とスケーラビリティを実現する-ARR と NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)</span><span class="sxs-lookup"><span data-stu-id="12431-119">[Achieving High Availability and Scalability - ARR and NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)</span></span>

-   <span data-ttu-id="12431-120">Microsoft Windows Server の構成</span><span class="sxs-lookup"><span data-stu-id="12431-120">Configuring Microsoft Windows Server</span></span>

    <span data-ttu-id="12431-121">[ネットワーク負荷分散](https://go.microsoft.com/fwlink/?LinkId=316370)( https://go.microsoft.com/fwlink/?LinkId=316370) .</span><span class="sxs-lookup"><span data-stu-id="12431-121">[Network Load Balancing](https://go.microsoft.com/fwlink/?LinkId=316370) (https://go.microsoft.com/fwlink/?LinkId=316370).</span></span>

    <span data-ttu-id="12431-122">この情報は、Windows Server2008、Windows Server2008R2、または Windows Server2012 の IIS ネットワーク負荷分散 (NLB) クラスターにも適用されます。</span><span class="sxs-lookup"><span data-stu-id="12431-122">This information also applies to IIS Network Load Balancing (NLB) clusters in Windows Server2008, Windows Server2008R2, or Windows Server2012.</span></span>

    <span data-ttu-id="12431-123">**注** Windows Server2012 の IIS ネットワーク負荷分散機能は、通常、Windows Server2008R2 と同じです。</span><span class="sxs-lookup"><span data-stu-id="12431-123">**Note** The IIS Network Load Balancing functionality in Windows Server2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="12431-124">ただし、一部のタスクの詳細は Windows Server2012 で変更されています。</span><span class="sxs-lookup"><span data-stu-id="12431-124">However, some task details are changed in Windows Server2012.</span></span> <span data-ttu-id="12431-125">新しいタスクを実行する方法については、「 [Windows server 2012 R2 Preview の一般的な管理タスクとナビゲーション」および「Windows server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=316371) 。</span><span class="sxs-lookup"><span data-stu-id="12431-125">For information on new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) (https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

     

## <a href="" id="bkmk-clusterscsmode"></a><span data-ttu-id="12431-126">(SCS) モードでのクラスター化されたファイルサーバーのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-126">Support for clustered file servers when running (SCS) mode</span></span>


<span data-ttu-id="12431-127">クラスター化されたファイルサーバーを使用して、共有コンテンツストア (SCS) モードでの App-v 5.0 の実行がサポートされています。</span><span class="sxs-lookup"><span data-stu-id="12431-127">Running App-V 5.0 in Share Content Store (SCS) mode with clustered file servers is supported.</span></span>

<span data-ttu-id="12431-128">この構成を有効にするには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="12431-128">The following steps can be used to enable this configuration:</span></span>

-   <span data-ttu-id="12431-129">クライアント SCS モードで実行するようにアプリ-V 5.0 を構成します。</span><span class="sxs-lookup"><span data-stu-id="12431-129">Configure App-V 5.0 to run in client SCS mode.</span></span> <span data-ttu-id="12431-130">App-v 5.0 SCS モードの構成の詳細については、「[共有コンテンツストアモード用に app-v 5.0 クライアントをインストールする方法](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-130">For more information about configuring App-V 5.0 SCS mode, see [How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md).</span></span>

-   <span data-ttu-id="12431-131">Microsoft Server2012 scale out モードとプレ**2012**モードの両方で構成されているファイルサーバークラスターを仮想 SAN で構成します。</span><span class="sxs-lookup"><span data-stu-id="12431-131">Configure the file server cluster configured in both the Microsoft Server2012 scale out mode and pre **2012** mode with a virtual SAN.</span></span>

<span data-ttu-id="12431-132">次の手順を使用して、構成を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="12431-132">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="12431-133">公開サーバーにパッケージを追加します。</span><span class="sxs-lookup"><span data-stu-id="12431-133">Add a package on the publishing server.</span></span> <span data-ttu-id="12431-134">パッケージの追加の詳細については、「[管理コンソールを使用してパッケージを追加またはアップグレードする方法](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-134">For more information about adding a package, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md).</span></span>

2.  <span data-ttu-id="12431-135">App-v 5.0 クライアントを実行しているコンピューターで公開更新を実行し、アプリケーションを開きます。</span><span class="sxs-lookup"><span data-stu-id="12431-135">Perform a publishing refresh on the computer running the App-V 5.0 client and open an application.</span></span>

3.  <span data-ttu-id="12431-136">フェールオーバーが正常に動作するように、クラスターノードの中間公開の更新と中間ストリームを切り替えます。</span><span class="sxs-lookup"><span data-stu-id="12431-136">Switch cluster nodes mid-publishing refresh and mid-streaming to ensure fail-over works correctly.</span></span>

<span data-ttu-id="12431-137">Windows Server フェールオーバークラスターの構成の詳細については、以下を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-137">Review the following for more information about configuring Windows Server Failover clusters:</span></span>

-   <span data-ttu-id="12431-138">[チェックリスト: クラスター化されたファイルサーバーを作成する](https://go.microsoft.com/fwlink/?LinkId=316372)( https://go.microsoft.com/fwlink/?LinkId=316372) .</span><span class="sxs-lookup"><span data-stu-id="12431-138">[Checklist: Create a Clustered File Server](https://go.microsoft.com/fwlink/?LinkId=316372) (https://go.microsoft.com/fwlink/?LinkId=316372).</span></span>

-   <span data-ttu-id="12431-139">[Windows Server 2012 フェールオーバークラスター () でクラスターの共有ボリュームを使用](https://go.microsoft.com/fwlink/?LinkId=316373) https://go.microsoft.com/fwlink/?LinkId=316373) します。</span><span class="sxs-lookup"><span data-stu-id="12431-139">[Use Cluster Shared Volumes in a Windows Server 2012 Failover Cluster](https://go.microsoft.com/fwlink/?LinkId=316373) (https://go.microsoft.com/fwlink/?LinkId=316373).</span></span>

## <a href="" id="bkmk-sqlmirroring"></a><span data-ttu-id="12431-140">Microsoft SQL Server ミラーリングのサポート</span><span class="sxs-lookup"><span data-stu-id="12431-140">Support for Microsoft SQL Server Mirroring</span></span>


<span data-ttu-id="12431-141">Microsoft SQL Server ミラーリング (app-v 5.0 management server データベースが2つの SQL Server インスタンスを使ってミラーリングされている場合は、app-v 5.0 management server データベースがサポートされます。</span><span class="sxs-lookup"><span data-stu-id="12431-141">Using Microsoft SQL Server mirroring, where the App-V 5.0 management server database is mirrored utilizing two SQL Server instances, for App-V 5.0 management server databases is supported.</span></span>

<span data-ttu-id="12431-142">Microsoft SQL Server ミラーリングの構成の詳細については、次の情報を参照してください。</span><span class="sxs-lookup"><span data-stu-id="12431-142">Review the following for more information about configuring Microsoft SQL Server Mirroring:</span></span>

-   <span data-ttu-id="12431-143">[方法: ミラーリング用のミラーデータベースの準備 (transact-sql)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)</span><span class="sxs-lookup"><span data-stu-id="12431-143">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)</span></span>

-   <span data-ttu-id="12431-144">[Windows 認証を使ってデータベースミラーリングセッションを確立する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)</span><span class="sxs-lookup"><span data-stu-id="12431-144">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)</span></span>

<span data-ttu-id="12431-145">次の手順を使用して、構成を検証することができます。</span><span class="sxs-lookup"><span data-stu-id="12431-145">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="12431-146">Microsoft SQL Server ミラーリングセッションを開始します。</span><span class="sxs-lookup"><span data-stu-id="12431-146">Initiate a Microsoft SQL Server Mirroring session.</span></span>

2.  <span data-ttu-id="12431-147">新しいマスター Microsoft SQL Server インスタンスを指定するには、[**フェールオーバー** ] を選択します。</span><span class="sxs-lookup"><span data-stu-id="12431-147">Select **Failover** to designate a new master Microsoft SQL Server instance.</span></span>

3.  <span data-ttu-id="12431-148">フェールオーバー後も App-v 5.0 management server が予期したとおりに機能することを確認します。</span><span class="sxs-lookup"><span data-stu-id="12431-148">Verify that the App-V 5.0 management server continues to function as expected after the failover.</span></span>

<span data-ttu-id="12431-149">管理サーバー上の接続文字列を変更して、\*\*フェールオーバーパートナー = &lt; server2 &gt; \*\*を含めることができます。</span><span class="sxs-lookup"><span data-stu-id="12431-149">The connection string on the management server can be modified to include **failover partner = &lt;server2&gt;**.</span></span> <span data-ttu-id="12431-150">これは、ミラーのプライマリがセカンダリにフェールオーバーされた場合にのみ役立ちます。また、App-v 5.0 クライアントを実行しているコンピューターでは、再起動した後に新しい接続が行われます。</span><span class="sxs-lookup"><span data-stu-id="12431-150">This will only help when the primary on the mirror has failed over to the secondary and the computer running the App-V 5.0 client is doing a fresh connection (say after reboot).</span></span>

<span data-ttu-id="12431-151">次の手順を使用して、\*\*フェイルオーバーパートナー = &lt; server2 &gt; \*\*を含むように接続文字列を変更します。</span><span class="sxs-lookup"><span data-stu-id="12431-151">Use the following steps to modify the connection string to include **failover partner = &lt;server2&gt;**:</span></span>

<span data-ttu-id="12431-152">**重要** このトピックでは、レジストリエディターを使用して Windows レジストリを変更する方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="12431-152">**Important** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="12431-153">Windows レジストリを誤って変更した場合、Windows の再インストールが必要になる可能性のある重大な問題が発生する可能性があります。</span><span class="sxs-lookup"><span data-stu-id="12431-153">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="12431-154">レジストリを変更する前に、レジストリファイル (system.dat とユーザー) のバックアップコピーを作成しておく必要があります。</span><span class="sxs-lookup"><span data-stu-id="12431-154">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="12431-155">Microsoft は、レジストリを変更したときに発生する可能性のある問題を解決できないことを保証できません。</span><span class="sxs-lookup"><span data-stu-id="12431-155">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="12431-156">レジストリは、自分の責任において変更してください。</span><span class="sxs-lookup"><span data-stu-id="12431-156">Change the registry at your own risk.</span></span>

 

1.  <span data-ttu-id="12431-157">管理サーバーにログインして、 **regedit**を開きます。</span><span class="sxs-lookup"><span data-stu-id="12431-157">Login to the management server and open **regedit**.</span></span>

2.  <span data-ttu-id="12431-158">ウイルス対策**\ _LOCAL \ _MACHINE**  \\  **Software**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**に移動します。</span><span class="sxs-lookup"><span data-stu-id="12431-158">Navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Server** \\ **ManagementService**.</span></span>

3.  <span data-ttu-id="12431-159">**フェールオーバーパートナー = &lt; &gt; server2**を使用して、**管理 \ _SQL \ _CONNECTION \ _STRING**の値を変更します。</span><span class="sxs-lookup"><span data-stu-id="12431-159">Modify the **MANAGEMENT\_SQL\_CONNECTION\_STRING** value with the **failover partner = &lt;server2&gt;**.</span></span>

4.  <span data-ttu-id="12431-160">IIS コンソールを使用して、管理サービスを再起動します。</span><span class="sxs-lookup"><span data-stu-id="12431-160">Restart management service using the IIS console.</span></span>

    <span data-ttu-id="12431-161">**注** Microsoft sql Server 2012 で利用可能な**AlwaysOn**機能により、データベースのミラーリングは、Microsoft sql Server2012 の廃止されたデータベースエンジン機能の一覧にあります。</span><span class="sxs-lookup"><span data-stu-id="12431-161">**Note** Database Mirroring is on the list of Deprecated Database Engine Features for Microsoft SQL Server2012 due to the **AlwaysOn** feature available with Microsoft SQL Server 2012.</span></span>

     

<span data-ttu-id="12431-162">詳細については、次のリンクをクリックしてください。</span><span class="sxs-lookup"><span data-stu-id="12431-162">Click any of the following links for more information:</span></span>

-   <span data-ttu-id="12431-163">[方法: ミラーリング用のミラーデータベースの準備 (transact-sql)](https://go.microsoft.com/fwlink/?LinkId=394235) ( https://go.microsoft.com/fwlink/?LinkId=394235) .</span><span class="sxs-lookup"><span data-stu-id="12431-163">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=394235) (https://go.microsoft.com/fwlink/?LinkId=394235).</span></span>

-   <span data-ttu-id="12431-164">[方法: データベースミラーリングセッションを構成する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) ( https://go.microsoft.com/fwlink/?LinkId=394236) .</span><span class="sxs-lookup"><span data-stu-id="12431-164">[How to: Configure a Database Mirroring Session (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) (https://go.microsoft.com/fwlink/?LinkId=394236).</span></span>

-   <span data-ttu-id="12431-165">[Windows 認証を使ってデータベースミラーリングセッションを確立する (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) ( https://go.microsoft.com/fwlink/?LinkId=394237) .</span><span class="sxs-lookup"><span data-stu-id="12431-165">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) (https://go.microsoft.com/fwlink/?LinkId=394237).</span></span>

-   <span data-ttu-id="12431-166">[SQL Server 2012 () で廃止されたデータベースエンジンの機能](https://go.microsoft.com/fwlink/?LinkId=394238) https://go.microsoft.com/fwlink/?LinkId=394238)</span><span class="sxs-lookup"><span data-stu-id="12431-166">[Deprecated Database Engine Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=394238) (https://go.microsoft.com/fwlink/?LinkId=394238).</span></span>

## <a href="" id="bkmk-sqlalwayson"></a><span data-ttu-id="12431-167">Microsoft SQL Server のサポートは常に構成される</span><span class="sxs-lookup"><span data-stu-id="12431-167">Support for Microsoft SQL Server Always On configuration</span></span>


<span data-ttu-id="12431-168">App-v 5.0 management server データベースは、 **[常に**構成する (Microsoft SQL server) を実行しているコンピューターへの展開をサポートします。</span><span class="sxs-lookup"><span data-stu-id="12431-168">The App-V 5.0 management server database supports deployments to computers running Microsoft SQL Server with the **Always On** configuration.</span></span>

## <span data-ttu-id="12431-169">関連トピック</span><span class="sxs-lookup"><span data-stu-id="12431-169">Related topics</span></span>


[<span data-ttu-id="12431-170">App-V の展開計画</span><span class="sxs-lookup"><span data-stu-id="12431-170">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

 

 





