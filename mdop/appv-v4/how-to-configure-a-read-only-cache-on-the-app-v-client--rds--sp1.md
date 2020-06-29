---
title: App-V Client の読み取り専用キャッシュを構成する方法 (RDS)
description: App-V Client の読み取り専用キャッシュを構成する方法 (RDS)
author: dansimp
ms.assetid: b6607fe2-6f92-4567-99f1-d8e3c8a591e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a44844ae9ffc3497151be7713f6a43fda0ccd8fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10817947"
---
# <span data-ttu-id="810c5-103">App-V Client の読み取り専用キャッシュを構成する方法 (RDS)</span><span class="sxs-lookup"><span data-stu-id="810c5-103">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>


<span data-ttu-id="810c5-104">**重要** この手順を使用するには、App-v 4.6 の SP1 を実行している必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-104">**Important** You must be running App-V 4.6, SP1 to use this procedure.</span></span>

 

<span data-ttu-id="810c5-105">すべてのユーザーに必要なすべてのアプリケーションが設定された共有キャッシュを使用して、App-v クライアントを展開することができます。</span><span class="sxs-lookup"><span data-stu-id="810c5-105">You can deploy the App-V client by using a shared cache that is populated with all the applications required for all users.</span></span> <span data-ttu-id="810c5-106">次に、同じキャッシュファイルを使用するように、App-v リモートデスクトップサービス (RDS) クライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-106">Then you configure the App-V Remote Desktop Services (RDS) Clients to use the same cache file.</span></span> <span data-ttu-id="810c5-107">ユーザーには、App-v の公開プロセスを使用して、特定のアプリケーションへのアクセス権が付与されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-107">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="810c5-108">キャッシュは既にすべてのアプリケーションに読み込まれているため、ユーザーがアプリケーションを起動しても、ストリーミングは発生しません。</span><span class="sxs-lookup"><span data-stu-id="810c5-108">Because the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="810c5-109">ただし、キャッシュを事前に作成するために使用されるパッケージは、リアルタイムストリーミングプロトコル (RTSP) ストリーミングをサポートしていて、アプリ V クライアントへのアクセス許可を付与する app-v サーバーに配置する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-109">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="810c5-110">App-v Management Server を使ってアプリケーションを公開する場合は、アプリを使ってこのストリーミング機能を提供できます。</span><span class="sxs-lookup"><span data-stu-id="810c5-110">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="810c5-111">**注** 以下の手順で説明する詳細は、例としてのみ使用されています。</span><span class="sxs-lookup"><span data-stu-id="810c5-111">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="810c5-112">プロセス全体を完了するには、別の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="810c5-112">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="810c5-113">RDS シナリオでの App-v クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="810c5-113">Deploying the App-V Client in an RDS Scenario</span></span>


<span data-ttu-id="810c5-114">展開プロセスは、次の4つの主要なタスクで構成されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-114">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="810c5-115">マスター共有キャッシュファイルの作成と設定</span><span class="sxs-lookup"><span data-stu-id="810c5-115">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="810c5-116">共有キャッシュファイルをサーバーストレージにコピーする</span><span class="sxs-lookup"><span data-stu-id="810c5-116">Copying the shared cache file to the server storage</span></span>

-   <span data-ttu-id="810c5-117">App-v クライアントソフトウェアの構成</span><span class="sxs-lookup"><span data-stu-id="810c5-117">Configuring the App-V client software</span></span>

