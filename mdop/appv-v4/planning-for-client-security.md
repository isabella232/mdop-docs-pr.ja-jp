---
title: クライアントのセキュリティの計画
description: クライアントのセキュリティの計画
author: dansimp
ms.assetid: 4840a60f-4c91-489c-ad0b-6671882abf9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0038f7cbc8592d6c7fcdfa485111da88c17791d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815934"
---
# <span data-ttu-id="a18d5-103">クライアントのセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="a18d5-103">Planning for Client Security</span></span>


<span data-ttu-id="a18d5-104">App-v クライアントには、以前のバージョンの製品では提供されていないセキュリティの拡張機能がいくつか用意されています。</span><span class="sxs-lookup"><span data-stu-id="a18d5-104">The App-V Client provides several security enhancements that were not present in previous versions of the product.</span></span> <span data-ttu-id="a18d5-105">これらの変更により、インストール後およびクライアント設定の後の構成により、セキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-105">These changes provide improved security after installation and through later configuration of the client settings.</span></span> <span data-ttu-id="a18d5-106">このトピックでは、これらの拡張機能の一部について説明し、計画プロセスで考慮する必要がある重要なセキュリティ関連の構成設定をいくつか示します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-106">This topic describes some of those enhancements and identifies several important security-related configuration settings that you should consider during your planning process.</span></span> <span data-ttu-id="a18d5-107">仮想アプリケーションは依然として実行可能であることを覚えておく必要があります。そのため、これらのアセットは、不正ユーザーによって改ざんされないようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-107">It is important to remember that virtual applications are still executables, so you must ensure that these assets cannot be tampered with by unauthorized people.</span></span> <span data-ttu-id="a18d5-108">このため、このトピックの後半で説明するように、Open Software Descriptor (OSD) ファイルキャッシュは、このトピックで後述するように保護されています。 RTSPS、HTTPS、IPsec を使用してパブリッシングとストリーミングを保護することを強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="a18d5-108">For this reason, the Open Software Descriptor (OSD) file cache is protected as described later in this topic, and we strongly recommend that you use RTSPS, HTTPS, and IPsec to protect publishing and streaming.</span></span>

## <span data-ttu-id="a18d5-109">App-v クライアントセキュリティ</span><span class="sxs-lookup"><span data-stu-id="a18d5-109">App-V Client Security</span></span>


<span data-ttu-id="a18d5-110">既定では、インストール時に、ユーザーが発行の更新を実行してアプリケーションを起動するために必要な最低限のアクセス許可を持つ App-v クライアントが構成されます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-110">By default, at installation the App-V client is configured with the minimum permissions required to allow a user to perform a publishing refresh and to start applications.</span></span> <span data-ttu-id="a18d5-111">App-v クライアントで提供されるその他のセキュリティ強化機能には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-111">Other security enhancements provided in the App-V client include the following:</span></span>

-   <span data-ttu-id="a18d5-112">既定では、OSD ファイルキャッシュは管理者のみが更新できます。また、発行更新プロセスを使うこともできます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-112">By default, the OSD file cache can be updated only by administrators and by using the publishing refresh process.</span></span>

-   <span data-ttu-id="a18d5-113">ログファイル (sftlog.txt) は、クライアントへのローカル管理アクセス権を持つアカウントによってのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-113">The log file (sftlog.txt) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="a18d5-114">ログファイルに最大サイズが設定されました。</span><span class="sxs-lookup"><span data-stu-id="a18d5-114">The log file now has a maximum size.</span></span>

### <span data-ttu-id="a18d5-115">ファイルの種類の関連付け</span><span class="sxs-lookup"><span data-stu-id="a18d5-115">File Type Associations</span></span>

