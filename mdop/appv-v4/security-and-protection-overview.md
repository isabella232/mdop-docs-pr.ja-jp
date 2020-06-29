---
title: セキュリティと保護の概要
description: セキュリティと保護の概要
author: dansimp
ms.assetid: a43e1c53-7936-4d48-a110-0be26c8e9d97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b08b7dcb3defa8a01a4fd8a3e7234b5ac2956c4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10815657"
---
# <span data-ttu-id="bad25-103">セキュリティと保護の概要</span><span class="sxs-lookup"><span data-stu-id="bad25-103">Security and Protection Overview</span></span>


<span data-ttu-id="bad25-104">Microsoft Application Virtualization 4.5 は、より安全な展開戦略を計画して実装するために役立つ、次の強化されたセキュリティ機能を提供します。</span><span class="sxs-lookup"><span data-stu-id="bad25-104">Microsoft Application Virtualization4.5 provides the following enhanced security features to help you plan and implement a more secure deployment strategy:</span></span>

-   <span data-ttu-id="bad25-105">Application Virtualization は、x.509 V3 証明書を使ったトランスポート層セキュリティ (TLS) をサポートするようになりました。</span><span class="sxs-lookup"><span data-stu-id="bad25-105">Application Virtualization now supports Transport Layer Security (TLS) using X.509 V3 certificates.</span></span> <span data-ttu-id="bad25-106">計画されたアプリケーション仮想化管理またはストリーミングサーバーにサーバー証明書がプロビジョニングされている場合、そのインストールは、322の RTSPS プロトコルを使用して、既定でセキュリティで保護されます。</span><span class="sxs-lookup"><span data-stu-id="bad25-106">Provided that a server certificate has been provisioned to the planned Application Virtualization Management or Streaming Server, the installation will default to secure, using the RTSPS protocol over port 322.</span></span> <span data-ttu-id="bad25-107">RTSPS を使用すると、アプリケーションの仮想化サーバーとアプリケーションの仮想化クライアント間の通信が署名され、暗号化されるようになります。</span><span class="sxs-lookup"><span data-stu-id="bad25-107">Using RTSPS ensures that communication between the Application Virtualization Servers and the Application Virtualization Clients is signed and encrypted.</span></span> <span data-ttu-id="bad25-108">Application Virtualization Server のインストール中にサーバーに証明書が割り当てられていない場合、通信はポート554を経由して RTSP に設定されます。</span><span class="sxs-lookup"><span data-stu-id="bad25-108">If no certificate is assigned to the server during the Application Virtualization Server installation, the communication will be set to RTSP over port 554.</span></span>

    **<span data-ttu-id="bad25-109">セキュリティに関するメモ:</span><span class="sxs-lookup"><span data-stu-id="bad25-109">Security Note:</span></span>**

    <span data-ttu-id="bad25-110">セキュリティで保護されたサーバーのセットアップを実現するには、すべてのパッケージを RTSPS を使用するように構成している場合でも、RTSP ポートが無効になっていることを確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-110">To help provide a secure setup of the server, you must make sure that RTSP ports are disabled even if you have all packages configured to use RTSPS.</span></span>

    <span data-ttu-id="bad25-111">サーバーをインストールした後でサーバーにセキュリティ証明書を追加した場合、サーバーで証明書が検出されないことがあります。</span><span class="sxs-lookup"><span data-stu-id="bad25-111">If you add security certificates to the server after installing the server, the server might not detect the certificates.</span></span> <span data-ttu-id="bad25-112">セキュリティ証明書を検出できるようにするには、証明書を追加した後でサーバーを再起動します。</span><span class="sxs-lookup"><span data-stu-id="bad25-112">To help ensure security certificate detection, restart the server after adding the certificates.</span></span>

-   <span data-ttu-id="bad25-113">クライアントは、サーバーと同じプロトコルとポートを使用するように構成されている必要があります。また、サーバーと通信できません。</span><span class="sxs-lookup"><span data-stu-id="bad25-113">The client must be configured to use the same protocol and port as the server, or it will not be able to communicate with the server.</span></span> <span data-ttu-id="bad25-114">クライアントは、信頼されたルートストアの一部のプライマリプロバイダーと共に、証明書の発行者を信頼する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-114">The client must also trust the issuer of the certificate and ships with several of the primary providers in its Trusted Root Store.</span></span> <span data-ttu-id="bad25-115">自己署名入りの証明書を使用できますが、クライアントを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-115">You can use self-signed certificates, but you will need to update the clients.</span></span>

