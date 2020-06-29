---
title: サーバーのセキュリティの計画
description: サーバーのセキュリティの計画
author: dansimp
ms.assetid: c7cd8227-b359-41e7-a8ae-d0d5718a76a2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bea1bd8287a15385200bbfb425ed8e00fbcdb02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815904"
---
# <span data-ttu-id="3ffbc-103">サーバーのセキュリティの計画</span><span class="sxs-lookup"><span data-stu-id="3ffbc-103">Planning for Server Security</span></span>


<span data-ttu-id="3ffbc-104">環境のセキュリティを強化するには、環境内の潜在的な脅威のリスクを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-104">To enhance the security of an environment, you must look at the exposure to any potential threats in the environment.</span></span> <span data-ttu-id="3ffbc-105">App-v インフラストラクチャのセキュリティを提供するには、特定の App-v セキュリティ機能と、基になるインフラストラクチャのセキュリティプラクティスと機能を使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-105">Providing security for an App-V infrastructure requires you to use the specific App-V security features as well as the security practices and features for the underlying infrastructure.</span></span> <span data-ttu-id="3ffbc-106">インターネットインフォメーションサービス (IIS)、Active Directory ドメインサービス、SQL Server などのサービスの基になるインフラストラクチャをセキュリティで保護すると、アプリの全体的なセキュリティが向上します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-106">Securing the underlying infrastructure for services such as Internet Information Services (IIS), Active Directory Domain Services, and SQL Server will improve the overall security for your App-V system.</span></span>

<span data-ttu-id="3ffbc-107">サーバーインストールの既定の設定では、最高レベルのセキュリティが提供されます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-107">The default settings for the server installation provide the highest levels of security.</span></span> <span data-ttu-id="3ffbc-108">ただし、一部のコンポーネントは、インストールの一部として構成されていない基礎インフラストラクチャに依存しています。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-108">However, some of the components rely on underlying infrastructure that is not configured as part of the installation.</span></span> <span data-ttu-id="3ffbc-109">インストール後に次の手順を実行すると、App-v インフラストラクチャのセキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-109">Following up with post-installation steps will enhance the security of the App-V infrastructure.</span></span>

<span data-ttu-id="3ffbc-110">Content ディレクトリには、クライアントにストリーミングされるすべてのパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-110">The content directory contains all of the packages that are to be streamed to clients.</span></span> <span data-ttu-id="3ffbc-111">これらのリソースは、考えられるさまざまなセキュリティの脅威を排除するため、可能な限りセキュリティで保護されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-111">These resources need to be as secure as possible to eliminate many possible security threats.</span></span> <span data-ttu-id="3ffbc-112">次の一覧では、追加のガイダンスをいくつか紹介します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-112">The following list offers some additional guidance:</span></span>

-   <span data-ttu-id="3ffbc-113">UNC ベースのパブリッシングまたはストリーミング: このアイテムに対する権限は、環境で最も制限されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-113">UNC-based publishing and/or streaming—The permissions for this item should be the most restrictive in the environment.</span></span> <span data-ttu-id="3ffbc-114">NTFS アクセス許可を使用して、コンテンツディレクトリ (ユーザー = 読み取り、管理者 = 読み取りおよび書き込み) に最も制限の厳しいアクセス制御リスト (Acl) を実装します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-114">Use NTFS permissions to implement the most restrictive access control lists (ACLs) for the content directory (Users=Read, Administrators=Read and Write).</span></span>

-   <span data-ttu-id="3ffbc-115">公開/ストリーミング用に使用される IIS — Windows 統合認証のみをサポートするように IIS を構成します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-115">IIS used for publishing and/or streaming—Configure IIS to support only Windows Integrated authentication.</span></span> <span data-ttu-id="3ffbc-116">IIS サーバーへの匿名アクセスを削除し、NTFS アクセス許可を使用してディレクトリへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-116">Remove anonymous access to the IIS server, and restrict access to the directory with NTFS permissions.</span></span>

-   <span data-ttu-id="3ffbc-117">RTSP/RTSPS をストリーミングするアプリケーションパッケージ: 認証を要求し、アクセス許可を適用し、必要なグループのみにプロバイダーポリシーへのアクセスを許可するように、アプリ-V プロバイダーポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-117">RTSP/RTSPS to stream application packages—Configure the App-V Provider Policy to require authentication, enforce access permissions, and enable only required groups to have access to the provider policy.</span></span> <span data-ttu-id="3ffbc-118">データベースの適切なアクセス許可を使用してアプリケーションを構成します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-118">Configure applications with the appropriate permissions in the database.</span></span>

