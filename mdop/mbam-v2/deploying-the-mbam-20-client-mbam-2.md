---
title: MBAM 2.0 クライアントの展開
description: MBAM 2.0 クライアントの展開
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10823447"
---
# <span data-ttu-id="2708f-103">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="2708f-103">Deploying the MBAM 2.0 Client</span></span>


<span data-ttu-id="2708f-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを使うと、管理者は企業内のコンピューター上の BitLocker ドライブ暗号化を強制および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="2708f-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="2708f-105">Active Directory ドメインサービスなどの電子ソフトウェア配布システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化することによって、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="2708f-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="2708f-106">Microsoft BitLocker の管理と監視クライアントを展開するときには、組織内のコンピューターで BitLocker 暗号化を有効にするには、エンドユーザーがコンピューターを受信する前に、またはグループポリシーを構成し、エンタープライズソフトウェア展開システムを使って MBAM クライアントソフトウェアを展開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="2708f-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="2708f-107">デスクトップまたはノート Pc に MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="2708f-107">Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="2708f-108">グループポリシーを構成した後、Microsoft System Center Configuration Manager 2012 または Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="2708f-108">After configuring Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="2708f-109">クライアントを展開するには、32ビット版または64ビット版の MbamClientSetup.exe ファイル、または MBAM ソフトウェアで提供されている32ビットまたは64ビットの MBAMClient.msi ファイルを使用します。</span><span class="sxs-lookup"><span data-stu-id="2708f-109">You can deploy the client by using either the 32-bit or 64-bit MbamClientSetup.exe files, or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM software.</span></span> <span data-ttu-id="2708f-110">MBAM グループポリシーオブジェクトの展開の詳細については、「 [mbam 2.0 グループポリシーオブジェクトの展開](deploying-mbam-20-group-policy-objects-mbam-2.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2708f-110">For more information about deploying MBAM Group Policy Objects, see [Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md).</span></span>

[<span data-ttu-id="2708f-111">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="2708f-111">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## <span data-ttu-id="2708f-112">Windows 展開の一部として MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="2708f-112">Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="2708f-113">コンピューターが受信され、構成されている組織では、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理するために MBAM クライアントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="2708f-113">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="2708f-114">このプロセスの利点は、すべてのコンピューターが BitLocker 暗号化に準拠していることです。</span><span class="sxs-lookup"><span data-stu-id="2708f-114">The benefit of this process is that every computer is then BitLocker encryption compliant.</span></span> <span data-ttu-id="2708f-115">この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。</span><span class="sxs-lookup"><span data-stu-id="2708f-115">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="2708f-116">このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="2708f-116">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="2708f-117">グループポリシーが PIN を要求するように構成されている場合、ユーザーはグループポリシーを受信した後に PIN を設定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="2708f-117">If the Group Policy has been configured to require a PIN, users are prompted to set a PIN after they receive the Group Policy.</span></span>

[<span data-ttu-id="2708f-118">Windows 展開の一部として MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="2708f-118">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## <span data-ttu-id="2708f-119">コマンド ラインを使用して MBAM クライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2708f-119">How to Use a Command Line to Install the MBAM Client</span></span>


<span data-ttu-id="2708f-120">このセクションでは、コマンドラインを使用して MBAM クライアントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="2708f-120">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="2708f-121">コマンド ラインを使用して MBAM クライアントをインストールする方法</span><span class="sxs-lookup"><span data-stu-id="2708f-121">How to Use a Command Line to Install the MBAM Client</span></span>](how-to-use-a-command-line-to-install-the-mbam-client.md)

## <span data-ttu-id="2708f-122">MBAM クライアントを展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="2708f-122">Other Resources for Deploying the MBAM Client</span></span>


<span data-ttu-id="2708f-123">[Mbam 2.0 を展開](deploying-mbam-20-mbam-2.md)[する Mbam 2.0 クライアント展開の計画](planning-for-mbam-20-client-deployment-mbam-2.md)</span><span class="sxs-lookup"><span data-stu-id="2708f-123">[Deploying MBAM 2.0](deploying-mbam-20-mbam-2.md)[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)</span></span>

 

 