<span data-ttu-id="a18d5-116">既定では、クライアントのインストールによって OSD ファイルのファイルの種類の関連付け (FTAs) が登録されます。これにより、ユーザーは公開されたショートカットではなく OSD ファイルから直接アプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-116">By default, the installation of the client registers file type associations (FTAs) for OSD files, which enables users to start applications directly from OSD files instead of the published shortcuts.</span></span> <span data-ttu-id="a18d5-117">ローカル管理者の権限を持つユーザーが、悪意のあるコードを含む OSD ファイル (電子メールまたは Web サイトからダウンロードしたもの) を受信した場合、ユーザーは OSD ファイルを開き、クライアントが**アプリケーション**のアクセス許可を制限するように設定されていても、アプリケーションを起動することができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-117">If a user with local administrator rights receives an OSD file containing malicious code, either in e-mail or downloaded from a Web site, the user can open the OSD file and start the application even if the client has been set to restrict the **Add Application** permission.</span></span> <span data-ttu-id="a18d5-118">このリスクを軽減するために、「FTAs」という OSD の登録を解除することができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-118">You can unregister the FTAs for the OSD to reduce this risk.</span></span> <span data-ttu-id="a18d5-119">また、メールシステムとファイアウォールでこの拡張機能をブロックすることも検討してください。</span><span class="sxs-lookup"><span data-stu-id="a18d5-119">Also, consider blocking this extension in the e-mail system and at the firewall.</span></span> <span data-ttu-id="a18d5-120">拡張機能をブロックするように Outlook を構成する方法については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=133278> 。</span><span class="sxs-lookup"><span data-stu-id="a18d5-120">For more information about configuring Outlook to block extensions, see <https://go.microsoft.com/fwlink/?LinkId=133278>.</span></span>

**<span data-ttu-id="a18d5-121">セキュリティに関するメモ:</span><span class="sxs-lookup"><span data-stu-id="a18d5-121">Security Note:</span></span>**

<span data-ttu-id="a18d5-122">App-v バージョン4.6 以降では、クライアントの新規インストール時に、OSD ファイルのファイルの種類の関連付けは作成されません。ただし、既存の設定は、App-v クライアントのバージョン4.2 または4.5 からのアップグレード中に維持されます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-122">Starting with App-V version4.6, the file type association is no longer created for OSD files during a new installation of the client, although the existing settings will be maintained during an upgrade from version 4.2 or 4.5 of the App-V client.</span></span> <span data-ttu-id="a18d5-123">何らかの理由でファイルの種類の関連付けを作成することが重要である場合は、次のレジストリキーを作成して、次のように値を設定できます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-123">If for any reason it is essential to create the file type association, you can create the following registry keys and set their values as shown:</span></span>

    Create HKEY\_CLASSES\_ROOT\\.osd with a default value of SoftGrid.osd.File

    Under HKEY\_LOCAL\_MACHINE\\software\\classes\\Softgrid.osd.file, create a string value named AppUserModelID with a data value of Microsoft.AppV.Client.Tray

### <span data-ttu-id="a18d5-124">Authorization</span><span class="sxs-lookup"><span data-stu-id="a18d5-124">Authorization</span></span>

<span data-ttu-id="a18d5-125">インストール時には、 **Requireauthorizationifcached**パラメーターを使って、ユーザーがアプリケーションを起動しようとしたときにサーバーからの認証を要求するようにクライアントを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-125">During installation, you can use the **RequireAuthorizationIfCached** parameter to configure the client to require authorization from the server when the user tries to start an application.</span></span> <span data-ttu-id="a18d5-126">このパラメーターの設定方法について慎重に検討する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-126">You should consider carefully how to set this parameter.</span></span> <span data-ttu-id="a18d5-127">何らかの理由で App-v サーバーが利用できない場合、アプリケーションはこのパラメーターの最新の保存された状態を使って、アプリケーションへのユーザーアクセスを制御します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-127">If the App-V server is unavailable for any reason, the application will use the most recent stored state of this parameter to control user access to the application.</span></span> <span data-ttu-id="a18d5-128">ユーザーがアプリケーションを正常に起動せずに、アプリが実行されなくなった場合は、サーバーと通信して承認を受けるまでアプリケーションを起動することはできません。</span><span class="sxs-lookup"><span data-stu-id="a18d5-128">If the user has not launched the application successfully before the App-V server becomes unavailable, they will not be able to launch the application until they can communicate with the server and receive authorization.</span></span> <span data-ttu-id="a18d5-129">ただし、クライアントが認証を必要としないようにパラメーターを設定し、サーバーが利用できない場合は、以前にキャッシュされたすべてのアプリケーションを、承認されたかどうかにかかわらず開始できます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-129">However, if you set the parameter so that the client does not require authorization and if the server is unavailable, all previously cached applications can be started whether authorized or not.</span></span> <span data-ttu-id="a18d5-130">また、ユーザーにアクセス許可を使用してオフラインモードで動作するようにクライアントを変更する権限がある場合、またはユーザーがローカル管理者である場合は、App-v インフラストラクチャを利用できない場合と同様に、キャッシュされたパッケージをすべて開くことができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-130">Also, if the user has permission to change the client to Work Offline mode through permissions or if the user is a local administrator, the user would be able to open all cached packages as if the App-V infrastructure was unavailable.</span></span>