<span data-ttu-id="3ffbc-119">管理者権限を持つユーザーの数を最小限に抑えて、データストア内のデータに対する脅威を軽減し、悪意のあるアプリケーションをインフラストラクチャに公開しないようにします。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-119">Keep the number of users with administrative privileges to a minimum to reduce possible threats to the data in the data store and to avoid publishing malicious applications into the infrastructure.</span></span>

## <span data-ttu-id="3ffbc-120">Application Virtualization のセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3ffbc-120">Application Virtualization Security</span></span>


<span data-ttu-id="3ffbc-121">App-v では、インフラストラクチャのさまざまな構成要素間でいくつかの通信方法を使用します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-121">App-V uses several methods of communication between the various components of the infrastructure.</span></span> <span data-ttu-id="3ffbc-122">App-v インフラストラクチャを計画する場合は、サーバー間の通信をセキュリティで保護することで、既存のネットワークに既に存在する可能性があるセキュリティリスクを軽減することができます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-122">When you plan your App-V infrastructure, securing the communications between servers can reduce the security risks that might already be present on the existing network.</span></span>

### <span data-ttu-id="3ffbc-123">データストア</span><span class="sxs-lookup"><span data-stu-id="3ffbc-123">Data Store</span></span>

<span data-ttu-id="3ffbc-124">Application Virtualization Management Server と Application Virtualization 管理サービスは、TCP ポート1433経由の SQL 接続を使用して、データストアと通信します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-124">The Application Virtualization Management Server and Application Virtualization Management Service communicate with the data store by using an SQL connection over TCP port 1433.</span></span> <span data-ttu-id="3ffbc-125">管理サーバーは、データストアを使ってアプリケーションデータと構成データを取得し、データベースに使用状況情報を書き込みます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-125">The Management Server uses the data store to retrieve application and configuration data, and it writes usage information to the database.</span></span> <span data-ttu-id="3ffbc-126">管理サービスは、App-v インフラストラクチャを構成している管理者の代わりに、データストアと通信します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-126">The Management Service communicates with the data store on behalf of an administrator who is configuring the App-V infrastructure.</span></span> <span data-ttu-id="3ffbc-127">データストアには重要な情報が含まれているため、このデータに対する脅威を最小限に抑えることが重要です。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-127">Because the data store contains critical information, it is important to minimize threats to this data.</span></span>

<span data-ttu-id="3ffbc-128">App-v Management Server、管理サービス、データストア間の通信は、インターネットプロトコルセキュリティ (IPsec) を使ってセキュリティで保護することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-128">It is recommended that communications between App-V Management Server, Management Service and the data store be secured with Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="3ffbc-129">具体的には、データストア (SQL) と管理サーバー間、およびデータストアと管理サービス間の通信チャネルをセキュリティで保護するためのポリシーを作成します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-129">Specifically, create policies that secure the communication channel between the data store (SQL) and the Management Server and the data store and the Management Service.</span></span> <span data-ttu-id="3ffbc-130">また、IPsec を使用してサーバーとドメインの分離を展開し、すべての App-v インフラストラクチャコンポーネントがセキュリティで保護されたチャネルのみで通信できることを確認することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-130">You can also deploy server and domain isolation with IPsec, ensuring all App-V infrastructure components communicate only with secure channels.</span></span> <span data-ttu-id="3ffbc-131">IPsec の実装については、次のドキュメントを参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-131">For information about implementing IPsec, refer to the following documentation:</span></span>

-   <span data-ttu-id="3ffbc-132">Windows Server2003 の場合は、() を参照してください <https://go.microsoft.com/fwlink/?LinkId=133226> https://go.microsoft.com/fwlink/?LinkId=133226) 。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-132">For Windows Server2003, see <https://go.microsoft.com/fwlink/?LinkId=133226> (https://go.microsoft.com/fwlink/?LinkId=133226).</span></span>

-   <span data-ttu-id="3ffbc-133">Windows Server2008 の場合は、() を参照してください <https://go.microsoft.com/fwlink/?LinkId=133227> https://go.microsoft.com/fwlink/?LinkId=133227) 。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-133">For Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=133227> (https://go.microsoft.com/fwlink/?LinkId=133227).</span></span>