-   <span data-ttu-id="810c5-118">最初の展開後に共有キャッシュファイルの更新プログラムの展開サイクルを管理する</span><span class="sxs-lookup"><span data-stu-id="810c5-118">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="810c5-119">これらのタスクには慎重に計画する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-119">These tasks require careful planning.</span></span> <span data-ttu-id="810c5-120">組織的で再現可能なプロセスを準備して文書化することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="810c5-120">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="810c5-121">これは、マスター共有キャッシュファイルの準備と展開、およびアプリケーション更新プログラムの継続的な管理のために、マスター共有キャッシュの更新が必要な場合に特に重要です。</span><span class="sxs-lookup"><span data-stu-id="810c5-121">This is especially important for the preparation and deployment of the master shared cache file, and for the ongoing management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="810c5-122">次の手順を使用して、これらの主要なタスクを実行します。</span><span class="sxs-lookup"><span data-stu-id="810c5-122">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="810c5-123">**注** 複数の方法を使用してアプリケーションを公開することはできますが、次の手順は、公開のための App-v Management サーバーの使用に基づくものです。</span><span class="sxs-lookup"><span data-stu-id="810c5-123">**Note** Although you can publish the applications by using several different methods, the following procedures are based on your using an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="810c5-124">初期展開用に読み取り専用キャッシュを構成するには</span><span class="sxs-lookup"><span data-stu-id="810c5-124">To configure the read-only cache for initial deployment</span></span>**