### <span data-ttu-id="a18d5-131">ウイルス対策スキャン</span><span class="sxs-lookup"><span data-stu-id="a18d5-131">Antivirus Scanning</span></span>

<span data-ttu-id="a18d5-132">App-v クライアントコンピューターで実行されているウイルス対策ソフトウェアにより、仮想環境の感染したファイルを検出して報告することができます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-132">Antivirus software running on an App-V Client computer can detect and report an infected file in the virtual environment.</span></span> <span data-ttu-id="a18d5-133">ただし、ファイルをウイルス駆除することはできません。</span><span class="sxs-lookup"><span data-stu-id="a18d5-133">However, it cannot disinfect the file.</span></span> <span data-ttu-id="a18d5-134">仮想環境でウイルスが検出された場合、ウイルス対策ソフトウェアは、実際のパッケージではなく、キャッシュ内で構成済みの検疫または修復操作を実行します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-134">If a virus is detected in the virtual environment, the antivirus software would perform the configured quarantine or repair operation in the cache, not in the actual package.</span></span> <span data-ttu-id="a18d5-135">Fsd ファイルの例外を使ってウイルス対策ソフトウェアを構成します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-135">Configure the antivirus software with an exception for the sftfs.fsd file.</span></span> <span data-ttu-id="a18d5-136">このファイルは、App-v クライアントでパッケージを保存するキャッシュファイルです。</span><span class="sxs-lookup"><span data-stu-id="a18d5-136">This file is the cache file that stores packages on the App-V Client.</span></span>

**<span data-ttu-id="a18d5-137">セキュリティに関するメモ:</span><span class="sxs-lookup"><span data-stu-id="a18d5-137">Security Note:</span></span>**

<span data-ttu-id="a18d5-138">運用環境に展開されたアプリケーションまたはパッケージでウイルスが検出された場合は、そのアプリケーションまたはパッケージをウイルスに感染していないバージョンに置き換えます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-138">If a virus is detected in an application or package deployed in the production environment, replace the application or package with a virus-free version.</span></span>

## <span data-ttu-id="a18d5-139">クライアントとサーバーの間の通信</span><span class="sxs-lookup"><span data-stu-id="a18d5-139">Communication Between Client and Server</span></span>


<span data-ttu-id="a18d5-140">公開の更新とパッケージストリーミングも、クライアントとサーバー間の通信に関連するセキュリティ上の考慮事項が重要な部分です。</span><span class="sxs-lookup"><span data-stu-id="a18d5-140">Publishing refreshes and package streaming are also areas where security considerations relating to client-server communication are important.</span></span>

### <span data-ttu-id="a18d5-141">公開の更新</span><span class="sxs-lookup"><span data-stu-id="a18d5-141">Publishing Refresh</span></span>

