---
title: 安全なストリーミングをサポートするための証明書の構成
description: 安全なストリーミングをサポートするための証明書の構成
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821894"
---
# <span data-ttu-id="14b95-103">安全なストリーミングをサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="14b95-103">Configuring Certificates to Support Secure Streaming</span></span>


<span data-ttu-id="14b95-104">既定では、App-v サービスは Network Service アカウントで実行されます。</span><span class="sxs-lookup"><span data-stu-id="14b95-104">By default, the App-V service runs under the Network Service account.</span></span> <span data-ttu-id="14b95-105">ただし、Active Directory ドメインサービスでサービスアカウントを作成し、ネットワークサービスアカウントを Active Directory ドメインアカウントに置き換えることができます。</span><span class="sxs-lookup"><span data-stu-id="14b95-105">However, you can create a service account in Active Directory Domain Services and replace the Network Service account with the Active Directory Domain account.</span></span>

<span data-ttu-id="14b95-106">サービスが実行されるセキュリティコンテキストは、強化されたセキュリティで保護された通信を構成するために重要です。</span><span class="sxs-lookup"><span data-stu-id="14b95-106">The security context under which the service runs is important for configuring enhanced secure communications.</span></span> <span data-ttu-id="14b95-107">このセキュリティコンテキストは、証明書の秘密キーの読み取りアクセス許可を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="14b95-107">This security context must have read permissions for the certificate private key.</span></span> <span data-ttu-id="14b95-108">アプリ-V server で PKCS \ #10*証明書署名要求*(CSR) が生成されると、Windows*暗号化サービスプロバイダー*が呼び出され、秘密キーが生成されます。</span><span class="sxs-lookup"><span data-stu-id="14b95-108">When a PKCS\#10 *Certificate Signing Request* (CSR) is generated for the App-V server, the Windows *Cryptographic Service Provider* is called and a private key is generated.</span></span> <span data-ttu-id="14b95-109">秘密鍵は、システムアカウントと管理者アカウントに付与された権限によって保護されます。</span><span class="sxs-lookup"><span data-stu-id="14b95-109">The private key is secured with permissions given to the System and Administrator accounts only.</span></span>

<span data-ttu-id="14b95-110">TLS でセキュリティ保護された通信を成功させるために必要な秘密キーにアクセスするには、秘密キーのアクセス制御リスト (Acl) を変更する必要があります。</span><span class="sxs-lookup"><span data-stu-id="14b95-110">You must modify the access control lists (ACLs) on the private key to let the App-V Management or Streaming Server access the private key required for successful TLS secured communication.</span></span>

## <span data-ttu-id="14b95-111">証明書の入手とインストール</span><span class="sxs-lookup"><span data-stu-id="14b95-111">Obtaining and Installing a Certificate</span></span>


<span data-ttu-id="14b95-112">App-v 用の証明書を取得してインストールするシナリオは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="14b95-112">The scenarios for obtaining and installing a certificate for App-V are as follows:</span></span>

-   <span data-ttu-id="14b95-113">内部公開キー基盤 (PKI)。</span><span class="sxs-lookup"><span data-stu-id="14b95-113">Internal public key infrastructure (PKI).</span></span>

-   <span data-ttu-id="14b95-114">サードパーティ証明書の発行証明機関 (CA)。</span><span class="sxs-lookup"><span data-stu-id="14b95-114">Third-party certificate issuing certification authority (CA).</span></span>

    <span data-ttu-id="14b95-115">**注** サードパーティ CA から証明書を取得する必要がある場合は、その CA の Web サイトで利用可能なドキュメントに従ってください。</span><span class="sxs-lookup"><span data-stu-id="14b95-115">**Note** If you need to obtain a certificate from a third-party CA, follow the documentation available on that CA’s Web site.</span></span>

     

<span data-ttu-id="14b95-116">PKI インフラストラクチャが展開されている場合は、PKI 管理者に問い合わせて、このトピックで説明されている要件に準拠する証明書を取得してください。</span><span class="sxs-lookup"><span data-stu-id="14b95-116">If a PKI infrastructure has been deployed, consult with the PKI administrators to acquire a certificate that complies with the requirements described in this topic.</span></span> <span data-ttu-id="14b95-117">PKI インフラストラクチャが利用できない場合は、サードパーティ CA を使って有効な証明書を取得してください。</span><span class="sxs-lookup"><span data-stu-id="14b95-117">If a PKI infrastructure is not available, use a third-party CA to obtain a valid certificate.</span></span>

<span data-ttu-id="14b95-118">証明書を入手してインストールするための詳しいガイダンスについては、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151969> 。</span><span class="sxs-lookup"><span data-stu-id="14b95-118">For step-by-step guidance for obtaining and installing a certificate, see <https://go.microsoft.com/fwlink/?LinkId=151969>.</span></span>

## <span data-ttu-id="14b95-119">関連トピック</span><span class="sxs-lookup"><span data-stu-id="14b95-119">Related topics</span></span>


<span data-ttu-id="14b95-120">セキュリティで保護されたストリーミングをサポートするための証明書の構成[管理サーバーまたはストリーミングサーバーをサポートするための秘密キーのアクセス許可を変更する方法](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span><span class="sxs-lookup"><span data-stu-id="14b95-120">Configuring Certificates to Support Secure Streaming [How to Modify Private Key Permissions to Support Management Server or Streaming Server](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span></span>

 

 