1. <span data-ttu-id="810c5-125">ユーザー認証と発行のサポートを提供するように、アプリの管理サーバーをセットアップして構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-125">Set up and configure an App-V Management Server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="810c5-126">この Management Server のコンテンツフォルダーに、すべてのユーザーに必要なすべてのアプリケーションパッケージを設定します。</span><span class="sxs-lookup"><span data-stu-id="810c5-126">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="810c5-127">App-v クライアントがインストールされているステージングコンピューターをセットアップします。</span><span class="sxs-lookup"><span data-stu-id="810c5-127">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="810c5-128">すべてのアプリケーションに対するアクセス権を持つアカウントを使ってステージングコンピューターにログオンします。これにより、すべてのアプリケーションがコンピューターに公開され、アプリケーションが完全に読み込まれるようにキャッシュにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="810c5-128">Log on to the staging computer by using an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="810c5-129">重要</span><span class="sxs-lookup"><span data-stu-id="810c5-129">Important</span></span>**  
   <span data-ttu-id="810c5-130">ステージングコンピューターでは、App-v クライアントが実行される Vm で使用されているものと同じオペレーティングシステムの種類とシステムアーキテクチャを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-130">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="810c5-131">セーフモードでステージングコンピューターを再起動して、ドライバーが開始されないようにします。これにより、キャッシュファイルがロックされるためです。</span><span class="sxs-lookup"><span data-stu-id="810c5-131">Restart the staging computer in safe mode to make sure that the drivers are not started, because this would lock the cache file.</span></span>

   **<span data-ttu-id="810c5-132">注</span><span class="sxs-lookup"><span data-stu-id="810c5-132">Note</span></span>**  
   <span data-ttu-id="810c5-133">または、Application Virtualization サービスを停止して無効にしてから、コンピューターを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="810c5-133">Or, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="810c5-134">ファイルがコピーされたら、もう一度サービスを有効にして開始してください。</span><span class="sxs-lookup"><span data-stu-id="810c5-134">After the file is copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="810c5-135">Sftfs fsd キャッシュファイルを SAN にコピーします。このファイルは、すべての RDS サーバーが共有フォルダー内などでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="810c5-135">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="810c5-136">グループの [全員] のアクセス許可を読み取り専用に、キャッシュファイルの更新を管理する管理者にはフルコントロールを設定します。</span><span class="sxs-lookup"><span data-stu-id="810c5-136">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="810c5-137">キャッシュファイルの場所は、レジストリ AppFS\\FileName. から取得できます。</span><span class="sxs-lookup"><span data-stu-id="810c5-137">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="810c5-138">重要</span><span class="sxs-lookup"><span data-stu-id="810c5-138">Important</span></span>**  
   <span data-ttu-id="810c5-139">FSD ファイルは、ローカルに接続された記憶域のパフォーマンス (たとえば、SAN) に等しい、応答性と信頼性のある場所に置く必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-139">You must put the FSD file in a location that has the responsiveness and reliability equal to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="810c5-140">各 RDS サーバーに App-v RDS クライアントをインストールし、次のレジストリキーの値をクライアントの AppFS キーに追加して、読み取り専用キャッシュを使用するように構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-140">Install the App-V RDS Client on each RDS server, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="810c5-141">AppFS キーは、HKEY \ _LOCAL \ _MACHINE \\ pc \\ 4、32ビットコンピューターの場合は、HKEY \ _LOCAL \ _MACHINE \\ pc \\ wow6432om¥¥ 64-(ビットコンピューターの場合は、$ 5) \ \ "のように使用します。</span><span class="sxs-lookup"><span data-stu-id="810c5-141">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 32-bit computers and at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 64-bit computers.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="810c5-142">キー</span><span class="sxs-lookup"><span data-stu-id="810c5-142">Key</span></span></th>
   <th align="left"><span data-ttu-id="810c5-143">型</span><span class="sxs-lookup"><span data-stu-id="810c5-143">Type</span></span></th>
   <th align="left"><span data-ttu-id="810c5-144">値</span><span class="sxs-lookup"><span data-stu-id="810c5-144">Value</span></span></th>
   <th align="left"><span data-ttu-id="810c5-145">目的</span><span class="sxs-lookup"><span data-stu-id="810c5-145">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="810c5-146">FileName</span><span class="sxs-lookup"><span data-stu-id="810c5-146">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-147">String</span><span class="sxs-lookup"><span data-stu-id="810c5-147">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-148">FSD のパス</span><span class="sxs-lookup"><span data-stu-id="810c5-148">path of FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-149">共有キャッシュファイルのパスを指定します (例 \RDSServername\Sharefolder\SFTFS.FSD (必須)。</span><span class="sxs-lookup"><span data-stu-id="810c5-149">Specifies the path of the shared cache file, for example, \RDSServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="810c5-150">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="810c5-150">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-151">DWORD</span><span class="sxs-lookup"><span data-stu-id="810c5-151">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-152">件</span><span class="sxs-lookup"><span data-stu-id="810c5-152">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-153">読み取り専用モードで動作するようにクライアントを構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-153">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="810c5-154">これにより、クライアントがパッケージキャッシュへの更新をストリームしないようになります。</span><span class="sxs-lookup"><span data-stu-id="810c5-154">This ensures that the client will not try to stream updates to the package cache.</span></span> <span data-ttu-id="810c5-155">(必須)</span><span class="sxs-lookup"><span data-stu-id="810c5-155">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="810c5-156">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="810c5-156">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-157">String</span><span class="sxs-lookup"><span data-stu-id="810c5-157">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-158">エラーログ (.etl) ファイルのパス</span><span class="sxs-lookup"><span data-stu-id="810c5-158">path of error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="810c5-159">エラーログのパスを指定するために使用されるエントリ。</span><span class="sxs-lookup"><span data-stu-id="810c5-159">Entry used to specify the path of the error log.</span></span> <span data-ttu-id="810c5-160">勧め.</span><span class="sxs-lookup"><span data-stu-id="810c5-160">(Recommended.</span></span> <span data-ttu-id="810c5-161">C:\Logs\Sftfs.etl などのローカルパスを使用します。</span><span class="sxs-lookup"><span data-stu-id="810c5-161">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="810c5-162">発行サーバーを使用し、ユーザーがログオンするときに発行更新を使うように、ファーム内の各 RDS サーバーを構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-162">Configure each RDS server in the farm to use the publishing server and to use publishing update when users log on.</span></span> <span data-ttu-id="810c5-163">ユーザーが RDS サーバーにログオンすると、公開更新サイクルが行われ、そのアカウントが承認されているすべてのアプリケーションが公開されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-163">As users log on to the RDS servers, a publishing update cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="810c5-164">これらのアプリケーションは共有キャッシュから実行されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-164">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="810c5-165">パッケージのアップグレード用に RDS クライアントを構成するには</span><span class="sxs-lookup"><span data-stu-id="810c5-165">To configure the RDS client for package upgrade</span></span>**

