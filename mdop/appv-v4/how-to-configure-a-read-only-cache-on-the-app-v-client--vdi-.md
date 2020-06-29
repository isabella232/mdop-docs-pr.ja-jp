---
title: App-V Client の読み取り専用キャッシュを構成する方法 (VDI)
description: App-V Client の読み取り専用キャッシュを構成する方法 (VDI)
author: dansimp
ms.assetid: 7a41e017-9e23-4a6a-a659-04d23f008b83
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 114f9dfbf55a3f62b6bc8bec6b37a659ffbfaf56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817944"
---
# <span data-ttu-id="0b763-103">App-V Client の読み取り専用キャッシュを構成する方法 (VDI)</span><span class="sxs-lookup"><span data-stu-id="0b763-103">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>


<span data-ttu-id="0b763-104">Microsoft Application Virtualization (App-v) 4.6 では、クライアントは共有読み取り専用キャッシュの使用をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="0b763-104">In Microsoft Application Virtualization (App-V) 4.6 the Client supports using a shared read-only cache.</span></span> <span data-ttu-id="0b763-105">共有読み取り専用キャッシュを使用すると、クライアントは仮想デスクトップインフラストラクチャ (VDI) システムでディスク領域を効率的に使うことができます。このシステムでは、ユーザーがデータセンターサーバー環境でホストされている仮想マシン (VM) でアプリケーションを実行し、記憶域ネットワーク (SAN) でネットワークストレージを共有します。</span><span class="sxs-lookup"><span data-stu-id="0b763-105">The shared read-only cache enables the Client to use disk space efficiently in a Virtual Desktop Infrastructure (VDI) system, where users run applications on Virtual Machines (VM) that are hosted in a data center server environment and share network storage on a Storage Area Network (SAN).</span></span> <span data-ttu-id="0b763-106">次の手順では、"プールされた VM" または "静的 VM" と呼ばれるプライマリ VDI アーキテクチャのいずれかで、App-v クライアントを実装するために必要なプロセスの概要について説明します。</span><span class="sxs-lookup"><span data-stu-id="0b763-106">The following procedures provide an overview of the process that is required to implement the App-V Client in either of the primary VDI architectures, known as “Pooled VM” or “Static VM”.</span></span> <span data-ttu-id="0b763-107">App-v システムとそのコンポーネントの計画、展開、操作、および VDI サーバーの運用と管理に精通していることを前提としています。</span><span class="sxs-lookup"><span data-stu-id="0b763-107">It is assumed that you are familiar with the planning, deployment, and operation of the App-V system and its components, and also the operation and management of the VDI server.</span></span> <span data-ttu-id="0b763-108">App-v の詳細については、 [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939)</span><span class="sxs-lookup"><span data-stu-id="0b763-108">For more information about App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939)</span></span>

<span data-ttu-id="0b763-109">**注** 以下の手順で説明する詳細は、例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="0b763-109">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="0b763-110">プロセス全体を完了するには、別の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="0b763-110">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="0b763-111">VDI シナリオでの App-v クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="0b763-111">Deploying the App-V Client in a VDI Scenario</span></span>