### <span data-ttu-id="3ffbc-134">コンテンツディレクトリ</span><span class="sxs-lookup"><span data-stu-id="3ffbc-134">Content Directory</span></span>

<span data-ttu-id="3ffbc-135">App-v Management Server をインストールすると、コンテンツディレクトリの場所が構成されます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-135">The App-V Management Server installation configures a location for the content directory.</span></span> <span data-ttu-id="3ffbc-136">このディレクトリは、仮想化されたアプリケーションパッケージの保存場所です。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-136">This directory is the storage location for virtualized application packages.</span></span> <span data-ttu-id="3ffbc-137">この場所は、サーバーに対してローカルにすることも、リモートネットワーク共有に配置することもできます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-137">This location can be local to the server, or it can be placed on a remote network share.</span></span> <span data-ttu-id="3ffbc-138">したがって、コンテンツディレクトリのリモートの場所との通信をセキュリティで保護するために IPsec を実装します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-138">Therefore, implement IPsec to help secure the communication with a remote location for the content directory.</span></span>

<span data-ttu-id="3ffbc-139">また、IIS サーバー上の仮想ディレクトリを使って、クライアントへのパッケージのストリーミングを行うこともできます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-139">You can also use a virtual directory on an IIS server to stream packages to the clients.</span></span> <span data-ttu-id="3ffbc-140">コンテンツ用に作成された仮想ディレクトリがリモートソースにある場合は、IPsec を使って、IIS サーバーとリモート記憶域の場所の間の通信をセキュリティで保護します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-140">If the virtual directory that is created for content is located on a remote source, use IPsec to help secure the communication between the IIS server and the remote storage location.</span></span>

<span data-ttu-id="3ffbc-141">Content ディレクトリには、クライアントにストリーミングされるすべてのパッケージが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-141">The content directory contains all of the packages that are streamed to clients.</span></span> <span data-ttu-id="3ffbc-142">これらのリソースは、考えられるさまざまなセキュリティの脅威を排除するため、可能な限りセキュリティで保護されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-142">These resources need to be as secure as possible to eliminate many possible security threats.</span></span>

### <span data-ttu-id="3ffbc-143">セキュリティプロトコル</span><span class="sxs-lookup"><span data-stu-id="3ffbc-143">Security Protocols</span></span>

<span data-ttu-id="3ffbc-144">セキュリティで保護された通信を強化するには、RTSPS または HTTPS を使用できます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-144">You can use RTSPS or HTTPS for enhanced secure communications.</span></span> <span data-ttu-id="3ffbc-145">RTSPS は、App-v サーバーによって使用されるプロトコルであり、HTTPS は IIS サーバーによって使用されるプロトコルです。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-145">RTSPS is the protocol used by App-V servers, and HTTPS is the protocol used by IIS servers.</span></span> <span data-ttu-id="3ffbc-146">これらのプロトコルは、サーバーからアプリケーションの仮想化デスクトップクライアントにアプリケーションを公開するときに使われます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-146">These protocols are used when publishing applications from the server to the Application Virtualization Desktop Client.</span></span> <span data-ttu-id="3ffbc-147">目的のプロトコルを決定したら、そのプロトコルを使用する発行サーバーを追加します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-147">After you determine the desired protocol, add a publishing server that uses that protocol.</span></span>

### <a href="" id="configuring-app-v-servers-for-rtsps-"></a><span data-ttu-id="3ffbc-148">RTSPS の App-v サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="3ffbc-148">Configuring App-V Servers for RTSPS</span></span>

<span data-ttu-id="3ffbc-149">強化されたセキュリティ (TLS など) を使用するようにアプリをインストールまたは構成するには、x.509 V3 証明書を App-v Server にプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-149">Installing or configuring an App-V Management Server or Streaming Server to use Enhanced Security (for example, TLS) requires that an X.509 V3 certificate be provisioned to the App-V server.</span></span> <span data-ttu-id="3ffbc-150">サーバーのセキュリティをインストールまたは構成する準備を行う際には、特定の要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-150">When you prepare to install or configure security for a server, you must fulfill some specific requirements.</span></span> <span data-ttu-id="3ffbc-151">セキュリティで保護されたアプリで証明書を展開して構成するための技術的要件には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-151">Technical requirements for deploying and configuring certificates for a more secure App-V Management Server or Streaming Server include the following:</span></span>

