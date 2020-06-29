---
title: App-V Web Management Service をサポートするための証明書の構成
description: App-V Web Management Service をサポートするための証明書の構成
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10821887"
---
# <span data-ttu-id="5288c-103">App-V Web Management Service をサポートするための証明書の構成</span><span class="sxs-lookup"><span data-stu-id="5288c-103">Configuring Certificates to Support the App-V Web Management Service</span></span>


<span data-ttu-id="5288c-104">通信をセキュリティで保護するために、SSL ベースの接続をサポートするように App-v Web 管理サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5288c-104">The App-V Web Management Service must be configured to support SSL-based connections to help secure the communication.</span></span> <span data-ttu-id="5288c-105">このプロセスでは、管理サービスがインストールされている Web サーバーまたはコンピューターに、サービスまたはコンピューターに発行された証明書が必要です。</span><span class="sxs-lookup"><span data-stu-id="5288c-105">This process requires that the Web server or computer on which the Management Service is installed has a certificate issued to the service or computer.</span></span>

<span data-ttu-id="5288c-106">次のシナリオは、この目的で証明書を取得する方法を示しています。</span><span class="sxs-lookup"><span data-stu-id="5288c-106">The following scenarios illustrate how to obtain a certificate for this purpose:</span></span>

1.  <span data-ttu-id="5288c-107">会社のインフラストラクチャには、自動的に証明書をコンピューターに発行する公開キー基盤 (PKI) が用意されています。</span><span class="sxs-lookup"><span data-stu-id="5288c-107">The company infrastructure already has a public key infrastructure (PKI) in place that automatically issues certificates to computers.</span></span>

2.  <span data-ttu-id="5288c-108">会社のインフラストラクチャには、既に PKI が実装されていますが、コンピューターに対して自動的に証明書が発行されることはありません。</span><span class="sxs-lookup"><span data-stu-id="5288c-108">The company infrastructure already has a PKI in place, although it does not automatically issue certificates to computers.</span></span>

3.  <span data-ttu-id="5288c-109">会社のインフラストラクチャには、PKI は用意されていません。</span><span class="sxs-lookup"><span data-stu-id="5288c-109">The company infrastructure has no PKI in place.</span></span>

<span data-ttu-id="5288c-110">上記のそれぞれのシナリオでは、証明書を取得する方法は異なりますが、最終的な結果は同じになります。</span><span class="sxs-lookup"><span data-stu-id="5288c-110">In each of the preceding scenarios, the method for obtaining a certificate is different, but the end result is the same.</span></span> <span data-ttu-id="5288c-111">管理者は、IIS の既定の Web サイトに証明書を割り当てる必要があります。また、セキュリティで保護された通信を要求するように App-v Web Management サービスを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5288c-111">The administrator must assign a certificate to the IIS Default Web Site and configure the App-V Web Management Service to require secure communications.</span></span>

<span data-ttu-id="5288c-112">**重要** 証明書の名前は、サーバーの名前と一致する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5288c-112">**Important** The name of the certificate must match the name of the server.</span></span> <span data-ttu-id="5288c-113">証明書の共通名には完全修飾ドメイン名 (Fqdn) を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="5288c-113">It is a best practice to use fully qualified domain names (FQDNs) for the common name of the certificate.</span></span>

 

<span data-ttu-id="5288c-114">App-v では、IIS サーバーを使用して、さまざまなインフラストラクチャ構成をサポートできます。</span><span class="sxs-lookup"><span data-stu-id="5288c-114">App-V can use IIS servers to support different infrastructure configurations.</span></span> <span data-ttu-id="5288c-115">HTTPS をサポートするように IIS サーバーを構成する方法の詳細については、を参照してください <https://go.microsoft.com/fwlink/?LinkId=151972> 。</span><span class="sxs-lookup"><span data-stu-id="5288c-115">For more information about configuring IIS servers to support HTTPS, see <https://go.microsoft.com/fwlink/?LinkId=151972>.</span></span>

## <span data-ttu-id="5288c-116">関連トピック</span><span class="sxs-lookup"><span data-stu-id="5288c-116">Related topics</span></span>


[<span data-ttu-id="5288c-117">より安全な環境のために APP-V Management Console をインストールして構成する方法</span><span class="sxs-lookup"><span data-stu-id="5288c-117">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





