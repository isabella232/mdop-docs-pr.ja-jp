---
title: インストール後の安全な通信のための Management Server または Streaming Server の構成
description: インストール後の安全な通信のための Management Server または Streaming Server の構成
author: dansimp
ms.assetid: 1062a213-470b-4ae2-b12f-b3e28a6ab745
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a2713f130809c431b7444f3e928a523838597a6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821877"
---
# <span data-ttu-id="fd916-103">インストール後の安全な通信のための Management Server または Streaming Server の構成</span><span class="sxs-lookup"><span data-stu-id="fd916-103">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>


<span data-ttu-id="fd916-104">適切な証明書が、app-v 管理サーバーまたは App-v Streaming Server のインストール前にプロビジョニングされなかった場合は、最初のインストール後にセキュリティを強化するように App-v を構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd916-104">If the proper certificate was not provisioned before the installation of the App-V Management Server or the App-V Streaming Server, App-V can be configured for enhanced security after the initial installation.</span></span> <span data-ttu-id="fd916-105">App-v Management Server は、App-v 管理コンソールを使って構成できます。</span><span class="sxs-lookup"><span data-stu-id="fd916-105">You can configure the App-V Management Server through the App-V Management Console.</span></span> <span data-ttu-id="fd916-106">ただし、App-v ストリーミングサーバーはレジストリによって管理されます。</span><span class="sxs-lookup"><span data-stu-id="fd916-106">However, the App-V Streaming Server is managed through the registry.</span></span> <span data-ttu-id="fd916-107">どちらの場合も、証明書にサーバー認証用の適切な*拡張キー使用法*(EKU) を含める必要があり、ネットワークサービスは秘密キーに対する読み取りアクセス権を持っている必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd916-107">In either case, the certificate must include the proper *extended key usage* (EKU) for Server authentication and the Network Service must have read access to the private key.</span></span>

## <span data-ttu-id="fd916-108">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="fd916-108">In This Section</span></span>


<a href="" id="how-to-configure-management-server-security-post-installation"></a>[<span data-ttu-id="fd916-109">Management Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fd916-109">How to Configure Management Server Security Post-Installation</span></span>](how-to-configure-management-server-security-post-installation.md)  
<span data-ttu-id="fd916-110">アプリ-V 管理コンソールを使用して、証明書を追加し、セキュリティを強化するために App-v Management Server を構成するために、インストール後に実行できる手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd916-110">Provides a procedure that can be performed post-installation, using the App-V Management Console, to add the certificate and configure the App-V Management Server for enhanced security.</span></span>

<a href="" id="how-to-configure-streaming-server-security-post-installation"></a>[<span data-ttu-id="fd916-111">Streaming Server のインストール後のセキュリティを構成する方法</span><span class="sxs-lookup"><span data-stu-id="fd916-111">How to Configure Streaming Server Security Post-Installation</span></span>](how-to-configure-streaming-server-security-post-installation.md)  
<span data-ttu-id="fd916-112">インストール後に実行できる手順と、証明書を追加して、セキュリティ強化のために App-v ストリーミングサーバーを構成する手順について説明します。</span><span class="sxs-lookup"><span data-stu-id="fd916-112">Provides a procedure that can be performed post-installation, to add the certificate and configure the App-V Streaming Server for enhanced security.</span></span>

<a href="" id="troubleshooting-certificate-permission-issues"></a>[<span data-ttu-id="fd916-113">証明書のアクセス許可の問題のトラブルシューティング</span><span class="sxs-lookup"><span data-stu-id="fd916-113">Troubleshooting Certificate Permission Issues</span></span>](troubleshooting-certificate-permission-issues.md)  
<span data-ttu-id="fd916-114">秘密キーがネットワークサービス用の適切な ACL で構成されていない場合のトラブルシューティングのガイダンスを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd916-114">Provides troubleshooting guidance for when the private key has not been configured with the proper ACL for the Network Service.</span></span>

 

 





