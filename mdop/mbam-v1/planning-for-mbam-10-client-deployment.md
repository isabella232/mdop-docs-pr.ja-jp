---
title: MBAM 1.0 クライアントの展開計画
description: MBAM 1.0 クライアントの展開計画
author: dansimp
ms.assetid: 3af2e7f3-134b-4ab9-9847-b07474ca6ac3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d58d6420febd2da9ee9cd4074fc8b5870285b0b4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/26/2020
ms.locfileid: "10825877"
---
# <span data-ttu-id="17566-103">MBAM 1.0 クライアントの展開計画</span><span class="sxs-lookup"><span data-stu-id="17566-103">Planning for MBAM 1.0 Client Deployment</span></span>


<span data-ttu-id="17566-104">Microsoft BitLocker 管理と監視 (MBAM) クライアントを展開するときには、組織内のコンピューターで BitLocker 暗号化を有効にすることができます。その前に、エンドユーザーがコンピューターを受信するか、その後で行うことができます。</span><span class="sxs-lookup"><span data-stu-id="17566-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="17566-105">エンドユーザーがコンピューターを受信した後に BitLocker 暗号化を有効にするには、グループポリシーを構成します。</span><span class="sxs-lookup"><span data-stu-id="17566-105">To enable BitLocker encryption after the end user receives the computer, configure Group Policy.</span></span> <span data-ttu-id="17566-106">エンドユーザーがコンピューターを受け取る前に BitLocker 暗号化を有効にするには、エンタープライズソフトウェア展開システムを使用して MBAM クライアントソフトウェアを展開します。</span><span class="sxs-lookup"><span data-stu-id="17566-106">To enable BitLocker encryption before the end user receives the computer, deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="17566-107">組織内の一方または両方の方法を使用することができます。</span><span class="sxs-lookup"><span data-stu-id="17566-107">You can use one or both methods in your organization.</span></span> <span data-ttu-id="17566-108">両方の方法を使用すると、コンプライアンス、レポート、キー回復のサポートが改善されます。</span><span class="sxs-lookup"><span data-stu-id="17566-108">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