-   <span data-ttu-id="3ffbc-152">証明書が有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-152">Certificate must be valid.</span></span> <span data-ttu-id="3ffbc-153">それ以外の場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-153">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="3ffbc-154">証明書には、適切な拡張キー使用法 (EKU)-サーバー認証 (OID 1.3.6.1.5.5.7.3.1) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-154">Certificate must contain the correct Enhanced Key Usage (EKU) - Server Authentication (OID 1.3.6.1.5.5.7.3.1).</span></span> <span data-ttu-id="3ffbc-155">それ以外の場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-155">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="3ffbc-156">証明書の完全修飾ドメイン名 (FQDN) は、それがインストールされているサーバーと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-156">Certificate fully qualified domain name (FQDN) must match the server on which it is installed.</span></span> <span data-ttu-id="3ffbc-157">たとえば、クライアントが通話を発信していても、[ `RTSPS://Myserver.mycompany.com/content/MyApp.sft` **発行先**] フィールドが含まれている場合、 `Myserver1.mycompany.com` クライアントはサーバーに接続せず、 `Myserver.mycompany.com` `Myserver1.mycompany.com` 同じ IP アドレスに解決された場合でも、セッションは終了します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-157">For example, if the client is calling `RTSPS://Myserver.mycompany.com/content/MyApp.sft`, but the certificate **Issued To** field contains `Myserver1.mycompany.com`, the client will not connect to the server and the session is terminated, even if `Myserver.mycompany.com` and `Myserver1.mycompany.com` resolve to the same IP address.</span></span>

    <span data-ttu-id="3ffbc-158">**注** ネットワーク負荷分散クラスターで App-v を使用している場合、RTSPS をサポートするために、証明書は*サブジェクト代替名*(san) で構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-158">**Note** If you use App-V in a network load balanced cluster, the certificate must be configured with *Subject Alternate Names* (SANs) to support RTSPS.</span></span> <span data-ttu-id="3ffbc-159">証明機関 (CA) を構成し、San で証明書を作成する方法については、() を参照してください <https://go.microsoft.com/fwlink/?LinkId=133228> https://go.microsoft.com/fwlink/?LinkId=133228) 。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-159">For information about configuring the certification authority (CA) and creating certificates with SANs, see <https://go.microsoft.com/fwlink/?LinkId=133228> (https://go.microsoft.com/fwlink/?LinkId=133228).</span></span>

     

-   <span data-ttu-id="3ffbc-160">証明書を App-v server に発行する CA は、サーバーに接続しているクライアントによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-160">The CA issuing the certificate to the App-V server must be trusted by the client connecting to the server.</span></span> <span data-ttu-id="3ffbc-161">それ以外の場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-161">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="3ffbc-162">サーバー App-v サービスによるアクセスを有効にするには、*証明書の秘密キー*のアクセス許可を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-162">You must change the permissions for the *Certificate Private Key* to enable access by the Server App-V Service.</span></span> <span data-ttu-id="3ffbc-163">既定では、App-v Management Server サービスと Streaming Server サービスは Network Service アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-163">By default, the App-V Management Server and Streaming Server services run under the Network Service account.</span></span> <span data-ttu-id="3ffbc-164">サーバー上で PKCS \ #10 が生成されると、秘密キーが作成されます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-164">When a PKCS\#10 is generated on the server, a private key is created.</span></span> <span data-ttu-id="3ffbc-165">ローカルシステムグループと管理者グループのみがこのキーにアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-165">Only the Local System and Administrators groups have access to this key.</span></span> <span data-ttu-id="3ffbc-166">これらの既定の Acl は、App-v サーバーがセキュリティで保護された接続を受け入れないようにします。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-166">These default ACLs prevent the App-V server from accepting secure connections.</span></span>

    <span data-ttu-id="3ffbc-167">**注** 公開キー基盤 (PKI) の構成の詳細については、() を参照してください <https://go.microsoft.com/fwlink/?LinkId=133229> https://go.microsoft.com/fwlink/?LinkId=133229) 。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-167">**Note** For information about configuring a public key infrastructure (PKI), see <https://go.microsoft.com/fwlink/?LinkId=133229> (https://go.microsoft.com/fwlink/?LinkId=133229).</span></span>

     