<span data-ttu-id="0b763-112">VDI シナリオでは、すべてのユーザーに必要なすべてのアプリケーションが設定されている共有の読み取り専用キャッシュを使用して、App-v クライアントを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="0b763-112">You can deploy the App-V Client in a VDI scenario by using a shared read-only cache that has been populated with all the applications required for all users.</span></span> <span data-ttu-id="0b763-113">次に、すべての App-v クライアントで同じキャッシュファイルを使用するように、VDI マスター VM イメージを構成します。</span><span class="sxs-lookup"><span data-stu-id="0b763-113">You then configure the VDI Master VM Image so that all the App-V Clients use the same cache file.</span></span> <span data-ttu-id="0b763-114">ユーザーには、App-v の公開プロセスを使用して、特定のアプリケーションへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-114">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="0b763-115">キャッシュは既にすべてのアプリケーションに読み込まれているため、ユーザーがアプリケーションを起動しても、ストリーミングは発生しません。</span><span class="sxs-lookup"><span data-stu-id="0b763-115">Since the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="0b763-116">ただし、キャッシュを事前に作成するために使用されるパッケージは、リアルタイムストリーミングプロトコル (RTSP) ストリーミングをサポートしていて、アプリ V クライアントへのアクセス許可を付与する app-v サーバーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-116">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="0b763-117">App-v Management Server を使ってアプリケーションを公開する場合は、アプリを使ってこのストリーミング機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="0b763-117">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="0b763-118">展開プロセスは、次の4つの主要なタスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-118">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="0b763-119">マスター共有キャッシュファイルの作成と設定</span><span class="sxs-lookup"><span data-stu-id="0b763-119">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="0b763-120">共有キャッシュファイルを VDI サーバーストレージにコピーする</span><span class="sxs-lookup"><span data-stu-id="0b763-120">Copying the shared cache file to the VDI server storage</span></span>

-   <span data-ttu-id="0b763-121">VDI マスターイメージでの App-v クライアントソフトウェアの構成</span><span class="sxs-lookup"><span data-stu-id="0b763-121">Configuring the App-V client software on the VDI Master Image</span></span>

-   <span data-ttu-id="0b763-122">最初の展開後に共有キャッシュファイルの更新プログラムの展開サイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="0b763-122">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="0b763-123">これらのタスクには慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-123">These tasks require careful planning.</span></span> <span data-ttu-id="0b763-124">組織的で再現可能なプロセスを準備して文書化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="0b763-124">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="0b763-125">これは、マスター共有キャッシュファイルの最初の準備と展開を行うときに特に重要です。また、アプリケーション更新プログラムの進行中の管理については、マスター共有キャッシュの更新が必要になります。</span><span class="sxs-lookup"><span data-stu-id="0b763-125">This is especially important for the initial preparation and deployment of the master shared cache file, and for the on-going management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="0b763-126">次の手順を使用して、これらの主要なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="0b763-126">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="0b763-127">**注** 複数の異なる方法を使用してアプリケーションを公開することはできますが、次の手順は、発行用の App-v Management Server の使用に基づいています。</span><span class="sxs-lookup"><span data-stu-id="0b763-127">**Note** Although you can publish the applications by using several different methods, the following procedures are based on the use of an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="0b763-128">プールされた VM VDI または静的 VM VDI シナリオで最初の展開用に読み取り専用キャッシュを構成するには</span><span class="sxs-lookup"><span data-stu-id="0b763-128">To configure the read-only cache for initial deployment in a Pooled VM VDI or Static VM VDI scenario</span></span>**

