---
title: MBAM 1.0 クライアントの展開
description: MBAM 1.0 クライアントの展開
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10822904"
---
# <span data-ttu-id="c0a19-103">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="c0a19-103">Deploying the MBAM 1.0 Client</span></span>


<span data-ttu-id="c0a19-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="c0a19-105">BitLocker クライアントを組織に統合するには、Active Directory ドメインサービスなどのツールを使用してクライアントを展開するか、または最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化します。</span><span class="sxs-lookup"><span data-stu-id="c0a19-105">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="c0a19-106">MBAM クライアントを展開するタイミングに応じて、組織内のコンピューター上で、またはエンドユーザーがコンピューターを受信した後に BitLocker 暗号化を有効にすることができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-106">Depending on when you deploy the MBAM Client, you can enable BitLocker encryption on a computer in your organization either before or after the end user receives the computer.</span></span> <span data-ttu-id="c0a19-107">このタイミングを制御するには、グループポリシーを構成し、エンタープライズソフトウェア展開システムを使用して MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="c0a19-107">To control this timing, you configure Group Policy and deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="c0a19-108">組織では、これらの方法のいずれかまたは両方を使用できます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-108">You can use either or both of these methods in your organization.</span></span> <span data-ttu-id="c0a19-109">両方の方法を使用すると、コンプライアンス、レポート、キー回復のサポートが改善されます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-109">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

## <span data-ttu-id="c0a19-110">デスクトップまたはノート pc に MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="c0a19-110">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="c0a19-111">グループポリシーを構成した後で、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-111">After you have configured Group Policy, you can deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="c0a19-112">これは、Microsoft System Center 2012 構成マネージャーまたは Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して行うことができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-112">You can do this by use of an enterprise software deployment system product like Microsoft System Center 2012 Configuration Manager or Active Directory Domain Services.</span></span> <span data-ttu-id="c0a19-113">使用できる MBAM クライアントインストール用の2つの Windows インストーラーファイルは、MBAMClient-64bit.msi と MBAMClient-32bit.msi です。</span><span class="sxs-lookup"><span data-stu-id="c0a19-113">The two available MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi.</span></span> <span data-ttu-id="c0a19-114">これらのファイルは、MBAM ソフトウェアで提供されます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-114">These files are provided with the MBAM software.</span></span> <span data-ttu-id="c0a19-115">MBAM グループポリシーオブジェクトの展開方法の詳細については、「 [mbam 1.0 グループポリシーオブジェクトの展開](deploying-mbam-10-group-policy-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="c0a19-115">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

[<span data-ttu-id="c0a19-116">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="c0a19-116">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## <span data-ttu-id="c0a19-117">Windows 展開の一部として MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="c0a19-117">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="c0a19-118">組織によっては、新しいコンピューターを1か所で受信して構成する場合があります。</span><span class="sxs-lookup"><span data-stu-id="c0a19-118">In some organizations, new computers are received and configured centrally.</span></span> <span data-ttu-id="c0a19-119">この状況では、管理者は MBAM クライアントをインストールして、ユーザーデータがコンピューターに書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-119">This situation enables administrators to install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to the computer.</span></span> <span data-ttu-id="c0a19-120">この方法では、管理者がエンドユーザーの操作に依存せずに操作を実行するため、コンピューターが適切に暗号化されていることを確認することができます。</span><span class="sxs-lookup"><span data-stu-id="c0a19-120">This approach helps to ensure that computers are properly encrypted because the administrator performs the action without reliance on end-user action.</span></span> <span data-ttu-id="c0a19-121">このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="c0a19-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

[<span data-ttu-id="c0a19-122">Windows 展開の一部として MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="c0a19-122">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## <span data-ttu-id="c0a19-123">MBAM クライアントを展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="c0a19-123">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="c0a19-124">MBAM 1.0 の展開</span><span class="sxs-lookup"><span data-stu-id="c0a19-124">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

[<span data-ttu-id="c0a19-125">MBAM 1.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="c0a19-125">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

 

 