### <span data-ttu-id="3ffbc-168">HTTPS で IIS サーバーを構成する</span><span class="sxs-lookup"><span data-stu-id="3ffbc-168">Configuring IIS Servers with HTTPS</span></span>

<span data-ttu-id="3ffbc-169">App-v では、特定のインフラストラクチャ構成で IIS サーバーを使用する場合があります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-169">App-V might use IIS servers in certain infrastructure configurations.</span></span> <span data-ttu-id="3ffbc-170">IIS サーバーの構成の詳細については、() を参照してください <https://go.microsoft.com/fwlink/?LinkId=133230> https://go.microsoft.com/fwlink/?LinkId=133230) 。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-170">For more information about configuring IIS servers, see <https://go.microsoft.com/fwlink/?LinkId=133230> (https://go.microsoft.com/fwlink/?LinkId=133230).</span></span>

<span data-ttu-id="3ffbc-171">**注** IIS を使って ICO ファイルと OSD ファイルを公開する場合は、OSD = TXT の MIME タイプを構成します。そうしないと、IIS は、ICO ファイルと OSD ファイルをクライアントに提供することを拒否します。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-171">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="3ffbc-172">アプリケーションレベルのセキュリティ</span><span class="sxs-lookup"><span data-stu-id="3ffbc-172">Application-Level Security</span></span>

<span data-ttu-id="3ffbc-173">特定のアプリケーションをユーザーのデスクトップにストリーミングするようにサーバーを構成することができます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-173">You can configure the servers to stream specific applications to a user’s desktop.</span></span> <span data-ttu-id="3ffbc-174">ただし、アクセス許可は、実際にはアプリケーションレベルではなく、パッケージレベルで許可されています。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-174">However, access permission actually is granted at the package level, not at the application level.</span></span> <span data-ttu-id="3ffbc-175">特定のアプリケーションはユーザーのデスクトップに公開されないことがありますが、ユーザーにアプリケーションを追加するアクセス許可が与えられているか、クライアントコンピューターの管理者である場合、ユーザーはクライアント上のショートカットを作成して使用して、パッケージ内のすべてのアプリケーションを実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-175">Although a specific application might not be published to the user’s desktop, if the user has permission to add applications or is an administrator on the client computer, the user can create and use a shortcut on the client to run all the applications in a package.</span></span>

## <span data-ttu-id="3ffbc-176">分散環境への App-V 管理の構成</span><span class="sxs-lookup"><span data-stu-id="3ffbc-176">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="3ffbc-177">特定の組織のインフラストラクチャを設計する場合は、app-v management Server をインストールするコンピューター以外のコンピューターに、App-v 管理 Web サービスをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-177">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="3ffbc-178">これらの App-v コンポーネントを分離する一般的な理由には、次のようなものがあります。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-178">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="3ffbc-179">パフォーマンス</span><span class="sxs-lookup"><span data-stu-id="3ffbc-179">Performance</span></span>

-   <span data-ttu-id="3ffbc-180">信頼性</span><span class="sxs-lookup"><span data-stu-id="3ffbc-180">Reliability</span></span>

-   <span data-ttu-id="3ffbc-181">対象</span><span class="sxs-lookup"><span data-stu-id="3ffbc-181">Availability</span></span>

-   <span data-ttu-id="3ffbc-182">スケーラビリティ</span><span class="sxs-lookup"><span data-stu-id="3ffbc-182">Scalability</span></span>

<span data-ttu-id="3ffbc-183">インフラストラクチャが正常に動作するためには、App-v 管理コンソール、管理サーバー、および管理 Web サービスを分離するには追加の構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-183">For the infrastructure to operate correctly, separating the App-V Management Console, Management Server and Management Web Service requires additional configuration.</span></span> <span data-ttu-id="3ffbc-184">サーバーの構成方法の詳細については、「[委任に対して信頼されるようにサーバーを構成する方法](how-to-configure-the-server-to-be-trusted-for-delegation.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="3ffbc-184">For detailed information about how to configure the server, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md).</span></span>

## <span data-ttu-id="3ffbc-185">関連トピック</span><span class="sxs-lookup"><span data-stu-id="3ffbc-185">Related topics</span></span>


[<span data-ttu-id="3ffbc-186">セキュリティと保護の計画</span><span class="sxs-lookup"><span data-stu-id="3ffbc-186">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