<span data-ttu-id="a18d5-142">クライアントがサーバーと通信して公開の更新を実行すると、ログオンしているユーザーの資格情報を使って、アプリケーションパッケージに関する情報が要求されます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-142">When the client communicates with the server to perform a publishing refresh, it uses the credentials of the logged on user to request information about the application packages.</span></span> <span data-ttu-id="a18d5-143">App-v client と App-v Management Server の間で発生した通信をセキュリティで保護して、どの公開情報も転送中に改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="a18d5-143">You should secure the communication that occurs between the App-V client and App-V Management Server to ensure that none of the publishing information can be tampered with in transit.</span></span> <span data-ttu-id="a18d5-144">これは、RTSPS/HTTPS を使用する強化されたセキュリティオプションを使用することで行われます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-144">This is done by using the Enhanced Security option, which will use RTSPS/HTTPS.</span></span> <span data-ttu-id="a18d5-145">クライアントと、ICO および OSD ファイルが保存されている場所の間の通信では、IIS サーバーに対して SMB/CIFS 共有と HTTPS に対して IPsec を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-145">Communication between the Client and the location where the ICO and OSD files are stored should use IPsec for SMB/CIFS shares and HTTPS for an IIS server.</span></span>

<span data-ttu-id="a18d5-146">**注** IIS を使って ICO ファイルと OSD ファイルを公開する場合は、OSD = TXT の MIME タイプを構成します。そうしないと、IIS は、ICO ファイルと OSD ファイルをクライアントに提供することを拒否します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-146">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="a18d5-147">パッケージストリーミング</span><span class="sxs-lookup"><span data-stu-id="a18d5-147">Package Streaming</span></span>

<span data-ttu-id="a18d5-148">ユーザーがアプリケーションを初めて起動した場合、またはクライアントで自動読み込みパラメーターが設定されている場合は、アプリケーションパッケージがサーバーからクライアントキャッシュにストリーミングされます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-148">When a user launches an application for the first time, or if auto-loading parameters have been set on the client, the application package is streamed from a server to the client cache.</span></span> <span data-ttu-id="a18d5-149">このプロセスでは、RTSP/RTSPS、HTTP/HTTPS、SMB/CIFS プロトコルがサポートされています。</span><span class="sxs-lookup"><span data-stu-id="a18d5-149">This process supports the RTSP/RTSPS, HTTP/HTTPS, and SMB/CIFS protocols.</span></span> <span data-ttu-id="a18d5-150">OSD ファイルは、クライアントで**ApplicationSourceRoot**または**overrideurl**の設定が構成されていない限り、どのプロトコルを使用するかを制御します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-150">The OSD files control which protocols are used, unless the **ApplicationSourceRoot** or **OverrideURL** setting has been configured on the clients.</span></span> <span data-ttu-id="a18d5-151">より高いレベルのセキュリティを実現するには、SMB/CIFS の RTSPS、HTTPS、または IPsec 経由で通信を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-151">You should configure communication to occur over RTSPS, HTTPS, or IPsec for SMB/CIFS to achieve higher levels of security.</span></span> <span data-ttu-id="a18d5-152">使用する通信方法の選択の詳細については、「App-v の計画と展開ガイド」を参照してください <https://go.microsoft.com/fwlink/?LinkId=122063> 。</span><span class="sxs-lookup"><span data-stu-id="a18d5-152">For more information about choosing which communication method to use, see the App-V Planning and Deployment Guide at <https://go.microsoft.com/fwlink/?LinkId=122063>.</span></span>

<span data-ttu-id="a18d5-153">**注** IIS を使用してパッケージ (SFT ファイル) を公開している場合は、SFT = Binary の MIME タイプを構成します。そうしないと、IIS は、SFT ファイルをクライアントに提供することを拒否します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-153">**Note** If you are using IIS to publish packages (SFT files), configure a MIME type for SFT=Binary; otherwise, IIS will refuse to serve the SFT files to clients.</span></span>

 

### <span data-ttu-id="a18d5-154">ローミングプロファイルとフォルダリダイレクション</span><span class="sxs-lookup"><span data-stu-id="a18d5-154">Roaming Profiles and Folder Redirection</span></span>