1.  <span data-ttu-id="810c5-166">アプリケーションパッケージのアップグレードとテストを完了します。</span><span class="sxs-lookup"><span data-stu-id="810c5-166">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="810c5-167">App-v server でパッケージをアップグレードします。</span><span class="sxs-lookup"><span data-stu-id="810c5-167">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="810c5-168">次に、ステージングコンピューター上のクライアントに新しいバージョンのアプリケーションを公開して、キャッシュに完全に読み込まれるようにします。</span><span class="sxs-lookup"><span data-stu-id="810c5-168">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="810c5-169">セーフモードでステージングコンピューターを再起動し、ドライバーが開始されないようにします。</span><span class="sxs-lookup"><span data-stu-id="810c5-169">Restart the staging computer in safe mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="810c5-170">**注** または、まず、services.msc で Application Virtualization サービスを停止してから無効にしてから、コンピューターを再起動することもできます。</span><span class="sxs-lookup"><span data-stu-id="810c5-170">**Note** Or, you can first stop and then disable the Application Virtualization service in the Services.msc, and restart the computer.</span></span> <span data-ttu-id="810c5-171">ファイルのコピーが完了したら、もう一度サービスを有効にして開始してください。</span><span class="sxs-lookup"><span data-stu-id="810c5-171">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="810c5-172">Sftfs fsd キャッシュファイルを SAN にコピーします。このファイルは、すべての RDS サーバーが共有フォルダー内などでアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="810c5-172">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="810c5-173">別のファイル名を使用できます。たとえば、SFTFS \ _V2 などです。FSD を作成し、新しいバージョンを区別します。</span><span class="sxs-lookup"><span data-stu-id="810c5-173">You can use a different file name, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="810c5-174">ファーム内の各 RDS サーバーで App-v RDS クライアントを構成して、更新された共有キャッシュファイルを使用するには、\\\\RDSServername\\Sharefolder\\SFTFS\ _V2 など、更新されたファイルの場所を指すように AppFS レジストリキーのファイル名の値を変更します。FSD.</span><span class="sxs-lookup"><span data-stu-id="810c5-174">To configure the App-V RDS Client on each RDS server in the farm to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\RDSServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="810c5-175">これにより、アプリの Vclient ドライバーを再起動したときに、各 RDS server が更新されたキャッシュのコピーを受信することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-175">This guarantees that each RDS server receives the updated copy of the cache when the App-Vclient drivers restart.</span></span>

    <span data-ttu-id="810c5-176">**重要** 更新された共有キャッシュファイルを使用するには、RDS サーバーを再起動する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-176">**Important** You must restart the RDS servers in order to use the updated shared cache file.</span></span>

     

## <span data-ttu-id="810c5-177">キャッシュのアップグレード時にシンボリックリンクを使用する方法</span><span class="sxs-lookup"><span data-stu-id="810c5-177">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="810c5-178">新規またはアップグレードされたパッケージを含む新しいキャッシュファイルが展開されるたびに、AppFS キーのファイル名の値を変更する代わりに、次のオペレーティングシステムでは、Windows Vista、Windows 7、Windows Server 2008 のシンボリックリンクを使用できます。</span><span class="sxs-lookup"><span data-stu-id="810c5-178">Instead of changing the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="810c5-179">シンボリックリンクの詳細については、「[シンボリックリンク](https://go.microsoft.com/fwlink/?LinkId=157626)()」を参照してください https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="810c5-179">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="810c5-180">これに対し、Windows XP では、シンボリックリンクの使用はサポートされていないため、代わりに接合ポイントを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-180">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="810c5-181">接合部の詳細については、「Microsoft サポート技術情報の[記事 205524](https://go.microsoft.com/fwlink/?LinkId=182553) 」 https://go.microsoft.com/fwlink/?LinkId=182553) および「ツール[ジャンクション v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (」を参照してください https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="810c5-181">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="810c5-182">キャッシュを参照するためのシンボリックリンクを構成するには</span><span class="sxs-lookup"><span data-stu-id="810c5-182">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="810c5-183">最初の展開段階で、RDS server ホストオペレーティングシステムのローカル管理者としてコマンドプロンプトウィンドウを開きます。</span><span class="sxs-lookup"><span data-stu-id="810c5-183">During the initial deployment stage, open a Command Prompt window as a local administrator on the RDS server host operating system.</span></span>

