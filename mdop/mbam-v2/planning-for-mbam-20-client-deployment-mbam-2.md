---
title: MBAM 2.0 クライアントの展開計画
description: MBAM 2.0 クライアントの展開計画
author: dansimp
ms.assetid: 3a92cf29-092f-4cad-bdfa-d5f6aafe554b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c3a7383188d4064247d8e493c8e6125fc24a1d2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812619"
---
# <span data-ttu-id="474b8-103">MBAM 2.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="474b8-103">Planning for MBAM 2.0 Client Deployment</span></span>


<span data-ttu-id="474b8-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを展開するときには、組織内のコンピューターで BitLocker ドライブの暗号化を有効にすることができます。これは、エンドユーザーがコンピューターを受信するか、その後に行うことができます。</span><span class="sxs-lookup"><span data-stu-id="474b8-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker drive encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="474b8-105">MBAM スタンドアロンと構成マネージャーの両方のトポロジの場合、MBAM のグループポリシー設定を構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="474b8-105">For both the MBAM Stand-alone and the Configuration Manager topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="474b8-106">MBAM スタンドアロントポロジを使用している場合は、エンタープライズソフトウェア展開システムを使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="474b8-106">If you are using the MBAM Stand-alone topology, it is recommended that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="474b8-107">Configuration Manager トポロジを使用して MBAM を展開する場合は、Configuration Manager を使用して、MBAM クライアントソフトウェアをエンドユーザーコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="474b8-107">If you deploy MBAM with the Configuration Manager topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="474b8-108">Configuration Manager の MBAM インストールでは、MBAM で管理できるコンピューターのコレクションが作成されます。</span><span class="sxs-lookup"><span data-stu-id="474b8-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="474b8-109">このコレクションには、トラステッドプラットフォームモジュール (TPM) を持たないが、Windows 8 を実行しているワークステーションとデバイスが含まれます。</span><span class="sxs-lookup"><span data-stu-id="474b8-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8.</span></span>

<span data-ttu-id="474b8-110">**注** Configuration Manager 2007 を使用している場合、統合構成マネージャーの MBAM インストールでは、Windows To Go はサポートされません。</span><span class="sxs-lookup"><span data-stu-id="474b8-110">**Note** Windows To Go is not supported for integrated Configuration Manager installations of MBAM if you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="474b8-111">コンピューターの配布後のエンドユーザーへの BitLocker 暗号化を有効にするための MBAM クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="474b8-111">Deploying the MBAM Client to Enable BitLocker Encryption After Computer Distribution to End Users</span></span>


<span data-ttu-id="474b8-112">グループポリシーを構成した後、Microsoft System Center Configuration Manager または Active Directory ドメインサービス (AD DS) などのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows Installer ファイルを展開して、コンピューターをターゲットにすることができます。</span><span class="sxs-lookup"><span data-stu-id="474b8-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="474b8-113">MBAM クライアントを展開するには、32ビットまたは64ビットの MbamClientSetup.exe ファイルまたは MBAMClient.msi ファイルのいずれかを使用できます。これらは、MBAM ソフトウェアで提供されます。</span><span class="sxs-lookup"><span data-stu-id="474b8-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM software.</span></span>

<span data-ttu-id="474b8-114">クライアントコンピューターにコンピューターを配布した後で MBAM クライアントを展開すると、エンドユーザーに対してコンピューターを暗号化するように求められます。</span><span class="sxs-lookup"><span data-stu-id="474b8-114">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="474b8-115">これにより、MBAM がデータを収集することができます。これには、PIN とパスワードが含まれています。その後、暗号化処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="474b8-115">This enables MBAM to collect the data, which includes the PIN and password, and then to begin the encryption process.</span></span>

<span data-ttu-id="474b8-116">**注** この方法では、TPM チップを使用しているコンピューターを使っているユーザーは、チップがアクティブになっていない場合は、TPM チップのアクティブ化と初期化を行うように求められます。</span><span class="sxs-lookup"><span data-stu-id="474b8-116">**Note** In this approach, users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="474b8-117">MBAM クライアントを使用して、コンピューターの配布がエンドユーザーに対して実行される前に BitLocker 暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="474b8-117">Using the MBAM Client to Enable BitLocker Encryption Before Computer Distribution to End Users</span></span>


<span data-ttu-id="474b8-118">コンピューターが受信され、構成されている組織で、コンピューターが対応する TPM チップを使用している場合、MBAM クライアントをインストールして、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理することができます。</span><span class="sxs-lookup"><span data-stu-id="474b8-118">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="474b8-119">このプロセスには、すべてのコンピューターが BitLocker 暗号化準拠であるという利点があります。</span><span class="sxs-lookup"><span data-stu-id="474b8-119">The benefit of this process is that every computer will then be BitLocker encryption-compliant.</span></span> <span data-ttu-id="474b8-120">この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。</span><span class="sxs-lookup"><span data-stu-id="474b8-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="474b8-121">このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="474b8-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="474b8-122">組織で TPM チップを使用してコンピューターを暗号化する場合、管理者は、コンピューターのオペレーティングシステムボリュームを暗号化する TPM プロテクターを追加します。</span><span class="sxs-lookup"><span data-stu-id="474b8-122">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="474b8-123">組織で TPM チップと PIN の保護機能を使用する必要がある場合、管理者は TPM プロテクターを使ってオペレーティングシステムボリュームを暗号化し、ユーザーが初めてログオンするときに PIN を選択します。</span><span class="sxs-lookup"><span data-stu-id="474b8-123">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="474b8-124">組織で PIN のプロテクターのみを使用することにした場合、管理者は最初にボリュームを暗号化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="474b8-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="474b8-125">ユーザーがログオンすると、Microsoft BitLocker の管理と監視によって、PIN、または後でコンピューターを再起動するために使用する PIN とパスワードを入力するように求められます。</span><span class="sxs-lookup"><span data-stu-id="474b8-125">When users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="474b8-126">**注** TPM プロテクターオプションの場合、管理者は、コンピューターがユーザーに配信される前に TPM をアクティブ化して初期化するために、BIOS プロンプトを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="474b8-126">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the user.</span></span>

 

## <span data-ttu-id="474b8-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="474b8-127">Related topics</span></span>


[<span data-ttu-id="474b8-128">MBAM 2.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="474b8-128">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="474b8-129">MBAM 2.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="474b8-129">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

 

 





