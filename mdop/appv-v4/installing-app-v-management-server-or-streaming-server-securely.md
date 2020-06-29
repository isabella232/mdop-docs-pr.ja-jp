---
title: APP-V Management Server または Streaming Server を安全にインストールする
description: APP-V Management Server または Streaming Server を安全にインストールする
author: dansimp
ms.assetid: d2a51a81-a80f-427c-a727-611e1eb74f02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0150f4dc7f489731c4a818fed9780ebb25dbd24f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10816327"
---
# <span data-ttu-id="ea963-103">APP-V Management Server または Streaming Server を安全にインストールする</span><span class="sxs-lookup"><span data-stu-id="ea963-103">Installing App-V Management Server or Streaming Server Securely</span></span>


<span data-ttu-id="ea963-104">このセクションのトピックでは、強化されたセキュリティバージョンの App-v Management Server または App-v ストリーミングサーバーのインストールに関する情報を提供します。</span><span class="sxs-lookup"><span data-stu-id="ea963-104">The topics in this section provide information for installing an enhanced security version of the App-V Management Server or the App-V Streaming Server.</span></span>

<span data-ttu-id="ea963-105">**注** 強化されたセキュリティ (トランスポート層セキュリティ、TLS など) を使用するためにアプリをインストールまたは構成するには、x.509 V3 証明書が App-v サーバーにプロビジョニングされている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-105">**Note** Installing or configuring an App-V Management or Streaming Server to use enhanced security (for example, Transport Layer Security, or TLS) requires that an X.509 V3 certificate has been provisioned to the App-V server.</span></span>

 

<span data-ttu-id="ea963-106">セキュリティで保護された管理サーバーまたはストリーミングサーバーをインストールまたは構成するための準備として、次の技術要件を考慮してください。</span><span class="sxs-lookup"><span data-stu-id="ea963-106">When you prepare to install or configure a secure Management or Streaming Server, consider the following technical requirements:</span></span>

-   <span data-ttu-id="ea963-107">証明書は有効である必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-107">The certificate must be valid.</span></span> <span data-ttu-id="ea963-108">証明書が有効でない場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="ea963-108">If the certificate is not valid, the client ends the connection.</span></span>

-   <span data-ttu-id="ea963-109">証明書には、適切な*拡張キー使用法*(EKU)、サーバー認証 (OID 1.3.6.1.5.5.7.3.1) が含まれている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-109">The certificate must contain the correct *Enhanced Key Usage* (EKU)—Server Authentication (OID 1.3.6.1.5.5.7.3.1).</span></span> <span data-ttu-id="ea963-110">証明書にこの EKU が含まれていない場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="ea963-110">If the certificate does not contain this EKU, the client ends the connection.</span></span>

-   <span data-ttu-id="ea963-111">証明書の完全修飾ドメイン名 (FQDN) は、それがインストールされているサーバーと一致している必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-111">The certificate fully qualified domain name (FQDN) must match the server on which it is installed.</span></span> <span data-ttu-id="ea963-112">たとえば、クライアントが通話を発信していて `RTSPS://Myserver.mycompany.com/content/MyApp.sft` 、[**発行先**] フィールドがに設定されている場合、 `Server1.mycompany.com` クライアントはサーバーに接続せず、セッションは終了します。</span><span class="sxs-lookup"><span data-stu-id="ea963-112">For example, if the client is calling `RTSPS://Myserver.mycompany.com/content/MyApp.sft` and the certificate **Issued To** field is set to `Server1.mycompany.com`, the client will not connect to the server and the session ends.</span></span> <span data-ttu-id="ea963-113">このエラーはユーザーに報告されます。</span><span class="sxs-lookup"><span data-stu-id="ea963-113">The failure is reported to the user.</span></span>

    <span data-ttu-id="ea963-114">**注** ネットワーク負荷分散クラスターで App-v を使用している場合は、RTSPS をサポートするようにサブジェクト代替名 (San) を使用する証明書を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-114">**Note** If you are using App-V in a Network Load Balancing cluster, you must configure the certificate with Subject Alternate Names (SANs) to support RTSPS.</span></span> <span data-ttu-id="ea963-115">証明機関 (CA) を構成し、San で証明書を作成する方法については、「」を参照してください <https://go.microsoft.com/fwlink/?LinkId=133228> 。</span><span class="sxs-lookup"><span data-stu-id="ea963-115">For information about configuring the certification authority (CA) and creating certificates with SANs, see <https://go.microsoft.com/fwlink/?LinkId=133228>.</span></span>

     

-   <span data-ttu-id="ea963-116">クライアントとサーバーは、ルート CA を信頼する必要があります。 CA は、サーバーに接続しているクライアントによって信頼されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-116">The client and the server need to trust the root CA—The CA issuing the certificate to the App-V server must by trusted by the client connecting to the server.</span></span> <span data-ttu-id="ea963-117">それ以外の場合、クライアントは接続を終了します。</span><span class="sxs-lookup"><span data-stu-id="ea963-117">If not, the client ends the connection.</span></span>

-   <span data-ttu-id="ea963-118">アプリ-V サービスアカウントが証明書にアクセスできるようにするには、証明書の秘密キーにアクセス許可が変更されている必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea963-118">The certificate’s private key must have permissions changed to allow the App-V Service account to access the certificate.</span></span> <span data-ttu-id="ea963-119">既定では、App-v は Network Service アカウントを使用します。既定では、ネットワークサービスアカウントには秘密キーへのアクセス許可が与えられていないため、安全な接続はできません。</span><span class="sxs-lookup"><span data-stu-id="ea963-119">By default, App-V uses the Network Service account, and by default, the Network Service account does not have permission to access the private key, which will prevent secure connections.</span></span>

## <span data-ttu-id="ea963-120">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="ea963-120">In This Section</span></span>


<a href="" id="configuring-certificates-to-support-secure-streaming"></a>[<span data-ttu-id="ea963-121">安全なストリーミングをサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="ea963-121">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)  
<span data-ttu-id="ea963-122">セキュリティで保護されたストリーミングをサポートするための証明書の取得、構成、インストールについて説明します。</span><span class="sxs-lookup"><span data-stu-id="ea963-122">Provides information about obtaining, configuring, and installing certificates to support secure streaming.</span></span>

<a href="" id="how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server"></a>[<span data-ttu-id="ea963-123">Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法</span><span class="sxs-lookup"><span data-stu-id="ea963-123">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)  
<span data-ttu-id="ea963-124">Windows Server2003 および Windows Server2008 でキーを変更するための手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea963-124">Provides procedures you can use to modify keys in Windows Server2003 and Windows Server2008.</span></span>

<a href="" id="configuring-certificates-to-support-app-v-management-server-or-streaming-server"></a>[<span data-ttu-id="ea963-125">APP-V Management Server または Streaming Server をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="ea963-125">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>](configuring-certificates-to-support-app-v-management-server-or-streaming-server.md)  
<span data-ttu-id="ea963-126">ネットワーク負荷分散環境用の証明書の構成に関する情報を含む、App-v 管理またはストリーミングサーバー用の証明書の構成について説明します。</span><span class="sxs-lookup"><span data-stu-id="ea963-126">Provides information about configuring certificates for the App-V Management or Streaming Servers, including information about configuring certificates for Network Load Balancing environments.</span></span>

 

 