<span data-ttu-id="a18d5-155">App-v システムは、usrvol \ _sftfs \ _v1 .pkg ファイルのパッケージに対するユーザー固有の変更を保存します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-155">The App-V system stores user-specific changes to packages in the usrvol\_sftfs\_v1.pkg file.</span></span> <span data-ttu-id="a18d5-156">このファイルは、ユーザーのプロファイルのアプリケーションデータフォルダーにあります。</span><span class="sxs-lookup"><span data-stu-id="a18d5-156">This file is located in the Application Data folder of a user’s profile.</span></span> <span data-ttu-id="a18d5-157">プロファイルまたはリダイレクトされたアプリケーションデータフォルダーは、クライアントとサーバーの間で転送されるため、IPsec を使って通信をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-157">Because the profile or a redirected Application Data folder is transferred between the client and the server, use IPsec to secure the communication.</span></span>

## <span data-ttu-id="a18d5-158">インターネットに接続しているクライアントに関する考慮事項</span><span class="sxs-lookup"><span data-stu-id="a18d5-158">Considerations for Internet-Facing Clients</span></span>


<span data-ttu-id="a18d5-159">インターネットに接続しているクライアントの場合、クライアントがドメインに参加しているか、ドメイン以外に参加しているかを検討することが重要です。</span><span class="sxs-lookup"><span data-stu-id="a18d5-159">For Internet-facing clients, it is important to consider whether the client is domain joined or non-domain joined.</span></span>

### <span data-ttu-id="a18d5-160">ドメインに参加しているクライアント</span><span class="sxs-lookup"><span data-stu-id="a18d5-160">Domain Joined Client</span></span>

<span data-ttu-id="a18d5-161">既定では、App-v クライアントは、イントラネット上の認証と承認のために Active Directory ドメインサービスによって発行された Kerberos チケットを使用します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-161">By default, App-V Clients use Kerberos tickets that were issued by Active Directory Domain Services for authentication and authorization on the intranet.</span></span> <span data-ttu-id="a18d5-162">既定では、これらの Kerberos チケットは10時間有効です。</span><span class="sxs-lookup"><span data-stu-id="a18d5-162">These Kerberos tickets are valid for 10 hours by default.</span></span> <span data-ttu-id="a18d5-163">クライアントは、このチケットを使って、チケットが有効である限り、コンピューターがドメインコントローラーに接続してチケットを更新できない場合でも、このチケットを使用してアプリ-V server にアクセスします。</span><span class="sxs-lookup"><span data-stu-id="a18d5-163">The client will use this ticket to access the App-V server for as long as the ticket is valid, even if the computer is unable to connect to the domain controller to refresh the ticket.</span></span> <span data-ttu-id="a18d5-164">Kerberos チケットの有効期限が切れた場合、App-v クライアントは NTLM 認証に戻り、ユーザーのキャッシュされた資格情報を使用します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-164">If the Kerberos ticket expires, the App-V client will revert to NTLM authentication and use the user’s cached credentials.</span></span>

### <span data-ttu-id="a18d5-165">ドメインに参加していないクライアント</span><span class="sxs-lookup"><span data-stu-id="a18d5-165">Non-Domain Joined Client</span></span>

<span data-ttu-id="a18d5-166">ユーザーが自宅ベースであり、コンピューターが会社のドメインに参加していない場合は、アプリケーションの配信は引き続きサポートされます。</span><span class="sxs-lookup"><span data-stu-id="a18d5-166">If a user is home-based and the computer is not joined to the company domain, App-V can still support delivering applications.</span></span> <span data-ttu-id="a18d5-167">公開の更新を実行してアプリケーションを起動するようにユーザーを認証して承認するには、クライアントコンピューターでユーザーアカウントを構成し、そのユーザー名とパスワードを保存し、そのアプリケーションに対する適切なアクセス許可を付与します。</span><span class="sxs-lookup"><span data-stu-id="a18d5-167">To authenticate and authorize a user to perform a publishing refresh and to start applications, configure the user account on the client computer to store the user name and password that has access to the App-V environment and to provide appropriate permissions to the applications.</span></span>

## <span data-ttu-id="a18d5-168">関連トピック</span><span class="sxs-lookup"><span data-stu-id="a18d5-168">Related topics</span></span>


[<span data-ttu-id="a18d5-169">セキュリティと保護の計画</span><span class="sxs-lookup"><span data-stu-id="a18d5-169">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