-   <span data-ttu-id="bad25-116">ストリーミング用に HTTPS プロトコルを使用するように IIS サーバーを構成する場合は、IIS サーバーで Secure Sockets Layer (SSL) を設定し、サーバー用の証明書をプロビジョニングする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-116">When configuring IIS servers to use the HTTPS protocol for streaming, you will need to set up Secure Sockets Layer (SSL) on the IIS server and provision the certificate for the server.</span></span> <span data-ttu-id="bad25-117">また、クライアントは、サーバー証明書を発行したルート証明機関を信頼するように構成されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-117">The clients will also need to be configured to trust the root certification authority that issued the server certificate.</span></span>

-   <span data-ttu-id="bad25-118">Kerberos 認証は、既定の認証メカニズムとして Microsoft Application Virtualization に追加されました。</span><span class="sxs-lookup"><span data-stu-id="bad25-118">Kerberos authentication has been added to Microsoft Application Virtualization as the default authentication mechanism.</span></span> <span data-ttu-id="bad25-119">以前のバージョンは、NTLM V2 の認証に依存しています。</span><span class="sxs-lookup"><span data-stu-id="bad25-119">Earlier versions relied upon NTLM V2 for authentication.</span></span> <span data-ttu-id="bad25-120">Kerberos 認証を使用すると、クライアントとアプリケーションの仮想化サーバー間の通信のセキュリティが強化されます。</span><span class="sxs-lookup"><span data-stu-id="bad25-120">Using Kerberos Authentication strengthens the security of the communication between the client and the Application Virtualization server.</span></span> <span data-ttu-id="bad25-121">クライアントから開始された接続は、Application Virtualization サーバーは、キー配布センター (KDC) を使ってセッションチケットを確認します。</span><span class="sxs-lookup"><span data-stu-id="bad25-121">When a connection has been initiated from the client, the Application Virtualization Server verifies the session ticket with the Key Distribution Center (KDC).</span></span>

-   <span data-ttu-id="bad25-122">サーバー証明書の使用と RTSPS または HTTPS プロトコルの使用がサポートされているため、企業ネットワークの外部からクライアントをサポートできるようになりました。</span><span class="sxs-lookup"><span data-stu-id="bad25-122">Because of the support for using server certificates and using the RTSPS or HTTPS protocols, you can now support clients outside of the corporate network.</span></span> <span data-ttu-id="bad25-123">これにより、モバイルユーザーは、アプリケーションの仮想化プロビジョニングアプリケーションを起動する前に、企業ネットワーク (VPN、RAS など) へのセキュリティで保護された接続を設定する必要がなくなります。</span><span class="sxs-lookup"><span data-stu-id="bad25-123">This can help eliminate the need for mobile users to set up a secure connection to the corporate network (VPN, RAS, and so on) prior to launching Application Virtualization provisioned applications.</span></span>

<span data-ttu-id="bad25-124">考慮する必要があるその他の重要なセキュリティの考慮事項は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="bad25-124">Other important security considerations to consider include the following:</span></span>

-   <span data-ttu-id="bad25-125">常にサーバーを完全に最新の状態に保ち、保護します。</span><span class="sxs-lookup"><span data-stu-id="bad25-125">Always keep servers fully updated and protected.</span></span>

-   <span data-ttu-id="bad25-126">証明書を追加して、Application Virtualization Management Server へのセキュリティで保護された通信を実現するには、次の条件を満たしている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-126">To add a certificate to enable more secure communications to the Application Virtualization Management Server, the following criteria must be met:</span></span>

    -   <span data-ttu-id="bad25-127">証明書を追加しようとしているユーザーは、証明書ストアが配置されているサーバーの管理者である必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-127">The user who will be adding the certificate must be an administrator on the server where the certificate store is located.</span></span>

    -   <span data-ttu-id="bad25-128">サーバーサービスを開始する必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-128">The server service must be started.</span></span>

    -   <span data-ttu-id="bad25-129">管理サーバー上のポート139は、Web サービスサーバーの SIP に開かれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-129">Port 139 on the Management Server must be open to the Web Service server’sIP.</span></span>

