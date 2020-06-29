---
title: MBAM 2.5 クライアントの展開
description: MBAM 2.5 クライアントの展開
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10826277"
---
# <span data-ttu-id="435db-103">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="435db-103">Deploying the MBAM 2.5 Client</span></span>


<span data-ttu-id="435db-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントソフトウェアを使用すると、管理者は企業内のコンピューターで BitLocker ドライブ暗号化を適用および監視することができます。</span><span class="sxs-lookup"><span data-stu-id="435db-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client software enables administrators to enforce and monitor BitLocker Drive Encryption on computers in the enterprise.</span></span> <span data-ttu-id="435db-105">Active Directory ドメインサービスなどの電子ソフトウェア配布システムを通じてクライアントを展開するか、最初のイメージングプロセスの一部としてクライアントコンピューターを直接暗号化することによって、BitLocker クライアントを組織に統合することができます。</span><span class="sxs-lookup"><span data-stu-id="435db-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="435db-106">Microsoft BitLocker の管理と監視クライアントソフトウェアを展開するときには、組織内のコンピューターで BitLocker ドライブの暗号化を有効にすることができます。これは、エンドユーザーがコンピューターを受け取る前に、またはエンタープライズソフトウェア展開システムを使用して、グループポリシーを構成して、MBAM クライアントソフトウェアを展開することです。</span><span class="sxs-lookup"><span data-stu-id="435db-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="435db-107">デスクトップまたはノート pc に MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="435db-107">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="435db-108">グループポリシー設定を構成したら、MicrosoftSystemCenter2012 ConfigurationManager や Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows インストーラーファイルをターゲットコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="435db-108">After configuring Group Policy settings, you can use an enterprise software deployment system product like MicrosoftSystemCenter2012 ConfigurationManager or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="435db-109">MBAM クライアントソフトウェアで提供される、32ビットまたは64ビットの MbamClientSetup.exe ファイル、または32ビットまたは64ビットの MBAMClient.msi ファイルを使うことができます。</span><span class="sxs-lookup"><span data-stu-id="435db-109">You can use either the 32-bit or 64-bit MbamClientSetup.exe files or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM Client software.</span></span> <span data-ttu-id="435db-110">MBAM グループポリシー設定の展開の詳細については、「 [mbam 2.5 グループポリシーオブジェクトの展開](deploying-mbam-25-group-policy-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="435db-110">For more information about deploying MBAM Group Policy settings, see [Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md).</span></span>

<span data-ttu-id="435db-111">**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="435db-111">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="435db-112">ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。</span><span class="sxs-lookup"><span data-stu-id="435db-112">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

[<span data-ttu-id="435db-113">MBAM クライアントをデスクトップまたはノート PC に展開する方法</span><span class="sxs-lookup"><span data-stu-id="435db-113">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## <span data-ttu-id="435db-114">Windows 展開の一部として MBAM クライアントを展開する</span><span class="sxs-lookup"><span data-stu-id="435db-114">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="435db-115">コンピューターが送受信され、集中して構成されている組織では、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker ドライブ暗号化を管理するために MBAM クライアントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="435db-115">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="435db-116">このプロセスの利点は、すべてのコンピューターが BitLocker ドライブ暗号化に準拠していることです。</span><span class="sxs-lookup"><span data-stu-id="435db-116">The benefit of this process is that every computer is then BitLocker Drive Encryption-compliant.</span></span> <span data-ttu-id="435db-117">この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。</span><span class="sxs-lookup"><span data-stu-id="435db-117">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="435db-118">このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="435db-118">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="435db-119">グループポリシー設定が PIN を要求するように構成されている場合、ユーザーはポリシーを受信した後に PIN を設定するように求められます。</span><span class="sxs-lookup"><span data-stu-id="435db-119">If the Group Policy settings has been configured to require a PIN, users are prompted to set a PIN after they receive the policy.</span></span>

[<span data-ttu-id="435db-120">Windows 展開の一部として MBAM を使用して BitLocker を有効にする方法</span><span class="sxs-lookup"><span data-stu-id="435db-120">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## <span data-ttu-id="435db-121">コマンドラインを使用して MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="435db-121">How to deploy the MBAM Client by using a command line</span></span>


<span data-ttu-id="435db-122">このセクションでは、コマンドラインを使用して MBAM クライアントをインストールする方法について説明します。</span><span class="sxs-lookup"><span data-stu-id="435db-122">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="435db-123">コマンド ラインを使用して MBAM クライアントを展開する方法</span><span class="sxs-lookup"><span data-stu-id="435db-123">How to Deploy the MBAM Client by Using a Command Line</span></span>](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## <span data-ttu-id="435db-124">MBAM クライアントを展開するためのその他のリソース</span><span class="sxs-lookup"><span data-stu-id="435db-124">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="435db-125">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="435db-125">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)



## <span data-ttu-id="435db-126">関連トピック</span><span class="sxs-lookup"><span data-stu-id="435db-126">Related topics</span></span>


[<span data-ttu-id="435db-127">MBAM 2.5 の展開</span><span class="sxs-lookup"><span data-stu-id="435db-127">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="435db-128">MBAM 2.5 の計画</span><span class="sxs-lookup"><span data-stu-id="435db-128">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 
## <span data-ttu-id="435db-129">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="435db-129">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="435db-130">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="435db-130">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="435db-131">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="435db-131">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