1. <span data-ttu-id="0b763-129">VDI サーバー上の VM で、ユーザー認証と発行のサポートを提供するために、アプリをセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="0b763-129">Set up and configure an App-V Management Server in a VM on the VDI server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="0b763-130">この Management Server のコンテンツフォルダーに、すべてのユーザーに必要なすべてのアプリケーションパッケージを設定します。</span><span class="sxs-lookup"><span data-stu-id="0b763-130">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="0b763-131">App-v クライアントがインストールされているステージングコンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="0b763-131">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="0b763-132">すべてのアプリケーションに対するアクセス権を持つアカウントでステージングコンピューターにログオンします。これにより、すべてのアプリケーションがコンピューターに公開され、アプリケーションが完全に読み込まれるようにキャッシュにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="0b763-132">Log on to the staging computer with an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="0b763-133">重要</span><span class="sxs-lookup"><span data-stu-id="0b763-133">Important</span></span>**  
   <span data-ttu-id="0b763-134">ステージングコンピューターでは、App-v クライアントが実行される Vm で使用されているものと同じオペレーティングシステムの種類とシステムアーキテクチャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-134">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="0b763-135">セーフモードでステージングコンピューターを再起動して、ドライバーが開始されていないことを確認します。これにより、キャッシュファイルがロックされます。</span><span class="sxs-lookup"><span data-stu-id="0b763-135">Restart the staging computer in Safe Mode to ensure the drivers are not started, which would lock the cache file.</span></span>

   **<span data-ttu-id="0b763-136">注</span><span class="sxs-lookup"><span data-stu-id="0b763-136">Note</span></span>**  
   <span data-ttu-id="0b763-137">または、Application Virtualization サービスを停止して無効にしてから、コンピューターを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-137">Alternatively, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="0b763-138">ファイルのコピーが完了したら、もう一度サービスを有効にして開始してください。</span><span class="sxs-lookup"><span data-stu-id="0b763-138">After the file has been copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="0b763-139">Sftfs キャッシュファイルを VDI サーバーの SAN にコピーします。このファイルは、共有フォルダー内など、すべての Vm でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-139">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="0b763-140">グループの [全員] のアクセス許可を読み取り専用に、キャッシュファイルの更新を管理する管理者にはフルコントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="0b763-140">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="0b763-141">キャッシュファイルの場所は、レジストリ AppFS\\FileName. から取得できます。</span><span class="sxs-lookup"><span data-stu-id="0b763-141">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="0b763-142">重要</span><span class="sxs-lookup"><span data-stu-id="0b763-142">Important</span></span>**  
   <span data-ttu-id="0b763-143">FSD ファイルは、ローカルに接続された記憶域のパフォーマンス (たとえば、SAN) に相当する応答性と信頼性を備えた場所に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-143">You must put the FSD file in a location that has the responsiveness and reliability equivalent to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="0b763-144">VDI マスター VM イメージに app-v デスクトップクライアントをインストールし、次のレジストリキー値をクライアントの AppFS キーに追加して、読み取り専用キャッシュを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="0b763-144">Install the App-V Desktop Client on the VDI Master VM Image, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="0b763-145">AppFS キーは、HKEY \ _LOCAL \ _MACHINE ¥¥¥ \ [Wow6432Node\\\] の各デバイス \\ 365 にあります (¥)。</span><span class="sxs-lookup"><span data-stu-id="0b763-145">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="0b763-146">キー</span><span class="sxs-lookup"><span data-stu-id="0b763-146">Key</span></span></th>
   <th align="left"><span data-ttu-id="0b763-147">型</span><span class="sxs-lookup"><span data-stu-id="0b763-147">Type</span></span></th>
   <th align="left"><span data-ttu-id="0b763-148">値</span><span class="sxs-lookup"><span data-stu-id="0b763-148">Value</span></span></th>
   <th align="left"><span data-ttu-id="0b763-149">目的</span><span class="sxs-lookup"><span data-stu-id="0b763-149">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="0b763-150">FileName</span><span class="sxs-lookup"><span data-stu-id="0b763-150">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-151">String</span><span class="sxs-lookup"><span data-stu-id="0b763-151">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-152">FSD へのパス</span><span class="sxs-lookup"><span data-stu-id="0b763-152">path to FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-153">共有キャッシュファイルへのパスを指定します (例 \VDIServername\Sharefolder\SFTFS.FSD (必須)。</span><span class="sxs-lookup"><span data-stu-id="0b763-153">Specifies the path to the shared cache file, for example, \VDIServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="0b763-154">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="0b763-154">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-155">DWORD</span><span class="sxs-lookup"><span data-stu-id="0b763-155">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-156">件</span><span class="sxs-lookup"><span data-stu-id="0b763-156">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-157">読み取り専用モードで動作するようにクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="0b763-157">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="0b763-158">これにより、クライアントは、パッケージキャッシュへの更新をストリーム処理しないようになります。</span><span class="sxs-lookup"><span data-stu-id="0b763-158">This ensures that the client will not attempt to stream updates to the package cache.</span></span> <span data-ttu-id="0b763-159">(必須)</span><span class="sxs-lookup"><span data-stu-id="0b763-159">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="0b763-160">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="0b763-160">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-161">String</span><span class="sxs-lookup"><span data-stu-id="0b763-161">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-162">エラーログ (.etl) ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="0b763-162">path to error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="0b763-163">エラーログへのパスを指定するために使用されるエントリ。</span><span class="sxs-lookup"><span data-stu-id="0b763-163">Entry used to specify the path to the error log.</span></span> <span data-ttu-id="0b763-164">勧め.</span><span class="sxs-lookup"><span data-stu-id="0b763-164">(Recommended.</span></span> <span data-ttu-id="0b763-165">C:\Logs\Sftfs.etl などのローカルパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="0b763-165">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="0b763-166">マスター VM イメージクライアントを構成して、発行サーバーを使用し、ログオン時に公開更新を使用します。</span><span class="sxs-lookup"><span data-stu-id="0b763-166">Configure the Master VM Image client to use the publishing server and to use publishing refresh at logon.</span></span> <span data-ttu-id="0b763-167">ユーザーが VDI システムにログオンし、その VM がマスター VM イメージから構築されると、公開の更新サイクルが行われ、そのアカウントが承認されているすべてのアプリケーションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-167">As users log on to the VDI system and their VM is built from the Master VM Image, a publishing refresh cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="0b763-168">これらのアプリケーションは共有キャッシュから実行されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-168">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="0b763-169">プールされた VM シナリオでパッケージのアップグレードのためにクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="0b763-169">To configure the client for package upgrade in a Pooled VM scenario</span></span>**

1.  <span data-ttu-id="0b763-170">アプリケーションパッケージのアップグレードとテストを完了します。</span><span class="sxs-lookup"><span data-stu-id="0b763-170">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="0b763-171">App-v server でパッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0b763-171">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="0b763-172">次に、ステージングコンピューター上のクライアントに新しいバージョンのアプリケーションを公開して、キャッシュに完全に読み込まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b763-172">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="0b763-173">セーフモードでステージングコンピューターを再起動し、ドライバーが開始されないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b763-173">Restart the staging computer in Safe Mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="0b763-174">**注** または、services.msc で Application Virtualization サービスを停止して無効にしてから、コンピューターを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-174">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="0b763-175">ファイルのコピーが完了したら、もう一度サービスを有効にして開始してください。</span><span class="sxs-lookup"><span data-stu-id="0b763-175">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="0b763-176">Sftfs キャッシュファイルを VDI サーバーの SAN にコピーします。このファイルは、共有フォルダー内など、すべての Vm でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-176">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="0b763-177">たとえば、SFTFS \ _V2 のように、別のファイル名を使うことができます。FSD を作成し、新しいバージョンを区別します。</span><span class="sxs-lookup"><span data-stu-id="0b763-177">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="0b763-178">VDI マスター VM イメージで、更新された共有キャッシュファイルを使用するように App-v デスクトップクライアントを構成するには、\\\\VDIServername\\Sharefolder\\SFTFS\ _V2 などの更新されたファイルの場所を指すように、AppFS レジストリキーのファイル名の値を変更します。FSD.</span><span class="sxs-lookup"><span data-stu-id="0b763-178">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="0b763-179">ユーザーがログオフしてから再びログオンすると、更新されたマスターイメージを使用して、新しい VM が作成されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-179">When users log off and then log on again, a new VM is created for them by using the updated Master Image.</span></span> <span data-ttu-id="0b763-180">すべてのユーザー設定が保持され、新しい VM に適用されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-180">All their user settings will be retained and applied to the new VM.</span></span> <span data-ttu-id="0b763-181">その後、更新されたアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-181">Then they have access to the updated applications.</span></span>

**<span data-ttu-id="0b763-182">静的な VM シナリオでパッケージのアップグレードのためにクライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="0b763-182">To configure the client for package upgrade in a Static VM scenario</span></span>**

1.  <span data-ttu-id="0b763-183">アプリケーションパッケージのアップグレードとテストを完了します。</span><span class="sxs-lookup"><span data-stu-id="0b763-183">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="0b763-184">App-v server でパッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="0b763-184">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="0b763-185">次に、アプリケーションが完全にキャッシュに読み込まれるように、ステージングコンピューター上のクライアントに新しいバージョンのアプリケーションを発行してストリームします。</span><span class="sxs-lookup"><span data-stu-id="0b763-185">Then, publish and stream the new version of the applications to the client on the staging computer so that the applications are fully loaded into cache.</span></span>

3.  <span data-ttu-id="0b763-186">セーフモードでステージングコンピューターを再起動し、ドライバーが開始されないようにします。</span><span class="sxs-lookup"><span data-stu-id="0b763-186">Restart the staging computer in Safe Mode to ensure that the drivers are not started.</span></span>

    <span data-ttu-id="0b763-187">**注** または、services.msc で Application Virtualization サービスを停止して無効にしてから、コンピューターを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-187">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="0b763-188">ファイルのコピーが完了したら、もう一度サービスを有効にして開始してください。</span><span class="sxs-lookup"><span data-stu-id="0b763-188">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="0b763-189">Sftfs キャッシュファイルを VDI サーバーの SAN にコピーします。このファイルは、共有フォルダー内など、すべての Vm でアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-189">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="0b763-190">たとえば、SFTFS \ _V2 のように、別のファイル名を使うことができます。FSD を作成し、新しいバージョンを区別します。</span><span class="sxs-lookup"><span data-stu-id="0b763-190">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="0b763-191">VDI マスター VM イメージで、更新された共有キャッシュファイルを使用するように App-v デスクトップクライアントを構成するには、\\\\VDIServername\\Sharefolder\\SFTFS\ _V2 などの更新されたファイルの場所を指すように、AppFS レジストリキーのファイル名の値を変更します。FSD.</span><span class="sxs-lookup"><span data-stu-id="0b763-191">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="0b763-192">これにより、新しいユーザーが新しいバージョンを入手できるようになります。</span><span class="sxs-lookup"><span data-stu-id="0b763-192">This ensures that new users get the new version.</span></span>

6.  <span data-ttu-id="0b763-193">更新されたキャッシュの場所 (\\\\VDIServername\\Sharefolder\\SFTFS\ _V2 など) に設定するために、AppFS キーのファイル名の値を編集するスクリプトを作成します。FSD.</span><span class="sxs-lookup"><span data-stu-id="0b763-193">Create a script that edits the AppFS key FILENAME value to set it to the location of the updated cache, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="0b763-194">このスクリプトは、ユーザーがログオフまたはログオフするときに実行されるように構成します。たとえば、グループポリシー設定を使用して、アプリの実行時に実行されるようにします。</span><span class="sxs-lookup"><span data-stu-id="0b763-194">Configure this script to run when the user logs off or logs on so that it runs before the App-V client drivers start, for example, by using Group Policy settings.</span></span> <span data-ttu-id="0b763-195">ユーザーがログオフして再びログオンすると、既存の VM が更新され、更新されたキャッシュのコピーが使用されます。</span><span class="sxs-lookup"><span data-stu-id="0b763-195">When users log off and log on again, their existing VM is updated, and they will use the updated copy of the cache.</span></span> <span data-ttu-id="0b763-196">その後、更新されたアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-196">Then, they have access to the updated applications.</span></span>

## <span data-ttu-id="0b763-197">キャッシュのアップグレード時にシンボリックリンクを使用する方法</span><span class="sxs-lookup"><span data-stu-id="0b763-197">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="0b763-198">新規またはアップグレードされたパッケージを含む新しいキャッシュファイルが展開されるたびに、AppFS キーのファイル名の値を変更する代わりに、次のオペレーティングシステムでは、Windows Vista、Windows 7、Windows Server 2008 のシンボリックリンクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="0b763-198">Instead of modifying the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="0b763-199">シンボリックリンクの詳細については、「[シンボリックリンク](https://go.microsoft.com/fwlink/?LinkId=157626)()」を参照してください https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="0b763-199">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="0b763-200">これに対し、Windows XP では、シンボリックリンクの使用はサポートされていないため、代わりに接合ポイントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-200">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="0b763-201">接合部の詳細については、「Microsoft サポート技術情報の[記事 205524](https://go.microsoft.com/fwlink/?LinkId=182553) 」 https://go.microsoft.com/fwlink/?LinkId=182553) および「ツール[ジャンクション v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="0b763-201">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="0b763-202">キャッシュを参照するためのシンボリックリンクを構成するには</span><span class="sxs-lookup"><span data-stu-id="0b763-202">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="0b763-203">最初の展開段階で、VDI server ホストオペレーティングシステムのローカル管理者としてコマンドプロンプトウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="0b763-203">During the initial deployment stage, open a Command Prompt window as a local administrator on the VDI server host operating system.</span></span>

2.  <span data-ttu-id="0b763-204">MKLINK コマンドを使用してシンボリックリンクを作成してから、Sftfs ファイルをポイントするように構成します。</span><span class="sxs-lookup"><span data-stu-id="0b763-204">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="0b763-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="0b763-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="0b763-206">VDI マスター VM イメージで、[**管理者として実行**] オプションを使用してコマンドプロンプトウィンドウを開き、VM が VDI ホストオペレーティングシステムのシンボリックリンクにアクセスできるようにリモートリンクのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="0b763-206">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="0b763-207">既定では、リモートリンクのアクセス許可は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="0b763-207">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="0b763-208">fsutil behavior set SymlinkEvaluation R2R: 1</span><span class="sxs-lookup"><span data-stu-id="0b763-208">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="0b763-209">**注** ストレージサーバーで、適切なリンクのアクセス許可を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="0b763-209">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="0b763-210">Link の場所と Sftfs fsd ファイルのアクセス許可は、 **L2L:** 1 または**L2R:** 1 または R2L: 1 または: 1 または **:** 1 または**R2R:** 1 のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="0b763-210">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="0b763-211">VDI マスター VM イメージで App-v デスクトップクライアントを構成する場合は、シンボリックリンクを使用している FSD ファイルの UNC パスとして、AppFS key FILENAME の値を設定します。たとえば、\\\\VDIHostserver\\Symlinkname. に設定します。</span><span class="sxs-lookup"><span data-stu-id="0b763-211">When you configure the App-V Desktop Client on the VDI Master VM Image, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link; for example, set it to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="0b763-212">App-v クライアントが最初にキャッシュにアクセスすると、シンボリックリンクは、キャッシュファイルへのハンドルをクライアントに渡します。</span><span class="sxs-lookup"><span data-stu-id="0b763-212">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="0b763-213">クライアントは、クライアントが実行されている限り、そのハンドルを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="0b763-213">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="0b763-214">シンボリックリンクの値は、既存のクライアントに古い共有キャッシュが開かれている場合でも、安全に更新できます。</span><span class="sxs-lookup"><span data-stu-id="0b763-214">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="0b763-215">パッケージをアップグレードするか、新しいパッケージをキャッシュに追加する必要がある場合は、静的な VM またはプールされた VM のシナリオについて、アップグレード手順の 1 ~ 5 の手順に従います。</span><span class="sxs-lookup"><span data-stu-id="0b763-215">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 5 of the upgrade procedure for either the Static VM or Pooled VM scenario.</span></span> <span data-ttu-id="0b763-216">次に、シンボリックリンクを削除して再作成し、共有キャッシュファイルの新しいバージョンをポイントします。</span><span class="sxs-lookup"><span data-stu-id="0b763-216">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="0b763-217">Vm を再起動すると、更新されたシンボリックリンクを含むパスが使用されるため、クライアントは、更新されたキャッシュのコピーへのハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="0b763-217">When the VM is restarted, the client receives a handle to the updated copy of the cache because the VM uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="0b763-218">次に、ユーザーは新規および更新されたアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="0b763-218">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="0b763-219">関連トピック</span><span class="sxs-lookup"><span data-stu-id="0b763-219">Related topics</span></span>


[<span data-ttu-id="0b763-220">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0b763-220">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="0b763-221">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0b763-221">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="0b763-222">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="0b763-222">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