-   <span data-ttu-id="bad25-130">アクセス制御リスト (Acl) を使って、アプリケーションパッケージとすべてのパッケージファイルが保護され、改ざんされないようにします。</span><span class="sxs-lookup"><span data-stu-id="bad25-130">Use access control lists (ACLs) to ensure that the application packages and all package files are protected and cannot be tampered.</span></span> <span data-ttu-id="bad25-131">Acl は、パッケージを保存する場所またはフォルダーへのアクセスを制限し、特定のアカウントにのみアクセスできるようにします。</span><span class="sxs-lookup"><span data-stu-id="bad25-131">ACLs restrict access to the location or folder where you store the packages, allowing access only to certain accounts.</span></span>

-   <span data-ttu-id="bad25-132">アプリケーションの仮想化管理サーバーとデータベースの間のチャネルがセキュリティで保護されていることを確認します (たとえば、IPsec を使用してください)。</span><span class="sxs-lookup"><span data-stu-id="bad25-132">Make sure that the channel between the Application Virtualization Management Server and the database is secured—for example, by using IPsec.</span></span>

-   <span data-ttu-id="bad25-133">パッケージが SAN または NAS に保存されている場合は、中央のストレージデバイスとアプリケーションの仮想化サーバー間の接続が保護されていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="bad25-133">If packages are stored on a SAN or NAS, ensure the connection between the central storage device and the Application Virtualization Servers is protected.</span></span>

-   <span data-ttu-id="bad25-134">HTTPS や IPsec などのプロトコルを使用して、クライアントへのすべての通信チャネルを保護する必要があります。これには、発行サーバー、Application Virtualization Server、OSD および ICO ファイルへの接続などが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bad25-134">All communication channels to the client should be protected—including connections to the publishing server, the Application Virtualization Server, and the path to the OSD and ICO files—by using a protocol such as HTTPS or IPsec.</span></span> 

-   <span data-ttu-id="bad25-135">クライアントのアクセス許可を構成して、ユーザーによるパッケージの改ざんを防止できるようにする必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-135">Client permissions should be configured to help ensure that packages cannot be tampered with by users.</span></span> <span data-ttu-id="bad25-136">複数のユーザーと共有されるリモートデスクトップセッションホスト (RDSession Host) サーバーなどのシステム上のパッケージを追加または更新する権限をユーザーに付与しないことが特に重要です。</span><span class="sxs-lookup"><span data-stu-id="bad25-136">It is especially important that you do not grant users permission to add or update packages on systems, such as Remote Desktop Session Host (RDSession Host) servers, that are shared with multiple users.</span></span>

-   <span data-ttu-id="bad25-137">サーバー管理コンソールが正常に動作するためには、ドメインまたはフォレスト環境全体で Kerberos 認証が許可されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="bad25-137">Kerberos authentication must be permitted across domain or forest environments for the Server Management Console to work correctly.</span></span>

-   <span data-ttu-id="bad25-138">このソフトウェアのリリースでは、Kerberos ベースの RTSP サーバーと、同じコンピューター上の Microsoft NTLM のみベースの IIS サーバーをホストすることはサポートされていません。</span><span class="sxs-lookup"><span data-stu-id="bad25-138">This release of the software does not support hosting a Kerberos-based RTSP server and a Microsoft NTLM-only-based IIS server on the same computer.</span></span> <span data-ttu-id="bad25-139">同じコンピューター上で RTSP サーバーと IIS サーバーをホストするには、IIS サーバーから SPN を削除し、NTLM 認証を使用します。</span><span class="sxs-lookup"><span data-stu-id="bad25-139">To host an RTSP server and an IIS server on the same computer, remove the SPN from the IIS server and use NTLM authentication.</span></span>

## <span data-ttu-id="bad25-140">関連トピック</span><span class="sxs-lookup"><span data-stu-id="bad25-140">Related topics</span></span>


[<span data-ttu-id="bad25-141">Application Virtualization システムの展開計画</span><span class="sxs-lookup"><span data-stu-id="bad25-141">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





