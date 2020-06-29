---
title: APP-V Management Server または Streaming Server をサポートするための証明書の構成
description: APP-V Management Server または Streaming Server をサポートするための証明書の構成
author: dansimp
ms.assetid: 2f24e550-585e-4b7e-b486-22a3f181f543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e537244b24d7303af550b3ced8286ba2680009e7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821897"
---
# <span data-ttu-id="5e2a8-103">APP-V Management Server または Streaming Server をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="5e2a8-103">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>


<span data-ttu-id="5e2a8-104">証明書のプロビジョニングプロセスを完了して、App-v のインストールをサポートするための秘密キーのアクセス許可を変更したら、管理サーバーまたはストリーミングサーバーのセットアップを起動できます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-104">After you complete the certificate provisioning process and change the private key permissions to support the App-V installation, you can launch the setup of the Management Server or the Streaming Server.</span></span> <span data-ttu-id="5e2a8-105">セットアップ中に、セットアッププログラムを実行する前に証明書がプロビジョニングされた場合、ウィザードによって [**接続セキュリティモード**] 画面に証明書が表示され、既定では [強化された**セキュリティを使用する**] チェックボックスがオンになっています。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-105">During setup, if a certificate is provisioned before running the setup program, the wizard displays the certificate in the **Connection Security Mode** screen and, by default, the **Use enhanced security** check box is selected.</span></span>

<span data-ttu-id="5e2a8-106">**注** このサーバーに対して複数の証明書がプロビジョニングされている場合は、App-v 用に構成された証明書を選びます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-106">**Note** Select the certificate that was configured for App-V if there is more than one certificate provisioned for this server.</span></span>

 

<span data-ttu-id="5e2a8-107">**重要** バージョン4.2 からバージョン4.5 にアップグレードする場合、セットアップには強化された**セキュリティを使用**するオプションがあります。ただし、このオプションを選ぶと、RTSP 経由のストリーミングが無効になりません。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-107">**Important** When upgrading from version 4.2 to version 4.5, the setup has an option for **Use enhanced security**; however, selecting this option will not disable streaming over RTSP.</span></span> <span data-ttu-id="5e2a8-108">インストール後に RTSP を無効にするには、管理コンソールを使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-108">You must use the Management Console to disable RTSP after installation.</span></span>

 

<span data-ttu-id="5e2a8-109">サービスがクライアント通信に使用する TCP ポートを選択します。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-109">Select the TCP port that the service will use for client communications.</span></span> <span data-ttu-id="5e2a8-110">既定のポートは TCP 322 です。ただし、環境のポートをカスタムポートに変更することはできます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-110">The default port is TCP 322; however, you can change the port to a custom port for your environment.</span></span>

<span data-ttu-id="5e2a8-111">ウィザードの残りの手順は、強化された**セキュリティ**機能を使わずに、app-v 管理またはストリーミングサーバーを展開している場合と同じです。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-111">The remaining steps of the wizard are the same as if you were deploying an App-V Management or Streaming Server without using the **Enhanced security** feature.</span></span>

## <span data-ttu-id="5e2a8-112">NLB 環境用の証明書を構成する</span><span class="sxs-lookup"><span data-stu-id="5e2a8-112">Configuring Certificates for NLB Environments</span></span>


<span data-ttu-id="5e2a8-113">大企業をサポートするために、多くの場合、管理サーバーはネットワーク負荷分散 (NLB) クラスターに配置され、多数の接続をサポートします。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-113">To support large enterprises, often the Management Server is placed into a Network Load Balancing (NLB) cluster to support the large number of connections.</span></span> <span data-ttu-id="5e2a8-114">これには、1つの管理サーバーとして表示される少なくとも2つの管理サーバーが必要です。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-114">This requires at least two Management Servers that appear to be a single Management Server.</span></span> <span data-ttu-id="5e2a8-115">複数の管理サーバーで NLB クラスターを使用している環境では、NLB クラスターに使用される証明書の詳細構成が必要です。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-115">When your environment uses an NLB cluster with several Management Servers, you need an advanced configuration of the certificate used for the NLB cluster.</span></span>

<span data-ttu-id="5e2a8-116">App-v 証明書は、Windows Server2003 を実行しているコンピューターで構成されている証明機関 (CA) に送信されます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-116">The App-V certificate is submitted to a certification authority (CA) that is configured on a computer running Windows Server2003.</span></span> <span data-ttu-id="5e2a8-117">SAN では、NLB クラスターを構成する最大32のサーバーが存在する可能性があるため、実際のコンピューター名とは異なるドメインネームシステム (DNS) 名を使って、特定の管理サーバー NLB クラスターホスト名に接続できます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-117">The SAN lets you connect to a specific Management Server NLB cluster host name by using a Domain Name System (DNS) name that might differ from the actual computer names, because there can be up to 32 servers that comprise the NLB cluster.</span></span>

<span data-ttu-id="5e2a8-118">この構成は、NLB クラスターを使用する場合にのみ必要です。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-118">This configuration is necessary only when using an NLB cluster.</span></span> <span data-ttu-id="5e2a8-119">クライアントがサーバーに接続すると、個々のサーバーの FQDN ではなく、NLB クラスターの完全修飾ドメイン名 (FQDN) を使って接続されます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-119">When the client connects to the server, it will connect using the fully qualified domain name (FQDN) of the NLB cluster and not the FQDN of an individual server.</span></span> <span data-ttu-id="5e2a8-120">クラスターのサーバーノードの FQDN で SAN プロパティを追加しないと、証明書の共通名がサーバー名と一致しないため、すべてのクライアント接続が拒否されます。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-120">If you do not add the SAN property with the FQDN of the server nodes in the cluster, all client connections are refused because the common name of the certificate won’t match the server name.</span></span>

<span data-ttu-id="5e2a8-121">SAN 属性を使った証明書の構成の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=133228> 。</span><span class="sxs-lookup"><span data-stu-id="5e2a8-121">For more detailed information about configuring certificates with the SAN attribute, see <https://go.microsoft.com/fwlink/?LinkId=133228>.</span></span>

## <span data-ttu-id="5e2a8-122">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5e2a8-122">Related topics</span></span>


[<span data-ttu-id="5e2a8-123">安全なストリーミングをサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="5e2a8-123">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)

[<span data-ttu-id="5e2a8-124">Management Server または Streaming Server をサポートするために秘密キーのアクセス許可を変更する方法</span><span class="sxs-lookup"><span data-stu-id="5e2a8-124">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