2.  <span data-ttu-id="810c5-184">MKLINK コマンドを使用してシンボリックリンクを作成してから、Sftfs ファイルをポイントするように構成します。</span><span class="sxs-lookup"><span data-stu-id="810c5-184">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="810c5-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="810c5-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="810c5-186">VDI マスター VM イメージで、[**管理者として実行**] オプションを使用してコマンドプロンプトウィンドウを開き、VM が VDI ホストオペレーティングシステムのシンボリックリンクにアクセスできるようにリモートリンクのアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="810c5-186">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="810c5-187">既定では、リモートリンクのアクセス許可は無効になっています。</span><span class="sxs-lookup"><span data-stu-id="810c5-187">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="810c5-188">fsutil behavior set SymlinkEvaluation R2R: 1</span><span class="sxs-lookup"><span data-stu-id="810c5-188">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="810c5-189">**注** ストレージサーバーで、適切なリンクのアクセス許可を有効にする必要があります。</span><span class="sxs-lookup"><span data-stu-id="810c5-189">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="810c5-190">Link の場所と Sftfs fsd ファイルのアクセス許可は、 **L2L:** 1 または**L2R:** 1 または R2L: 1 または: 1 または **:** 1 または**R2R:** 1 のいずれかになります。</span><span class="sxs-lookup"><span data-stu-id="810c5-190">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="810c5-191">App-v RDS クライアントを構成する場合は、シンボリックリンクを使用している FSD ファイルの UNC パスに、AppFS key FILENAME の値を設定します。</span><span class="sxs-lookup"><span data-stu-id="810c5-191">When you configure the App-V RDS Client, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link.</span></span> <span data-ttu-id="810c5-192">たとえば、ファイル名を \\\\VDIHostserver\\Symlinkname. に設定します。</span><span class="sxs-lookup"><span data-stu-id="810c5-192">For example, set the file name to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="810c5-193">App-v クライアントが最初にキャッシュにアクセスすると、シンボリックリンクは、キャッシュファイルへのハンドルをクライアントに渡します。</span><span class="sxs-lookup"><span data-stu-id="810c5-193">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="810c5-194">クライアントは、クライアントが実行されている限り、そのハンドルを引き続き使用します。</span><span class="sxs-lookup"><span data-stu-id="810c5-194">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="810c5-195">シンボリックリンクの値は、既存のクライアントに古い共有キャッシュが開かれている場合でも、安全に更新できます。</span><span class="sxs-lookup"><span data-stu-id="810c5-195">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="810c5-196">パッケージをアップグレードするか、新しいパッケージをキャッシュに追加する必要がある場合は、アップグレード手順の手順 1 ~ 4 に従います。</span><span class="sxs-lookup"><span data-stu-id="810c5-196">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 4 of the upgrade procedure.</span></span> <span data-ttu-id="810c5-197">次に、シンボリックリンクを削除して再作成し、共有キャッシュファイルの新しいバージョンをポイントします。</span><span class="sxs-lookup"><span data-stu-id="810c5-197">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="810c5-198">これにより、各 RDS server は、App-v クライアントドライバーが再起動したときに、更新されたキャッシュのコピーを受信することが保証されます。</span><span class="sxs-lookup"><span data-stu-id="810c5-198">This guarantees that each RDS server receives the updated copy of the cache when the App-V client drivers restart.</span></span> <span data-ttu-id="810c5-199">RDS サーバーが再起動されると、更新されたシンボリックリンクを含むパスがクライアントによって使用されるため、App-v クライアントは、更新されたキャッシュのコピーへのハンドルを受け取ります。</span><span class="sxs-lookup"><span data-stu-id="810c5-199">When the RDS server is restarted, the App-V client receives a handle to the updated copy of the cache because the client uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="810c5-200">次に、ユーザーは新規および更新されたアプリケーションにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="810c5-200">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="810c5-201">関連トピック</span><span class="sxs-lookup"><span data-stu-id="810c5-201">Related topics</span></span>


[<span data-ttu-id="810c5-202">Application Virtualization Management Server をインストールする方法</span><span class="sxs-lookup"><span data-stu-id="810c5-202">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="810c5-203">Application Virtualization Client を手動でインストールする方法</span><span class="sxs-lookup"><span data-stu-id="810c5-203">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="810c5-204">コマンド ラインを使用してクライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="810c5-204">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