<span data-ttu-id="17566-109">**注** MBAM クライアントシステム要件を確認するには、「 [mbam 1.0 でサポートされている構成](mbam-10-supported-configurations.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17566-109">**Note** To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="17566-110">コンピューターの配布後のエンドユーザーへの BitLocker 暗号化を有効にするための MBAM クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="17566-110">Deploying the MBAM Client to enable BitLocker encryption after computer distribution to end users</span></span>


<span data-ttu-id="17566-111">グループポリシーを構成した後、Microsoft System Center Configuration Manager 2012 または Active Directory ドメインサービスなどのエンタープライズソフトウェア展開システム製品を使用して、MBAM クライアントインストールの Windows Installer ファイルをターゲットコンピューターに展開することができます。</span><span class="sxs-lookup"><span data-stu-id="17566-111">After you configure the Group Policy, you can use an enterprise software deployment system product, such as Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services, to deploy the MBAM Client installation Windows Installer files to the target computers.</span></span> <span data-ttu-id="17566-112">2つの MBAM クライアントインストール Windows Installer ファイルは、MBAM ソフトウェアに付属の MBAMClient-64bit.msi と MBAMClient-32bit.msi です。</span><span class="sxs-lookup"><span data-stu-id="17566-112">The two MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi, which are provided with the MBAM software.</span></span> <span data-ttu-id="17566-113">MBAM グループポリシーオブジェクトの展開方法の詳細については、「 [mbam 1.0 グループポリシーオブジェクトの展開](deploying-mbam-10-group-policy-objects.md)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="17566-113">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

<span data-ttu-id="17566-114">MBAM クライアントを展開すると、コンピューターをエンドユーザーに配布した後、エンドユーザーにコンピューターの暗号化を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="17566-114">When you deploy the MBAM Client, after you distribute the computers to end users, the end users are prompted to encrypt their computers.</span></span> <span data-ttu-id="17566-115">これにより、MBAM がデータを収集し、PIN とパスワードを含めることができます。次に、暗号化処理を開始します。</span><span class="sxs-lookup"><span data-stu-id="17566-115">This lets MBAM collect the data, to include the PIN and password, and then begin the encryption process.</span></span>

<span data-ttu-id="17566-116">**注** この方法では、トラステッドプラットフォームモジュール (TPM) チップが有効になっていない場合は、そのチップをアクティブ化して初期化するようにユーザーに求めます。</span><span class="sxs-lookup"><span data-stu-id="17566-116">**Note** In this approach, users are prompted to activate and initialize the Trusted Platform Module (TPM) chip, if it has not been previously activated.</span></span>

 

## <span data-ttu-id="17566-117">MBAM クライアントを使用して、コンピューターの配布がエンドユーザーに対して実行される前に BitLocker 暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="17566-117">Using the MBAM Client to enable BitLocker encryption before computer distribution to end users</span></span>


<span data-ttu-id="17566-118">コンピューターが受信され、構成されている組織では、ユーザーデータが書き込まれる前に、各コンピューター上の BitLocker 暗号化を管理するために MBAM クライアントをインストールできます。</span><span class="sxs-lookup"><span data-stu-id="17566-118">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written on it.</span></span> <span data-ttu-id="17566-119">このプロセスの利点は、すべてのコンピューターが BitLocker 暗号化に準拠していることです。</span><span class="sxs-lookup"><span data-stu-id="17566-119">The benefit of this process is that every computer will then be compliant with the BitLocker encryption.</span></span> <span data-ttu-id="17566-120">この方法では、管理者がコンピューターを既に暗号化しているため、ユーザー操作に依存することはありません。</span><span class="sxs-lookup"><span data-stu-id="17566-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="17566-121">このシナリオを前提としているのは、組織のポリシーによって、コンピューターがユーザーに配信される前に企業の Windows イメージをインストールすることです。</span><span class="sxs-lookup"><span data-stu-id="17566-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="17566-122">組織でコンピューターの暗号化に (TPM) を使用する場合、管理者は、TPM プロテクターを使用してコンピューターのオペレーティングシステムボリュームを暗号化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17566-122">If your organization wants to use (TPM) to encrypt computers, the administrator must encrypt the operating system volume of the computer with TPM protector.</span></span> <span data-ttu-id="17566-123">組織で TPM チップと PIN の保護機能を使用する場合、管理者は、TPM プロテクターを使ってシステムボリュームを暗号化してから、ユーザーが最初にログオンしたときに PIN を選択する必要があります。</span><span class="sxs-lookup"><span data-stu-id="17566-123">If your organization wants to use the TPM chip and a PIN protector, the administrator must encrypt the system volume with the TPM protector, and then the users select a PIN the first time they log on.</span></span> <span data-ttu-id="17566-124">組織で PIN のプロテクターのみを使用することにした場合、管理者は最初にボリュームを暗号化する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="17566-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="17566-125">ユーザーがコンピューターにログオンしたとき、MBAM は、後でコンピューターを再起動するときに使用する PIN または PIN とパスワードを入力するように求めます。</span><span class="sxs-lookup"><span data-stu-id="17566-125">When users log on their computers, MBAM prompts them to provide a PIN or a PIN and a password that they will use when they restart their computer later.</span></span>

<span data-ttu-id="17566-126">**注** TPM プロテクターオプションを使用するには、コンピューターをユーザーに納入する前に、TPM をアクティブ化して初期化するための BIOS プロンプトを受け入れる必要があります。</span><span class="sxs-lookup"><span data-stu-id="17566-126">**Note** The TPM protector option requires for the administrator to accept the BIOS prompt to activate and initialize the TPM before delivering the computer to the user.</span></span>

 

## <span data-ttu-id="17566-127">関連トピック</span><span class="sxs-lookup"><span data-stu-id="17566-127">Related topics</span></span>


[<span data-ttu-id="17566-128">MBAM 1.0 の展開計画</span><span class="sxs-lookup"><span data-stu-id="17566-128">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="17566-129">MBAM 1.0 クライアントの展開</span><span class="sxs-lookup"><span data-stu-id="17566-129">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)

 

 





