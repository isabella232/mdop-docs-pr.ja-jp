---
title: MBAM 2.5 クライアントの展開計画
description: MBAM 2.5 クライアントの展開計画
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825994"
---
# <span data-ttu-id="ad7d9-103">MBAM 2.5 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="ad7d9-103">Planning for MBAM 2.5 Client Deployment</span></span>


<span data-ttu-id="ad7d9-104">Microsoft BitLocker の管理と監視 (MBAM) クライアントソフトウェアを展開するときには、組織内のコンピューターで BitLocker ドライブの暗号化を有効にするには、エンドユーザーがコンピューターを受け取るか後で行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="ad7d9-105">MBAM スタンドアロンと System Center Configuration Manager の統合トポロジのどちらの場合も、MBAM のグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-105">For both the MBAM Stand-alone and the System Center Configuration Manager Integration topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="ad7d9-106">MBAM スタンドアロントポロジを使用している場合は、エンタープライズソフトウェア展開システムを使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-106">If you are using the MBAM Stand-alone topology, we recommend that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="ad7d9-107">Configuration Manager の統合トポロジで MBAM を展開する場合は、Configuration Manager を使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-107">If you deploy MBAM with the Configuration Manager Integration topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="ad7d9-108">Configuration Manager の MBAM インストールでは、MBAM で管理できるコンピューターのコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="ad7d9-109">このコレクションには、トラステッドプラットフォームモジュール (TPM) を持たないが、Windows 8、Windows 8.1、または Windows 10 を実行しているワークステーションとデバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8, Windows 8.1, or Windows 10.</span></span>

<span data-ttu-id="ad7d9-110">**注** Configuration Manager 2007 を使用している場合、Configuration Manager 統合トポロジのインストールでは、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-110">**Note** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="ad7d9-111">コンピューターの配布後のエンドユーザーへの BitLocker ドライブ暗号化を有効にするための MBAM クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="ad7d9-111">Deploying the MBAM Client to enable BitLocker Drive Encryption after computer distribution to end users</span></span>


<span data-ttu-id="ad7d9-112">グループポリシーを構成した後、Microsoft System Center Configuration Manager または Active Directory ドメインサービス (AD DS) などのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows Installer ファイルを展開して、コンピューターをターゲットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="ad7d9-113">MBAM クライアントを展開するには、MBAM クライアントソフトウェアで提供される32ビットまたは64ビットの MbamClientSetup.exe ファイルまたは MBAMClient.msi ファイルのいずれかを使用できます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM Client software.</span></span>

<span data-ttu-id="ad7d9-114">**注** MBAM 2.5 SP1 以降、MBAM 製品には別の MSI が含まれなくなりました。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-114">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="ad7d9-115">ただし、製品に含まれている実行可能ファイル (.exe) から MSI を抽出することはできます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-115">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

<span data-ttu-id="ad7d9-116">クライアントコンピューターにコンピューターを配布した後で MBAM クライアントを展開すると、エンドユーザーに対してコンピューターを暗号化するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-116">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="ad7d9-117">このアクションでは、MBAM がデータを収集できます。このデータには、PIN とパスワードが含まれます (ポリシーによって必要な場合)。その後、暗号化処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-117">This action enables MBAM to collect the data, which includes the PIN and password (if required by policy), and then to begin the encryption process.</span></span>

<span data-ttu-id="ad7d9-118">**注** この方法では、TPM チップを使用しているコンピューターを持つエンドユーザーは、チップがアクティブになっていない場合は、TPM チップをアクティブ化して初期化するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-118">**Note** In this approach, end users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="ad7d9-119">MBAM クライアントを使用して、コンピューターの配布がエンドユーザーになる前に BitLocker ドライブ暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="ad7d9-119">Using the MBAM Client to enable BitLocker Drive Encryption before computer distribution to end users</span></span>


<span data-ttu-id="ad7d9-120">コンピューターが受信され、構成されている組織で、コンピューターに準拠している TPM チップがある場合、MBAM クライアントを使用して、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker ドライブ暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-120">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can use the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="ad7d9-121">このプロセスの利点は、すべてのコンピューターが準拠していることです。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-121">The benefit of this process is that every computer is then compliant.</span></span> <span data-ttu-id="ad7d9-122">この方法では、管理者がコンピューターを既に暗号化しているため、エンドユーザー操作に依存することはありません。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-122">This method does not rely on end-user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="ad7d9-123">このシナリオの重要な前提として、組織のポリシーによって、コンピューターがエンドユーザーに配信される前に企業の Windows イメージがインストールされます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-123">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the end user.</span></span>

<span data-ttu-id="ad7d9-124">組織で TPM チップを使用してコンピューターを暗号化する場合、管理者は、コンピューターのオペレーティングシステムボリュームを暗号化する TPM プロテクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-124">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="ad7d9-125">組織で TPM チップと PIN の保護機能を使用する必要がある場合、管理者は TPM プロテクターを使ってオペレーティングシステムボリュームを暗号化した後、エンドユーザーが初めてログオンするときに PIN を選択します。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-125">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then end users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="ad7d9-126">組織で PIN のプロテクターのみを使用することにした場合、管理者は最初にボリュームを暗号化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-126">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="ad7d9-127">エンドユーザーがログオンすると、Microsoft BitLocker の管理と監視で、PIN、または後でコンピューターを再起動するために使用する PIN とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-127">When end users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="ad7d9-128">**注** TPM プロテクターオプションの場合、管理者は、コンピューターがエンドユーザーに配信される前に TPM をアクティブ化して初期化するために、BIOS プロンプトを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-128">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the end user.</span></span>

 

## <span data-ttu-id="ad7d9-129">暗号化されたハードドライブ向け MBAM クライアントのサポート</span><span class="sxs-lookup"><span data-stu-id="ad7d9-129">MBAM Client support for Encrypted Hard Drives</span></span>


<span data-ttu-id="ad7d9-130">MBAM は、Opal と IEEE 1667 標準の TCG 仕様要件を満たす、暗号化されたハードドライブ上の BitLocker をサポートしています。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-130">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="ad7d9-131">これらのデバイスで BitLocker が有効になっている場合は、暗号化されたドライブでキーを生成し、管理機能を実行します。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-131">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="ad7d9-132">詳細については、「[暗号化されたハードドライブ](https://technet.microsoft.com/library/hh831627.aspx)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-132">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>


## <span data-ttu-id="ad7d9-133">関連トピック</span><span class="sxs-lookup"><span data-stu-id="ad7d9-133">Related topics</span></span>


[<span data-ttu-id="ad7d9-134">MBAM 2.5 の展開計画</span><span class="sxs-lookup"><span data-stu-id="ad7d9-134">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="ad7d9-135">MBAM 2.5 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="ad7d9-135">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="ad7d9-136">MBAM の提案をお寄せください。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-136">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ad7d9-137">[ここで](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)候補を追加または投票してください。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-137">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ad7d9-138">MBAM の問題については、 [Mbam TechNet フォーラムをご覧](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)ください。</span><span class="sxs-lookup"><span data-stu-id="ad7d9-138">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




